# NatOpenService(ushort const *,ulong,SC_HANDLE__ * *)

- ea: `0x1800399c8`
- end: `0x180039b18`
- name: `?NatOpenService@@YAJPEBGKPEAPEAUSC_HANDLE__@@@Z`
- size: `336`
- prototype: `__int64 __fastcall(LPCWSTR lpServiceName, unsigned int, struct SC_HANDLE__ **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180039764`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x1800399c8`
- `0x180039b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039a88`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039a24`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180039a24`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039a7a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180039a7a`

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
0x1800399c8  push    rbx
0x1800399ca  push    rbp
0x1800399cb  push    rsi
0x1800399cc  push    rdi
0x1800399cd  push    r14
0x1800399cf  push    r15
0x1800399d1  sub     rsp, 28h
0x1800399d5  mov     rdi, r8
0x1800399d8  mov     rbp, rcx
0x1800399db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800399e2  lea     r15, WPP_GLOBAL_Control
0x1800399e9  mov     r14d, 200h
0x1800399ef  cmp     rcx, r15
0x1800399f2  jz      short loc_180039A15
0x1800399f4  test    [rcx+1Ch], r14d
0x1800399f8  jz      short loc_180039A15
0x1800399fa  cmp     byte ptr [rcx+19h], 6
0x1800399fe  jb      short loc_180039A15
0x180039a00  mov     rcx, [rcx+10h]
0x180039a04  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180039a0b  mov     edx, 0BFh
0x180039a10  call    WPP_SF_
0x180039a15  xor     edx, edx; lpDatabaseName
0x180039a17  mov     qword ptr [rdi], 0
0x180039a1e  xor     ecx, ecx; lpMachineName
0x180039a20  lea     r8d, [rdx+1]; dwDesiredAccess
0x180039a24  call    cs:__imp_OpenSCManagerW
0x180039a2a  mov     rsi, rax
0x180039a2d  test    rax, rax
0x180039a30  jnz     short loc_180039A6E
0x180039a32  call    cs:__imp_GetLastError
0x180039a38  mov     ebx, eax
0x180039a3a  test    eax, eax
0x180039a3c  jle     short loc_180039A47
0x180039a3e  movzx   ebx, ax
0x180039a41  or      ebx, 80070000h
0x180039a47  test    ebx, ebx
0x180039a49  jns     loc_180039AD1
0x180039a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039a56  cmp     rcx, r15
0x180039a59  jz      short loc_180039AD1
0x180039a5b  test    [rcx+1Ch], r14d
0x180039a5f  jz      short loc_180039AD1
0x180039a61  cmp     byte ptr [rcx+19h], 2
0x180039a65  jb      short loc_180039AD1
0x180039a67  mov     edx, 0C0h
0x180039a6c  jmp     short loc_180039ABE
0x180039a6e  xor     ebx, ebx
0x180039a70  mov     rdx, rbp; lpServiceName
0x180039a73  mov     rcx, rsi; hSCManager
0x180039a76  lea     r8d, [rbx+14h]; dwDesiredAccess
0x180039a7a  call    cs:__imp_OpenServiceW
0x180039a80  mov     [rdi], rax
0x180039a83  test    rax, rax
0x180039a86  jnz     short loc_180039AD1
0x180039a88  call    cs:__imp_GetLastError
0x180039a8e  mov     ebx, eax
0x180039a90  test    eax, eax
0x180039a92  jle     short loc_180039A9D
0x180039a94  movzx   ebx, ax
0x180039a97  or      ebx, 80070000h
0x180039a9d  test    ebx, ebx
0x180039a9f  jns     short loc_180039AD1
0x180039aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180039aa8  cmp     rcx, r15
0x180039aab  jz      short loc_180039AD1
0x180039aad  test    [rcx+1Ch], r14d
0x180039ab1  jz      short loc_180039AD1
0x180039ab3  cmp     byte ptr [rcx+19h], 2
0x180039ab7  jb      short loc_180039AD1
0x180039ab9  mov     edx, 0C1h
0x180039abe  mov     rcx, [rcx+10h]
0x180039ac2  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180039ac9  mov     r9d, ebx
0x180039acc  call    WPP_SF_d
0x180039ad1  mov     rcx, rsi; hSCObject
0x180039ad4  call    ?NatCloseServiceHandle@@YAXPEAUSC_HANDLE__@@@Z; NatCloseServiceHandle(SC_HANDLE__ *)
0x180039ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039ae0  cmp     rcx, r15
0x180039ae3  jz      short loc_180039B09
0x180039ae5  test    [rcx+1Ch], r14d
0x180039ae9  jz      short loc_180039B09
0x180039aeb  cmp     byte ptr [rcx+19h], 6
0x180039aef  jb      short loc_180039B09
0x180039af1  mov     rcx, [rcx+10h]
0x180039af5  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x180039afc  mov     edx, 0C2h
0x180039b01  mov     r9d, ebx
0x180039b04  call    WPP_SF_d
0x180039b09  mov     eax, ebx
0x180039b0b  add     rsp, 28h
0x180039b0f  pop     r15
0x180039b11  pop     r14
0x180039b13  pop     rdi
0x180039b14  pop     rsi
0x180039b15  pop     rbp
0x180039b16  pop     rbx
0x180039b17  retn
```
