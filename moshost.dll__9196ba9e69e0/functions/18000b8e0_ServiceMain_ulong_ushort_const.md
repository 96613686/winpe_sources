# ServiceMain(ulong,ushort * * const)

- ea: `0x18000b8e0`
- end: `0x18000bab0`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `464`
- prototype: `void __fastcall(unsigned int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000b30c`
- `0x18000b720`
- `0x18000b8e0`
- `0x18000bc1c`
- `0x18000bcc0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000b909`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18000b909`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba6e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000ba6e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b981`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b981`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ba52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ba3f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b953`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b953`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, LPCWSTR *a2)
{
  int v4; // ebx
  int v5; // eax
  signed int LastError; // eax

  ServiceStatus.dwControlsAccepted = 0;
  if ( a1 )
  {
    Block = (void *)_o__wcsdup(*a2);
    if ( Block )
    {
      v4 = 0;
      SvcLogEventFromServiceEngine(0, 0);
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
      ServiceStatus.dwServiceType = 32;
      hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
      if ( hServiceStatus )
      {
        SvcFrameworkUpdateServiceStatus(2u, 0, 0x32u);
        hObject = CreateEventW(0, 0, 0, 0);
        if ( hObject )
        {
          v4 = InitializeService(a1, (unsigned __int16 **const)a2);
          if ( v4 >= 0 )
          {
            ServiceStatus.dwControlsAccepted |= 1u;
            SvcFrameworkUpdateServiceStatus(4u, 0, 0);
            SvcLogEventFromServiceEngine(1, 0);
            if ( !qword_180018638 || (v4 = qword_180018638(), v4 >= 0) )
            {
              v5 = (*(__int64 (__fastcall **)(HANDLE *, void *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_180018668 + 192))(
                     &WaitHandle,
                     Block,
                     hObject,
                     StopService,
                     0,
                     8);
              v4 = v5;
              if ( !v5 )
                return;
              if ( v5 > 0 )
                v4 = (unsigned __int16)v5 | 0x80070000;
            }
            UninitializeService(v4);
          }
          CloseHandle(hObject);
          hObject = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      free(Block);
      Block = 0;
    }
    else
    {
      v4 = -2147024882;
    }
    SvcLogEventFromServiceEngine(3, (unsigned int)v4);
    SvcFrameworkUpdateServiceStatus(1u, v4, 0);
  }
}

```

## disassembly

