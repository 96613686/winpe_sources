# IkeAddAttributeToPacket

- ea: `0x180008e40`
- end: `0x180009620`
- name: `IkeAddAttributeToPacket`
- size: `2016`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180006320`
- `0x180008b70`
- `0x18010b900`
- `0x18010bad4`
- `0x18010bbe8`
- `0x18010cedc`

## callees

- `0x180008388`
- `0x180008e40`
- `0x180009630`
- `0x180037e90`
- `0x180050850`
- `0x1800b9138`
- `0x1800ba414`
- `0x1800ba994`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008ee6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008f2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800090af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800090f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009269`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800092ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009497`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800094df`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008ee6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180008f2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800090af`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800090f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009269`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800092ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009497`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800094df`
- `ntdll!EtwEventWriteTransfer` at `0x180009005`
- `ntdll!EtwEventWriteTransfer` at `0x1800091d0`
- `ntdll!EtwEventWriteTransfer` at `0x180009390`
- `ntdll!EtwEventWriteTransfer` at `0x1800095bd`
- `ntdll!EtwEventWriteTransfer` at `0x180009005`
- `ntdll!EtwEventWriteTransfer` at `0x1800091d0`
- `ntdll!EtwEventWriteTransfer` at `0x180009390`
- `ntdll!EtwEventWriteTransfer` at `0x1800095bd`

## pseudocode

