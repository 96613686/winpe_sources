# QuicCryptoTlsEncodeTransportParameters

- ea: `0x14001a050`
- end: `0x14001b2f0`
- name: `QuicCryptoTlsEncodeTransportParameters`
- size: `4768`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000554c`
- `0x14001f464`
- `0x140046374`

## callees

- `0x14001a050`
- `0x14001b2f8`
- `0x14001b360`
- `0x14001b3c0`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003ec10`
- `0x14003ed00`
- `0x140040b80`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001a0bc`
- `ntoskrnl!_snprintf_s` at `0x14001a6cf`
- `ntoskrnl!_snprintf_s` at `0x14001a737`
- `ntoskrnl!_snprintf_s` at `0x14001a7b7`
- `ntoskrnl!_snprintf_s` at `0x14001a81f`
- `ntoskrnl!_snprintf_s` at `0x14001a888`
- `ntoskrnl!_snprintf_s` at `0x14001a8f0`
- `ntoskrnl!_snprintf_s` at `0x14001a958`
- `ntoskrnl!_snprintf_s` at `0x14001a9c0`
- `ntoskrnl!_snprintf_s` at `0x14001aa28`
- `ntoskrnl!_snprintf_s` at `0x14001aa90`
- `ntoskrnl!_snprintf_s` at `0x14001aaf8`
- `ntoskrnl!_snprintf_s` at `0x14001ab62`
- `ntoskrnl!_snprintf_s` at `0x14001abc2`
- `ntoskrnl!_snprintf_s` at `0x14001ac29`
- `ntoskrnl!_snprintf_s` at `0x14001ac93`
- `ntoskrnl!_snprintf_s` at `0x14001ad16`
- `ntoskrnl!_snprintf_s` at `0x14001ada3`
- `ntoskrnl!_snprintf_s` at `0x14001ae0d`
- `ntoskrnl!_snprintf_s` at `0x14001ae6f`
- `ntoskrnl!_snprintf_s` at `0x14001aee4`
- `ntoskrnl!_snprintf_s` at `0x14001af4e`
- `ntoskrnl!_snprintf_s` at `0x14001b054`
- `ntoskrnl!_snprintf_s` at `0x14001b0b6`
- `ntoskrnl!_snprintf_s` at `0x14001b11d`
- `ntoskrnl!_snprintf_s` at `0x14001b18e`
- `ntoskrnl!_snprintf_s` at `0x14001b200`
- `ntoskrnl!_snprintf_s` at `0x14001b2a7`
- `ntoskrnl!_snprintf_s` at `0x14001a0bc`
- `ntoskrnl!_snprintf_s` at `0x14001a6cf`
- `ntoskrnl!_snprintf_s` at `0x14001a737`
- `ntoskrnl!_snprintf_s` at `0x14001a7b7`
- `ntoskrnl!_snprintf_s` at `0x14001a81f`
- `ntoskrnl!_snprintf_s` at `0x14001a888`
- `ntoskrnl!_snprintf_s` at `0x14001a8f0`
- `ntoskrnl!_snprintf_s` at `0x14001a958`
- `ntoskrnl!_snprintf_s` at `0x14001a9c0`
- `ntoskrnl!_snprintf_s` at `0x14001aa28`
- `ntoskrnl!_snprintf_s` at `0x14001aa90`
- `ntoskrnl!_snprintf_s` at `0x14001aaf8`
- `ntoskrnl!_snprintf_s` at `0x14001ab62`
- `ntoskrnl!_snprintf_s` at `0x14001abc2`
- `ntoskrnl!_snprintf_s` at `0x14001ac29`
- `ntoskrnl!_snprintf_s` at `0x14001ac93`
- `ntoskrnl!_snprintf_s` at `0x14001ad16`
- `ntoskrnl!_snprintf_s` at `0x14001ada3`
- `ntoskrnl!_snprintf_s` at `0x14001ae0d`
- `ntoskrnl!_snprintf_s` at `0x14001ae6f`
- `ntoskrnl!_snprintf_s` at `0x14001aee4`
- `ntoskrnl!_snprintf_s` at `0x14001af4e`
- `ntoskrnl!_snprintf_s` at `0x14001b054`
- `ntoskrnl!_snprintf_s` at `0x14001b0b6`
- `ntoskrnl!_snprintf_s` at `0x14001b11d`
- `ntoskrnl!_snprintf_s` at `0x14001b18e`
- `ntoskrnl!_snprintf_s` at `0x14001b200`
- `ntoskrnl!_snprintf_s` at `0x14001b2a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b26d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b26d`
- `ntoskrnl!ExAllocatePool2` at `0x14001a62b`
- `ntoskrnl!ExAllocatePool2` at `0x14001a62b`

## string_xrefs

- `0x14001a798`: `TP: Stateless Reset Token (%s)`
- `0x14001aec6`: `TP: Version Negotiation Extension (%u bytes)`

## pseudocode

```c
char *__fastcall QuicCryptoTlsEncodeTransportParameters(
        __int64 a1,
        unsigned __int8 a2,
        int *a3,
        unsigned int *a4,
        _DWORD *a5)
{
  __int64 v8; // rcx
  int v9; // ecx
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  __int64 v17; // rdx
  unsigned __int64 v18; // r8
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // r8
  __int64 v23; // rdx
  unsigned __int64 v24; // r8
  __int64 v25; // rdx
  unsigned __int64 v26; // r8
  __int64 v27; // rdx
  unsigned __int64 v28; // r8
  __int64 v29; // rdx
  unsigned __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rdi
  int v33; // edx
  unsigned __int64 v34; // rcx
  __int64 v35; // rax
  unsigned __int64 v36; // rcx
  __int64 v37; // rax
  unsigned __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rcx
  unsigned __int64 v41; // rcx
  __int64 v42; // rax
  __int64 v43; // r15
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // r9
  __int64 v46; // rcx
  __int64 v47; // rax
  unsigned __int64 v48; // rax
  unsigned __int64 v49; // r12
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v56; // rdx
  __int64 v57; // rcx
  char *Pool2; // r13
  __int64 v59; // rdi
  __int64 v60; // r9
  const char *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // r8
  __int64 v65; // r9
  const char *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // r9
  const char *v81; // rax
  __int64 v82; // rcx
  __int64 v83; // r9
  const char *v84; // rax
  __int64 v85; // rcx
  __int64 v86; // rcx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // rcx
  unsigned __int64 v90; // rax
  __int64 v91; // r8
  unsigned __int64 v92; // rax
  __int64 v93; // rax
  __int64 v94; // r8
  __int64 v95; // rax
  __int64 v96; // r8
  __int64 v97; // rax
  __int64 v98; // r8
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  int v102; // r11d
  __int64 v103; // rcx
  __int64 v104; // rcx
  __int64 v105; // rdi
  __int64 v106; // rcx
  char v108[520]; // [rsp+38h] [rbp-C8h] BYREF
  char DstBuf[128]; // [rsp+240h] [rbp+140h] BYREF

  if ( (byte_14005C48C & 1) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Encoding Transport Parameters (Server = %hhu)", a2);
    McTemplateU0ps_EtwWriteTransfer(v8, QuicConnLogVerbose, a1, DstBuf);
  }
  v9 = *a3;
  v10 = 0;
  if ( (*a3 & 0x2000) != 0 )
  {
    if ( *((_BYTE *)a3 + 216) > 0x14u )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c",
        745,
        "TransportParams->OriginalDestinationConnectionIDLength <= 20");
      __int2c();
      v9 = *a3;
    }
    v10 = *((unsigned __int8 *)a3 + 216) + 3LL - (*((_BYTE *)a3 + 216) < 0x40u);
  }
  if ( (v9 & 0x800) != 0 )
  {
    v11 = *((_QWORD *)a3 + 1);
    if ( v11 >= 0x40 )
    {
      if ( v11 >= 0x4000 )
      {
        v12 = 10;
        if ( v11 < 0x40000000 )
          v12 = 6;
      }
      else
      {
        v12 = 4;
      }
    }
    else
    {
      v12 = 3;
    }
    v10 += v12;
  }
  v13 = v10 + 18;
  if ( (v9 & 0x100) == 0 )
    v13 = v10;
  if ( (v9 & 0x40) != 0 )
  {
    v14 = *((_QWORD *)a3 + 8);
    if ( v14 >= 0x40 )
    {
      if ( v14 >= 0x4000 )
      {
        v15 = 10;
        if ( v14 < 0x40000000 )
          v15 = 6;
      }
      else
      {
        v15 = 4;
      }
    }
    else
    {
      v15 = 3;
    }
    v13 += v15;
  }
  if ( (v9 & 1) != 0 )
  {
    v16 = *((_QWORD *)a3 + 5);
    if ( v16 >= 0x40 )
    {
      if ( v16 >= 0x4000 )
      {
        v17 = 10;
        if ( v16 < 0x40000000 )
          v17 = 6;
      }
      else
      {
        v17 = 4;
      }
    }
    else
    {
      v17 = 3;
    }
    v13 += v17;
  }
  if ( (v9 & 2) != 0 )
  {
    v18 = *((_QWORD *)a3 + 2);
    if ( v18 >= 0x40 )
    {
      if ( v18 >= 0x4000 )
      {
        v19 = 10;
        if ( v18 < 0x40000000 )
          v19 = 6;
      }
      else
      {
        v19 = 4;
      }
    }
    else
    {
      v19 = 3;
    }
    v13 += v19;
  }
  if ( (v9 & 4) != 0 )
  {
    v20 = *((_QWORD *)a3 + 3);
    if ( v20 >= 0x40 )
    {
      if ( v20 >= 0x4000 )
      {
        v21 = 10;
        if ( v20 < 0x40000000 )
          v21 = 6;
      }
      else
      {
        v21 = 4;
      }
    }
    else
    {
      v21 = 3;
    }
    v13 += v21;
  }
  if ( (v9 & 8) != 0 )
  {
    v22 = *((_QWORD *)a3 + 4);
    if ( v22 >= 0x40 )
    {
      if ( v22 >= 0x4000 )
      {
        v23 = 10;
        if ( v22 < 0x40000000 )
          v23 = 6;
      }
      else
      {
        v23 = 4;
      }
    }
    else
    {
      v23 = 3;
    }
    v13 += v23;
  }
  if ( (v9 & 0x10) != 0 )
  {
    v24 = *((_QWORD *)a3 + 6);
    if ( v24 >= 0x40 )
    {
      if ( v24 >= 0x4000 )
      {
        v25 = 10;
        if ( v24 < 0x40000000 )
          v25 = 6;
      }
      else
      {
        v25 = 4;
      }
    }
    else
    {
      v25 = 3;
    }
    v13 += v25;
  }
  if ( (v9 & 0x20) != 0 )
  {
    v26 = *((_QWORD *)a3 + 7);
    if ( v26 >= 0x40 )
    {
      if ( v26 >= 0x4000 )
      {
        v27 = 10;
        if ( v26 < 0x40000000 )
          v27 = 6;
      }
      else
      {
        v27 = 4;
      }
    }
    else
    {
      v27 = 3;
    }
    v13 += v27;
  }
  if ( (v9 & 0x80u) != 0 )
  {
    v28 = *((_QWORD *)a3 + 9);
    if ( v28 >= 0x40 )
    {
      if ( v28 >= 0x4000 )
      {
        v29 = 10;
        if ( v28 < 0x40000000 )
          v29 = 6;
      }
      else
      {
        v29 = 4;
      }
    }
    else
    {
      v29 = 3;
    }
    v13 += v29;
  }
  if ( (v9 & 0x1000) != 0 )
  {
    v30 = *((_QWORD *)a3 + 10);
    if ( v30 >= 0x40 )
    {
      if ( v30 >= 0x4000 )
      {
        v31 = 10;
        if ( v30 < 0x40000000 )
          v31 = 6;
      }
      else
      {
        v31 = 4;
      }
    }
    else
    {
      v31 = 3;
    }
    v13 += v31;
  }
  v32 = v13 + 2;
  if ( (v9 & 0x400) == 0 )
    v32 = v13;
  if ( (v9 & 0x200) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c", 826, "0");
    __int2c();
  }
  v33 = *a3;
  if ( (*a3 & 0x4000) != 0 )
  {
    v34 = *((_QWORD *)a3 + 12);
    if ( v34 >= 0x40 )
    {
      if ( v34 >= 0x4000 )
      {
        v35 = 10;
        if ( v34 < 0x40000000 )
          v35 = 6;
      }
      else
      {
        v35 = 4;
      }
    }
    else
    {
      v35 = 3;
    }
    v32 += v35;
  }
  if ( (v33 & 0x10000) != 0 )
  {
    if ( *((_BYTE *)a3 + 132) > 0x14u )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c",
        835,
        "TransportParams->InitialSourceConnectionIDLength <= 20");
      __int2c();
      v33 = *a3;
    }
    v32 += 3LL - (*((_BYTE *)a3 + 132) < 0x40u) + *((unsigned __int8 *)a3 + 132);
  }
  if ( (v33 & 0x20000) != 0 )
  {
    if ( *((_BYTE *)a3 + 237) > 0x14u )
    {
      CxPlatLogAssert(
        "C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c",
        843,
        "TransportParams->RetrySourceConnectionIDLength <= 20");
      __int2c();
      v33 = *a3;
    }
    v32 += 3LL - (*((_BYTE *)a3 + 237) < 0x40u) + *((unsigned __int8 *)a3 + 237);
  }
  if ( (v33 & 0x8000) != 0 )
  {
    v36 = *((_QWORD *)a3 + 13);
    if ( v36 >= 0x40 )
    {
      if ( v36 >= 0x4000 )
      {
        v37 = 10;
        if ( v36 < 0x40000000 )
          v37 = 6;
      }
      else
      {
        v37 = 4;
      }
    }
    else
    {
      v37 = 3;
    }
    v32 += v37;
  }
  v38 = v32 + 5;
  if ( (v33 & 0x40000) == 0 )
    v38 = v32;
  if ( (v33 & 0x80000) != 0 )
  {
    v39 = (unsigned int)a3[60];
    if ( (unsigned int)v39 >= 0x40 )
    {
      if ( (unsigned int)v39 >= 0x4000 )
      {
        v40 = 9;
        if ( (unsigned int)v39 < 0x40000000 )
          v40 = 5;
      }
      else
      {
        v40 = 3;
      }
    }
    else
    {
      v40 = 2;
    }
    v38 += v40 + v39;
  }
  if ( (v33 & 0x100000) != 0 )
  {
    v41 = *((_QWORD *)a3 + 11);
    if ( v41 >= 0x40 )
    {
      if ( v41 >= 0x4000 )
      {
        v42 = 17;
        if ( v41 < 0x40000000 )
          v42 = 13;
      }
      else
      {
        v42 = 11;
      }
    }
    else
    {
      v42 = 10;
    }
    v38 += v42;
  }
  v43 = 1;
  if ( (v33 & 0x200000) != 0 )
  {
    v44 = *((_QWORD *)a3 + 17);
    v45 = *((_QWORD *)a3 + 18);
    if ( v44 >= 0x40 )
    {
      if ( v44 >= 0x4000 )
      {
        v46 = 11;
        if ( v44 < 0x40000000 )
          v46 = 7;
      }
      else
      {
        v46 = 5;
      }
    }
    else
    {
      v46 = 4;
    }
    if ( v45 >= 0x40 )
    {
      if ( v45 >= 0x4000 )
      {
        v47 = 8;
        if ( v45 < 0x40000000 )
          v47 = 4;
      }
      else
      {
        v47 = 2;
      }
    }
    else
    {
      v47 = 1;
    }
    v38 += v46 + v47;
  }
  v48 = v38 + 3;
  if ( (v33 & 0x400000) == 0 )
    v48 = v38;
  v49 = v48 + 9;
  if ( (v33 & 0x800000) == 0 )
    v49 = v48;
  if ( (v33 & 0x3000000) != 0 )
    v49 += 6LL;
  if ( a4 )
  {
    v50 = *a4;
    v51 = 4;
    if ( *a4 >= 0x40 )
    {
      if ( v50 >= 0x4000 )
      {
        v52 = 8;
        if ( v50 < 0x40000000 )
          v52 = 4;
      }
      else
      {
        v52 = 2;
      }
    }
    else
    {
      v52 = 1;
    }
    v53 = *((unsigned __int16 *)a4 + 2);
    if ( (unsigned int)v53 >= 0x40 )
    {
      if ( (unsigned __int16)v53 < 0x4000u )
        v51 = 2;
    }
    else
    {
      v51 = 1;
    }
    v49 += v52 + v51 + v53;
  }
  if ( v49 > 0xFFFF )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c", 914, "RequiredTPLen <= 0xffffui16");
    if ( (byte_14005C48B & 4) != 0 )
    {
      McTemplateU0ps_EtwWriteTransfer(v54, QuicConnError, a1, "Encoding TP too big.");
      return 0;
    }
    return 0;
  }
  Pool2 = (char *)ExAllocatePool2(66, v49 + 10, 1177641809);
  if ( !Pool2 )
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(v57, v56, "TP buffer", v49 + 10);
    return 0;
  }
  *a5 = v49 + 10;
  v59 = (__int64)(Pool2 + 10);
  if ( (*a3 & 0x2000) != 0 )
  {
    v59 = TlsWriteTransportParam(0, *((unsigned __int8 *)a3 + 216), a3 + 49, Pool2 + 10);
    if ( (byte_14005C48C & 1) != 0 )
    {
      v61 = (const char *)QuicCidBufToStr(v108, a3 + 49, *((unsigned __int8 *)a3 + 216), v60);
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Original Destination Connection ID (%s)", v61);
      McTemplateU0ps_EtwWriteTransfer(v62, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x800) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(1, *((_QWORD *)a3 + 1), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Idle Timeout (%llu ms)", *((_QWORD *)a3 + 1));
      McTemplateU0ps_EtwWriteTransfer(v63, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x100) != 0 )
  {
    v59 = TlsWriteTransportParam(2, 16, a3 + 38, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      LOBYTE(v64) = 16;
      v66 = (const char *)QuicCidBufToStr(v108, a3 + 38, v64, v65);
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Stateless Reset Token (%s)", v66);
      McTemplateU0ps_EtwWriteTransfer(v67, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x40) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(3, *((_QWORD *)a3 + 8), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Udp Payload Size (%llu bytes)", *((_QWORD *)a3 + 8));
      McTemplateU0ps_EtwWriteTransfer(v68, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 1) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(4, *((_QWORD *)a3 + 5), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Data (%llu bytes)", *((_QWORD *)a3 + 5));
      McTemplateU0ps_EtwWriteTransfer(v69, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 2) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(5, *((_QWORD *)a3 + 2), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: Max Local Bidirectional Stream Data (%llu bytes)",
        *((_QWORD *)a3 + 2));
      McTemplateU0ps_EtwWriteTransfer(v70, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 4) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(6, *((_QWORD *)a3 + 3), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: Max Remote Bidirectional Stream Data (%llu bytes)",
        *((_QWORD *)a3 + 3));
      McTemplateU0ps_EtwWriteTransfer(v71, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 8) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(7, *((_QWORD *)a3 + 4), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: Max Unidirectional Stream Data (%llu)",
        *((_QWORD *)a3 + 4));
      McTemplateU0ps_EtwWriteTransfer(v72, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x10) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(8, *((_QWORD *)a3 + 6), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Bidirectional Streams (%llu)", *((_QWORD *)a3 + 6));
      McTemplateU0ps_EtwWriteTransfer(v73, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x20) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(9, *((_QWORD *)a3 + 7), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max Unidirectional Streams (%llu)", *((_QWORD *)a3 + 7));
      McTemplateU0ps_EtwWriteTransfer(v74, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x80u) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(10, *((_QWORD *)a3 + 9), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: ACK Delay Exponent (%llu)", *((_QWORD *)a3 + 9));
      McTemplateU0ps_EtwWriteTransfer(v75, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x1000) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(11, *((_QWORD *)a3 + 10), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Max ACK Delay (%llu ms)", *((_QWORD *)a3 + 10));
      McTemplateU0ps_EtwWriteTransfer(v76, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x400) != 0 )
  {
    v59 = TlsWriteTransportParam(12, 0, 0, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Disable Active Migration");
      McTemplateU0ps_EtwWriteTransfer(v77, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x200) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c", 1098, "0");
    __int2c();
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Preferred Address");
      McTemplateU0ps_EtwWriteTransfer(v78, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x4000) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(14, *((_QWORD *)a3 + 12), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Connection ID Limit (%llu)", *((_QWORD *)a3 + 12));
      McTemplateU0ps_EtwWriteTransfer(v79, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x10000) != 0 )
  {
    v59 = TlsWriteTransportParam(15, *((unsigned __int8 *)a3 + 132), a3 + 28, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      v81 = (const char *)QuicCidBufToStr(v108, a3 + 28, *((unsigned __int8 *)a3 + 132), v80);
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Initial Source Connection ID (%s)", v81);
      McTemplateU0ps_EtwWriteTransfer(v82, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x20000) != 0 )
  {
    v59 = TlsWriteTransportParam(16, *((unsigned __int8 *)a3 + 237), (char *)a3 + 217, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      v84 = (const char *)QuicCidBufToStr(v108, (char *)a3 + 217, *((unsigned __int8 *)a3 + 237), v83);
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Retry Source Connection ID (%s)", v84);
      McTemplateU0ps_EtwWriteTransfer(v85, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x8000) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(32, *((_QWORD *)a3 + 13), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: Max Datagram Frame Size (%llu bytes)",
        *((_QWORD *)a3 + 13));
      McTemplateU0ps_EtwWriteTransfer(v86, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x40000) != 0 )
  {
    v59 = TlsWriteTransportParam(47789, 0, 0, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Disable 1-RTT Encryption");
      McTemplateU0ps_EtwWriteTransfer(v87, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x80000) != 0 )
  {
    v59 = TlsWriteTransportParam(17, *((unsigned __int16 *)a3 + 120), *((_QWORD *)a3 + 31), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Version Negotiation Extension (%u bytes)", a3[60]);
      McTemplateU0ps_EtwWriteTransfer(v88, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x100000) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(4278509083LL, *((_QWORD *)a3 + 11), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Min ACK Delay (%llu us)", *((_QWORD *)a3 + 11));
      McTemplateU0ps_EtwWriteTransfer(v89, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x200000) != 0 )
  {
    v90 = *((_QWORD *)a3 + 17);
    if ( v90 >= 0x40 )
    {
      if ( v90 >= 0x4000 )
      {
        v91 = 8;
        if ( v90 < 0x40000000 )
          v91 = 4;
      }
      else
      {
        v91 = 2;
      }
    }
    else
    {
      v91 = 1;
    }
    v92 = *((_QWORD *)a3 + 18);
    if ( v92 >= 0x40 )
    {
      if ( v92 >= 0x4000 )
      {
        v43 = 8;
        if ( v92 < 0x40000000 )
          v43 = 4;
      }
      else
      {
        v43 = 2;
      }
    }
    v93 = QuicVarIntEncode(4096, v59, v91);
    v95 = QuicVarIntEncode(v43 + v94, v93, v94);
    v97 = QuicVarIntEncode(*((_QWORD *)a3 + 17), v95, v96);
    v59 = QuicVarIntEncode(*((_QWORD *)a3 + 18), v97, v98);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: CIBIR Encoding (%llu length, %llu offset)",
        *((_QWORD *)a3 + 17),
        *((_QWORD *)a3 + 18));
      McTemplateU0ps_EtwWriteTransfer(v99, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x400000) != 0 )
  {
    v59 = TlsWriteTransportParam(10930, 0, 0, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Grease Quic Bit");
      McTemplateU0ps_EtwWriteTransfer(v100, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x800000) != 0 )
  {
    v59 = TlsWriteTransportParam(0x17F7586D2CB570LL, 0, 0, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Reliable Reset");
      McTemplateU0ps_EtwWriteTransfer(v101, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( (*a3 & 0x3000000) != 0 )
  {
    v59 = TlsWriteTransportParamVarInt(29016, HIBYTE(*a3) & 3, v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "TP: Timestamp (%u)", v102);
      McTemplateU0ps_EtwWriteTransfer(v103, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  if ( a4 )
  {
    v59 = TlsWriteTransportParam(*a4, *((unsigned __int16 *)a4 + 2), *((_QWORD *)a4 + 1), v59);
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "TP: TEST TP (Type %hu, Length %hu)",
        *a4,
        *((unsigned __int16 *)a4 + 2));
      McTemplateU0ps_EtwWriteTransfer(v104, QuicConnLogVerbose, a1, DstBuf);
    }
  }
  v105 = v59 - (_QWORD)Pool2 - 10;
  if ( v105 == v49 )
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Encoded %hu bytes for QUIC TP", (unsigned __int16)v105);
      McTemplateU0ps_EtwWriteTransfer(v106, QuicConnLogVerbose, a1, DstBuf);
    }
    return Pool2;
  }
  else
  {
    if ( (byte_14005C48B & 4) != 0 )
      McTemplateU0ps_EtwWriteTransfer(v57, QuicConnError, a1, "Encoding error! Length mismatch.");
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\crypto_tls.c", 1271, "FinalTPLength == RequiredTPLen");
    ExFreePoolWithTag(Pool2, 0x46316351u);
    return 0;
  }
}

```

## disassembly

```asm
0x14001a050  push    rbp
0x14001a052  push    rbx
0x14001a053  push    rsi
0x14001a054  push    rdi
0x14001a055  push    r12
0x14001a057  push    r13
0x14001a059  push    r14
0x14001a05b  push    r15
0x14001a05d  lea     rbp, [rsp-1D8h]
0x14001a065  sub     rsp, 2D8h
0x14001a06c  mov     rax, cs:__security_cookie
0x14001a073  xor     rax, rsp
0x14001a076  mov     [rbp+210h+var_50], rax
0x14001a07d  test    cs:byte_14005C48C, 1
0x14001a084  mov     r13, r9
0x14001a087  mov     rsi, [rbp+210h+arg_20]
0x14001a08e  mov     rbx, r8
0x14001a091  mov     [rsp+310h+var_2E0], r9
0x14001a096  mov     r14, rcx
0x14001a099  jz      short loc_14001A0DE
0x14001a09b  movzx   eax, dl
0x14001a09e  lea     r9, aEncodingTransp; "Encoding Transport Parameters (Server ="...
0x14001a0a5  mov     edx, 80h; SizeInBytes
0x14001a0aa  mov     dword ptr [rsp+310h+var_2F0], eax
0x14001a0ae  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001a0b5  lea     rcx, [rbp+210h+DstBuf]; DstBuf
0x14001a0bc  call    cs:__imp__snprintf_s
0x14001a0c3  nop     dword ptr [rax+rax+00h]
0x14001a0c8  lea     r9, [rbp+210h+DstBuf]
0x14001a0cf  mov     r8, r14
0x14001a0d2  lea     rdx, QuicConnLogVerbose
0x14001a0d9  call    McTemplateU0ps_EtwWriteTransfer
0x14001a0de  mov     ecx, [rbx]
0x14001a0e0  xor     edx, edx
0x14001a0e2  bt      ecx, 0Dh
0x14001a0e6  jnb     short loc_14001A120
0x14001a0e8  cmp     byte ptr [rbx+0D8h], 14h
0x14001a0ef  jbe     short loc_14001A10D
0x14001a0f1  lea     r8, aTransportparam_0; "TransportParams->OriginalDestinationCon"...
0x14001a0f8  mov     edx, 2E9h
0x14001a0fd  lea     rcx, aCW1SMsquicSrcC_16; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001a104  call    CxPlatLogAssert
0x14001a109  int     2Ch; Windows NT - assertion failure
0x14001a10b  mov     ecx, [rbx]
0x14001a10d  movzx   eax, byte ptr [rbx+0D8h]
0x14001a114  cmp     al, 40h ; '@'
0x14001a116  sbb     rdx, rdx
0x14001a119  add     rdx, 3
0x14001a11d  add     rdx, rax
0x14001a120  mov     r9d, 4
0x14001a126  mov     r12d, 4000h
0x14001a12c  lea     r15d, [r9+2]
0x14001a130  bt      ecx, 0Bh
0x14001a134  jnb     short loc_14001A163
0x14001a136  mov     r8, [rbx+8]
0x14001a13a  cmp     r8, 40h ; '@'
0x14001a13e  jnb     short loc_14001A146
0x14001a140  lea     eax, [r9-1]
0x14001a144  jmp     short loc_14001A160
0x14001a146  cmp     r8, r12
0x14001a149  jnb     short loc_14001A150
0x14001a14b  mov     rax, r9
0x14001a14e  jmp     short loc_14001A160
0x14001a150  cmp     r8, 40000000h
0x14001a157  mov     eax, 0Ah
0x14001a15c  cmovb   rax, r15
0x14001a160  add     rdx, rax
0x14001a163  bt      ecx, 8
0x14001a167  lea     rax, [rdx+12h]
0x14001a16b  cmovnb  rax, rdx
0x14001a16f  test    cl, 40h
0x14001a172  jz      short loc_14001A1A2
0x14001a174  mov     r8, [rbx+40h]
0x14001a178  cmp     r8, 40h ; '@'
0x14001a17c  jnb     short loc_14001A185
0x14001a17e  mov     edx, 3
0x14001a183  jmp     short loc_14001A19F
0x14001a185  cmp     r8, r12
0x14001a188  jnb     short loc_14001A18F
0x14001a18a  mov     rdx, r9
0x14001a18d  jmp     short loc_14001A19F
0x14001a18f  cmp     r8, 40000000h
0x14001a196  mov     edx, 0Ah
0x14001a19b  cmovb   rdx, r15
0x14001a19f  add     rax, rdx
0x14001a1a2  test    cl, 1
0x14001a1a5  jz      short loc_14001A1D5
0x14001a1a7  mov     r8, [rbx+28h]
0x14001a1ab  cmp     r8, 40h ; '@'
0x14001a1af  jnb     short loc_14001A1B8
0x14001a1b1  mov     edx, 3
0x14001a1b6  jmp     short loc_14001A1D2
0x14001a1b8  cmp     r8, r12
0x14001a1bb  jnb     short loc_14001A1C2
0x14001a1bd  mov     rdx, r9
0x14001a1c0  jmp     short loc_14001A1D2
0x14001a1c2  cmp     r8, 40000000h
0x14001a1c9  mov     edx, 0Ah
0x14001a1ce  cmovb   rdx, r15
0x14001a1d2  add     rax, rdx
0x14001a1d5  test    cl, 2
0x14001a1d8  jz      short loc_14001A208
0x14001a1da  mov     r8, [rbx+10h]
0x14001a1de  cmp     r8, 40h ; '@'
0x14001a1e2  jnb     short loc_14001A1EB
0x14001a1e4  mov     edx, 3
0x14001a1e9  jmp     short loc_14001A205
0x14001a1eb  cmp     r8, r12
0x14001a1ee  jnb     short loc_14001A1F5
0x14001a1f0  mov     rdx, r9
0x14001a1f3  jmp     short loc_14001A205
0x14001a1f5  cmp     r8, 40000000h
0x14001a1fc  mov     edx, 0Ah
0x14001a201  cmovb   rdx, r15
0x14001a205  add     rax, rdx
0x14001a208  test    r9b, cl
0x14001a20b  jz      short loc_14001A23B
0x14001a20d  mov     r8, [rbx+18h]
0x14001a211  cmp     r8, 40h ; '@'
0x14001a215  jnb     short loc_14001A21E
0x14001a217  mov     edx, 3
0x14001a21c  jmp     short loc_14001A238
0x14001a21e  cmp     r8, r12
0x14001a221  jnb     short loc_14001A228
0x14001a223  mov     rdx, r9
0x14001a226  jmp     short loc_14001A238
0x14001a228  cmp     r8, 40000000h
0x14001a22f  mov     edx, 0Ah
0x14001a234  cmovb   rdx, r15
0x14001a238  add     rax, rdx
0x14001a23b  test    cl, 8
0x14001a23e  jz      short loc_14001A26E
0x14001a240  mov     r8, [rbx+20h]
0x14001a244  cmp     r8, 40h ; '@'
0x14001a248  jnb     short loc_14001A251
0x14001a24a  mov     edx, 3
0x14001a24f  jmp     short loc_14001A26B
0x14001a251  cmp     r8, r12
0x14001a254  jnb     short loc_14001A25B
0x14001a256  mov     rdx, r9
0x14001a259  jmp     short loc_14001A26B
0x14001a25b  cmp     r8, 40000000h
0x14001a262  mov     edx, 0Ah
0x14001a267  cmovb   rdx, r15
0x14001a26b  add     rax, rdx
0x14001a26e  test    cl, 10h
0x14001a271  jz      short loc_14001A2A1
0x14001a273  mov     r8, [rbx+30h]
0x14001a277  cmp     r8, 40h ; '@'
0x14001a27b  jnb     short loc_14001A284
0x14001a27d  mov     edx, 3
0x14001a282  jmp     short loc_14001A29E
0x14001a284  cmp     r8, r12
0x14001a287  jnb     short loc_14001A28E
0x14001a289  mov     rdx, r9
0x14001a28c  jmp     short loc_14001A29E
0x14001a28e  cmp     r8, 40000000h
0x14001a295  mov     edx, 0Ah
0x14001a29a  cmovb   rdx, r15
0x14001a29e  add     rax, rdx
0x14001a2a1  test    cl, 20h
0x14001a2a4  jz      short loc_14001A2D4
0x14001a2a6  mov     r8, [rbx+38h]
0x14001a2aa  cmp     r8, 40h ; '@'
0x14001a2ae  jnb     short loc_14001A2B7
0x14001a2b0  mov     edx, 3
0x14001a2b5  jmp     short loc_14001A2D1
0x14001a2b7  cmp     r8, r12
0x14001a2ba  jnb     short loc_14001A2C1
0x14001a2bc  mov     rdx, r9
0x14001a2bf  jmp     short loc_14001A2D1
0x14001a2c1  cmp     r8, 40000000h
0x14001a2c8  mov     edx, 0Ah
0x14001a2cd  cmovb   rdx, r15
0x14001a2d1  add     rax, rdx
0x14001a2d4  test    cl, cl
0x14001a2d6  jns     short loc_14001A306
0x14001a2d8  mov     r8, [rbx+48h]
0x14001a2dc  cmp     r8, 40h ; '@'
0x14001a2e0  jnb     short loc_14001A2E9
0x14001a2e2  mov     edx, 3
0x14001a2e7  jmp     short loc_14001A303
0x14001a2e9  cmp     r8, r12
0x14001a2ec  jnb     short loc_14001A2F3
0x14001a2ee  mov     rdx, r9
0x14001a2f1  jmp     short loc_14001A303
0x14001a2f3  cmp     r8, 40000000h
0x14001a2fa  mov     edx, 0Ah
0x14001a2ff  cmovb   rdx, r15
0x14001a303  add     rax, rdx
0x14001a306  bt      ecx, 0Ch
0x14001a30a  jnb     short loc_14001A33A
0x14001a30c  mov     r8, [rbx+50h]
0x14001a310  cmp     r8, 40h ; '@'
0x14001a314  jnb     short loc_14001A31D
0x14001a316  mov     edx, 3
0x14001a31b  jmp     short loc_14001A337
0x14001a31d  cmp     r8, r12
0x14001a320  jnb     short loc_14001A327
0x14001a322  mov     rdx, r9
0x14001a325  jmp     short loc_14001A337
0x14001a327  cmp     r8, 40000000h
0x14001a32e  mov     edx, 0Ah
0x14001a333  cmovb   rdx, r15
0x14001a337  add     rax, rdx
0x14001a33a  bt      ecx, 0Ah
0x14001a33e  lea     rdi, [rax+2]
0x14001a342  cmovnb  rdi, rax
0x14001a346  bt      ecx, 9
0x14001a34a  jnb     short loc_14001A36C
0x14001a34c  lea     r8, a0; "0"
0x14001a353  mov     edx, 33Ah
0x14001a358  lea     rcx, aCW1SMsquicSrcC_16; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001a35f  call    CxPlatLogAssert
0x14001a364  int     2Ch; Windows NT - assertion failure
0x14001a366  mov     r9d, 4
0x14001a36c  mov     edx, [rbx]
0x14001a36e  test    r12d, edx
0x14001a371  jz      short loc_14001A3A1
0x14001a373  mov     rcx, [rbx+60h]
0x14001a377  cmp     rcx, 40h ; '@'
0x14001a37b  jnb     short loc_14001A384
0x14001a37d  mov     eax, 3
0x14001a382  jmp     short loc_14001A39E
0x14001a384  cmp     rcx, r12
0x14001a387  jnb     short loc_14001A38E
0x14001a389  mov     rax, r9
0x14001a38c  jmp     short loc_14001A39E
0x14001a38e  cmp     rcx, 40000000h
0x14001a395  mov     eax, 0Ah
0x14001a39a  cmovb   rax, r15
0x14001a39e  add     rdi, rax
0x14001a3a1  bt      edx, 10h
0x14001a3a5  jnb     short loc_14001A3E3
0x14001a3a7  cmp     byte ptr [rbx+84h], 14h
0x14001a3ae  jbe     short loc_14001A3CC
0x14001a3b0  lea     r8, aTransportparam_1; "TransportParams->InitialSourceConnectio"...
0x14001a3b7  mov     edx, 343h
0x14001a3bc  lea     rcx, aCW1SMsquicSrcC_16; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001a3c3  call    CxPlatLogAssert
0x14001a3c8  int     2Ch; Windows NT - assertion failure
0x14001a3ca  mov     edx, [rbx]
0x14001a3cc  movzx   ecx, byte ptr [rbx+84h]
0x14001a3d3  cmp     cl, 40h ; '@'
0x14001a3d6  sbb     rax, rax
0x14001a3d9  add     rdi, rcx
0x14001a3dc  add     rax, 3
0x14001a3e0  add     rdi, rax
0x14001a3e3  bt      edx, 11h
0x14001a3e7  jnb     short loc_14001A425
0x14001a3e9  cmp     byte ptr [rbx+0EDh], 14h
0x14001a3f0  jbe     short loc_14001A40E
0x14001a3f2  lea     r8, aTransportparam; "TransportParams->RetrySourceConnectionI"...
0x14001a3f9  mov     edx, 34Bh
0x14001a3fe  lea     rcx, aCW1SMsquicSrcC_16; "C:\\__w\\1\\s\\msquic\\src\\core\\crypt"...
0x14001a405  call    CxPlatLogAssert
0x14001a40a  int     2Ch; Windows NT - assertion failure
0x14001a40c  mov     edx, [rbx]
0x14001a40e  movzx   ecx, byte ptr [rbx+0EDh]
0x14001a415  cmp     cl, 40h ; '@'
0x14001a418  sbb     rax, rax
0x14001a41b  add     rdi, rcx
0x14001a41e  add     rax, 3
0x14001a422  add     rdi, rax
0x14001a425  bt      edx, 0Fh
0x14001a429  jnb     short loc_14001A45B
0x14001a42b  mov     rcx, [rbx+68h]
0x14001a42f  cmp     rcx, 40h ; '@'
0x14001a433  jnb     short loc_14001A43C
0x14001a435  mov     eax, 3
0x14001a43a  jmp     short loc_14001A458
0x14001a43c  cmp     rcx, r12
0x14001a43f  jnb     short loc_14001A448
0x14001a441  mov     eax, 4
0x14001a446  jmp     short loc_14001A458
0x14001a448  cmp     rcx, 40000000h
0x14001a44f  mov     eax, 0Ah
0x14001a454  cmovb   rax, r15
0x14001a458  add     rdi, rax
0x14001a45b  bt      edx, 12h
0x14001a45f  lea     r8, [rdi+5]
0x14001a463  cmovnb  r8, rdi
0x14001a467  mov     edi, 2
0x14001a46c  lea     r10d, [rdi+3]
0x14001a470  bt      edx, 13h
0x14001a474  jnb     short loc_14001A4A5
0x14001a476  mov     eax, [rbx+0F0h]
0x14001a47c  cmp     eax, 40h ; '@'
0x14001a47f  jnb     short loc_14001A485
0x14001a481  mov     ecx, edi
0x14001a483  jmp     short loc_14001A49F
0x14001a485  cmp     eax, r12d
0x14001a488  jnb     short loc_14001A491
0x14001a48a  mov     ecx, 3
0x14001a48f  jmp     short loc_14001A49F
0x14001a491  cmp     eax, 40000000h
0x14001a496  mov     ecx, 9
0x14001a49b  cmovb   rcx, r10
0x14001a49f  add     rax, rcx
0x14001a4a2  add     r8, rax
  ... truncated ...
```
