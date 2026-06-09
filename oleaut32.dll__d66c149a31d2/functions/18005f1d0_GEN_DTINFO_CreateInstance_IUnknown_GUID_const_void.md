# GEN_DTINFO::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18005f1d0`
- end: `0x18005f2f8`
- name: `?CreateInstance@GEN_DTINFO@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `296`
- prototype: `int(GEN_DTINFO *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18004d900`
- `0x18005f1d0`
- `0x1800730d0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f2da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f2da`

## pseudocode

```c
HRESULT __fastcall GEN_DTINFO::CreateInstance(GEN_DTINFO *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  __int64 v7; // r8
  int v8; // ebx
  IUnknown *ppunk; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  ppunk = 0;
  rclsid = 0;
  if ( !a4 )
    return -2147024809;
  *a4 = 0;
  v7 = *((_QWORD *)this + 7);
  if ( *(_DWORD *)(v7 + 152) != 5 )
    return -2147317571;
  if ( a2 )
    return -2147221232;
  if ( *(int *)(v7 + 148) < 2 )
    return -2147319767;
  rclsid = *(IID *)(*(_QWORD *)(*((_QWORD *)this + 3) + 32LL) + 80LL * *((unsigned __int16 *)this + 20) + 56);
  if ( a4 != (void **)(v7 + 208) || (*(_BYTE *)(v7 + 132) & 8) == 0 || GetActiveObject(&rclsid, 0, &ppunk) )
    return CoCreateInstance(&rclsid, 0, 0x15u, a3, a4);
  v8 = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, void **))ppunk->lpVtbl->QueryInterface)(ppunk, a3, a4);
  ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
  return v8;
}

```

## disassembly

```asm
0x18005f1d0  mov     [rsp+arg_8], rbx
0x18005f1d5  push    rdi
0x18005f1d6  sub     rsp, 50h
0x18005f1da  mov     rax, cs:__security_cookie
0x18005f1e1  xor     rax, rsp
0x18005f1e4  mov     [rsp+58h+var_10], rax
0x18005f1e9  mov     [rsp+58h+ppunk], 0
0x18005f1f2  xorps   xmm0, xmm0
0x18005f1f5  mov     rbx, r9
0x18005f1f8  mov     rdi, r8
0x18005f1fb  movups  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x18005f200  test    r9, r9
0x18005f203  jnz     short loc_18005F20F
0x18005f205  mov     eax, 80070057h
0x18005f20a  jmp     loc_18005F2E0
0x18005f20f  mov     qword ptr [r9], 0
0x18005f216  mov     r8, [rcx+38h]
0x18005f21a  cmp     dword ptr [r8+98h], 5
0x18005f222  jz      short loc_18005F22E
0x18005f224  mov     eax, 800288BDh
0x18005f229  jmp     loc_18005F2E0
0x18005f22e  test    rdx, rdx
0x18005f231  jz      short loc_18005F23D
0x18005f233  mov     eax, 80040110h
0x18005f238  jmp     loc_18005F2E0
0x18005f23d  cmp     dword ptr [r8+94h], 2
0x18005f245  jge     short loc_18005F251
0x18005f247  mov     eax, 80028029h
0x18005f24c  jmp     loc_18005F2E0
0x18005f251  movzx   eax, word ptr [rcx+28h]
0x18005f255  lea     rdx, [rax+rax*4]
0x18005f259  mov     rax, [rcx+18h]
0x18005f25d  add     rdx, rdx
0x18005f260  mov     rcx, [rax+20h]
0x18005f264  lea     rax, [r8+0D0h]
0x18005f26b  movups  xmm0, xmmword ptr [rcx+rdx*8+38h]
0x18005f270  movdqu  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x18005f276  cmp     rbx, rax
0x18005f279  jnz     short loc_18005F2C7
0x18005f27b  test    byte ptr [r8+84h], 8
0x18005f283  jz      short loc_18005F2C7
0x18005f285  lea     r8, [rsp+58h+ppunk]; ppunk
0x18005f28a  xor     edx, edx; pvReserved
0x18005f28c  lea     rcx, [rsp+58h+rclsid]; rclsid
0x18005f291  call    GetActiveObject
0x18005f296  test    eax, eax
0x18005f298  jnz     short loc_18005F2C7
0x18005f29a  mov     rcx, [rsp+58h+ppunk]
0x18005f29f  mov     r8, rbx
0x18005f2a2  mov     rdx, rdi
0x18005f2a5  mov     rax, [rcx]
0x18005f2a8  mov     rax, [rax]
0x18005f2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2b0  mov     rcx, [rsp+58h+ppunk]
0x18005f2b5  mov     ebx, eax
0x18005f2b7  mov     rdx, [rcx]
0x18005f2ba  mov     rax, [rdx+10h]
0x18005f2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2c3  mov     eax, ebx
0x18005f2c5  jmp     short loc_18005F2E0
0x18005f2c7  xor     edx, edx; pUnkOuter
0x18005f2c9  mov     [rsp+58h+ppv], rbx; ppv
0x18005f2ce  mov     r9, rdi; riid
0x18005f2d1  lea     rcx, [rsp+58h+rclsid]; rclsid
0x18005f2d6  lea     r8d, [rdx+15h]; dwClsContext
0x18005f2da  call    cs:__imp_CoCreateInstance
0x18005f2e0  mov     rcx, [rsp+58h+var_10]
0x18005f2e5  xor     rcx, rsp; StackCookie
0x18005f2e8  call    __security_check_cookie
0x18005f2ed  mov     rbx, [rsp+58h+arg_8]
0x18005f2f2  add     rsp, 50h
0x18005f2f6  pop     rdi
0x18005f2f7  retn
```
