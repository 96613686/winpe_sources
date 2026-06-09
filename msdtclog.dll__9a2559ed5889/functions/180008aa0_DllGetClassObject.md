# DllGetClassObject

- ea: `0x180008aa0`
- end: `0x180008b60`
- name: `DllGetClassObject`
- size: `192`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x1800012c0`
- `0x180001300`
- `0x180008aa0`
- `0x18000e64c`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v6; // rbx
  HRESULT v7; // edi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  if ( *(_OWORD *)rclsid != *(_OWORD *)&CLSID_CLogMgr )
    return -2147221231;
  v6 = operator new(0x48u);
  if ( v6 )
  {
    *(_QWORD *)v6 = &CFLogMgr::`vftable';
    CSemExclusive::CSemExclusive((CSemExclusive *)(v6 + 4));
    v6[2] = 0;
  }
  else
  {
    v6 = 0;
  }
  if ( !v6 )
    return -2147024882;
  v7 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
  if ( v7 < 0 )
    operator delete(v6);
  return v7;
}

```

## disassembly

```asm
0x180008aa0  mov     [rsp+arg_0], rbx
0x180008aa5  mov     [rsp+arg_8], rsi
0x180008aaa  push    rdi
0x180008aab  sub     rsp, 20h
0x180008aaf  mov     rdi, r8
0x180008ab2  mov     rsi, rdx
0x180008ab5  test    r8, r8
0x180008ab8  jnz     short loc_180008AC4
0x180008aba  mov     eax, 80070057h
0x180008abf  jmp     loc_180008B50
0x180008ac4  mov     qword ptr [r8], 0
0x180008acb  mov     rax, [rcx]
0x180008ace  cmp     rax, qword ptr cs:CLSID_CLogMgr.Data1
0x180008ad5  jnz     short loc_180008B4B
0x180008ad7  mov     rax, [rcx+8]
0x180008adb  cmp     rax, qword ptr cs:CLSID_CLogMgr.Data4
0x180008ae2  jnz     short loc_180008B4B
0x180008ae4  mov     ecx, 48h ; 'H'; Size
0x180008ae9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008aee  mov     rbx, rax
0x180008af1  mov     [rsp+28h+arg_10], rax
0x180008af6  test    rax, rax
0x180008af9  jz      short loc_180008B17
0x180008afb  lea     rax, ??_7CFLogMgr@@6B@; const CFLogMgr::`vftable'
0x180008b02  mov     [rbx], rax
0x180008b05  lea     rcx, [rbx+10h]; this
0x180008b09  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180008b0e  mov     dword ptr [rbx+8], 0
0x180008b15  jmp     short loc_180008B19
0x180008b17  xor     ebx, ebx
0x180008b19  test    rbx, rbx
0x180008b1c  jnz     short loc_180008B25
0x180008b1e  mov     eax, 8007000Eh
0x180008b23  jmp     short loc_180008B50
0x180008b25  mov     rax, [rbx]
0x180008b28  mov     r8, rdi
0x180008b2b  mov     rdx, rsi
0x180008b2e  mov     rcx, rbx
0x180008b31  mov     rax, [rax]
0x180008b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b39  mov     edi, eax
0x180008b3b  test    eax, eax
0x180008b3d  jns     short loc_180008B47
0x180008b3f  mov     rcx, rbx; Block
0x180008b42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008b47  mov     eax, edi
0x180008b49  jmp     short loc_180008B50
0x180008b4b  mov     eax, 80040111h
0x180008b50  mov     rbx, [rsp+28h+arg_0]
0x180008b55  mov     rsi, [rsp+28h+arg_8]
0x180008b5a  add     rsp, 20h
0x180008b5e  pop     rdi
0x180008b5f  retn
```
