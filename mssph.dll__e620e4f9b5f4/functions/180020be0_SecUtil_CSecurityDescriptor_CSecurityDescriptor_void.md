# SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)

- ea: `0x180020be0`
- end: `0x180020c5d`
- name: `??0CSecurityDescriptor@SecUtil@@QEAA@XZ`
- size: `125`
- prototype: `_QWORD *__fastcall(_QWORD *pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x18001fea0`
- `0x180020be0`
- `0x180022114`
- `0x180023a4c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180020c27`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180020c27`

## string_xrefs

- `0x180020c36`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`

## pseudocode

```c
_QWORD *__fastcall SecUtil::CSecurityDescriptor::CSecurityDescriptor(_QWORD *pSecurityDescriptor)
{
  SecUtil::CACL *v2; // rcx
  int v3; // edx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  pSecurityDescriptor[5] = 0;
  pSecurityDescriptor[6] = 0;
  v2 = (SecUtil::CACL *)(pSecurityDescriptor + 7);
  *(_QWORD *)v2 = 0;
  SecUtil::CACL::Reset(v2);
  pSecurityDescriptor[8] = 0;
  SecUtil::CACL::Reset((SecUtil::CACL *)(pSecurityDescriptor + 8));
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v4);
  SecUtil::CSecurityDescriptor::SetDacl((SecUtil::CSecurityDescriptor *)pSecurityDescriptor, v3, 0, (int)v4);
  return pSecurityDescriptor;
}

```

## disassembly

```asm
0x180020be0  mov     [rsp+arg_0], rcx
0x180020be5  push    rbx
0x180020be6  sub     rsp, 20h
0x180020bea  mov     rbx, rcx
0x180020bed  mov     qword ptr [rcx+28h], 0
0x180020bf5  mov     qword ptr [rcx+30h], 0
0x180020bfd  add     rcx, 38h ; '8'; this
0x180020c01  mov     qword ptr [rcx], 0
0x180020c08  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x180020c0d  nop
0x180020c0e  lea     rcx, [rbx+40h]; this
0x180020c12  mov     qword ptr [rcx], 0
0x180020c19  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x180020c1e  nop
0x180020c1f  mov     edx, 1; dwRevision
0x180020c24  mov     rcx, rbx; pSecurityDescriptor
0x180020c27  call    cs:__imp_InitializeSecurityDescriptor
0x180020c2d  test    eax, eax
0x180020c2f  jnz     short loc_180020C48
0x180020c31  mov     rcx, [rsp+28h]; this
0x180020c36  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180020c3d  mov     edx, 18Dh; void *
0x180020c42  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180020c48  xor     r8d, r8d; struct _ACL *
0x180020c4b  mov     rcx, rbx; this
0x180020c4e  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x180020c53  nop
0x180020c54  mov     rax, rbx
0x180020c57  add     rsp, 20h
0x180020c5b  pop     rbx
0x180020c5c  retn
```
