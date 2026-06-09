# CmStringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180004ffc`
- end: `0x180005103`
- name: `?CmStringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `263`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ec0`

## callees

- `0x180004d54`
- `0x180004ffc`

## string_xrefs

- `0x1800050e7`: `StringCchCopyNEx failed with error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall CmStringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const size_t *a3,
        unsigned __int64 a4)
{
  int v5; // ebx
  const size_t *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // r9
  unsigned __int16 *v10; // rcx

  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v5 = -2147024809;
    *a1 = 0;
LABEL_24:
    MyDbgPrintfA(0xFFFFFFFFLL, "StringCchCopyNEx failed with error: 0x%x\n", v5);
    return (unsigned int)v5;
  }
  if ( a4 >= 0x7FFFFFFF )
  {
    v5 = -2147024809;
    if ( !a2 )
      goto LABEL_23;
    *a1 = 0;
    goto LABEL_21;
  }
  v6 = &Format;
  if ( a3 )
    v6 = a3;
  v7 = a4 & -(__int64)(a3 != 0);
  if ( a2 )
  {
    v8 = a2;
    v9 = a1;
    do
    {
      if ( !v7 )
        break;
      if ( !*(_WORD *)v6 )
        break;
      *v9 = *(_WORD *)v6;
      v6 = (const size_t *)((char *)v6 + 2);
      ++v9;
      --v7;
      --v8;
    }
    while ( v8 );
    v10 = v9 - 1;
    if ( v8 )
      v10 = v9;
    v5 = v8 == 0 ? 0x8007007A : 0;
    *v10 = 0;
    if ( !v8 )
    {
LABEL_21:
      if ( (a2 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
        *a1 = 0;
    }
  }
  else
  {
    v5 = 0;
    if ( v7 && *(_WORD *)v6 )
      v5 = a1 != 0 ? -2147024774 : -2147024809;
  }
LABEL_23:
  if ( v5 < 0 )
    goto LABEL_24;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004ffc  mov     [rsp+arg_0], rbx
0x180005001  push    rdi
0x180005002  sub     rsp, 20h
0x180005006  xor     edi, edi
0x180005008  mov     r10, rcx
0x18000500b  test    rcx, rcx
0x18000500e  jnz     short loc_180005015
0x180005010  test    rdx, rdx
0x180005013  jnz     short loc_18000501F
0x180005015  mov     eax, 7FFFFFFFh
0x18000501a  cmp     rdx, rax
0x18000501d  jbe     short loc_18000502C
0x18000501f  mov     ebx, 80070057h
0x180005024  mov     [rcx], di
0x180005027  jmp     loc_1800050E4
0x18000502c  cmp     r9, rax
0x18000502f  jb      short loc_180005047
0x180005031  mov     ebx, 80070057h
0x180005036  test    rdx, rdx
0x180005039  jz      loc_1800050E0
0x18000503f  mov     [rcx], di
0x180005042  jmp     loc_1800050CD
0x180005047  test    r8, r8
0x18000504a  lea     rcx, Format
0x180005051  cmovnz  rcx, r8
0x180005055  neg     r8
0x180005058  sbb     rax, rax
0x18000505b  and     rax, r9
0x18000505e  test    rdx, rdx
0x180005061  jnz     short loc_180005080
0x180005063  mov     ebx, edi
0x180005065  test    rax, rax
0x180005068  jz      short loc_1800050E0
0x18000506a  cmp     [rcx], di
0x18000506d  jz      short loc_1800050E0
0x18000506f  neg     r10
0x180005072  mov     ebx, 80070057h
0x180005077  sbb     eax, eax
0x180005079  and     eax, 23h
0x18000507c  add     ebx, eax
0x18000507e  jmp     short loc_1800050E0
0x180005080  mov     r8, rdx
0x180005083  mov     r9, r10
0x180005086  test    rax, rax
0x180005089  jz      short loc_1800050AA
0x18000508b  movzx   r11d, word ptr [rcx]
0x18000508f  test    r11w, r11w
0x180005093  jz      short loc_1800050AA
0x180005095  mov     [r9], r11w
0x180005099  add     rcx, 2
0x18000509d  add     r9, 2
0x1800050a1  dec     rax
0x1800050a4  sub     r8, 1
0x1800050a8  jnz     short loc_180005086
0x1800050aa  test    r8, r8
0x1800050ad  lea     rcx, [r9-2]
0x1800050b1  mov     rax, r8
0x1800050b4  cmovnz  rcx, r9
0x1800050b8  neg     rax
0x1800050bb  sbb     ebx, ebx
0x1800050bd  not     ebx
0x1800050bf  and     ebx, 8007007Ah
0x1800050c5  mov     [rcx], di
0x1800050c8  test    r8, r8
0x1800050cb  jnz     short loc_1800050E0
0x1800050cd  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800050d7  test    rax, rdx
0x1800050da  jbe     short loc_1800050E0
0x1800050dc  mov     [r10], di
0x1800050e0  test    ebx, ebx
0x1800050e2  jns     short loc_1800050F6
0x1800050e4  mov     r8d, ebx
0x1800050e7  lea     rdx, aStringcchcopyn; "StringCchCopyNEx failed with error: 0x%"...
0x1800050ee  or      ecx, 0FFFFFFFFh
0x1800050f1  call    MyDbgPrintfA
0x1800050f6  mov     eax, ebx
0x1800050f8  mov     rbx, [rsp+28h+arg_0]
0x1800050fd  add     rsp, 20h
0x180005101  pop     rdi
0x180005102  retn
```
