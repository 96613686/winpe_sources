# CFontFolderViewCallback::MessageSFVCB(uint,unsigned __int64,__int64)

- ea: `0x18002ac70`
- end: `0x18002af14`
- name: `?MessageSFVCB@CFontFolderViewCallback@@UEAAJI_K_J@Z`
- size: `676`
- prototype: `__int64 __fastcall(CFontFolderViewCallback *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006624`
- `0x180008374`
- `0x18001037c`
- `0x18002a90c`
- `0x18002ac70`
- `0x18002b8ec`
- `0x18002b91c`
- `0x180032010`

## import_xrefs

- `SHELL32!SHGetSpecialFolderLocation` at `0x18002add6`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18002add6`
- `SHELL32!__imp_Create_IEnumUICommandFromDefArray` at `0x18002ae90`
- `SHELL32!__imp_Create_IEnumUICommandFromDefArray` at `0x18002ae90`
- `USER32!SetPropW` at `0x18002ad76`
- `USER32!SetPropW` at `0x18002ad76`
- `USER32!RemovePropW` at `0x18002ad5a`
- `USER32!RemovePropW` at `0x18002ad5a`

## pseudocode

```c
__int64 __fastcall CFontFolderViewCallback::MessageSFVCB(
        CFontFolderViewCallback *this,
        unsigned int a2,
        HWND a3,
        __int64 a4)
{
  unsigned int v7; // ebx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  unsigned int v11; // edx
  unsigned int v12; // edx
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  int v14; // edi
  int v15; // eax
  __int64 v16; // rcx
  HRESULT v18; // ecx
  unsigned int v19; // edx
  unsigned int v20; // edx
  unsigned int v21; // edx
  unsigned int v22; // edx
  unsigned int v23; // edx
  struct CFontCollectionBuilder *Instance; // rax
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  _QWORD v27[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 > 0x31 )
  {
    v19 = a2 - 63;
    if ( v19 )
    {
      v20 = v19 - 10;
      if ( !v20 )
      {
        v26 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)this + 4);
        v27[0] = 0;
        v14 = (**v26)(v26, &IID_IFontFolderPrivate, v27);
        if ( v14 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, HWND))(*(_QWORD *)v27[0] + 40LL))(v27[0], a4, a3);
          goto LABEL_38;
        }
        return (unsigned int)v14;
      }
      v21 = v20 - 11;
      if ( v21 )
      {
        v22 = v21 - 23;
        if ( !v22 )
        {
          Instance = CFontCollectionBuilder::s_GetInstance();
          v7 = 0;
          if ( Instance )
          {
            *((_DWORD *)Instance + 3) = 1;
            RefreshFontFolderView();
          }
          return v7;
        }
        v23 = v22 - 918;
        if ( !v23 )
        {
          CFontFolderViewCallback::_SetTimer(
            this,
            0x7D0u,
            (unsigned int)a3,
            (unsigned int *)this + 15,
            (void (*)(HWND, unsigned int, unsigned __int64, unsigned int))CFontFolderViewCallback::s_DelayedEnable_TimerProc);
          return 0;
        }
        if ( v23 == 1 )
        {
          CFontFolderViewCallback::_KillTimer(this, (unsigned int *)this + 15);
          v7 = 0;
          *((_BYTE *)this + 64) = 0;
          return v7;
        }
        return (unsigned int)-2147467263;
      }
      *(_OWORD *)a4 = 0;
      *(_QWORD *)(a4 + 16) = 0;
      return (unsigned int)Create_IEnumUICommandFromDefArray(this, &off_1800347D0, 4);
    }
    else
    {
      return (unsigned int)StringCchCopyW(
                             (unsigned __int16 *)(a4 + 520),
                             0x104u,
                             L"mshelp://windows/?id=f144ad40-bc63-43f1-a06e-4cc6b22bde30");
    }
  }
  if ( a2 == 49 )
  {
    *(_QWORD *)a3 = 0;
    v18 = 0;
    if ( *((_QWORD *)this + 9) || (v18 = SHGetSpecialFolderLocation(0, 20, (LPITEMIDLIST *)this + 9), v18 >= 0) )
    {
      *(_QWORD *)a3 = *((_QWORD *)this + 9);
      *(_DWORD *)a4 = 145439;
    }
    return (unsigned int)v18;
  }
  v7 = 0;
  v8 = a2 - 14;
  if ( !v8 )
  {
    if ( (a4 & 0x1001) != 0 && *((_BYTE *)this + 64) )
      CFontFolderViewCallback::_SetTimer(
        this,
        0x3E8u,
        (unsigned int)a3,
        (unsigned int *)this + 14,
        (void (*)(HWND, unsigned int, unsigned __int64, unsigned int))CFontFolderViewCallback::s_BkgndInstall_TimerProc);
    return v7;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    *((_QWORD *)this + 6) = a3;
    if ( !SetPropW(a3, L"FontFolderViewCBPtr", this) )
      ResultFromLastError();
    return v7;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    CFontFolderViewCallback::_KillTimer(this, (unsigned int *)this + 14);
    CFontFolderViewCallback::_KillTimer(this, (unsigned int *)this + 15);
    RemovePropW(*((HWND *)this + 6), L"FontFolderViewCBPtr");
    return v7;
  }
  v11 = v10 - 8;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      if ( v12 == 11 )
      {
        v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)this + 4);
        v27[0] = 0;
        v14 = (**v13)(v13, &IID_IFontFolderPrivate, v27);
        if ( v14 >= 0 )
        {
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)v27[0] + 48LL))(
                  v27[0],
                  a4,
                  (unsigned int)a3);
