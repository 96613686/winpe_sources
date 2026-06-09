# RasScriptExecute

- ea: `0x1800b1170`
- end: `0x1800b13e4`
- name: `RasScriptExecute`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800b1170`
- `0x1800b13f0`
- `0x1800b14d0`
- `0x1800b1dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b11cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b1212`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b11cb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800b1212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1224`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b11d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b1372`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b12d5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800b12d5`
- `rtutils!TracePrintfExA` at `0x1800b11bb`
- `rtutils!TracePrintfExA` at `0x1800b11fd`
- `rtutils!TracePrintfExA` at `0x1800b1248`
- `rtutils!TracePrintfExA` at `0x1800b12a2`
- `rtutils!TracePrintfExA` at `0x1800b12f8`
- `rtutils!TracePrintfExA` at `0x1800b1323`
- `rtutils!TracePrintfExA` at `0x1800b1348`
- `rtutils!TracePrintfExA` at `0x1800b13a7`
- `rtutils!TracePrintfExA` at `0x1800b13d9`
- `rtutils!TracePrintfExA` at `0x1800b11bb`
- `rtutils!TracePrintfExA` at `0x1800b11fd`
- `rtutils!TracePrintfExA` at `0x1800b1248`
- `rtutils!TracePrintfExA` at `0x1800b12a2`
- `rtutils!TracePrintfExA` at `0x1800b12f8`
- `rtutils!TracePrintfExA` at `0x1800b1323`
- `rtutils!TracePrintfExA` at `0x1800b1348`
- `rtutils!TracePrintfExA` at `0x1800b13a7`
- `rtutils!TracePrintfExA` at `0x1800b13d9`

## string_xrefs

- `0x1800b133e`: `script processing completed`

## pseudocode

```c
__int64 __fastcall RasScriptExecute(HRASCONN a1, __int64 a2, const char *a3, const char *a4, const char *a5)
{
  HANDLE EventA; // rsi
  DWORD v10; // eax
  DWORD v11; // ebx
  DWORD LastError; // eax
  DWORD v13; // eax
  _DWORD *v14; // rdi
  DWORD v15; // eax
  DWORD v16; // ecx
  unsigned int v17; // ebx
  int IpAddress; // eax
  HGLOBAL hMem; // [rsp+40h] [rbp-58h] BYREF
  HANDLE Handles[10]; // [rsp+48h] [rbp-50h] BYREF

  hMem = 0;
  *(_OWORD *)Handles = 0;
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RasScriptExecute");
  EventA = CreateEventA(0, 0, 0, 0);
  if ( EventA )
  {
    g_hIpAddressSet = CreateEventA(0, 0, 0, 0);
    if ( g_hIpAddressSet )
    {
      v13 = RasScriptInit(a1, a2, a3, a4, 0, (__int64)EventA, &hMem);
      v14 = hMem;
      v11 = v13;
      if ( v13 )
      {
        if ( g_dwRasscrptTraceId != -1 )
          TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d initializing scripting", v13);
      }
      else
      {
        Handles[1] = g_hIpAddressSet;
        Handles[0] = EventA;
        do
        {
          while ( 1 )
          {
            v15 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
            if ( !v15 )
              break;
            if ( v15 == 1 )
            {
              if ( g_dwRasscrptTraceId != -1 )
                TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "IP address changed");
              IpAddress = RasScriptGetIpAddress(v14, a5);
              if ( g_dwRasscrptTraceId != -1 )
                TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RasScriptGetIpAddress(e=%d,a=%s)", IpAddress, a5);
            }
          }
          v16 = g_dwRasscrptTraceId;
          if ( g_dwRasscrptTraceId != -1 )
          {
            TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RasGetEventCode");
            v16 = g_dwRasscrptTraceId;
          }
          v17 = 87;
          if ( v14 )
            v17 = v14[26];
          if ( v16 != -1 )
          {
            TracePrintfExA(v16, 0xCu, "RasScriptExecute: eventcode %d", v17);
            v16 = g_dwRasscrptTraceId;
          }
        }
        while ( v17 > 1 && v17 != 6 );
        if ( v16 != -1 )
          TracePrintfExA(v16, 0xCu, "script processing completed");
        v11 = 0;
      }
      if ( v14 )
        RasScriptTerm(v14);
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( g_dwRasscrptTraceId != -1 )
        TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d creating event", LastError);
    }
    CloseHandle(EventA);
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( g_dwRasscrptTraceId != -1 )
      TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "error %d creating event", v10);
  }
  if ( g_hIpAddressSet )
    CloseHandle(g_hIpAddressSet);
  return v11;
}

```

