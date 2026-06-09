# ComputeStorageInternal::DeleteFolderWithReparsePoints(ushort const *)

- ea: `0x18001a5f4`
- end: `0x18001a6c3`
- name: `?DeleteFolderWithReparsePoints@ComputeStorageInternal@@YAXPEBG@Z`
- size: `207`
- prototype: `void __fastcall(ComputeStorageInternal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014330`

## callees

- `0x180002690`
- `0x180008a8c`
- `0x18000971c`
- `0x1800127bc`
- `0x18001a5f4`

## import_xrefs

- `wc_storage!WcDestroyLayer` at `0x18001a654`
- `wc_storage!WcDestroyLayer` at `0x18001a654`

## string_xrefs

- `0x18001a6b1`: `onecore\vm\compute\dll\lib\storage\computestorageinternal.cpp`

## pseudocode

```c
void __fastcall ComputeStorageInternal::DeleteFolderWithReparsePoints(
        ComputeStorageInternal *this,
        const unsigned __int16 *a2)
{
  char v3; // di
  unsigned int v4; // eax
  __int64 v5; // r8
  const char *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  const char *v9; // r9
  int v10[4]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v11; // [rsp+30h] [rbp-38h]
  __int128 v12; // [rsp+38h] [rbp-30h] BYREF
  __int64 v13; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v12 = 0;
  v13 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)&v12, 17);
  *(_OWORD *)v10 = 0;
  v11 = 0;
  Vml::TemporaryPrivilege::TemporaryPrivilege((Vml::TemporaryPrivilege *)v10, 18);
  v3 = 1;
  v4 = WcDestroyLayer(this, 1);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -2147024894 )
    v3 = 0;
  if ( v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\computestorageinternal.cpp",
      (const char *)v4,
      v10[0]);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)v10, 0x80000000LL, v5, v6);
  Vml::TemporaryPrivilege::~TemporaryPrivilege((const struct _LUID *)&v12, v7, v8, v9);
}

```

## disassembly

```asm
0x18001a5f4  mov     [rsp+arg_8], rbx
0x18001a5f9  push    rdi
0x18001a5fa  sub     rsp, 60h
0x18001a5fe  mov     rax, cs:__security_cookie
0x18001a605  xor     rax, rsp
0x18001a608  mov     [rsp+68h+var_18], rax
0x18001a60d  mov     rbx, rcx
0x18001a610  xorps   xmm0, xmm0
0x18001a613  xor     eax, eax
0x18001a615  movups  [rsp+68h+var_30], xmm0
0x18001a61a  mov     [rsp+68h+var_20], rax
0x18001a61f  lea     edx, [rax+11h]; int
0x18001a622  lea     rcx, [rsp+68h+var_30]; this
0x18001a627  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001a62c  nop
0x18001a62d  xorps   xmm0, xmm0
0x18001a630  xor     eax, eax
0x18001a632  movups  xmmword ptr [rsp+68h+var_48], xmm0; int
0x18001a637  mov     [rsp+68h+var_38], rax
0x18001a63c  lea     edx, [rax+12h]; int
0x18001a63f  lea     rcx, [rsp+68h+var_48]; this
0x18001a644  call    ??0TemporaryPrivilege@Vml@@QEAA@J@Z; Vml::TemporaryPrivilege::TemporaryPrivilege(long)
0x18001a649  nop
0x18001a64a  mov     edi, 1
0x18001a64f  mov     edx, edi
0x18001a651  mov     rcx, rbx
0x18001a654  call    cs:__imp_WcDestroyLayer
0x18001a65b  nop     dword ptr [rax+rax+00h]
0x18001a660  mov     edx, 80000000h
0x18001a665  lea     ecx, [rax+rdx]
0x18001a668  test    edx, ecx
0x18001a66a  jnz     short loc_18001A673
0x18001a66c  cmp     eax, 80070002h
0x18001a671  jnz     short loc_18001A676
0x18001a673  xor     dil, dil
0x18001a676  mov     rcx, [rsp+68h]; this
0x18001a67b  test    dil, dil
0x18001a67e  jnz     short loc_18001A6AE
0x18001a680  lea     rcx, [rsp+68h+var_48]; this
0x18001a685  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001a68a  nop
0x18001a68b  lea     rcx, [rsp+68h+var_30]; this
0x18001a690  call    ??1TemporaryPrivilege@Vml@@QEAA@XZ; Vml::TemporaryPrivilege::~TemporaryPrivilege(void)
0x18001a695  mov     rcx, [rsp+68h+var_18]
0x18001a69a  xor     rcx, rsp; StackCookie
0x18001a69d  call    __security_check_cookie
0x18001a6a2  mov     rbx, [rsp+68h+arg_8]
0x18001a6a7  add     rsp, 60h
0x18001a6ab  pop     rdi
0x18001a6ac  retn
0x18001a6ae  mov     r9d, eax; char *
0x18001a6b1  lea     r8, aOnecoreVmCompu_6; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x18001a6b8  mov     edx, 21h ; '!'; void *
0x18001a6bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
