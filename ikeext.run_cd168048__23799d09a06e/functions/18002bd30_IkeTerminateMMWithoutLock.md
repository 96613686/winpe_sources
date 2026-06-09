# IkeTerminateMMWithoutLock

- ea: `0x18002bd30`
- end: `0x18002c32f`
- name: `IkeTerminateMMWithoutLock`
- size: `1535`
- prototype: ``
- caller_count: `19`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180002a40`
- `0x18000c880`
- `0x180014078`
- `0x18001c3f8`
- `0x1800226a0`
- `0x1800238b0`
- `0x180025110`
- `0x18002b2f0`
- `0x18002b788`
- `0x18003d320`
- `0x18006a890`
- `0x18006cfd4`
- `0x1800c86fc`
- `0x1800cbd10`
- `0x1800cbf20`
- `0x1800cc630`
- `0x1800ccb80`
- `0x1800cd260`
- `0x1800e0590`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x180025d88`
- `0x18002ba1c`
- `0x18002bd30`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bdd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002be1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bf61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bfa0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c004`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c049`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c1f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c23c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bdd5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002be1a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bf61`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002bfa0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c004`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c049`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c1f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002c23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c16f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c16f`
- `ntdll!EtwEventWriteTransfer` at `0x18002bef0`
- `ntdll!EtwEventWriteTransfer` at `0x18002c131`
- `ntdll!EtwEventWriteTransfer` at `0x18002c309`
- `ntdll!EtwEventWriteTransfer` at `0x18002bef0`
- `ntdll!EtwEventWriteTransfer` at `0x18002c131`
- `ntdll!EtwEventWriteTransfer` at `0x18002c309`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002c165`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18002c165`

## string_xrefs

- `0x18002c17b`: `TrySubmitThreadpoolCallback`

## pseudocode

