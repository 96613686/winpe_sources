# ExtractNameFromPath(char * &,char *,int)

- ea: `0x18001da80`
- end: `0x18001db54`
- name: `?ExtractNameFromPath@@YAJAEAPEADPEADH@Z`
- size: `212`
- prototype: `int(char **, char *, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180015c50`
- `0x18001919c`
- `0x18001aeb4`
- `0x18001c580`
- `0x180020be8`
- `0x180022c20`
- `0x180022ed8`

## callees

- `0x18001da80`
- `0x18001db5c`
- `0x18003098e`

## import_xrefs

- `USER32!CharNextExA` at `0x18001daeb`
- `USER32!CharNextExA` at `0x18001daeb`

## pseudocode

```c
__int64 __fastcall ExtractNameFromPath(char **a1, char *a2, int a3)
{
  unsigned int NameFromPath; // ebp
  unsigned __int16 *v6; // rdi
  char *v7; // rcx
  CHAR v8; // al
  char *v9; // rdx
  LPSTR v10; // rax
  unsigned int v11; // eax
  __int64 v12; // rbx
  bool v13; // zf
  char *v15; // [rsp+58h] [rbp+20h] BYREF

  if ( a3 )
  {
    v15 = *a1;
    NameFromPath = ExtractNameFromPath((unsigned __int16 **)&v15, (unsigned __int16 *)a2);
    *a1 = v15;
  }
  else
  {
    v6 = (unsigned __int16 *)*a1;
    NameFromPath = -2147024893;
    if ( *a1 )
    {
      v7 = *a1;
      do
      {
        v8 = *(_BYTE *)v6;
        v9 = v7;
        if ( !*(_BYTE *)v6 )
          break;
        if ( v8 == 47 )
          break;
        if ( v8 == 92 )
          break;
        v10 = CharNextExA(0, (LPCSTR)v6, 0);
        v7 = *a1;
        v6 = (unsigned __int16 *)v10;
        v9 = *a1;
      }
      while ( v10 - *a1 < 256 );
      v11 = (_DWORD)v6 - *(_DWORD *)a1;
      if ( v11 < 0x100 )
      {
        v12 = v11;
        memcpy_0(a2, v9, v11);
        a2[v12] = 0;
        v13 = *a2 == 0;
        *a1 = (char *)v6;
        if ( !v13 )
        {
          if ( *(_BYTE *)v6 == 47 || *(_BYTE *)v6 == 92 )
            *a1 = (char *)v6 + 1;
          return 0;
        }
      }
      else
      {
        return (unsigned int)-2147024773;
      }
    }
  }
  return NameFromPath;
}

```

## disassembly

```asm
0x18001da80  mov     r11, rsp
0x18001da83  mov     [r11+8], rbx
0x18001da87  mov     [r11+10h], rbp
0x18001da8b  push    rsi
0x18001da8c  push    rdi
0x18001da8d  push    r14
0x18001da8f  sub     rsp, 20h
0x18001da93  mov     r14, rdx
0x18001da96  mov     rsi, rcx
0x18001da99  test    r8d, r8d
0x18001da9c  jz      short loc_18001DABD
0x18001da9e  mov     rax, [rcx]
0x18001daa1  lea     rcx, [r11+20h]; unsigned __int16 **
0x18001daa5  mov     [r11+20h], rax
0x18001daa9  call    ?ExtractNameFromPath@@YAJPEAPEAGPEAG@Z; ExtractNameFromPath(ushort * *,ushort *)
0x18001daae  mov     rdx, [rsp+38h+arg_18]
0x18001dab3  mov     ebp, eax
0x18001dab5  mov     [rsi], rdx
0x18001dab8  jmp     loc_18001DB3F
0x18001dabd  mov     rdi, [rcx]
0x18001dac0  mov     ebp, 80070003h
0x18001dac5  test    rdi, rdi
0x18001dac8  jz      short loc_18001DB3F
0x18001daca  mov     rcx, rdi
0x18001dacd  mov     ebx, 100h
0x18001dad2  mov     al, [rdi]
0x18001dad4  mov     rdx, rcx
0x18001dad7  test    al, al
0x18001dad9  jz      short loc_18001DB02
0x18001dadb  cmp     al, 2Fh ; '/'
0x18001dadd  jz      short loc_18001DB02
0x18001dadf  cmp     al, 5Ch ; '\'
0x18001dae1  jz      short loc_18001DB02
0x18001dae3  xor     ecx, ecx; CodePage
0x18001dae5  xor     r8d, r8d; dwFlags
0x18001dae8  mov     rdx, rdi; lpCurrentChar
0x18001daeb  call    cs:__imp_CharNextExA
0x18001daf1  mov     rcx, [rsi]
0x18001daf4  mov     rdi, rax
0x18001daf7  sub     rax, rcx
0x18001dafa  mov     rdx, rcx; Src
0x18001dafd  cmp     rax, rbx
0x18001db00  jl      short loc_18001DAD2
0x18001db02  mov     eax, edi
0x18001db04  sub     eax, [rsi]
0x18001db06  cmp     eax, ebx
0x18001db08  jb      short loc_18001DB11
0x18001db0a  mov     ebp, 8007007Bh
0x18001db0f  jmp     short loc_18001DB3F
0x18001db11  mov     r8d, eax; Size
0x18001db14  mov     rcx, r14; void *
0x18001db17  mov     ebx, eax
0x18001db19  call    memcpy_0
0x18001db1e  mov     byte ptr [rbx+r14], 0
0x18001db23  cmp     byte ptr [r14], 0
0x18001db27  mov     [rsi], rdi
0x18001db2a  jz      short loc_18001DB3F
0x18001db2c  cmp     byte ptr [rdi], 2Fh ; '/'
0x18001db2f  jz      short loc_18001DB36
0x18001db31  cmp     byte ptr [rdi], 5Ch ; '\'
0x18001db34  jnz     short loc_18001DB3D
0x18001db36  lea     rax, [rdi+1]
0x18001db3a  mov     [rsi], rax
0x18001db3d  xor     ebp, ebp
0x18001db3f  mov     rbx, [rsp+38h+arg_0]
0x18001db44  mov     eax, ebp
0x18001db46  mov     rbp, [rsp+38h+arg_8]
0x18001db4b  add     rsp, 20h
0x18001db4f  pop     r14
0x18001db51  pop     rdi
0x18001db52  pop     rsi
0x18001db53  retn
```
