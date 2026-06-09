# SplitPathInterior(ushort const *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *,ushort const * *,unsigned __int64 *)

- ea: `0x140011f48`
- end: `0x14001209b`
- name: `?SplitPathInterior@@YAXPEBGPEAPEBGPEA_K121212@Z`
- size: `339`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 **, unsigned __int64 *, const unsigned __int16 **, unsigned __int64 *, const unsigned __int16 **, unsigned __int64 *, const unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011e90`

## callees

- `0x140011f48`

## pseudocode

```c
void __fastcall SplitPathInterior(
        const unsigned __int16 *a1,
        const unsigned __int16 **a2,
        unsigned __int64 *a3,
        const unsigned __int16 **a4,
        unsigned __int64 *a5,
        const unsigned __int16 **a6,
        unsigned __int64 *a7,
        const unsigned __int16 **a8,
        unsigned __int64 *a9)
{
  const unsigned __int16 *v9; // r10
  const unsigned __int16 *v10; // r11
  __int64 v11; // rax
  unsigned __int16 v12; // ax
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rcx

  v9 = a1;
  v10 = 0;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  if ( v11 && a1[1] == 58 )
  {
    if ( a2 && a3 )
    {
      *a2 = a1;
      *a3 = 2;
    }
    v9 = a1 + 2;
  }
  else if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
  }
  v12 = *v9;
  v13 = 0;
  v14 = v9;
  if ( !*v9 )
    goto LABEL_25;
  do
  {
    if ( v12 == 47 || v12 == 92 )
    {
      v13 = v14 + 1;
    }
    else if ( v12 == 46 )
    {
      v10 = v14;
    }
    v12 = *++v14;
  }
  while ( *v14 );
  if ( v13 )
  {
    if ( a4 && a5 )
    {
      *a4 = v9;
      *a5 = v13 - v9;
    }
    v9 = v13;
  }
  else
  {
LABEL_25:
    if ( a4 && a5 )
    {
      *a4 = 0;
      *a5 = 0;
    }
  }
  if ( v10 && v10 >= v9 )
  {
    if ( a6 && a7 )
    {
      *a6 = v9;
      *a7 = v10 - v9;
    }
    if ( a8 )
    {
      if ( a9 )
      {
        *a8 = v10;
        *a9 = v14 - v10;
      }
    }
  }
  else
  {
    if ( a6 && a7 )
    {
      *a6 = v9;
      *a7 = v14 - v9;
    }
    if ( a8 && a9 )
    {
      *a8 = 0;
      *a9 = 0;
    }
  }
}

