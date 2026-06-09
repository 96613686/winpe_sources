# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140005170`
- end: `0x14000521a`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `170`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004340`
- `0x1400052dc`

## callees

- `0x140005170`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

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
0x140005170  mov     [rsp+arg_0], rbx
0x140005175  mov     [rsp+arg_8], rdi
0x14000517a  mov     r9d, 104h
0x140005180  mov     rbx, rcx
0x140005183  mov     r10d, r9d
0x140005186  mov     rax, rcx
0x140005189  xor     edi, edi
0x14000518b  cmp     [rax], di
0x14000518e  jz      short loc_14000519A
0x140005190  add     rax, 2
0x140005194  sub     r10, 1
0x140005198  jnz     short loc_14000518B
0x14000519a  mov     rax, r10
0x14000519d  mov     rcx, r9
0x1400051a0  neg     rax
0x1400051a3  mov     rax, r10
0x1400051a6  sbb     edx, edx
0x1400051a8  sub     rcx, r10
0x1400051ab  not     edx
0x1400051ad  and     edx, 80070057h
0x1400051b3  neg     rax
0x1400051b6  sbb     r11, r11
0x1400051b9  and     r11, rcx
0x1400051bc  test    r10, r10
0x1400051bf  jz      short loc_14000520C
0x1400051c1  lea     rax, [rbx+r11*2]
0x1400051c5  mov     ecx, 7FFFFFFEh
0x1400051ca  sub     r9, r11
0x1400051cd  jz      short loc_1400051F1
0x1400051cf  test    rcx, rcx
0x1400051d2  jz      short loc_1400051F1
0x1400051d4  movzx   edx, word ptr [r8]
0x1400051d8  test    dx, dx
0x1400051db  jz      short loc_1400051F1
0x1400051dd  mov     [rax], dx
0x1400051e0  add     r8, 2
0x1400051e4  add     rax, 2
0x1400051e8  dec     rcx
0x1400051eb  sub     r9, 1
0x1400051ef  jnz     short loc_1400051CF
0x1400051f1  test    r9, r9
0x1400051f4  lea     rcx, [rax-2]
0x1400051f8  cmovnz  rcx, rax
0x1400051fc  neg     r9
0x1400051ff  sbb     edx, edx
0x140005201  not     edx
0x140005203  and     edx, 8007007Ah
0x140005209  mov     [rcx], di
0x14000520c  mov     rbx, [rsp+arg_0]
0x140005211  mov     eax, edx
0x140005213  mov     rdi, [rsp+arg_8]
0x140005218  retn
```
