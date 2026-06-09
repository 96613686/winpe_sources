# GetBinaryArch(ushort const *)

- ea: `0x180003db0`
- end: `0x180003fe3`
- name: `?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z`
- size: `563`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800030d0`
- `0x180003d6c`

## callees

- `0x180003db0`
- `0x180004bd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003f89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f74`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180003f69`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180003f69`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180003f3e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180003f3e`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180003e4b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180003e4b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003e17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003e17`

## pseudocode

```c
__int64 __fastcall GetBinaryArch(const WCHAR *a1)
{
  unsigned int v2; // esi
  HMODULE v3; // r14
  HMODULE v4; // r12
  void *v5; // rdi
  BOOL v6; // r13d
  HANDLE FileW; // r15
  HANDLE FileMappingW; // rax
  __int64 v9; // rax
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  HMODULE v15; // rax
  HMODULE ModuleHandleW; // rax
  DWORD LastError; // eax

  v2 = -1;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 )
  {
    v6 = 0;
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, LastError);
      }
    }
    else
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
      v5 = FileMappingW;
      if ( FileMappingW )
      {
        v15 = (HMODULE)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        v4 = v15;
        if ( v15 )
        {
          v3 = v15;
          v6 = 1;
        }
      }
    }
  }
  else
  {
    FileW = 0;
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
      v3 = ModuleHandleW;
    v6 = ModuleHandleW != 0;
  }
  if ( v6 && *(_WORD *)v3 == 23117 )
  {
    v9 = *((int *)v3 + 15);
    if ( *(_DWORD *)((char *)v3 + v9) == 17744 )
    {
      v10 = *(unsigned __int16 *)((char *)v3 + v9 + 4);
      if ( v10 == 34404 )
      {
        v2 = 2;
      }
      else
      {
        v11 = v10 - 332;
        if ( v11 )
        {
          v12 = v11 - 120;
          if ( v12 )
          {
            v13 = v12 - 60;
            if ( v13 )
            {
              if ( v13 == 43108 )
                v2 = 4;
            }
            else
            {
              v2 = 1;
            }
          }
          else
          {
            v2 = 3;
          }
        }
        else
        {
          v2 = 0;
        }
      }
    }
  }
  if ( a1 )
  {
    if ( v4 )
      UnmapViewOfFile(v4);
    if ( v5 )
      CloseHandle(v5);
    if ( FileW )
      CloseHandle(FileW);
  }
  return v2;
}

