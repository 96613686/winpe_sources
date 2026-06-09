# PwrshPlugInMediator::ReadConfigXmlValue(ushort const *,ushort const *,unsigned __int64)

- ea: `0x180003f0c`
- end: `0x180004047`
- name: `?ReadConfigXmlValue@PwrshPlugInMediator@@QEAAPEAGPEBG0_K@Z`
- size: `315`
- prototype: `unsigned __int16 *__fastcall(PwrshPlugInMediator *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180003a68`

## callees

- `0x180001098`
- `0x180001318`
- `0x180001dfc`
- `0x180002058`
- `0x180002e80`
- `0x180003f0c`
- `0x1800042ec`

## import_xrefs

- `msvcrt!isspace` at `0x180003f57`
- `msvcrt!isspace` at `0x180003f57`
- `msvcrt!wcsstr` at `0x180003f2a`
- `msvcrt!wcsstr` at `0x180003f2a`

## pseudocode

```c
unsigned __int16 *__fastcall PwrshPlugInMediator::ReadConfigXmlValue(
        PwrshPlugInMediator *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4)
{
  wchar_t *v6; // rax
  _WORD *i; // rbx
  const unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // rsi
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rdi
  PlugInException *v13; // rax
  void *v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-68h] BYREF
  _QWORD pExceptionObject[9]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *v18; // [rsp+70h] [rbp+8h] BYREF

  v18 = (unsigned __int16 *)this;
  v6 = wcsstr(a2, L"Value=");
  if ( !v6 )
    return 0;
  for ( i = v6 + 6; isspace((unsigned __int16)*i) && i - a3 < a4; ++i )
    ;
  if ( *i != 34 && *i != 39 )
    return 0;
  v8 = i + 1;
  v9 = v8;
  while ( *v8 != 34 && *v8 != 39 && v8 - a3 < a4 )
    ++v8;
  v10 = v8 - v9;
  if ( !v10 )
    return 0;
  v11 = (unsigned __int16 *)operator new[](saturated_mul(v10 + 1, 2u));
  pExceptionObject[1] = v11;
  if ( (int)StringCchCopyNW(v11, v10 + 1, v9, v10) < 0 )
  {
    v18 = 0;
    try
    {
      GetFormattedErrorMessage(&v18, 0x805403EE);
      v13 = (PlugInException *)operator new(0x10u);
      if ( v13 )
        v13 = PlugInException::PlugInException(v13, 0x805403EE, v18);
      pExceptionObject[0] = v13;
      throw (PlugInException **)pExceptionObject;
    }
    catch ( ... )
    {
      v15 = &v16;
      v14 = (void *)v15[5];
      if ( v14 )
        operator delete[](v14);
      throw;
    }
  }
  return v11;
}

```

## disassembly

```asm
0x180003f0c  mov     [rsp+arg_0], rcx
0x180003f11  push    rbx
0x180003f12  push    rsi
0x180003f13  push    rdi
0x180003f14  push    r14
0x180003f16  sub     rsp, 48h
0x180003f1a  mov     rdi, r9
0x180003f1d  mov     r14, r8
0x180003f20  mov     rcx, rdx; Str
0x180003f23  lea     rdx, aValue; "Value="
0x180003f2a  call    cs:__imp_wcsstr
0x180003f30  mov     rbx, rax
0x180003f33  test    rax, rax
0x180003f36  jz      loc_180003FE4
0x180003f3c  add     rbx, 0Ch
0x180003f40  jmp     short loc_180003F54
0x180003f42  mov     rax, rbx
0x180003f45  sub     rax, r14
0x180003f48  sar     rax, 1
0x180003f4b  cmp     rax, rdi
0x180003f4e  jnb     short loc_180003F61
0x180003f50  add     rbx, 2
0x180003f54  movzx   ecx, word ptr [rbx]; C
0x180003f57  call    cs:__imp_isspace
0x180003f5d  test    eax, eax
0x180003f5f  jnz     short loc_180003F42
0x180003f61  mov     edx, 22h ; '"'
0x180003f66  lea     ecx, [rdx+5]
0x180003f69  cmp     dx, [rbx]
0x180003f6c  jz      short loc_180003F73
0x180003f6e  cmp     cx, [rbx]
0x180003f71  jnz     short loc_180003FE4
0x180003f73  add     rbx, 2
0x180003f77  mov     rsi, rbx
0x180003f7a  jmp     short loc_180003F93
0x180003f7c  cmp     cx, ax
0x180003f7f  jz      short loc_180003F9B
0x180003f81  mov     rax, rbx
0x180003f84  sub     rax, r14
0x180003f87  sar     rax, 1
0x180003f8a  cmp     rax, rdi
0x180003f8d  jnb     short loc_180003F9B
0x180003f8f  add     rbx, 2
0x180003f93  movzx   eax, word ptr [rbx]
0x180003f96  cmp     dx, ax
0x180003f99  jnz     short loc_180003F7C
0x180003f9b  sub     rbx, rsi
0x180003f9e  sar     rbx, 1
0x180003fa1  jz      short loc_180003FE4
0x180003fa3  lea     r14, [rbx+1]
0x180003fa7  mov     eax, 2
0x180003fac  mul     r14
0x180003faf  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003fb6  cmovb   rax, rcx
0x180003fba  mov     rcx, rax; unsigned __int64
0x180003fbd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003fc2  mov     rdi, rax
0x180003fc5  mov     [rsp+68h+var_40], rax
0x180003fca  mov     r9, rbx; unsigned __int64
0x180003fcd  mov     r8, rsi; unsigned __int16 *
0x180003fd0  mov     rdx, r14; unsigned __int64
0x180003fd3  mov     rcx, rax; unsigned __int16 *
0x180003fd6  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180003fdb  test    eax, eax
0x180003fdd  js      short loc_180003FF0
0x180003fdf  mov     rax, rdi
0x180003fe2  jmp     short loc_180003FE6
0x180003fe4  xor     eax, eax
0x180003fe6  add     rsp, 48h
0x180003fea  pop     r14
0x180003fec  pop     rdi
0x180003fed  pop     rsi
0x180003fee  pop     rbx
0x180003fef  retn
0x180003ff0  mov     [rsp+68h+arg_0], 0
0x180003ff9  lea     r8, aInitialization; "InitializationParameters"
0x180004000  mov     ebx, 805403EEh
0x180004005  mov     edx, ebx; unsigned int
0x180004007  lea     rcx, [rsp+68h+arg_0]; unsigned __int16 **
0x18000400c  call    ?GetFormattedErrorMessage@@YAKPEAPEAGKZZ; GetFormattedErrorMessage(ushort * *,ulong,...)
0x180004011  mov     ecx, 10h; Size
0x180004016  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000401b  test    rax, rax
0x18000401e  jz      short loc_18000402F
0x180004020  mov     r8, [rsp+68h+arg_0]; unsigned __int16 *
0x180004025  mov     edx, ebx; unsigned int
0x180004027  mov     rcx, rax; this
0x18000402a  call    ??0PlugInException@@QEAA@KPEAG@Z; PlugInException::PlugInException(ulong,ushort *)
0x18000402f  mov     [rsp+68h+pExceptionObject], rax
0x180004034  lea     rdx, _TI2PEAVPlugInException@@; pThrowInfo
0x18000403b  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180004040  call    _CxxThrowException_0
```
