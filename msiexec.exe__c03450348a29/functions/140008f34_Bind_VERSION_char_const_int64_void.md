# Bind_VERSION(char const *,__int64 (**)(void))

- ea: `0x140008f34`
- end: `0x140008fc8`
- name: `?Bind_VERSION@@YAP6A_JXZPEBDPEAP6A_JXZ@Z`
- size: `148`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName, __int64 (**)(void)))(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140009250`
- `0x1400092b0`
- `0x140009470`

## callees

- `0x140008f34`
- `0x1400094c4`

## import_xrefs

- `KERNEL32!Sleep` at `0x140008f57`
- `KERNEL32!Sleep` at `0x140008f57`
- `KERNEL32!GetProcAddress` at `0x140008f9f`
- `KERNEL32!GetProcAddress` at `0x140008f9f`

## pseudocode

```c
__int64 (*__fastcall Bind_VERSION(LPCSTR lpProcName, __int64 (**a2)(void)))(void)
{
  HMODULE SystemLibrary; // rax
  __int64 (*v5)(void); // rcx
  __int64 (*ProcAddress)(void); // rax
  __int64 (*result)(void); // rax

  while ( _InterlockedExchange(&dword_1400111B0, 1) == 1 )
    Sleep(0xAu);
  SystemLibrary = qword_1400111A8;
  if ( byte_1400101A1 )
  {
    if ( !qword_1400111A8 )
    {
      SystemLibrary = LoadSystemLibrary(L"VERSION");
      qword_1400111A8 = SystemLibrary;
      if ( !SystemLibrary )
        byte_1400101A1 = 0;
    }
  }
  v5 = 0;
  if ( SystemLibrary )
  {
    ProcAddress = GetProcAddress(SystemLibrary, lpProcName);
    v5 = ProcAddress;
    if ( ProcAddress )
      *a2 = ProcAddress;
  }
  result = v5;
  dword_1400111B0 = 0;
  return result;
}

```

## disassembly

```asm
0x140008f34  mov     [rsp+arg_0], rbx
0x140008f39  push    rdi
0x140008f3a  sub     rsp, 20h
0x140008f3e  mov     rbx, rdx
0x140008f41  mov     rdi, rcx
0x140008f44  mov     eax, 1
0x140008f49  xchg    eax, cs:dword_1400111B0
0x140008f4f  cmp     eax, 1
0x140008f52  jnz     short loc_140008F5F
0x140008f54  lea     ecx, [rax+9]; dwMilliseconds
0x140008f57  call    cs:__imp_Sleep
0x140008f5d  jmp     short loc_140008F44
0x140008f5f  cmp     cs:byte_1400101A1, 0
0x140008f66  mov     rax, cs:qword_1400111A8
0x140008f6d  jz      short loc_140008F92
0x140008f6f  test    rax, rax
0x140008f72  jnz     short loc_140008F92
0x140008f74  lea     rcx, aVersion; "VERSION"
0x140008f7b  call    ?LoadSystemLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; LoadSystemLibrary(ushort const *)
0x140008f80  mov     cs:qword_1400111A8, rax
0x140008f87  test    rax, rax
0x140008f8a  jnz     short loc_140008F92
0x140008f8c  mov     cs:byte_1400101A1, al
0x140008f92  xor     ecx, ecx
0x140008f94  test    rax, rax
0x140008f97  jz      short loc_140008FB0
0x140008f99  mov     rdx, rdi; lpProcName
0x140008f9c  mov     rcx, rax; hModule
0x140008f9f  call    cs:__imp_GetProcAddress
0x140008fa5  mov     rcx, rax
0x140008fa8  test    rax, rax
0x140008fab  jz      short loc_140008FB0
0x140008fad  mov     [rbx], rax
0x140008fb0  mov     rbx, [rsp+28h+arg_0]
0x140008fb5  mov     rax, rcx
0x140008fb8  mov     cs:dword_1400111B0, 0
0x140008fc2  add     rsp, 20h
0x140008fc6  pop     rdi
0x140008fc7  retn
```
