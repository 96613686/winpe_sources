# DllGetClassObject

- ea: `0x180001a80`
- end: `0x180001b5a`
- name: `DllGetClassObject`
- size: `218`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001008`
- `0x180001a80`
- `0x180005010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180001aca`
- `RPCRT4!NdrDllGetClassObject` at `0x180001aca`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  HRESULT result; // eax
  IID *v8; // rax
  IID *v9; // rbx
  HRESULT v10; // edi

  *ppv = 0;
  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  result = NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  if ( result )
  {
    if ( *(_QWORD *)&rclsid->Data1 != *(_QWORD *)&CLSID_FtpHost.Data1
      || *(_QWORD *)rclsid->Data4 != *(_QWORD *)CLSID_FtpHost.Data4 )
    {
      return -2147221231;
    }
    v8 = (IID *)operator new(0x20u);
    v9 = v8;
    if ( !v8 )
      return -2147024882;
    *(_DWORD *)&v8->Data4[4] = 1;
    *(_QWORD *)&v8->Data1 = &FTPHOST_CLASS_FACTORY::`vftable';
    *(_DWORD *)v8->Data4 = 1179863110;
    v8[1] = *rclsid;
    v10 = ((__int64 (__fastcall *)(IID *, const IID *const, LPVOID *))FTPHOST_CLASS_FACTORY::`vftable')(v8, riid, ppv);
    (*(void (__fastcall **)(IID *))(*(_QWORD *)&v9->Data1 + 16LL))(v9);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180001a80  push    rbx
0x180001a82  push    rbp
0x180001a83  push    rsi
0x180001a84  push    rdi
0x180001a85  sub     rsp, 38h
0x180001a89  mov     qword ptr [r8], 0
0x180001a90  mov     rsi, r8
0x180001a93  mov     rax, cs:aProxyFileList
0x180001a9a  mov     rbp, rdx
0x180001a9d  mov     rdi, rcx
0x180001aa0  mov     r9, [rax+8]
0x180001aa4  mov     rax, [r9]
0x180001aa7  test    rax, rax
0x180001aaa  jz      short loc_180001AAF
0x180001aac  mov     rax, [rax]
0x180001aaf  lea     rcx, gPFactory
0x180001ab6  mov     [rsp+58h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x180001abb  lea     r9, aProxyFileList; pProxyFileList
0x180001ac2  mov     rcx, rdi; rclsid
0x180001ac5  mov     [rsp+58h+pclsid], rax; pclsid
0x180001aca  call    cs:__imp_NdrDllGetClassObject
0x180001ad0  test    eax, eax
0x180001ad2  jz      short loc_180001B51
0x180001ad4  mov     rax, [rdi]
0x180001ad7  cmp     rax, qword ptr cs:CLSID_FtpHost.Data1
0x180001ade  jnz     short loc_180001B4A
0x180001ae0  mov     rax, [rdi+8]
0x180001ae4  cmp     rax, qword ptr cs:CLSID_FtpHost.Data4
0x180001aeb  jnz     short loc_180001B4A
0x180001aed  mov     ecx, 20h ; ' '; Size
0x180001af2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001af7  mov     rbx, rax
0x180001afa  test    rax, rax
0x180001afd  jz      short loc_180001B43
0x180001aff  lea     rax, ??_7FTPHOST_CLASS_FACTORY@@6B@; const FTPHOST_CLASS_FACTORY::`vftable'
0x180001b06  mov     dword ptr [rbx+0Ch], 1
0x180001b0d  mov     [rbx], rax
0x180001b10  mov     r8, rsi
0x180001b13  mov     rax, [rax]
0x180001b16  mov     rdx, rbp
0x180001b19  mov     dword ptr [rbx+8], 46534846h
0x180001b20  mov     rcx, rbx
0x180001b23  movups  xmm0, xmmword ptr [rdi]
0x180001b26  movdqu  xmmword ptr [rbx+10h], xmm0
0x180001b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b30  mov     rcx, [rbx]
0x180001b33  mov     edi, eax
0x180001b35  mov     rax, [rcx+10h]
0x180001b39  mov     rcx, rbx
0x180001b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b41  jmp     short loc_180001B4F
0x180001b43  mov     eax, 8007000Eh
0x180001b48  jmp     short loc_180001B51
0x180001b4a  mov     edi, 80040111h
0x180001b4f  mov     eax, edi
0x180001b51  add     rsp, 38h
0x180001b55  pop     rdi
0x180001b56  pop     rsi
0x180001b57  pop     rbp
0x180001b58  pop     rbx
0x180001b59  retn
```
