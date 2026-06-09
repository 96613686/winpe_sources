# NextToken(ushort * *)

- ea: `0x14000cef4`
- end: `0x14000cf90`
- name: `?NextToken@@YAPEAGPEAPEAG@Z`
- size: `156`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e89c`

## callees

- `0x14000cef4`

## pseudocode

```c
unsigned __int16 *__fastcall NextToken(unsigned __int16 **a1)
{
  _WORD *v1; // rdx
  __int64 v3; // r8
  __int16 v4; // ax
  _WORD *v5; // rcx
  __int16 i; // ax
  unsigned __int16 *v7; // rax
  __int16 v8; // ax

  v1 = *a1;
  v3 = 0;
  if ( *a1 )
  {
    while ( 1 )
    {
      v4 = *v1;
      if ( *v1 != 32 )
        break;
      ++v1;
    }
    if ( !v4 )
    {
      *a1 = 0;
      return (unsigned __int16 *)v3;
    }
    if ( v4 == 34 )
    {
      v5 = ++v1;
      for ( i = *v1; i && i != 34; i = *v5 )
        ++v5;
      if ( !*v5 )
      {
        v1 = 0;
LABEL_13:
        v7 = 0;
LABEL_14:
        *a1 = v7;
        return v1;
      }
    }
    else
    {
      v8 = *v1;
      v5 = v1;
      while ( v8 && v8 != 32 )
        v8 = *++v5;
      if ( !*v5 )
        goto LABEL_13;
    }
    *v5 = 0;
    v7 = v5 + 1;
    goto LABEL_14;
  }
  return (unsigned __int16 *)v3;
}

```

## disassembly

```asm
0x14000cef4  mov     rdx, [rcx]
0x14000cef7  xor     r10d, r10d
0x14000cefa  mov     r9, rcx
0x14000cefd  mov     r8d, r10d
0x14000cf00  test    rdx, rdx
0x14000cf03  jz      loc_14000CF8C
0x14000cf09  lea     r11d, [r10+20h]
0x14000cf0d  jmp     short loc_14000CF13
0x14000cf0f  add     rdx, 2
0x14000cf13  movzx   eax, word ptr [rdx]
0x14000cf16  cmp     r11w, ax
0x14000cf1a  jz      short loc_14000CF0F
0x14000cf1c  test    ax, ax
0x14000cf1f  jz      short loc_14000CF89
0x14000cf21  mov     r8d, 22h ; '"'
0x14000cf27  cmp     r8w, ax
0x14000cf2b  jnz     short loc_14000CF5F
0x14000cf2d  add     rdx, 2
0x14000cf31  mov     rcx, rdx
0x14000cf34  movzx   eax, word ptr [rdx]
0x14000cf37  jmp     short loc_14000CF46
0x14000cf39  cmp     r8w, ax
0x14000cf3d  jz      short loc_14000CF4B
0x14000cf3f  add     rcx, 2
0x14000cf43  movzx   eax, word ptr [rcx]
0x14000cf46  test    ax, ax
0x14000cf49  jnz     short loc_14000CF39
0x14000cf4b  cmp     [rcx], r10w
0x14000cf4f  jnz     short loc_14000CF7F
0x14000cf51  mov     rdx, r10
0x14000cf54  mov     rax, r10
0x14000cf57  mov     [r9], rax
0x14000cf5a  mov     r8, rdx
0x14000cf5d  jmp     short loc_14000CF8C
0x14000cf5f  movzx   eax, word ptr [rdx]
0x14000cf62  mov     rcx, rdx
0x14000cf65  jmp     short loc_14000CF74
0x14000cf67  cmp     r11w, ax
0x14000cf6b  jz      short loc_14000CF79
0x14000cf6d  add     rcx, 2
0x14000cf71  movzx   eax, word ptr [rcx]
0x14000cf74  test    ax, ax
0x14000cf77  jnz     short loc_14000CF67
0x14000cf79  cmp     [rcx], r10w
0x14000cf7d  jz      short loc_14000CF54
0x14000cf7f  mov     [rcx], r10w
0x14000cf83  lea     rax, [rcx+2]
0x14000cf87  jmp     short loc_14000CF57
0x14000cf89  mov     [rcx], r10
0x14000cf8c  mov     rax, r8
0x14000cf8f  retn
```
