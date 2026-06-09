# NfsService::StartServiceInternal(SC_HANDLE__ *)

- ea: `0x180023574`
- end: `0x1800236c5`
- name: `?StartServiceInternal@NfsService@@AEAAKPEAUSC_HANDLE__@@@Z`
- size: `337`
- prototype: `unsigned int(NfsService *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001323c`
- `0x180013378`

## callees

- `0x180023574`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800235c0`
- `KERNEL32!GetLastError` at `0x180023600`
- `KERNEL32!GetLastError` at `0x180023690`
- `KERNEL32!GetLastError` at `0x1800235c0`
- `KERNEL32!GetLastError` at `0x180023600`
- `KERNEL32!GetLastError` at `0x180023690`
- `KERNEL32!Sleep` at `0x18002364c`
- `KERNEL32!Sleep` at `0x18002364c`
- `KERNEL32!GetTickCount` at `0x180023610`
- `KERNEL32!GetTickCount` at `0x180023679`
- `KERNEL32!GetTickCount` at `0x180023681`
- `KERNEL32!GetTickCount` at `0x180023610`
- `KERNEL32!GetTickCount` at `0x180023679`
- `KERNEL32!GetTickCount` at `0x180023681`
- `ADVAPI32!StartServiceW` at `0x1800235b6`
- `ADVAPI32!StartServiceW` at `0x1800235b6`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800235f6`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002366a`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800235f6`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002366a`

## pseudocode

```c
__int64 __fastcall NfsService::StartServiceInternal(NfsService *this, SC_HANDLE a2)
{
  DWORD v3; // ebx
  DWORD LastError; // eax
  DWORD TickCount; // eax
  unsigned int v7; // edi
  DWORD v8; // esi
  int v9; // ecx
  DWORD v10; // edx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+58h] [rbp-20h]

  pcbBytesNeeded = 0;
  v14 = 0;
  v3 = 0;
  *(_OWORD *)Buffer = 0;
  v13 = 0;
  if ( StartServiceW(a2, 0, 0) )
    goto LABEL_24;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError == 1056 )
    return 0;
  if ( !LastError )
  {
LABEL_24:
    if ( QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) || (v3 = GetLastError()) == 0 )
    {
LABEL_7:
      TickCount = GetTickCount();
      v7 = DWORD1(v13);
      v8 = TickCount;
      while ( 1 )
      {
        v9 = *(_DWORD *)&Buffer[4];
        if ( *(_DWORD *)&Buffer[4] != 2 )
          break;
        v10 = DWORD2(v13) / 0xA;
        if ( DWORD2(v13) / 0xA >= 0x3E8 )
        {
          if ( v10 > 0x2710 )
            v10 = 10000;
        }
        else
        {
          v10 = 1000;
        }
        Sleep(v10);
        if ( !QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
        {
          v3 = GetLastError();
          if ( v3 )
            return v3;
LABEL_18:
          v9 = *(_DWORD *)&Buffer[4];
          break;
        }
        if ( DWORD1(v13) > v7 )
          goto LABEL_7;
        if ( GetTickCount() - v8 > DWORD2(v13) )
          goto LABEL_18;
      }
      if ( v9 != 4 )
        return 1053;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180023574  push    rbp
0x180023576  push    rbx
0x180023577  push    rsi
0x180023578  push    rdi
0x180023579  push    r12
0x18002357b  push    r14
0x18002357d  mov     rbp, rsp
0x180023580  sub     rsp, 78h
0x180023584  mov     rax, cs:__security_cookie
0x18002358b  xor     rax, rsp
0x18002358e  mov     [rbp+var_18], rax
0x180023592  mov     r14, rdx
0x180023595  mov     [rbp+var_48], 0
0x18002359c  xorps   xmm0, xmm0
0x18002359f  xor     eax, eax
0x1800235a1  mov     rcx, r14; hService
0x1800235a4  mov     [rbp+var_20], eax
0x1800235a7  xor     r8d, r8d; lpServiceArgVectors
0x1800235aa  xor     edx, edx; dwNumServiceArgs
0x1800235ac  xor     ebx, ebx
0x1800235ae  movups  xmmword ptr [rbp+Buffer], xmm0
0x1800235b2  movups  [rbp+var_30], xmm0
0x1800235b6  call    cs:__imp_StartServiceW
0x1800235bc  test    eax, eax
0x1800235be  jnz     short loc_1800235DE
0x1800235c0  call    cs:__imp_GetLastError
0x1800235c6  mov     ebx, eax
0x1800235c8  cmp     eax, 420h
0x1800235cd  jnz     short loc_1800235D6
0x1800235cf  xor     eax, eax
0x1800235d1  jmp     loc_1800236AC
0x1800235d6  test    eax, eax
0x1800235d8  jnz     loc_1800236AA
0x1800235de  lea     rax, [rbp+var_48]
0x1800235e2  mov     r9d, 24h ; '$'; cbBufSize
0x1800235e8  lea     r8, [rbp+Buffer]; lpBuffer
0x1800235ec  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800235f1  xor     edx, edx; InfoLevel
0x1800235f3  mov     rcx, r14; hService
0x1800235f6  call    cs:__imp_QueryServiceStatusEx
0x1800235fc  test    eax, eax
0x1800235fe  jnz     short loc_180023610
0x180023600  call    cs:__imp_GetLastError
0x180023606  mov     ebx, eax
0x180023608  test    eax, eax
0x18002360a  jnz     loc_1800236AA
0x180023610  call    cs:__imp_GetTickCount
0x180023616  mov     r12d, 2710h
0x18002361c  mov     edi, dword ptr [rbp+var_30+4]
0x18002361f  mov     esi, eax
0x180023621  mov     ecx, dword ptr [rbp+Buffer+4]
0x180023624  cmp     ecx, 2
0x180023627  jnz     short loc_18002369F
0x180023629  mov     eax, 0CCCCCCCDh
0x18002362e  mul     dword ptr [rbp+var_30+8]
0x180023631  shr     edx, 3
0x180023634  cmp     edx, 3E8h
0x18002363a  jnb     short loc_180023643
0x18002363c  mov     edx, 3E8h
0x180023641  jmp     short loc_18002364A
0x180023643  cmp     edx, r12d
0x180023646  cmova   edx, r12d
0x18002364a  mov     ecx, edx; dwMilliseconds
0x18002364c  call    cs:__imp_Sleep
0x180023652  lea     rax, [rbp+var_48]
0x180023656  mov     r9d, 24h ; '$'; cbBufSize
0x18002365c  lea     r8, [rbp+Buffer]; lpBuffer
0x180023660  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180023665  xor     edx, edx; InfoLevel
0x180023667  mov     rcx, r14; hService
0x18002366a  call    cs:__imp_QueryServiceStatusEx
0x180023670  test    eax, eax
0x180023672  jz      short loc_180023690
0x180023674  cmp     dword ptr [rbp+var_30+4], edi
0x180023677  jbe     short loc_180023681
0x180023679  call    cs:__imp_GetTickCount
0x18002367f  jmp     short loc_18002361C
0x180023681  call    cs:__imp_GetTickCount
0x180023687  sub     eax, esi
0x180023689  cmp     eax, dword ptr [rbp+var_30+8]
0x18002368c  jbe     short loc_180023621
0x18002368e  jmp     short loc_18002369C
0x180023690  call    cs:__imp_GetLastError
0x180023696  mov     ebx, eax
0x180023698  test    eax, eax
0x18002369a  jnz     short loc_1800236AA
0x18002369c  mov     ecx, dword ptr [rbp+Buffer+4]
0x18002369f  cmp     ecx, 4
0x1800236a2  mov     eax, 41Dh
0x1800236a7  cmovnz  ebx, eax
0x1800236aa  mov     eax, ebx
0x1800236ac  mov     rcx, [rbp+var_18]
0x1800236b0  xor     rcx, rsp; StackCookie
0x1800236b3  call    __security_check_cookie
0x1800236b8  add     rsp, 78h
0x1800236bc  pop     r14
0x1800236be  pop     r12
0x1800236c0  pop     rdi
0x1800236c1  pop     rsi
0x1800236c2  pop     rbx
0x1800236c3  pop     rbp
0x1800236c4  retn
```
