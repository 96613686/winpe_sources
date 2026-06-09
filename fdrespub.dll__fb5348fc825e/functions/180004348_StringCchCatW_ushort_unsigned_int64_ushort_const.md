# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004348`
- end: `0x180004403`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bc0`
- `0x180003ae8`
- `0x180004498`

## callees

- `0x180004348`

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
0x180004348  mov     [rsp+arg_0], rbx
0x18000434d  mov     [rsp+arg_8], rdi
0x180004352  lea     rax, [rdx-1]
0x180004356  mov     r10d, 7FFFFFFEh
0x18000435c  mov     r9, rdx
0x18000435f  mov     rbx, rcx
0x180004362  cmp     rax, r10
0x180004365  ja      loc_1800043F1
0x18000436b  mov     r11, rdx
0x18000436e  mov     rax, rcx
0x180004371  xor     edi, edi
0x180004373  cmp     [rax], di
0x180004376  jz      short loc_180004382
0x180004378  add     rax, 2
0x18000437c  sub     r11, 1
0x180004380  jnz     short loc_180004373
0x180004382  mov     rax, r11
0x180004385  mov     rcx, r9
0x180004388  neg     rax
0x18000438b  mov     rax, r11
0x18000438e  sbb     edx, edx
0x180004390  sub     rcx, r11
0x180004393  not     edx
0x180004395  and     edx, 80070057h
0x18000439b  neg     rax
0x18000439e  sbb     rax, rax
0x1800043a1  and     rax, rcx
0x1800043a4  test    r11, r11
0x1800043a7  jz      short loc_1800043F6
0x1800043a9  sub     r9, rax
0x1800043ac  lea     rax, [rbx+rax*2]
0x1800043b0  jz      short loc_1800043D4
0x1800043b2  test    r10, r10
0x1800043b5  jz      short loc_1800043D4
0x1800043b7  movzx   ecx, word ptr [r8]
0x1800043bb  test    cx, cx
0x1800043be  jz      short loc_1800043D4
0x1800043c0  mov     [rax], cx
0x1800043c3  add     r8, 2
0x1800043c7  add     rax, 2
0x1800043cb  dec     r10
0x1800043ce  sub     r9, 1
0x1800043d2  jnz     short loc_1800043B2
0x1800043d4  test    r9, r9
0x1800043d7  lea     rcx, [rax-2]
0x1800043db  cmovnz  rcx, rax
0x1800043df  neg     r9
0x1800043e2  sbb     edx, edx
0x1800043e4  not     edx
0x1800043e6  and     edx, 8007007Ah
0x1800043ec  mov     [rcx], di
0x1800043ef  jmp     short loc_1800043F6
0x1800043f1  mov     edx, 80070057h
0x1800043f6  mov     rbx, [rsp+arg_0]
0x1800043fb  mov     eax, edx
0x1800043fd  mov     rdi, [rsp+arg_8]
0x180004402  retn
```
