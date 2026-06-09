# StringCbCopyA(char *,unsigned __int64,char const *)

- ea: `0x180005fd4`
- end: `0x18000601d`
- name: `?StringCbCopyA@@YAJPEAD_KPEBD@Z`
- size: `73`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003db4`
- `0x180003df0`

## callees

- `0x180005fd4`

## pseudocode

```c
__int64 __fastcall StringCbCopyA(char *a1, __int64 a2, char *a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  char *v6; // rcx
  __int64 result; // rax

  v4 = 2147483646;
  v5 = 260;
  do
  {
    if ( !v4 )
      break;
    if ( !*a3 )
      break;
    *a1++ = *a3++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = a1 - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = a1;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x180005fd4  mov     r9, rcx
0x180005fd7  mov     eax, 7FFFFFFEh
0x180005fdc  mov     edx, 104h
0x180005fe1  test    rax, rax
0x180005fe4  jz      short loc_180005FFF
0x180005fe6  mov     cl, [r8]
0x180005fe9  test    cl, cl
0x180005feb  jz      short loc_180005FFF
0x180005fed  mov     [r9], cl
0x180005ff0  inc     r8
0x180005ff3  inc     r9
0x180005ff6  dec     rax
0x180005ff9  sub     rdx, 1
0x180005ffd  jnz     short loc_180005FE1
0x180005fff  mov     rax, rdx
0x180006002  lea     rcx, [r9-1]
0x180006006  neg     rax
0x180006009  sbb     eax, eax
0x18000600b  not     eax
0x18000600d  and     eax, 8007007Ah
0x180006012  test    rdx, rdx
0x180006015  cmovnz  rcx, r9
0x180006019  mov     byte ptr [rcx], 0
0x18000601c  retn
```
