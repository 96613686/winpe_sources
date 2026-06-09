# IkePostAcquire

- ea: `0x18003a2e0`
- end: `0x18003aa45`
- name: `IkePostAcquire`
- size: `1893`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `14`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800116e0`
- `0x18002a21c`
- `0x18002a3ec`
- `0x18006ab0c`
- `0x18006c560`
- `0x18006c894`
- `0x1800bf5c8`
- `0x1800c1268`
- `0x1800c67ec`
- `0x1800d0a04`
- `0x1800d3658`
- `0x1800d7714`
- `0x1800dfe14`
- `0x1800e1c98`

## callees

- `0x180003cf0`
- `0x1800061ec`
- `0x180006910`
- `0x180008388`
- `0x180018240`
- `0x18003a2e0`
- `0x180050850`
- `0x180071634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a378`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a3bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a8ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a933`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a378`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a3bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a8ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003a933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a81e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a81e`
- `ntdll!EtwEventWriteTransfer` at `0x18003a490`
- `ntdll!EtwEventWriteTransfer` at `0x18003aa0b`
- `ntdll!EtwEventWriteTransfer` at `0x18003a490`
- `ntdll!EtwEventWriteTransfer` at `0x18003aa0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a899`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a899`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18003a814`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18003a814`

## string_xrefs

- `0x18003a82a`: `TrySubmitThreadpoolCallback`

## pseudocode

```c
__int64 __fastcall IkePostAcquire(__int64 a1)
{
  __int64 v2; // rsi
  LPCRITICAL_SECTION v3; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v6; // rcx
  DWORD v7; // ecx
  char *v8; // rax
  const WCHAR *v9; // rdx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  __int64 v13; // rax
  char *v14; // rbx
  __int64 v15; // r14
  HANDLE *v16; // r15
  HANDLE *v17; // r12
  __int64 v18; // rax
  __int128 v19; // xmm0
  __int64 v20; // rcx
  _BYTE *v21; // rax
  __int64 v22; // rdx
  _BYTE *v23; // rcx
  __int64 v24; // r8
  _BYTE *v25; // rax
  DWORD LastError; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  LPCRITICAL_SECTION v29; // rax
  DWORD v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // rcx
  DWORD v33; // ecx
  char *v34; // rax
  const WCHAR *v35; // rdx
  int v36; // esi
  PVOID pv; // [rsp+38h] [rbp-71h] BYREF
  __int64 v39; // [rsp+40h] [rbp-69h] BYREF
  int v40; // [rsp+48h] [rbp-61h] BYREF
  int v41; // [rsp+4Ch] [rbp-5Dh]
  __int64 v42; // [rsp+50h] [rbp-59h]
  char *v43; // [rsp+60h] [rbp-49h] BYREF
  int v44; // [rsp+68h] [rbp-41h]
  int v45; // [rsp+6Ch] [rbp-3Dh]
  int *v46; // [rsp+70h] [rbp-39h]
  int v47; // [rsp+78h] [rbp-31h]
  int v48; // [rsp+7Ch] [rbp-2Dh]
  __int64 *v49; // [rsp+80h] [rbp-29h]
  __int64 v50; // [rsp+88h] [rbp-21h]
  const WCHAR *v51; // [rsp+90h] [rbp-19h]
  int v52; // [rsp+98h] [rbp-11h]
  int v53; // [rsp+9Ch] [rbp-Dh]
  const char *v54; // [rsp+A0h] [rbp-9h]
  __int64 v55; // [rsp+A8h] [rbp-1h]

  pv = 0;
  v2 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v3 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v3 = gIkeExtGlobals;
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  v6 = *Value;
  v3 = gIkeExtGlobals;
LABEL_10:
  v39 = v6;
  v49 = &v39;
  v50 = 8;
  if ( !v3 )
    goto LABEL_18;
  v7 = (DWORD)v3[86].LockSemaphore;
  if ( v7 == -1 )
    goto LABEL_18;
  v8 = (char *)TlsGetValue(v7);
  v9 = (const WCHAR *)(v8 + 8);
  if ( !v8 )
    v9 = 0;
  if ( v9 )
  {
    v10 = -1;
    do
      v11 = v9[++v10] == 0;
    while ( !v11 );
    v12 = 2 * v10 + 2;
  }
  else
  {
LABEL_18:
    v9 = &LocaleName;
    v12 = 2;
  }
  v52 = v12;
  v41 = 5;
  v43 = off_180173280;
  v51 = v9;
  v53 = 0;
  v54 = "IkePostAcquire";
  v55 = 15;
  v40 = 184549376;
  v42 = 1;
  v44 = *(unsigned __int16 *)off_180173280;
  v46 = &dword_180166EA4;
  v45 = 2;
  v47 = 45;
  v48 = 1;
  EtwEventWriteTransfer(qword_180173298, &v40, 0, 0, 5, &v43);
LABEL_20:
  v13 = WfpMemAlloc(0x250u, 8u, &pv);
  v14 = (char *)pv;
  v15 = v13;
  if ( v13 )
    goto LABEL_43;
  v16 = (HANDLE *)(a1 + 400);
  *((_QWORD *)pv + 45) = *(_QWORD *)(a1 + 360);
  *((_DWORD *)v14 + 92) = *(_DWORD *)(a1 + 368);
  *((_DWORD *)v14 + 93) = *(_DWORD *)(a1 + 372);
  *((_DWORD *)v14 + 94) = *(_DWORD *)(a1 + 376);
  *(_OWORD *)(v14 + 472) = *(_OWORD *)(a1 + 472);
  *(_OWORD *)(v14 + 488) = *(_OWORD *)(a1 + 488);
  *(_OWORD *)(v14 + 504) = *(_OWORD *)(a1 + 504);
  *(_OWORD *)(v14 + 520) = *(_OWORD *)(a1 + 520);
  *((_DWORD *)v14 + 146) = *(_DWORD *)(a1 + 584);
  *((_QWORD *)v14 + 50) = *(_QWORD *)(a1 + 400);
  *(_QWORD *)(a1 + 400) = 0;
  v17 = (HANDLE *)(a1 + 408);
  *((_QWORD *)v14 + 51) = *(_QWORD *)(a1 + 408);
  v18 = *(_QWORD *)(a1 + 416);
  *(_QWORD *)(a1 + 408) = 0;
  *((_QWORD *)v14 + 52) = v18;
  v19 = *(_OWORD *)(a1 + 424);
  *(_QWORD *)(a1 + 416) = 0;
  *(_OWORD *)(v14 + 424) = v19;
  *(_OWORD *)(a1 + 424) = 0;
  *(_OWORD *)(v14 + 440) = *(_OWORD *)(a1 + 440);
  *((_DWORD *)v14 + 147) = *(_DWORD *)(a1 + 588);
  *((_DWORD *)v14 + 114) = *(_DWORD *)(a1 + 456);
  *((_QWORD *)v14 + 58) = *(_QWORD *)(a1 + 464);
  *((_DWORD *)v14 + 134) = *(_DWORD *)(a1 + 536);
  *((_DWORD *)v14 + 135) = *(_DWORD *)(a1 + 540);
  *((_QWORD *)v14 + 68) = *(_QWORD *)(a1 + 544);
  *((_DWORD *)v14 + 138) = *(_DWORD *)(a1 + 552);
  *((_DWORD *)v14 + 139) = *(_DWORD *)(a1 + 556);
  v20 = *(_QWORD *)(a1 + 392);
  if ( v20 )
  {
    v15 = IkeCopyIpsecId(v20, v14 + 392);
    if ( v15 )
      goto LABEL_43;
  }
  v21 = (_BYTE *)(a1 + 564);
  if ( a1 != -564 )
  {
    v22 = 20;
    v23 = v14 + 564;
    v24 = 2147483646;
    do
    {
      if ( !v24 )
        break;
      if ( !*v21 )
        break;
      *v23++ = *v21++;
      --v24;
      --v22;
    }
    while ( v22 );
    v25 = v23 - 1;
    if ( v22 )
      v25 = v23;
    *v25 = 0;
  }
  *((_OWORD *)v14 + 1) = *(_OWORD *)(a1 + 16);
  *((_OWORD *)v14 + 2) = *(_OWORD *)(a1 + 32);
  *((_OWORD *)v14 + 3) = *(_OWORD *)(a1 + 48);
  *((_OWORD *)v14 + 4) = *(_OWORD *)(a1 + 64);
  *((_OWORD *)v14 + 5) = *(_OWORD *)(a1 + 80);
  *((_OWORD *)v14 + 6) = *(_OWORD *)(a1 + 96);
  *((_OWORD *)v14 + 7) = *(_OWORD *)(a1 + 112);
  *((_OWORD *)v14 + 8) = *(_OWORD *)(a1 + 128);
  *((_OWORD *)v14 + 9) = *(_OWORD *)(a1 + 144);
  *((_OWORD *)v14 + 10) = *(_OWORD *)(a1 + 160);
  *((_QWORD *)v14 + 22) = *(_QWORD *)(a1 + 176);
  *(_OWORD *)(v14 + 184) = *(_OWORD *)(a1 + 184);
  *(_OWORD *)(v14 + 200) = *(_OWORD *)(a1 + 200);
  *(_OWORD *)(v14 + 216) = *(_OWORD *)(a1 + 216);
  *(_OWORD *)(v14 + 232) = *(_OWORD *)(a1 + 232);
  *(_OWORD *)(v14 + 248) = *(_OWORD *)(a1 + 248);
  *(_OWORD *)(v14 + 264) = *(_OWORD *)(a1 + 264);
  *(_OWORD *)(v14 + 280) = *(_OWORD *)(a1 + 280);
  *(_OWORD *)(v14 + 296) = *(_OWORD *)(a1 + 296);
  *(_OWORD *)(v14 + 312) = *(_OWORD *)(a1 + 312);
  *(_OWORD *)(v14 + 328) = *(_OWORD *)(a1 + 328);
  *(_OWORD *)(v14 + 344) = *(_OWORD *)(a1 + 344);
  if ( *(_QWORD *)(a1 + 160) )
  {
    *((_DWORD *)v14 + 38) = *(_DWORD *)(a1 + 152);
    *((_QWORD *)v14 + 20) = *(_QWORD *)(a1 + 160);
    *(_QWORD *)(a1 + 160) = v15;
  }
  if ( *(_QWORD *)(a1 + 344) )
  {
    *((_DWORD *)v14 + 84) = *(_DWORD *)(a1 + 336);
    *((_QWORD *)v14 + 43) = *(_QWORD *)(a1 + 344);
    *(_QWORD *)(a1 + 344) = v15;
  }
  if ( *((_DWORD *)v14 + 78) == 2 && (*((_DWORD *)v14 + 94) & 0x800) == 0 )
  {
    v15 = IkeQueueWorkItemHiPri(IkeHandleAcquireDispatch, v14);
    if ( !v15 )
      goto LABEL_44;
LABEL_43:
    IkeFreeAcquireContext(v14);
    v16 = (HANDLE *)(a1 + 400);
    v17 = (HANDLE *)(a1 + 408);
    goto LABEL_44;
  }
  if ( TrySubmitThreadpoolCallback(IkeHandleAcquireDispatch, v14, (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[76].LockCount) )
  {
    v28 = v15;
    _InterlockedIncrement((volatile signed __int32 *)&gIkeExtGlobals[48].SpinCount + 1);
  }
  else
  {
    LastError = GetLastError();
    v28 = WfpReportSysErrorAsWinError(v27, "TrySubmitThreadpoolCallback", LastError, 1);
  }
  v15 = IkeReturnError(v28, "IkeQueueWorkItem");
  if ( v15 )
    goto LABEL_43;
LABEL_44:
  if ( *v16 )
  {
    CloseHandle(*v16);
    *v16 = 0;
  }
  if ( *v17 )
  {
    CloseHandle(*v17);
    *v17 = 0;
  }
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v29 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v30 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v30 != -1 )
      {
        v31 = (__int64 *)TlsGetValue(v30);
        if ( v31 )
        {
          v32 = *v31;
          v29 = gIkeExtGlobals;
LABEL_57:
          v39 = v32;
          v49 = &v39;
          v50 = 8;
          if ( !v29 )
            goto LABEL_64;
          v33 = (DWORD)v29[86].LockSemaphore;
          if ( v33 == -1 )
            goto LABEL_64;
          v34 = (char *)TlsGetValue(v33);
          v35 = (const WCHAR *)(v34 + 8);
          if ( !v34 )
            v35 = 0;
          if ( v35 )
          {
            do
              v11 = v35[++v2] == 0;
            while ( !v11 );
            v36 = 2 * v2 + 2;
          }
          else
          {
LABEL_64:
            v35 = &LocaleName;
            v36 = 2;
          }
          v41 = 5;
          v43 = off_180173280;
          v51 = v35;
          v52 = v36;
          v53 = 0;
          v54 = "IkePostAcquire";
          v55 = 15;
          v40 = 184549376;
          v42 = 1;
          v44 = *(unsigned __int16 *)off_180173280;
          v46 = (int *)byte_180166E6B;
          v45 = 2;
          v47 = 45;
          v48 = 1;
          EtwEventWriteTransfer(qword_180173298, &v40, 0, 0, 5, &v43);
          return IkeReturnError(v15, "IkePostAcquire");
        }
        v29 = gIkeExtGlobals;
      }
    }
    v32 = 0;
    goto LABEL_57;
  }
  return IkeReturnError(v15, "IkePostAcquire");
}

