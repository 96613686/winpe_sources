# GetBinaryArch(ushort const *)

- ea: `0x180004110`
- end: `0x180004374`
- name: `?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z`
- size: `612`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003240`
- `0x1800040d4`

## callees

- `0x180004110`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000430e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000430e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004344`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004344`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800042f3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800042e2`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800042e2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800042b1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800042b1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800041b1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800041b1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004177`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004177`

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
0x180004110  mov     [rsp+arg_0], rcx
0x180004115  push    rbx
0x180004116  push    rsi
0x180004117  push    rdi
0x180004118  push    r12
0x18000411a  push    r13
0x18000411c  push    r14
0x18000411e  push    r15
0x180004120  sub     rsp, 50h
0x180004124  mov     rbx, rcx
0x180004127  mov     esi, 0FFFFFFFFh
0x18000412c  mov     [rsp+88h+var_48], esi
0x180004130  xor     r14d, r14d
0x180004133  xor     r12d, r12d
0x180004136  mov     [rsp+88h+arg_8], r12
0x18000413e  xor     edi, edi
0x180004140  mov     [rsp+88h+arg_18], rdi
0x180004148  test    rcx, rcx
0x18000414b  jz      loc_180004301
0x180004151  xor     r13d, r13d
0x180004154  mov     [rsp+88h+hTemplateFile], rdi; hTemplateFile
0x180004159  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004161  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x180004169  xor     r9d, r9d; lpSecurityAttributes
0x18000416c  mov     edx, 80000000h; dwDesiredAccess
0x180004171  mov     r8d, 1; dwShareMode
0x180004177  call    cs:__imp_CreateFileW
0x18000417e  nop     dword ptr [rax+rax+00h]
0x180004183  mov     r15, rax
0x180004186  mov     [rsp+88h+arg_10], rax
0x18000418e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004192  jz      loc_180004330
0x180004198  xor     eax, eax
0x18000419a  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rax; lpName
0x18000419f  mov     [rsp+88h+dwCreationDisposition], eax; dwMaximumSizeLow
0x1800041a3  xor     r9d, r9d; dwMaximumSizeHigh
0x1800041a6  xor     edx, edx; lpFileMappingAttributes
0x1800041a8  mov     r8d, 2; flProtect
0x1800041ae  mov     rcx, r15; hFile
0x1800041b1  call    cs:__imp_CreateFileMappingW
0x1800041b8  nop     dword ptr [rax+rax+00h]
0x1800041bd  mov     rdi, rax
0x1800041c0  mov     [rsp+88h+arg_18], rax
0x1800041c8  test    rax, rax
0x1800041cb  jnz     loc_18000429E
0x1800041d1  cmp     r13d, 1
0x1800041d5  jnz     loc_180004266
0x1800041db  mov     eax, 5A4Dh
0x1800041e0  cmp     [r14], ax
0x1800041e4  jnz     short loc_180004240
0x1800041e6  movsxd  rax, dword ptr [r14+3Ch]
0x1800041ea  cmp     dword ptr [rax+r14], 4550h
0x1800041f2  jnz     short loc_180004240
0x1800041f4  movzx   ecx, word ptr [rax+r14+4]
0x1800041fa  cmp     ecx, 8664h
0x180004200  jnz     short loc_18000420D
0x180004202  mov     esi, 2
0x180004207  mov     [rsp+88h+var_48], esi
0x18000420b  jmp     short loc_180004240
0x18000420d  sub     ecx, 14Ch
0x180004213  jz      short loc_18000423C
0x180004215  sub     ecx, 78h ; 'x'
0x180004218  jz      short loc_180004235
0x18000421a  sub     ecx, 3Ch ; '<'
0x18000421d  jz      short loc_18000422E
0x18000421f  cmp     ecx, 0A864h
0x180004225  jnz     short loc_180004240
0x180004227  mov     esi, 4
0x18000422c  jmp     short loc_180004207
0x18000422e  mov     esi, 1
0x180004233  jmp     short loc_180004207
0x180004235  mov     esi, 3
0x18000423a  jmp     short loc_180004207
0x18000423c  xor     esi, esi
0x18000423e  jmp     short loc_180004207
0x180004240  jmp     short loc_180004266
0x180004242  mov     rbx, [rsp+88h+arg_0]
0x18000424a  mov     esi, [rsp+88h+var_48]
0x18000424e  mov     r12, [rsp+88h+arg_8]
0x180004256  mov     r15, [rsp+88h+arg_10]
0x18000425e  mov     rdi, [rsp+88h+arg_18]
0x180004266  test    rbx, rbx
0x180004269  jnz     short loc_18000427E
0x18000426b  mov     eax, esi
0x18000426d  add     rsp, 50h
0x180004271  pop     r15
0x180004273  pop     r14
0x180004275  pop     r13
0x180004277  pop     r12
0x180004279  pop     rdi
0x18000427a  pop     rsi
0x18000427b  pop     rbx
0x18000427c  retn
0x18000427e  test    r12, r12
0x180004281  jnz     short loc_1800042DF
0x180004283  test    rdi, rdi
0x180004286  jnz     short loc_1800042F0
0x180004288  test    r15, r15
0x18000428b  jz      short loc_18000426B
0x18000428d  mov     rcx, r15; hObject
0x180004290  call    cs:__imp_CloseHandle
0x180004297  nop     dword ptr [rax+rax+00h]
0x18000429c  jmp     short loc_18000426B
0x18000429e  mov     qword ptr [rsp+88h+dwCreationDisposition], r12; dwNumberOfBytesToMap
0x1800042a3  xor     r9d, r9d; dwFileOffsetLow
0x1800042a6  xor     r8d, r8d; dwFileOffsetHigh
0x1800042a9  mov     edx, 4; dwDesiredAccess
0x1800042ae  mov     rcx, rax; hFileMappingObject
0x1800042b1  call    cs:__imp_MapViewOfFile
0x1800042b8  nop     dword ptr [rax+rax+00h]
0x1800042bd  mov     r12, rax
0x1800042c0  mov     [rsp+88h+arg_8], rax
0x1800042c8  test    rax, rax
0x1800042cb  jz      loc_1800041D1
0x1800042d1  mov     r14, rax
0x1800042d4  mov     r13d, 1
0x1800042da  jmp     loc_1800041D1
0x1800042df  mov     rcx, r12; lpBaseAddress
0x1800042e2  call    cs:__imp_UnmapViewOfFile
0x1800042e9  nop     dword ptr [rax+rax+00h]
0x1800042ee  jmp     short loc_180004283
0x1800042f0  mov     rcx, rdi; hObject
0x1800042f3  call    cs:__imp_CloseHandle
0x1800042fa  nop     dword ptr [rax+rax+00h]
0x1800042ff  jmp     short loc_180004288
0x180004301  xor     r15d, r15d
0x180004304  mov     [rsp+88h+arg_10], r15
0x18000430c  xor     ecx, ecx; lpModuleName
0x18000430e  call    cs:__imp_GetModuleHandleW
0x180004315  nop     dword ptr [rax+rax+00h]
0x18000431a  test    rax, rax
0x18000431d  cmovnz  r14, rax
0x180004321  xor     r13d, r13d
0x180004324  test    rax, rax
0x180004327  setnz   r13b
0x18000432b  jmp     loc_1800041D1
0x180004330  lea     rax, WPP_GLOBAL_Control
0x180004337  cmp     cs:WPP_GLOBAL_Control, rax
0x18000433e  jz      loc_1800041D1
0x180004344  call    cs:__imp_GetLastError
0x18000434b  nop     dword ptr [rax+rax+00h]
0x180004350  mov     edx, 0Ah
0x180004355  mov     r9d, eax
0x180004358  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000435f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004366  mov     rcx, [rcx+10h]
0x18000436a  call    WPP_SF_d
0x18000436f  jmp     loc_1800041D1
```