LABEL_38:
          v14 = v15;
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 16LL))(v27[0]);
          return (unsigned int)v14;
        }
        return (unsigned int)v14;
      }
    }
    else
    {
      *(_QWORD *)a4 = 0;
      *(_DWORD *)(a4 + 8) = 1;
    }
    return (unsigned int)-2147467263;
  }
  v16 = *((_QWORD *)this + 5);
  if ( v16 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 24LL))(v16, (int)a3);
  return v7;
}

```

## disassembly

```asm
0x18002ac70  push    rbx
0x18002ac72  push    rsi
0x18002ac73  push    rdi
0x18002ac74  push    r14
0x18002ac76  sub     rsp, 48h
0x18002ac7a  mov     rsi, r9
0x18002ac7d  mov     r14, r8
0x18002ac80  mov     rdi, rcx
0x18002ac83  cmp     edx, 31h ; '1'
0x18002ac86  ja      loc_18002ADF6
0x18002ac8c  jz      loc_18002ADC2
0x18002ac92  xor     ebx, ebx
0x18002ac94  sub     edx, 0Eh
0x18002ac97  jz      loc_18002AD8E
0x18002ac9d  sub     edx, 1
0x18002aca0  jz      loc_18002AD65
0x18002aca6  sub     edx, 1
0x18002aca9  jz      loc_18002AD3A
0x18002acaf  sub     edx, 8
0x18002acb2  jz      short loc_18002AD19
0x18002acb4  sub     edx, 1
0x18002acb7  jz      short loc_18002AD04
0x18002acb9  cmp     edx, 0Bh
0x18002acbc  jnz     short loc_18002AD0F
0x18002acbe  mov     rcx, [rcx+20h]
0x18002acc2  lea     r8, [rsp+68h+var_38]
0x18002acc7  mov     [rsp+68h+var_38], rbx
0x18002accc  lea     rdx, IID_IFontFolderPrivate
0x18002acd3  mov     rax, [rcx]
0x18002acd6  mov     rax, [rax]
0x18002acd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acde  mov     edi, eax
0x18002ace0  test    eax, eax
0x18002ace2  js      loc_18002AEEA
0x18002ace8  mov     rcx, [rsp+68h+var_38]
0x18002aced  mov     r8d, r14d
0x18002acf0  mov     rdx, rsi
0x18002acf3  mov     rax, [rcx]
0x18002acf6  mov     rax, [rax+30h]
0x18002acfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acff  jmp     loc_18002AED7
0x18002ad04  mov     [r9], rbx
0x18002ad07  mov     dword ptr [r9+8], 1
0x18002ad0f  mov     ebx, 80004001h
0x18002ad14  jmp     loc_18002AF08
0x18002ad19  mov     rcx, [rcx+28h]
0x18002ad1d  test    rcx, rcx
0x18002ad20  jz      loc_18002AF08
0x18002ad26  mov     rax, [rcx]
0x18002ad29  movsxd  rdx, r14d
0x18002ad2c  mov     rax, [rax+18h]
0x18002ad30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad35  jmp     loc_18002AF0A
0x18002ad3a  lea     rdx, [rcx+38h]; unsigned int *
0x18002ad3e  call    ?_KillTimer@CFontFolderViewCallback@@AEAAJPEAI@Z; CFontFolderViewCallback::_KillTimer(uint *)
0x18002ad43  lea     rdx, [rdi+3Ch]; unsigned int *
0x18002ad47  mov     rcx, rdi; this
0x18002ad4a  call    ?_KillTimer@CFontFolderViewCallback@@AEAAJPEAI@Z; CFontFolderViewCallback::_KillTimer(uint *)
0x18002ad4f  mov     rcx, [rdi+30h]; hWnd
0x18002ad53  lea     rdx, c_szProp_ViewCallbackObjPtr; "FontFolderViewCBPtr"
0x18002ad5a  call    cs:__imp_RemovePropW
0x18002ad60  jmp     loc_18002AF08
0x18002ad65  mov     [rcx+30h], r14
0x18002ad69  lea     rdx, c_szProp_ViewCallbackObjPtr; "FontFolderViewCBPtr"
0x18002ad70  mov     rcx, r14; hWnd
0x18002ad73  mov     r8, rdi; hData
0x18002ad76  call    cs:__imp_SetPropW
0x18002ad7c  test    eax, eax
0x18002ad7e  jnz     loc_18002AF08
0x18002ad84  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002ad89  jmp     loc_18002AF08
0x18002ad8e  test    esi, 1001h
0x18002ad94  jz      loc_18002AF08
0x18002ad9a  cmp     [rcx+40h], bl
0x18002ad9d  jz      loc_18002AF08
0x18002ada3  lea     rax, ?s_BkgndInstall_TimerProc@CFontFolderViewCallback@@CAXPEAUHWND__@@I_KK@Z; CFontFolderViewCallback::s_BkgndInstall_TimerProc(HWND__ *,uint,unsigned __int64,ulong)
0x18002adaa  mov     edx, 3E8h; unsigned __int64
0x18002adaf  lea     r9, [rcx+38h]; unsigned int *
0x18002adb3  mov     [rsp+68h+var_48], rax; void (*)(HWND, unsigned int, unsigned __int64, unsigned int)
0x18002adb8  call    ?_SetTimer@CFontFolderViewCallback@@AEAAJ_KIPEAIP6AXPEAUHWND__@@I0K@Z@Z; CFontFolderViewCallback::_SetTimer(unsigned __int64,uint,uint *,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x18002adbd  jmp     loc_18002AF08
0x18002adc2  xor     ebx, ebx
0x18002adc4  mov     [r8], rbx
0x18002adc7  mov     ecx, ebx; hwnd
0x18002adc9  cmp     [rdi+48h], rbx
0x18002adcd  jnz     short loc_18002ADE2
0x18002adcf  lea     r8, [rdi+48h]; ppidl
0x18002add3  lea     edx, [rbx+14h]; csidl
0x18002add6  call    cs:__imp_SHGetSpecialFolderLocation
0x18002addc  mov     ecx, eax; this
0x18002adde  test    eax, eax
0x18002ade0  js      short loc_18002ADEF
0x18002ade2  mov     rax, [rdi+48h]
0x18002ade6  mov     [r14], rax
0x18002ade9  mov     dword ptr [rsi], 2381Fh
0x18002adef  mov     ebx, ecx
0x18002adf1  jmp     loc_18002AF08
0x18002adf6  sub     edx, 3Fh ; '?'
0x18002adf9  jz      loc_18002AEEE
0x18002adff  sub     edx, 0Ah
0x18002ae02  jz      loc_18002AE98
0x18002ae08  sub     edx, 0Bh
0x18002ae0b  jz      short loc_18002AE78
0x18002ae0d  sub     edx, 17h
0x18002ae10  jz      short loc_18002AE57
0x18002ae12  sub     edx, 396h
0x18002ae18  jz      short loc_18002AE36
0x18002ae1a  cmp     edx, 1
0x18002ae1d  jnz     loc_18002AD0F
0x18002ae23  lea     rdx, [rcx+3Ch]; unsigned int *
0x18002ae27  call    ?_KillTimer@CFontFolderViewCallback@@AEAAJPEAI@Z; CFontFolderViewCallback::_KillTimer(uint *)
0x18002ae2c  xor     ebx, ebx
0x18002ae2e  mov     [rdi+40h], bl
0x18002ae31  jmp     loc_18002AF08
0x18002ae36  lea     rax, ?s_DelayedEnable_TimerProc@CFontFolderViewCallback@@CAXPEAUHWND__@@I_KK@Z; CFontFolderViewCallback::s_DelayedEnable_TimerProc(HWND__ *,uint,unsigned __int64,ulong)
0x18002ae3d  mov     edx, 7D0h; unsigned __int64
0x18002ae42  lea     r9, [rcx+3Ch]; unsigned int *
0x18002ae46  mov     [rsp+68h+var_48], rax; void (*)(HWND, unsigned int, unsigned __int64, unsigned int)
0x18002ae4b  call    ?_SetTimer@CFontFolderViewCallback@@AEAAJ_KIPEAIP6AXPEAUHWND__@@I0K@Z@Z; CFontFolderViewCallback::_SetTimer(unsigned __int64,uint,uint *,void (*)(HWND__ *,uint,unsigned __int64,ulong))
0x18002ae50  xor     ebx, ebx
0x18002ae52  jmp     loc_18002AF08
0x18002ae57  call    ?s_GetInstance@CFontCollectionBuilder@@SAPEAV1@XZ; CFontCollectionBuilder::s_GetInstance(void)
0x18002ae5c  xor     ebx, ebx
0x18002ae5e  test    rax, rax
0x18002ae61  jz      loc_18002AF08
0x18002ae67  mov     dword ptr [rax+0Ch], 1
0x18002ae6e  call    ?RefreshFontFolderView@@YAXXZ; RefreshFontFolderView(void)
0x18002ae73  jmp     loc_18002AF08
0x18002ae78  xor     eax, eax
0x18002ae7a  lea     rdx, off_1800347D0
0x18002ae81  xorps   xmm0, xmm0
0x18002ae84  movups  xmmword ptr [r9], xmm0
0x18002ae88  mov     [r9+10h], rax
0x18002ae8c  lea     r8d, [rax+4]
0x18002ae90  call    cs:__imp_Create_IEnumUICommandFromDefArray
0x18002ae96  jmp     short loc_18002AF06
0x18002ae98  mov     rcx, [rcx+20h]
0x18002ae9c  lea     r8, [rsp+68h+var_38]
0x18002aea1  xor     ebx, ebx
0x18002aea3  lea     rdx, IID_IFontFolderPrivate
0x18002aeaa  mov     [rsp+68h+var_38], rbx
0x18002aeaf  mov     rax, [rcx]
0x18002aeb2  mov     rax, [rax]
0x18002aeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeba  mov     edi, eax
0x18002aebc  test    eax, eax
0x18002aebe  js      short loc_18002AEEA
0x18002aec0  mov     rcx, [rsp+68h+var_38]
0x18002aec5  mov     r8, r14
0x18002aec8  mov     rdx, rsi
0x18002aecb  mov     rax, [rcx]
0x18002aece  mov     rax, [rax+28h]
0x18002aed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aed7  mov     rcx, [rsp+68h+var_38]
0x18002aedc  mov     edi, eax
0x18002aede  mov     rax, [rcx]
0x18002aee1  mov     rax, [rax+10h]
0x18002aee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aeea  mov     ebx, edi
0x18002aeec  jmp     short loc_18002AF08
0x18002aeee  lea     rcx, [r9+208h]; unsigned __int16 *
0x18002aef5  mov     edx, 104h; unsigned __int64
0x18002aefa  lea     r8, aMshelpWindowsI; "mshelp://windows/?id=f144ad40-bc63-43f1"...
0x18002af01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002af06  mov     ebx, eax
0x18002af08  mov     eax, ebx
0x18002af0a  add     rsp, 48h
0x18002af0e  pop     r14
0x18002af10  pop     rdi
0x18002af11  pop     rsi
0x18002af12  pop     rbx
0x18002af13  retn
```
