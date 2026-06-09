# ARI::ProcessToken::SysAppId::OpenProcess(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800185b8`
- end: `0x18001883c`
- name: `?OpenProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `644`
- prototype: `__int64 __fastcall(ARI::ProcessToken::SysAppId *__hidden this, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003810`
- `0x1800170a0`

## callees

- `0x1800185b8`
- `0x1800192d8`
- `0x18004b9d0`
- `0x180053c30`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001872d`
- `ntdll!RtlInitUnicodeString` at `0x180018750`
- `ntdll!RtlInitUnicodeString` at `0x18001872d`
- `ntdll!RtlInitUnicodeString` at `0x180018750`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001880f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d62`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001880f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d62`
- `ntdll!NtQueryInformationToken` at `0x180018648`
- `ntdll!NtQueryInformationToken` at `0x1800186f3`
- `ntdll!NtQueryInformationToken` at `0x180018648`
- `ntdll!NtQueryInformationToken` at `0x1800186f3`
- `ntdll!RtlCompareUnicodeString` at `0x18001877e`
- `ntdll!RtlCompareUnicodeString` at `0x18001879d`
- `ntdll!RtlCompareUnicodeString` at `0x18001877e`
- `ntdll!RtlCompareUnicodeString` at `0x18001879d`
- `ntdll!NtOpenProcessToken` at `0x1800185f9`
- `ntdll!NtOpenProcessToken` at `0x1800185f9`
- `ntdll!RtlAllocateHeap` at `0x1800186bb`
- `ntdll!RtlAllocateHeap` at `0x1800186bb`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::SysAppId::OpenProcess(
        ARI::ProcessToken::SysAppId *this,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v6; // eax
  ULONG LastErrorValue; // ebx
  __int64 v8; // rbx
  NTSTATUS v9; // eax
  PVOID Heap; // rax
  PVOID v12; // rdi
  int v13; // eax
  char v14; // r12
  bool v15; // r15
  __int64 i; // rbx
  __int64 v17; // rax
  const UNICODE_STRING *v18; // r14
  HANDLE TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+48h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+A0h] [rbp+40h] BYREF
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **v23; // [rsp+B0h] [rbp+50h]

  v23 = a3;
  TokenHandle = 0;
  if ( this == (ARI::ProcessToken::SysAppId *)-1LL )
  {
    v8 = -4;
    TokenHandle = (HANDLE)-4LL;
  }
  else
  {
    v6 = NtOpenProcessToken(this, 8u, &TokenHandle);
    if ( v6 < 0 )
    {
      BaseSetLastNTError((unsigned int)v6);
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
      if ( LastErrorValue )
        return LastErrorValue;
    }
    v8 = (__int64)TokenHandle;
  }
  if ( a4 )
    *(_BYTE *)a4 = 0;
  TokenInformationLength = 0;
  v9 = NtQueryInformationToken((HANDLE)v8, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v9 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(TokenInformationLength, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v12 = Heap) != 0) )
    {
      memset_0(Heap, 0, TokenInformationLength);
      v13 = NtQueryInformationToken(
              (HANDLE)v8,
              TokenSecurityAttributes,
              v12,
              TokenInformationLength,
              &TokenInformationLength);
      if ( v13 < 0 )
      {
        LastErrorValue = RtlNtStatusToDosErrorNoTeb(v13);
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v12);
      }
      else
      {
        if ( *((_DWORD *)v12 + 1) )
        {
          v14 = 1;
          v15 = a4 != 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          String1 = 0;
          if ( a4 )
            RtlInitUnicodeString(&String1, L"WIN://PKG");
          for ( i = 0; (unsigned int)i < *((_DWORD *)v12 + 1); i = (unsigned int)(i + 1) )
          {
            v17 = *((_QWORD *)v12 + 1);
            v18 = (const UNICODE_STRING *)(v17 + 40 * i);
            if ( v14 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v17 + 40 * i), 1u) )
            {
              *v23 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)v18;
              if ( !v15 )
                goto LABEL_29;
              v14 = 0;
            }
            else if ( v15 && !RtlCompareUnicodeString(&String1, v18, 1u) )
            {
              *(_BYTE *)a4 = 1;
              if ( !v14 )
              {
LABEL_29:
                *a2 = v12;
                AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                LastErrorValue = 0;
                goto LABEL_10;
              }
              v15 = 0;
            }
          }
        }
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v12);
        LastErrorValue = 1168;
      }
    }
    else
    {
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
      LastErrorValue = 8;
    }
  }
  else if ( v9 )
  {
    LastErrorValue = RtlNtStatusToDosErrorNoTeb(v9);
  }
  else
  {
    LastErrorValue = 1359;
  }
