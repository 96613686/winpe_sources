# CLanConnectionUi::AddPages(HWND__ *,int (*)(_PSP *,__int64),__int64)

- ea: `0x18002a9e0`
- end: `0x18002aeef`
- name: `?AddPages@CLanConnectionUi@@UEAAJPEAUHWND__@@P6AHPEAU_PSP@@_J@Z2@Z`
- size: `1295`
- prototype: `__int64 __fastcall(unsigned __int64 this, HWND, void (__fastcall *)(struct _PSP *, __int64), __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002010`
- `0x1800157f0`
- `0x18001644c`
- `0x180018d74`
- `0x18001e1e0`
- `0x18002a9e0`
- `0x18002ba00`
- `0x18002c594`
- `0x180034cc8`
- `0x18003fa48`
- `0x18003fc54`
- `0x180065010`

## import_xrefs

- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18002ae8b`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x18002ae8b`
- `USER32!GetKeyState` at `0x18002aab1`
- `USER32!GetKeyState` at `0x18002aab1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002acb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002acb2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ac99`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ac99`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002acc8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002acc8`
- `ole32!CoCreateInstance` at `0x18002ad96`
- `ole32!CoCreateInstance` at `0x18002ad96`

## string_xrefs

- `0x18002ac8c`: `dot3ui.dll`
- `0x18002aca8`: `Dot3CreatePsPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLanConnectionUi::AddPages(
        unsigned __int64 this,
        HWND a2,
        void (__fastcall *a3)(struct _PSP *, __int64),
        __int64 a4)
{
  unsigned int v7; // edx
  unsigned __int8 v8; // cl
  HRESULT Instance; // esi
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v12; // r8d
  const unsigned __int16 *v13; // r9
  CPropSheetPage *v14; // rdi
  const unsigned __int16 *v15; // rcx
  unsigned int v16; // edx
  struct _PSP *Page; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v20; // rax
  unsigned int v21; // r8d
  const unsigned __int16 *v22; // r9
  unsigned int v23; // r8d
  const unsigned __int16 *v24; // r9
  CPropSheetPage **v25; // rdi
  struct _PSP *v26; // rax
  CPropSheetPage *v27; // rdi
  CPropSheetPage *v28; // rax
  struct _PSP *v29; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-60h]
  LPVOID *ppva; // [rsp+20h] [rbp-60h]
  struct IHNetConnection *v32; // [rsp+28h] [rbp-58h]
  HINSTANCE v33; // [rsp+30h] [rbp-50h]
  struct IUnknown *v34; // [rsp+40h] [rbp-40h] BYREF
  struct tagNETCON_PROPERTIES_EX *pv; // [rsp+48h] [rbp-38h] BYREF
  struct IUnknown *v36; // [rsp+50h] [rbp-30h] BYREF
  struct IUnknown *v37; // [rsp+58h] [rbp-28h] BYREF
  __int64 v38; // [rsp+60h] [rbp-20h] BYREF
  __int128 v39; // [rsp+68h] [rbp-18h] BYREF

  v39 = 0;
  if ( !FCheckGroupMembershipInternal(this, (unsigned int)a2, 0x22Cu, 0)
    && !FCheckGroupMembershipInternal(v8, v7, 0x220u, 0) )
  {
    return 2147943140LL;
  }
  if ( a3 )
  {
    v11 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(this + 80);
    if ( !v11 )
      return (unsigned int)-2147418113;
    v38 = 0;
    pv = 0;
    Instance = (**v11)(v11, &IID_INetConnection2, &v38);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(__int64, struct tagNETCON_PROPERTIES_EX **))(*(_QWORD *)v38 + 24LL))(
                       v38,
                       &pv),
          Instance < 0) )
    {
LABEL_64:
      ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v38);
      return (unsigned int)Instance;
    }
    if ( GetKeyState(16) >= 0 )
    {
      if ( *((_DWORD *)pv + 11) == 7 )
      {
        v14 = *(CPropSheetPage **)(this + 88);
        if ( v14
          || ((v14 = (CPropSheetPage *)MemAlloc(0xC0u)) == 0
            ? (v14 = 0)
            : (CPropSheetPage *)(CLanNetPage::CLanNetPage(
                                   v14,
                                   (struct IUnknown *)(this & -(__int64)(this != 8)),
                                   *(struct INetCfg **)(this + 120),
                                   *(struct INetConnection **)(this + 80),
                                   *(_BYTE *)(this + 176),
                                   *(_BYTE *)(this + 177),
                                   *(_BYTE *)(this + 178)),
                                 *((_QWORD *)v14 + 22) = 0,
                                 *(_QWORD *)v14 = &CLanNetNetworkBridgePage::`vftable',
                                 *((_QWORD *)v14 + 23) = 0),
              (*(_QWORD *)(this + 88) = v14) != 0) )
        {
          v16 = 16059;
LABEL_31:
          Page = CPropSheetPage::CreatePage(
                   v14,
                   v16,
                   v12,
                   v13,
                   (const unsigned __int16 *)ppv,
                   (const unsigned __int16 *)v32,
                   v33);
          a3(Page, a4);
          goto LABEL_32;
        }
        goto LABEL_32;
      }
      if ( (*((_DWORD *)pv + 13) & 0x200) != 0 )
      {
        v14 = *(CPropSheetPage **)(this + 88);
        if ( v14
          || ((v14 = (CPropSheetPage *)MemAlloc(0xA8u)) == 0
            ? (v14 = 0)
            : (CPropSheetPage *)(CLanNetPage::CLanNetPage(
                                   v14,
                                   (struct IUnknown *)(this & -(__int64)(this != 8)),
                                   *(struct INetCfg **)(this + 120),
                                   *(struct INetConnection **)(this + 80),
                                   *(_BYTE *)(this + 176),
                                   *(_BYTE *)(this + 177),
                                   *(_BYTE *)(this + 178)),
                                 *(_QWORD *)v14 = &CLanNetBridgedPage::`vftable'),
              (*(_QWORD *)(this + 88) = v14) != 0) )
        {
          v16 = 16058;
          goto LABEL_31;
        }
LABEL_32:
        if ( *((_DWORD *)pv + 11) == 3 && *((_DWORD *)pv + 12) == 1 )
        {
          if ( *(_QWORD *)(this + 112) )
            goto LABEL_39;
          Library = LoadLibraryExW(L"dot3ui.dll", 0, 0x800u);
          *(_QWORD *)(this + 112) = Library;
          if ( Library )
          {
            ProcAddress = GetProcAddress(Library, "Dot3CreatePsPage");
            *(_QWORD *)(this + 184) = ProcAddress;
            if ( !ProcAddress )
            {
              FreeLibrary(*(HMODULE *)(this + 112));
              *(_QWORD *)(this + 112) = 0;
              *(_QWORD *)(this + 184) = 0;
            }
          }
          if ( *(_QWORD *)(this + 112) )
          {
LABEL_39:
            Instance = (*(__int64 (__fastcall **)(unsigned __int64, __int128 *))(*(_QWORD *)(this + 16) + 24LL))(
                         this + 16,
                         &v39);
            if ( Instance >= 0 )
            {
              v32 = 0;
              v20 = (*(__int64 (__fastcall **)(__int128 *, _QWORD, _QWORD, _QWORD, _QWORD))(this + 184))(
                      &v39,
                      0,
                      0,
                      0,
                      0);
              if ( v20 )
                a3((struct _PSP *)v20, a4);
            }
          }
        }
        if ( (*((_DWORD *)pv + 13) & 0x1000) != 0 && (unsigned int)(*((_DWORD *)pv + 12) - 7) > 1 )
        {
          LODWORD(v34) = 0;
          if ( (int)HrSvcQueryStatus(v15, (unsigned int *)&v34) >= 0 && (_DWORD)v34 == 4 )
          {
            v34 = 0;
            v37 = 0;
            v36 = 0;
            Instance = CoCreateInstance(&CLSID_HNetCfgMgr, 0, 0x17u, &IID_IHNetCfgMgr, (LPVOID *)&v34);
            if ( Instance < 0 )
              goto LABEL_56;
            Instance = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v34->lpVtbl->QueryInterface)(
                         v34,
                         &GUID_85d18b6f_3032_11d4_9348_00c04f8eeb71,
                         &v37);
            if ( Instance >= 0 )
            {
              Instance = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, struct IUnknown **))v34->lpVtbl[1].QueryInterface)(
                           v34,
                           *(_QWORD *)(this + 80),
                           &v36);
              if ( Instance >= 0 )
              {
                v25 = (CPropSheetPage **)(this + 96);
                if ( !*(_QWORD *)(this + 96) )
                  Instance = HrQueryLanAdvancedPage(
                               *(struct INetConnection **)(this + 80),
                               (struct IUnknown *)(this & -(__int64)(this != 8)),
                               (struct CPropSheetPage **)(this + 96),
                               (struct IHNetCfgMgr *)v34,
                               (struct IHNetIcsSettings *)v37,
                               (struct IHNetConnection *)v36);
                if ( *v25 )
                {
                  v26 = CPropSheetPage::CreatePage(
                          *v25,
                          0x29FFu,
                          v23,
                          v24,
                          (const unsigned __int16 *)ppva,
                          (const unsigned __int16 *)v32,
                          v33);
                  a3(v26, a4);
                }
                ReleaseObj(v36);
              }
              ReleaseObj(v37);
            }
            ReleaseObj(v34);
            if ( Instance < 0 )
            {
LABEL_56:
              v27 = *(CPropSheetPage **)(this + 104);
              if ( v27 )
                goto LABEL_61;
              v28 = (CPropSheetPage *)MemAlloc(0x18u);
              v27 = v28;
              if ( v28 )
              {
                *((_QWORD *)v28 + 1) = 0;
                *(_QWORD *)v28 = &CLanHomenetUnavailable::`vftable';
                *((_DWORD *)v28 + 4) = Instance;
                LinkWindow_RegisterClass();
              }
              else
              {
                v27 = 0;
              }
              *(_QWORD *)(this + 104) = v27;
              if ( v27 )
              {
LABEL_61:
                v29 = CPropSheetPage::CreatePage(
                        v27,
                        0x3ECCu,
                        v21,
                        v22,
                        (const unsigned __int16 *)ppva,
                        (const unsigned __int16 *)v32,
                        v33);
                a3(v29, a4);
              }
              Instance = 0;
            }
          }
        }
        HrFreeNetConProperties2(pv);
        goto LABEL_64;
      }
    }
    v14 = *(CPropSheetPage **)(this + 88);
    if ( v14
      || ((v14 = (CPropSheetPage *)MemAlloc(0xB8u)) == 0
        ? (v14 = 0)
        : (CPropSheetPage *)(CLanNetPage::CLanNetPage(
                               v14,
                               (struct IUnknown *)(this & -(__int64)(this != 8)),
                               *(struct INetCfg **)(this + 120),
                               *(struct INetConnection **)(this + 80),
                               *(_BYTE *)(this + 176),
                               *(_BYTE *)(this + 177),
                               *(_BYTE *)(this + 178)),
                             *((_DWORD *)v14 + 44) = 0,
                             *(_QWORD *)v14 = &CLanNetNormalPage::`vftable'),
          (*(_QWORD *)(this + 88) = v14) != 0) )
    {
      v16 = 16004;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  return (unsigned int)-2147467261;
}

```

## disassembly

```asm
0x18002a9e0  push    rbp
0x18002a9e2  push    rbx
0x18002a9e3  push    rsi
0x18002a9e4  push    rdi
0x18002a9e5  push    r12
0x18002a9e7  push    r14
0x18002a9e9  push    r15
0x18002a9eb  mov     rbp, rsp
0x18002a9ee  sub     rsp, 80h
0x18002a9f5  mov     rax, cs:__security_cookie
0x18002a9fc  xor     rax, rsp
0x18002a9ff  mov     [rbp+var_8], rax
0x18002aa03  mov     r15, r9
0x18002aa06  mov     r14, r8
0x18002aa09  xorps   xmm0, xmm0
0x18002aa0c  xor     r9d, r9d; int
0x18002aa0f  mov     r8d, 22Ch; unsigned int
0x18002aa15  mov     rbx, rcx
0x18002aa18  movups  [rbp+var_18], xmm0
0x18002aa1c  call    ?FCheckGroupMembershipInternal@@YAHEKKH@Z; FCheckGroupMembershipInternal(uchar,ulong,ulong,int)
0x18002aa21  xor     r12d, r12d
0x18002aa24  test    eax, eax
0x18002aa26  jnz     short loc_18002AA44
0x18002aa28  xor     r9d, r9d; int
0x18002aa2b  mov     r8d, 220h; unsigned int
0x18002aa31  call    ?FCheckGroupMembershipInternal@@YAHEKKH@Z; FCheckGroupMembershipInternal(uchar,ulong,ulong,int)
0x18002aa36  test    eax, eax
0x18002aa38  jnz     short loc_18002AA44
0x18002aa3a  mov     eax, 800702E4h
0x18002aa3f  jmp     loc_18002AED1
0x18002aa44  test    r14, r14
0x18002aa47  jnz     short loc_18002AA53
0x18002aa49  mov     esi, 80004003h
0x18002aa4e  jmp     loc_18002AECF
0x18002aa53  mov     rcx, [rbx+50h]
0x18002aa57  test    rcx, rcx
0x18002aa5a  jnz     short loc_18002AA66
0x18002aa5c  mov     esi, 8000FFFFh
0x18002aa61  jmp     loc_18002AECF
0x18002aa66  mov     [rbp+var_20], r12
0x18002aa6a  lea     r8, [rbp+var_20]
0x18002aa6e  mov     [rbp+pv], r12
0x18002aa72  lea     rdx, IID_INetConnection2
0x18002aa79  mov     rax, [rcx]
0x18002aa7c  mov     rax, [rax]
0x18002aa7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa84  mov     esi, eax
0x18002aa86  test    eax, eax
0x18002aa88  js      loc_18002AEC6
0x18002aa8e  mov     rcx, [rbp+var_20]
0x18002aa92  lea     rdx, [rbp+pv]
0x18002aa96  mov     rax, [rcx]
0x18002aa99  mov     rax, [rax+18h]
0x18002aa9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaa2  mov     esi, eax
0x18002aaa4  test    eax, eax
0x18002aaa6  js      loc_18002AEC6
0x18002aaac  mov     ecx, 10h; nVirtKey
0x18002aab1  call    cs:__imp_GetKeyState
0x18002aab7  bt      ax, 0Fh
0x18002aabc  jb      loc_18002ABDC
0x18002aac2  mov     rax, [rbp+pv]
0x18002aac6  cmp     dword ptr [rax+2Ch], 7
0x18002aaca  jnz     loc_18002AB5A
0x18002aad0  mov     rdi, [rbx+58h]
0x18002aad4  test    rdi, rdi
0x18002aad7  jnz     short loc_18002AB50
0x18002aad9  mov     ecx, 0C0h; unsigned __int64
0x18002aade  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002aae3  mov     rdi, rax
0x18002aae6  test    rax, rax
0x18002aae9  jz      short loc_18002AB40
0x18002aaeb  mov     r9, [rbx+50h]; struct INetConnection *
0x18002aaef  lea     rax, [rbx-8]
0x18002aaf3  mov     r8, [rbx+78h]; struct INetCfg *
0x18002aaf7  neg     rax
0x18002aafa  mov     al, [rbx+0B2h]
0x18002ab00  mov     rcx, rdi; this
0x18002ab03  mov     byte ptr [rsp+80h+var_50], al; char
0x18002ab07  sbb     rdx, rdx
0x18002ab0a  mov     al, [rbx+0B1h]
0x18002ab10  and     rdx, rbx; struct IUnknown *
0x18002ab13  mov     byte ptr [rsp+80h+var_58], al; char
0x18002ab17  mov     al, [rbx+0B0h]
0x18002ab1d  mov     byte ptr [rsp+80h+ppv], al; char
0x18002ab21  call    ??0CLanNetPage@@QEAA@PEAUIUnknown@@PEAUINetCfg@@PEAUINetConnection@@EEE@Z; CLanNetPage::CLanNetPage(IUnknown *,INetCfg *,INetConnection *,uchar,uchar,uchar)
0x18002ab26  lea     rax, ??_7CLanNetNetworkBridgePage@@6B@; const CLanNetNetworkBridgePage::`vftable'
0x18002ab2d  mov     [rdi+0B0h], r12
0x18002ab34  mov     [rdi], rax
0x18002ab37  mov     [rdi+0B8h], r12
0x18002ab3e  jmp     short loc_18002AB43
0x18002ab40  mov     rdi, r12
0x18002ab43  mov     [rbx+58h], rdi
0x18002ab47  test    rdi, rdi
0x18002ab4a  jz      loc_18002AC6C
0x18002ab50  mov     edx, 3EBBh
0x18002ab55  jmp     loc_18002AC56
0x18002ab5a  test    dword ptr [rax+34h], 200h
0x18002ab61  jz      short loc_18002ABDC
0x18002ab63  mov     rdi, [rbx+58h]
0x18002ab67  test    rdi, rdi
0x18002ab6a  jnz     short loc_18002ABD5
0x18002ab6c  mov     ecx, 0A8h; unsigned __int64
0x18002ab71  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002ab76  mov     rdi, rax
0x18002ab79  test    rax, rax
0x18002ab7c  jz      short loc_18002ABC5
0x18002ab7e  mov     r9, [rbx+50h]; struct INetConnection *
0x18002ab82  lea     rax, [rbx-8]
0x18002ab86  mov     r8, [rbx+78h]; struct INetCfg *
0x18002ab8a  neg     rax
0x18002ab8d  mov     al, [rbx+0B2h]
0x18002ab93  mov     rcx, rdi; this
0x18002ab96  mov     byte ptr [rsp+80h+var_50], al; char
0x18002ab9a  sbb     rdx, rdx
0x18002ab9d  mov     al, [rbx+0B1h]
0x18002aba3  and     rdx, rbx; struct IUnknown *
0x18002aba6  mov     byte ptr [rsp+80h+var_58], al; char
0x18002abaa  mov     al, [rbx+0B0h]
0x18002abb0  mov     byte ptr [rsp+80h+ppv], al; char
0x18002abb4  call    ??0CLanNetPage@@QEAA@PEAUIUnknown@@PEAUINetCfg@@PEAUINetConnection@@EEE@Z; CLanNetPage::CLanNetPage(IUnknown *,INetCfg *,INetConnection *,uchar,uchar,uchar)
0x18002abb9  lea     rax, ??_7CLanNetBridgedPage@@6B@; const CLanNetBridgedPage::`vftable'
0x18002abc0  mov     [rdi], rax
0x18002abc3  jmp     short loc_18002ABC8
0x18002abc5  mov     rdi, r12
0x18002abc8  mov     [rbx+58h], rdi
0x18002abcc  test    rdi, rdi
0x18002abcf  jz      loc_18002AC6C
0x18002abd5  mov     edx, 3EBAh
0x18002abda  jmp     short loc_18002AC56
0x18002abdc  mov     rdi, [rbx+58h]
0x18002abe0  test    rdi, rdi
0x18002abe3  jnz     short loc_18002AC51
0x18002abe5  mov     ecx, 0B8h; unsigned __int64
0x18002abea  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002abef  mov     rdi, rax
0x18002abf2  test    rax, rax
0x18002abf5  jz      short loc_18002AC45
0x18002abf7  mov     r9, [rbx+50h]; struct INetConnection *
0x18002abfb  lea     rax, [rbx-8]
0x18002abff  mov     r8, [rbx+78h]; struct INetCfg *
0x18002ac03  neg     rax
0x18002ac06  mov     al, [rbx+0B2h]
0x18002ac0c  mov     rcx, rdi; this
0x18002ac0f  mov     byte ptr [rsp+80h+var_50], al; char
0x18002ac13  sbb     rdx, rdx
0x18002ac16  mov     al, [rbx+0B1h]
0x18002ac1c  and     rdx, rbx; struct IUnknown *
0x18002ac1f  mov     byte ptr [rsp+80h+var_58], al; char
0x18002ac23  mov     al, [rbx+0B0h]
0x18002ac29  mov     byte ptr [rsp+80h+ppv], al; char
0x18002ac2d  call    ??0CLanNetPage@@QEAA@PEAUIUnknown@@PEAUINetCfg@@PEAUINetConnection@@EEE@Z; CLanNetPage::CLanNetPage(IUnknown *,INetCfg *,INetConnection *,uchar,uchar,uchar)
0x18002ac32  lea     rax, ??_7CLanNetNormalPage@@6B@; const CLanNetNormalPage::`vftable'
0x18002ac39  mov     [rdi+0B0h], r12d
0x18002ac40  mov     [rdi], rax
0x18002ac43  jmp     short loc_18002AC48
0x18002ac45  mov     rdi, r12
0x18002ac48  mov     [rbx+58h], rdi
0x18002ac4c  test    rdi, rdi
0x18002ac4f  jz      short loc_18002AC6C
0x18002ac51  mov     edx, 3E84h; unsigned int
0x18002ac56  mov     rcx, rdi; this
0x18002ac59  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *)
0x18002ac5e  mov     rcx, rax
0x18002ac61  mov     rdx, r15
0x18002ac64  mov     rax, r14
0x18002ac67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac6c  mov     rax, [rbp+pv]
0x18002ac70  cmp     dword ptr [rax+2Ch], 3
0x18002ac74  jnz     loc_18002AD2E
0x18002ac7a  cmp     dword ptr [rax+30h], 1
0x18002ac7e  jnz     loc_18002AD2E
0x18002ac84  cmp     [rbx+70h], r12
0x18002ac88  jnz     short loc_18002ACDF
0x18002ac8a  xor     edx, edx; hFile
0x18002ac8c  lea     rcx, aDot3uiDll; "dot3ui.dll"
0x18002ac93  mov     r8d, 800h; dwFlags
0x18002ac99  call    cs:__imp_LoadLibraryExW
0x18002ac9f  mov     [rbx+70h], rax
0x18002aca3  test    rax, rax
0x18002aca6  jz      short loc_18002ACD9
0x18002aca8  lea     rdx, aDot3createpspa; "Dot3CreatePsPage"
0x18002acaf  mov     rcx, rax; hModule
0x18002acb2  call    cs:__imp_GetProcAddress
0x18002acb8  mov     [rbx+0B8h], rax
0x18002acbf  test    rax, rax
0x18002acc2  jnz     short loc_18002ACD9
0x18002acc4  mov     rcx, [rbx+70h]; hLibModule
0x18002acc8  call    cs:__imp_FreeLibrary
0x18002acce  mov     [rbx+70h], r12
0x18002acd2  mov     [rbx+0B8h], r12
0x18002acd9  cmp     [rbx+70h], r12
0x18002acdd  jz      short loc_18002AD2E
0x18002acdf  lea     rcx, [rbx+10h]
0x18002ace3  mov     rax, [rcx]
0x18002ace6  lea     rdx, [rbp+var_18]
0x18002acea  mov     rax, [rax+18h]
0x18002acee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acf3  mov     esi, eax
0x18002acf5  test    eax, eax
0x18002acf7  js      short loc_18002AD2E
0x18002acf9  mov     rax, [rbx+0B8h]
0x18002ad00  lea     rcx, [rbp+var_18]
0x18002ad04  mov     [rsp+80h+var_58], r12
0x18002ad09  xor     r9d, r9d
0x18002ad0c  xor     r8d, r8d
0x18002ad0f  mov     [rsp+80h+ppv], r12
0x18002ad14  xor     edx, edx
0x18002ad16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad1b  test    rax, rax
0x18002ad1e  jz      short loc_18002AD2E
0x18002ad20  mov     rcx, rax
0x18002ad23  mov     rdx, r15
0x18002ad26  mov     rax, r14
0x18002ad29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ad2e  mov     rax, [rbp+pv]
0x18002ad32  test    dword ptr [rax+34h], 1000h
0x18002ad39  jz      loc_18002AEBD
0x18002ad3f  mov     eax, [rax+30h]
0x18002ad42  sub     eax, 7
0x18002ad45  cmp     eax, 1
0x18002ad48  jbe     loc_18002AEBD
0x18002ad4e  lea     rdx, [rbp+var_40]; unsigned int *
0x18002ad52  mov     dword ptr [rbp+var_40], r12d
0x18002ad56  call    ?HrSvcQueryStatus@@YAJPEBGPEAK@Z; HrSvcQueryStatus(ushort const *,ulong *)
0x18002ad5b  test    eax, eax
0x18002ad5d  js      loc_18002AEBD
0x18002ad63  cmp     dword ptr [rbp+var_40], 4
0x18002ad67  jnz     loc_18002AEBD
0x18002ad6d  xor     edx, edx; pUnkOuter
0x18002ad6f  mov     [rbp+var_40], r12
0x18002ad73  lea     rax, [rbp+var_40]
0x18002ad77  mov     [rbp+var_28], r12
0x18002ad7b  lea     r9, IID_IHNetCfgMgr; riid
0x18002ad82  mov     [rbp+var_30], r12
0x18002ad86  lea     rcx, CLSID_HNetCfgMgr; rclsid
0x18002ad8d  mov     [rsp+80h+ppv], rax; ppv
0x18002ad92  lea     r8d, [rdx+17h]; dwClsContext
0x18002ad96  call    cs:__imp_CoCreateInstance
0x18002ad9c  mov     esi, eax
0x18002ad9e  test    eax, eax
0x18002ada0  js      loc_18002AE61
0x18002ada6  mov     rcx, [rbp+var_40]
0x18002adaa  lea     r8, [rbp+var_28]
0x18002adae  lea     rdx, _GUID_85d18b6f_3032_11d4_9348_00c04f8eeb71
0x18002adb5  mov     rax, [rcx]
0x18002adb8  mov     rax, [rax]
0x18002adbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adc0  mov     esi, eax
0x18002adc2  test    eax, eax
0x18002adc4  js      loc_18002AE54
0x18002adca  mov     rcx, [rbp+var_40]
0x18002adce  lea     r8, [rbp+var_30]
0x18002add2  mov     rdx, [rbx+50h]
0x18002add6  mov     rax, [rcx]
0x18002add9  mov     rax, [rax+18h]
0x18002addd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ade2  mov     esi, eax
0x18002ade4  test    eax, eax
0x18002ade6  js      short loc_18002AE4B
0x18002ade8  lea     rdi, [rbx+60h]
0x18002adec  cmp     [rdi], r12
0x18002adef  jnz     short loc_18002AE22
0x18002adf1  mov     r9, [rbp+var_40]; struct IHNetCfgMgr *
0x18002adf5  lea     rax, [rbx-8]
0x18002adf9  mov     rcx, [rbx+50h]; struct INetConnection *
0x18002adfd  neg     rax
0x18002ae00  mov     rax, [rbp+var_30]
0x18002ae04  mov     r8, rdi; struct CPropSheetPage **
0x18002ae07  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18002ae0c  sbb     rdx, rdx
0x18002ae0f  mov     rax, [rbp+var_28]
0x18002ae13  and     rdx, rbx; struct IUnknown *
0x18002ae16  mov     [rsp+80h+ppv], rax; unsigned __int16 *
0x18002ae1b  call    ?HrQueryLanAdvancedPage@@YAJPEAUINetConnection@@PEAUIUnknown@@AEAPEAVCPropSheetPage@@PEAUIHNetCfgMgr@@PEAUIHNetIcsSettings@@PEAUIHNetConnection@@@Z; HrQueryLanAdvancedPage(INetConnection *,IUnknown *,CPropSheetPage * &,IHNetCfgMgr *,IHNetIcsSettings *,IHNetConnection *)
0x18002ae20  mov     esi, eax
0x18002ae22  mov     rcx, [rdi]; this
0x18002ae25  test    rcx, rcx
0x18002ae28  jz      short loc_18002AE42
0x18002ae2a  mov     edx, 29FFh; unsigned int
0x18002ae2f  call    ?CreatePage@CPropSheetPage@@QEAAPEAU_PSP@@IKPEBG00PEAUHINSTANCE__@@@Z; CPropSheetPage::CreatePage(uint,ulong,ushort const *,ushort const *,ushort const *,HINSTANCE__ *)
0x18002ae34  mov     rcx, rax
0x18002ae37  mov     rdx, r15
0x18002ae3a  mov     rax, r14
0x18002ae3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae42  mov     rcx, [rbp+var_30]; struct IUnknown *
0x18002ae46  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002ae4b  mov     rcx, [rbp+var_28]; struct IUnknown *
0x18002ae4f  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002ae54  mov     rcx, [rbp+var_40]; struct IUnknown *
0x18002ae58  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002ae5d  test    esi, esi
0x18002ae5f  jns     short loc_18002AEBD
0x18002ae61  mov     rdi, [rbx+68h]
0x18002ae65  test    rdi, rdi
0x18002ae68  jnz     short loc_18002AE9F
0x18002ae6a  lea     ecx, [rdi+18h]; unsigned __int64
0x18002ae6d  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18002ae72  mov     rdi, rax
0x18002ae75  test    rax, rax
  ... truncated ...
```
