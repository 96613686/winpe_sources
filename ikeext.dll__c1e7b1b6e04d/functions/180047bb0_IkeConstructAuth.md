# IkeConstructAuth

- ea: `0x180047bb0`
- end: `0x180048235`
- name: `IkeConstructAuth`
- size: `1669`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _DWORD **)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180043270`
- `0x1800e7294`
- `0x1800e77b4`
- `0x1800e7b04`
- `0x1800eedd0`
- `0x1800ef0d8`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x1800096c0`
- `0x180047bb0`
- `0x180050850`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047c48`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047c8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047dae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047de9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047e45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047e8a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800480de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180048123`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047c48`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047c8d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047dae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047de9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047e45`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180047e8a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800480de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180048123`
- `ntdll!EtwEventWriteTransfer` at `0x180047d64`
- `ntdll!EtwEventWriteTransfer` at `0x180047f5b`
- `ntdll!EtwEventWriteTransfer` at `0x1800481fb`
- `ntdll!EtwEventWriteTransfer` at `0x180047d64`
- `ntdll!EtwEventWriteTransfer` at `0x180047f5b`
- `ntdll!EtwEventWriteTransfer` at `0x1800481fb`
- `WS2_32!__imp_htons` at `0x180048008`
- `WS2_32!__imp_htons` at `0x180048050`
- `WS2_32!__imp_htons` at `0x18004805c`
- `WS2_32!__imp_htons` at `0x180048008`
- `WS2_32!__imp_htons` at `0x180048050`
- `WS2_32!__imp_htons` at `0x18004805c`

## pseudocode

```c
__int64 __fastcall IkeConstructAuth(__int64 a1, unsigned int a2, __int64 a3, _DWORD **a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rsi
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
  _QWORD *v19; // rcx
  LPCRITICAL_SECTION v20; // rdx
  DWORD v21; // eax
  LPVOID v22; // rax
  LPVOID v23; // r8
  __int64 v24; // rbx
  DWORD v25; // eax
  __int64 *v26; // rax
  __int64 v27; // r9
  LPCRITICAL_SECTION v28; // rax
  DWORD v29; // ecx
  __int64 *v30; // rax
  __int64 v31; // rcx
  DWORD v32; // ecx
  char *v33; // rax
  const WCHAR *v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // r15
  int v39; // r14d
  __int64 v40; // rdi
  __int64 v41; // rsi
  unsigned int v42; // edx
  LPCRITICAL_SECTION v43; // rax
  DWORD v44; // ecx
  __int64 *v45; // rax
  __int64 v46; // rcx
  DWORD v47; // ecx
  char *v48; // rax
  const WCHAR *v49; // rdx
  int v50; // esi
  int v52; // [rsp+30h] [rbp-79h]
  int v53; // [rsp+34h] [rbp-75h]
  __int64 v54; // [rsp+38h] [rbp-71h] BYREF
  __int64 v55; // [rsp+40h] [rbp-69h] BYREF
  int v56; // [rsp+48h] [rbp-61h] BYREF
  int v57; // [rsp+4Ch] [rbp-5Dh]
  __int64 v58; // [rsp+50h] [rbp-59h]
  char *v59; // [rsp+60h] [rbp-49h] BYREF
  int v60; // [rsp+68h] [rbp-41h]
  int v61; // [rsp+6Ch] [rbp-3Dh]
  char *v62; // [rsp+70h] [rbp-39h]
  int v63; // [rsp+78h] [rbp-31h]
  int v64; // [rsp+7Ch] [rbp-2Dh]
  __int64 *v65; // [rsp+80h] [rbp-29h]
  __int64 v66; // [rsp+88h] [rbp-21h]
  const WCHAR *v67; // [rsp+90h] [rbp-19h]
  int v68; // [rsp+98h] [rbp-11h]
  int v69; // [rsp+9Ch] [rbp-Dh]
  const char *v70; // [rsp+A0h] [rbp-9h]
  __int64 v71; // [rsp+A8h] [rbp-1h]

  v4 = 0;
  v55 = a3;
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
  v54 = v12;
  v65 = &v54;
  v66 = 8;
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
  v68 = v18;
  v57 = 5;
  v59 = off_180173280;
  v67 = v15;
  v69 = 0;
  v70 = "IkeConstructAuth";
  v71 = 17;
  v56 = 184549376;
  v58 = 1;
  v60 = *(unsigned __int16 *)off_180173280;
  v62 = (char *)&dword_180166EA4;
  v61 = 2;
  v63 = 45;
  v64 = 1;
  EtwEventWriteTransfer(qword_180173298, &v56, 0, 0, 5, &v59);
LABEL_20:
  v19 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v20 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v21 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v21 == -1) )
    {
      v23 = 0;
    }
    else
    {
      v22 = TlsGetValue(v21);
      v19 = WPP_GLOBAL_Control;
      v23 = v22;
      v20 = gIkeExtGlobals;
    }
    v24 = (__int64)v23 + 8;
    if ( !v23 )
      v24 = 0;
    if ( v20
      && (v25 = (DWORD)v20[86].LockSemaphore, v25 != -1)
      && (v26 = (__int64 *)TlsGetValue(v25), v19 = WPP_GLOBAL_Control, v26) )
    {
      v27 = *v26;
    }
    else
    {
      LODWORD(v27) = 0;
    }
    WPP_SF_iS(v19[2], 10, (unsigned int)WPP_5a40d38e410634e30354fd62cae0e05b_Traceguids, v27, v24);
    v4 = 0;
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v28 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v29 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v29 != -1 )
      {
        v30 = (__int64 *)TlsGetValue(v29);
        if ( v30 )
        {
          v31 = *v30;
          v28 = gIkeExtGlobals;
LABEL_42:
          v54 = v31;
          v65 = &v54;
          v66 = 8;
          if ( !v28 )
            goto LABEL_50;
          v32 = (DWORD)v28[86].LockSemaphore;
          if ( v32 == -1 )
            goto LABEL_50;
          v33 = (char *)TlsGetValue(v32);
          v34 = (const WCHAR *)(v33 + 8);
          if ( !v33 )
            v34 = 0;
          if ( v34 )
          {
            v35 = -1;
            do
              v17 = v34[++v35] == 0;
            while ( !v17 );
            v36 = 2 * v35 + 2;
          }
          else
          {
LABEL_50:
            v34 = &LocaleName;
            v36 = 2;
          }
          v68 = v36;
          v67 = v34;
          v70 = "Construct Auth";
          v57 = 4;
          v59 = off_180173280;
          v69 = 0;
          v71 = 15;
          v56 = 184549376;
          v58 = 0;
          v60 = *(unsigned __int16 *)off_180173280;
          v62 = byte_180165253;
          v61 = 2;
          v63 = 50;
          v64 = 1;
          EtwEventWriteTransfer(qword_180173298, &v56, 0, 0, 5, &v59);
          goto LABEL_52;
        }
        v28 = gIkeExtGlobals;
      }
    }
    v31 = 0;
    goto LABEL_42;
  }
