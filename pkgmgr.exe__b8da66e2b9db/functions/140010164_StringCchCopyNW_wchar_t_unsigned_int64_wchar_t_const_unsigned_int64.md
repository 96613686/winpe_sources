# StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x140010164`
- end: `0x1400101e1`
- name: `?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z`
- size: `125`
- prototype: `__int64 __fastcall(wchar_t *, unsigned __int64, const wchar_t *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400170c0`
- `0x140017568`

## callees

- `0x140010164`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(wchar_t *a1, unsigned __int64 a2, wchar_t *a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // r10
  wchar_t *v5; // r11
  unsigned int v6; // edx

  v4 = a2;
  v5 = a1;
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || a4 > 0x7FFFFFFE )
    {
      v6 = -2147024809;
    }
    else
    {
      do
      {
        if ( !a4 )
          break;
        if ( !*a3 )
          break;
        *v5++ = *a3++;
        --a4;
        --v4;
      }
      while ( v4 );
      a1 = v5 - 1;
      if ( v4 )
        a1 = v5;
      v6 = v4 == 0 ? 0x8007007A : 0;
    }
    *a1 = 0;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x140010164  mov     [rsp+arg_0], rbx
0x140010169  xor     ebx, ebx
0x14001016b  mov     r10, rdx
0x14001016e  mov     r11, rcx
0x140010171  test    rdx, rdx
0x140010174  jz      short loc_1400101CC
0x140010176  cmp     rdx, 7FFFFFFFh
0x14001017d  jbe     short loc_140010186
0x14001017f  mov     edx, 80070057h
0x140010184  jmp     short loc_1400101D6
0x140010186  cmp     r9, 7FFFFFFEh
0x14001018d  ja      short loc_14001017F
0x14001018f  test    r9, r9
0x140010192  jz      short loc_1400101B2
0x140010194  movzx   eax, word ptr [r8]
0x140010198  test    ax, ax
0x14001019b  jz      short loc_1400101B2
0x14001019d  mov     [r11], ax
0x1400101a1  add     r8, 2
0x1400101a5  add     r11, 2
0x1400101a9  dec     r9
0x1400101ac  sub     r10, 1
0x1400101b0  jnz     short loc_14001018F
0x1400101b2  test    r10, r10
0x1400101b5  lea     rcx, [r11-2]
0x1400101b9  cmovnz  rcx, r11
0x1400101bd  neg     r10
0x1400101c0  sbb     edx, edx
0x1400101c2  not     edx
0x1400101c4  and     edx, 8007007Ah
0x1400101ca  jmp     short loc_1400101D6
0x1400101cc  mov     edx, 80070057h
0x1400101d1  test    r10, r10
0x1400101d4  jz      short loc_1400101D9
0x1400101d6  mov     [rcx], bx
0x1400101d9  mov     rbx, [rsp+arg_0]
0x1400101de  mov     eax, edx
0x1400101e0  retn
```
