# CTravelEntry::_VerifySchemeAndDomainAreSame(IUnknown *,CTravelEntry *,CTravelEntry *,int,int *,IUri * *)

- ea: `0x1810744c8`
- end: `0x1810748c2`
- name: `?_VerifySchemeAndDomainAreSame@CTravelEntry@@IEAAJPEAUIUnknown@@PEAV1@1HPEAHPEAPEAUIUri@@@Z`
- size: `1018`
- prototype: `__int64 __fastcall(CTravelEntry *__hidden this, struct IUnknown *, struct CTravelEntry *, struct CTravelEntry *, int, int *, struct IUri **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x181073fc8`

## callees

- `0x18040ac58`
- `0x1810744c8`
- `0x181094ae4`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1810747ec`
- `KERNEL32!GlobalFree` at `0x1810747ec`
- `iertutil!CreateUri` at `0x18107474c`
- `iertutil!CreateUri` at `0x18107474c`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1810747d7`
- `api-ms-win-downlevel-ole32-l1-1-0!GetHGlobalFromStream` at `0x1810747d7`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1810746bb`
- `api-ms-win-downlevel-ole32-l1-1-0!CreateStreamOnHGlobal` at `0x1810746bb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18107479b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810747ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810747bc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18107479b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810747ac`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1810747bc`
- `SHELL32!__imp_ILFree` at `0x18107478a`
- `SHELL32!__imp_ILFree` at `0x18107478a`
- `urlmon!CoInternetCombineUrlEx` at `0x181074559`
- `urlmon!CoInternetCombineUrlEx` at `0x1810745a0`
- `urlmon!CoInternetCombineUrlEx` at `0x181074777`
- `urlmon!CoInternetCombineUrlEx` at `0x181074559`
- `urlmon!CoInternetCombineUrlEx` at `0x1810745a0`
- `urlmon!CoInternetCombineUrlEx` at `0x181074777`

## pseudocode

