# CTypeInfo2::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18006dfb0`
- end: `0x18006e0c3`
- name: `?CreateInstance@CTypeInfo2@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `275`
- prototype: `int(CTypeInfo2 *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18003268c`
- `0x18004d900`
- `0x18006dfb0`
- `0x1800730d0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e0a5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006e0a5`

## pseudocode

```c
HRESULT __fastcall CTypeInfo2::CreateInstance(CTypeInfo2 *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r8
  int v13; // ebx
  IUnknown *ppunk; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  ppunk = 0;
  rclsid = 0;
  if ( !a4 )
    return -2147024809;
  *a4 = 0;
  v8 = *((unsigned int *)this + 4);
  v9 = *((_QWORD *)this + 3);
  if ( (unsigned int)v8 < *(_DWORD *)(v9 + 36) )
    v10 = *(_QWORD *)(v9 + 48) + v8;
  else
    v10 = 0;
  if ( *((_DWORD *)this + 8) != 5 )
    return -2147317571;
  if ( a2 )
    return -2147221232;
  rclsid = *CTypeLib2::PGuid((CTypeLib2 *)v9, *(_DWORD *)(v10 + 64));
  if ( a4 != (void **)(v11 + 40) || (*(_BYTE *)(v12 + 68) & 1) == 0 || GetActiveObject(&rclsid, 0, &ppunk) )
    return CoCreateInstance(&rclsid, 0, 0x15u, a3, a4);
  v13 = ((__int64 (__fastcall *)(IUnknown *, const struct _GUID *, void **))ppunk->lpVtbl->QueryInterface)(
          ppunk,
          a3,
          a4);
  ((void (__fastcall *)(IUnknown *))ppunk->lpVtbl->Release)(ppunk);
  return v13;
}

```

## disassembly

```asm
0x18006dfb0  mov     [rsp+arg_8], rbx
0x18006dfb5  push    rdi
0x18006dfb6  sub     rsp, 50h
0x18006dfba  mov     rax, cs:__security_cookie
0x18006dfc1  xor     rax, rsp
0x18006dfc4  mov     [rsp+58h+var_10], rax
0x18006dfc9  mov     rbx, r9
0x18006dfcc  mov     [rsp+58h+ppunk], 0
0x18006dfd5  xorps   xmm0, xmm0
0x18006dfd8  mov     rdi, r8
0x18006dfdb  mov     r9, rcx
0x18006dfde  movups  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x18006dfe3  test    rbx, rbx
0x18006dfe6  jnz     short loc_18006DFF2
0x18006dfe8  mov     eax, 80070057h
0x18006dfed  jmp     loc_18006E0AB
0x18006dff2  mov     qword ptr [rbx], 0
0x18006dff9  mov     eax, [rcx+10h]
0x18006dffc  mov     rcx, [rcx+18h]; this
0x18006e000  cmp     eax, [rcx+24h]
0x18006e003  jb      short loc_18006E00A
0x18006e005  xor     r8d, r8d
0x18006e008  jmp     short loc_18006E011
0x18006e00a  mov     r8, rax
0x18006e00d  add     r8, [rcx+30h]
0x18006e011  cmp     dword ptr [r9+20h], 5
0x18006e016  jz      short loc_18006E022
0x18006e018  mov     eax, 800288BDh
0x18006e01d  jmp     loc_18006E0AB
0x18006e022  test    rdx, rdx
0x18006e025  jz      short loc_18006E02E
0x18006e027  mov     eax, 80040110h
0x18006e02c  jmp     short loc_18006E0AB
0x18006e02e  mov     edx, [r8+40h]; unsigned int
0x18006e032  call    ?PGuid@CTypeLib2@@QEAAPEBU_GUID@@K@Z; CTypeLib2::PGuid(ulong)
0x18006e037  movups  xmm0, xmmword ptr [rax]
0x18006e03a  lea     rax, [r9+28h]
0x18006e03e  movdqu  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x18006e044  cmp     rbx, rax
0x18006e047  jnz     short loc_18006E092
0x18006e049  test    byte ptr [r8+44h], 1
0x18006e04e  jz      short loc_18006E092
0x18006e050  lea     r8, [rsp+58h+ppunk]; ppunk
0x18006e055  xor     edx, edx; pvReserved
0x18006e057  lea     rcx, [rsp+58h+rclsid]; rclsid
0x18006e05c  call    GetActiveObject
0x18006e061  test    eax, eax
0x18006e063  jnz     short loc_18006E092
0x18006e065  mov     rcx, [rsp+58h+ppunk]
0x18006e06a  mov     r8, rbx
0x18006e06d  mov     rdx, rdi
0x18006e070  mov     rax, [rcx]
0x18006e073  mov     rax, [rax]
0x18006e076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e07b  mov     rcx, [rsp+58h+ppunk]
0x18006e080  mov     ebx, eax
0x18006e082  mov     rdx, [rcx]
0x18006e085  mov     rax, [rdx+10h]
0x18006e089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e08e  mov     eax, ebx
0x18006e090  jmp     short loc_18006E0AB
0x18006e092  xor     edx, edx; pUnkOuter
0x18006e094  mov     [rsp+58h+ppv], rbx; ppv
0x18006e099  mov     r9, rdi; riid
0x18006e09c  lea     rcx, [rsp+58h+rclsid]; rclsid
0x18006e0a1  lea     r8d, [rdx+15h]; dwClsContext
0x18006e0a5  call    cs:__imp_CoCreateInstance
0x18006e0ab  mov     rcx, [rsp+58h+var_10]
0x18006e0b0  xor     rcx, rsp; StackCookie
0x18006e0b3  call    __security_check_cookie
0x18006e0b8  mov     rbx, [rsp+58h+arg_8]
0x18006e0bd  add     rsp, 50h
0x18006e0c1  pop     rdi
0x18006e0c2  retn
```
