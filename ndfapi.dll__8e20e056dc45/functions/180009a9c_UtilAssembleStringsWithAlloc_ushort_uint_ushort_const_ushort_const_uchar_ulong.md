# UtilAssembleStringsWithAlloc(ushort * *,uint,ushort const *,ushort const *,uchar,ulong)

- ea: `0x180009a9c`
- end: `0x180009c48`
- name: `?UtilAssembleStringsWithAlloc@@YAJPEAPEAGIPEBG1EK@Z`
- size: `428`
- prototype: `int(unsigned __int16 **, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800087f8`
- `0x180019590`

## callees

- `0x180003d50`
- `0x180009a9c`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180009ae7`
- `KERNEL32!GetModuleHandleW` at `0x180009b5a`
- `KERNEL32!GetModuleHandleW` at `0x180009ae7`
- `KERNEL32!GetModuleHandleW` at `0x180009b5a`
- `KERNEL32!GetLastError` at `0x180009b05`
- `KERNEL32!GetLastError` at `0x180009b78`
- `KERNEL32!GetLastError` at `0x180009b05`
- `KERNEL32!GetLastError` at `0x180009b78`
- `USER32!LoadStringW` at `0x180009afb`
- `USER32!LoadStringW` at `0x180009b6e`
- `USER32!LoadStringW` at `0x180009afb`
- `USER32!LoadStringW` at `0x180009b6e`
- `ole32!CoTaskMemAlloc` at `0x180009acc`
- `ole32!CoTaskMemAlloc` at `0x180009b40`
- `ole32!CoTaskMemAlloc` at `0x180009bba`
- `ole32!CoTaskMemAlloc` at `0x180009acc`
- `ole32!CoTaskMemAlloc` at `0x180009b40`
- `ole32!CoTaskMemAlloc` at `0x180009bba`
- `ole32!CoTaskMemFree` at `0x180009b1d`
- `ole32!CoTaskMemFree` at `0x180009b90`
- `ole32!CoTaskMemFree` at `0x180009ba2`
- `ole32!CoTaskMemFree` at `0x180009bd0`
- `ole32!CoTaskMemFree` at `0x180009bde`
- `ole32!CoTaskMemFree` at `0x180009c14`
- `ole32!CoTaskMemFree` at `0x180009c22`
- `ole32!CoTaskMemFree` at `0x180009c40`
- `ole32!CoTaskMemFree` at `0x180009b1d`
- `ole32!CoTaskMemFree` at `0x180009b90`
- `ole32!CoTaskMemFree` at `0x180009ba2`
- `ole32!CoTaskMemFree` at `0x180009bd0`
- `ole32!CoTaskMemFree` at `0x180009bde`
- `ole32!CoTaskMemFree` at `0x180009c14`
- `ole32!CoTaskMemFree` at `0x180009c22`
- `ole32!CoTaskMemFree` at `0x180009c40`

## pseudocode

```c
__int64 __fastcall UtilAssembleStringsWithAlloc(
        unsigned __int16 **a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // r14
  unsigned __int16 *v5; // rbx
  unsigned __int16 *v8; // rbp
  signed int v9; // edi
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  unsigned __int16 *v13; // rbp
  HMODULE v14; // rax
  signed int v15; // eax
  unsigned __int16 *v16; // rdi
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rbp
  int v19; // esi

  v4 = L"%s";
  v5 = 0;
  if ( (unsigned __int64)L"%s" < 0x10000 )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
    if ( !v8 )
      return (unsigned int)-2147024882;
    ModuleHandleW = GetModuleHandleW(0);
    if ( LoadStringW(ModuleHandleW, (unsigned __int16)L"%s", v8, 1024) )
    {
      v4 = v8;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      CoTaskMemFree(v8);
      if ( v9 < 0 )
        return (unsigned int)v9;
    }
    v5 = (unsigned __int16 *)v4;
  }
  if ( (unsigned __int64)a4 >= 0x10000 )
  {
    v16 = 0;
  }
  else
  {
    v13 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
    if ( !v13 )
    {
      v9 = -2147024882;
LABEL_18:
      if ( v5 )
        CoTaskMemFree(v5);
      return (unsigned int)v9;
    }
    v14 = GetModuleHandleW(0);
    if ( LoadStringW(v14, (unsigned __int16)a4, v13, 1024) )
    {
      a4 = v13;
    }
    else
    {
      v15 = GetLastError();
      v9 = v15;
      if ( v15 > 0 )
        v9 = (unsigned __int16)v15 | 0x80070000;
      CoTaskMemFree(v13);
      if ( v9 < 0 )
        goto LABEL_18;
    }
    v16 = a4;
  }
  v17 = (unsigned __int16 *)CoTaskMemAlloc(0x800u);
  v18 = v17;
  if ( !v17 )
  {
    if ( v16 )
      CoTaskMemFree(v16);
    if ( v5 )
      CoTaskMemFree(v5);
    return 2147942414LL;
  }
  v19 = StringCchPrintfW(v17, 0x400u, v4, a4);
  if ( v19 == -2147024774 )
  {
    v19 = 0;
  }
  else if ( v19 < 0 )
  {
    CoTaskMemFree(v18);
    goto LABEL_32;
  }
  *a1 = v18;
