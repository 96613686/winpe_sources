# CreateWizard(HWND__ *,CSharePageSharedData *,int)

- ea: `0x1800715e4`
- end: `0x1800718db`
- name: `?CreateWizard@@YAJPEAUHWND__@@PEAVCSharePageSharedData@@H@Z`
- size: `759`
- prototype: `__int64 __fastcall(HWND, struct CSharePageSharedData *, int)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x180071cf0`
- `0x180071e2c`

## callees

- `0x18000323c`
- `0x1800098dc`
- `0x1800254e0`
- `0x180026394`
- `0x1800341c4`
- `0x180035248`
- `0x1800713bc`
- `0x1800713e8`
- `0x1800715e4`
- `0x180071fc0`
- `0x180074208`
- `0x180074480`
- `0x1800746bc`
- `0x180074724`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007177c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18007177c`
- `USER32!SetThreadDpiAwarenessContext` at `0x180071646`
- `USER32!SetThreadDpiAwarenessContext` at `0x18007189b`
- `USER32!SetThreadDpiAwarenessContext` at `0x180071646`
- `USER32!SetThreadDpiAwarenessContext` at `0x18007189b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreateWizard(HWND a1, struct CSharePageSharedData *a2, int a3)
{
  CShareCache *v6; // rcx
  int Error; // ebx
  signed int i; // edi
  __int64 v9; // rbx
  __int64 SharePage; // rax
  __int64 v11; // rdx
  struct _PSP *PropertySheetPageW; // rax
  DWORD v13; // eax
  unsigned int j; // edi
  struct _PSP *v15; // rcx
  unsigned int k; // edi
  CShareCache *v17; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h]
  PROPSHEETHEADERW_V2 v20; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v21[42]; // [rsp+90h] [rbp-70h] BYREF
  HPROPSHEETPAGE v22[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v23; // [rsp+1F0h] [rbp+F0h]
  __int128 v24; // [rsp+200h] [rbp+100h]
  _BYTE v25[192]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v26[624]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Buffer[56]; // [rsp+540h] [rbp+440h] BYREF

  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v21);
  v21[0] = &SharingWizardTelemetry::ShowSharingWizard::`vftable';
  SharingWizardTelemetry::ShowSharingWizard::StartActivity((SharingWizardTelemetry::ShowSharingWizard *)v21);
  v19 = SetThreadDpiAwarenessContext(-2);
  CShareCache::Refresh(v6);
  Error = 0;
  *(_OWORD *)v22 = 0;
  v23 = 0;
  v24 = 0;
  memset_0(v26, 0, sizeof(v26));
  memset_0(v25, 0, sizeof(v25));
  for ( i = 0; (unsigned int)i < 6; ++i )
  {
    v9 = 32LL * i;
    *(_QWORD *)&v25[v9] = 32;
    *(_QWORD *)&v25[v9 + 16] = a2;
    SharePage = CreateSharePage(HIDWORD(qword_180082B10[i]));
    *(_QWORD *)&v25[v9 + 8] = SharePage;
    if ( !SharePage )
      goto LABEL_6;
    v11 = 104LL * i;
    *(_DWORD *)&v26[v11] = 104;
    *(_QWORD *)&v26[v11 + 8] = g_hInstance;
    *(_DWORD *)&v26[v11 + 4] = 4096;
    *(_QWORD *)&v26[v11 + 16] = LOWORD(qword_180082B10[i]);
    *(_QWORD *)&v26[v11 + 40] = CSharePage::s_SharePageDlgProc;
    *(_QWORD *)&v26[v11 + 48] = &v25[v9];
    PropertySheetPageW = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)&v26[v11]);
    v22[i] = PropertySheetPageW;
    if ( !PropertySheetPageW )
    {
LABEL_6:
      Error = -2147024882;
      break;
    }
    Error = 0;
  }
  if ( Error < 0 )
  {
    for ( j = 0; j < 6; ++j )
    {
      v15 = v22[j];
      if ( v15 )
        DestroyPropertySheetPage(v15);
    }
  }
  else
  {
    LoadStringW(g_hInstance, 0xC84u, Buffer, 50);
    memset_0(&v20, 0, sizeof(v20));
    v20.dwSize = 96;
    v20.dwFlags = 16402;
    v20.hwndParent = a1;
    v20.hInstance = g_hInstance;
    v20.ppsp = (LPCPROPSHEETPAGEW)v22;
    v20.nPages = 6;
    v20.nStartPage = 0;
    v20.pszCaption = Buffer;
    LoadIconMetric(0, (PCWSTR)0xB2, 1, &v20.hIcon);
    if ( !a3 )
    {
      v13 = v20.dwFlags | 0x4000000;
      v20.dwFlags |= 0x4000000u;
      if ( *((_DWORD *)a2 + 2) != 4 && *((_DWORD *)a2 + 23) == 2 )
      {
        v20.dwFlags = v13 | 0x100;
        v20.pfnCallback = (PFNPROPSHEETCALLBACK)WizardPSCallback;
      }
    }
    if ( PropertySheetW(&v20) == -1 )
      Error = ResultFromKnownLastError();
    else
      Error = 0;
  }
  for ( k = 0; k < 6; ++k )
  {
    v17 = *(CShareCache **)&v25[32 * k + 8];
    if ( v17 )
    {
      (*(void (__fastcall **)(CShareCache *))(*(_QWORD *)v17 + 16LL))(v17);
      *(_QWORD *)&v25[32 * k + 8] = 0;
    }
  }
  CShareCache::Refresh(v17);
  SetThreadDpiAwarenessContext(v19);
  wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v21, (unsigned int)Error);
  SharingWizardTelemetry::ShowSharingWizard::~ShowSharingWizard((SharingWizardTelemetry::ShowSharingWizard *)v21);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800715e4  push    rbp
0x1800715e6  push    rbx
0x1800715e7  push    rsi
0x1800715e8  push    rdi
0x1800715e9  push    r12
0x1800715eb  push    r13
0x1800715ed  push    r14
0x1800715ef  push    r15
0x1800715f1  lea     rbp, [rsp-4C8h]
0x1800715f9  sub     rsp, 5C8h
0x180071600  mov     rax, cs:__security_cookie
0x180071607  xor     rax, rsp
0x18007160a  mov     [rbp+500h+var_50], rax
0x180071611  mov     r12d, r8d
0x180071614  mov     r14, rdx
0x180071617  mov     r13, rcx
0x18007161a  lea     rdx, aShowsharingwiz; "ShowSharingWizard"
0x180071621  lea     rcx, [rbp+500h+var_570]; struct wil::details::IFailureCallback *
0x180071625  call    ??0?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18007162a  lea     rax, ??_7ShowSharingWizard@SharingWizardTelemetry@@6B@; const SharingWizardTelemetry::ShowSharingWizard::`vftable'
0x180071631  mov     [rbp+500h+var_570], rax
0x180071635  lea     rcx, [rbp+500h+var_570]; this
0x180071639  call    ?StartActivity@ShowSharingWizard@SharingWizardTelemetry@@QEAAXXZ; SharingWizardTelemetry::ShowSharingWizard::StartActivity(void)
0x18007163e  nop
0x18007163f  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180071646  call    cs:__imp_SetThreadDpiAwarenessContext
0x18007164c  mov     [rsp+600h+var_5E0], rax
0x180071651  call    ?Refresh@CShareCache@@QEAAXXZ; CShareCache::Refresh(void)
0x180071656  xor     ebx, ebx
0x180071658  xorps   xmm0, xmm0
0x18007165b  movups  xmmword ptr [rbp+500h+var_420], xmm0
0x180071662  movups  [rbp+500h+var_410], xmm0
0x180071669  movups  [rbp+500h+var_400], xmm0
0x180071670  xor     edx, edx; Val
0x180071672  mov     r8d, 270h; Size
0x180071678  lea     rcx, [rbp+500h+var_330]; void *
0x18007167f  call    memset_0
0x180071684  xor     edx, edx; Val
0x180071686  mov     r8d, 0C0h; Size
0x18007168c  lea     rcx, [rbp+500h+var_3F0]; void *
0x180071693  call    memset_0
0x180071698  xor     edi, edi
0x18007169a  lea     rax, qword_180082B10
0x1800716a1  cmp     edi, 6
0x1800716a4  jnb     loc_18007175B
0x1800716aa  movsxd  rsi, edi
0x1800716ad  mov     rbx, rsi
0x1800716b0  shl     rbx, 5
0x1800716b4  lea     r15, [rbp+500h+var_3F0]
0x1800716bb  add     r15, rbx
0x1800716be  mov     qword ptr [r15], 20h ; ' '
0x1800716c5  mov     [rbp+rbx+500h+var_3E0], r14
0x1800716cd  mov     ecx, [rax+rsi*8+4]
0x1800716d1  call    ?CreateSharePage@@YAPEAVCSharePage@@W4_SHAREPAGETYPE@@@Z; CreateSharePage(_SHAREPAGETYPE)
0x1800716d6  mov     [rbp+rbx+500h+var_3E8], rax
0x1800716de  test    rax, rax
0x1800716e1  jz      short loc_180071756
0x1800716e3  imul    rdx, rsi, 68h ; 'h'
0x1800716e7  lea     rcx, [rbp+500h+var_330]
0x1800716ee  add     rcx, rdx; constPropSheetPagePointer
0x1800716f1  mov     dword ptr [rcx], 68h ; 'h'
0x1800716f7  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800716fe  mov     [rbp+rdx+500h+var_328], rax
0x180071706  mov     [rbp+rdx+500h+var_32C], 1000h
0x180071711  lea     rax, qword_180082B10
0x180071718  movzx   eax, word ptr [rax+rsi*8]
0x18007171c  mov     [rbp+rdx+500h+var_320], rax
0x180071724  lea     rax, ?s_SharePageDlgProc@CSharePage@@SA_JPEAUHWND__@@I_K_J@Z; CSharePage::s_SharePageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18007172b  mov     [rbp+rdx+500h+var_308], rax
0x180071733  mov     [rbp+rdx+500h+var_300], r15
0x18007173b  call    CreatePropertySheetPageW
0x180071740  mov     [rbp+rsi*8+500h+var_420], rax
0x180071748  test    rax, rax
0x18007174b  jz      short loc_180071756
0x18007174d  xor     ebx, ebx
0x18007174f  inc     edi
0x180071751  jmp     loc_18007169A
0x180071756  mov     ebx, 8007000Eh
0x18007175b  test    ebx, ebx
0x18007175d  js      loc_18007183E
0x180071763  mov     r9d, 32h ; '2'; cchBufferMax
0x180071769  lea     r8, [rbp+500h+Buffer]; lpBuffer
0x180071770  mov     edx, 0C84h; uID
0x180071775  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18007177c  call    cs:__imp_LoadStringW
0x180071782  mov     ebx, 60h ; '`'
0x180071787  mov     r8d, ebx; Size
0x18007178a  xor     edx, edx; Val
0x18007178c  lea     rcx, [rsp+600h+var_5D0]; void *
0x180071791  call    memset_0
0x180071796  mov     [rsp+600h+var_5D0.dwSize], ebx
0x18007179a  mov     [rsp+600h+var_5D0.dwFlags], 4012h
0x1800717a2  mov     [rsp+600h+var_5D0.hwndParent], r13
0x1800717a7  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800717ae  mov     [rsp+600h+var_5D0.hInstance], rax
0x1800717b3  lea     rax, [rbp+500h+var_420]
0x1800717ba  mov     qword ptr [rsp+600h+var_5D0.38h], rax
0x1800717bf  mov     [rsp+600h+var_5D0.nPages], 6
0x1800717c7  mov     dword ptr [rsp+600h+var_5D0.30h], 0
0x1800717cf  lea     rax, [rbp+500h+Buffer]
0x1800717d6  mov     [rsp+600h+var_5D0.pszCaption], rax
0x1800717db  lea     r9, [rsp+600h+var_5D0.18h]; phico
0x1800717e0  lea     edx, [rbx+52h]; pszName
0x1800717e3  xor     ecx, ecx; hinst
0x1800717e5  lea     r8d, [rbx-5Fh]; lims
0x1800717e9  call    LoadIconMetric
0x1800717ee  test    r12d, r12d
0x1800717f1  jnz     short loc_180071821
0x1800717f3  mov     eax, [rsp+600h+var_5D0.dwFlags]
0x1800717f7  bts     eax, 1Ah
0x1800717fb  mov     [rsp+600h+var_5D0.dwFlags], eax
0x1800717ff  cmp     dword ptr [r14+8], 4
0x180071804  jz      short loc_180071821
0x180071806  cmp     dword ptr [r14+5Ch], 2
0x18007180b  jnz     short loc_180071821
0x18007180d  bts     eax, 8
0x180071811  mov     [rsp+600h+var_5D0.dwFlags], eax
0x180071815  lea     rax, WizardPSCallback
0x18007181c  mov     [rsp+600h+var_5D0.pfnCallback], rax
0x180071821  lea     rcx, [rsp+600h+var_5D0]; LPCPROPSHEETHEADERW
0x180071826  call    PropertySheetW
0x18007182b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007182f  jnz     short loc_18007183A
0x180071831  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180071836  mov     ebx, eax
0x180071838  jmp     short loc_18007185C
0x18007183a  xor     ebx, ebx
0x18007183c  jmp     short loc_18007185C
0x18007183e  xor     edi, edi
0x180071840  movsxd  rax, edi
0x180071843  mov     rcx, [rbp+rax*8+500h+var_420]; HPROPSHEETPAGE
0x18007184b  test    rcx, rcx
0x18007184e  jz      short loc_180071855
0x180071850  call    DestroyPropertySheetPage
0x180071855  inc     edi
0x180071857  cmp     edi, 6
0x18007185a  jb      short loc_180071840
0x18007185c  xor     edi, edi
0x18007185e  movsxd  rsi, edi
0x180071861  shl     rsi, 5
0x180071865  mov     rcx, [rbp+rsi+500h+var_3E8]
0x18007186d  test    rcx, rcx
0x180071870  jz      short loc_18007188A
0x180071872  mov     rax, [rcx]
0x180071875  mov     rax, [rax+10h]
0x180071879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007187e  mov     [rbp+rsi+500h+var_3E8], 0
0x18007188a  inc     edi
0x18007188c  cmp     edi, 6
0x18007188f  jb      short loc_18007185E
0x180071891  call    ?Refresh@CShareCache@@QEAAXXZ; CShareCache::Refresh(void)
0x180071896  mov     rcx, [rsp+600h+var_5E0]
0x18007189b  call    cs:__imp_SetThreadDpiAwarenessContext
0x1800718a1  mov     edx, ebx
0x1800718a3  lea     rcx, [rbp+500h+var_570]
0x1800718a7  call    ?Stop@?$ActivityBase@VSharingWizardLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharingWizardLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800718ac  nop
0x1800718ad  lea     rcx, [rbp+500h+var_570]; this
0x1800718b1  call    ??1ShowSharingWizard@SharingWizardTelemetry@@QEAA@XZ; SharingWizardTelemetry::ShowSharingWizard::~ShowSharingWizard(void)
0x1800718b6  mov     eax, ebx
0x1800718b8  mov     rcx, [rbp+500h+var_50]
0x1800718bf  xor     rcx, rsp; StackCookie
0x1800718c2  call    __security_check_cookie
0x1800718c7  add     rsp, 5C8h
0x1800718ce  pop     r15
0x1800718d0  pop     r14
0x1800718d2  pop     r13
0x1800718d4  pop     r12
0x1800718d6  pop     rdi
0x1800718d7  pop     rsi
0x1800718d8  pop     rbx
0x1800718d9  pop     rbp
0x1800718da  retn
```
