# AddPackageNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180010f00`
- end: `0x180010f85`
- name: `?GetChildNodeNames@AddPackageNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `133`
- prototype: `__int64 __fastcall(AddPackageNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180010f00`
- `0x180011120`
- `0x180011184`

## string_xrefs

- `0x180010f1d`: `Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddPackageNode::GetChildNodeNames(AddPackageNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  unsigned __int16 **v4; // rax
  const char *v5; // r9
  __int64 result; // rax
  unsigned __int16 **v7; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  const unsigned __int16 *v9[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v9[0] = L"Path";
  v9[1] = L"Install";
  v7 = 0;
  v8 = 0;
  try
  {
    *a2 = ChildNodeNames::Initialize((ChildNodeNames *)&v7, v9, 2u);
    v8 = 0;
    v4 = v7;
    v7 = 0;
    *a3 = v4;
    ChildNodeNames::~ChildNodeNames((ChildNodeNames *)&v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x19,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackagenode.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180010f00  mov     r11, rsp
0x180010f03  mov     [r11+8], rbx
0x180010f07  push    rdi
0x180010f08  sub     rsp, 40h
0x180010f0c  mov     rbx, r8
0x180010f0f  mov     rdi, rdx
0x180010f12  lea     rax, ?gc_wszAddPackagePathNode@@3QBGB; "Path"
0x180010f19  mov     [r11-18h], rax
0x180010f1d  lea     rax, ?gc_wszAddPackageInstallNode@@3QBGB; "Install"
0x180010f24  mov     [r11-10h], rax
0x180010f28  mov     qword ptr [r11-28h], 0
0x180010f30  mov     [rsp+48h+var_20], 0
0x180010f38  mov     r8d, 2; unsigned __int64
0x180010f3e  lea     rdx, [r11-18h]; unsigned __int16 **
0x180010f42  lea     rcx, [r11-28h]; this
0x180010f46  call    ?Initialize@ChildNodeNames@@QEAAKPEAPEBG_K@Z; ChildNodeNames::Initialize(ushort const * *,unsigned __int64)
0x180010f4b  mov     [rdi], eax
0x180010f4d  mov     [rsp+48h+var_20], 0
0x180010f55  mov     rax, [rsp+48h+var_28]
0x180010f5a  mov     [rsp+48h+var_28], 0
0x180010f63  mov     [rbx], rax
0x180010f66  lea     rcx, [rsp+48h+var_28]; this
0x180010f6b  call    ??1ChildNodeNames@@QEAA@XZ; ChildNodeNames::~ChildNodeNames(void)
0x180010f70  nop
0x180010f71  xor     eax, eax
0x180010f73  jmp     short loc_180010F79
0x180010f75  mov     eax, [rsp+48h+arg_18]
0x180010f79  mov     rbx, [rsp+48h+arg_0]
0x180010f7e  add     rsp, 40h
0x180010f82  pop     rdi
0x180010f83  retn
```
