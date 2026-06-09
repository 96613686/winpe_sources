# CCustRg::SetRegistrarClsid(_GUID const &)

- ea: `0x180043000`
- end: `0x18004305d`
- name: `?SetRegistrarClsid@CCustRg@@UEAAJAEBU_GUID@@@Z`
- size: `93`
- prototype: `HRESULT __fastcall(CCustRg *this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180043000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004304c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004304c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043015`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043015`

## pseudocode

```c
HRESULT __fastcall CCustRg::SetRegistrarClsid(CCustRg *this, const struct _GUID *a2)
{
  struct _GUID *v4; // rax

  v4 = (struct _GUID *)CoTaskMemAlloc(0x10u);
  *((_QWORD *)this + 8) = v4;
  if ( !v4 )
    return -2147024882;
  *v4 = *a2;
  return CoCreateInstance(*((const IID *const *)this + 8), 0, 0x17u, &IID_IComponentRegistrar, (LPVOID *)this + 9);
}

```

## disassembly

```asm
0x180043000  mov     [rsp+arg_0], rbx
0x180043005  push    rdi
0x180043006  sub     rsp, 30h
0x18004300a  mov     rbx, rcx
0x18004300d  mov     rdi, rdx
0x180043010  mov     ecx, 10h; cb
0x180043015  call    cs:__imp_CoTaskMemAlloc
0x18004301b  mov     [rbx+40h], rax
0x18004301f  test    rax, rax
0x180043022  jnz     short loc_18004302B
0x180043024  mov     eax, 8007000Eh
0x180043029  jmp     short loc_180043052
0x18004302b  movups  xmm0, xmmword ptr [rdi]
0x18004302e  xor     edx, edx; pUnkOuter
0x180043030  lea     r9, IID_IComponentRegistrar; riid
0x180043037  movdqu  xmmword ptr [rax], xmm0
0x18004303b  mov     rcx, [rbx+40h]; rclsid
0x18004303f  lea     rax, [rbx+48h]
0x180043043  lea     r8d, [rdx+17h]; dwClsContext
0x180043047  mov     [rsp+38h+ppv], rax; ppv
0x18004304c  call    cs:__imp_CoCreateInstance
0x180043052  mov     rbx, [rsp+38h+arg_0]
0x180043057  add     rsp, 30h
0x18004305b  pop     rdi
0x18004305c  retn
```
