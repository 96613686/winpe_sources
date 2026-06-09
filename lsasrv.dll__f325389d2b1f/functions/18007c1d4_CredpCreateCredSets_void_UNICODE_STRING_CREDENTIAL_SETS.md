# CredpCreateCredSets(void *,_UNICODE_STRING *,_CREDENTIAL_SETS *)

- ea: `0x18007c1d4`
- end: `0x18007c4e8`
- name: `?CredpCreateCredSets@@YAJPEAXPEAU_UNICODE_STRING@@PEAU_CREDENTIAL_SETS@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(void *Src, PCUNICODE_STRING String1, struct _CREDENTIAL_SETS *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005c8b4`

## callees

- `0x18000c300`
- `0x180016f70`
- `0x18004091c`
- `0x18007c1d4`
- `0x18007c4f0`
- `0x1800b86d0`
- `0x1800bd6e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007c32e`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18007c32e`
- `ntdll!RtlDeleteCriticalSection` at `0x18007c4b5`
- `ntdll!RtlDeleteCriticalSection` at `0x18007c4b5`
- `ntdll!RtlLengthSid` at `0x18007c3be`
- `ntdll!RtlLengthSid` at `0x18007c3be`
- `ntdll!RtlEqualSid` at `0x18007c2f6`
- `ntdll!RtlEqualSid` at `0x18007c2f6`
- `ntdll!RtlLeaveCriticalSection` at `0x18007c387`
- `ntdll!RtlLeaveCriticalSection` at `0x18007c4a0`
- `ntdll!RtlLeaveCriticalSection` at `0x18007c387`
- `ntdll!RtlLeaveCriticalSection` at `0x18007c4a0`
- `ntdll!RtlEnterCriticalSection` at `0x18007c21e`
- `ntdll!RtlEnterCriticalSection` at `0x18007c21e`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c418`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c432`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c418`
- `ntdll!RtlInitializeCriticalSection` at `0x18007c432`
- `ntdll!RtlEqualUnicodeString` at `0x18007c363`
- `ntdll!RtlEqualUnicodeString` at `0x18007c363`
- `ntdll!RtlInitUnicodeString` at `0x18007c34c`
- `ntdll!RtlInitUnicodeString` at `0x18007c34c`

## pseudocode

