# StubNlmCacheDeleteActiveStoreEntry

- ea: `0x180011300`
- end: `0x1800113d0`
- name: `StubNlmCacheDeleteActiveStoreEntry`
- size: `208`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001125c`
- `0x18002c380`

## callees

- `0x180011300`
- `0x18001182c`
- `0x18001c500`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18001137b`
- `ntdll!RtlRemoveEntryHashTable` at `0x18001137b`

## pseudocode

```c
__int64 __fastcall StubNlmCacheDeleteActiveStoreEntry(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rdx
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  --*(_DWORD *)(a1 + 68);
  v4 = (_QWORD *)(a2 + 8);
  v5 = *(_QWORD *)(a2 + 8);
  if ( *(_QWORD *)(v5 + 8) != a2 + 8 || (v6 = *(_QWORD **)(a2 + 16), (_QWORD *)*v6 != v4) )
    __fastfail(3u);
  *v6 = v5;
  *(_QWORD *)(v5 + 8) = v6;
  *(_QWORD *)(a2 + 16) = a2 + 8;
  *v4 = v4;
  RtlRemoveEntryHashTable(a1 + 88, a2 + 24, 0);
  result = StubNlmCacheDereferenceEntry(a1, a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180011300  mov     [rsp+arg_0], rbx
0x180011305  mov     [rsp+arg_8], rsi
0x18001130a  push    rdi
0x18001130b  sub     rsp, 20h
0x18001130f  mov     rdi, rdx
0x180011312  mov     rbx, rcx
0x180011315  mov     rcx, cs:WPP_GLOBAL_Control
0x18001131c  lea     rsi, WPP_GLOBAL_Control
0x180011323  cmp     rcx, rsi
0x180011326  jz      short loc_180011349
0x180011328  test    byte ptr [rcx+1Ch], 4
0x18001132c  jz      short loc_180011349
0x18001132e  cmp     byte ptr [rcx+19h], 6
0x180011332  jb      short loc_180011349
0x180011334  mov     rcx, [rcx+10h]
0x180011338  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x18001133f  mov     edx, 58h ; 'X'
0x180011344  call    WPP_SF_
0x180011349  dec     dword ptr [rbx+44h]
0x18001134c  lea     rax, [rdi+8]
0x180011350  mov     rcx, [rax]
0x180011353  cmp     [rcx+8], rax
0x180011357  jnz     short loc_1800113C9
0x180011359  mov     rdx, [rax+8]
0x18001135d  cmp     [rdx], rax
0x180011360  jnz     short loc_1800113C9
0x180011362  mov     [rdx], rcx
0x180011365  xor     r8d, r8d
0x180011368  mov     [rcx+8], rdx
0x18001136c  lea     rdx, [rdi+18h]
0x180011370  lea     rcx, [rbx+58h]
0x180011374  mov     [rax+8], rax
0x180011378  mov     [rax], rax
0x18001137b  call    cs:__imp_RtlRemoveEntryHashTable
0x180011381  mov     rdx, rdi
0x180011384  mov     rcx, rbx
0x180011387  call    StubNlmCacheDereferenceEntry
0x18001138c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011393  cmp     rcx, rsi
0x180011396  jz      short loc_1800113B9
0x180011398  test    byte ptr [rcx+1Ch], 4
0x18001139c  jz      short loc_1800113B9
0x18001139e  cmp     byte ptr [rcx+19h], 6
0x1800113a2  jb      short loc_1800113B9
0x1800113a4  mov     rcx, [rcx+10h]
0x1800113a8  lea     r8, WPP_095151aedd4c30f2c093374c08bcbfbc_Traceguids
0x1800113af  mov     edx, 59h ; 'Y'
0x1800113b4  call    WPP_SF_
0x1800113b9  mov     rbx, [rsp+28h+arg_0]
0x1800113be  mov     rsi, [rsp+28h+arg_8]
0x1800113c3  add     rsp, 20h
0x1800113c7  pop     rdi
0x1800113c8  retn
0x1800113c9  mov     ecx, 3
0x1800113ce  int     29h; Win8: RtlFailFast(ecx)
```
