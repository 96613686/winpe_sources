# CVolume::_ScanExtents(void *,RETRIEVAL_POINTERS_BUFFER *,ulong,ulong *,unsigned __int64 *)

- ea: `0x180034a60`
- end: `0x180035207`
- name: `?_ScanExtents@CVolume@@IEAAJPEAXPEAURETRIEVAL_POINTERS_BUFFER@@KPEAKPEA_K@Z`
- size: `1959`
- prototype: `__int64 __fastcall(CVolume *this, char *, struct RETRIEVAL_POINTERS_BUFFER *, DWORD, unsigned int *, unsigned __int64 *)`
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003d84`
- `0x180014acc`
- `0x18002dad0`
- `0x18003ec00`
- `0x180041680`
- `0x1800431e0`
- `0x180063370`

## callees

- `0x180006400`
- `0x180006bf8`
- `0x180008530`
- `0x18000ad50`
- `0x180010d80`
- `0x18001fd00`
- `0x180034a60`
- `0x180067b0a`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180034c2a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180034c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034b6f`

## pseudocode

```c
__int64 __fastcall CVolume::_ScanExtents(
        CVolume *this,
        char *a2,
        struct RETRIEVAL_POINTERS_BUFFER *a3,
        DWORD a4,
        unsigned int *a5,
        unsigned __int64 *a6)
{
  CVolume *v8; // r15
  unsigned int v9; // r14d
  unsigned int v10; // edi
  __int16 v11; // ax
  __int64 v12; // r9
  struct RETRIEVAL_POINTERS_BUFFER *v13; // rsi
  LARGE_INTEGER NextVcn; // rbx
  __int64 v15; // r8
  __int64 v16; // r13
  __int64 v17; // r12
  BOOL v18; // ebx
  DWORD LastError; // eax
  DWORD v20; // eax
  _QWORD *v21; // r11
  _QWORD *v22; // r15
  __int64 v23; // r13
  __int16 v24; // ax
  _QWORD *v25; // rax
  __int64 v26; // rdx
  bool v27; // zf
  __int64 v28; // rdx
  __int64 v29; // rcx
  _BYTE *v30; // rax
  LARGE_INTEGER Lcn; // rax
  LONGLONG v32; // rcx
  LARGE_INTEGER v33; // r8
  __int16 v34; // ax
  LARGE_INTEGER *v35; // rbx
  __int64 v36; // rcx
  LARGE_INTEGER *v37; // rax
  LARGE_INTEGER v38; // rcx
  LARGE_INTEGER v39; // rdx
  DWORD v40; // eax
  __int16 v41; // ax
  __int16 v42; // ax
  LARGE_INTEGER *v43; // rbx
  LARGE_INTEGER *v44; // rax
  __int64 v45; // rcx
  LARGE_INTEGER v46; // rdx
  DWORD v47; // eax
  unsigned int v48; // ebx
  LPVOID lpOutBuffer; // [rsp+28h] [rbp-E0h]
  DWORD nOutBufferSize[2]; // [rsp+30h] [rbp-D8h]
  unsigned int v52; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v53; // [rsp+4Ch] [rbp-BCh] BYREF
  unsigned int v54; // [rsp+50h] [rbp-B8h]
  DWORD v55; // [rsp+54h] [rbp-B4h]
  int Element; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v57; // [rsp+5Ch] [rbp-ACh]
  __int16 v58; // [rsp+5Eh] [rbp-AAh]
  unsigned int v59; // [rsp+90h] [rbp-78h]
  unsigned int v60; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v61; // [rsp+98h] [rbp-70h] BYREF
  DWORD v62; // [rsp+9Ch] [rbp-6Ch]
  DWORD v63; // [rsp+A0h] [rbp-68h]
  LARGE_INTEGER v64; // [rsp+A8h] [rbp-60h]
  LARGE_INTEGER *v65; // [rsp+B0h] [rbp-58h] BYREF
  LARGE_INTEGER v66; // [rsp+B8h] [rbp-50h]
  LARGE_INTEGER StartingVcn; // [rsp+C0h] [rbp-48h]
  DWORD BytesReturned; // [rsp+C8h] [rbp-40h] BYREF
  LARGE_INTEGER InBuffer; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD *v70; // [rsp+D8h] [rbp-30h]
  __int64 v71; // [rsp+E0h] [rbp-28h]
  LARGE_INTEGER *v72; // [rsp+E8h] [rbp-20h]
  unsigned __int64 v73; // [rsp+F0h] [rbp-18h]
  __int64 v74; // [rsp+F8h] [rbp-10h]

  v8 = this;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&Element, "CVolume::_ScanExtents", 300, 1);
  v9 = 0;
  v61 = 0;
  InBuffer.QuadPart = 0;
  BytesReturned = 0;
  v53 = 0;
  v55 = 0;
  v60 = 0;
  v65 = 0;
  v10 = 0;
  v52 = 0;
  v11 = 325;
  if ( !a5
    || (v57 = 325, v11 = 326, !a6)
    || (v57 = 326, v11 = 331, (a3 != 0) == (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL) )
  {
    Element = -2147024809;
    goto LABEL_104;
  }
  Element = 0;
  v57 = 331;
  Element = CVolume::_FreeExtents(v8, a5);
  v11 = 334;
  if ( Element < 0 )
  {
LABEL_104:
    v58 = v11;
    goto LABEL_105;
  }
  v57 = 334;
  *a5 = 0;
  *a6 = 0;
  if ( a3 )
  {
    v13 = a3;
  }
  else
  {
    v13 = (struct RETRIEVAL_POINTERS_BUFFER *)*((_QWORD *)v8 + 20);
    if ( !v13 )
    {
      v13 = (struct RETRIEVAL_POINTERS_BUFFER *)CoTaskMemAlloc(0x10000u);
      *((_QWORD *)v8 + 20) = v13;
      if ( !v13 )
      {
        Element = -2147024882;
        v58 = 348;
        goto LABEL_105;
      }
      Element = 0;
      v57 = 348;
    }
  }
  v72 = 0;
  v66.QuadPart = 0;
  NextVcn.QuadPart = 0;
  v64.QuadPart = 0;
  StartingVcn.QuadPart = 0;
  v15 = 0;
  v59 = 0;
  v63 = 0;
  v16 = 0;
  v71 = 0;
  v17 = 0;
  v54 = 0;
  v73 = 0;
LABEL_12:
  if ( a3 )
    goto LABEL_19;
  memset_0(v13, 0, 0x10000u);
  InBuffer = NextVcn;
  v18 = DeviceIoControl(a2, 0x90073u, &InBuffer, 8u, v13, 0x10000u, &BytesReturned, 0);
  LastError = GetLastError();
  v63 = LastError;
  if ( !v18 )
  {
    if ( LastError == 234 )
    {
LABEL_17:
      if ( v13->ExtentCount )
        goto LABEL_18;
      Element = 0;
      v41 = 390;
LABEL_66:
      v57 = v41;
      goto LABEL_101;
    }
    if ( LastError != 38 )
    {
      Element = 150995200;
      v41 = 384;
      goto LABEL_66;
    }
  }
  if ( LastError != 38 )
    goto LABEL_17;
LABEL_18:
  NextVcn = v64;
  v15 = v59;
LABEL_19:
  v20 = 0;
  v21 = (_QWORD *)((char *)v8 + 152);
  while ( 1 )
  {
    v62 = v20;
    v22 = v21;
    if ( v20 >= v13->ExtentCount )
    {
      if ( v63 == 234 )
      {
        v8 = this;
        goto LABEL_12;
      }
      if ( !(_DWORD)v15 )
        goto LABEL_95;
      Element = CBulkAllocator<_CExtent>::Alloc(*v21, &v52);
      v10 = v52;
      v34 = 613;
      if ( Element >= 0 )
      {
        v57 = 613;
        v42 = 614;
        if ( !v52 )
          goto LABEL_76;
        Element = 0;
        v57 = 614;
        Element = CBulkAllocator<CNtfsFile>::GetElement(*v22, &v52, &v65);
        v34 = 616;
        if ( Element >= 0 )
        {
          v57 = 616;
          v43 = v65;
          v34 = 617;
          if ( v65 )
          {
            Element = 0;
            v57 = 617;
            v44 = v65;
            v45 = 40;
            do
            {
              LOBYTE(v44->LowPart) = 0;
              v44 = (LARGE_INTEGER *)((char *)v44 + 1);
              --v45;
            }
            while ( v45 );
            *v43 = v66;
            v46 = StartingVcn;
            v43[1].QuadPart = v64.QuadPart - StartingVcn.QuadPart;
            v43[3] = v46;
            v43[2].HighPart = a4;
            v43[4].LowPart = a4;
            if ( v54 > 1 )
            {
              v47 = v55;
              if ( v16 )
                *(_DWORD *)(v16 + 20) = 0;
              goto LABEL_90;
            }
            Element = CBulkAllocator<_CExtent>::Free(*v22, &v60, v15, v12, lpOutBuffer, *(_QWORD *)nOutBufferSize);
            v34 = 631;
            if ( Element >= 0 )
            {
              v57 = 631;
              v47 = 0;
LABEL_90:
              v43[2].LowPart = v47;
              if ( v72 )
                v72[2].HighPart = v10;
              if ( !v9 )
                v9 = v10;
              v10 = 0;
              v52 = 0;
LABEL_95:
              *a5 = v9;
              v9 = 0;
              v61 = 0;
              *a6 = v73;
LABEL_96:
              if ( v10 )
                CBulkAllocator<_CExtent>::Free(*v22, &v52, v15, v12, lpOutBuffer, *(_QWORD *)nOutBufferSize);
              goto LABEL_98;
            }
          }
          else
          {
LABEL_68:
            Element = -2147024882;
          }
        }
      }
LABEL_69:
      v58 = v34;
      goto LABEL_96;
    }
    v23 = v20;
    if ( v13->Extents[v20].NextVcn.QuadPart <= (unsigned __int64)NextVcn.QuadPart )
    {
      Element = 150995200;
      v57 = 401;
      goto LABEL_100;
    }
    v70 = (_QWORD *)((char *)this + 152);
    Element = CBulkAllocator<_CExtent>::Alloc(*((_QWORD *)this + 19), &v53);
    v24 = 407;
    if ( Element < 0 )
      goto LABEL_71;
    v57 = 407;
    if ( !v53 )
    {
      v42 = 408;
LABEL_76:
      Element = -2147024882;
      v58 = v42;
      goto LABEL_100;
    }
    Element = 0;
    v57 = 408;
    v21 = v70;
    v15 = *v70;
    if ( !*(_DWORD *)(*v70 + 28LL) )
      break;
    if ( (v53 & 0xF0000000) != *(_DWORD *)(v15 + 28)
      || (v12 = ((unsigned __int16)v53 - 1) & (unsigned int)-((unsigned __int16)v53 != 0),
          (v25 = *(_QWORD **)(*(_QWORD *)(v15 + 8) + 8 * (((unsigned __int64)v53 >> 16) & 0xFFF))) == 0)
      || (unsigned int)v12 >= *(_DWORD *)(v15 + 20) )
    {
      Element = -2147024809;
      goto LABEL_74;
    }
    v26 = *(_QWORD *)(v15 + 32) * (unsigned int)v12;
    v27 = *v25 + v26 == 0;
    v28 = *v25 + v26;
    v74 = v28;
    v57 = 410;
    v24 = 411;
    if ( v27 )
      goto LABEL_70;
    Element = 0;
    v57 = 411;
    v29 = 40;
    v30 = (_BYTE *)v28;
    do
    {
      *v30++ = 0;
      --v29;
    }
    while ( v29 );
    Lcn = v13->Extents[v23].Lcn;
    *(LARGE_INTEGER *)v28 = Lcn;
    v32 = v13->Extents[v23].NextVcn.QuadPart - NextVcn.QuadPart;
    *(_QWORD *)(v28 + 8) = v32;
    *(LARGE_INTEGER *)(v28 + 24) = NextVcn;
    *(_QWORD *)(v28 + 16) = 0;
    *(_DWORD *)(v28 + 32) = a4;
    if ( Lcn.QuadPart != -1 )
      v73 += v32;
    if ( v59 )
    {
      if ( v13->Extents[v23].Lcn.QuadPart == -1 || v13->Extents[v23].Lcn.QuadPart == v17 )
      {
        if ( v71 )
          *(_DWORD *)(v71 + 20) = v53;
        if ( v13->Extents[v23].Lcn.QuadPart != -1 )
          v17 = *(_QWORD *)v28 + *(_QWORD *)(v28 + 8);
        if ( v17 != -1 )
          ++v54;
      }
      else
      {
        Element = CBulkAllocator<_CExtent>::Alloc(*v21, &v52);
        v10 = v52;
        v34 = 521;
        if ( Element < 0 )
          goto LABEL_69;
        v57 = 521;
        v24 = 522;
        if ( !v52 )
        {
LABEL_70:
          Element = -2147024882;
          goto LABEL_71;
        }
        Element = 0;
        v57 = 522;
        Element = CBulkAllocator<CNtfsFile>::GetElement(*v70, &v52, &v65);
        v34 = 524;
        if ( Element < 0 )
          goto LABEL_69;
        v57 = 524;
        v35 = v65;
        v34 = 525;
        if ( !v65 )
          goto LABEL_68;
        Element = 0;
        v57 = 525;
        v36 = 40;
        v37 = v65;
        do
        {
          LOBYTE(v37->LowPart) = 0;
          v37 = (LARGE_INTEGER *)((char *)v37 + 1);
          --v36;
        }
        while ( v36 );
        *v35 = v66;
        v38 = v64;
        v39 = StartingVcn;
        v35[1].QuadPart = v64.QuadPart - StartingVcn.QuadPart;
        v35[3] = v39;
        v35[2].HighPart = a4;
        v35[4].LowPart = a4;
        if ( v54 > 1 )
        {
          v40 = v55;
          if ( v71 )
            *(_DWORD *)(v71 + 20) = 0;
        }
        else
        {
          Element = CBulkAllocator<_CExtent>::Free(*v21, &v60, v15, v12, lpOutBuffer, *(_QWORD *)nOutBufferSize);
          v34 = 546;
          if ( Element < 0 )
            goto LABEL_69;
          v57 = 546;
          v40 = 0;
          v38 = v64;
          v21 = v70;
        }
        v35[2].LowPart = v40;
        if ( v72 )
          v72[2].HighPart = v10;
        if ( !v9 )
          v9 = v10;
        v61 = v9;
        v72 = v35;
        StartingVcn = v38;
        v66 = v13->Extents[v23].Lcn;
        v17 = v66.QuadPart + v13->Extents[v23].NextVcn.QuadPart - v38.QuadPart;
        v55 = v53;
        v60 = v53;
        v54 = 1;
        v10 = 0;
        v52 = 0;
        v28 = v74;
      }
    }
    else
    {
      StartingVcn = v13->StartingVcn;
      v33 = v13->Extents[v23].Lcn;
      v66 = v33;
      if ( v33.QuadPart == -1 )
        v17 = -1;
      else
        v17 = v33.QuadPart + v13->Extents[v23].NextVcn.QuadPart;
      v55 = v53;
      v60 = v53;
      v54 = 1;
    }
    v53 = 0;
    NextVcn = v13->Extents[v23].NextVcn;
    v64 = NextVcn;
    v15 = ++v59;
    v20 = v62 + 1;
    v16 = v28;
    v71 = v28;
  }
  Element = -2147467259;
LABEL_74:
  v24 = 410;
LABEL_71:
  v58 = v24;
LABEL_98:
  if ( v53 )
    CBulkAllocator<_CExtent>::Free(*v22, &v53, v15, v12, lpOutBuffer, *(_QWORD *)nOutBufferSize);
LABEL_100:
  v8 = this;
LABEL_101:
  if ( v9 )
    CVolume::_FreeExtents(v8, &v61);
LABEL_105:
  v48 = Element;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&Element);
  return v48;
}

```

