# BATCHCTX::ProcessFedAuthInfo(void *,ulong)

- ea: `0x100453f4c`
- end: `0x100454ab6`
- name: `?ProcessFedAuthInfo@BATCHCTX@@AEAAJPEAXK@Z`
- size: `2922`
- prototype: `__int64 __fastcall(BATCHCTX *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x100457010`

## callees

- `0x1004385b0`
- `0x100446aac`
- `0x10044dca4`
- `0x100453f4c`
- `0x100463e78`
- `0x100465518`
- `0x100486308`
- `0x100487d50`
- `0x100546a24`
- `0x100546aa8`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!Sleep` at `0x1004545e3`
- `KERNEL32!Sleep` at `0x1004545e3`
- `KERNEL32!GetLastError` at `0x100454472`
- `KERNEL32!GetLastError` at `0x1004544d7`
- `KERNEL32!GetLastError` at `0x100454472`
- `KERNEL32!GetLastError` at `0x1004544d7`
- `KERNEL32!GetTickCount` at `0x1004544fd`
- `KERNEL32!GetTickCount` at `0x1004545d2`
- `KERNEL32!GetTickCount` at `0x1004544fd`
- `KERNEL32!GetTickCount` at `0x1004545d2`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100454430`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100454430`

## string_xrefs

- `0x10045483b`: `ActiveDirectoryIntegrated`
- `0x10045484e`: `ActiveDirectoryPassword`
- `0x10045485c`: `ActiveDirectoryMSI`
- `0x100454834`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall BATCHCTX::ProcessFedAuthInfo(BATCHCTX *this, void *a2, unsigned int a3)
{
  unsigned int v6; // r12d
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
  int Bytes; // eax
  unsigned int v11; // esi
  unsigned int v12; // esi
  int v13; // r10d
  unsigned int v14; // ecx
  unsigned int v15; // r8d
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned __int16 **v21; // r9
  unsigned int v22; // esi
  unsigned __int16 **v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  unsigned int v26; // esi
  unsigned int v27; // esi
  bool v28; // zf
  unsigned int v29; // eax
  __int64 v30; // r8
  char v31; // cl
  DWORD LastError; // eax
  CTdsParser *v33; // rdi
  DWORD TickCount; // r13d
  DWORD i; // r12d
  char v36; // dl
  unsigned int v37; // eax
  __int64 v38; // rcx
  int v39; // r12d
  __int64 v40; // r9
  unsigned int v41; // edx
  int AccessTokenW; // r13d
  const wchar_t *v43; // rdx
  unsigned int v44; // edx
  int v45; // eax
  __int64 v46; // r9
  __int64 v47; // rdx
  unsigned __int16 *v49; // [rsp+28h] [rbp-F0h]
  unsigned __int16 *v50; // [rsp+38h] [rbp-E0h]
  unsigned __int16 *v51; // [rsp+38h] [rbp-E0h]
  char v52[8]; // [rsp+40h] [rbp-D8h]
  char v53[8]; // [rsp+40h] [rbp-D8h]
  unsigned int v54; // [rsp+98h] [rbp-80h] BYREF
  char v55[4]; // [rsp+9Ch] [rbp-7Ch] BYREF
  unsigned int v56; // [rsp+A0h] [rbp-78h]
  unsigned int v57; // [rsp+A4h] [rbp-74h]
  unsigned int v58[2]; // [rsp+A8h] [rbp-70h] BYREF
  void **v59; // [rsp+B0h] [rbp-68h]
  void **v60; // [rsp+B8h] [rbp-60h]
  unsigned __int16 *v61; // [rsp+C0h] [rbp-58h] BYREF
  unsigned __int16 *v62; // [rsp+C8h] [rbp-50h] BYREF
  unsigned __int16 *v63; // [rsp+D0h] [rbp-48h] BYREF
  unsigned int v64; // [rsp+D8h] [rbp-40h] BYREF
  unsigned int v65; // [rsp+DCh] [rbp-3Ch] BYREF
  unsigned int v66[2]; // [rsp+E0h] [rbp-38h] BYREF
  unsigned __int8 v67[8]; // [rsp+E8h] [rbp-30h] BYREF
  __int64 v68; // [rsp+F0h] [rbp-28h] BYREF
  _BYTE v69[16]; // [rsp+F8h] [rbp-20h] BYREF
  __int64 v70; // [rsp+108h] [rbp-10h] BYREF
  size_t Size; // [rsp+110h] [rbp-8h]
  size_t v72; // [rsp+118h] [rbp+0h]
  _QWORD v73[3]; // [rsp+120h] [rbp+8h] BYREF
  unsigned __int16 Destination[144]; // [rsp+138h] [rbp+20h] BYREF

  v73[2] = -2;
  LODWORD(v59) = 0;
  v6 = 0;
  LODWORD(v60) = 0;
  v56 = 0;
  memset_0(Destination, 0, sizeof(Destination));
  v62 = 0;
  v63 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 9) + 364LL) )
  {
    if ( (bidGblFlags & 2) == 0 )
      return 2147500037LL;
    v8 = 2147500037LL;
    v9 = 3443721;
    goto LABEL_133;
  }
  Bytes = BATCHCTX::GetBytes(this, a2, 4u, &v54, 0, a3);
  if ( Bytes < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 3448841;
LABEL_132:
      v8 = (unsigned int)Bytes;
      _mm_lfence();
LABEL_133:
      bidTraceHR(0, v9, v8, v7);
      goto LABEL_134;
    }
    goto LABEL_134;
  }
  if ( v54 - 24 > 0x27E8 )
    return 2147549183LL;
  _mm_lfence();
  Bytes = BATCHCTX::GetBytes(this, a2, 4u, &v64, 0, a3);
  if ( Bytes < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      v9 = 3461129;
      goto LABEL_132;
    }
LABEL_134:
    if ( v62 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    if ( v63 )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    return 2147500037LL;
  }
  _mm_lfence();
  if ( v64 - 2 > 0xFE )
    return 2147549183LL;
  v11 = v54 - 4;
  v54 = v11;
  if ( v11 < 9 * v64 )
    return 2147549183LL;
  v12 = v11 - 9 * v64;
  v57 = 0;
  if ( !v64 )
    return 2147549183LL;
  do
  {
    Bytes = BATCHCTX::GetBytes(this, a2, 1u, v55, 0, a3);
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3483657;
      goto LABEL_132;
    }
    _mm_lfence();
    Bytes = BATCHCTX::GetBytes(this, a2, 4u, v66, 0, a3);
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3485705;
      goto LABEL_132;
    }
    _mm_lfence();
    Bytes = BATCHCTX::GetBytes(this, a2, 4u, &v65, 0, a3);
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3487753;
      goto LABEL_132;
    }
    if ( v66[0] > 0x2800 )
      return 2147549183LL;
    v13 = 9 * v64;
    if ( v65 + v66[0] > v12 + 9 * v64 + 4 || v65 < v13 + 4 )
      return 2147549183LL;
    v14 = v65 - 4;
    v65 -= 4;
    if ( v55[0] == 1 )
    {
      v6 = v66[0];
      LODWORD(v59) = v14;
    }
    else
    {
      if ( v55[0] == 2 )
      {
        v15 = v66[0];
        v56 = v66[0];
        v16 = v14;
        LODWORD(v60) = v14;
        v14 = (unsigned int)v59;
        goto LABEL_26;
      }
      v14 = (unsigned int)v59;
    }
    v15 = v56;
    v16 = (unsigned int)v60;
LABEL_26:
    v54 -= 9;
    ++v57;
  }
  while ( v57 < v64 );
  if ( !v14 || !v16 || (((unsigned __int8)v6 | (unsigned __int8)v15) & 1) != 0 || v6 + v14 > v16 && v15 + v16 > v14 )
    return 2147549183LL;
  v17 = v16 - v13;
  v18 = v14 - v13;
  v19 = v17;
  if ( v18 < v17 )
    v19 = v18;
  v56 = v19;
  v20 = v15;
  if ( v18 < v17 )
    v20 = v6;
  v57 = v20;
  v21 = &v62;
  if ( v18 >= v17 )
    v21 = &v63;
  v60 = (void **)v21;
  v22 = v18;
  if ( v18 < v17 )
  {
    v22 = v17;
    v6 = v15;
  }
  v23 = &v63;
  if ( v18 >= v17 )
    v23 = &v62;
  v59 = (void **)v23;
  Size = v20 + 2;
  v24 = ((__int64 (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Alloc)(g_pMO);
  *v60 = (void *)v24;
  if ( !v24 )
    goto LABEL_134;
  v72 = v6 + 2;
  v25 = ((__int64 (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Alloc)(g_pMO);
  *v59 = (void *)v25;
  if ( !v25 )
    goto LABEL_134;
  memset_0(*v60, 0, Size);
  memset_0(*v59, 0, v72);
  if ( v56 )
  {
    _mm_lfence();
    Bytes = BATCHCTX::GetBytes(this, a2, v56, 0, 0, a3);
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3564553;
      goto LABEL_132;
    }
    v54 -= v56;
  }
  _mm_lfence();
  Bytes = BATCHCTX::GetBytes(this, a2, v57, *v60, 0, a3);
  if ( Bytes < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_134;
    v9 = 3570697;
    goto LABEL_132;
  }
  v54 -= v57;
  v26 = v22 - v57 - v56;
  if ( v26 )
  {
    _mm_lfence();
    Bytes = BATCHCTX::GetBytes(this, a2, v26, 0, 0, a3);
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3579913;
      goto LABEL_132;
    }
    v54 -= v26;
  }
  _mm_lfence();
  Bytes = BATCHCTX::GetBytes(this, a2, v6, *v59, 0, a3);
  v27 = Bytes;
  if ( Bytes < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_134;
    v9 = 3586057;
    goto LABEL_132;
  }
  _mm_lfence();
  v28 = v54 == v6;
  v29 = v54 - v6;
  v54 -= v6;
  if ( !v28 )
  {
    Bytes = BATCHCTX::GetBytes(this, a2, v29, 0, 0, a3);
    v27 = Bytes;
    if ( Bytes < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_134;
      v9 = 3593225;
      goto LABEL_132;
    }
  }
  v30 = *((_QWORD *)this + 16);
  v31 = *(_BYTE *)(v30 + 140);
  if ( ((v31 - 1) & 0xFC) != 0 || v31 == 3 )
  {
    memcpy_s(Destination, 0x120u, *(const void *const *)(v30 + 40), 0x120u);
    if ( g_pfnCryptUnprotectMemory )
    {
      if ( !g_pfnCryptUnprotectMemory(Destination, 0x120u, 0) )
      {
        if ( (bidGblFlags & 2) != 0 && off_1005E6880[0] )
        {
          LastError = GetLastError();
          bidTraceW(0, 3611648, off_1005E6880[0], LastError, v49);
        }
        if ( (bidGblFlags & 2) != 0 && off_1005E6888[0] )
          bidTraceW(0, 3613696, off_1005E6888[0], this, a2);
        v33 = (CTdsParser *)*((_QWORD *)this + 13);
        LODWORD(v49) = GetLastError();
        CTdsParser::PostFormattedParserErrorEx(v33, a2, 0x9E28u, 0x80004005, v49);
        goto LABEL_134;
      }
    }
  }
  _mm_lfence();
  TickCount = GetTickCount();
  for ( i = 100; ; i *= 2 )
  {
    v61 = 0;
    v38 = *((_QWORD *)this + 16);
    v68 = 0;
    if ( *(_BYTE *)(v38 + 140) == 6 )
      break;
    v36 = *(_BYTE *)(v38 + 140);
    if ( v36 == 7 )
      break;
    v37 = SNISecMSQAGetAccessToken(
            *(unsigned __int16 **)(v38 + 32),
            L"https://sqlaad/",
            *(_QWORD *)(v38 + 304),
            L"2c1229aa-16c5-4ff5-b46b-4f7fe2a2a9c8",
            v36,
            *(MSQAAuthContextCache **)(v38 + 352),
            (__int64)&v61,
            (__int64)v58,
            (__int64)&v68,
            (__int64)&v70,
            (__int64)v67,
            &v66[1],
            *(_DWORD *)(v38 + 360),
            41378,
            *(_QWORD *)(v38 + 72));
    v27 = v37;
    if ( !v37 )
    {
      _mm_lfence();
      if ( *(_BYTE *)(*((_QWORD *)this + 16) + 140LL) == 4 )
      {
        _mm_lfence();
        if ( !*(_DWORD *)(*((_QWORD *)this + 16) + 344LL) )
        {
          _mm_lfence();
          *(_DWORD *)(*((_QWORD *)this + 16) + 344LL) = 1;
        }
      }
LABEL_107:
      _mm_lfence();
      _InterlockedExchange((volatile __int32 *)this + 8, 4);
      *(_DWORD *)&v67[4] = v58[0] + 4;
      v45 = BATCHCTX::QueuePacket(this, a2, 4u, &v67[4], 8, a3, 0);
      v27 = v45;
      if ( v45 >= 0 )
      {
        _mm_lfence();
        v45 = BATCHCTX::QueuePacket(this, a2, 4u, (const unsigned __int8 *)v58, 8, a3, 0);
        v27 = v45;
        if ( v45 >= 0 )
        {
          _mm_lfence();
          v45 = BATCHCTX::QueuePacket(this, a2, v58[0], (const unsigned __int8 *)v61, 8, a3, 1);
          v27 = v45;
          if ( v45 >= 0 || (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          v47 = 3732489;
        }
        else
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_117;
          v47 = 3730441;
        }
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_117;
        v47 = 3728393;
      }
      _mm_lfence();
      bidTraceHR(0, v47, (unsigned int)v45, v46);
      goto LABEL_117;
    }
    if ( v37 != 2 || GetTickCount() - TickCount >= a3 )
    {
      _mm_lfence();
      v27 = -2147467259;
      if ( (bidGblFlags & 2) != 0 && off_1005E6890[0] )
      {
        _mm_lfence();
        bidTraceW(0, 3675136, off_1005E6890[0], this, a2);
      }
      *(_DWORD *)v52 = v66[1];
      LODWORD(v50) = *(_DWORD *)v67;
      CTdsParser::PostFormattedParserErrorEx(
        *((CTdsParser **)this + 13),
        a2,
        0xA1BCu,
        0x80004005,
        *(_QWORD *)(*((_QWORD *)this + 16) + 32LL),
        off_1005CF8B0[*(unsigned __int8 *)(*((_QWORD *)this + 16) + 140LL)],
        v50,
        *(_QWORD *)v52,
        v68);
      goto LABEL_117;
    }
    Sleep(i);
  }
  _mm_lfence();
  v39 = 3;
  aadauth::AzureADAuth::AzureADAuth((aadauth::AzureADAuth *)v69, 3u, 0x1388u, 0x1F4u);
  v73[0] = a2;
  v73[1] = this;
  v40 = *((_QWORD *)this + 16);
  if ( *(_BYTE *)(v40 + 140) == 6 )
  {
    v39 = 5;
  }
  else
  {
    _mm_lfence();
    v40 = *((_QWORD *)this + 16);
    if ( *(_BYTE *)(v40 + 140) == 3 )
    {
      v39 = 2;
    }
    else
    {
      _mm_lfence();
      v40 = *((_QWORD *)this + 16);
      if ( *(_BYTE *)(v40 + 140) == 7 )
        v39 = 1;
    }
  }
  AccessTokenW = aadauth::AzureADAuth::GetAccessTokenW(
                   (aadauth::AzureADAuth *)v69,
                   (void (*)(struct CEKeystoreContext *, const unsigned __int16 *, ...))BATCHCTX::ADErrorCallback,
                   v73,
                   *(const unsigned __int16 **)(v40 + 32),
                   Destination,
                   v62,
                   v63,
                   v39,
                   *(_DWORD *)(v40 + 360),
                   *(const unsigned __int16 **)(v40 + 72),
                   &v61,
                   v58);
  if ( !AccessTokenW )
  {
    SNI_IOCPIOQueue::Poll((SNI_IOCPIOQueue *)v69, v41);
    goto LABEL_107;
  }
  _mm_lfence();
  if ( (bidGblFlags & 2) != 0 && off_1005E6898[0] )
  {
    _mm_lfence();
    bidTraceW(0, 3715072, off_1005E6898[0], this, a2);
  }
  v43 = L"ActiveDirectoryIntegrated";
  if ( v39 == 1 )
    v43 = L"ActiveDirectoryServicePrincipal";
  if ( v39 == 2 )
    v43 = L"ActiveDirectoryPassword";
  if ( v39 == 5 )
    v43 = L"ActiveDirectoryMSI";
  *(_DWORD *)v53 = AccessTokenW;
  LODWORD(v51) = AccessTokenW;
  CTdsParser::PostFormattedParserErrorEx(
    *((CTdsParser **)this + 13),
    a2,
    0xA1BCu,
    v27,
    *(_QWORD *)(*((_QWORD *)this + 16) + 32LL),
    v43,
    v51,
    *(_QWORD *)v53,
    v61);
  SNI_IOCPIOQueue::Poll((SNI_IOCPIOQueue *)v69, v44);
LABEL_117:
  if ( *(_BYTE *)(*((_QWORD *)this + 16) + 140LL) == 3 )
    memset(Destination, 0, sizeof(Destination));
  if ( v61 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  if ( v62 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  if ( v63 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
  return v27;
}

```

