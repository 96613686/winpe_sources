# pSetupGetPolicyValue

- ea: `0x1800040d8`
- end: `0x1800041c3`
- name: `pSetupGetPolicyValue`
- size: `235`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, const WCHAR *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180001c4c`
- `0x180003cf8`
- `0x1800087c4`
- `0x18000892c`
- `0x180008bc0`
- `0x180008d80`

## callees

- `0x180003820`
- `0x180003988`
- `0x1800040d8`

## import_xrefs

- `ntdll!NtClose` at `0x180004158`
- `ntdll!NtClose` at `0x180004193`
- `ntdll!NtClose` at `0x180004158`
- `ntdll!NtClose` at `0x180004193`

## pseudocode

```c
__int64 __fastcall pSetupGetPolicyValue(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        const WCHAR *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v6; // ebx
  int v8; // eax
  __int64 v9; // r8
  int v10; // edi
  int Value; // edi
  HANDLE KeyHandle[2]; // [rsp+30h] [rbp-10h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp+30h] BYREF

  v6 = a5;
  Handle = 0;
  KeyHandle[0] = 0;
  v8 = pSetupOpenKey((void *)0xFFFFFFFF80000002LL, a2, a3, 1u, &Handle);
  if ( v8 != 2 )
  {
    if ( v8 )
      return a6;
    v10 = pSetupOpenKey(Handle, L"Restrictions", v9, 1u, KeyHandle);
    NtClose((HANDLE)(unsigned int)Handle);
    if ( v10 != 2 )
    {
      if ( v10 )
        return a6;
      a5 = 0;
      LODWORD(Handle) = 4;
      Value = pSetupQueryValue(KeyHandle[0], a4, (__int64)&Handle);
      NtClose((HANDLE)LODWORD(KeyHandle[0]));
      if ( Value != 2 )
      {
        if ( Value )
          return a6;
        if ( a5 != 4 )
          return a6;
        v6 = 0;
        if ( (_DWORD)Handle != 4 )
          return a6;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800040d8  mov     r11, rsp
0x1800040db  mov     [r11+10h], rbx
0x1800040df  mov     [r11+18h], r8
0x1800040e3  mov     [r11+8], rcx
0x1800040e7  push    rbp
0x1800040e8  push    rsi
0x1800040e9  push    rdi
0x1800040ea  mov     rbp, rsp
0x1800040ed  sub     rsp, 40h
0x1800040f1  mov     ebx, [rbp+arg_20]
0x1800040f4  lea     rax, [rbp+Handle]
0x1800040f8  mov     rsi, r9
0x1800040fb  mov     [rbp+Handle], 0
0x180004103  mov     edi, 1
0x180004108  mov     [rbp+KeyHandle], 0
0x180004110  mov     r9d, edi
0x180004113  mov     [rbp+arg_0], 0
0x18000411a  mov     rcx, 0FFFFFFFF80000002h
0x180004121  mov     [r11-38h], rax
0x180004125  call    pSetupOpenKey
0x18000412a  cmp     eax, 2
0x18000412d  jz      loc_1800041B4
0x180004133  test    eax, eax
0x180004135  jnz     short loc_1800041B1
0x180004137  mov     rcx, [rbp+Handle]
0x18000413b  lea     rax, [rbp+KeyHandle]
0x18000413f  mov     r9d, edi
0x180004142  mov     [rsp+40h+var_20], rax
0x180004147  lea     rdx, aRestrictions; "Restrictions"
0x18000414e  call    pSetupOpenKey
0x180004153  mov     ecx, dword ptr [rbp+Handle]; Handle
0x180004156  mov     edi, eax
0x180004158  call    cs:__imp_NtClose
0x18000415e  cmp     edi, 2
0x180004161  jz      short loc_1800041B4
0x180004163  test    edi, edi
0x180004165  jnz     short loc_1800041B1
0x180004167  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000416b  lea     rax, [rbp+Handle]
0x18000416f  lea     r9, [rbp+arg_0]
0x180004173  mov     [rsp+40h+var_20], rax; __int64
0x180004178  lea     r8, [rbp+arg_20]
0x18000417c  mov     [rbp+arg_20], edi
0x18000417f  mov     rdx, rsi; SourceString
0x180004182  mov     dword ptr [rbp+Handle], 4
0x180004189  call    pSetupQueryValue
0x18000418e  mov     ecx, dword ptr [rbp+KeyHandle]; Handle
0x180004191  mov     edi, eax
0x180004193  call    cs:__imp_NtClose
0x180004199  cmp     edi, 2
0x18000419c  jz      short loc_1800041B4
0x18000419e  test    edi, edi
0x1800041a0  jnz     short loc_1800041B1
0x1800041a2  cmp     [rbp+arg_20], 4
0x1800041a6  jnz     short loc_1800041B1
0x1800041a8  cmp     dword ptr [rbp+Handle], 4
0x1800041ac  mov     ebx, [rbp+arg_0]
0x1800041af  jz      short loc_1800041B4
0x1800041b1  mov     ebx, [rbp+arg_28]
0x1800041b4  mov     eax, ebx
0x1800041b6  mov     rbx, [rsp+40h+arg_8]
0x1800041bb  add     rsp, 40h
0x1800041bf  pop     rdi
0x1800041c0  pop     rsi
0x1800041c1  pop     rbp
0x1800041c2  retn
```
