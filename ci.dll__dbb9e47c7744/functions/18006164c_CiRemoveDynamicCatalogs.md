# CiRemoveDynamicCatalogs

- ea: `0x18006164c`
- end: `0x18006188b`
- name: `CiRemoveDynamicCatalogs`
- size: `575`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005eb20`

## callees

- `0x18000ecb4`
- `0x18001508c`
- `0x18001d100`
- `0x18002bf50`
- `0x18006164c`
- `0x18006194c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x18006169a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18006169a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006179b`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006179b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006183a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006183a`
- `ntoskrnl!ExAllocatePool2` at `0x1800616b9`
- `ntoskrnl!ExAllocatePool2` at `0x1800616b9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800617fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061812`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006185f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800617fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061812`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006185f`
- `ntoskrnl!ExGetPreviousMode` at `0x18006166d`
- `ntoskrnl!ExGetPreviousMode` at `0x18006166d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180061846`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180061846`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1800616e9`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1800616e9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800617c1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1800617c1`

## pseudocode

```c
__int64 __fastcall CiRemoveDynamicCatalogs(void *Src, size_t Size)
{
  size_t v2; // r14
  KPROCESSOR_MODE PreviousMode; // di
  void *Pool2; // rsi
  HRESULT v6; // edi
  USHORT MaximumLength; // dx
  __int64 *i; // rbx
  __int64 v9; // rax
  __int64 **v10; // rcx
  UNICODE_STRING pusResult; // [rsp+28h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-30h] BYREF

  v2 = (unsigned int)Size;
  DestinationString = 0;
  PreviousMode = ExGetPreviousMode();
  if ( !Src || (unsigned int)(v2 - 3) > 0xFFFB )
    return 3221225476LL;
  KeEnterCriticalRegion();
  CipTryAcquireCatalogStoreLockExclusive();
  Pool2 = (void *)ExAllocatePool2(259, (unsigned int)v2, 1919109443);
  if ( Pool2 )
  {
    if ( PreviousMode )
    {
      if ( ((unsigned __int8)Src & 1) != 0 )
        ExRaiseDatatypeMisalignment();
      RtlCopyFromUser(Pool2, Src, v2);
    }
    else
    {
      RtlCopyVolatileMemory(Pool2, Src, v2);
    }
    *(_QWORD *)&pusResult.Length = 0;
    pusResult.Buffer = (PWSTR)Pool2;
    v6 = ULongToUShort(v2, &pusResult.MaximumLength);
    if ( v6 >= 0 )
    {
      MaximumLength = pusResult.MaximumLength;
      if ( pusResult.Buffer[((unsigned __int64)pusResult.MaximumLength >> 1) - 1] == 92 )
        MaximumLength = pusResult.MaximumLength - 2;
      pusResult.Length = MaximumLength;
      v6 = RtlUnicodeStringValidateEx(&pusResult, 0);
      if ( v6 >= 0 )
      {
        for ( i = (__int64 *)qword_180049780; i != &qword_180049780; i = (__int64 *)*i )
        {
          if ( (*(_DWORD *)(i - 3) & 0x10) != 0 && *((_WORD *)i - 8) > 0x72u )
          {
            RtlInitUnicodeString(&DestinationString, (PCWSTR)*(i - 1));
            DestinationString.Length = *((_WORD *)i - 8) - 114;
            if ( RtlEqualUnicodeString(&DestinationString, &pusResult, 1u) )
            {
              v9 = *i;
              if ( *(__int64 **)(*i + 8) != i || (v10 = (__int64 **)i[1], *v10 != i) )
                __fastfail(3u);
              *v10 = (__int64 *)v9;
              *(_QWORD *)(v9 + 8) = v10;
              ExFreePoolWithTag((PVOID)*(i - 1), 0x72634943u);
              ExFreePoolWithTag(i - 3, 0x72634943u);
              break;
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -1073741801;
  }
  ExReleasePushLockExclusiveEx(&g_CatalogStoreListLock, 0);
  KeLeaveCriticalRegion();
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x72634943u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006164c  mov     [rsp+arg_8], rbx
0x180061651  mov     [rsp+arg_18], rsi
0x180061656  push    rdi
0x180061657  push    r12
0x180061659  push    r14
0x18006165b  sub     rsp, 50h
0x18006165f  mov     r14d, edx
0x180061662  mov     rbx, rcx
0x180061665  xorps   xmm0, xmm0
0x180061668  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18006166d  call    cs:__imp_ExGetPreviousMode
0x180061674  nop     dword ptr [rax+rax+00h]
0x180061679  mov     dil, al
0x18006167c  test    rbx, rbx
0x18006167f  jz      loc_18006186F
0x180061685  lea     r8d, [r14-3]
0x180061689  cmp     r8d, 0FFFBh
0x180061690  ja      loc_18006186F
0x180061696  mov     [rsp+68h+arg_0], al
0x18006169a  call    cs:__imp_KeEnterCriticalRegion
0x1800616a1  nop     dword ptr [rax+rax+00h]
0x1800616a6  call    CipTryAcquireCatalogStoreLockExclusive
0x1800616ab  mov     r8d, 72634943h
0x1800616b1  mov     edx, r14d
0x1800616b4  mov     ecx, 103h
0x1800616b9  call    cs:__imp_ExAllocatePool2
0x1800616c0  nop     dword ptr [rax+rax+00h]
0x1800616c5  mov     rsi, rax
0x1800616c8  mov     [rsp+68h+arg_10], rax
0x1800616d0  test    rax, rax
0x1800616d3  jnz     short loc_1800616DF
0x1800616d5  mov     edi, 0C0000017h
0x1800616da  jmp     loc_180061831
0x1800616df  test    dil, dil
0x1800616e2  jz      short loc_18006170A
0x1800616e4  test    bl, 1
0x1800616e7  jz      short loc_1800616F5
0x1800616e9  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1800616f0  nop     dword ptr [rax+rax+00h]
0x1800616f5  test    dil, dil
0x1800616f8  jz      short loc_18006170A
0x1800616fa  mov     r8, r14; Size
0x1800616fd  mov     rdx, rbx; Src
0x180061700  mov     rcx, rsi; void *
0x180061703  call    RtlCopyFromUser
0x180061708  jmp     short loc_180061719
0x18006170a  mov     r8, r14; Size
0x18006170d  mov     rdx, rbx; Src
0x180061710  mov     rcx, rsi; void *
0x180061713  call    RtlCopyVolatileMemory
0x180061718  nop
0x180061719  mov     qword ptr [rsp+68h+pusResult], 0
0x180061722  mov     [rsp+68h+var_38], rsi
0x180061727  lea     rdx, [rsp+68h+pusResult+2]; pusResult
0x18006172c  mov     ecx, r14d; ulOperand
0x18006172f  call    ULongToUShort
0x180061734  mov     edi, eax
0x180061736  test    eax, eax
0x180061738  js      loc_180061831
0x18006173e  movzx   edx, [rsp+68h+pusResult+2]
0x180061743  mov     ecx, edx
0x180061745  shr     rcx, 1
0x180061748  mov     rax, [rsp+68h+var_38]
0x18006174d  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180061753  jnz     short loc_180061759
0x180061755  sub     dx, 2
0x180061759  mov     [rsp+68h+pusResult], dx
0x18006175e  xor     edx, edx; dwFlags
0x180061760  lea     rcx, [rsp+68h+pusResult]; SourceString
0x180061765  call    RtlUnicodeStringValidateEx
0x18006176a  mov     edi, eax
0x18006176c  test    eax, eax
0x18006176e  js      loc_180061831
0x180061774  mov     rbx, cs:qword_180049780
0x18006177b  lea     r12, qword_180049780
0x180061782  jmp     short loc_1800617D4
0x180061784  mov     eax, [rbx-18h]
0x180061787  test    al, 10h
0x180061789  jz      short loc_1800617D1
0x18006178b  cmp     word ptr [rbx-10h], 72h ; 'r'
0x180061790  jbe     short loc_1800617D1
0x180061792  mov     rdx, [rbx-8]; SourceString
0x180061796  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18006179b  call    cs:__imp_RtlInitUnicodeString
0x1800617a2  nop     dword ptr [rax+rax+00h]
0x1800617a7  movzx   eax, word ptr [rbx-10h]
0x1800617ab  sub     ax, 72h ; 'r'
0x1800617af  mov     [rsp+68h+DestinationString.Length], ax
0x1800617b4  mov     r8b, 1; CaseInSensitive
0x1800617b7  lea     rdx, [rsp+68h+pusResult]; String2
0x1800617bc  lea     rcx, [rsp+68h+DestinationString]; String1
0x1800617c1  call    cs:__imp_RtlEqualUnicodeString
0x1800617c8  nop     dword ptr [rax+rax+00h]
0x1800617cd  test    al, al
0x1800617cf  jnz     short loc_1800617DB
0x1800617d1  mov     rbx, [rbx]
0x1800617d4  cmp     rbx, r12
0x1800617d7  jnz     short loc_180061784
0x1800617d9  jmp     short loc_180061831
0x1800617db  mov     rax, [rbx]
0x1800617de  cmp     [rax+8], rbx
0x1800617e2  jnz     short loc_180061820
0x1800617e4  mov     rcx, [rbx+8]
0x1800617e8  cmp     [rcx], rbx
0x1800617eb  jnz     short loc_180061820
0x1800617ed  mov     [rcx], rax
0x1800617f0  mov     [rax+8], rcx
0x1800617f4  mov     edx, 72634943h; Tag
0x1800617f9  mov     rcx, [rbx-8]; P
0x1800617fd  call    cs:__imp_ExFreePoolWithTag
0x180061804  nop     dword ptr [rax+rax+00h]
0x180061809  mov     edx, 72634943h; Tag
0x18006180e  lea     rcx, [rbx-18h]; P
0x180061812  call    cs:__imp_ExFreePoolWithTag
0x180061819  nop     dword ptr [rax+rax+00h]
0x18006181e  jmp     short loc_180061831
0x180061820  mov     ecx, 3
0x180061825  int     29h; Win8: RtlFailFast(ecx)
0x180061827  mov     edi, eax
0x180061829  mov     rsi, [rsp+68h+arg_10]
0x180061831  xor     edx, edx
0x180061833  lea     rcx, g_CatalogStoreListLock
0x18006183a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180061841  nop     dword ptr [rax+rax+00h]
0x180061846  call    cs:__imp_KeLeaveCriticalRegion
0x18006184d  nop     dword ptr [rax+rax+00h]
0x180061852  test    rsi, rsi
0x180061855  jz      short loc_18006186B
0x180061857  mov     edx, 72634943h; Tag
0x18006185c  mov     rcx, rsi; P
0x18006185f  call    cs:__imp_ExFreePoolWithTag
0x180061866  nop     dword ptr [rax+rax+00h]
0x18006186b  mov     eax, edi
0x18006186d  jmp     short loc_180061874
0x18006186f  mov     eax, 0C0000004h
0x180061874  lea     r11, [rsp+68h+var_18]
0x180061879  mov     rbx, [r11+28h]
0x18006187d  mov     rsi, [r11+38h]
0x180061881  mov     rsp, r11
0x180061884  pop     r14
0x180061886  pop     r12
0x180061888  pop     rdi
0x180061889  retn
0x1800e9c61  push    rbp
0x1800e9c63  sub     rsp, 20h
0x1800e9c67  mov     rbp, rdx
0x1800e9c6a  xor     eax, eax
0x1800e9c6c  cmp     [rbp+70h], al
0x1800e9c6f  setnz   al
0x1800e9c72  mov     [rbp+20h], eax
0x1800e9c75  mov     eax, [rbp+20h]
0x1800e9c78  add     rsp, 20h
0x1800e9c7c  pop     rbp
0x1800e9c7d  retn
```