## disassembly

```asm
0x100453f4c  mov     rax, rsp
0x100453f4f  push    rbp
0x100453f50  push    rsi
0x100453f51  push    rdi
0x100453f52  push    r12
0x100453f54  push    r13
0x100453f56  push    r14
0x100453f58  push    r15
0x100453f5a  lea     rbp, [rax-188h]
0x100453f61  sub     rsp, 260h
0x100453f68  mov     [rbp+180h+var_168], 0FFFFFFFFFFFFFFFEh
0x100453f70  mov     [rax+20h], rbx
0x100453f74  mov     rax, cs:__security_cookie
0x100453f7b  xor     rax, rsp
0x100453f7e  mov     [rbp+180h+var_40], rax
0x100453f85  mov     r15d, r8d
0x100453f88  mov     r14, rdx
0x100453f8b  mov     rdi, rcx
0x100453f8e  xor     ebx, ebx
0x100453f90  mov     dword ptr [rbp+180h+var_1E8], ebx
0x100453f93  mov     r12d, ebx
0x100453f96  mov     dword ptr [rbp+180h+var_1E0], ebx
0x100453f99  mov     dword ptr [rbp+180h+var_1F8], ebx
0x100453f9c  xor     edx, edx; Val
0x100453f9e  mov     r8d, 120h; Size
0x100453fa4  lea     rcx, [rbp+180h+Destination]; void *
0x100453fa8  call    memset_0
0x100453fad  mov     [rbp+180h+var_1D0], rbx
0x100453fb1  mov     [rbp+180h+var_1C8], rbx
0x100453fb5  mov     rax, [rdi+48h]
0x100453fb9  mov     r13d, 80004005h
0x100453fbf  cmp     [rax+16Ch], ebx
0x100453fc5  jz      short loc_100453FE5
0x100453fc7  mov     ebx, 2
0x100453fcc  test    byte ptr cs:_bidGblFlags, bl
0x100453fd2  jz      loc_100454A82
0x100453fd8  mov     r8d, r13d
0x100453fdb  mov     edx, 348C09h
0x100453fe0  jmp     loc_100454A41
0x100453fe5  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x100453fea  mov     [rsp+290h+var_270], rbx; unsigned __int64 *
0x100453fef  lea     r9, [rbp+180h+var_200]; void *
0x100453ff3  mov     esi, 4
0x100453ff8  mov     r8d, esi; unsigned __int64
0x100453ffb  mov     rdx, r14; void *
0x100453ffe  mov     rcx, rdi; this
0x100454001  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x100454006  test    eax, eax
0x100454008  jns     short loc_100454023
0x10045400a  lea     ebx, [rsi-2]
0x10045400d  test    byte ptr cs:_bidGblFlags, bl
0x100454013  jz      loc_100454A48
0x100454019  mov     edx, 34A009h
0x10045401e  jmp     loc_100454A3B
0x100454023  mov     eax, [rbp+180h+var_200]
0x100454026  add     eax, 0FFFFFFE8h
0x100454029  cmp     eax, 27E8h
0x10045402e  ja      loc_100454A87
0x100454034  lfence
0x100454037  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x10045403c  mov     [rsp+290h+var_270], rbx; unsigned __int64 *
0x100454041  lea     r9, [rbp+180h+var_1C0]; void *
0x100454045  mov     r8, rsi; unsigned __int64
0x100454048  mov     rdx, r14; void *
0x10045404b  mov     rcx, rdi; this
0x10045404e  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x100454053  test    eax, eax
0x100454055  jns     short loc_100454072
0x100454057  mov     ebx, 2
0x10045405c  test    byte ptr cs:_bidGblFlags, bl
0x100454062  jz      loc_100454A48
0x100454068  mov     edx, 34D009h
0x10045406d  jmp     loc_100454A3B
0x100454072  lfence
0x100454075  mov     ecx, [rbp+180h+var_1C0]
0x100454078  lea     eax, [rcx-2]
0x10045407b  cmp     eax, 0FEh
0x100454080  ja      loc_100454A87
0x100454086  mov     eax, [rbp+180h+var_200]
0x100454089  add     eax, 0FFFFFFFCh
0x10045408c  mov     esi, eax
0x10045408e  mov     [rbp+180h+var_200], eax
0x100454091  lea     eax, [rcx+rcx*8]
0x100454094  cmp     esi, eax
0x100454096  jb      loc_100454A87
0x10045409c  sub     esi, eax
0x10045409e  mov     dword ptr [rbp+180h+var_1F8+4], ebx
0x1004540a1  test    ecx, ecx
0x1004540a3  jz      loc_100454A87
0x1004540a9  mov     ebx, 2
0x1004540ae  lea     r11d, [rbx-1]
0x1004540b2  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x1004540b7  and     [rsp+290h+var_270], 0
0x1004540bd  lea     r9, [rbp+180h+var_1FC]; void *
0x1004540c1  mov     r8, r11; unsigned __int64
0x1004540c4  mov     rdx, r14; void *
0x1004540c7  mov     rcx, rdi; this
0x1004540ca  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x1004540cf  test    eax, eax
0x1004540d1  js      loc_100454A2E
0x1004540d7  lfence
0x1004540da  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x1004540df  and     [rsp+290h+var_270], 0
0x1004540e5  lea     r9, [rbp+180h+var_1B8]; void *
0x1004540e9  mov     r8d, 4; unsigned __int64
0x1004540ef  mov     rdx, r14; void *
0x1004540f2  mov     rcx, rdi; this
0x1004540f5  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x1004540fa  test    eax, eax
0x1004540fc  js      loc_100454A1F
0x100454102  lfence
0x100454105  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x10045410a  and     [rsp+290h+var_270], 0
0x100454110  lea     r9, [rbp+180h+var_1BC]; void *
0x100454114  mov     r8d, 4; unsigned __int64
0x10045411a  mov     rdx, r14; void *
0x10045411d  mov     rcx, rdi; this
0x100454120  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x100454125  test    eax, eax
0x100454127  js      loc_100454A10
0x10045412d  mov     edx, [rbp+180h+var_1B8]
0x100454130  cmp     edx, 2800h
0x100454136  ja      loc_100454A87
0x10045413c  mov     r9d, [rbp+180h+var_1C0]
0x100454140  lea     r10d, [r9+r9*8]
0x100454144  lea     ecx, [r10+4]
0x100454148  add     ecx, esi
0x10045414a  mov     r8d, [rbp+180h+var_1BC]
0x10045414e  lea     eax, [r8+rdx]
0x100454152  cmp     eax, ecx
0x100454154  ja      loc_100454A87
0x10045415a  lea     eax, [r10+4]
0x10045415e  cmp     r8d, eax
0x100454161  jb      loc_100454A87
0x100454167  lea     eax, [r8-4]
0x10045416b  mov     ecx, eax
0x10045416d  mov     [rbp+180h+var_1BC], eax
0x100454170  mov     al, [rbp+180h+var_1FC]
0x100454173  mov     r11d, 1
0x100454179  cmp     al, r11b
0x10045417c  jnz     short loc_100454186
0x10045417e  mov     r12d, edx
0x100454181  mov     dword ptr [rbp+180h+var_1E8], ecx
0x100454184  jmp     short loc_10045419D
0x100454186  cmp     al, bl
0x100454188  jnz     short loc_10045419A
0x10045418a  mov     r8d, edx
0x10045418d  mov     dword ptr [rbp+180h+var_1F8], edx
0x100454190  mov     edx, ecx
0x100454192  mov     dword ptr [rbp+180h+var_1E0], ecx
0x100454195  mov     ecx, dword ptr [rbp+180h+var_1E8]
0x100454198  jmp     short loc_1004541A4
0x10045419a  mov     ecx, dword ptr [rbp+180h+var_1E8]
0x10045419d  mov     r8d, dword ptr [rbp+180h+var_1F8]
0x1004541a1  mov     edx, dword ptr [rbp+180h+var_1E0]
0x1004541a4  add     [rbp+180h+var_200], 0FFFFFFF7h
0x1004541a8  mov     eax, dword ptr [rbp+180h+var_1F8+4]
0x1004541ab  add     eax, r11d
0x1004541ae  mov     dword ptr [rbp+180h+var_1F8+4], eax
0x1004541b1  cmp     eax, r9d
0x1004541b4  jb      loc_1004540B2
0x1004541ba  test    ecx, ecx
0x1004541bc  jz      loc_100454A87
0x1004541c2  test    edx, edx
0x1004541c4  jz      loc_100454A87
0x1004541ca  mov     eax, r8d
0x1004541cd  or      eax, r12d
0x1004541d0  test    r11b, al
0x1004541d3  jnz     loc_100454A87
0x1004541d9  lea     eax, [r12+rcx]
0x1004541dd  cmp     eax, edx
0x1004541df  jbe     short loc_1004541ED
0x1004541e1  lea     eax, [r8+rdx]
0x1004541e5  cmp     eax, ecx
0x1004541e7  ja      loc_100454A87
0x1004541ed  sub     edx, r10d
0x1004541f0  sub     ecx, r10d
0x1004541f3  mov     eax, edx
0x1004541f5  cmp     ecx, edx
0x1004541f7  cmovb   eax, ecx
0x1004541fa  mov     dword ptr [rbp+180h+var_1F8], eax
0x1004541fd  mov     eax, r8d
0x100454200  cmovb   eax, r12d
0x100454204  mov     dword ptr [rbp+180h+var_1F8+4], eax
0x100454207  lea     r9, [rbp+180h+var_1D0]
0x10045420b  lea     r10, [rbp+180h+var_1C8]
0x10045420f  cmovnb  r9, r10
0x100454213  mov     [rbp+180h+var_1E0], r9
0x100454217  mov     esi, ecx
0x100454219  cmovb   esi, edx
0x10045421c  cmovb   r12d, r8d
0x100454220  lea     r8, [rbp+180h+var_1C8]
0x100454224  lea     r9, [rbp+180h+var_1D0]
0x100454228  cmovnb  r8, r9
0x10045422c  mov     [rbp+180h+var_1E8], r8
0x100454230  lea     edx, [rax+2]
0x100454233  mov     [rbp+180h+Size], rdx
0x100454237  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10045423e  mov     rax, [rcx]
0x100454241  mov     rax, [rax+18h]
0x100454245  call    cs:__guard_dispatch_icall_fptr
0x10045424b  mov     rcx, [rbp+180h+var_1E0]
0x10045424f  mov     [rcx], rax
0x100454252  test    rax, rax
0x100454255  jz      loc_100454A48
0x10045425b  lea     edx, [r12+2]
0x100454260  mov     [rbp+180h+var_180], rdx
0x100454264  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x10045426b  mov     rax, [rcx]
0x10045426e  mov     rax, [rax+18h]
0x100454272  call    cs:__guard_dispatch_icall_fptr
0x100454278  mov     rcx, [rbp+180h+var_1E8]
0x10045427c  mov     [rcx], rax
0x10045427f  test    rax, rax
0x100454282  jz      loc_100454A48
0x100454288  mov     r8, [rbp+180h+Size]; Size
0x10045428c  xor     edx, edx; Val
0x10045428e  mov     rax, [rbp+180h+var_1E0]
0x100454292  mov     rcx, [rax]; void *
0x100454295  call    memset_0
0x10045429a  mov     r8, [rbp+180h+var_180]; Size
0x10045429e  xor     edx, edx; Val
0x1004542a0  mov     rax, [rbp+180h+var_1E8]
0x1004542a4  mov     rcx, [rax]; void *
0x1004542a7  call    memset_0
0x1004542ac  mov     eax, dword ptr [rbp+180h+var_1F8]
0x1004542af  test    eax, eax
0x1004542b1  jz      short loc_1004542F2
0x1004542b3  lfence
0x1004542b6  mov     r8d, eax; unsigned __int64
0x1004542b9  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x1004542be  and     [rsp+290h+var_270], 0
0x1004542c4  xor     r9d, r9d; void *
0x1004542c7  mov     rdx, r14; void *
0x1004542ca  mov     rcx, rdi; this
0x1004542cd  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x1004542d2  test    eax, eax
0x1004542d4  jns     short loc_1004542EC
0x1004542d6  test    byte ptr cs:_bidGblFlags, bl
0x1004542dc  jz      loc_100454A48
0x1004542e2  mov     edx, 366409h
0x1004542e7  jmp     loc_100454A3B
0x1004542ec  mov     eax, dword ptr [rbp+180h+var_1F8]
0x1004542ef  sub     [rbp+180h+var_200], eax
0x1004542f2  lfence
0x1004542f5  mov     r8d, dword ptr [rbp+180h+var_1F8+4]; unsigned __int64
0x1004542f9  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x1004542fe  and     [rsp+290h+var_270], 0
0x100454304  mov     rax, [rbp+180h+var_1E0]
0x100454308  mov     r9, [rax]; void *
0x10045430b  mov     rdx, r14; void *
0x10045430e  mov     rcx, rdi; this
0x100454311  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x100454316  test    eax, eax
0x100454318  jns     short loc_100454330
0x10045431a  test    byte ptr cs:_bidGblFlags, bl
0x100454320  jz      loc_100454A48
0x100454326  mov     edx, 367C09h
0x10045432b  jmp     loc_100454A3B
0x100454330  mov     eax, dword ptr [rbp+180h+var_1F8+4]
0x100454333  sub     [rbp+180h+var_200], eax
0x100454336  sub     esi, eax
0x100454338  sub     esi, dword ptr [rbp+180h+var_1F8]
0x10045433b  jz      short loc_100454379
0x10045433d  lfence
0x100454340  mov     r8d, esi; unsigned __int64
0x100454343  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x100454348  and     [rsp+290h+var_270], 0
0x10045434e  xor     r9d, r9d; void *
0x100454351  mov     rdx, r14; void *
0x100454354  mov     rcx, rdi; this
0x100454357  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x10045435c  test    eax, eax
0x10045435e  jns     short loc_100454376
0x100454360  test    byte ptr cs:_bidGblFlags, bl
0x100454366  jz      loc_100454A48
0x10045436c  mov     edx, 36A009h
0x100454371  jmp     loc_100454A3B
0x100454376  sub     [rbp+180h+var_200], esi
0x100454379  lfence
0x10045437c  mov     r8d, r12d; unsigned __int64
0x10045437f  mov     dword ptr [rsp+290h+var_268], r15d; unsigned int
0x100454384  and     [rsp+290h+var_270], 0
0x10045438a  mov     rax, [rbp+180h+var_1E8]
0x10045438e  mov     r9, [rax]; void *
0x100454391  mov     rdx, r14; void *
0x100454394  mov     rcx, rdi; this
0x100454397  call    ?GetBytes@BATCHCTX@@AEAAJPEAX_K0PEA_KK@Z; BATCHCTX::GetBytes(void *,unsigned __int64,void *,unsigned __int64 *,ulong)
0x10045439c  mov     esi, eax
0x10045439e  test    eax, eax
0x1004543a0  jns     short loc_1004543B8
0x1004543a2  test    byte ptr cs:_bidGblFlags, bl
0x1004543a8  jz      loc_100454A48
0x1004543ae  mov     edx, 36B809h
0x1004543b3  jmp     loc_100454A3B
0x1004543b8  lfence
0x1004543bb  mov     eax, [rbp+180h+var_200]
0x1004543be  sub     eax, r12d
0x1004543c1  mov     [rbp+180h+var_200], eax
0x1004543c4  jz      short loc_1004543FE
  ... truncated ...
```
