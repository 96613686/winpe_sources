# RegistryKey::ReadDWORDValue(ushort const *,ulong *)

- ea: `0x18004c868`
- end: `0x18004c922`
- name: `?ReadDWORDValue@RegistryKey@@QEBAJPEBGPEAK@Z`
- size: `186`
- prototype: `int(RegistryKey *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800368a4`
- `0x1800369a0`

## callees

- `0x18004c798`
- `0x18004c7dc`
- `0x18004c868`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c8a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004c8a8`

## string_xrefs

- `0x18004c904`: `onecore\internal\com\inc\combase\RegistryKey.hpp`

## pseudocode

```c
__int64 __fastcall RegistryKey::ReadDWORDValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  HKEY v3; // rcx
  LSTATUS ValueW; // eax
  void *v6; // rdx
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v12; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  v3 = *this;
  v12 = 4;
  ValueW = RegGetValueW(v3, 0, a2, 0x10u, 0, a3, &v12);
  v8 = ValueW;
  if ( ValueW > 0 )
    v8 = (unsigned __int16)ValueW | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( v8 == -2147024894 || v8 == -2147024662 )
      return v8;
    wil::details::in1diag3::Log_Hr(retaddr, v6, v7, (const char *)v8, v10);
  }
  if ( v8 == -2147023266 )
  {
    v8 = -2147221165;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x8FC,
      (unsigned int)"onecore\\internal\\com\\inc\\combase\\RegistryKey.hpp",
      (const char *)0x80040153LL,
      (int)"value:%ls",
      (const char *)a2);
  }
  return v8;
}

```

## disassembly

```asm
0x18004c868  mov     r11, rsp
0x18004c86b  mov     [r11+10h], rbx
0x18004c86f  push    rdi
0x18004c870  sub     rsp, 40h
0x18004c874  mov     dword ptr [r8], 0
0x18004c87b  lea     rax, [r11+8]
0x18004c87f  mov     rcx, [rcx]; hkey
0x18004c882  mov     rdi, rdx
0x18004c885  mov     [r11-18h], rax
0x18004c889  mov     r9d, 10h; dwFlags
0x18004c88f  mov     [r11-20h], r8
0x18004c893  mov     r8, rdx; lpValue
0x18004c896  xor     edx, edx; lpSubKey
0x18004c898  mov     [rsp+48h+arg_0], 4
0x18004c8a0  mov     qword ptr [r11-28h], 0
0x18004c8a8  call    cs:__imp_RegGetValueW
0x18004c8ae  mov     ebx, eax
0x18004c8b0  test    eax, eax
0x18004c8b2  jle     short loc_18004C8BD
0x18004c8b4  movzx   ebx, ax
0x18004c8b7  or      ebx, 80070000h
0x18004c8bd  test    ebx, ebx
0x18004c8bf  jns     short loc_18004C8DE
0x18004c8c1  cmp     ebx, 80070002h
0x18004c8c7  jz      short loc_18004C915
0x18004c8c9  cmp     ebx, 800700EAh
0x18004c8cf  jz      short loc_18004C915
0x18004c8d1  mov     rcx, [rsp+48h]; this
0x18004c8d6  mov     r9d, ebx; char *
0x18004c8d9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004c8de  cmp     ebx, 8007065Eh
0x18004c8e4  jnz     short loc_18004C915
0x18004c8e6  mov     rcx, [rsp+48h]; this
0x18004c8eb  lea     rax, aValueLs; "value:%ls"
0x18004c8f2  mov     ebx, 80040153h
0x18004c8f7  mov     [rsp+48h+var_20], rdi; char *
0x18004c8fc  mov     r9d, ebx; char *
0x18004c8ff  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004c904  lea     r8, aOnecoreInterna_3; "onecore\\internal\\com\\inc\\combase\\R"...
0x18004c90b  mov     edx, 8FCh; void *
0x18004c910  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c915  mov     eax, ebx
0x18004c917  mov     rbx, [rsp+48h+arg_8]
0x18004c91c  add     rsp, 40h
0x18004c920  pop     rdi
0x18004c921  retn
```