```c
__int64 __fastcall CredpCreateCredSets(void *Src, PCUNICODE_STRING String1, struct _CREDENTIAL_SETS *a3)
{
  bool v3; // zf
  _DWORD *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rcx
  struct _LIST_ENTRY *i; // rbx
  NTSTATUS v15; // ebx
  ULONG v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rsi
  void *v20; // rdx
  struct _CREDENTIAL_SET *CredSet; // rax
  struct _LIST_ENTRY *Flink; // rax
  struct _CREDENTIAL_SET *v23; // rax
  DWORD nSize; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-60h] BYREF
  WCHAR Buffer[16]; // [rsp+38h] [rbp-50h] BYREF

  v3 = *((_DWORD *)a3 + 6) == 0;
  DestinationString = 0;
  nSize = 16;
  if ( v3 )
  {
    RtlEnterCriticalSection(&CredentialSetListLock);
    if ( !*((_DWORD *)a3 + 6) )
    {
      *(_OWORD *)a3 = 0;
      *((_OWORD *)a3 + 1) = 0;
      v7 = (_DWORD *)LsapAllocate(312);
      *((_QWORD *)a3 + 1) = v7;
      if ( v7 )
      {
        *v7 = 1;
        v8 = 0;
        do
        {
          v9 = v8 + 2;
          ++v8;
          v10 = (_QWORD *)(*((_QWORD *)a3 + 1) + 16 * v9);
          v10[1] = v10;
          *v10 = v10;
        }
        while ( v8 != 16 );
        *(_DWORD *)(*((_QWORD *)a3 + 1) + 304LL) = 0;
        v11 = (_QWORD *)(*((_QWORD *)a3 + 1) + 288LL);
        v11[1] = v11;
        *v11 = v11;
        v12 = (_QWORD *)(*((_QWORD *)a3 + 1) + 16LL);
        v13 = 0;
        v12[1] = v12;
        *v12 = v12;
        do
          *(_BYTE *)(*((_QWORD *)a3 + 1) + v13++ + 308) = 0;
        while ( v13 != 2 );
        *(_QWORD *)(*((_QWORD *)a3 + 1) + 8LL) = CredpAllocateCredSet();
        if ( *(_QWORD *)(*((_QWORD *)a3 + 1) + 8LL) )
        {
          for ( i = CredentialSetList.Flink; i != &CredentialSetList; i = i->Flink )
          {
            *(_QWORD *)a3 = i;
            if ( RtlEqualSid(Src, i[2].Blink) )
            {
              ++*(_DWORD *)(*(_QWORD *)a3 + 16LL);
              break;
            }
            *(_QWORD *)a3 = 0;
          }
          if ( *(_QWORD *)a3 )
          {
LABEL_15:
            if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
            {
              RtlInitUnicodeString(&DestinationString, Buffer);
              if ( RtlEqualUnicodeString(String1, &DestinationString, 1u) )
                *((_DWORD *)a3 + 4) |= 1u;
              *((_DWORD *)a3 + 6) = 1;
              v15 = 0;
              goto LABEL_19;
            }
            goto LABEL_25;
          }
          v17 = RtlLengthSid(Src);
          v18 = LsapAllocate(v17 + 128LL);
          v19 = v18;
          if ( v18 )
          {
            *(_DWORD *)(v18 + 16) = 1;
            *(_QWORD *)(v18 + 8) = v18;
            *(_QWORD *)v18 = v18;
            *(_QWORD *)(v18 + 24) = 0;
            *(_QWORD *)(v18 + 32) = 0;
            *(_QWORD *)(v18 + 40) = v18 + 128;
            memcpy_0((void *)(v18 + 128), Src, v17);
            v15 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 48));
            if ( v15 >= 0 )
            {
              v15 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 88));
              if ( v15 >= 0 )
              {
                *(_QWORD *)a3 = v19;
                CredSet = CredpAllocateCredSet();
                *(_QWORD *)(v19 + 24) = CredSet;
                if ( CredSet )
                {
                  v23 = CredpAllocateCredSet();
                  *(_QWORD *)(v19 + 32) = v23;
                  if ( v23 )
                  {
                    *((_DWORD *)a3 + 5) = 0;
                    Flink = CredentialSetList.Flink;
                    if ( CredentialSetList.Flink->Blink != &CredentialSetList )
                      __fastfail(3u);
                    *(_QWORD *)v19 = CredentialSetList.Flink;
                    *(_QWORD *)(v19 + 8) = &CredentialSetList;
                    Flink->Blink = (struct _LIST_ENTRY *)v19;
                    CredentialSetList.Flink = (struct _LIST_ENTRY *)v19;
                    goto LABEL_15;
                  }
                }
                goto LABEL_25;
              }
              RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)(v19 + 48));
            }
            LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v19, v20);
            goto LABEL_26;
          }
        }
      }
LABEL_25:
      v15 = -1073741801;
LABEL_26:
      CredpDereferenceCredSets(a3);
LABEL_19:
      RtlLeaveCriticalSection(&CredentialSetListLock);
      return (unsigned int)v15;
    }
    RtlLeaveCriticalSection(&CredentialSetListLock);
  }
  return 0;
}

```

## disassembly

