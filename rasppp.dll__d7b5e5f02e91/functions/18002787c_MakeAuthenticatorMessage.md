# MakeAuthenticatorMessage

- ea: `0x18002787c`
- end: `0x1800281a6`
- name: `MakeAuthenticatorMessage`
- size: `2346`
- prototype: `DWORD __fastcall(__int64, unsigned __int8 *, _BYTE *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180026fa0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18000bd94`
- `0x18001ae70`
- `0x18001b0d4`
- `0x18002787c`
- `0x1800281ac`
- `0x18002b0dc`
- `0x180033a80`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027dc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800279f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027c87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027d2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027db8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027dc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027eaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028028`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027a44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027cb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027efb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027a44`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027cb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027efb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cd0`

## string_xrefs

- `0x1800280fb`: `pReceiveBuf->Length is less than PPP_CONFIG_HDR_LEN + 1 -- Dropping invalid packet`
- `0x180027c3c`: `Error %d while processing Access-Request`
- `0x180027b17`: `The cached EapSendBufferr is NULL or its size is less than minimum size`

## pseudocode

```c
DWORD __fastcall MakeAuthenticatorMessage(
        __int64 a1,
        unsigned __int8 *a2,
        _BYTE *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v9; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // r8
  const void **v13; // rbx
  void *v14; // rcx
  HLOCAL v15; // rax
  void *v16; // rcx
  int v17; // eax
  DWORD RequestAttributes; // edx
  __int64 v19; // rax
  void *v20; // rcx
  const void **v21; // rax
  const void **v22; // rbx
  HLOCAL v23; // rax
  char *ConcatString; // r14
  void *v25; // rcx
  char *v26; // rax
  unsigned __int16 v27; // r12
  HLOCAL v28; // rax
  size_t v29; // r8
  HLOCAL v30; // rdx
  __int64 v31; // rdx
  unsigned int v32; // r12d
  HLOCAL v33; // rax
  size_t v34; // r8
  void *v35; // rcx
  _DWORD *v36; // rax
  _DWORD *v37; // rax
  int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // rbx
  unsigned int Size; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int Size_4; // [rsp+28h] [rbp-D8h]
  size_t v44; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h]
  int v46; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v47[2044]; // [rsp+44h] [rbp-BCh] BYREF

  Size = 0;
  LODWORD(v44) = 0;
  v46 = 0;
  Size_4 = a4;
  memset_0(v47, 0, sizeof(v47));
  v9 = *((_QWORD *)&xmmword_18004D740 + 1);
  if ( *((_QWORD *)&xmmword_18004D740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004D740 + 1),
      L"MakeAuthenticatorMessage...");
    v9 = *((_QWORD *)&xmmword_18004D740 + 1);
  }
  if ( !a1 )
    return 87;
  *(_DWORD *)(a5 + 360) = *(_DWORD *)(a1 + 36);
  if ( !*(_DWORD *)a1 )
    goto LABEL_113;
  if ( *(_DWORD *)a1 == 1 )
  {
    if ( v9 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        v9,
        L"EAPSTATE_IdentityRequestSent");
      v9 = *((_QWORD *)&xmmword_18004D740 + 1);
    }
    if ( a2 )
    {
      v39 = a2[3] + (a2[2] << 8);
      if ( v39 >= 5 )
      {
        if ( *a2 == 2 && a2[4] == 1 )
        {
          v40 = v39 - 5;
          if ( v40 > 0x110 )
            v40 = 272;
          v41 = v40;
          memcpy_0((void *)(a1 + 44), a2 + 5, v40);
          *(_BYTE *)(a1 + v41 + 44) = 0;
          RequestAttributes = MakeRequestAttributes(a1, a2);
          if ( !RequestAttributes )
          {
            *(_QWORD *)(a5 + 288) = *(_QWORD *)(a1 + 384);
            *(_DWORD *)a1 = 3;
            *(_DWORD *)a5 = 6;
          }
          return RequestAttributes;
        }
        if ( !v9 )
          goto LABEL_109;
        v12 = L"Dropping invalid packet";
        goto LABEL_108;
      }
      if ( v9 )
      {
        v12 = L"pReceiveBuf->Length is less than PPP_CONFIG_HDR_LEN + 1 -- Dropping invalid packet";
        goto LABEL_108;
      }
      goto LABEL_109;
    }
    if ( !v9 )
    {
LABEL_115:
      *(_DWORD *)(a1 + 320) = (unsigned __int8)bNextId;
      *a3 = 1;
      a3[1] = *(_BYTE *)(a1 + 320);
      *((_WORD *)a3 + 1) = 1280;
      a3[4] = 1;
      *(_DWORD *)a5 = 4;
      *(_BYTE *)(a5 + 4) = *(_BYTE *)(a1 + 320);
      *(_DWORD *)a1 = 1;
      return 0;
    }
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      v9,
      L"No response from the client, timing out and retransmitting identity request.");
    v9 = *((_QWORD *)&xmmword_18004D740 + 1);
