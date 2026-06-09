# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x14000b8e0`
- end: `0x14000b9f8`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `280`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140008f78`

## callees

- `0x140001af3`
- `0x14000b8e0`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  unsigned int v5; // ebx
  const WCHAR *v6; // rcx
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
    v6 = &Data;
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
0x14000b8e0  mov     [rsp+arg_0], rbx
0x14000b8e5  push    rdi
0x14000b8e6  sub     rsp, 20h
0x14000b8ea  xor     edi, edi
0x14000b8ec  mov     r10, rcx
0x14000b8ef  test    rcx, rcx
0x14000b8f2  jnz     short loc_14000B8F9
0x14000b8f4  test    rdx, rdx
0x14000b8f7  jnz     short loc_14000B903
0x14000b8f9  mov     eax, 7FFFFFFFh
0x14000b8fe  cmp     rdx, rax
0x14000b901  jbe     short loc_14000B90A
0x14000b903  mov     ebx, 80070057h
0x14000b908  jmp     short loc_14000B91D
0x14000b90a  cmp     r9, rax
0x14000b90d  jb      short loc_14000B925
0x14000b90f  mov     ebx, 80070057h
0x14000b914  test    rdx, rdx
0x14000b917  jz      loc_14000B9EA
0x14000b91d  mov     [rcx], di
0x14000b920  jmp     loc_14000B9EA
0x14000b925  test    r8, r8
0x14000b928  lea     rcx, Data
0x14000b92f  cmovnz  rcx, r8
0x14000b933  neg     r8
0x14000b936  sbb     rax, rax
0x14000b939  and     rax, r9
0x14000b93c  test    rdx, rdx
0x14000b93f  jnz     short loc_14000B969
0x14000b941  mov     ebx, edi
0x14000b943  test    rax, rax
0x14000b946  jz      loc_14000B9EA
0x14000b94c  cmp     [rcx], di
0x14000b94f  jz      loc_14000B9EA
0x14000b955  neg     r10
0x14000b958  mov     ebx, 80070057h
0x14000b95d  sbb     eax, eax
0x14000b95f  and     eax, 23h
0x14000b962  add     ebx, eax
0x14000b964  jmp     loc_14000B9EA
0x14000b969  mov     r8, rdx
0x14000b96c  mov     r9, r10
0x14000b96f  mov     rbx, rdi
0x14000b972  test    rax, rax
0x14000b975  jz      short loc_14000B999
0x14000b977  movzx   r11d, word ptr [rcx]
0x14000b97b  test    r11w, r11w
0x14000b97f  jz      short loc_14000B999
0x14000b981  mov     [r9], r11w
0x14000b985  add     rcx, 2
0x14000b989  add     r9, 2
0x14000b98d  dec     rax
0x14000b990  inc     rbx
0x14000b993  sub     r8, 1
0x14000b997  jnz     short loc_14000B972
0x14000b999  test    r8, r8
0x14000b99c  lea     r11, [rbx-1]
0x14000b9a0  lea     rcx, [r9-2]
0x14000b9a4  mov     rax, r8
0x14000b9a7  cmovnz  r11, rbx
0x14000b9ab  cmovnz  rcx, r9
0x14000b9af  neg     rax
0x14000b9b2  sbb     ebx, ebx
0x14000b9b4  not     ebx
0x14000b9b6  mov     [rcx], di
0x14000b9b9  and     ebx, 8007007Ah
0x14000b9bf  test    r8, r8
0x14000b9c2  jz      short loc_14000B9EA
0x14000b9c4  sub     rdx, r11
0x14000b9c7  cmp     rdx, 1
0x14000b9cb  jbe     short loc_14000B9EA
0x14000b9cd  lea     r8, [rdx+rdx]
0x14000b9d1  cmp     r8, 2
0x14000b9d5  jbe     short loc_14000B9EA
0x14000b9d7  add     r10, 2
0x14000b9db  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x14000b9df  xor     edx, edx; Val
0x14000b9e1  lea     rcx, [r10+r11*2]; void *
0x14000b9e5  call    memset_0
0x14000b9ea  mov     eax, ebx
0x14000b9ec  mov     rbx, [rsp+28h+arg_0]
0x14000b9f1  add     rsp, 20h
0x14000b9f5  pop     rdi
0x14000b9f6  retn
```
