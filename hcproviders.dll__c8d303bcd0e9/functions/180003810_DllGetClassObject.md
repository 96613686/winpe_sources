# DllGetClassObject

- ea: `0x180003810`
- end: `0x18000393b`
- name: `DllGetClassObject`
- size: `299`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003810`
- `0x180004fc8`
- `0x180005bdc`
- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int (*v3)(struct IUnknown **); // rdi
  __int64 v6; // r8
  __int64 v7; // rax
  CGenericClassFactory *v8; // rax
  CGenericClassFactory *v9; // rax
  CGenericClassFactory *v10; // rdi
  HRESULT v11; // ebx
  __int128 v13; // [rsp+20h] [rbp-58h]
  __int64 (__fastcall *v14)(struct IUnknown **); // [rsp+30h] [rbp-48h]
  __int128 v15; // [rsp+38h] [rbp-40h]
  __int64 (__fastcall *v16)(struct IUnknown **); // [rsp+48h] [rbp-30h]
  __int128 v17; // [rsp+50h] [rbp-28h]
  __int64 (__fastcall *v18)(struct IUnknown **); // [rsp+60h] [rbp-18h]

  *ppv = 0;
  v14 = UACCheckProvider_CreateInstance;
  v3 = 0;
  v13 = xmmword_18000D660;
  v16 = UACCheckProviderSSO_CreateInstance;
  v15 = xmmword_18000D640;
  v18 = StartupAppCheckProvider_CreateInstance;
  v6 = 0;
  v17 = xmmword_18000D650;
  do
  {
    if ( (unsigned int)v6 >= 3 )
      return -2147221231;
    v7 = *((_QWORD *)&v13 + 3 * v6) - *(_QWORD *)&rclsid->Data1;
    if ( !v7 )
      v7 = *((_QWORD *)&v13 + 3 * v6 + 1) - *(_QWORD *)rclsid->Data4;
    if ( !v7 )
      v3 = (int (*)(struct IUnknown **))*(&v14 + 3 * v6);
    v6 = (unsigned int)(v6 + 1);
  }
  while ( !v3 );
  v8 = (CGenericClassFactory *)operator new(0x18u);
  if ( !v8 )
    return -2147024882;
  v9 = CGenericClassFactory::CGenericClassFactory(v8, v3);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  v11 = (**(__int64 (__fastcall ***)(CGenericClassFactory *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
  (*(void (__fastcall **)(CGenericClassFactory *))(*(_QWORD *)v10 + 16LL))(v10);
  return v11;
}

```

## disassembly

```asm
0x180003810  mov     [rsp+arg_0], rbx
0x180003815  mov     [rsp+arg_8], rsi
0x18000381a  push    rdi
0x18000381b  sub     rsp, 70h
0x18000381f  movups  xmm0, cs:xmmword_18000D660
0x180003826  lea     rax, ?UACCheckProvider_CreateInstance@@YAJPEAPEAUIUnknown@@@Z; UACCheckProvider_CreateInstance(IUnknown * *)
0x18000382d  mov     qword ptr [r8], 0
0x180003834  mov     [rsp+78h+var_48], rax
0x180003839  xor     edi, edi
0x18000383b  movaps  [rsp+78h+var_58], xmm0
0x180003840  lea     rax, ?UACCheckProviderSSO_CreateInstance@@YAJPEAPEAUIUnknown@@@Z; UACCheckProviderSSO_CreateInstance(IUnknown * *)
0x180003847  movups  xmm0, cs:xmmword_18000D640
0x18000384e  mov     [rsp+78h+var_30], rax
0x180003853  mov     rbx, r8
0x180003856  lea     rax, ?StartupAppCheckProvider_CreateInstance@@YAJPEAPEAUIUnknown@@@Z; StartupAppCheckProvider_CreateInstance(IUnknown * *)
0x18000385d  mov     rsi, rdx
0x180003860  movups  [rsp+78h+var_40], xmm0
0x180003865  mov     rdx, rcx
0x180003868  mov     [rsp+78h+var_18], rax
0x18000386d  movups  xmm0, cs:xmmword_18000D650
0x180003874  xor     r8d, r8d
0x180003877  movaps  [rsp+78h+var_28], xmm0
0x18000387c  cmp     r8d, 3
0x180003880  jnb     loc_180003923
0x180003886  lea     rcx, [r8+r8*2]
0x18000388a  mov     rax, qword ptr [rsp+rcx*8+78h+var_58]
0x18000388f  sub     rax, [rdx]
0x180003892  jnz     short loc_18000389D
0x180003894  mov     rax, qword ptr [rsp+rcx*8+78h+var_58+8]
0x180003899  sub     rax, [rdx+8]
0x18000389d  test    rax, rax
0x1800038a0  jnz     short loc_1800038A7
0x1800038a2  mov     rdi, [rsp+rcx*8+78h+var_48]
0x1800038a7  inc     r8d
0x1800038aa  test    rdi, rdi
0x1800038ad  jz      short loc_18000387C
0x1800038af  mov     ecx, 18h; Size
0x1800038b4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800038b9  test    rax, rax
0x1800038bc  jz      short loc_18000390B
0x1800038be  mov     rdx, rdi; int (*)(struct IUnknown **)
0x1800038c1  mov     rcx, rax; this
0x1800038c4  call    ??0CGenericClassFactory@@QEAA@P6AJPEAPEAUIUnknown@@@Z@Z; CGenericClassFactory::CGenericClassFactory(long (*)(IUnknown * *))
0x1800038c9  mov     rdi, rax
0x1800038cc  test    rax, rax
0x1800038cf  jz      short loc_18000390B
0x1800038d1  mov     rcx, [rax]
0x1800038d4  mov     r8, rbx
0x1800038d7  mov     rdx, rsi
0x1800038da  mov     rax, [rcx]
0x1800038dd  mov     rcx, rdi
0x1800038e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038e5  mov     rcx, [rdi]
0x1800038e8  mov     ebx, eax
0x1800038ea  mov     rax, [rcx+10h]
0x1800038ee  mov     rcx, rdi
0x1800038f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038f6  mov     eax, ebx
0x1800038f8  lea     r11, [rsp+78h+var_8]
0x1800038fd  mov     rbx, [r11+10h]
0x180003901  mov     rsi, [r11+18h]
0x180003905  mov     rsp, r11
0x180003908  pop     rdi
0x180003909  retn
0x18000390b  mov     eax, 8007000Eh
0x180003910  lea     r11, [rsp+78h+var_8]
0x180003915  mov     rbx, [r11+10h]
0x180003919  mov     rsi, [r11+18h]
0x18000391d  mov     rsp, r11
0x180003920  pop     rdi
0x180003921  retn
0x180003923  lea     r11, [rsp+78h+var_8]
0x180003928  mov     eax, 80040111h
0x18000392d  mov     rbx, [r11+10h]
0x180003931  mov     rsi, [r11+18h]
0x180003935  mov     rsp, r11
0x180003938  pop     rdi
0x180003939  retn
```
