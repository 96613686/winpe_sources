# SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(void *)

- ea: `0x180023910`
- end: `0x180023a45`
- name: `?InitializeFromSelfRelative@CSecurityDescriptor@SecUtil@@QEAAXPEAX@Z`
- size: `309`
- prototype: `void __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003970`

## callees

- `0x18001fea0`
- `0x1800238cc`
- `0x180023910`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180023993`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180023a16`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180023993`
- `api-ms-win-security-base-l1-1-0!MakeAbsoluteSD` at `0x180023a16`

## string_xrefs

- `0x180023a24`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
void __fastcall SecUtil::CSecurityDescriptor::InitializeFromSelfRelative(
        void **pAbsoluteSecurityDescriptor,
        PSECURITY_DESCRIPTOR pSelfRelativeSecurityDescriptor)
{
  const char *v4; // r9
  DWORD dwDaclSize; // [rsp+60h] [rbp-10h] BYREF
  DWORD dwAbsoluteSecurityDescriptorSize[3]; // [rsp+64h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  DWORD dwPrimaryGroupSize; // [rsp+B0h] [rbp+40h] BYREF
  DWORD dwOwnerSize; // [rsp+C0h] [rbp+50h] BYREF
  DWORD dwSaclSize; // [rsp+C8h] [rbp+58h] BYREF

  dwDaclSize = 0;
  dwSaclSize = 0;
  dwOwnerSize = 0;
  dwPrimaryGroupSize = 0;
  dwAbsoluteSecurityDescriptorSize[0] = 40;
  MakeAbsoluteSD(
    pSelfRelativeSecurityDescriptor,
    pAbsoluteSecurityDescriptor,
    dwAbsoluteSecurityDescriptorSize,
    0,
    &dwDaclSize,
    0,
    &dwSaclSize,
    0,
    &dwOwnerSize,
    0,
    &dwPrimaryGroupSize);
  SecUtil::CSID::AllocateBuffer(pAbsoluteSecurityDescriptor + 7, dwDaclSize);
  SecUtil::CSID::AllocateBuffer(pAbsoluteSecurityDescriptor + 8, dwSaclSize);
  SecUtil::CSID::AllocateBuffer(pAbsoluteSecurityDescriptor + 5, dwOwnerSize);
  SecUtil::CSID::AllocateBuffer(pAbsoluteSecurityDescriptor + 6, dwPrimaryGroupSize);
  if ( !MakeAbsoluteSD(
          pSelfRelativeSecurityDescriptor,
          pAbsoluteSecurityDescriptor,
          dwAbsoluteSecurityDescriptorSize,
          (PACL)pAbsoluteSecurityDescriptor[7],
          &dwDaclSize,
          (PACL)pAbsoluteSecurityDescriptor[8],
          &dwSaclSize,
          pAbsoluteSecurityDescriptor[5],
          &dwOwnerSize,
          pAbsoluteSecurityDescriptor[6],
          &dwPrimaryGroupSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
      v4);
}

```

## disassembly

