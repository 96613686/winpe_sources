# ARI::ProcessToken::AutoSysAppId::OpenProcessIfPackaged(void *)

- ea: `0x180018844`
- end: `0x180018af4`
- name: `?OpenProcessIfPackaged@AutoSysAppId@ProcessToken@ARI@@QEAAJPEAX@Z`
- size: `688`
- prototype: `__int64 __fastcall(ARI::ProcessToken::AutoSysAppId *__hidden this, HANDLE ProcessHandle)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018490`
- `0x180019650`
- `0x180104320`
- `0x180115268`

## callees

- `0x180018844`
- `0x1800192d8`
- `0x18001930c`
- `0x18004b9d0`
- `0x180053c30`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018997`
- `ntdll!RtlInitUnicodeString` at `0x1800189b5`
- `ntdll!RtlInitUnicodeString` at `0x180018997`
- `ntdll!RtlInitUnicodeString` at `0x1800189b5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018ac7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d78`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018ac7`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d78`
- `ntdll!NtQueryInformationToken` at `0x1800188da`
- `ntdll!NtQueryInformationToken` at `0x180018964`
- `ntdll!NtQueryInformationToken` at `0x1800188da`
- `ntdll!NtQueryInformationToken` at `0x180018964`
- `ntdll!RtlCompareUnicodeString` at `0x1800189e9`
- `ntdll!RtlCompareUnicodeString` at `0x180018a08`
- `ntdll!RtlCompareUnicodeString` at `0x1800189e9`
- `ntdll!RtlCompareUnicodeString` at `0x180018a08`
- `ntdll!NtOpenProcessToken` at `0x18001888f`
- `ntdll!NtOpenProcessToken` at `0x18001888f`
- `ntdll!RtlAllocateHeap` at `0x18001892c`
- `ntdll!RtlAllocateHeap` at `0x18001892c`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::AutoSysAppId::OpenProcessIfPackaged(
        ARI::ProcessToken::AutoSysAppId *this,
        HANDLE ProcessHandle)
{
  void *v4; // rcx
  NTSTATUS v5; // eax
  ULONG LastErrorValue; // ebx
  __int64 v7; // rbx
  NTSTATUS v8; // eax
  char v9; // r14
  PVOID Heap; // rax
  PVOID v11; // rdi
  int v12; // eax
  char v13; // r13
  __int64 v14; // rbx
  char v15; // r12
  __int64 v16; // rax
  const UNICODE_STRING *v17; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+90h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp+48h] BYREF
  __int64 v23; // [rsp+A0h] [rbp+50h]

  v4 = *(void **)this;
  if ( v4 )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v4);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  TokenHandle = 0;
  if ( ProcessHandle == (HANDLE)-1LL )
  {
    v7 = -4;
    TokenHandle = (HANDLE)-4LL;
  }
  else
  {
    v5 = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle);
    if ( v5 < 0 )
    {
      BaseSetLastNTError((unsigned int)v5);
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( LastErrorValue )
        return LastErrorValue;
    }
    v7 = (__int64)TokenHandle;
  }
  TokenInformationLength = 0;
  v8 = NtQueryInformationToken((HANDLE)v7, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v8 != -1073741789 )
  {
    if ( v8 )
      LastErrorValue = RtlNtStatusToDosErrorNoTeb(v8);
    else
      LastErrorValue = 1359;
    goto LABEL_10;
  }
  v23 = 0;
  if ( !is_mul_ok(TokenInformationLength, 0x10u)
    || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v11 = Heap) == 0) )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
    LastErrorValue = 8;
LABEL_10:
    v9 = 0;
    goto LABEL_23;
  }
  memset_0(Heap, 0, TokenInformationLength);
  v12 = NtQueryInformationToken(
          (HANDLE)v7,
          TokenSecurityAttributes,
          v11,
          TokenInformationLength,
          &TokenInformationLength);
  if ( v12 < 0 )
  {
    LastErrorValue = RtlNtStatusToDosErrorNoTeb(v12);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
    goto LABEL_10;
  }
  if ( *((_DWORD *)v11 + 1) )
  {
    v13 = 1;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
    String1 = 0;
    RtlInitUnicodeString(&String1, L"WIN://PKG");
    v14 = 0;
    v15 = 1;
    v9 = 0;
    while ( (unsigned int)v14 < *((_DWORD *)v11 + 1) )
    {
      v16 = *((_QWORD *)v11 + 1);
      v17 = (const UNICODE_STRING *)(v16 + 40 * v14);
      if ( v13 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v16 + 40 * v14), 1u) )
      {
        *((_QWORD *)this + 1) = v17;
        if ( !v15 )
          goto LABEL_32;
        v13 = 0;
      }
      else if ( v15 && !RtlCompareUnicodeString(&String1, v17, 1u) )
      {
        v9 = 1;
        if ( !v13 )
        {
LABEL_32:
          *(_QWORD *)this = v11;
          AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
          LastErrorValue = 0;
          goto LABEL_23;
        }
        v15 = 0;
      }
      v14 = (unsigned int)(v14 + 1);
    }
  }
  else
  {
    v9 = 0;
  }
  AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
  LastErrorValue = 1168;
LABEL_23:
  if ( TokenHandle != (HANDLE)-4LL )
    CloseHandle(TokenHandle);
  if ( LastErrorValue || v9 )
    return LastErrorValue;
  ARI::ProcessToken::AutoSysAppId::Close(this);
  return 15700;
}

```

