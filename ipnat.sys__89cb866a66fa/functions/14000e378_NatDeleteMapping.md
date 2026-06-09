# NatDeleteMapping

- ea: `0x14000e378`
- end: `0x14000e593`
- name: `NatDeleteMapping`
- size: `539`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140001710`
- `0x140017168`
- `0x14001a0f0`
- `0x14001a4c0`
- `0x14001eeb0`
- `0x14001f110`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000d66c`
- `0x14000e378`
- `0x140010404`

## import_xrefs

- `ntoskrnl!RtlDelete` at `0x14000e470`
- `ntoskrnl!RtlDelete` at `0x14000e494`
- `ntoskrnl!RtlDelete` at `0x14000e470`
- `ntoskrnl!RtlDelete` at `0x14000e494`

## pseudocode

```c
__int64 __fastcall NatDeleteMapping(char *Entry)
{
  int v2; // eax
  PDEVICE_OBJECT v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  PVOID *v6; // rax
  PRTL_SPLAY_LINKS v7; // rax
  PRTL_SPLAY_LINKS v8; // rax
  int v9; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  v2 = *((_DWORD *)Entry + 60);
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return 259;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 259;
    }
    v4 = 22;
    goto LABEL_27;
  }
  *((_DWORD *)Entry + 60) = v2 | 0x80000000;
  _InterlockedDecrement(&MappingCount);
  v5 = *(_QWORD **)Entry;
  if ( *(char **)(*(_QWORD *)Entry + 8LL) != Entry || (v6 = (PVOID *)*((_QWORD *)Entry + 1), *v6 != Entry) )
    __fastfail(3u);
  *v6 = v5;
  v5[1] = v6;
  if ( (*((_DWORD *)Entry + 60) & 1) != 0 )
    _InterlockedDecrement(&ExpiredMappingCount);
  v7 = RtlDelete((PRTL_SPLAY_LINKS)(Entry + 16));
  *(_QWORD *)&MappingTree = (unsigned __int64)&v7[-1].LeftChild & -(__int64)(v7 != 0);
  v8 = RtlDelete((PRTL_SPLAY_LINKS)(Entry + 40));
  *((_QWORD *)&MappingTree + 1) = (unsigned __int64)&v8[-2].LeftChild & -(__int64)(v8 != 0);
  v9 = *((_DWORD *)Entry + 60);
  if ( (v9 & 0x400) == 0 )
  {
    if ( (v9 & 0x20) != 0 )
      NatLogConnectionDeletion(
        *((_DWORD *)Entry + 16),
        *((unsigned int *)Entry + 20),
        *((unsigned __int16 *)Entry + 34),
        *((_WORD *)Entry + 42),
        Entry[86],
        1);
    else
      NatLogConnectionDeletion(
        *((_DWORD *)Entry + 18),
        *((unsigned int *)Entry + 22),
        *((unsigned __int16 *)Entry + 38),
        *((_WORD *)Entry + 46),
        Entry[70],
        0);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 28, 0xFFFFFFFF) > 1 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 259;
    }
    v4 = 23;
LABEL_27:
    WPP_SF_d(v3->AttachedDevice, v4, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, 259);
    return 259;
  }
  NatCleanupMapping(Entry);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e378  mov     [rsp+arg_0], rbx
0x14000e37d  mov     [rsp+arg_8], rbp
0x14000e382  push    rsi
0x14000e383  sub     rsp, 30h
0x14000e387  mov     rbx, rcx
0x14000e38a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e391  lea     rsi, WPP_GLOBAL_Control
0x14000e398  lea     rbp, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000e39f  cmp     rcx, rsi
0x14000e3a2  jz      short loc_14000E3C2
0x14000e3a4  mov     eax, [rcx+2Ch]
0x14000e3a7  test    al, 1
0x14000e3a9  jz      short loc_14000E3C2
0x14000e3ab  cmp     byte ptr [rcx+29h], 6
0x14000e3af  jb      short loc_14000E3C2
0x14000e3b1  mov     rcx, [rcx+18h]
0x14000e3b5  mov     edx, 14h
0x14000e3ba  mov     r8, rbp
0x14000e3bd  call    WPP_SF_
0x14000e3c2  mov     eax, [rbx+0F0h]
0x14000e3c8  test    eax, eax
0x14000e3ca  jns     short loc_14000E429
0x14000e3cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3d3  cmp     rcx, rsi
0x14000e3d6  jz      loc_14000E53D
0x14000e3dc  mov     eax, [rcx+2Ch]
0x14000e3df  test    al, 1
0x14000e3e1  jz      short loc_14000E3FA
0x14000e3e3  cmp     byte ptr [rcx+29h], 2
0x14000e3e7  jb      short loc_14000E3FA
0x14000e3e9  mov     rcx, [rcx+18h]
0x14000e3ed  mov     edx, 15h
0x14000e3f2  mov     r8, rbp
0x14000e3f5  call    WPP_SF_
0x14000e3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e401  cmp     rcx, rsi
0x14000e404  jz      loc_14000E53D
0x14000e40a  mov     eax, [rcx+2Ch]
0x14000e40d  test    al, 1
0x14000e40f  jz      loc_14000E53D
0x14000e415  cmp     byte ptr [rcx+29h], 6
0x14000e419  jb      loc_14000E53D
0x14000e41f  mov     edx, 16h
0x14000e424  jmp     loc_14000E52B
0x14000e429  bts     eax, 1Fh
0x14000e42d  mov     [rbx+0F0h], eax
0x14000e433  lock dec cs:MappingCount
0x14000e43a  mov     rcx, [rbx]
0x14000e43d  cmp     [rcx+8], rbx
0x14000e441  jnz     loc_14000E58C
0x14000e447  mov     rax, [rbx+8]
0x14000e44b  cmp     [rax], rbx
0x14000e44e  jnz     loc_14000E58C
0x14000e454  mov     [rax], rcx
0x14000e457  mov     [rcx+8], rax
0x14000e45b  mov     eax, [rbx+0F0h]
0x14000e461  test    al, 1
0x14000e463  jz      short loc_14000E46C
0x14000e465  lock dec cs:ExpiredMappingCount
0x14000e46c  lea     rcx, [rbx+10h]; Links
0x14000e470  call    cs:__imp_RtlDelete
0x14000e477  nop     dword ptr [rax+rax+00h]
0x14000e47c  lea     rcx, [rax-10h]
0x14000e480  neg     rax
0x14000e483  sbb     rax, rax
0x14000e486  and     rax, rcx
0x14000e489  lea     rcx, [rbx+28h]; Links
0x14000e48d  mov     qword ptr cs:MappingTree, rax
0x14000e494  call    cs:__imp_RtlDelete
0x14000e49b  nop     dword ptr [rax+rax+00h]
0x14000e4a0  lea     rcx, [rax-28h]
0x14000e4a4  neg     rax
0x14000e4a7  sbb     rax, rax
0x14000e4aa  and     rax, rcx
0x14000e4ad  mov     qword ptr cs:MappingTree+8, rax
0x14000e4b4  mov     eax, [rbx+0F0h]
0x14000e4ba  bt      eax, 0Ah
0x14000e4be  jb      short loc_14000E4FF
0x14000e4c0  test    al, 20h
0x14000e4c2  jz      short loc_14000E4DE
0x14000e4c4  mov     al, [rbx+56h]
0x14000e4c7  movzx   r9d, word ptr [rbx+54h]
0x14000e4cc  movzx   r8d, word ptr [rbx+44h]
0x14000e4d1  mov     edx, [rbx+50h]
0x14000e4d4  mov     ecx, [rbx+40h]
0x14000e4d7  mov     [rsp+38h+var_10], 1
0x14000e4dc  jmp     short loc_14000E4F6
0x14000e4de  mov     al, [rbx+46h]
0x14000e4e1  movzx   r9d, word ptr [rbx+5Ch]
0x14000e4e6  movzx   r8d, word ptr [rbx+4Ch]
0x14000e4eb  mov     edx, [rbx+58h]
0x14000e4ee  mov     ecx, [rbx+48h]
0x14000e4f1  mov     [rsp+38h+var_10], 0
0x14000e4f6  mov     [rsp+38h+var_18], al
0x14000e4fa  call    NatLogConnectionDeletion
0x14000e4ff  or      eax, 0FFFFFFFFh
0x14000e502  lock xadd [rbx+70h], eax
0x14000e507  sub     eax, 1
0x14000e50a  jle     short loc_14000E553
0x14000e50c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e513  cmp     rcx, rsi
0x14000e516  jz      short loc_14000E53D
0x14000e518  mov     edx, [rcx+2Ch]
0x14000e51b  test    dl, 1
0x14000e51e  jz      short loc_14000E53D
0x14000e520  cmp     byte ptr [rcx+29h], 6
0x14000e524  jb      short loc_14000E53D
0x14000e526  mov     edx, 17h
0x14000e52b  mov     rcx, [rcx+18h]
0x14000e52f  mov     r9d, 103h
0x14000e535  mov     r8, rbp
0x14000e538  call    WPP_SF_d
0x14000e53d  mov     eax, 103h
0x14000e542  mov     rbx, [rsp+38h+arg_0]
0x14000e547  mov     rbp, [rsp+38h+arg_8]
0x14000e54c  add     rsp, 30h
0x14000e550  pop     rsi
0x14000e551  retn
0x14000e553  mov     rcx, rbx; Entry
0x14000e556  call    NatCleanupMapping
0x14000e55b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e562  cmp     rcx, rsi
0x14000e565  jz      short loc_14000E588
0x14000e567  mov     eax, [rcx+2Ch]
0x14000e56a  test    al, 1
0x14000e56c  jz      short loc_14000E588
0x14000e56e  cmp     byte ptr [rcx+29h], 6
0x14000e572  jb      short loc_14000E588
0x14000e574  mov     rcx, [rcx+18h]
0x14000e578  mov     edx, 18h
0x14000e57d  xor     r9d, r9d
0x14000e580  mov     r8, rbp
0x14000e583  call    WPP_SF_d
0x14000e588  xor     eax, eax
0x14000e58a  jmp     short loc_14000E542
0x14000e58c  mov     ecx, 3
0x14000e591  int     29h; Win8: RtlFailFast(ecx)
```
