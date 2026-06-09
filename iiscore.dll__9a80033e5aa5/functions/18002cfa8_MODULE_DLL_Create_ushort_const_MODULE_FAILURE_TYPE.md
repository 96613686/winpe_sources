# MODULE_DLL::Create(ushort const *,MODULE_FAILURE_TYPE *)

- ea: `0x18002cfa8`
- end: `0x18002d074`
- name: `?Create@MODULE_DLL@@AEAAJPEBGPEAW4MODULE_FAILURE_TYPE@@@Z`
- size: `204`
- prototype: `int __fastcall(MODULE_DLL *this, const unsigned __int16 *, enum MODULE_FAILURE_TYPE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180017b2c`

## callees

- `0x18002cfa8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d00a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d00a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002cfdb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002cfdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cfec`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cfc4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002cfc4`

## pseudocode

```c
int __fastcall MODULE_DLL::Create(MODULE_DLL *this, const unsigned __int16 *a2, enum MODULE_FAILURE_TYPE *a3)
{
  int result; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v9; // ecx
  unsigned int v10; // eax
  _QWORD *v11; // rcx

  result = STRU::Copy((MODULE_DLL *)((char *)this + 56), a2);
  if ( result >= 0 )
  {
    Library = LoadLibraryExW(a2, 0, 8u);
    *((_QWORD *)this + 5) = Library;
    if ( !Library )
    {
      *(_DWORD *)a3 = 0;
      goto LABEL_4;
    }
    ProcAddress = GetProcAddress(Library, "RegisterModule");
    *((_QWORD *)this + 6) = ProcAddress;
    if ( !ProcAddress )
    {
      *(_DWORD *)a3 = 1;
LABEL_4:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    v9 = MODULE_DLL::sm_cModuleCount;
    *((_DWORD *)this + 8) = MODULE_DLL::sm_cModuleCount;
    v10 = v9 + 1;
    v11 = (_QWORD *)qword_18004B4E0;
    MODULE_DLL::sm_cModuleCount = v10;
    if ( *(struct _LIST_ENTRY **)qword_18004B4E0 != &MODULE_DLL::sm_ModuleListHead )
      __fastfail(3u);
    *((_QWORD *)this + 2) = &MODULE_DLL::sm_ModuleListHead;
    *((_QWORD *)this + 3) = v11;
    *v11 = (char *)this + 16;
    qword_18004B4E0 = (__int64)this + 16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002cfa8  mov     [rsp+arg_0], rbx
0x18002cfad  mov     [rsp+arg_8], rsi
0x18002cfb2  push    rdi
0x18002cfb3  sub     rsp, 20h
0x18002cfb7  mov     rbx, rcx
0x18002cfba  mov     rdi, r8
0x18002cfbd  add     rcx, 38h ; '8'
0x18002cfc1  mov     rsi, rdx
0x18002cfc4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002cfca  test    eax, eax
0x18002cfcc  js      loc_18002D064
0x18002cfd2  xor     edx, edx; hFile
0x18002cfd4  mov     rcx, rsi; lpLibFileName
0x18002cfd7  lea     r8d, [rdx+8]; dwFlags
0x18002cfdb  call    cs:__imp_LoadLibraryExW
0x18002cfe1  mov     [rbx+28h], rax
0x18002cfe5  test    rax, rax
0x18002cfe8  jnz     short loc_18002D000
0x18002cfea  mov     [rdi], eax
0x18002cfec  call    cs:__imp_GetLastError
0x18002cff2  test    eax, eax
0x18002cff4  jle     short loc_18002D064
0x18002cff6  movzx   eax, ax
0x18002cff9  or      eax, 80070000h
0x18002cffe  jmp     short loc_18002D064
0x18002d000  lea     rdx, aRegistermodule; "RegisterModule"
0x18002d007  mov     rcx, rax; hModule
0x18002d00a  call    cs:__imp_GetProcAddress
0x18002d010  mov     [rbx+30h], rax
0x18002d014  test    rax, rax
0x18002d017  jnz     short loc_18002D021
0x18002d019  mov     dword ptr [rdi], 1
0x18002d01f  jmp     short loc_18002CFEC
0x18002d021  mov     ecx, cs:?sm_cModuleCount@MODULE_DLL@@0KA; ulong MODULE_DLL::sm_cModuleCount
0x18002d027  lea     rdx, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18002d02e  mov     [rbx+20h], ecx
0x18002d031  lea     eax, [rcx+1]
0x18002d034  mov     rcx, cs:qword_18004B4E0
0x18002d03b  mov     cs:?sm_cModuleCount@MODULE_DLL@@0KA, eax; ulong MODULE_DLL::sm_cModuleCount
0x18002d041  cmp     [rcx], rdx
0x18002d044  jz      short loc_18002D04D
0x18002d046  mov     ecx, 3
0x18002d04b  int     29h; Win8: RtlFailFast(ecx)
0x18002d04d  lea     rax, [rbx+10h]
0x18002d051  mov     [rax], rdx
0x18002d054  mov     [rax+8], rcx
0x18002d058  mov     [rcx], rax
0x18002d05b  mov     cs:qword_18004B4E0, rax
0x18002d062  xor     eax, eax
0x18002d064  mov     rbx, [rsp+28h+arg_0]
0x18002d069  mov     rsi, [rsp+28h+arg_8]
0x18002d06e  add     rsp, 20h
0x18002d072  pop     rdi
0x18002d073  retn
```
