# DetermineIISResetState(SC_HANDLE__ *,IISRESET_ACTION *)

- ea: `0x180024db4`
- end: `0x1800250a6`
- name: `?DetermineIISResetState@@YAJPEAUSC_HANDLE__@@PEAW4IISRESET_ACTION@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(SC_HANDLE hService, enum IISRESET_ACTION *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024bf8`

## callees

- `0x180002da0`
- `0x1800034f0`
- `0x180008000`
- `0x180024db4`
- `0x1800255b4`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180025013`
- `msvcrt!_wcslwr` at `0x180025013`
- `msvcrt!wcsstr` at `0x18002502a`
- `msvcrt!wcsstr` at `0x180025046`
- `msvcrt!wcsstr` at `0x18002502a`
- `msvcrt!wcsstr` at `0x180025046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024f04`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180024e52`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180024ef0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180024e52`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x180024ef0`

## string_xrefs

- `0x180024f80`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180024ff8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\adminmonitor.cxx`
- `0x180024ec5`: `Failed to resize the buffer to the appropriate size, hr = %08x attempted size = %d\n`
- `0x180024f36`: `( 1 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n`
- `0x180024f67`: `( 2 ) Failed to query the IISAdmin service config, hr = %08x bytes needed = %d\n`

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
0x180024db4  mov     [rsp-8+arg_10], rbx
0x180024db9  push    rbp
0x180024dba  push    rsi
0x180024dbb  push    rdi
0x180024dbc  push    r14
0x180024dbe  push    r15
0x180024dc0  lea     rbp, [rsp-90h]
0x180024dc8  sub     rsp, 190h
0x180024dcf  mov     rax, cs:__security_cookie
0x180024dd6  xor     rax, rsp
0x180024dd9  mov     [rbp+0B0h+var_30], rax
0x180024de0  mov     r15, rdx
0x180024de3  mov     r14, rcx
0x180024de6  xor     edx, edx; Val
0x180024de8  lea     rcx, [rbp+0B0h+var_12F]; void *
0x180024dec  mov     r8d, 0FFh; Size
0x180024df2  call    memset_0
0x180024df7  mov     [rbp+0B0h+Buffer], 0
0x180024dfb  mov     edi, 100h
0x180024e00  mov     [rsp+1B0h+cbBufSize], edi
0x180024e04  lea     rax, [rbp+0B0h+Buffer]
0x180024e08  mov     [rsp+1B0h+lpBuffer], rax
0x180024e0d  mov     [rsp+1B0h+var_13C], di
0x180024e12  mov     [rsp+1B0h+var_170], 0
0x180024e1a  test    r14, r14
0x180024e1d  jz      loc_180025070
0x180024e23  test    r15, r15
0x180024e26  jz      loc_180025070
0x180024e2c  xor     ebx, ebx
0x180024e2e  call    ?IsIISResetEnabled@@YAHXZ; IsIISResetEnabled(void)
0x180024e33  test    eax, eax
0x180024e35  jz      loc_18002505D
0x180024e3b  lea     rax, [rsp+1B0h+var_170]
0x180024e40  mov     r9d, edi; cbBufSize
0x180024e43  lea     r8, [rbp+0B0h+Buffer]; lpBuffer
0x180024e47  mov     [rsp+1B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180024e4c  lea     edx, [rbx+2]; dwInfoLevel
0x180024e4f  mov     rcx, r14; hService
0x180024e52  call    cs:__imp_QueryServiceConfig2W
0x180024e59  nop     dword ptr [rax+rax+00h]
0x180024e5e  test    eax, eax
0x180024e60  jnz     loc_180024F9E
0x180024e66  xor     edi, edi
0x180024e68  call    cs:__imp_GetLastError
0x180024e6f  nop     dword ptr [rax+rax+00h]
0x180024e74  cmp     eax, 7Ah ; 'z'
0x180024e77  jnz     loc_180024F3F
0x180024e7d  mov     edx, [rsp+1B0h+var_170]; unsigned int
0x180024e81  lea     rcx, [rsp+1B0h+var_168]; this
0x180024e86  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180024e8b  test    al, al
0x180024e8d  jnz     short loc_180024ED1
0x180024e8f  call    cs:__imp_GetLastError
0x180024e96  nop     dword ptr [rax+rax+00h]
0x180024e9b  mov     ebx, eax
0x180024e9d  test    eax, eax
0x180024e9f  jle     short loc_180024EAA
0x180024ea1  movzx   ebx, ax
0x180024ea4  or      ebx, 80070000h
0x180024eaa  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180024eb1  jz      loc_180024F91
0x180024eb7  mov     eax, [rsp+1B0h+var_170]
0x180024ebb  mov     r8d, 22Fh
0x180024ec1  mov     [rsp+1B0h+var_180], eax
0x180024ec5  lea     rax, aFailedToResize; "Failed to resize the buffer to the appr"...
0x180024ecc  jmp     loc_180024F6E
0x180024ed1  mov     rsi, [rsp+1B0h+lpBuffer]
0x180024ed6  lea     rax, [rsp+1B0h+var_170]
0x180024edb  mov     r9d, [rsp+1B0h+cbBufSize]; cbBufSize
0x180024ee0  mov     r8, rsi; lpBuffer
0x180024ee3  mov     edx, 2; dwInfoLevel
0x180024ee8  mov     [rsp+1B0h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180024eed  mov     rcx, r14; hService
0x180024ef0  call    cs:__imp_QueryServiceConfig2W
0x180024ef7  nop     dword ptr [rax+rax+00h]
0x180024efc  test    eax, eax
0x180024efe  jnz     loc_180024FA2
0x180024f04  call    cs:__imp_GetLastError
0x180024f0b  nop     dword ptr [rax+rax+00h]
0x180024f10  mov     ebx, eax
0x180024f12  test    eax, eax
0x180024f14  jle     short loc_180024F1F
0x180024f16  movzx   ebx, ax
0x180024f19  or      ebx, 80070000h
0x180024f1f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180024f26  jz      short loc_180024F91
0x180024f28  mov     eax, [rsp+1B0h+var_170]
0x180024f2c  mov     r8d, 241h
0x180024f32  mov     [rsp+1B0h+var_180], eax
0x180024f36  lea     rax, a1FailedToQuery; "( 1 ) Failed to query the IISAdmin serv"...
0x180024f3d  jmp     short loc_180024F6E
0x180024f3f  test    eax, eax
0x180024f41  jg      short loc_180024F47
0x180024f43  mov     ebx, eax
0x180024f45  jmp     short loc_180024F50
0x180024f47  movzx   ebx, ax
0x180024f4a  or      ebx, 80070000h
0x180024f50  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180024f57  jz      short loc_180024F91
0x180024f59  mov     eax, [rsp+1B0h+var_170]
0x180024f5d  mov     r8d, 24Eh; unsigned int
0x180024f63  mov     [rsp+1B0h+var_180], eax
0x180024f67  lea     rax, a2FailedToQuery; "( 2 ) Failed to query the IISAdmin serv"...
0x180024f6e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180024f75  lea     r9, aDetermineiisre; "DetermineIISResetState"
0x180024f7c  mov     dword ptr [rsp+1B0h+var_188], ebx; char
0x180024f80  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180024f87  mov     [rsp+1B0h+pcbBytesNeeded], rax; char *
0x180024f8c  call    PuDbgPrint
0x180024f91  test    ebx, ebx
0x180024f93  js      loc_180025062
0x180024f99  jmp     loc_18002505F
0x180024f9e  lea     rsi, [rbp+0B0h+Buffer]
0x180024fa2  xor     edx, edx
0x180024fa4  cmp     edx, [rsi+18h]
0x180024fa7  jnb     loc_18002505D
0x180024fad  mov     rax, [rsi+20h]
0x180024fb1  cmp     dword ptr [rax+rdx*8], 3
0x180024fb5  jz      short loc_180024FBB
0x180024fb7  inc     edx
0x180024fb9  jmp     short loc_180024FA4
0x180024fbb  mov     rdx, [rsi+10h]
0x180024fbf  test    rdx, rdx
0x180024fc2  jz      loc_18002505D
0x180024fc8  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180024fce  test    al, 3
0x180024fd0  setnz   cl
0x180024fd3  bt      eax, 1Bh
0x180024fd7  setb    al
0x180024fda  test    al, cl
0x180024fdc  jz      short loc_18002500F
0x180024fde  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180024fe5  lea     rax, aIisadminPfailu; "IISAdmin pFailureActions = %S \n "
0x180024fec  mov     qword ptr [rsp+1B0h+var_188], rdx; char
0x180024ff1  lea     r9, aDetermineiisre; "DetermineIISResetState"
0x180024ff8  lea     rdx, aServercommonIn_7; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180024fff  mov     [rsp+1B0h+pcbBytesNeeded], rax; char *
0x180025004  mov     r8d, 276h; unsigned int
0x18002500a  call    PuDbgPrint
0x18002500f  mov     rcx, [rsi+10h]; String
0x180025013  call    cs:__imp__wcslwr
0x18002501a  nop     dword ptr [rax+rax+00h]
0x18002501f  mov     rcx, [rsi+10h]; Str
0x180025023  lea     rdx, aIisreset; "iisreset"
0x18002502a  call    cs:__imp_wcsstr
0x180025031  nop     dword ptr [rax+rax+00h]
0x180025036  test    rax, rax
0x180025039  jz      short loc_18002505D
0x18002503b  mov     rcx, [rsi+10h]; Str
0x18002503f  lea     rdx, aStart; "/start"
0x180025046  call    cs:__imp_wcsstr
0x18002504d  nop     dword ptr [rax+rax+00h]
0x180025052  neg     rax
0x180025055  sbb     edi, edi
0x180025057  neg     edi
0x180025059  inc     edi
0x18002505b  jmp     short loc_18002505F
0x18002505d  xor     edi, edi
0x18002505f  mov     [r15], edi
0x180025062  lea     rcx, [rsp+1B0h+var_168]; this
0x180025067  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002506c  mov     eax, ebx
0x18002506e  jmp     short loc_18002507F
0x180025070  lea     rcx, [rsp+1B0h+var_168]; this
0x180025075  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002507a  mov     eax, 80070057h
0x18002507f  mov     rcx, [rbp+0B0h+var_30]
0x180025086  xor     rcx, rsp; StackCookie
0x180025089  call    __security_check_cookie
0x18002508e  mov     rbx, [rsp+1B0h+arg_10]
0x180025096  add     rsp, 190h
0x18002509d  pop     r15
0x18002509f  pop     r14
0x1800250a1  pop     rdi
0x1800250a2  pop     rsi
0x1800250a3  pop     rbp
0x1800250a4  retn
```
