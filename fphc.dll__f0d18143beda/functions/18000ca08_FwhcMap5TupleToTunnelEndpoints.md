# FwhcMap5TupleToTunnelEndpoints

- ea: `0x18000ca08`
- end: `0x18000cfed`
- name: `FwhcMap5TupleToTunnelEndpoints`
- size: `1509`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008b74`

## callees

- `0x18000ca08`
- `0x18000ee60`
- `0x18000eed4`
- `0x180010e48`
- `0x180011302`
- `0x180011340`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18000cb39`
- `WS2_32!__imp_ntohl` at `0x18000cbb2`
- `WS2_32!__imp_ntohl` at `0x18000cb39`
- `WS2_32!__imp_ntohl` at `0x18000cbb2`
- `WS2_32!__imp_ntohs` at `0x18000cb4f`
- `WS2_32!__imp_ntohs` at `0x18000cbc3`
- `WS2_32!__imp_ntohs` at `0x18000cc54`
- `WS2_32!__imp_ntohs` at `0x18000ccd1`
- `WS2_32!__imp_ntohs` at `0x18000cb4f`
- `WS2_32!__imp_ntohs` at `0x18000cbc3`
- `WS2_32!__imp_ntohs` at `0x18000cc54`
- `WS2_32!__imp_ntohs` at `0x18000ccd1`
- `fwpuclnt!FwpmEngineClose0` at `0x18000cfbb`
- `fwpuclnt!FwpmEngineClose0` at `0x18000cfbb`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000cfab`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000cfab`
- `fwpuclnt!FwpmFilterEnum0` at `0x18000cda3`
- `fwpuclnt!FwpmFilterEnum0` at `0x18000cda3`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18000cd6d`
- `fwpuclnt!FwpmFilterCreateEnumHandle0` at `0x18000cd6d`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000cd3f`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000cd3f`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x18000cf99`
- `fwpuclnt!FwpmFilterDestroyEnumHandle0` at `0x18000cf99`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x18000cdea`
- `fwpuclnt!FwpmProviderContextGetByKey3` at `0x18000cdea`

## pseudocode

```c
__int64 __fastcall FwhcMap5TupleToTunnelEndpoints(
        char *a1,
        _WORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _WORD *a6,
        _WORD *a7,
        _DWORD *a8,
        _QWORD *a9,
        _DWORD *a10)
{
  UINT32 v14; // edi
  char v15; // si
  __int64 v16; // r12
  char v17; // al
  u_long v18; // ecx
  __int64 v19; // rbx
  u_short v20; // ax
  __int64 v21; // rdx
  u_long v22; // ecx
  __int64 v23; // rbx
  u_short v24; // ax
  __int64 v25; // rdx
  unsigned int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // rcx
  u_short v29; // ax
  __int64 v30; // rdx
  unsigned int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rcx
  GUID v34; // xmm0
  FWPM_FILTER_CONDITION0 *filterCondition; // rax
  signed int v36; // eax
  signed int v37; // ebx
  signed int v38; // eax
  signed int v39; // eax
  UINT32 v40; // eax
  int v41; // edi
  int v42; // eax
  __int64 v43; // rdx
  int v44; // ecx
  _WORD *v45; // rax
  _WORD *v46; // rax
  unsigned __int32 v47; // ecx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  _WORD *v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r9
  unsigned int v55; // r8d
  _DWORD *v56; // r11
  __int64 v57; // rdx
  int v58; // ecx
  __int64 v59; // r10
  unsigned __int64 v60; // rcx
  UINT32 numEntriesReturned; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE engineHandle; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v64; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v65; // [rsp+48h] [rbp-B8h] BYREF
  FWPM_FILTER0 **entries; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE enumHandle; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v68; // [rsp+60h] [rbp-A0h]
  __int64 v69; // [rsp+68h] [rbp-98h]
  _WORD *v70; // [rsp+70h] [rbp-90h]
  _DWORD *v71; // [rsp+78h] [rbp-88h]
  _DWORD *v72; // [rsp+80h] [rbp-80h]
  _QWORD *v73; // [rsp+88h] [rbp-78h]
  FWPM_FILTER_ENUM_TEMPLATE0 enumTemplate; // [rsp+90h] [rbp-70h] BYREF
  GUID v75; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v76[2]; // [rsp+F0h] [rbp-10h]
  int v77; // [rsp+F8h] [rbp-8h]
  _QWORD v78[36]; // [rsp+100h] [rbp+0h]

  v70 = a6;
  v69 = a5;
  v68 = a7;
  v72 = a8;
  v73 = a9;
  v71 = a10;
  memset_0(&v75, 0, 0x140u);
  v14 = 0;
  numEntriesReturned = 0;
  engineHandle = 0;
  memset_0(&enumTemplate, 0, sizeof(enumTemplate));
  *a10 = 0;
  v15 = 1;
  enumHandle = 0;
  v16 = 0;
  entries = 0;
  v64 = 0;
  v65 = 0;
  if ( a1 )
  {
    v17 = *a1;
    v14 = 1;
    v76[0] = 0;
    v75 = FWPM_CONDITION_IP_PROTOCOL;
    v77 = 1;
    LOBYTE(v78[0]) = v17;
  }
  if ( !a2 )
    goto LABEL_30;
  if ( *a2 == 2 )
  {
    if ( a3 )
    {
      v18 = *(_DWORD *)(a3 + 4);
      if ( v18 )
      {
        v19 = 5LL * v14;
        *(GUID *)((char *)&v75 + 8 * v19) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
        v76[2 * v19] = 0;
        LODWORD(v78[v19]) = 3;
        LODWORD(v78[5 * v14++]) = ntohl(v18);
      }
      v20 = ntohs(*(_WORD *)(a3 + 2));
      a3 = 0;
      v21 = 5LL * v14;
      LOWORD(v78[5 * v14]) = v20;
      if ( v20 )
      {
        v76[10 * v14++] = 0;
        LODWORD(v78[v21]) = 2;
        *(GUID *)((char *)&v75 + 8 * v21) = FWPM_CONDITION_IP_LOCAL_PORT;
      }
    }
    if ( a4 )
    {
      v22 = *(_DWORD *)(a4 + 4);
      if ( v22 )
      {
        v23 = 5LL * v14;
        *(GUID *)((char *)&v75 + 8 * v23) = FWPM_CONDITION_IP_REMOTE_ADDRESS;
        v76[2 * v23] = a3;
        LODWORD(v78[v23]) = 3;
        LODWORD(v78[5 * v14++]) = ntohl(v22);
      }
LABEL_13:
      v24 = ntohs(*(_WORD *)(a4 + 2));
      v25 = 5LL * v14;
      LOWORD(v78[5 * v14]) = v24;
      if ( (_WORD)a3 != v24 )
      {
        ++v14;
        *(GUID *)((char *)&v75 + 8 * v25) = FWPM_CONDITION_IP_REMOTE_PORT;
        v76[2 * v25] = a3;
        LODWORD(v78[v25]) = 2;
      }
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( *a2 != 23 )
  {
LABEL_30:
    a3 = 0;
    goto LABEL_31;
  }
  if ( a3 )
  {
    v26 = 0;
    while ( !*(_WORD *)(a3 + 2LL * v26 + 8) )
    {
      if ( (int)++v26 >= 8 )
        goto LABEL_22;
    }
    v27 = v14++;
    v28 = 5 * v27;
    v76[2 * v28] = 0;
    v78[v28] = a3 + 8;
    *(GUID *)((char *)&v75 + 8 * v28) = FWPM_CONDITION_IP_LOCAL_ADDRESS;
    LODWORD(v78[v28]) = 11;
LABEL_22:
    v29 = ntohs(*(_WORD *)(a3 + 2));
    a3 = 0;
    v30 = 5LL * v14;
    LOWORD(v78[5 * v14]) = v29;
    if ( v29 )
    {
      v76[10 * v14++] = 0;
      LODWORD(v78[v30]) = 2;
      *(GUID *)((char *)&v75 + 8 * v30) = FWPM_CONDITION_IP_LOCAL_PORT;
    }
  }
  if ( a4 )
  {
    v31 = a3;
    while ( *(_WORD *)(a4 + 2LL * v31 + 8) == (_WORD)a3 )
    {
      if ( (int)++v31 >= 8 )
        goto LABEL_13;
    }
    v32 = v14++;
    v33 = 5 * v32;
    v76[2 * v33] = a3;
    v78[v33] = a4 + 8;
    *(GUID *)((char *)&v75 + 8 * v33) = FWPM_CONDITION_IP_REMOTE_ADDRESS;
    LODWORD(v78[v33]) = 11;
    goto LABEL_13;
  }
LABEL_31:
  memset_0(&enumTemplate, 0, sizeof(enumTemplate));
  if ( *a2 == 2 )
    v34 = FWPM_LAYER_IPSEC_V4;
  else
    v34 = FWPM_LAYER_IPSEC_V6;
  enumTemplate.numFilterConditions = v14;
  filterCondition = (FWPM_FILTER_CONDITION0 *)&v75;
  if ( !v14 )
    filterCondition = enumTemplate.filterCondition;
  enumTemplate.filterCondition = filterCondition;
  enumTemplate.actionMask = -1;
  enumTemplate.layerKey = v34;
  v36 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v37 = v36;
  if ( v36 > 0 )
    v37 = (unsigned __int16)v36 | 0x80070000;
  if ( v37 < 0 )
  {
    v15 = a3;
    goto LABEL_73;
  }
  v38 = FwpmFilterCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
  v37 = v38;
  if ( v38 > 0 )
    v37 = (unsigned __int16)v38 | 0x80070000;
  if ( v37 < 0 )
    goto LABEL_70;
  v39 = FwpmFilterEnum0(engineHandle, enumHandle, 0xFFFFFFFF, &entries, &numEntriesReturned);
  v37 = v39;
  if ( v39 > 0 )
    v37 = (unsigned __int16)v39 | 0x80070000;
  if ( v37 < 0 )
    goto LABEL_73;
  v40 = numEntriesReturned;
  v41 = a3;
  if ( numEntriesReturned )
  {
    while ( 1 )
    {
      v42 = FwpmProviderContextGetByKey3(engineHandle, &entries[v41]->rawContext, &v64);
      v37 = v42;
      if ( v42 > 0 )
        v37 = (unsigned __int16)v42 | 0x80070000;
      if ( v37 < 0 )
        goto LABEL_73;
      v43 = v64;
      v40 = numEntriesReturned;
      if ( ((*(_DWORD *)(v64 + 64) - 2) & 0xFFFFFFFD) != 0 && ++v41 < numEntriesReturned )
        continue;
      goto LABEL_53;
    }
  }
  v43 = v64;
LABEL_53:
  if ( v41 != v40 )
  {
    *v71 = 1;
    v44 = *(_DWORD *)(*(_QWORD *)(v43 + 72) + 16LL);
    if ( v44 )
    {
      if ( v44 == 1 )
      {
        v48 = v69;
        *v68 = 23;
        v49 = *(_QWORD *)(v43 + 72);
        *(_WORD *)v48 = 23;
        *(_OWORD *)(v48 + 8) = *(_OWORD *)(v49 + 20);
        v50 = *(_QWORD *)(v43 + 72);
        v51 = v70;
        *v70 = 23;
        *(_OWORD *)(v51 + 4) = *(_OWORD *)(v50 + 36);
      }
      else
      {
        v37 = 1;
      }
    }
    else
    {
      *v68 = 2;
      v45 = (_WORD *)v69;
      *(_DWORD *)(v69 + 4) = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v43 + 72) + 20LL));
      *v45 = 2;
      v46 = v70;
      v47 = _byteswap_ulong(*(_DWORD *)(*(_QWORD *)(v43 + 72) + 36LL));
      *v70 = 2;
      *((_DWORD *)v46 + 1) = v47;
    }
    v52 = *(_QWORD *)(v43 + 72);
    if ( *(_QWORD *)(v52 + 80) != a3 )
    {
      v53 = WfpMemAlloc((unsigned __int64)*(unsigned int *)(v52 + 72) << 7, 8u);
      if ( v53 && WfpReportError(v53, "WfpMemAllocArray") )
      {
        v16 = v65;
      }
      else
      {
        v54 = v64;
        v55 = a3;
        v56 = v72;
        v57 = v65;
        v58 = *(_DWORD *)(*(_QWORD *)(v64 + 72) + 72LL);
        *v72 = v58;
        if ( v58 )
        {
          while ( 1 )
          {
            v59 = *(_QWORD *)(*(_QWORD *)(v54 + 72) + 80LL);
            v60 = (unsigned __int64)v55 << 7;
            if ( *(_DWORD *)(v59 + 20LL * v55) == (_DWORD)a3 )
            {
              *(_DWORD *)(v60 + v57 + 4) = _byteswap_ulong(*(_DWORD *)(v59 + 20LL * v55 + 4));
              *(_WORD *)(v60 + v57) = 2;
            }
            else
            {
              *(_WORD *)(v60 + v57) = 23;
              *(_OWORD *)(v60 + v57 + 8) = *(_OWORD *)(v59 + 20LL * v55 + 4);
            }
            if ( ++v55 >= *v56 )
              break;
            v54 = v64;
          }
        }
        v16 = a3;
        v65 = a3;
        *v73 = v57;
      }
LABEL_70:
      if ( v16 )
        WfpMemFree(&v65);
    }
  }
