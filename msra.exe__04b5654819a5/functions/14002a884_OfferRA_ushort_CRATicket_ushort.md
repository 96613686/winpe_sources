# OfferRA(ushort *,CRATicket *,ushort *)

- ea: `0x14002a884`
- end: `0x14002ad45`
- name: `?OfferRA@@YAJPEAGPEAVCRATicket@@0@Z`
- size: `1217`
- prototype: `int(unsigned __int16 *, struct CRATicket *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400316c0`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x14002a884`
- `0x140034ce4`
- `0x140036070`
- `0x14003ff50`
- `0x1400401b4`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14002ac7e`
- `KERNEL32!HeapFree` at `0x14002ac7e`
- `KERNEL32!GetProcessHeap` at `0x14002ac68`
- `KERNEL32!GetProcessHeap` at `0x14002ac68`
- `ole32!CoTaskMemFree` at `0x14002ad14`
- `ole32!CoTaskMemFree` at `0x14002ad14`
- `ole32!MkParseDisplayName` at `0x14002ab44`
- `ole32!MkParseDisplayName` at `0x14002ab44`
- `ole32!CreateBindCtx` at `0x14002aa66`
- `ole32!CreateBindCtx` at `0x14002aa66`
- `OLEAUT32!__imp_SysAllocString` at `0x14002abf8`
- `OLEAUT32!__imp_SysAllocString` at `0x14002abf8`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac92`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ac92`

## string_xrefs

