# DetourCopyInstruction

- ea: `0x140003800`
- end: `0x1400038c5`
- name: `DetourCopyInstruction`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400022d0`

## callees

- `0x140003800`
- `0x1400109c0`
- `0x140011010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000387c`
- `KERNEL32!SetLastError` at `0x14000387c`

## pseudocode

```c
__int64 __fastcall DetourCopyInstruction(char *a1, __int64 a2, unsigned __int8 *a3, char *a4, char *a5)
{
  char *v5; // rdx
  char *v8; // rcx
  char *v9; // rcx
  _QWORD v11[5]; // [rsp+30h] [rbp-98h] BYREF
  char *v12; // [rsp+58h] [rbp-70h]
  char v13; // [rsp+60h] [rbp-68h] BYREF
  char v14; // [rsp+68h] [rbp-60h] BYREF
  char v15; // [rsp+70h] [rbp-58h] BYREF

  v5 = &v14;
  memset(v11, 0, 24);
  v8 = &v13;
  if ( a4 )
    v5 = a4;
  v11[4] = v5;
  if ( a5 )
    v8 = a5;
  v12 = v8;
  v9 = &v15;
  *(_QWORD *)v5 = 0;
  if ( a1 )
    v9 = a1;
  *(_DWORD *)v12 = 0;
  if ( a3 )
    return (*((__int64 (__fastcall **)(_QWORD *, const struct CDetourDis::COPYENTRY near *const *, char *, unsigned __int8 *))&CDetourDis::s_rceCopyTable
            + 2 * *a3
            + 1))(
             v11,
             &CDetourDis::s_rceCopyTable + 2 * *a3,
             v9,
             a3);
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x140003800  push    rbx
0x140003802  sub     rsp, 0C0h
0x140003809  mov     rax, cs:__security_cookie
0x140003810  xor     rax, rsp
0x140003813  mov     [rsp+0C8h+var_18], rax
0x14000381b  mov     rax, [rsp+0C8h+arg_20]
0x140003823  lea     rdx, [rsp+0C8h+var_60]
0x140003828  xor     ebx, ebx
0x14000382a  mov     r10, r8
0x14000382d  mov     r8, rcx
0x140003830  mov     [rsp+0C8h+var_98], rbx
0x140003835  test    r9, r9
0x140003838  mov     [rsp+0C8h+var_90], rbx
0x14000383d  mov     [rsp+0C8h+var_88], rbx
0x140003842  lea     rcx, [rsp+0C8h+var_68]
0x140003847  cmovnz  rdx, r9
0x14000384b  test    rax, rax
0x14000384e  mov     [rsp+0C8h+var_78], rdx
0x140003853  cmovnz  rcx, rax
0x140003857  test    r8, r8
0x14000385a  mov     [rsp+0C8h+var_70], rcx
0x14000385f  lea     rcx, [rsp+0C8h+var_58]
0x140003864  mov     [rdx], rbx
0x140003867  cmovnz  rcx, r8
0x14000386b  mov     rax, [rsp+0C8h+var_70]
0x140003870  mov     [rax], ebx
0x140003872  test    r10, r10
0x140003875  jnz     short loc_140003886
0x140003877  mov     ecx, 0Dh; dwErrCode
0x14000387c  call    cs:__imp_SetLastError
0x140003882  mov     eax, ebx
0x140003884  jmp     short loc_1400038AC
0x140003886  movzx   eax, byte ptr [r10]
0x14000388a  lea     rdx, ?s_rceCopyTable@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable
0x140003891  shl     rax, 4
0x140003895  mov     r8, rcx
0x140003898  add     rdx, rax
0x14000389b  lea     rcx, [rsp+0C8h+var_98]
0x1400038a0  mov     r9, r10
0x1400038a3  mov     rax, [rdx+8]
0x1400038a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038ac  mov     rcx, [rsp+0C8h+var_18]
0x1400038b4  xor     rcx, rsp; StackCookie
0x1400038b7  call    __security_check_cookie
0x1400038bc  add     rsp, 0C0h
0x1400038c3  pop     rbx
0x1400038c4  retn
```