```

## disassembly

```asm
0x180003db0  mov     [rsp+arg_0], rcx
0x180003db5  push    rbx
0x180003db6  push    rsi
0x180003db7  push    rdi
0x180003db8  push    r12
0x180003dba  push    r13
0x180003dbc  push    r14
0x180003dbe  push    r15
0x180003dc0  sub     rsp, 50h
0x180003dc4  mov     rbx, rcx
0x180003dc7  mov     esi, 0FFFFFFFFh
0x180003dcc  mov     [rsp+88h+var_48], esi
0x180003dd0  xor     r14d, r14d
0x180003dd3  xor     r12d, r12d
0x180003dd6  mov     [rsp+88h+arg_8], r12
0x180003dde  xor     edi, edi
0x180003de0  mov     [rsp+88h+arg_18], rdi
0x180003de8  test    rcx, rcx
0x180003deb  jz      loc_180003F7C
0x180003df1  xor     r13d, r13d
0x180003df4  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x180003df9  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180003e01  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180003e09  xor     r9d, r9d; lpSecurityAttributes
0x180003e0c  mov     edx, 80000000h; dwDesiredAccess
0x180003e11  mov     r8d, 1; dwShareMode
0x180003e17  call    cs:__imp_CreateFileW
0x180003e1d  mov     r15, rax
0x180003e20  mov     [rsp+88h+arg_10], rax
0x180003e28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003e2c  jz      loc_180003FA5
0x180003e32  xor     eax, eax
0x180003e34  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; lpName
0x180003e39  mov     [rsp+88h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180003e3d  xor     r9d, r9d; dwMaximumSizeHigh
0x180003e40  xor     edx, edx; lpFileMappingAttributes
0x180003e42  mov     r8d, 2; flProtect
0x180003e48  mov     rcx, r15; hFile
0x180003e4b  call    cs:__imp_CreateFileMappingW
0x180003e51  mov     rdi, rax
0x180003e54  mov     [rsp+88h+arg_18], rax
0x180003e5c  test    rax, rax
0x180003e5f  jnz     loc_180003F2B
0x180003e65  cmp     r13d, 1
0x180003e69  jnz     loc_180003EFA
0x180003e6f  mov     eax, 5A4Dh
0x180003e74  cmp     [r14], ax
0x180003e78  jnz     short loc_180003ED4
0x180003e7a  movsxd  rax, dword ptr [r14+3Ch]
0x180003e7e  cmp     dword ptr [rax+r14], 4550h
0x180003e86  jnz     short loc_180003ED4
0x180003e88  movzx   ecx, word ptr [rax+r14+4]
0x180003e8e  cmp     ecx, 8664h
0x180003e94  jnz     short loc_180003EA1
0x180003e96  mov     esi, 2
0x180003e9b  mov     [rsp+88h+var_48], esi
0x180003e9f  jmp     short loc_180003ED4
0x180003ea1  sub     ecx, 14Ch
0x180003ea7  jz      short loc_180003ED0
0x180003ea9  sub     ecx, 78h ; 'x'
0x180003eac  jz      short loc_180003EC9
0x180003eae  sub     ecx, 3Ch ; '<'
0x180003eb1  jz      short loc_180003EC2
0x180003eb3  cmp     ecx, 0A864h
0x180003eb9  jnz     short loc_180003ED4
0x180003ebb  mov     esi, 4
0x180003ec0  jmp     short loc_180003E9B
0x180003ec2  mov     esi, 1
0x180003ec7  jmp     short loc_180003E9B
0x180003ec9  mov     esi, 3
0x180003ece  jmp     short loc_180003E9B
0x180003ed0  xor     esi, esi
0x180003ed2  jmp     short loc_180003E9B
0x180003ed4  jmp     short loc_180003EFA
0x180003ed6  mov     rbx, [rsp+88h+arg_0]
0x180003ede  mov     esi, [rsp+88h+var_48]
0x180003ee2  mov     r12, [rsp+88h+arg_8]
0x180003eea  mov     r15, [rsp+88h+arg_10]
0x180003ef2  mov     rdi, [rsp+88h+arg_18]
0x180003efa  test    rbx, rbx
0x180003efd  jnz     short loc_180003F11
0x180003eff  mov     eax, esi
0x180003f01  add     rsp, 50h
0x180003f05  pop     r15
0x180003f07  pop     r14
0x180003f09  pop     r13
0x180003f0b  pop     r12
0x180003f0d  pop     rdi
0x180003f0e  pop     rsi
0x180003f0f  pop     rbx
0x180003f10  retn
0x180003f11  test    r12, r12
0x180003f14  jnz     short loc_180003F66
0x180003f16  test    rdi, rdi
0x180003f19  jnz     short loc_180003F71
0x180003f1b  test    r15, r15
0x180003f1e  jz      short loc_180003EFF
0x180003f20  mov     rcx, r15; hObject
0x180003f23  call    cs:__imp_CloseHandle
0x180003f29  jmp     short loc_180003EFF
0x180003f2b  mov     qword ptr [rsp+88h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x180003f30  xor     r9d, r9d; dwFileOffsetLow
0x180003f33  xor     r8d, r8d; dwFileOffsetHigh
0x180003f36  mov     edx, 4; dwDesiredAccess
0x180003f3b  mov     rcx, rax; hFileMappingObject
0x180003f3e  call    cs:__imp_MapViewOfFile
0x180003f44  mov     r12, rax
0x180003f47  mov     [rsp+88h+arg_8], rax
0x180003f4f  test    rax, rax
0x180003f52  jz      loc_180003E65
0x180003f58  mov     r14, rax
0x180003f5b  mov     r13d, 1
0x180003f61  jmp     loc_180003E65
0x180003f66  mov     rcx, r12; lpBaseAddress
0x180003f69  call    cs:__imp_UnmapViewOfFile
0x180003f6f  jmp     short loc_180003F16
0x180003f71  mov     rcx, rdi; hObject
0x180003f74  call    cs:__imp_CloseHandle
0x180003f7a  jmp     short loc_180003F1B
0x180003f7c  xor     r15d, r15d
0x180003f7f  mov     [rsp+88h+arg_10], r15
0x180003f87  xor     ecx, ecx; lpModuleName
0x180003f89  call    cs:__imp_GetModuleHandleW
0x180003f8f  test    rax, rax
0x180003f92  cmovnz  r14, rax
0x180003f96  xor     r13d, r13d
0x180003f99  test    rax, rax
0x180003f9c  setnz   r13b
0x180003fa0  jmp     loc_180003E65
0x180003fa5  lea     rax, WPP_GLOBAL_Control
0x180003fac  cmp     cs:WPP_GLOBAL_Control, rax
0x180003fb3  jz      loc_180003E65
0x180003fb9  call    cs:__imp_GetLastError
0x180003fbf  mov     edx, 0Ah
0x180003fc4  mov     r9d, eax
0x180003fc7  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x180003fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd5  mov     rcx, [rcx+10h]
0x180003fd9  call    WPP_SF_d
0x180003fde  jmp     loc_180003E65
```
