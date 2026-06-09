# IkeDetermineMMExchType

- ea: `0x180029490`
- end: `0x180029a34`
- name: `IkeDetermineMMExchType`
- size: `1444`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800416f0`

## callees

- `0x180025d88`
- `0x180029490`
- `0x180050850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002952c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029571`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800296d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002970c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029772`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800297b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800298f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029935`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002952c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029571`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800296d3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002970c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029772`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800297b7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800298f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029935`
- `ntdll!EtwEventWriteTransfer` at `0x180029640`
- `ntdll!EtwEventWriteTransfer` at `0x180029897`
- `ntdll!EtwEventWriteTransfer` at `0x1800299fe`
- `ntdll!EtwEventWriteTransfer` at `0x180029640`
- `ntdll!EtwEventWriteTransfer` at `0x180029897`
- `ntdll!EtwEventWriteTransfer` at `0x1800299fe`

## pseudocode

```c
__int64 __fastcall IkeDetermineMMExchType(__int64 a1)
{
  __int64 v2; // rbx
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
  int v13; // eax
  unsigned __int8 v14; // di
  _QWORD *v15; // rcx
  LPCRITICAL_SECTION v16; // rdx
  DWORD v17; // eax
  LPVOID v18; // rax
  LPVOID v19; // r8
  __int64 v20; // rsi
  DWORD v21; // eax
  __int64 *v22; // rax
  __int64 v23; // r9
  LPCRITICAL_SECTION v24; // rax
  DWORD v25; // ecx
  __int64 *v26; // rax
  __int64 v27; // rcx
  DWORD v28; // ecx
  char *v29; // rax
  const WCHAR *v30; // rdx
  __int64 v31; // rax
  int v32; // eax
  LPCRITICAL_SECTION v33; // rax
  DWORD v34; // ecx
  __int64 *v35; // rax
  __int64 v36; // rcx
  DWORD v37; // ecx
  char *v38; // rax
  const WCHAR *v39; // rdx
  int v40; // ebx
  __int64 v42; // [rsp+38h] [rbp-61h] BYREF
  char *v43; // [rsp+40h] [rbp-59h] BYREF
  int v44; // [rsp+48h] [rbp-51h]
  int v45; // [rsp+4Ch] [rbp-4Dh]
  int *v46; // [rsp+50h] [rbp-49h]
  int v47; // [rsp+58h] [rbp-41h]
  int v48; // [rsp+5Ch] [rbp-3Dh]
  __int64 *v49; // [rsp+60h] [rbp-39h]
  __int64 v50; // [rsp+68h] [rbp-31h]
  const WCHAR *v51; // [rsp+70h] [rbp-29h]
  int v52; // [rsp+78h] [rbp-21h]
  int v53; // [rsp+7Ch] [rbp-1Dh]
  const char *v54; // [rsp+80h] [rbp-19h]
  __int64 v55; // [rsp+88h] [rbp-11h]
  _QWORD *v56; // [rsp+90h] [rbp-9h]
  __int64 v57; // [rsp+98h] [rbp-1h]
  _QWORD v58[2]; // [rsp+A0h] [rbp+7h] BYREF
  int v59; // [rsp+B0h] [rbp+17h] BYREF
  int v60; // [rsp+B4h] [rbp+1Bh]
  __int64 v61; // [rsp+B8h] [rbp+1Fh]

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
  v42 = v6;
  v49 = &v42;
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
  v43 = off_180173280;
  v51 = v9;
  v53 = 0;
  v54 = "IkeDetermineMMExchType";
  v55 = 23;
  v58[0] = 0x50B000000LL;
  v58[1] = 1;
  v44 = *(unsigned __int16 *)off_180173280;
  v46 = &dword_180166EA4;
  v45 = 2;
  v47 = 45;
  v48 = 1;
  EtwEventWriteTransfer(qword_180173298, v58, 0, 0, 5, &v43);
LABEL_20:
  v13 = *(_DWORD *)(a1 + 584);
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      v14 = -13;
    }
    else if ( *(_QWORD *)(*(_QWORD *)(a1 + 1104) + 464LL) )
    {
      v14 = 36;
    }
    else
    {
      v14 = (**(_DWORD **)(a1 + 616) != 0) + 34;
    }
  }
  else
  {
    v14 = 2;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v16 = gIkeExtGlobals;
    if ( !gIkeExtGlobals || (v17 = (DWORD)gIkeExtGlobals[86].LockSemaphore, v17 == -1) )
    {
      v19 = 0;
    }
    else
    {
      v18 = TlsGetValue(v17);
      v15 = WPP_GLOBAL_Control;
      v19 = v18;
      v16 = gIkeExtGlobals;
    }
    v20 = (__int64)v19 + 8;
    if ( !v19 )
      v20 = 0;
    if ( v16
      && (v21 = (DWORD)v16[86].LockSemaphore, v21 != -1)
      && (v22 = (__int64 *)TlsGetValue(v21), v15 = WPP_GLOBAL_Control, v22) )
    {
      v23 = *v22;
    }
    else
    {
      LODWORD(v23) = 0;
    }
    WPP_SF_iSq(v15[2], 35, (unsigned int)WPP_27bc70e61d40360834a5a0166f146b13_Traceguids, v23, v20, a1);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v24 = gIkeExtGlobals;
    if ( gIkeExtGlobals )
    {
      v25 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
      if ( v25 != -1 )
      {
        v26 = (__int64 *)TlsGetValue(v25);
        if ( v26 )
        {
          v27 = *v26;
          v24 = gIkeExtGlobals;
LABEL_49:
          v42 = v27;
          v49 = &v42;
          v50 = 8;
          if ( !v24 )
            goto LABEL_57;
          v28 = (DWORD)v24[86].LockSemaphore;
          if ( v28 == -1 )
            goto LABEL_57;
          v29 = (char *)TlsGetValue(v28);
          v30 = (const WCHAR *)(v29 + 8);
          if ( !v29 )
            v30 = 0;
          if ( v30 )
          {
            v31 = -1;
            do
              v11 = v30[++v31] == 0;
            while ( !v11 );
            v32 = 2 * v31 + 2;
          }
          else
          {
LABEL_57:
            v30 = &LocaleName;
            v32 = 2;
          }
          v52 = v32;
          v51 = v30;
          v54 = "The exchange type has been set";
          v53 = 0;
          v56 = v58;
          v60 = 4;
          v43 = off_180173280;
          v55 = 31;
          v58[0] = a1;
          v57 = 8;
          v59 = 184549376;
          v61 = 0;
          v44 = *(unsigned __int16 *)off_180173280;
          v46 = (int *)&unk_180152668;
          v45 = 2;
          v47 = 63;
          v48 = 1;
          EtwEventWriteTransfer(qword_180173298, &v59, 0, 0, 6, &v43);
          goto LABEL_59;
        }
        v24 = gIkeExtGlobals;
      }
    }
    v27 = 0;
    goto LABEL_49;
  }
LABEL_59:
  if ( (unsigned int)dword_180173278 <= 5 || (qword_180173288 & 1) == 0 || (qword_180173290 & 1) != qword_180173290 )
    return v14;
  v33 = gIkeExtGlobals;
  if ( !gIkeExtGlobals )
    goto LABEL_67;
  v34 = (DWORD)gIkeExtGlobals[86].LockSemaphore;
  if ( v34 == -1 )
    goto LABEL_67;
  v35 = (__int64 *)TlsGetValue(v34);
  if ( !v35 )
  {
    v33 = gIkeExtGlobals;
LABEL_67:
    v36 = 0;
    goto LABEL_68;
  }
  v36 = *v35;
  v33 = gIkeExtGlobals;
LABEL_68:
  v58[0] = v36;
  v49 = v58;
  v50 = 8;
  if ( !v33 )
    goto LABEL_75;
  v37 = (DWORD)v33[86].LockSemaphore;
  if ( v37 == -1 )
    goto LABEL_75;
  v38 = (char *)TlsGetValue(v37);
  v39 = (const WCHAR *)(v38 + 8);
  if ( !v38 )
    v39 = 0;
  if ( v39 )
  {
    do
      v11 = v39[++v2] == 0;
    while ( !v11 );
    v40 = 2 * v2 + 2;
  }
  else
  {
LABEL_75:
    v39 = &LocaleName;
    v40 = 2;
  }
  v60 = 5;
  v43 = off_180173280;
  v51 = v39;
  v52 = v40;
  v53 = 0;
  v54 = "IkeDetermineMMExchType";
  v55 = 23;
  v59 = 184549376;
  v61 = 1;
  v44 = *(unsigned __int16 *)off_180173280;
  v46 = (int *)byte_180166E6B;
  v45 = 2;
  v47 = 45;
  v48 = 1;
  EtwEventWriteTransfer(qword_180173298, &v59, 0, 0, 5, &v43);
  return v14;
}

```