LABEL_113:
    if ( v9 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        v9,
        L"EAPSTATE_Initial");
    goto LABEL_115;
  }
  if ( *(_DWORD *)a1 != 3 )
  {
    if ( *(_DWORD *)a1 == 4 )
    {
      if ( a2 )
      {
        v19 = *(_QWORD *)(a1 + 408);
        if ( v19 && *(_DWORD *)(a1 + 416) >= 5u )
        {
          if ( a2[1] == *(_BYTE *)(v19 + 1) )
          {
            if ( *a2 == 2 && a2[4] > 3u )
              *(_DWORD *)(a1 + 36) = a2[4];
            RequestAttributes = MakeRequestAttributes(a1, a2);
            if ( !RequestAttributes )
            {
              *(_QWORD *)(a5 + 288) = *(_QWORD *)(a1 + 384);
              *(_DWORD *)a5 = 6;
              *(_DWORD *)a1 = 3;
            }
            return RequestAttributes;
          }
LABEL_14:
          if ( v9 )
          {
            v12 = L"Id of packet recvd doesn't match one sent";
LABEL_108:
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(gRasEapEtwContext, v9, v12);
            goto LABEL_109;
          }
          goto LABEL_109;
        }
        goto LABEL_33;
      }
    }
    else
    {
      if ( *(_DWORD *)a1 != 5 )
        return 0;
      if ( a2 )
      {
        v11 = *(_QWORD *)(a1 + 408);
        if ( v11 && *(_DWORD *)(a1 + 416) >= 5u )
        {
          if ( a2[1] != *(_BYTE *)(v11 + 1) )
            goto LABEL_14;
          memset_0((void *)(a5 + 16), 0, 0x110u);
          StringCbCopyNA((STRSAFE_LPSTR)(a5 + 16), 0x110u, (STRSAFE_PCNZCH)(a1 + 44), 0x111u);
          v13 = (const void **)RasAuthAttributeGet(79, *(_QWORD *)(a1 + 392));
          if ( !v13 )
            goto LABEL_32;
          v14 = *(void **)(a1 + 408);
          if ( v14 )
          {
            LocalFree(v14);
            *(_DWORD *)(a1 + 416) = 0;
          }
          if ( *((_DWORD *)v13 + 1) > Size_4 && *((_QWORD *)&xmmword_18004D740 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
              gRasEapEtwContext,
              *((_QWORD *)&xmmword_18004D740 + 1),
              L"Need a larger buffer to construct reply");
          v15 = LocalAlloc(0x40u, *((unsigned int *)v13 + 1));
          *(_QWORD *)(a1 + 408) = v15;
          if ( v15 )
          {
            if ( *((_QWORD *)&xmmword_18004D740 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
                gRasEapEtwContext,
                *((_QWORD *)&xmmword_18004D740 + 1),
                L"Sending packet to client");
            v16 = *(void **)(a1 + 408);
            *(_DWORD *)(a1 + 416) = *((_DWORD *)v13 + 1);
            memcpy_0(v16, v13[1], *((unsigned int *)v13 + 1));
            memcpy_0(a3, v13[1], *((unsigned int *)v13 + 1));
            v17 = *(_DWORD *)(a1 + 400);
            if ( v17 )
            {
              *(_DWORD *)(a5 + 8) = v17;
LABEL_27:
              *(_DWORD *)a5 = 2;
              return 0;
            }
            if ( *a3 == 3 )
            {
              *(_DWORD *)(a5 + 8) = 0;
              goto LABEL_27;
            }
LABEL_32:
            *(_DWORD *)(a5 + 8) = 691;
            *(_DWORD *)a5 = 1;
            return 0;
          }
          return GetLastError();
        }
LABEL_33:
        if ( v9 )
        {
          v12 = L"The cached EapSendBufferr is NULL or its size is less than minimum size";
          goto LABEL_108;
        }
LABEL_109:
        *(_DWORD *)a5 = 0;
        return 0;
      }
    }
    if ( v9 )
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
        gRasEapEtwContext,
        v9,
        L"Timed out, resending packet to client");
    memcpy_0(a3, *(const void **)(a1 + 408), *(unsigned int *)(a1 + 416));
    *(_DWORD *)a5 = (*(_DWORD *)(a1 + 424) != 0) + 4;
    *(_BYTE *)(a5 + 4) = *(_BYTE *)(a1 + 320);
    return 0;
  }
  if ( !a6 || !*(_DWORD *)(a6 + 104) )
    goto LABEL_109;
  memset_0((void *)(a5 + 16), 0, 0x110u);
  StringCbCopyNA((STRSAFE_LPSTR)(a5 + 16), 0x110u, (STRSAFE_PCNZCH)(a1 + 44), 0x111u);
  if ( !*(_DWORD *)(a6 + 108) )
  {
    v20 = *(void **)(a1 + 432);
    if ( v20 )
    {
      LocalFree(v20);
      *(_QWORD *)(a1 + 432) = 0;
    }
    v21 = (const void **)RasAuthAttributeGet(24, *(_QWORD *)(a6 + 120));
    v22 = v21;
    if ( v21 )
    {
      v23 = LocalAlloc(0x40u, *((unsigned int *)v21 + 1));
      *(_QWORD *)(a1 + 432) = v23;
      if ( !v23 )
        return GetLastError();
      memcpy_0(v23, v22[1], *((unsigned int *)v22 + 1));
      *(_DWORD *)(a1 + 440) = *((_DWORD *)v22 + 1);
    }
    ConcatString = RasAuthAttributeGetConcatString(79, *(_QWORD *)(a6 + 120), &v44);
    if ( ConcatString )
    {
      v25 = *(void **)(a1 + 408);
      if ( v25 )
      {
        LocalFree(v25);
        *(_DWORD *)(a1 + 416) = 0;
      }
      v26 = RasAuthAttributeGetConcatString(18, *(_QWORD *)(a6 + 120), &Size);
      hMem = v26;
      if ( v26 )
      {
        v27 = Size + 5;
        if ( (_WORD)Size != 0xFFFB && v27 <= Size_4 && (unsigned __int8)(*ConcatString - 3) <= 1u )
        {
          v44 = v27;
          v28 = LocalAlloc(0x40u, v27);
          *(_QWORD *)(a1 + 408) = v28;
          if ( v28 )
          {
            v29 = Size;
            v30 = hMem;
            *(_DWORD *)(a1 + 416) = v27;
            *a3 = 1;
            a3[1] = ++ConcatString[1];
            a3[2] = HIBYTE(v27);
            a3[3] = v27;
            a3[4] = 2;
            memcpy_0(a3 + 5, v30, v29);
            LocalFree(hMem);
            memcpy_0(*(void **)(a1 + 408), a3, v44);
            v31 = *((_QWORD *)&xmmword_18004D740 + 1);
            *(_DWORD *)a5 = 4;
            *(_BYTE *)(a5 + 4) = a3[1];
            *(_DWORD *)(a1 + 424) = 0;
            *(_DWORD *)(a1 + 320) = (unsigned __int8)a3[1];
            *(_DWORD *)a1 = 5;
            *(_QWORD *)(a1 + 392) = *(_QWORD *)(a6 + 120);
            *(_DWORD *)(a1 + 400) = *(_DWORD *)(a6 + 112);
            if ( v31 )
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gRasEapTemplateFunc)(
                gRasEapEtwContext,
                v31,
                L"Sending notification to client");
            return 0;
          }
          LocalFree(hMem);
          goto LABEL_68;
        }
      }
      LocalFree(v26);
      v32 = v44;
      Size = v44;
      if ( (unsigned int)v44 > Size_4 )
      {
        v32 = Size_4;
        if ( *((_QWORD *)&xmmword_18004D740 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            *((_QWORD *)&xmmword_18004D740 + 1),
            L"Need a larger buffer to construct reply");
      }
      v33 = LocalAlloc(0x40u, Size);
      *(_QWORD *)(a1 + 408) = v33;
      if ( !v33 )
      {
LABEL_68:
        LocalFree(ConcatString);
        return GetLastError();
      }
      if ( *((_QWORD *)&xmmword_18004D740 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_18004D740 + 1),
          L"Sending packet to client");
      v34 = Size;
      v35 = *(void **)(a1 + 408);
      *(_DWORD *)(a1 + 416) = v44;
      memcpy_0(v35, ConcatString, v34);
      memcpy_0(a3, ConcatString, v32);
      v36 = (_DWORD *)(a6 + 112);
    }
    else
    {
      if ( *((_QWORD *)&xmmword_18004D740 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_18004D740 + 1),
          L"No EAP Message attribute received, failing auth");
      v36 = (_DWORD *)(a6 + 112);
      if ( !*(_DWORD *)(a6 + 112) )
        *v36 = 691;
    }
    if ( *v36 )
    {
      *(_DWORD *)(a5 + 8) = *v36;
      *(_DWORD *)a5 = (ConcatString != 0) + 1;
    }
    else
    {
      if ( ConcatString )
      {
        if ( *a3 == 3 )
        {
          *(_DWORD *)a5 = 2;
        }
        else
        {
          *(_DWORD *)a5 = 4;
          *(_DWORD *)(a1 + 424) = 0;
          v37 = RasAuthAttributeGet(27, *(_QWORD *)(a6 + 120));
          if ( v37 && v37[2] > 0xAu )
          {
            *(_DWORD *)a5 = 5;
            *(_DWORD *)(a1 + 424) = 1;
          }
          v38 = (unsigned __int8)a3[1];
          *(_DWORD *)(a1 + 320) = v38;
          *(_BYTE *)(a5 + 4) = v38;
          *(_DWORD *)a1 = 4;
        }
      }
      else
      {
        *(_DWORD *)a5 = 1;
      }
      *(_DWORD *)(a5 + 8) = 0;
    }
    LocalFree(ConcatString);
    return 0;
  }
  if ( (_QWORD)xmmword_18004D740 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString((wchar_t *)&v46, L"Error %d while processing Access-Request");
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004D740, &v46);
  }
  return *(_DWORD *)(a6 + 108);
}

