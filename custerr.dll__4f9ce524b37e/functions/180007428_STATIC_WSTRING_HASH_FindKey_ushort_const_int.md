# STATIC_WSTRING_HASH::FindKey(ushort const *,int)

- ea: `0x180007428`
- end: `0x1800074c7`
- name: `?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z`
- size: `159`
- prototype: `struct STATIC_WSTRING_HASH_RECORD *(STATIC_WSTRING_HASH *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000761c`

## callees

- `0x180007428`
- `0x1800074d0`
- `0x1800074f4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800074a1`
- `msvcrt!_wcsicmp` at `0x1800074a1`

## pseudocode

```c
struct STATIC_WSTRING_HASH_RECORD *__fastcall STATIC_WSTRING_HASH::FindKey(
        STATIC_WSTRING_HASH *this,
        const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  __int64 i; // rbx
  const wchar_t *v6; // rdx
  const unsigned __int16 *v7; // rax
  signed __int64 v8; // rdx
  int v9; // r8d
  int v10; // ecx
  bool v11; // zf

  if ( *((_DWORD *)this + 262) )
    v4 = HashString(a2, (unsigned int)a2);
  else
    v4 = HashStringNoCase(a2, (unsigned int)a2);
  for ( i = *((_QWORD *)this + v4 % 0x83); i; i = *(_QWORD *)(i + 8) )
  {
    v6 = *(const wchar_t **)i;
    if ( *((_DWORD *)this + 262) )
    {
      v7 = a2;
      v8 = (char *)v6 - (char *)a2;
      do
      {
        v9 = *(const unsigned __int16 *)((char *)v7 + v8);
        v10 = *v7 - v9;
        if ( v10 )
          break;
        ++v7;
      }
      while ( v9 );
      v11 = v10 == 0;
    }
    else
    {
      v11 = _wcsicmp(a2, v6) == 0;
    }
    if ( v11 )
      break;
  }
  return (struct STATIC_WSTRING_HASH_RECORD *)i;
}

```

## disassembly

```asm
0x180007428  mov     [rsp+arg_0], rbx
0x18000742d  mov     [rsp+arg_8], rsi
0x180007432  push    rdi
0x180007433  sub     rsp, 20h
0x180007437  cmp     dword ptr [rcx+418h], 0
0x18000743e  mov     rdi, rcx
0x180007441  mov     rcx, rdx; unsigned __int16 *
0x180007444  mov     rsi, rdx
0x180007447  jz      short loc_180007450
0x180007449  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x18000744e  jmp     short loc_180007455
0x180007450  call    ?HashStringNoCase@@YAKPEBGK@Z; HashStringNoCase(ushort const *,ulong)
0x180007455  mov     r9d, eax
0x180007458  mov     eax, 0FA232CF3h
0x18000745d  mul     r9d
0x180007460  shr     edx, 7
0x180007463  imul    eax, edx, 83h
0x180007469  sub     r9d, eax
0x18000746c  mov     rbx, [rdi+r9*8]
0x180007470  jmp     short loc_1800074AF
0x180007472  cmp     dword ptr [rdi+418h], 0
0x180007479  mov     rdx, [rbx]; String2
0x18000747c  jz      short loc_18000749E
0x18000747e  mov     rax, rsi
0x180007481  sub     rdx, rsi
0x180007484  movzx   ecx, word ptr [rax]
0x180007487  movzx   r8d, word ptr [rax+rdx]
0x18000748c  sub     ecx, r8d
0x18000748f  jnz     short loc_18000749A
0x180007491  add     rax, 2
0x180007495  test    r8d, r8d
0x180007498  jnz     short loc_180007484
0x18000749a  test    ecx, ecx
0x18000749c  jmp     short loc_1800074A9
0x18000749e  mov     rcx, rsi; String1
0x1800074a1  call    cs:__imp__wcsicmp
0x1800074a7  test    eax, eax
0x1800074a9  jz      short loc_1800074B4
0x1800074ab  mov     rbx, [rbx+8]
0x1800074af  test    rbx, rbx
0x1800074b2  jnz     short loc_180007472
0x1800074b4  mov     rsi, [rsp+28h+arg_8]
0x1800074b9  mov     rax, rbx
0x1800074bc  mov     rbx, [rsp+28h+arg_0]
0x1800074c1  add     rsp, 20h
0x1800074c5  pop     rdi
0x1800074c6  retn
```
