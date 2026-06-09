# Bind_KERNEL32(char const *,__int64 (**)(void))

- ea: `0x140008dfc`
- end: `0x140008e90`
- name: `?Bind_KERNEL32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z`
- size: `148`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName, __int64 (**)(void)))(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140008ff0`
- `0x1400091f0`
- `0x140009370`

## callees

- `0x140008dfc`
- `0x1400094c4`

## import_xrefs

- `KERNEL32!Sleep` at `0x140008e1f`
- `KERNEL32!Sleep` at `0x140008e1f`
- `KERNEL32!GetProcAddress` at `0x140008e67`
- `KERNEL32!GetProcAddress` at `0x140008e67`

## pseudocode

```c
__int64 (*__fastcall Bind_KERNEL32(LPCSTR lpProcName, __int64 (**a2)(void)))(void)
{
  HMODULE SystemLibrary; // rax
  __int64 (*v5)(void); // rcx
  __int64 (*ProcAddress)(void); // rax
  __int64 (*result)(void); // rax

  while ( _InterlockedExchange(&dword_1400111A0, 1) == 1 )
    Sleep(0xAu);
  SystemLibrary = qword_140011198;
  if ( byte_1400101A0 )
  {
    if ( !qword_140011198 )
    {
      SystemLibrary = LoadSystemLibrary(L"KERNEL32");
      qword_140011198 = SystemLibrary;
      if ( !SystemLibrary )
        byte_1400101A0 = 0;
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
  dword_1400111A0 = 0;
  return result;
}

```

## disassembly

```asm
0x140008dfc  mov     [rsp+arg_0], rbx
0x140008e01  push    rdi
0x140008e02  sub     rsp, 20h
0x140008e06  mov     rbx, rdx
0x140008e09  mov     rdi, rcx
0x140008e0c  mov     eax, 1
0x140008e11  xchg    eax, cs:dword_1400111A0
0x140008e17  cmp     eax, 1
0x140008e1a  jnz     short loc_140008E27
0x140008e1c  lea     ecx, [rax+9]; dwMilliseconds
0x140008e1f  call    cs:__imp_Sleep
0x140008e25  jmp     short loc_140008E0C
0x140008e27  cmp     cs:byte_1400101A0, 0
0x140008e2e  mov     rax, cs:qword_140011198
0x140008e35  jz      short loc_140008E5A
0x140008e37  test    rax, rax
0x140008e3a  jnz     short loc_140008E5A
0x140008e3c  lea     rcx, aKernel32; "KERNEL32"
0x140008e43  call    ?LoadSystemLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; LoadSystemLibrary(ushort const *)
0x140008e48  mov     cs:qword_140011198, rax
0x140008e4f  test    rax, rax
0x140008e52  jnz     short loc_140008E5A
0x140008e54  mov     cs:byte_1400101A0, al
0x140008e5a  xor     ecx, ecx
0x140008e5c  test    rax, rax
0x140008e5f  jz      short loc_140008E78
0x140008e61  mov     rdx, rdi; lpProcName
0x140008e64  mov     rcx, rax; hModule
0x140008e67  call    cs:__imp_GetProcAddress
0x140008e6d  mov     rcx, rax
0x140008e70  test    rax, rax
0x140008e73  jz      short loc_140008E78
0x140008e75  mov     [rbx], rax
0x140008e78  mov     rbx, [rsp+28h+arg_0]
0x140008e7d  mov     rax, rcx
0x140008e80  mov     cs:dword_1400111A0, 0
0x140008e8a  add     rsp, 20h
0x140008e8e  pop     rdi
0x140008e8f  retn
```
