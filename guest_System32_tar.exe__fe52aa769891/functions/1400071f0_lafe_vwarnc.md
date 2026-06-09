# lafe_vwarnc

- ea: `0x1400071f0`
- end: `0x140007292`
- name: `lafe_vwarnc`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400071a4`
- `0x140007298`

## callees

- `0x140001b96`
- `0x140001cc4`
- `0x140001d10`
- `0x1400071f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x140007245`
- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x140007245`

## pseudocode

```c
int __fastcall lafe_vwarnc(unsigned int a1, const char *a2, va_list a3)
{
  FILE *v6; // rax
  FILE *v7; // rax
  const char *v8; // rbx
  FILE *v9; // rax
  FILE *v10; // rax

  v6 = o___acrt_iob_func_0(2u);
  fprintf(v6, "%s: ", (const char *)qword_14000F118);
  v7 = o___acrt_iob_func_0(2u);
  vfprintf(v7, a2, a3);
  if ( a1 )
  {
    v8 = (const char *)_o_strerror(a1);
    v9 = o___acrt_iob_func_0(2u);
    fprintf(v9, ": %s", v8);
  }
  v10 = o___acrt_iob_func_0(2u);
  return fprintf(v10, "\n");
}

```

## disassembly

```asm
0x1400071f0  mov     [rsp+arg_0], rbx
0x1400071f5  mov     [rsp+arg_8], rsi
0x1400071fa  push    rdi
0x1400071fb  sub     rsp, 20h
0x1400071ff  mov     esi, ecx
0x140007201  mov     rbx, r8
0x140007204  mov     ecx, 2; Ix
0x140007209  mov     rdi, rdx
0x14000720c  call    _o___acrt_iob_func_0
0x140007211  mov     r8, cs:qword_14000F118
0x140007218  lea     rdx, aS_2; "%s: "
0x14000721f  mov     rcx, rax; Stream
0x140007222  call    fprintf
0x140007227  mov     ecx, 2; Ix
0x14000722c  call    _o___acrt_iob_func_0
0x140007231  mov     rcx, rax; Stream
0x140007234  mov     r8, rbx; ArgList
0x140007237  mov     rdx, rdi; Format
0x14000723a  call    vfprintf
0x14000723f  test    esi, esi
0x140007241  jz      short loc_14000726A
0x140007243  mov     ecx, esi
0x140007245  call    cs:__imp__o_strerror
0x14000724b  mov     ecx, 2; Ix
0x140007250  mov     rbx, rax
0x140007253  call    _o___acrt_iob_func_0
0x140007258  mov     rcx, rax; Stream
0x14000725b  lea     rdx, aS_1; ": %s"
0x140007262  mov     r8, rbx
0x140007265  call    fprintf
0x14000726a  mov     ecx, 2; Ix
0x14000726f  call    _o___acrt_iob_func_0
0x140007274  mov     rcx, rax
0x140007277  lea     rdx, asc_14000B8DC; "\n"
0x14000727e  mov     rbx, [rsp+28h+arg_0]
0x140007283  mov     rsi, [rsp+28h+arg_8]
0x140007288  add     rsp, 20h
0x14000728c  pop     rdi
0x14000728d  jmp     fprintf
```