## disassembly

```asm
0x180029490  mov     [rsp-8+arg_18], rbx
0x180029495  push    rbp
0x180029496  push    rsi
0x180029497  push    r12
0x180029499  push    r13
0x18002949b  push    r15
0x18002949d  lea     rbp, [rsp-37h]
0x1800294a2  sub     rsp, 0D0h
0x1800294a9  mov     rax, cs:__security_cookie
0x1800294b0  xor     rax, rsp
0x1800294b3  mov     [rbp+57h+var_30], rax
0x1800294b7  mov     eax, cs:dword_180173278
0x1800294bd  lea     rsi, aIkedeterminemm_3; "IkeDetermineMMExchType"
0x1800294c4  xor     r12d, r12d
0x1800294c7  mov     [rsp+0F0h+arg_10], r14
0x1800294cf  lea     r15, _TraceLoggingMetadataEnd
0x1800294d6  mov     r14, rcx
0x1800294d9  lea     r13, _TraceLoggingMetadata
0x1800294e0  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800294e7  cmp     eax, 5
0x1800294ea  jbe     loc_180029646
0x1800294f0  mov     rcx, cs:qword_180173290
0x1800294f7  mov     rax, cs:qword_180173288
0x1800294fe  test    al, 1
0x180029500  jz      loc_180029646
0x180029506  mov     rax, rcx
0x180029509  and     eax, 1
0x18002950c  cmp     rax, rcx
0x18002950f  jnz     loc_180029646
0x180029515  mov     rax, cs:gIkeExtGlobals
0x18002951c  test    rax, rax
0x18002951f  jz      short loc_18002954A
0x180029521  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180029527  cmp     ecx, 0FFFFFFFFh
0x18002952a  jz      short loc_18002954A
0x18002952c  call    cs:__imp_TlsGetValue
0x180029532  test    rax, rax
0x180029535  jz      short loc_180029543
0x180029537  mov     rcx, [rax]
0x18002953a  mov     rax, cs:gIkeExtGlobals
0x180029541  jmp     short loc_18002954D
0x180029543  mov     rax, cs:gIkeExtGlobals
0x18002954a  mov     rcx, r12
0x18002954d  mov     [rbp+57h+var_B8], rcx
0x180029551  lea     rcx, [rbp+57h+var_B8]
0x180029555  mov     [rbp+57h+var_90], rcx
0x180029559  mov     [rbp+57h+var_88], 8
0x180029561  test    rax, rax
0x180029564  jz      short loc_1800295A5
0x180029566  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002956c  cmp     ecx, 0FFFFFFFFh
0x18002956f  jz      short loc_1800295A5
0x180029571  call    cs:__imp_TlsGetValue
0x180029577  test    rax, rax
0x18002957a  lea     rdx, [rax+8]
0x18002957e  cmovz   rdx, r12
0x180029582  test    rdx, rdx
0x180029585  jz      short loc_1800295A5
0x180029587  mov     rax, rbx
0x18002958a  nop     word ptr [rax+rax+00h]
0x180029590  cmp     [rdx+rax*2+2], r12w
0x180029596  lea     rax, [rax+1]
0x18002959a  jnz     short loc_180029590
0x18002959c  lea     eax, ds:2[rax*2]
0x1800295a3  jmp     short loc_1800295B1
0x1800295a5  lea     rdx, LocaleName
0x1800295ac  mov     eax, 2
0x1800295b1  mov     [rbp+57h+var_78], eax
0x1800295b4  xor     r9d, r9d
0x1800295b7  movzx   eax, cs:word_180166E9A
0x1800295be  xor     r8d, r8d
0x1800295c1  mov     dword ptr [rbp+57h+var_50+4], eax
0x1800295c4  mov     rax, cs:off_180173280
0x1800295cb  mov     [rbp+57h+var_B0], rax
0x1800295cf  mov     [rbp+57h+var_80], rdx
0x1800295d3  lea     rdx, [rbp+57h+var_50]
0x1800295d7  mov     [rbp+57h+var_74], r12d
0x1800295db  mov     [rbp+57h+var_70], rsi
0x1800295df  mov     [rbp+57h+var_68], 17h
0x1800295e7  mov     dword ptr [rbp+57h+var_50], 0B000000h
0x1800295ee  mov     [rbp+57h+var_48], 1
0x1800295f6  movzx   eax, word ptr [rax]
0x1800295f9  mov     [rbp+57h+var_A8], eax
0x1800295fc  lea     rax, dword_180166EA4
0x180029603  mov     [rbp+57h+var_A0], rax
0x180029607  mov     rax, r15
0x18002960a  sub     eax, r13d
0x18002960d  mov     [rbp+57h+var_A4], 2
0x180029614  mov     [rbp+57h+var_98], 2Dh ; '-'
0x18002961b  mov     [rbp+57h+var_94], 1
0x180029622  mov     [rbp+57h+var_C0], eax
0x180029625  mov     eax, [rbp+57h+var_C0]
0x180029628  mov     rcx, cs:qword_180173298
0x18002962f  lea     rax, [rbp+57h+var_B0]
0x180029633  mov     [rsp+0F0h+var_C8], rax
0x180029638  mov     dword ptr [rsp+0F0h+var_D0], 5
0x180029640  call    cs:__imp_EtwEventWriteTransfer
0x180029646  mov     eax, [r14+248h]
0x18002964d  mov     [rsp+0F0h+arg_8], rdi
0x180029655  test    eax, eax
0x180029657  jnz     short loc_18002965E
0x180029659  mov     dil, 2
0x18002965c  jmp     short loc_18002968F
0x18002965e  cmp     eax, 1
0x180029661  jnz     short loc_180029668
0x180029663  mov     dil, 0F3h
0x180029666  jmp     short loc_18002968F
0x180029668  mov     rax, [r14+450h]
0x18002966f  cmp     [rax+1D0h], r12
0x180029676  jz      short loc_18002967D
0x180029678  mov     dil, 24h ; '$'
0x18002967b  jmp     short loc_18002968F
0x18002967d  mov     rax, [r14+268h]
0x180029684  cmp     [rax], r12d
0x180029687  setnz   dil
0x18002968b  add     dil, 22h ; '"'
0x18002968f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029696  lea     rax, WPP_GLOBAL_Control
0x18002969d  cmp     rcx, rax
0x1800296a0  jz      loc_18002974C
0x1800296a6  cmp     byte ptr [rcx+19h], 4
0x1800296aa  jb      loc_18002974C
0x1800296b0  test    byte ptr [rcx+1Ch], 10h
0x1800296b4  jz      loc_18002974C
0x1800296ba  mov     rdx, cs:gIkeExtGlobals
0x1800296c1  test    rdx, rdx
0x1800296c4  jz      short loc_1800296EC
0x1800296c6  mov     eax, [rdx+0D88h]
0x1800296cc  cmp     eax, 0FFFFFFFFh
0x1800296cf  jz      short loc_1800296EC
0x1800296d1  mov     ecx, eax; dwTlsIndex
0x1800296d3  call    cs:__imp_TlsGetValue
0x1800296d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800296e0  mov     r8, rax
0x1800296e3  mov     rdx, cs:gIkeExtGlobals
0x1800296ea  jmp     short loc_1800296EF
0x1800296ec  mov     r8, r12
0x1800296ef  test    r8, r8
0x1800296f2  lea     rsi, [r8+8]
0x1800296f6  cmovz   rsi, r12
0x1800296fa  test    rdx, rdx
0x1800296fd  jz      short loc_180029723
0x1800296ff  mov     eax, [rdx+0D88h]
0x180029705  cmp     eax, 0FFFFFFFFh
0x180029708  jz      short loc_180029723
0x18002970a  mov     ecx, eax; dwTlsIndex
0x18002970c  call    cs:__imp_TlsGetValue
0x180029712  mov     rcx, cs:WPP_GLOBAL_Control
0x180029719  test    rax, rax
0x18002971c  jz      short loc_180029723
0x18002971e  mov     r9, [rax]
0x180029721  jmp     short loc_180029726
0x180029723  mov     r9, r12
0x180029726  mov     rcx, [rcx+10h]
0x18002972a  lea     r8, WPP_27bc70e61d40360834a5a0166f146b13_Traceguids
0x180029731  mov     edx, 23h ; '#'
0x180029736  mov     [rsp+0F0h+var_C8], r14
0x18002973b  mov     [rsp+0F0h+var_D0], rsi
0x180029740  call    WPP_SF_iSq
0x180029745  lea     rsi, aIkedeterminemm_3; "IkeDetermineMMExchType"
0x18002974c  mov     eax, cs:dword_180173278
0x180029752  cmp     eax, 4
0x180029755  jbe     loc_18002989D
0x18002975b  mov     rax, cs:gIkeExtGlobals
0x180029762  test    rax, rax
0x180029765  jz      short loc_180029790
0x180029767  mov     ecx, [rax+0D88h]; dwTlsIndex
0x18002976d  cmp     ecx, 0FFFFFFFFh
0x180029770  jz      short loc_180029790
0x180029772  call    cs:__imp_TlsGetValue
0x180029778  test    rax, rax
0x18002977b  jz      short loc_180029789
0x18002977d  mov     rcx, [rax]
0x180029780  mov     rax, cs:gIkeExtGlobals
0x180029787  jmp     short loc_180029793
0x180029789  mov     rax, cs:gIkeExtGlobals
0x180029790  mov     rcx, r12
0x180029793  mov     [rbp+57h+var_B8], rcx
0x180029797  lea     rcx, [rbp+57h+var_B8]
0x18002979b  mov     [rbp+57h+var_90], rcx
0x18002979f  mov     [rbp+57h+var_88], 8
0x1800297a7  test    rax, rax
0x1800297aa  jz      short loc_1800297E5
0x1800297ac  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800297b2  cmp     ecx, 0FFFFFFFFh
0x1800297b5  jz      short loc_1800297E5
0x1800297b7  call    cs:__imp_TlsGetValue
0x1800297bd  test    rax, rax
0x1800297c0  lea     rdx, [rax+8]
0x1800297c4  cmovz   rdx, r12
0x1800297c8  test    rdx, rdx
0x1800297cb  jz      short loc_1800297E5
0x1800297cd  mov     rax, rbx
0x1800297d0  cmp     [rdx+rax*2+2], r12w
0x1800297d6  lea     rax, [rax+1]
0x1800297da  jnz     short loc_1800297D0
0x1800297dc  lea     eax, ds:2[rax*2]
0x1800297e3  jmp     short loc_1800297F1
0x1800297e5  lea     rdx, LocaleName
0x1800297ec  mov     eax, 2
0x1800297f1  mov     [rbp+57h+var_78], eax
0x1800297f4  xor     r9d, r9d
0x1800297f7  mov     [rbp+57h+var_80], rdx
0x1800297fb  lea     rax, aTheExchangeTyp; "The exchange type has been set"
0x180029802  mov     [rbp+57h+var_70], rax
0x180029806  lea     rdx, [rbp+57h+var_40]
0x18002980a  lea     rax, [rbp+57h+var_50]
0x18002980e  mov     [rbp+57h+var_74], r12d
0x180029812  mov     [rbp+57h+var_60], rax
0x180029816  xor     r8d, r8d
0x180029819  movzx   eax, cs:word_18015265E
0x180029820  mov     [rbp+57h+var_3C], eax
0x180029823  mov     rax, cs:off_180173280
0x18002982a  mov     [rbp+57h+var_B0], rax
0x18002982e  mov     [rbp+57h+var_68], 1Fh
0x180029836  mov     [rbp+57h+var_50], r14
0x18002983a  mov     [rbp+57h+var_58], 8
0x180029842  mov     [rbp+57h+var_40], 0B000000h
0x180029849  mov     [rbp+57h+var_38], r12
0x18002984d  movzx   eax, word ptr [rax]
0x180029850  mov     [rbp+57h+var_A8], eax
0x180029853  lea     rax, unk_180152668
0x18002985a  mov     [rbp+57h+var_A0], rax
0x18002985e  mov     rax, r15
0x180029861  sub     eax, r13d
0x180029864  mov     [rbp+57h+var_A4], 2
0x18002986b  mov     [rbp+57h+var_98], 3Fh ; '?'
0x180029872  mov     [rbp+57h+var_94], 1
0x180029879  mov     [rbp+57h+var_C0], eax
0x18002987c  mov     eax, [rbp+57h+var_C0]
0x18002987f  mov     rcx, cs:qword_180173298
0x180029886  lea     rax, [rbp+57h+var_B0]
0x18002988a  mov     [rsp+0F0h+var_C8], rax
0x18002988f  mov     dword ptr [rsp+0F0h+var_D0], 6
0x180029897  call    cs:__imp_EtwEventWriteTransfer
0x18002989d  mov     eax, cs:dword_180173278
0x1800298a3  mov     r14, [rsp+0F0h+arg_10]
0x1800298ab  cmp     eax, 5
0x1800298ae  jbe     loc_180029A04
0x1800298b4  mov     rcx, cs:qword_180173290
0x1800298bb  mov     rax, cs:qword_180173288
0x1800298c2  test    al, 1
0x1800298c4  jz      loc_180029A04
0x1800298ca  mov     rax, rcx
0x1800298cd  and     eax, 1
0x1800298d0  cmp     rax, rcx
0x1800298d3  jnz     loc_180029A04
0x1800298d9  mov     rax, cs:gIkeExtGlobals
0x1800298e0  test    rax, rax
0x1800298e3  jz      short loc_18002990E
0x1800298e5  mov     ecx, [rax+0D88h]; dwTlsIndex
0x1800298eb  cmp     ecx, 0FFFFFFFFh
0x1800298ee  jz      short loc_18002990E
0x1800298f0  call    cs:__imp_TlsGetValue
0x1800298f6  test    rax, rax
0x1800298f9  jz      short loc_180029907
0x1800298fb  mov     rcx, [rax]
0x1800298fe  mov     rax, cs:gIkeExtGlobals
0x180029905  jmp     short loc_180029911
0x180029907  mov     rax, cs:gIkeExtGlobals
0x18002990e  mov     rcx, r12
0x180029911  mov     [rbp+57h+var_50], rcx
0x180029915  lea     rcx, [rbp+57h+var_50]
0x180029919  mov     [rbp+57h+var_90], rcx
0x18002991d  mov     [rbp+57h+var_88], 8
0x180029925  test    rax, rax
0x180029928  jz      short loc_180029965
0x18002992a  mov     ecx, [rax+0D88h]; dwTlsIndex
0x180029930  cmp     ecx, 0FFFFFFFFh
0x180029933  jz      short loc_180029965
0x180029935  call    cs:__imp_TlsGetValue
0x18002993b  test    rax, rax
0x18002993e  lea     rdx, [rax+8]
0x180029942  cmovz   rdx, r12
0x180029946  test    rdx, rdx
0x180029949  jz      short loc_180029965
0x18002994b  nop     dword ptr [rax+rax+00h]
0x180029950  cmp     [rdx+rbx*2+2], r12w
0x180029956  lea     rbx, [rbx+1]
0x18002995a  jnz     short loc_180029950
0x18002995c  lea     ebx, ds:2[rbx*2]
0x180029963  jmp     short loc_180029971
0x180029965  lea     rdx, LocaleName
0x18002996c  mov     ebx, 2
0x180029971  movzx   eax, cs:word_180166E61
0x180029978  sub     r15d, r13d
0x18002997b  mov     [rbp+57h+var_3C], eax
0x18002997e  xor     r9d, r9d
0x180029981  mov     rax, cs:off_180173280
0x180029988  xor     r8d, r8d
0x18002998b  mov     [rbp+57h+var_B0], rax
0x18002998f  mov     [rbp+57h+var_80], rdx
0x180029993  lea     rdx, [rbp+57h+var_40]
0x180029997  mov     [rbp+57h+var_78], ebx
0x18002999a  mov     [rbp+57h+var_74], r12d
0x18002999e  mov     [rbp+57h+var_70], rsi
0x1800299a2  mov     [rbp+57h+var_68], 17h
0x1800299aa  mov     [rbp+57h+var_40], 0B000000h
0x1800299b1  mov     [rbp+57h+var_38], 1
0x1800299b9  movzx   eax, word ptr [rax]
  ... truncated ...
```
