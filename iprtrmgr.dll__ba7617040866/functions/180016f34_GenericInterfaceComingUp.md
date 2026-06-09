# GenericInterfaceComingUp

- ea: `0x180016f34`
- end: `0x180017395`
- name: `GenericInterfaceComingUp`
- size: `1121`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001a110`
- `0x18001c814`

## callees

- `0x180011790`
- `0x180015550`
- `0x180016f34`
- `0x180036574`
- `0x18003a220`
- `0x18003b100`
- `0x18003e450`
- `0x18004d8d0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180017127`
- `WS2_32!__imp_WSAGetLastError` at `0x180017127`

## string_xrefs

- `0x180016fdb`: `Entered: GenericInterfaceComingUp`
- `0x18001701d`: `GenericInterfaceComingUp: %ws coming UP`
- `0x180017092`: `CreateSockets: Joining ALL_ROUTERS on %ws`
- `0x180017130`: `GenericInterfaceComingUp: Error %d joining all-routers group on %ws`
- `0x1800171a0`: `GenericInterfaceComingUp: Error %d activating router discovery on %ws`
- `0x18001721c`: `GenericInterfaceComingUp: Error %d activating router discovery on %ws`
- `0x1800172ff`: `GenericInterfaceComingUp: Error %d binding %ws for %hs info`

## pseudocode

```c
__int64 __fastcall GenericInterfaceComingUp(__int64 a1)
{
  int v1; // esi
  __int64 *v2; // r14
  unsigned int v4; // r15d
  char v5; // al
  __int128 *v6; // r9
  __int64 v7; // r8
  __int128 *v8; // r9
  __int64 v9; // r8
  __int128 *v10; // r9
  __int64 v11; // rbx
  unsigned int Error; // eax
  __int128 *v13; // r9
  unsigned int v14; // eax
  __int64 v15; // r9
  __int128 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // r9
  __int128 *v19; // r9
  unsigned int i; // ebx
  __int64 j; // rbx
  __int64 (__fastcall *v22)(__int64); // rax
  unsigned int v23; // eax
  __int64 v24; // r9
  __int128 *v25; // r9
  __int128 v27; // [rsp+38h] [rbp-880h] BYREF
  int v28; // [rsp+48h] [rbp-870h] BYREF
  __int128 v29; // [rsp+4Ch] [rbp-86Ch]
  __int128 v30; // [rsp+5Ch] [rbp-85Ch]
  int v31; // [rsp+6Ch] [rbp-84Ch]
  int v32; // [rsp+70h] [rbp-848h] BYREF
  _BYTE v33[2044]; // [rsp+74h] [rbp-844h] BYREF

  v1 = *(_DWORD *)(a1 + 516);
  v2 = &g_rgicInfoCbv4;
  if ( v1 != 1 )
    v2 = &g_rgicInfoCbv6;
  v4 = 5;
  if ( v1 != 1 )
    v4 = 3;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v31 = 0;
  v5 = Microsoft_Windows_RRASEnableBits;
  v29 = 0;
  v30 = 0;
  v27 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v6 = &v27;
    LOWORD(v28) = 0;
    if ( a1 != -688 )
      LODWORD(v6) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: GenericInterfaceComingUp",
      (_DWORD)v6,
      *(_QWORD *)(a1 + 72),
      (__int64)&v28);
    v5 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v5 < 0 )
  {
    v7 = *(_QWORD *)(a1 + 72);
    LOWORD(v32) = 0;
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v32, L"GenericInterfaceComingUp: %ws coming UP", v7);
    v5 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v8 = &v27;
      if ( a1 != -688 )
        LODWORD(v8) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v32,
        (_DWORD)v8,
        *(_QWORD *)(a1 + 72),
        (__int64)&v28);
      v5 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v1 )
  {
    if ( v5 < 0 )
    {
      v9 = *(_QWORD *)(a1 + 72);
      LOWORD(v32) = 0;
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v32, L"CreateSockets: Joining ALL_ROUTERS on %ws", v9);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v10 = &v27;
        if ( a1 != -688 )
          LODWORD(v10) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v32,
          (_DWORD)v10,
          *(_QWORD *)(a1 + 72),
          (__int64)&v28);
      }
    }
    if ( (unsigned int)McJoinGroupByIndex(McMiscSocket) == -1 && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v11 = *(_QWORD *)(a1 + 72);
      LOWORD(v32) = 0;
      LOWORD(v28) = 0;
      Error = WSAGetLastError();
      FormatRRASErrorString(&v32, L"GenericInterfaceComingUp: Error %d joining all-routers group on %ws", Error, v11);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v13 = &v27;
        if ( a1 != -688 )
          LODWORD(v13) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v32,
          (_DWORD)v13,
          *(_QWORD *)(a1 + 72),
          (__int64)&v28);
      }
    }
    v14 = ActivateRouterDiscovery(a1);
    if ( v14 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = *(_QWORD *)(a1 + 72);
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v32, L"GenericInterfaceComingUp: Error %d activating router discovery on %ws", v14, v15);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v16 = &v27;
          if ( a1 != -688 )
            LODWORD(v16) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v32,
            (_DWORD)v16,
            *(_QWORD *)(a1 + 72),
            (__int64)&v28);
        }
      }
    }
    v17 = ActivateMHeartbeat(a1);
    if ( v17 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v18 = *(_QWORD *)(a1 + 72);
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v32, L"GenericInterfaceComingUp: Error %d activating router discovery on %ws", v17, v18);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v19 = &v27;
          if ( a1 != -688 )
            LODWORD(v19) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v32,
            (_DWORD)v19,
            *(_QWORD *)(a1 + 72),
            (__int64)&v28);
        }
      }
    }
    for ( i = 0; i < *(_DWORD *)(a1 + 668); ++i )
      ;
  }
  BindInterfaceInAllProtocols(a1);
  if ( v1 )
    ActivateMcastLimits(a1);
  for ( j = 0; (unsigned int)j < v4; j = (unsigned int)(j + 1) )
  {
    v22 = (__int64 (__fastcall *)(__int64))v2[5 * j + 3];
    if ( v22 )
    {
      v23 = v22(a1);
      if ( v23 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v24 = *(_QWORD *)(a1 + 72);
          LOWORD(v32) = 0;
          LOWORD(v28) = 0;
          FormatRRASErrorString(
            &v32,
            L"GenericInterfaceComingUp: Error %d binding %ws for %hs info",
            v23,
            v24,
            v2[5 * j]);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v25 = &v27;
            if ( a1 != -688 )
              LODWORD(v25) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v32,
              (_DWORD)v25,
              *(_QWORD *)(a1 + 72),
              (__int64)&v28);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016f34  push    rbx
0x180016f36  push    rsi
0x180016f37  push    rdi
0x180016f38  push    r13
0x180016f3a  push    r14
0x180016f3c  push    r15
0x180016f3e  sub     rsp, 888h
0x180016f45  mov     rax, cs:__security_cookie
0x180016f4c  xor     rax, rsp
0x180016f4f  mov     [rsp+8B8h+var_48], rax
0x180016f57  mov     esi, [rcx+204h]
0x180016f5d  lea     rax, g_rgicInfoCbv6
0x180016f64  cmp     esi, 1
0x180016f67  lea     r14, g_rgicInfoCbv4
0x180016f6e  mov     rdi, rcx
0x180016f71  mov     r8d, 7FCh; Size
0x180016f77  cmovnz  r14, rax
0x180016f7b  lea     rcx, [rsp+8B8h+var_844]; void *
0x180016f80  mov     eax, 3
0x180016f85  lea     r15d, [rax+2]
0x180016f89  cmovnz  r15d, eax
0x180016f8d  xor     eax, eax
0x180016f8f  xor     edx, edx; Val
0x180016f91  mov     [rsp+8B8h+var_848], eax
0x180016f95  call    memset_0
0x180016f9a  xor     eax, eax
0x180016f9c  lea     rbx, RasRtrmgrParamTraceInfo
0x180016fa3  xorps   xmm0, xmm0
0x180016fa6  mov     [rsp+8B8h+var_870], eax
0x180016faa  mov     [rsp+8B8h+var_84C], eax
0x180016fae  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016fb5  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180016fbc  movups  [rsp+8B8h+var_86C], xmm0
0x180016fc1  movups  [rsp+8B8h+var_85C], xmm0
0x180016fc6  movups  [rsp+8B8h+var_880], xmm0
0x180016fcb  test    al, 80h
0x180016fcd  jz      short loc_180017015
0x180016fcf  xor     eax, eax
0x180016fd1  lea     r9, [rsp+8B8h+var_880]
0x180016fd6  mov     word ptr [rsp+8B8h+var_870], ax
0x180016fdb  lea     r8, aEnteredGeneric_0; "Entered: GenericInterfaceComingUp"
0x180016fe2  lea     rax, [rdi+2B0h]
0x180016fe9  mov     rdx, rbx
0x180016fec  test    rax, rax
0x180016fef  mov     rcx, r13
0x180016ff2  cmovnz  r9, rax
0x180016ff6  lea     rax, [rsp+8B8h+var_870]
0x180016ffb  mov     [rsp+8B8h+var_890], rax
0x180017000  mov     rax, [rdi+48h]
0x180017004  mov     [rsp+8B8h+var_898], rax
0x180017009  call    McTemplateU0zjzz_EventWriteTransfer
0x18001700e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180017015  test    al, al
0x180017017  jns     short loc_180017082
0x180017019  mov     r8, [rdi+48h]
0x18001701d  lea     rdx, aGenericinterfa_3; "GenericInterfaceComingUp: %ws coming UP"
0x180017024  xor     eax, eax
0x180017026  lea     rcx, [rsp+8B8h+var_848]
0x18001702b  mov     word ptr [rsp+8B8h+var_848], ax
0x180017030  mov     word ptr [rsp+8B8h+var_870], ax
0x180017035  call    FormatRRASErrorString
0x18001703a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180017041  test    al, al
0x180017043  jns     short loc_180017082
0x180017045  lea     rax, [rdi+2B0h]
0x18001704c  mov     rdx, rbx
0x18001704f  test    rax, rax
0x180017052  lea     r9, [rsp+8B8h+var_880]
0x180017057  lea     r8, [rsp+8B8h+var_848]
0x18001705c  mov     rcx, r13
0x18001705f  cmovnz  r9, rax
0x180017063  lea     rax, [rsp+8B8h+var_870]
0x180017068  mov     [rsp+8B8h+var_890], rax
0x18001706d  mov     rax, [rdi+48h]
0x180017071  mov     [rsp+8B8h+var_898], rax
0x180017076  call    McTemplateU0zjzz_EventWriteTransfer
0x18001707b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180017082  test    esi, esi
0x180017084  jz      loc_1800172B5
0x18001708a  test    al, al
0x18001708c  jns     short loc_1800170EE
0x18001708e  mov     r8, [rdi+48h]
0x180017092  lea     rdx, aCreatesocketsJ_0; "CreateSockets: Joining ALL_ROUTERS on %"...
0x180017099  xor     eax, eax
0x18001709b  lea     rcx, [rsp+8B8h+var_848]
0x1800170a0  mov     word ptr [rsp+8B8h+var_848], ax
0x1800170a5  mov     word ptr [rsp+8B8h+var_870], ax
0x1800170aa  call    FormatRRASErrorString
0x1800170af  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800170b6  jge     short loc_1800170EE
0x1800170b8  lea     rax, [rdi+2B0h]
0x1800170bf  mov     rdx, rbx
0x1800170c2  test    rax, rax
0x1800170c5  lea     r9, [rsp+8B8h+var_880]
0x1800170ca  lea     r8, [rsp+8B8h+var_848]
0x1800170cf  mov     rcx, r13
0x1800170d2  cmovnz  r9, rax
0x1800170d6  lea     rax, [rsp+8B8h+var_870]
0x1800170db  mov     [rsp+8B8h+var_890], rax
0x1800170e0  mov     rax, [rdi+48h]
0x1800170e4  mov     [rsp+8B8h+var_898], rax
0x1800170e9  call    McTemplateU0zjzz_EventWriteTransfer
0x1800170ee  mov     r9d, [rdi+10h]
0x1800170f2  mov     edx, 3
0x1800170f7  mov     rcx, cs:McMiscSocket; s
0x1800170fe  mov     r8d, 20000E0h
0x180017104  call    McJoinGroupByIndex
0x180017109  cmp     eax, 0FFFFFFFFh
0x18001710c  jnz     short loc_180017187
0x18001710e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180017115  jz      short loc_180017187
0x180017117  mov     rbx, [rdi+48h]
0x18001711b  xor     eax, eax
0x18001711d  mov     word ptr [rsp+8B8h+var_848], ax
0x180017122  mov     word ptr [rsp+8B8h+var_870], ax
0x180017127  call    cs:__imp_WSAGetLastError
0x18001712d  mov     r9, rbx
0x180017130  lea     rdx, aGenericinterfa_2; "GenericInterfaceComingUp: Error %d join"...
0x180017137  mov     r8d, eax
0x18001713a  lea     rcx, [rsp+8B8h+var_848]
0x18001713f  call    FormatRRASErrorString
0x180017144  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001714b  jz      short loc_180017187
0x18001714d  lea     rax, [rdi+2B0h]
0x180017154  mov     rcx, r13
0x180017157  test    rax, rax
0x18001715a  lea     r9, [rsp+8B8h+var_880]
0x18001715f  lea     r8, [rsp+8B8h+var_848]
0x180017164  cmovnz  r9, rax
0x180017168  lea     rdx, RasRtrMgrParamTraceError
0x18001716f  lea     rax, [rsp+8B8h+var_870]
0x180017174  mov     [rsp+8B8h+var_890], rax
0x180017179  mov     rax, [rdi+48h]
0x18001717d  mov     [rsp+8B8h+var_898], rax
0x180017182  call    McTemplateU0zjzz_EventWriteTransfer
0x180017187  mov     rcx, rdi
0x18001718a  call    ActivateRouterDiscovery
0x18001718f  test    eax, eax
0x180017191  jz      short loc_180017203
0x180017193  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001719a  jz      short loc_180017203
0x18001719c  mov     r9, [rdi+48h]
0x1800171a0  lea     rdx, aGenericinterfa_5; "GenericInterfaceComingUp: Error %d acti"...
0x1800171a7  xor     ecx, ecx
0x1800171a9  mov     r8d, eax
0x1800171ac  mov     word ptr [rsp+8B8h+var_848], cx
0x1800171b1  mov     word ptr [rsp+8B8h+var_870], cx
0x1800171b6  lea     rcx, [rsp+8B8h+var_848]
0x1800171bb  call    FormatRRASErrorString
0x1800171c0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800171c7  jz      short loc_180017203
0x1800171c9  lea     rax, [rdi+2B0h]
0x1800171d0  mov     rcx, r13
0x1800171d3  test    rax, rax
0x1800171d6  lea     r9, [rsp+8B8h+var_880]
0x1800171db  lea     r8, [rsp+8B8h+var_848]
0x1800171e0  cmovnz  r9, rax
0x1800171e4  lea     rdx, RasRtrMgrParamTraceError
0x1800171eb  lea     rax, [rsp+8B8h+var_870]
0x1800171f0  mov     [rsp+8B8h+var_890], rax
0x1800171f5  mov     rax, [rdi+48h]
0x1800171f9  mov     [rsp+8B8h+var_898], rax
0x1800171fe  call    McTemplateU0zjzz_EventWriteTransfer
0x180017203  mov     rcx, rdi
0x180017206  call    ActivateMHeartbeat
0x18001720b  test    eax, eax
0x18001720d  jz      short loc_18001727F
0x18001720f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180017216  jz      short loc_18001727F
0x180017218  mov     r9, [rdi+48h]
0x18001721c  lea     rdx, aGenericinterfa_5; "GenericInterfaceComingUp: Error %d acti"...
0x180017223  xor     ecx, ecx
0x180017225  mov     r8d, eax
0x180017228  mov     word ptr [rsp+8B8h+var_848], cx
0x18001722d  mov     word ptr [rsp+8B8h+var_870], cx
0x180017232  lea     rcx, [rsp+8B8h+var_848]
0x180017237  call    FormatRRASErrorString
0x18001723c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180017243  jz      short loc_18001727F
0x180017245  lea     rax, [rdi+2B0h]
0x18001724c  mov     rcx, r13
0x18001724f  test    rax, rax
0x180017252  lea     r9, [rsp+8B8h+var_880]
0x180017257  lea     r8, [rsp+8B8h+var_848]
0x18001725c  cmovnz  r9, rax
0x180017260  lea     rdx, RasRtrMgrParamTraceError
0x180017267  lea     rax, [rsp+8B8h+var_870]
0x18001726c  mov     [rsp+8B8h+var_890], rax
0x180017271  mov     rax, [rdi+48h]
0x180017275  mov     [rsp+8B8h+var_898], rax
0x18001727a  call    McTemplateU0zjzz_EventWriteTransfer
0x18001727f  xor     ebx, ebx
0x180017281  cmp     [rdi+29Ch], ebx
0x180017287  jbe     short loc_1800172B5
0x180017289  mov     eax, ebx
0x18001728b  imul    r8, rax, 1Ch
0x18001728f  mov     rax, [rdi+2C8h]
0x180017296  mov     edx, [r8+rax]
0x18001729a  test    edx, edx
0x18001729c  jz      short loc_1800172AB
0x18001729e  mov     r8d, [r8+rax+4]
0x1800172a3  mov     rcx, rdi
0x1800172a6  call    _guard_check_icall_nop
0x1800172ab  inc     ebx
0x1800172ad  cmp     ebx, [rdi+29Ch]
0x1800172b3  jb      short loc_180017289
0x1800172b5  mov     rcx, rdi
0x1800172b8  call    BindInterfaceInAllProtocols
0x1800172bd  test    esi, esi
0x1800172bf  jz      short loc_1800172C9
0x1800172c1  mov     rcx, rdi
0x1800172c4  call    ActivateMcastLimits
0x1800172c9  xor     ebx, ebx
0x1800172cb  cmp     ebx, r15d
0x1800172ce  jnb     loc_180017372
0x1800172d4  lea     rsi, [rbx+rbx*4]
0x1800172d8  mov     rax, [r14+rsi*8+18h]
0x1800172dd  test    rax, rax
0x1800172e0  jz      loc_18001736B
0x1800172e6  mov     rcx, rdi
0x1800172e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ee  test    eax, eax
0x1800172f0  jz      short loc_18001736B
0x1800172f2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800172f9  jz      short loc_18001736B
0x1800172fb  mov     r9, [rdi+48h]
0x1800172ff  lea     rdx, aGenericinterfa_4; "GenericInterfaceComingUp: Error %d bind"...
0x180017306  xor     ecx, ecx
0x180017308  mov     r8d, eax
0x18001730b  mov     word ptr [rsp+8B8h+var_848], cx
0x180017310  mov     word ptr [rsp+8B8h+var_870], cx
0x180017315  mov     rcx, [r14+rsi*8]
0x180017319  mov     [rsp+8B8h+var_898], rcx
0x18001731e  lea     rcx, [rsp+8B8h+var_848]
0x180017323  call    FormatRRASErrorString
0x180017328  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001732f  jz      short loc_18001736B
0x180017331  lea     rax, [rdi+2B0h]
0x180017338  mov     rcx, r13
0x18001733b  test    rax, rax
0x18001733e  lea     r9, [rsp+8B8h+var_880]
0x180017343  lea     r8, [rsp+8B8h+var_848]
0x180017348  cmovnz  r9, rax
0x18001734c  lea     rdx, RasRtrMgrParamTraceError
0x180017353  lea     rax, [rsp+8B8h+var_870]
0x180017358  mov     [rsp+8B8h+var_890], rax
0x18001735d  mov     rax, [rdi+48h]
0x180017361  mov     [rsp+8B8h+var_898], rax
0x180017366  call    McTemplateU0zjzz_EventWriteTransfer
0x18001736b  inc     ebx
0x18001736d  jmp     loc_1800172CB
0x180017372  xor     eax, eax
0x180017374  mov     rcx, [rsp+8B8h+var_48]
0x18001737c  xor     rcx, rsp; StackCookie
0x18001737f  call    __security_check_cookie
0x180017384  add     rsp, 888h
0x18001738b  pop     r15
0x18001738d  pop     r14
0x18001738f  pop     r13
0x180017391  pop     rdi
0x180017392  pop     rsi
0x180017393  pop     rbx
0x180017394  retn
```
