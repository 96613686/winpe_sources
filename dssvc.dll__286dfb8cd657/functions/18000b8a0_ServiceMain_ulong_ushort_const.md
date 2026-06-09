# ServiceMain(ulong,ushort * * const)

- ea: `0x18000b8a0`
- end: `0x18000ba51`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `433`
- prototype: `void __fastcall(int, const wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000b700`
- `0x18000b8a0`
- `0x18000bbb8`
- `0x18000bc50`
- `0x18001c010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18000b8c9`
- `msvcrt!_wcsdup` at `0x18000b8c9`
- `msvcrt!free` at `0x18000ba1b`
- `msvcrt!free` at `0x18000ba1b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b93a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000b93a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b9ec`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b90a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000b90a`

## pseudocode

```c
void __fastcall ServiceMain(int a1, const wchar_t **a2)
{
  signed int v4; // ebx
  int v5; // ecx
  int v6; // eax
  signed int LastError; // eax

  ServiceStatus.dwControlsAccepted = 0;
  if ( a1 )
  {
    Block = _wcsdup(*a2);
    if ( Block )
    {
      ServiceStatus.dwServiceType = 32;
      *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
      v4 = 0;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
      if ( hServiceStatus )
      {
        SvcFrameworkUpdateServiceStatus(2u, 0, 0x2710u);
        hObject = CreateEventW(0, 0, 0, 0);
        if ( hObject )
        {
          v4 = InitializeService(a1, (unsigned __int16 **const)a2);
          if ( v4 >= 0 )
          {
            ServiceStatus.dwControlsAccepted |= 1u;
            SvcFrameworkUpdateServiceStatus(4u, 0, 0);
            if ( !qword_18002B200 || (v4 = qword_18002B200(), v4 >= 0) )
            {
              v6 = (*(__int64 (__fastcall **)(HANDLE *, void *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18002B230 + 192))(
                     &WaitHandle,
                     Block,
                     hObject,
                     StopService,
                     0,
                     8);
              v4 = v6;
              if ( !v6 )
                return;
              if ( v6 > 0 )
                v4 = (unsigned __int16)v6 | 0x80070000;
            }
            UninitializeService(v5);
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
    SvcFrameworkUpdateServiceStatus(1u, v4, 0);
  }
}

```

## disassembly

```asm
0x18000b8a0  mov     [rsp+arg_0], rbx
0x18000b8a5  mov     [rsp+arg_8], rsi
0x18000b8aa  push    rdi
0x18000b8ab  sub     rsp, 40h
0x18000b8af  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18000b8b9  mov     rdi, rdx
0x18000b8bc  mov     esi, ecx
0x18000b8be  test    ecx, ecx
0x18000b8c0  jz      loc_18000BA41
0x18000b8c6  mov     rcx, [rdx]; String
0x18000b8c9  call    cs:__imp__wcsdup
0x18000b8cf  mov     cs:Block, rax
0x18000b8d6  test    rax, rax
0x18000b8d9  jz      loc_18000BA2E
0x18000b8df  xorps   xmm0, xmm0
0x18000b8e2  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18000b8ec  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x18000b8f4  xor     ebx, ebx
0x18000b8f6  lea     rdx, ServiceHandler; lpHandlerProc
0x18000b8fd  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x18000b904  xor     r8d, r8d; lpContext
0x18000b907  mov     rcx, [rdi]; lpServiceName
0x18000b90a  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000b910  mov     cs:hServiceStatus, rax
0x18000b917  test    rax, rax
0x18000b91a  jz      loc_18000BA14
0x18000b920  xor     edx, edx; unsigned int
0x18000b922  lea     ecx, [rbx+2]; unsigned int
0x18000b925  mov     r8d, 2710h; unsigned int
0x18000b92b  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000b930  xor     r9d, r9d; lpName
0x18000b933  xor     r8d, r8d; bInitialState
0x18000b936  xor     edx, edx; bManualReset
0x18000b938  xor     ecx, ecx; lpEventAttributes
0x18000b93a  call    cs:__imp_CreateEventW
0x18000b940  mov     cs:hObject, rax
0x18000b947  test    rax, rax
0x18000b94a  jz      loc_18000B9FF
0x18000b950  mov     rdx, rdi; unsigned __int16 **
0x18000b953  mov     ecx, esi; unsigned int
0x18000b955  call    ?InitializeService@@YAJKQEAPEAG@Z; InitializeService(ulong,ushort * * const)
0x18000b95a  mov     ebx, eax
0x18000b95c  test    eax, eax
0x18000b95e  js      loc_18000B9E5
0x18000b964  or      cs:ServiceStatus.dwControlsAccepted, 1
0x18000b96b  xor     edx, edx; unsigned int
0x18000b96d  xor     r8d, r8d; unsigned int
0x18000b970  lea     ecx, [rdx+4]; unsigned int
0x18000b973  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000b978  mov     rax, cs:qword_18002B200
0x18000b97f  test    rax, rax
0x18000b982  jz      short loc_18000B98F
0x18000b984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b989  mov     ebx, eax
0x18000b98b  test    eax, eax
0x18000b98d  js      short loc_18000B9E0
0x18000b98f  mov     rax, cs:qword_18002B230
0x18000b996  lea     r9, StopService
0x18000b99d  mov     r8, cs:hObject
0x18000b9a4  lea     rcx, WaitHandle
0x18000b9ab  mov     rdx, cs:Block
0x18000b9b2  mov     [rsp+48h+var_20], 8
0x18000b9ba  mov     rax, [rax+0C0h]
0x18000b9c1  mov     [rsp+48h+var_28], 0
0x18000b9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9cf  mov     ebx, eax
0x18000b9d1  test    eax, eax
0x18000b9d3  jz      short loc_18000BA41
0x18000b9d5  jle     short loc_18000B9E0
0x18000b9d7  movzx   ebx, ax
0x18000b9da  or      ebx, 80070000h
0x18000b9e0  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x18000b9e5  mov     rcx, cs:hObject; hObject
0x18000b9ec  call    cs:__imp_CloseHandle
0x18000b9f2  mov     cs:hObject, 0
0x18000b9fd  jmp     short loc_18000BA14
0x18000b9ff  call    cs:__imp_GetLastError
0x18000ba05  mov     ebx, eax
0x18000ba07  test    eax, eax
0x18000ba09  jle     short loc_18000BA14
0x18000ba0b  movzx   ebx, ax
0x18000ba0e  or      ebx, 80070000h
0x18000ba14  mov     rcx, cs:Block; Block
0x18000ba1b  call    cs:__imp_free
0x18000ba21  mov     cs:Block, 0
0x18000ba2c  jmp     short loc_18000BA33
0x18000ba2e  mov     ebx, 8007000Eh
0x18000ba33  xor     r8d, r8d; unsigned int
0x18000ba36  mov     edx, ebx; unsigned int
0x18000ba38  lea     ecx, [r8+1]; unsigned int
0x18000ba3c  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18000ba41  mov     rbx, [rsp+48h+arg_0]
0x18000ba46  mov     rsi, [rsp+48h+arg_8]
0x18000ba4b  add     rsp, 40h
0x18000ba4f  pop     rdi
0x18000ba50  retn
```
