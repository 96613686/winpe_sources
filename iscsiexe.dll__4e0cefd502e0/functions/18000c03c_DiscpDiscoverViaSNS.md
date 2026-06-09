# DiscpDiscoverViaSNS

- ea: `0x18000c03c`
- end: `0x18000c11b`
- name: `DiscpDiscoverViaSNS`
- size: `223`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, char)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180004380`
- `0x180009408`
- `0x18000d090`
- `0x180011df0`

## callees

- `0x1800067e8`
- `0x18000690c`
- `0x180007b20`
- `0x180007bb4`
- `0x18000c03c`
- `0x18000c474`

## import_xrefs

- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000c102`
- `ISCSIUM!DiscpReportEventlogWithStatus` at `0x18000c102`

## pseudocode

```c
__int64 __fastcall DiscpDiscoverViaSNS(STRSAFE_LPCWSTR pszSrc, char a2)
{
  unsigned int DiscoveryTag; // edi
  __int16 v5; // [rsp+30h] [rbp-18h]

  if ( a2 && !(unsigned int)DiscpGetDiscoveryTag(pszSrc) )
  {
    DiscpRemoveTargetsByTag(0);
    DiscpRemoveTargetPortalsByTag(0);
    DiscpFreeDiscoveryTag(pszSrc);
  }
  DiscoveryTag = DiscpGetDiscoveryTag(pszSrc);
  if ( DiscoveryTag )
    goto LABEL_7;
  DiscoveryTag = DiscpDoDiscoverViaSNS(pszSrc);
  if ( DiscoveryTag )
  {
    DiscpRemoveTargetsByTag(0);
    DiscpRemoveTargetPortalsByTag(0);
    DiscpFreeDiscoveryTag(pszSrc);
LABEL_7:
    v5 = 1;
    DiscpReportEventlogWithStatus(112, 2, 0, DiscoveryTag, 0, 0, v5);
  }
  return DiscoveryTag;
}

```

## disassembly

```asm
0x18000c03c  mov     rax, rsp
0x18000c03f  mov     [rax+8], rbx
0x18000c043  mov     [rax+18h], rdi
0x18000c047  push    r15
0x18000c049  sub     rsp, 40h
0x18000c04d  mov     dword ptr [rax+10h], 0
0x18000c054  mov     rbx, rcx
0x18000c057  test    dl, dl
0x18000c059  jz      short loc_18000C08E
0x18000c05b  xor     r8d, r8d
0x18000c05e  lea     r9, [rax+10h]
0x18000c062  lea     edx, [r8+3]
0x18000c066  call    DiscpGetDiscoveryTag
0x18000c06b  test    eax, eax
0x18000c06d  jnz     short loc_18000C08E
0x18000c06f  mov     ecx, [rsp+48h+arg_8]
0x18000c073  call    DiscpRemoveTargetsByTag
0x18000c078  mov     ecx, [rsp+48h+arg_8]
0x18000c07c  call    DiscpRemoveTargetPortalsByTag
0x18000c081  mov     edx, 3
0x18000c086  mov     rcx, rbx; pszSrc
0x18000c089  call    DiscpFreeDiscoveryTag
0x18000c08e  mov     r15d, 1
0x18000c094  lea     r9, [rsp+48h+arg_8]
0x18000c099  mov     r8b, r15b
0x18000c09c  mov     rcx, rbx; pszSrc
0x18000c09f  lea     edx, [r15+2]
0x18000c0a3  call    DiscpGetDiscoveryTag
0x18000c0a8  mov     edi, eax
0x18000c0aa  test    eax, eax
0x18000c0ac  jnz     short loc_18000C0DE
0x18000c0ae  mov     edx, [rsp+48h+arg_8]
0x18000c0b2  mov     rcx, rbx; pszSrc
0x18000c0b5  call    DiscpDoDiscoverViaSNS
0x18000c0ba  mov     edi, eax
0x18000c0bc  test    eax, eax
0x18000c0be  jz      short loc_18000C108
0x18000c0c0  mov     ecx, [rsp+48h+arg_8]
0x18000c0c4  call    DiscpRemoveTargetsByTag
0x18000c0c9  mov     ecx, [rsp+48h+arg_8]
0x18000c0cd  call    DiscpRemoveTargetPortalsByTag
0x18000c0d2  lea     edx, [r15+2]
0x18000c0d6  mov     rcx, rbx; pszSrc
0x18000c0d9  call    DiscpFreeDiscoveryTag
0x18000c0de  xor     eax, eax
0x18000c0e0  mov     [rsp+48h+var_10], rbx
0x18000c0e5  mov     [rsp+48h+var_18], r15w
0x18000c0eb  mov     r9d, edi
0x18000c0ee  mov     [rsp+48h+var_20], rax
0x18000c0f3  movzx   r8d, ax
0x18000c0f7  lea     edx, [rax+2]
0x18000c0fa  mov     [rsp+48h+var_28], rax
0x18000c0ff  lea     ecx, [rax+70h]
0x18000c102  call    cs:__imp_DiscpReportEventlogWithStatus
0x18000c108  mov     rbx, [rsp+48h+arg_0]
0x18000c10d  mov     eax, edi
0x18000c10f  mov     rdi, [rsp+48h+arg_10]
0x18000c114  add     rsp, 40h
0x18000c118  pop     r15
0x18000c11a  retn
```
