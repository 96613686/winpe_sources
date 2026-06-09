# CObjrefMoniker::GetDisplayName(IBindCtx *,IMoniker *,ushort * *)

- ea: `0x180056380`
- end: `0x180056665`
- name: `?GetDisplayName@CObjrefMoniker@@UEAAJPEAUIBindCtx@@PEAUIMoniker@@PEAPEAG@Z`
- size: `741`
- prototype: `HRESULT __fastcall(CObjrefMoniker *this, IBindCtx *pbc, IMoniker *pmkToLeft, wchar_t **lplpszDisplayName)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800077fc`
- `0x18000fc2c`
- `0x18001a630`
- `0x18004cbb8`
- `0x180056380`
- `0x180056744`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800563fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800564fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056600`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800563fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800564fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056600`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800563e3`
- `api-ms-win-core-com-l1-1-0!ProgIDFromCLSID` at `0x1800563e3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056444`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180056444`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800565be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005662c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800565be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005662c`

## pseudocode

```c
__int64 __fastcall CObjrefMoniker::GetDisplayName(
        CObjrefMoniker *this,
        IBindCtx *pbc,
        IMoniker *pmkToLeft,
        LPVOID *lplpszDisplayName)
{
  HRESULT v6; // ebx
  wchar_t *v8; // rax
  int v9; // eax
  __int64 v10; // r14
  DWORD v11; // r15d
  unsigned __int64 v12; // r14
  wchar_t *v13; // rax
  wchar_t *m_lpszDisplayName; // rcx
  int v15; // eax
  unsigned __int64 v16; // r14
  wchar_t *v17; // rax
  unsigned int v18; // [rsp+28h] [rbp-38h]
  unsigned int v19; // [rsp+28h] [rbp-38h]
  wchar_t *pszPrefix; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 cch; // [rsp+38h] [rbp-28h] BYREF
  wchar_t *pszTemp; // [rsp+40h] [rbp-20h] BYREF
  _ULARGE_INTEGER uli; // [rsp+48h] [rbp-18h] BYREF
  _ULARGE_INTEGER uliNewPos; // [rsp+50h] [rbp-10h] BYREF
  IStream *pIStream; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  if ( !lplpszDisplayName )
    return 2147942487LL;
  *lplpszDisplayName = 0;
  if ( !this->m_pUnk || pmkToLeft )
    return 2147549183LL;
  pszPrefix = 0;
  if ( !this->m_lpszDisplayName )
  {
    v6 = ProgIDFromCLSID(&CLSID_ObjrefMoniker, &pszPrefix);
    if ( v6 < 0 )
    {
      v8 = (wchar_t *)CoTaskMemAlloc(0xEu);
      pszPrefix = v8;
      if ( !v8 )
      {
        v6 = -2147024882;
        pIStream = 0;
LABEL_23:
        if ( v8 )
          CoTaskMemFree(v8);
        goto LABEL_25;
      }
      v6 = StringCchCopyW(v8, 7u, L"objref");
    }
    pIStream = 0;
    if ( v6 >= 0 )
    {
      v6 = CreateStreamOnHGlobal(0, 1, &pIStream);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(CObjrefMoniker *, IStream *, __int64))this->CPointerMoniker::CBaseMoniker::IMoniker::lpVtbl->Save)(
               this,
               pIStream,
               1);
        if ( v6 >= 0 )
        {
          v9 = safe_lstrlenW(pszPrefix);
          uli.QuadPart = 0;
          v10 = v9 + 1;
          v6 = ((__int64 (__fastcall *)(CObjrefMoniker *, _ULARGE_INTEGER *))this->CPointerMoniker::CBaseMoniker::IMoniker::lpVtbl->GetSizeMax)(
                 this,
                 &uli);
          if ( v6 >= 0 )
          {
            uliNewPos.QuadPart = 0;
            pszTemp = 0;
            v11 = 4 * ((uli.LowPart + 2) / 3) + 1;
            v6 = ((__int64 (__fastcall *)(IStream *, _QWORD, _QWORD, _ULARGE_INTEGER *))pIStream->lpVtbl->Seek)(
                   pIStream,
                   0,
                   0,
                   &uliNewPos);
            if ( v6 >= 0 )
            {
              v12 = v11 + 1LL + v10;
              cch = v12;
              v13 = (wchar_t *)CoTaskMemAlloc(2 * v12);
              this->m_lpszDisplayName = v13;
              if ( v13 )
              {
                pszTemp = v13;
                v6 = StringCchCopyExW(v13, v12, pszPrefix, &pszTemp, &cch, v18);
                if ( v6 >= 0 )
                {
                  v6 = StringCchCopyExW(pszTemp, cch, L":", &pszTemp, &cch, v19);
                  if ( v6 >= 0 )
                  {
                    v6 = IStreamToBase64(pIStream, pszTemp, cch);
                    if ( v6 >= 0 )
                      v6 = StringCchCatW(this->m_lpszDisplayName, v12, L":");
                  }
                }
              }
              else
              {
                v6 = -2147024882;
              }
            }
          }
        }
        ((void (__fastcall *)(IStream *))pIStream->lpVtbl->Release)(pIStream);
      }
    }
    v8 = pszPrefix;
    goto LABEL_23;
  }