```asm
0x18007c1d4  mov     [rsp+arg_18], rbx
0x18007c1d9  push    rbp
0x18007c1da  push    rsi
0x18007c1db  push    rdi
0x18007c1dc  push    r13
0x18007c1de  push    r14
0x18007c1e0  sub     rsp, 60h
0x18007c1e4  mov     rax, cs:__security_cookie
0x18007c1eb  xor     rax, rsp
0x18007c1ee  mov     [rsp+88h+var_30], rax
0x18007c1f3  cmp     dword ptr [r8+18h], 0
0x18007c1f8  xorps   xmm0, xmm0
0x18007c1fb  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x18007c200  mov     rdi, r8
0x18007c203  mov     [rsp+88h+nSize], 10h
0x18007c20b  mov     r14, rdx
0x18007c20e  mov     rbp, rcx
0x18007c211  jnz     loc_18007C397
0x18007c217  lea     rcx, ?CredentialSetListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007c21e  call    cs:__imp_RtlEnterCriticalSection
0x18007c225  nop     dword ptr [rax+rax+00h]
0x18007c22a  cmp     dword ptr [rdi+18h], 0
0x18007c22e  jnz     loc_18007C499
0x18007c234  xorps   xmm0, xmm0
0x18007c237  mov     ecx, 138h
0x18007c23c  movups  xmmword ptr [rdi], xmm0
0x18007c23f  movups  xmmword ptr [rdi+10h], xmm0
0x18007c243  call    LsapAllocate
0x18007c248  mov     [rdi+8], rax
0x18007c24c  test    rax, rax
0x18007c24f  jz      loc_18007C455
0x18007c255  mov     dword ptr [rax], 1
0x18007c25b  xor     edx, edx
0x18007c25d  lea     rcx, [rdx+2]
0x18007c261  inc     rdx
0x18007c264  shl     rcx, 4
0x18007c268  add     rcx, [rdi+8]
0x18007c26c  mov     [rcx+8], rcx
0x18007c270  mov     [rcx], rcx
0x18007c273  cmp     rdx, 10h
0x18007c277  jnz     short loc_18007C25D
0x18007c279  mov     rax, [rdi+8]
0x18007c27d  mov     dword ptr [rax+130h], 0
0x18007c287  mov     rax, [rdi+8]
0x18007c28b  add     rax, 120h
0x18007c291  mov     [rax+8], rax
0x18007c295  mov     [rax], rax
0x18007c298  mov     rax, [rdi+8]
0x18007c29c  add     rax, rdx
0x18007c29f  xor     ecx, ecx
0x18007c2a1  mov     [rax+8], rax
0x18007c2a5  mov     [rax], rax
0x18007c2a8  mov     rax, [rdi+8]
0x18007c2ac  mov     byte ptr [rax+rcx+134h], 0
0x18007c2b4  inc     rcx
0x18007c2b7  cmp     rcx, 2
0x18007c2bb  jnz     short loc_18007C2A8
0x18007c2bd  call    ?CredpAllocateCredSet@@YAPEAU_CREDENTIAL_SET@@XZ; CredpAllocateCredSet(void)
0x18007c2c2  mov     rcx, [rdi+8]
0x18007c2c6  mov     [rcx+8], rax
0x18007c2ca  mov     rax, [rdi+8]
0x18007c2ce  cmp     qword ptr [rax+8], 0
0x18007c2d3  jz      loc_18007C455
0x18007c2d9  mov     rbx, cs:?CredentialSetList@@3U_LIST_ENTRY@@A; _LIST_ENTRY CredentialSetList
0x18007c2e0  lea     r13, ?CredentialSetList@@3U_LIST_ENTRY@@A; _LIST_ENTRY CredentialSetList
0x18007c2e7  cmp     rbx, r13
0x18007c2ea  jz      short loc_18007C318
0x18007c2ec  mov     [rdi], rbx
0x18007c2ef  mov     rcx, rbp; Sid1
0x18007c2f2  mov     rdx, [rbx+28h]; Sid2
0x18007c2f6  call    cs:__imp_RtlEqualSid
0x18007c2fd  nop     dword ptr [rax+rax+00h]
0x18007c302  test    al, al
0x18007c304  jnz     short loc_18007C312
0x18007c306  mov     qword ptr [rdi], 0
0x18007c30d  mov     rbx, [rbx]
0x18007c310  jmp     short loc_18007C2E7
0x18007c312  mov     rax, [rdi]
0x18007c315  inc     dword ptr [rax+10h]
0x18007c318  cmp     qword ptr [rdi], 0
0x18007c31c  jz      loc_18007C3BB
0x18007c322  lea     r8, [rsp+88h+nSize]; nSize
0x18007c327  xor     ecx, ecx; NameType
0x18007c329  lea     rdx, [rsp+88h+Buffer]; lpBuffer
0x18007c32e  call    cs:__imp_GetComputerNameExW
0x18007c335  nop     dword ptr [rax+rax+00h]
0x18007c33a  test    eax, eax
0x18007c33c  jz      loc_18007C455
0x18007c342  lea     rdx, [rsp+88h+Buffer]; SourceString
0x18007c347  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18007c34c  call    cs:__imp_RtlInitUnicodeString
0x18007c353  nop     dword ptr [rax+rax+00h]
0x18007c358  mov     r8b, 1; CaseInsensitive
0x18007c35b  lea     rdx, [rsp+88h+DestinationString]; String2
0x18007c360  mov     rcx, r14; String1
0x18007c363  call    cs:__imp_RtlEqualUnicodeString
0x18007c36a  nop     dword ptr [rax+rax+00h]
0x18007c36f  test    al, al
0x18007c371  jnz     loc_18007C4DF
0x18007c377  mov     dword ptr [rdi+18h], 1
0x18007c37e  xor     ebx, ebx
0x18007c380  lea     rcx, ?CredentialSetListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007c387  call    cs:__imp_RtlLeaveCriticalSection
0x18007c38e  nop     dword ptr [rax+rax+00h]
0x18007c393  mov     eax, ebx
0x18007c395  jmp     short loc_18007C399
0x18007c397  xor     eax, eax
0x18007c399  mov     rcx, [rsp+88h+var_30]
0x18007c39e  xor     rcx, rsp; StackCookie
0x18007c3a1  call    __security_check_cookie
0x18007c3a6  mov     rbx, [rsp+88h+arg_18]
0x18007c3ae  add     rsp, 60h
0x18007c3b2  pop     r14
0x18007c3b4  pop     r13
0x18007c3b6  pop     rdi
0x18007c3b7  pop     rsi
0x18007c3b8  pop     rbp
0x18007c3b9  retn
0x18007c3bb  mov     rcx, rbp; Sid
0x18007c3be  call    cs:__imp_RtlLengthSid
0x18007c3c5  nop     dword ptr [rax+rax+00h]
0x18007c3ca  mov     ebx, eax
0x18007c3cc  lea     rcx, [rbx+80h]
0x18007c3d3  call    LsapAllocate
0x18007c3d8  mov     rsi, rax
0x18007c3db  test    rax, rax
0x18007c3de  jz      short loc_18007C455
0x18007c3e0  mov     dword ptr [rax+10h], 1
0x18007c3e7  lea     rcx, [rax+80h]; void *
0x18007c3ee  mov     [rax+8], rax
0x18007c3f2  mov     r8d, ebx; Size
0x18007c3f5  mov     [rax], rax
0x18007c3f8  mov     rdx, rbp; Src
0x18007c3fb  mov     qword ptr [rax+18h], 0
0x18007c403  mov     qword ptr [rax+20h], 0
0x18007c40b  mov     [rax+28h], rcx
0x18007c40f  call    memcpy_0
0x18007c414  lea     rcx, [rsi+30h]; CriticalSection
0x18007c418  call    cs:__imp_RtlInitializeCriticalSection
0x18007c41f  nop     dword ptr [rax+rax+00h]
0x18007c424  mov     ebx, eax
0x18007c426  test    eax, eax
0x18007c428  js      loc_18007C4C1
0x18007c42e  lea     rcx, [rsi+58h]; CriticalSection
0x18007c432  call    cs:__imp_RtlInitializeCriticalSection
0x18007c439  nop     dword ptr [rax+rax+00h]
0x18007c43e  mov     ebx, eax
0x18007c440  test    eax, eax
0x18007c442  js      short loc_18007C4B1
0x18007c444  mov     [rdi], rsi
0x18007c447  call    ?CredpAllocateCredSet@@YAPEAU_CREDENTIAL_SET@@XZ; CredpAllocateCredSet(void)
0x18007c44c  mov     [rsi+18h], rax
0x18007c450  test    rax, rax
0x18007c453  jnz     short loc_18007C4CB
0x18007c455  mov     ebx, 0C0000017h
0x18007c45a  mov     rcx, rdi; struct _CREDENTIAL_SETS *
0x18007c45d  call    ?CredpDereferenceCredSets@@YAXPEAU_CREDENTIAL_SETS@@@Z; CredpDereferenceCredSets(_CREDENTIAL_SETS *)
0x18007c462  jmp     loc_18007C380
0x18007c467  mov     dword ptr [rdi+14h], 0
0x18007c46e  mov     rax, cs:?CredentialSetList@@3U_LIST_ENTRY@@A; _LIST_ENTRY CredentialSetList
0x18007c475  cmp     [rax+8], r13
0x18007c479  jz      short loc_18007C482
0x18007c47b  mov     ecx, 3
0x18007c480  int     29h; Win8: RtlFailFast(ecx)
0x18007c482  mov     [rsi], rax
0x18007c485  mov     [rsi+8], r13
0x18007c489  mov     [rax+8], rsi
0x18007c48d  mov     cs:?CredentialSetList@@3U_LIST_ENTRY@@A, rsi; _LIST_ENTRY CredentialSetList
0x18007c494  jmp     loc_18007C322
0x18007c499  lea     rcx, ?CredentialSetListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18007c4a0  call    cs:__imp_RtlLeaveCriticalSection
0x18007c4a7  nop     dword ptr [rax+rax+00h]
0x18007c4ac  jmp     loc_18007C397
0x18007c4b1  lea     rcx, [rsi+30h]; CriticalSection
0x18007c4b5  call    cs:__imp_RtlDeleteCriticalSection
0x18007c4bc  nop     dword ptr [rax+rax+00h]
0x18007c4c1  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x18007c4c4  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18007c4c9  jmp     short loc_18007C45A
0x18007c4cb  call    ?CredpAllocateCredSet@@YAPEAU_CREDENTIAL_SET@@XZ; CredpAllocateCredSet(void)
0x18007c4d0  mov     [rsi+20h], rax
0x18007c4d4  test    rax, rax
0x18007c4d7  jz      loc_18007C455
0x18007c4dd  jmp     short loc_18007C467
0x18007c4df  or      dword ptr [rdi+10h], 1
0x18007c4e3  jmp     loc_18007C377
```
