# DiscpGetDiscoveryTag

- ea: `0x18000690c`
- end: `0x18000698f`
- name: `DiscpGetDiscoveryTag`
- size: `131`
- prototype: `__int64 __fastcall(wchar_t *pszSrc, int, char, _DWORD *)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002cbc`
- `0x180004380`
- `0x180005720`
- `0x18000a748`
- `0x18000bfc4`
- `0x18000c03c`
- `0x180011df0`

## callees

- `0x180005630`
- `0x1800061a8`
- `0x18000690c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000697c`
- `ntdll!RtlLeaveCriticalSection` at `0x18000697c`
- `ntdll!RtlEnterCriticalSection` at `0x180006932`
- `ntdll!RtlEnterCriticalSection` at `0x180006932`

## pseudocode

```c
__int64 __fastcall DiscpGetDiscoveryTag(wchar_t *pszSrc, int a2, char a3, _DWORD *a4)
{
  unsigned int DiscoveryTag; // ebx
  _QWORD v10[7]; // [rsp+20h] [rbp-38h] BYREF

  v10[0] = 0;
  RtlEnterCriticalSection(&DiscpCritSection);
  DiscoveryTag = DiscpFindDiscoveryTag(pszSrc, a2, v10);
  if ( DiscoveryTag == 1168 )
  {
    if ( !a3 )
      goto LABEL_6;
    DiscoveryTag = DiscpAllocDiscoveryTag(pszSrc);
  }
  if ( !DiscoveryTag )
    *a4 = *(_DWORD *)(v10[0] + 16LL);
LABEL_6:
  RtlLeaveCriticalSection(&DiscpCritSection);
  return DiscoveryTag;
}

```

## disassembly

```asm
0x18000690c  push    rbx
0x18000690e  push    rbp
0x18000690f  push    rsi
0x180006910  push    rdi
0x180006911  push    r14
0x180006913  sub     rsp, 30h
0x180006917  mov     rsi, rcx
0x18000691a  mov     [rsp+58h+var_38], 0
0x180006923  lea     rcx, DiscpCritSection; CriticalSection
0x18000692a  mov     r14, r9
0x18000692d  mov     bpl, r8b
0x180006930  mov     edi, edx
0x180006932  call    cs:__imp_RtlEnterCriticalSection
0x180006938  lea     r8, [rsp+58h+var_38]
0x18000693d  mov     edx, edi
0x18000693f  mov     rcx, rsi; pszSrc
0x180006942  call    DiscpFindDiscoveryTag
0x180006947  mov     ebx, eax
0x180006949  cmp     eax, 490h
0x18000694e  jnz     short loc_180006966
0x180006950  test    bpl, bpl
0x180006953  jz      short loc_180006975
0x180006955  lea     r8, [rsp+58h+var_38]
0x18000695a  mov     edx, edi
0x18000695c  mov     rcx, rsi; pszSrc
0x18000695f  call    DiscpAllocDiscoveryTag
0x180006964  mov     ebx, eax
0x180006966  test    ebx, ebx
0x180006968  jnz     short loc_180006975
0x18000696a  mov     rax, [rsp+58h+var_38]
0x18000696f  mov     edx, [rax+10h]
0x180006972  mov     [r14], edx
0x180006975  lea     rcx, DiscpCritSection; CriticalSection
0x18000697c  call    cs:__imp_RtlLeaveCriticalSection
0x180006982  mov     eax, ebx
0x180006984  add     rsp, 30h
0x180006988  pop     r14
0x18000698a  pop     rdi
0x18000698b  pop     rsi
0x18000698c  pop     rbp
0x18000698d  pop     rbx
0x18000698e  retn
```
