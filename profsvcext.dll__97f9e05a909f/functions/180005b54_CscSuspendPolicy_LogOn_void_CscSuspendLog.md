# CscSuspendPolicy_LogOn(void *,CscSuspendLog *)

- ea: `0x180005b54`
- end: `0x180006132`
- name: `?CscSuspendPolicy_LogOn@@YAXPEAXPEAVCscSuspendLog@@@Z`
- size: `1502`
- prototype: `void __fastcall(void *, void ***)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800029d0`

## callees

- `0x180002f6c`
- `0x1800038e0`
- `0x18000502c`
- `0x180005a6c`
- `0x180005acc`
- `0x180005b54`
- `0x180006138`
- `0x180006154`
- `0x18000a520`
- `0x18000aef8`
- `0x18000f700`
- `0x18000f738`
- `0x18000f86c`
- `0x18000fa10`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005c9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180005c9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006102`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005d04`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005d04`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005d3f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005dd4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005e9d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005d3f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005dd4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180005e9d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005d64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005e31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000601a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005d64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005e31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000601a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800060f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CscSuspendPolicy_LogOn(void *a1, void ***a2)
{
  struct IOfflineFilesCache *v2; // rdi
  void ***v3; // r15
  unsigned int v5; // r9d
  unsigned int v6; // eax
  unsigned int v7; // r12d
  unsigned int v8; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // r13d
  unsigned int v11; // esi
  __int64 v12; // rcx
  LPVOID *v13; // rax
  HRESULT Instance; // eax
  HANDLE v15; // r14
  unsigned int i; // esi
  int v17; // eax
  void **v18; // r10
  unsigned int v19; // esi
  unsigned int j; // r14d
  bool v21; // si
  HRESULT (__stdcall *FindItem)(IOfflineFilesCache *, LPCWSTR, DWORD, IOfflineFilesItem **); // rbx
  PCNZWCH v23; // r13
  int v24; // eax
  HANDLE v25; // rbx
  int v26; // eax
  struct IOfflineFilesCacheVtbl *lpVtbl; // rax
  int v28; // eax
  __int64 v29; // rbx
  int v30; // eax
  void **v31; // r10
  const WCHAR *v32; // r9
  __int64 v33; // rax
  PCNZWCH v34; // r8
  HKEY v35; // rcx
  unsigned int v36; // [rsp+50h] [rbp-B0h] BYREF
  struct IOfflineFilesCache *v37; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v41; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+84h] [rbp-7Ch]
  unsigned __int16 *v44; // [rsp+88h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  void **v46; // [rsp+98h] [rbp-68h] BYREF
  PCNZWCH v47[64]; // [rsp+A0h] [rbp-60h] BYREF
  PCNZWCH lpString1[128]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 *v49[128]; // [rsp+6A0h] [rbp+5A0h] BYREF

  v2 = 0;
  hToken = a1;
  pv = 0;
  v36 = 0;
  v3 = &v46;
  v46 = &CscSuspendLogNull::`vftable';
  if ( a2 )
    v3 = a2;
  if ( (int)LoadPolicyPaths(a1, (unsigned __int16 **)&pv, &v36) < 0 )
    goto LABEL_59;
  hKey = 0;
  if ( OpenLastStateKey(a1, 0x2001Fu, &hKey) < 0 )
    goto LABEL_57;
  memset_0(v47, 0, sizeof(v47));
  v6 = MultiStringToArray((const unsigned __int16 *)pv, v36, v47, v5);
  v44 = 0;
  v7 = v6;
  v36 = 0;
  if ( LoadLastState(hKey, &v44, &v36) < 0 )
    goto LABEL_56;
  memset_0(v49, 0, 0x200u);
  v8 = 0;
  memset_0(lpString1, 0, 0x200u);
  v10 = MultiStringToArray(v44, v36, lpString1, v9);
  v11 = 0;
  if ( !v10 )
    goto LABEL_13;
  do
  {
    while ( (unsigned int)v2 < v7 )
    {
      if ( CompareStringW(0x7Fu, 1u, lpString1[v11], -1, v47[(unsigned int)v2], -1) == 2 )
        goto LABEL_11;
      LODWORD(v2) = (_DWORD)v2 + 1;
    }
    v12 = v8++;
    v49[v12] = (unsigned __int16 *)lpString1[v11];
LABEL_11:
    ++v11;
    v2 = 0;
  }
  while ( v11 < v10 );
  if ( v8 )
    goto LABEL_14;
