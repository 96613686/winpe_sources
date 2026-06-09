# NDXGI::CUMDAdapter::LogStringTableEntryCB(void *,uint,ushort const *)

- ea: `0x1800ba450`
- end: `0x1800ba53b`
- name: `?LogStringTableEntryCB@CUMDAdapter@NDXGI@@KAJPEAXIPEBG@Z`
- size: `235`
- prototype: `static int(void *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800a9d20`
- `0x1800ba450`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800ba4d4`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x1800ba4d4`
- `ntdll!EtwEventWrite` at `0x1800ba51c`
- `ntdll!EtwEventWrite` at `0x1800ba51c`

## pseudocode

```c
__int64 __fastcall NDXGI::CUMDAdapter::LogStringTableEntryCB(char *a1, int a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // rbx
  int v4; // eax
  _QWORD v6[5]; // [rsp+20h] [rbp-40h] BYREF
  int v7; // [rsp+48h] [rbp-18h]
  int v8; // [rsp+4Ch] [rbp-14h]
  int v9; // [rsp+78h] [rbp+18h] BYREF

  v9 = a2;
  v3 = a3;
  if ( dword_1802282A4
    && (qword_180228290 & 0x8000000000000400uLL) != 0
    && (qword_180228298 & 0x8000000000000400uLL) == qword_180228298 )
  {
    v6[1] = 8;
    v6[0] = a1 + 920;
    v6[2] = &v9;
    v6[3] = 4;
    if ( a3 )
      v4 = 2 * wcslen(a3) + 2;
    else
      v4 = 2;
    v7 = v4;
    v8 = 0;
    if ( !v3 )
      v3 = (const unsigned __int16 *)&unk_1801F94F0;
    v6[4] = v3;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11CustomDriverStringTable, 3, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ba450  mov     [rsp-8+arg_0], rbx
0x1800ba455  mov     [rsp-8+arg_8], edx
0x1800ba459  push    rbp
0x1800ba45a  mov     rbp, rsp
0x1800ba45d  sub     rsp, 60h
0x1800ba461  mov     rax, cs:__security_cookie
0x1800ba468  xor     rax, rsp
0x1800ba46b  mov     [rbp+var_10], rax
0x1800ba46f  cmp     cs:dword_1802282A4, 0
0x1800ba476  mov     rbx, r8
0x1800ba479  jz      loc_1800BA522
0x1800ba47f  mov     r8, 8000000000000400h
0x1800ba489  test    cs:qword_180228290, r8
0x1800ba490  jz      loc_1800BA522
0x1800ba496  mov     rax, cs:qword_180228298
0x1800ba49d  and     rax, r8
0x1800ba4a0  cmp     rax, cs:qword_180228298
0x1800ba4a7  jnz     short loc_1800BA522
0x1800ba4a9  mov     [rbp+var_38], 8
0x1800ba4b1  lea     rax, [rcx+398h]
0x1800ba4b8  mov     [rbp+var_40], rax
0x1800ba4bc  lea     rax, [rbp+arg_8]
0x1800ba4c0  mov     [rbp+var_30], rax
0x1800ba4c4  mov     [rbp+var_28], 4
0x1800ba4cc  test    rbx, rbx
0x1800ba4cf  jz      short loc_1800BA4E3
0x1800ba4d1  mov     rcx, rbx; String
0x1800ba4d4  call    cs:__imp_wcslen
0x1800ba4da  lea     eax, ds:2[rax*2]
0x1800ba4e1  jmp     short loc_1800BA4E8
0x1800ba4e3  mov     eax, 2
0x1800ba4e8  test    rbx, rbx
0x1800ba4eb  mov     [rbp+var_18], eax
0x1800ba4ee  lea     rcx, unk_1801F94F0
0x1800ba4f5  mov     [rbp+var_14], 0
0x1800ba4fc  cmovz   rbx, rcx
0x1800ba500  lea     r9, [rbp+var_40]
0x1800ba504  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800ba50b  lea     rdx, EventD3D11CustomDriverStringTable
0x1800ba512  mov     r8d, 3
0x1800ba518  mov     [rbp+var_20], rbx
0x1800ba51c  call    cs:__imp_EtwEventWrite
0x1800ba522  xor     eax, eax
0x1800ba524  mov     rcx, [rbp+var_10]
0x1800ba528  xor     rcx, rsp; StackCookie
0x1800ba52b  call    __security_check_cookie
0x1800ba530  mov     rbx, [rsp+60h+arg_0]
0x1800ba535  add     rsp, 60h
0x1800ba539  pop     rbp
0x1800ba53a  retn
```
