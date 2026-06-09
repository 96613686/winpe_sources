# Csl::OfflineHive::KeyExists(ushort const *,bool &)

- ea: `0x1400227a4`
- end: `0x14002282d`
- name: `?KeyExists@OfflineHive@Csl@@QEBAJPEBGAEA_N@Z`
- size: `137`
- prototype: `int(Csl::OfflineHive *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018320`

## callees

- `0x14000d7bc`
- `0x1400227a4`
- `0x140023c20`
- `0x140024760`

## string_xrefs

- `0x1400227ea`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Csl::OfflineHive::KeyExists(Csl::OfflineHive *this, const unsigned __int16 *a2, bool *a3)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  v4 = OROpenKey(*((_QWORD *)this + 1), a2, &v10);
  if ( v4 == 2 )
  {
    *a3 = 0;
    v5 = v10;
    if ( v10 )
      goto LABEL_9;
    return 0;
  }
  if ( !v4 )
  {
    *a3 = 1;
    v5 = v10;
    if ( v10 )
LABEL_9:
      ORCloseKey(v5);
    return 0;
  }
  v6 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x150,
         (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
         (const char *)v4,
         v8);
  if ( v10 )
    ORCloseKey(v10);
  return v6;
}

```

## disassembly

```asm
0x1400227a4  push    rbx; unsigned int
0x1400227a6  sub     rsp, 20h
0x1400227aa  mov     rbx, r8
0x1400227ad  mov     [rsp+28h+arg_0], 0
0x1400227b6  lea     r8, [rsp+28h+arg_0]
0x1400227bb  mov     rcx, [rcx+8]
0x1400227bf  call    OROpenKey
0x1400227c4  cmp     eax, 2
0x1400227c7  jnz     short loc_1400227DE
0x1400227c9  mov     byte ptr [rbx], 0
0x1400227cc  mov     rcx, [rsp+28h+arg_0]
0x1400227d1  test    rcx, rcx
0x1400227d4  jz      short loc_140022824
0x1400227d6  call    ORCloseKey
0x1400227db  nop
0x1400227dc  jmp     short loc_140022824
0x1400227de  test    eax, eax
0x1400227e0  jz      short loc_140022811
0x1400227e2  mov     rcx, [rsp+28h]; this
0x1400227e7  mov     r9d, eax; char *
0x1400227ea  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1400227f1  mov     edx, 150h; void *
0x1400227f6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400227fb  mov     ebx, eax
0x1400227fd  mov     rcx, [rsp+28h+arg_0]
0x140022802  test    rcx, rcx
0x140022805  jz      short loc_14002280D
0x140022807  call    ORCloseKey
0x14002280c  nop
0x14002280d  mov     eax, ebx
0x14002280f  jmp     short loc_140022826
0x140022811  mov     byte ptr [rbx], 1
0x140022814  mov     rcx, [rsp+28h+arg_0]
0x140022819  test    rcx, rcx
0x14002281c  jz      short loc_140022824
0x14002281e  call    ORCloseKey
0x140022823  nop
0x140022824  xor     eax, eax
0x140022826  add     rsp, 20h
0x14002282a  pop     rbx
0x14002282b  retn
```
