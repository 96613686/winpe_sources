# ProcessRasPortListenEvent

- ea: `0x180016d40`
- end: `0x180017485`
- name: `ProcessRasPortListenEvent`
- size: `1861`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800109a0`
- `0x180011038`
- `0x180013490`
- `0x180013af8`
- `0x180016d40`
- `0x1800186a0`
- `0x18002a138`
- `0x180032400`
- `0x180032460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800171a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800171a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800170c4`
- `rasman!RasProtocolStart` at `0x1800172e1`
- `rasman!RasProtocolStart` at `0x1800172e1`
- `rasman!RasPortClose` at `0x180017466`
- `rasman!RasPortClose` at `0x180017466`
- `rasman!RasPortDisconnect` at `0x180017416`
- `rasman!RasPortDisconnect` at `0x180017416`
- `rasman!RasPortConnectComplete` at `0x180016f2c`
- `rasman!RasPortConnectComplete` at `0x180016f2c`
- `rasman!RasSetEapInfo` at `0x1800170ff`
- `rasman!RasSetEapInfo` at `0x1800170ff`
- `rasman!RasPortSetFraming` at `0x180016f9d`
- `rasman!RasPortSetFraming` at `0x180016f9d`
- `rasman!RasGetInfo` at `0x180016ee5`
- `rasman!RasGetInfo` at `0x180016ee5`

## string_xrefs

- `0x180016f45`: `RasPortConnectComplete on hPort %d returned error %d`

## pseudocode

```c
int __fastcall ProcessRasPortListenEvent(__int64 a1)
{
  __int64 v2; // r8
  __int64 PCBPointerFromhPort; // rax
  char *v4; // rdi
  __int64 v5; // r12
  __int64 v6; // r14
  unsigned int Info; // ebx
  __int64 BCBPointerFromhConnection; // rax
  unsigned int v9; // eax
  const wchar_t *v10; // rdx
  __int64 v11; // r9
  __int64 v12; // r15
  unsigned int v13; // r8d
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // r13
  unsigned int v17; // eax
  const wchar_t *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  _BYTE *v21; // r12
  _BYTE *i; // rax
  __int64 v23; // rdx
  unsigned int v24; // eax
  const wchar_t *v25; // rdx
  __int64 *v26; // rdx
  _BYTE *v27; // rax
  __int64 v28; // rbx
  _OWORD *v29; // rax
  _OWORD *v30; // rcx
  __int128 v31; // xmm1
  int *v32; // rax
  unsigned int v33; // eax
  size_t Size; // [rsp+70h] [rbp-90h] BYREF
  void *Src; // [rsp+78h] [rbp-88h] BYREF
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+90h] [rbp-70h]
  _BYTE v39[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v40; // [rsp+A4h] [rbp-5Ch]
  unsigned int v41; // [rsp+ACh] [rbp-54h]
  int v42; // [rsp+B0h] [rbp-50h]
  _BYTE v43[8]; // [rsp+440h] [rbp+340h] BYREF
  int v44; // [rsp+448h] [rbp+348h]
  int v45; // [rsp+44Ch] [rbp+34Ch]
  int v46; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v47[2044]; // [rsp+874h] [rbp+774h] BYREF
  _BYTE v48[272]; // [rsp+1070h] [rbp+F70h] BYREF

  memset_0(v39, 0, 0x398u);
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
  v2 = *(_QWORD *)(a1 + 16);
  v38 = 0;
  v37 = 0;
  DWORD1(v37) = -1;
  PCBPointerFromhPort = GetPCBPointerFromhPort(v2);
  v4 = (char *)PCBPointerFromhPort;
  v5 = 257;
  if ( !PCBPointerFromhPort )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get the PCB for hPort %d");
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    v6 = 0;
    Info = 615;
    goto LABEL_52;
  }
  BCBPointerFromhConnection = GetBCBPointerFromhConnection(*(_QWORD *)(PCBPointerFromhPort + 120));
  v6 = BCBPointerFromhConnection;
  if ( !BCBPointerFromhConnection )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get the BCB for HCONN 0x%x", *((_QWORD *)v4 + 15));
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    Info = 754;
    goto LABEL_52;
  }
  if ( (byte_18004CF34 & 1) != 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"ProcessRasPortListenEvent on HCONN 0x%x", *(_QWORD *)(BCBPointerFromhConnection + 40));
    if ( (byte_18004CF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
  }
  Info = RasGetInfo(0, *((_QWORD *)v4 + 2), v39);
  if ( Info || (Info = v41) != 0 )
  {
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v46) = 0;
      v32 = (int *)" (ERROR_REQUEST_TIMEOUT)";
      if ( Info != 638 )
        v32 = &dword_180039974;
      FormatRRASErrorString(&v46, L"RasGetInfo on hPort %d returned error %d%hs", *((_QWORD *)v4 + 2), Info, v32);
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    if ( (v42 & 1) == 0 )
    {
      v33 = RasPortDisconnect(*((_QWORD *)v4 + 2), -1);
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"RasPortDisconnect returned %d", v33);
        if ( byte_18004CF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
      }
    }
    v17 = RasPortClose(*((_QWORD *)v4 + 2));
    if ( byte_18004CF33 < 0 )
    {
      v18 = L"RasPortDisconnect returned %d";
LABEL_37:
      v19 = v17;
LABEL_38:
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, v18, v19);
LABEL_21:
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
  }
  else
  {
    if ( v40 != 5 )
      goto LABEL_52;
    LODWORD(Size) = 0;
    Src = 0;
    memset_0(v43, 0, 0x430u);
    v9 = RasPortConnectComplete(*((_QWORD *)v4 + 2));
    Info = v9;
    if ( v9 )
    {
      if ( byte_18004CF33 >= 0 )
        goto LABEL_52;
      v10 = L"RasPortConnectComplete on hPort %d returned error %d";
      goto LABEL_20;
    }
    v9 = RasPortSetFraming(*((_QWORD *)v4 + 2), 0, &v37, &v37);
    Info = v9;
    if ( v9 )
    {
      if ( byte_18004CF33 >= 0 )
        goto LABEL_52;
      v10 = L"RasPortSetFraming on hPort %d returned error %d";
LABEL_20:
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, v10, *((_QWORD *)v4 + 2), v9);
      goto LABEL_21;
    }
    if ( *(_DWORD *)(v6 + 48) )
    {
      v11 = *(_QWORD *)(v6 + 8);
      v12 = 0;
      v13 = 0;
      v14 = 0;
      do
      {
        v15 = *(_QWORD *)(v11 + 8LL * v14);
        if ( v15 && *(_DWORD *)(v15 + 1456) == 9 && *(_DWORD *)(v15 + 1256) >= v13 )
        {
          v12 = *(_QWORD *)(v11 + 8LL * v14);
          v13 = *(_DWORD *)(v15 + 1256);
        }
        ++v14;
      }
      while ( v14 < *(_DWORD *)(v6 + 48) );
      if ( v12 )
      {
        v16 = v12 + 8;
        v17 = DecodePassword(*(_QWORD *)(v12 + 8) + 184LL, &Size, &Src);
        Info = v17;
        if ( v17 )
        {
          if ( byte_18004CF33 >= 0 )
            goto LABEL_52;
          v18 = L"DecodePassword failed. 0x%x";
          goto LABEL_37;
        }
        v48[0] = 0;
        if ( (unsigned int)Size > 0x101 )
        {
          Info = 8;
          if ( byte_18004CF33 >= 0 )
            goto LABEL_52;
          v19 = 8;
          v18 = L"Not enough memory. 0x%x";
          goto LABEL_38;
        }
        v20 = (unsigned int)Size;
        v21 = Src;
        memcpy_0(v48, Src, (unsigned int)Size);
        for ( i = v21; v20; --v20 )
          *i++ = 0;
        LocalFree(v21);
        v23 = *(unsigned int *)(v12 + 128);
        if ( (_DWORD)v23
          && (v24 = RasSetEapInfo(
                      *((_QWORD *)v4 + 2),
                      v23,
                      **(unsigned int **)(*(_QWORD *)v16 + 88LL),
                      *(_QWORD *)(*(_QWORD *)v16 + 88LL) + 4LL,
                      **(_DWORD **)(*(_QWORD *)v16 + 96LL),
                      *(_QWORD *)(*(_QWORD *)v16 + 96LL) + 4LL),
              (Info = v24) != 0) )
        {
          if ( byte_18004CF33 >= 0 )
            goto LABEL_51;
          v25 = L"RasSetEapInfo failed. dwErr = %d";
        }
        else
        {
          v28 = 8;
          v29 = (_OWORD *)(v12 + 184);
          v30 = v43;
          do
          {
            *v30 = *v29;
            v30[1] = v29[1];
            v30[2] = v29[2];
            v30[3] = v29[3];
            v30[4] = v29[4];
            v30[5] = v29[5];
            v30[6] = v29[6];
            v31 = v29[7];
            v29 += 8;
            v30[7] = v31;
            v30 += 8;
            --v28;
          }
          while ( v28 );
          *v30 = *v29;
          v30[1] = v29[1];
          v30[2] = v29[2];
          v44 = *(_DWORD *)(v12 + 88);
          v45 = 4;
          v24 = RasProtocolStart(
                  *((_QWORD *)v4 + 2),
                  v4 + 1665,
                  *(_QWORD *)(*(_QWORD *)v16 + 152LL),
                  *(_QWORD *)(*(_QWORD *)v16 + 160LL),
                  *(_QWORD *)(*(_QWORD *)v16 + 104LL),
                  *(_QWORD *)v16 + 489LL,
                  v48,
                  *(_QWORD *)v16 + 746LL,
                  v12 + 1528,
                  v43,
                  v6 + 1320,
                  v6 + 1344,
                  -1,
                  0);
          Info = v24;
          if ( !v24 )
          {
            if ( (byte_18004CF34 & 1) == 0 )
              goto LABEL_51;
            LOWORD(v46) = 0;
            FormatRRASErrorString(
              &v46,
              L"RasPppStart called successfully for hPort %d on HCONN 0x%x",
              *((_QWORD *)v4 + 2),
              *(_QWORD *)(v6 + 40));
            if ( (byte_18004CF34 & 1) == 0 )
              goto LABEL_51;
            v26 = RasPppTraceInfo;
            goto LABEL_50;
          }
          if ( byte_18004CF33 >= 0 )
            goto LABEL_51;
          v25 = L"RasPppStart failed. dwErr = %d";
        }
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, v25, v24);
        if ( byte_18004CF33 < 0 )
        {
          v26 = RasPppTraceError;
LABEL_50:
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v26, &v46);
        }