LABEL_52:
  v37 = *(unsigned __int16 *)(a1 + 14);
  LOWORD(v52) = 0;
  if ( (unsigned int)v37 >= *(_DWORD *)(a1 + 8) )
  {
    v38 = WfpReportSysErrorAsWinError(v19, "IkeConstructAuth", 13829, 1);
    goto LABEL_69;
  }
  *(_BYTE *)(v37 + *(_QWORD *)a1) = -121;
  *(_WORD *)(a1 + 14) = *(_WORD *)(a1 + 12);
  if ( **a4 == -1 )
  {
    v39 = 0;
    v4 = a2;
    goto LABEL_61;
  }
  if ( a2 )
  {
    do
    {
      if ( (*a4)[v4] == -1 )
        break;
      ++v4;
    }
    while ( v4 < a2 );
  }
  v38 = IkeReturnError(0, "IkeCountPrunedAuthMethods");
  if ( !v38 )
  {
    v39 = 1;
LABEL_61:
    v38 = IkeExpandPacket(a1, 4 * v4 + 4, a3);
    if ( !v38 )
    {
      v40 = 0;
      HIWORD(v52) = htons(4 * (v4 + 1));
      *(_DWORD *)(*(unsigned __int16 *)(a1 + 12) + *(_QWORD *)a1) = v52;
      *(_WORD *)(a1 + 12) += 4;
      if ( v4 )
      {
        v41 = v55;
        do
        {
          if ( v39 )
            v42 = (*a4)[v40];
          else
            v42 = v40;
          LOWORD(v53) = htons(*(_WORD *)(v41 + 80LL * v42));
          v40 = (unsigned int)(v40 + 1);
          HIWORD(v53) = htons(0);
          *(_DWORD *)(*(unsigned __int16 *)(a1 + 12) + *(_QWORD *)a1) = v53;
          *(_WORD *)(a1 + 12) += 4;
        }
        while ( (unsigned int)v40 < v4 );
        v8 = -1;
      }
    }
  }