LABEL_13:
  if ( v7 )
  {
LABEL_14:
    v37 = 0;
    v13 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IOfflineFilesCache>>(&v37);
    Instance = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, v13);
    if ( Instance < 0 )
    {
      ((void (__fastcall *)(void ***, _QWORD))(*v3)[4])(v3, (unsigned int)Instance);
    }
    else
    {
      if ( v8 )
      {
        `vector constructor iterator'(
          lpString1,
          0x10u,
          0x40u,
          (void *(*)(void *))COfflineFilesSuspendInfo::COfflineFilesSuspendInfo);
        v15 = hToken;
        if ( ImpersonateLoggedOnUser(hToken) )
        {
          GetSuspendItfs(
            v37,
            (const unsigned __int16 **const)v49,
            v8,
            (struct COfflineFilesSuspendInfo *const)lpString1);
          RevertToSelf();
        }
        for ( i = 0; i < v8; ++i )
        {
          v17 = (int)lpString1[2 * (_QWORD)v2 + 1];
          if ( v17 >= 0 )
            v17 = (*(__int64 (__fastcall **)(PCNZWCH, _QWORD))(*(_QWORD *)lpString1[2 * (_QWORD)v2] + 24LL))(
                    lpString1[2 * (_QWORD)v2],
                    0);
          v18 = *v3;
          if ( v17 < 0 )
            ((void (__fastcall *)(void ***, _QWORD, _QWORD, unsigned __int16 *))v18[2])(
              v3,
              0,
              (unsigned int)v17,
              v49[(_QWORD)v2]);
          else
            ((void (__fastcall *)(void ***, _QWORD, unsigned __int16 *))v18[1])(v3, 0, v49[(_QWORD)v2]);
          v2 = (struct IOfflineFilesCache *)((char *)v2 + 1);
        }
        LODWORD(v2) = 0;
        if ( ImpersonateLoggedOnUser(v15) )
        {
          do
          {
            v41 = v49[(unsigned int)v2];
            ((void (__fastcall *)(struct IOfflineFilesCache *, _QWORD, unsigned __int16 **, __int64, int, _DWORD, int, _QWORD))v37->lpVtbl->Unpin)(
              v37,
              0,
              &v41,
              1,
              1,
              0,
              32,
              0);
            LODWORD(v2) = (_DWORD)v2 + 1;
          }
          while ( (unsigned int)v2 < v8 );
          RevertToSelf();
          LODWORD(v2) = 0;
        }
        `vector destructor iterator'(
          lpString1,
          0x10u,
          0x40u,
          (void (*)(void *))COfflineFilesSuspendInfo::~COfflineFilesSuspendInfo);
      }
      else
      {
        v15 = hToken;
      }
      memset_0(lpString1, 0, 0x200u);
      v43 = 0;
      v19 = 0;
      if ( v7 )
      {
        `vector constructor iterator'(
          v49,
          0x10u,
          0x40u,
          (void *(*)(void *))COfflineFilesSuspendInfo::COfflineFilesSuspendInfo);
        if ( ImpersonateLoggedOnUser(v15) )
        {
          for ( j = 0; j < v7; ++j )
          {
            hToken = 0;
            v2 = v37;
            v21 = 1;
            FindItem = v37->lpVtbl->FindItem;
            Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&hToken);
            v23 = v47[j];
            v24 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, PCNZWCH, _QWORD, HANDLE *))FindItem)(
                    v2,
                    v23,
                    0,
                    &hToken);
            LODWORD(v2) = 0;
            if ( v24 >= 0 )
            {
              v25 = hToken;
              v40 = 0;
              v2 = **(struct IOfflineFilesCache ***)hToken;
              Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v40);
              v26 = ((__int64 (__fastcall *)(HANDLE, GUID *, __int64 *))v2)(
                      v25,
                      &GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b,
                      &v40);
              LODWORD(v2) = 0;
              if ( v26 >= 0 )
              {
                v36 = 0;
                v42 = 0;
                if ( (*(int (__fastcall **)(__int64, unsigned int *, int *))(*(_QWORD *)v40 + 32LL))(v40, &v36, &v42) >= 0 )
                  v21 = v36 == 0;
              }
              Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v40);
            }
            v41 = (unsigned __int16 *)v23;
            lpVtbl = v37->lpVtbl;
            if ( v21 )
              v28 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, unsigned __int16 **))lpVtbl->Pin)(
                      v37,
                      0,
                      &v41);
            else
              v28 = ((__int64 (__fastcall *)(struct IOfflineFilesCache *, _QWORD, unsigned __int16 **, __int64, _DWORD, int, _QWORD, _QWORD, _QWORD))lpVtbl->Synchronize)(
                      v37,
                      0,
                      &v41,
                      1,
                      0,
                      805306410,
                      0,
                      0,
                      0);
            if ( v28 < 0 )
              ((void (__fastcall *)(void ***, _QWORD, PCNZWCH))(*v3)[3])(v3, (unsigned int)v28, v23);
            Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&hToken);
          }
          v19 = v43;
          GetSuspendItfs(v37, v47, v7, (struct COfflineFilesSuspendInfo *const)v49);
          RevertToSelf();
        }
        v29 = 0;
        do
        {
          v30 = (int)v49[2 * v29 + 1];
          if ( v30 >= 0 )
            v30 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64))(*(_QWORD *)v49[2 * v29] + 24LL))(
                    v49[2 * v29],
                    1);
          v31 = *v3;
          v32 = v47[v29];
          if ( v30 < 0 )
          {
            ((void (__fastcall *)(void ***, __int64, _QWORD, const WCHAR *))v31[2])(v3, 1, (unsigned int)v30, v32);
          }
          else
          {
            v33 = v19;
            v34 = v47[v29];
            ++v19;
            lpString1[v33] = v32;
            ((void (__fastcall *)(void ***, __int64, PCNZWCH))v31[1])(v3, 1, v34);
          }
          LODWORD(v2) = (_DWORD)v2 + 1;
          ++v29;
        }
        while ( (unsigned int)v2 < v7 );
        `vector destructor iterator'(
          v49,
          0x10u,
          0x40u,
          (void (*)(void *))COfflineFilesSuspendInfo::~COfflineFilesSuspendInfo);
      }
      SaveLastState(hKey, lpString1, v19);
    }
    Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(&v37);
  }
