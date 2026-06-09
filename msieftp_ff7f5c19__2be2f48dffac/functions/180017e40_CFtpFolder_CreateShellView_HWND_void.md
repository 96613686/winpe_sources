# CFtpFolder::_CreateShellView(HWND__ *,void * *)

- ea: `0x180017e40`
- end: `0x180018032`
- name: `?_CreateShellView@CFtpFolder@@UEAAJPEAUHWND__@@PEAPEAX@Z`
- size: `498`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, HWND, IShellView **ppsv)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180017e40`
- `0x180023340`
- `0x180023adc`
- `0x180024ac8`
- `0x1800250a4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x180017fef`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x180017fef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eda`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eda`

## pseudocode

```c
__int64 __fastcall CFtpFolder::_CreateShellView(CFtpFolder *this, struct CFtpDir *a2, IShellView **ppsv)
{
  HRESULT v6; // edi
  struct CFtpDir **v7; // rax
  struct CFtpDir **v8; // rbx
  HWND StatusBar; // rax
  HWND v10; // rdi
  _QWORD *v11; // rax
  IShellFolderViewCB *v12; // rbx
  __int64 (__fastcall **v13)(CFtpFolder *, GUID *, IShellFolder **); // rax
  IShellFolderViewCB *v15; // [rsp+20h] [rbp-30h] BYREF
  SFV_CREATE pcsfv; // [rsp+28h] [rbp-28h] BYREF
  IShellFolder *v17; // [rsp+98h] [rbp+48h] BYREF

  v15 = 0;
  v6 = -2147024882;
  v7 = (struct CFtpDir **)operator new(0x88u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *v7 = (struct CFtpDir *)&CBaseFolderViewCB::`vftable'{for `IShellFolderViewCB'};
    v7[1] = (struct CFtpDir *)&CBaseFolderViewCB::`vftable'{for `CObjectWithSite'};
    *((_DWORD *)v7 + 6) = 1;
    *((_DWORD *)v7 + 10) = 1129727554;
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    v7[4] = 0;
    *v7 = (struct CFtpDir *)&CFtpView::`vftable'{for `IShellFolderViewCB'};
    v7[1] = (struct CFtpDir *)&CFtpView::`vftable'{for `CObjectWithSite'};
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
    v7[9] = 0;
    v7[15] = 0;
    *((_DWORD *)v7 + 32) = GetCurrentThreadId();
    if ( a2 )
    {
      v8[6] = a2;
      StatusBar = Misc_FindStatusBar((HWND)a2);
      v8[7] = (struct CFtpDir *)StatusBar;
      v10 = StatusBar;
      v11 = operator new(0x98u);
      if ( v11 )
      {
        _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
        v11[2] = 0;
        v11[3] = 0;
        v11[17] = 0;
        v11[18] = 0;
        v11[1] = v10;
        *((_DWORD *)v11 + 32) = -1;
      }
      else
      {
        v11 = 0;
      }
      v8[10] = (struct CFtpDir *)v11;
      if ( v11 )
        CStatusBar::SetStatusMessage((CStatusBar *)v11, 0x40u, 0);
    }
    v8[12] = (struct CFtpDir *)-1LL;
    v8[13] = (struct CFtpDir *)-1LL;
    IUnknown_Set(v8 + 8, this);
    _InterlockedIncrement((volatile signed __int32 *)&g_cRef_CFtpView);
    v6 = (*(__int64 (__fastcall **)(struct CFtpDir **, GUID *, IShellFolderViewCB **))*v8)(
           v8,
           &IID_IShellFolderViewCB,
           &v15);
    (*((void (__fastcall **)(struct CFtpDir **))*v8 + 2))(v8);
    if ( v6 >= 0 )
    {
      v12 = v15;
      *ppsv = 0;
      v13 = *(__int64 (__fastcall ***)(CFtpFolder *, GUID *, IShellFolder **))this;
      v17 = 0;
      v6 = (*v13)(this, &GUID_000214e6_0000_0000_c000_000000000046, &v17);
      if ( v6 >= 0 )
      {
        pcsfv.pshf = v17;
        *(_QWORD *)&pcsfv.cbSize = 32;
        pcsfv.psvOuter = 0;
        pcsfv.psfvcb = v12;
        v6 = SHCreateShellFolderView(&pcsfv, ppsv);
        ((void (__fastcall *)(IShellFolder *))v17->lpVtbl->Release)(v17);
      }
      ((void (__fastcall *)(IShellFolderViewCB *))v15->lpVtbl[2].MessageSFVCB)(v15);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180017e40  mov     [rsp-28h+arg_0], rbx
0x180017e45  mov     [rsp-28h+arg_8], rsi
0x180017e4a  push    rbp
0x180017e4b  push    rdi
0x180017e4c  push    r12
0x180017e4e  push    r14
0x180017e50  push    r15
0x180017e52  mov     rbp, rsp
0x180017e55  sub     rsp, 50h
0x180017e59  mov     r14, rcx
0x180017e5c  xor     r12d, r12d
0x180017e5f  mov     ecx, 88h; unsigned __int64
0x180017e64  mov     [rbp+var_30], r12
0x180017e68  mov     r15, r8
0x180017e6b  mov     rsi, rdx
0x180017e6e  mov     edi, 8007000Eh
0x180017e73  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017e78  mov     rbx, rax
0x180017e7b  test    rax, rax
0x180017e7e  jz      loc_180018017
0x180017e84  mov     [rax+10h], r12
0x180017e88  lea     rax, ??_7CBaseFolderViewCB@@6BIShellFolderViewCB@@@; const CBaseFolderViewCB::`vftable'{for `IShellFolderViewCB'}
0x180017e8f  mov     [rbx], rax
0x180017e92  lea     rax, ??_7CBaseFolderViewCB@@6BCObjectWithSite@@@; const CBaseFolderViewCB::`vftable'{for `CObjectWithSite'}
0x180017e99  mov     [rbx+8], rax
0x180017e9d  mov     dword ptr [rbx+18h], 1
0x180017ea4  mov     dword ptr [rbx+28h], 43564642h
0x180017eab  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180017eb2  lea     rax, ??_7CFtpView@@6BIShellFolderViewCB@@@; const CFtpView::`vftable'{for `IShellFolderViewCB'}
0x180017eb9  mov     [rbx+20h], r12
0x180017ebd  mov     [rbx], rax
0x180017ec0  lea     rax, ??_7CFtpView@@6BCObjectWithSite@@@; const CFtpView::`vftable'{for `CObjectWithSite'}
0x180017ec7  mov     [rbx+8], rax
0x180017ecb  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180017ed2  mov     [rbx+48h], r12
0x180017ed6  mov     [rbx+78h], r12
0x180017eda  call    cs:__imp_GetCurrentThreadId
0x180017ee0  mov     [rbx+80h], eax
0x180017ee6  test    rsi, rsi
0x180017ee9  jz      short loc_180017F55
0x180017eeb  mov     rcx, rsi; HWND
0x180017eee  mov     [rbx+30h], rsi
0x180017ef2  call    ?Misc_FindStatusBar@@YAPEAUHWND__@@PEAU1@@Z; Misc_FindStatusBar(HWND__ *)
0x180017ef7  mov     ecx, 98h; unsigned __int64
0x180017efc  mov     [rbx+38h], rax
0x180017f00  mov     rdi, rax
0x180017f03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017f08  test    rax, rax
0x180017f0b  jz      short loc_180017F3A
0x180017f0d  lock inc cs:?g_cRef@@3KA; ulong g_cRef
0x180017f14  mov     [rax+10h], r12
0x180017f18  mov     [rax+18h], r12
0x180017f1c  mov     [rax+88h], r12
0x180017f23  mov     [rax+90h], r12
0x180017f2a  mov     [rax+8], rdi
0x180017f2e  mov     dword ptr [rax+80h], 0FFFFFFFFh
0x180017f38  jmp     short loc_180017F3D
0x180017f3a  mov     rax, r12
0x180017f3d  mov     [rbx+50h], rax
0x180017f41  test    rax, rax
0x180017f44  jz      short loc_180017F55
0x180017f46  xor     r8d, r8d; unsigned __int16 *
0x180017f49  mov     rcx, rax; this
0x180017f4c  lea     edx, [r8+40h]; unsigned int
0x180017f50  call    ?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z; CStatusBar::SetStatusMessage(uint,ushort const *)
0x180017f55  lea     rcx, [rbx+40h]; struct CFtpDir **
0x180017f59  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x180017f61  mov     rdx, r14; struct CFtpDir *
0x180017f64  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x180017f6c  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x180017f71  lock inc cs:?g_cRef_CFtpView@@3KA; ulong g_cRef_CFtpView
0x180017f78  mov     rax, [rbx]
0x180017f7b  lea     r8, [rbp+var_30]
0x180017f7f  lea     rdx, IID_IShellFolderViewCB
0x180017f86  mov     rcx, rbx
0x180017f89  mov     rax, [rax]
0x180017f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f91  mov     edi, eax
0x180017f93  mov     rcx, rbx
0x180017f96  mov     rax, [rbx]
0x180017f99  mov     rax, [rax+10h]
0x180017f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fa2  test    edi, edi
0x180017fa4  js      short loc_180018017
0x180017fa6  mov     rbx, [rbp+var_30]
0x180017faa  lea     r8, [rbp+arg_18]
0x180017fae  mov     [r15], r12
0x180017fb1  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x180017fb8  mov     rax, [r14]
0x180017fbb  mov     rcx, r14
0x180017fbe  mov     [rbp+arg_18], r12
0x180017fc2  mov     rax, [rax]
0x180017fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fca  mov     edi, eax
0x180017fcc  test    eax, eax
0x180017fce  js      short loc_180018007
0x180017fd0  mov     rax, [rbp+arg_18]
0x180017fd4  lea     rcx, [rbp+pcsfv]; pcsfv
0x180017fd8  mov     rdx, r15; ppsv
0x180017fdb  mov     [rbp+pcsfv.pshf], rax
0x180017fdf  mov     qword ptr [rbp+pcsfv.cbSize], 20h ; ' '
0x180017fe7  mov     [rbp+pcsfv.psvOuter], r12
0x180017feb  mov     [rbp+pcsfv.psfvcb], rbx
0x180017fef  call    cs:__imp_SHCreateShellFolderView
0x180017ff5  mov     rcx, [rbp+arg_18]
0x180017ff9  mov     edi, eax
0x180017ffb  mov     rax, [rcx]
0x180017ffe  mov     rax, [rax+10h]
0x180018002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018007  mov     rcx, [rbp+var_30]
0x18001800b  mov     rax, [rcx]
0x18001800e  mov     rax, [rax+10h]
0x180018012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018017  lea     r11, [rsp+50h+var_s0]
0x18001801c  mov     eax, edi
0x18001801e  mov     rbx, [r11+30h]
0x180018022  mov     rsi, [r11+38h]
0x180018026  mov     rsp, r11
0x180018029  pop     r15
0x18001802b  pop     r14
0x18001802d  pop     r12
0x18001802f  pop     rdi
0x180018030  pop     rbp
0x180018031  retn
```
