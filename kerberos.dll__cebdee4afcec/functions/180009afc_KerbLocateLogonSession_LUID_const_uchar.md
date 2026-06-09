# KerbLocateLogonSession(_LUID const *,uchar)

- ea: `0x180009afc`
- end: `0x180009c58`
- name: `?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z`
- size: `348`
- prototype: `struct _KERB_LOGON_SESSION *__fastcall(const struct _LUID *, char)`
- caller_count: `64`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x18000951c`
- `0x180009744`
- `0x1800097b0`
- `0x18000b430`
- `0x18000b5c0`
- `0x180019678`
- `0x180021574`
- `0x18002bd40`
- `0x18002db10`
- `0x18003a1f0`
- `0x180048cf0`
- `0x18004969c`
- `0x18004fc00`
- `0x180054508`
- `0x1800548b4`
- `0x180058590`
- `0x18005a360`
- `0x18005a3d0`
- `0x18005b210`
- `0x18005d250`
- `0x180065c70`
- `0x180078664`
- `0x18007b52c`
- `0x1800819b0`
- `0x18008868c`
- `0x18008f1e4`
- `0x180090040`
- `0x1800911f0`
- `0x180095f48`
- `0x180096e28`
- `0x1800974f0`
- `0x18009a3b4`
- `0x18009a414`
- `0x18009eb08`
- `0x1800a0a40`
- `0x1800a0d10`
- `0x1800a1c80`
- `0x1800a1e50`
- `0x1800a2d40`
- `0x1800a3040`
- `0x1800a3ba0`
- `0x1800a3ed0`
- `0x1800a45c0`
- `0x1800a48e0`
- `0x1800a4c70`
- `0x1800a5000`
- `0x1800a5510`
- `0x1800a56e0`
- `0x1800a6410`
- `0x1800a7640`

## callees

- `0x180009afc`
- `0x180014c40`
- `0x180067c48`
- `0x180070680`
- `0x18008b70c`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180009c13`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180009c13`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009bb5`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180009bb5`
- `ntdll!RtlReleaseResource` at `0x180009c2a`
- `ntdll!RtlReleaseResource` at `0x180009c2a`
- `ntdll!RtlAcquireResourceShared` at `0x180009ba3`
- `ntdll!RtlAcquireResourceShared` at `0x180009ba3`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009b9b`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009b9b`

## string_xrefs

- `0x180009beb`: `REMOVE logonsess %p for %#x:%#x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct _KERB_LOGON_SESSION *__fastcall KerbLocateLogonSession(const struct _LUID *a1, char a2)
{
  struct _KERB_LOGON_SESSION *v3; // rbx
  unsigned __int16 *v4; // rax
  void *v5; // rdi
  const void *v6; // rax
  char *Buffer; // [rsp+40h] [rbp-C0h] BYREF
  char v9; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+90h] [rbp-70h]
  _BYTE v11[184]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v12; // [rsp+180h] [rbp+80h]
  __int64 v13; // [rsp+1A8h] [rbp+A8h]
  __int64 v14; // [rsp+1B0h] [rbp+B0h]
  __int128 v15; // [rsp+1D0h] [rbp+D0h]
  __int64 v16; // [rsp+1F8h] [rbp+F8h]
  int v17; // [rsp+200h] [rbp+100h]
  __int64 v18; // [rsp+370h] [rbp+270h]
  __int128 v19; // [rsp+378h] [rbp+278h]
  __int128 v20; // [rsp+388h] [rbp+288h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v3 = 0;
  v10 = (__int64)*a1;
  Buffer = &v9;
  if ( a2 )
    RtlAcquireResourceExclusive(&KerbGlobalLogonSessionTableLock, 1u);
  else
    RtlAcquireResourceShared(&KerbGlobalLogonSessionTableLock, 1u);
  v4 = (unsigned __int16 *)RtlLookupElementGenericTableAvl(&KerbGlobalLogonSessionTable, &Buffer);
  v5 = v4;
  if ( v4 )
  {
    v3 = *(struct _KERB_LOGON_SESSION **)v4;
    if ( a2 )
    {
      if ( v3 )
        v6 = (const void *)v4[1];
      else
        v6 = 0;
      KerbTracerT::Log(
        10,
        "KerbLocateLogonSession",
        537,
        "REMOVE logonsess %p for %#x:%#x\n",
        v6,
        *((_DWORD *)v3 + 17),
        *((_DWORD *)v3 + 16));
      RtlDeleteElementGenericTableAvl(&KerbGlobalLogonSessionTable, v5);
    }
    else
    {
      KerbReferenceLogonSession(*(struct _KERB_LOGON_SESSION **)v4);
    }
  }
  RtlReleaseResource(&KerbGlobalLogonSessionTableLock);
  _KERB_PRIMARY_CREDENTIAL::~_KERB_PRIMARY_CREDENTIAL((_KERB_PRIMARY_CREDENTIAL *)v11);
  return v3;
}

