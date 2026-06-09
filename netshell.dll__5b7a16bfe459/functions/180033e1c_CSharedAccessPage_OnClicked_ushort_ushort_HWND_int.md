# CSharedAccessPage::OnClicked(ushort,ushort,HWND__ *,int &)

- ea: `0x180033e1c`
- end: `0x180033fce`
- name: `?OnClicked@CSharedAccessPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `434`
- prototype: `__int64 __fastcall(CSharedAccessPage *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800340f0`

## callees

- `0x180009930`
- `0x18001644c`
- `0x18001eb7c`
- `0x180033e1c`
- `0x180060c00`
- `0x180065010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033ef1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180033ef1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033ed5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180033ed5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033f95`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180033f95`

## string_xrefs

- `0x180033ece`: `hnetcfg.dll`
- `0x180033ee7`: `HNetGetSharingServicesPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSharedAccessPage::OnClicked(CSharedAccessPage *this, __int64 a2, __int16 a3, __int64 a4, int *a5)
{
  NETCON_MEDIATYPE MediaType; // ebx
  int v7; // eax
  __int64 v8; // rbx
  HMODULE Library; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // r14
  NETCON_PROPERTIES *pProps; // [rsp+28h] [rbp-A1h] BYREF
  PROPSHEETHEADERW_V2 v14; // [rsp+38h] [rbp-91h] BYREF
  _DWORD v15[12]; // [rsp+98h] [rbp-31h] BYREF
  __int64 v16; // [rsp+C8h] [rbp-1h]
  __int64 v17; // [rsp+140h] [rbp+77h] BYREF

  v17 = a4;
  if ( a3 == 15030
    && (pProps = 0,
        (*(int (__fastcall **)(_QWORD, NETCON_PROPERTIES **))(**((_QWORD **)this + 2) + 56LL))(
          *((_QWORD *)this + 2),
          &pProps) >= 0)
    && (MediaType = pProps->MediaType, NcFreeNetconProperties(pProps), (unsigned int)(MediaType - 8) <= 1) )
  {
    v17 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 3) + 32LL))(
           *((_QWORD *)this + 3),
           (unsigned int)(MediaType != NCM_SHAREDACCESSHOST_LAN) + 2,
           &v17);
    v8 = 0;
    if ( v17 )
    {
      if ( v7 >= 0 )
      {
        Library = LoadLibraryExW(L"hnetcfg.dll", 0, 0x800u);
        v10 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "HNetGetSharingServicesPage");
          if ( ProcAddress )
          {
            memset_0(v15, 0, 0x68u);
            v15[0] = 104;
            v16 = *((_QWORD *)this + 1);
            v8 = 0;
            if ( ((int (__fastcall *)(__int64, _DWORD *))ProcAddress)(v17, v15) >= 0 )
            {
              memset_0(&v14, 0, sizeof(v14));
              v14.dwSize = 72;
              v14.dwFlags = 33554568;
              v14.hwndParent = (HWND)*((_QWORD *)this + 1);
              v14.pszCaption = (LPCWSTR)16123;
              v14.hInstance = hInst;
              v14.nPages = 1;
              v14.ppsp = (LPCPROPSHEETPAGEW)v15;
              PropertySheetW(&v14);
              v8 = 1;
            }
          }
          FreeLibrary(v10);
        }
      }
    }
    ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(&v17);
    return v8;
  }
  else
  {
    *a5 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180033e1c  mov     rax, rsp
0x180033e1f  mov     [rax+8], rbx
0x180033e23  mov     [rax+10h], rsi
0x180033e27  mov     [rax+20h], r9
0x180033e2b  push    rbp
0x180033e2c  push    rdi
0x180033e2d  push    r14
0x180033e2f  lea     rbp, [rax-57h]
0x180033e33  sub     rsp, 100h
0x180033e3a  mov     rsi, rcx
0x180033e3d  mov     eax, 3AB6h
0x180033e42  cmp     r8w, ax
0x180033e46  jnz     loc_180033FAA
0x180033e4c  mov     [rsp+110h+pProps], 0
0x180033e55  mov     rcx, [rcx+10h]
0x180033e59  mov     rax, [rcx]
0x180033e5c  lea     rdx, [rsp+110h+pProps]
0x180033e61  mov     rax, [rax+38h]
0x180033e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e6a  test    eax, eax
0x180033e6c  js      loc_180033FAA
0x180033e72  mov     rcx, [rsp+110h+pProps]; pProps
0x180033e77  mov     ebx, [rcx+24h]
0x180033e7a  call    NcFreeNetconProperties
0x180033e7f  lea     eax, [rbx-8]
0x180033e82  cmp     eax, 1
0x180033e85  ja      loc_180033FAA
0x180033e8b  mov     [rbp+4Fh+arg_18], 0
0x180033e93  mov     rcx, [rsi+18h]
0x180033e97  mov     rax, [rcx]
0x180033e9a  xor     edx, edx
0x180033e9c  cmp     ebx, 8
0x180033e9f  setnz   dl
0x180033ea2  add     edx, 2
0x180033ea5  lea     r8, [rbp+4Fh+arg_18]
0x180033ea9  mov     rax, [rax+20h]
0x180033ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033eb2  xor     ebx, ebx
0x180033eb4  cmp     [rbp+4Fh+arg_18], rbx
0x180033eb8  jz      loc_180033F9C
0x180033ebe  test    eax, eax
0x180033ec0  js      loc_180033F9C
0x180033ec6  xor     edx, edx; hFile
0x180033ec8  mov     r8d, 800h; dwFlags
0x180033ece  lea     rcx, aHnetcfgDll; "hnetcfg.dll"
0x180033ed5  call    cs:__imp_LoadLibraryExW
0x180033edb  mov     rdi, rax
0x180033ede  test    rax, rax
0x180033ee1  jz      loc_180033F9C
0x180033ee7  lea     rdx, aHnetgetsharing; "HNetGetSharingServicesPage"
0x180033eee  mov     rcx, rax; hModule
0x180033ef1  call    cs:__imp_GetProcAddress
0x180033ef7  mov     r14, rax
0x180033efa  test    rax, rax
0x180033efd  jz      loc_180033F92
0x180033f03  mov     ebx, 68h ; 'h'
0x180033f08  mov     r8d, ebx; Size
0x180033f0b  xor     edx, edx; Val
0x180033f0d  lea     rcx, [rbp+4Fh+var_80]; void *
0x180033f11  call    memset_0
0x180033f16  mov     [rbp+4Fh+var_80], ebx
0x180033f19  mov     rcx, [rsi+8]
0x180033f1d  mov     [rbp+4Fh+var_50], rcx
0x180033f21  lea     rdx, [rbp+4Fh+var_80]
0x180033f25  mov     rcx, [rbp+4Fh+arg_18]
0x180033f29  mov     rax, r14
0x180033f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f31  xor     ebx, ebx
0x180033f33  test    eax, eax
0x180033f35  js      short loc_180033F92
0x180033f37  xor     edx, edx; Val
0x180033f39  lea     r8d, [rbx+60h]; Size
0x180033f3d  lea     rcx, [rsp+110h+var_E0]; void *
0x180033f42  call    memset_0
0x180033f47  mov     [rsp+110h+var_E0.dwSize], 48h ; 'H'
0x180033f4f  mov     [rsp+110h+var_E0.dwFlags], 2000088h
0x180033f57  mov     rax, [rsi+8]
0x180033f5b  mov     [rsp+110h+var_E0.hwndParent], rax
0x180033f60  mov     [rbp+4Fh+var_E0.pszCaption], 3EFBh
0x180033f68  mov     rax, cs:hInst
0x180033f6f  mov     [rsp+110h+var_E0.hInstance], rax
0x180033f74  mov     [rbp+4Fh+var_E0.nPages], 1
0x180033f7b  lea     rax, [rbp+4Fh+var_80]
0x180033f7f  mov     qword ptr [rbp+4Fh+var_E0.38h], rax
0x180033f83  lea     rcx, [rsp+110h+var_E0]; LPCPROPSHEETHEADERW
0x180033f88  call    PropertySheetW
0x180033f8d  mov     ebx, 1
0x180033f92  mov     rcx, rdi; hLibModule
0x180033f95  call    cs:__imp_FreeLibrary
0x180033f9b  nop
0x180033f9c  lea     rcx, [rbp+4Fh+arg_18]
0x180033fa0  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180033fa5  mov     rax, rbx
0x180033fa8  jmp     short loc_180033FB6
0x180033faa  mov     rax, [rbp+4Fh+arg_20]
0x180033fae  mov     dword ptr [rax], 0
0x180033fb4  xor     eax, eax
0x180033fb6  lea     r11, [rsp+110h+var_10]
0x180033fbe  mov     rbx, [r11+20h]
0x180033fc2  mov     rsi, [r11+28h]
0x180033fc6  mov     rsp, r11
0x180033fc9  pop     r14
0x180033fcb  pop     rdi
0x180033fcc  pop     rbp
0x180033fcd  retn
```
