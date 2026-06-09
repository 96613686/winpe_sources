# CCredentials::Initialize(ushort const *,ushort const *,ulong)

- ea: `0x18000e0d4`
- end: `0x18000e14b`
- name: `?Initialize@CCredentials@@AEAAJPEBG0K@Z`
- size: `119`
- prototype: `__int64 __fastcall(CCredentials *this, LPCWSTR pStr, const unsigned __int16 *, int)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x1800051d0`
- `0x180005310`
- `0x180005a58`
- `0x1800065a0`
- `0x18000683c`
- `0x1800071b0`
- `0x1800072a0`
- `0x18000745c`
- `0x1800080d0`
- `0x18000828c`
- `0x180008834`
- `0x180008fc0`
- `0x180009c20`
- `0x180009df0`
- `0x18000a5b0`
- `0x18000a7f0`
- `0x18000a94c`
- `0x18000e01c`

## callees

- `0x18000df38`
- `0x18000e0d4`
- `0x18000e154`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsStr` at `0x18000e10d`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000e10d`

## pseudocode

```c
__int64 __fastcall CCredentials::Initialize(CCredentials *this, LPCWSTR pStr, const unsigned __int16 *a3, int a4)
{
  LPWSTR v8; // rax
  int v9; // edi

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  CCredentials::FreeUserName((unsigned __int16 **)this);
  if ( !pStr || (v8 = AllocADsStr(pStr), (*(_QWORD *)this = v8) != 0) )
  {
    v9 = CCredentials::SetPassword(this, a3);
    if ( v9 < 0 )
      CCredentials::FreeUserName((unsigned __int16 **)this);
    else
      *((_DWORD *)this + 4) = a4;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000e0d4  push    rbx
0x18000e0d6  push    rbp
0x18000e0d7  push    rsi
0x18000e0d8  push    rdi
0x18000e0d9  sub     rsp, 28h
0x18000e0dd  mov     esi, r9d
0x18000e0e0  mov     qword ptr [rcx], 0
0x18000e0e7  mov     rbp, r8
0x18000e0ea  mov     qword ptr [rcx+8], 0
0x18000e0f2  mov     rdi, rdx
0x18000e0f5  mov     qword ptr [rcx+10h], 0
0x18000e0fd  mov     rbx, rcx
0x18000e100  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000e105  test    rdi, rdi
0x18000e108  jz      short loc_18000E122
0x18000e10a  mov     rcx, rdi; pStr
0x18000e10d  call    cs:__imp_AllocADsStr
0x18000e113  mov     [rbx], rax
0x18000e116  test    rax, rax
0x18000e119  jnz     short loc_18000E122
0x18000e11b  mov     edi, 80004005h
0x18000e120  jmp     short loc_18000E140
0x18000e122  mov     rdx, rbp; unsigned __int16 *
0x18000e125  mov     rcx, rbx; this
0x18000e128  call    ?SetPassword@CCredentials@@QEAAJPEBG@Z; CCredentials::SetPassword(ushort const *)
0x18000e12d  mov     edi, eax
0x18000e12f  test    eax, eax
0x18000e131  js      short loc_18000E138
0x18000e133  mov     [rbx+10h], esi
0x18000e136  jmp     short loc_18000E140
0x18000e138  mov     rcx, rbx; unsigned __int16 **
0x18000e13b  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000e140  mov     eax, edi
0x18000e142  add     rsp, 28h
0x18000e146  pop     rdi
0x18000e147  pop     rsi
0x18000e148  pop     rbp
0x18000e149  pop     rbx
0x18000e14a  retn
```
