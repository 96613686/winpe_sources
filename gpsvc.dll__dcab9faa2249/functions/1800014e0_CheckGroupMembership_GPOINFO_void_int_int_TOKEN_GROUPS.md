# CheckGroupMembership(_GPOINFO *,void *,int *,int *,_TOKEN_GROUPS * *)

- ea: `0x1800014e0`
- end: `0x1800016bf`
- name: `?CheckGroupMembership@@YAXPEAU_GPOINFO@@PEAXPEAH2PEAPEAU_TOKEN_GROUPS@@@Z`
- size: `479`
- prototype: `void __fastcall(struct _GPOINFO *, HANDLE TokenHandle, int *, int *, struct _TOKEN_GROUPS **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005ce5c`

## callees

- `0x1800014e0`
- `0x180001930`
- `0x18002d9b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001580`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000163f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001580`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000163f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001621`
- `ntdll!NtQueryInformationToken` at `0x18000152a`
- `ntdll!NtQueryInformationToken` at `0x180001667`
- `ntdll!NtQueryInformationToken` at `0x18000152a`
- `ntdll!NtQueryInformationToken` at `0x180001667`
- `ntdll!RtlCopySid` at `0x1800015d7`
- `ntdll!RtlCopySid` at `0x1800015d7`
- `ntdll!RtlLengthSid` at `0x1800015c6`
- `ntdll!RtlLengthSid` at `0x1800015c6`

## pseudocode

```c
void __fastcall CheckGroupMembership(
        struct _GPOINFO *a1,
        HANDLE TokenHandle,
        int *a3,
        int *a4,
        struct _TOKEN_GROUPS **a5)
{
  struct _TOKEN_GROUPS *v9; // rsi
  NTSTATUS InformationToken; // eax
  int MembershipList; // eax
  struct _TOKEN_GROUPS *v12; // rax
  DWORD v13; // ebx
  DWORD v14; // r14d
  char *i; // r15
  char *v16; // rbp
  ULONG v17; // eax
  __int64 v18; // rdi
  __int64 v19; // r8
  int v20; // eax
  ULONG TokenInformationLength[18]; // [rsp+30h] [rbp-48h] BYREF

  TokenInformationLength[0] = 0;
  *a5 = 0;
  v9 = 0;
  InformationToken = NtQueryInformationToken(TokenHandle, TokenGroups, 0, 0, TokenInformationLength);
  if ( InformationToken == -1073741789 )
  {
    v9 = (struct _TOKEN_GROUPS *)LocalAlloc(0x40u, TokenInformationLength[0]);
    if ( !v9 )
    {
      *a3 = 1;
      *a4 = 1;
      return;
    }
    InformationToken = NtQueryInformationToken(
                         TokenHandle,
                         TokenGroups,
                         v9,
                         TokenInformationLength[0],
                         TokenInformationLength);
  }
  if ( InformationToken )
  {
    *a3 = 1;
    *a4 = 1;
    if ( !v9 )
      return;
    goto LABEL_15;
  }
  MembershipList = ReadMembershipList(a1, 0, v9);
  *a3 = MembershipList;
  if ( MembershipList )
    SaveMembershipList(a1, 0, v9);
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    *a4 = *a3;
  }
  else
  {
    v20 = ReadMembershipList(a1, *((const unsigned __int16 **)a1 + 9), v9);
    *a4 = v20;
    if ( v20 )
      SaveMembershipList(a1, *((const unsigned __int16 **)a1 + 9), v9);
  }
  if ( v9 )
  {
    v12 = (struct _TOKEN_GROUPS *)LocalAlloc(0x40u, 84LL * v9->GroupCount + 24);
    *a5 = v12;
    if ( v12 )
    {
      v13 = 0;
      v14 = 0;
      for ( i = (char *)&v12[1] + 16 * v9->GroupCount; v13 < v9->GroupCount; ++v13 )
      {
        v16 = (char *)v9 + 16 * v13;
        if ( (*((_DWORD *)v16 + 4) & 0xC0000000) == 0 )
        {
          v17 = RtlLengthSid(*((PSID *)v16 + 1));
          v18 = v17;
          RtlCopySid(v17, i, *((PSID *)v16 + 1));
          v19 = v14;
          (*a5)->Groups[v19].Attributes = *((_DWORD *)v16 + 4);
          (*a5)->Groups[v19].Sid = i;
          i += v18;
          ++v14;
        }
      }
      (*a5)->GroupCount = v14;
    }
LABEL_15:
    LocalFree(v9);
  }
}

```

