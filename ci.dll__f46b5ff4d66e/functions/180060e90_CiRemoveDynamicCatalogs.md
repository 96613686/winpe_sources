# CiRemoveDynamicCatalogs

- ea: `0x180060e90`
- end: `0x180061047`
- name: `CiRemoveDynamicCatalogs`
- size: `439`
- prototype: `__int64 __fastcall(volatile void *Address, ULONG ulOperand)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005e420`

## callees

- `0x18000ecb4`
- `0x18001d1c0`
- `0x180060e90`
- `0x180061108`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x180060ebd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180060ebd`
- `ntoskrnl!RtlInitUnicodeString` at `0x180060f82`
- `ntoskrnl!RtlInitUnicodeString` at `0x180060f82`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006101b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18006101b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fed`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180061027`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180061027`
- `ntoskrnl!ProbeForRead` at `0x180060ed7`
- `ntoskrnl!ProbeForRead` at `0x180060ed7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180060fa8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180060fa8`

## pseudocode

```c
__int64 __fastcall CiRemoveDynamicCatalogs(volatile void *Address, ULONG ulOperand)
{
  HRESULT v4; // edi
  USHORT v5; // dx
  __int64 *i; // rbx
  __int64 *v7; // rsi
  __int64 v8; // rax
  __int64 **v9; // rcx
  USHORT pusResult[8]; // [rsp+28h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-40h] BYREF

  DestinationString = 0;
  if ( !Address || ulOperand <= 2 )
    return 3221225476LL;
  KeEnterCriticalRegion();
  CipTryAcquireCatalogStoreLockExclusive();
  ProbeForRead(Address, ulOperand, 2u);
  *(_QWORD *)pusResult = 0;
  *(_QWORD *)&pusResult[4] = Address;
  v4 = ULongToUShort(ulOperand, &pusResult[1]);
  if ( v4 >= 0 )
  {
    v5 = pusResult[1];
    if ( *(_WORD *)(*(_QWORD *)&pusResult[4] + 2 * ((unsigned __int64)pusResult[1] >> 1) - 2) == 92 )
      v5 = pusResult[1] - 2;
    pusResult[0] = v5;
    v4 = RtlUnicodeStringValidateEx((PCUNICODE_STRING)pusResult, 0);
    if ( v4 >= 0 )
    {
      for ( i = (__int64 *)qword_180048780; i != &qword_180048780; i = (__int64 *)*i )
      {
        v7 = i - 3;
        if ( (*(_DWORD *)(i - 3) & 0x10) != 0 && *((_WORD *)v7 + 4) > 0x72u )
        {
          RtlInitUnicodeString(&DestinationString, (PCWSTR)v7[2]);
          DestinationString.Length = *((_WORD *)v7 + 4) - 114;
          if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)pusResult, 1u) )
          {
            v8 = *i;
            if ( *(__int64 **)(*i + 8) != i || (v9 = (__int64 **)i[1], *v9 != i) )
              __fastfail(3u);
            *v9 = (__int64 *)v8;
            *(_QWORD *)(v8 + 8) = v9;
            ExFreePoolWithTag((PVOID)v7[2], 0x72634943u);
            ExFreePoolWithTag(v7, 0x72634943u);
            break;
          }
        }
      }
    }
  }
  ExReleasePushLockExclusiveEx(&g_CatalogStoreListLock, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180060e90  push    rbx
0x180060e92  push    rsi
0x180060e93  push    rdi
0x180060e94  push    r14
0x180060e96  sub     rsp, 58h
0x180060e9a  mov     ebx, edx
0x180060e9c  mov     rdi, rcx
0x180060e9f  xorps   xmm0, xmm0
0x180060ea2  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x180060ea7  test    rcx, rcx
0x180060eaa  jz      loc_180061037
0x180060eb0  mov     esi, 2
0x180060eb5  cmp     ebx, esi
0x180060eb7  jbe     loc_180061037
0x180060ebd  call    cs:__imp_KeEnterCriticalRegion
0x180060ec4  nop     dword ptr [rax+rax+00h]
0x180060ec9  call    CipTryAcquireCatalogStoreLockExclusive
0x180060ece  nop
0x180060ecf  mov     edx, ebx; Length
0x180060ed1  mov     r8d, esi; Alignment
0x180060ed4  mov     rcx, rdi; Address
0x180060ed7  call    cs:__imp_ProbeForRead
0x180060ede  nop     dword ptr [rax+rax+00h]
0x180060ee3  xorps   xmm0, xmm0
0x180060ee6  movups  xmmword ptr [rsp+78h+pusResult], xmm0
0x180060eeb  mov     qword ptr [rsp+78h+pusResult+8], rdi
0x180060ef0  lea     rdx, [rsp+78h+pusResult+2]; pusResult
0x180060ef5  mov     ecx, ebx; ulOperand
0x180060ef7  call    ULongToUShort
0x180060efc  mov     edi, eax
0x180060efe  mov     [rsp+78h+var_58], eax
0x180060f02  test    eax, eax
0x180060f04  js      loc_180061012
0x180060f0a  movzx   edx, [rsp+78h+pusResult+2]
0x180060f0f  mov     ecx, edx
0x180060f11  shr     rcx, 1
0x180060f14  mov     rax, qword ptr [rsp+78h+pusResult+8]
0x180060f19  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180060f1f  jnz     short loc_180060F24
0x180060f21  sub     dx, si
0x180060f24  mov     [rsp+78h+pusResult], dx
0x180060f29  xor     edx, edx; dwFlags
0x180060f2b  lea     rcx, [rsp+78h+pusResult]; SourceString
0x180060f30  call    RtlUnicodeStringValidateEx
0x180060f35  mov     edi, eax
0x180060f37  mov     [rsp+78h+var_58], eax
0x180060f3b  test    eax, eax
0x180060f3d  js      loc_180061012
0x180060f43  mov     r14d, 72h ; 'r'
0x180060f49  mov     rbx, cs:qword_180048780
0x180060f50  lea     rax, qword_180048780
0x180060f57  cmp     rbx, rax
0x180060f5a  jz      loc_18006100A
0x180060f60  lea     rsi, [rbx-18h]
0x180060f64  mov     eax, [rsi]
0x180060f66  test    al, 10h
0x180060f68  jz      loc_180061002
0x180060f6e  cmp     [rsi+8], r14w
0x180060f73  jbe     loc_180061002
0x180060f79  mov     rdx, [rsi+10h]; SourceString
0x180060f7d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180060f82  call    cs:__imp_RtlInitUnicodeString
0x180060f89  nop     dword ptr [rax+rax+00h]
0x180060f8e  movzx   eax, word ptr [rsi+8]
0x180060f92  sub     ax, r14w
0x180060f96  mov     [rsp+78h+DestinationString.Length], ax
0x180060f9b  mov     r8b, 1; CaseInSensitive
0x180060f9e  lea     rdx, [rsp+78h+pusResult]; String2
0x180060fa3  lea     rcx, [rsp+78h+DestinationString]; String1
0x180060fa8  call    cs:__imp_RtlEqualUnicodeString
0x180060faf  nop     dword ptr [rax+rax+00h]
0x180060fb4  test    al, al
0x180060fb6  jz      short loc_180061002
0x180060fb8  mov     rax, [rbx]
0x180060fbb  cmp     [rax+8], rbx
0x180060fbf  jnz     short loc_180060FFB
0x180060fc1  mov     rcx, [rbx+8]
0x180060fc5  cmp     [rcx], rbx
0x180060fc8  jnz     short loc_180060FFB
0x180060fca  mov     [rcx], rax
0x180060fcd  mov     [rax+8], rcx
0x180060fd1  mov     ebx, 72634943h
0x180060fd6  mov     edx, ebx; Tag
0x180060fd8  mov     rcx, [rsi+10h]; P
0x180060fdc  call    cs:__imp_ExFreePoolWithTag
0x180060fe3  nop     dword ptr [rax+rax+00h]
0x180060fe8  mov     edx, ebx; Tag
0x180060fea  mov     rcx, rsi; P
0x180060fed  call    cs:__imp_ExFreePoolWithTag
0x180060ff4  nop     dword ptr [rax+rax+00h]
0x180060ff9  jmp     short loc_180061012
0x180060ffb  mov     ecx, 3
0x180061000  int     29h; Win8: RtlFailFast(ecx)
0x180061002  mov     rbx, [rbx]
0x180061005  jmp     loc_180060F50
0x18006100a  jmp     short loc_180061012
0x18006100c  mov     edi, eax
0x18006100e  mov     [rsp+78h+var_58], eax
0x180061012  xor     edx, edx
0x180061014  lea     rcx, g_CatalogStoreListLock
0x18006101b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180061022  nop     dword ptr [rax+rax+00h]
0x180061027  call    cs:__imp_KeLeaveCriticalRegion
0x18006102e  nop     dword ptr [rax+rax+00h]
0x180061033  mov     eax, edi
0x180061035  jmp     short loc_18006103C
0x180061037  mov     eax, 0C0000004h
0x18006103c  add     rsp, 58h
0x180061040  pop     r14
0x180061042  pop     rdi
0x180061043  pop     rsi
0x180061044  pop     rbx
0x180061045  retn
```
