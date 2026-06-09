# CADMCOMW::NotifySinkHelper(IMSAdminBaseSinkW *,ulong,_MD_CHANGE_OBJECT_W * const,int)

- ea: `0x1800078ac`
- end: `0x180007a4a`
- name: `?NotifySinkHelper@CADMCOMW@@AEAAJPEAUIMSAdminBaseSinkW@@KQEAU_MD_CHANGE_OBJECT_W@@H@Z`
- size: `414`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, struct IMSAdminBaseSinkW *, unsigned int, struct _MD_CHANGE_OBJECT_W *const, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007c20`

## callees

- `0x1800078ac`
- `0x18000d5e0`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x18000794a`
- `IisRTL!PuDbgPrint` at `0x18000794a`

## string_xrefs

- `0x18000793e`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007937`: `CADMCOMW::NotifySinkHelper`
- `0x18000798c`: `Failled in CreateCall to ICallFactory !!!\n`
- `0x1800079b4`: `SetSinkCallbackSecurityBlanket failled for the async sink !!!\n`

## pseudocode

```c
__int64 __fastcall CADMCOMW::NotifySinkHelper(
        CADMCOMW *this,
        struct IMSAdminBaseSinkW *a2,
        unsigned int a3,
        struct _MD_CHANGE_OBJECT_W *const a4,
        int a5)
{
  int v7; // ebx
  struct IMSAdminBaseSinkWVtbl *lpVtbl; // r9
  struct IUnknownVtbl *v9; // rax
  int v10; // eax
  __int64 (*Release)(void); // rax
  _QWORD v13[3]; // [rsp+30h] [rbp-18h] BYREF
  struct IUnknown *v14; // [rsp+58h] [rbp+10h] BYREF

  v13[0] = 0;
  v14 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  lpVtbl = a2->lpVtbl;
  if ( *((_DWORD *)this + 42) != CADMCOMW::sm_dwProcessIdThis )
  {
    v7 = ((__int64 (__fastcall *)(struct IMSAdminBaseSinkW *, GUID *, _QWORD *))lpVtbl->QueryInterface)(
           a2,
           &IID_ICallFactory,
           v13);
    if ( v7 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          6205,
          "CADMCOMW::NotifySinkHelper",
          "Failled in to get ICallFactory !!!\n");
      goto LABEL_23;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)v13[0] + 24LL))(
           v13[0],
           &IID_AsyncIMSAdminBaseSink_W,
           0,
           &IID_AsyncIMSAdminBaseSink_W,
           &v14);
    if ( v7 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          6216,
          "CADMCOMW::NotifySinkHelper",
          "Failled in CreateCall to ICallFactory !!!\n");
      goto LABEL_23;
    }
    v7 = SetSinkCallbackSecurityBlanket(v14);
    if ( v7 < 0 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\coadmin\\comobj.cxx",
          6225,
          "CADMCOMW::NotifySinkHelper",
          "SetSinkCallbackSecurityBlanket failled for the async sink !!!\n");
      goto LABEL_23;
    }
    v9 = v14->lpVtbl;
    if ( a5 )
    {
      v10 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct _MD_CHANGE_OBJECT_W *const))v9[1].QueryInterface)(
              v14,
              a3,
              a4);
      goto LABEL_22;
    }
    Release = (__int64 (*)(void))v9[1].Release;
    goto LABEL_21;
  }
  if ( !a5 )
  {
    Release = (__int64 (*)(void))lpVtbl->ShutdownNotify;
LABEL_21:
    v10 = Release();
    goto LABEL_22;
  }
  v10 = ((__int64 (__fastcall *)(struct IMSAdminBaseSinkW *, _QWORD, struct _MD_CHANGE_OBJECT_W *const))lpVtbl->SinkNotify)(
          a2,
          a3,
          a4);
LABEL_22:
  v7 = v10;
