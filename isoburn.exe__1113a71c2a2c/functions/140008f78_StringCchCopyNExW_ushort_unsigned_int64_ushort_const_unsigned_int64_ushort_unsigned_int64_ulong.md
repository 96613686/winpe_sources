# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x140008f78`
- end: `0x14000908f`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000469c`

## callees

- `0x140002bc6`
- `0x140008f78`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(unsigned __int16 *a1, unsigned __int64 a2, char *a3, unsigned __int64 a4)
{
  unsigned int v5; // ebx
  char *v6; // rcx
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
    v6 = byte_140012698;
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
        if ( !*(_WORD *)v6 )
          break;
        *v9 = *(_WORD *)v6;
        v6 += 2;
        ++v9;
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
      if ( v7 && *(_WORD *)v6 )
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
0x140008f78  mov     [rsp+arg_0], rbx
0x140008f7d  push    rdi
0x140008f7e  sub     rsp, 20h
0x140008f82  xor     edi, edi
0x140008f84  mov     r10, rcx
0x140008f87  test    rcx, rcx
0x140008f8a  jnz     short loc_140008F91
0x140008f8c  test    rdx, rdx
0x140008f8f  jnz     short loc_140008F9B
0x140008f91  mov     eax, 7FFFFFFFh
0x140008f96  cmp     rdx, rax
0x140008f99  jbe     short loc_140008FA2
0x140008f9b  mov     ebx, 80070057h
0x140008fa0  jmp     short loc_140008FB5
0x140008fa2  cmp     r9, rax
0x140008fa5  jb      short loc_140008FBD
0x140008fa7  mov     ebx, 80070057h
0x140008fac  test    rdx, rdx
0x140008faf  jz      loc_140009082
0x140008fb5  mov     [rcx], di
0x140008fb8  jmp     loc_140009082
0x140008fbd  test    r8, r8
0x140008fc0  lea     rcx, byte_140012698
0x140008fc7  cmovnz  rcx, r8
0x140008fcb  neg     r8
0x140008fce  sbb     rax, rax
0x140008fd1  and     rax, r9
0x140008fd4  test    rdx, rdx
0x140008fd7  jnz     short loc_140009001
0x140008fd9  mov     ebx, edi
0x140008fdb  test    rax, rax
0x140008fde  jz      loc_140009082
0x140008fe4  cmp     [rcx], di
0x140008fe7  jz      loc_140009082
0x140008fed  neg     r10
0x140008ff0  mov     ebx, 80070057h
0x140008ff5  sbb     eax, eax
0x140008ff7  and     eax, 23h
0x140008ffa  add     ebx, eax
0x140008ffc  jmp     loc_140009082
0x140009001  mov     r8, rdx
0x140009004  mov     r9, r10
0x140009007  mov     rbx, rdi
0x14000900a  test    rax, rax
0x14000900d  jz      short loc_140009031
0x14000900f  movzx   r11d, word ptr [rcx]
0x140009013  test    r11w, r11w
0x140009017  jz      short loc_140009031
0x140009019  mov     [r9], r11w
0x14000901d  add     rcx, 2
0x140009021  add     r9, 2
0x140009025  dec     rax
0x140009028  inc     rbx
0x14000902b  sub     r8, 1
0x14000902f  jnz     short loc_14000900A
0x140009031  test    r8, r8
0x140009034  lea     r11, [rbx-1]
0x140009038  lea     rcx, [r9-2]
0x14000903c  mov     rax, r8
0x14000903f  cmovnz  r11, rbx
0x140009043  cmovnz  rcx, r9
0x140009047  neg     rax
0x14000904a  sbb     ebx, ebx
0x14000904c  not     ebx
0x14000904e  mov     [rcx], di
0x140009051  and     ebx, 8007007Ah
0x140009057  test    r8, r8
0x14000905a  jz      short loc_140009082
0x14000905c  sub     rdx, r11
0x14000905f  cmp     rdx, 1
0x140009063  jbe     short loc_140009082
0x140009065  lea     r8, [rdx+rdx]
0x140009069  cmp     r8, 2
0x14000906d  jbe     short loc_140009082
0x14000906f  add     r10, 2
0x140009073  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x140009077  xor     edx, edx; Val
0x140009079  lea     rcx, [r10+r11*2]; void *
0x14000907d  call    memset_0
0x140009082  mov     eax, ebx
0x140009084  mov     rbx, [rsp+28h+arg_0]
0x140009089  add     rsp, 20h
0x14000908d  pop     rdi
0x14000908e  retn
```