```asm
0x180023910  mov     r11, rsp
0x180023913  push    rbp
0x180023914  push    rbx
0x180023915  push    rsi
0x180023916  push    rdi
0x180023917  push    r12
0x180023919  push    r14
0x18002391b  push    r15
0x18002391d  mov     rbp, rsp
0x180023920  sub     rsp, 70h
0x180023924  mov     r12, rdx
0x180023927  mov     [rbp+dwDaclSize], 0
0x18002392e  lea     rax, [rbp+dwPrimaryGroupSize]
0x180023932  mov     [rbp+dwSaclSize], 0
0x180023939  mov     [r11-58h], rax
0x18002393d  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x180023941  mov     qword ptr [r11-60h], 0
0x180023949  lea     rax, [rbp+dwOwnerSize]
0x18002394d  mov     [r11-68h], rax
0x180023951  mov     r15, rcx
0x180023954  mov     qword ptr [r11-70h], 0
0x18002395c  lea     rax, [rbp+dwSaclSize]
0x180023960  mov     [r11-78h], rax
0x180023964  mov     rdx, rcx; pAbsoluteSecurityDescriptor
0x180023967  lea     rax, [rbp+dwDaclSize]
0x18002396b  mov     qword ptr [r11-80h], 0
0x180023973  xor     r9d, r9d; pDacl
0x180023976  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x18002397b  mov     rcx, r12; pSelfRelativeSecurityDescriptor
0x18002397e  mov     [rbp+dwOwnerSize], 0
0x180023985  mov     [rbp+dwPrimaryGroupSize], 0
0x18002398c  mov     [rbp+dwAbsoluteSecurityDescriptorSize], 28h ; '('
0x180023993  call    cs:__imp_MakeAbsoluteSD
0x180023999  mov     edx, [rbp+dwDaclSize]; unsigned int
0x18002399c  lea     rcx, [r15+38h]; this
0x1800239a0  call    ?AllocateBuffer@CSID@SecUtil@@QEAAXK@Z; SecUtil::CSID::AllocateBuffer(ulong)
0x1800239a5  mov     edx, [rbp+dwSaclSize]; unsigned int
0x1800239a8  lea     rcx, [r15+40h]; this
0x1800239ac  call    ?AllocateBuffer@CSID@SecUtil@@QEAAXK@Z; SecUtil::CSID::AllocateBuffer(ulong)
0x1800239b1  mov     edx, [rbp+dwOwnerSize]; unsigned int
0x1800239b4  lea     rcx, [r15+28h]; this
0x1800239b8  call    ?AllocateBuffer@CSID@SecUtil@@QEAAXK@Z; SecUtil::CSID::AllocateBuffer(ulong)
0x1800239bd  mov     edx, [rbp+dwPrimaryGroupSize]; unsigned int
0x1800239c0  lea     rcx, [r15+30h]; this
0x1800239c4  call    ?AllocateBuffer@CSID@SecUtil@@QEAAXK@Z; SecUtil::CSID::AllocateBuffer(ulong)
0x1800239c9  mov     r9, [r15+38h]; pDacl
0x1800239cd  lea     rax, [rbp+dwPrimaryGroupSize]
0x1800239d1  mov     [rsp+70h+lpdwPrimaryGroupSize], rax; lpdwPrimaryGroupSize
0x1800239d6  lea     r8, [rbp+dwAbsoluteSecurityDescriptorSize]; lpdwAbsoluteSecurityDescriptorSize
0x1800239da  mov     rax, [r15+30h]
0x1800239de  mov     rdx, r15; pAbsoluteSecurityDescriptor
0x1800239e1  mov     [rsp+70h+pPrimaryGroup], rax; pPrimaryGroup
0x1800239e6  mov     rcx, r12; pSelfRelativeSecurityDescriptor
0x1800239e9  lea     rax, [rbp+dwOwnerSize]
0x1800239ed  mov     [rsp+70h+lpdwOwnerSize], rax; lpdwOwnerSize
0x1800239f2  mov     rax, [r15+28h]
0x1800239f6  mov     [rsp+70h+pOwner], rax; pOwner
0x1800239fb  lea     rax, [rbp+dwSaclSize]
0x1800239ff  mov     [rsp+70h+lpdwSaclSize], rax; lpdwSaclSize
0x180023a04  mov     rax, [r15+40h]
0x180023a08  mov     [rsp+70h+pSacl], rax; pSacl
0x180023a0d  lea     rax, [rbp+dwDaclSize]
0x180023a11  mov     [rsp+70h+lpdwDaclSize], rax; lpdwDaclSize
0x180023a16  call    cs:__imp_MakeAbsoluteSD
0x180023a1c  test    eax, eax
0x180023a1e  jnz     short loc_180023A36
0x180023a20  mov     rcx, [rbp+38h]; this
0x180023a24  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\search\\com"...
0x180023a2b  mov     edx, 19Fh; void *
0x180023a30  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180023a36  add     rsp, 70h
0x180023a3a  pop     r15
0x180023a3c  pop     r14
0x180023a3e  pop     r12
0x180023a40  pop     rdi
0x180023a41  pop     rsi
0x180023a42  pop     rbx
0x180023a43  pop     rbp
0x180023a44  retn
```
