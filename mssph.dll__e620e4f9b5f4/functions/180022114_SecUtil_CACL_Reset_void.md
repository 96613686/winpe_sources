# SecUtil::CACL::Reset(void)

- ea: `0x180022114`
- end: `0x180022171`
- name: `?Reset@CACL@SecUtil@@QEAAXXZ`
- size: `93`
- prototype: `void __fastcall(SecUtil::CACL *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020be0`

## callees

- `0x1800101c0`
- `0x180010220`
- `0x18001fea0`
- `0x180022114`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002214a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002214a`

## string_xrefs

- `0x180022159`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`

## pseudocode

```c
void __fastcall SecUtil::CACL::Reset(void **this)
{
  void *v2; // rcx
  struct _ACL *v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *this;
  if ( v2 )
  {
    operator delete(v2);
    *this = 0;
  }
  v3 = (struct _ACL *)operator new[](8u);
  *this = v3;
  if ( !InitializeAcl(v3, 8u, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v4);
}

```

## disassembly

```asm
0x180022114  push    rbx
0x180022116  sub     rsp, 20h
0x18002211a  mov     rbx, rcx
0x18002211d  mov     rcx, [rcx]; Block
0x180022120  test    rcx, rcx
0x180022123  jz      short loc_180022131
0x180022125  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002212a  mov     qword ptr [rbx], 0
0x180022131  mov     ecx, 8; unsigned __int64
0x180022136  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002213b  mov     edx, 8; nAclLength
0x180022140  mov     [rbx], rax
0x180022143  mov     rcx, rax; pAcl
0x180022146  lea     r8d, [rdx-6]; dwAclRevision
0x18002214a  call    cs:__imp_InitializeAcl
0x180022150  test    eax, eax
0x180022152  jnz     short loc_18002216B
0x180022154  mov     rcx, [rsp+28h]; this
0x180022159  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180022160  mov     edx, 16Ah; void *
0x180022165  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002216b  add     rsp, 20h
0x18002216f  pop     rbx
0x180022170  retn
```