LABEL_56:
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v44);
LABEL_57:
  v35 = hKey;
  hKey = 0;
  if ( v35 )
    RegCloseKey(v35);
LABEL_59:
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180005b54  mov     [rsp-8+arg_10], rbx
0x180005b59  push    rbp
0x180005b5a  push    rsi
0x180005b5b  push    rdi
0x180005b5c  push    r12
0x180005b5e  push    r13
0x180005b60  push    r14
0x180005b62  push    r15
0x180005b64  lea     rbp, [rsp-9B0h]
0x180005b6c  sub     rsp, 0AB0h
0x180005b73  mov     rax, cs:__security_cookie
0x180005b7a  xor     rax, rsp
0x180005b7d  mov     [rbp+9E0h+var_40], rax
0x180005b84  xor     edi, edi
0x180005b86  mov     [rsp+0AE0h+hToken], rcx
0x180005b8b  test    rdx, rdx
0x180005b8e  mov     [rbp+9E0h+pv], rdi
0x180005b92  lea     rax, ??_7CscSuspendLogNull@@6B@; const CscSuspendLogNull::`vftable'
0x180005b99  mov     [rsp+0AE0h+var_A90], edi
0x180005b9d  lea     r15, [rbp+9E0h+var_A48]
0x180005ba1  mov     [rbp+9E0h+var_A48], rax
0x180005ba5  cmovnz  r15, rdx
0x180005ba9  lea     r8, [rsp+0AE0h+var_A90]; unsigned int *
0x180005bae  lea     rdx, [rbp+9E0h+pv]; unsigned __int16 **
0x180005bb2  mov     rbx, rcx
0x180005bb5  call    ?LoadPolicyPaths@@YAJPEAXPEAPEAGAEAI@Z; LoadPolicyPaths(void *,ushort * *,uint &)
0x180005bba  test    eax, eax
0x180005bbc  js      loc_1800060FE
0x180005bc2  lea     r8, [rsp+0AE0h+hKey]; HKEY *
0x180005bc7  mov     [rsp+0AE0h+hKey], rdi
0x180005bcc  mov     edx, 2001Fh; unsigned int
0x180005bd1  mov     rcx, rbx; void *
0x180005bd4  call    ?OpenLastStateKey@@YAJPEAXKPEAPEAUHKEY__@@@Z; OpenLastStateKey(void *,ulong,HKEY__ * *)
0x180005bd9  test    eax, eax
0x180005bdb  js      loc_1800060E9
0x180005be1  mov     esi, 200h
0x180005be6  lea     rcx, [rbp+9E0h+var_A40]; void *
0x180005bea  mov     r8d, esi; Size
0x180005bed  xor     edx, edx; Val
0x180005bef  call    memset_0
0x180005bf4  mov     edx, [rsp+0AE0h+var_A90]; unsigned int
0x180005bf8  lea     r8, [rbp+9E0h+var_A40]; unsigned __int16 **
0x180005bfc  mov     rcx, [rbp+9E0h+pv]; unsigned __int16 *
0x180005c00  call    ?MultiStringToArray@@YAIPEBGIPEAPEBGI@Z; MultiStringToArray(ushort const *,uint,ushort const * *,uint)
0x180005c05  mov     rcx, [rsp+0AE0h+hKey]; HKEY
0x180005c0a  lea     r8, [rsp+0AE0h+var_A90]; unsigned int *
0x180005c0f  lea     rdx, [rbp+9E0h+var_A58]; unsigned __int16 **
0x180005c13  mov     [rbp+9E0h+var_A58], rdi
0x180005c17  mov     r12d, eax
0x180005c1a  mov     [rsp+0AE0h+var_A90], edi
0x180005c1e  call    ?LoadLastState@@YAJPEAUHKEY__@@PEAPEAGAEAI@Z; LoadLastState(HKEY__ *,ushort * *,uint &)
0x180005c23  test    eax, eax
0x180005c25  js      loc_1800060E0
0x180005c2b  mov     r8d, esi; Size
0x180005c2e  lea     rcx, [rbp+9E0h+var_440]; void *
0x180005c35  xor     edx, edx; Val
0x180005c37  call    memset_0
0x180005c3c  mov     r8d, esi; Size
0x180005c3f  lea     rcx, [rbp+9E0h+lpString1]; void *
0x180005c46  xor     edx, edx; Val
0x180005c48  mov     ebx, edi
0x180005c4a  call    memset_0
0x180005c4f  mov     edx, [rsp+0AE0h+var_A90]; unsigned int
0x180005c53  lea     r8, [rbp+9E0h+lpString1]; unsigned __int16 **
0x180005c5a  mov     rcx, [rbp+9E0h+var_A58]; unsigned __int16 *
0x180005c5e  call    ?MultiStringToArray@@YAIPEBGIPEAPEBGI@Z; MultiStringToArray(ushort const *,uint,ushort const * *,uint)
0x180005c63  mov     r13d, eax
0x180005c66  mov     esi, edi
0x180005c68  test    eax, eax
0x180005c6a  jz      short loc_180005CCE
0x180005c6c  mov     r14d, esi
0x180005c6f  cmp     edi, r12d
0x180005c72  jnb     short loc_180005CAA
0x180005c74  mov     r8, [rbp+r14*8+9E0h+lpString1]; lpString1
0x180005c7c  or      r9d, 0FFFFFFFFh; cchCount1
0x180005c80  mov     eax, edi
0x180005c82  mov     [rsp+0AE0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180005c8a  lea     edx, [r9+2]; dwCmpFlags
0x180005c8e  mov     rax, [rbp+rax*8+9E0h+var_A40]
0x180005c93  lea     ecx, [rdx+7Eh]; Locale
0x180005c96  mov     [rsp+0AE0h+lpString2], rax; lpString2
0x180005c9b  call    cs:__imp_CompareStringW
0x180005ca1  cmp     eax, 2
0x180005ca4  jz      short loc_180005CBE
0x180005ca6  inc     edi
0x180005ca8  jmp     short loc_180005C6F
0x180005caa  mov     rax, [rbp+r14*8+9E0h+lpString1]
0x180005cb2  mov     ecx, ebx
0x180005cb4  inc     ebx
0x180005cb6  mov     [rbp+rcx*8+9E0h+var_440], rax
0x180005cbe  inc     esi
0x180005cc0  mov     edi, 0
0x180005cc5  cmp     esi, r13d
0x180005cc8  jb      short loc_180005C6C
0x180005cca  test    ebx, ebx
0x180005ccc  jnz     short loc_180005CD7
0x180005cce  test    r12d, r12d
0x180005cd1  jz      loc_1800060E0
0x180005cd7  lea     rcx, [rsp+0AE0h+var_A88]
0x180005cdc  mov     [rsp+0AE0h+var_A88], rdi
0x180005ce1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IOfflineFilesCache>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IOfflineFilesCache>>)
0x180005ce6  mov     r13d, 1
0x180005cec  mov     [rsp+0AE0h+lpString2], rax; ppv
0x180005cf1  mov     r8d, r13d; dwClsContext
0x180005cf4  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180005cfb  xor     edx, edx; pUnkOuter
0x180005cfd  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180005d04  call    cs:__imp_CoCreateInstance
0x180005d0a  mov     edx, eax
0x180005d0c  test    eax, eax
0x180005d0e  js      loc_1800060C7
0x180005d14  test    ebx, ebx
0x180005d16  jz      loc_180005E57
0x180005d1c  lea     r9, ??0COfflineFilesSuspendInfo@@QEAA@XZ; void *(*)(void *)
0x180005d23  lea     edx, [r13+0Fh]; unsigned __int64
0x180005d27  lea     r8d, [r13+3Fh]; unsigned __int64
0x180005d2b  lea     rcx, [rbp+9E0h+lpString1]; void *
0x180005d32  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180005d37  mov     r14, [rsp+0AE0h+hToken]
0x180005d3c  mov     rcx, r14; hToken
0x180005d3f  call    cs:__imp_ImpersonateLoggedOnUser
0x180005d45  test    eax, eax
0x180005d47  jz      short loc_180005D6A
0x180005d49  mov     rcx, [rsp+0AE0h+var_A88]; struct IOfflineFilesCache *
0x180005d4e  lea     r9, [rbp+9E0h+lpString1]; struct COfflineFilesSuspendInfo *
0x180005d55  mov     r8d, ebx; unsigned int
0x180005d58  lea     rdx, [rbp+9E0h+var_440]; unsigned __int16 **
0x180005d5f  call    ?GetSuspendItfs@@YAXPEAUIOfflineFilesCache@@QEAPEBGIQEAVCOfflineFilesSuspendInfo@@@Z; GetSuspendItfs(IOfflineFilesCache *,ushort const * * const,uint,COfflineFilesSuspendInfo * const)
0x180005d64  call    cs:__imp_RevertToSelf
0x180005d6a  mov     esi, edi
0x180005d6c  test    ebx, ebx
0x180005d6e  jz      short loc_180005DD1
0x180005d70  mov     rcx, rdi
0x180005d73  add     rcx, rcx
0x180005d76  mov     eax, [rbp+rcx*8+9E0h+var_838]
0x180005d7d  test    eax, eax
0x180005d7f  js      short loc_180005D97
0x180005d81  mov     rcx, [rbp+rcx*8+9E0h+lpString1]
0x180005d89  xor     edx, edx
0x180005d8b  mov     rax, [rcx]
0x180005d8e  mov     rax, [rax+18h]
0x180005d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d97  mov     r10, [r15]
0x180005d9a  xor     edx, edx
0x180005d9c  mov     r9, [rbp+rdi*8+9E0h+var_440]
0x180005da4  mov     rcx, r15
0x180005da7  test    eax, eax
0x180005da9  js      short loc_180005DB9
0x180005dab  mov     rax, [r10+8]
0x180005daf  mov     r8, r9
0x180005db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db7  jmp     short loc_180005DC5
0x180005db9  mov     r8d, eax
0x180005dbc  mov     rax, [r10+10h]
0x180005dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dc5  add     esi, r13d
0x180005dc8  add     rdi, r13
0x180005dcb  cmp     esi, ebx
0x180005dcd  jb      short loc_180005D70
0x180005dcf  xor     edi, edi
0x180005dd1  mov     rcx, r14; hToken
0x180005dd4  call    cs:__imp_ImpersonateLoggedOnUser
0x180005dda  test    eax, eax
0x180005ddc  jz      short loc_180005E39
0x180005dde  test    ebx, ebx
0x180005de0  jz      short loc_180005E31
0x180005de2  mov     [rsp+0AE0h+var_AA8], 0
0x180005deb  lea     r8, [rsp+0AE0h+var_A68]
0x180005df0  mov     eax, edi
0x180005df2  mov     r9d, r13d
0x180005df5  mov     dword ptr [rsp+0AE0h+var_AB0], 20h ; ' '
0x180005dfd  xor     edx, edx
0x180005dff  mov     [rsp+0AE0h+cchCount2], 0
0x180005e07  mov     dword ptr [rsp+0AE0h+lpString2], r13d
0x180005e0c  mov     rcx, [rbp+rax*8+9E0h+var_440]
0x180005e14  mov     [rsp+0AE0h+var_A68], rcx
0x180005e19  mov     rcx, [rsp+0AE0h+var_A88]
0x180005e1e  mov     rax, [rcx]
0x180005e21  mov     rax, [rax+38h]
0x180005e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2a  add     edi, r13d
0x180005e2d  cmp     edi, ebx
0x180005e2f  jb      short loc_180005DE2
0x180005e31  call    cs:__imp_RevertToSelf
0x180005e37  xor     edi, edi
0x180005e39  mov     edx, 10h; unsigned __int64
0x180005e3e  lea     r9, ??1COfflineFilesSuspendInfo@@QEAA@XZ; void (*)(void *)
0x180005e45  lea     rcx, [rbp+9E0h+lpString1]; void *
0x180005e4c  lea     r8d, [rdx+30h]; unsigned __int64
0x180005e50  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005e55  jmp     short loc_180005E5C
0x180005e57  mov     r14, [rsp+0AE0h+hToken]
0x180005e5c  xor     edx, edx; Val
0x180005e5e  lea     rcx, [rbp+9E0h+lpString1]; void *
0x180005e65  mov     r8d, 200h; Size
0x180005e6b  call    memset_0
0x180005e70  mov     [rbp+9E0h+var_A5C], edi
0x180005e73  mov     esi, edi
0x180005e75  test    r12d, r12d
0x180005e78  jz      loc_1800060B1
0x180005e7e  mov     edx, 10h; unsigned __int64
0x180005e83  lea     r9, ??0COfflineFilesSuspendInfo@@QEAA@XZ; void *(*)(void *)
0x180005e8a  lea     rcx, [rbp+9E0h+var_440]; void *
0x180005e91  lea     r8d, [rdx+30h]; unsigned __int64
0x180005e95  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180005e9a  mov     rcx, r14; hToken
0x180005e9d  call    cs:__imp_ImpersonateLoggedOnUser
0x180005ea3  test    eax, eax
0x180005ea5  jz      loc_180006020
0x180005eab  mov     r14d, edi
0x180005eae  test    r12d, r12d
0x180005eb1  jz      loc_180006002
0x180005eb7  mov     [rsp+0AE0h+hToken], rdi
0x180005ebc  lea     rcx, [rsp+0AE0h+hToken]
0x180005ec1  mov     rdi, [rsp+0AE0h+var_A88]
0x180005ec6  movzx   esi, r13b
0x180005eca  mov     rax, [rdi]
0x180005ecd  mov     rbx, [rax+50h]
0x180005ed1  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x180005ed6  mov     edx, r14d
0x180005ed9  lea     r9, [rsp+0AE0h+hToken]
0x180005ede  xor     r8d, r8d
0x180005ee1  mov     rcx, rdi
0x180005ee4  mov     rax, rbx
0x180005ee7  mov     r13, [rbp+rdx*8+9E0h+var_A40]
0x180005eec  mov     rdx, r13
0x180005eef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef4  xor     edi, edi
0x180005ef6  test    eax, eax
0x180005ef8  js      short loc_180005F67
0x180005efa  mov     rbx, [rsp+0AE0h+hToken]
0x180005eff  lea     rcx, [rsp+0AE0h+var_A70]
0x180005f04  mov     [rsp+0AE0h+var_A70], rdi
0x180005f09  mov     rax, [rbx]
0x180005f0c  mov     rdi, [rax]
0x180005f0f  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x180005f14  lea     r8, [rsp+0AE0h+var_A70]
0x180005f19  mov     rcx, rbx
0x180005f1c  lea     rdx, _GUID_5b2b0655_b3fd_497d_adeb_bd156bc8355b
0x180005f23  mov     rax, rdi
0x180005f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2b  xor     edi, edi
0x180005f2d  test    eax, eax
0x180005f2f  js      short loc_180005F5D
0x180005f31  mov     rcx, [rsp+0AE0h+var_A70]
0x180005f36  lea     r8, [rbp+9E0h+var_A60]
0x180005f3a  mov     [rsp+0AE0h+var_A90], edi
0x180005f3e  lea     rdx, [rsp+0AE0h+var_A90]
0x180005f43  mov     [rbp+9E0h+var_A60], edi
0x180005f46  mov     rax, [rcx]
0x180005f49  mov     rax, [rax+20h]
0x180005f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f52  test    eax, eax
0x180005f54  js      short loc_180005F5D
0x180005f56  cmp     [rsp+0AE0h+var_A90], edi
0x180005f5a  cmovnz  esi, edi
0x180005f5d  lea     rcx, [rsp+0AE0h+var_A70]
0x180005f62  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x180005f67  mov     rcx, [rsp+0AE0h+var_A88]
0x180005f6c  lea     r8, [rsp+0AE0h+var_A68]
0x180005f71  xor     edx, edx
0x180005f73  mov     [rsp+0AE0h+var_A68], r13
0x180005f78  mov     r9d, 1
0x180005f7e  mov     rax, [rcx]
0x180005f81  test    sil, sil
0x180005f84  jz      short loc_180005FA7
0x180005f86  mov     rax, [rax+30h]
0x180005f8a  mov     [rsp+0AE0h+var_AA8], rdi
0x180005f8f  mov     dword ptr [rsp+0AE0h+var_AB0], 21h ; '!'
0x180005f97  mov     [rsp+0AE0h+cchCount2], edi
0x180005f9b  mov     dword ptr [rsp+0AE0h+lpString2], r9d
0x180005fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa5  jmp     short loc_180005FCB
0x180005fa7  mov     rax, [rax+18h]
0x180005fab  mov     [rsp+0AE0h+var_AA0], rdi
0x180005fb0  mov     [rsp+0AE0h+var_AA8], rdi
0x180005fb5  mov     [rsp+0AE0h+var_AB0], rdi
0x180005fba  mov     [rsp+0AE0h+cchCount2], 3000002Ah
0x180005fc2  mov     dword ptr [rsp+0AE0h+lpString2], edi
0x180005fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fcb  mov     edx, eax
0x180005fcd  test    eax, eax
0x180005fcf  jns     short loc_180005FE3
0x180005fd1  mov     rax, [r15]
0x180005fd4  mov     r8, r13
0x180005fd7  mov     rcx, r15
0x180005fda  mov     rax, [rax+18h]
0x180005fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe3  lea     rcx, [rsp+0AE0h+hToken]
0x180005fe8  call    ?InternalRelease@?$ComPtr@UIOfflineFilesCache@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOfflineFilesCache>::InternalRelease(void)
0x180005fed  mov     r13d, 1
0x180005ff3  add     r14d, r13d
0x180005ff6  cmp     r14d, r12d
0x180005ff9  jb      loc_180005EB7
0x180005fff  mov     esi, [rbp+9E0h+var_A5C]
0x180006002  mov     rcx, [rsp+0AE0h+var_A88]; struct IOfflineFilesCache *
0x180006007  lea     r9, [rbp+9E0h+var_440]; struct COfflineFilesSuspendInfo *
0x18000600e  mov     r8d, r12d; unsigned int
0x180006011  lea     rdx, [rbp+9E0h+var_A40]; unsigned __int16 **
0x180006015  call    ?GetSuspendItfs@@YAXPEAUIOfflineFilesCache@@QEAPEBGIQEAVCOfflineFilesSuspendInfo@@@Z; GetSuspendItfs(IOfflineFilesCache *,ushort const * * const,uint,COfflineFilesSuspendInfo * const)
  ... truncated ...
```
