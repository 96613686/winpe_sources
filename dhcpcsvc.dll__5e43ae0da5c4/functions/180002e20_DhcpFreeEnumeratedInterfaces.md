# DhcpFreeEnumeratedInterfaces

- ea: `0x180002e20`
- end: `0x180002e8d`
- name: `DhcpFreeEnumeratedInterfaces`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ca0`

## callees

- `0x180002e20`
- `0x1800127f0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002e36`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180002e36`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002e75`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002e75`

## pseudocode

```c
__int64 __fastcall DhcpFreeEnumeratedInterfaces(_DWORD *a1)
{
  LPWSTR CommandLineW; // rax
  HLOCAL *v3; // rbx
  __int64 result; // rax

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_S(1028, 138, WPP_e15037783097355a5233924022d92169_Traceguids, CommandLineW);
  }
  v3 = (HLOCAL *)(a1 + 2);
  if ( a1 != (_DWORD *)-8LL && *v3 )
  {
    LocalFree(*v3);
    result = 0;
    *v3 = 0;
    *a1 = 0;
  }
  else
  {
    result = 0;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002e20  mov     [rsp+arg_0], rbx
0x180002e25  push    rdi
0x180002e26  sub     rsp, 20h
0x180002e2a  mov     rdi, rcx
0x180002e2d  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002e34  jz      short loc_180002E55
0x180002e36  call    cs:__imp_GetCommandLineW
0x180002e3c  mov     edx, 8Ah
0x180002e41  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180002e48  mov     r9, rax
0x180002e4b  mov     ecx, 404h
0x180002e50  call    WPP_SF_S
0x180002e55  lea     rbx, [rdi+8]
0x180002e59  test    rbx, rbx
0x180002e5c  jz      short loc_180002E66
0x180002e5e  mov     rcx, [rbx]; hMem
0x180002e61  test    rcx, rcx
0x180002e64  jnz     short loc_180002E75
0x180002e66  xor     eax, eax
0x180002e68  mov     [rdi], eax
0x180002e6a  mov     rbx, [rsp+28h+arg_0]
0x180002e6f  add     rsp, 20h
0x180002e73  pop     rdi
0x180002e74  retn
0x180002e75  call    cs:__imp_LocalFree
0x180002e7b  xor     eax, eax
0x180002e7d  mov     [rbx], rax
0x180002e80  mov     rbx, [rsp+28h+arg_0]
0x180002e85  mov     [rdi], eax
0x180002e87  add     rsp, 20h
0x180002e8b  pop     rdi
0x180002e8c  retn
```
