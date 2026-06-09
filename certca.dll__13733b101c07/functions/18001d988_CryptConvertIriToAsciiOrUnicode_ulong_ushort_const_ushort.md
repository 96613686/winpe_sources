# CryptConvertIriToAsciiOrUnicode(ulong,ushort const *,ushort * *)

- ea: `0x18001d988`
- end: `0x18001da77`
- name: `?CryptConvertIriToAsciiOrUnicode@@YAHKPEBGPEAPEAG@Z`
- size: `239`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e180`

## callees

- `0x18000d9f0`
- `0x18001d988`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da62`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001da62`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d9ce`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001da12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001da54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d9f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001da25`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001da25`

## string_xrefs

- `0x18001d99b`: `cryptnet.dll`

## pseudocode

```c
__int64 __fastcall CryptConvertIriToAsciiOrUnicode(__int64 a1, unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v4; // rbx
  unsigned int v5; // esi
  HMODULE System32Library; // rax
  HMODULE v8; // rdi
  FARPROC ProcAddress; // rax
  unsigned int (__fastcall *v10)(__int64, unsigned __int16 *, unsigned int *, unsigned __int16 *); // rbp
  unsigned __int16 *v11; // rax
  unsigned int v13; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v5 = 0;
  *a3 = 0;
  v13 = 0;
  System32Library = myLoadSystem32LibraryEx(L"cryptnet.dll", a2, 0);
  v8 = System32Library;
  if ( System32Library )
  {
    ProcAddress = GetProcAddress(System32Library, "I_CryptConvertIriToAsciiOrUnicodeWithFlags");
    v10 = (unsigned int (__fastcall *)(__int64, unsigned __int16 *, unsigned int *, unsigned __int16 *))ProcAddress;
    if ( ProcAddress )
    {
      v13 = 0;
      if ( ((unsigned int (__fastcall *)(__int64, unsigned __int16 *, unsigned int *, _QWORD))ProcAddress)(
             393216,
             a2,
             &v13,
             0)
        || GetLastError() == -2146893784 )
      {
        v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v13);
        v4 = v11;
        if ( v11 )
        {
          if ( v10(393216, a2, &v13, v11) )
          {
            *a3 = v4;
            v4 = 0;
            v5 = 1;
          }
        }
        else
        {
          SetLastError(0x8007000E);
        }
      }
    }
  }
  LocalFree(v4);
  if ( v8 )
    FreeLibrary(v8);
  return v5;
}

```

## disassembly

```asm
0x18001d988  mov     [rsp+arg_0], ecx
0x18001d98c  push    rbx
0x18001d98d  push    rbp
0x18001d98e  push    rsi
0x18001d98f  push    rdi
0x18001d990  push    r14
0x18001d992  push    r15
0x18001d994  sub     rsp, 38h
0x18001d998  mov     r14, r8
0x18001d99b  lea     rcx, aCryptnetDll_0; "cryptnet.dll"
0x18001d9a2  xor     ebx, ebx
0x18001d9a4  xor     esi, esi
0x18001d9a6  mov     [r8], rbx
0x18001d9a9  mov     r15, rdx
0x18001d9ac  xor     r8d, r8d; unsigned int
0x18001d9af  mov     [rsp+68h+arg_0], esi
0x18001d9b3  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x18001d9b8  mov     rdi, rax
0x18001d9bb  test    rax, rax
0x18001d9be  jz      loc_18001DA51
0x18001d9c4  lea     rdx, aICryptconverti; "I_CryptConvertIriToAsciiOrUnicodeWithFl"...
0x18001d9cb  mov     rcx, rax; hModule
0x18001d9ce  call    cs:__imp_GetProcAddress
0x18001d9d4  mov     rbp, rax
0x18001d9d7  test    rax, rax
0x18001d9da  jz      short loc_18001DA51
0x18001d9dc  xor     r9d, r9d
0x18001d9df  mov     [rsp+68h+arg_0], ebx
0x18001d9e3  lea     r8, [rsp+68h+arg_0]
0x18001d9e8  mov     rdx, r15
0x18001d9eb  mov     ecx, 60000h
0x18001d9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f5  test    eax, eax
0x18001d9f7  jnz     short loc_18001DA06
0x18001d9f9  call    cs:__imp_GetLastError
0x18001d9ff  cmp     eax, 80090028h
0x18001da04  jnz     short loc_18001DA51
0x18001da06  mov     edx, [rsp+68h+arg_0]
0x18001da0a  mov     ecx, 40h ; '@'; uFlags
0x18001da0f  add     rdx, rdx; uBytes
0x18001da12  call    cs:__imp_LocalAlloc
0x18001da18  mov     rbx, rax
0x18001da1b  test    rax, rax
0x18001da1e  jnz     short loc_18001DA2D
0x18001da20  mov     ecx, 8007000Eh; dwErrCode
0x18001da25  call    cs:__imp_SetLastError
0x18001da2b  jmp     short loc_18001DA51
0x18001da2d  mov     r9, rbx
0x18001da30  lea     r8, [rsp+68h+arg_0]
0x18001da35  mov     rdx, r15
0x18001da38  mov     ecx, 60000h
0x18001da3d  mov     rax, rbp
0x18001da40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da45  test    eax, eax
0x18001da47  jz      short loc_18001DA51
0x18001da49  mov     [r14], rbx
0x18001da4c  xor     ebx, ebx
0x18001da4e  lea     esi, [rbx+1]
0x18001da51  mov     rcx, rbx; hMem
0x18001da54  call    cs:__imp_LocalFree
0x18001da5a  test    rdi, rdi
0x18001da5d  jz      short loc_18001DA68
0x18001da5f  mov     rcx, rdi; hLibModule
0x18001da62  call    cs:__imp_FreeLibrary
0x18001da68  mov     eax, esi
0x18001da6a  add     rsp, 38h
0x18001da6e  pop     r15
0x18001da70  pop     r14
0x18001da72  pop     rdi
0x18001da73  pop     rsi
0x18001da74  pop     rbp
0x18001da75  pop     rbx
0x18001da76  retn
```
