# MRxDAVCreateFileInfoCache

- ea: `0x140025520`
- end: `0x1400255ce`
- name: `MRxDAVCreateFileInfoCache`
- size: `174`
- prototype: `_UNKNOWN **__fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400130e0`

## callees

- `0x1400027ac`
- `0x1400253e0`
- `0x140025520`
- `0x14002564c`

## pseudocode

```c
_UNKNOWN **__fastcall MRxDAVCreateFileInfoCache(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 *v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r9
  _UNKNOWN **result; // rax

  v4 = *(_QWORD *)(a1 + 56);
  v5 = (__int64 *)(a1 + 648);
  if ( *(_BYTE *)(a1 + 32) )
    v6 = *(_QWORD *)(v4 + 120);
  else
    v6 = *v5;
  MRxDAVCreateBasicFileInfoCacheWithName(v4 + 360, v6, a2);
  v7 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(a1 + 32) )
    v5 = (__int64 *)(v7 + 120);
  MRxDAVCreateStandardFileInfoCacheWithName(v7 + 360, *v5, a2 + 40);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    return (_UNKNOWN **)WPP_SF_Z(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          10,
                          WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids,
                          *(_QWORD *)(a1 + 56) + 360LL);
  return result;
}

```

## disassembly

```asm
0x140025520  mov     [rsp+arg_0], rbx
0x140025525  mov     [rsp+arg_8], rsi
0x14002552a  push    rdi
0x14002552b  sub     rsp, 20h
0x14002552f  mov     rbx, rcx
0x140025532  mov     rsi, rdx
0x140025535  mov     rcx, [rcx+38h]
0x140025539  cmp     byte ptr [rbx+20h], 0
0x14002553d  lea     rdi, [rbx+288h]
0x140025544  jnz     short loc_14002554B
0x140025546  mov     rdx, [rdi]
0x140025549  jmp     short loc_14002554F
0x14002554b  mov     rdx, [rcx+78h]
0x14002554f  add     rcx, 168h
0x140025556  mov     r8, rsi
0x140025559  call    MRxDAVCreateBasicFileInfoCacheWithName
0x14002555e  mov     r9, [rbx+38h]
0x140025562  lea     r8, [rsi+28h]
0x140025566  cmp     byte ptr [rbx+20h], 0
0x14002556a  lea     rcx, [r9+78h]
0x14002556e  cmovnz  rdi, rcx
0x140025572  lea     rcx, [r9+168h]
0x140025579  mov     rdx, [rdi]
0x14002557c  call    MRxDAVCreateStandardFileInfoCacheWithName
0x140025581  mov     rcx, cs:WPP_GLOBAL_Control
0x140025588  lea     rax, WPP_GLOBAL_Control
0x14002558f  cmp     rcx, rax
0x140025592  jz      short loc_1400255BD
0x140025594  test    dword ptr [rcx+2Ch], 2000h
0x14002559b  jz      short loc_1400255BD
0x14002559d  mov     r9, [rbx+38h]
0x1400255a1  lea     r8, WPP_0bb9bda0334334abcb947ee897e48a0b_Traceguids
0x1400255a8  mov     rcx, [rcx+18h]
0x1400255ac  add     r9, 168h
0x1400255b3  mov     edx, 0Ah
0x1400255b8  call    WPP_SF_Z
0x1400255bd  mov     rbx, [rsp+28h+arg_0]
0x1400255c2  mov     rsi, [rsp+28h+arg_8]
0x1400255c7  add     rsp, 20h
0x1400255cb  pop     rdi
0x1400255cc  retn
```
