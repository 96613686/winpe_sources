# QASF_DllGetClassObject

- ea: `0x180001df0`
- end: `0x180001ed7`
- name: `QASF_DllGetClassObject`
- size: `231`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001020`
- `0x180001df0`
- `0x18001e5b9`
- `0x18001f010`

## pseudocode

```c
HRESULT __stdcall QASF_DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
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
    if ( ++v7 >= 5 )
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
0x180001df0  push    rbx
0x180001df2  push    rbp
0x180001df3  push    rsi
0x180001df4  push    rdi
0x180001df5  push    r15
0x180001df7  sub     rsp, 20h
0x180001dfb  mov     rbx, rdx
0x180001dfe  mov     qword ptr [r8], 0
0x180001e05  mov     rdi, r8
0x180001e08  lea     rdx, IID_IUnknown; Buf2
0x180001e0f  mov     rbp, rcx
0x180001e12  mov     r15d, 10h
0x180001e18  mov     r8d, r15d; Size
0x180001e1b  mov     rcx, rbx; Buf1
0x180001e1e  call    memcmp_0
0x180001e23  test    eax, eax
0x180001e25  jz      short loc_180001E47
0x180001e27  mov     r8d, r15d; Size
0x180001e2a  lea     rdx, IID_IClassFactory; Buf2
0x180001e31  mov     rcx, rbx; Buf1
0x180001e34  call    memcmp_0
0x180001e39  test    eax, eax
0x180001e3b  jz      short loc_180001E47
0x180001e3d  mov     eax, 80004002h
0x180001e42  jmp     loc_180001ECC
0x180001e47  xor     ebx, ebx
0x180001e49  movsxd  rax, ebx
0x180001e4c  mov     r8, r15; Size
0x180001e4f  mov     rdx, rbp; Buf2
0x180001e52  lea     rcx, [rax+rax*4]
0x180001e56  lea     rax, ?g_Templates@@3PAVCFactoryTemplate@@A; CFactoryTemplate near * g_Templates
0x180001e5d  lea     rsi, [rax+rcx*8]
0x180001e61  mov     rcx, [rsi+8]; Buf1
0x180001e65  call    memcmp_0
0x180001e6a  test    eax, eax
0x180001e6c  jz      short loc_180001E7C
0x180001e6e  inc     ebx
0x180001e70  cmp     ebx, 5
0x180001e73  jl      short loc_180001E49
0x180001e75  mov     eax, 80040111h
0x180001e7a  jmp     short loc_180001ECC
0x180001e7c  mov     ecx, 18h; Size
0x180001e81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e86  mov     rdx, rax
0x180001e89  test    rax, rax
0x180001e8c  jz      short loc_180001EC0
0x180001e8e  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x180001e95  mov     [rdx+8], rsi
0x180001e99  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180001ea0  mov     [rdx], rax
0x180001ea3  mov     dword ptr [rdx+10h], 0
0x180001eaa  mov     [rdi], rdx
0x180001ead  mov     rcx, [rdx]
0x180001eb0  mov     rax, [rcx+8]
0x180001eb4  mov     rcx, rdx
0x180001eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ebc  xor     eax, eax
0x180001ebe  jmp     short loc_180001ECC
0x180001ec0  mov     qword ptr [rdi], 0
0x180001ec7  mov     eax, 8007000Eh
0x180001ecc  add     rsp, 20h
0x180001ed0  pop     r15
0x180001ed2  pop     rdi
0x180001ed3  pop     rsi
0x180001ed4  pop     rbp
0x180001ed5  pop     rbx
0x180001ed6  retn
```
