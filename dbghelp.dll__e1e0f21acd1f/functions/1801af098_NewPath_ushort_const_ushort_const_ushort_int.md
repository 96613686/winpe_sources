# NewPath(ushort const *,ushort const *,ushort *,int)

- ea: `0x1801af098`
- end: `0x1801af149`
- name: `?NewPath@@YAPEAGPEBG0PEAGH@Z`
- size: `177`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1801a16d0`

## callees

- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1801af11f`
- `api-ms-win-crt-private-l1-1-0!_o__wmakepath_s` at `0x1801af11f`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801af0f4`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801af0f4`

## pseudocode

```c
unsigned __int16 *__fastcall NewPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  wchar_t Ext[264]; // [rsp+50h] [rbp-438h] BYREF
  wchar_t Filename[264]; // [rsp+260h] [rbp-228h] BYREF

  _wsplitpath_s(a1, 0, 0, 0, 0, Filename, 0x101u, Ext, 0x101u);
  _o__wmakepath_s(a3, 261, 0, a2, Filename, Ext);
  return a3;
}

```

## disassembly

```asm
0x1801af098  mov     [rsp+arg_18], rbx
0x1801af09d  push    rdi
0x1801af09e  sub     rsp, 480h
0x1801af0a5  mov     rax, cs:__security_cookie
0x1801af0ac  xor     rax, rsp
0x1801af0af  mov     [rsp+488h+var_18], rax
0x1801af0b7  mov     rbx, rdx
0x1801af0ba  lea     rax, [rsp+488h+var_438]
0x1801af0bf  mov     edx, 101h
0x1801af0c4  mov     rdi, r8
0x1801af0c7  mov     [rsp+488h+ExtCount], rdx; ExtCount
0x1801af0cc  xor     r9d, r9d; Dir
0x1801af0cf  mov     [rsp+488h+Ext], rax; Ext
0x1801af0d4  xor     r8d, r8d; DriveCount
0x1801af0d7  mov     [rsp+488h+FilenameCount], rdx; FilenameCount
0x1801af0dc  lea     rax, [rsp+488h+var_228]
0x1801af0e4  mov     [rsp+488h+Filename], rax; Filename
0x1801af0e9  xor     edx, edx; Drive
0x1801af0eb  mov     [rsp+488h+DirCount], 0; DirCount
0x1801af0f4  call    cs:__imp__wsplitpath_s
0x1801af0fa  lea     rax, [rsp+488h+var_438]
0x1801af0ff  mov     r9, rbx
0x1801af102  mov     [rsp+488h+Filename], rax
0x1801af107  xor     r8d, r8d
0x1801af10a  lea     rax, [rsp+488h+var_228]
0x1801af112  mov     edx, 105h
0x1801af117  mov     rcx, rdi
0x1801af11a  mov     [rsp+488h+DirCount], rax
0x1801af11f  call    cs:__imp__o__wmakepath_s
0x1801af125  mov     rax, rdi
0x1801af128  mov     rcx, [rsp+488h+var_18]
0x1801af130  xor     rcx, rsp; StackCookie
0x1801af133  call    __security_check_cookie
0x1801af138  mov     rbx, [rsp+488h+arg_18]
0x1801af140  add     rsp, 480h
0x1801af147  pop     rdi
0x1801af148  retn
```
