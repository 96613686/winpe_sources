# DiscpFreeDiscoveryTag

- ea: `0x1800067e8`
- end: `0x180006867`
- name: `DiscpFreeDiscoveryTag`
- size: `127`
- prototype: `__int64 __fastcall(wchar_t *pszSrc, int)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002cbc`
- `0x180004380`
- `0x180005720`
- `0x180007900`
- `0x18000a748`
- `0x18000bfc4`
- `0x18000c03c`
- `0x180011df0`

## callees

- `0x1800061a8`
- `0x1800067e8`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x180006840`
- `ISCSIUM!DiscpFreeMemory` at `0x180006840`
- `ntdll!RtlLeaveCriticalSection` at `0x18000684d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000684d`
- `ntdll!RtlEnterCriticalSection` at `0x180006807`
- `ntdll!RtlEnterCriticalSection` at `0x180006807`

## pseudocode

```c
__int64 __fastcall DiscpFreeDiscoveryTag(wchar_t *pszSrc, int a2)
{
  unsigned int DiscoveryTag; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  _QWORD *v7; // r8
  _QWORD *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  DiscoveryTag = DiscpFindDiscoveryTag(pszSrc, a2, &v9);
  if ( !DiscoveryTag )
  {
    v5 = v9;
    v6 = *v9;
    if ( *(_QWORD **)(*v9 + 8LL) != v9 || (v7 = (_QWORD *)v9[1], (_QWORD *)*v7 != v9) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    DiscpFreeMemory(v5);
  }
  RtlLeaveCriticalSection(&DiscpCritSection);
  return DiscoveryTag;
}

```

## disassembly

```asm
0x1800067e8  mov     [rsp+arg_0], rbx
0x1800067ed  push    rdi
0x1800067ee  sub     rsp, 20h
0x1800067f2  mov     rdi, rcx
0x1800067f5  mov     [rsp+28h+arg_10], 0
0x1800067fe  lea     rcx, DiscpCritSection; CriticalSection
0x180006805  mov     ebx, edx
0x180006807  call    cs:__imp_RtlEnterCriticalSection
0x18000680d  lea     r8, [rsp+28h+arg_10]
0x180006812  mov     edx, ebx
0x180006814  mov     rcx, rdi; pszSrc
0x180006817  call    DiscpFindDiscoveryTag
0x18000681c  mov     ebx, eax
0x18000681e  test    eax, eax
0x180006820  jnz     short loc_180006846
0x180006822  mov     rcx, [rsp+28h+arg_10]
0x180006827  mov     rdx, [rcx]
0x18000682a  cmp     [rdx+8], rcx
0x18000682e  jnz     short loc_180006860
0x180006830  mov     r8, [rcx+8]
0x180006834  cmp     [r8], rcx
0x180006837  jnz     short loc_180006860
0x180006839  mov     [r8], rdx
0x18000683c  mov     [rdx+8], r8
0x180006840  call    cs:__imp_DiscpFreeMemory
0x180006846  lea     rcx, DiscpCritSection; CriticalSection
0x18000684d  call    cs:__imp_RtlLeaveCriticalSection
0x180006853  mov     eax, ebx
0x180006855  mov     rbx, [rsp+28h+arg_0]
0x18000685a  add     rsp, 20h
0x18000685e  pop     rdi
0x18000685f  retn
0x180006860  mov     ecx, 3
0x180006865  int     29h; Win8: RtlFailFast(ecx)
```
