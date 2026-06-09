# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140004314`
- end: `0x1400043d0`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `188`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003ea4`
- `0x140005630`
- `0x14000c498`
- `0x14000f768`
- `0x140010114`

## callees

- `0x140004314`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140004314  mov     [rsp+arg_0], rbx
0x140004319  mov     [rsp+arg_8], rdi
0x14000431e  lea     rax, [rdx-1]
0x140004322  mov     r10d, 7FFFFFFEh
0x140004328  mov     r9, rdx
0x14000432b  mov     rbx, rcx
0x14000432e  cmp     rax, r10
0x140004331  ja      loc_1400043BD
0x140004337  mov     r11, rdx
0x14000433a  mov     rax, rcx
0x14000433d  xor     edi, edi
0x14000433f  cmp     [rax], di
0x140004342  jz      short loc_14000434E
0x140004344  add     rax, 2
0x140004348  sub     r11, 1
0x14000434c  jnz     short loc_14000433F
0x14000434e  mov     rax, r11
0x140004351  mov     rcx, r9
0x140004354  neg     rax
0x140004357  mov     rax, r11
0x14000435a  sbb     edx, edx
0x14000435c  sub     rcx, r11
0x14000435f  not     edx
0x140004361  and     edx, 80070057h
0x140004367  neg     rax
0x14000436a  sbb     rax, rax
0x14000436d  and     rax, rcx
0x140004370  test    r11, r11
0x140004373  jz      short loc_1400043C2
0x140004375  sub     r9, rax
0x140004378  lea     rax, [rbx+rax*2]
0x14000437c  jz      short loc_1400043A0
0x14000437e  test    r10, r10
0x140004381  jz      short loc_1400043A0
0x140004383  movzx   ecx, word ptr [r8]
0x140004387  test    cx, cx
0x14000438a  jz      short loc_1400043A0
0x14000438c  mov     [rax], cx
0x14000438f  add     r8, 2
0x140004393  add     rax, 2
0x140004397  dec     r10
0x14000439a  sub     r9, 1
0x14000439e  jnz     short loc_14000437E
0x1400043a0  test    r9, r9
0x1400043a3  lea     rcx, [rax-2]
0x1400043a7  cmovnz  rcx, rax
0x1400043ab  neg     r9
0x1400043ae  sbb     edx, edx
0x1400043b0  not     edx
0x1400043b2  and     edx, 8007007Ah
0x1400043b8  mov     [rcx], di
0x1400043bb  jmp     short loc_1400043C2
0x1400043bd  mov     edx, 80070057h
0x1400043c2  mov     rbx, [rsp+arg_0]
0x1400043c7  mov     eax, edx
0x1400043c9  mov     rdi, [rsp+arg_8]
0x1400043ce  retn
```
