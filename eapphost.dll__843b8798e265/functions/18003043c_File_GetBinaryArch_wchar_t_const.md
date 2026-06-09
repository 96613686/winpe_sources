# File::GetBinaryArch(wchar_t const *)

- ea: `0x18003043c`
- end: `0x180030632`
- name: `?GetBinaryArch@File@@CA?AW4ArchType@ArchValue@1@PEB_W@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001cb34`

## callees

- `0x18003043c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030482`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030482`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030613`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800305ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030613`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800304c8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800304c8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180030527`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180030527`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800305eb`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800305eb`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800304f9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800304f9`

## pseudocode

```c
__int64 __fastcall File::GetBinaryArch(const WCHAR *a1)
{
  unsigned int v2; // ebx
  HMODULE v3; // r14
  HMODULE v4; // rdi
  void *v5; // rsi
  void *v6; // r15
  HMODULE ModuleHandleW; // rax
  BOOL v8; // r13d
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  HMODULE v11; // rax
  __int64 v12; // rax

  v2 = -1;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( a1 )
  {
    v8 = 0;
    FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v6 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      FileMappingW = CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
      v5 = FileMappingW;
      if ( FileMappingW )
      {
        v11 = (HMODULE)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        v4 = v11;
        if ( v11 )
        {
          v3 = v11;
          v8 = 1;
        }
      }
    }
  }
  else
  {
    v6 = 0;
    ModuleHandleW = GetModuleHandleW(0);
    if ( ModuleHandleW )
      v3 = ModuleHandleW;
    v8 = ModuleHandleW != 0;
  }
  if ( v8 && *(_WORD *)v3 == 23117 )
  {
    v12 = *((int *)v3 + 15);
    if ( *(_DWORD *)((char *)v3 + v12) == 17744 )
    {
      switch ( *(_WORD *)((char *)v3 + v12 + 4) )
      {
        case 0x14C:
          v2 = 0;
          break;
        case 0x1C4:
          v2 = 3;
          break;
        case 0x200:
          v2 = 1;
          break;
        default:
          if ( *(unsigned __int16 *)((char *)v3 + v12 + 4) == 34404 )
          {
            v2 = 2;
          }
          else if ( *(unsigned __int16 *)((char *)v3 + v12 + 4) == 43620 )
          {
            v2 = 4;
          }
          break;
      }
    }
  }
  if ( a1 )
  {
    if ( v4 )
      UnmapViewOfFile(v4);
    if ( v5 )
      CloseHandle(v5);
    if ( v6 )
      CloseHandle(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x18003043c  mov     [rsp+arg_0], rcx
0x180030441  push    rbx
0x180030442  push    rsi
0x180030443  push    rdi
0x180030444  push    r12
0x180030446  push    r13
0x180030448  push    r14
0x18003044a  push    r15
0x18003044c  sub     rsp, 50h
0x180030450  mov     r12, rcx
0x180030453  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030457  mov     [rsp+88h+var_48], ebx
0x18003045b  xor     r14d, r14d
0x18003045e  xor     edi, edi
0x180030460  mov     [rsp+88h+arg_8], rdi
0x180030468  xor     esi, esi
0x18003046a  mov     [rsp+88h+arg_18], rsi
0x180030472  test    rcx, rcx
0x180030475  jnz     short loc_1800304A4
0x180030477  xor     r15d, r15d
0x18003047a  mov     [rsp+88h+arg_10], r15
0x180030482  call    cs:__imp_GetModuleHandleW
0x180030489  nop     dword ptr [rax+rax+00h]
0x18003048e  test    rax, rax
0x180030491  cmovnz  r14, rax
0x180030495  xor     r13d, r13d
0x180030498  test    rax, rax
0x18003049b  setnz   r13b
0x18003049f  jmp     loc_18003054C
0x1800304a4  xor     r13d, r13d
0x1800304a7  mov     [rsp+88h+hTemplateFile], rsi; hTemplateFile
0x1800304ac  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800304b4  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1800304bc  xor     r9d, r9d; lpSecurityAttributes
0x1800304bf  mov     edx, 80000000h; dwDesiredAccess
0x1800304c4  lea     r8d, [r13+1]; dwShareMode
0x1800304c8  call    cs:__imp_CreateFileW
0x1800304cf  nop     dword ptr [rax+rax+00h]
0x1800304d4  mov     r15, rax
0x1800304d7  mov     [rsp+88h+arg_10], rax
0x1800304df  cmp     rax, rbx
0x1800304e2  jz      short loc_18003054C
0x1800304e4  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rsi; lpName
0x1800304e9  mov     [rsp+88h+dwCreationDisposition], esi; dwMaximumSizeLow
0x1800304ed  xor     r9d, r9d; dwMaximumSizeHigh
0x1800304f0  xor     edx, edx; lpFileMappingAttributes
0x1800304f2  lea     r8d, [r13+2]; flProtect
0x1800304f6  mov     rcx, rax; hFile
0x1800304f9  call    cs:__imp_CreateFileMappingW
0x180030500  nop     dword ptr [rax+rax+00h]
0x180030505  mov     rsi, rax
0x180030508  mov     [rsp+88h+arg_18], rax
0x180030510  test    rax, rax
0x180030513  jz      short loc_18003054C
0x180030515  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; dwNumberOfBytesToMap
0x18003051a  xor     r9d, r9d; dwFileOffsetLow
0x18003051d  xor     r8d, r8d; dwFileOffsetHigh
0x180030520  lea     edx, [r13+4]; dwDesiredAccess
0x180030524  mov     rcx, rax; hFileMappingObject
0x180030527  call    cs:__imp_MapViewOfFile
0x18003052e  nop     dword ptr [rax+rax+00h]
0x180030533  mov     rdi, rax
0x180030536  mov     [rsp+88h+arg_8], rax
0x18003053e  test    rax, rax
0x180030541  jz      short loc_18003054C
0x180030543  mov     r14, rax
0x180030546  mov     r13d, 1
0x18003054c  cmp     r13d, 1
0x180030550  jnz     loc_1800305DE
0x180030556  mov     eax, 5A4Dh
0x18003055b  cmp     [r14], ax
0x18003055f  jnz     short loc_1800305B8
0x180030561  movsxd  rax, dword ptr [r14+3Ch]
0x180030565  cmp     dword ptr [rax+r14], 4550h
0x18003056d  jnz     short loc_1800305B8
0x18003056f  movzx   ecx, word ptr [rax+r14+4]
0x180030575  sub     ecx, 14Ch
0x18003057b  jz      short loc_1800305B2
0x18003057d  sub     ecx, 78h ; 'x'
0x180030580  jz      short loc_1800305AB
0x180030582  sub     ecx, 3Ch ; '<'
0x180030585  jz      short loc_1800305A4
0x180030587  sub     ecx, 8464h
0x18003058d  jz      short loc_18003059D
0x18003058f  cmp     ecx, 2400h
0x180030595  jnz     short loc_1800305B8
0x180030597  lea     ebx, [r13+3]
0x18003059b  jmp     short loc_1800305B4
0x18003059d  mov     ebx, 2
0x1800305a2  jmp     short loc_1800305B4
0x1800305a4  mov     ebx, 1
0x1800305a9  jmp     short loc_1800305B4
0x1800305ab  mov     ebx, 3
0x1800305b0  jmp     short loc_1800305B4
0x1800305b2  xor     ebx, ebx
0x1800305b4  mov     [rsp+88h+var_48], ebx
0x1800305b8  jmp     short loc_1800305DE
0x1800305ba  mov     r12, [rsp+88h+arg_0]
0x1800305c2  mov     ebx, [rsp+88h+var_48]
0x1800305c6  mov     rdi, [rsp+88h+arg_8]
0x1800305ce  mov     r15, [rsp+88h+arg_10]
0x1800305d6  mov     rsi, [rsp+88h+arg_18]
0x1800305de  test    r12, r12
0x1800305e1  jz      short loc_18003061F
0x1800305e3  test    rdi, rdi
0x1800305e6  jz      short loc_1800305F7
0x1800305e8  mov     rcx, rdi; lpBaseAddress
0x1800305eb  call    cs:__imp_UnmapViewOfFile
0x1800305f2  nop     dword ptr [rax+rax+00h]
0x1800305f7  test    rsi, rsi
0x1800305fa  jz      short loc_18003060B
0x1800305fc  mov     rcx, rsi; hObject
0x1800305ff  call    cs:__imp_CloseHandle
0x180030606  nop     dword ptr [rax+rax+00h]
0x18003060b  test    r15, r15
0x18003060e  jz      short loc_18003061F
0x180030610  mov     rcx, r15; hObject
0x180030613  call    cs:__imp_CloseHandle
0x18003061a  nop     dword ptr [rax+rax+00h]
0x18003061f  mov     eax, ebx
0x180030621  add     rsp, 50h
0x180030625  pop     r15
0x180030627  pop     r14
0x180030629  pop     r13
0x18003062b  pop     r12
0x18003062d  pop     rdi
0x18003062e  pop     rsi
0x18003062f  pop     rbx
0x180030630  retn
```