```

## disassembly

```asm
0x140011f48  mov     [rsp+arg_0], rbx
0x140011f4d  xor     ebx, ebx
0x140011f4f  mov     r10, rcx
0x140011f52  mov     r11d, ebx
0x140011f55  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011f59  inc     rax
0x140011f5c  cmp     [rcx+rax*2], bx
0x140011f60  jnz     short loc_140011F59
0x140011f62  cmp     rax, 1
0x140011f66  jb      short loc_140011F89
0x140011f68  cmp     word ptr [rcx+2], 3Ah ; ':'
0x140011f6d  jnz     short loc_140011F89
0x140011f6f  test    rdx, rdx
0x140011f72  jz      short loc_140011F83
0x140011f74  test    r8, r8
0x140011f77  jz      short loc_140011F83
0x140011f79  mov     [rdx], r10
0x140011f7c  mov     qword ptr [r8], 2
0x140011f83  add     r10, 4
0x140011f87  jmp     short loc_140011F99
0x140011f89  test    rdx, rdx
0x140011f8c  jz      short loc_140011F99
0x140011f8e  test    r8, r8
0x140011f91  jz      short loc_140011F99
0x140011f93  mov     [rdx], rbx
0x140011f96  mov     [r8], rbx
0x140011f99  movzx   eax, word ptr [r10]
0x140011f9d  mov     rdx, rbx
0x140011fa0  mov     rcx, r10
0x140011fa3  test    ax, ax
0x140011fa6  jz      short loc_140011FF7
0x140011fa8  cmp     ax, 2Fh ; '/'
0x140011fac  jz      short loc_140011FBF
0x140011fae  cmp     ax, 5Ch ; '\'
0x140011fb2  jz      short loc_140011FBF
0x140011fb4  cmp     ax, 2Eh ; '.'
0x140011fb8  jnz     short loc_140011FC3
0x140011fba  mov     r11, rcx
0x140011fbd  jmp     short loc_140011FC3
0x140011fbf  lea     rdx, [rcx+2]
0x140011fc3  add     rcx, 2
0x140011fc7  movzx   eax, word ptr [rcx]
0x140011fca  test    ax, ax
0x140011fcd  jnz     short loc_140011FA8
0x140011fcf  test    rdx, rdx
0x140011fd2  jz      short loc_140011FF7
0x140011fd4  test    r9, r9
0x140011fd7  jz      short loc_140011FF2
0x140011fd9  mov     r8, [rsp+arg_20]
0x140011fde  test    r8, r8
0x140011fe1  jz      short loc_140011FF2
0x140011fe3  mov     rax, rdx
0x140011fe6  mov     [r9], r10
0x140011fe9  sub     rax, r10
0x140011fec  sar     rax, 1
0x140011fef  mov     [r8], rax
0x140011ff2  mov     r10, rdx
0x140011ff5  jmp     short loc_14001200C
0x140011ff7  test    r9, r9
0x140011ffa  jz      short loc_14001200C
0x140011ffc  mov     rax, [rsp+arg_20]
0x140012001  test    rax, rax
0x140012004  jz      short loc_14001200C
0x140012006  mov     [r9], rbx
0x140012009  mov     [rax], rbx
0x14001200c  test    r11, r11
0x14001200f  jz      short loc_14001205B
0x140012011  cmp     r11, r10
0x140012014  jb      short loc_14001205B
0x140012016  mov     rax, [rsp+arg_28]
0x14001201b  test    rax, rax
0x14001201e  jz      short loc_140012039
0x140012020  mov     rdx, [rsp+arg_30]
0x140012025  test    rdx, rdx
0x140012028  jz      short loc_140012039
0x14001202a  mov     [rax], r10
0x14001202d  mov     rax, r11
0x140012030  sub     rax, r10
0x140012033  sar     rax, 1
0x140012036  mov     [rdx], rax
0x140012039  mov     rax, [rsp+arg_38]
0x14001203e  test    rax, rax
0x140012041  jz      short loc_140012095
0x140012043  mov     rdx, [rsp+arg_40]
0x140012048  test    rdx, rdx
0x14001204b  jz      short loc_140012095
0x14001204d  sub     rcx, r11
0x140012050  mov     [rax], r11
0x140012053  sar     rcx, 1
0x140012056  mov     [rdx], rcx
0x140012059  jmp     short loc_140012095
0x14001205b  mov     rax, [rsp+arg_28]
0x140012060  test    rax, rax
0x140012063  jz      short loc_14001207B
0x140012065  mov     rdx, [rsp+arg_30]
0x14001206a  test    rdx, rdx
0x14001206d  jz      short loc_14001207B
0x14001206f  sub     rcx, r10
0x140012072  mov     [rax], r10
0x140012075  sar     rcx, 1
0x140012078  mov     [rdx], rcx
0x14001207b  mov     rax, [rsp+arg_38]
0x140012080  test    rax, rax
0x140012083  jz      short loc_140012095
0x140012085  mov     rcx, [rsp+arg_40]
0x14001208a  test    rcx, rcx
0x14001208d  jz      short loc_140012095
0x14001208f  mov     [rax], rbx
0x140012092  mov     [rcx], rbx
0x140012095  mov     rbx, [rsp+arg_0]
0x14001209a  retn
```
