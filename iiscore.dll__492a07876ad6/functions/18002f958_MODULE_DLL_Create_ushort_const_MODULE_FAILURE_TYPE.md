# MODULE_DLL::Create(ushort const *,MODULE_FAILURE_TYPE *)

- ea: `0x18002f958`
- end: `0x18002fa3d`
- name: `?Create@MODULE_DLL@@AEAAJPEBGPEAW4MODULE_FAILURE_TYPE@@@Z`
- size: `229`
- prototype: `int __fastcall(MODULE_DLL *this, const unsigned __int16 *, enum MODULE_FAILURE_TYPE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180018f70`

## callees

- `0x18002f958`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f9cc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f991`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f9a8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f974`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18002f974`

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
    v11 = (_QWORD *)qword_18004E4E0;
    MODULE_DLL::sm_cModuleCount = v10;
    if ( *(struct _LIST_ENTRY **)qword_18004E4E0 != &MODULE_DLL::sm_ModuleListHead )
      __fastfail(3u);
    *((_QWORD *)this + 2) = &MODULE_DLL::sm_ModuleListHead;
    *((_QWORD *)this + 3) = v11;
    *v11 = (char *)this + 16;
    qword_18004E4E0 = (__int64)this + 16;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002f958  mov     [rsp+arg_0], rbx
0x18002f95d  mov     [rsp+arg_8], rsi
0x18002f962  push    rdi
0x18002f963  sub     rsp, 20h
0x18002f967  mov     rbx, rcx
0x18002f96a  mov     rdi, r8
0x18002f96d  add     rcx, 38h ; '8'
0x18002f971  mov     rsi, rdx
0x18002f974  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18002f97b  nop     dword ptr [rax+rax+00h]
0x18002f980  test    eax, eax
0x18002f982  js      loc_18002FA2C
0x18002f988  xor     edx, edx; hFile
0x18002f98a  mov     rcx, rsi; lpLibFileName
0x18002f98d  lea     r8d, [rdx+8]; dwFlags
0x18002f991  call    cs:__imp_LoadLibraryExW
0x18002f998  nop     dword ptr [rax+rax+00h]
0x18002f99d  mov     [rbx+28h], rax
0x18002f9a1  test    rax, rax
0x18002f9a4  jnz     short loc_18002F9C2
0x18002f9a6  mov     [rdi], eax
0x18002f9a8  call    cs:__imp_GetLastError
0x18002f9af  nop     dword ptr [rax+rax+00h]
0x18002f9b4  test    eax, eax
0x18002f9b6  jle     short loc_18002FA2C
0x18002f9b8  movzx   eax, ax
0x18002f9bb  or      eax, 80070000h
0x18002f9c0  jmp     short loc_18002FA2C
0x18002f9c2  lea     rdx, aRegistermodule; "RegisterModule"
0x18002f9c9  mov     rcx, rax; hModule
0x18002f9cc  call    cs:__imp_GetProcAddress
0x18002f9d3  nop     dword ptr [rax+rax+00h]
0x18002f9d8  mov     [rbx+30h], rax
0x18002f9dc  test    rax, rax
0x18002f9df  jnz     short loc_18002F9E9
0x18002f9e1  mov     dword ptr [rdi], 1
0x18002f9e7  jmp     short loc_18002F9A8
0x18002f9e9  mov     ecx, cs:?sm_cModuleCount@MODULE_DLL@@0KA; ulong MODULE_DLL::sm_cModuleCount
0x18002f9ef  lea     rdx, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x18002f9f6  mov     [rbx+20h], ecx
0x18002f9f9  lea     eax, [rcx+1]
0x18002f9fc  mov     rcx, cs:qword_18004E4E0
0x18002fa03  mov     cs:?sm_cModuleCount@MODULE_DLL@@0KA, eax; ulong MODULE_DLL::sm_cModuleCount
0x18002fa09  cmp     [rcx], rdx
0x18002fa0c  jz      short loc_18002FA15
0x18002fa0e  mov     ecx, 3
0x18002fa13  int     29h; Win8: RtlFailFast(ecx)
0x18002fa15  lea     rax, [rbx+10h]
0x18002fa19  mov     [rax], rdx
0x18002fa1c  mov     [rax+8], rcx
0x18002fa20  mov     [rcx], rax
0x18002fa23  mov     cs:qword_18004E4E0, rax
0x18002fa2a  xor     eax, eax
0x18002fa2c  mov     rbx, [rsp+28h+arg_0]
0x18002fa31  mov     rsi, [rsp+28h+arg_8]
0x18002fa36  add     rsp, 20h
0x18002fa3a  pop     rdi
0x18002fa3b  retn
```