```

## disassembly

```asm
0x18003a2e0  push    rbp
0x18003a2e2  push    rbx
0x18003a2e3  push    rsi
0x18003a2e4  push    rdi
0x18003a2e5  push    r12
0x18003a2e7  push    r13
0x18003a2e9  push    r14
0x18003a2eb  push    r15
0x18003a2ed  lea     rbp, [rsp-1Fh]
0x18003a2f2  sub     rsp, 0C8h
0x18003a2f9  mov     rax, cs:__security_cookie
0x18003a300  xor     rax, rsp
0x18003a303  mov     [rbp+57h+var_50], rax
0x18003a307  mov     eax, cs:dword_180173278
0x18003a30d  lea     rbx, aIkepostacquire; "IkePostAcquire"
0x18003a314  xor     r12d, r12d
0x18003a317  lea     r13, _TraceLoggingMetadataEnd
0x18003a31e  mov     [rbp+57h+pv], r12
0x18003a322  mov     rdi, rcx
0x18003a325  lea     r14, _TraceLoggingMetadata
0x18003a32c  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003a333  cmp     eax, 5
0x18003a336  jbe     loc_18003A496
0x18003a33c  mov     rcx, cs:qword_180173290
0x18003a343  mov     rax, cs:qword_180173288
0x18003a34a  test    al, 1
0x18003a34c  jz      loc_18003A496
0x18003a352  mov     rax, rcx
0x18003a355  and     eax, 1
0x18003a358  cmp     rax, rcx
0x18003a35b  jnz     loc_18003A496
0x18003a361  mov     rax, cs:gIkeExtGlobals
0x18003a368  test    rax, rax
0x18003a36b  jz      short loc_18003A396
0x18003a36d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003a373  cmp     ecx, 0FFFFFFFFh
0x18003a376  jz      short loc_18003A396
0x18003a378  call    cs:__imp_TlsGetValue
0x18003a37e  test    rax, rax
0x18003a381  jz      short loc_18003A38F
0x18003a383  mov     rcx, [rax]
0x18003a386  mov     rax, cs:gIkeExtGlobals
0x18003a38d  jmp     short loc_18003A399
0x18003a38f  mov     rax, cs:gIkeExtGlobals
0x18003a396  mov     rcx, r12
0x18003a399  mov     [rbp+57h+var_C0], rcx
0x18003a39d  lea     rcx, [rbp+57h+var_C0]
0x18003a3a1  mov     [rbp+57h+var_80], rcx
0x18003a3a5  mov     [rbp+57h+var_78], 8
0x18003a3ad  test    rax, rax
0x18003a3b0  jz      short loc_18003A3F5
0x18003a3b2  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18003a3b8  cmp     ecx, 0FFFFFFFFh
0x18003a3bb  jz      short loc_18003A3F5
0x18003a3bd  call    cs:__imp_TlsGetValue
0x18003a3c3  test    rax, rax
0x18003a3c6  lea     rdx, [rax+8]
0x18003a3ca  cmovz   rdx, r12
0x18003a3ce  test    rdx, rdx
0x18003a3d1  jz      short loc_18003A3F5
0x18003a3d3  mov     rax, rsi
0x18003a3d6  nop     word ptr [rax+rax+00000000h]
0x18003a3e0  cmp     [rdx+rax*2+2], r12w
0x18003a3e6  lea     rax, [rax+1]
0x18003a3ea  jnz     short loc_18003A3E0
0x18003a3ec  lea     eax, ds:2[rax*2]
0x18003a3f3  jmp     short loc_18003A401
0x18003a3f5  lea     rdx, LocaleName
0x18003a3fc  mov     eax, 2
0x18003a401  mov     [rbp+57h+var_68], eax
0x18003a404  xor     r9d, r9d
0x18003a407  movzx   eax, cs:word_180166E9A
0x18003a40e  xor     r8d, r8d
0x18003a411  mov     [rbp+57h+var_B4], eax
0x18003a414  mov     rax, cs:off_180173280
0x18003a41b  mov     [rbp+57h+var_A0], rax
0x18003a41f  mov     [rbp+57h+var_70], rdx
0x18003a423  lea     rdx, [rbp+57h+var_B8]
0x18003a427  mov     [rbp+57h+var_64], r12d
0x18003a42b  mov     [rbp+57h+var_60], rbx
0x18003a42f  mov     [rbp+57h+var_58], 0Fh
0x18003a437  mov     [rbp+57h+var_B8], 0B000000h
0x18003a43e  mov     [rbp+57h+var_B0], 1
0x18003a446  movzx   eax, word ptr [rax]
0x18003a449  mov     [rbp+57h+var_98], eax
0x18003a44c  lea     rax, dword_180166EA4
0x18003a453  mov     [rbp+57h+var_90], rax
0x18003a457  mov     rax, r13
0x18003a45a  sub     eax, r14d
0x18003a45d  mov     [rbp+57h+var_94], 2
0x18003a464  mov     [rbp+57h+var_88], 2Dh ; '-'
0x18003a46b  mov     [rbp+57h+var_84], 1
0x18003a472  mov     [rbp+57h+var_D0], eax
0x18003a475  mov     eax, [rbp+57h+var_D0]
0x18003a478  mov     rcx, cs:qword_180173298
0x18003a47f  lea     rax, [rbp+57h+var_A0]
0x18003a483  mov     [rsp+100h+var_D8], rax
0x18003a488  mov     [rsp+100h+var_E0], 5
0x18003a490  call    cs:__imp_EtwEventWriteTransfer
0x18003a496  lea     r8, [rbp+57h+pv]
0x18003a49a  mov     edx, 8; dwFlags
0x18003a49f  mov     ecx, 250h; dwBytes
0x18003a4a4  call    WfpMemAlloc
0x18003a4a9  mov     rbx, [rbp+57h+pv]
0x18003a4ad  mov     r14, rax
0x18003a4b0  test    rax, rax
0x18003a4b3  jnz     loc_18003A863
0x18003a4b9  mov     rax, [rdi+168h]
0x18003a4c0  lea     r15, [rdi+190h]
0x18003a4c7  mov     [rbx+168h], rax
0x18003a4ce  mov     eax, [rdi+170h]
0x18003a4d4  mov     [rbx+170h], eax
0x18003a4da  mov     eax, [rdi+174h]
0x18003a4e0  mov     [rbx+174h], eax
0x18003a4e6  mov     eax, [rdi+178h]
0x18003a4ec  mov     [rbx+178h], eax
0x18003a4f2  movups  xmm0, xmmword ptr [rdi+1D8h]
0x18003a4f9  movups  xmmword ptr [rbx+1D8h], xmm0
0x18003a500  movups  xmm1, xmmword ptr [rdi+1E8h]
0x18003a507  movups  xmmword ptr [rbx+1E8h], xmm1
0x18003a50e  movups  xmm0, xmmword ptr [rdi+1F8h]
0x18003a515  movups  xmmword ptr [rbx+1F8h], xmm0
0x18003a51c  movups  xmm1, xmmword ptr [rdi+208h]
0x18003a523  movups  xmmword ptr [rbx+208h], xmm1
0x18003a52a  mov     eax, [rdi+248h]
0x18003a530  mov     [rbx+248h], eax
0x18003a536  xorps   xmm1, xmm1
0x18003a539  mov     rax, [r15]
0x18003a53c  mov     [rbx+190h], rax
0x18003a543  mov     [r15], r12
0x18003a546  lea     r12, [rdi+198h]
0x18003a54d  mov     rax, [r12]
0x18003a551  mov     [rbx+198h], rax
0x18003a558  mov     rax, [rdi+1A0h]
0x18003a55f  mov     [r12], r14
0x18003a563  mov     [rbx+1A0h], rax
0x18003a56a  movups  xmm0, xmmword ptr [rdi+1A8h]
0x18003a571  mov     [rdi+1A0h], r14
0x18003a578  movups  xmmword ptr [rbx+1A8h], xmm0
0x18003a57f  movups  xmmword ptr [rdi+1A8h], xmm1
0x18003a586  movups  xmm0, xmmword ptr [rdi+1B8h]
0x18003a58d  movups  xmmword ptr [rbx+1B8h], xmm0
0x18003a594  mov     eax, [rdi+24Ch]
0x18003a59a  mov     [rbx+24Ch], eax
0x18003a5a0  mov     eax, [rdi+1C8h]
0x18003a5a6  mov     [rbx+1C8h], eax
0x18003a5ac  mov     rax, [rdi+1D0h]
0x18003a5b3  mov     [rbx+1D0h], rax
0x18003a5ba  mov     eax, [rdi+218h]
0x18003a5c0  mov     [rbx+218h], eax
0x18003a5c6  mov     eax, [rdi+21Ch]
0x18003a5cc  mov     [rbx+21Ch], eax
0x18003a5d2  mov     rax, [rdi+220h]
0x18003a5d9  mov     [rbx+220h], rax
0x18003a5e0  mov     eax, [rdi+228h]
0x18003a5e6  mov     [rbx+228h], eax
0x18003a5ec  mov     eax, [rdi+22Ch]
0x18003a5f2  mov     [rbx+22Ch], eax
0x18003a5f8  mov     rcx, [rdi+188h]
0x18003a5ff  test    rcx, rcx
0x18003a602  jz      short loc_18003A61C
0x18003a604  lea     rdx, [rbx+188h]
0x18003a60b  call    IkeCopyIpsecId
0x18003a610  mov     r14, rax
0x18003a613  test    rax, rax
0x18003a616  jnz     loc_18003A863
0x18003a61c  lea     rax, [rdi+234h]
0x18003a623  test    rax, rax
0x18003a626  jz      short loc_18003A66E
0x18003a628  mov     edx, 14h
0x18003a62d  lea     rcx, [rbx+234h]
0x18003a634  mov     r8d, 7FFFFFFEh
0x18003a63a  nop     word ptr [rax+rax+00h]
0x18003a640  test    r8, r8
0x18003a643  jz      short loc_18003A660
0x18003a645  movzx   r9d, byte ptr [rax]
0x18003a649  test    r9b, r9b
0x18003a64c  jz      short loc_18003A660
0x18003a64e  mov     [rcx], r9b
0x18003a651  inc     rax
0x18003a654  inc     rcx
0x18003a657  dec     r8
0x18003a65a  sub     rdx, 1
0x18003a65e  jnz     short loc_18003A640
0x18003a660  test    rdx, rdx
0x18003a663  lea     rax, [rcx-1]
0x18003a667  cmovnz  rax, rcx
0x18003a66b  mov     byte ptr [rax], 0
0x18003a66e  movups  xmm0, xmmword ptr [rdi+10h]
0x18003a672  movups  xmmword ptr [rbx+10h], xmm0
0x18003a676  movups  xmm1, xmmword ptr [rdi+20h]
0x18003a67a  movups  xmmword ptr [rbx+20h], xmm1
0x18003a67e  movups  xmm0, xmmword ptr [rdi+30h]
0x18003a682  movups  xmmword ptr [rbx+30h], xmm0
0x18003a686  movups  xmm1, xmmword ptr [rdi+40h]
0x18003a68a  movups  xmmword ptr [rbx+40h], xmm1
0x18003a68e  movups  xmm0, xmmword ptr [rdi+50h]
0x18003a692  movups  xmmword ptr [rbx+50h], xmm0
0x18003a696  movups  xmm1, xmmword ptr [rdi+60h]
0x18003a69a  movups  xmmword ptr [rbx+60h], xmm1
0x18003a69e  movups  xmm0, xmmword ptr [rdi+70h]
0x18003a6a2  movups  xmmword ptr [rbx+70h], xmm0
0x18003a6a6  movups  xmm1, xmmword ptr [rdi+80h]
0x18003a6ad  movups  xmmword ptr [rbx+80h], xmm1
0x18003a6b4  movups  xmm0, xmmword ptr [rdi+90h]
0x18003a6bb  movups  xmmword ptr [rbx+90h], xmm0
0x18003a6c2  movups  xmm1, xmmword ptr [rdi+0A0h]
0x18003a6c9  movups  xmmword ptr [rbx+0A0h], xmm1
0x18003a6d0  mov     rax, [rdi+0B0h]
0x18003a6d7  mov     [rbx+0B0h], rax
0x18003a6de  movups  xmm0, xmmword ptr [rdi+0B8h]
0x18003a6e5  movups  xmmword ptr [rbx+0B8h], xmm0
0x18003a6ec  movups  xmm1, xmmword ptr [rdi+0C8h]
0x18003a6f3  movups  xmmword ptr [rbx+0C8h], xmm1
0x18003a6fa  movups  xmm0, xmmword ptr [rdi+0D8h]
0x18003a701  movups  xmmword ptr [rbx+0D8h], xmm0
0x18003a708  movups  xmm1, xmmword ptr [rdi+0E8h]
0x18003a70f  movups  xmmword ptr [rbx+0E8h], xmm1
0x18003a716  movups  xmm0, xmmword ptr [rdi+0F8h]
0x18003a71d  movups  xmmword ptr [rbx+0F8h], xmm0
0x18003a724  movups  xmm1, xmmword ptr [rdi+108h]
0x18003a72b  movups  xmmword ptr [rbx+108h], xmm1
0x18003a732  movups  xmm0, xmmword ptr [rdi+118h]
0x18003a739  movups  xmmword ptr [rbx+118h], xmm0
0x18003a740  movups  xmm1, xmmword ptr [rdi+128h]
0x18003a747  movups  xmmword ptr [rbx+128h], xmm1
0x18003a74e  movups  xmm0, xmmword ptr [rdi+138h]
0x18003a755  movups  xmmword ptr [rbx+138h], xmm0
0x18003a75c  movups  xmm1, xmmword ptr [rdi+148h]
0x18003a763  movups  xmmword ptr [rbx+148h], xmm1
0x18003a76a  movups  xmm0, xmmword ptr [rdi+158h]
0x18003a771  movups  xmmword ptr [rbx+158h], xmm0
0x18003a778  cmp     qword ptr [rdi+0A0h], 0
0x18003a780  jz      short loc_18003A7A3
0x18003a782  mov     eax, [rdi+98h]
0x18003a788  mov     [rbx+98h], eax
0x18003a78e  mov     rax, [rdi+0A0h]
0x18003a795  mov     [rbx+0A0h], rax
0x18003a79c  mov     [rdi+0A0h], r14
0x18003a7a3  cmp     qword ptr [rdi+158h], 0
0x18003a7ab  jz      short loc_18003A7CE
0x18003a7ad  mov     eax, [rdi+150h]
0x18003a7b3  mov     [rbx+150h], eax
0x18003a7b9  mov     rax, [rdi+158h]
0x18003a7c0  mov     [rbx+158h], rax
0x18003a7c7  mov     [rdi+158h], r14
0x18003a7ce  cmp     dword ptr [rbx+138h], 2
0x18003a7d5  jnz     short loc_18003A7FC
0x18003a7d7  test    dword ptr [rbx+178h], 800h
0x18003a7e1  jnz     short loc_18003A7FC
0x18003a7e3  mov     rdx, rbx; pv
0x18003a7e6  lea     rcx, IkeHandleAcquireDispatch; pfns
0x18003a7ed  call    IkeQueueWorkItemHiPri
0x18003a7f2  mov     r14, rax
0x18003a7f5  test    rax, rax
0x18003a7f8  jnz     short loc_18003A863
0x18003a7fa  jmp     short loc_18003A879
0x18003a7fc  mov     r8, cs:gIkeExtGlobals
0x18003a803  lea     rcx, IkeHandleAcquireDispatch; pfns
0x18003a80a  add     r8, 0BE8h; pcbe
0x18003a811  mov     rdx, rbx; pv
0x18003a814  call    cs:__imp_TrySubmitThreadpoolCallback
0x18003a81a  test    eax, eax
0x18003a81c  jnz     short loc_18003A83E
0x18003a81e  call    cs:__imp_GetLastError
0x18003a824  mov     r9d, 1
0x18003a82a  lea     rdx, aTrysubmitthrea; "TrySubmitThreadpoolCallback"
0x18003a831  mov     r8d, eax
0x18003a834  call    WfpReportSysErrorAsWinError
0x18003a839  mov     rcx, rax
0x18003a83c  jmp     short loc_18003A84F
0x18003a83e  mov     rax, cs:gIkeExtGlobals
0x18003a845  mov     rcx, r14
0x18003a848  lock inc dword ptr [rax+7A4h]
0x18003a84f  lea     rdx, aIkequeueworkit_0; "IkeQueueWorkItem"
0x18003a856  call    IkeReturnError
0x18003a85b  mov     r14, rax
0x18003a85e  test    rax, rax
0x18003a861  jz      short loc_18003A879
0x18003a863  mov     rcx, rbx
0x18003a866  call    IkeFreeAcquireContext
0x18003a86b  lea     r15, [rdi+190h]
0x18003a872  lea     r12, [rdi+198h]
0x18003a879  mov     rcx, [r15]; hObject
0x18003a87c  test    rcx, rcx
0x18003a87f  jz      short loc_18003A88E
0x18003a881  call    cs:__imp_CloseHandle
0x18003a887  xor     ebx, ebx
0x18003a889  mov     [r15], rbx
0x18003a88c  jmp     short loc_18003A890
0x18003a88e  xor     ebx, ebx
0x18003a890  mov     rcx, [r12]; hObject
0x18003a894  test    rcx, rcx
0x18003a897  jz      short loc_18003A8A3
0x18003a899  call    cs:__imp_CloseHandle
0x18003a89f  mov     [r12], rbx
0x18003a8a3  mov     eax, cs:dword_180173278
0x18003a8a9  cmp     eax, 5
0x18003a8ac  jbe     loc_18003AA13
0x18003a8b2  mov     rcx, cs:qword_180173290
  ... truncated ...
```
