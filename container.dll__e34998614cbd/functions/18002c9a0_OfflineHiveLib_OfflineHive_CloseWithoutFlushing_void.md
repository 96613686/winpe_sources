# OfflineHiveLib::OfflineHive::CloseWithoutFlushing(void)

- ea: `0x18002c9a0`
- end: `0x18002c9f5`
- name: `?CloseWithoutFlushing@OfflineHive@OfflineHiveLib@@QEAAXXZ`
- size: `85`
- prototype: `void(OfflineHiveLib::OfflineHive *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002c978`

## callees

- `0x180004b70`
- `0x180026344`
- `0x18002c9a0`
- `0x18002e050`

## string_xrefs

- `0x18002c9e0`: `onecore\base\gendrv\silos\registry\offlinehivelib\offlinehive.cpp`

## pseudocode

```c
void __fastcall OfflineHiveLib::OfflineHive::CloseWithoutFlushing(OfflineHiveLib::OfflineHive *this)
{
  signed int v2; // eax
  unsigned int v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 4) )
  {
    v2 = ORCloseHive();
    if ( v2 )
    {
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      v3 = wil::verify_hresult<long>((unsigned int)v2);
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x7EB,
        (unsigned int)"onecore\\base\\gendrv\\silos\\registry\\offlinehivelib\\offlinehive.cpp",
        (const char *)v3,
        v4);
    }
    *((_QWORD *)this + 4) = 0;
  }
}

```

## disassembly

```asm
0x18002c9a0  push    rbx; int
0x18002c9a2  sub     rsp, 20h
0x18002c9a6  mov     rbx, rcx
0x18002c9a9  mov     rcx, [rcx+20h]
0x18002c9ad  test    rcx, rcx
0x18002c9b0  jz      short loc_18002C9C3
0x18002c9b2  call    ORCloseHive
0x18002c9b7  test    eax, eax
0x18002c9b9  jnz     short loc_18002C9CA
0x18002c9bb  mov     qword ptr [rbx+20h], 0
0x18002c9c3  add     rsp, 20h
0x18002c9c7  pop     rbx
0x18002c9c8  retn
0x18002c9ca  jle     short loc_18002C9D4
0x18002c9cc  movzx   eax, ax
0x18002c9cf  or      eax, 80070000h
0x18002c9d4  mov     ecx, eax
0x18002c9d6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002c9db  mov     rcx, [rsp+28h]; this
0x18002c9e0  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\registry"...
0x18002c9e7  mov     r9d, eax; char *
0x18002c9ea  mov     edx, 7EBh; void *
0x18002c9ef  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
```