```c
__int64 __fastcall CTravelEntry::_VerifySchemeAndDomainAreSame(
        CTravelEntry *this,
        struct IUnknown *a2,
        struct CTravelEntry *a3,
        IUri **a4,
        int a5,
        int *a6,
        struct IUri **a7)
{
  IUri *v10; // rcx
  HRESULT v11; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  __int64 v15; // [rsp+38h] [rbp-D0h] BYREF
  LPSTREAM ppstm; // [rsp+40h] [rbp-C8h] BYREF
  HGLOBAL phglobal; // [rsp+48h] [rbp-C0h] BYREF
  IUri *ppURI; // [rsp+50h] [rbp-B8h] BYREF
  IUri *v19; // [rsp+58h] [rbp-B0h] BYREF
  IUri *ppCombinedUri; // [rsp+60h] [rbp-A8h] BYREF
  IUri *ppCombinedUri_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int128 pidl_8; // [rsp+78h] [rbp-90h]
  LPVOID pv; // [rsp+88h] [rbp-80h]
  WCHAR pwzURI[2088]; // [rsp+98h] [rbp-70h] BYREF

  *a6 = 0;
  v10 = (IUri *)*((_QWORD *)a3 + 7);
  ppCombinedUri = 0;
  v11 = CoInternetCombineUrlEx(v10, L"/", 0, &ppCombinedUri, 0);
  if ( v11 < 0 )
    return (unsigned int)v11;
  ppURI = 0;
  v19 = 0;
  if ( ((a5 + 1) & 0xFFFFFFFD) != 0 )
  {
    v11 = CoInternetCombineUrlEx(a4[7], L"/", 0, &v19, 0);
LABEL_25:
    if ( v11 >= 0 )
    {
      LODWORD(v15) = 0;
      if ( ((int (__fastcall *)(IUri *, IUri *, __int64 *))ppCombinedUri->lpVtbl->IsEqual)(ppCombinedUri, v19, &v15) >= 0 )
      {
        *a6 = v15;
        *a7 = ppURI;
        ppURI = 0;
      }
    }
    goto LABEL_28;
  }
  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
          a2,
          &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
          &v15);
  if ( v11 >= 0 )
  {
    v13 = *((unsigned int *)this + 18);
    if ( (_DWORD)v13 == -1 )
      goto LABEL_11;
    ppstm = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, LPSTREAM *))(*(_QWORD *)v15 + 24LL))(v15, v13, &ppstm);
    if ( v11 >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v15 = 0;
      v11 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, __int64 *))ppstm)(
              ppstm,
              &GUID_241c033e_e659_43da_aa4d_4086dbc4758d,
              &v15);
      if ( v11 >= 0 )
      {
        phglobal = 0;
        v11 = (**(__int64 (__fastcall ***)(LPSTREAM, GUID *, HGLOBAL *))ppstm)(
                ppstm,
                &GUID_cef3b021_5ab5_465e_9d62_0e97a2e30d3b,
                &phglobal);
        if ( v11 >= 0 )
        {
          v11 = (*(__int64 (__fastcall **)(HGLOBAL, __int64))(*(_QWORD *)phglobal + 24LL))(phglobal, 0xFFFFFFFFLL);
          (*(void (__fastcall **)(HGLOBAL))(*(_QWORD *)phglobal + 16LL))(phglobal);
        }
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      if ( v11 >= 0 )
      {
LABEL_11:
        ppstm = 0;
        v11 = CreateStreamOnHGlobal(0, 0, &ppstm);
        if ( v11 >= 0 )
        {
          pv = 0;
          *(_OWORD *)ppCombinedUri_8 = 0;
          pidl_8 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, LPSTREAM, IUri **))(*(_QWORD *)v15 + 32LL))(
                  v15,
                  ppstm,
                  ppCombinedUri_8);
          if ( v11 >= 0 )
          {
            pwzURI[0] = 0;
            if ( ppCombinedUri_8[1] )
            {
              IEGetNameAndFlagsEx((struct _ITEMIDLIST_RELATIVE *)ppCombinedUri_8[1]);
            }
            else if ( (_QWORD)pidl_8 )
            {
              StringCchCopyW(pwzURI, 0x824u, (unsigned __int16 *)pidl_8);
            }
            v11 = CreateUri(pwzURI, 0x3002B84u, 0, &ppURI);
            if ( v11 >= 0 )
              v11 = CoInternetCombineUrlEx(ppURI, L"/", 0, &v19, 0);
            ILFree((LPITEMIDLIST)ppCombinedUri_8[1]);
            CoTaskMemFree((LPVOID)pidl_8);
            CoTaskMemFree(*((LPVOID *)&pidl_8 + 1));
            CoTaskMemFree(pv);
          }
          phglobal = 0;
          if ( GetHGlobalFromStream(ppstm, &phglobal) >= 0 )
            GlobalFree(phglobal);
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
        }
      }
    }
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    goto LABEL_25;
  }
LABEL_28:
  ((void (__fastcall *)(IUri *))ppCombinedUri->lpVtbl->Release)(ppCombinedUri);
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  if ( v19 )
    ((void (__fastcall *)(IUri *))v19->lpVtbl->Release)(v19);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1810744c8  mov     rax, rsp
0x1810744cb  mov     [rax+20h], r9
0x1810744cf  mov     [rax+18h], r8
0x1810744d3  mov     [rax+10h], rdx
0x1810744d7  mov     [rax+8], rcx
0x1810744db  push    rbp
0x1810744dc  push    rbx
0x1810744dd  push    rsi
0x1810744de  push    rdi
0x1810744df  push    r12
0x1810744e1  push    r13
0x1810744e3  push    r14
0x1810744e5  push    r15
0x1810744e7  lea     rbp, [rax-1038h]
0x1810744ee  mov     eax, 10F8h
0x1810744f3  call    _alloca_probe
0x1810744f8  sub     rsp, rax
0x1810744fb  mov     rax, cs:__security_cookie
0x181074502  xor     rax, rsp
0x181074505  mov     [rbp+1030h+var_50], rax
0x18107450c  mov     r15, [rbp+1030h+arg_28]
0x181074513  lea     r9, [rsp+1130h+ppCombinedUri]; ppCombinedUri
0x181074518  mov     rcx, [rbp+1030h+arg_10]
0x18107451f  lea     rdx, asc_181401D08; "/"
0x181074526  mov     rsi, [rbp+1030h+arg_0]
0x18107452d  xor     r13d, r13d
0x181074530  mov     rdi, [rbp+1030h+arg_8]
0x181074537  xor     r8d, r8d; dwCombineFlags
0x18107453a  mov     r14, [rbp+1030h+arg_18]
0x181074541  mov     r12, [rbp+1030h+arg_30]
0x181074548  mov     [r15], r13d
0x18107454b  mov     rcx, [rcx+38h]; pBaseUri
0x18107454f  mov     [rsp+1130h+ppCombinedUri], r13
0x181074554  mov     [rsp+20h], r13; dwReserved
0x181074559  call    cs:__imp_CoInternetCombineUrlEx
0x181074560  nop     dword ptr [rax+rax+00h]
0x181074565  mov     ebx, eax
0x181074567  test    eax, eax
0x181074569  js      loc_18107489C
0x18107456f  mov     eax, [rbp+1030h+arg_20]
0x181074575  inc     eax
0x181074577  mov     [rsp+1130h+ppURI], r13
0x18107457c  mov     [rsp+1130h+var_10E0], r13
0x181074581  test    eax, 0FFFFFFFDh
0x181074586  jz      short loc_1810745B3
0x181074588  mov     rcx, [r14+38h]; pBaseUri
0x18107458c  lea     r9, [rsp+1130h+var_10E0]; ppCombinedUri
0x181074591  xor     r8d, r8d; dwCombineFlags
0x181074594  mov     [rsp+20h], r13; dwReserved
0x181074599  lea     rdx, asc_181401D08; "/"
0x1810745a0  call    cs:__imp_CoInternetCombineUrlEx
0x1810745a7  nop     dword ptr [rax+rax+00h]
0x1810745ac  mov     ebx, eax
0x1810745ae  jmp     loc_18107481F
0x1810745b3  mov     rax, [rdi]
0x1810745b6  lea     r8, [rsp+1130h+var_1100]
0x1810745bb  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x1810745c2  mov     [rsp+1130h+var_1100], r13
0x1810745c7  mov     rcx, rdi
0x1810745ca  mov     rax, [rax]
0x1810745cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810745d2  mov     ebx, eax
0x1810745d4  test    eax, eax
0x1810745d6  js      loc_18107485F
0x1810745dc  mov     edx, [rsi+48h]
0x1810745df  or      edi, 0FFFFFFFFh
0x1810745e2  cmp     edx, edi
0x1810745e4  jz      loc_1810746AD
0x1810745ea  mov     rcx, [rsp+1130h+var_1100]
0x1810745ef  lea     r8, [rsp+1130h+ppstm]
0x1810745f4  mov     [rsp+1130h+ppstm], r13
0x1810745f9  mov     rax, [rcx]
0x1810745fc  mov     rax, [rax+18h]
0x181074600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074605  mov     ebx, eax
0x181074607  test    eax, eax
0x181074609  js      loc_181074809
0x18107460f  mov     rcx, [rsp+1130h+var_1100]
0x181074614  mov     rax, [rcx]
0x181074617  mov     rax, [rax+10h]
0x18107461b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074620  mov     rcx, [rsp+1130h+ppstm]
0x181074625  lea     r8, [rsp+1130h+var_1100]
0x18107462a  mov     [rsp+1130h+var_1100], r13
0x18107462f  lea     rdx, _GUID_241c033e_e659_43da_aa4d_4086dbc4758d
0x181074636  mov     rax, [rcx]
0x181074639  mov     rax, [rax]
0x18107463c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074641  mov     ebx, eax
0x181074643  test    eax, eax
0x181074645  js      short loc_181074694
0x181074647  mov     rcx, [rsp+1130h+ppstm]
0x18107464c  lea     r8, [rsp+1130h+phglobal]
0x181074651  mov     [rsp+1130h+phglobal], r13
0x181074656  lea     rdx, _GUID_cef3b021_5ab5_465e_9d62_0e97a2e30d3b
0x18107465d  mov     rax, [rcx]
0x181074660  mov     rax, [rax]
0x181074663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074668  mov     ebx, eax
0x18107466a  test    eax, eax
0x18107466c  js      short loc_181074694
0x18107466e  mov     rcx, [rsp+1130h+phglobal]
0x181074673  mov     edx, edi
0x181074675  mov     rax, [rcx]
0x181074678  mov     rax, [rax+18h]
0x18107467c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074681  mov     rcx, [rsp+1130h+phglobal]
0x181074686  mov     ebx, eax
0x181074688  mov     rax, [rcx]
0x18107468b  mov     rax, [rax+10h]
0x18107468f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074694  mov     rcx, [rsp+1130h+ppstm]
0x181074699  mov     rax, [rcx]
0x18107469c  mov     rax, [rax+10h]
0x1810746a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810746a5  test    ebx, ebx
0x1810746a7  js      loc_181074809
0x1810746ad  lea     r8, [rsp+1130h+ppstm]; ppstm
0x1810746b2  mov     [rsp+1130h+ppstm], r13
0x1810746b7  xor     edx, edx; fDeleteOnRelease
0x1810746b9  xor     ecx, ecx; hGlobal
0x1810746bb  call    cs:__imp_CreateStreamOnHGlobal
0x1810746c2  nop     dword ptr [rax+rax+00h]
0x1810746c7  mov     ebx, eax
0x1810746c9  test    eax, eax
0x1810746cb  js      loc_181074809
0x1810746d1  mov     rcx, [rsp+1130h+var_1100]
0x1810746d6  lea     r8, [rsp+1130h+ppCombinedUri+8]
0x1810746db  mov     rdx, [rsp+1130h+ppstm]
0x1810746e0  xor     eax, eax
0x1810746e2  xorps   xmm0, xmm0
0x1810746e5  mov     [rbp+1030h+pv], rax
0x1810746e9  movups  xmmword ptr [rsp+1130h+ppCombinedUri+8], xmm0
0x1810746ee  movups  xmmword ptr [rsp+1130h+pidl+8], xmm0
0x1810746f3  mov     rax, [rcx]
0x1810746f6  mov     rax, [rax+20h]
0x1810746fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1810746ff  mov     ebx, eax
0x181074701  test    eax, eax
0x181074703  js      loc_1810747C8
0x181074709  mov     rcx, qword ptr [rsp+1130h+pidl]; struct _ITEMIDLIST_RELATIVE *
0x18107470e  mov     [rbp+1030h+pwzURI], r13w
0x181074713  test    rcx, rcx
0x181074716  jz      short loc_181074723
0x181074718  lea     r9, [rbp+1030h+pwzURI]
0x18107471c  call    IEGetNameAndFlagsEx
0x181074721  jmp     short loc_18107473B
0x181074723  mov     r8, qword ptr [rsp+1130h+pidl+8]; unsigned __int16 *
0x181074728  test    r8, r8
0x18107472b  jz      short loc_18107473B
0x18107472d  mov     edx, 824h; unsigned __int64
0x181074732  lea     rcx, [rbp+1030h+pwzURI]; unsigned __int16 *
0x181074736  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18107473b  lea     r9, [rsp+1130h+ppURI]; ppURI
0x181074740  xor     r8d, r8d; dwReserved
0x181074743  mov     edx, 3002B84h; dwFlags
0x181074748  lea     rcx, [rbp+1030h+pwzURI]; pwzURI
0x18107474c  call    cs:__imp_CreateUri
0x181074753  nop     dword ptr [rax+rax+00h]
0x181074758  mov     ebx, eax
0x18107475a  test    eax, eax
0x18107475c  js      short loc_181074785
0x18107475e  mov     rcx, [rsp+1130h+ppURI]; pBaseUri
0x181074763  lea     r9, [rsp+1130h+var_10E0]; ppCombinedUri
0x181074768  xor     r8d, r8d; dwCombineFlags
0x18107476b  mov     [rsp+20h], r13; dwReserved
0x181074770  lea     rdx, asc_181401D08; "/"
0x181074777  call    cs:__imp_CoInternetCombineUrlEx
0x18107477e  nop     dword ptr [rax+rax+00h]
0x181074783  mov     ebx, eax
0x181074785  mov     rcx, qword ptr [rsp+1130h+pidl]; pidl
0x18107478a  call    cs:__imp_ILFree
0x181074791  nop     dword ptr [rax+rax+00h]
0x181074796  mov     rcx, qword ptr [rsp+1130h+pidl+8]; pv
0x18107479b  call    cs:__imp_CoTaskMemFree
0x1810747a2  nop     dword ptr [rax+rax+00h]
0x1810747a7  mov     rcx, qword ptr [rsp+1130h+pidl+10h]; pv
0x1810747ac  call    cs:__imp_CoTaskMemFree
0x1810747b3  nop     dword ptr [rax+rax+00h]
0x1810747b8  mov     rcx, [rbp+1030h+pv]; pv
0x1810747bc  call    cs:__imp_CoTaskMemFree
0x1810747c3  nop     dword ptr [rax+rax+00h]
0x1810747c8  mov     rcx, [rsp+1130h+ppstm]; pstm
0x1810747cd  lea     rdx, [rsp+1130h+phglobal]; phglobal
0x1810747d2  mov     [rsp+1130h+phglobal], r13
0x1810747d7  call    cs:__imp_GetHGlobalFromStream
0x1810747de  nop     dword ptr [rax+rax+00h]
0x1810747e3  test    eax, eax
0x1810747e5  js      short loc_1810747F8
0x1810747e7  mov     rcx, [rsp+1130h+phglobal]; hMem
0x1810747ec  call    cs:__imp_GlobalFree
0x1810747f3  nop     dword ptr [rax+rax+00h]
0x1810747f8  mov     rcx, [rsp+1130h+ppstm]
0x1810747fd  mov     rax, [rcx]
0x181074800  mov     rax, [rax+10h]
0x181074804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074809  mov     rcx, [rsp+1130h+var_1100]
0x18107480e  test    rcx, rcx
0x181074811  jz      short loc_18107481F
0x181074813  mov     rax, [rcx]
0x181074816  mov     rax, [rax+10h]
0x18107481a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18107481f  test    ebx, ebx
0x181074821  js      short loc_18107485F
0x181074823  mov     rcx, [rsp+1130h+ppCombinedUri]
0x181074828  lea     r8, [rsp+1130h+var_1100]
0x18107482d  mov     rdx, [rsp+1130h+var_10E0]
0x181074832  mov     dword ptr [rsp+1130h+var_1100], r13d
0x181074837  mov     rax, [rcx]
0x18107483a  mov     rax, [rax+0D8h]
0x181074841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074846  test    eax, eax
0x181074848  js      short loc_18107485F
0x18107484a  mov     eax, dword ptr [rsp+1130h+var_1100]
0x18107484e  mov     [r15], eax
0x181074851  mov     rax, [rsp+1130h+ppURI]
0x181074856  mov     [r12], rax
0x18107485a  mov     [rsp+1130h+ppURI], r13
0x18107485f  mov     rcx, [rsp+1130h+ppCombinedUri]
0x181074864  mov     rax, [rcx]
0x181074867  mov     rax, [rax+10h]
0x18107486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074870  mov     rcx, [rsp+1130h+ppURI]
0x181074875  test    rcx, rcx
0x181074878  jz      short loc_181074886
0x18107487a  mov     rax, [rcx]
0x18107487d  mov     rax, [rax+10h]
0x181074881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x181074886  mov     rcx, [rsp+1130h+var_10E0]
0x18107488b  test    rcx, rcx
0x18107488e  jz      short loc_18107489C
0x181074890  mov     rax, [rcx]
0x181074893  mov     rax, [rax+10h]
0x181074897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18107489c  mov     eax, ebx
0x18107489e  mov     rcx, [rbp+1030h+var_50]
0x1810748a5  xor     rcx, rsp; StackCookie
0x1810748a8  call    __security_check_cookie
0x1810748ad  add     rsp, 10F8h
0x1810748b4  pop     r15
0x1810748b6  pop     r14
0x1810748b8  pop     r13
0x1810748ba  pop     r12
0x1810748bc  pop     rdi
0x1810748bd  pop     rsi
0x1810748be  pop     rbx
0x1810748bf  pop     rbp
0x1810748c0  retn
```
