# MRxDAVCreateFileInfoCacheWithName

- ea: `0x1400255d4`
- end: `0x140025644`
- name: `MRxDAVCreateFileInfoCacheWithName`
- size: `112`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14001e6a0`

## callees

- `0x1400027ac`
- `0x1400253e0`
- `0x1400255d4`
- `0x14002564c`

## pseudocode

```c
_UNKNOWN **__fastcall MRxDAVCreateFileInfoCacheWithName(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _UNKNOWN **result; // rax

  MRxDAVCreateBasicFileInfoCacheWithName(a1, a2, a3);
  MRxDAVCreateStandardFileInfoCacheWithName(a1, a2, a4);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    return (_UNKNOWN **)WPP_SF_Z(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          11,
                          WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
                          a1);
  return result;
}

```

## disassembly

```asm
0x1400255d4  mov     [rsp+arg_0], rbx
0x1400255d9  mov     [rsp+arg_8], rsi
0x1400255de  push    rdi
0x1400255df  sub     rsp, 20h
0x1400255e3  mov     rdi, r9
0x1400255e6  mov     rbx, rdx
0x1400255e9  mov     rsi, rcx
0x1400255ec  call    MRxDAVCreateBasicFileInfoCacheWithName
0x1400255f1  mov     r8, rdi
0x1400255f4  mov     rdx, rbx
0x1400255f7  mov     rcx, rsi
0x1400255fa  call    MRxDAVCreateStandardFileInfoCacheWithName
0x1400255ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140025606  lea     rax, WPP_GLOBAL_Control
0x14002560d  cmp     rcx, rax
0x140025610  jz      short loc_140025633
0x140025612  test    dword ptr [rcx+2Ch], 2000h
0x140025619  jz      short loc_140025633
0x14002561b  mov     rcx, [rcx+18h]
0x14002561f  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x140025626  mov     edx, 0Bh
0x14002562b  mov     r9, rsi
0x14002562e  call    WPP_SF_Z
0x140025633  mov     rbx, [rsp+28h+arg_0]
0x140025638  mov     rsi, [rsp+28h+arg_8]
0x14002563d  add     rsp, 20h
0x140025641  pop     rdi
0x140025642  retn
```
