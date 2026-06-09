# ValidateTrace

- ea: `0x18000ea9c`
- end: `0x18000ec14`
- name: `ValidateTrace`
- size: `376`
- prototype: `_BOOL8 __fastcall(wchar_t *FullPath)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000dc70`

## callees

- `0x18000ea9c`
- `0x180013c7c`
- `0x180013f00`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `msvcrt!_wmakepath_s` at `0x18000eb92`
- `msvcrt!_wmakepath_s` at `0x18000eb92`
- `msvcrt!_wsplitpath_s` at `0x18000eb67`
- `msvcrt!_wsplitpath_s` at `0x18000eb67`
- `KERNEL32!FreeLibrary` at `0x18000ebe5`
- `KERNEL32!FreeLibrary` at `0x18000ebe5`
- `KERNEL32!GetProcAddress` at `0x18000ebc6`
- `KERNEL32!GetProcAddress` at `0x18000ebc6`

## pseudocode

```c
_BOOL8 __fastcall ValidateTrace(wchar_t *FullPath)
{
  BOOL v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // r9
  HMODULE v5; // rax
  HMODULE v6; // rdi
  unsigned int (*ProcAddress)(void); // rax
  wchar_t Ext; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v10[526]; // [rsp+52h] [rbp-AEh] BYREF
  wchar_t Filename; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v12[526]; // [rsp+262h] [rbp+162h] BYREF
  wchar_t Buffer; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v14[526]; // [rsp+472h] [rbp+372h] BYREF

  Filename = 0;
  v2 = 0;
  memset_0(v12, 0, 0x208u);
  Ext = 0;
  memset_0(v10, 0, 0x208u);
  Buffer = 0;
  memset_0(v14, 0, 0x208u);
  if ( FullPath )
  {
    if ( *FullPath )
    {
      _wsplitpath_s(FullPath, 0, 0, 0, 0, &Filename, 0x105u, &Ext, 0x105u);
      _wmakepath_s(&Buffer, 0x105u, 0, 0, &Filename, &Ext);
      PrivateDriverRootInitialized((HMODULE)hinst);
      v5 = LoadLibraryPD(&Buffer, v3, 8, v4);
      v6 = v5;
      if ( v5 )
      {
        ProcAddress = (unsigned int (*)(void))GetProcAddress(v5, "TraceVersion");
        if ( ProcAddress )
          v2 = ProcAddress() >= 0x3E8;
        FreeLibrary(v6);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000ea9c  mov     [rsp-8+arg_8], rbx
0x18000eaa1  mov     [rsp-8+arg_10], rsi
0x18000eaa6  push    rbp
0x18000eaa7  push    rdi
0x18000eaa8  push    r14
0x18000eaaa  lea     rbp, [rsp-590h]
0x18000eab2  sub     rsp, 690h
0x18000eab9  mov     rax, cs:__security_cookie
0x18000eac0  xor     rax, rsp
0x18000eac3  mov     [rbp+5A0h+var_20], rax
0x18000eaca  mov     rdi, rcx
0x18000eacd  xor     r14d, r14d
0x18000ead0  mov     esi, 208h
0x18000ead5  mov     [rbp+5A0h+var_440], r14w
0x18000eadd  mov     r8d, esi; Size
0x18000eae0  lea     rcx, [rbp+5A0h+var_43E]; void *
0x18000eae7  xor     edx, edx; Val
0x18000eae9  mov     ebx, r14d
0x18000eaec  call    memset_0
0x18000eaf1  mov     r8d, esi; Size
0x18000eaf4  mov     [rsp+6A0h+var_650], r14w
0x18000eafa  xor     edx, edx; Val
0x18000eafc  lea     rcx, [rsp+6A0h+var_64E]; void *
0x18000eb01  call    memset_0
0x18000eb06  mov     r8d, esi; Size
0x18000eb09  mov     [rbp+5A0h+Buffer], r14w
0x18000eb11  xor     edx, edx; Val
0x18000eb13  lea     rcx, [rbp+5A0h+var_22E]; void *
0x18000eb1a  call    memset_0
0x18000eb1f  test    rdi, rdi
0x18000eb22  jz      loc_18000EBEB
0x18000eb28  cmp     [rdi], r14w
0x18000eb2c  jz      loc_18000EBEB
0x18000eb32  mov     esi, 105h
0x18000eb37  lea     rax, [rsp+6A0h+var_650]
0x18000eb3c  mov     [rsp+6A0h+ExtCount], rsi; ExtCount
0x18000eb41  xor     r9d, r9d; Dir
0x18000eb44  mov     [rsp+6A0h+Ext], rax; Ext
0x18000eb49  xor     r8d, r8d; DriveCount
0x18000eb4c  lea     rax, [rbp+5A0h+var_440]
0x18000eb53  mov     [rsp+6A0h+FilenameCount], rsi; FilenameCount
0x18000eb58  mov     [rsp+6A0h+Filename], rax; Filename
0x18000eb5d  xor     edx, edx; Drive
0x18000eb5f  mov     rcx, rdi; FullPath
0x18000eb62  mov     [rsp+6A0h+DirCount], r14; DirCount
0x18000eb67  call    cs:__imp__wsplitpath_s
0x18000eb6d  lea     rax, [rsp+6A0h+var_650]
0x18000eb72  xor     r9d, r9d; Dir
0x18000eb75  mov     [rsp+6A0h+Filename], rax; Ext
0x18000eb7a  lea     rcx, [rbp+5A0h+Buffer]; Buffer
0x18000eb81  lea     rax, [rbp+5A0h+var_440]
0x18000eb88  xor     r8d, r8d; Drive
0x18000eb8b  mov     edx, esi; BufferCount
0x18000eb8d  mov     [rsp+6A0h+DirCount], rax; Filename
0x18000eb92  call    cs:__imp__wmakepath_s
0x18000eb98  mov     rcx, cs:hinst
0x18000eb9f  call    PrivateDriverRootInitialized
0x18000eba4  lea     r8d, [r14+8]
0x18000eba8  lea     rcx, [rbp+5A0h+Buffer]; lpLibFileName
0x18000ebaf  call    LoadLibraryPD
0x18000ebb4  mov     rdi, rax
0x18000ebb7  test    rax, rax
0x18000ebba  jz      short loc_18000EBEB
0x18000ebbc  lea     rdx, aTraceversion; "TraceVersion"
0x18000ebc3  mov     rcx, rax; hModule
0x18000ebc6  call    cs:__imp_GetProcAddress
0x18000ebcc  test    rax, rax
0x18000ebcf  jz      short loc_18000EBE2
0x18000ebd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd6  cmp     eax, 3E8h
0x18000ebdb  lea     ecx, [r14+1]
0x18000ebdf  cmovnb  ebx, ecx
0x18000ebe2  mov     rcx, rdi; hLibModule
0x18000ebe5  call    cs:__imp_FreeLibrary
0x18000ebeb  mov     eax, ebx
0x18000ebed  mov     rcx, [rbp+5A0h+var_20]
0x18000ebf4  xor     rcx, rsp; StackCookie
0x18000ebf7  call    __security_check_cookie
0x18000ebfc  lea     r11, [rsp+6A0h+var_10]
0x18000ec04  mov     rbx, [r11+28h]
0x18000ec08  mov     rsi, [r11+30h]
0x18000ec0c  mov     rsp, r11
0x18000ec0f  pop     r14
0x18000ec11  pop     rdi
0x18000ec12  pop     rbp
0x18000ec13  retn
```