LABEL_25:
  m_lpszDisplayName = this->m_lpszDisplayName;
  if ( m_lpszDisplayName && v6 >= 0 )
  {
    v15 = safe_lstrlenW(m_lpszDisplayName);
    if ( (unsigned __int64)v15 < 0x800 )
    {
      if ( v15 )
      {
        v16 = v15 + 1LL;
        v6 = -2147024882;
        v17 = (wchar_t *)CoTaskMemAlloc(2 * v16);
        *lplpszDisplayName = v17;
        if ( v17 )
        {
          v6 = StringCchCopyW(v17, v16, this->m_lpszDisplayName);
          if ( v6 < 0 )
          {
            CoTaskMemFree(*lplpszDisplayName);
            *lplpszDisplayName = 0;
          }
        }
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180056380  mov     [rsp-28h+arg_0], rbx
0x180056385  mov     [rsp-28h+arg_8], rsi
0x18005638a  push    rbp
0x18005638b  push    rdi
0x18005638c  push    r12
0x18005638e  push    r14
0x180056390  push    r15
0x180056392  mov     rbp, rsp
0x180056395  sub     rsp, 60h
0x180056399  xor     r12d, r12d
0x18005639c  mov     rsi, lplpszDisplayName
0x18005639f  mov     rdi, this
0x1800563a2  mov     ebx, r12d
0x1800563a5  test    lplpszDisplayName, lplpszDisplayName
0x1800563a8  jnz     short loc_1800563B4
0x1800563aa  mov     eax, 80070057h
0x1800563af  jmp     loc_18005664B
0x1800563b4  mov     [lplpszDisplayName], r12
0x1800563b7  cmp     [this+30h], r12
0x1800563bb  jz      loc_180056646
0x1800563c1  test    pmkToLeft, pmkToLeft
0x1800563c4  jnz     loc_180056646
0x1800563ca  mov     [rbp+pszPrefix], r12
0x1800563ce  cmp     [this+38h], r12
0x1800563d2  jnz     loc_1800565CA
0x1800563d8  lea     pbc, [rbp+pszPrefix]; lplpszProgID
0x1800563dc  lea     this, CLSID_ObjrefMoniker; clsid
0x1800563e3  call    cs:__imp_ProgIDFromCLSID
0x1800563ea  nop     dword ptr [rax+rax+00h]
0x1800563ef  mov     ebx, eax
0x1800563f1  test    eax, eax
0x1800563f3  jns     short loc_180056429
0x1800563f5  mov     ecx, 0Eh; cb
0x1800563fa  call    cs:__imp_CoTaskMemAlloc
0x180056401  nop     dword ptr [rax+rax+00h]
0x180056406  mov     [rbp+pszPrefix], rax
0x18005640a  test    rax, rax
0x18005640d  jz      loc_180056592
0x180056413  lea     pmkToLeft, aObjref; "objref"
0x18005641a  mov     edx, 7; cchDest
0x18005641f  mov     this, rax; pszDest
0x180056422  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056427  mov     ebx, eax
0x180056429  mov     [rbp+pIStream], r12
0x18005642d  test    ebx, ebx
0x18005642f  js      loc_1800565B2
0x180056435  mov     r14d, 1
0x18005643b  lea     pmkToLeft, [rbp+pIStream]; ppstm
0x18005643f  mov     edx, r14d; fDeleteOnRelease
0x180056442  xor     ecx, ecx; hGlobal
0x180056444  call    cs:__imp_CreateStreamOnHGlobal
0x18005644b  nop     dword ptr [rax+rax+00h]
0x180056450  mov     ebx, eax
0x180056452  test    eax, eax
0x180056454  js      loc_1800565B2
0x18005645a  mov     rax, [rdi]
0x18005645d  mov     r8d, r14d
0x180056460  mov     pbc, [rbp+pIStream]
0x180056464  mov     this, rdi
0x180056467  mov     rax, [rax+30h]
0x18005646b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056470  mov     ebx, eax
0x180056472  test    eax, eax
0x180056474  js      loc_1800565A2
0x18005647a  mov     this, [rbp+pszPrefix]; string
0x18005647e  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180056483  add     eax, r14d
0x180056486  mov     qword ptr [rbp+uli], r12
0x18005648a  movsxd  r14, eax
0x18005648d  lea     pbc, [rbp+uli]
0x180056491  mov     rax, [rdi]
0x180056494  mov     this, rdi
0x180056497  mov     rax, [rax+38h]
0x18005649b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564a0  mov     ebx, eax
0x1800564a2  test    eax, eax
0x1800564a4  js      loc_1800565A2
0x1800564aa  mov     ecx, dword ptr [rbp+uli]
0x1800564ad  lea     lplpszDisplayName, [rbp+uliNewPos]
0x1800564b1  add     ecx, 2
0x1800564b4  mov     qword ptr [rbp+uliNewPos], r12
0x1800564b8  mov     eax, 0AAAAAAABh
0x1800564bd  mov     [rbp+pszTemp], r12
0x1800564c1  mul     ecx
0x1800564c3  mov     this, [rbp+pIStream]
0x1800564c7  xor     r8d, r8d
0x1800564ca  shr     edx, 1
0x1800564cc  mov     rax, [this]
0x1800564cf  lea     r15d, ds:1[pbc*4]
0x1800564d7  mov     pbc, r12
0x1800564da  mov     rax, [rax+28h]
0x1800564de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564e3  mov     ebx, eax
0x1800564e5  test    eax, eax
0x1800564e7  js      loc_1800565A2
0x1800564ed  mov     eax, r15d
0x1800564f0  inc     rax
0x1800564f3  add     r14, rax
0x1800564f6  mov     [rbp+cch], r14
0x1800564fa  lea     this, [r14+r14]; cb
0x1800564fe  call    cs:__imp_CoTaskMemAlloc
0x180056505  nop     dword ptr [rax+rax+00h]
0x18005650a  mov     [rdi+38h], rax
0x18005650e  test    rax, rax
0x180056511  jz      loc_18005659D
0x180056517  mov     pmkToLeft, [rbp+pszPrefix]; pszSrc
0x18005651b  lea     this, [rbp+cch]
0x18005651f  mov     [rsp+60h+pcchRemaining], this; pcchRemaining
0x180056524  lea     lplpszDisplayName, [rbp+pszTemp]; ppszDestEnd
0x180056528  mov     this, rax; pszDest
0x18005652b  mov     [rbp+pszTemp], rax
0x18005652f  mov     pbc, r14; cchDest
0x180056532  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180056537  mov     ebx, eax
0x180056539  test    eax, eax
0x18005653b  js      short loc_1800565A2
0x18005653d  mov     pbc, [rbp+cch]; cchDest
0x180056541  lea     rax, [rbp+cch]
0x180056545  mov     this, [rbp+pszTemp]; pszDest
0x180056549  lea     lplpszDisplayName, [rbp+pszTemp]; ppszDestEnd
0x18005654d  lea     pmkToLeft, asc_1800EACD4; ":"
0x180056554  mov     [rsp+60h+pcchRemaining], rax; pcchRemaining
0x180056559  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18005655e  mov     ebx, eax
0x180056560  test    eax, eax
0x180056562  js      short loc_1800565A2
0x180056564  mov     pmkToLeft, [rbp+cch]; cchEncoded
0x180056568  mov     pbc, [rbp+pszTemp]; pszEncoded
0x18005656c  mov     this, [rbp+pIStream]; pStream
0x180056570  call    ?IStreamToBase64@@YAJPEAUIStream@@PEAG_K@Z; IStreamToBase64(IStream *,ushort *,unsigned __int64)
0x180056575  mov     ebx, eax
0x180056577  test    eax, eax
0x180056579  js      short loc_1800565A2
0x18005657b  mov     this, [rdi+38h]; pszDest
0x18005657f  lea     pmkToLeft, asc_1800EACD4; ":"
0x180056586  mov     pbc, r14; cchDest
0x180056589  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005658e  mov     ebx, eax
0x180056590  jmp     short loc_1800565A2
0x180056592  mov     ebx, 8007000Eh
0x180056597  mov     [rbp+pIStream], r12
0x18005659b  jmp     short loc_1800565B6
0x18005659d  mov     ebx, 8007000Eh
0x1800565a2  mov     this, [rbp+pIStream]
0x1800565a6  mov     rax, [this]
0x1800565a9  mov     rax, [rax+10h]
0x1800565ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800565b2  mov     rax, [rbp+pszPrefix]
0x1800565b6  test    rax, rax
0x1800565b9  jz      short loc_1800565CA
0x1800565bb  mov     this, rax; pv
0x1800565be  call    cs:__imp_CoTaskMemFree
0x1800565c5  nop     dword ptr [rax+rax+00h]
0x1800565ca  mov     this, [rdi+38h]; string
0x1800565ce  test    this, this
0x1800565d1  jz      short loc_180056642
0x1800565d3  test    ebx, ebx
0x1800565d5  js      short loc_180056642
0x1800565d7  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800565dc  movsxd  this, eax
0x1800565df  cmp     this, 800h
0x1800565e6  jb      short loc_1800565EF
0x1800565e8  mov     ebx, 80070057h
0x1800565ed  jmp     short loc_180056642
0x1800565ef  test    eax, eax
0x1800565f1  jz      short loc_18005663D
0x1800565f3  lea     r14, [this+1]
0x1800565f7  mov     ebx, 8007000Eh
0x1800565fc  lea     this, [r14+r14]; cb
0x180056600  call    cs:__imp_CoTaskMemAlloc
0x180056607  nop     dword ptr [rax+rax+00h]
0x18005660c  mov     [rsi], rax
0x18005660f  test    rax, rax
0x180056612  jz      short loc_180056642
0x180056614  mov     pmkToLeft, [rdi+38h]; pszSrc
0x180056618  mov     pbc, r14; cchDest
0x18005661b  mov     this, rax; pszDest
0x18005661e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056623  mov     ebx, eax
0x180056625  test    eax, eax
0x180056627  jns     short loc_180056642
0x180056629  mov     this, [rsi]; pv
0x18005662c  call    cs:__imp_CoTaskMemFree
0x180056633  nop     dword ptr [rax+rax+00h]
0x180056638  mov     [rsi], r12
0x18005663b  jmp     short loc_180056642
0x18005663d  mov     ebx, 80004005h
0x180056642  mov     eax, ebx
0x180056644  jmp     short loc_18005664B
0x180056646  mov     eax, 8000FFFFh
0x18005664b  lea     r11, [rsp+60h+var_s0]
0x180056650  mov     rbx, [r11+30h]
0x180056654  mov     rsi, [r11+38h]
0x180056658  mov     rsp, r11
0x18005665b  pop     r15
0x18005665d  pop     r14
0x18005665f  pop     r12
0x180056661  pop     rdi
0x180056662  pop     rbp
0x180056663  retn
```
