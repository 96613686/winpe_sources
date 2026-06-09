# KpsDereferenceDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)

- ea: `0x180028dc0`
- end: `0x180028e14`
- name: `?KpsDereferenceDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z`
- size: `84`
- prototype: `void __fastcall(struct _KPS_DOMAIN_HASH_ENTRY *lpMem, __int64, __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180027de0`
- `0x1800280d8`
- `0x180028f28`
- `0x1800291e4`
- `0x180029c48`
- `0x18002b03c`

## callees

- `0x180028dc0`
- `0x180028e78`
- `0x18002c4dc`

## pseudocode

```c
void __fastcall KpsDereferenceDomainHashEntry(struct _KPS_DOMAIN_HASH_ENTRY *lpMem, __int64 a2, __int64 a3)
{
  int v4; // eax

  v4 = *((_DWORD *)lpMem + 6) - 1;
  *((_DWORD *)lpMem + 6) = v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, a3, lpMem, v4);
  if ( !*((_DWORD *)lpMem + 6) )
    KpsFreeDomainHashEntry(lpMem);
}

```

## disassembly

```asm
0x180028dc0  push    rbx
0x180028dc2  sub     rsp, 30h
0x180028dc6  mov     eax, [rcx+18h]
0x180028dc9  mov     rbx, rcx
0x180028dcc  dec     eax
0x180028dce  mov     [rcx+18h], eax
0x180028dd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180028dd8  lea     rdx, WPP_GLOBAL_Control
0x180028ddf  cmp     rcx, rdx
0x180028de2  jz      short loc_180028DFF
0x180028de4  test    byte ptr [rcx+1Ch], 80h
0x180028de8  jz      short loc_180028DFF
0x180028dea  mov     rcx, [rcx+10h]
0x180028dee  mov     edx, 21h ; '!'
0x180028df3  mov     r9, rbx
0x180028df6  mov     [rsp+38h+var_18], eax
0x180028dfa  call    WPP_SF_qL
0x180028dff  cmp     dword ptr [rbx+18h], 0
0x180028e03  jnz     short loc_180028E0D
0x180028e05  mov     rcx, rbx; lpMem
0x180028e08  call    ?KpsFreeDomainHashEntry@@YAXPEAU_KPS_DOMAIN_HASH_ENTRY@@@Z; KpsFreeDomainHashEntry(_KPS_DOMAIN_HASH_ENTRY *)
0x180028e0d  add     rsp, 30h
0x180028e11  pop     rbx
0x180028e12  retn
```
