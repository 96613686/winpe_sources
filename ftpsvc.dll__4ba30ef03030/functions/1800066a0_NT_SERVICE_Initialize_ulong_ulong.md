# NT_SERVICE::Initialize(ulong,ulong)

- ea: `0x1800066a0`
- end: `0x180006888`
- name: `?Initialize@NT_SERVICE@@AEAAJKK@Z`
- size: `488`
- prototype: `__int64 __fastcall(NT_SERVICE *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180006978`

## callees

- `0x1800066a0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180006790`
- `KERNEL32!CreateEventW` at `0x1800067e0`
- `KERNEL32!CreateEventW` at `0x180006830`
- `KERNEL32!CreateEventW` at `0x180006790`
- `KERNEL32!CreateEventW` at `0x1800067e0`
- `KERNEL32!CreateEventW` at `0x180006830`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800066c3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800066c3`
- `KERNEL32!GetLastError` at `0x1800066cd`
- `KERNEL32!GetLastError` at `0x180006756`
- `KERNEL32!GetLastError` at `0x1800067a2`
- `KERNEL32!GetLastError` at `0x1800067f2`
- `KERNEL32!GetLastError` at `0x180006842`
- `KERNEL32!GetLastError` at `0x1800066cd`
- `KERNEL32!GetLastError` at `0x180006756`
- `KERNEL32!GetLastError` at `0x1800067a2`
- `KERNEL32!GetLastError` at `0x1800067f2`
- `KERNEL32!GetLastError` at `0x180006842`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180006747`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x180006747`
- `iisutil!PuDbgPrint` at `0x180006716`
- `iisutil!PuDbgPrint` at `0x180006716`

## string_xrefs

- `0x1800066ff`: `NT_SERVICE::Initialize`
- `0x18000670a`: `inetsrv\iis\iisrearc\ftp\server\core\nt_service.cxx`
- `0x180006774`: `Error calling RegisterServiceCtrlHandlerEx().  hr = %x\n`
- `0x1800067c4`: `Error in CreateEvent().  hr = %x\n`
- `0x180006814`: `Error in CreateEvent().  hr = %x\n`
- `0x180006864`: `Error in CreateEvent().  hr = %x\n`

## pseudocode

```c
__int64 __fastcall NT_SERVICE::Initialize(NT_SERVICE *this, int a2, int a3)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  __int64 v9; // r8
  SERVICE_STATUS_HANDLE v11; // rax
  signed int v12; // eax
  HANDLE EventW; // rax
  signed int v14; // eax
  HANDLE v15; // rax
  signed int v16; // eax
  HANDLE v17; // rax
  signed int v18; // eax
  unsigned int v19; // [rsp+28h] [rbp-10h]

  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 584), 0x800003E8) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      return v7;
    v8 = "Error calling InitializeCriticalSectionAndSpinCount().  hr = %x\n";
    v9 = 112;
