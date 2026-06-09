# Csl::OfflineHive::CreateKey(ushort const * const,bool &)

- ea: `0x140021a0c`
- end: `0x140021aa4`
- name: `?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z`
- size: `152`
- prototype: `__int64 __fastcall(Csl::OfflineHive *__hidden this, const unsigned __int16 *const, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018320`
- `0x14001d310`

## callees

- `0x14000d7bc`
- `0x140021a0c`
- `0x140023c20`
- `0x140023cb0`

## string_xrefs

- `0x140021a5a`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::CreateKey(Csl::OfflineHive *this, const unsigned __int16 *const a2, bool *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  v4 = ORCreateKey(*((_QWORD *)this + 1), (int)a2, 0, 0, 0, (__int64)&v10, (__int64)&v9);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x126,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v4,
           v7);
    if ( v10 )
      ORCloseKey();
    return v5;
  }
  else
  {
    *a3 = v9 == 1;
    if ( v10 )
      ORCloseKey();
    return 0;
  }
}

```

## disassembly

```asm
0x140021a0c  mov     r11, rsp
0x140021a0f  push    rbx
0x140021a10  sub     rsp, 40h
0x140021a14  mov     rbx, r8
0x140021a17  mov     [rsp+48h+arg_0], 0
0x140021a1f  mov     qword ptr [r11+20h], 0
0x140021a27  lea     rax, [r11+8]
0x140021a2b  mov     [r11-18h], rax
0x140021a2f  lea     rax, [r11+20h]
0x140021a33  mov     [r11-20h], rax
0x140021a37  mov     qword ptr [r11-28h], 0
0x140021a3f  xor     r9d, r9d; int
0x140021a42  xor     r8d, r8d; int
0x140021a45  mov     rcx, [rcx+8]; int
0x140021a49  call    ORCreateKey
0x140021a4e  test    eax, eax
0x140021a50  jz      short loc_140021A81
0x140021a52  mov     rcx, [rsp+48h]; this
0x140021a57  mov     r9d, eax; char *
0x140021a5a  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021a61  mov     edx, 126h; void *
0x140021a66  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021a6b  mov     ebx, eax
0x140021a6d  mov     rcx, [rsp+48h+arg_18]
0x140021a72  test    rcx, rcx
0x140021a75  jz      short loc_140021A7D
0x140021a77  call    ORCloseKey
0x140021a7c  nop
0x140021a7d  mov     eax, ebx
0x140021a7f  jmp     short loc_140021A9D
0x140021a81  cmp     [rsp+48h+arg_0], 1
0x140021a86  setz    al
0x140021a89  mov     [rbx], al
0x140021a8b  mov     rcx, [rsp+48h+arg_18]
0x140021a90  test    rcx, rcx
0x140021a93  jz      short loc_140021A9B
0x140021a95  call    ORCloseKey
0x140021a9a  nop
0x140021a9b  xor     eax, eax
0x140021a9d  add     rsp, 40h
0x140021aa1  pop     rbx
0x140021aa2  retn
```
