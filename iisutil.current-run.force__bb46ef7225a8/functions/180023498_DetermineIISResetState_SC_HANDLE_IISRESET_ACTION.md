# DetermineIISResetState(SC_HANDLE__ *,IISRESET_ACTION *)

- ea: `0x180023498`
- end: `0x180023759`
- name: `?DetermineIISResetState@@YAJPEAUSC_HANDLE__@@PEAW4IISRESET_ACTION@@@Z`
- size: `705`
- prototype: `__int64 __fastcall(SC_HANDLE hService, enum IISRESET_ACTION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023308`

## callees

- `0x180002470`
- `0x180002b60`
- `0x180007300`
- `0x180023498`
- `0x180023bf0`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!_wcslwr` at `0x1800236d9`
- `msvcrt!_wcslwr` at `0x1800236d9`
- `msvcrt!wcsstr` at `0x1800236ea`
- `msvcrt!wcsstr` at `0x180023700`
- `msvcrt!wcsstr` at `0x1800236ea`
- `msvcrt!wcsstr` at `0x180023700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800235d0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180023536`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800235c2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180023536`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x1800235c2`

## string_xrefs

- `0x180023646`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x1800236be`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180023597`: `Failed to resize the buffer to the appropriate size, hr = %08x attempted size = %d\n`
- `0x1800235fc`: `( 1 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n`
- `0x18002362d`: `( 2 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n`

## pseudocode

```c
__int64 __fastcall DetermineIISResetState(SC_HANDLE hService, enum IISRESET_ACTION *a2)
{
  signed int v4; // ebx
  int v5; // edi
  signed int LastError; // eax
  signed int v7; // eax
  unsigned int v8; // r8d
  char *v9; // rax
  BYTE *p_Buffer; // rsi
  signed int v11; // eax
  __int64 i; // rdx
  DWORD pcbBytesNeeded; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPBYTE lpBuffer; // [rsp+68h] [rbp-98h]
  DWORD cbBufSize; // [rsp+70h] [rbp-90h]
  __int16 v18; // [rsp+74h] [rbp-8Ch]
  BYTE Buffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[255]; // [rsp+81h] [rbp-7Fh] BYREF

  memset_0(v20, 0, sizeof(v20));
  Buffer = 0;
  cbBufSize = 256;
  lpBuffer = &Buffer;
  v18 = 256;
  pcbBytesNeeded = 0;
  if ( hService && a2 )
  {
    v4 = 0;
    if ( (unsigned int)IsIISResetEnabled() )
    {
      if ( QueryServiceConfig2W(hService, 2u, &Buffer, 0x100u, &pcbBytesNeeded) )
      {
        p_Buffer = &Buffer;
      }
      else
      {
        v5 = 0;
        LastError = GetLastError();
        if ( LastError != 122 )
        {
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          else
            v4 = LastError;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          {
            v8 = 590;
            v9 = "( 2 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n";
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        if ( !BUFFER::Resize((BUFFER *)v15, pcbBytesNeeded) )
        {
          v7 = GetLastError();
          v4 = v7;
          if ( v7 > 0 )
            v4 = (unsigned __int16)v7 | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          {
            v8 = 559;
            v9 = "Failed to resize the buffer to the appropriate size, hr = %08x attempted size = %d\n";
LABEL_21:
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
              v8,
              "DetermineIISResetState",
              v9,
              v4);
            goto LABEL_22;
          }
          goto LABEL_22;
        }
        p_Buffer = lpBuffer;
        if ( !QueryServiceConfig2W(hService, 2u, lpBuffer, cbBufSize, &pcbBytesNeeded) )
        {
          v11 = GetLastError();
          v4 = v11;
          if ( v11 > 0 )
            v4 = (unsigned __int16)v11 | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          {
            v8 = 577;
            v9 = "( 1 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n";
            goto LABEL_21;
          }
LABEL_22:
          if ( v4 < 0 )
          {
LABEL_36:
            BUFFER::~BUFFER((BUFFER *)v15);
            return (unsigned int)v4;
          }
LABEL_35:
          *(_DWORD *)a2 = v5;
          goto LABEL_36;
        }
      }
      for ( i = 0; (unsigned int)i < *((_DWORD *)p_Buffer + 6); i = (unsigned int)(i + 1) )
      {
        if ( *(_DWORD *)(*((_QWORD *)p_Buffer + 4) + 8 * i) == 3 )
        {
          if ( *((_QWORD *)p_Buffer + 2) )
          {
            if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x8000000) != 0 )
              PuDbgPrint(
                (struct _DEBUG_PRINTS *)g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\adminmonitor.cxx",
                0x276u,
                "DetermineIISResetState",
                "IISAdmin pFailureActions = %S \n ",
                *((_QWORD *)p_Buffer + 2));
            _wcslwr(*((wchar_t **)p_Buffer + 2));
            if ( wcsstr(*((const wchar_t **)p_Buffer + 2), L"iisreset") )
            {
              v5 = (wcsstr(*((const wchar_t **)p_Buffer + 2), L"/start") != 0) + 1;
              goto LABEL_35;
            }
          }
          break;
        }
      }
    }
    v5 = 0;
    goto LABEL_35;
  }
  BUFFER::~BUFFER((BUFFER *)v15);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180023498  mov     [rsp-8+arg_10], rbx
0x18002349d  push    rbp
0x18002349e  push    rsi
0x18002349f  push    rdi
0x1800234a0  push    r14
0x1800234a2  push    r15
0x1800234a4  lea     rbp, [rsp-90h]
0x1800234ac  sub     rsp, 190h
0x1800234b3  mov     rax, cs:__security_cookie
0x1800234ba  xor     rax, rsp
0x1800234bd  mov     [rbp+0B0h+var_30], rax
0x1800234c4  mov     r15, rdx
0x1800234c7  mov     r14, rcx
0x1800234ca  xor     edx, edx; Val
0x1800234cc  lea     rcx, [rbp+0B0h+var_12F]; void *
0x1800234d0  mov     r8d, 0FFh; Size
0x1800234d6  call    memset_0
0x1800234db  mov     [rbp+0B0h+Buffer], 0
0x1800234df  mov     edi, 100h
0x1800234e4  mov     [rsp+1B0h+cbBufSize], edi
0x1800234e8  lea     rax, [rbp+0B0h+Buffer]
0x1800234ec  mov     [rsp+1B0h+lpBuffer], rax
0x1800234f1  mov     [rsp+1B0h+var_13C], di
0x1800234f6  mov     [rsp+1B0h+var_170], 0
0x1800234fe  test    r14, r14
0x180023501  jz      loc_180023724
0x180023507  test    r15, r15
0x18002350a  jz      loc_180023724
0x180023510  xor     ebx, ebx
0x180023512  call    ?IsIISResetEnabled@@YAHXZ; IsIISResetEnabled(void)
0x180023517  test    eax, eax
0x180023519  jz      loc_180023711
0x18002351f  lea     rax, [rsp+1B0h+var_170]
0x180023524  mov     r9d, edi; cbBufSize
0x180023527  lea     r8, [rbp+0B0h+Buffer]; lpBuffer
0x18002352b  mov     [rsp+1B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180023530  lea     edx, [rbx+2]; dwInfoLevel
0x180023533  mov     rcx, r14; hService
0x180023536  call    cs:__imp_QueryServiceConfig2W
0x18002353c  test    eax, eax
0x18002353e  jnz     loc_180023664
0x180023544  xor     edi, edi
0x180023546  call    cs:__imp_GetLastError
0x18002354c  cmp     eax, 7Ah ; 'z'
0x18002354f  jnz     loc_180023605
0x180023555  mov     edx, [rsp+1B0h+var_170]; unsigned int
0x180023559  lea     rcx, [rsp+1B0h+var_168]; this
0x18002355e  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180023563  test    al, al
0x180023565  jnz     short loc_1800235A3
0x180023567  call    cs:__imp_GetLastError
0x18002356d  mov     ebx, eax
0x18002356f  test    eax, eax
0x180023571  jle     short loc_18002357C
0x180023573  movzx   ebx, ax
0x180023576  or      ebx, 80070000h
0x18002357c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180023583  jz      loc_180023657
0x180023589  mov     eax, [rsp+1B0h+var_170]
0x18002358d  mov     r8d, 22Fh
0x180023593  mov     [rsp+1B0h+var_180], eax
0x180023597  lea     rax, aFailedToResize; "Failed to resize the buffer to the appr"...
0x18002359e  jmp     loc_180023634
0x1800235a3  mov     rsi, [rsp+1B0h+lpBuffer]
0x1800235a8  lea     rax, [rsp+1B0h+var_170]
0x1800235ad  mov     r9d, [rsp+1B0h+cbBufSize]; cbBufSize
0x1800235b2  mov     r8, rsi; lpBuffer
0x1800235b5  mov     edx, 2; dwInfoLevel
0x1800235ba  mov     [rsp+1B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800235bf  mov     rcx, r14; hService
0x1800235c2  call    cs:__imp_QueryServiceConfig2W
0x1800235c8  test    eax, eax
0x1800235ca  jnz     loc_180023668
0x1800235d0  call    cs:__imp_GetLastError
0x1800235d6  mov     ebx, eax
0x1800235d8  test    eax, eax
0x1800235da  jle     short loc_1800235E5
0x1800235dc  movzx   ebx, ax
0x1800235df  or      ebx, 80070000h
0x1800235e5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800235ec  jz      short loc_180023657
0x1800235ee  mov     eax, [rsp+1B0h+var_170]
0x1800235f2  mov     r8d, 241h
0x1800235f8  mov     [rsp+1B0h+var_180], eax
0x1800235fc  lea     rax, a1FailedToQuery; "( 1 ) Failed to query the IISAdmin serv"...
0x180023603  jmp     short loc_180023634
0x180023605  test    eax, eax
0x180023607  jg      short loc_18002360D
0x180023609  mov     ebx, eax
0x18002360b  jmp     short loc_180023616
0x18002360d  movzx   ebx, ax
0x180023610  or      ebx, 80070000h
0x180023616  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002361d  jz      short loc_180023657
0x18002361f  mov     eax, [rsp+1B0h+var_170]
0x180023623  mov     r8d, 24Eh; unsigned int
0x180023629  mov     [rsp+1B0h+var_180], eax
0x18002362d  lea     rax, a2FailedToQuery; "( 2 ) Failed to query the IISAdmin serv"...
0x180023634  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002363b  lea     r9, aDetermineiisre; "DetermineIISResetState"
0x180023642  mov     dword ptr [rsp+1B0h+var_188], ebx; char
0x180023646  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002364d  mov     [rsp+1B0h+pcbBytesNeeded], rax; char *
0x180023652  call    PuDbgPrint
0x180023657  test    ebx, ebx
0x180023659  js      loc_180023716
0x18002365f  jmp     loc_180023713
0x180023664  lea     rsi, [rbp+0B0h+Buffer]
0x180023668  xor     edx, edx
0x18002366a  cmp     edx, [rsi+18h]
0x18002366d  jnb     loc_180023711
0x180023673  mov     rax, [rsi+20h]
0x180023677  cmp     dword ptr [rax+rdx*8], 3
0x18002367b  jz      short loc_180023681
0x18002367d  inc     edx
0x18002367f  jmp     short loc_18002366A
0x180023681  mov     rdx, [rsi+10h]
0x180023685  test    rdx, rdx
0x180023688  jz      loc_180023711
0x18002368e  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180023694  test    al, 3
0x180023696  setnz   cl
0x180023699  bt      eax, 1Bh
0x18002369d  setb    al
0x1800236a0  test    al, cl
0x1800236a2  jz      short loc_1800236D5
0x1800236a4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800236ab  lea     rax, aIisadminPfailu; "IISAdmin pFailureActions = %S \n "
0x1800236b2  mov     qword ptr [rsp+1B0h+var_188], rdx; char
0x1800236b7  lea     r9, aDetermineiisre; "DetermineIISResetState"
0x1800236be  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800236c5  mov     [rsp+1B0h+pcbBytesNeeded], rax; char *
0x1800236ca  mov     r8d, 276h; unsigned int
0x1800236d0  call    PuDbgPrint
0x1800236d5  mov     rcx, [rsi+10h]; String
0x1800236d9  call    cs:__imp__wcslwr
0x1800236df  mov     rcx, [rsi+10h]; Str
0x1800236e3  lea     rdx, aIisreset; "iisreset"
0x1800236ea  call    cs:__imp_wcsstr
0x1800236f0  test    rax, rax
0x1800236f3  jz      short loc_180023711
0x1800236f5  mov     rcx, [rsi+10h]; Str
0x1800236f9  lea     rdx, aStart; "/start"
0x180023700  call    cs:__imp_wcsstr
0x180023706  neg     rax
0x180023709  sbb     edi, edi
0x18002370b  neg     edi
0x18002370d  inc     edi
0x18002370f  jmp     short loc_180023713
0x180023711  xor     edi, edi
0x180023713  mov     [r15], edi
0x180023716  lea     rcx, [rsp+1B0h+var_168]; this
0x18002371b  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180023720  mov     eax, ebx
0x180023722  jmp     short loc_180023733
0x180023724  lea     rcx, [rsp+1B0h+var_168]; this
0x180023729  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002372e  mov     eax, 80070057h
0x180023733  mov     rcx, [rbp+0B0h+var_30]
0x18002373a  xor     rcx, rsp; StackCookie
0x18002373d  call    __security_check_cookie
0x180023742  mov     rbx, [rsp+1B0h+arg_10]
0x18002374a  add     rsp, 190h
0x180023751  pop     r15
0x180023753  pop     r14
0x180023755  pop     rdi
0x180023756  pop     rsi
0x180023757  pop     rbp
0x180023758  retn
```