## disassembly

```asm
0x180018844  mov     [rsp-38h+arg_18], rbx
0x180018849  push    rbp
0x18001884a  push    rsi
0x18001884b  push    rdi
0x18001884c  push    r12
0x18001884e  push    r13
0x180018850  push    r14
0x180018852  push    r15
0x180018854  mov     rbp, rsp
0x180018857  sub     rsp, 50h
0x18001885b  mov     rsi, rcx
0x18001885e  mov     rbx, rdx
0x180018861  mov     rcx, [rcx]; P
0x180018864  test    rcx, rcx
0x180018867  jnz     loc_180018AA4
0x18001886d  mov     [rbp+TokenHandle], 0
0x180018875  mov     r14d, 8
0x18001887b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001887f  jz      loc_180018A94
0x180018885  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180018889  mov     edx, r14d; DesiredAccess
0x18001888c  mov     rcx, rbx; ProcessHandle
0x18001888f  call    cs:__imp_NtOpenProcessToken
0x180018896  nop     dword ptr [rax+rax+00h]
0x18001889b  test    eax, eax
0x18001889d  jns     short loc_1800188B6
0x18001889f  mov     ecx, eax
0x1800188a1  call    BaseSetLastNTError
0x1800188a6  mov     ebx, gs:68h
0x1800188ae  test    ebx, ebx
0x1800188b0  jnz     loc_180018A3A
0x1800188b6  mov     rbx, [rbp+TokenHandle]
0x1800188ba  xor     r9d, r9d; TokenInformationLength
0x1800188bd  mov     [rbp+TokenInformationLength], 0
0x1800188c4  lea     rax, [rbp+TokenInformationLength]
0x1800188c8  xor     r8d, r8d; TokenInformation
0x1800188cb  mov     rcx, rbx; TokenHandle
0x1800188ce  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x1800188d3  lea     r15d, [r9+27h]
0x1800188d7  mov     edx, r15d; TokenInformationClass
0x1800188da  call    cs:__imp_NtQueryInformationToken
0x1800188e1  nop     dword ptr [rax+rax+00h]
0x1800188e6  cmp     eax, 0C0000023h
0x1800188eb  jnz     loc_180018AE2
0x1800188f1  mov     ecx, [rbp+TokenInformationLength]
0x1800188f4  lea     eax, [r15-17h]
0x1800188f8  mul     rcx
0x1800188fb  mov     [rbp+arg_10], 0
0x180018903  test    rdx, rdx
0x180018906  jz      short loc_18001891A
0x180018908  xor     ecx, ecx; P
0x18001890a  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18001890f  mov     ebx, r14d
0x180018912  xor     r14b, r14b
0x180018915  jmp     loc_180018A2C
0x18001891a  mov     rcx, gs:60h
0x180018923  mov     r8, rax; Size
0x180018926  xor     edx, edx; Flags
0x180018928  mov     rcx, [rcx+30h]; HeapHandle
0x18001892c  call    cs:__imp_RtlAllocateHeap
0x180018933  nop     dword ptr [rax+rax+00h]
0x180018938  mov     rdi, rax
0x18001893b  test    rax, rax
0x18001893e  jz      short loc_180018908
0x180018940  mov     r8d, [rbp+TokenInformationLength]; Size
0x180018944  xor     edx, edx; Val
0x180018946  mov     rcx, rax; void *
0x180018949  call    memset_0
0x18001894e  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180018952  lea     rax, [rbp+TokenInformationLength]
0x180018956  mov     r8, rdi; TokenInformation
0x180018959  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18001895e  mov     edx, r15d; TokenInformationClass
0x180018961  mov     rcx, rbx; TokenHandle
0x180018964  call    cs:__imp_NtQueryInformationToken
0x18001896b  nop     dword ptr [rax+rax+00h]
0x180018970  test    eax, eax
0x180018972  js      loc_180018AC5
0x180018978  cmp     dword ptr [rdi+4], 0
0x18001897c  jbe     loc_180018A1C
0x180018982  xorps   xmm0, xmm0
0x180018985  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18001898c  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018990  mov     r13b, 1
0x180018993  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018997  call    cs:__imp_RtlInitUnicodeString
0x18001899e  nop     dword ptr [rax+rax+00h]
0x1800189a3  xorps   xmm0, xmm0
0x1800189a6  lea     rdx, aWinPkg; "WIN://PKG"
0x1800189ad  lea     rcx, [rbp+String1]; DestinationString
0x1800189b1  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1800189b5  call    cs:__imp_RtlInitUnicodeString
0x1800189bc  nop     dword ptr [rax+rax+00h]
0x1800189c1  xor     ebx, ebx
0x1800189c3  mov     r12b, r13b
0x1800189c6  xor     r14b, r14b
0x1800189c9  cmp     ebx, [rdi+4]
0x1800189cc  jnb     short loc_180018A1F
0x1800189ce  mov     rax, [rdi+8]
0x1800189d2  lea     rcx, [rbx+rbx*4]
0x1800189d6  lea     r15, [rax+rcx*8]
0x1800189da  test    r13b, r13b
0x1800189dd  jz      short loc_1800189F9
0x1800189df  mov     r8b, 1; CaseInsensitive
0x1800189e2  lea     rcx, [rbp+DestinationString]; String1
0x1800189e6  mov     rdx, r15; String2
0x1800189e9  call    cs:__imp_RtlCompareUnicodeString
0x1800189f0  nop     dword ptr [rax+rax+00h]
0x1800189f5  test    eax, eax
0x1800189f7  jz      short loc_180018A70
0x1800189f9  test    r12b, r12b
0x1800189fc  jz      short loc_180018A18
0x1800189fe  mov     r8b, 1; CaseInsensitive
0x180018a01  lea     rcx, [rbp+String1]; String1
0x180018a05  mov     rdx, r15; String2
0x180018a08  call    cs:__imp_RtlCompareUnicodeString
0x180018a0f  nop     dword ptr [rax+rax+00h]
0x180018a14  test    eax, eax
0x180018a16  jz      short loc_180018A7E
0x180018a18  inc     ebx
0x180018a1a  jmp     short loc_1800189C9
0x180018a1c  xor     r14b, r14b
0x180018a1f  mov     rcx, rdi; P
0x180018a22  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018a27  mov     ebx, 490h
0x180018a2c  mov     rcx, [rbp+TokenHandle]; hObject
0x180018a30  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180018a34  jnz     short loc_180018A55
0x180018a36  test    ebx, ebx
0x180018a38  jz      short loc_180018A5C
0x180018a3a  mov     eax, ebx
0x180018a3c  mov     rbx, [rsp+50h+arg_18]
0x180018a44  add     rsp, 50h
0x180018a48  pop     r15
0x180018a4a  pop     r14
0x180018a4c  pop     r13
0x180018a4e  pop     r12
0x180018a50  pop     rdi
0x180018a51  pop     rsi
0x180018a52  pop     rbp
0x180018a53  retn
0x180018a55  call    CloseHandle
0x180018a5a  jmp     short loc_180018A36
0x180018a5c  test    r14b, r14b
0x180018a5f  jnz     short loc_180018A3A
0x180018a61  mov     rcx, rsi; this
0x180018a64  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180018a69  mov     eax, 3D54h
0x180018a6e  jmp     short loc_180018A3C
0x180018a70  mov     [rsi+8], r15
0x180018a74  test    r12b, r12b
0x180018a77  jz      short loc_180018A86
0x180018a79  xor     r13b, r13b
0x180018a7c  jmp     short loc_180018A18
0x180018a7e  mov     r14b, 1
0x180018a81  test    r13b, r13b
0x180018a84  jnz     short loc_180018ABD
0x180018a86  xor     ecx, ecx; P
0x180018a88  mov     [rsi], rdi
0x180018a8b  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018a90  xor     ebx, ebx
0x180018a92  jmp     short loc_180018A2C
0x180018a94  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x180018a9b  mov     [rbp+TokenHandle], rbx
0x180018a9f  jmp     loc_1800188BA
0x180018aa4  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018aa9  mov     qword ptr [rsi], 0
0x180018ab0  mov     qword ptr [rsi+8], 0
0x180018ab8  jmp     loc_18001886D
0x180018abd  xor     r12b, r12b
0x180018ac0  jmp     loc_180018A18
0x180018ac5  mov     ecx, eax; Status
0x180018ac7  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180018ace  nop     dword ptr [rax+rax+00h]
0x180018ad3  mov     rcx, rdi; P
0x180018ad6  mov     ebx, eax
0x180018ad8  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018add  jmp     loc_180018912
0x180018ae2  test    eax, eax
0x180018ae4  jnz     loc_180199D76
0x180018aea  mov     ebx, 54Fh
0x180018aef  jmp     loc_180018912
0x180199d76  mov     ecx, eax; Status
0x180199d78  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180199d7f  nop     dword ptr [rax+rax+00h]
0x180199d84  mov     ebx, eax
0x180199d86  jmp     loc_180018912
```