```

## disassembly

```asm
0x18002787c  push    rbp
0x18002787e  push    rbx
0x18002787f  push    rsi
0x180027880  push    rdi
0x180027881  push    r12
0x180027883  push    r13
0x180027885  push    r14
0x180027887  push    r15
0x180027889  lea     rbp, [rsp-758h]
0x180027891  sub     rsp, 858h
0x180027898  mov     rax, cs:__security_cookie
0x18002789f  xor     rax, rsp
0x1800278a2  mov     [rbp+790h+var_50], rax
0x1800278a9  mov     rsi, [rbp+790h+arg_20]
0x1800278b0  xor     r12d, r12d
0x1800278b3  mov     r13, [rbp+790h+arg_28]
0x1800278ba  mov     r15, r8
0x1800278bd  mov     r14, rdx
0x1800278c0  mov     dword ptr [rsp+890h+Size], r12d
0x1800278c5  mov     rdi, rcx
0x1800278c8  mov     dword ptr [rsp+890h+var_860], r12d
0x1800278cd  xor     edx, edx; Val
0x1800278cf  mov     [rsp+890h+var_850], r12d
0x1800278d4  mov     r8d, 7FCh; Size
0x1800278da  mov     dword ptr [rsp+890h+Size+4], r9d
0x1800278df  lea     rcx, [rsp+890h+var_84C]; void *
0x1800278e4  call    memset_0
0x1800278e9  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x1800278f0  test    rdx, rdx
0x1800278f3  jz      short loc_180027916
0x1800278f5  mov     rcx, cs:gRasEapEtwContext
0x1800278fc  lea     r8, aMakeauthentica_0; "MakeAuthenticatorMessage..."
0x180027903  mov     rax, cs:gRasEapTemplateFunc
0x18002790a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002790f  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180027916  test    rdi, rdi
0x180027919  jnz     short loc_180027923
0x18002791b  lea     eax, [rdi+57h]
0x18002791e  jmp     loc_180027ACC
0x180027923  mov     eax, [rdi+24h]
0x180027926  mov     [rsi+168h], eax
0x18002792c  mov     ecx, [rdi]
0x18002792e  mov     [rsp+890h+var_870], r12d
0x180027933  test    ecx, ecx
0x180027935  jz      loc_180028146
0x18002793b  sub     ecx, 1
0x18002793e  jz      loc_180028039
0x180027944  sub     ecx, 2
0x180027947  jz      loc_180027BEB
0x18002794d  sub     ecx, 1
0x180027950  jz      loc_180027B23
0x180027956  cmp     ecx, 1
0x180027959  jnz     loc_180028118
0x18002795f  test    r14, r14
0x180027962  jz      loc_180027B97
0x180027968  mov     rax, [rdi+198h]
0x18002796f  test    rax, rax
0x180027972  jz      loc_180027B0E
0x180027978  lea     ebx, [rcx+4]
0x18002797b  cmp     [rdi+1A0h], ebx
0x180027981  jb      loc_180027B0E
0x180027987  mov     al, [rax+1]
0x18002798a  cmp     [r14+1], al
0x18002798e  jz      short loc_1800279A5
0x180027990  test    rdx, rdx
0x180027993  jz      loc_180028115
0x180027999  lea     r8, aIdOfPacketRecv; "Id of packet recvd doesn't match one se"...
0x1800279a0  jmp     loc_180028102
0x1800279a5  mov     r12d, 110h
0x1800279ab  lea     rcx, [rsi+10h]; void *
0x1800279af  mov     r8d, r12d; Size
0x1800279b2  xor     edx, edx; Val
0x1800279b4  call    memset_0
0x1800279b9  lea     r8, [rdi+2Ch]; pszSrc
0x1800279bd  mov     edx, r12d; cbDest
0x1800279c0  lea     r9d, [r12+1]; cbToCopy
0x1800279c5  lea     rcx, [rsi+10h]; pszDest
0x1800279c9  call    StringCbCopyNA
0x1800279ce  mov     rdx, [rdi+188h]
0x1800279d5  mov     ecx, 4Fh ; 'O'
0x1800279da  call    RasAuthAttributeGet
0x1800279df  mov     rbx, rax
0x1800279e2  test    rax, rax
0x1800279e5  jz      loc_180027AFF
0x1800279eb  mov     rcx, [rdi+198h]; hMem
0x1800279f2  test    rcx, rcx
0x1800279f5  jz      short loc_180027A0D
0x1800279f7  call    cs:__imp_LocalFree
0x1800279fe  nop     dword ptr [rax+rax+00h]
0x180027a03  mov     dword ptr [rdi+1A0h], 0
0x180027a0d  mov     ecx, dword ptr [rsp+890h+Size+4]
0x180027a11  cmp     [rbx+4], ecx
0x180027a14  jbe     short loc_180027A3C
0x180027a16  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180027a1d  test    rdx, rdx
0x180027a20  jz      short loc_180027A3C
0x180027a22  mov     rcx, cs:gRasEapEtwContext
0x180027a29  lea     r8, aNeedALargerBuf; "Need a larger buffer to construct reply"
0x180027a30  mov     rax, cs:gRasEapTemplateFunc
0x180027a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a3c  mov     edx, [rbx+4]; uBytes
0x180027a3f  mov     ecx, 40h ; '@'; uFlags
0x180027a44  call    cs:__imp_LocalAlloc
0x180027a4b  nop     dword ptr [rax+rax+00h]
0x180027a50  mov     [rdi+198h], rax
0x180027a57  test    rax, rax
0x180027a5a  jz      loc_180027CD0
0x180027a60  mov     rdx, qword ptr cs:xmmword_18004D740+8
0x180027a67  test    rdx, rdx
0x180027a6a  jz      short loc_180027A86
0x180027a6c  mov     rcx, cs:gRasEapEtwContext
0x180027a73  lea     r8, aSendingPacketT; "Sending packet to client"
0x180027a7a  mov     rax, cs:gRasEapTemplateFunc
0x180027a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a86  mov     eax, [rbx+4]
0x180027a89  mov     rcx, [rdi+198h]; void *
0x180027a90  mov     [rdi+1A0h], eax
0x180027a96  mov     r8d, [rbx+4]; Size
0x180027a9a  mov     rdx, [rbx+8]; Src
0x180027a9e  call    memcpy_0
0x180027aa3  mov     r8d, [rbx+4]; Size
0x180027aa7  mov     rcx, r15; void *
0x180027aaa  mov     rdx, [rbx+8]; Src
0x180027aae  call    memcpy_0
0x180027ab3  mov     eax, [rdi+190h]
0x180027ab9  test    eax, eax
0x180027abb  jz      short loc_180027AF0
0x180027abd  mov     [rsi+8], eax
0x180027ac0  mov     dword ptr [rsi], 2
0x180027ac6  mov     edx, [rsp+890h+var_870]
0x180027aca  mov     eax, edx
0x180027acc  mov     rcx, [rbp+790h+var_50]
0x180027ad3  xor     rcx, rsp; StackCookie
0x180027ad6  call    __security_check_cookie
0x180027adb  add     rsp, 858h
0x180027ae2  pop     r15
0x180027ae4  pop     r14
0x180027ae6  pop     r13
0x180027ae8  pop     r12
0x180027aea  pop     rdi
0x180027aeb  pop     rsi
0x180027aec  pop     rbx
0x180027aed  pop     rbp
0x180027aee  retn
0x180027af0  cmp     byte ptr [r15], 3
0x180027af4  jnz     short loc_180027AFF
0x180027af6  mov     dword ptr [rsi+8], 0
0x180027afd  jmp     short loc_180027AC0
0x180027aff  mov     dword ptr [rsi+8], 2B3h
0x180027b06  mov     dword ptr [rsi], 1
0x180027b0c  jmp     short loc_180027AC6
0x180027b0e  test    rdx, rdx
0x180027b11  jz      loc_180028115
0x180027b17  lea     r8, aTheCachedEapse; "The cached EapSendBufferr is NULL or it"...
0x180027b1e  jmp     loc_180028102
0x180027b23  test    r14, r14
0x180027b26  jz      short loc_180027B97
0x180027b28  mov     rax, [rdi+198h]
0x180027b2f  test    rax, rax
0x180027b32  jz      short loc_180027B0E
0x180027b34  mov     ebx, 5
0x180027b39  cmp     [rdi+1A0h], ebx
0x180027b3f  jb      short loc_180027B0E
0x180027b41  mov     al, [rax+1]
0x180027b44  cmp     [r14+1], al
0x180027b48  jnz     loc_180027990
0x180027b4e  cmp     byte ptr [r14], 2
0x180027b52  jnz     short loc_180027B63
0x180027b54  cmp     byte ptr [r14+4], 3
0x180027b59  jbe     short loc_180027B63
0x180027b5b  movzx   eax, byte ptr [r14+4]
0x180027b60  mov     [rdi+24h], eax
0x180027b63  mov     rdx, r14
0x180027b66  mov     rcx, rdi
0x180027b69  call    MakeRequestAttributes
0x180027b6e  mov     edx, eax
0x180027b70  test    eax, eax
0x180027b72  jnz     loc_180027ACA
0x180027b78  mov     rcx, [rdi+180h]
0x180027b7f  mov     [rsi+120h], rcx
0x180027b86  mov     dword ptr [rsi], 6
0x180027b8c  mov     dword ptr [rdi], 3
0x180027b92  jmp     loc_180027ACA
0x180027b97  test    rdx, rdx
0x180027b9a  jz      short loc_180027BB6
0x180027b9c  mov     rcx, cs:gRasEapEtwContext
0x180027ba3  lea     r8, aTimedOutResend; "Timed out, resending packet to client"
0x180027baa  mov     rax, cs:gRasEapTemplateFunc
0x180027bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bb6  mov     r8d, [rdi+1A0h]; Size
0x180027bbd  mov     rcx, r15; void *
0x180027bc0  mov     rdx, [rdi+198h]; Src
0x180027bc7  call    memcpy_0
0x180027bcc  mov     eax, [rdi+1A8h]
0x180027bd2  neg     eax
0x180027bd4  sbb     ecx, ecx
0x180027bd6  neg     ecx
0x180027bd8  add     ecx, 4
0x180027bdb  mov     [rsi], ecx
0x180027bdd  mov     al, [rdi+140h]
0x180027be3  mov     [rsi+4], al
0x180027be6  jmp     loc_180028118
0x180027beb  test    r13, r13
0x180027bee  jz      loc_180028115
0x180027bf4  cmp     [r13+68h], r12d
0x180027bf8  jz      loc_180028115
0x180027bfe  mov     r12d, 110h
0x180027c04  lea     rcx, [rsi+10h]; void *
0x180027c08  mov     r8d, r12d; Size
0x180027c0b  xor     edx, edx; Val
0x180027c0d  call    memset_0
0x180027c12  lea     r8, [rdi+2Ch]; pszSrc
0x180027c16  mov     edx, r12d; cbDest
0x180027c19  lea     r9d, [r12+1]; cbToCopy
0x180027c1e  lea     rcx, [rsi+10h]; pszDest
0x180027c22  call    StringCbCopyNA
0x180027c27  mov     r8d, [r13+6Ch]
0x180027c2b  xor     r12d, r12d
0x180027c2e  test    r8d, r8d
0x180027c31  jz      short loc_180027C7B
0x180027c33  cmp     qword ptr cs:xmmword_18004D740, r12
0x180027c3a  jz      short loc_180027C72
0x180027c3c  lea     rdx, aErrorDWhilePro; "Error %d while processing Access-Reques"...
0x180027c43  mov     word ptr [rsp+890h+var_850], r12w
0x180027c49  lea     rcx, [rsp+890h+var_850]
0x180027c4e  call    FormatRRASErrorString
0x180027c53  mov     rdx, qword ptr cs:xmmword_18004D740
0x180027c5a  lea     r8, [rsp+890h+var_850]
0x180027c5f  mov     rcx, cs:gRasEapEtwContext
0x180027c66  mov     rax, cs:gRasEapTemplateFunc
0x180027c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c72  mov     eax, [r13+6Ch]
0x180027c76  jmp     loc_180027ACC
0x180027c7b  mov     rcx, [rdi+1B0h]; hMem
0x180027c82  test    rcx, rcx
0x180027c85  jz      short loc_180027C9A
0x180027c87  call    cs:__imp_LocalFree
0x180027c8e  nop     dword ptr [rax+rax+00h]
0x180027c93  mov     [rdi+1B0h], r12
0x180027c9a  mov     rdx, [r13+78h]
0x180027c9e  mov     ecx, 18h
0x180027ca3  call    RasAuthAttributeGet
0x180027ca8  mov     rbx, rax
0x180027cab  test    rax, rax
0x180027cae  jz      short loc_180027CFA
0x180027cb0  mov     edx, [rax+4]; uBytes
0x180027cb3  mov     ecx, 40h ; '@'; uFlags
0x180027cb8  call    cs:__imp_LocalAlloc
0x180027cbf  nop     dword ptr [rax+rax+00h]
0x180027cc4  mov     [rdi+1B0h], rax
0x180027ccb  test    rax, rax
0x180027cce  jnz     short loc_180027CE1
0x180027cd0  call    cs:__imp_GetLastError
0x180027cd7  nop     dword ptr [rax+rax+00h]
0x180027cdc  jmp     loc_180027ACC
0x180027ce1  mov     r8d, [rbx+4]; Size
0x180027ce5  mov     rcx, rax; void *
0x180027ce8  mov     rdx, [rbx+8]; Src
0x180027cec  call    memcpy_0
0x180027cf1  mov     eax, [rbx+4]
0x180027cf4  mov     [rdi+1B8h], eax
0x180027cfa  mov     rdx, [r13+78h]
0x180027cfe  lea     r8, [rsp+890h+var_860]
0x180027d03  mov     ecx, 4Fh ; 'O'
0x180027d08  call    RasAuthAttributeGetConcatString
0x180027d0d  mov     r14, rax
0x180027d10  mov     ebx, 5
0x180027d15  test    rax, rax
0x180027d18  jz      loc_180027F72
0x180027d1e  mov     rcx, [rdi+198h]; hMem
0x180027d25  test    rcx, rcx
0x180027d28  jz      short loc_180027D3D
0x180027d2a  call    cs:__imp_LocalFree
0x180027d31  nop     dword ptr [rax+rax+00h]
0x180027d36  mov     [rdi+1A0h], r12d
0x180027d3d  mov     rdx, [r13+78h]
0x180027d41  lea     r8, [rsp+890h+Size]
0x180027d46  mov     ecx, 12h
0x180027d4b  call    RasAuthAttributeGetConcatString
0x180027d50  mov     [rsp+890h+hMem], rax
0x180027d55  test    rax, rax
0x180027d58  jz      loc_180027EA7
0x180027d5e  movzx   r12d, word ptr [rsp+890h+Size]
0x180027d64  add     r12w, bx
0x180027d68  jz      loc_180027EA7
0x180027d6e  movzx   edx, r12w
0x180027d72  cmp     edx, dword ptr [rsp+890h+Size+4]
0x180027d76  ja      loc_180027EA7
0x180027d7c  mov     cl, [r14]
0x180027d7f  sub     cl, 3
0x180027d82  cmp     cl, 1
0x180027d85  ja      loc_180027EA7
0x180027d8b  movzx   eax, r12w
0x180027d8f  mov     ecx, 40h ; '@'; uFlags
0x180027d94  mov     edx, eax; uBytes
0x180027d96  mov     [rsp+890h+var_860], rax
0x180027d9b  call    cs:__imp_LocalAlloc
0x180027da2  nop     dword ptr [rax+rax+00h]
0x180027da7  mov     [rdi+198h], rax
0x180027dae  test    rax, rax
  ... truncated ...
```
