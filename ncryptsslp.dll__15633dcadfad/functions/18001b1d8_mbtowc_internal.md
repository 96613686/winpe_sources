# _mbtowc_internal

- ea: `0x18001b1d8`
- end: `0x18001b332`
- name: `_mbtowc_internal`
- size: `346`
- prototype: `__int64 __fastcall(__crt_mbstring *this, wchar_t *, char *, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001c26c`

## callees

- `0x18001756c`
- `0x180018020`
- `0x18001b1d8`
- `0x18001b518`

## pseudocode

```c
unsigned __int64 __fastcall mbtowc_internal(__crt_mbstring *this, wchar_t *a2, char *a3, __crt_cached_ptd_host *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // r10d
  unsigned __int64 result; // rax
  int v11; // r9d
  struct __crt_cached_ptd_host *v12; // [rsp+28h] [rbp-30h]

  if ( !a2 || !a3 )
  {
    qword_18003E370 = 0;
    return 0;
  }
  if ( !*(_BYTE *)a2 )
  {
    if ( this )
      *(_WORD *)this = 0;
    return 0;
  }
  if ( !*((_BYTE *)a4 + 40) )
    __crt_cached_ptd_host::update_locale_slow(a4);
  v8 = *((_QWORD *)a4 + 3);
  v9 = *(_DWORD *)(v8 + 12);
  if ( v9 != 65001 )
  {
    if ( !*(_QWORD *)(v8 + 312) )
    {
      if ( this )
        *(_WORD *)this = *(unsigned __int8 *)a2;
      return 1;
    }
    if ( *(__int16 *)(*(_QWORD *)v8 + 2LL * *(unsigned __int8 *)a2) >= 0 )
    {
      if ( (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2) )
        return 1;
    }
    else
    {
      v11 = *(_DWORD *)(v8 + 8);
      if ( v11 > 1 && (int)a3 >= v11 && (unsigned int)_acrt_MultiByteToWideChar(v9, 9, a2)
        || (unsigned __int64)a3 >= *(int *)(*((_QWORD *)a4 + 3) + 8LL) && *((_BYTE *)a2 + 1) )
      {
        return *(unsigned int *)(*((_QWORD *)a4 + 3) + 8LL);
      }
    }
    *((_BYTE *)a4 + 48) = 1;
    result = 0xFFFFFFFFLL;
    *((_DWORD *)a4 + 11) = 42;
    return result;
  }
  result = __crt_mbstring::__mbrtowc_utf8(this, a2, a3, (unsigned __int64)&qword_18003E370, (struct _Mbstatet *)a4, v12);
  if ( (result & 0x80000000) != 0LL )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x18001b1d8  push    rbx
0x18001b1da  push    rbp
0x18001b1db  push    rsi
0x18001b1dc  push    rdi
0x18001b1dd  push    r14
0x18001b1df  sub     rsp, 30h
0x18001b1e3  xor     r14d, r14d
0x18001b1e6  mov     rbx, r9
0x18001b1e9  mov     rbp, r8
0x18001b1ec  mov     rsi, rdx
0x18001b1ef  mov     rdi, rcx
0x18001b1f2  test    rdx, rdx
0x18001b1f5  jz      loc_18001B31E
0x18001b1fb  test    r8, r8
0x18001b1fe  jz      loc_18001B31E
0x18001b204  cmp     [rdx], r14b
0x18001b207  jnz     short loc_18001B21B
0x18001b209  test    rcx, rcx
0x18001b20c  jz      loc_18001B325
0x18001b212  mov     [rcx], r14w
0x18001b216  jmp     loc_18001B325
0x18001b21b  cmp     [r9+28h], r14b
0x18001b21f  jnz     short loc_18001B229
0x18001b221  mov     rcx, rbx; this
0x18001b224  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x18001b229  mov     rdx, [rbx+18h]
0x18001b22d  mov     r10d, [rdx+0Ch]
0x18001b231  cmp     r10d, 0FDE9h
0x18001b238  jnz     short loc_18001B261
0x18001b23a  lea     r9, qword_18003E370; unsigned __int64
0x18001b241  mov     [rsp+58h+var_38], rbx; struct _Mbstatet *
0x18001b246  mov     r8, rbp; char *
0x18001b249  mov     rdx, rsi; wchar_t *
0x18001b24c  mov     rcx, rdi; this
0x18001b24f  call    ?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b254  or      ecx, 0FFFFFFFFh
0x18001b257  test    eax, eax
0x18001b259  cmovs   eax, ecx
0x18001b25c  jmp     loc_18001B327
0x18001b261  cmp     [rdx+138h], r14
0x18001b268  jnz     short loc_18001B27E
0x18001b26a  test    rdi, rdi
0x18001b26d  jz      loc_18001B317
0x18001b273  movzx   eax, byte ptr [rsi]
0x18001b276  mov     [rdi], ax
0x18001b279  jmp     loc_18001B317
0x18001b27e  movzx   ecx, byte ptr [rsi]
0x18001b281  mov     rax, [rdx]
0x18001b284  cmp     [rax+rcx*2], r14w
0x18001b289  jge     short loc_18001B2EC
0x18001b28b  mov     r9d, [rdx+8]
0x18001b28f  cmp     r9d, 1
0x18001b293  jle     short loc_18001B2C0
0x18001b295  cmp     ebp, r9d
0x18001b298  jl      short loc_18001B2C0
0x18001b29a  mov     eax, r14d
0x18001b29d  test    rdi, rdi
0x18001b2a0  mov     r8, rsi
0x18001b2a3  mov     edx, 9
0x18001b2a8  setnz   al
0x18001b2ab  mov     ecx, r10d
0x18001b2ae  mov     [rsp+58h+var_30], eax
0x18001b2b2  mov     [rsp+58h+var_38], rdi
0x18001b2b7  call    __acrt_MultiByteToWideChar
0x18001b2bc  test    eax, eax
0x18001b2be  jnz     short loc_18001B2D3
0x18001b2c0  mov     rax, [rbx+18h]
0x18001b2c4  movsxd  rcx, dword ptr [rax+8]
0x18001b2c8  cmp     rbp, rcx
0x18001b2cb  jb      short loc_18001B2DC
0x18001b2cd  cmp     [rsi+1], r14b
0x18001b2d1  jz      short loc_18001B2DC
0x18001b2d3  mov     rax, [rbx+18h]
0x18001b2d7  mov     eax, [rax+8]
0x18001b2da  jmp     short loc_18001B327
0x18001b2dc  mov     byte ptr [rbx+30h], 1
0x18001b2e0  or      eax, 0FFFFFFFFh
0x18001b2e3  mov     dword ptr [rbx+2Ch], 2Ah ; '*'
0x18001b2ea  jmp     short loc_18001B327
0x18001b2ec  mov     eax, r14d
0x18001b2ef  mov     r9d, 1
0x18001b2f5  test    rdi, rdi
0x18001b2f8  mov     r8, rsi
0x18001b2fb  mov     ecx, r10d
0x18001b2fe  setnz   al
0x18001b301  mov     [rsp+58h+var_30], eax
0x18001b305  lea     edx, [r9+8]
0x18001b309  mov     [rsp+58h+var_38], rdi
0x18001b30e  call    __acrt_MultiByteToWideChar
0x18001b313  test    eax, eax
0x18001b315  jz      short loc_18001B2DC
0x18001b317  mov     eax, 1
0x18001b31c  jmp     short loc_18001B327
0x18001b31e  mov     cs:qword_18003E370, r14
0x18001b325  xor     eax, eax
0x18001b327  add     rsp, 30h
0x18001b32b  pop     r14
0x18001b32d  pop     rdi
0x18001b32e  pop     rsi
0x18001b32f  pop     rbp
0x18001b330  pop     rbx
0x18001b331  retn
```
