# CCryptUiExtension::Initialize(ushort const *)

- ea: `0x18000a2ac`
- end: `0x18000a3e3`
- name: `?Initialize@CCryptUiExtension@@IEAAJPEBG@Z`
- size: `311`
- prototype: `int(CCryptUiExtension *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180037ca4`

## callees

- `0x1800050ac`
- `0x18000a2ac`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a329`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a329`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a397`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a397`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a376`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a36b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a36b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a38e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a38e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a2f7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a347`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a2f7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a347`

## pseudocode

```c
__int64 __fastcall CCryptUiExtension::Initialize(CCryptUiExtension *this, const unsigned __int16 *a2)
{
  WCHAR *v2; // rbp
  signed int v5; // ebx
  DWORD v6; // eax
  DWORD v7; // edi
  signed int v8; // eax
  WCHAR *v9; // rax
  HMODULE LibraryW; // rax
  HMODULE v11; // rdi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  int v15; // ecx
  int v16; // [rsp+48h] [rbp+10h] BYREF
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  v17 = 0;
  v16 = 0;
  if ( a2 )
  {
    if ( *(_QWORD *)this )
    {
      v5 = -2147023649;
    }
    else
    {
      v6 = ExpandEnvironmentStringsW(a2, 0, 0);
      v7 = v6;
      if ( !v6 )
        goto LABEL_6;
      v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * v6);
      v2 = v9;
      if ( !v9 )
      {
        v5 = -2147024882;
        goto LABEL_16;
      }
      if ( ExpandEnvironmentStringsW(a2, v9, v7) && (LibraryW = IsolationAwareLoadLibraryW(v2), (v11 = LibraryW) != 0) )
      {
        ProcAddress = GetProcAddress(LibraryW, "GetFunctionTable");
        if ( ProcAddress )
        {
          v5 = ((__int64 (__fastcall *)(__int64 *, int *))ProcAddress)(&v17, &v16);
          if ( v5 >= 0 )
          {
            v15 = v16;
            if ( v16 )
            {
              v5 = 0;
              *((_QWORD *)this + 1) = v17;
              *((_DWORD *)this + 4) = v15;
              *(_QWORD *)this = v11;
              goto LABEL_16;
            }
            v5 = -2147221497;
          }
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
        FreeLibrary(v11);
      }
      else
      {
LABEL_6:
        v8 = GetLastError();
        v5 = v8;
        if ( v8 > 0 )
          v5 = (unsigned __int16)v8 | 0x80070000;
      }
    }
  }
  else
  {
    v5 = -2147467261;
  }
LABEL_16:
  LocalFree(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a2ac  mov     [rsp+arg_0], rbx
0x18000a2b1  push    rbp
0x18000a2b2  push    rsi
0x18000a2b3  push    rdi
0x18000a2b4  sub     rsp, 20h
0x18000a2b8  xor     ebp, ebp
0x18000a2ba  mov     [rsp+38h+arg_10], 0
0x18000a2c3  mov     [rsp+38h+arg_8], 0
0x18000a2cb  mov     rbx, rdx
0x18000a2ce  mov     rsi, rcx
0x18000a2d1  test    rdx, rdx
0x18000a2d4  jnz     short loc_18000A2E0
0x18000a2d6  mov     ebx, 80004003h
0x18000a2db  jmp     loc_18000A394
0x18000a2e0  cmp     [rcx], rbp
0x18000a2e3  jz      short loc_18000A2EF
0x18000a2e5  mov     ebx, 800704DFh
0x18000a2ea  jmp     loc_18000A394
0x18000a2ef  xor     r8d, r8d; nSize
0x18000a2f2  xor     edx, edx; lpDst
0x18000a2f4  mov     rcx, rbx; lpSrc
0x18000a2f7  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a2fd  mov     edi, eax
0x18000a2ff  test    eax, eax
0x18000a301  jnz     short loc_18000A31E
0x18000a303  call    cs:__imp_GetLastError
0x18000a309  mov     ebx, eax
0x18000a30b  test    eax, eax
0x18000a30d  jle     loc_18000A394
0x18000a313  movzx   ebx, ax
0x18000a316  or      ebx, 80070000h
0x18000a31c  jmp     short loc_18000A394
0x18000a31e  mov     rdx, rdi
0x18000a321  mov     ecx, 40h ; '@'; uFlags
0x18000a326  add     rdx, rdx; uBytes
0x18000a329  call    cs:__imp_LocalAlloc
0x18000a32f  mov     rbp, rax
0x18000a332  test    rax, rax
0x18000a335  jnz     short loc_18000A33E
0x18000a337  mov     ebx, 8007000Eh
0x18000a33c  jmp     short loc_18000A394
0x18000a33e  mov     r8d, edi; nSize
0x18000a341  mov     rdx, rbp; lpDst
0x18000a344  mov     rcx, rbx; lpSrc
0x18000a347  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a34d  test    eax, eax
0x18000a34f  jz      short loc_18000A303
0x18000a351  mov     rcx, rbp; lpLibFileName
0x18000a354  call    IsolationAwareLoadLibraryW
0x18000a359  mov     rdi, rax
0x18000a35c  test    rax, rax
0x18000a35f  jz      short loc_18000A303
0x18000a361  lea     rdx, aGetfunctiontab; "GetFunctionTable"
0x18000a368  mov     rcx, rax; hModule
0x18000a36b  call    cs:__imp_GetProcAddress
0x18000a371  test    rax, rax
0x18000a374  jnz     short loc_18000A3AC
0x18000a376  call    cs:__imp_GetLastError
0x18000a37c  mov     ebx, eax
0x18000a37e  test    eax, eax
0x18000a380  jle     short loc_18000A38B
0x18000a382  movzx   ebx, ax
0x18000a385  or      ebx, 80070000h
0x18000a38b  mov     rcx, rdi; hLibModule
0x18000a38e  call    cs:__imp_FreeLibrary
0x18000a394  mov     rcx, rbp; hMem
0x18000a397  call    cs:__imp_LocalFree
0x18000a39d  mov     eax, ebx
0x18000a39f  mov     rbx, [rsp+38h+arg_0]
0x18000a3a4  add     rsp, 20h
0x18000a3a8  pop     rdi
0x18000a3a9  pop     rsi
0x18000a3aa  pop     rbp
0x18000a3ab  retn
0x18000a3ac  lea     rdx, [rsp+38h+arg_8]
0x18000a3b1  lea     rcx, [rsp+38h+arg_10]
0x18000a3b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bb  mov     ebx, eax
0x18000a3bd  test    eax, eax
0x18000a3bf  js      short loc_18000A38B
0x18000a3c1  mov     ecx, [rsp+38h+arg_8]
0x18000a3c5  test    ecx, ecx
0x18000a3c7  jnz     short loc_18000A3D0
0x18000a3c9  mov     ebx, 80040007h
0x18000a3ce  jmp     short loc_18000A38B
0x18000a3d0  mov     rax, [rsp+38h+arg_10]
0x18000a3d5  xor     ebx, ebx
0x18000a3d7  mov     [rsi+8], rax
0x18000a3db  mov     [rsi+10h], ecx
0x18000a3de  mov     [rsi], rdi
0x18000a3e1  jmp     short loc_18000A394
```