LABEL_32:
  if ( v16 )
    CoTaskMemFree(v16);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180009a9c  push    rbx
0x180009a9e  push    rbp
0x180009a9f  push    rsi
0x180009aa0  push    rdi
0x180009aa1  push    r12
0x180009aa3  push    r14
0x180009aa5  push    r15
0x180009aa7  sub     rsp, 20h
0x180009aab  lea     r14, aS_0; "%s"
0x180009ab2  xor     ebx, ebx
0x180009ab4  mov     rsi, r9
0x180009ab7  mov     r15, rcx
0x180009aba  mov     r12d, 800h
0x180009ac0  cmp     r14, 10000h
0x180009ac7  jnb     short loc_180009B34
0x180009ac9  mov     ecx, r12d; cb
0x180009acc  call    cs:__imp_CoTaskMemAlloc
0x180009ad2  mov     rbp, rax
0x180009ad5  test    rax, rax
0x180009ad8  jnz     short loc_180009AE1
0x180009ada  mov     edi, 8007000Eh
0x180009adf  jmp     short loc_180009B27
0x180009ae1  xor     ecx, ecx; lpModuleName
0x180009ae3  movzx   ebx, r14w
0x180009ae7  call    cs:__imp_GetModuleHandleW
0x180009aed  mov     r9d, 400h; cchBufferMax
0x180009af3  mov     r8, rbp; lpBuffer
0x180009af6  mov     rcx, rax; hInstance
0x180009af9  mov     edx, ebx; uID
0x180009afb  call    cs:__imp_LoadStringW
0x180009b01  test    eax, eax
0x180009b03  jnz     short loc_180009B2E
0x180009b05  call    cs:__imp_GetLastError
0x180009b0b  mov     edi, eax
0x180009b0d  test    eax, eax
0x180009b0f  jle     short loc_180009B1A
0x180009b11  movzx   edi, ax
0x180009b14  or      edi, 80070000h
0x180009b1a  mov     rcx, rbp; pv
0x180009b1d  call    cs:__imp_CoTaskMemFree
0x180009b23  test    edi, edi
0x180009b25  jns     short loc_180009B31
0x180009b27  mov     eax, edi
0x180009b29  jmp     loc_180009C2A
0x180009b2e  mov     r14, rbp
0x180009b31  mov     rbx, r14
0x180009b34  cmp     rsi, 10000h
0x180009b3b  jnb     short loc_180009BB5
0x180009b3d  mov     rcx, r12; cb
0x180009b40  call    cs:__imp_CoTaskMemAlloc
0x180009b46  mov     rbp, rax
0x180009b49  test    rax, rax
0x180009b4c  jnz     short loc_180009B55
0x180009b4e  mov     edi, 8007000Eh
0x180009b53  jmp     short loc_180009B9A
0x180009b55  xor     ecx, ecx; lpModuleName
0x180009b57  movzx   edi, si
0x180009b5a  call    cs:__imp_GetModuleHandleW
0x180009b60  mov     r9d, 400h; cchBufferMax
0x180009b66  mov     r8, rbp; lpBuffer
0x180009b69  mov     rcx, rax; hInstance
0x180009b6c  mov     edx, edi; uID
0x180009b6e  call    cs:__imp_LoadStringW
0x180009b74  test    eax, eax
0x180009b76  jnz     short loc_180009BAD
0x180009b78  call    cs:__imp_GetLastError
0x180009b7e  mov     edi, eax
0x180009b80  test    eax, eax
0x180009b82  jle     short loc_180009B8D
0x180009b84  movzx   edi, ax
0x180009b87  or      edi, 80070000h
0x180009b8d  mov     rcx, rbp; pv
0x180009b90  call    cs:__imp_CoTaskMemFree
0x180009b96  test    edi, edi
0x180009b98  jns     short loc_180009BB0
0x180009b9a  test    rbx, rbx
0x180009b9d  jz      short loc_180009B27
0x180009b9f  mov     rcx, rbx; pv
0x180009ba2  call    cs:__imp_CoTaskMemFree
0x180009ba8  jmp     loc_180009B27
0x180009bad  mov     rsi, rbp
0x180009bb0  mov     rdi, rsi
0x180009bb3  jmp     short loc_180009BB7
0x180009bb5  xor     edi, edi
0x180009bb7  mov     rcx, r12; cb
0x180009bba  call    cs:__imp_CoTaskMemAlloc
0x180009bc0  mov     rbp, rax
0x180009bc3  test    rax, rax
0x180009bc6  jnz     short loc_180009BEB
0x180009bc8  test    rdi, rdi
0x180009bcb  jz      short loc_180009BD6
0x180009bcd  mov     rcx, rdi; pv
0x180009bd0  call    cs:__imp_CoTaskMemFree
0x180009bd6  test    rbx, rbx
0x180009bd9  jz      short loc_180009BE4
0x180009bdb  mov     rcx, rbx; pv
0x180009bde  call    cs:__imp_CoTaskMemFree
0x180009be4  mov     eax, 8007000Eh
0x180009be9  jmp     short loc_180009C2A
0x180009beb  mov     r9, rsi
0x180009bee  mov     r8, r14; unsigned __int16 *
0x180009bf1  mov     edx, 400h; unsigned __int64
0x180009bf6  mov     rcx, rbp; unsigned __int16 *
0x180009bf9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009bfe  mov     esi, eax
0x180009c00  cmp     eax, 8007007Ah
0x180009c05  jnz     short loc_180009C39
0x180009c07  xor     esi, esi
0x180009c09  mov     [r15], rbp
0x180009c0c  test    rdi, rdi
0x180009c0f  jz      short loc_180009C1A
0x180009c11  mov     rcx, rdi; pv
0x180009c14  call    cs:__imp_CoTaskMemFree
0x180009c1a  test    rbx, rbx
0x180009c1d  jz      short loc_180009C28
0x180009c1f  mov     rcx, rbx; pv
0x180009c22  call    cs:__imp_CoTaskMemFree
0x180009c28  mov     eax, esi
0x180009c2a  add     rsp, 20h
0x180009c2e  pop     r15
0x180009c30  pop     r14
0x180009c32  pop     r12
0x180009c34  pop     rdi
0x180009c35  pop     rsi
0x180009c36  pop     rbp
0x180009c37  pop     rbx
0x180009c38  retn
0x180009c39  test    esi, esi
0x180009c3b  jns     short loc_180009C09
0x180009c3d  mov     rcx, rbp; pv
0x180009c40  call    cs:__imp_CoTaskMemFree
0x180009c46  jmp     short loc_180009C0C
```
