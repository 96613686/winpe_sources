# CiRemoveDynamicCatalogs

- ea: `0x1800617b0`
- end: `0x1800619ef`
- name: `CiRemoveDynamicCatalogs`
- size: `575`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005eac0`

## callees

- `0x18000ecc4`
- `0x1800150ec`
- `0x18001d1b8`
- `0x18002c100`
- `0x1800617b0`
- `0x180061ab0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800617fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800617fe`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800618ff`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800618ff`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006199e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006199e`
- `ntoskrnl!ExAllocatePool2` at `0x18006181d`
- `ntoskrnl!ExAllocatePool2` at `0x18006181d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061961`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061976`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800619c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061961`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061976`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800619c3`
- `ntoskrnl!ExGetPreviousMode` at `0x1800617d1`
- `ntoskrnl!ExGetPreviousMode` at `0x1800617d1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800619aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800619aa`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18006184d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18006184d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061925`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180061925`

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
0x1800617b0  mov     [rsp+arg_8], rbx
0x1800617b5  mov     [rsp+arg_18], rsi
0x1800617ba  push    rdi
0x1800617bb  push    r12
0x1800617bd  push    r14
0x1800617bf  sub     rsp, 50h
0x1800617c3  mov     r14d, edx
0x1800617c6  mov     rbx, rcx
0x1800617c9  xorps   xmm0, xmm0
0x1800617cc  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1800617d1  call    cs:__imp_ExGetPreviousMode
0x1800617d8  nop     dword ptr [rax+rax+00h]
0x1800617dd  mov     dil, al
0x1800617e0  test    rbx, rbx
0x1800617e3  jz      loc_1800619D3
0x1800617e9  lea     r8d, [r14-3]
0x1800617ed  cmp     r8d, 0FFFBh
0x1800617f4  ja      loc_1800619D3
0x1800617fa  mov     [rsp+68h+arg_0], al
0x1800617fe  call    cs:__imp_KeEnterCriticalRegion
0x180061805  nop     dword ptr [rax+rax+00h]
0x18006180a  call    CipTryAcquireCatalogStoreLockExclusive
0x18006180f  mov     r8d, 72634943h
0x180061815  mov     edx, r14d
0x180061818  mov     ecx, 103h
0x18006181d  call    cs:__imp_ExAllocatePool2
0x180061824  nop     dword ptr [rax+rax+00h]
0x180061829  mov     rsi, rax
0x18006182c  mov     [rsp+68h+arg_10], rax
0x180061834  test    rax, rax
0x180061837  jnz     short loc_180061843
0x180061839  mov     edi, 0C0000017h
0x18006183e  jmp     loc_180061995
0x180061843  test    dil, dil
0x180061846  jz      short loc_18006186E
0x180061848  test    bl, 1
0x18006184b  jz      short loc_180061859
0x18006184d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x180061854  nop     dword ptr [rax+rax+00h]
0x180061859  test    dil, dil
0x18006185c  jz      short loc_18006186E
0x18006185e  mov     r8, r14; Size
0x180061861  mov     rdx, rbx; Src
0x180061864  mov     rcx, rsi; void *
0x180061867  call    RtlCopyFromUser
0x18006186c  jmp     short loc_18006187D
0x18006186e  mov     r8, r14; Size
0x180061871  mov     rdx, rbx; Src
0x180061874  mov     rcx, rsi; void *
0x180061877  call    RtlCopyVolatileMemory
0x18006187c  nop
0x18006187d  mov     qword ptr [rsp+68h+pusResult], 0
0x180061886  mov     [rsp+68h+var_38], rsi
0x18006188b  lea     rdx, [rsp+68h+pusResult+2]; pusResult
0x180061890  mov     ecx, r14d; ulOperand
0x180061893  call    ULongToUShort
0x180061898  mov     edi, eax
0x18006189a  test    eax, eax
0x18006189c  js      loc_180061995
0x1800618a2  movzx   edx, [rsp+68h+pusResult+2]
0x1800618a7  mov     ecx, edx
0x1800618a9  shr     rcx, 1
0x1800618ac  mov     rax, [rsp+68h+var_38]
0x1800618b1  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1800618b7  jnz     short loc_1800618BD
0x1800618b9  sub     dx, 2
0x1800618bd  mov     [rsp+68h+pusResult], dx
0x1800618c2  xor     edx, edx; dwFlags
0x1800618c4  lea     rcx, [rsp+68h+pusResult]; SourceString
0x1800618c9  call    RtlUnicodeStringValidateEx
0x1800618ce  mov     edi, eax
0x1800618d0  test    eax, eax
0x1800618d2  js      loc_180061995
0x1800618d8  mov     rbx, cs:qword_180049780
0x1800618df  lea     r12, qword_180049780
0x1800618e6  jmp     short loc_180061938
0x1800618e8  mov     eax, [rbx-18h]
0x1800618eb  test    al, 10h
0x1800618ed  jz      short loc_180061935
0x1800618ef  cmp     word ptr [rbx-10h], 72h ; 'r'
0x1800618f4  jbe     short loc_180061935
0x1800618f6  mov     rdx, [rbx-8]; SourceString
0x1800618fa  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1800618ff  call    cs:__imp_RtlInitUnicodeString
0x180061906  nop     dword ptr [rax+rax+00h]
0x18006190b  movzx   eax, word ptr [rbx-10h]
0x18006190f  sub     ax, 72h ; 'r'
0x180061913  mov     [rsp+68h+DestinationString.Length], ax
0x180061918  mov     r8b, 1; CaseInSensitive
0x18006191b  lea     rdx, [rsp+68h+pusResult]; String2
0x180061920  lea     rcx, [rsp+68h+DestinationString]; String1
0x180061925  call    cs:__imp_RtlEqualUnicodeString
0x18006192c  nop     dword ptr [rax+rax+00h]
0x180061931  test    al, al
0x180061933  jnz     short loc_18006193F
0x180061935  mov     rbx, [rbx]
0x180061938  cmp     rbx, r12
0x18006193b  jnz     short loc_1800618E8
0x18006193d  jmp     short loc_180061995
0x18006193f  mov     rax, [rbx]
0x180061942  cmp     [rax+8], rbx
0x180061946  jnz     short loc_180061984
0x180061948  mov     rcx, [rbx+8]
0x18006194c  cmp     [rcx], rbx
0x18006194f  jnz     short loc_180061984
0x180061951  mov     [rcx], rax
0x180061954  mov     [rax+8], rcx
0x180061958  mov     edx, 72634943h; Tag
0x18006195d  mov     rcx, [rbx-8]; P
0x180061961  call    cs:__imp_ExFreePoolWithTag
0x180061968  nop     dword ptr [rax+rax+00h]
0x18006196d  mov     edx, 72634943h; Tag
0x180061972  lea     rcx, [rbx-18h]; P
0x180061976  call    cs:__imp_ExFreePoolWithTag
0x18006197d  nop     dword ptr [rax+rax+00h]
0x180061982  jmp     short loc_180061995
0x180061984  mov     ecx, 3
0x180061989  int     29h; Win8: RtlFailFast(ecx)
0x18006198b  mov     edi, eax
0x18006198d  mov     rsi, [rsp+68h+arg_10]
0x180061995  xor     edx, edx
0x180061997  lea     rcx, g_CatalogStoreListLock
0x18006199e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1800619a5  nop     dword ptr [rax+rax+00h]
0x1800619aa  call    cs:__imp_KeLeaveCriticalRegion
0x1800619b1  nop     dword ptr [rax+rax+00h]
0x1800619b6  test    rsi, rsi
0x1800619b9  jz      short loc_1800619CF
0x1800619bb  mov     edx, 72634943h; Tag
0x1800619c0  mov     rcx, rsi; P
0x1800619c3  call    cs:__imp_ExFreePoolWithTag
0x1800619ca  nop     dword ptr [rax+rax+00h]
0x1800619cf  mov     eax, edi
0x1800619d1  jmp     short loc_1800619D8
0x1800619d3  mov     eax, 0C0000004h
0x1800619d8  lea     r11, [rsp+68h+var_18]
0x1800619dd  mov     rbx, [r11+28h]
0x1800619e1  mov     rsi, [r11+38h]
0x1800619e5  mov     rsp, r11
0x1800619e8  pop     r14
0x1800619ea  pop     r12
0x1800619ec  pop     rdi
0x1800619ed  retn
0x1800ea4a1  push    rbp
0x1800ea4a3  sub     rsp, 20h
0x1800ea4a7  mov     rbp, rdx
0x1800ea4aa  xor     eax, eax
0x1800ea4ac  cmp     [rbp+70h], al
0x1800ea4af  setnz   al
0x1800ea4b2  mov     [rbp+20h], eax
0x1800ea4b5  mov     eax, [rbp+20h]
0x1800ea4b8  add     rsp, 20h
0x1800ea4bc  pop     rbp
0x1800ea4bd  retn
```