```

## disassembly

```asm
0x180009afc  push    rbp
0x180009afe  push    rbx
0x180009aff  push    rsi
0x180009b00  push    rdi
0x180009b01  lea     rbp, [rsp-318h]
0x180009b09  sub     rsp, 418h
0x180009b10  mov     rax, cs:__security_cookie
0x180009b17  xor     rax, rsp
0x180009b1a  mov     [rbp+330h+var_30], rax
0x180009b21  mov     sil, dl
0x180009b24  xorps   xmm0, xmm0
0x180009b27  movdqa  [rbp+330h+var_2B0], xmm0
0x180009b2f  mov     [rbp+330h+var_288], 0
0x180009b3a  mov     [rbp+330h+var_280], 0
0x180009b45  movdqa  [rbp+330h+var_260], xmm0
0x180009b4d  mov     [rbp+330h+var_238], 0
0x180009b58  mov     [rbp+330h+var_230], 0
0x180009b62  mov     [rbp+330h+var_C0], 0
0x180009b6d  movups  [rbp+330h+var_B8], xmm0
0x180009b74  movups  [rbp+330h+var_A8], xmm0
0x180009b7b  xor     ebx, ebx
0x180009b7d  mov     rax, [rcx]
0x180009b80  mov     [rbp+330h+var_3A0], rax
0x180009b84  lea     rax, [rsp+430h+var_3E0]
0x180009b89  mov     [rsp+430h+Buffer], rax
0x180009b8e  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x180009b95  test    dl, dl
0x180009b97  mov     dl, 1; Wait
0x180009b99  jz      short loc_180009BA3
0x180009b9b  call    cs:__imp_RtlAcquireResourceExclusive
0x180009ba1  jmp     short loc_180009BA9
0x180009ba3  call    cs:__imp_RtlAcquireResourceShared
0x180009ba9  lea     rdx, [rsp+430h+Buffer]; Buffer
0x180009bae  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x180009bb5  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180009bbb  mov     rdi, rax
0x180009bbe  test    rax, rax
0x180009bc1  jz      short loc_180009C23
0x180009bc3  mov     rbx, [rax]
0x180009bc6  test    sil, sil
0x180009bc9  jz      short loc_180009C1B
0x180009bcb  mov     ecx, [rbx+40h]
0x180009bce  mov     edx, [rbx+44h]
0x180009bd1  test    rbx, rbx
0x180009bd4  jz      short loc_180009BDC
0x180009bd6  movzx   eax, word ptr [rax+2]
0x180009bda  jmp     short loc_180009BDE
0x180009bdc  xor     eax, eax
0x180009bde  mov     [rsp+430h+var_400], ecx
0x180009be2  mov     [rsp+430h+var_408], edx
0x180009be6  mov     [rsp+430h+var_410], rax
0x180009beb  lea     r9, aRemoveLogonses; "REMOVE logonsess %p for %#x:%#x\n"
0x180009bf2  mov     r8d, 219h
0x180009bf8  lea     rdx, aKerblocatelogo; "KerbLocateLogonSession"
0x180009bff  mov     ecx, 0Ah
0x180009c04  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180009c09  mov     rdx, rdi; Buffer
0x180009c0c  lea     rcx, ?KerbGlobalLogonSessionTable@@3U_RTL_AVL_TABLE@@A; Table
0x180009c13  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180009c19  jmp     short loc_180009C23
0x180009c1b  mov     rcx, rbx; struct _KERB_LOGON_SESSION *
0x180009c1e  call    ?KerbReferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbReferenceLogonSession(_KERB_LOGON_SESSION *)
0x180009c23  lea     rcx, ?KerbGlobalLogonSessionTableLock@@3U_RTL_RESOURCE@@A; Resource
0x180009c2a  call    cs:__imp_RtlReleaseResource
0x180009c30  nop
0x180009c31  lea     rcx, [rbp+330h+var_368]; this
0x180009c35  call    ??1_KERB_PRIMARY_CREDENTIAL@@QEAA@XZ; _KERB_PRIMARY_CREDENTIAL::~_KERB_PRIMARY_CREDENTIAL(void)
0x180009c3a  mov     rax, rbx
0x180009c3d  mov     rcx, [rbp+330h+var_30]
0x180009c44  xor     rcx, rsp; StackCookie
0x180009c47  call    __security_check_cookie
0x180009c4c  add     rsp, 418h
0x180009c53  pop     rdi
0x180009c54  pop     rsi
0x180009c55  pop     rbx
0x180009c56  pop     rbp
0x180009c57  retn
```
