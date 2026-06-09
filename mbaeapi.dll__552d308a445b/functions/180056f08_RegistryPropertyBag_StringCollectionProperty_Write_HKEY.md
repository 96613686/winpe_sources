# RegistryPropertyBag::StringCollectionProperty::Write(HKEY__ *)

- ea: `0x180056f08`
- end: `0x180056fc6`
- name: `?Write@StringCollectionProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `190`
- prototype: `int(RegistryPropertyBag::StringCollectionProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180055de0`

## callees

- `0x180055448`
- `0x180055470`
- `0x180056f08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056f74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056f74`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::StringCollectionProperty::Write(
        RegistryPropertyBag::StringCollectionProperty *this,
        HKEY a2)
{
  int v4; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
  v4 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    v4 = RegSetValueExW(a2, *((LPCWSTR *)this + 5), 0, 7u, *((const BYTE **)this + 6), 2 * *((_DWORD *)this + 14));
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  *((_DWORD *)this + 9) = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids,
      (unsigned int)v4);
  return *((unsigned int *)this + 9);
}

```

## disassembly

```asm
0x180056f08  mov     [rsp+arg_0], rbx
0x180056f0d  mov     [rsp+arg_8], rsi
0x180056f12  push    rdi
0x180056f13  sub     rsp, 30h
0x180056f17  mov     rdi, rdx
0x180056f1a  mov     rbx, rcx
0x180056f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f24  lea     rsi, WPP_GLOBAL_Control
0x180056f2b  cmp     rcx, rsi
0x180056f2e  jz      short loc_180056F4B
0x180056f30  test    byte ptr [rcx+1Ch], 10h
0x180056f34  jz      short loc_180056F4B
0x180056f36  mov     rcx, [rcx+10h]
0x180056f3a  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056f41  mov     edx, 1Ah
0x180056f46  call    WPP_SF_
0x180056f4b  xor     eax, eax
0x180056f4d  cmp     [rbx+8], al
0x180056f50  jz      short loc_180056F86
0x180056f52  mov     eax, [rbx+38h]
0x180056f55  mov     r9d, 7; dwType
0x180056f5b  mov     rdx, [rbx+28h]; lpValueName
0x180056f5f  add     eax, eax
0x180056f61  mov     [rsp+38h+cbData], eax; cbData
0x180056f65  xor     r8d, r8d; Reserved
0x180056f68  mov     rax, [rbx+30h]
0x180056f6c  mov     rcx, rdi; hKey
0x180056f6f  mov     [rsp+38h+lpData], rax; lpData
0x180056f74  call    cs:__imp_RegSetValueExW
0x180056f7a  test    eax, eax
0x180056f7c  jle     short loc_180056F86
0x180056f7e  movzx   eax, ax
0x180056f81  or      eax, 80070000h
0x180056f86  mov     [rbx+24h], eax
0x180056f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f90  cmp     rcx, rsi
0x180056f93  jz      short loc_180056FB3
0x180056f95  test    byte ptr [rcx+1Ch], 10h
0x180056f99  jz      short loc_180056FB3
0x180056f9b  mov     rcx, [rcx+10h]
0x180056f9f  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056fa6  mov     edx, 1Bh
0x180056fab  mov     r9d, eax
0x180056fae  call    WPP_SF_d
0x180056fb3  mov     eax, [rbx+24h]
0x180056fb6  mov     rbx, [rsp+38h+arg_0]
0x180056fbb  mov     rsi, [rsp+38h+arg_8]
0x180056fc0  add     rsp, 30h
0x180056fc4  pop     rdi
0x180056fc5  retn
```
