# DllGetClassObject

- ea: `0x180007bc0`
- end: `0x180007ca7`
- name: `DllGetClassObject`
- size: `231`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001120`
- `0x180007bc0`
- `0x18001d35d`
- `0x18001e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int v7; // ebx
  struct CFactoryTemplate near **v8; // rsi
  _QWORD *v9; // rax

  *ppv = 0;
  if ( memcmp_0(riid, &IID_IUnknown, 0x10u) && memcmp_0(riid, &IID_IClassFactory, 0x10u) )
    return -2147467262;
  v7 = 0;
  while ( 1 )
  {
    v8 = &g_Templates + 5 * v7;
    if ( !memcmp_0(v8[1], rclsid, 0x10u) )
      break;
    if ( ++v7 >= 1 )
      return -2147221231;
  }
  v9 = operator new(0x18u);
  if ( v9 )
  {
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    v9[1] = v8;
    *v9 = &CClassFactory::`vftable';
    *((_DWORD *)v9 + 4) = 0;
    *ppv = v9;
    (*(void (__fastcall **)(_QWORD *))(*v9 + 8LL))(v9);
    return 0;
  }
  else
  {
    *ppv = 0;
    return -2147024882;
  }
}

```

## disassembly

```asm
0x180007bc0  push    rbx
0x180007bc2  push    rbp
0x180007bc3  push    rsi
0x180007bc4  push    rdi
0x180007bc5  push    r15
0x180007bc7  sub     rsp, 20h
0x180007bcb  mov     rbx, rdx
0x180007bce  mov     qword ptr [r8], 0
0x180007bd5  mov     rdi, r8
0x180007bd8  lea     rdx, IID_IUnknown; Buf2
0x180007bdf  mov     rbp, rcx
0x180007be2  mov     r15d, 10h
0x180007be8  mov     r8d, r15d; Size
0x180007beb  mov     rcx, rbx; Buf1
0x180007bee  call    memcmp_0
0x180007bf3  test    eax, eax
0x180007bf5  jz      short loc_180007C17
0x180007bf7  mov     r8d, r15d; Size
0x180007bfa  lea     rdx, IID_IClassFactory; Buf2
0x180007c01  mov     rcx, rbx; Buf1
0x180007c04  call    memcmp_0
0x180007c09  test    eax, eax
0x180007c0b  jz      short loc_180007C17
0x180007c0d  mov     eax, 80004002h
0x180007c12  jmp     loc_180007C9C
0x180007c17  xor     ebx, ebx
0x180007c19  movsxd  rax, ebx
0x180007c1c  mov     r8, r15; Size
0x180007c1f  mov     rdx, rbp; Buf2
0x180007c22  lea     rcx, [rax+rax*4]
0x180007c26  lea     rax, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x180007c2d  lea     rsi, [rax+rcx*8]
0x180007c31  mov     rcx, [rsi+8]; Buf1
0x180007c35  call    memcmp_0
0x180007c3a  test    eax, eax
0x180007c3c  jz      short loc_180007C4C
0x180007c3e  inc     ebx
0x180007c40  cmp     ebx, 1
0x180007c43  jl      short loc_180007C19
0x180007c45  mov     eax, 80040111h
0x180007c4a  jmp     short loc_180007C9C
0x180007c4c  mov     ecx, 18h; Size
0x180007c51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c56  mov     rdx, rax
0x180007c59  test    rax, rax
0x180007c5c  jz      short loc_180007C90
0x180007c5e  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180007c65  mov     [rdx+8], rsi
0x180007c69  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180007c70  mov     [rdx], rax
0x180007c73  mov     dword ptr [rdx+10h], 0
0x180007c7a  mov     [rdi], rdx
0x180007c7d  mov     rcx, [rdx]
0x180007c80  mov     rax, [rcx+8]
0x180007c84  mov     rcx, rdx
0x180007c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8c  xor     eax, eax
0x180007c8e  jmp     short loc_180007C9C
0x180007c90  mov     qword ptr [rdi], 0
0x180007c97  mov     eax, 8007000Eh
0x180007c9c  add     rsp, 20h
0x180007ca0  pop     r15
0x180007ca2  pop     rdi
0x180007ca3  pop     rsi
0x180007ca4  pop     rbp
0x180007ca5  pop     rbx
0x180007ca6  retn
```