LABEL_23:
  if ( v14 )
  {
    ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->Release)(v14);
    v14 = 0;
  }
  if ( v13[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800078ac  mov     rax, rsp
0x1800078af  mov     [rax+8], rbx
0x1800078b3  mov     [rax+18h], rsi
0x1800078b7  push    rdi
0x1800078b8  sub     rsp, 40h
0x1800078bc  mov     qword ptr [rax-18h], 0
0x1800078c4  mov     rdi, r9
0x1800078c7  mov     qword ptr [rax+10h], 0
0x1800078cf  mov     esi, r8d
0x1800078d2  mov     r10, rdx
0x1800078d5  test    rdx, rdx
0x1800078d8  jnz     short loc_1800078E4
0x1800078da  mov     ebx, 80070057h
0x1800078df  jmp     loc_180007A38
0x1800078e4  mov     eax, cs:?sm_dwProcessIdThis@CADMCOMW@@2KA; ulong CADMCOMW::sm_dwProcessIdThis
0x1800078ea  cmp     [rcx+0A8h], eax
0x1800078f0  mov     rcx, r10
0x1800078f3  mov     r9, [rdx]
0x1800078f6  jz      loc_1800079EB
0x1800078fc  mov     rax, [r9]
0x1800078ff  lea     r8, [rsp+48h+var_18]
0x180007904  lea     rdx, IID_ICallFactory
0x18000790b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007910  mov     ebx, eax
0x180007912  test    eax, eax
0x180007914  jns     short loc_180007955
0x180007916  test    byte ptr cs:g_dwDebugFlags, 3
0x18000791d  jz      loc_180007A03
0x180007923  lea     rax, aFailledInToGet; "Failled in to get ICallFactory !!!\n"
0x18000792a  mov     r8d, 183Dh
0x180007930  mov     rcx, cs:g_pDebug
0x180007937  lea     r9, aCadmcomwNotify; "CADMCOMW::NotifySinkHelper"
0x18000793e  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007945  mov     [rsp+48h+var_28], rax
0x18000794a  call    cs:__imp_PuDbgPrint
0x180007950  jmp     loc_180007A03
0x180007955  mov     rcx, [rsp+48h+var_18]
0x18000795a  lea     rdx, [rsp+48h+arg_8]
0x18000795f  mov     [rsp+48h+var_28], rdx
0x180007964  xor     r8d, r8d
0x180007967  lea     rdx, IID_AsyncIMSAdminBaseSink_W
0x18000796e  mov     r9, rdx
0x180007971  mov     rax, [rcx]
0x180007974  mov     rax, [rax+18h]
0x180007978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000797d  mov     ebx, eax
0x18000797f  test    eax, eax
0x180007981  jns     short loc_18000799B
0x180007983  test    byte ptr cs:g_dwDebugFlags, 3
0x18000798a  jz      short loc_180007A03
0x18000798c  lea     rax, aFailledInCreat; "Failled in CreateCall to ICallFactory !"...
0x180007993  mov     r8d, 1848h
0x180007999  jmp     short loc_180007930
0x18000799b  mov     rcx, [rsp+48h+arg_8]; struct IUnknown *
0x1800079a0  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x1800079a5  mov     ebx, eax
0x1800079a7  test    eax, eax
0x1800079a9  jns     short loc_1800079C6
0x1800079ab  test    byte ptr cs:g_dwDebugFlags, 3
0x1800079b2  jz      short loc_180007A03
0x1800079b4  lea     rax, aSetsinkcallbac; "SetSinkCallbackSecurityBlanket failled "...
0x1800079bb  mov     r8d, 1851h
0x1800079c1  jmp     loc_180007930
0x1800079c6  cmp     [rsp+48h+arg_20], 0
0x1800079cb  mov     rcx, [rsp+48h+arg_8]
0x1800079d0  mov     rax, [rcx]
0x1800079d3  jz      short loc_1800079E5
0x1800079d5  mov     rax, [rax+18h]
0x1800079d9  mov     edx, esi
0x1800079db  mov     r8, rdi
0x1800079de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079e3  jmp     short loc_180007A01
0x1800079e5  mov     rax, [rax+28h]
0x1800079e9  jmp     short loc_1800079FC
0x1800079eb  cmp     [rsp+48h+arg_20], 0
0x1800079f0  jz      short loc_1800079F8
0x1800079f2  mov     rax, [r9+18h]
0x1800079f6  jmp     short loc_1800079D9
0x1800079f8  mov     rax, [r9+20h]
0x1800079fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a01  mov     ebx, eax
0x180007a03  mov     rcx, [rsp+48h+arg_8]
0x180007a08  test    rcx, rcx
0x180007a0b  jz      short loc_180007A22
0x180007a0d  mov     rax, [rcx]
0x180007a10  mov     rax, [rax+10h]
0x180007a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a19  mov     [rsp+48h+arg_8], 0
0x180007a22  mov     rcx, [rsp+48h+var_18]
0x180007a27  test    rcx, rcx
0x180007a2a  jz      short loc_180007A38
0x180007a2c  mov     rax, [rcx]
0x180007a2f  mov     rax, [rax+10h]
0x180007a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a38  mov     rsi, [rsp+48h+arg_10]
0x180007a3d  mov     eax, ebx
0x180007a3f  mov     rbx, [rsp+48h+arg_0]
0x180007a44  add     rsp, 40h
0x180007a48  pop     rdi
0x180007a49  retn
```
