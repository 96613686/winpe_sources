# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x18001a768`
- end: `0x18001a87f`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `279`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a888`

## callees

- `0x1800022b4`
- `0x18001a768`

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
    v6 = &WindowName;
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
0x18001a768  mov     [rsp+arg_0], rbx
0x18001a76d  push    rdi
0x18001a76e  sub     rsp, 20h
0x18001a772  xor     edi, edi
0x18001a774  mov     r10, rcx
0x18001a777  test    rcx, rcx
0x18001a77a  jnz     short loc_18001A781
0x18001a77c  test    rdx, rdx
0x18001a77f  jnz     short loc_18001A78B
0x18001a781  mov     eax, 7FFFFFFFh
0x18001a786  cmp     rdx, rax
0x18001a789  jbe     short loc_18001A792
0x18001a78b  mov     ebx, 80070057h
0x18001a790  jmp     short loc_18001A7A5
0x18001a792  cmp     r9, rax
0x18001a795  jb      short loc_18001A7AD
0x18001a797  mov     ebx, 80070057h
0x18001a79c  test    rdx, rdx
0x18001a79f  jz      loc_18001A872
0x18001a7a5  mov     [rcx], di
0x18001a7a8  jmp     loc_18001A872
0x18001a7ad  test    r8, r8
0x18001a7b0  lea     rcx, WindowName
0x18001a7b7  cmovnz  rcx, r8
0x18001a7bb  neg     r8
0x18001a7be  sbb     rax, rax
0x18001a7c1  and     rax, r9
0x18001a7c4  test    rdx, rdx
0x18001a7c7  jnz     short loc_18001A7F1
0x18001a7c9  mov     ebx, edi
0x18001a7cb  test    rax, rax
0x18001a7ce  jz      loc_18001A872
0x18001a7d4  cmp     [rcx], di
0x18001a7d7  jz      loc_18001A872
0x18001a7dd  neg     r10
0x18001a7e0  mov     ebx, 80070057h
0x18001a7e5  sbb     eax, eax
0x18001a7e7  and     eax, 23h
0x18001a7ea  add     ebx, eax
0x18001a7ec  jmp     loc_18001A872
0x18001a7f1  mov     r8, rdx
0x18001a7f4  mov     r9, r10
0x18001a7f7  mov     rbx, rdi
0x18001a7fa  test    rax, rax
0x18001a7fd  jz      short loc_18001A821
0x18001a7ff  movzx   r11d, word ptr [rcx]
0x18001a803  test    r11w, r11w
0x18001a807  jz      short loc_18001A821
0x18001a809  mov     [r9], r11w
0x18001a80d  add     rcx, 2
0x18001a811  add     r9, 2
0x18001a815  dec     rax
0x18001a818  inc     rbx
0x18001a81b  sub     r8, 1
0x18001a81f  jnz     short loc_18001A7FA
0x18001a821  test    r8, r8
0x18001a824  lea     r11, [rbx-1]
0x18001a828  lea     rcx, [r9-2]
0x18001a82c  mov     rax, r8
0x18001a82f  cmovnz  r11, rbx
0x18001a833  cmovnz  rcx, r9
0x18001a837  neg     rax
0x18001a83a  sbb     ebx, ebx
0x18001a83c  not     ebx
0x18001a83e  mov     [rcx], di
0x18001a841  and     ebx, 8007007Ah
0x18001a847  test    r8, r8
0x18001a84a  jz      short loc_18001A872
0x18001a84c  sub     rdx, r11
0x18001a84f  cmp     rdx, 1
0x18001a853  jbe     short loc_18001A872
0x18001a855  lea     r8, [rdx+rdx]
0x18001a859  cmp     r8, 2
0x18001a85d  jbe     short loc_18001A872
0x18001a85f  add     r10, 2
0x18001a863  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18001a867  xor     edx, edx; Val
0x18001a869  lea     rcx, [r10+r11*2]; void *
0x18001a86d  call    memset_0
0x18001a872  mov     eax, ebx
0x18001a874  mov     rbx, [rsp+28h+arg_0]
0x18001a879  add     rsp, 20h
0x18001a87d  pop     rdi
0x18001a87e  retn
```
