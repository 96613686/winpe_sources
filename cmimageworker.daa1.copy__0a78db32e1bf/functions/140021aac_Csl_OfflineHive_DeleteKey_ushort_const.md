# Csl::OfflineHive::DeleteKey(ushort const *)

- ea: `0x140021aac`
- end: `0x140021b5c`
- name: `?DeleteKey@OfflineHive@Csl@@QEAAJPEBG@Z`
- size: `176`
- prototype: `int(Csl::OfflineHive *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140021b64`

## callees

- `0x14000d7bc`
- `0x140021aac`
- `0x140023c20`
- `0x140024310`
- `0x140024760`

## string_xrefs

- `0x140021ad9`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140021b1b`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::OfflineHive::DeleteKey(Csl::OfflineHive *this, const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // rbx
  unsigned int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v2 = OROpenKey(*((_QWORD *)this + 1), a2, &v10);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x170,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)v2,
           v8);
    if ( v10 )
      ORCloseKey(v10);
    return v3;
  }
  else
  {
    v5 = v10;
    v6 = ORDeleteKey(v10, 0);
    if ( v6 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x173,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
             (const char *)v6,
             v8);
      if ( v5 )
        ORCloseKey(v5);
      return v7;
    }
    else
    {
      if ( v5 )
        ORCloseKey(v5);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x140021aac  mov     [rsp+arg_8], rbx
0x140021ab1  push    rdi; unsigned int
0x140021ab2  sub     rsp, 20h
0x140021ab6  mov     [rsp+28h+arg_0], 0
0x140021abf  lea     r8, [rsp+28h+arg_0]
0x140021ac4  mov     rcx, [rcx+8]
0x140021ac8  call    OROpenKey
0x140021acd  test    eax, eax
0x140021acf  jz      short loc_140021B00
0x140021ad1  mov     rcx, [rsp+28h]; this
0x140021ad6  mov     r9d, eax; char *
0x140021ad9  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021ae0  mov     edx, 170h; void *
0x140021ae5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021aea  mov     ebx, eax
0x140021aec  mov     rcx, [rsp+28h+arg_0]
0x140021af1  test    rcx, rcx
0x140021af4  jz      short loc_140021AFC
0x140021af6  call    ORCloseKey
0x140021afb  nop
0x140021afc  mov     eax, ebx
0x140021afe  jmp     short loc_140021B50
0x140021b00  xor     edx, edx
0x140021b02  mov     rbx, [rsp+28h+arg_0]
0x140021b07  mov     rcx, rbx
0x140021b0a  call    ORDeleteKey
0x140021b0f  test    eax, eax
0x140021b11  jz      short loc_140021B40
0x140021b13  mov     rcx, [rsp+28h]; this
0x140021b18  mov     r9d, eax; char *
0x140021b1b  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x140021b22  mov     edx, 173h; void *
0x140021b27  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140021b2c  mov     edi, eax
0x140021b2e  test    rbx, rbx
0x140021b31  jz      short loc_140021B3C
0x140021b33  mov     rcx, rbx
0x140021b36  call    ORCloseKey
0x140021b3b  nop
0x140021b3c  mov     eax, edi
0x140021b3e  jmp     short loc_140021B50
0x140021b40  test    rbx, rbx
0x140021b43  jz      short loc_140021B4E
0x140021b45  mov     rcx, rbx
0x140021b48  call    ORCloseKey
0x140021b4d  nop
0x140021b4e  xor     eax, eax
0x140021b50  mov     rbx, [rsp+28h+arg_8]
0x140021b55  add     rsp, 20h
0x140021b59  pop     rdi
0x140021b5a  retn
```
