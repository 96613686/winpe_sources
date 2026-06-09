# CSafeReg::QueryPath(ushort const *,ushort *,ulong,int)

- ea: `0x18001af3c`
- end: `0x18001b048`
- name: `?QueryPath@CSafeReg@@QEAAJPEBGPEAGKH@Z`
- size: `268`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, BYTE *, unsigned int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000de10`
- `0x18000e824`
- `0x18000f09c`
- `0x180016084`
- `0x18001f9cc`

## callees

- `0x180002bb8`
- `0x18001af3c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b001`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b001`
- `msvcrt!wcscpy_s` at `0x18001afda`
- `msvcrt!wcscpy_s` at `0x18001afda`
- `ADVAPI32!RegQueryValueExW` at `0x18001af7a`
- `ADVAPI32!RegQueryValueExW` at `0x18001af7a`
- `KERNEL32!GetLastError` at `0x18001afe9`
- `KERNEL32!GetLastError` at `0x18001afe9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001afc4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001afc4`

## pseudocode

```c
__int64 __fastcall CSafeReg::QueryPath(HKEY *this, const unsigned __int16 *a2, BYTE *a3, unsigned int a4, int a5)
{
  HKEY v5; // rcx
  unsigned __int64 v7; // rsi
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  WCHAR *v10; // rax
  wchar_t *v11; // rdi
  DWORD v12; // eax
  signed int LastError; // eax
  int v15; // [rsp+50h] [rbp+8h] BYREF
  DWORD v16; // [rsp+68h] [rbp+20h] BYREF

  v5 = *this;
  v7 = a4;
  v16 = 0;
  v15 = 2 * a4;
  v8 = RegQueryValueExW(v5, a2, 0, &v16, a3, (LPDWORD)&v15);
  v9 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
  }
  else if ( v16 == 2 )
  {
    if ( !a5 )
      return v9;
    v10 = (WCHAR *)operator new[](saturated_mul(v7, 2u));
    v11 = v10;
    if ( v10 )
    {
      v12 = ExpandEnvironmentStringsW((LPCWSTR)a3, v10, v7);
      if ( v12 )
      {
        if ( v12 > (unsigned int)v7 )
          v9 = -2147467259;
        else
          wcscpy_s((wchar_t *)a3, (unsigned int)v7, v11);
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      operator delete[](v11);
    }
    else
    {
      v9 = -2147024882;
    }
  }
  else if ( v16 != 1 )
  {
    v9 = -2147467259;
LABEL_18:
    *(_WORD *)a3 = 0;
    return v9;
  }
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_18;
  return v9;
}

```

## disassembly

```asm
0x18001af3c  mov     r11, rsp
0x18001af3f  mov     [r11+10h], rbx
0x18001af43  mov     [r11+18h], rbp
0x18001af47  push    rsi
0x18001af48  push    rdi
0x18001af49  push    r14
0x18001af4b  sub     rsp, 30h
0x18001af4f  mov     rcx, [rcx]; hKey
0x18001af52  mov     r14, r8
0x18001af55  mov     esi, r9d
0x18001af58  lea     r9, [r11+20h]; lpType
0x18001af5c  mov     [rsp+48h+arg_18], 0
0x18001af64  lea     eax, [rsi+rsi]
0x18001af67  mov     [rsp+48h+arg_0], eax
0x18001af6b  lea     rax, [r11+8]
0x18001af6f  mov     [r11-20h], rax
0x18001af73  mov     [r11-28h], r8
0x18001af77  xor     r8d, r8d; lpReserved
0x18001af7a  call    cs:__imp_RegQueryValueExW
0x18001af80  mov     ebx, eax
0x18001af82  test    eax, eax
0x18001af84  jnz     loc_18001B01E
0x18001af8a  lea     eax, [rbx+2]
0x18001af8d  cmp     [rsp+48h+arg_18], eax
0x18001af91  jnz     short loc_18001B010
0x18001af93  cmp     [rsp+48h+arg_20], ebx
0x18001af97  jz      loc_18001B033
0x18001af9d  mul     rsi
0x18001afa0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001afa7  cmovb   rax, rcx
0x18001afab  mov     rcx, rax; unsigned __int64
0x18001afae  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001afb3  mov     rdi, rax
0x18001afb6  test    rax, rax
0x18001afb9  jz      short loc_18001B009
0x18001afbb  mov     r8d, esi; nSize
0x18001afbe  mov     rdx, rax; lpDst
0x18001afc1  mov     rcx, r14; lpSrc
0x18001afc4  call    cs:__imp_ExpandEnvironmentStringsW
0x18001afca  test    eax, eax
0x18001afcc  jz      short loc_18001AFE9
0x18001afce  cmp     eax, esi
0x18001afd0  ja      short loc_18001AFE2
0x18001afd2  mov     r8, rdi; Source
0x18001afd5  mov     edx, esi; SizeInWords
0x18001afd7  mov     rcx, r14; Destination
0x18001afda  call    cs:__imp_wcscpy_s
0x18001afe0  jmp     short loc_18001AFFE
0x18001afe2  mov     ebx, 80004005h
0x18001afe7  jmp     short loc_18001AFFE
0x18001afe9  call    cs:__imp_GetLastError
0x18001afef  mov     ebx, eax
0x18001aff1  test    eax, eax
0x18001aff3  jle     short loc_18001AFFE
0x18001aff5  movzx   ebx, ax
0x18001aff8  or      ebx, 80070000h
0x18001affe  mov     rcx, rdi
0x18001b001  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b007  jmp     short loc_18001B029
0x18001b009  mov     ebx, 8007000Eh
0x18001b00e  jmp     short loc_18001B029
0x18001b010  cmp     [rsp+48h+arg_18], 1
0x18001b015  jz      short loc_18001B029
0x18001b017  mov     ebx, 80004005h
0x18001b01c  jmp     short loc_18001B02D
0x18001b01e  jle     short loc_18001B029
0x18001b020  movzx   ebx, ax
0x18001b023  or      ebx, 80070000h
0x18001b029  test    ebx, ebx
0x18001b02b  jns     short loc_18001B033
0x18001b02d  xor     ecx, ecx
0x18001b02f  mov     [r14], cx
0x18001b033  mov     rbp, [rsp+48h+arg_10]
0x18001b038  mov     eax, ebx
0x18001b03a  mov     rbx, [rsp+48h+arg_8]
0x18001b03f  add     rsp, 30h
0x18001b043  pop     r14
0x18001b045  pop     rdi
0x18001b046  pop     rsi
0x18001b047  retn
```
