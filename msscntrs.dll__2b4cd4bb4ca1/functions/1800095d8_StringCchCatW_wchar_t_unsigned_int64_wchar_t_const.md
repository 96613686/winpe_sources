# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x1800095d8`
- end: `0x180009681`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `169`
- prototype: `__int64 __fastcall(wchar_t *, __int64, wchar_t *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005880`
- `0x180009b0c`
- `0x1800111b0`
- `0x180011500`
- `0x1800140d8`

## callees

- `0x1800095d8`

## pseudocode

```c
__int64 __fastcall StringCchCatW(wchar_t *a1, __int64 a2, wchar_t *a3)
{
  __int64 v3; // r10
  wchar_t *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  wchar_t *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  wchar_t *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800095d8  mov     [rsp+arg_0], rbx
0x1800095dd  mov     [rsp+arg_8], rdi
0x1800095e2  mov     r9d, 104h
0x1800095e8  mov     rbx, rcx
0x1800095eb  mov     r10d, r9d
0x1800095ee  mov     rax, rcx
0x1800095f1  xor     edi, edi
0x1800095f3  cmp     [rax], di
0x1800095f6  jz      short loc_180009602
0x1800095f8  add     rax, 2
0x1800095fc  sub     r10, 1
0x180009600  jnz     short loc_1800095F3
0x180009602  mov     rax, r10
0x180009605  mov     rcx, r9
0x180009608  neg     rax
0x18000960b  mov     rax, r10
0x18000960e  sbb     edx, edx
0x180009610  sub     rcx, r10
0x180009613  not     edx
0x180009615  and     edx, 80070057h
0x18000961b  neg     rax
0x18000961e  sbb     r11, r11
0x180009621  and     r11, rcx
0x180009624  test    r10, r10
0x180009627  jz      short loc_180009674
0x180009629  lea     rax, [rbx+r11*2]
0x18000962d  mov     ecx, 7FFFFFFEh
0x180009632  sub     r9, r11
0x180009635  jz      short loc_180009659
0x180009637  test    rcx, rcx
0x18000963a  jz      short loc_180009659
0x18000963c  movzx   edx, word ptr [r8]
0x180009640  test    dx, dx
0x180009643  jz      short loc_180009659
0x180009645  mov     [rax], dx
0x180009648  add     r8, 2
0x18000964c  add     rax, 2
0x180009650  dec     rcx
0x180009653  sub     r9, 1
0x180009657  jnz     short loc_180009637
0x180009659  test    r9, r9
0x18000965c  lea     rcx, [rax-2]
0x180009660  cmovnz  rcx, rax
0x180009664  neg     r9
0x180009667  sbb     edx, edx
0x180009669  not     edx
0x18000966b  and     edx, 8007007Ah
0x180009671  mov     [rcx], di
0x180009674  mov     rbx, [rsp+arg_0]
0x180009679  mov     eax, edx
0x18000967b  mov     rdi, [rsp+arg_8]
0x180009680  retn
```
