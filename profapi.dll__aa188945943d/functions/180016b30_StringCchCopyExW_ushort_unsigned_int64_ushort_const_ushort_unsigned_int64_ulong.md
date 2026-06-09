# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180016b30`
- end: `0x180016be5`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `181`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d984`

## callees

- `0x180016b30`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  __int64 result; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // rdx
  unsigned __int64 v11; // r9
  unsigned __int16 *v12; // rax
  __int64 v13; // r11
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // r8

  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
    v9 = 2147483646;
    v10 = L"\\";
    v11 = a2;
    v12 = a1;
    v13 = 0;
    do
    {
      if ( !v9 )
        break;
      if ( !*v10 )
        break;
      *v12++ = *v10++;
      --v9;
      ++v13;
      --v11;
    }
    while ( v11 );
    v14 = v12 - 1;
    v15 = v13 - 1;
    if ( v11 )
    {
      v14 = v12;
      v15 = v13;
    }
    v16 = a2 - v15;
    *v14 = 0;
    result = v11 == 0 ? 0x8007007A : 0;
    if ( a4 )
      *a4 = &a1[v15];
    if ( a5 )
      *a5 = v16;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016b30  push    rbx
0x180016b32  push    rsi
0x180016b33  push    rdi
0x180016b34  xor     esi, esi
0x180016b36  mov     rdi, r9
0x180016b39  mov     r8, rdx
0x180016b3c  mov     r10, rcx
0x180016b3f  test    rdx, rdx
0x180016b42  jz      loc_180016BD4
0x180016b48  cmp     rdx, 7FFFFFFFh
0x180016b4f  jbe     short loc_180016B5B
0x180016b51  mov     eax, 80070057h
0x180016b56  jmp     loc_180016BDE
0x180016b5b  mov     ecx, 7FFFFFFEh
0x180016b60  lea     rdx, asc_18001A840; "\\"
0x180016b67  mov     r9, r8
0x180016b6a  mov     rax, r10
0x180016b6d  mov     r11, rsi
0x180016b70  test    rcx, rcx
0x180016b73  jz      short loc_180016B94
0x180016b75  movzx   ebx, word ptr [rdx]
0x180016b78  test    bx, bx
0x180016b7b  jz      short loc_180016B94
0x180016b7d  mov     [rax], bx
0x180016b80  add     rdx, 2
0x180016b84  add     rax, 2
0x180016b88  dec     rcx
0x180016b8b  inc     r11
0x180016b8e  sub     r9, 1
0x180016b92  jnz     short loc_180016B70
0x180016b94  test    r9, r9
0x180016b97  lea     rcx, [rax-2]
0x180016b9b  lea     rdx, [r11-1]
0x180016b9f  cmovnz  rcx, rax
0x180016ba3  cmovnz  rdx, r11
0x180016ba7  neg     r9
0x180016baa  sbb     eax, eax
0x180016bac  sub     r8, rdx
0x180016baf  not     eax
0x180016bb1  mov     [rcx], si
0x180016bb4  and     eax, 8007007Ah
0x180016bb9  lea     rcx, [r10+rdx*2]
0x180016bbd  test    rdi, rdi
0x180016bc0  jz      short loc_180016BC5
0x180016bc2  mov     [rdi], rcx
0x180016bc5  mov     rcx, [rsp+18h+arg_20]
0x180016bca  test    rcx, rcx
0x180016bcd  jz      short loc_180016BE1
0x180016bcf  mov     [rcx], r8
0x180016bd2  jmp     short loc_180016BE1
0x180016bd4  mov     eax, 80070057h
0x180016bd9  test    r8, r8
0x180016bdc  jz      short loc_180016BE1
0x180016bde  mov     [rcx], si
0x180016be1  pop     rdi
0x180016be2  pop     rsi
0x180016be3  pop     rbx
0x180016be4  retn
```