```c
__int64 __fastcall IkeAddAttributeToPacket(unsigned __int16 a1, _WORD *a2, int a3, __int64 a4)
{
  unsigned __int16 v4; // r14
  int v6; // r15d
  unsigned __int16 v7; // r13
  __int64 v10; // rdi
  LPCRITICAL_SECTION v11; // rax
  DWORD LockSemaphore; // ecx
  __int64 *Value; // rax
  __int64 v14; // rcx
  DWORD v15; // ecx
  char *v16; // rax
  const WCHAR *v17; // rdx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  LPCRITICAL_SECTION v21; // rax
  DWORD v22; // ecx
  __int64 *v23; // rax
  __int64 v24; // rcx
  DWORD v25; // ecx
  char *v26; // rax
  const WCHAR *v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  LPCRITICAL_SECTION v30; // rax
  DWORD v31; // ecx
  __int64 *v32; // rax
  __int64 v33; // rcx
  DWORD v34; // ecx
  char *v35; // rax
  const WCHAR *v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  __int16 v39; // ax
  __int64 v40; // rbx
  LPCRITICAL_SECTION v41; // rax
  DWORD v42; // ecx
  __int64 *v43; // rax
  __int64 v44; // rcx
  DWORD v45; // ecx
  char *v46; // rax
  const WCHAR *v47; // rdx
  int v48; // eax
  unsigned __int16 v50; // [rsp+34h] [rbp-55h] BYREF
  __int64 v51; // [rsp+38h] [rbp-51h] BYREF
  int v52; // [rsp+40h] [rbp-49h] BYREF
  int v53; // [rsp+44h] [rbp-45h]
  __int64 v54; // [rsp+48h] [rbp-41h]
  char *v55; // [rsp+50h] [rbp-39h] BYREF
  int v56; // [rsp+58h] [rbp-31h]
  int v57; // [rsp+5Ch] [rbp-2Dh]
  int *v58; // [rsp+60h] [rbp-29h]
  int v59; // [rsp+68h] [rbp-21h]
  int v60; // [rsp+6Ch] [rbp-1Dh]
  __int64 *v61; // [rsp+70h] [rbp-19h]
  __int64 v62; // [rsp+78h] [rbp-11h]
  const WCHAR *v63; // [rsp+80h] [rbp-9h]
  int v64; // [rsp+88h] [rbp-1h]
  int v65; // [rsp+8Ch] [rbp+3h]
  const char *v66; // [rsp+90h] [rbp+7h]
  __int64 v67; // [rsp+98h] [rbp+Fh]

  v4 = 0;
  v6 = a1;
  v50 = 0;
  v7 = 0;
  v10 = -1;
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    goto LABEL_20;
  v11 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_9;
  LockSemaphore = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( LockSemaphore == -1 )
    goto LABEL_9;
  Value = (__int64 *)TlsGetValue(LockSemaphore);
  if ( !Value )
  {
    v11 = gIkeExtGlobals;
LABEL_9:
    v14 = 0;
    goto LABEL_10;
  }
  v14 = *Value;
  v11 = gIkeExtGlobals;
LABEL_10:
  v51 = v14;
  v61 = &v51;
  v62 = 8;
  if ( !v11 )
    goto LABEL_18;
  v15 = (DWORD)v11[86].LockSemaphore;
  if ( v15 == -1 )
    goto LABEL_18;
  v16 = (char *)TlsGetValue(v15);
  v17 = (const WCHAR *)(v16 + 8);
  if ( !v16 )
    v17 = 0;
  if ( v17 )
  {
    v18 = -1;
    do
      v19 = v17[++v18] == 0;
    while ( !v19 );
    v20 = 2 * v18 + 2;
  }
  else
  {
LABEL_18:
    v17 = &LocaleName;
    v20 = 2;
  }
  v64 = v20;
  v63 = v17;
  v66 = "IkeAddAttributeToPacket";
  v53 = 5;
  v55 = off_180173280;
  v65 = 0;
  v67 = 24;
  v52 = 184549376;
  v54 = 1;
  v56 = *(unsigned __int16 *)off_180173280;
  v58 = &dword_180166EA4;
  v57 = 2;
  v59 = 45;
  v60 = 1;
  EtwEventWriteTransfer(qword_180173298, &v52, 0, 0, 5, &v55);
LABEL_20:
  if ( a3 )
  {
    LODWORD(a2) = (unsigned __int16)*a2;
    if ( v6 == 1 )
    {
      v39 = IkeMMCipherInternalToDoi((unsigned __int16)a2, &v50, 1);
      v4 = v50;
      LOWORD(a2) = v39;
      v7 = 14;
      goto LABEL_90;
    }
    if ( v6 == 2 )
    {
      if ( (_DWORD)a2 )
      {
        switch ( (_DWORD)a2 )
        {
          case 1:
            LOWORD(a2) = 2;
            break;
          case 2:
            LOWORD(a2) = 4;
            break;
          case 3:
            LOWORD(a2) = 5;
            break;
          default:
            goto LABEL_86;
        }
      }
      else
      {
        LOWORD(a2) = 1;
      }
      goto LABEL_90;
    }
    if ( v6 != 3 )
    {
      if ( v6 == 4 )
      {
        LOWORD(a2) = IkeMMDhInternalToDoi((unsigned __int16)a2, 2, 1);
      }
      else if ( v6 != 11 )
      {
LABEL_86:
        __fastfail(5u);
      }
      goto LABEL_90;
    }
    if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    {
LABEL_47:
      switch ( (int)a2 )
      {
        case 0:
          LOWORD(a2) = 1;
          goto LABEL_54;
        case 1:
          LOWORD(a2) = 3;
          goto LABEL_54;
        case 2:
          LOWORD(a2) = -535;
          goto LABEL_54;
        case 6:
          LOWORD(a2) = -531;
          goto LABEL_54;
        case 7:
          LOWORD(a2) = 9;
          goto LABEL_54;
        case 8:
          LOWORD(a2) = 10;
LABEL_54:
          if ( (unsigned int)dword_180173278 <= 5
            || (qword_180173288 & 1) == 0
            || (qword_180173290 & 1) != qword_180173290 )
          {
            goto LABEL_90;
          }
          v30 = gIkeExtGlobals;
          if ( !gIkeExtGlobals )
            goto LABEL_62;
          v31 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
          if ( v31 == -1 )
            goto LABEL_62;
          v32 = (__int64 *)TlsGetValue(v31);
          if ( v32 )
          {
            v33 = *v32;
            v30 = gIkeExtGlobals;
          }
          else
          {
            v30 = gIkeExtGlobals;
LABEL_62:
            v33 = 0;
          }
          v51 = v33;
          v61 = &v51;
          v62 = 8;
          if ( !v30 )
            goto LABEL_71;
          v34 = (DWORD)v30[86].LockSemaphore;
          if ( v34 == -1 )
            goto LABEL_71;
          v35 = (char *)TlsGetValue(v34);
          v36 = (const WCHAR *)(v35 + 8);
          if ( !v35 )
            v36 = 0;
          if ( v36 )
          {
            v37 = -1;
            do
              v19 = v36[++v37] == 0;
            while ( !v19 );
            v38 = 2 * v37 + 2;
          }
          else
          {
LABEL_71:
            v36 = &LocaleName;
            v38 = 2;
          }
          v64 = v38;
          v63 = v36;
          v66 = "IkeMMAuthInternalToDoi";
          v53 = 5;
          v55 = off_180173280;
          v65 = 0;
          v67 = 23;
          v52 = 184549376;
          v54 = 1;
          v56 = *(unsigned __int16 *)off_180173280;
          v58 = (int *)byte_180166E6B;
          v57 = 2;
          v59 = 45;
          v60 = 1;
          EtwEventWriteTransfer(qword_180173298, &v52, 0, 0, 5, &v55);
          break;
        default:
          goto LABEL_86;
      }
      goto LABEL_90;
    }
    v21 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v22 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v22 != -1 )
      {
        v23 = (__int64 *)TlsGetValue(v22);
        if ( v23 )
        {
          v24 = *v23;
          v21 = gIkeExtGlobals;
LABEL_37:
          v51 = v24;
          v61 = &v51;
          v62 = 8;
          if ( !v21 )
            goto LABEL_45;
          v25 = (DWORD)v21[86].LockSemaphore;
          if ( v25 == -1 )
            goto LABEL_45;
          v26 = (char *)TlsGetValue(v25);
          v27 = (const WCHAR *)(v26 + 8);
          if ( !v26 )
            v27 = 0;
          if ( v27 )
          {
            v28 = -1;
            do
              v19 = v27[++v28] == 0;
            while ( !v19 );
            v29 = 2 * v28 + 2;
          }
          else
          {
LABEL_45:
            v27 = &LocaleName;
            v29 = 2;
          }
          v64 = v29;
          v63 = v27;
          v66 = "IkeMMAuthInternalToDoi";
          v53 = 5;
          v55 = off_180173280;
          v65 = 0;
          v67 = 23;
          v52 = 184549376;
          v54 = 1;
          v56 = *(unsigned __int16 *)off_180173280;
          v58 = &dword_180166EA4;
          v57 = 2;
          v59 = 45;
          v60 = 1;
          EtwEventWriteTransfer(qword_180173298, &v52, 0, 0, 5, &v55);
          goto LABEL_47;
        }
        v21 = gIkeExtGlobals;
      }
    }
    v24 = 0;
    goto LABEL_37;
  }
  switch ( v6 )
  {
    case 1:
      goto LABEL_89;
    case 3:
      LOWORD(a2) = IkeQMPfsInternalToDoi((unsigned __int16)*a2, 2, 1);
      goto LABEL_90;
    case 4:
LABEL_89:
      LOWORD(a2) = *a2;
      goto LABEL_90;
  }
  if ( v6 != 5 )
    goto LABEL_86;
  LOWORD(a2) = IkeQMHmacInternalToDoi(a2, 2, 1);
LABEL_90:
  v40 = IkeBasicAtt((unsigned __int16)v6, (unsigned __int16)a2, a4);
  if ( !v40 && v4 )
    v40 = IkeBasicAtt(v7, v4, a4);
  if ( (unsigned int)dword_180173278 > 5 && (qword_180173288 & 1) != 0 && (qword_180173290 & 1) == qword_180173290 )
  {
    v41 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v42 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v42 != -1 )
      {
        v43 = (__int64 *)TlsGetValue(v42);
        if ( v43 )
        {
          v44 = *v43;
          v41 = gIkeExtGlobals;
LABEL_102:
          v51 = v44;
          v61 = &v51;
          v62 = 8;
          if ( !v41 )
            goto LABEL_109;
          v45 = (DWORD)v41[86].LockSemaphore;
          if ( v45 == -1 )
            goto LABEL_109;
          v46 = (char *)TlsGetValue(v45);
          v47 = (const WCHAR *)(v46 + 8);
          if ( !v46 )
            v47 = 0;
          if ( v47 )
          {
            do
              v19 = v47[++v10] == 0;
            while ( !v19 );
            v48 = 2 * v10 + 2;
          }
          else
          {
LABEL_109:
            v47 = &LocaleName;
            v48 = 2;
          }
          v64 = v48;
          v54 = 1;
          v66 = "IkeAddAttributeToPacket";
          v53 = 5;
          v55 = off_180173280;
          v63 = v47;
          v65 = 0;
          v67 = 24;
          v52 = 184549376;
          v56 = *(unsigned __int16 *)off_180173280;
          v58 = (int *)byte_180166E6B;
          v60 = 1;
          v57 = 2;
          v59 = 45;
          EtwEventWriteTransfer(qword_180173298, &v52, 0, 0, 5, &v55);
          return IkeReturnError(v40, "IkeAddAttributeToPacket");
        }
        v41 = gIkeExtGlobals;
      }
    }
    v44 = 0;
    goto LABEL_102;
  }
  return IkeReturnError(v40, "IkeAddAttributeToPacket");
}

```

