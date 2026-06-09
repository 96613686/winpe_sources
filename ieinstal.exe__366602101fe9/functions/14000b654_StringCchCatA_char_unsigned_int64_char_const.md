# StringCchCatA(char *,unsigned __int64,char const *)

- ea: `0x14000b654`
- end: `0x14000b6fa`
- name: `?StringCchCatA@@YAJPEAD_KPEBD@Z`
- size: `166`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a0c`
- `0x140008c74`
- `0x14000abd4`

## callees

- `0x14000b654`

## pseudocode

```c
__int64 __fastcall StringCchCatA(char *a1, __int64 a2, char *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  char *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  char *v9; // rcx
  __int64 i; // r9
  char *v11; // rax

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
      v9 = &a1[v8];
      for ( i = a2 - v8; i; --i )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *v9++ = *a3++;
        --v3;
      }
      v11 = v9 - 1;
      if ( i )
        v11 = v9;
      v7 = i == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14000b654  mov     [rsp+arg_0], rbx
0x14000b659  lea     rax, [rdx-1]
0x14000b65d  mov     r10d, 7FFFFFFEh
0x14000b663  mov     r9, rdx
0x14000b666  mov     rbx, rcx
0x14000b669  cmp     rax, r10
0x14000b66c  ja      short loc_14000B6EC
0x14000b66e  mov     r11, rdx
0x14000b671  mov     rax, rcx
0x14000b674  cmp     byte ptr [rax], 0
0x14000b677  jz      short loc_14000B682
0x14000b679  inc     rax
0x14000b67c  sub     r11, 1
0x14000b680  jnz     short loc_14000B674
0x14000b682  mov     rax, r11
0x14000b685  mov     rcx, r9
0x14000b688  neg     rax
0x14000b68b  mov     rax, r11
0x14000b68e  sbb     edx, edx
0x14000b690  sub     rcx, r11
0x14000b693  not     edx
0x14000b695  and     edx, 80070057h
0x14000b69b  neg     rax
0x14000b69e  sbb     rax, rax
0x14000b6a1  and     rax, rcx
0x14000b6a4  test    r11, r11
0x14000b6a7  jz      short loc_14000B6F1
0x14000b6a9  lea     rcx, [rax+rbx]
0x14000b6ad  sub     r9, rax
0x14000b6b0  jz      short loc_14000B6CF
0x14000b6b2  test    r10, r10
0x14000b6b5  jz      short loc_14000B6CF
0x14000b6b7  mov     al, [r8]
0x14000b6ba  test    al, al
0x14000b6bc  jz      short loc_14000B6CF
0x14000b6be  mov     [rcx], al
0x14000b6c0  inc     r8
0x14000b6c3  inc     rcx
0x14000b6c6  dec     r10
0x14000b6c9  sub     r9, 1
0x14000b6cd  jnz     short loc_14000B6B2
0x14000b6cf  test    r9, r9
0x14000b6d2  lea     rax, [rcx-1]
0x14000b6d6  cmovnz  rax, rcx
0x14000b6da  neg     r9
0x14000b6dd  sbb     edx, edx
0x14000b6df  not     edx
0x14000b6e1  and     edx, 8007007Ah
0x14000b6e7  mov     byte ptr [rax], 0
0x14000b6ea  jmp     short loc_14000B6F1
0x14000b6ec  mov     edx, 80070057h
0x14000b6f1  mov     rbx, [rsp+arg_0]
0x14000b6f6  mov     eax, edx
0x14000b6f8  retn
```
