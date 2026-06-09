# NatDeletePptpMapping

- ea: `0x14001526c`
- end: `0x14001533a`
- name: `NatDeletePptpMapping`
- size: `206`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140015be8`
- `0x14001f110`

## callees

- `0x14000218c`
- `0x140006e18`
- `0x14001526c`

## pseudocode

```c
void __fastcall NatDeletePptpMapping(_QWORD *Entry)
{
  _QWORD *v2; // rax
  PVOID *v3; // rcx
  _QWORD **v4; // rdx
  PVOID *v5; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
  v2 = (_QWORD *)*Entry;
  if ( *(_QWORD **)(*Entry + 8LL) != Entry
    || (v3 = (PVOID *)Entry[1], *v3 != Entry)
    || (*v3 = v2, v2[1] = v3, v4 = (_QWORD **)Entry[2], v4[1] != Entry + 2)
    || (v5 = (PVOID *)Entry[3], *v5 != Entry + 2) )
  {
    __fastfail(3u);
  }
  *v5 = v4;
  v4[1] = v5;
  NatFreeBlockAndUpdateStateAllocationUsage(&PptpLookasideList, Entry, 72);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids);
  }
}

```

## disassembly

```asm
0x14001526c  mov     [rsp+arg_0], rbx
0x140015271  push    rdi
0x140015272  sub     rsp, 20h
0x140015276  mov     rbx, rcx
0x140015279  mov     rcx, cs:WPP_GLOBAL_Control
0x140015280  lea     rdi, WPP_GLOBAL_Control
0x140015287  cmp     rcx, rdi
0x14001528a  jz      short loc_1400152AE
0x14001528c  mov     eax, [rcx+2Ch]
0x14001528f  test    al, 1
0x140015291  jz      short loc_1400152AE
0x140015293  cmp     byte ptr [rcx+29h], 6
0x140015297  jb      short loc_1400152AE
0x140015299  mov     rcx, [rcx+18h]
0x14001529d  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x1400152a4  mov     edx, 1Bh
0x1400152a9  call    WPP_SF_
0x1400152ae  mov     rax, [rbx]
0x1400152b1  cmp     [rax+8], rbx
0x1400152b5  jnz     short loc_140015333
0x1400152b7  mov     rcx, [rbx+8]
0x1400152bb  cmp     [rcx], rbx
0x1400152be  jnz     short loc_140015333
0x1400152c0  mov     [rcx], rax
0x1400152c3  mov     [rax+8], rcx
0x1400152c7  lea     rax, [rbx+10h]
0x1400152cb  mov     rdx, [rax]
0x1400152ce  cmp     [rdx+8], rax
0x1400152d2  jnz     short loc_140015333
0x1400152d4  mov     rcx, [rax+8]
0x1400152d8  cmp     [rcx], rax
0x1400152db  jnz     short loc_140015333
0x1400152dd  mov     [rcx], rdx
0x1400152e0  mov     r8d, 48h ; 'H'
0x1400152e6  mov     [rdx+8], rcx
0x1400152ea  mov     rdx, rbx; Entry
0x1400152ed  lea     rcx, PptpLookasideList; Lookaside
0x1400152f4  call    NatFreeBlockAndUpdateStateAllocationUsage
0x1400152f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140015300  cmp     rcx, rdi
0x140015303  jz      short loc_140015327
0x140015305  mov     eax, [rcx+2Ch]
0x140015308  test    al, 1
0x14001530a  jz      short loc_140015327
0x14001530c  cmp     byte ptr [rcx+29h], 6
0x140015310  jb      short loc_140015327
0x140015312  mov     rcx, [rcx+18h]
0x140015316  lea     r8, WPP_3a27ebff4bcb33fb26a0ac83a330c0c4_Traceguids
0x14001531d  mov     edx, 1Ch
0x140015322  call    WPP_SF_
0x140015327  mov     rbx, [rsp+28h+arg_0]
0x14001532c  add     rsp, 20h
0x140015330  pop     rdi
0x140015331  retn
0x140015333  mov     ecx, 3
0x140015338  int     29h; Win8: RtlFailFast(ecx)
```
