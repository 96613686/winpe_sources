# DomainNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800122f0`
- end: `0x1800123a4`
- name: `?GetChildNodeNames@DomainNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `180`
- prototype: `__int64 __fastcall(DomainNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180011120`
- `0x180011184`
- `0x1800122f0`

## string_xrefs

- `0x180012302`: `ComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DomainNode::GetChildNodeNames(DomainNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  unsigned __int16 **v4; // rax
  const char *v5; // r9
  __int64 result; // rax
  unsigned __int16 **v7; // [rsp+20h] [rbp-48h] BYREF
  int v8; // [rsp+28h] [rbp-40h]
  const unsigned __int16 *v9[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v9[0] = L"ComputerName";
  v9[1] = L"DomainName";
  v9[2] = L"AccountOU";
  v9[3] = L"Account";
  v9[4] = L"Password";
  v9[5] = L"Options";
  v7 = 0;
  v8 = 0;
  try
  {
    *a2 = ChildNodeNames::Initialize((ChildNodeNames *)&v7, v9, 6u);
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
                           (void *)0x23,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x1800122f0  mov     r11, rsp
0x1800122f3  mov     [r11+8], rbx
0x1800122f7  push    rdi
0x1800122f8  sub     rsp, 60h
0x1800122fc  mov     rbx, r8
0x1800122ff  mov     rdi, rdx
0x180012302  lea     rax, ?gc_wszAccountsDomainComputerNameNode@@3QBGB; "ComputerName"
0x180012309  mov     [r11-38h], rax
0x18001230d  lea     rax, ?gc_wszAccountsDomainDomainNameNode@@3QBGB; "DomainName"
0x180012314  mov     [r11-30h], rax
0x180012318  lea     rax, ?gc_wszAccountsDomainAccountOUNode@@3QBGB; "AccountOU"
0x18001231f  mov     [r11-28h], rax
0x180012323  lea     rax, ?gc_wszAccountsDomainAccountNode@@3QBGB; "Account"
0x18001232a  mov     [r11-20h], rax
0x18001232e  lea     rax, ?gc_wszAccountsDomainPasswordNode@@3QBGB; "Password"
0x180012335  mov     [r11-18h], rax
0x180012339  lea     rax, ?gc_wszAccountsDomainOptionsNode@@3QBGB; "Options"
0x180012340  mov     [r11-10h], rax
0x180012344  mov     qword ptr [r11-48h], 0
0x18001234c  mov     [rsp+68h+var_40], 0
0x180012354  mov     r8d, 6; unsigned __int64
0x18001235a  lea     rdx, [r11-38h]; unsigned __int16 **
0x18001235e  lea     rcx, [r11-48h]; this
0x180012362  call    ?Initialize@ChildNodeNames@@QEAAKPEAPEBG_K@Z; ChildNodeNames::Initialize(ushort const * *,unsigned __int64)
0x180012367  mov     [rdi], eax
0x180012369  mov     [rsp+68h+var_40], 0
0x180012371  mov     rax, [rsp+68h+var_48]
0x180012376  mov     [rsp+68h+var_48], 0
0x18001237f  mov     [rbx], rax
0x180012382  lea     rcx, [rsp+68h+var_48]; this
0x180012387  call    ??1ChildNodeNames@@QEAA@XZ; ChildNodeNames::~ChildNodeNames(void)
0x18001238c  nop
0x18001238d  xor     eax, eax
0x18001238f  jmp     short loc_180012398
0x180012391  mov     eax, [rsp+68h+arg_18]
0x180012398  mov     rbx, [rsp+68h+arg_0]
0x18001239d  add     rsp, 60h
0x1800123a1  pop     rdi
0x1800123a2  retn
```
