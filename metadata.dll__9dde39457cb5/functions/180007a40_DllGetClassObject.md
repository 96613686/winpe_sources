# DllGetClassObject

- ea: `0x180007a40`
- end: `0x180007b27`
- name: `DllGetClassObject`
- size: `231`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x1800089c8`
- `0x180015870`
- `0x180015948`
- `0x180031010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007adf`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007b1a`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007adf`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007b1a`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007aa5`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007aa5`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  __int64 v6; // rax
  struct CMDCOMSrvFactory *v7; // rcx
  CMDCOMSrvFactory *v8; // rax

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v6 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&CLSID_MDCOM.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_MDCOM.Data1 )
    v6 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)CLSID_MDCOM.Data4;
  if ( v6 )
    return -2147221231;
  v7 = g_pFactory;
  if ( g_pFactory )
    return (**(__int64 (__fastcall ***)(struct CMDCOMSrvFactory *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
  result = AssureRunningAsAdministrator();
  if ( result < 0 )
    return result;
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&g_LockMasterResource);
  if ( !g_pFactory )
  {
    v8 = (CMDCOMSrvFactory *)operator new(0x90u);
    if ( v8 )
    {
      g_pFactory = CMDCOMSrvFactory::CMDCOMSrvFactory(v8);
      if ( g_pFactory )
        goto LABEL_12;
    }
    else
    {
      g_pFactory = 0;
    }
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
    return -2147024882;
  }
LABEL_12:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&g_LockMasterResource);
  v7 = g_pFactory;
  return (**(__int64 (__fastcall ***)(struct CMDCOMSrvFactory *, const IID *const, LPVOID *))v7)(v7, riid, ppv);
}

```

## disassembly

```asm
0x180007a40  mov     [rsp+arg_0], rbx
0x180007a45  push    rdi
0x180007a46  sub     rsp, 20h
0x180007a4a  mov     rbx, r8
0x180007a4d  mov     rdi, rdx
0x180007a50  test    r8, r8
0x180007a53  jnz     short loc_180007A5F
0x180007a55  mov     eax, 80070057h
0x180007a5a  jmp     loc_180007AFD
0x180007a5f  mov     qword ptr [r8], 0
0x180007a66  mov     rax, [rcx]
0x180007a69  sub     rax, qword ptr cs:CLSID_MDCOM.Data1
0x180007a70  jnz     short loc_180007A7D
0x180007a72  mov     rax, [rcx+8]
0x180007a76  sub     rax, qword ptr cs:CLSID_MDCOM.Data4
0x180007a7d  test    rax, rax
0x180007a80  jz      short loc_180007A89
0x180007a82  mov     eax, 80040111h
0x180007a87  jmp     short loc_180007AFD
0x180007a89  mov     rcx, cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA; CMDCOMSrvFactory * g_pFactory
0x180007a90  test    rcx, rcx
0x180007a93  jnz     short loc_180007AEC
0x180007a95  call    ?AssureRunningAsAdministrator@@YAJXZ; AssureRunningAsAdministrator(void)
0x180007a9a  test    eax, eax
0x180007a9c  js      short loc_180007AFD
0x180007a9e  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180007aa5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180007aab  cmp     cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA, 0; CMDCOMSrvFactory * g_pFactory
0x180007ab3  jnz     short loc_180007AD8
0x180007ab5  mov     ecx, 90h; Size
0x180007aba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007abf  test    rax, rax
0x180007ac2  jz      short loc_180007B08
0x180007ac4  mov     rcx, rax; this
0x180007ac7  call    ??0CMDCOMSrvFactory@@QEAA@XZ; CMDCOMSrvFactory::CMDCOMSrvFactory(void)
0x180007acc  mov     cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA, rax; CMDCOMSrvFactory * g_pFactory
0x180007ad3  test    rax, rax
0x180007ad6  jz      short loc_180007B13
0x180007ad8  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180007adf  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007ae5  mov     rcx, cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA; CMDCOMSrvFactory * g_pFactory
0x180007aec  mov     rax, [rcx]
0x180007aef  mov     r8, rbx
0x180007af2  mov     rdx, rdi
0x180007af5  mov     rax, [rax]
0x180007af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afd  mov     rbx, [rsp+28h+arg_0]
0x180007b02  add     rsp, 20h
0x180007b06  pop     rdi
0x180007b07  retn
0x180007b08  mov     cs:?g_pFactory@@3PEAVCMDCOMSrvFactory@@EA, 0; CMDCOMSrvFactory * g_pFactory
0x180007b13  lea     rcx, ?g_LockMasterResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockMasterResource
0x180007b1a  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007b20  mov     eax, 8007000Eh
0x180007b25  jmp     short loc_180007AFD
```
