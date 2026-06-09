# dxrt11::Direct3DDevice::GetIids(ulong *,_GUID * *)

- ea: `0x1800d9fc0`
- end: `0x1800da02a`
- name: `?GetIids@Direct3DDevice@dxrt11@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(dxrt11::Direct3DDevice *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800da030`

## callees

- `0x1800d9f94`
- `0x1800d9fc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9fe2`

## pseudocode

```c
__int64 __fastcall dxrt11::Direct3DDevice::GetIids(dxrt11::Direct3DDevice *this, unsigned int *a2, struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_a37624ab_8d5f_4650_9d3e_9eae3d9bc670;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800d9fc0  mov     [rsp+arg_0], rbx
0x1800d9fc5  push    rdi
0x1800d9fc6  sub     rsp, 20h
0x1800d9fca  mov     qword ptr [r8], 0
0x1800d9fd1  mov     ecx, 30h ; '0'; cb
0x1800d9fd6  mov     dword ptr [rdx], 0
0x1800d9fdc  mov     rbx, r8
0x1800d9fdf  mov     rdi, rdx
0x1800d9fe2  call    cs:__imp_CoTaskMemAlloc
0x1800d9fe8  mov     r8, rax
0x1800d9feb  test    rax, rax
0x1800d9fee  jnz     short loc_1800D9FF7
0x1800d9ff0  mov     eax, 8007000Eh
0x1800d9ff5  jmp     short loc_1800DA01F
0x1800d9ff7  movups  xmm0, xmmword ptr cs:_GUID_a37624ab_8d5f_4650_9d3e_9eae3d9bc670.Data1
0x1800d9ffe  lea     rdx, [rsp+28h+arg_8]
0x1800da003  mov     [rsp+28h+arg_8], 1
0x1800da00b  movdqu  xmmword ptr [rax], xmm0
0x1800da00f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIClosable@Foundation@Windows@@U?$CloakedIid@UIDirect3DDxgiInterfaceAccess@Direct3D11@DirectX@Graphics@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<Windows::Graphics::DirectX::Direct3D11::IDirect3DDxgiInterfaceAccess>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800da014  mov     dword ptr [rdi], 3
0x1800da01a  xor     eax, eax
0x1800da01c  mov     [rbx], r8
0x1800da01f  mov     rbx, [rsp+28h+arg_0]
0x1800da024  add     rsp, 20h
0x1800da028  pop     rdi
0x1800da029  retn
```
