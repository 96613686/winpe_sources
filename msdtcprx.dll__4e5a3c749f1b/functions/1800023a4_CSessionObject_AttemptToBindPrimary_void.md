# CSessionObject::AttemptToBindPrimary(void)

- ea: `0x1800023a4`
- end: `0x180002903`
- name: `?AttemptToBindPrimary@CSessionObject@@AEAAJXZ`
- size: `1375`
- prototype: `__int64 __fastcall(CSessionObject *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180001ca4`

## callees

- `0x1800023a4`
- `0x180003cf0`
- `0x18000f674`
- `0x18001216c`
- `0x18001234c`
- `0x1800123a8`
- `0x180019908`
- `0x180027920`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002430`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180002430`
- `RPCRT4!RpcStringFreeA` at `0x1800024e3`
- `RPCRT4!RpcStringFreeA` at `0x1800024e3`
- `RPCRT4!UuidToStringA` at `0x18000247f`
- `RPCRT4!UuidToStringA` at `0x18000247f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002656`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002691`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002656`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002691`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002673`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002673`
- `msvcrt!_stricmp` at `0x180002625`
- `msvcrt!_stricmp` at `0x180002625`

## string_xrefs

- `0x180002459`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800024a6`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x1800024fb`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x18000244e`: `CSessionObject::AttemptToBindPrimary`
- `0x18000249b`: `CSessionObject::AttemptToBindPrimary`
- `0x180002502`: `CSessionObject::AttemptToBindPrimary`
- `0x1800024e9`: `STATUS : (PRIMARY)Attempting to Connect.`
- `0x180002721`: `STATUS : (PRIMARY)AttemptSucceeded.`
- `0x18000243c`: `CoCreateGuid failed. This could be due to low memory.`
- `0x18000265c`: `Primary: Received E_CM_SERVER_NOT_READY Message`
- `0x180002807`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x18000275b`: `Primary: Session Bind Failed. Protocol Not Supported`
- `0x18000277e`: `Primary: Session Bind Failed. The protocol is not supported`
- `0x180002883`: `STATUS : (PRIMARY)Attempt Failed.`

## pseudocode

```c
__int64 __fastcall CSessionObject::AttemptToBindPrimary(CSessionObject *this)
{
  unsigned int v1; // r15d
  const char *v2; // r8
  __int64 v4; // rax
  __int64 v5; // rdx
  char *v6; // rcx
  char *v7; // rax
  HRESULT v8; // ebx
  RPC_STATUS v9; // eax
  size_t *v10; // r8
  int v12; // r12d
  __int64 v13; // rax
  char *v14; // r9
  __int64 v15; // rdx
  char *v16; // rcx
  char *v17; // rax
  int v18; // eax
  DWORD TickCount; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  void *v22; // [rsp+20h] [rbp-E0h]
  char *v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+30h] [rbp-D0h]
  void *v25; // [rsp+50h] [rbp-B0h]
  RPC_CSTR StringUuid; // [rsp+60h] [rbp-A0h] BYREF
  GUID pguid; // [rsp+68h] [rbp-98h] BYREF
  char String2[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v29[264]; // [rsp+A0h] [rbp-60h] BYREF

  v1 = 0;
  v2 = "00000000-0000-0000-0000-000000000000";
  StringUuid = 0;
  v4 = 2147483646;
  pguid = 0;
  v5 = 37;
  v6 = String2;
  do
  {
    if ( !v4 )
      break;
    if ( !*v2 )
      break;
    *v6++ = *v2++;
    --v4;
    --v5;
  }
  while ( v5 );
  v7 = v6 - 1;
  if ( v5 )
    v7 = v6;
  *v7 = 0;
  v8 = CoCreateGuid(&pguid);
  if ( v8 >= 0 )
  {
    v9 = UuidToStringA(&pguid, &StringUuid);
    if ( v9 )
    {
      LODWORD(v23) = v9;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2060,
        L"CSessionObject::AttemptToBindPrimary",
        v23,
        L"UuidToString failed. This could be due to low memory.");
      return 2147942414LL;
    }
    v12 = 0;
    StringCopyWorkerA((STRSAFE_LPSTR)this + 48, 0x25u, v10, (STRSAFE_PCNZCH)StringUuid, (size_t)v22);
    RpcStringFreeA(&StringUuid);
    TraceStringInline(
      1,
      240,
      L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
      2074,
      L"CSessionObject::AttemptToBindPrimary",
      0,
      L"STATUS : (PRIMARY)Attempting to Connect.");
    while ( v1 < (unsigned int)(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 81) + 136LL) + 8LL) + 1) >> 1 )
    {
      v12 = 0;
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2093,
        L"CSessionObject::AttemptToBindPrimary",
        0,
        L"PRIMARY: Taking the following GUID with me %S",
        (char *)this + 48);
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, char *))(**((_QWORD **)this + 80) + 8LL))(
             *((_QWORD *)this + 80),
             1,
             (char *)this + 48,
             String2);
      *((_DWORD *)this + 343) = v8;
      v13 = 2147483646;
      v14 = String2;
      v15 = 37;
      v16 = (char *)this + 1376;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v16 - 1;
      if ( v15 )
        v17 = v16;
      *v17 = 0;
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2111,
        L"CSessionObject::AttemptToBindPrimary",
        0,
        L"PRIMARY: Returned with the following GUID with me %S");
      v18 = _stricmp((const char *)this + 48, String2);
      LOBYTE(v12) = v18 == 0;
      if ( !v8 && !v18 )
      {
        (***((void (__fastcall ****)(_QWORD))this + 21))(*((_QWORD *)this + 21));
        (***((void (__fastcall ****)(_QWORD))this + 20))(*((_QWORD *)this + 20));
        *((_DWORD *)this + 26) = 5;
        *((_DWORD *)this + 25) = 0;
        TraceStringInline(
          1,
          240,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
          2122,
          L"CSessionObject::AttemptToBindPrimary",
          0,
          L"STATUS : (PRIMARY)AttemptSucceeded.");
        goto LABEL_39;
      }
      if ( !*((_DWORD *)this + 2) )
        break;
      switch ( v8 )
      {
        case -2147483357:
          Sleep(0x3E8u);
          TraceStringInline(
            1,
            240,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2133,
            L"CSessionObject::AttemptToBindPrimary",
            0,
            L"Primary: Received E_CM_SERVER_NOT_READY Message");
          break;
        case -2147483391:
          TickCount = GetTickCount();
          Sleep(30 * (TickCount % 0x64));
          TraceStringInline(
            1,
            240,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2140,
            L"CSessionObject::AttemptToBindPrimary",
            0,
            L"Primary: Received E_S_UNAVAILABLE_OR_BUSY Message");
          break;
        case -2147483356:
          v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
          StringCbCopyW(v29, 0x202u, *(const unsigned __int16 **)(v20 + 8));
          v21 = -1;
          do
            ++v21;
          while ( v29[v21] );
          DELLog(0, 2u, 0xAu, 0xC0001107, 0, 0, 2 * v21 + 2, v29, "com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp", 2151, v25);
          TraceStringInline(
            1,
            2,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2153,
            L"CSessionObject::AttemptToBindPrimary",
            0,
            L"Primary: Session Bind Failed due. Primary Timed Out while waiting for the secondary to Bind");
          goto LABEL_40;
        case -2147483278:
          DtcWriteToEventLoggerA(
            4u,
            3u,
            0x4000103Cu,
            0,
            0,
            "Primary: Session Bind Failed. The Version Numbers did not match",
            v24);
          TraceStringInline(
            1,
            2,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2160,
            L"CSessionObject::AttemptToBindPrimary",
            0,
            L"Primary: Session Bind Failed. The Version Numbers did not match");
          goto LABEL_40;
        case -2147483277:
          DtcWriteToEventLoggerA(4u, 3u, 0x4000103Cu, 0, 0, "Primary: Session Bind Failed. Protocol Not Supported", v24);
          TraceStringInline(
            1,
            2,
            L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
            2167,
            L"CSessionObject::AttemptToBindPrimary",
            0,
            L"Primary: Session Bind Failed. The protocol is not supported");
          goto LABEL_40;
      }
      ++v1;
    }
    if ( v8 )
      goto LABEL_40;
