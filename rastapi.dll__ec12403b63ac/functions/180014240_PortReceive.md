# PortReceive

- ea: `0x180014240`
- end: `0x1800143bc`
- name: `PortReceive`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c918`
- `0x18000d92c`
- `0x180012340`
- `0x180014240`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180014286`
- `msvcrt!_stricmp` at `0x180014286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001439e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014324`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001439e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800142d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001434f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014394`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800142d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001434f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014394`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001431a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001431a`
- `api-ms-win-core-comm-l1-1-0!SetCommTimeouts` at `0x1800142ad`
- `api-ms-win-core-comm-l1-1-0!SetCommTimeouts` at `0x1800142ad`

## string_xrefs

- `0x1800142c4`: `PorTReceive: SetCommTimeouts failed for %s. %d`

## pseudocode

```c
__int64 __fastcall PortReceive(__int64 a1, void *a2, __int64 a3, __int64 a4)
{
  DWORD v4; // ebp
  DWORD v5; // esi
  void *v8; // rcx
  DWORD LastError; // edi
  DWORD v11; // ebx
  _DWORD *v12; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-58h] BYREF
  _COMMTIMEOUTS CommTimeouts; // [rsp+38h] [rbp-50h] BYREF

  memset(&CommTimeouts, 0, sizeof(CommTimeouts));
  v4 = a4;
  NumberOfBytesRead = 0;
  v5 = a3;
  GetMutex(a1, a2, a3, a4);
  if ( !_stricmp((const char *)(a1 + 64), "MODEM") )
  {
    v8 = *(void **)(a1 + 888);
    *(_QWORD *)&CommTimeouts.ReadIntervalTimeout = 0;
    CommTimeouts.ReadTotalTimeoutConstant = v4;
    if ( !SetCommTimeouts(v8, &CommTimeouts) )
    {
      LastError = GetLastError();
      RasTapiTrace("PorTReceive: SetCommTimeouts failed for %s. %d");
      if ( !ReleaseMutex(RasTapiMutex) )
        GetLastError();
      RasTapiTrace(" ");
      return LastError;
    }
    if ( !ReadFile(*(HANDLE *)(a1 + 888), a2, v5, &NumberOfBytesRead, (LPOVERLAPPED)(a1 + 896)) )
    {
      v11 = GetLastError();
      if ( v11 != 997 )
        goto LABEL_18;
    }
    goto LABEL_16;
  }
  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 216) + 32LL) )
  {
    v11 = 0;
    goto LABEL_18;
  }
  if ( *(_DWORD *)(a1 + 56) == 3 )
  {
    v12 = *(_DWORD **)(a1 + 1168);
    *(_QWORD *)(a1 + 1152) = a2;
    *(_DWORD *)(a1 + 1160) = v5;
    if ( *v12 )
      PostNotificationCompletion(a1);
LABEL_16:
    v11 = 600;
LABEL_18:
    if ( !ReleaseMutex(RasTapiMutex) )
      GetLastError();
    return v11;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return 0;
}

