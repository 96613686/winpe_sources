# GetNextSectionPtrSafe(unsigned __int64,unsigned __int64,unsigned __int64,char *)

- ea: `0x140002304`
- end: `0x140002394`
- name: `?GetNextSectionPtrSafe@@YAPEAD_K00PEAD@Z`
- size: `144`
- prototype: `char *__fastcall(unsigned __int64, unsigned __int64, unsigned __int64, char *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000239c`
- `0x140002460`
- `0x140002d24`
- `0x140009bfc`
- `0x140009c34`
- `0x14001e6e8`

## callees

- `0x140002304`
- `0x140002ee8`

## pseudocode

```c
char *__fastcall GetNextSectionPtrSafe(unsigned __int64 a1, unsigned __int64 a2, unsigned __int64 a3, char *a4)
{
  unsigned __int64 v6; // rax
  char *result; // rax
  unsigned __int64 v8; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v9; // [rsp+28h] [rbp-8h]
  bool v10; // [rsp+48h] [rbp+18h] BYREF

  v8 = a2;
  v9 = a3;
  v10 = 0;
  v6 = SafeAddPointersEx(2, &v8, &v10);
  if ( v10 )
    return 0;
  v10 = 0;
  if ( ((v6 + 3) & 0xFFFFFFFFFFFFFFFCuLL) < v6 )
    return 0;
  v9 = (v6 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
  v8 = a1;
  result = (char *)SafeAddPointersEx(2, &v8, &v10);
  if ( v10 )
    return 0;
  if ( a4 )
  {
    if ( result > a4 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140002304  mov     [rsp-8+arg_0], rbx
0x140002309  mov     [rsp-8+arg_10], rdi
0x14000230e  push    rbp
0x14000230f  mov     rbp, rsp
0x140002312  sub     rsp, 30h
0x140002316  mov     rdi, rcx
0x140002319  mov     [rbp+var_10], rdx
0x14000231d  mov     [rbp+var_8], r8
0x140002321  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x140002325  lea     r8, [rbp+arg_8]; bool *
0x140002329  mov     [rbp+arg_8], 0
0x14000232d  mov     ecx, 2; int
0x140002332  mov     rbx, r9
0x140002335  call    ?SafeAddPointersEx@@YA_KHQEA_KPEA_N@Z; SafeAddPointersEx(int,unsigned __int64 * const,bool *)
0x14000233a  cmp     [rbp+arg_8], 0
0x14000233e  jnz     short loc_140002381
0x140002340  lea     rdx, [rax+3]
0x140002344  mov     [rbp+arg_8], 0
0x140002348  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14000234c  cmp     rdx, rax
0x14000234f  jb      short loc_140002381
0x140002351  mov     [rbp+var_8], rdx
0x140002355  lea     r8, [rbp+arg_8]; bool *
0x140002359  lea     rdx, [rbp+var_10]; unsigned __int64 *
0x14000235d  mov     [rbp+var_10], rdi
0x140002361  mov     ecx, 2; int
0x140002366  call    ?SafeAddPointersEx@@YA_KHQEA_KPEA_N@Z; SafeAddPointersEx(int,unsigned __int64 * const,bool *)
0x14000236b  cmp     [rbp+arg_8], 0
0x14000236f  jnz     short loc_140002381
0x140002371  test    rbx, rbx
0x140002374  jz      short loc_140002383
0x140002376  xor     ecx, ecx
0x140002378  cmp     rax, rbx
0x14000237b  cmova   rax, rcx
0x14000237f  jmp     short loc_140002383
0x140002381  xor     eax, eax
0x140002383  mov     rbx, [rsp+30h+arg_0]
0x140002388  mov     rdi, [rsp+30h+arg_10]
0x14000238d  add     rsp, 30h
0x140002391  pop     rbp
0x140002392  retn
```