LABEL_6:
    v19 = v7;
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\nt_service.cxx",
      v9,
      "NT_SERVICE::Initialize",
      v8,
      v19);
    return v7;
  }
  *((_DWORD *)this + 156) = 1;
  *((_DWORD *)this + 157) = a2;
  *((_DWORD *)this + 158) = a3;
  v11 = RegisterServiceCtrlHandlerExW(
          (LPCWSTR)this + 22,
          (LPHANDLER_FUNCTION_EX)NT_SERVICE::GlobalServiceControlHandler,
          this);
  *((_QWORD *)this + 1) = v11;
  if ( !v11 )
  {
    v12 = GetLastError();
    v7 = v12;
    if ( v12 > 0 )
      v7 = (unsigned __int16)v12 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      return v7;
    v8 = "Error calling RegisterServiceCtrlHandlerEx().  hr = %x\n";
    v9 = 136;
    goto LABEL_6;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 70) = EventW;
  if ( !EventW )
  {
    v14 = GetLastError();
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      return v7;
    v8 = "Error in CreateEvent().  hr = %x\n";
    v9 = 155;
    goto LABEL_6;
  }
  v15 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 71) = v15;
  if ( !v15 )
  {
    v16 = GetLastError();
    v7 = v16;
    if ( v16 > 0 )
      v7 = (unsigned __int16)v16 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      return v7;
    v8 = "Error in CreateEvent().  hr = %x\n";
    v9 = 174;
    goto LABEL_6;
  }
  v17 = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 72) = v17;
  if ( !v17 )
  {
    v18 = GetLastError();
    v7 = v18;
    if ( v18 > 0 )
      v7 = (unsigned __int16)v18 | 0x80070000;
    if ( (g_dwDebugFlags & 3) == 0 )
      return v7;
    v8 = "Error in CreateEvent().  hr = %x\n";
    v9 = 193;
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x1800066a0  mov     [rsp+arg_0], rbx
0x1800066a5  mov     [rsp+arg_8], rsi
0x1800066aa  push    rdi
0x1800066ab  sub     rsp, 30h
0x1800066af  mov     esi, edx
0x1800066b1  mov     rbx, rcx
0x1800066b4  add     rcx, 248h; lpCriticalSection
0x1800066bb  mov     edx, 800003E8h; dwSpinCount
0x1800066c0  mov     edi, r8d
0x1800066c3  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800066c9  test    eax, eax
0x1800066cb  jnz     short loc_180006723
0x1800066cd  call    cs:__imp_GetLastError
0x1800066d3  mov     ebx, eax
0x1800066d5  test    eax, eax
0x1800066d7  jle     short loc_1800066E2
0x1800066d9  movzx   ebx, ax
0x1800066dc  or      ebx, 80070000h
0x1800066e2  test    byte ptr cs:g_dwDebugFlags, 3
0x1800066e9  jz      short loc_18000671C
0x1800066eb  lea     rax, aErrorCallingIn; "Error calling InitializeCriticalSection"...
0x1800066f2  mov     r8d, 70h ; 'p'
0x1800066f8  mov     rcx, cs:g_pDebug
0x1800066ff  lea     r9, aNtServiceIniti; "NT_SERVICE::Initialize"
0x180006706  mov     [rsp+38h+var_10], ebx
0x18000670a  lea     rdx, aInetsrvIisIisr_38; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x180006711  mov     [rsp+38h+var_18], rax
0x180006716  call    cs:__imp_PuDbgPrint
0x18000671c  mov     eax, ebx
0x18000671e  jmp     loc_180006878
0x180006723  lea     rcx, [rbx+2Ch]; lpServiceName
0x180006727  mov     dword ptr [rbx+270h], 1
0x180006731  mov     r8, rbx; lpContext
0x180006734  mov     [rbx+274h], esi
0x18000673a  lea     rdx, ?GlobalServiceControlHandler@NT_SERVICE@@CAKKKPEAX0@Z; lpHandlerProc
0x180006741  mov     [rbx+278h], edi
0x180006747  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000674d  mov     [rbx+8], rax
0x180006751  test    rax, rax
0x180006754  jnz     short loc_180006786
0x180006756  call    cs:__imp_GetLastError
0x18000675c  mov     ebx, eax
0x18000675e  test    eax, eax
0x180006760  jle     short loc_18000676B
0x180006762  movzx   ebx, ax
0x180006765  or      ebx, 80070000h
0x18000676b  test    byte ptr cs:g_dwDebugFlags, 3
0x180006772  jz      short loc_18000671C
0x180006774  lea     rax, aErrorCallingRe; "Error calling RegisterServiceCtrlHandle"...
0x18000677b  mov     r8d, 88h
0x180006781  jmp     loc_1800066F8
0x180006786  xor     r9d, r9d; lpName
0x180006789  xor     r8d, r8d; bInitialState
0x18000678c  xor     edx, edx; bManualReset
0x18000678e  xor     ecx, ecx; lpEventAttributes
0x180006790  call    cs:__imp_CreateEventW
0x180006796  mov     [rbx+230h], rax
0x18000679d  test    rax, rax
0x1800067a0  jnz     short loc_1800067D6
0x1800067a2  call    cs:__imp_GetLastError
0x1800067a8  mov     ebx, eax
0x1800067aa  test    eax, eax
0x1800067ac  jle     short loc_1800067B7
0x1800067ae  movzx   ebx, ax
0x1800067b1  or      ebx, 80070000h
0x1800067b7  test    byte ptr cs:g_dwDebugFlags, 3
0x1800067be  jz      loc_18000671C
0x1800067c4  lea     rax, aErrorInCreatee; "Error in CreateEvent().  hr = %x\n"
0x1800067cb  mov     r8d, 9Bh
0x1800067d1  jmp     loc_1800066F8
0x1800067d6  xor     r9d, r9d; lpName
0x1800067d9  xor     r8d, r8d; bInitialState
0x1800067dc  xor     edx, edx; bManualReset
0x1800067de  xor     ecx, ecx; lpEventAttributes
0x1800067e0  call    cs:__imp_CreateEventW
0x1800067e6  mov     [rbx+238h], rax
0x1800067ed  test    rax, rax
0x1800067f0  jnz     short loc_180006826
0x1800067f2  call    cs:__imp_GetLastError
0x1800067f8  mov     ebx, eax
0x1800067fa  test    eax, eax
0x1800067fc  jle     short loc_180006807
0x1800067fe  movzx   ebx, ax
0x180006801  or      ebx, 80070000h
0x180006807  test    byte ptr cs:g_dwDebugFlags, 3
0x18000680e  jz      loc_18000671C
0x180006814  lea     rax, aErrorInCreatee; "Error in CreateEvent().  hr = %x\n"
0x18000681b  mov     r8d, 0AEh
0x180006821  jmp     loc_1800066F8
0x180006826  xor     r9d, r9d; lpName
0x180006829  xor     r8d, r8d; bInitialState
0x18000682c  xor     edx, edx; bManualReset
0x18000682e  xor     ecx, ecx; lpEventAttributes
0x180006830  call    cs:__imp_CreateEventW
0x180006836  mov     [rbx+240h], rax
0x18000683d  test    rax, rax
0x180006840  jnz     short loc_180006876
0x180006842  call    cs:__imp_GetLastError
0x180006848  mov     ebx, eax
0x18000684a  test    eax, eax
0x18000684c  jle     short loc_180006857
0x18000684e  movzx   ebx, ax
0x180006851  or      ebx, 80070000h
0x180006857  test    byte ptr cs:g_dwDebugFlags, 3
0x18000685e  jz      loc_18000671C
0x180006864  lea     rax, aErrorInCreatee; "Error in CreateEvent().  hr = %x\n"
0x18000686b  mov     r8d, 0C1h
0x180006871  jmp     loc_1800066F8
0x180006876  xor     eax, eax
0x180006878  mov     rbx, [rsp+38h+arg_0]
0x18000687d  mov     rsi, [rsp+38h+arg_8]
0x180006882  add     rsp, 30h
0x180006886  pop     rdi
0x180006887  retn
```
