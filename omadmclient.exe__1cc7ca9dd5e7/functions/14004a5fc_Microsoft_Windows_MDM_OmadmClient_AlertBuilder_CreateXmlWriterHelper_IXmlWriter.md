# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::CreateXmlWriterHelper(IXmlWriter * *)

- ea: `0x14004a5fc`
- end: `0x14004a723`
- name: `?CreateXmlWriterHelper@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIXmlWriter@@@Z`
- size: `295`
- prototype: `static int(struct IXmlWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004a890`

## callees

- `0x14000b0f4`
- `0x14004a5fc`
- `0x140069010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x14004a621`
- `XmlLite!CreateXmlWriter` at `0x14004a621`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::CreateXmlWriterHelper(struct IXmlWriter **a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppvObject; // [rsp+38h] [rbp+10h] BYREF

  ppvObject = 0;
  v2 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 3, 1);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 2);
      v3 = v5;
      if ( v5 >= 0 )
      {
        *a1 = (struct IXmlWriter *)ppvObject;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
          (const char *)(unsigned int)v5,
          v7);
        if ( ppvObject )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x269,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v4,
        v7);
      if ( ppvObject )
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v2,
      v7);
    if ( ppvObject )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 16LL))(ppvObject);
  }
  return v3;
}

```

## disassembly

```asm
0x14004a5fc  mov     [rsp+arg_0], rbx
0x14004a601  push    rdi; int
0x14004a602  sub     rsp, 20h
0x14004a606  mov     rdi, rcx
0x14004a609  mov     [rsp+28h+ppvObject], 0
0x14004a612  xor     r8d, r8d; pMalloc
0x14004a615  lea     rdx, [rsp+28h+ppvObject]; ppvObject
0x14004a61a  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x14004a621  call    cs:__imp_CreateXmlWriter
0x14004a628  nop     dword ptr [rax+rax+00h]
0x14004a62d  mov     ebx, eax
0x14004a62f  test    eax, eax
0x14004a631  jns     short loc_14004A669
0x14004a633  mov     rcx, [rsp+28h]; this
0x14004a638  mov     r9d, eax; char *
0x14004a63b  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004a642  mov     edx, 266h; void *
0x14004a647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a64c  nop
0x14004a64d  mov     rcx, [rsp+28h+ppvObject]
0x14004a652  test    rcx, rcx
0x14004a655  jz      short loc_14004A664
0x14004a657  mov     rax, [rcx]
0x14004a65a  mov     rax, [rax+10h]
0x14004a65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a663  nop
0x14004a664  jmp     loc_14004A715
0x14004a669  mov     rcx, [rsp+28h+ppvObject]
0x14004a66e  mov     rax, [rcx]
0x14004a671  mov     edx, 3
0x14004a676  lea     r8d, [rdx-2]
0x14004a67a  mov     rax, [rax+28h]
0x14004a67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a683  mov     ebx, eax
0x14004a685  test    eax, eax
0x14004a687  jns     short loc_14004A6BC
0x14004a689  mov     rcx, [rsp+28h]; this
0x14004a68e  mov     r9d, eax; char *
0x14004a691  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004a698  mov     edx, 269h; void *
0x14004a69d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a6a2  nop
0x14004a6a3  mov     rcx, [rsp+28h+ppvObject]
0x14004a6a8  test    rcx, rcx
0x14004a6ab  jz      short loc_14004A6BA
0x14004a6ad  mov     rax, [rcx]
0x14004a6b0  mov     rax, [rax+10h]
0x14004a6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6b9  nop
0x14004a6ba  jmp     short loc_14004A715
0x14004a6bc  mov     rcx, [rsp+28h+ppvObject]
0x14004a6c1  mov     rax, [rcx]
0x14004a6c4  xor     r8d, r8d
0x14004a6c7  lea     edx, [r8+2]
0x14004a6cb  mov     rax, [rax+28h]
0x14004a6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a6d4  mov     ebx, eax
0x14004a6d6  test    eax, eax
0x14004a6d8  jns     short loc_14004A70D
0x14004a6da  mov     rcx, [rsp+28h]; this
0x14004a6df  mov     r9d, eax; char *
0x14004a6e2  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004a6e9  mov     edx, 26Ch; void *
0x14004a6ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a6f3  nop
0x14004a6f4  mov     rcx, [rsp+28h+ppvObject]
0x14004a6f9  test    rcx, rcx
0x14004a6fc  jz      short loc_14004A70B
0x14004a6fe  mov     rax, [rcx]
0x14004a701  mov     rax, [rax+10h]
0x14004a705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a70a  nop
0x14004a70b  jmp     short loc_14004A715
0x14004a70d  mov     rax, [rsp+28h+ppvObject]
0x14004a712  mov     [rdi], rax
0x14004a715  mov     eax, ebx
0x14004a717  mov     rbx, [rsp+28h+arg_0]
0x14004a71c  add     rsp, 20h
0x14004a720  pop     rdi
0x14004a721  retn
```
