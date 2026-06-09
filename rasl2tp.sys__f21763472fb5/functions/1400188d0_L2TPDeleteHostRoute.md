# L2TPDeleteHostRoute

- ea: `0x1400188d0`
- end: `0x140018991`
- name: `L2TPDeleteHostRoute`
- size: `193`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140003050`
- `0x1400188d0`
- `0x14001c860`
- `0x14001f304`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018928`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140018928`

## pseudocode

```c
__int64 __fastcall L2TPDeleteHostRoute(PVOID Entry, __int64 a2)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a2 + 24) + 960LL), Entry);
  if ( (*(_DWORD *)(a2 + 120) & 4) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids);
    }
    DeleteHostRoute(a2 + 48);
  }
  return ClearFlags(a2 + 120, 16);
}

```

## disassembly

```asm
0x1400188d0  mov     [rsp+arg_0], rbx
0x1400188d5  mov     [rsp+arg_8], rbp
0x1400188da  push    rdi
0x1400188db  sub     rsp, 20h
0x1400188df  mov     rbx, rdx
0x1400188e2  mov     rdi, rcx
0x1400188e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188ec  lea     rbp, WPP_GLOBAL_Control
0x1400188f3  cmp     rcx, rbp
0x1400188f6  jz      short loc_14001891A
0x1400188f8  mov     eax, [rcx+2Ch]
0x1400188fb  test    al, 40h
0x1400188fd  jz      short loc_14001891A
0x1400188ff  cmp     byte ptr [rcx+29h], 4
0x140018903  jb      short loc_14001891A
0x140018905  mov     rcx, [rcx+18h]
0x140018909  lea     r8, WPP_9cb31f361fe3358cd45b783e7e5b98ac_Traceguids
0x140018910  mov     edx, 0Eh
0x140018915  call    WPP_SF_
0x14001891a  mov     rcx, [rbx+18h]
0x14001891e  mov     rdx, rdi; Entry
0x140018921  add     rcx, 3C0h; Lookaside
0x140018928  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001892f  nop     dword ptr [rax+rax+00h]
0x140018934  mov     eax, [rbx+78h]
0x140018937  test    al, 4
0x140018939  jnz     short loc_140018972
0x14001893b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018942  cmp     rcx, rbp
0x140018945  jz      short loc_140018969
0x140018947  mov     eax, [rcx+2Ch]
0x14001894a  test    al, 40h
0x14001894c  jz      short loc_140018969
0x14001894e  cmp     byte ptr [rcx+29h], 4
0x140018952  jb      short loc_140018969
0x140018954  mov     rcx, [rcx+18h]
0x140018958  lea     r8, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids
0x14001895f  mov     edx, 16h
0x140018964  call    WPP_SF_
0x140018969  lea     rcx, [rbx+30h]
0x14001896d  call    DeleteHostRoute
0x140018972  mov     edx, 10h
0x140018977  lea     rcx, [rbx+78h]
0x14001897b  call    ClearFlags
0x140018980  mov     rbx, [rsp+28h+arg_0]
0x140018985  mov     rbp, [rsp+28h+arg_8]
0x14001898a  add     rsp, 20h
0x14001898e  pop     rdi
0x14001898f  retn
```
