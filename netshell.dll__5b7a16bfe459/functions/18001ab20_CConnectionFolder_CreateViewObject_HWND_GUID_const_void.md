# CConnectionFolder::CreateViewObject(HWND__ *,_GUID const &,void * *)

- ea: `0x18001ab20`
- end: `0x18001ae0e`
- name: `?CreateViewObject@CConnectionFolder@@UEAAJPEAUHWND__@@AEBU_GUID@@PEAPEAX@Z`
- size: `750`
- prototype: `int(CConnectionFolder *__hidden this, HWND, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180005d80`
- `0x180007de0`
- `0x18001644c`
- `0x18001ab20`
- `0x18001ae14`
- `0x18001bc10`
- `0x18001e1e0`
- `0x180065010`

## import_xrefs

- `SHELL32!__imp_SHCreateShellFolderView` at `0x18001abbf`
- `SHELL32!__imp_SHCreateShellFolderView` at `0x18001abbf`
- `ole32!CoCreateInstance` at `0x18001ac90`
- `ole32!CoCreateInstance` at `0x18001ac90`
- `RASDLG!RasUserGetManualDial` at `0x18001abe5`
- `RASDLG!RasUserGetManualDial` at `0x18001abe5`

## pseudocode

```c
__int64 __fastcall CConnectionFolder::CreateViewObject(
        unsigned __int64 this,
        HWND a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  HRESULT Instance; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  void (__fastcall *v12)(unsigned __int64, __int64, __int128 *); // rax
  LPVOID ppv; // [rsp+40h] [rbp-79h] BYREF
  _QWORD v15[4]; // [rsp+48h] [rbp-71h] BYREF
  SFV_CREATE pcsfv; // [rsp+68h] [rbp-51h] BYREF
  __int128 v17; // [rsp+88h] [rbp-31h] BYREF
  int v18; // [rsp+98h] [rbp-21h]
  __int128 v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+B0h] [rbp-9h]
  GUID v21; // [rsp+B8h] [rbp-1h] BYREF
  int v22; // [rsp+C8h] [rbp+Fh]
  GUID v23; // [rsp+CCh] [rbp+13h]
  int v24; // [rsp+DCh] [rbp+23h]

  *a4 = 0;
  v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IShellView.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IShellView.Data1 )
    v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IShellView.Data4;
  if ( v6 )
  {
    v9 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
      v9 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
    if ( v9 )
    {
      Instance = -2147467262;
      v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_ICategoryProvider.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_ICategoryProvider.Data1 )
        v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_ICategoryProvider.Data4;
      if ( !v10 )
      {
        ppv = 0;
        Instance = CoCreateInstance(&CLSID_DefCategoryProvider, 0, 0x17u, &IID_IDefCategoryProvider, &ppv);
        if ( Instance >= 0 )
        {
          v18 = 0;
          v20 = 0;
          v11 = *(_QWORD *)this;
          v17 = 0;
          v12 = *(void (__fastcall **)(unsigned __int64, __int64, __int128 *))(v11 + 152);
          v19 = 0;
          v12(this, 6, &v17);
          (*(void (__fastcall **)(unsigned __int64, __int64, __int128 *))(*(_QWORD *)this + 152LL))(this, 7, &v19);
          v15[0] = &CLSID_AlphabeticalCategorizer;
          v22 = 7;
          v15[1] = &pcsfv;
          v15[2] = &GUID_NULL;
          v24 = 0;
          v21 = GUID_NETSHELL_PROPS;
          LODWORD(pcsfv.psvOuter) = 0;
          v15[3] = 0;
          v23 = GUID_NULL;
          *(GUID *)&pcsfv.cbSize = GUID_NETSHELL_PROPS;
          (*(void (__fastcall **)(LPVOID, GUID *, __int128 *, GUID *, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)ppv + 24LL))(
            ppv,
            &GUID_NETSHELL_PROPS,
            &v17,
            &v21,
            0,
            v15,
            this & ((unsigned __int128)-(__int128)(this - 16) >> 64));
          Instance = (**(__int64 (__fastcall ***)(LPVOID, GUID *, void **))ppv)(ppv, &IID_ICategoryProvider, a4);
        }
        ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&ppv);
      }
    }
    else
    {
      memset(&pcsfv, 0, 24);
      Instance = CConnectionFolderContextMenu::CreateInstance(
                   this != 16 ? this : 0,
                   (_DWORD)a4,
                   2,
                   (_DWORD)a2,
                   (__int64)&pcsfv,
                   this & -(__int64)(this != 16));
      std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>((__int64)&pcsfv);
    }
  }
  else if ( (unsigned int)FHasPermission(0x13u) )
  {
    *(_QWORD *)&pcsfv.cbSize = 32;
    pcsfv.psvOuter = 0;
    if ( this == 16 )
    {
      pcsfv.pshf = 0;
      pcsfv.psfvcb = 0;
    }
    else
    {
      pcsfv.pshf = (IShellFolder *)this;
      pcsfv.psfvcb = (IShellFolderViewCB *)(this + 16);
    }
    Instance = SHCreateShellFolderView(&pcsfv, (IShellView **)(this + 640));
    if ( Instance >= 0 )
    {
      *a4 = *(void **)(this + 640);
      RasUserGetManualDial(a2, 0, &g_fOperatorAssistEnabled);
    }
  }
  else if ( a2 )
  {
    NcMsgBox(hInst, a2, 0x424u, 0x44Fu, 0x30u);
    return (unsigned int)-2147023673;
  }
  else
  {
    return (unsigned int)-2147024891;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001ab20  push    rbp
0x18001ab22  push    rbx
0x18001ab23  push    rsi
0x18001ab24  push    rdi
0x18001ab25  push    r14
0x18001ab27  lea     rbp, [rsp-37h]
0x18001ab2c  sub     rsp, 0F0h
0x18001ab33  mov     rax, cs:__security_cookie
0x18001ab3a  xor     rax, rsp
0x18001ab3d  mov     [rbp+57h+var_30], rax
0x18001ab41  mov     qword ptr [r9], 0
0x18001ab48  mov     r14, r9
0x18001ab4b  mov     rax, [r8]
0x18001ab4e  mov     rsi, rdx
0x18001ab51  sub     rax, qword ptr cs:IID_IShellView.Data1
0x18001ab58  mov     rdi, rcx
0x18001ab5b  jnz     short loc_18001AB68
0x18001ab5d  mov     rax, [r8+8]
0x18001ab61  sub     rax, qword ptr cs:IID_IShellView.Data4
0x18001ab68  test    rax, rax
0x18001ab6b  jnz     loc_18001AC2A
0x18001ab71  lea     ecx, [rax+13h]; unsigned int
0x18001ab74  call    ?FHasPermission@@YAHK@Z; FHasPermission(ulong)
0x18001ab79  test    eax, eax
0x18001ab7b  jz      short loc_18001ABF0
0x18001ab7d  lea     rax, [rdi-10h]
0x18001ab81  mov     qword ptr [rbp+57h+pcsfv.cbSize], 20h ; ' '
0x18001ab89  mov     [rbp+57h+pcsfv.psvOuter], 0
0x18001ab91  test    rax, rax
0x18001ab94  jz      short loc_18001ABA4
0x18001ab96  lea     rax, [rdi+10h]
0x18001ab9a  mov     [rbp+57h+pcsfv.pshf], rdi
0x18001ab9e  mov     [rbp+57h+pcsfv.psfvcb], rax
0x18001aba2  jmp     short loc_18001ABB4
0x18001aba4  mov     [rbp+57h+pcsfv.pshf], 0
0x18001abac  mov     [rbp+57h+pcsfv.psfvcb], 0
0x18001abb4  lea     rdx, [rdi+280h]; ppsv
0x18001abbb  lea     rcx, [rbp+57h+pcsfv]; pcsfv
0x18001abbf  call    cs:__imp_SHCreateShellFolderView
0x18001abc5  mov     ebx, eax
0x18001abc7  test    eax, eax
0x18001abc9  js      loc_18001ADF2
0x18001abcf  mov     rdx, [rdi+280h]
0x18001abd6  lea     r8, ?g_fOperatorAssistEnabled@@3HA; int g_fOperatorAssistEnabled
0x18001abdd  mov     [r14], rdx
0x18001abe0  mov     rcx, rsi
0x18001abe3  xor     edx, edx
0x18001abe5  call    cs:__imp_RasUserGetManualDial
0x18001abeb  jmp     loc_18001ADF2
0x18001abf0  test    rsi, rsi
0x18001abf3  jz      short loc_18001AC20
0x18001abf5  mov     rcx, cs:hInst; hModule
0x18001abfc  mov     r9d, 44Fh; unsigned int
0x18001ac02  mov     rdx, rsi; hWnd
0x18001ac05  mov     dword ptr [rsp+110h+ppv], 30h ; '0'; uType
0x18001ac0d  lea     r8d, [r9-2Bh]; unsigned int
0x18001ac11  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18001ac16  mov     ebx, 800704C7h
0x18001ac1b  jmp     loc_18001ADF2
0x18001ac20  mov     ebx, 80070005h
0x18001ac25  jmp     loc_18001ADF2
0x18001ac2a  mov     rax, [r8]
0x18001ac2d  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x18001ac34  jnz     short loc_18001AC41
0x18001ac36  mov     rax, [r8+8]
0x18001ac3a  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x18001ac41  test    rax, rax
0x18001ac44  jz      loc_18001ADAB
0x18001ac4a  mov     rax, [r8]
0x18001ac4d  mov     ebx, 80004002h
0x18001ac52  sub     rax, qword ptr cs:IID_ICategoryProvider.Data1
0x18001ac59  jnz     short loc_18001AC66
0x18001ac5b  mov     rax, [r8+8]
0x18001ac5f  sub     rax, qword ptr cs:IID_ICategoryProvider.Data4
0x18001ac66  test    rax, rax
0x18001ac69  jnz     loc_18001ADF2
0x18001ac6f  xor     edx, edx; pUnkOuter
0x18001ac71  mov     [rbp+57h+var_D0], rax
0x18001ac75  lea     rax, [rbp+57h+var_D0]
0x18001ac79  lea     r9, IID_IDefCategoryProvider; riid
0x18001ac80  mov     [rsp+110h+ppv], rax; ppv
0x18001ac85  lea     rcx, CLSID_DefCategoryProvider; rclsid
0x18001ac8c  lea     r8d, [rdx+17h]; dwClsContext
0x18001ac90  call    cs:__imp_CoCreateInstance
0x18001ac96  mov     ebx, eax
0x18001ac98  test    eax, eax
0x18001ac9a  js      loc_18001ADA0
0x18001aca0  xor     eax, eax
0x18001aca2  lea     r8, [rbp+57h+var_88]
0x18001aca6  mov     [rbp+57h+var_78], eax
0x18001aca9  xorps   xmm0, xmm0
0x18001acac  mov     [rbp+57h+var_60], eax
0x18001acaf  xorps   xmm1, xmm1
0x18001acb2  mov     rax, [rdi]
0x18001acb5  mov     edx, 6
0x18001acba  mov     rcx, rdi
0x18001acbd  movups  [rbp+57h+var_88], xmm0
0x18001acc1  mov     rax, [rax+98h]
0x18001acc8  movups  [rbp+57h+var_70], xmm1
0x18001accc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acd1  mov     rax, [rdi]
0x18001acd4  lea     r8, [rbp+57h+var_70]
0x18001acd8  mov     ebx, 7
0x18001acdd  mov     rcx, rdi
0x18001ace0  mov     edx, ebx
0x18001ace2  mov     rax, [rax+98h]
0x18001ace9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acee  movups  xmm1, xmmword ptr cs:GUID_NETSHELL_PROPS.Data1
0x18001acf5  mov     rcx, [rbp+57h+var_D0]
0x18001acf9  lea     rax, CLSID_AlphabeticalCategorizer
0x18001ad00  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001ad07  mov     [rbp+57h+var_C8], rax
0x18001ad0b  lea     r9, [rbp+57h+var_58]
0x18001ad0f  lea     rax, [rbp+57h+pcsfv]
0x18001ad13  mov     [rbp+57h+var_48], ebx
0x18001ad16  mov     [rbp+57h+var_C0], rax
0x18001ad1a  lea     rax, GUID_NULL
0x18001ad21  mov     [rbp+57h+var_B8], rax
0x18001ad25  lea     rax, [rdi-10h]
0x18001ad29  neg     rax
0x18001ad2c  mov     [rbp+57h+var_34], 0
0x18001ad33  movdqu  [rbp+57h+var_58], xmm1
0x18001ad38  sbb     rdx, rdx
0x18001ad3b  mov     dword ptr [rbp+57h+pcsfv.psvOuter], 0
0x18001ad42  and     rdx, rdi
0x18001ad45  mov     [rbp+57h+var_B0], 0
0x18001ad4d  mov     [rsp+110h+var_E0], rdx
0x18001ad52  lea     rdx, [rbp+57h+var_C8]
0x18001ad56  mov     [rsp+110h+var_E8], rdx
0x18001ad5b  lea     rdx, GUID_NETSHELL_PROPS
0x18001ad62  movdqu  [rbp+57h+var_44], xmm0
0x18001ad67  mov     [rsp+110h+ppv], 0
0x18001ad70  movdqu  xmmword ptr [rbp+57h+pcsfv.cbSize], xmm1
0x18001ad75  mov     r8, [rcx]
0x18001ad78  mov     rax, [r8+18h]
0x18001ad7c  lea     r8, [rbp+57h+var_88]
0x18001ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad85  mov     rcx, [rbp+57h+var_D0]
0x18001ad89  lea     rdx, IID_ICategoryProvider
0x18001ad90  mov     r8, r14
0x18001ad93  mov     rax, [rcx]
0x18001ad96  mov     rax, [rax]
0x18001ad99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad9e  mov     ebx, eax
0x18001ada0  lea     rcx, [rbp+57h+var_D0]
0x18001ada4  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x18001ada9  jmp     short loc_18001ADF2
0x18001adab  lea     rax, [rcx-10h]
0x18001adaf  mov     [rbp+57h+pcsfv.psvOuter], 0
0x18001adb7  neg     rax
0x18001adba  xorps   xmm0, xmm0
0x18001adbd  lea     rax, [rbp+57h+pcsfv]
0x18001adc1  mov     r9, rsi
0x18001adc4  sbb     rcx, rcx
0x18001adc7  mov     r8d, 2
0x18001adcd  and     rcx, rdi
0x18001add0  mov     rdx, r14
0x18001add3  mov     [rsp+110h+var_E8], rcx
0x18001add8  mov     [rsp+110h+ppv], rax
0x18001addd  movdqu  xmmword ptr [rbp+57h+pcsfv.cbSize], xmm0
0x18001ade2  call    ?CreateInstance@CConnectionFolderContextMenu@@SAJAEBU_GUID@@PEAPEAXW4CMENU_TYPE@@PEAUHWND__@@AEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUIShellFolder@@@Z; CConnectionFolderContextMenu::CreateInstance(_GUID const &,void * *,CMENU_TYPE,HWND__ *,std::vector<CPConFoldPidl<ConFoldPidl_v3>> const &,IShellFolder *)
0x18001ade7  lea     rcx, [rbp+57h+pcsfv]
0x18001adeb  mov     ebx, eax
0x18001aded  call    ??1?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@QEAA@XZ; std::vector<CPConFoldPidl<ConFoldPidl_v3>>::~vector<CPConFoldPidl<ConFoldPidl_v3>>(void)
0x18001adf2  mov     eax, ebx
0x18001adf4  mov     rcx, [rbp+57h+var_30]
0x18001adf8  xor     rcx, rsp; StackCookie
0x18001adfb  call    __security_check_cookie
0x18001ae00  add     rsp, 0F0h
0x18001ae07  pop     r14
0x18001ae09  pop     rdi
0x18001ae0a  pop     rsi
0x18001ae0b  pop     rbx
0x18001ae0c  pop     rbp
0x18001ae0d  retn
```
