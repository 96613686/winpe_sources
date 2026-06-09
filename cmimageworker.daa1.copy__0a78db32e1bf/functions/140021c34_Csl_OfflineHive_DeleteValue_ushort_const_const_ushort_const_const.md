# Csl::OfflineHive::DeleteValue(ushort const * const,ushort const * const)

- ea: `0x140021c34`
- end: `0x140021d02`
- name: `?DeleteValue@OfflineHive@Csl@@QEAAJQEBG0@Z`
- size: `206`
- prototype: `int(Csl::OfflineHive *__hidden this, const unsigned __int16 *const, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001bb2c`

## callees

- `0x14000d7bc`
- `0x140021c34`
- `0x140023c20`
- `0x140024760`
- `0x140025640`

## string_xrefs

- `0x140021c64`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140021cc1`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::OfflineHive::DeleteValue(
        Csl::OfflineHive *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+30h] [rbp+8h] BYREF

  v13 = 0;
  v4 = OROpenKey(*((_QWORD *)this + 1), a2, &v13);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1C3,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v4,
           v11);
    if ( v13 )
      ORCloseKey(v13);
    return v5;
  }
  else
  {
    v7 = a3;
    v8 = v13;
    v9 = ORDeleteValue(v13, v7);
    if ( v9 == 2 )
    {
      if ( v8 )
        ORCloseKey(v8);
      return 2147942402LL;
    }
    else if ( v9 )
    {
      v10 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1CF,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
              (const char *)v9,
              v11);
      if ( v8 )
        ORCloseKey(v8);
      return v10;
    }
    else
    {
      if ( v8 )
        ORCloseKey(v8);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x140021c34  mov     [rsp+arg_8], rbx
0x140021c39  push    rdi; unsigned int
0x140021c3a  sub     rsp, 20h
0x140021c3e  mov     rbx, r8
0x140021c41  mov     [rsp+28h+arg_0], 0
0x140021c4a  lea     r8, [rsp+28h+arg_0]
0x140021c4f  mov     rcx, [rcx+8]
0x140021c53  call    OROpenKey
0x140021c58  test    eax, eax
0x140021c5a  jz      short loc_140021C8B
0x140021c5c  mov     rcx, [rsp+28h]; this
0x140021c61  mov     r9d, eax; char *
0x140021c64  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021c6b  mov     edx, 1C3h; void *
0x140021c70  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021c75  mov     ebx, eax
0x140021c77  mov     rcx, [rsp+28h+arg_0]
0x140021c7c  test    rcx, rcx
0x140021c7f  jz      short loc_140021C87
0x140021c81  call    ORCloseKey
0x140021c86  nop
0x140021c87  mov     eax, ebx
0x140021c89  jmp     short loc_140021CF6
0x140021c8b  mov     rdx, rbx
0x140021c8e  mov     rbx, [rsp+28h+arg_0]
0x140021c93  mov     rcx, rbx
0x140021c96  call    ORDeleteValue
0x140021c9b  cmp     eax, 2
0x140021c9e  jnz     short loc_140021CB5
0x140021ca0  test    rbx, rbx
0x140021ca3  jz      short loc_140021CAE
0x140021ca5  mov     rcx, rbx
0x140021ca8  call    ORCloseKey
0x140021cad  nop
0x140021cae  mov     eax, 80070002h
0x140021cb3  jmp     short loc_140021CF6
0x140021cb5  test    eax, eax
0x140021cb7  jz      short loc_140021CE6
0x140021cb9  mov     rcx, [rsp+28h]; this
0x140021cbe  mov     r9d, eax; char *
0x140021cc1  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021cc8  mov     edx, 1CFh; void *
0x140021ccd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021cd2  mov     edi, eax
0x140021cd4  test    rbx, rbx
0x140021cd7  jz      short loc_140021CE2
0x140021cd9  mov     rcx, rbx
0x140021cdc  call    ORCloseKey
0x140021ce1  nop
0x140021ce2  mov     eax, edi
0x140021ce4  jmp     short loc_140021CF6
0x140021ce6  test    rbx, rbx
0x140021ce9  jz      short loc_140021CF4
0x140021ceb  mov     rcx, rbx
0x140021cee  call    ORCloseKey
0x140021cf3  nop
0x140021cf4  xor     eax, eax
0x140021cf6  mov     rbx, [rsp+28h+arg_8]
0x140021cfb  add     rsp, 20h
0x140021cff  pop     rdi
0x140021d00  retn
```