## disassembly

```asm
0x180008e40  mov     [rsp-8+arg_10], rbx
0x180008e45  push    rbp
0x180008e46  push    rsi
0x180008e47  push    rdi
0x180008e48  push    r12
0x180008e4a  push    r13
0x180008e4c  push    r14
0x180008e4e  push    r15
0x180008e50  lea     rbp, [rsp-27h]
0x180008e55  sub     rsp, 0B0h
0x180008e5c  mov     rax, cs:__security_cookie
0x180008e63  xor     rax, rsp
0x180008e66  mov     [rbp+57h+var_40], rax
0x180008e6a  mov     eax, cs:dword_180173278
0x180008e70  xor     r14d, r14d
0x180008e73  mov     r12, r9
0x180008e76  movzx   r15d, cx
0x180008e7a  mov     r9d, 5
0x180008e80  mov     [rbp+57h+var_AC], r14w
0x180008e85  xor     r13d, r13d
0x180008e88  mov     esi, r8d
0x180008e8b  mov     rbx, rdx
0x180008e8e  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180008e95  mov     edx, 2
0x180008e9a  mov     r8d, 1
0x180008ea0  cmp     eax, r9d
0x180008ea3  jbe     loc_18000901C
0x180008ea9  mov     rcx, cs:qword_180173290
0x180008eb0  mov     rax, cs:qword_180173288
0x180008eb7  test    r8b, al
0x180008eba  jz      loc_18000901C
0x180008ec0  mov     rax, rcx
0x180008ec3  and     eax, r8d
0x180008ec6  cmp     rax, rcx
0x180008ec9  jnz     loc_18000901C
0x180008ecf  mov     rax, cs:gIkeExtGlobals
0x180008ed6  test    rax, rax
0x180008ed9  jz      short loc_180008F04
0x180008edb  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180008ee1  cmp     ecx, 0FFFFFFFFh
0x180008ee4  jz      short loc_180008F04
0x180008ee6  call    cs:__imp_TlsGetValue
0x180008eec  test    rax, rax
0x180008eef  jz      short loc_180008EFD
0x180008ef1  mov     rcx, [rax]
0x180008ef4  mov     rax, cs:gIkeExtGlobals
0x180008efb  jmp     short loc_180008F06
0x180008efd  mov     rax, cs:gIkeExtGlobals
0x180008f04  xor     ecx, ecx
0x180008f06  mov     [rbp+57h+var_A8], rcx
0x180008f0a  lea     rcx, [rbp+57h+var_A8]
0x180008f0e  mov     [rbp+57h+var_70], rcx
0x180008f12  mov     [rbp+57h+var_68], 8
0x180008f1a  test    rax, rax
0x180008f1d  jz      short loc_180008F59
0x180008f1f  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180008f25  cmp     ecx, 0FFFFFFFFh
0x180008f28  jz      short loc_180008F59
0x180008f2a  call    cs:__imp_TlsGetValue
0x180008f30  xor     ecx, ecx
0x180008f32  test    rax, rax
0x180008f35  lea     rdx, [rax+8]
0x180008f39  cmovz   rdx, rcx
0x180008f3d  test    rdx, rdx
0x180008f40  jz      short loc_180008F59
0x180008f42  mov     rax, rdi
0x180008f45  cmp     [rdx+rax*2+2], cx
0x180008f4a  lea     rax, [rax+1]
0x180008f4e  jnz     short loc_180008F45
0x180008f50  lea     eax, ds:2[rax*2]
0x180008f57  jmp     short loc_180008F65
0x180008f59  lea     rdx, LocaleName
0x180008f60  mov     eax, 2
0x180008f65  mov     [rbp+57h+var_58], eax
0x180008f68  lea     rcx, _TraceLoggingMetadata
0x180008f6f  mov     [rbp+57h+var_60], rdx
0x180008f73  lea     rax, aIkeaddattribut; "IkeAddAttributeToPacket"
0x180008f7a  mov     [rbp+57h+var_50], rax
0x180008f7e  lea     rdx, [rbp+57h+var_A0]
0x180008f82  movzx   eax, cs:word_180166E9A
0x180008f89  xor     r9d, r9d
0x180008f8c  mov     [rbp+57h+var_9C], eax
0x180008f8f  xor     r8d, r8d
0x180008f92  mov     rax, cs:off_180173280
0x180008f99  mov     [rbp+57h+var_90], rax
0x180008f9d  mov     [rbp+57h+var_54], r13d
0x180008fa1  mov     [rbp+57h+var_48], 18h
0x180008fa9  mov     [rbp+57h+var_A0], 0B000000h
0x180008fb0  mov     [rbp+57h+var_98], 1
0x180008fb8  movzx   eax, word ptr [rax]
0x180008fbb  mov     [rbp+57h+var_88], eax
0x180008fbe  lea     rax, dword_180166EA4
0x180008fc5  mov     [rbp+57h+var_80], rax
0x180008fc9  lea     rax, _TraceLoggingMetadataEnd
0x180008fd0  sub     eax, ecx
0x180008fd2  mov     [rbp+57h+var_84], 2
0x180008fd9  mov     [rbp+57h+var_78], 2Dh ; '-'
0x180008fe0  mov     [rbp+57h+var_74], 1
0x180008fe7  mov     [rbp+57h+var_B0], eax
0x180008fea  mov     eax, [rbp+57h+var_B0]
0x180008fed  mov     rcx, cs:qword_180173298
0x180008ff4  lea     rax, [rbp+57h+var_90]
0x180008ff8  mov     [rsp+0E0h+var_B8], rax
0x180008ffd  mov     [rsp+0E0h+var_C0], 5
0x180009005  call    cs:__imp_EtwEventWriteTransfer
0x18000900b  mov     edx, 2
0x180009010  mov     r8d, 1
0x180009016  mov     r9d, 5
0x18000901c  mov     ecx, r15d
0x18000901f  test    esi, esi
0x180009021  jz      loc_1800093E4
0x180009027  movzx   ebx, word ptr [rbx]
0x18000902a  sub     ecx, 1
0x18000902d  jz      loc_1800093C8
0x180009033  sub     ecx, 1
0x180009036  jz      loc_18000939B
0x18000903c  sub     ecx, 1
0x18000903f  jz      short loc_180009064
0x180009041  sub     ecx, 1
0x180009044  jz      short loc_180009054
0x180009046  cmp     ecx, 7
0x180009049  jz      loc_18000941C
0x18000904f  jmp     def_1800091F4; jumptable 00000001800091F4 default case, cases 3-5
0x180009054  movzx   ecx, bx
0x180009057  call    IkeMMDhInternalToDoi
0x18000905c  movzx   ebx, ax
0x18000905f  jmp     loc_18000941C
0x180009064  mov     eax, cs:dword_180173278
0x18000906a  cmp     eax, 5
0x18000906d  jbe     loc_1800091D8
0x180009073  mov     rcx, cs:qword_180173290
0x18000907a  mov     rax, cs:qword_180173288
0x180009081  test    al, 1
0x180009083  jz      loc_1800091D8
0x180009089  mov     rax, rcx
0x18000908c  and     eax, 1
0x18000908f  cmp     rax, rcx
0x180009092  jnz     loc_1800091D8
0x180009098  mov     rax, cs:gIkeExtGlobals
0x18000909f  test    rax, rax
0x1800090a2  jz      short loc_1800090CF
0x1800090a4  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800090aa  cmp     ecx, 0FFFFFFFFh
0x1800090ad  jz      short loc_1800090CF
0x1800090af  call    cs:__imp_TlsGetValue
0x1800090b5  test    rax, rax
0x1800090b8  jz      short loc_1800090C8
0x1800090ba  mov     rcx, [rax]
0x1800090bd  xor     esi, esi
0x1800090bf  mov     rax, cs:gIkeExtGlobals
0x1800090c6  jmp     short loc_1800090D3
0x1800090c8  mov     rax, cs:gIkeExtGlobals
0x1800090cf  xor     esi, esi
0x1800090d1  mov     ecx, esi
0x1800090d3  mov     [rbp+57h+var_A8], rcx
0x1800090d7  lea     rcx, [rbp+57h+var_A8]
0x1800090db  mov     [rbp+57h+var_70], rcx
0x1800090df  mov     [rbp+57h+var_68], 8
0x1800090e7  test    rax, rax
0x1800090ea  jz      short loc_180009125
0x1800090ec  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800090f2  cmp     ecx, 0FFFFFFFFh
0x1800090f5  jz      short loc_180009125
0x1800090f7  call    cs:__imp_TlsGetValue
0x1800090fd  test    rax, rax
0x180009100  lea     rdx, [rax+8]
0x180009104  cmovz   rdx, rsi
0x180009108  test    rdx, rdx
0x18000910b  jz      short loc_180009125
0x18000910d  mov     rax, rdi
0x180009110  cmp     [rdx+rax*2+2], r13w
0x180009116  lea     rax, [rax+1]
0x18000911a  jnz     short loc_180009110
0x18000911c  lea     eax, ds:2[rax*2]
0x180009123  jmp     short loc_180009131
0x180009125  lea     rdx, LocaleName
0x18000912c  mov     eax, 2
0x180009131  mov     [rbp+57h+var_58], eax
0x180009134  lea     rcx, _TraceLoggingMetadata
0x18000913b  mov     [rbp+57h+var_60], rdx
0x18000913f  lea     rax, aIkemmauthinter; "IkeMMAuthInternalToDoi"
0x180009146  mov     [rbp+57h+var_50], rax
0x18000914a  lea     rdx, [rbp+57h+var_A0]
0x18000914e  movzx   eax, cs:word_180166E9A
0x180009155  xor     r9d, r9d
0x180009158  mov     [rbp+57h+var_9C], eax
0x18000915b  xor     r8d, r8d
0x18000915e  mov     rax, cs:off_180173280
0x180009165  mov     [rbp+57h+var_90], rax
0x180009169  mov     [rbp+57h+var_54], esi
0x18000916c  mov     [rbp+57h+var_48], 17h
0x180009174  mov     [rbp+57h+var_A0], 0B000000h
0x18000917b  mov     [rbp+57h+var_98], 1
0x180009183  movzx   eax, word ptr [rax]
0x180009186  mov     [rbp+57h+var_88], eax
0x180009189  lea     rax, dword_180166EA4
0x180009190  mov     [rbp+57h+var_80], rax
0x180009194  lea     rax, _TraceLoggingMetadataEnd
0x18000919b  sub     eax, ecx
0x18000919d  mov     [rbp+57h+var_84], 2
0x1800091a4  mov     [rbp+57h+var_78], 2Dh ; '-'
0x1800091ab  mov     [rbp+57h+var_74], 1
0x1800091b2  mov     [rbp+57h+var_B0], eax
0x1800091b5  mov     eax, [rbp+57h+var_B0]
0x1800091b8  mov     rcx, cs:qword_180173298
0x1800091bf  lea     rax, [rbp+57h+var_90]
0x1800091c3  mov     [rsp+0E0h+var_B8], rax
0x1800091c8  mov     [rsp+0E0h+var_C0], 5
0x1800091d0  call    cs:__imp_EtwEventWriteTransfer
0x1800091d6  jmp     short loc_1800091DA
0x1800091d8  xor     esi, esi
0x1800091da  cmp     ebx, 8; switch 9 cases
0x1800091dd  ja      def_1800091F4; jumptable 00000001800091F4 default case, cases 3-5
0x1800091e3  lea     rdx, __ImageBase
0x1800091ea  mov     ecx, ds:(jpt_1800091F4 - 180000000h)[rdx+rbx*4]
0x1800091f1  add     rcx, rdx
0x1800091f4  jmp     rcx; switch jump
0x1800091f6  mov     ebx, 1; jumptable 00000001800091F4 case 0
0x1800091fb  jmp     short loc_18000921E
0x1800091fd  mov     ebx, 3; jumptable 00000001800091F4 case 1
0x180009202  jmp     short loc_18000921E
0x180009204  mov     ebx, 9; jumptable 00000001800091F4 case 7
0x180009209  jmp     short loc_18000921E
0x18000920b  mov     ebx, 0Ah; jumptable 00000001800091F4 case 8
0x180009210  jmp     short loc_18000921E
0x180009212  mov     ebx, 0FDE9h; jumptable 00000001800091F4 case 2
0x180009217  jmp     short loc_18000921E
0x180009219  mov     ebx, 0FDEDh; jumptable 00000001800091F4 case 6
0x18000921e  mov     eax, cs:dword_180173278
0x180009224  cmp     eax, 5
0x180009227  jbe     loc_18000941C
0x18000922d  mov     rcx, cs:qword_180173290
0x180009234  mov     rax, cs:qword_180173288
0x18000923b  test    al, 1
0x18000923d  jz      loc_18000941C
0x180009243  mov     rax, rcx
0x180009246  and     eax, 1
0x180009249  cmp     rax, rcx
0x18000924c  jnz     loc_18000941C
0x180009252  mov     rax, cs:gIkeExtGlobals
0x180009259  test    rax, rax
0x18000925c  jz      short loc_180009287
0x18000925e  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180009264  cmp     ecx, 0FFFFFFFFh
0x180009267  jz      short loc_180009287
0x180009269  call    cs:__imp_TlsGetValue
0x18000926f  test    rax, rax
0x180009272  jz      short loc_180009280
0x180009274  mov     rcx, [rax]
0x180009277  mov     rax, cs:gIkeExtGlobals
0x18000927e  jmp     short loc_18000928A
0x180009280  mov     rax, cs:gIkeExtGlobals
0x180009287  mov     rcx, rsi
0x18000928a  mov     [rbp+57h+var_A8], rcx
0x18000928e  lea     rcx, [rbp+57h+var_A8]
0x180009292  mov     [rbp+57h+var_70], rcx
0x180009296  mov     [rbp+57h+var_68], 8
0x18000929e  test    rax, rax
0x1800092a1  jz      short loc_1800092E5
0x1800092a3  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800092a9  cmp     ecx, 0FFFFFFFFh
0x1800092ac  jz      short loc_1800092E5
0x1800092ae  call    cs:__imp_TlsGetValue
0x1800092b4  test    rax, rax
0x1800092b7  lea     rdx, [rax+8]
0x1800092bb  cmovz   rdx, rsi
0x1800092bf  test    rdx, rdx
0x1800092c2  jz      short loc_1800092E5
0x1800092c4  mov     rax, rdi
0x1800092c7  nop     word ptr [rax+rax+00000000h]
0x1800092d0  cmp     [rdx+rax*2+2], r13w
0x1800092d6  lea     rax, [rax+1]
0x1800092da  jnz     short loc_1800092D0
0x1800092dc  lea     eax, ds:2[rax*2]
0x1800092e3  jmp     short loc_1800092F1
0x1800092e5  lea     rdx, LocaleName
0x1800092ec  mov     eax, 2
0x1800092f1  mov     [rbp+57h+var_58], eax
0x1800092f4  lea     rcx, _TraceLoggingMetadata
0x1800092fb  mov     [rbp+57h+var_60], rdx
0x1800092ff  lea     rax, aIkemmauthinter; "IkeMMAuthInternalToDoi"
0x180009306  mov     [rbp+57h+var_50], rax
0x18000930a  lea     rdx, [rbp+57h+var_A0]
0x18000930e  movzx   eax, cs:word_180166E61
0x180009315  xor     r9d, r9d
0x180009318  mov     [rbp+57h+var_9C], eax
0x18000931b  xor     r8d, r8d
0x18000931e  mov     rax, cs:off_180173280
0x180009325  mov     [rbp+57h+var_90], rax
0x180009329  mov     [rbp+57h+var_54], esi
0x18000932c  mov     [rbp+57h+var_48], 17h
0x180009334  mov     [rbp+57h+var_A0], 0B000000h
0x18000933b  mov     [rbp+57h+var_98], 1
0x180009343  movzx   eax, word ptr [rax]
0x180009346  mov     [rbp+57h+var_88], eax
0x180009349  lea     rax, byte_180166E6B
0x180009350  mov     [rbp+57h+var_80], rax
0x180009354  lea     rax, _TraceLoggingMetadataEnd
0x18000935b  sub     eax, ecx
0x18000935d  mov     [rbp+57h+var_84], 2
  ... truncated ...
```