LABEL_51:
        v5 = 257;
        goto LABEL_52;
      }
    }
    if ( byte_18004CF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get a PCB for HCONN 0x%x", *((_QWORD *)v4 + 15));
      if ( byte_18004CF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    Info = 1;
  }
LABEL_52:
  v27 = v48;
  do
  {
    *v27++ = 0;
    --v5;
  }
  while ( v5 );
  if ( v6 )
    *(_DWORD *)(v6 + 52) &= ~0x100u;
  if ( Info && v4 )
  {
    NotifyCallerOfFailure(v4, 0);
    RemovePcbFromTable(v4);
    LODWORD(v27) = HeapFree(hHeap, 0, v4);
  }
  return (int)v27;
}

```

## disassembly

```asm
0x180016d40  push    rbp
0x180016d42  push    rbx
0x180016d43  push    rsi
0x180016d44  push    rdi
0x180016d45  push    r12
0x180016d47  push    r13
0x180016d49  push    r14
0x180016d4b  push    r15
0x180016d4d  lea     rbp, [rsp-1098h]
0x180016d55  mov     eax, 1198h
0x180016d5a  call    _alloca_probe
0x180016d5f  sub     rsp, rax
0x180016d62  mov     rax, cs:__security_cookie
0x180016d69  xor     rax, rsp
0x180016d6c  mov     [rbp+10D0h+var_50], rax
0x180016d73  mov     rbx, rcx
0x180016d76  xor     edx, edx; Val
0x180016d78  lea     rcx, [rbp+10D0h+var_1130]; void *
0x180016d7c  mov     r8d, 398h; Size
0x180016d82  call    memset_0
0x180016d87  xor     r13d, r13d
0x180016d8a  lea     rcx, [rbp+10D0h+var_95C]; void *
0x180016d91  xor     edx, edx; Val
0x180016d93  mov     [rbp+10D0h+var_960], r13d
0x180016d9a  mov     r8d, 7FCh; Size
0x180016da0  call    memset_0
0x180016da5  mov     r8, [rbx+10h]
0x180016da9  xor     eax, eax
0x180016dab  xorps   xmm0, xmm0
0x180016dae  mov     [rbp+10D0h+var_1140], rax
0x180016db2  movups  [rbp+10D0h+var_1150], xmm0
0x180016db6  mov     rcx, r8
0x180016db9  mov     dword ptr [rbp+10D0h+var_1150+4], 0FFFFFFFFh
0x180016dc0  call    GetPCBPointerFromhPort
0x180016dc5  mov     rdi, rax
0x180016dc8  mov     r12d, 101h
0x180016dce  test    rax, rax
0x180016dd1  jnz     short loc_180016E27
0x180016dd3  cmp     cs:byte_18004CF33, r13b
0x180016dda  jge     short loc_180016E1A
0x180016ddc  lea     rdx, aCouldnTGetTheP; "Couldn't get the PCB for hPort %d"
0x180016de3  mov     word ptr [rbp+10D0h+var_960], r13w
0x180016deb  lea     rcx, [rbp+10D0h+var_960]
0x180016df2  call    FormatRRASErrorString
0x180016df7  cmp     cs:byte_18004CF33, r13b
0x180016dfe  jge     short loc_180016E1A
0x180016e00  lea     r8, [rbp+10D0h+var_960]
0x180016e07  lea     rdx, RasPppTraceError
0x180016e0e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e15  call    McTemplateU0z_EventWriteTransfer
0x180016e1a  mov     r14, r13
0x180016e1d  mov     ebx, 267h
0x180016e22  jmp     loc_18001715E
0x180016e27  mov     rcx, [rax+78h]
0x180016e2b  call    GetBCBPointerFromhConnection
0x180016e30  mov     r14, rax
0x180016e33  test    rax, rax
0x180016e36  jnz     short loc_180016E8D
0x180016e38  cmp     cs:byte_18004CF33, r13b
0x180016e3f  jge     short loc_180016E83
0x180016e41  mov     word ptr [rbp+10D0h+var_960], r13w
0x180016e49  lea     rdx, aCouldnTGetTheB; "Couldn't get the BCB for HCONN 0x%x"
0x180016e50  mov     r8, [rdi+78h]
0x180016e54  lea     rcx, [rbp+10D0h+var_960]
0x180016e5b  call    FormatRRASErrorString
0x180016e60  cmp     cs:byte_18004CF33, r13b
0x180016e67  jge     short loc_180016E83
0x180016e69  lea     r8, [rbp+10D0h+var_960]
0x180016e70  lea     rdx, RasPppTraceError
0x180016e77  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e7e  call    McTemplateU0z_EventWriteTransfer
0x180016e83  mov     ebx, 2F2h
0x180016e88  jmp     loc_18001715E
0x180016e8d  test    cs:byte_18004CF34, 1
0x180016e94  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e9b  jz      short loc_180016EDB
0x180016e9d  mov     word ptr [rbp+10D0h+var_960], r13w
0x180016ea5  lea     rdx, aProcessrasport; "ProcessRasPortListenEvent on HCONN 0x%x"
0x180016eac  mov     r8, [rax+28h]
0x180016eb0  lea     rcx, [rbp+10D0h+var_960]
0x180016eb7  call    FormatRRASErrorString
0x180016ebc  test    cs:byte_18004CF34, 1
0x180016ec3  jz      short loc_180016EDB
0x180016ec5  lea     r8, [rbp+10D0h+var_960]
0x180016ecc  mov     rcx, rsi
0x180016ecf  lea     rdx, RasPppTraceInfo
0x180016ed6  call    McTemplateU0z_EventWriteTransfer
0x180016edb  mov     rdx, [rdi+10h]
0x180016edf  lea     r8, [rbp+10D0h+var_1130]
0x180016ee3  xor     ecx, ecx
0x180016ee5  call    cs:__imp_RasGetInfo
0x180016eeb  mov     ebx, eax
0x180016eed  test    eax, eax
0x180016eef  jnz     loc_1800173A0
0x180016ef5  mov     ebx, [rbp+10D0h+var_1124]
0x180016ef8  test    ebx, ebx
0x180016efa  jnz     loc_1800173A0
0x180016f00  cmp     [rbp+10D0h+var_112C], 5
0x180016f04  jnz     loc_18001715E
0x180016f0a  xor     edx, edx; Val
0x180016f0c  mov     dword ptr [rsp+11D0h+Size], r13d
0x180016f11  mov     r8d, 430h; Size
0x180016f17  mov     [rsp+11D0h+Src], r13
0x180016f1c  lea     rcx, [rbp+10D0h+var_D90]; void *
0x180016f23  call    memset_0
0x180016f28  mov     rcx, [rdi+10h]
0x180016f2c  call    cs:__imp_RasPortConnectComplete
0x180016f32  mov     ebx, eax
0x180016f34  test    eax, eax
0x180016f36  jz      short loc_180016F8F
0x180016f38  cmp     cs:byte_18004CF33, r13b
0x180016f3f  jge     loc_18001715E
0x180016f45  lea     rdx, aRasportconnect; "RasPortConnectComplete on hPort %d retu"...
0x180016f4c  mov     word ptr [rbp+10D0h+var_960], r13w
0x180016f54  lea     rcx, [rbp+10D0h+var_960]
0x180016f5b  mov     r8, [rdi+10h]
0x180016f5f  mov     r9d, eax
0x180016f62  call    FormatRRASErrorString
0x180016f67  cmp     cs:byte_18004CF33, r13b
0x180016f6e  jge     loc_18001715E
0x180016f74  lea     r8, [rbp+10D0h+var_960]
0x180016f7b  mov     rcx, rsi
0x180016f7e  lea     rdx, RasPppTraceError
0x180016f85  call    McTemplateU0z_EventWriteTransfer
0x180016f8a  jmp     loc_18001715E
0x180016f8f  mov     rcx, [rdi+10h]
0x180016f93  lea     r9, [rbp+10D0h+var_1150]
0x180016f97  lea     r8, [rbp+10D0h+var_1150]
0x180016f9b  xor     edx, edx
0x180016f9d  call    cs:__imp_RasPortSetFraming
0x180016fa3  mov     ebx, eax
0x180016fa5  test    eax, eax
0x180016fa7  jz      short loc_180016FBF
0x180016fa9  cmp     cs:byte_18004CF33, r13b
0x180016fb0  jge     loc_18001715E
0x180016fb6  lea     rdx, aRasportsetfram; "RasPortSetFraming on hPort %d returned "...
0x180016fbd  jmp     short loc_180016F4C
0x180016fbf  cmp     [r14+30h], r13d
0x180016fc3  jbe     loc_18001734F
0x180016fc9  mov     r9, [r14+8]
0x180016fcd  mov     r15, r13
0x180016fd0  mov     r8d, r13d
0x180016fd3  mov     edx, r13d
0x180016fd6  mov     eax, edx
0x180016fd8  mov     rcx, [r9+rax*8]
0x180016fdc  test    rcx, rcx
0x180016fdf  jz      short loc_180016FFB
0x180016fe1  cmp     dword ptr [rcx+5B0h], 9
0x180016fe8  jnz     short loc_180016FFB
0x180016fea  mov     eax, [rcx+4E8h]
0x180016ff0  cmp     eax, r8d
0x180016ff3  jb      short loc_180016FFB
0x180016ff5  mov     r15, rcx
0x180016ff8  mov     r8d, eax
0x180016ffb  inc     edx
0x180016ffd  cmp     edx, [r14+30h]
0x180017001  jb      short loc_180016FD6
0x180017003  test    r15, r15
0x180017006  jz      loc_18001734F
0x18001700c  lea     r13, [r15+8]
0x180017010  mov     rcx, [r13+0]
0x180017014  lea     r8, [rsp+11D0h+Src]
0x180017019  add     rcx, 0B8h
0x180017020  lea     rdx, [rsp+11D0h+Size]
0x180017025  call    DecodePassword
0x18001702a  mov     ebx, eax
0x18001702c  test    eax, eax
0x18001702e  jz      short loc_180017063
0x180017030  xor     r13d, r13d
0x180017033  cmp     cs:byte_18004CF33, r13b
0x18001703a  jge     loc_18001715E
0x180017040  lea     rdx, aDecodepassword; "DecodePassword failed. 0x%x"
0x180017047  mov     r8d, eax
0x18001704a  lea     rcx, [rbp+10D0h+var_960]
0x180017051  mov     word ptr [rbp+10D0h+var_960], r13w
0x180017059  call    FormatRRASErrorString
0x18001705e  jmp     loc_180016F67
0x180017063  mov     [rbp+10D0h+var_160], 0
0x18001706a  cmp     dword ptr [rsp+11D0h+Size], r12d
0x18001706f  jbe     short loc_180017092
0x180017071  xor     r13d, r13d
0x180017074  mov     ebx, 8
0x180017079  cmp     cs:byte_18004CF33, r13b
0x180017080  jge     loc_18001715E
0x180017086  mov     r8d, ebx
0x180017089  lea     rdx, aNotEnoughMemor; "Not enough memory. 0x%x"
0x180017090  jmp     short loc_18001704A
0x180017092  mov     ebx, dword ptr [rsp+11D0h+Size]
0x180017096  lea     rcx, [rbp+10D0h+var_160]; void *
0x18001709d  mov     r12, [rsp+11D0h+Src]
0x1800170a2  mov     r8d, ebx; Size
0x1800170a5  mov     rdx, r12; Src
0x1800170a8  call    memcpy_0
0x1800170ad  mov     rax, r12
0x1800170b0  test    rbx, rbx
0x1800170b3  jz      short loc_1800170C1
0x1800170b5  mov     byte ptr [rax], 0
0x1800170b8  inc     rax
0x1800170bb  sub     rbx, 1
0x1800170bf  jnz     short loc_1800170B5
0x1800170c1  mov     rcx, r12; hMem
0x1800170c4  call    cs:__imp_LocalFree
0x1800170ca  mov     edx, [r15+80h]
0x1800170d1  test    edx, edx
0x1800170d3  jz      loc_1800171CC
0x1800170d9  mov     rax, [r13+0]
0x1800170dd  mov     r8, [rax+58h]
0x1800170e1  mov     rcx, [rax+60h]
0x1800170e5  lea     r9, [r8+4]
0x1800170e9  mov     r8d, [r8]
0x1800170ec  lea     rax, [rcx+4]
0x1800170f0  mov     [rsp+11D0h+var_11A8], rax
0x1800170f5  mov     eax, [rcx]
0x1800170f7  mov     rcx, [rdi+10h]
0x1800170fb  mov     dword ptr [rsp+11D0h+var_11B0], eax
0x1800170ff  call    cs:__imp_RasSetEapInfo
0x180017105  mov     ebx, eax
0x180017107  test    eax, eax
0x180017109  jz      loc_1800171CC
0x18001710f  xor     r13d, r13d
0x180017112  cmp     cs:byte_18004CF33, r13b
0x180017119  jge     short loc_180017158
0x18001711b  lea     rdx, aRasseteapinfoF; "RasSetEapInfo failed. dwErr = %d"
0x180017122  mov     r8d, eax
0x180017125  mov     word ptr [rbp+10D0h+var_960], r13w
0x18001712d  lea     rcx, [rbp+10D0h+var_960]
0x180017134  call    FormatRRASErrorString
0x180017139  cmp     cs:byte_18004CF33, r13b
0x180017140  jge     short loc_180017158
0x180017142  lea     rdx, RasPppTraceError
0x180017149  lea     r8, [rbp+10D0h+var_960]
0x180017150  mov     rcx, rsi
0x180017153  call    McTemplateU0z_EventWriteTransfer
0x180017158  mov     r12d, 101h
0x18001715e  lea     rax, [rbp+10D0h+var_160]
0x180017165  mov     [rax], r13b
0x180017168  inc     rax
0x18001716b  sub     r12, 1
0x18001716f  jnz     short loc_180017165
0x180017171  test    r14, r14
0x180017174  jz      short loc_18001717C
0x180017176  btr     dword ptr [r14+34h], 8
0x18001717c  test    ebx, ebx
0x18001717e  jz      short loc_1800171A9
0x180017180  test    rdi, rdi
0x180017183  jz      short loc_1800171A9
0x180017185  xor     edx, edx
0x180017187  mov     rcx, rdi
0x18001718a  call    NotifyCallerOfFailure
0x18001718f  mov     rcx, rdi
0x180017192  call    RemovePcbFromTable
0x180017197  mov     rcx, cs:hHeap; hHeap
0x18001719e  mov     r8, rdi; lpMem
0x1800171a1  xor     edx, edx; dwFlags
0x1800171a3  call    cs:__imp_HeapFree
0x1800171a9  mov     rcx, [rbp+10D0h+var_50]
0x1800171b0  xor     rcx, rsp; StackCookie
0x1800171b3  call    __security_check_cookie
0x1800171b8  add     rsp, 1198h
0x1800171bf  pop     r15
0x1800171c1  pop     r14
0x1800171c3  pop     r13
0x1800171c5  pop     r12
0x1800171c7  pop     rdi
0x1800171c8  pop     rsi
0x1800171c9  pop     rbx
0x1800171ca  pop     rbp
0x1800171cb  retn
0x1800171cc  mov     ebx, 8
0x1800171d1  lea     rax, [r15+0B8h]
0x1800171d8  lea     rcx, [rbp+10D0h+var_D90]
0x1800171df  lea     edx, [rbx+78h]
0x1800171e2  movups  xmm0, xmmword ptr [rax]
0x1800171e5  movups  xmmword ptr [rcx], xmm0
0x1800171e8  movups  xmm1, xmmword ptr [rax+10h]
0x1800171ec  movups  xmmword ptr [rcx+10h], xmm1
0x1800171f0  movups  xmm0, xmmword ptr [rax+20h]
0x1800171f4  movups  xmmword ptr [rcx+20h], xmm0
0x1800171f8  movups  xmm1, xmmword ptr [rax+30h]
0x1800171fc  movups  xmmword ptr [rcx+30h], xmm1
0x180017200  movups  xmm0, xmmword ptr [rax+40h]
0x180017204  movups  xmmword ptr [rcx+40h], xmm0
0x180017208  movups  xmm1, xmmword ptr [rax+50h]
0x18001720c  movups  xmmword ptr [rcx+50h], xmm1
0x180017210  movups  xmm0, xmmword ptr [rax+60h]
0x180017214  movups  xmmword ptr [rcx+60h], xmm0
0x180017218  movups  xmm1, xmmword ptr [rax+70h]
0x18001721c  add     rax, rdx
0x18001721f  movups  xmmword ptr [rcx+70h], xmm1
0x180017223  add     rcx, rdx
0x180017226  sub     rbx, 1
0x18001722a  jnz     short loc_1800171E2
0x18001722c  movups  xmm0, xmmword ptr [rax]
0x18001722f  lea     r9, [r15+5F8h]
0x180017236  lea     rdx, [rdi+681h]
0x18001723d  movups  xmmword ptr [rcx], xmm0
0x180017240  movups  xmm1, xmmword ptr [rax+10h]
0x180017244  movups  xmmword ptr [rcx+10h], xmm1
0x180017248  movups  xmm0, xmmword ptr [rax+20h]
0x18001724c  movups  xmmword ptr [rcx+20h], xmm0
  ... truncated ...
```
