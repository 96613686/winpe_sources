# NatOpenService(ushort const *,ulong,SC_HANDLE__ * *)

- ea: `0x18003c8d4`
- end: `0x18003ca41`
- name: `?NatOpenService@@YAJPEBGKPEAPEAUSC_HANDLE__@@@Z`
- size: `365`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, struct SC_HANDLE__ **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18003c63c`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003c8d4`
- `0x18003ca48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c9aa`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c930`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18003c930`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c996`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18003c996`

## pseudocode

```c
__int64 __fastcall NatOpenService(LPCWSTR lpServiceName, __int64 a2, struct SC_HANDLE__ **a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  signed int v7; // eax
  signed int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  SC_HANDLE v11; // rax
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  *a3 = 0;
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v8 = 0;
    v11 = OpenServiceW(v5, lpServiceName, 0x14u);
    *a3 = v11;
    if ( !v11 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v10 = 193;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = 192;
LABEL_21:
        WPP_SF_d(v9[2], v10, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v8);
      }
    }
  }
  NatCloseServiceHandle(v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      194,
      &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003c8d4  push    rbx
0x18003c8d6  push    rbp
0x18003c8d7  push    rsi
0x18003c8d8  push    rdi
0x18003c8d9  push    r14
0x18003c8db  push    r15
0x18003c8dd  sub     rsp, 28h
0x18003c8e1  mov     rdi, r8
0x18003c8e4  mov     rbp, rcx
0x18003c8e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8ee  lea     r15, WPP_GLOBAL_Control
0x18003c8f5  mov     r14d, 200h
0x18003c8fb  cmp     rcx, r15
0x18003c8fe  jz      short loc_18003C921
0x18003c900  test    [rcx+1Ch], r14d
0x18003c904  jz      short loc_18003C921
0x18003c906  cmp     byte ptr [rcx+19h], 6
0x18003c90a  jb      short loc_18003C921
0x18003c90c  mov     rcx, [rcx+10h]
0x18003c910  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003c917  mov     edx, 0BFh
0x18003c91c  call    WPP_SF_
0x18003c921  xor     edx, edx; lpDatabaseName
0x18003c923  mov     qword ptr [rdi], 0
0x18003c92a  xor     ecx, ecx; lpMachineName
0x18003c92c  lea     r8d, [rdx+1]; dwDesiredAccess
0x18003c930  call    cs:__imp_OpenSCManagerW
0x18003c937  nop     dword ptr [rax+rax+00h]
0x18003c93c  mov     rsi, rax
0x18003c93f  test    rax, rax
0x18003c942  jnz     short loc_18003C98A
0x18003c944  call    cs:__imp_GetLastError
0x18003c94b  nop     dword ptr [rax+rax+00h]
0x18003c950  mov     ebx, eax
0x18003c952  test    eax, eax
0x18003c954  jle     short loc_18003C95F
0x18003c956  movzx   ebx, ax
0x18003c959  or      ebx, 80070000h
0x18003c95f  test    ebx, ebx
0x18003c961  jns     loc_18003C9F9
0x18003c967  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c96e  cmp     rcx, r15
0x18003c971  jz      loc_18003C9F9
0x18003c977  test    [rcx+1Ch], r14d
0x18003c97b  jz      short loc_18003C9F9
0x18003c97d  cmp     byte ptr [rcx+19h], 2
0x18003c981  jb      short loc_18003C9F9
0x18003c983  mov     edx, 0C0h
0x18003c988  jmp     short loc_18003C9E6
0x18003c98a  xor     ebx, ebx
0x18003c98c  mov     rdx, rbp; lpServiceName
0x18003c98f  mov     rcx, rsi; hSCManager
0x18003c992  lea     r8d, [rbx+14h]; dwDesiredAccess
0x18003c996  call    cs:__imp_OpenServiceW
0x18003c99d  nop     dword ptr [rax+rax+00h]
0x18003c9a2  mov     [rdi], rax
0x18003c9a5  test    rax, rax
0x18003c9a8  jnz     short loc_18003C9F9
0x18003c9aa  call    cs:__imp_GetLastError
0x18003c9b1  nop     dword ptr [rax+rax+00h]
0x18003c9b6  mov     ebx, eax
0x18003c9b8  test    eax, eax
0x18003c9ba  jle     short loc_18003C9C5
0x18003c9bc  movzx   ebx, ax
0x18003c9bf  or      ebx, 80070000h
0x18003c9c5  test    ebx, ebx
0x18003c9c7  jns     short loc_18003C9F9
0x18003c9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c9d0  cmp     rcx, r15
0x18003c9d3  jz      short loc_18003C9F9
0x18003c9d5  test    [rcx+1Ch], r14d
0x18003c9d9  jz      short loc_18003C9F9
0x18003c9db  cmp     byte ptr [rcx+19h], 2
0x18003c9df  jb      short loc_18003C9F9
0x18003c9e1  mov     edx, 0C1h
0x18003c9e6  mov     rcx, [rcx+10h]
0x18003c9ea  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003c9f1  mov     r9d, ebx
0x18003c9f4  call    WPP_SF_d
0x18003c9f9  mov     rcx, rsi; hSCObject
0x18003c9fc  call    ?NatCloseServiceHandle@@YAXPEAUSC_HANDLE__@@@Z; NatCloseServiceHandle(SC_HANDLE__ *)
0x18003ca01  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca08  cmp     rcx, r15
0x18003ca0b  jz      short loc_18003CA31
0x18003ca0d  test    [rcx+1Ch], r14d
0x18003ca11  jz      short loc_18003CA31
0x18003ca13  cmp     byte ptr [rcx+19h], 6
0x18003ca17  jb      short loc_18003CA31
0x18003ca19  mov     rcx, [rcx+10h]
0x18003ca1d  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18003ca24  mov     edx, 0C2h
0x18003ca29  mov     r9d, ebx
0x18003ca2c  call    WPP_SF_d
0x18003ca31  mov     eax, ebx
0x18003ca33  add     rsp, 28h
0x18003ca37  pop     r15
0x18003ca39  pop     r14
0x18003ca3b  pop     rdi
0x18003ca3c  pop     rsi
0x18003ca3d  pop     rbp
0x18003ca3e  pop     rbx
0x18003ca3f  retn
```
