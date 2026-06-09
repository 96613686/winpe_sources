# ProcessRasPortListenEvent

- ea: `0x180017510`
- end: `0x180017c8c`
- name: `ProcessRasPortListenEvent`
- size: `1916`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180010ed0`
- `0x1800115a0`
- `0x180013b54`
- `0x1800141bc`
- `0x180017510`
- `0x180018f24`
- `0x18002b0dc`
- `0x180033a20`
- `0x180033a80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017991`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017991`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800178a6`
- `rasman!RasProtocolStart` at `0x180017ad6`
- `rasman!RasProtocolStart` at `0x180017ad6`
- `rasman!RasPortClose` at `0x180017c67`
- `rasman!RasPortClose` at `0x180017c67`
- `rasman!RasPortDisconnect` at `0x180017c11`
- `rasman!RasPortDisconnect` at `0x180017c11`
- `rasman!RasPortConnectComplete` at `0x180017702`
- `rasman!RasPortConnectComplete` at `0x180017702`
- `rasman!RasSetEapInfo` at `0x1800178e7`
- `rasman!RasSetEapInfo` at `0x1800178e7`
- `rasman!RasPortSetFraming` at `0x180017779`
- `rasman!RasPortSetFraming` at `0x180017779`
- `rasman!RasGetInfo` at `0x1800176b5`
- `rasman!RasGetInfo` at `0x1800176b5`

## string_xrefs

- `0x180017721`: `RasPortConnectComplete on hPort %d returned error %d`

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
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get the PCB for hPort %d");
      if ( byte_18004DF33 < 0 )
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
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get the BCB for HCONN 0x%x", *((_QWORD *)v4 + 15));
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    Info = 754;
    goto LABEL_52;
  }
  if ( (byte_18004DF34 & 1) != 0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(&v46, L"ProcessRasPortListenEvent on HCONN 0x%x", *(_QWORD *)(BCBPointerFromhConnection + 40));
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v46);
  }
  Info = RasGetInfo(0, *((_QWORD *)v4 + 2), v39);
  if ( Info || (Info = v41) != 0 )
  {
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v46) = 0;
      v32 = (int *)" (ERROR_REQUEST_TIMEOUT)";
      if ( Info != 638 )
        v32 = &dword_18003A974;
      FormatRRASErrorString(&v46, L"RasGetInfo on hPort %d returned error %d%hs", *((_QWORD *)v4 + 2), Info, v32);
      if ( byte_18004DF33 < 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
    }
    if ( (v42 & 1) == 0 )
    {
      v33 = RasPortDisconnect(*((_QWORD *)v4 + 2), -1);
      if ( byte_18004DF33 < 0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, L"RasPortDisconnect returned %d", v33);
        if ( byte_18004DF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v46);
      }
    }
    v17 = RasPortClose(*((_QWORD *)v4 + 2));
    if ( byte_18004DF33 < 0 )
    {
      v18 = L"RasPortDisconnect returned %d";
LABEL_37:
      v19 = v17;
LABEL_38:
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, v18, v19);
LABEL_21:
      if ( byte_18004DF33 < 0 )
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
      if ( byte_18004DF33 >= 0 )
        goto LABEL_52;
      v10 = L"RasPortConnectComplete on hPort %d returned error %d";
      goto LABEL_20;
    }
    v9 = RasPortSetFraming(*((_QWORD *)v4 + 2), 0, &v37, &v37);
    Info = v9;
    if ( v9 )
    {
      if ( byte_18004DF33 >= 0 )
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
          if ( byte_18004DF33 >= 0 )
            goto LABEL_52;
          v18 = L"DecodePassword failed. 0x%x";
          goto LABEL_37;
        }
        v48[0] = 0;
        if ( (unsigned int)Size > 0x101 )
        {
          Info = 8;
          if ( byte_18004DF33 >= 0 )
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
          if ( byte_18004DF33 >= 0 )
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
            if ( (byte_18004DF34 & 1) == 0 )
              goto LABEL_51;
            LOWORD(v46) = 0;
            FormatRRASErrorString(
              &v46,
              L"RasPppStart called successfully for hPort %d on HCONN 0x%x",
              *((_QWORD *)v4 + 2),
              *(_QWORD *)(v6 + 40));
            if ( (byte_18004DF34 & 1) == 0 )
              goto LABEL_51;
            v26 = RasPppTraceInfo;
            goto LABEL_50;
          }
          if ( byte_18004DF33 >= 0 )
            goto LABEL_51;
          v25 = L"RasPppStart failed. dwErr = %d";
        }
        LOWORD(v46) = 0;
        FormatRRASErrorString(&v46, v25, v24);
        if ( byte_18004DF33 < 0 )
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
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(&v46, L"Couldn't get a PCB for HCONN 0x%x", *((_QWORD *)v4 + 15));
      if ( byte_18004DF33 < 0 )
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
0x180017510  push    rbp
0x180017512  push    rbx
0x180017513  push    rsi
0x180017514  push    rdi
0x180017515  push    r12
0x180017517  push    r13
0x180017519  push    r14
0x18001751b  push    r15
0x18001751d  lea     rbp, [rsp-1098h]
0x180017525  mov     eax, 1198h
0x18001752a  call    _alloca_probe
0x18001752f  sub     rsp, rax
0x180017532  mov     rax, cs:__security_cookie
0x180017539  xor     rax, rsp
0x18001753c  mov     [rbp+10D0h+var_50], rax
0x180017543  mov     rbx, rcx
0x180017546  xor     edx, edx; Val
0x180017548  lea     rcx, [rbp+10D0h+var_1130]; void *
0x18001754c  mov     r8d, 398h; Size
0x180017552  call    memset_0
0x180017557  xor     r13d, r13d
0x18001755a  lea     rcx, [rbp+10D0h+var_95C]; void *
0x180017561  xor     edx, edx; Val
0x180017563  mov     [rbp+10D0h+var_960], r13d
0x18001756a  mov     r8d, 7FCh; Size
0x180017570  call    memset_0
0x180017575  mov     r8, [rbx+10h]
0x180017579  xor     eax, eax
0x18001757b  xorps   xmm0, xmm0
0x18001757e  mov     [rbp+10D0h+var_1140], rax
0x180017582  movups  [rbp+10D0h+var_1150], xmm0
0x180017586  mov     rcx, r8
0x180017589  mov     dword ptr [rbp+10D0h+var_1150+4], 0FFFFFFFFh
0x180017590  call    GetPCBPointerFromhPort
0x180017595  mov     rdi, rax
0x180017598  mov     r12d, 101h
0x18001759e  test    rax, rax
0x1800175a1  jnz     short loc_1800175F7
0x1800175a3  cmp     cs:byte_18004DF33, r13b
0x1800175aa  jge     short loc_1800175EA
0x1800175ac  lea     rdx, aCouldnTGetTheP; "Couldn't get the PCB for hPort %d"
0x1800175b3  mov     word ptr [rbp+10D0h+var_960], r13w
0x1800175bb  lea     rcx, [rbp+10D0h+var_960]
0x1800175c2  call    FormatRRASErrorString
0x1800175c7  cmp     cs:byte_18004DF33, r13b
0x1800175ce  jge     short loc_1800175EA
0x1800175d0  lea     r8, [rbp+10D0h+var_960]
0x1800175d7  lea     rdx, RasPppTraceError
0x1800175de  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800175e5  call    McTemplateU0z_EventWriteTransfer
0x1800175ea  mov     r14, r13
0x1800175ed  mov     ebx, 267h
0x1800175f2  jmp     loc_18001794C
0x1800175f7  mov     rcx, [rax+78h]
0x1800175fb  call    GetBCBPointerFromhConnection
0x180017600  mov     r14, rax
0x180017603  test    rax, rax
0x180017606  jnz     short loc_18001765D
0x180017608  cmp     cs:byte_18004DF33, r13b
0x18001760f  jge     short loc_180017653
0x180017611  mov     word ptr [rbp+10D0h+var_960], r13w
0x180017619  lea     rdx, aCouldnTGetTheB; "Couldn't get the BCB for HCONN 0x%x"
0x180017620  mov     r8, [rdi+78h]
0x180017624  lea     rcx, [rbp+10D0h+var_960]
0x18001762b  call    FormatRRASErrorString
0x180017630  cmp     cs:byte_18004DF33, r13b
0x180017637  jge     short loc_180017653
0x180017639  lea     r8, [rbp+10D0h+var_960]
0x180017640  lea     rdx, RasPppTraceError
0x180017647  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001764e  call    McTemplateU0z_EventWriteTransfer
0x180017653  mov     ebx, 2F2h
0x180017658  jmp     loc_18001794C
0x18001765d  test    cs:byte_18004DF34, 1
0x180017664  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001766b  jz      short loc_1800176AB
0x18001766d  mov     word ptr [rbp+10D0h+var_960], r13w
0x180017675  lea     rdx, aProcessrasport; "ProcessRasPortListenEvent on HCONN 0x%x"
0x18001767c  mov     r8, [rax+28h]
0x180017680  lea     rcx, [rbp+10D0h+var_960]
0x180017687  call    FormatRRASErrorString
0x18001768c  test    cs:byte_18004DF34, 1
0x180017693  jz      short loc_1800176AB
0x180017695  lea     r8, [rbp+10D0h+var_960]
0x18001769c  mov     rcx, rsi
0x18001769f  lea     rdx, RasPppTraceInfo
0x1800176a6  call    McTemplateU0z_EventWriteTransfer
0x1800176ab  mov     rdx, [rdi+10h]
0x1800176af  lea     r8, [rbp+10D0h+var_1130]
0x1800176b3  xor     ecx, ecx
0x1800176b5  call    cs:__imp_RasGetInfo
0x1800176bc  nop     dword ptr [rax+rax+00h]
0x1800176c1  mov     ebx, eax
0x1800176c3  test    eax, eax
0x1800176c5  jnz     loc_180017B9B
0x1800176cb  mov     ebx, [rbp+10D0h+var_1124]
0x1800176ce  test    ebx, ebx
0x1800176d0  jnz     loc_180017B9B
0x1800176d6  cmp     [rbp+10D0h+var_112C], 5
0x1800176da  jnz     loc_18001794C
0x1800176e0  xor     edx, edx; Val
0x1800176e2  mov     dword ptr [rsp+11D0h+Size], r13d
0x1800176e7  mov     r8d, 430h; Size
0x1800176ed  mov     [rsp+11D0h+Src], r13
0x1800176f2  lea     rcx, [rbp+10D0h+var_D90]; void *
0x1800176f9  call    memset_0
0x1800176fe  mov     rcx, [rdi+10h]
0x180017702  call    cs:__imp_RasPortConnectComplete
0x180017709  nop     dword ptr [rax+rax+00h]
0x18001770e  mov     ebx, eax
0x180017710  test    eax, eax
0x180017712  jz      short loc_18001776B
0x180017714  cmp     cs:byte_18004DF33, r13b
0x18001771b  jge     loc_18001794C
0x180017721  lea     rdx, aRasportconnect; "RasPortConnectComplete on hPort %d retu"...
0x180017728  mov     word ptr [rbp+10D0h+var_960], r13w
0x180017730  lea     rcx, [rbp+10D0h+var_960]
0x180017737  mov     r8, [rdi+10h]
0x18001773b  mov     r9d, eax
0x18001773e  call    FormatRRASErrorString
0x180017743  cmp     cs:byte_18004DF33, r13b
0x18001774a  jge     loc_18001794C
0x180017750  lea     r8, [rbp+10D0h+var_960]
0x180017757  mov     rcx, rsi
0x18001775a  lea     rdx, RasPppTraceError
0x180017761  call    McTemplateU0z_EventWriteTransfer
0x180017766  jmp     loc_18001794C
0x18001776b  mov     rcx, [rdi+10h]
0x18001776f  lea     r9, [rbp+10D0h+var_1150]
0x180017773  lea     r8, [rbp+10D0h+var_1150]
0x180017777  xor     edx, edx
0x180017779  call    cs:__imp_RasPortSetFraming
0x180017780  nop     dword ptr [rax+rax+00h]
0x180017785  mov     ebx, eax
0x180017787  test    eax, eax
0x180017789  jz      short loc_1800177A1
0x18001778b  cmp     cs:byte_18004DF33, r13b
0x180017792  jge     loc_18001794C
0x180017798  lea     rdx, aRasportsetfram; "RasPortSetFraming on hPort %d returned "...
0x18001779f  jmp     short loc_180017728
0x1800177a1  cmp     [r14+30h], r13d
0x1800177a5  jbe     loc_180017B4A
0x1800177ab  mov     r9, [r14+8]
0x1800177af  mov     r15, r13
0x1800177b2  mov     r8d, r13d
0x1800177b5  mov     edx, r13d
0x1800177b8  mov     eax, edx
0x1800177ba  mov     rcx, [r9+rax*8]
0x1800177be  test    rcx, rcx
0x1800177c1  jz      short loc_1800177DD
0x1800177c3  cmp     dword ptr [rcx+5B0h], 9
0x1800177ca  jnz     short loc_1800177DD
0x1800177cc  mov     eax, [rcx+4E8h]
0x1800177d2  cmp     eax, r8d
0x1800177d5  jb      short loc_1800177DD
0x1800177d7  mov     r15, rcx
0x1800177da  mov     r8d, eax
0x1800177dd  inc     edx
0x1800177df  cmp     edx, [r14+30h]
0x1800177e3  jb      short loc_1800177B8
0x1800177e5  test    r15, r15
0x1800177e8  jz      loc_180017B4A
0x1800177ee  lea     r13, [r15+8]
0x1800177f2  mov     rcx, [r13+0]
0x1800177f6  lea     r8, [rsp+11D0h+Src]
0x1800177fb  add     rcx, 0B8h
0x180017802  lea     rdx, [rsp+11D0h+Size]
0x180017807  call    DecodePassword
0x18001780c  mov     ebx, eax
0x18001780e  test    eax, eax
0x180017810  jz      short loc_180017845
0x180017812  xor     r13d, r13d
0x180017815  cmp     cs:byte_18004DF33, r13b
0x18001781c  jge     loc_18001794C
0x180017822  lea     rdx, aDecodepassword; "DecodePassword failed. 0x%x"
0x180017829  mov     r8d, eax
0x18001782c  lea     rcx, [rbp+10D0h+var_960]
0x180017833  mov     word ptr [rbp+10D0h+var_960], r13w
0x18001783b  call    FormatRRASErrorString
0x180017840  jmp     loc_180017743
0x180017845  mov     [rbp+10D0h+var_160], 0
0x18001784c  cmp     dword ptr [rsp+11D0h+Size], r12d
0x180017851  jbe     short loc_180017874
0x180017853  xor     r13d, r13d
0x180017856  mov     ebx, 8
0x18001785b  cmp     cs:byte_18004DF33, r13b
0x180017862  jge     loc_18001794C
0x180017868  mov     r8d, ebx
0x18001786b  lea     rdx, aNotEnoughMemor; "Not enough memory. 0x%x"
0x180017872  jmp     short loc_18001782C
0x180017874  mov     ebx, dword ptr [rsp+11D0h+Size]
0x180017878  lea     rcx, [rbp+10D0h+var_160]; void *
0x18001787f  mov     r12, [rsp+11D0h+Src]
0x180017884  mov     r8d, ebx; Size
0x180017887  mov     rdx, r12; Src
0x18001788a  call    memcpy_0
0x18001788f  mov     rax, r12
0x180017892  test    rbx, rbx
0x180017895  jz      short loc_1800178A3
0x180017897  mov     byte ptr [rax], 0
0x18001789a  inc     rax
0x18001789d  sub     rbx, 1
0x1800178a1  jnz     short loc_180017897
0x1800178a3  mov     rcx, r12; hMem
0x1800178a6  call    cs:__imp_LocalFree
0x1800178ad  nop     dword ptr [rax+rax+00h]
0x1800178b2  mov     edx, [r15+80h]
0x1800178b9  test    edx, edx
0x1800178bb  jz      loc_1800179C1
0x1800178c1  mov     rax, [r13+0]
0x1800178c5  mov     r8, [rax+58h]
0x1800178c9  mov     rcx, [rax+60h]
0x1800178cd  lea     r9, [r8+4]
0x1800178d1  mov     r8d, [r8]
0x1800178d4  lea     rax, [rcx+4]
0x1800178d8  mov     [rsp+11D0h+var_11A8], rax
0x1800178dd  mov     eax, [rcx]
0x1800178df  mov     rcx, [rdi+10h]
0x1800178e3  mov     dword ptr [rsp+11D0h+var_11B0], eax
0x1800178e7  call    cs:__imp_RasSetEapInfo
0x1800178ee  nop     dword ptr [rax+rax+00h]
0x1800178f3  mov     ebx, eax
0x1800178f5  test    eax, eax
0x1800178f7  jz      loc_1800179C1
0x1800178fd  xor     r13d, r13d
0x180017900  cmp     cs:byte_18004DF33, r13b
0x180017907  jge     short loc_180017946
0x180017909  lea     rdx, aRasseteapinfoF; "RasSetEapInfo failed. dwErr = %d"
0x180017910  mov     r8d, eax
0x180017913  mov     word ptr [rbp+10D0h+var_960], r13w
0x18001791b  lea     rcx, [rbp+10D0h+var_960]
0x180017922  call    FormatRRASErrorString
0x180017927  cmp     cs:byte_18004DF33, r13b
0x18001792e  jge     short loc_180017946
0x180017930  lea     rdx, RasPppTraceError
0x180017937  lea     r8, [rbp+10D0h+var_960]
0x18001793e  mov     rcx, rsi
0x180017941  call    McTemplateU0z_EventWriteTransfer
0x180017946  mov     r12d, 101h
0x18001794c  lea     rax, [rbp+10D0h+var_160]
0x180017953  mov     [rax], r13b
0x180017956  inc     rax
0x180017959  sub     r12, 1
0x18001795d  jnz     short loc_180017953
0x18001795f  test    r14, r14
0x180017962  jz      short loc_18001796A
0x180017964  btr     dword ptr [r14+34h], 8
0x18001796a  test    ebx, ebx
0x18001796c  jz      short loc_18001799D
0x18001796e  test    rdi, rdi
0x180017971  jz      short loc_18001799D
0x180017973  xor     edx, edx
0x180017975  mov     rcx, rdi
0x180017978  call    NotifyCallerOfFailure
0x18001797d  mov     rcx, rdi
0x180017980  call    RemovePcbFromTable
0x180017985  mov     rcx, cs:hHeap; hHeap
0x18001798c  mov     r8, rdi; lpMem
0x18001798f  xor     edx, edx; dwFlags
0x180017991  call    cs:__imp_HeapFree
0x180017998  nop     dword ptr [rax+rax+00h]
0x18001799d  mov     rcx, [rbp+10D0h+var_50]
0x1800179a4  xor     rcx, rsp; StackCookie
0x1800179a7  call    __security_check_cookie
0x1800179ac  add     rsp, 1198h
0x1800179b3  pop     r15
0x1800179b5  pop     r14
0x1800179b7  pop     r13
0x1800179b9  pop     r12
0x1800179bb  pop     rdi
0x1800179bc  pop     rsi
0x1800179bd  pop     rbx
0x1800179be  pop     rbp
0x1800179bf  retn
0x1800179c1  mov     ebx, 8
0x1800179c6  lea     rax, [r15+0B8h]
0x1800179cd  lea     rcx, [rbp+10D0h+var_D90]
0x1800179d4  lea     edx, [rbx+78h]
0x1800179d7  movups  xmm0, xmmword ptr [rax]
0x1800179da  movups  xmmword ptr [rcx], xmm0
0x1800179dd  movups  xmm1, xmmword ptr [rax+10h]
0x1800179e1  movups  xmmword ptr [rcx+10h], xmm1
0x1800179e5  movups  xmm0, xmmword ptr [rax+20h]
0x1800179e9  movups  xmmword ptr [rcx+20h], xmm0
0x1800179ed  movups  xmm1, xmmword ptr [rax+30h]
0x1800179f1  movups  xmmword ptr [rcx+30h], xmm1
0x1800179f5  movups  xmm0, xmmword ptr [rax+40h]
0x1800179f9  movups  xmmword ptr [rcx+40h], xmm0
0x1800179fd  movups  xmm1, xmmword ptr [rax+50h]
0x180017a01  movups  xmmword ptr [rcx+50h], xmm1
0x180017a05  movups  xmm0, xmmword ptr [rax+60h]
0x180017a09  movups  xmmword ptr [rcx+60h], xmm0
0x180017a0d  movups  xmm1, xmmword ptr [rax+70h]
0x180017a11  add     rax, rdx
0x180017a14  movups  xmmword ptr [rcx+70h], xmm1
0x180017a18  add     rcx, rdx
0x180017a1b  sub     rbx, 1
0x180017a1f  jnz     short loc_1800179D7
0x180017a21  movups  xmm0, xmmword ptr [rax]
0x180017a24  lea     r9, [r15+5F8h]
  ... truncated ...
```
