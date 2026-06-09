# InitializeServerProtocolEngine

- ea: `0x180008990`
- end: `0x180008c67`
- name: `InitializeServerProtocolEngine`
- size: `727`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008990`
- `0x1800187b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800089f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008bf2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008b56`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008b86`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008bda`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008b56`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008b86`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008bda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008bb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008c24`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800089e8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800089e8`

## pseudocode

```c
DWORD __fastcall InitializeServerProtocolEngine(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int a5,
        __int64 *a6,
        __int64 a7,
        __int64 a8)
{
  __int64 *v8; // rbx
  DWORD LastError; // ebx
  DWORD nSize; // [rsp+30h] [rbp+8h] BYREF

  nSize = 16;
  if ( !a1 )
    return 87;
  v8 = a6;
  if ( !a6 || !a7 )
    return 87;
  qword_18004DA60 = a1;
  dword_18004DAD0 = a2;
  LODWORD(dword_18004DAC8) = a4;
  dword_18004DA20 = a3;
  if ( !GetComputerNameA(&Src, &nSize) )
    return GetLastError();
  dword_18004D9F0 = a5;
  qword_18004DA70 = v8[1];
  qword_18004DA68 = *v8;
  qword_18004DA78 = v8[2];
  qword_18004DA80 = v8[3];
  qword_18004DA88 = v8[4];
  qword_18004DA90 = v8[5];
  qword_18004DA98 = v8[6];
  qword_18004DAA0 = *(_QWORD *)a8;
  PeHlpFunc = *(_OWORD *)a8;
  xmmword_18004D3F0 = *(_OWORD *)(a8 + 16);
  *(_OWORD *)byte_18004D400 = *(_OWORD *)(a8 + 32);
  xmmword_18004D410 = *(_OWORD *)(a8 + 48);
  xmmword_18004D420 = *(_OWORD *)(a8 + 64);
  *(_OWORD *)byte_18004D430 = *(_OWORD *)(a8 + 80);
  xmmword_18004D440 = *(_OWORD *)(a8 + 96);
  xmmword_18004D450 = *(_OWORD *)(a8 + 112);
  xmmword_18004D460 = *(_OWORD *)(a8 + 128);
  xmmword_18004D470 = *(_OWORD *)(a8 + 144);
  xmmword_18004D480 = *(_OWORD *)(a8 + 160);
  xmmword_18004D490 = *(_OWORD *)(a8 + 176);
  xmmword_18004D4A0 = *(_OWORD *)(a8 + 192);
  xmmword_18004D4B0 = *(_OWORD *)(a8 + 208);
  RasPPPSrvrAddressMgmtInitialize(a7);
  g_AuthProv = 0;
  LODWORD(g_AuthProv) = 1;
  g_DdmMsgHandler = 0;
  g_AcctProv = 0;
  *((_QWORD *)&g_AuthProv + 1) = CreateEventA(0, 0, 0, 0);
  if ( !*((_QWORD *)&g_AuthProv + 1) )
    return GetLastError();
  LODWORD(g_AcctProv) = 0;
  *((_QWORD *)&g_AcctProv + 1) = CreateEventA(0, 0, 0, 0);
  if ( !*((_QWORD *)&g_AcctProv + 1) )
  {
    LastError = GetLastError();
    CloseHandle(*((HANDLE *)&g_AuthProv + 1));
    g_AuthProv = 0;
    return LastError;
  }
  *((_QWORD *)&g_DdmMsgHandler + 1) = CreateEventA(0, 0, 0, 0);
  if ( !*((_QWORD *)&g_DdmMsgHandler + 1) )
  {
    LastError = GetLastError();
    CloseHandle(*((HANDLE *)&g_AuthProv + 1));
    g_AuthProv = 0;
    CloseHandle(*((HANDLE *)&g_AcctProv + 1));
    g_AcctProv = 0;
    return LastError;
  }
  _InterlockedAdd((_DWORD *)&g_AuthProv + 1, 1u);
  _InterlockedAdd((_DWORD *)&g_AcctProv + 1, 1u);
  _InterlockedAdd((volatile signed __int32 *)&g_DdmMsgHandler, 1u);
  DDMInitialized = 1;
  return 0;
}