```c
__int64 __fastcall IkeTerminateMMWithoutLock(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v8; // rbx
  LPCRITICAL_SECTION v9; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v12; // rcx
  DWORD v13; // ecx
  char *v14; // rax
  const WCHAR *v15; // rdx
  __int64 v16; // rax
  bool v17; // zf
  int v18; // eax
  int v19; // esi
  _QWORD *v20; // rcx
  LPCRITICAL_SECTION v21; // rdx
  DWORD v22; // eax
  LPVOID v23; // rax
  LPVOID v24; // r8
  __int64 v25; // rdi
  DWORD v26; // eax
  __int64 *v27; // rax
  __int64 v28; // r9
  LPCRITICAL_SECTION v29; // rax
  DWORD v30; // ecx
  __int64 *v31; // rax
  __int64 v32; // rcx
  DWORD v33; // ecx
  char *v34; // rax
  const WCHAR *v35; // rdx
  __int64 v36; // rax
  int v37; // eax
  DWORD LastError; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 result; // rax
  LPCRITICAL_SECTION v42; // rax
  DWORD v43; // ecx
  __int64 *v44; // rax
  __int64 v45; // rcx
  DWORD v46; // ecx
  char *v47; // rax
  const WCHAR *v48; // rdx
  int v49; // ebx
  _QWORD v50[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+58h] [rbp-A8h]
  int v52; // [rsp+5Ch] [rbp-A4h]
  __int64 v53; // [rsp+60h] [rbp-A0h]
  int v54; // [rsp+68h] [rbp-98h]
  int v55; // [rsp+6Ch] [rbp-94h]
  __int128 v56; // [rsp+70h] [rbp-90h]
  _QWORD v57[2]; // [rsp+80h] [rbp-80h] BYREF
  char *v58; // [rsp+90h] [rbp-70h] BYREF
  int v59; // [rsp+98h] [rbp-68h]
  int v60; // [rsp+9Ch] [rbp-64h]
  int *v61; // [rsp+A0h] [rbp-60h]
  int v62; // [rsp+A8h] [rbp-58h]
  int v63; // [rsp+ACh] [rbp-54h]
  _QWORD *v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  const WCHAR *v66; // [rsp+C0h] [rbp-40h]
  int v67; // [rsp+C8h] [rbp-38h]
  int v68; // [rsp+CCh] [rbp-34h]
  const char *v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  _QWORD *v71; // [rsp+E0h] [rbp-20h]
  __int64 v72; // [rsp+E8h] [rbp-18h]
  _QWORD v73[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v74; // [rsp+100h] [rbp+0h] BYREF
  int v75; // [rsp+104h] [rbp+4h]
  __int64 v76; // [rsp+108h] [rbp+8h]

  v50[0] = 0;
  v50[1] = 0;
  v52 = 0;
  v56 = 0;
  v8 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v9 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v9 = gIkeExtGlobals;
LABEL_9:
    v12 = 0;
    goto LABEL_10;
  }
  v12 = *Value;
  v9 = gIkeExtGlobals;
LABEL_10:
  v57[0] = v12;
  v64 = v57;
  v65 = 8;
  if ( !v9 )
    goto LABEL_18;
  v13 = (DWORD)v9[86].LockSemaphore;
  if ( v13 == -1 )
    goto LABEL_18;
  v14 = (char *)TlsGetValue(v13);
  v15 = (const WCHAR *)(v14 + 8);
  if ( !v14 )
    v15 = 0;
  if ( v15 )
  {
    v16 = -1;
    do
      v17 = v15[++v16] == 0;
    while ( !v17 );
    v18 = 2 * v16 + 2;
  }
  else
  {
LABEL_18:
    v15 = &LocaleName;
    v18 = 2;
  }
  v67 = v18;
  v66 = v15;
  v69 = "IkeTerminateMMWithoutLock";
  v58 = off_180173280;
  v68 = 0;
  v70 = 26;
  v73[0] = 0x50B000000LL;
  v73[1] = 1;
  v59 = *(unsigned __int16 *)off_180173280;
  v61 = &dword_180166EA4;
  v60 = 2;
  v62 = 45;
  v63 = 1;
  EtwEventWriteTransfer(qword_180173298, v73, 0, 0, 5, &v58);
LABEL_20:
  v50[2] = a1;
  v53 = a2;
  v19 = a3 & 0x40;
  v54 = a3;
  v55 = a4;
  v51 = (v19 != 0) + 2;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v21 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v22 == -1) )
    {
      v24 = 0;
    }
    else
    {
      v23 = TlsGetValue(v22);
      v20 = WPP_GLOBAL_Control;
      v21 = gIkeExtGlobals;
      v24 = v23;
    }
    v25 = (__int64)v24 + 8;
    if ( !v24 )
      v25 = 0;
    if ( v21
      && (v26 = (DWORD)v21[86].LockSemaphore, v26 != -1)
      && (v27 = (__int64 *)TlsGetValue(v26), v20 = WPP_GLOBAL_Control, v27) )
    {
      v28 = *v27;
    }
    else
    {
      LODWORD(v28) = 0;
    }
    WPP_SF_iSq(v20[2], 56, (unsigned int)WPP_27bc70e61d40360834a5a0166f146b13_Traceguids, v28, v25, a1);
  }
  if ( (unsigned int)dword_180173278 > 2 )
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
LABEL_42:
          v57[0] = v32;
          v64 = v57;
          v65 = 8;
          if ( !v29 )
            goto LABEL_50;
          v33 = (DWORD)v29[86].LockSemaphore;
          if ( v33 == -1 )
            goto LABEL_50;
          v34 = (char *)TlsGetValue(v33);
          v35 = (const WCHAR *)(v34 + 8);
          if ( !v34 )
            v35 = 0;
          if ( v35 )
          {
            v36 = -1;
            do
              v17 = v35[++v36] == 0;
            while ( !v17 );
            v37 = 2 * v36 + 2;
          }
          else
          {
LABEL_50:
            v35 = &LocaleName;
            v37 = 2;
          }
          v67 = v37;
          v66 = v35;
          v69 = "Queuing invalidation of MM SA";
          v68 = 0;
          v71 = v73;
          v75 = 2;
          v58 = off_180173280;
          v70 = 30;
          v73[0] = a1;
          v72 = 8;
          v74 = 184549376;
          v76 = 0;
          v59 = *(unsigned __int16 *)off_180173280;
          v61 = &dword_180152114;
          v60 = 2;
          v62 = 53;
          v63 = 1;
          EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 6, &v58);
          goto LABEL_52;
        }
        v29 = gIkeExtGlobals;
      }
    }
    v32 = 0;
    goto LABEL_42;
  }
LABEL_52:
  IkeQueuePostponedWorkEntry(v50, a2);
  if ( v19 )
  {
    if ( TrySubmitThreadpoolCallback(IkeHandlePostponedWork, 0, (PTP_CALLBACK_ENVIRON)&gIkeExtGlobals[76].LockCount) )
    {
      v40 = 0;
      _InterlockedIncrement((volatile signed __int32 *)&gIkeExtGlobals[48].SpinCount + 1);
    }
    else
    {
      LastError = GetLastError();
      v40 = WfpReportSysErrorAsWinError(v39, "TrySubmitThreadpoolCallback", LastError, 1);
    }
    IkeReturnError(v40, "IkeQueueWorkItem");
  }
  result = (unsigned int)dword_180173278;
  if ( (unsigned int)dword_180173278 > 5 )
  {
    result = qword_180173288;
    if ( (qword_180173288 & 1) != 0 )
    {
      result = qword_180173290 & 1;
      if ( result == qword_180173290 )
      {
        v42 = gIkeExtGlobals;
        if ( gIkeExtGlobals )
        {
          v43 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v43 != -1 )
          {
            v44 = (__int64 *)TlsGetValue(v43);
            if ( v44 )
            {
              v45 = *v44;
              v42 = gIkeExtGlobals;
LABEL_66:
              v73[0] = v45;
              v64 = v73;
              v65 = 8;
              if ( !v42 )
                goto LABEL_73;
              v46 = (DWORD)v42[86].LockSemaphore;
              if ( v46 == -1 )
                goto LABEL_73;
              v47 = (char *)TlsGetValue(v46);
              v48 = (const WCHAR *)(v47 + 8);
              if ( !v47 )
                v48 = 0;
              if ( v48 )
              {
                do
                  v17 = v48[++v8] == 0;
                while ( !v17 );
                v49 = 2 * v8 + 2;
              }
              else
              {
LABEL_73:
                v48 = &LocaleName;
                v49 = 2;
              }
              v66 = v48;
              v69 = "IkeTerminateMMWithoutLock";
              v75 = 5;
              v58 = off_180173280;
              v67 = v49;
              v68 = 0;
              v70 = 26;
              v74 = 184549376;
              v76 = 1;
              v59 = *(unsigned __int16 *)off_180173280;
              v61 = (int *)byte_180166E6B;
              v60 = 2;
              v62 = 45;
              v63 = 1;
              return EtwEventWriteTransfer(qword_180173298, &v74, 0, 0, 5, &v58);
            }
            v42 = gIkeExtGlobals;
          }
        }
        v45 = 0;
        goto LABEL_66;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002bd30  push    rbp
0x18002bd32  push    rbx
0x18002bd33  push    rsi
0x18002bd34  push    rdi
0x18002bd35  push    r12
0x18002bd37  push    r13
0x18002bd39  push    r14
0x18002bd3b  push    r15
0x18002bd3d  lea     rbp, [rsp-28h]
0x18002bd42  sub     rsp, 128h
0x18002bd49  mov     rax, cs:__security_cookie
0x18002bd50  xor     rax, rsp
0x18002bd53  mov     [rbp+60h+var_50], rax
0x18002bd57  mov     eax, cs:dword_180173278
0x18002bd5d  lea     r13, _TraceLoggingMetadataEnd
0x18002bd64  xor     esi, esi
0x18002bd66  xorps   xmm0, xmm0
0x18002bd69  mov     [rsp+160h+var_120], rsi
0x18002bd6e  mov     r15d, r9d
0x18002bd71  mov     [rsp+160h+var_118], rsi
0x18002bd76  mov     edi, r8d
0x18002bd79  mov     [rsp+160h+var_104], esi
0x18002bd7d  mov     r14, rdx
0x18002bd80  movdqa  [rsp+160h+var_F0], xmm0
0x18002bd86  mov     r12, rcx
0x18002bd89  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002bd90  cmp     eax, 5
0x18002bd93  jbe     loc_18002BEF6
0x18002bd99  mov     rcx, cs:qword_180173290
0x18002bda0  mov     rax, cs:qword_180173288
0x18002bda7  test    al, 1
0x18002bda9  jz      loc_18002BEF6
0x18002bdaf  mov     rax, rcx
0x18002bdb2  and     eax, 1
0x18002bdb5  cmp     rax, rcx
0x18002bdb8  jnz     loc_18002BEF6
0x18002bdbe  mov     rax, cs:gIkeExtGlobals
0x18002bdc5  test    rax, rax
0x18002bdc8  jz      short loc_18002BDF3
0x18002bdca  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002bdd0  cmp     ecx, 0FFFFFFFFh
0x18002bdd3  jz      short loc_18002BDF3
0x18002bdd5  call    cs:__imp_TlsGetValue
0x18002bddb  test    rax, rax
0x18002bdde  jz      short loc_18002BDEC
0x18002bde0  mov     rcx, [rax]
0x18002bde3  mov     rax, cs:gIkeExtGlobals
0x18002bdea  jmp     short loc_18002BDF6
0x18002bdec  mov     rax, cs:gIkeExtGlobals
0x18002bdf3  mov     rcx, rsi
0x18002bdf6  mov     [rbp+60h+var_E0], rcx
0x18002bdfa  lea     rcx, [rbp+60h+var_E0]
0x18002bdfe  mov     [rbp+60h+var_B0], rcx
0x18002be02  mov     [rbp+60h+var_A8], 8
0x18002be0a  test    rax, rax
0x18002be0d  jz      short loc_18002BE47
0x18002be0f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002be15  cmp     ecx, 0FFFFFFFFh
0x18002be18  jz      short loc_18002BE47
0x18002be1a  call    cs:__imp_TlsGetValue
0x18002be20  test    rax, rax
0x18002be23  lea     rdx, [rax+8]
0x18002be27  cmovz   rdx, rsi
0x18002be2b  test    rdx, rdx
0x18002be2e  jz      short loc_18002BE47
0x18002be30  mov     rax, rbx
0x18002be33  cmp     [rdx+rax*2+2], si
0x18002be38  lea     rax, [rax+1]
0x18002be3c  jnz     short loc_18002BE33
0x18002be3e  lea     eax, ds:2[rax*2]
0x18002be45  jmp     short loc_18002BE53
0x18002be47  lea     rdx, LocaleName
0x18002be4e  mov     eax, 2
0x18002be53  mov     [rbp+60h+var_98], eax
0x18002be56  lea     rcx, _TraceLoggingMetadata
0x18002be5d  mov     [rbp+60h+var_A0], rdx
0x18002be61  lea     rax, aIketerminatemm; "IkeTerminateMMWithoutLock"
0x18002be68  mov     [rbp+60h+var_90], rax
0x18002be6c  lea     rdx, [rbp+60h+var_70]
0x18002be70  movzx   eax, cs:word_180166E9A
0x18002be77  xor     r9d, r9d
0x18002be7a  mov     dword ptr [rbp+60h+var_70+4], eax
0x18002be7d  xor     r8d, r8d
0x18002be80  mov     rax, cs:off_180173280
0x18002be87  mov     [rbp+60h+var_D0], rax
0x18002be8b  mov     [rbp+60h+var_94], esi
0x18002be8e  mov     [rbp+60h+var_88], 1Ah
0x18002be96  mov     dword ptr [rbp+60h+var_70], 0B000000h
0x18002be9d  mov     [rbp+60h+var_68], 1
0x18002bea5  movzx   eax, word ptr [rax]
0x18002bea8  mov     [rbp+60h+var_C8], eax
0x18002beab  lea     rax, dword_180166EA4
0x18002beb2  mov     [rbp+60h+var_C0], rax
0x18002beb6  mov     rax, r13
0x18002beb9  sub     eax, ecx
0x18002bebb  mov     [rbp+60h+var_C4], 2
0x18002bec2  mov     [rbp+60h+var_B8], 2Dh ; '-'
0x18002bec9  mov     [rbp+60h+var_B4], 1
0x18002bed0  mov     [rsp+160h+var_130], eax
0x18002bed4  mov     eax, [rsp+160h+var_130]
0x18002bed8  mov     rcx, cs:qword_180173298
0x18002bedf  lea     rax, [rbp+60h+var_D0]
0x18002bee3  mov     [rsp+160h+var_138], rax
0x18002bee8  mov     dword ptr [rsp+160h+var_140], 5
0x18002bef0  call    cs:__imp_EtwEventWriteTransfer
0x18002bef6  mov     eax, 0
0x18002befb  mov     [rsp+160h+var_110], r12
0x18002bf00  mov     esi, edi
0x18002bf02  mov     [rsp+160h+var_100], r14
0x18002bf07  and     esi, 40h
0x18002bf0a  mov     [rsp+160h+var_F8], edi
0x18002bf0e  mov     [rsp+160h+var_F4], r15d
0x18002bf13  setnz   al
0x18002bf16  add     eax, 2
0x18002bf19  mov     [rsp+160h+var_108], eax
0x18002bf1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf24  lea     rax, WPP_GLOBAL_Control
0x18002bf2b  cmp     rcx, rax
0x18002bf2e  jz      loc_18002BFDB
0x18002bf34  cmp     byte ptr [rcx+19h], 4
0x18002bf38  jb      loc_18002BFDB
0x18002bf3e  test    byte ptr [rcx+1Ch], 10h
0x18002bf42  jz      loc_18002BFDB
0x18002bf48  mov     rdx, cs:gIkeExtGlobals
0x18002bf4f  test    rdx, rdx
0x18002bf52  jz      short loc_18002BF7D
0x18002bf54  mov     eax, [rdx+0D88h]
0x18002bf5a  cmp     eax, 0FFFFFFFFh
0x18002bf5d  jz      short loc_18002BF7D
0x18002bf5f  mov     ecx, eax; dwTlsIndex
0x18002bf61  call    cs:__imp_TlsGetValue
0x18002bf67  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bf6e  xor     r14d, r14d
0x18002bf71  mov     rdx, cs:gIkeExtGlobals
0x18002bf78  mov     r8, rax
0x18002bf7b  jmp     short loc_18002BF83
0x18002bf7d  xor     r14d, r14d
0x18002bf80  mov     r8d, r14d
0x18002bf83  test    r8, r8
0x18002bf86  lea     rdi, [r8+8]
0x18002bf8a  cmovz   rdi, r14
0x18002bf8e  test    rdx, rdx
0x18002bf91  jz      short loc_18002BFB7
0x18002bf93  mov     eax, [rdx+0D88h]
0x18002bf99  cmp     eax, 0FFFFFFFFh
0x18002bf9c  jz      short loc_18002BFB7
0x18002bf9e  mov     ecx, eax; dwTlsIndex
0x18002bfa0  call    cs:__imp_TlsGetValue
0x18002bfa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfad  test    rax, rax
0x18002bfb0  jz      short loc_18002BFB7
0x18002bfb2  mov     r9, [rax]
0x18002bfb5  jmp     short loc_18002BFBA
0x18002bfb7  mov     r9, r14
0x18002bfba  mov     rcx, [rcx+10h]
0x18002bfbe  lea     r8, WPP_27bc70e61d40360834a5a0166f146b13_Traceguids
0x18002bfc5  mov     edx, 38h ; '8'
0x18002bfca  mov     [rsp+160h+var_138], r12
0x18002bfcf  mov     [rsp+160h+var_140], rdi
0x18002bfd4  call    WPP_SF_iSq
0x18002bfd9  jmp     short loc_18002BFDE
0x18002bfdb  xor     r14d, r14d
0x18002bfde  mov     eax, cs:dword_180173278
0x18002bfe4  cmp     eax, 2
0x18002bfe7  jbe     loc_18002C139
0x18002bfed  mov     rax, cs:gIkeExtGlobals
0x18002bff4  test    rax, rax
0x18002bff7  jz      short loc_18002C022
0x18002bff9  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002bfff  cmp     ecx, 0FFFFFFFFh
0x18002c002  jz      short loc_18002C022
0x18002c004  call    cs:__imp_TlsGetValue
0x18002c00a  test    rax, rax
0x18002c00d  jz      short loc_18002C01B
0x18002c00f  mov     rcx, [rax]
0x18002c012  mov     rax, cs:gIkeExtGlobals
0x18002c019  jmp     short loc_18002C025
0x18002c01b  mov     rax, cs:gIkeExtGlobals
0x18002c022  mov     rcx, r14
0x18002c025  mov     [rbp+60h+var_E0], rcx
0x18002c029  lea     rcx, [rbp+60h+var_E0]
0x18002c02d  mov     [rbp+60h+var_B0], rcx
0x18002c031  mov     [rbp+60h+var_A8], 8
0x18002c039  test    rax, rax
0x18002c03c  jz      short loc_18002C077
0x18002c03e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c044  cmp     ecx, 0FFFFFFFFh
0x18002c047  jz      short loc_18002C077
0x18002c049  call    cs:__imp_TlsGetValue
0x18002c04f  test    rax, rax
0x18002c052  lea     rdx, [rax+8]
0x18002c056  cmovz   rdx, r14
0x18002c05a  test    rdx, rdx
0x18002c05d  jz      short loc_18002C077
0x18002c05f  mov     rax, rbx
0x18002c062  cmp     word ptr [rdx+rax*2+2], 0
0x18002c068  lea     rax, [rax+1]
0x18002c06c  jnz     short loc_18002C062
0x18002c06e  lea     eax, ds:2[rax*2]
0x18002c075  jmp     short loc_18002C083
0x18002c077  lea     rdx, LocaleName
0x18002c07e  mov     eax, 2
0x18002c083  mov     [rbp+60h+var_98], eax
0x18002c086  lea     rdi, _TraceLoggingMetadata
0x18002c08d  mov     [rbp+60h+var_A0], rdx
0x18002c091  lea     rax, aQueuingInvalid; "Queuing invalidation of MM SA"
0x18002c098  mov     [rbp+60h+var_90], rax
0x18002c09c  lea     rdx, [rbp+60h+var_60]
0x18002c0a0  lea     rax, [rbp+60h+var_70]
0x18002c0a4  mov     [rbp+60h+var_94], r14d
0x18002c0a8  mov     [rbp+60h+var_80], rax
0x18002c0ac  xor     r9d, r9d
0x18002c0af  movzx   eax, cs:word_18015210A
0x18002c0b6  xor     r8d, r8d
0x18002c0b9  mov     [rbp+60h+var_5C], eax
0x18002c0bc  mov     rax, cs:off_180173280
0x18002c0c3  mov     [rbp+60h+var_D0], rax
0x18002c0c7  mov     [rbp+60h+var_88], 1Eh
0x18002c0cf  mov     [rbp+60h+var_70], r12
0x18002c0d3  mov     [rbp+60h+var_78], 8
0x18002c0db  mov     [rbp+60h+var_60], 0B000000h
0x18002c0e2  mov     [rbp+60h+var_58], r14
0x18002c0e6  movzx   eax, word ptr [rax]
0x18002c0e9  mov     [rbp+60h+var_C8], eax
0x18002c0ec  lea     rax, dword_180152114
0x18002c0f3  mov     [rbp+60h+var_C0], rax
0x18002c0f7  mov     rax, r13
0x18002c0fa  sub     eax, edi
0x18002c0fc  mov     [rbp+60h+var_C4], 2
0x18002c103  mov     [rbp+60h+var_B8], 35h ; '5'
0x18002c10a  mov     [rbp+60h+var_B4], 1
0x18002c111  mov     [rsp+160h+var_130], eax
0x18002c115  mov     eax, [rsp+160h+var_130]
0x18002c119  mov     rcx, cs:qword_180173298
0x18002c120  lea     rax, [rbp+60h+var_D0]
0x18002c124  mov     [rsp+160h+var_138], rax
0x18002c129  mov     dword ptr [rsp+160h+var_140], 6
0x18002c131  call    cs:__imp_EtwEventWriteTransfer
0x18002c137  jmp     short loc_18002C140
0x18002c139  lea     rdi, _TraceLoggingMetadata
0x18002c140  lea     rcx, [rsp+160h+var_120]
0x18002c145  call    IkeQueuePostponedWorkEntry
0x18002c14a  test    esi, esi
0x18002c14c  jz      short loc_18002C1AC
0x18002c14e  mov     r8, cs:gIkeExtGlobals
0x18002c155  lea     rcx, IkeHandlePostponedWork; pfns
0x18002c15c  add     r8, 0BE8h; pcbe
0x18002c163  xor     edx, edx; pv
0x18002c165  call    cs:__imp_TrySubmitThreadpoolCallback
0x18002c16b  test    eax, eax
0x18002c16d  jnz     short loc_18002C18F
0x18002c16f  call    cs:__imp_GetLastError
0x18002c175  mov     r9d, 1
0x18002c17b  lea     rdx, aTrysubmitthrea; "TrySubmitThreadpoolCallback"
0x18002c182  mov     r8d, eax
0x18002c185  call    WfpReportSysErrorAsWinError
0x18002c18a  mov     rcx, rax
0x18002c18d  jmp     short loc_18002C1A0
0x18002c18f  mov     rax, cs:gIkeExtGlobals
0x18002c196  mov     rcx, r14
0x18002c199  lock inc dword ptr [rax+7A4h]
0x18002c1a0  lea     rdx, aIkequeueworkit_0; "IkeQueueWorkItem"
0x18002c1a7  call    IkeReturnError
0x18002c1ac  mov     eax, cs:dword_180173278
0x18002c1b2  cmp     eax, 5
0x18002c1b5  jbe     loc_18002C30F
0x18002c1bb  mov     rcx, cs:qword_180173290
0x18002c1c2  mov     rax, cs:qword_180173288
0x18002c1c9  test    al, 1
0x18002c1cb  jz      loc_18002C30F
0x18002c1d1  mov     rax, rcx
0x18002c1d4  and     eax, 1
0x18002c1d7  cmp     rax, rcx
0x18002c1da  jnz     loc_18002C30F
0x18002c1e0  mov     rax, cs:gIkeExtGlobals
0x18002c1e7  test    rax, rax
0x18002c1ea  jz      short loc_18002C215
0x18002c1ec  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c1f2  cmp     ecx, 0FFFFFFFFh
0x18002c1f5  jz      short loc_18002C215
0x18002c1f7  call    cs:__imp_TlsGetValue
0x18002c1fd  test    rax, rax
0x18002c200  jz      short loc_18002C20E
0x18002c202  mov     rcx, [rax]
0x18002c205  mov     rax, cs:gIkeExtGlobals
0x18002c20c  jmp     short loc_18002C218
0x18002c20e  mov     rax, cs:gIkeExtGlobals
0x18002c215  mov     rcx, r14
0x18002c218  mov     [rbp+60h+var_70], rcx
0x18002c21c  lea     rcx, [rbp+60h+var_70]
0x18002c220  mov     [rbp+60h+var_B0], rcx
0x18002c224  mov     [rbp+60h+var_A8], 8
0x18002c22c  test    rax, rax
0x18002c22f  jz      short loc_18002C267
0x18002c231  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002c237  cmp     ecx, 0FFFFFFFFh
0x18002c23a  jz      short loc_18002C267
0x18002c23c  call    cs:__imp_TlsGetValue
0x18002c242  test    rax, rax
0x18002c245  lea     rdx, [rax+8]
  ... truncated ...
```