- `0x14002a98e`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002a918`: `Session:%s!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D`

## pseudocode

```c
__int64 __fastcall OfferRA(unsigned __int16 *a1, struct CRATicket *a2, unsigned __int16 *a3)
{
  OLECHAR *v6; // rdi
  HRESULT v7; // eax
  CEventLogger *v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // r9d
  _WORD *v11; // r9
  unsigned __int16 *v12; // r9
  unsigned __int16 *v13; // r14
  unsigned __int16 *v14; // rax
  CEventLogger *v15; // rcx
  HANDLE ProcessHeap; // rax
  LPBC ppbc; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  LPMONIKER ppmk; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pchEaten; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v25; // [rsp+68h] [rbp-98h] BYREF
  __int128 v26; // [rsp+78h] [rbp-88h]
  __int64 v27; // [rsp+88h] [rbp-78h]
  __int128 v28; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h]
  __int128 *v32; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v33[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v34; // [rsp+F0h] [rbp-10h]
  __int128 v35; // [rsp+100h] [rbp+0h]
  __int128 v36; // [rsp+110h] [rbp+10h]
  __int128 v37; // [rsp+120h] [rbp+20h]
  _OWORD v38[2]; // [rsp+130h] [rbp+30h]
  OLECHAR szUserName[256]; // [rsp+150h] [rbp+50h] BYREF

  ppbc = 0;
  ppmk = 0;
  v21 = 0;
  v20 = 0;
  pchEaten = 0;
  v32 = 0;
  v27 = 0;
  psz = 0;
  v30 = 0;
  v6 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v25 = 0;
  v26 = 0;
  memset_0(szUserName, 0, sizeof(szUserName));
  *(_OWORD *)v33 = *(_OWORD *)L"Session:%s!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v35 = *(_OWORD *)L":3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v34 = *(_OWORD *)L"%s!clsid:3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D";
  v37 = *(_OWORD *)L"9B9-8ADA-28E11FCCAD5D";
  lpMem = 0;
  v36 = *(_OWORD *)L"7-A468-49B9-8ADA-28E11FCCAD5D";
  v38[0] = *(_OWORD *)L"-28E11FCCAD5D";
  *(_OWORD *)((char *)v38 + 12) = *(_OWORD *)L"FCCAD5D";
  v7 = DuplicateString(a3, (unsigned __int16 **)&lpMem);
  v9 = v7;
  if ( v7 >= 0 )
  {
    v11 = lpMem;
    if ( !lpMem )
    {
      v9 = -2147467261;
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x666u,
        L"OfferRA",
        0x80004003);
      goto LABEL_39;
    }
    while ( *v11 && *v11 != 92 )
      ++v11;
    if ( *v11 != 92 )
    {
      v9 = -2147418113;
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x66Eu,
        L"OfferRA",
        0x8000FFFF);
      goto LABEL_39;
    }
    v12 = v11 + 1;
    v13 = v12;
    while ( *v12 && *v12 != 58 )
      ++v12;
    if ( *v12 != 58 )
    {
      v9 = -2147418113;
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x680u,
        L"OfferRA",
        0x8000FFFF);
      goto LABEL_39;
    }
    *v12 = 0;
    v7 = StringCchPrintfW(szUserName, 0x100u, v33, v12 + 1);
    v9 = v7;
    if ( v7 >= 0 )
    {
      v7 = CreateBindCtx(0, &ppbc);
      v9 = v7;
      if ( v7 >= 0 )
      {
        *(_QWORD *)&v29 = &v25;
        v27 = 0;
        v32 = 0;
        v30 = 0;
        v25 = 0xFFFFFFFF00000009uLL;
        v26 = 0x300000006uLL;
        *(_QWORD *)&v28 = 0;
        *((_QWORD *)&v29 + 1) = 0;
        *((_QWORD *)&v28 + 1) = a1;
        v31 = 0;
        LODWORD(v30) = 40;
        v7 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->GetBindOptions)(ppbc, &v30);
        v9 = v7;
        if ( v7 >= 0 )
        {
          v32 = &v28;
          v7 = ((__int64 (__fastcall *)(LPBC, __int128 *))ppbc->lpVtbl->SetBindOptions)(ppbc, &v30);
          v9 = v7;
          if ( v7 >= 0 )
          {
            v7 = MkParseDisplayName(ppbc, szUserName, &pchEaten, &ppmk);
            v9 = v7;
            if ( v7 >= 0 )
            {
              v7 = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, __int64 *))ppmk->lpVtbl->BindToObject)(
                     ppmk,
                     ppbc,
                     0,
                     &IID_IClassFactory,
                     &v21);
              v9 = v7;
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v21 + 24LL))(
                       v21,
                       0,
                       &IID_IRASrv,
                       &v20);
                v9 = v7;
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, OLECHAR **))(*(_QWORD *)v20 + 56LL))(v20, &psz);
                  v9 = v7;
                  if ( v7 >= 0 )
                  {
                    v14 = SysAllocString(psz);
                    v6 = v14;
                    if ( !v14 )
                    {
                      v9 = -2147024882;
                      CEventLogger::LogError(
                        v15,
                        &Recoverable_Error,
                        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
                        0x6D4u,
                        L"OfferRA",
                        0x8007000E);
                      goto LABEL_39;
                    }
                    v7 = CRATicket::put_RATicketString(a2, v14);
                    v9 = v7;
                    if ( v7 >= 0 )
                    {
                      CRATicket::put_NoviceName(*((CRATicket **)_AtlModule + 104), v13);
                      *((_DWORD *)a2 + 38) = 2;
                      goto LABEL_39;
                    }
                    v10 = 1749;
                  }
                  else
                  {
                    v10 = 1742;
                  }
                }
                else
                {
                  v10 = 1741;
                }
              }
              else
              {
                v10 = 1735;
              }
            }
            else
            {
              v10 = 1729;
            }
          }
          else
          {
            v10 = 1720;
          }
        }
        else
        {
          v10 = 1717;
        }
      }
      else
      {
        v10 = 1689;
      }
    }
    else
    {
      v10 = 1684;
    }
  }
  else
  {
    v10 = 1630;
  }
  CEventLogger::LogError(v8, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\commonfunc.cpp", v10, L"OfferRA", v7);
LABEL_39:
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  if ( v6 )
    SysFreeString(v6);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( ppmk )
  {
    ((void (__fastcall *)(LPMONIKER))ppmk->lpVtbl->Release)(ppmk);
    ppmk = 0;
  }
  if ( ppbc )
  {
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
  }
  if ( psz )
    CoTaskMemFree(psz);
  return v9;
}