## disassembly

```asm
0x180034a60  mov     rax, rsp
0x180034a63  mov     [rax+20h], r9d
0x180034a67  mov     [rax+18h], r8
0x180034a6b  mov     [rax+10h], rdx
0x180034a6f  mov     [rax+8], rcx
0x180034a73  push    rbp
0x180034a74  push    rbx
0x180034a75  push    rsi
0x180034a76  push    rdi
0x180034a77  push    r12
0x180034a79  push    r13
0x180034a7b  push    r14
0x180034a7d  push    r15
0x180034a7f  lea     rbp, [rax-48h]
0x180034a83  sub     rsp, 108h
0x180034a8a  mov     rbx, r8
0x180034a8d  mov     r13, rdx
0x180034a90  mov     r15, rcx
0x180034a93  mov     r9d, 1; unsigned __int16
0x180034a99  mov     r8d, 12Ch; unsigned __int16
0x180034a9f  lea     rdx, aCvolumeScanext; "CVolume::_ScanExtents"
0x180034aa6  lea     rcx, [rsp+140h+var_F0]; this
0x180034aab  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180034ab0  nop
0x180034ab1  xor     edx, edx
0x180034ab3  mov     r14d, edx
0x180034ab6  mov     [rbp+40h+var_B0], edx
0x180034ab9  mov     [rbp+40h+InBuffer], rdx
0x180034abd  mov     [rbp+40h+BytesReturned], edx
0x180034ac0  mov     [rsp+140h+var_FC], edx
0x180034ac4  mov     dword ptr [rsp+140h+var_F4], edx
0x180034ac8  mov     [rbp+40h+var_B4], edx
0x180034acb  mov     [rbp+40h+var_98], rdx
0x180034acf  mov     edi, edx
0x180034ad1  mov     [rsp+140h+var_100], edx
0x180034ad5  mov     rsi, [rbp+40h+arg_20]
0x180034ad9  mov     eax, 145h
0x180034ade  test    rsi, rsi
0x180034ae1  jz      loc_1800351D6
0x180034ae7  mov     [rsp+140h+var_EC], ax
0x180034aec  mov     r12, [rbp+40h+arg_28]
0x180034af0  mov     eax, 146h
0x180034af5  test    r12, r12
0x180034af8  jz      loc_1800351D6
0x180034afe  mov     [rsp+140h+var_EC], ax
0x180034b03  lea     rax, [r13-1]
0x180034b07  mov     ecx, edx
0x180034b09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034b0d  setbe   cl
0x180034b10  mov     eax, edx
0x180034b12  test    rbx, rbx
0x180034b15  setnz   al
0x180034b18  cmp     eax, ecx
0x180034b1a  mov     eax, 14Bh
0x180034b1f  jz      loc_1800351D6
0x180034b25  mov     [rsp+140h+var_F0], edx
0x180034b29  mov     [rsp+140h+var_EC], ax
0x180034b2e  mov     rdx, rsi; unsigned int *
0x180034b31  mov     rcx, r15; this
0x180034b34  call    ?_FreeExtents@CVolume@@IEAAJPEAK@Z; CVolume::_FreeExtents(ulong *)
0x180034b39  mov     [rsp+140h+var_F0], eax
0x180034b3d  xor     r10d, r10d
0x180034b40  test    eax, eax
0x180034b42  mov     eax, 14Eh
0x180034b47  js      loc_1800351DE
0x180034b4d  mov     [rsp+140h+var_EC], ax
0x180034b52  mov     [rsi], r10d
0x180034b55  mov     [r12], r10
0x180034b59  test    rbx, rbx
0x180034b5c  jnz     short loc_180034BAA
0x180034b5e  mov     rsi, [r15+0A0h]
0x180034b65  test    rsi, rsi
0x180034b68  jnz     short loc_180034BAD
0x180034b6a  mov     ecx, 10000h; cb
0x180034b6f  call    cs:__imp_CoTaskMemAlloc
0x180034b75  mov     rsi, rax
0x180034b78  mov     [r15+0A0h], rax
0x180034b7f  xor     r10d, r10d
0x180034b82  mov     ecx, 15Ch
0x180034b87  test    rax, rax
0x180034b8a  jz      short loc_180034B98
0x180034b8c  mov     [rsp+140h+var_F0], r10d
0x180034b91  mov     [rsp+140h+var_EC], cx
0x180034b96  jmp     short loc_180034BAD
0x180034b98  mov     [rsp+140h+var_F0], 8007000Eh
0x180034ba0  mov     [rsp+140h+var_EA], cx
0x180034ba5  jmp     loc_1800351E3
0x180034baa  mov     rsi, rbx
0x180034bad  mov     [rbp+40h+var_60], r10
0x180034bb1  mov     [rbp+40h+var_90], r10
0x180034bb5  mov     rbx, r10
0x180034bb8  mov     [rbp+40h+var_A0], rbx
0x180034bbc  mov     [rbp+40h+var_88], r10
0x180034bc0  mov     r8d, r10d
0x180034bc3  mov     [rbp+40h+var_B8], r10d
0x180034bc7  mov     [rbp+40h+var_A8], r10d
0x180034bcb  mov     r13, r10
0x180034bce  mov     [rbp+40h+var_68], r10
0x180034bd2  mov     r12, r10
0x180034bd5  mov     [rsp+140h+var_F8], r10d
0x180034bda  mov     [rbp+40h+var_58], r10
0x180034bde  cmp     [rbp+40h+arg_10], r10
0x180034be2  jnz     loc_180034C68
0x180034be8  xor     edx, edx; Val
0x180034bea  mov     r8d, 10000h; Size
0x180034bf0  mov     rcx, rsi; void *
0x180034bf3  call    memset_0
0x180034bf8  mov     [rbp+40h+InBuffer], rbx
0x180034bfc  xor     edx, edx
0x180034bfe  mov     [rsp+140h+lpOverlapped], rdx; lpOverlapped
0x180034c03  lea     rax, [rbp+40h+BytesReturned]
0x180034c07  mov     [rsp+140h+lpBytesReturned], rax; lpBytesReturned
0x180034c0c  mov     [rsp+140h+nOutBufferSize], 10000h; nOutBufferSize
0x180034c14  mov     [rsp+140h+lpOutBuffer], rsi; lpOutBuffer
0x180034c19  lea     r9d, [rdx+8]; nInBufferSize
0x180034c1d  lea     r8, [rbp+40h+InBuffer]; lpInBuffer
0x180034c21  mov     edx, 90073h; dwIoControlCode
0x180034c26  mov     rcx, [rbp+40h+hDevice]; hDevice
0x180034c2a  call    cs:__imp_DeviceIoControl
0x180034c30  mov     ebx, eax
0x180034c32  call    cs:__imp_GetLastError
0x180034c38  mov     [rbp+40h+var_A8], eax
0x180034c3b  xor     r10d, r10d
0x180034c3e  test    ebx, ebx
0x180034c40  jnz     short loc_180034C52
0x180034c42  cmp     eax, 0EAh
0x180034c47  jz      short loc_180034C57
0x180034c49  cmp     eax, 26h ; '&'
0x180034c4c  jnz     loc_180034FD5
0x180034c52  cmp     eax, 26h ; '&'
0x180034c55  jz      short loc_180034C60
0x180034c57  cmp     [rsi], r10d
0x180034c5a  jz      loc_180034FEC
0x180034c60  mov     rbx, [rbp+40h+var_A0]
0x180034c64  mov     r8d, [rbp+40h+var_B8]
0x180034c68  mov     eax, r10d
0x180034c6b  lea     r11, [r15+98h]
0x180034c72  mov     [rbp+40h+var_AC], eax
0x180034c75  lea     r15, [r11]
0x180034c78  cmp     eax, [rsi]
0x180034c7a  jnb     loc_180034FBF
0x180034c80  mov     r13d, eax
0x180034c83  add     r13, r13
0x180034c86  cmp     [rsi+r13*8+10h], rbx
0x180034c8b  jbe     loc_18003504C
0x180034c91  mov     rcx, [rbp+40h+arg_0]
0x180034c95  add     rcx, 98h
0x180034c9c  mov     [rbp+40h+var_70], rcx
0x180034ca0  lea     rdx, [rsp+140h+var_FC]
0x180034ca5  mov     rcx, [rcx]
0x180034ca8  call    ?Alloc@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Alloc(ulong *)
0x180034cad  mov     [rsp+140h+var_F0], eax
0x180034cb1  xor     r10d, r10d
0x180034cb4  test    eax, eax
0x180034cb6  mov     eax, 197h
0x180034cbb  js      loc_180035012
0x180034cc1  mov     [rsp+140h+var_EC], ax
0x180034cc6  mov     eax, [rsp+140h+var_FC]
0x180034cca  test    eax, eax
0x180034ccc  jz      loc_180035035
0x180034cd2  mov     [rsp+140h+var_F0], r10d
0x180034cd7  mov     ecx, 198h
0x180034cdc  mov     [rsp+140h+var_EC], cx
0x180034ce1  mov     r11, [rbp+40h+var_70]
0x180034ce5  mov     r8, [r11]
0x180034ce8  cmp     [r8+1Ch], r10d
0x180034cec  jbe     loc_180035026
0x180034cf2  mov     edx, eax
0x180034cf4  and     eax, 0F0000000h
0x180034cf9  cmp     eax, [r8+1Ch]
0x180034cfd  jnz     loc_18003501C
0x180034d03  test    edx, edx
0x180034d05  jz      loc_18003501C
0x180034d0b  movzx   eax, dx
0x180034d0e  lea     ecx, [rax-1]
0x180034d11  neg     eax
0x180034d13  sbb     r9d, r9d
0x180034d16  and     r9d, ecx
0x180034d19  shr     rdx, 10h
0x180034d1d  and     edx, 0FFFh
0x180034d23  mov     rax, [r8+8]
0x180034d27  mov     rax, [rax+rdx*8]
0x180034d2b  test    rax, rax
0x180034d2e  jz      loc_18003501C
0x180034d34  cmp     r9d, [r8+14h]
0x180034d38  jnb     loc_18003501C
0x180034d3e  mov     edx, r9d
0x180034d41  imul    rdx, [r8+20h]
0x180034d46  add     rdx, [rax]
0x180034d49  mov     [rbp+40h+var_50], rdx
0x180034d4d  mov     eax, 19Ah
0x180034d52  mov     [rsp+140h+var_EC], ax
0x180034d57  mov     eax, 19Bh
0x180034d5c  jz      loc_18003500A
0x180034d62  mov     [rsp+140h+var_F0], r10d
0x180034d67  mov     [rsp+140h+var_EC], ax
0x180034d6c  lea     ecx, [r10+28h]
0x180034d70  mov     rax, rdx
0x180034d73  mov     [rax], r10b
0x180034d76  inc     rax
0x180034d79  sub     rcx, 1
0x180034d7d  jnz     short loc_180034D73
0x180034d7f  mov     rax, [rsi+r13*8+18h]
0x180034d84  mov     [rdx], rax
0x180034d87  mov     rcx, [rsi+r13*8+10h]
0x180034d8c  sub     rcx, rbx
0x180034d8f  mov     [rdx+8], rcx
0x180034d93  mov     [rdx+18h], rbx
0x180034d97  mov     [rdx+10h], r10
0x180034d9b  mov     r8d, [rbp+40h+arg_18]
0x180034d9f  mov     [rdx+20h], r8d
0x180034da3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034da7  jz      short loc_180034DAD
0x180034da9  add     [rbp+40h+var_58], rcx
0x180034dad  cmp     [rbp+40h+var_B8], r10d
0x180034db1  jnz     short loc_180034DEF
0x180034db3  mov     r8, [rsi+8]
0x180034db7  mov     [rbp+40h+var_88], r8
0x180034dbb  mov     r8, [rsi+r13*8+18h]
0x180034dc0  mov     [rbp+40h+var_90], r8
0x180034dc4  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180034dc8  jnz     short loc_180034DCF
0x180034dca  or      r12, r8
0x180034dcd  jmp     short loc_180034DD7
0x180034dcf  mov     r12, [rsi+r13*8+10h]
0x180034dd4  add     r12, r8
0x180034dd7  mov     eax, [rsp+140h+var_FC]
0x180034ddb  mov     dword ptr [rsp+140h+var_F4], eax
0x180034ddf  mov     [rbp+40h+var_B4], eax
0x180034de2  mov     [rsp+140h+var_F8], 1
0x180034dea  jmp     loc_180034F95
0x180034def  cmp     qword ptr [rsi+r13*8+18h], 0FFFFFFFFFFFFFFFFh
0x180034df5  jz      loc_180034F6B
0x180034dfb  cmp     [rsi+r13*8+18h], r12
0x180034e00  jz      loc_180034F6B
0x180034e06  lea     rdx, [rsp+140h+var_100]
0x180034e0b  mov     rcx, [r11]
0x180034e0e  call    ?Alloc@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Alloc(ulong *)
0x180034e13  mov     [rsp+140h+var_F0], eax
0x180034e17  xor     r10d, r10d
0x180034e1a  mov     edi, [rsp+140h+var_100]
0x180034e1e  test    eax, eax
0x180034e20  mov     eax, 209h
0x180034e25  js      loc_180035000
0x180034e2b  mov     [rsp+140h+var_EC], ax
0x180034e30  mov     eax, 20Ah
0x180034e35  test    edi, edi
0x180034e37  jz      loc_18003500A
0x180034e3d  mov     [rsp+140h+var_F0], r10d
0x180034e42  mov     [rsp+140h+var_EC], ax
0x180034e47  lea     r8, [rbp+40h+var_98]
0x180034e4b  lea     rdx, [rsp+140h+var_100]
0x180034e50  mov     r11, [rbp+40h+var_70]
0x180034e54  mov     rcx, [r11]
0x180034e57  call    ?GetElement@?$CBulkAllocator@VCNtfsFile@@@@QEAAJPEAKPEAPEAVCNtfsFile@@@Z; CBulkAllocator<CNtfsFile>::GetElement(ulong *,CNtfsFile * *)
0x180034e5c  mov     [rsp+140h+var_F0], eax
0x180034e60  xor     r10d, r10d
0x180034e63  test    eax, eax
0x180034e65  mov     eax, 20Ch
0x180034e6a  js      loc_180035000
0x180034e70  mov     [rsp+140h+var_EC], ax
0x180034e75  mov     rbx, [rbp+40h+var_98]
0x180034e79  mov     eax, 20Dh
0x180034e7e  test    rbx, rbx
0x180034e81  jz      loc_180034FF8
0x180034e87  mov     [rsp+140h+var_F0], r10d
0x180034e8c  mov     [rsp+140h+var_EC], ax
0x180034e91  lea     ecx, [r10+28h]
0x180034e95  mov     rax, rbx
0x180034e98  mov     [rax], r10b
0x180034e9b  inc     rax
0x180034e9e  sub     rcx, 1
0x180034ea2  jnz     short loc_180034E98
0x180034ea4  mov     rax, [rbp+40h+var_90]
0x180034ea8  mov     [rbx], rax
0x180034eab  mov     rcx, [rbp+40h+var_A0]
0x180034eaf  mov     rax, rcx
0x180034eb2  mov     rdx, [rbp+40h+var_88]
0x180034eb6  sub     rax, rdx
0x180034eb9  mov     [rbx+8], rax
0x180034ebd  mov     [rbx+18h], rdx
0x180034ec1  mov     eax, [rbp+40h+arg_18]
0x180034ec4  mov     [rbx+14h], eax
0x180034ec7  mov     [rbx+20h], eax
0x180034eca  cmp     [rsp+140h+var_F8], 1
0x180034ecf  ja      short loc_180034F03
0x180034ed1  lea     rdx, [rbp+40h+var_B4]
0x180034ed5  mov     rcx, [r11]
0x180034ed8  call    ?Free@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Free(ulong *)
0x180034edd  mov     [rsp+140h+var_F0], eax
0x180034ee1  xor     r10d, r10d
0x180034ee4  test    eax, eax
0x180034ee6  mov     eax, 222h
0x180034eeb  js      loc_180035000
0x180034ef1  mov     [rsp+140h+var_EC], ax
0x180034ef6  mov     eax, r10d
0x180034ef9  mov     rcx, [rbp+40h+var_A0]
0x180034efd  mov     r11, [rbp+40h+var_70]
0x180034f01  jmp     short loc_180034F14
0x180034f03  mov     r8, [rbp+40h+var_68]
  ... truncated ...
```