## disassembly

```asm
0x1800014e0  push    rbx
0x1800014e2  push    rbp
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  push    r12
0x1800014e7  push    r14
0x1800014e9  push    r15
0x1800014eb  sub     rsp, 40h
0x1800014ef  mov     r12, [rsp+78h+arg_20]
0x1800014f7  lea     rax, [rsp+78h+TokenInformationLength]
0x1800014fc  mov     r14, rdx
0x1800014ff  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180001504  xor     r15d, r15d
0x180001507  mov     rdi, r9
0x18000150a  mov     rbx, r8
0x18000150d  mov     [rsp+78h+TokenInformationLength], r15d
0x180001512  mov     rbp, rcx
0x180001515  mov     [r12], r15
0x180001519  xor     r9d, r9d; TokenInformationLength
0x18000151c  xor     r8d, r8d; TokenInformation
0x18000151f  mov     edx, 2; TokenInformationClass
0x180001524  mov     rcx, r14; TokenHandle
0x180001527  mov     esi, r15d
0x18000152a  call    cs:__imp_NtQueryInformationToken
0x180001530  cmp     eax, 0C0000023h
0x180001535  jz      loc_180001636
0x18000153b  test    eax, eax
0x18000153d  jnz     loc_18000160D
0x180001543  mov     r8, rsi; struct _TOKEN_GROUPS *
0x180001546  xor     edx, edx; unsigned __int16 *
0x180001548  mov     rcx, rbp; struct _GPOINFO *
0x18000154b  call    ?ReadMembershipList@@YAHPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z; ReadMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)
0x180001550  mov     [rbx], eax
0x180001552  test    eax, eax
0x180001554  jnz     loc_180001680
0x18000155a  test    byte ptr [rbp+0], 1
0x18000155e  jz      loc_180001692
0x180001564  mov     eax, [rbx]
0x180001566  mov     [rdi], eax
0x180001568  test    rsi, rsi
0x18000156b  jz      loc_180001627
0x180001571  mov     eax, [rsi]
0x180001573  mov     ecx, 40h ; '@'; uFlags
0x180001578  imul    rdx, rax, 54h ; 'T'
0x18000157c  add     rdx, 18h; uBytes
0x180001580  call    cs:__imp_LocalAlloc
0x180001586  mov     [r12], rax
0x18000158a  test    rax, rax
0x18000158d  jz      loc_18000161E
0x180001593  mov     edx, [rsi]
0x180001595  mov     ebx, r15d
0x180001598  mov     r14d, r15d
0x18000159b  mov     r15d, edx
0x18000159e  shl     r15, 4
0x1800015a2  add     r15, 18h
0x1800015a6  add     r15, rax
0x1800015a9  test    edx, edx
0x1800015ab  jz      short loc_180001604
0x1800015ad  nop     dword ptr [rax]
0x1800015b0  mov     ebp, ebx
0x1800015b2  shl     rbp, 4
0x1800015b6  add     rbp, rsi
0x1800015b9  test    dword ptr [rbp+10h], 0C0000000h
0x1800015c0  jnz     short loc_1800015FE
0x1800015c2  mov     rcx, [rbp+8]; Sid
0x1800015c6  call    cs:__imp_RtlLengthSid
0x1800015cc  mov     r8, [rbp+8]; SourceSid
0x1800015d0  mov     rdx, r15; DestinationSid
0x1800015d3  mov     ecx, eax; DestinationSidLength
0x1800015d5  mov     edi, eax
0x1800015d7  call    cs:__imp_RtlCopySid
0x1800015dd  mov     ecx, [rbp+10h]
0x1800015e0  mov     rdx, [r12]
0x1800015e4  mov     r8d, r14d
0x1800015e7  add     r8, r8
0x1800015ea  mov     [rdx+r8*8+10h], ecx
0x1800015ef  mov     rcx, [r12]
0x1800015f3  mov     [rcx+r8*8+8], r15
0x1800015f8  add     r15, rdi
0x1800015fb  inc     r14d
0x1800015fe  inc     ebx
0x180001600  cmp     ebx, [rsi]
0x180001602  jb      short loc_1800015B0
0x180001604  mov     rax, [r12]
0x180001608  mov     [rax], r14d
0x18000160b  jmp     short loc_18000161E
0x18000160d  mov     dword ptr [rbx], 1
0x180001613  mov     dword ptr [rdi], 1
0x180001619  test    rsi, rsi
0x18000161c  jz      short loc_180001627
0x18000161e  mov     rcx, rsi; hMem
0x180001621  call    cs:__imp_LocalFree
0x180001627  add     rsp, 40h
0x18000162b  pop     r15
0x18000162d  pop     r14
0x18000162f  pop     r12
0x180001631  pop     rdi
0x180001632  pop     rsi
0x180001633  pop     rbp
0x180001634  pop     rbx
0x180001635  retn
0x180001636  mov     edx, [rsp+78h+TokenInformationLength]; uBytes
0x18000163a  mov     ecx, 40h ; '@'; uFlags
0x18000163f  call    cs:__imp_LocalAlloc
0x180001645  mov     rsi, rax
0x180001648  test    rax, rax
0x18000164b  jz      short loc_180001672
0x18000164d  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x180001652  lea     rax, [rsp+78h+TokenInformationLength]
0x180001657  mov     r8, rsi; TokenInformation
0x18000165a  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18000165f  mov     edx, 2; TokenInformationClass
0x180001664  mov     rcx, r14; TokenHandle
0x180001667  call    cs:__imp_NtQueryInformationToken
0x18000166d  jmp     loc_18000153B
0x180001672  mov     dword ptr [rbx], 1
0x180001678  mov     dword ptr [rdi], 1
0x18000167e  jmp     short loc_180001627
0x180001680  mov     r8, rsi; struct _TOKEN_GROUPS *
0x180001683  xor     edx, edx; unsigned __int16 *
0x180001685  mov     rcx, rbp; struct _GPOINFO *
0x180001688  call    ?SaveMembershipList@@YAXPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z; SaveMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)
0x18000168d  jmp     loc_18000155A
0x180001692  mov     rdx, [rbp+48h]; unsigned __int16 *
0x180001696  mov     r8, rsi; struct _TOKEN_GROUPS *
0x180001699  mov     rcx, rbp; struct _GPOINFO *
0x18000169c  call    ?ReadMembershipList@@YAHPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z; ReadMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)
0x1800016a1  mov     [rdi], eax
0x1800016a3  test    eax, eax
0x1800016a5  jz      loc_180001568
0x1800016ab  mov     rdx, [rbp+48h]; unsigned __int16 *
0x1800016af  mov     r8, rsi; struct _TOKEN_GROUPS *
0x1800016b2  mov     rcx, rbp; struct _GPOINFO *
0x1800016b5  call    ?SaveMembershipList@@YAXPEAU_GPOINFO@@PEBGPEAU_TOKEN_GROUPS@@@Z; SaveMembershipList(_GPOINFO *,ushort const *,_TOKEN_GROUPS *)
0x1800016ba  jmp     loc_180001568
```