```

## disassembly

```asm
0x14002a884  push    rbp
0x14002a886  push    rbx
0x14002a887  push    rdi
0x14002a888  push    r12
0x14002a88a  push    r13
0x14002a88c  push    r14
0x14002a88e  push    r15
0x14002a890  lea     rbp, [rsp-260h]
0x14002a898  sub     rsp, 360h
0x14002a89f  mov     rax, cs:__security_cookie
0x14002a8a6  xor     rax, rsp
0x14002a8a9  mov     [rbp+290h+var_40], rax
0x14002a8b0  xor     r13d, r13d
0x14002a8b3  xorps   xmm0, xmm0
0x14002a8b6  xor     eax, eax
0x14002a8b8  mov     [rsp+390h+ppbc], r13
0x14002a8bd  xorps   xmm1, xmm1
0x14002a8c0  mov     [rsp+390h+ppmk], r13
0x14002a8c5  mov     rbx, r8
0x14002a8c8  mov     [rsp+390h+var_348], r13
0x14002a8cd  mov     r15, rdx
0x14002a8d0  mov     [rsp+390h+var_350], r13
0x14002a8d5  mov     r12, rcx
0x14002a8d8  mov     [rsp+390h+pchEaten], r13d
0x14002a8dd  xor     edx, edx; Val
0x14002a8df  mov     [rbp+290h+var_2C0], rax
0x14002a8e3  mov     r8d, 200h; Size
0x14002a8e9  mov     [rbp+290h+var_308], rax
0x14002a8ed  lea     rcx, [rbp+290h+szUserName]; void *
0x14002a8f1  mov     [rsp+390h+psz], r13
0x14002a8f6  movups  [rbp+290h+var_2E0], xmm0
0x14002a8fa  mov     edi, r13d
0x14002a8fd  movups  [rbp+290h+var_2D0], xmm0
0x14002a901  movups  [rbp+290h+var_300], xmm0
0x14002a905  movups  [rbp+290h+var_2F0], xmm0
0x14002a909  movups  [rsp+390h+var_328], xmm1
0x14002a90e  movups  [rsp+390h+var_318], xmm1
0x14002a913  call    memset_0
0x14002a918  movaps  xmm0, xmmword ptr cs:aSessionSClsid3; "Session:%s!clsid:3C3A70A7-A468-49B9-8AD"...
0x14002a91f  lea     rdx, [rsp+390h+lpMem]; unsigned __int16 **
0x14002a924  movaps  xmm1, xmmword ptr cs:aSessionSClsid3+10h; "%s!clsid:3C3A70A7-A468-49B9-8ADA-28E11F"...
0x14002a92b  mov     rcx, rbx; Src
0x14002a92e  movaps  xmmword ptr [rbp+290h+var_2B0], xmm0
0x14002a932  movaps  xmm0, xmmword ptr cs:aSessionSClsid3+20h; ":3C3A70A7-A468-49B9-8ADA-28E11FCCAD5D"
0x14002a939  movaps  [rbp+290h+var_290], xmm0
0x14002a93d  movaps  xmm0, xmmword ptr cs:aSessionSClsid3+40h; "9B9-8ADA-28E11FCCAD5D"
0x14002a944  movaps  [rbp+290h+var_2A0], xmm1
0x14002a948  movaps  xmm1, xmmword ptr cs:aSessionSClsid3+30h; "7-A468-49B9-8ADA-28E11FCCAD5D"
0x14002a94f  movaps  [rbp+290h+var_270], xmm0
0x14002a953  movups  xmm0, xmmword ptr cs:aSessionSClsid3+5Ch; "FCCAD5D"
0x14002a95a  mov     [rsp+390h+lpMem], r13
0x14002a95f  movaps  [rbp+290h+var_280], xmm1
0x14002a963  movaps  xmm1, xmmword ptr cs:aSessionSClsid3+50h; "-28E11FCCAD5D"
0x14002a96a  movaps  xmmword ptr [rbp+290h+var_260], xmm1
0x14002a96e  movups  xmmword ptr [rbp+290h+var_260+0Ch], xmm0
0x14002a972  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x14002a977  mov     ebx, eax
0x14002a979  test    eax, eax
0x14002a97b  jns     short loc_14002A9AB
0x14002a97d  mov     r9d, 65Eh; unsigned int
0x14002a983  mov     [rsp+390h+var_368], eax; unsigned int
0x14002a987  lea     rax, aOfferra_0; "OfferRA"
0x14002a98e  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002a995  mov     [rsp+390h+var_370], rax; unsigned __int16 *
0x14002a99a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002a9a1  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002a9a6  jmp     loc_14002AC61
0x14002a9ab  mov     r9, [rsp+390h+lpMem]
0x14002a9b0  test    r9, r9
0x14002a9b3  jnz     short loc_14002A9D4
0x14002a9b5  mov     ebx, 80004003h
0x14002a9ba  mov     [rsp+390h+var_368], 80004003h
0x14002a9c2  mov     r9d, 666h
0x14002a9c8  jmp     short loc_14002A987
0x14002a9ca  cmp     ax, 5Ch ; '\'
0x14002a9ce  jz      short loc_14002A9DD
0x14002a9d0  add     r9, 2
0x14002a9d4  movzx   eax, word ptr [r9]
0x14002a9d8  test    ax, ax
0x14002a9db  jnz     short loc_14002A9CA
0x14002a9dd  cmp     word ptr [r9], 5Ch ; '\'
0x14002a9e2  jz      short loc_14002A9F9
0x14002a9e4  mov     ebx, 8000FFFFh
0x14002a9e9  mov     [rsp+390h+var_368], 8000FFFFh
0x14002a9f1  mov     r9d, 66Eh
0x14002a9f7  jmp     short loc_14002A987
0x14002a9f9  add     r9, 2
0x14002a9fd  mov     r14, r9
0x14002aa00  jmp     short loc_14002AA0C
0x14002aa02  cmp     ax, 3Ah ; ':'
0x14002aa06  jz      short loc_14002AA15
0x14002aa08  add     r9, 2
0x14002aa0c  movzx   eax, word ptr [r9]
0x14002aa10  test    ax, ax
0x14002aa13  jnz     short loc_14002AA02
0x14002aa15  cmp     word ptr [r9], 3Ah ; ':'
0x14002aa1a  jz      short loc_14002AA34
0x14002aa1c  mov     ebx, 8000FFFFh
0x14002aa21  mov     [rsp+390h+var_368], 8000FFFFh
0x14002aa29  mov     r9d, 680h
0x14002aa2f  jmp     loc_14002A987
0x14002aa34  mov     [r9], r13w
0x14002aa38  lea     r8, [rbp+290h+var_2B0]; unsigned __int16 *
0x14002aa3c  add     r9, 2
0x14002aa40  lea     rcx, [rbp+290h+szUserName]; unsigned __int16 *
0x14002aa44  mov     edx, 100h; unsigned __int64
0x14002aa49  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002aa4e  mov     ebx, eax
0x14002aa50  test    eax, eax
0x14002aa52  jns     short loc_14002AA5F
0x14002aa54  mov     r9d, 694h
0x14002aa5a  jmp     loc_14002A983
0x14002aa5f  lea     rdx, [rsp+390h+ppbc]; ppbc
0x14002aa64  xor     ecx, ecx; reserved
0x14002aa66  call    cs:__imp_CreateBindCtx
0x14002aa6d  nop     dword ptr [rax+rax+00h]
0x14002aa72  mov     ebx, eax
0x14002aa74  test    eax, eax
0x14002aa76  jns     short loc_14002AA83
0x14002aa78  mov     r9d, 699h
0x14002aa7e  jmp     loc_14002A983
0x14002aa83  mov     rcx, [rsp+390h+ppbc]
0x14002aa88  lea     rax, [rsp+390h+var_328]
0x14002aa8d  mov     qword ptr [rbp+290h+var_2F0], rax
0x14002aa91  lea     rdx, [rbp+290h+var_2E0]
0x14002aa95  xor     eax, eax
0x14002aa97  mov     [rbp+290h+var_308], r13
0x14002aa9b  xorps   xmm0, xmm0
0x14002aa9e  mov     [rbp+290h+var_2C0], rax
0x14002aaa2  movups  [rbp+290h+var_2E0], xmm0
0x14002aaa6  mov     dword ptr [rsp+390h+var_328], 9
0x14002aaae  mov     dword ptr [rsp+390h+var_328+4], 0FFFFFFFFh
0x14002aab6  mov     qword ptr [rsp+390h+var_328+8], r13
0x14002aabb  mov     dword ptr [rsp+390h+var_318], 6
0x14002aac3  mov     dword ptr [rsp+390h+var_318+4], 3
0x14002aacb  mov     qword ptr [rbp+290h+var_318+8], r13
0x14002aacf  mov     qword ptr [rbp+290h+var_300], r13
0x14002aad3  mov     qword ptr [rbp+290h+var_2F0+8], r13
0x14002aad7  mov     qword ptr [rbp+290h+var_300+8], r12
0x14002aadb  movups  [rbp+290h+var_2D0], xmm0
0x14002aadf  mov     dword ptr [rbp+290h+var_2E0], 28h ; '('
0x14002aae6  mov     rax, [rcx]
0x14002aae9  mov     rax, [rax+38h]
0x14002aaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aaf2  mov     ebx, eax
0x14002aaf4  test    eax, eax
0x14002aaf6  jns     short loc_14002AB03
0x14002aaf8  mov     r9d, 6B5h
0x14002aafe  jmp     loc_14002A983
0x14002ab03  mov     rcx, [rsp+390h+ppbc]
0x14002ab08  lea     rax, [rbp+290h+var_300]
0x14002ab0c  mov     [rbp+290h+var_2C0], rax
0x14002ab10  lea     rdx, [rbp+290h+var_2E0]
0x14002ab14  mov     rax, [rcx]
0x14002ab17  mov     rax, [rax+30h]
0x14002ab1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ab20  mov     ebx, eax
0x14002ab22  test    eax, eax
0x14002ab24  jns     short loc_14002AB31
0x14002ab26  mov     r9d, 6B8h
0x14002ab2c  jmp     loc_14002A983
0x14002ab31  mov     rcx, [rsp+390h+ppbc]; pbc
0x14002ab36  lea     r9, [rsp+390h+ppmk]; ppmk
0x14002ab3b  lea     r8, [rsp+390h+pchEaten]; pchEaten
0x14002ab40  lea     rdx, [rbp+290h+szUserName]; szUserName
0x14002ab44  call    cs:__imp_MkParseDisplayName
0x14002ab4b  nop     dword ptr [rax+rax+00h]
0x14002ab50  mov     ebx, eax
0x14002ab52  test    eax, eax
0x14002ab54  jns     short loc_14002AB61
0x14002ab56  mov     r9d, 6C1h
0x14002ab5c  jmp     loc_14002A983
0x14002ab61  mov     rcx, [rsp+390h+ppmk]
0x14002ab66  lea     rdx, [rsp+390h+var_348]
0x14002ab6b  mov     [rsp+390h+var_370], rdx
0x14002ab70  lea     r9, IID_IClassFactory
0x14002ab77  mov     rdx, [rsp+390h+ppbc]
0x14002ab7c  xor     r8d, r8d
0x14002ab7f  mov     rax, [rcx]
0x14002ab82  mov     rax, [rax+40h]
0x14002ab86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ab8b  mov     ebx, eax
0x14002ab8d  test    eax, eax
0x14002ab8f  jns     short loc_14002AB9C
0x14002ab91  mov     r9d, 6C7h
0x14002ab97  jmp     loc_14002A983
0x14002ab9c  mov     rcx, [rsp+390h+var_348]
0x14002aba1  lea     r9, [rsp+390h+var_350]
0x14002aba6  lea     r8, IID_IRASrv
0x14002abad  xor     edx, edx
0x14002abaf  mov     rax, [rcx]
0x14002abb2  mov     rax, [rax+18h]
0x14002abb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abbb  mov     ebx, eax
0x14002abbd  test    eax, eax
0x14002abbf  jns     short loc_14002ABCC
0x14002abc1  mov     r9d, 6CDh
0x14002abc7  jmp     loc_14002A983
0x14002abcc  mov     rcx, [rsp+390h+var_350]
0x14002abd1  lea     rdx, [rsp+390h+psz]
0x14002abd6  mov     rax, [rcx]
0x14002abd9  mov     rax, [rax+38h]
0x14002abdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002abe2  mov     ebx, eax
0x14002abe4  test    eax, eax
0x14002abe6  jns     short loc_14002ABF3
0x14002abe8  mov     r9d, 6CEh
0x14002abee  jmp     loc_14002A983
0x14002abf3  mov     rcx, [rsp+390h+psz]; psz
0x14002abf8  call    cs:__imp_SysAllocString
0x14002abff  nop     dword ptr [rax+rax+00h]
0x14002ac04  mov     rdi, rax
0x14002ac07  test    rax, rax
0x14002ac0a  jnz     short loc_14002AC24
0x14002ac0c  mov     ebx, 8007000Eh
0x14002ac11  mov     [rsp+390h+var_368], 8007000Eh
0x14002ac19  mov     r9d, 6D4h
0x14002ac1f  jmp     loc_14002A987
0x14002ac24  mov     rdx, rax; unsigned __int16 *
0x14002ac27  mov     rcx, r15; this
0x14002ac2a  call    ?put_RATicketString@CRATicket@@QEAAJPEAG@Z; CRATicket::put_RATicketString(ushort *)
0x14002ac2f  mov     ebx, eax
0x14002ac31  test    eax, eax
0x14002ac33  jns     short loc_14002AC40
0x14002ac35  mov     r9d, 6D5h
0x14002ac3b  jmp     loc_14002A983
0x14002ac40  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002ac47  mov     rdx, r14; unsigned __int16 *
0x14002ac4a  mov     rcx, [rcx+340h]; this
0x14002ac51  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14002ac56  mov     dword ptr [r15+98h], 2
0x14002ac61  cmp     [rsp+390h+lpMem], r13
0x14002ac66  jz      short loc_14002AC8A
0x14002ac68  call    cs:__imp_GetProcessHeap
0x14002ac6f  nop     dword ptr [rax+rax+00h]
0x14002ac74  mov     r8, [rsp+390h+lpMem]; lpMem
0x14002ac79  xor     edx, edx; dwFlags
0x14002ac7b  mov     rcx, rax; hHeap
0x14002ac7e  call    cs:__imp_HeapFree
0x14002ac85  nop     dword ptr [rax+rax+00h]
0x14002ac8a  test    rdi, rdi
0x14002ac8d  jz      short loc_14002AC9E
0x14002ac8f  mov     rcx, rdi; bstrString
0x14002ac92  call    cs:__imp_SysFreeString
0x14002ac99  nop     dword ptr [rax+rax+00h]
0x14002ac9e  mov     rcx, [rsp+390h+var_350]
0x14002aca3  test    rcx, rcx
0x14002aca6  jz      short loc_14002ACB9
0x14002aca8  mov     rax, [rcx]
0x14002acab  mov     rax, [rax+10h]
0x14002acaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002acb4  mov     [rsp+390h+var_350], r13
0x14002acb9  mov     rcx, [rsp+390h+var_348]
0x14002acbe  test    rcx, rcx
0x14002acc1  jz      short loc_14002ACD4
0x14002acc3  mov     rax, [rcx]
0x14002acc6  mov     rax, [rax+10h]
0x14002acca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002accf  mov     [rsp+390h+var_348], r13
0x14002acd4  mov     rcx, [rsp+390h+ppmk]
0x14002acd9  test    rcx, rcx
0x14002acdc  jz      short loc_14002ACEF
0x14002acde  mov     rax, [rcx]
0x14002ace1  mov     rax, [rax+10h]
0x14002ace5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002acea  mov     [rsp+390h+ppmk], r13
0x14002acef  mov     rcx, [rsp+390h+ppbc]
0x14002acf4  test    rcx, rcx
0x14002acf7  jz      short loc_14002AD0A
0x14002acf9  mov     rax, [rcx]
0x14002acfc  mov     rax, [rax+10h]
0x14002ad00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ad05  mov     [rsp+390h+ppbc], r13
0x14002ad0a  mov     rcx, [rsp+390h+psz]; pv
0x14002ad0f  test    rcx, rcx
0x14002ad12  jz      short loc_14002AD20
0x14002ad14  call    cs:__imp_CoTaskMemFree
0x14002ad1b  nop     dword ptr [rax+rax+00h]
0x14002ad20  mov     eax, ebx
0x14002ad22  mov     rcx, [rbp+290h+var_40]
0x14002ad29  xor     rcx, rsp; StackCookie
0x14002ad2c  call    __security_check_cookie
0x14002ad31  add     rsp, 360h
0x14002ad38  pop     r15
0x14002ad3a  pop     r14
0x14002ad3c  pop     r13
0x14002ad3e  pop     r12
0x14002ad40  pop     rdi
0x14002ad41  pop     rbx
0x14002ad42  pop     rbp
0x14002ad43  retn
```