## disassembly

```asm
0x1800b1170  push    rbx
0x1800b1172  push    rbp
0x1800b1173  push    rsi
0x1800b1174  push    rdi
0x1800b1175  push    r12
0x1800b1177  push    r14
0x1800b1179  push    r15
0x1800b117b  sub     rsp, 60h
0x1800b117f  mov     r14, rcx
0x1800b1182  mov     [rsp+98h+hMem], 0
0x1800b118b  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b1191  or      r15d, 0FFFFFFFFh
0x1800b1195  xorps   xmm0, xmm0
0x1800b1198  mov     rbx, r9
0x1800b119b  mov     rdi, r8
0x1800b119e  mov     rbp, rdx
0x1800b11a1  mov     r12d, 0Ch
0x1800b11a7  movups  xmmword ptr [rsp+98h+Handles], xmm0
0x1800b11ac  cmp     ecx, r15d
0x1800b11af  jz      short loc_1800B11C1
0x1800b11b1  lea     r8, aRasscriptexecu_0; "RasScriptExecute"
0x1800b11b8  mov     edx, r12d; dwFlags
0x1800b11bb  call    cs:__imp_TracePrintfExA
0x1800b11c1  xor     r9d, r9d; lpName
0x1800b11c4  xor     r8d, r8d; bInitialState
0x1800b11c7  xor     edx, edx; bManualReset
0x1800b11c9  xor     ecx, ecx; lpEventAttributes
0x1800b11cb  call    cs:__imp_CreateEventA
0x1800b11d1  mov     rsi, rax
0x1800b11d4  test    rax, rax
0x1800b11d7  jnz     short loc_1800B1208
0x1800b11d9  call    cs:__imp_GetLastError
0x1800b11df  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b11e5  mov     ebx, eax
0x1800b11e7  cmp     ecx, r15d
0x1800b11ea  jz      loc_1800B1366
0x1800b11f0  mov     r9d, eax
0x1800b11f3  lea     r8, aErrorDCreating_3; "error %d creating event"
0x1800b11fa  mov     edx, r12d; dwFlags
0x1800b11fd  call    cs:__imp_TracePrintfExA
0x1800b1203  jmp     loc_1800B1366
0x1800b1208  xor     r9d, r9d; lpName
0x1800b120b  xor     r8d, r8d; bInitialState
0x1800b120e  xor     edx, edx; bManualReset
0x1800b1210  xor     ecx, ecx; lpEventAttributes
0x1800b1212  call    cs:__imp_CreateEventA
0x1800b1218  mov     cs:g_hIpAddressSet, rax
0x1800b121f  test    rax, rax
0x1800b1222  jnz     short loc_1800B1253
0x1800b1224  call    cs:__imp_GetLastError
0x1800b122a  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b1230  mov     ebx, eax
0x1800b1232  cmp     ecx, r15d
0x1800b1235  jz      loc_1800B135D
0x1800b123b  mov     r9d, eax
0x1800b123e  lea     r8, aErrorDCreating_3; "error %d creating event"
0x1800b1245  mov     edx, r12d; dwFlags
0x1800b1248  call    cs:__imp_TracePrintfExA
0x1800b124e  jmp     loc_1800B135D
0x1800b1253  lea     rax, [rsp+98h+hMem]
0x1800b1258  mov     r9, rbx
0x1800b125b  mov     [rsp+98h+var_68], rax; __int64
0x1800b1260  mov     r8, rdi
0x1800b1263  mov     [rsp+98h+var_70], rsi; __int64
0x1800b1268  mov     rdx, rbp
0x1800b126b  mov     rcx, r14; HRASCONN
0x1800b126e  mov     [rsp+98h+var_78], 0; int
0x1800b1276  call    RasScriptInit
0x1800b127b  mov     rdi, [rsp+98h+hMem]
0x1800b1280  mov     ebx, eax
0x1800b1282  test    eax, eax
0x1800b1284  jz      short loc_1800B12AD
0x1800b1286  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b128c  cmp     ecx, r15d
0x1800b128f  jz      loc_1800B1350
0x1800b1295  mov     r9d, eax
0x1800b1298  lea     r8, aErrorDInitiali; "error %d initializing scripting"
0x1800b129f  mov     edx, r12d; dwFlags
0x1800b12a2  call    cs:__imp_TracePrintfExA
0x1800b12a8  jmp     loc_1800B1350
0x1800b12ad  mov     rax, cs:g_hIpAddressSet
0x1800b12b4  mov     rbp, [rsp+98h+arg_20]
0x1800b12bc  mov     [rsp+98h+Handles+8], rax
0x1800b12c1  mov     [rsp+98h+Handles], rsi
0x1800b12c6  xor     r8d, r8d; bWaitAll
0x1800b12c9  lea     rdx, [rsp+98h+Handles]; lpHandles
0x1800b12ce  mov     r9d, r15d; dwMilliseconds
0x1800b12d1  lea     ecx, [r8+2]; nCount
0x1800b12d5  call    cs:__imp_WaitForMultipleObjects
0x1800b12db  test    eax, eax
0x1800b12dd  jnz     loc_1800B1389
0x1800b12e3  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b12e9  cmp     ecx, r15d
0x1800b12ec  jz      short loc_1800B1304
0x1800b12ee  lea     r8, aRasgeteventcod; "RasGetEventCode"
0x1800b12f5  mov     edx, r12d; dwFlags
0x1800b12f8  call    cs:__imp_TracePrintfExA
0x1800b12fe  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b1304  mov     ebx, 57h ; 'W'
0x1800b1309  test    rdi, rdi
0x1800b130c  jz      short loc_1800B1311
0x1800b130e  mov     ebx, [rdi+68h]
0x1800b1311  cmp     ecx, r15d
0x1800b1314  jz      short loc_1800B132F
0x1800b1316  mov     r9d, ebx
0x1800b1319  lea     r8, aRasscriptexecu_1; "RasScriptExecute: eventcode %d"
0x1800b1320  mov     edx, r12d; dwFlags
0x1800b1323  call    cs:__imp_TracePrintfExA
0x1800b1329  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b132f  cmp     ebx, 1
0x1800b1332  jbe     short loc_1800B1339
0x1800b1334  cmp     ebx, 6
0x1800b1337  jnz     short loc_1800B12C6
0x1800b1339  cmp     ecx, r15d
0x1800b133c  jz      short loc_1800B134E
0x1800b133e  lea     r8, aScriptProcessi; "script processing completed"
0x1800b1345  mov     edx, r12d; dwFlags
0x1800b1348  call    cs:__imp_TracePrintfExA
0x1800b134e  xor     ebx, ebx
0x1800b1350  test    rdi, rdi
0x1800b1353  jz      short loc_1800B135D
0x1800b1355  mov     rcx, rdi; hMem
0x1800b1358  call    RasScriptTerm
0x1800b135d  mov     rcx, rsi; hObject
0x1800b1360  call    cs:__imp_CloseHandle
0x1800b1366  mov     rcx, cs:g_hIpAddressSet; hObject
0x1800b136d  test    rcx, rcx
0x1800b1370  jz      short loc_1800B1378
0x1800b1372  call    cs:__imp_CloseHandle
0x1800b1378  mov     eax, ebx
0x1800b137a  add     rsp, 60h
0x1800b137e  pop     r15
0x1800b1380  pop     r14
0x1800b1382  pop     r12
0x1800b1384  pop     rdi
0x1800b1385  pop     rsi
0x1800b1386  pop     rbp
0x1800b1387  pop     rbx
0x1800b1388  retn
0x1800b1389  cmp     eax, 1
0x1800b138c  jnz     loc_1800B12C6
0x1800b1392  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b1398  cmp     ecx, r15d
0x1800b139b  jz      short loc_1800B13AD
0x1800b139d  lea     r8, aIpAddressChang; "IP address changed"
0x1800b13a4  mov     edx, r12d; dwFlags
0x1800b13a7  call    cs:__imp_TracePrintfExA
0x1800b13ad  mov     rdx, rbp
0x1800b13b0  mov     rcx, rdi
0x1800b13b3  call    RasScriptGetIpAddress
0x1800b13b8  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b13be  cmp     ecx, r15d
0x1800b13c1  jz      loc_1800B12C6
0x1800b13c7  mov     r9d, eax
0x1800b13ca  mov     qword ptr [rsp+98h+var_78], rbp
0x1800b13cf  lea     r8, aRasscriptgetip_1; "RasScriptGetIpAddress(e=%d,a=%s)"
0x1800b13d6  mov     edx, r12d; dwFlags
0x1800b13d9  call    cs:__imp_TracePrintfExA
0x1800b13df  jmp     loc_1800B12C6
```
