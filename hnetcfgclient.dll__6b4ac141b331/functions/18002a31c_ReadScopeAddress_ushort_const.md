# ReadScopeAddress(ushort const *)

- ea: `0x18002a31c`
- end: `0x18002a3e3`
- name: `?ReadScopeAddress@@YAKPEBG@Z`
- size: `199`
- prototype: `unsigned int __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002a2b4`

## callees

- `0x180007b74`
- `0x180008570`
- `0x1800285a4`
- `0x18002a1e8`
- `0x18002a31c`
- `0x18002d200`

## string_xrefs

- `0x18002a37c`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadScopeAddress(const unsigned __int16 *a1)
{
  unsigned int v2; // ebx
  unsigned int v4; // [rsp+20h] [rbp-50h] BYREF
  HKEY v5[3]; // [rsp+28h] [rbp-48h] BYREF
  WCHAR AddressString[8]; // [rsp+40h] [rbp-30h] BYREF
  __int128 v7; // [rsp+50h] [rbp-20h]

  *(_OWORD *)AddressString = 0;
  v7 = 0;
  memset(v5, 0, sizeof(v5));
  v4 = 32;
  if ( a1 )
  {
    v2 = -1;
    if ( !(unsigned int)ATL::CRegKey::Open(
                          v5,
                          HKEY_LOCAL_MACHINE,
                          L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters",
                          0x20019u)
      && !ATL::CRegKey::QueryValue((ATL::CRegKey *)v5, AddressString, a1, &v4) )
    {
      v2 = ConvertStringToAddress(AddressString);
    }
  }
  else
  {
    v2 = 87;
  }
  ATL::CRegKey::Close(v5);
  return v2;
}

```

## disassembly

```asm
0x18002a31c  mov     [rsp-8+arg_8], rbx
0x18002a321  mov     [rsp-8+arg_10], rdi
0x18002a326  push    rbp
0x18002a327  mov     rbp, rsp
0x18002a32a  sub     rsp, 70h
0x18002a32e  mov     rax, cs:__security_cookie
0x18002a335  xor     rax, rsp
0x18002a338  mov     [rbp+var_10], rax
0x18002a33c  mov     rdi, rcx
0x18002a33f  xorps   xmm0, xmm0
0x18002a342  movups  xmmword ptr [rbp+AddressString], xmm0
0x18002a346  movups  [rbp+var_20], xmm0
0x18002a34a  mov     [rbp+var_48], 0
0x18002a352  mov     [rbp+var_40], 0
0x18002a35a  mov     [rbp+var_38], 0
0x18002a362  mov     [rbp+var_50], 20h ; ' '
0x18002a369  test    rcx, rcx
0x18002a36c  jnz     short loc_18002A373
0x18002a36e  lea     ebx, [rcx+57h]
0x18002a371  jmp     short loc_18002A3BA
0x18002a373  or      ebx, 0FFFFFFFFh
0x18002a376  mov     r9d, 20019h; unsigned int
0x18002a37c  lea     r8, ?c_szDhcpScopeKey@@3QBGB; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18002a383  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002a38a  lea     rcx, [rbp+var_48]; this
0x18002a38e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002a393  test    eax, eax
0x18002a395  jnz     short loc_18002A3BA
0x18002a397  lea     r9, [rbp+var_50]; unsigned int *
0x18002a39b  mov     r8, rdi; unsigned __int16 *
0x18002a39e  lea     rdx, [rbp+AddressString]; unsigned __int16 *
0x18002a3a2  lea     rcx, [rbp+var_48]; this
0x18002a3a6  call    ?QueryValue@CRegKey@ATL@@QEAAJPEAGPEBGPEAK@Z; ATL::CRegKey::QueryValue(ushort *,ushort const *,ulong *)
0x18002a3ab  test    eax, eax
0x18002a3ad  jnz     short loc_18002A3BA
0x18002a3af  lea     rcx, [rbp+AddressString]; AddressString
0x18002a3b3  call    ?ConvertStringToAddress@@YAKPEAG@Z; ConvertStringToAddress(ushort *)
0x18002a3b8  mov     ebx, eax
0x18002a3ba  lea     rcx, [rbp+var_48]; this
0x18002a3be  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002a3c3  mov     eax, ebx
0x18002a3c5  mov     rcx, [rbp+var_10]
0x18002a3c9  xor     rcx, rsp; StackCookie
0x18002a3cc  call    __security_check_cookie
0x18002a3d1  lea     r11, [rsp+70h+var_s0]
0x18002a3d6  mov     rbx, [r11+18h]
0x18002a3da  mov     rdi, [r11+20h]
0x18002a3de  mov     rsp, r11
0x18002a3e1  pop     rbp
0x18002a3e2  retn
```
