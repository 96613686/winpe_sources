# MupReleaseIrpContext

- ea: `0x140001880`
- end: `0x1400019f1`
- name: `MupReleaseIrpContext`
- size: `369`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14001a370`
- `0x14001c300`

## callees

- `0x140001880`
- `0x140002754`
- `0x14000f284`
- `0x14001dbc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001935`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140001935`
- `ntoskrnl!KeSetEvent` at `0x1400019d9`
- `ntoskrnl!KeSetEvent` at `0x1400019d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001969`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001969`

## pseudocode

```c
void __fastcall MupReleaseIrpContext(char *P)
{
  char *v2; // rsi
  char *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, P);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids, P);
    }
    v2 = (char *)*((_QWORD *)P + 9);
    while ( v2 != P + 72 )
    {
      v3 = v2 - 8;
      v2 = *(char **)v2;
      MupReleaseSurrogateIrpContext(v3);
    }
    if ( *((_QWORD *)P + 6) )
    {
      MupDereferenceContainerContext();
      *((_QWORD *)P + 6) = 0;
      *((_QWORD *)P + 7) = 0;
    }
    if ( (*((_DWORD *)P + 2) & 2) != 0 )
    {
      qword_14000AB80 = 0;
      if ( _InterlockedAdd(&MupReserveIrpContext, 1u) <= 0 )
        KeSetEvent(&Event, 1, 0);
    }
    else if ( *((_WORD *)P + 51) )
    {
      ExFreeToNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)MupiIrpContextLookasideLists + (unsigned __int64)*((unsigned __int16 *)P + 51) - 1,
        P);
    }
    else
    {
      ExFreePoolWithTag(P, 0);
    }
  }
}

```

## disassembly

```asm
0x140001880  mov     [rsp+arg_8], rbx
0x140001885  push    rdi
0x140001886  sub     rsp, 20h
0x14000188a  mov     rbx, rcx
0x14000188d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001894  lea     rdi, WPP_GLOBAL_Control
0x14000189b  cmp     rcx, rdi
0x14000189e  jz      short loc_1400018AD
0x1400018a0  test    dword ptr [rcx+2Ch], 4000000h
0x1400018a7  jnz     loc_140001977
0x1400018ad  mov     eax, 0FFFFFFFFh
0x1400018b2  lock xadd [rbx+4], eax
0x1400018b7  cmp     eax, 1
0x1400018ba  jnz     loc_140001941
0x1400018c0  mov     [rsp+28h+arg_0], rsi
0x1400018c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018cc  cmp     rcx, rdi
0x1400018cf  jz      short loc_1400018DE
0x1400018d1  test    dword ptr [rcx+2Ch], 4000000h
0x1400018d8  jnz     loc_140001994
0x1400018de  mov     rsi, [rbx+48h]
0x1400018e2  lea     rdi, [rbx+48h]
0x1400018e6  cmp     rsi, rdi
0x1400018e9  jz      short loc_1400018FC
0x1400018eb  lea     rcx, [rsi-8]
0x1400018ef  mov     rsi, [rsi]
0x1400018f2  call    MupReleaseSurrogateIrpContext
0x1400018f7  cmp     rsi, rdi
0x1400018fa  jnz     short loc_1400018EB
0x1400018fc  mov     rcx, [rbx+30h]
0x140001900  mov     rsi, [rsp+28h+arg_0]
0x140001905  test    rcx, rcx
0x140001908  jnz     short loc_14000194D
0x14000190a  mov     eax, [rbx+8]
0x14000190d  test    al, 2
0x14000190f  jnz     loc_1400019B1
0x140001915  movzx   eax, word ptr [rbx+66h]
0x140001919  test    ax, ax
0x14000191c  jz      short loc_140001964
0x14000191e  mov     ecx, eax
0x140001920  mov     rdx, rbx; Entry
0x140001923  mov     rax, cs:MupiIrpContextLookasideLists
0x14000192a  add     rax, 0FFFFFFFFFFFFFF80h
0x14000192e  shl     rcx, 7
0x140001932  add     rcx, rax; Lookaside
0x140001935  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000193c  nop     dword ptr [rax+rax+00h]
0x140001941  mov     rbx, [rsp+28h+arg_8]
0x140001946  add     rsp, 20h
0x14000194a  pop     rdi
0x14000194b  retn
0x14000194d  call    MupDereferenceContainerContext
0x140001952  mov     qword ptr [rbx+30h], 0
0x14000195a  mov     qword ptr [rbx+38h], 0
0x140001962  jmp     short loc_14000190A
0x140001964  xor     edx, edx; Tag
0x140001966  mov     rcx, rbx; P
0x140001969  call    cs:__imp_ExFreePoolWithTag
0x140001970  nop     dword ptr [rax+rax+00h]
0x140001975  jmp     short loc_140001941
0x140001977  mov     rcx, [rcx+18h]
0x14000197b  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x140001982  mov     edx, 11h
0x140001987  mov     r9, rbx
0x14000198a  call    WPP_SF_q
0x14000198f  jmp     loc_1400018AD
0x140001994  mov     rcx, [rcx+18h]
0x140001998  lea     r8, WPP_4224fc6462d239efe09d540716e6c5d6_Traceguids
0x14000199f  mov     edx, 12h
0x1400019a4  mov     r9, rbx
0x1400019a7  call    WPP_SF_q
0x1400019ac  jmp     loc_1400018DE
0x1400019b1  mov     cs:qword_14000AB80, 0
0x1400019bc  lock add cs:MupReserveIrpContext, 1
0x1400019c4  jg      loc_140001941
0x1400019ca  xor     r8d, r8d; Wait
0x1400019cd  lea     rcx, Event; Event
0x1400019d4  mov     edx, 1; Increment
0x1400019d9  call    cs:__imp_KeSetEvent
0x1400019e0  nop     dword ptr [rax+rax+00h]
0x1400019e5  mov     rbx, [rsp+28h+arg_8]
0x1400019ea  add     rsp, 20h
0x1400019ee  pop     rdi
0x1400019ef  retn
```
