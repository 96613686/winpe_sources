# MakeAuthenticatorMessage

- ea: `0x180026a5c`
- end: `0x180027337`
- name: `MakeAuthenticatorMessage`
- size: `2267`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800261c0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18000b970`
- `0x18001a4bc`
- `0x18001a704`
- `0x180026a5c`
- `0x180027340`
- `0x18002a138`
- `0x180032460`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026bd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026fc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002704d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026bd7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026eeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026fc8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002704d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026e85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026f56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027098`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026c1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026e85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026f56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e97`

## string_xrefs

- `0x18002728c`: `pReceiveBuf->Length is less than PPP_CONFIG_HDR_LEN + 1 -- Dropping invalid packet`
- `0x180026e0f`: `Error %d while processing Access-Request`
- `0x180026cea`: `The cached EapSendBufferr is NULL or its size is less than minimum size`

## pseudocode

```c
DWORD __fastcall MakeAuthenticatorMessage(__int64 a1, _BYTE *a2, _BYTE *a3, unsigned int a4, __int64 a5, __int64 a6)
{
  __int64 v9; // rdx
  __int64 v11; // rax
  const wchar_t *v12; // r8
  __int64 v13; // rbx
  void *v14; // rcx
  HLOCAL v15; // rax
  void *v16; // rcx
  int v17; // eax
  int RequestAttributes; // edx
  __int64 v19; // rax
  void *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rbx
  HLOCAL v23; // rax
  _BYTE *ConcatString; // r14
  void *v25; // rcx
  void *v26; // rax
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
  __int64 v37; // rax
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
  v9 = *((_QWORD *)&xmmword_18004C740 + 1);
  if ( *((_QWORD *)&xmmword_18004C740 + 1) )
  {
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
      gRasEapEtwContext,
      *((_QWORD *)&xmmword_18004C740 + 1),
      L"MakeAuthenticatorMessage...");
    v9 = *((_QWORD *)&xmmword_18004C740 + 1);
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
      v9 = *((_QWORD *)&xmmword_18004C740 + 1);
    }
    if ( a2 )
    {
      v39 = (unsigned __int8)a2[3] + ((unsigned __int8)a2[2] << 8);
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
    v9 = *((_QWORD *)&xmmword_18004C740 + 1);
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
              *(_DWORD *)(a1 + 36) = (unsigned __int8)a2[4];
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
          v13 = RasAuthAttributeGet(79, *(_QWORD *)(a1 + 392));
          if ( !v13 )
            goto LABEL_32;
          v14 = *(void **)(a1 + 408);
          if ( v14 )
          {
            LocalFree(v14);
            *(_DWORD *)(a1 + 416) = 0;
          }
          if ( *(_DWORD *)(v13 + 4) > Size_4 && *((_QWORD *)&xmmword_18004C740 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
              gRasEapEtwContext,
              *((_QWORD *)&xmmword_18004C740 + 1),
              L"Need a larger buffer to construct reply");
          v15 = LocalAlloc(0x40u, *(unsigned int *)(v13 + 4));
          *(_QWORD *)(a1 + 408) = v15;
          if ( v15 )
          {
            if ( *((_QWORD *)&xmmword_18004C740 + 1) )
              ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
                gRasEapEtwContext,
                *((_QWORD *)&xmmword_18004C740 + 1),
                L"Sending packet to client");
            v16 = *(void **)(a1 + 408);
            *(_DWORD *)(a1 + 416) = *(_DWORD *)(v13 + 4);
            memcpy_0(v16, *(const void **)(v13 + 8), *(unsigned int *)(v13 + 4));
            memcpy_0(a3, *(const void **)(v13 + 8), *(unsigned int *)(v13 + 4));
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
    v21 = RasAuthAttributeGet(24, *(_QWORD *)(a6 + 120));
    v22 = v21;
    if ( v21 )
    {
      v23 = LocalAlloc(0x40u, *(unsigned int *)(v21 + 4));
      *(_QWORD *)(a1 + 432) = v23;
      if ( !v23 )
        return GetLastError();
      memcpy_0(v23, *(const void **)(v22 + 8), *(unsigned int *)(v22 + 4));
      *(_DWORD *)(a1 + 440) = *(_DWORD *)(v22 + 4);
    }
    ConcatString = (_BYTE *)RasAuthAttributeGetConcatString(79, *(_QWORD *)(a6 + 120), &v44);
    if ( ConcatString )
    {
      v25 = *(void **)(a1 + 408);
      if ( v25 )
      {
        LocalFree(v25);
        *(_DWORD *)(a1 + 416) = 0;
      }
      v26 = (void *)RasAuthAttributeGetConcatString(18, *(_QWORD *)(a6 + 120), &Size);
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
            v31 = *((_QWORD *)&xmmword_18004C740 + 1);
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
        if ( *((_QWORD *)&xmmword_18004C740 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
            gRasEapEtwContext,
            *((_QWORD *)&xmmword_18004C740 + 1),
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
      if ( *((_QWORD *)&xmmword_18004C740 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_18004C740 + 1),
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
      if ( *((_QWORD *)&xmmword_18004C740 + 1) )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gRasEapTemplateFunc)(
          gRasEapEtwContext,
          *((_QWORD *)&xmmword_18004C740 + 1),
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
          if ( v37 && *(_DWORD *)(v37 + 8) > 0xAu )
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
  if ( (_QWORD)xmmword_18004C740 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"Error %d while processing Access-Request");
    ((void (__fastcall *)(__int64, _QWORD, int *))gRasEapTemplateFunc)(gRasEapEtwContext, xmmword_18004C740, &v46);
  }
  return *(_DWORD *)(a6 + 108);
}

```

## disassembly

```asm
0x180026a5c  push    rbp
0x180026a5e  push    rbx
0x180026a5f  push    rsi
0x180026a60  push    rdi
0x180026a61  push    r12
0x180026a63  push    r13
0x180026a65  push    r14
0x180026a67  push    r15
0x180026a69  lea     rbp, [rsp-758h]
0x180026a71  sub     rsp, 858h
0x180026a78  mov     rax, cs:__security_cookie
0x180026a7f  xor     rax, rsp
0x180026a82  mov     [rbp+790h+var_50], rax
0x180026a89  mov     rsi, [rbp+790h+arg_20]
0x180026a90  xor     r12d, r12d
0x180026a93  mov     r13, [rbp+790h+arg_28]
0x180026a9a  mov     r15, r8
0x180026a9d  mov     r14, rdx
0x180026aa0  mov     dword ptr [rsp+890h+Size], r12d
0x180026aa5  mov     rdi, rcx
0x180026aa8  mov     dword ptr [rsp+890h+var_860], r12d
0x180026aad  xor     edx, edx; Val
0x180026aaf  mov     [rsp+890h+var_850], r12d
0x180026ab4  mov     r8d, 7FCh; Size
0x180026aba  mov     dword ptr [rsp+890h+Size+4], r9d
0x180026abf  lea     rcx, [rsp+890h+var_84C]; void *
0x180026ac4  call    memset_0
0x180026ac9  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180026ad0  test    rdx, rdx
0x180026ad3  jz      short loc_180026AF6
0x180026ad5  mov     rcx, cs:gRasEapEtwContext
0x180026adc  lea     r8, aMakeauthentica_0; "MakeAuthenticatorMessage..."
0x180026ae3  mov     rax, cs:gRasEapTemplateFunc
0x180026aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aef  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180026af6  test    rdi, rdi
0x180026af9  jnz     short loc_180026B03
0x180026afb  lea     eax, [rdi+57h]
0x180026afe  jmp     loc_180026CA0
0x180026b03  mov     eax, [rdi+24h]
0x180026b06  mov     [rsi+168h], eax
0x180026b0c  mov     ecx, [rdi]
0x180026b0e  mov     [rsp+890h+var_870], r12d
0x180026b13  test    ecx, ecx
0x180026b15  jz      loc_1800272D7
0x180026b1b  sub     ecx, 1
0x180026b1e  jz      loc_1800271CA
0x180026b24  sub     ecx, 2
0x180026b27  jz      loc_180026DBE
0x180026b2d  sub     ecx, 1
0x180026b30  jz      loc_180026CF6
0x180026b36  cmp     ecx, 1
0x180026b39  jnz     loc_1800272A9
0x180026b3f  test    r14, r14
0x180026b42  jz      loc_180026D6A
0x180026b48  mov     rax, [rdi+198h]
0x180026b4f  test    rax, rax
0x180026b52  jz      loc_180026CE1
0x180026b58  lea     ebx, [rcx+4]
0x180026b5b  cmp     [rdi+1A0h], ebx
0x180026b61  jb      loc_180026CE1
0x180026b67  mov     al, [rax+1]
0x180026b6a  cmp     [r14+1], al
0x180026b6e  jz      short loc_180026B85
0x180026b70  test    rdx, rdx
0x180026b73  jz      loc_1800272A6
0x180026b79  lea     r8, aIdOfPacketRecv; "Id of packet recvd doesn't match one se"...
0x180026b80  jmp     loc_180027293
0x180026b85  mov     r12d, 110h
0x180026b8b  lea     rcx, [rsi+10h]; void *
0x180026b8f  mov     r8d, r12d; Size
0x180026b92  xor     edx, edx; Val
0x180026b94  call    memset_0
0x180026b99  lea     r8, [rdi+2Ch]; pszSrc
0x180026b9d  mov     edx, r12d; cbDest
0x180026ba0  lea     r9d, [r12+1]; cbToCopy
0x180026ba5  lea     rcx, [rsi+10h]; pszDest
0x180026ba9  call    StringCbCopyNA
0x180026bae  mov     rdx, [rdi+188h]
0x180026bb5  mov     ecx, 4Fh ; 'O'
0x180026bba  call    RasAuthAttributeGet
0x180026bbf  mov     rbx, rax
0x180026bc2  test    rax, rax
0x180026bc5  jz      loc_180026CD2
0x180026bcb  mov     rcx, [rdi+198h]; hMem
0x180026bd2  test    rcx, rcx
0x180026bd5  jz      short loc_180026BE7
0x180026bd7  call    cs:__imp_LocalFree
0x180026bdd  mov     dword ptr [rdi+1A0h], 0
0x180026be7  mov     ecx, dword ptr [rsp+890h+Size+4]
0x180026beb  cmp     [rbx+4], ecx
0x180026bee  jbe     short loc_180026C16
0x180026bf0  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180026bf7  test    rdx, rdx
0x180026bfa  jz      short loc_180026C16
0x180026bfc  mov     rcx, cs:gRasEapEtwContext
0x180026c03  lea     r8, aNeedALargerBuf; "Need a larger buffer to construct reply"
0x180026c0a  mov     rax, cs:gRasEapTemplateFunc
0x180026c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c16  mov     edx, [rbx+4]; uBytes
0x180026c19  mov     ecx, 40h ; '@'; uFlags
0x180026c1e  call    cs:__imp_LocalAlloc
0x180026c24  mov     [rdi+198h], rax
0x180026c2b  test    rax, rax
0x180026c2e  jz      loc_180026E97
0x180026c34  mov     rdx, qword ptr cs:xmmword_18004C740+8
0x180026c3b  test    rdx, rdx
0x180026c3e  jz      short loc_180026C5A
0x180026c40  mov     rcx, cs:gRasEapEtwContext
0x180026c47  lea     r8, aSendingPacketT; "Sending packet to client"
0x180026c4e  mov     rax, cs:gRasEapTemplateFunc
0x180026c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c5a  mov     eax, [rbx+4]
0x180026c5d  mov     rcx, [rdi+198h]; void *
0x180026c64  mov     [rdi+1A0h], eax
0x180026c6a  mov     r8d, [rbx+4]; Size
0x180026c6e  mov     rdx, [rbx+8]; Src
0x180026c72  call    memcpy_0
0x180026c77  mov     r8d, [rbx+4]; Size
0x180026c7b  mov     rcx, r15; void *
0x180026c7e  mov     rdx, [rbx+8]; Src
0x180026c82  call    memcpy_0
0x180026c87  mov     eax, [rdi+190h]
0x180026c8d  test    eax, eax
0x180026c8f  jz      short loc_180026CC3
0x180026c91  mov     [rsi+8], eax
0x180026c94  mov     dword ptr [rsi], 2
0x180026c9a  mov     edx, [rsp+890h+var_870]
0x180026c9e  mov     eax, edx
0x180026ca0  mov     rcx, [rbp+790h+var_50]
0x180026ca7  xor     rcx, rsp; StackCookie
0x180026caa  call    __security_check_cookie
0x180026caf  add     rsp, 858h
0x180026cb6  pop     r15
0x180026cb8  pop     r14
0x180026cba  pop     r13
0x180026cbc  pop     r12
0x180026cbe  pop     rdi
0x180026cbf  pop     rsi
0x180026cc0  pop     rbx
0x180026cc1  pop     rbp
0x180026cc2  retn
0x180026cc3  cmp     byte ptr [r15], 3
0x180026cc7  jnz     short loc_180026CD2
0x180026cc9  mov     dword ptr [rsi+8], 0
0x180026cd0  jmp     short loc_180026C94
0x180026cd2  mov     dword ptr [rsi+8], 2B3h
0x180026cd9  mov     dword ptr [rsi], 1
0x180026cdf  jmp     short loc_180026C9A
0x180026ce1  test    rdx, rdx
0x180026ce4  jz      loc_1800272A6
0x180026cea  lea     r8, aTheCachedEapse; "The cached EapSendBufferr is NULL or it"...
0x180026cf1  jmp     loc_180027293
0x180026cf6  test    r14, r14
0x180026cf9  jz      short loc_180026D6A
0x180026cfb  mov     rax, [rdi+198h]
0x180026d02  test    rax, rax
0x180026d05  jz      short loc_180026CE1
0x180026d07  mov     ebx, 5
0x180026d0c  cmp     [rdi+1A0h], ebx
0x180026d12  jb      short loc_180026CE1
0x180026d14  mov     al, [rax+1]
0x180026d17  cmp     [r14+1], al
0x180026d1b  jnz     loc_180026B70
0x180026d21  cmp     byte ptr [r14], 2
0x180026d25  jnz     short loc_180026D36
0x180026d27  cmp     byte ptr [r14+4], 3
0x180026d2c  jbe     short loc_180026D36
0x180026d2e  movzx   eax, byte ptr [r14+4]
0x180026d33  mov     [rdi+24h], eax
0x180026d36  mov     rdx, r14
0x180026d39  mov     rcx, rdi
0x180026d3c  call    MakeRequestAttributes
0x180026d41  mov     edx, eax
0x180026d43  test    eax, eax
0x180026d45  jnz     loc_180026C9E
0x180026d4b  mov     rcx, [rdi+180h]
0x180026d52  mov     [rsi+120h], rcx
0x180026d59  mov     dword ptr [rsi], 6
0x180026d5f  mov     dword ptr [rdi], 3
0x180026d65  jmp     loc_180026C9E
0x180026d6a  test    rdx, rdx
0x180026d6d  jz      short loc_180026D89
0x180026d6f  mov     rcx, cs:gRasEapEtwContext
0x180026d76  lea     r8, aTimedOutResend; "Timed out, resending packet to client"
0x180026d7d  mov     rax, cs:gRasEapTemplateFunc
0x180026d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d89  mov     r8d, [rdi+1A0h]; Size
0x180026d90  mov     rcx, r15; void *
0x180026d93  mov     rdx, [rdi+198h]; Src
0x180026d9a  call    memcpy_0
0x180026d9f  mov     eax, [rdi+1A8h]
0x180026da5  neg     eax
0x180026da7  sbb     ecx, ecx
0x180026da9  neg     ecx
0x180026dab  add     ecx, 4
0x180026dae  mov     [rsi], ecx
0x180026db0  mov     al, [rdi+140h]
0x180026db6  mov     [rsi+4], al
0x180026db9  jmp     loc_1800272A9
0x180026dbe  test    r13, r13
0x180026dc1  jz      loc_1800272A6
0x180026dc7  cmp     [r13+68h], r12d
0x180026dcb  jz      loc_1800272A6
0x180026dd1  mov     r12d, 110h
0x180026dd7  lea     rcx, [rsi+10h]; void *
0x180026ddb  mov     r8d, r12d; Size
0x180026dde  xor     edx, edx; Val
0x180026de0  call    memset_0
0x180026de5  lea     r8, [rdi+2Ch]; pszSrc
0x180026de9  mov     edx, r12d; cbDest
0x180026dec  lea     r9d, [r12+1]; cbToCopy
0x180026df1  lea     rcx, [rsi+10h]; pszDest
0x180026df5  call    StringCbCopyNA
0x180026dfa  mov     r8d, [r13+6Ch]
0x180026dfe  xor     r12d, r12d
0x180026e01  test    r8d, r8d
0x180026e04  jz      short loc_180026E4E
0x180026e06  cmp     qword ptr cs:xmmword_18004C740, r12
0x180026e0d  jz      short loc_180026E45
0x180026e0f  lea     rdx, aErrorDWhilePro; "Error %d while processing Access-Reques"...
0x180026e16  mov     word ptr [rsp+890h+var_850], r12w
0x180026e1c  lea     rcx, [rsp+890h+var_850]
0x180026e21  call    FormatRRASErrorString
0x180026e26  mov     rdx, qword ptr cs:xmmword_18004C740
0x180026e2d  lea     r8, [rsp+890h+var_850]
0x180026e32  mov     rcx, cs:gRasEapEtwContext
0x180026e39  mov     rax, cs:gRasEapTemplateFunc
0x180026e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e45  mov     eax, [r13+6Ch]
0x180026e49  jmp     loc_180026CA0
0x180026e4e  mov     rcx, [rdi+1B0h]; hMem
0x180026e55  test    rcx, rcx
0x180026e58  jz      short loc_180026E67
0x180026e5a  call    cs:__imp_LocalFree
0x180026e60  mov     [rdi+1B0h], r12
0x180026e67  mov     rdx, [r13+78h]
0x180026e6b  mov     ecx, 18h
0x180026e70  call    RasAuthAttributeGet
0x180026e75  mov     rbx, rax
0x180026e78  test    rax, rax
0x180026e7b  jz      short loc_180026EBB
0x180026e7d  mov     edx, [rax+4]; uBytes
0x180026e80  mov     ecx, 40h ; '@'; uFlags
0x180026e85  call    cs:__imp_LocalAlloc
0x180026e8b  mov     [rdi+1B0h], rax
0x180026e92  test    rax, rax
0x180026e95  jnz     short loc_180026EA2
0x180026e97  call    cs:__imp_GetLastError
0x180026e9d  jmp     loc_180026CA0
0x180026ea2  mov     r8d, [rbx+4]; Size
0x180026ea6  mov     rcx, rax; void *
0x180026ea9  mov     rdx, [rbx+8]; Src
0x180026ead  call    memcpy_0
0x180026eb2  mov     eax, [rbx+4]
0x180026eb5  mov     [rdi+1B8h], eax
0x180026ebb  mov     rdx, [r13+78h]
0x180026ebf  lea     r8, [rsp+890h+var_860]
0x180026ec4  mov     ecx, 4Fh ; 'O'
0x180026ec9  call    RasAuthAttributeGetConcatString
0x180026ece  mov     r14, rax
0x180026ed1  mov     ebx, 5
0x180026ed6  test    rax, rax
0x180026ed9  jz      loc_180027109
0x180026edf  mov     rcx, [rdi+198h]; hMem
0x180026ee6  test    rcx, rcx
0x180026ee9  jz      short loc_180026EF8
0x180026eeb  call    cs:__imp_LocalFree
0x180026ef1  mov     [rdi+1A0h], r12d
0x180026ef8  mov     rdx, [r13+78h]
0x180026efc  lea     r8, [rsp+890h+Size]
0x180026f01  mov     ecx, 12h
0x180026f06  call    RasAuthAttributeGetConcatString
0x180026f0b  mov     [rsp+890h+hMem], rax
0x180026f10  test    rax, rax
0x180026f13  jz      loc_18002704A
0x180026f19  movzx   r12d, word ptr [rsp+890h+Size]
0x180026f1f  add     r12w, bx
0x180026f23  jz      loc_18002704A
0x180026f29  movzx   edx, r12w
0x180026f2d  cmp     edx, dword ptr [rsp+890h+Size+4]
0x180026f31  ja      loc_18002704A
0x180026f37  mov     cl, [r14]
0x180026f3a  sub     cl, 3
0x180026f3d  cmp     cl, 1
0x180026f40  ja      loc_18002704A
0x180026f46  movzx   eax, r12w
0x180026f4a  mov     ecx, 40h ; '@'; uFlags
0x180026f4f  mov     edx, eax; uBytes
0x180026f51  mov     [rsp+890h+var_860], rax
0x180026f56  call    cs:__imp_LocalAlloc
0x180026f5c  mov     [rdi+198h], rax
0x180026f63  test    rax, rax
0x180026f66  jnz     short loc_180026F81
0x180026f68  mov     rcx, [rsp+890h+hMem]; hMem
0x180026f6d  call    cs:__imp_LocalFree
0x180026f73  mov     rcx, r14; hMem
0x180026f76  call    cs:__imp_LocalFree
0x180026f7c  jmp     loc_180026E97
0x180026f81  mov     r8d, dword ptr [rsp+890h+Size]; Size
  ... truncated ...
```
