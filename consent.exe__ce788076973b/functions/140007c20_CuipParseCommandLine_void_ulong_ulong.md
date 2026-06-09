# CuipParseCommandLine(void * *,ulong *,ulong *)

- ea: `0x140007c20`
- end: `0x140007cd5`
- name: `?CuipParseCommandLine@@YAJPEAPEAXPEAK1@Z`
- size: `181`
- prototype: `__int64 __fastcall(void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140007c20`

## import_xrefs

- `msvcrt!swscanf_s` at `0x140007c6c`
- `msvcrt!swscanf_s` at `0x140007c8b`
- `msvcrt!swscanf_s` at `0x140007ca4`
- `msvcrt!swscanf_s` at `0x140007c6c`
- `msvcrt!swscanf_s` at `0x140007c8b`
- `msvcrt!swscanf_s` at `0x140007ca4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140007cbc`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140007cbc`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140007c3b`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x140007c3b`
- `SHELL32!CommandLineToArgvW` at `0x140007c49`
- `SHELL32!CommandLineToArgvW` at `0x140007c49`

## pseudocode

```c
__int64 __fastcall CuipParseCommandLine(void **a1, unsigned int *a2, unsigned int *a3)
{
  const WCHAR *CommandLineW; // rax
  LPWSTR *v7; // rax
  const wchar_t **v8; // rdi
  unsigned int v9; // ebx
  int pNumArgs; // [rsp+68h] [rbp+20h] BYREF

  pNumArgs = 0;
  CommandLineW = GetCommandLineW();
  v7 = CommandLineToArgvW(CommandLineW, &pNumArgs);
  v8 = (const wchar_t **)v7;
  if ( v7 )
  {
    if ( pNumArgs >= 4
      && (swscanf_s(v7[1], L"%u", a3), *a3)
      && (*a3 & 3) == 0
      && (swscanf_s(v8[2], L"%u", a2), *a2)
      && (swscanf_s(v8[3], L"%p", a1), *a1) )
    {
      v9 = 0;
    }
    else
    {
      v9 = -1073741811;
    }
  }
  else
  {
    v9 = -1073741801;
  }
  GlobalFree(v8);
  return v9;
}

```

## disassembly

```asm
0x140007c20  push    rbx
0x140007c22  push    rsi
0x140007c23  push    rdi
0x140007c24  push    r14
0x140007c26  sub     rsp, 28h
0x140007c2a  mov     r14, r8
0x140007c2d  mov     [rsp+48h+pNumArgs], 0
0x140007c35  mov     rsi, rdx
0x140007c38  mov     rbx, rcx
0x140007c3b  call    cs:__imp_GetCommandLineW
0x140007c41  mov     rcx, rax; lpCmdLine
0x140007c44  lea     rdx, [rsp+48h+pNumArgs]; pNumArgs
0x140007c49  call    cs:__imp_CommandLineToArgvW
0x140007c4f  mov     rdi, rax
0x140007c52  test    rax, rax
0x140007c55  jz      short loc_140007CCE
0x140007c57  cmp     [rsp+48h+pNumArgs], 4
0x140007c5c  jl      short loc_140007CB4
0x140007c5e  mov     rcx, [rax+8]; Buffer
0x140007c62  lea     rdx, aU; "%u"
0x140007c69  mov     r8, r14
0x140007c6c  call    cs:__imp_swscanf_s
0x140007c72  mov     eax, [r14]
0x140007c75  test    eax, eax
0x140007c77  jz      short loc_140007CB4
0x140007c79  test    al, 3
0x140007c7b  jnz     short loc_140007CB4
0x140007c7d  mov     rcx, [rdi+10h]; Buffer
0x140007c81  lea     rdx, aU; "%u"
0x140007c88  mov     r8, rsi
0x140007c8b  call    cs:__imp_swscanf_s
0x140007c91  cmp     dword ptr [rsi], 0
0x140007c94  jz      short loc_140007CB4
0x140007c96  mov     rcx, [rdi+18h]; Buffer
0x140007c9a  lea     rdx, aP; "%p"
0x140007ca1  mov     r8, rbx
0x140007ca4  call    cs:__imp_swscanf_s
0x140007caa  cmp     qword ptr [rbx], 0
0x140007cae  jz      short loc_140007CB4
0x140007cb0  xor     ebx, ebx
0x140007cb2  jmp     short loc_140007CB9
0x140007cb4  mov     ebx, 0C000000Dh
0x140007cb9  mov     rcx, rdi; hMem
0x140007cbc  call    cs:__imp_GlobalFree
0x140007cc2  mov     eax, ebx
0x140007cc4  add     rsp, 28h
0x140007cc8  pop     r14
0x140007cca  pop     rdi
0x140007ccb  pop     rsi
0x140007ccc  pop     rbx
0x140007ccd  retn
0x140007cce  mov     ebx, 0C0000017h
0x140007cd3  jmp     short loc_140007CB9
```