```

## disassembly

```asm
0x180008990  push    rbx
0x180008992  sub     rsp, 20h
0x180008996  mov     [rsp+28h+nSize], 10h
0x18000899e  test    rcx, rcx
0x1800089a1  jz      loc_180008C5B
0x1800089a7  mov     rbx, [rsp+28h+arg_28]
0x1800089ac  test    rbx, rbx
0x1800089af  jz      loc_180008C5B
0x1800089b5  cmp     [rsp+28h+arg_30], 0
0x1800089bb  jz      loc_180008C5B
0x1800089c1  mov     cs:qword_18004DA60, rcx
0x1800089c8  lea     rcx, Src; lpBuffer
0x1800089cf  mov     cs:dword_18004DAD0, edx
0x1800089d5  lea     rdx, [rsp+28h+nSize]; nSize
0x1800089da  mov     cs:dword_18004DAC8, r9d
0x1800089e1  mov     cs:dword_18004DA20, r8d
0x1800089e8  call    cs:__imp_GetComputerNameA
0x1800089ef  nop     dword ptr [rax+rax+00h]
0x1800089f4  test    eax, eax
0x1800089f6  jnz     short loc_180008A09
0x1800089f8  call    cs:__imp_GetLastError
0x1800089ff  nop     dword ptr [rax+rax+00h]
0x180008a04  jmp     loc_180008C60
0x180008a09  mov     rdx, [rsp+28h+arg_38]
0x180008a0e  mov     eax, [rsp+28h+arg_20]
0x180008a12  mov     rcx, [rsp+28h+arg_30]
0x180008a17  mov     cs:dword_18004D9F0, eax
0x180008a1d  mov     rax, [rbx+8]
0x180008a21  mov     cs:qword_18004DA70, rax
0x180008a28  mov     rax, [rbx]
0x180008a2b  mov     cs:qword_18004DA68, rax
0x180008a32  mov     rax, [rbx+10h]
0x180008a36  mov     cs:qword_18004DA78, rax
0x180008a3d  mov     rax, [rbx+18h]
0x180008a41  mov     cs:qword_18004DA80, rax
0x180008a48  mov     rax, [rbx+20h]
0x180008a4c  mov     cs:qword_18004DA88, rax
0x180008a53  mov     rax, [rbx+28h]
0x180008a57  mov     cs:qword_18004DA90, rax
0x180008a5e  mov     rax, [rbx+30h]
0x180008a62  mov     cs:qword_18004DA98, rax
0x180008a69  mov     rax, [rdx]
0x180008a6c  mov     cs:qword_18004DAA0, rax
0x180008a73  movups  xmm0, xmmword ptr [rdx]
0x180008a76  movups  cs:PeHlpFunc, xmm0
0x180008a7d  movups  xmm1, xmmword ptr [rdx+10h]
0x180008a81  movups  cs:xmmword_18004D3F0, xmm1
0x180008a88  movups  xmm0, xmmword ptr [rdx+20h]
0x180008a8c  movups  xmmword ptr cs:byte_18004D400, xmm0
0x180008a93  movups  xmm1, xmmword ptr [rdx+30h]
0x180008a97  movups  cs:xmmword_18004D410, xmm1
0x180008a9e  movups  xmm0, xmmword ptr [rdx+40h]
0x180008aa2  movups  cs:xmmword_18004D420, xmm0
0x180008aa9  movups  xmm1, xmmword ptr [rdx+50h]
0x180008aad  movups  xmmword ptr cs:byte_18004D430, xmm1
0x180008ab4  movups  xmm0, xmmword ptr [rdx+60h]
0x180008ab8  movups  cs:xmmword_18004D440, xmm0
0x180008abf  movups  xmm1, xmmword ptr [rdx+70h]
0x180008ac3  movups  cs:xmmword_18004D450, xmm1
0x180008aca  movups  xmm0, xmmword ptr [rdx+80h]
0x180008ad1  movups  cs:xmmword_18004D460, xmm0
0x180008ad8  movups  xmm1, xmmword ptr [rdx+90h]
0x180008adf  movups  cs:xmmword_18004D470, xmm1
0x180008ae6  movups  xmm0, xmmword ptr [rdx+0A0h]
0x180008aed  movups  cs:xmmword_18004D480, xmm0
0x180008af4  movups  xmm1, xmmword ptr [rdx+0B0h]
0x180008afb  movups  cs:xmmword_18004D490, xmm1
0x180008b02  movups  xmm0, xmmword ptr [rdx+0C0h]
0x180008b09  movups  cs:xmmword_18004D4A0, xmm0
0x180008b10  movups  xmm1, xmmword ptr [rdx+0D0h]
0x180008b17  movups  cs:xmmword_18004D4B0, xmm1
0x180008b1e  call    RasPPPSrvrAddressMgmtInitialize
0x180008b23  xorps   xmm2, xmm2
0x180008b26  xorps   xmm0, xmm0
0x180008b29  xorps   xmm3, xmm3
0x180008b2c  mov     ebx, 1
0x180008b31  movups  cs:g_AuthProv, xmm2
0x180008b38  xor     r9d, r9d; lpName
0x180008b3b  mov     dword ptr cs:g_AuthProv, ebx
0x180008b41  xor     r8d, r8d; bInitialState
0x180008b44  xor     edx, edx; bManualReset
0x180008b46  xor     ecx, ecx; lpEventAttributes
0x180008b48  movups  cs:g_DdmMsgHandler, xmm0
0x180008b4f  movups  cs:g_AcctProv, xmm3
0x180008b56  call    cs:__imp_CreateEventA
0x180008b5d  nop     dword ptr [rax+rax+00h]
0x180008b62  mov     qword ptr cs:g_AuthProv+8, rax
0x180008b69  test    rax, rax
0x180008b6c  jz      loc_1800089F8
0x180008b72  xor     r9d, r9d; lpName
0x180008b75  mov     dword ptr cs:g_AcctProv, 0
0x180008b7f  xor     r8d, r8d; bInitialState
0x180008b82  xor     edx, edx; bManualReset
0x180008b84  xor     ecx, ecx; lpEventAttributes
0x180008b86  call    cs:__imp_CreateEventA
0x180008b8d  nop     dword ptr [rax+rax+00h]
0x180008b92  mov     qword ptr cs:g_AcctProv+8, rax
0x180008b99  test    rax, rax
0x180008b9c  jnz     short loc_180008BD0
0x180008b9e  call    cs:__imp_GetLastError
0x180008ba5  nop     dword ptr [rax+rax+00h]
0x180008baa  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x180008bb1  mov     ebx, eax
0x180008bb3  call    cs:__imp_CloseHandle
0x180008bba  nop     dword ptr [rax+rax+00h]
0x180008bbf  xorps   xmm0, xmm0
0x180008bc2  movups  cs:g_AuthProv, xmm0
0x180008bc9  mov     eax, ebx
0x180008bcb  jmp     loc_180008C60
0x180008bd0  xor     r9d, r9d; lpName
0x180008bd3  xor     r8d, r8d; bInitialState
0x180008bd6  xor     edx, edx; bManualReset
0x180008bd8  xor     ecx, ecx; lpEventAttributes
0x180008bda  call    cs:__imp_CreateEventA
0x180008be1  nop     dword ptr [rax+rax+00h]
0x180008be6  mov     qword ptr cs:g_DdmMsgHandler+8, rax
0x180008bed  test    rax, rax
0x180008bf0  jnz     short loc_180008C3C
0x180008bf2  call    cs:__imp_GetLastError
0x180008bf9  nop     dword ptr [rax+rax+00h]
0x180008bfe  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x180008c05  mov     ebx, eax
0x180008c07  call    cs:__imp_CloseHandle
0x180008c0e  nop     dword ptr [rax+rax+00h]
0x180008c13  mov     rcx, qword ptr cs:g_AcctProv+8; hObject
0x180008c1a  xorps   xmm0, xmm0
0x180008c1d  movups  cs:g_AuthProv, xmm0
0x180008c24  call    cs:__imp_CloseHandle
0x180008c2b  nop     dword ptr [rax+rax+00h]
0x180008c30  xorps   xmm0, xmm0
0x180008c33  movups  cs:g_AcctProv, xmm0
0x180008c3a  jmp     short loc_180008BC9
0x180008c3c  lock add dword ptr cs:g_AuthProv+4, ebx
0x180008c43  lock add dword ptr cs:g_AcctProv+4, ebx
0x180008c4a  lock add dword ptr cs:g_DdmMsgHandler, ebx
0x180008c51  mov     cs:DDMInitialized, ebx
0x180008c57  xor     eax, eax
0x180008c59  jmp     short loc_180008C60
0x180008c5b  mov     eax, 57h ; 'W'
0x180008c60  add     rsp, 20h
0x180008c64  pop     rbx
0x180008c65  retn
```