LABEL_10:
  if ( TokenHandle != (HANDLE)-4LL )
    CloseHandle(TokenHandle);
  return LastErrorValue;
}

```

## disassembly

```asm
0x1800185b8  mov     [rsp-38h+arg_8], rbx
0x1800185bd  mov     [rsp-38h+arg_10], r8
0x1800185c2  push    rbp
0x1800185c3  push    rsi
0x1800185c4  push    rdi
0x1800185c5  push    r12
0x1800185c7  push    r13
0x1800185c9  push    r14
0x1800185cb  push    r15
0x1800185cd  mov     rbp, rsp
0x1800185d0  sub     rsp, 60h
0x1800185d4  mov     [rbp+TokenHandle], 0
0x1800185dc  mov     rsi, r9
0x1800185df  mov     r13, rdx
0x1800185e2  mov     r14d, 8
0x1800185e8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800185ec  jz      loc_1800187F8
0x1800185f2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800185f6  mov     edx, r14d; DesiredAccess
0x1800185f9  call    cs:__imp_NtOpenProcessToken
0x180018600  nop     dword ptr [rax+rax+00h]
0x180018605  test    eax, eax
0x180018607  jns     short loc_18001861C
0x180018609  mov     ecx, eax
0x18001860b  call    BaseSetLastNTError
0x180018610  mov     ebx, gs:68h
0x180018618  test    ebx, ebx
0x18001861a  jnz     short loc_18001868E
0x18001861c  mov     rbx, [rbp+TokenHandle]
0x180018620  test    rsi, rsi
0x180018623  jz      short loc_180018628
0x180018625  mov     byte ptr [rsi], 0
0x180018628  xor     r9d, r9d; TokenInformationLength
0x18001862b  mov     [rbp+TokenInformationLength], 0
0x180018632  lea     rax, [rbp+TokenInformationLength]
0x180018636  xor     r8d, r8d; TokenInformation
0x180018639  mov     rcx, rbx; TokenHandle
0x18001863c  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180018641  lea     r15d, [r9+27h]
0x180018645  mov     edx, r15d; TokenInformationClass
0x180018648  call    cs:__imp_NtQueryInformationToken
0x18001864f  nop     dword ptr [rax+rax+00h]
0x180018654  cmp     eax, 0C0000023h
0x180018659  jnz     loc_18001882A
0x18001865f  mov     ecx, [rbp+TokenInformationLength]
0x180018662  lea     eax, [r15-17h]
0x180018666  mul     rcx
0x180018669  mov     qword ptr [rbp+DestinationString.Length], 0
0x180018671  test    rdx, rdx
0x180018674  jz      short loc_1800186A9
0x180018676  xor     ecx, ecx; P
0x180018678  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18001867d  mov     ebx, r14d
0x180018680  mov     rcx, [rbp+TokenHandle]; hObject
0x180018684  cmp     rcx, 0FFFFFFFFFFFFFFFCh
0x180018688  jnz     loc_1800187C3
0x18001868e  mov     eax, ebx
0x180018690  mov     rbx, [rsp+60h+arg_8]
0x180018698  add     rsp, 60h
0x18001869c  pop     r15
0x18001869e  pop     r14
0x1800186a0  pop     r13
0x1800186a2  pop     r12
0x1800186a4  pop     rdi
0x1800186a5  pop     rsi
0x1800186a6  pop     rbp
0x1800186a7  retn
0x1800186a9  mov     rcx, gs:60h
0x1800186b2  mov     r8, rax; Size
0x1800186b5  xor     edx, edx; Flags
0x1800186b7  mov     rcx, [rcx+30h]; HeapHandle
0x1800186bb  call    cs:__imp_RtlAllocateHeap
0x1800186c2  nop     dword ptr [rax+rax+00h]
0x1800186c7  mov     rdi, rax
0x1800186ca  test    rax, rax
0x1800186cd  jz      short loc_180018676
0x1800186cf  mov     r8d, [rbp+TokenInformationLength]; Size
0x1800186d3  xor     edx, edx; Val
0x1800186d5  mov     rcx, rax; void *
0x1800186d8  call    memset_0
0x1800186dd  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800186e1  lea     rax, [rbp+TokenInformationLength]
0x1800186e5  mov     r8, rdi; TokenInformation
0x1800186e8  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800186ed  mov     edx, r15d; TokenInformationClass
0x1800186f0  mov     rcx, rbx; TokenHandle
0x1800186f3  call    cs:__imp_NtQueryInformationToken
0x1800186fa  nop     dword ptr [rax+rax+00h]
0x1800186ff  test    eax, eax
0x180018701  js      loc_18001880D
0x180018707  cmp     dword ptr [rdi+4], 0
0x18001870b  jbe     loc_1800187B1
0x180018711  xorps   xmm0, xmm0
0x180018714  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18001871b  test    rsi, rsi
0x18001871e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018722  mov     r12b, 1
0x180018725  setnz   r15b
0x180018729  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001872d  call    cs:__imp_RtlInitUnicodeString
0x180018734  nop     dword ptr [rax+rax+00h]
0x180018739  xorps   xmm0, xmm0
0x18001873c  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180018740  test    rsi, rsi
0x180018743  jz      short loc_18001875C
0x180018745  lea     rdx, aWinPkg; "WIN://PKG"
0x18001874c  lea     rcx, [rbp+String1]; DestinationString
0x180018750  call    cs:__imp_RtlInitUnicodeString
0x180018757  nop     dword ptr [rax+rax+00h]
0x18001875c  xor     ebx, ebx
0x18001875e  cmp     ebx, [rdi+4]
0x180018761  jnb     short loc_1800187B1
0x180018763  mov     rax, [rdi+8]
0x180018767  lea     rcx, [rbx+rbx*4]
0x18001876b  lea     r14, [rax+rcx*8]
0x18001876f  test    r12b, r12b
0x180018772  jz      short loc_18001878E
0x180018774  mov     r8b, 1; CaseInsensitive
0x180018777  lea     rcx, [rbp+DestinationString]; String1
0x18001877b  mov     rdx, r14; String2
0x18001877e  call    cs:__imp_RtlCompareUnicodeString
0x180018785  nop     dword ptr [rax+rax+00h]
0x18001878a  test    eax, eax
0x18001878c  jz      short loc_1800187CD
0x18001878e  test    r15b, r15b
0x180018791  jz      short loc_1800187AD
0x180018793  mov     r8b, 1; CaseInsensitive
0x180018796  lea     rcx, [rbp+String1]; String1
0x18001879a  mov     rdx, r14; String2
0x18001879d  call    cs:__imp_RtlCompareUnicodeString
0x1800187a4  nop     dword ptr [rax+rax+00h]
0x1800187a9  test    eax, eax
0x1800187ab  jz      short loc_1800187DE
0x1800187ad  inc     ebx
0x1800187af  jmp     short loc_18001875E
0x1800187b1  mov     rcx, rdi; P
0x1800187b4  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800187b9  mov     ebx, 490h
0x1800187be  jmp     loc_180018680
0x1800187c3  call    CloseHandle
0x1800187c8  jmp     loc_18001868E
0x1800187cd  mov     rax, [rbp+arg_10]
0x1800187d1  mov     [rax], r14
0x1800187d4  test    r15b, r15b
0x1800187d7  jz      short loc_1800187E6
0x1800187d9  xor     r12b, r12b
0x1800187dc  jmp     short loc_1800187AD
0x1800187de  mov     byte ptr [rsi], 1
0x1800187e1  test    r12b, r12b
0x1800187e4  jnz     short loc_180018808
0x1800187e6  xor     ecx, ecx; P
0x1800187e8  mov     [r13+0], rdi
0x1800187ec  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800187f1  xor     ebx, ebx
0x1800187f3  jmp     loc_180018680
0x1800187f8  mov     rbx, 0FFFFFFFFFFFFFFFCh
0x1800187ff  mov     [rbp+TokenHandle], rbx
0x180018803  jmp     loc_180018620
0x180018808  xor     r15b, r15b
0x18001880b  jmp     short loc_1800187AD
0x18001880d  mov     ecx, eax; Status
0x18001880f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180018816  nop     dword ptr [rax+rax+00h]
0x18001881b  mov     rcx, rdi; P
0x18001881e  mov     ebx, eax
0x180018820  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018825  jmp     loc_180018680
0x18001882a  test    eax, eax
0x18001882c  jnz     loc_180199D60
0x180018832  mov     ebx, 54Fh
0x180018837  jmp     loc_180018680
0x180199d60  mov     ecx, eax; Status
0x180199d62  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180199d69  nop     dword ptr [rax+rax+00h]
0x180199d6e  mov     ebx, eax
0x180199d70  jmp     loc_180018680
```