```

## disassembly

```asm
0x180014240  push    rbx
0x180014242  push    rbp
0x180014243  push    rsi
0x180014244  push    rdi
0x180014245  sub     rsp, 68h
0x180014249  mov     rax, cs:__security_cookie
0x180014250  xor     rax, rsp
0x180014253  mov     [rsp+88h+var_38], rax
0x180014258  xor     eax, eax
0x18001425a  xorps   xmm0, xmm0
0x18001425d  movups  xmmword ptr [rsp+88h+CommTimeouts.ReadIntervalTimeout], xmm0
0x180014262  mov     [rsp+88h+CommTimeouts.WriteTotalTimeoutConstant], eax
0x180014266  mov     ebp, r9d
0x180014269  mov     [rsp+88h+NumberOfBytesRead], eax
0x18001426d  mov     esi, r8d
0x180014270  mov     rdi, rdx
0x180014273  mov     rbx, rcx
0x180014276  call    GetMutex
0x18001427b  lea     rcx, [rbx+40h]; String1
0x18001427f  lea     rdx, aModem; "MODEM"
0x180014286  call    cs:__imp__stricmp
0x18001428c  test    eax, eax
0x18001428e  jnz     loc_180014335
0x180014294  mov     rcx, [rbx+378h]; hFile
0x18001429b  lea     rdx, [rsp+88h+CommTimeouts]; lpCommTimeouts
0x1800142a0  mov     qword ptr [rsp+88h+CommTimeouts.ReadIntervalTimeout], 0
0x1800142a9  mov     [rsp+88h+CommTimeouts.ReadTotalTimeoutConstant], ebp
0x1800142ad  call    cs:__imp_SetCommTimeouts
0x1800142b3  test    eax, eax
0x1800142b5  jnz     short loc_1800142FC
0x1800142b7  call    cs:__imp_GetLastError
0x1800142bd  mov     r8d, eax
0x1800142c0  lea     rdx, [rbx+18h]
0x1800142c4  lea     rcx, aPortreceiveSet; "PorTReceive: SetCommTimeouts failed for"...
0x1800142cb  mov     edi, eax
0x1800142cd  call    RasTapiTrace
0x1800142d2  mov     rcx, cs:RasTapiMutex; hMutex
0x1800142d9  call    cs:__imp_ReleaseMutex
0x1800142df  test    eax, eax
0x1800142e1  jnz     short loc_1800142E9
0x1800142e3  call    cs:__imp_GetLastError
0x1800142e9  lea     rcx, asc_18002C0B8; " "
0x1800142f0  call    RasTapiTrace
0x1800142f5  mov     eax, edi
0x1800142f7  jmp     loc_1800143A6
0x1800142fc  mov     rcx, [rbx+378h]; hFile
0x180014303  lea     rax, [rbx+380h]
0x18001430a  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001430f  mov     [rsp+88h+lpOverlapped], rax; lpOverlapped
0x180014314  mov     r8d, esi; nNumberOfBytesToRead
0x180014317  mov     rdx, rdi; lpBuffer
0x18001431a  call    cs:__imp_ReadFile
0x180014320  test    eax, eax
0x180014322  jnz     short loc_180014384
0x180014324  call    cs:__imp_GetLastError
0x18001432a  mov     ebx, eax
0x18001432c  cmp     eax, 3E5h
0x180014331  jnz     short loc_18001438D
0x180014333  jmp     short loc_180014384
0x180014335  mov     rax, [rbx+0D8h]
0x18001433c  cmp     dword ptr [rax+20h], 0
0x180014340  jz      short loc_18001438B
0x180014342  cmp     dword ptr [rbx+38h], 3
0x180014346  jz      short loc_180014363
0x180014348  mov     rcx, cs:RasTapiMutex; hMutex
0x18001434f  call    cs:__imp_ReleaseMutex
0x180014355  test    eax, eax
0x180014357  jnz     short loc_18001435F
0x180014359  call    cs:__imp_GetLastError
0x18001435f  xor     eax, eax
0x180014361  jmp     short loc_1800143A6
0x180014363  mov     rax, [rbx+490h]
0x18001436a  mov     [rbx+480h], rdi
0x180014371  mov     [rbx+488h], esi
0x180014377  cmp     dword ptr [rax], 0
0x18001437a  jbe     short loc_180014384
0x18001437c  mov     rcx, rbx
0x18001437f  call    PostNotificationCompletion
0x180014384  mov     ebx, 258h
0x180014389  jmp     short loc_18001438D
0x18001438b  xor     ebx, ebx
0x18001438d  mov     rcx, cs:RasTapiMutex; hMutex
0x180014394  call    cs:__imp_ReleaseMutex
0x18001439a  test    eax, eax
0x18001439c  jnz     short loc_1800143A4
0x18001439e  call    cs:__imp_GetLastError
0x1800143a4  mov     eax, ebx
0x1800143a6  mov     rcx, [rsp+88h+var_38]
0x1800143ab  xor     rcx, rsp; StackCookie
0x1800143ae  call    __security_check_cookie
0x1800143b3  add     rsp, 68h
0x1800143b7  pop     rdi
0x1800143b8  pop     rsi
0x1800143b9  pop     rbp
0x1800143ba  pop     rbx
0x1800143bb  retn
```