LABEL_69:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return IkeReturnError(v38, "IkeConstructAuth");
  v43 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_77;
  v44 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v44 == -1 )
    goto LABEL_77;
  v45 = (__int64 *)TlsGetValue(v44);
  if ( !v45 )
  {
    v43 = gIkeExtGlobals;
LABEL_77:
    v46 = 0;
    goto LABEL_78;
  }
  v46 = *v45;
  v43 = gIkeExtGlobals;
LABEL_78:
  v55 = v46;
  v65 = &v55;
  v66 = 8;
  if ( !v43 )
    goto LABEL_85;
  v47 = (DWORD)v43[86].LockSemaphore;
  if ( v47 == -1 )
    goto LABEL_85;
  v48 = (char *)TlsGetValue(v47);
  v49 = (const WCHAR *)(v48 + 8);
  if ( !v48 )
    v49 = 0;
  if ( v49 )
  {
    do
      v17 = v49[++v8] == 0;
    while ( !v17 );
    v50 = 2 * v8 + 2;
  }
  else
  {
LABEL_85:
    v49 = &LocaleName;
    v50 = 2;
  }
  v57 = 5;
  v59 = off_180173280;
  v67 = v49;
  v68 = v50;
  v69 = 0;
  v70 = "IkeConstructAuth";
  v71 = 17;
  v56 = 184549376;
  v58 = 1;
  v60 = *(unsigned __int16 *)off_180173280;
  v62 = byte_180166E6B;
  v61 = 2;
  v63 = 45;
  v64 = 1;
  EtwEventWriteTransfer(qword_180173298, &v56, 0, 0, 5, &v59);
  return IkeReturnError(v38, "IkeConstructAuth");
}

