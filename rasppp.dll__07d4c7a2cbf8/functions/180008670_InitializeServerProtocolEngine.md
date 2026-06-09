# InitializeServerProtocolEngine

- ea: `0x180008670`
- end: `0x180008907`
- name: `InitializeServerProtocolEngine`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008670`
- `0x180017f50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008866`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000882a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008854`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008893`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000882a`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008854`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008893`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008875`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008875`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088cb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800086c8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameA` at `0x1800086c8`

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
  qword_18004CA60 = a1;
  dword_18004CAD0 = a2;
  LODWORD(dword_18004CAC8) = a4;
  dword_18004CA20 = a3;
  if ( !GetComputerNameA(&Src, &nSize) )
    return GetLastError();
  dword_18004C9F0 = a5;
  qword_18004CA70 = v8[1];
  qword_18004CA68 = *v8;
  qword_18004CA78 = v8[2];
  qword_18004CA80 = v8[3];
  qword_18004CA88 = v8[4];
  qword_18004CA90 = v8[5];
  qword_18004CA98 = v8[6];
  qword_18004CAA0 = *(_QWORD *)a8;
  PeHlpFunc = *(_OWORD *)a8;
  xmmword_18004C3F0 = *(_OWORD *)(a8 + 16);
  *(_OWORD *)byte_18004C400 = *(_OWORD *)(a8 + 32);
  xmmword_18004C410 = *(_OWORD *)(a8 + 48);
  xmmword_18004C420 = *(_OWORD *)(a8 + 64);
  *(_OWORD *)byte_18004C430 = *(_OWORD *)(a8 + 80);
  xmmword_18004C440 = *(_OWORD *)(a8 + 96);
  xmmword_18004C450 = *(_OWORD *)(a8 + 112);
  xmmword_18004C460 = *(_OWORD *)(a8 + 128);
  xmmword_18004C470 = *(_OWORD *)(a8 + 144);
  xmmword_18004C480 = *(_OWORD *)(a8 + 160);
  xmmword_18004C490 = *(_OWORD *)(a8 + 176);
  xmmword_18004C4A0 = *(_OWORD *)(a8 + 192);
  xmmword_18004C4B0 = *(_OWORD *)(a8 + 208);
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
0x180008670  push    rbx
0x180008672  sub     rsp, 20h
0x180008676  mov     [rsp+28h+nSize], 10h
0x18000867e  test    rcx, rcx
0x180008681  jz      loc_1800088FC
0x180008687  mov     rbx, [rsp+28h+arg_28]
0x18000868c  test    rbx, rbx
0x18000868f  jz      loc_1800088FC
0x180008695  cmp     [rsp+28h+arg_30], 0
0x18000869b  jz      loc_1800088FC
0x1800086a1  mov     cs:qword_18004CA60, rcx
0x1800086a8  lea     rcx, Src; lpBuffer
0x1800086af  mov     cs:dword_18004CAD0, edx
0x1800086b5  lea     rdx, [rsp+28h+nSize]; nSize
0x1800086ba  mov     cs:dword_18004CAC8, r9d
0x1800086c1  mov     cs:dword_18004CA20, r8d
0x1800086c8  call    cs:__imp_GetComputerNameA
0x1800086ce  test    eax, eax
0x1800086d0  jnz     short loc_1800086DD
0x1800086d2  call    cs:__imp_GetLastError
0x1800086d8  jmp     loc_180008901
0x1800086dd  mov     rdx, [rsp+28h+arg_38]
0x1800086e2  mov     eax, [rsp+28h+arg_20]
0x1800086e6  mov     rcx, [rsp+28h+arg_30]
0x1800086eb  mov     cs:dword_18004C9F0, eax
0x1800086f1  mov     rax, [rbx+8]
0x1800086f5  mov     cs:qword_18004CA70, rax
0x1800086fc  mov     rax, [rbx]
0x1800086ff  mov     cs:qword_18004CA68, rax
0x180008706  mov     rax, [rbx+10h]
0x18000870a  mov     cs:qword_18004CA78, rax
0x180008711  mov     rax, [rbx+18h]
0x180008715  mov     cs:qword_18004CA80, rax
0x18000871c  mov     rax, [rbx+20h]
0x180008720  mov     cs:qword_18004CA88, rax
0x180008727  mov     rax, [rbx+28h]
0x18000872b  mov     cs:qword_18004CA90, rax
0x180008732  mov     rax, [rbx+30h]
0x180008736  mov     cs:qword_18004CA98, rax
0x18000873d  mov     rax, [rdx]
0x180008740  mov     cs:qword_18004CAA0, rax
0x180008747  movups  xmm0, xmmword ptr [rdx]
0x18000874a  movups  cs:PeHlpFunc, xmm0
0x180008751  movups  xmm1, xmmword ptr [rdx+10h]
0x180008755  movups  cs:xmmword_18004C3F0, xmm1
0x18000875c  movups  xmm0, xmmword ptr [rdx+20h]
0x180008760  movups  xmmword ptr cs:byte_18004C400, xmm0
0x180008767  movups  xmm1, xmmword ptr [rdx+30h]
0x18000876b  movups  cs:xmmword_18004C410, xmm1
0x180008772  movups  xmm0, xmmword ptr [rdx+40h]
0x180008776  movups  cs:xmmword_18004C420, xmm0
0x18000877d  movups  xmm1, xmmword ptr [rdx+50h]
0x180008781  movups  xmmword ptr cs:byte_18004C430, xmm1
0x180008788  movups  xmm0, xmmword ptr [rdx+60h]
0x18000878c  movups  cs:xmmword_18004C440, xmm0
0x180008793  movups  xmm1, xmmword ptr [rdx+70h]
0x180008797  movups  cs:xmmword_18004C450, xmm1
0x18000879e  movups  xmm0, xmmword ptr [rdx+80h]
0x1800087a5  movups  cs:xmmword_18004C460, xmm0
0x1800087ac  movups  xmm1, xmmword ptr [rdx+90h]
0x1800087b3  movups  cs:xmmword_18004C470, xmm1
0x1800087ba  movups  xmm0, xmmword ptr [rdx+0A0h]
0x1800087c1  movups  cs:xmmword_18004C480, xmm0
0x1800087c8  movups  xmm1, xmmword ptr [rdx+0B0h]
0x1800087cf  movups  cs:xmmword_18004C490, xmm1
0x1800087d6  movups  xmm0, xmmword ptr [rdx+0C0h]
0x1800087dd  movups  cs:xmmword_18004C4A0, xmm0
0x1800087e4  movups  xmm1, xmmword ptr [rdx+0D0h]
0x1800087eb  movups  cs:xmmword_18004C4B0, xmm1
0x1800087f2  call    RasPPPSrvrAddressMgmtInitialize
0x1800087f7  xorps   xmm2, xmm2
0x1800087fa  xorps   xmm0, xmm0
0x1800087fd  xorps   xmm3, xmm3
0x180008800  mov     ebx, 1
0x180008805  movups  cs:g_AuthProv, xmm2
0x18000880c  xor     r9d, r9d; lpName
0x18000880f  mov     dword ptr cs:g_AuthProv, ebx
0x180008815  xor     r8d, r8d; bInitialState
0x180008818  xor     edx, edx; bManualReset
0x18000881a  xor     ecx, ecx; lpEventAttributes
0x18000881c  movups  cs:g_DdmMsgHandler, xmm0
0x180008823  movups  cs:g_AcctProv, xmm3
0x18000882a  call    cs:__imp_CreateEventA
0x180008830  mov     qword ptr cs:g_AuthProv+8, rax
0x180008837  test    rax, rax
0x18000883a  jz      loc_1800086D2
0x180008840  xor     r9d, r9d; lpName
0x180008843  mov     dword ptr cs:g_AcctProv, 0
0x18000884d  xor     r8d, r8d; bInitialState
0x180008850  xor     edx, edx; bManualReset
0x180008852  xor     ecx, ecx; lpEventAttributes
0x180008854  call    cs:__imp_CreateEventA
0x18000885a  mov     qword ptr cs:g_AcctProv+8, rax
0x180008861  test    rax, rax
0x180008864  jnz     short loc_180008889
0x180008866  call    cs:__imp_GetLastError
0x18000886c  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x180008873  mov     ebx, eax
0x180008875  call    cs:__imp_CloseHandle
0x18000887b  xorps   xmm0, xmm0
0x18000887e  movups  cs:g_AuthProv, xmm0
0x180008885  mov     eax, ebx
0x180008887  jmp     short loc_180008901
0x180008889  xor     r9d, r9d; lpName
0x18000888c  xor     r8d, r8d; bInitialState
0x18000888f  xor     edx, edx; bManualReset
0x180008891  xor     ecx, ecx; lpEventAttributes
0x180008893  call    cs:__imp_CreateEventA
0x180008899  mov     qword ptr cs:g_DdmMsgHandler+8, rax
0x1800088a0  test    rax, rax
0x1800088a3  jnz     short loc_1800088DD
0x1800088a5  call    cs:__imp_GetLastError
0x1800088ab  mov     rcx, qword ptr cs:g_AuthProv+8; hObject
0x1800088b2  mov     ebx, eax
0x1800088b4  call    cs:__imp_CloseHandle
0x1800088ba  mov     rcx, qword ptr cs:g_AcctProv+8; hObject
0x1800088c1  xorps   xmm0, xmm0
0x1800088c4  movups  cs:g_AuthProv, xmm0
0x1800088cb  call    cs:__imp_CloseHandle
0x1800088d1  xorps   xmm0, xmm0
0x1800088d4  movups  cs:g_AcctProv, xmm0
0x1800088db  jmp     short loc_180008885
0x1800088dd  lock add dword ptr cs:g_AuthProv+4, ebx
0x1800088e4  lock add dword ptr cs:g_AcctProv+4, ebx
0x1800088eb  lock add dword ptr cs:g_DdmMsgHandler, ebx
0x1800088f2  mov     cs:DDMInitialized, ebx
0x1800088f8  xor     eax, eax
0x1800088fa  jmp     short loc_180008901
0x1800088fc  mov     eax, 57h ; 'W'
0x180008901  add     rsp, 20h
0x180008905  pop     rbx
0x180008906  retn
```
