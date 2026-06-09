# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x1800025d8`
- end: `0x1800026ef`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800029a0`

## callees

- `0x1800025d8`
- `0x1800030d6`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r11
  unsigned __int16 *v12; // rcx
  __int64 v13; // rdx
  bool v14; // cf

  if ( !a1 && a2 || a2 > 0x7FFFFFFF )
  {
    v5 = -2147024809;
LABEL_7:
    *a1 = 0;
    return v5;
  }
  if ( a4 < 0x7FFFFFFF )
  {
    v6 = (const unsigned __int16 *)&unk_180005B58;
    if ( a3 )
      v6 = a3;
    v7 = a4 & -(__int64)(a3 != 0);
    if ( a2 )
    {
      v8 = a2;
      v9 = a1;
      v10 = 0;
      do
      {
        if ( !v7 )
          break;
        if ( !*v6 )
          break;
        *v9++ = *v6++;
        --v7;
        ++v10;
        --v8;
      }
      while ( v8 );
      v11 = v10 - 1;
      v12 = v9 - 1;
      if ( v8 )
      {
        v11 = v10;
        v12 = v9;
      }
      *v12 = 0;
      v5 = v8 == 0 ? 0x8007007A : 0;
      if ( v8 )
      {
        v14 = a2 == v11;
        v13 = a2 - v11;
        if ( !v14 && v13 != 1 && (unsigned __int64)(2 * v13) > 2 )
          memset_0(&a1[v11 + 1], 0, 2 * v13 - 2);
      }
    }
    else
    {
      v5 = 0;
      if ( v7 && *v6 )
        return a1 != 0 ? -2147024774 : -2147024809;
    }
  }
  else
  {
    v5 = -2147024809;
    if ( a2 )
      goto LABEL_7;
  }
  return v5;
}

```

## disassembly

```asm
0x1800025d8  mov     [rsp+arg_0], rbx
0x1800025dd  push    rdi
0x1800025de  sub     rsp, 20h
0x1800025e2  xor     edi, edi
0x1800025e4  mov     r10, rcx
0x1800025e7  test    rcx, rcx
0x1800025ea  jnz     short loc_1800025F1
0x1800025ec  test    rdx, rdx
0x1800025ef  jnz     short loc_1800025FB
0x1800025f1  mov     eax, 7FFFFFFFh
0x1800025f6  cmp     rdx, rax
0x1800025f9  jbe     short loc_180002602
0x1800025fb  mov     ebx, 80070057h
0x180002600  jmp     short loc_180002615
0x180002602  cmp     r9, rax
0x180002605  jb      short loc_18000261D
0x180002607  mov     ebx, 80070057h
0x18000260c  test    rdx, rdx
0x18000260f  jz      loc_1800026E2
0x180002615  mov     [rcx], di
0x180002618  jmp     loc_1800026E2
0x18000261d  test    r8, r8
0x180002620  lea     rcx, unk_180005B58
0x180002627  cmovnz  rcx, r8
0x18000262b  neg     r8
0x18000262e  sbb     rax, rax
0x180002631  and     rax, r9
0x180002634  test    rdx, rdx
0x180002637  jnz     short loc_180002661
0x180002639  mov     ebx, edi
0x18000263b  test    rax, rax
0x18000263e  jz      loc_1800026E2
0x180002644  cmp     [rcx], di
0x180002647  jz      loc_1800026E2
0x18000264d  neg     r10
0x180002650  mov     ebx, 80070057h
0x180002655  sbb     eax, eax
0x180002657  and     eax, 23h
0x18000265a  add     ebx, eax
0x18000265c  jmp     loc_1800026E2
0x180002661  mov     r8, rdx
0x180002664  mov     r9, r10
0x180002667  mov     rbx, rdi
0x18000266a  test    rax, rax
0x18000266d  jz      short loc_180002691
0x18000266f  movzx   r11d, word ptr [rcx]
0x180002673  test    r11w, r11w
0x180002677  jz      short loc_180002691
0x180002679  mov     [r9], r11w
0x18000267d  add     rcx, 2
0x180002681  add     r9, 2
0x180002685  dec     rax
0x180002688  inc     rbx
0x18000268b  sub     r8, 1
0x18000268f  jnz     short loc_18000266A
0x180002691  test    r8, r8
0x180002694  lea     r11, [rbx-1]
0x180002698  lea     rcx, [r9-2]
0x18000269c  mov     rax, r8
0x18000269f  cmovnz  r11, rbx
0x1800026a3  cmovnz  rcx, r9
0x1800026a7  neg     rax
0x1800026aa  sbb     ebx, ebx
0x1800026ac  not     ebx
0x1800026ae  mov     [rcx], di
0x1800026b1  and     ebx, 8007007Ah
0x1800026b7  test    r8, r8
0x1800026ba  jz      short loc_1800026E2
0x1800026bc  sub     rdx, r11
0x1800026bf  cmp     rdx, 1
0x1800026c3  jbe     short loc_1800026E2
0x1800026c5  lea     r8, [rdx+rdx]
0x1800026c9  cmp     r8, 2
0x1800026cd  jbe     short loc_1800026E2
0x1800026cf  add     r10, 2
0x1800026d3  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800026d7  xor     edx, edx; Val
0x1800026d9  lea     rcx, [r10+r11*2]; void *
0x1800026dd  call    memset_0
0x1800026e2  mov     eax, ebx
0x1800026e4  mov     rbx, [rsp+28h+arg_0]
0x1800026e9  add     rsp, 20h
0x1800026ed  pop     rdi
0x1800026ee  retn
```