```

## disassembly

```asm
0x180047bb0  push    rbp
0x180047bb2  push    rbx
0x180047bb3  push    rsi
0x180047bb4  push    rdi
0x180047bb5  push    r12
0x180047bb7  push    r13
0x180047bb9  push    r14
0x180047bbb  push    r15
0x180047bbd  lea     rbp, [rsp-1Fh]
0x180047bc2  sub     rsp, 0C8h
0x180047bc9  mov     rax, cs:__security_cookie
0x180047bd0  xor     rax, rsp
0x180047bd3  mov     [rbp+57h+var_50], rax
0x180047bd7  mov     eax, cs:dword_180173278
0x180047bdd  lea     r15, aIkeconstructau_0; "IkeConstructAuth"
0x180047be4  xor     ebx, ebx
0x180047be6  mov     [rbp+57h+var_C0], r8
0x180047bea  mov     [rbp+57h+var_CC], ebx
0x180047bed  mov     r13, r9
0x180047bf0  lea     r14, _TraceLoggingMetadataEnd
0x180047bf7  mov     edi, edx
0x180047bf9  mov     r12, rcx
0x180047bfc  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180047c03  cmp     eax, 5
0x180047c06  jbe     loc_180047D6A
0x180047c0c  mov     rcx, cs:qword_180173290
0x180047c13  mov     rax, cs:qword_180173288
0x180047c1a  test    al, 1
0x180047c1c  jz      loc_180047D6A
0x180047c22  mov     rax, rcx
0x180047c25  and     eax, 1
0x180047c28  cmp     rax, rcx
0x180047c2b  jnz     loc_180047D6A
0x180047c31  mov     rax, cs:gIkeExtGlobals
0x180047c38  test    rax, rax
0x180047c3b  jz      short loc_180047C66
0x180047c3d  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047c43  cmp     ecx, 0FFFFFFFFh
0x180047c46  jz      short loc_180047C66
0x180047c48  call    cs:__imp_TlsGetValue
0x180047c4e  test    rax, rax
0x180047c51  jz      short loc_180047C5F
0x180047c53  mov     rcx, [rax]
0x180047c56  mov     rax, cs:gIkeExtGlobals
0x180047c5d  jmp     short loc_180047C69
0x180047c5f  mov     rax, cs:gIkeExtGlobals
0x180047c66  mov     rcx, rbx
0x180047c69  mov     [rbp+57h+var_C8], rcx
0x180047c6d  lea     rcx, [rbp+57h+var_C8]
0x180047c71  mov     [rbp+57h+var_80], rcx
0x180047c75  mov     [rbp+57h+var_78], 8
0x180047c7d  test    rax, rax
0x180047c80  jz      short loc_180047CC4
0x180047c82  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047c88  cmp     ecx, 0FFFFFFFFh
0x180047c8b  jz      short loc_180047CC4
0x180047c8d  call    cs:__imp_TlsGetValue
0x180047c93  test    rax, rax
0x180047c96  lea     rdx, [rax+8]
0x180047c9a  cmovz   rdx, rbx
0x180047c9e  test    rdx, rdx
0x180047ca1  jz      short loc_180047CC4
0x180047ca3  mov     rax, rsi
0x180047ca6  nop     word ptr [rax+rax+00000000h]
0x180047cb0  cmp     [rdx+rax*2+2], bx
0x180047cb5  lea     rax, [rax+1]
0x180047cb9  jnz     short loc_180047CB0
0x180047cbb  lea     eax, ds:2[rax*2]
0x180047cc2  jmp     short loc_180047CD0
0x180047cc4  lea     rdx, LocaleName
0x180047ccb  mov     eax, 2
0x180047cd0  mov     [rbp+57h+var_68], eax
0x180047cd3  lea     rcx, _TraceLoggingMetadata
0x180047cda  movzx   eax, cs:word_180166E9A
0x180047ce1  xor     r9d, r9d
0x180047ce4  mov     [rbp+57h+var_B4], eax
0x180047ce7  xor     r8d, r8d
0x180047cea  mov     rax, cs:off_180173280
0x180047cf1  mov     [rbp+57h+var_A0], rax
0x180047cf5  mov     [rbp+57h+var_70], rdx
0x180047cf9  lea     rdx, [rbp+57h+var_B8]
0x180047cfd  mov     [rbp+57h+var_64], ebx
0x180047d00  mov     [rbp+57h+var_60], r15
0x180047d04  mov     [rbp+57h+var_58], 11h
0x180047d0c  mov     [rbp+57h+var_B8], 0B000000h
0x180047d13  mov     [rbp+57h+var_B0], 1
0x180047d1b  movzx   eax, word ptr [rax]
0x180047d1e  mov     [rbp+57h+var_98], eax
0x180047d21  lea     rax, dword_180166EA4
0x180047d28  mov     [rbp+57h+var_90], rax
0x180047d2c  mov     rax, r14
0x180047d2f  sub     eax, ecx
0x180047d31  mov     [rbp+57h+var_94], 2
0x180047d38  mov     [rbp+57h+var_88], 2Dh ; '-'
0x180047d3f  mov     [rbp+57h+var_84], 1
0x180047d46  mov     [rbp+57h+var_D0], eax
0x180047d49  mov     eax, [rbp+57h+var_D0]
0x180047d4c  mov     rcx, cs:qword_180173298
0x180047d53  lea     rax, [rbp+57h+var_A0]
0x180047d57  mov     [rsp+100h+var_D8], rax
0x180047d5c  mov     dword ptr [rsp+100h+var_E0], 5
0x180047d64  call    cs:__imp_EtwEventWriteTransfer
0x180047d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047d71  lea     rax, WPP_GLOBAL_Control
0x180047d78  cmp     rcx, rax
0x180047d7b  jz      loc_180047E1F
0x180047d81  cmp     byte ptr [rcx+19h], 4
0x180047d85  jb      loc_180047E1F
0x180047d8b  test    byte ptr [rcx+1Ch], 10h
0x180047d8f  jz      loc_180047E1F
0x180047d95  mov     rdx, cs:gIkeExtGlobals
0x180047d9c  test    rdx, rdx
0x180047d9f  jz      short loc_180047DC7
0x180047da1  mov     eax, [rdx+0D88h]
0x180047da7  cmp     eax, 0FFFFFFFFh
0x180047daa  jz      short loc_180047DC7
0x180047dac  mov     ecx, eax; dwTlsIndex
0x180047dae  call    cs:__imp_TlsGetValue
0x180047db4  mov     rcx, cs:WPP_GLOBAL_Control
0x180047dbb  mov     r8, rax
0x180047dbe  mov     rdx, cs:gIkeExtGlobals
0x180047dc5  jmp     short loc_180047DCA
0x180047dc7  mov     r8, rbx
0x180047dca  xor     eax, eax
0x180047dcc  lea     rbx, [r8+8]
0x180047dd0  test    r8, r8
0x180047dd3  cmovz   rbx, rax
0x180047dd7  test    rdx, rdx
0x180047dda  jz      short loc_180047E00
0x180047ddc  mov     eax, [rdx+0D88h]
0x180047de2  cmp     eax, 0FFFFFFFFh
0x180047de5  jz      short loc_180047E00
0x180047de7  mov     ecx, eax; dwTlsIndex
0x180047de9  call    cs:__imp_TlsGetValue
0x180047def  mov     rcx, cs:WPP_GLOBAL_Control
0x180047df6  test    rax, rax
0x180047df9  jz      short loc_180047E00
0x180047dfb  mov     r9, [rax]
0x180047dfe  jmp     short loc_180047E03
0x180047e00  xor     r9d, r9d
0x180047e03  mov     rcx, [rcx+10h]
0x180047e07  lea     r8, WPP_5a40d38e410634e30354fd62cae0e05b_Traceguids
0x180047e0e  mov     edx, 0Ah
0x180047e13  mov     [rsp+100h+var_E0], rbx
0x180047e18  call    WPP_SF_iS
0x180047e1d  xor     ebx, ebx
0x180047e1f  mov     eax, cs:dword_180173278
0x180047e25  cmp     eax, 4
0x180047e28  jbe     loc_180047F61
0x180047e2e  mov     rax, cs:gIkeExtGlobals
0x180047e35  test    rax, rax
0x180047e38  jz      short loc_180047E63
0x180047e3a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047e40  cmp     ecx, 0FFFFFFFFh
0x180047e43  jz      short loc_180047E63
0x180047e45  call    cs:__imp_TlsGetValue
0x180047e4b  test    rax, rax
0x180047e4e  jz      short loc_180047E5C
0x180047e50  mov     rcx, [rax]
0x180047e53  mov     rax, cs:gIkeExtGlobals
0x180047e5a  jmp     short loc_180047E66
0x180047e5c  mov     rax, cs:gIkeExtGlobals
0x180047e63  mov     rcx, rbx
0x180047e66  mov     [rbp+57h+var_C8], rcx
0x180047e6a  lea     rcx, [rbp+57h+var_C8]
0x180047e6e  mov     [rbp+57h+var_80], rcx
0x180047e72  mov     [rbp+57h+var_78], 8
0x180047e7a  test    rax, rax
0x180047e7d  jz      short loc_180047EB8
0x180047e7f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180047e85  cmp     ecx, 0FFFFFFFFh
0x180047e88  jz      short loc_180047EB8
0x180047e8a  call    cs:__imp_TlsGetValue
0x180047e90  test    rax, rax
0x180047e93  lea     rdx, [rax+8]
0x180047e97  cmovz   rdx, rbx
0x180047e9b  test    rdx, rdx
0x180047e9e  jz      short loc_180047EB8
0x180047ea0  mov     rax, rsi
0x180047ea3  cmp     word ptr [rdx+rax*2+2], 0
0x180047ea9  lea     rax, [rax+1]
0x180047ead  jnz     short loc_180047EA3
0x180047eaf  lea     eax, ds:2[rax*2]
0x180047eb6  jmp     short loc_180047EC4
0x180047eb8  lea     rdx, LocaleName
0x180047ebf  mov     eax, 2
0x180047ec4  mov     [rbp+57h+var_68], eax
0x180047ec7  lea     rcx, _TraceLoggingMetadata
0x180047ece  mov     [rbp+57h+var_70], rdx
0x180047ed2  lea     rax, aConstructAuth; "Construct Auth"
0x180047ed9  mov     [rbp+57h+var_60], rax
0x180047edd  lea     rdx, [rbp+57h+var_B8]
0x180047ee1  movzx   eax, cs:word_180165249
0x180047ee8  xor     r9d, r9d
0x180047eeb  mov     [rbp+57h+var_B4], eax
0x180047eee  xor     r8d, r8d
0x180047ef1  mov     rax, cs:off_180173280
0x180047ef8  mov     [rbp+57h+var_A0], rax
0x180047efc  mov     [rbp+57h+var_64], ebx
0x180047eff  mov     [rbp+57h+var_58], 0Fh
0x180047f07  mov     [rbp+57h+var_B8], 0B000000h
0x180047f0e  mov     [rbp+57h+var_B0], rbx
0x180047f12  movzx   eax, word ptr [rax]
0x180047f15  mov     [rbp+57h+var_98], eax
0x180047f18  lea     rax, byte_180165253
0x180047f1f  mov     [rbp+57h+var_90], rax
0x180047f23  mov     rax, r14
0x180047f26  sub     eax, ecx
0x180047f28  mov     [rbp+57h+var_94], 2
0x180047f2f  mov     [rbp+57h+var_88], 32h ; '2'
0x180047f36  mov     [rbp+57h+var_84], 1
0x180047f3d  mov     [rbp+57h+var_D0], eax
0x180047f40  mov     eax, [rbp+57h+var_D0]
0x180047f43  mov     rcx, cs:qword_180173298
0x180047f4a  lea     rax, [rbp+57h+var_A0]
0x180047f4e  mov     [rsp+100h+var_D8], rax
0x180047f53  mov     dword ptr [rsp+100h+var_E0], 5
0x180047f5b  call    cs:__imp_EtwEventWriteTransfer
0x180047f61  movzx   eax, word ptr [r12+0Eh]
0x180047f67  mov     [rbp+57h+var_D0], ebx
0x180047f6a  cmp     eax, [r12+8]
0x180047f6f  jb      short loc_180047F8D
0x180047f71  mov     r9d, 1
0x180047f77  mov     r8d, 3605h
0x180047f7d  mov     rdx, r15
0x180047f80  call    WfpReportSysErrorAsWinError
0x180047f85  mov     r15, rax
0x180047f88  jmp     loc_180048093
0x180047f8d  mov     rcx, rax
0x180047f90  mov     rax, [r12]
0x180047f94  mov     byte ptr [rcx+rax], 87h
0x180047f98  movzx   eax, word ptr [r12+0Ch]
0x180047f9e  mov     [r12+0Eh], ax
0x180047fa4  mov     rcx, [r13+0]
0x180047fa8  cmp     dword ptr [rcx], 0FFFFFFFFh
0x180047fab  jz      short loc_180047FE1
0x180047fad  test    edi, edi
0x180047faf  jz      short loc_180047FBF
0x180047fb1  mov     eax, ebx
0x180047fb3  cmp     dword ptr [rcx+rax*4], 0FFFFFFFFh
0x180047fb7  jz      short loc_180047FBF
0x180047fb9  inc     ebx
0x180047fbb  cmp     ebx, edi
0x180047fbd  jb      short loc_180047FB1
0x180047fbf  lea     rdx, aIkecountpruned; "IkeCountPrunedAuthMethods"
0x180047fc6  xor     ecx, ecx
0x180047fc8  call    IkeReturnError
0x180047fcd  mov     r15, rax
0x180047fd0  test    rax, rax
0x180047fd3  jnz     loc_180048091
0x180047fd9  mov     r14d, 1
0x180047fdf  jmp     short loc_180047FE6
0x180047fe1  mov     r14d, ebx
0x180047fe4  mov     ebx, edi
0x180047fe6  lea     edx, ds:4[rbx*4]
0x180047fed  mov     rcx, r12
0x180047ff0  call    IkeExpandPacket
0x180047ff5  mov     r15, rax
0x180047ff8  test    rax, rax
0x180047ffb  jnz     loc_18004808A
0x180048001  lea     ecx, [rbx+1]
0x180048004  shl     cx, 2; hostshort
0x180048008  call    cs:__imp_htons
0x18004800e  movzx   edx, word ptr [r12+0Ch]
0x180048014  xor     edi, edi
0x180048016  mov     rcx, [r12]
0x18004801a  mov     word ptr [rbp+57h+var_D0+2], ax
0x18004801e  mov     eax, [rbp+57h+var_D0]
0x180048021  mov     [rdx+rcx], eax
0x180048024  add     word ptr [r12+0Ch], 4
0x18004802b  test    ebx, ebx
0x18004802d  jz      short loc_18004808A
0x18004802f  mov     rsi, [rbp+57h+var_C0]
0x180048033  test    r14d, r14d
0x180048036  jz      short loc_180048041
0x180048038  mov     rax, [r13+0]
0x18004803c  mov     edx, [rax+rdi*4]
0x18004803f  jmp     short loc_180048043
0x180048041  mov     edx, edi
0x180048043  mov     eax, edx
0x180048045  lea     rcx, [rax+rax*4]
0x180048049  add     rcx, rcx
0x18004804c  movzx   ecx, word ptr [rsi+rcx*8]; hostshort
0x180048050  call    cs:__imp_htons
0x180048056  xor     ecx, ecx; hostshort
0x180048058  mov     word ptr [rbp+57h+var_CC], ax
0x18004805c  call    cs:__imp_htons
0x180048062  movzx   edx, word ptr [r12+0Ch]
0x180048068  inc     edi
0x18004806a  mov     rcx, [r12]
0x18004806e  mov     word ptr [rbp+57h+var_CC+2], ax
0x180048072  mov     eax, [rbp+57h+var_CC]
0x180048075  mov     [rdx+rcx], eax
0x180048078  add     word ptr [r12+0Ch], 4
0x18004807f  cmp     edi, ebx
0x180048081  jb      short loc_180048033
0x180048083  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18004808a  lea     r14, _TraceLoggingMetadataEnd
0x180048091  xor     ebx, ebx
0x180048093  mov     eax, cs:dword_180173278
  ... truncated ...
```