LABEL_39:
    if ( v12 == 1 )
      goto LABEL_42;
LABEL_40:
    TraceStringInline(
      1,
      240,
      L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
      2175,
      L"CSessionObject::AttemptToBindPrimary",
      0,
      L"STATUS : (PRIMARY)Attempt Failed.");
    CSessionObject::SetStatus(this, 1);
    if ( *((_DWORD *)this + 26) == 2 )
      CSessionObject::SetState(this, 4);
LABEL_42:
    *((_DWORD *)this + 4) = 0;
  }
  else
  {
    LODWORD(v23) = v8;
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
      2052,
      L"CSessionObject::AttemptToBindPrimary",
      v23,
      L"CoCreateGuid failed. This could be due to low memory.");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800023a4  push    rbp
0x1800023a6  push    rbx
0x1800023a7  push    rsi
0x1800023a8  push    rdi
0x1800023a9  push    r12
0x1800023ab  push    r13
0x1800023ad  push    r14
0x1800023af  push    r15
0x1800023b1  lea     rbp, [rsp-1C8h]
0x1800023b9  sub     rsp, 2C8h
0x1800023c0  mov     rax, cs:__security_cookie
0x1800023c7  xor     rax, rsp
0x1800023ca  mov     [rbp+200h+var_50], rax
0x1800023d1  xor     r15d, r15d
0x1800023d4  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x1800023db  xorps   xmm0, xmm0
0x1800023de  mov     [rsp+300h+StringUuid], r15
0x1800023e3  mov     r14, rcx
0x1800023e6  mov     eax, 7FFFFFFEh
0x1800023eb  movups  xmmword ptr [rsp+300h+pguid.Data1], xmm0
0x1800023f0  lea     edi, [r15+25h]
0x1800023f4  mov     edx, edi
0x1800023f6  lea     rcx, [rsp+300h+String2]
0x1800023fb  lea     r12d, [r15+1]
0x1800023ff  test    rax, rax
0x180002402  jz      short loc_18000241D
0x180002404  mov     r9b, [r8]
0x180002407  test    r9b, r9b
0x18000240a  jz      short loc_18000241D
0x18000240c  mov     [rcx], r9b
0x18000240f  add     r8, r12
0x180002412  add     rcx, r12
0x180002415  sub     rax, r12
0x180002418  sub     rdx, r12
0x18000241b  jnz     short loc_1800023FF
0x18000241d  lea     rax, [rcx-1]
0x180002421  test    rdx, rdx
0x180002424  cmovnz  rax, rcx
0x180002428  lea     rcx, [rsp+300h+pguid]; pguid
0x18000242d  mov     [rax], r15b
0x180002430  call    cs:__imp_CoCreateGuid
0x180002436  mov     ebx, eax
0x180002438  test    eax, eax
0x18000243a  jns     short loc_180002475
0x18000243c  lea     rax, aCocreateguidFa; "CoCreateGuid failed. This could be due "...
0x180002443  mov     r9d, 804h
0x180002449  mov     qword ptr [rsp+300h+var_2D0], rax
0x18000244e  lea     rsi, aCsessionobject; "CSessionObject::AttemptToBindPrimary"
0x180002455  mov     dword ptr [rsp+300h+var_2D8], ebx
0x180002459  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002460  mov     edx, r12d
0x180002463  mov     [rsp+300h+var_2E0], rsi
0x180002468  mov     ecx, r12d
0x18000246b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002470  jmp     loc_1800028DE
0x180002475  lea     rdx, [rsp+300h+StringUuid]; StringUuid
0x18000247a  lea     rcx, [rsp+300h+pguid]; Uuid
0x18000247f  call    cs:__imp_UuidToStringA
0x180002485  test    eax, eax
0x180002487  jz      short loc_1800024C7
0x180002489  lea     rcx, aUuidtostringFa; "UuidToString failed. This could be due "...
0x180002490  mov     r9d, 80Ch
0x180002496  mov     qword ptr [rsp+300h+var_2D0], rcx
0x18000249b  lea     rsi, aCsessionobject; "CSessionObject::AttemptToBindPrimary"
0x1800024a2  mov     dword ptr [rsp+300h+var_2D8], eax
0x1800024a6  lea     r8, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x1800024ad  mov     ecx, r12d
0x1800024b0  mov     [rsp+300h+var_2E0], rsi
0x1800024b5  mov     edx, r12d
0x1800024b8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800024bd  mov     eax, 8007000Eh
0x1800024c2  jmp     loc_1800028E0
0x1800024c7  mov     r9, [rsp+300h+StringUuid]; pszSrc
0x1800024cc  lea     r13, [r14+30h]
0x1800024d0  mov     rcx, r13; pszDest
0x1800024d3  mov     rdx, rdi; cchDest
0x1800024d6  mov     r12d, r15d
0x1800024d9  call    StringCopyWorkerA
0x1800024de  lea     rcx, [rsp+300h+StringUuid]; String
0x1800024e3  call    cs:__imp_RpcStringFreeA
0x1800024e9  lea     rax, aStatusPrimaryA_0; "STATUS : (PRIMARY)Attempting to Connect"...
0x1800024f0  mov     r9d, 81Ah
0x1800024f6  mov     qword ptr [rsp+300h+var_2D0], rax
0x1800024fb  lea     rdi, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180002502  lea     rsi, aCsessionobject; "CSessionObject::AttemptToBindPrimary"
0x180002509  mov     [rsp+300h+var_2D8], r15
0x18000250e  mov     r8, rdi
0x180002511  mov     [rsp+300h+var_2E0], rsi
0x180002516  mov     edx, 0F0h
0x18000251b  mov     ecx, 1
0x180002520  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002525  mov     rax, [r14+288h]
0x18000252c  mov     rcx, [rax+88h]
0x180002533  mov     eax, [rcx+8]
0x180002536  inc     eax
0x180002538  shr     eax, 1
0x18000253a  cmp     r15d, eax
0x18000253d  jnb     loc_180002879
0x180002543  mov     [rsp+300h+var_2C8], r13
0x180002548  lea     rax, aPrimaryTakingT; "PRIMARY: Taking the following GUID with"...
0x18000254f  mov     qword ptr [rsp+300h+var_2D0], rax
0x180002554  xor     r12d, r12d
0x180002557  mov     [rsp+300h+var_2D8], r12
0x18000255c  mov     r9d, 82Dh
0x180002562  mov     r8, rdi
0x180002565  mov     [rsp+300h+var_2E0], rsi
0x18000256a  mov     edx, 0F0h
0x18000256f  lea     ecx, [r12+1]
0x180002574  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002579  mov     rcx, [r14+280h]
0x180002580  lea     r9, [rsp+300h+String2]
0x180002585  mov     r8, r13
0x180002588  lea     edx, [r12+1]
0x18000258d  mov     rax, [rcx]
0x180002590  mov     rax, [rax+8]
0x180002594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002599  mov     ebx, eax
0x18000259b  mov     [r14+55Ch], eax
0x1800025a2  mov     eax, 7FFFFFFEh
0x1800025a7  lea     r9, [rsp+300h+String2]
0x1800025ac  lea     edx, [r12+25h]
0x1800025b1  lea     rcx, [r14+560h]
0x1800025b8  test    rax, rax
0x1800025bb  jz      short loc_1800025D7
0x1800025bd  mov     r8b, [r9]
0x1800025c0  test    r8b, r8b
0x1800025c3  jz      short loc_1800025D7
0x1800025c5  mov     [rcx], r8b
0x1800025c8  inc     r9
0x1800025cb  inc     rcx
0x1800025ce  dec     rax
0x1800025d1  sub     rdx, 1
0x1800025d5  jnz     short loc_1800025B8
0x1800025d7  test    rdx, rdx
0x1800025da  lea     rax, [rcx-1]
0x1800025de  mov     r9d, 83Fh
0x1800025e4  mov     r8, rdi
0x1800025e7  cmovnz  rax, rcx
0x1800025eb  mov     edx, 0F0h
0x1800025f0  mov     ecx, 1
0x1800025f5  mov     [rax], r12b
0x1800025f8  lea     rax, [rsp+300h+String2]
0x1800025fd  mov     [rsp+300h+var_2C8], rax
0x180002602  lea     rax, aPrimaryReturne; "PRIMARY: Returned with the following GU"...
0x180002609  mov     qword ptr [rsp+300h+var_2D0], rax; int
0x18000260e  mov     [rsp+300h+var_2D8], r12
0x180002613  mov     [rsp+300h+var_2E0], rsi
0x180002618  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000261d  lea     rdx, [rsp+300h+String2]; String2
0x180002622  mov     rcx, r13; String1
0x180002625  call    cs:__imp__stricmp
0x18000262b  xor     ecx, ecx
0x18000262d  test    eax, eax
0x18000262f  setz    r12b
0x180002633  test    ebx, ebx
0x180002635  jnz     short loc_18000263F
0x180002637  test    eax, eax
0x180002639  jz      loc_1800026F3
0x18000263f  cmp     [r14+8], ecx
0x180002643  jz      loc_180002879
0x180002649  cmp     ebx, 80000123h
0x18000264f  jnz     short loc_18000266B
0x180002651  mov     ecx, 3E8h; dwMilliseconds
0x180002656  call    cs:__imp_Sleep
0x18000265c  lea     rax, aPrimaryReceive_0; "Primary: Received E_CM_SERVER_NOT_READY"...
0x180002663  mov     r9d, 855h
0x180002669  jmp     short loc_1800026A4
0x18000266b  cmp     ebx, 80000101h
0x180002671  jnz     short loc_1800026CB
0x180002673  call    cs:__imp_GetTickCount
0x180002679  mov     r8d, eax
0x18000267c  mov     eax, 51EB851Fh
0x180002681  mul     r8d
0x180002684  shr     edx, 5
0x180002687  imul    ecx, edx, 64h ; 'd'
0x18000268a  sub     r8d, ecx
0x18000268d  imul    ecx, r8d, 1Eh; dwMilliseconds
0x180002691  call    cs:__imp_Sleep
0x180002697  lea     rax, aPrimaryReceive; "Primary: Received E_S_UNAVAILABLE_OR_BU"...
0x18000269e  mov     r9d, 85Ch
0x1800026a4  mov     qword ptr [rsp+300h+var_2D0], rax
0x1800026a9  mov     r8, rdi
0x1800026ac  mov     [rsp+300h+var_2D8], 0
0x1800026b5  mov     edx, 0F0h
0x1800026ba  mov     ecx, 1
0x1800026bf  mov     [rsp+300h+var_2E0], rsi
0x1800026c4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800026c9  jmp     short loc_1800026EB
0x1800026cb  cmp     ebx, 80000124h
0x1800026d1  jz      loc_1800027C8
0x1800026d7  cmp     ebx, 80000172h
0x1800026dd  jz      loc_180002790
0x1800026e3  cmp     ebx, 80000173h
0x1800026e9  jz      short loc_180002758
0x1800026eb  inc     r15d
0x1800026ee  jmp     loc_180002525
0x1800026f3  mov     rcx, [r14+0A8h]
0x1800026fa  mov     rax, [rcx]
0x1800026fd  mov     rax, [rax]
0x180002700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002705  mov     rcx, [r14+0A0h]
0x18000270c  mov     rax, [rcx]
0x18000270f  mov     rax, [rax]
0x180002712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002717  xor     ecx, ecx
0x180002719  mov     dword ptr [r14+68h], 5
0x180002721  lea     rax, aStatusPrimaryA_1; "STATUS : (PRIMARY)AttemptSucceeded."
0x180002728  mov     [r14+64h], ecx
0x18000272c  mov     qword ptr [rsp+300h+var_2D0], rax
0x180002731  mov     r9d, 84Ah
0x180002737  mov     [rsp+300h+var_2D8], rcx
0x18000273c  mov     r8, rdi
0x18000273f  mov     ecx, 1
0x180002744  mov     [rsp+300h+var_2E0], rsi
0x180002749  mov     edx, 0F0h
0x18000274e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002753  jmp     loc_18000287D
0x180002758  xor     r9d, r9d; unsigned int
0x18000275b  lea     rax, aPrimarySession_3; "Primary: Session Bind Failed. Protocol "...
0x180002762  mov     [rsp+300h+var_2D8], rax; char *
0x180002767  mov     r8d, 4000103Ch; unsigned int
0x18000276d  mov     [rsp+300h+var_2E0], rcx; void *
0x180002772  lea     edx, [r9+3]; unsigned int
0x180002776  lea     ecx, [rdx+1]; unsigned int
0x180002779  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18000277e  lea     rax, aPrimarySession_1; "Primary: Session Bind Failed. The proto"...
0x180002785  mov     r9d, 877h
0x18000278b  jmp     loc_180002854
0x180002790  xor     r9d, r9d; unsigned int
0x180002793  lea     rax, aPrimarySession; "Primary: Session Bind Failed. The Versi"...
0x18000279a  mov     [rsp+300h+var_2D8], rax; char *
0x18000279f  mov     r8d, 4000103Ch; unsigned int
0x1800027a5  mov     [rsp+300h+var_2E0], rcx; void *
0x1800027aa  lea     edx, [r9+3]; unsigned int
0x1800027ae  lea     ecx, [rdx+1]; unsigned int
0x1800027b1  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x1800027b6  lea     rax, aPrimarySession_0; "Primary: Session Bind Failed. The Versi"...
0x1800027bd  mov     r9d, 870h
0x1800027c3  jmp     loc_180002854
0x1800027c8  mov     rcx, [r14+58h]
0x1800027cc  mov     rax, [rcx]
0x1800027cf  mov     rax, [rax+18h]
0x1800027d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d8  mov     edx, 202h; unsigned __int64
0x1800027dd  lea     rcx, [rbp+200h+var_260]; unsigned __int16 *
0x1800027e1  mov     r8, [rax+8]; unsigned __int16 *
0x1800027e5  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800027ea  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800027ee  lea     r11, [rbp+200h+var_260]
0x1800027f2  xor     r9d, r9d
0x1800027f5  inc     rax
0x1800027f8  cmp     [r11+rax*2], r9w
0x1800027fd  jnz     short loc_1800027F5
0x1800027ff  mov     [rsp+300h+var_2B8], 867h; int
0x180002807  lea     rcx, aComComplusDtcD_4; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x18000280e  mov     [rsp+300h+var_2C0], rcx; char *
0x180002813  lea     eax, ds:2[rax*2]
0x18000281a  lea     rcx, [rbp+200h+var_260]
0x18000281e  mov     edx, 2; unsigned __int16
0x180002823  mov     [rsp+300h+var_2C8], rcx; void *
0x180002828  xor     ecx, ecx; struct ITmInstance *
0x18000282a  mov     [rsp+300h+var_2D0], eax; unsigned int
0x18000282e  mov     dword ptr [rsp+300h+var_2D8], r9d; int
0x180002833  mov     dword ptr [rsp+300h+var_2E0], r9d; int
0x180002838  lea     r8d, [rdx+8]; unsigned __int16
0x18000283c  mov     r9d, 0C0001107h; unsigned int
0x180002842  call    ?DELLog@@YAXPEAUITmInstance@@GGKJHKPEAXPEADH1@Z; DELLog(ITmInstance *,ushort,ushort,ulong,long,int,ulong,void *,char *,int,void *)
0x180002847  lea     rax, aPrimarySession_2; "Primary: Session Bind Failed due. Prima"...
0x18000284e  mov     r9d, 869h
0x180002854  mov     qword ptr [rsp+300h+var_2D0], rax
0x180002859  mov     edx, 2
0x18000285e  mov     [rsp+300h+var_2D8], 0
0x180002867  mov     r8, rdi
0x18000286a  mov     [rsp+300h+var_2E0], rsi
0x18000286f  lea     ecx, [rdx-1]
0x180002872  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180002877  jmp     short loc_180002883
0x180002879  test    ebx, ebx
0x18000287b  jnz     short loc_180002883
0x18000287d  cmp     r12d, 1
0x180002881  jz      short loc_1800028D6
0x180002883  lea     rax, aStatusPrimaryA; "STATUS : (PRIMARY)Attempt Failed."
0x18000288a  mov     r9d, 87Fh
0x180002890  mov     qword ptr [rsp+300h+var_2D0], rax
0x180002895  mov     r8, rdi
0x180002898  mov     [rsp+300h+var_2D8], 0
0x1800028a1  mov     edx, 0F0h
0x1800028a6  mov     ecx, 1
0x1800028ab  mov     [rsp+300h+var_2E0], rsi
0x1800028b0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800028b5  mov     edx, 1
0x1800028ba  mov     rcx, r14
0x1800028bd  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x1800028c2  cmp     dword ptr [r14+68h], 2
0x1800028c7  jnz     short loc_1800028D6
0x1800028c9  mov     edx, 4
0x1800028ce  mov     rcx, r14
0x1800028d1  call    ?SetState@CSessionObject@@QEAAXW4_SessionState@@@Z; CSessionObject::SetState(_SessionState)
0x1800028d6  mov     dword ptr [r14+10h], 0
0x1800028de  mov     eax, ebx
  ... truncated ...
```