LABEL_73:
  if ( enumHandle )
    FwpmFilterDestroyEnumHandle0(engineHandle, enumHandle);
  if ( entries != (FWPM_FILTER0 **)a3 )
    FwpmFreeMemory0((void **)&entries);
  if ( v15 )
    FwpmEngineClose0(engineHandle);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18000ca08  mov     [rsp-8+arg_0], rbx
0x18000ca0d  push    rbp
0x18000ca0e  push    rsi
0x18000ca0f  push    rdi
0x18000ca10  push    r12
0x18000ca12  push    r13
0x18000ca14  push    r14
0x18000ca16  push    r15
0x18000ca18  lea     rbp, [rsp-130h]
0x18000ca20  sub     rsp, 230h
0x18000ca27  mov     rax, cs:__security_cookie
0x18000ca2e  xor     rax, rsp
0x18000ca31  mov     [rbp+160h+var_40], rax
0x18000ca38  mov     rax, [rbp+160h+arg_28]
0x18000ca3f  mov     r14, r8
0x18000ca42  mov     rsi, [rbp+160h+arg_48]
0x18000ca49  mov     r13, rdx
0x18000ca4c  mov     [rsp+260h+var_1F0], rax
0x18000ca51  mov     rbx, rcx
0x18000ca54  mov     rax, [rbp+160h+arg_20]
0x18000ca5b  lea     rcx, [rbp+160h+var_180]; void *
0x18000ca5f  mov     [rsp+260h+var_1F8], rax
0x18000ca64  xor     edx, edx; Val
0x18000ca66  mov     rax, [rbp+160h+arg_30]
0x18000ca6d  mov     r8d, 140h; Size
0x18000ca73  mov     [rsp+260h+var_200], rax
0x18000ca78  mov     r15, r9
0x18000ca7b  mov     rax, [rbp+160h+arg_38]
0x18000ca82  mov     [rbp+160h+var_1E0], rax
0x18000ca86  mov     rax, [rbp+160h+arg_40]
0x18000ca8d  mov     [rbp+160h+var_1D8], rax
0x18000ca91  mov     [rsp+260h+var_1E8], rsi
0x18000ca96  call    memset_0
0x18000ca9b  xor     edi, edi
0x18000ca9d  lea     rcx, [rbp+160h+enumTemplate]; void *
0x18000caa1  xor     edx, edx; Val
0x18000caa3  mov     [rsp+260h+numEntriesReturned], edi
0x18000caa7  mov     [rsp+260h+var_228], rdi
0x18000caac  lea     r8d, [rdi+48h]; Size
0x18000cab0  call    memset_0
0x18000cab5  xor     edx, edx
0x18000cab7  mov     [rsi], edx
0x18000cab9  lea     esi, [rdi+1]
0x18000cabc  mov     [rsp+260h+enumHandle], rdx
0x18000cac1  mov     r12d, edx
0x18000cac4  mov     [rsp+260h+entries], rdx
0x18000cac9  mov     [rsp+260h+var_220], rdx
0x18000cace  mov     [rsp+260h+var_218], rdx
0x18000cad3  test    rbx, rbx
0x18000cad6  jz      short loc_18000CAF1
0x18000cad8  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_PROTOCOL.Data1
0x18000cadf  mov     al, [rbx]
0x18000cae1  mov     edi, esi
0x18000cae3  mov     [rbp+160h+var_170], edx
0x18000cae6  movdqu  [rbp+160h+var_180], xmm0
0x18000caeb  mov     [rbp+160h+var_168], esi
0x18000caee  mov     byte ptr [rbp+160h+var_160], al
0x18000caf1  mov     eax, 17h
0x18000caf6  lea     ebx, [rax-15h]
0x18000caf9  test    r13, r13
0x18000cafc  jz      loc_18000CCDC
0x18000cb02  cmp     bx, [r13+0]
0x18000cb07  jnz     loc_18000CC00
0x18000cb0d  test    r14, r14
0x18000cb10  jz      short loc_18000CB81
0x18000cb12  mov     ecx, [r14+4]; netlong
0x18000cb16  test    ecx, ecx
0x18000cb18  jz      short loc_18000CB4A
0x18000cb1a  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x18000cb21  mov     eax, edi
0x18000cb23  lea     rbx, [rax+rax*4]
0x18000cb27  movdqu  [rbp+rbx*8+160h+var_180], xmm0
0x18000cb2d  mov     [rbp+rbx*8+160h+var_170], edx
0x18000cb31  mov     [rbp+rbx*8+160h+var_168], 3
0x18000cb39  call    cs:__imp_ntohl
0x18000cb3f  mov     dword ptr [rbp+rbx*8+160h+var_160], eax
0x18000cb43  add     edi, esi
0x18000cb45  mov     ebx, 2
0x18000cb4a  movzx   ecx, word ptr [r14+2]; netshort
0x18000cb4f  call    cs:__imp_ntohs
0x18000cb55  mov     ecx, edi
0x18000cb57  xor     r14d, r14d
0x18000cb5a  lea     rdx, [rcx+rcx*4]
0x18000cb5e  mov     word ptr [rbp+rdx*8+160h+var_160], ax
0x18000cb63  cmp     r14w, ax
0x18000cb67  jz      short loc_18000CB81
0x18000cb69  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18000cb70  mov     [rbp+rdx*8+160h+var_170], r14d
0x18000cb75  add     edi, esi
0x18000cb77  mov     [rbp+rdx*8+160h+var_168], ebx
0x18000cb7b  movdqu  [rbp+rdx*8+160h+var_180], xmm0
0x18000cb81  test    r15, r15
0x18000cb84  jz      loc_18000CCE1
0x18000cb8a  mov     ecx, [r15+4]; netlong
0x18000cb8e  test    ecx, ecx
0x18000cb90  jz      short loc_18000CBBE
0x18000cb92  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x18000cb99  mov     eax, edi
0x18000cb9b  lea     rbx, [rax+rax*4]
0x18000cb9f  movdqu  [rbp+rbx*8+160h+var_180], xmm0
0x18000cba5  mov     [rbp+rbx*8+160h+var_170], r14d
0x18000cbaa  mov     [rbp+rbx*8+160h+var_168], 3
0x18000cbb2  call    cs:__imp_ntohl
0x18000cbb8  mov     dword ptr [rbp+rbx*8+160h+var_160], eax
0x18000cbbc  add     edi, esi
0x18000cbbe  movzx   ecx, word ptr [r15+2]; netshort
0x18000cbc3  call    cs:__imp_ntohs
0x18000cbc9  mov     ebx, 2
0x18000cbce  mov     ecx, edi
0x18000cbd0  lea     rdx, [rcx+rcx*4]
0x18000cbd4  mov     word ptr [rbp+rdx*8+160h+var_160], ax
0x18000cbd9  cmp     r14w, ax
0x18000cbdd  jz      loc_18000CCE6
0x18000cbe3  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_PORT.Data1
0x18000cbea  add     edi, esi
0x18000cbec  movdqu  [rbp+rdx*8+160h+var_180], xmm0
0x18000cbf2  mov     [rbp+rdx*8+160h+var_170], r14d
0x18000cbf7  mov     [rbp+rdx*8+160h+var_168], ebx
0x18000cbfb  jmp     loc_18000CCE6
0x18000cc00  cmp     ax, [r13+0]
0x18000cc05  jnz     loc_18000CCDC
0x18000cc0b  test    r14, r14
0x18000cc0e  jz      short loc_18000CC86
0x18000cc10  mov     ecx, edx
0x18000cc12  mov     eax, ecx
0x18000cc14  cmp     [r14+rax*2+8], dx
0x18000cc1a  jnz     short loc_18000CC25
0x18000cc1c  add     ecx, esi
0x18000cc1e  cmp     ecx, 8
0x18000cc21  jl      short loc_18000CC12
0x18000cc23  jmp     short loc_18000CC4F
0x18000cc25  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_ADDRESS.Data1
0x18000cc2c  mov     eax, edi
0x18000cc2e  add     edi, esi
0x18000cc30  lea     rcx, [rax+rax*4]
0x18000cc34  lea     rax, [r14+8]
0x18000cc38  mov     [rbp+rcx*8+160h+var_170], edx
0x18000cc3c  mov     [rbp+rcx*8+160h+var_160], rax
0x18000cc41  movdqu  [rbp+rcx*8+160h+var_180], xmm0
0x18000cc47  mov     [rbp+rcx*8+160h+var_168], 0Bh
0x18000cc4f  movzx   ecx, word ptr [r14+2]; netshort
0x18000cc54  call    cs:__imp_ntohs
0x18000cc5a  mov     ecx, edi
0x18000cc5c  xor     r14d, r14d
0x18000cc5f  lea     rdx, [rcx+rcx*4]
0x18000cc63  mov     word ptr [rbp+rdx*8+160h+var_160], ax
0x18000cc68  cmp     r14w, ax
0x18000cc6c  jz      short loc_18000CC86
0x18000cc6e  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_LOCAL_PORT.Data1
0x18000cc75  mov     [rbp+rdx*8+160h+var_170], r14d
0x18000cc7a  add     edi, esi
0x18000cc7c  mov     [rbp+rdx*8+160h+var_168], ebx
0x18000cc80  movdqu  [rbp+rdx*8+160h+var_180], xmm0
0x18000cc86  test    r15, r15
0x18000cc89  jz      short loc_18000CCE6
0x18000cc8b  mov     ecx, r14d
0x18000cc8e  mov     eax, ecx
0x18000cc90  cmp     [r15+rax*2+8], r14w
0x18000cc96  jnz     short loc_18000CCA1
0x18000cc98  add     ecx, esi
0x18000cc9a  cmp     ecx, 8
0x18000cc9d  jl      short loc_18000CC8E
0x18000cc9f  jmp     short loc_18000CCCC
0x18000cca1  movups  xmm0, xmmword ptr cs:FWPM_CONDITION_IP_REMOTE_ADDRESS.Data1
0x18000cca8  mov     eax, edi
0x18000ccaa  add     edi, esi
0x18000ccac  lea     rcx, [rax+rax*4]
0x18000ccb0  lea     rax, [r15+8]
0x18000ccb4  mov     [rbp+rcx*8+160h+var_170], r14d
0x18000ccb9  mov     [rbp+rcx*8+160h+var_160], rax
0x18000ccbe  movdqu  [rbp+rcx*8+160h+var_180], xmm0
0x18000ccc4  mov     [rbp+rcx*8+160h+var_168], 0Bh
0x18000cccc  movzx   ecx, word ptr [r15+2]; netshort
0x18000ccd1  call    cs:__imp_ntohs
0x18000ccd7  jmp     loc_18000CBCE
0x18000ccdc  xor     r14d, r14d
0x18000ccdf  jmp     short loc_18000CCE6
0x18000cce1  mov     ebx, 2
0x18000cce6  xor     edx, edx; Val
0x18000cce8  lea     rcx, [rbp+160h+enumTemplate]; void *
0x18000ccec  lea     r8d, [rdx+48h]; Size
0x18000ccf0  call    memset_0
0x18000ccf5  cmp     bx, [r13+0]
0x18000ccfa  jnz     short loc_18000CD05
0x18000ccfc  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V4.Data1
0x18000cd03  jmp     short loc_18000CD0C
0x18000cd05  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V6.Data1
0x18000cd0c  test    edi, edi
0x18000cd0e  mov     [rbp+160h+enumTemplate.numFilterConditions], edi
0x18000cd11  lea     rax, [rbp+160h+var_180]
0x18000cd15  cmovz   rax, [rbp+160h+enumTemplate.filterCondition]
0x18000cd1a  or      edi, 0FFFFFFFFh
0x18000cd1d  xor     r9d, r9d; session
0x18000cd20  mov     [rbp+160h+enumTemplate.filterCondition], rax
0x18000cd24  lea     rax, [rsp+260h+var_228]
0x18000cd29  mov     [rbp+160h+enumTemplate.actionMask], edi
0x18000cd2c  xor     r8d, r8d; authIdentity
0x18000cd2f  mov     [rsp+260h+engineHandle], rax; engineHandle
0x18000cd34  xor     ecx, ecx; serverName
0x18000cd36  lea     edx, [r9+0Ah]; authnService
0x18000cd3a  movdqu  xmmword ptr [rbp+160h+enumTemplate.layerKey.Data1], xmm0
0x18000cd3f  call    cs:__imp_FwpmEngineOpen0
0x18000cd45  mov     ebx, eax
0x18000cd47  mov     r15d, 80070000h
0x18000cd4d  test    eax, eax
0x18000cd4f  jle     short loc_18000CD57
0x18000cd51  movzx   ebx, ax
0x18000cd54  or      ebx, r15d
0x18000cd57  test    ebx, ebx
0x18000cd59  js      loc_18000CF87
0x18000cd5f  mov     rcx, [rsp+260h+var_228]; engineHandle
0x18000cd64  lea     r8, [rsp+260h+enumHandle]; enumHandle
0x18000cd69  lea     rdx, [rbp+160h+enumTemplate]; enumTemplate
0x18000cd6d  call    cs:__imp_FwpmFilterCreateEnumHandle0
0x18000cd73  mov     ebx, eax
0x18000cd75  test    eax, eax
0x18000cd77  jle     short loc_18000CD7F
0x18000cd79  movzx   ebx, ax
0x18000cd7c  or      ebx, r15d
0x18000cd7f  test    ebx, ebx
0x18000cd81  js      loc_18000CF76
0x18000cd87  mov     rdx, [rsp+260h+enumHandle]; enumHandle
0x18000cd8c  lea     rax, [rsp+260h+numEntriesReturned]
0x18000cd91  mov     rcx, [rsp+260h+var_228]; engineHandle
0x18000cd96  lea     r9, [rsp+260h+entries]; entries
0x18000cd9b  mov     r8d, edi; numEntriesRequested
0x18000cd9e  mov     [rsp+260h+engineHandle], rax; numEntriesReturned
0x18000cda3  call    cs:__imp_FwpmFilterEnum0
0x18000cda9  mov     ebx, eax
0x18000cdab  test    eax, eax
0x18000cdad  jle     short loc_18000CDB5
0x18000cdaf  movzx   ebx, ax
0x18000cdb2  or      ebx, r15d
0x18000cdb5  test    ebx, ebx
0x18000cdb7  js      loc_18000CF8A
0x18000cdbd  mov     eax, [rsp+260h+numEntriesReturned]
0x18000cdc1  mov     edi, r14d
0x18000cdc4  mov     r12d, 2
0x18000cdca  test    eax, eax
0x18000cdcc  jz      short loc_18000CE22
0x18000cdce  mov     rax, [rsp+260h+entries]
0x18000cdd3  lea     r8, [rsp+260h+var_220]
0x18000cdd8  mov     ecx, edi
0x18000cdda  mov     rdx, [rax+rcx*8]
0x18000cdde  mov     rcx, [rsp+260h+var_228]
0x18000cde3  add     rdx, 98h
0x18000cdea  call    cs:__imp_FwpmProviderContextGetByKey3
0x18000cdf0  mov     ebx, eax
0x18000cdf2  test    eax, eax
0x18000cdf4  jle     short loc_18000CDFC
0x18000cdf6  movzx   ebx, ax
0x18000cdf9  or      ebx, r15d
0x18000cdfc  test    ebx, ebx
0x18000cdfe  js      loc_18000CF8A
0x18000ce04  mov     rdx, [rsp+260h+var_220]
0x18000ce09  mov     eax, [rdx+40h]
0x18000ce0c  sub     eax, r12d
0x18000ce0f  test    eax, 0FFFFFFFDh
0x18000ce14  mov     eax, [rsp+260h+numEntriesReturned]
0x18000ce18  jz      short loc_18000CE27
0x18000ce1a  add     edi, esi
0x18000ce1c  cmp     edi, eax
0x18000ce1e  jb      short loc_18000CDCE
0x18000ce20  jmp     short loc_18000CE27
0x18000ce22  mov     rdx, [rsp+260h+var_220]
0x18000ce27  cmp     edi, eax
0x18000ce29  jz      loc_18000CF8A
0x18000ce2f  mov     rax, [rsp+260h+var_1E8]
0x18000ce34  mov     [rax], esi
0x18000ce36  mov     rax, [rdx+48h]
0x18000ce3a  mov     ecx, [rax+10h]
0x18000ce3d  test    ecx, ecx
0x18000ce3f  jnz     short loc_18000CE76
0x18000ce41  mov     rax, [rsp+260h+var_200]
0x18000ce46  mov     [rax], r12w
0x18000ce4a  mov     rax, [rdx+48h]
0x18000ce4e  mov     ecx, [rax+14h]
0x18000ce51  mov     rax, [rsp+260h+var_1F8]
0x18000ce56  bswap   ecx
0x18000ce58  mov     [rax+4], ecx
0x18000ce5b  mov     [rax], r12w
0x18000ce5f  mov     rax, [rdx+48h]
0x18000ce63  mov     ecx, [rax+24h]
0x18000ce66  mov     rax, [rsp+260h+var_1F0]
0x18000ce6b  bswap   ecx
0x18000ce6d  mov     [rax], r12w
0x18000ce71  mov     [rax+4], ecx
0x18000ce74  jmp     short loc_18000CEB5
0x18000ce76  cmp     ecx, esi
0x18000ce78  jnz     short loc_18000CEB3
0x18000ce7a  mov     rcx, [rsp+260h+var_1F8]
0x18000ce7f  mov     edi, 17h
0x18000ce84  mov     rax, [rsp+260h+var_200]
0x18000ce89  mov     [rax], di
0x18000ce8c  mov     rax, [rdx+48h]
0x18000ce90  mov     [rcx], di
0x18000ce93  movups  xmm0, xmmword ptr [rax+14h]
0x18000ce97  movdqu  xmmword ptr [rcx+8], xmm0
0x18000ce9c  mov     rax, [rdx+48h]
0x18000cea0  mov     rcx, [rsp+260h+var_1F0]
  ... truncated ...
```