```asm
0x18000b8e0  mov     [rsp+arg_0], rbx
0x18000b8e5  mov     [rsp+arg_8], rsi
0x18000b8ea  push    rdi
0x18000b8eb  sub     rsp, 40h
0x18000b8ef  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18000b8f9  mov     rdi, rdx
0x18000b8fc  mov     esi, ecx
0x18000b8fe  test    ecx, ecx
0x18000b900  jz      loc_18000BAA0
0x18000b906  mov     rcx, [rdx]
0x18000b909  call    cs:__imp__o__wcsdup
0x18000b90f  mov     cs:Block, rax
0x18000b916  test    rax, rax
0x18000b919  jz      loc_18000BA81
0x18000b91f  xor     edx, edx
0x18000b921  xor     ecx, ecx
0x18000b923  xor     ebx, ebx
0x18000b925  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000b92a  xorps   xmm0, xmm0
0x18000b92d  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x18000b934  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x18000b93c  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000b946  lea     rdx, ServiceHandler; lpHandlerProc
0x18000b94d  mov     rcx, [rdi]; lpServiceName
0x18000b950  xor     r8d, r8d; lpContext
0x18000b953  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000b959  mov     cs:hServiceStatus, rax
0x18000b960  test    rax, rax
0x18000b963  jz      loc_18000BA67
0x18000b969  xor     edx, edx; unsigned int
0x18000b96b  lea     ecx, [rbx+2]; unsigned int
0x18000b96e  lea     r8d, [rbx+32h]; unsigned int
0x18000b972  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000b977  xor     r9d, r9d; lpName
0x18000b97a  xor     r8d, r8d; bInitialState
0x18000b97d  xor     edx, edx; bManualReset
0x18000b97f  xor     ecx, ecx; lpEventAttributes
0x18000b981  call    cs:__imp_CreateEventW
0x18000b987  mov     cs:hObject, rax
0x18000b98e  test    rax, rax
0x18000b991  jz      loc_18000BA52
0x18000b997  mov     rdx, rdi; unsigned __int16 **
0x18000b99a  mov     ecx, esi; unsigned int
0x18000b99c  call    ?InitializeService@@YAJKQEAPEAG@Z; InitializeService(ulong,ushort * * const)
0x18000b9a1  mov     ebx, eax
0x18000b9a3  test    eax, eax
0x18000b9a5  js      loc_18000BA38
0x18000b9ab  or      cs:ServiceStatus.dwControlsAccepted, 1
0x18000b9b2  xor     edx, edx; unsigned int
0x18000b9b4  xor     r8d, r8d; unsigned int
0x18000b9b7  lea     ecx, [rdx+4]; unsigned int
0x18000b9ba  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000b9bf  xor     edx, edx
0x18000b9c1  lea     ecx, [rdx+1]
0x18000b9c4  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000b9c9  mov     rax, cs:qword_180018638
0x18000b9d0  test    rax, rax
0x18000b9d3  jz      short loc_18000B9E0
0x18000b9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9da  mov     ebx, eax
0x18000b9dc  test    eax, eax
0x18000b9de  js      short loc_18000BA31
0x18000b9e0  mov     rax, cs:qword_180018668
0x18000b9e7  lea     r9, StopService
0x18000b9ee  mov     r8, cs:hObject
0x18000b9f5  lea     rcx, WaitHandle
0x18000b9fc  mov     rdx, cs:Block
0x18000ba03  mov     [rsp+48h+var_20], 8
0x18000ba0b  mov     rax, [rax+0C0h]
0x18000ba12  mov     [rsp+48h+var_28], 0
0x18000ba1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba20  mov     ebx, eax
0x18000ba22  test    eax, eax
0x18000ba24  jz      short loc_18000BAA0
0x18000ba26  jle     short loc_18000BA31
0x18000ba28  movzx   ebx, ax
0x18000ba2b  or      ebx, 80070000h
0x18000ba31  mov     ecx, ebx; int
0x18000ba33  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x18000ba38  mov     rcx, cs:hObject; hObject
0x18000ba3f  call    cs:__imp_CloseHandle
0x18000ba45  mov     cs:hObject, 0
0x18000ba50  jmp     short loc_18000BA67
0x18000ba52  call    cs:__imp_GetLastError
0x18000ba58  mov     ebx, eax
0x18000ba5a  test    eax, eax
0x18000ba5c  jle     short loc_18000BA67
0x18000ba5e  movzx   ebx, ax
0x18000ba61  or      ebx, 80070000h
0x18000ba67  mov     rcx, cs:Block; Block
0x18000ba6e  call    cs:__imp_free
0x18000ba74  mov     cs:Block, 0
0x18000ba7f  jmp     short loc_18000BA86
0x18000ba81  mov     ebx, 8007000Eh
0x18000ba86  mov     edx, ebx
0x18000ba88  mov     ecx, 3
0x18000ba8d  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000ba92  xor     r8d, r8d; unsigned int
0x18000ba95  mov     edx, ebx; unsigned int
0x18000ba97  lea     ecx, [r8+1]; unsigned int
0x18000ba9b  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000baa0  mov     rbx, [rsp+48h+arg_0]
0x18000baa5  mov     rsi, [rsp+48h+arg_8]
0x18000baaa  add     rsp, 40h
0x18000baae  pop     rdi
0x18000baaf  retn
```
