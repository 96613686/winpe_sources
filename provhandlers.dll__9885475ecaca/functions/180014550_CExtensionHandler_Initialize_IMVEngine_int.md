# CExtensionHandler::Initialize(IMVEngine *,int *)

- ea: `0x180014550`
- end: `0x1800145f1`
- name: `?Initialize@CExtensionHandler@@UEAAJPEAUIMVEngine@@PEAH@Z`
- size: `161`
- prototype: `__int64 __fastcall(CExtensionHandler *__hidden this, struct IMVEngine *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x1800076a4`
- `0x18000ee90`
- `0x180014550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800145cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800145cd`

## string_xrefs

- `0x18001456d`: `onecoreuap\admin\prov\multivariant\handlers\extension\extensionhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExtensionHandler::Initialize(CExtensionHandler *this, struct IMVEngine *a2, int *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int pdwType; // [rsp+20h] [rbp-38h]
  DWORD pcbData[6]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int pvData; // [rsp+78h] [rbp+20h] BYREF

  v4 = CHandlerBase::Initialize(this, a2, a3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    pvData = 0;
    pcbData[0] = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\OEM\\ADC\\CustomizationKeys",
            L"UseCarrierIDAsKey",
            0x10u,
            0,
            &pvData,
            pcbData) )
    {
      if ( pvData )
        *((_DWORD *)this + 15) = 1;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\extension\\extensionhandler.cpp",
      (const char *)(unsigned int)v4,
      pdwType);
    return v5;
  }
}

```

## disassembly

```asm
0x180014550  mov     [rsp+arg_0], rbx
0x180014555  push    rdi
0x180014556  sub     rsp, 50h
0x18001455a  mov     rdi, rcx
0x18001455d  call    ?Initialize@CHandlerBase@@UEAAJPEAUIMVEngine@@PEAH@Z; CHandlerBase::Initialize(IMVEngine *,int *)
0x180014562  mov     ebx, eax
0x180014564  test    eax, eax
0x180014566  jns     short loc_180014585
0x180014568  mov     rcx, [rsp+58h]; this
0x18001456d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180014574  mov     r9d, eax; char *
0x180014577  mov     edx, 7Ch ; '|'; void *
0x18001457c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014581  mov     eax, ebx
0x180014583  jmp     short loc_1800145E6
0x180014585  lea     rax, [rsp+58h+var_18]
0x18001458a  mov     [rsp+58h+arg_18], 0
0x180014592  mov     [rsp+58h+pcbData], rax; pcbData
0x180014597  lea     r8, ?sc_szUseCarrierIDAsKey@CExtensionHandler@@1QBGB; "UseCarrierIDAsKey"
0x18001459e  lea     rax, [rsp+58h+arg_18]
0x1800145a3  mov     [rsp+58h+var_18], 4
0x1800145ab  mov     [rsp+58h+pvData], rax; pvData
0x1800145b0  lea     rdx, ?gc_szCustomizationRootReg@@3QBGB; "Software\\OEM\\ADC\\CustomizationKeys"
0x1800145b7  mov     r9d, 10h; dwFlags
0x1800145bd  mov     [rsp+58h+pdwType], 0; pdwType
0x1800145c6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800145cd  call    cs:__imp_RegGetValueW
0x1800145d3  test    eax, eax
0x1800145d5  jnz     short loc_1800145E4
0x1800145d7  cmp     [rsp+58h+arg_18], eax
0x1800145db  jz      short loc_1800145E4
0x1800145dd  mov     dword ptr [rdi+3Ch], 1
0x1800145e4  xor     eax, eax
0x1800145e6  mov     rbx, [rsp+58h+arg_0]
0x1800145eb  add     rsp, 50h
0x1800145ef  pop     rdi
0x1800145f0  retn
```
