# TxfDeleteTxfVscb

- ea: `0x140188f30`
- end: `0x14018923d`
- name: `TxfDeleteTxfVscb`
- size: `781`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002c840`
- `0x140037200`
- `0x140187a00`
- `0x14018a0bc`
- `0x14018a28c`
- `0x14018a8a0`
- `0x1401d4f90`
- `0x1401e4170`

## callees

- `0x14005286c`
- `0x140188f30`
- `0x1401db21c`
- `0x14029b00c`

## import_xrefs

- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140189090`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140189090`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018900f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189059`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401890d0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018914a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018900f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189059`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401890d0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14018914a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401890ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018911e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401890ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018911e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401891e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402aae4e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401891e7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402aae4e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018902b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140189209`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aae90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018902b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140189209`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aae90`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140189178`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140189178`

## pseudocode

```c
void __fastcall TxfDeleteTxfVscb(char *Entry)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdx
  void *v14; // rdx
  void *v15; // rcx
  char *v16; // rdx
  char v17; // al
  struct _ERESOURCE *v18; // rcx

  v2 = 0;
  v3 = 0;
  v4 = 0;
  v5 = *((_QWORD *)Entry + 2);
  if ( v5 )
  {
    ++*(_DWORD *)(v5 + 28);
    v2 = *((_QWORD *)Entry + 2);
    v3 = *(_QWORD *)(v2 + 64);
    v4 = *(_QWORD *)(v3 + 40);
    v6 = *((_QWORD *)Entry + 5);
    if ( v6 )
    {
      *(_QWORD *)(v6 + 32) = 0;
    }
    else
    {
      *(_QWORD *)(v2 + 56) = 0;
      *(_DWORD *)(v2 + 40) = 0;
    }
    *((_QWORD *)Entry + 5) = 0;
    *((_QWORD *)Entry + 2) = 0;
  }
  v7 = *((_QWORD *)Entry + 13);
  if ( v7 )
  {
    --*(_WORD *)(v7 + 76);
    v8 = *((_QWORD *)Entry + 13);
    if ( !*(_WORD *)(v8 + 76) )
    {
      if ( !v2 )
      {
LABEL_11:
        v11 = (_QWORD *)*((_QWORD *)Entry + 13);
        v12 = *v11;
        if ( *(_QWORD **)(*v11 + 8LL) != v11 || (v13 = (_QWORD *)v11[1], (_QWORD *)*v13 != v11) )
          __fastfail(3u);
        *v13 = v12;
        *(_QWORD *)(v12 + 8) = v13;
        ExFreeToLookasideListEx(&TxfFcbInfoLookasideList, *((PVOID *)Entry + 13));
        goto LABEL_14;
      }
      v9 = *(_QWORD *)(v2 + 64);
      if ( !*(_QWORD *)(v9 + 24) || (*(_DWORD *)(v9 + 4) & 8) == 0 || *(_QWORD *)(v8 + 8) != v9 + 88 )
      {
        v10 = *(_QWORD *)(v2 + 64);
        if ( *(_QWORD *)(v8 + 8) == v10 + 88 )
          *(_DWORD *)(v10 + 4) &= ~8u;
        goto LABEL_11;
      }
    }
LABEL_14:
    *((_QWORD *)Entry + 13) = 0;
  }
  if ( v3 )
  {
    ExReleaseResourceLite(*(PERESOURCE *)(v3 + 136));
    v3 = 0;
  }
  if ( *((_QWORD *)Entry + 15) )
    TxfDetachBackupAttributeFromTxfVscb(Entry);
  v14 = (void *)*((_QWORD *)Entry + 3);
  if ( v14 )
  {
    ExFreeToLookasideListEx(&NtfsScbNonpagedLookasideList, v14);
    *((_QWORD *)Entry + 3) = 0;
  }
  v15 = (void *)*((_QWORD *)Entry + 18);
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0);
    *((_QWORD *)Entry + 18) = 0;
  }
  v16 = (char *)*((_QWORD *)Entry + 33);
  if ( v16 && v16 != Entry + 80 )
  {
    ExFreeToLookasideListEx(&TxfVscbFileSizesLookasideList, v16);
    *((_QWORD *)Entry + 33) = 0;
  }
  if ( (!RtlIsGenericTableEmptyAvl((PRTL_AVL_TABLE)(Entry + 152)) || *((_QWORD *)Entry + 36)) && v4 )
  {
    ExAcquireResourceSharedLite((PERESOURCE)(*(_QWORD *)(v4 + 24) + 1176LL), 1u);
    v17 = TxfFreeVersionInTopsStream(v4, v2, (__int64)Entry, 1, 0, 0);
    v18 = (struct _ERESOURCE *)(*(_QWORD *)(v4 + 24) + 1176LL);
    if ( v17 )
    {
      ExReleaseResourceLite(v18);
      goto LABEL_38;
    }
    ExReleaseResourceLite(v18);
  }
  ExFreePoolWithTag(*((PVOID *)Entry + 32), 0);
  ExFreeToLookasideListEx(&TxfVscbLookasideList, Entry);
LABEL_38:
  if ( v2 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(v2 + 64) + 136LL), 1u);
    v3 = *(_QWORD *)(v2 + 64);
    if ( (*(_DWORD *)(v2 + 28))-- == 1 && !*(_QWORD *)(v2 + 56) )
    {
      v3 = 0;
      TxfDeleteTxfScb((PVOID)v2);
    }
  }
  if ( v3 )
    ExReleaseResourceLite(*(PERESOURCE *)(v3 + 136));
}

```

## disassembly

```asm
0x140188f30  mov     r11, rsp
0x140188f33  mov     [r11+8], rbx
0x140188f37  mov     [r11+18h], rsi
0x140188f3b  push    rdi
0x140188f3c  push    r14
0x140188f3e  push    r15
0x140188f40  sub     rsp, 40h
0x140188f44  mov     rbx, rcx
0x140188f47  xor     r15d, r15d
0x140188f4a  mov     edi, r15d
0x140188f4d  mov     [r11-20h], r15
0x140188f51  mov     esi, r15d
0x140188f54  mov     [r11-28h], r15
0x140188f58  mov     r14d, r15d
0x140188f5b  mov     rax, [rcx+10h]
0x140188f5f  test    rax, rax
0x140188f62  jz      short loc_140188F98
0x140188f64  inc     dword ptr [rax+1Ch]
0x140188f67  mov     rdi, [rcx+10h]
0x140188f6b  mov     [r11-20h], rdi
0x140188f6f  mov     rsi, [rdi+40h]
0x140188f73  mov     [r11-28h], rsi
0x140188f77  mov     r14, [rsi+28h]
0x140188f7b  mov     rax, [rcx+28h]
0x140188f7f  test    rax, rax
0x140188f82  jnz     loc_1401890E8
0x140188f88  mov     [rdi+38h], r15
0x140188f8c  mov     [rdi+28h], r15d
0x140188f90  mov     [rcx+28h], r15
0x140188f94  mov     [rcx+10h], r15
0x140188f98  mov     rax, [rcx+68h]
0x140188f9c  test    rax, rax
0x140188f9f  jz      short loc_14018901F
0x140188fa1  mov     ecx, 0FFFFh
0x140188fa6  add     [rax+4Ch], cx
0x140188faa  mov     rdx, [rbx+68h]
0x140188fae  cmp     [rdx+4Ch], r15w
0x140188fb3  jnz     short loc_14018901B
0x140188fb5  test    rdi, rdi
0x140188fb8  jz      short loc_140188FDF
0x140188fba  mov     rcx, [rdi+40h]
0x140188fbe  cmp     [rcx+18h], r15
0x140188fc2  jnz     loc_1401890F1
0x140188fc8  test    rdi, rdi
0x140188fcb  jz      short loc_140188FDF
0x140188fcd  mov     rcx, [rdi+40h]
0x140188fd1  lea     rax, [rcx+58h]
0x140188fd5  cmp     [rdx+8], rax
0x140188fd9  jnz     short loc_140188FDF
0x140188fdb  and     dword ptr [rcx+4], 0FFFFFFF7h
0x140188fdf  mov     rax, [rbx+68h]
0x140188fe3  mov     rcx, [rax]
0x140188fe6  cmp     [rcx+8], rax
0x140188fea  jnz     loc_1401890E1
0x140188ff0  mov     rdx, [rax+8]
0x140188ff4  cmp     [rdx], rax
0x140188ff7  jnz     loc_1401890E1
0x140188ffd  mov     [rdx], rcx
0x140189000  mov     [rcx+8], rdx
0x140189004  mov     rdx, [rbx+68h]; Entry
0x140189008  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x14018900f  call    cs:__imp_ExFreeToLookasideListEx
0x140189016  nop     dword ptr [rax+rax+00h]
0x14018901b  mov     [rbx+68h], r15
0x14018901f  test    rsi, rsi
0x140189022  jz      short loc_14018903F
0x140189024  mov     rcx, [rsi+88h]; Resource
0x14018902b  call    cs:__imp_ExReleaseResourceLite
0x140189032  nop     dword ptr [rax+rax+00h]
0x140189037  mov     rsi, r15
0x14018903a  mov     [rsp+58h+var_28], r15
0x14018903f  cmp     [rbx+78h], r15
0x140189043  jnz     loc_14018910F
0x140189049  mov     rdx, [rbx+18h]; Entry
0x14018904d  test    rdx, rdx
0x140189050  jz      short loc_140189069
0x140189052  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140189059  call    cs:__imp_ExFreeToLookasideListEx
0x140189060  nop     dword ptr [rax+rax+00h]
0x140189065  mov     [rbx+18h], r15
0x140189069  mov     rcx, [rbx+90h]; P
0x140189070  test    rcx, rcx
0x140189073  jnz     loc_14018911C
0x140189079  mov     rdx, [rbx+108h]; Entry
0x140189080  test    rdx, rdx
0x140189083  jnz     loc_140189136
0x140189089  lea     rcx, [rbx+98h]; Table
0x140189090  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140189097  nop     dword ptr [rax+rax+00h]
0x14018909c  test    al, al
0x14018909e  jz      loc_140189162
0x1401890a4  cmp     [rbx+120h], r15
0x1401890ab  jnz     loc_140189162
0x1401890b1  xor     edx, edx; Tag
0x1401890b3  mov     rcx, [rbx+100h]; P
0x1401890ba  call    cs:__imp_ExFreePoolWithTag
0x1401890c1  nop     dword ptr [rax+rax+00h]
0x1401890c6  mov     rdx, rbx; Entry
0x1401890c9  lea     rcx, TxfVscbLookasideList; Lookaside
0x1401890d0  call    cs:__imp_ExFreeToLookasideListEx
0x1401890d7  nop     dword ptr [rax+rax+00h]
0x1401890dc  jmp     loc_1401891D0
0x1401890e1  mov     ecx, 3
0x1401890e6  int     29h; Win8: RtlFailFast(ecx)
0x1401890e8  mov     [rax+20h], r15
0x1401890ec  jmp     loc_140188F90
0x1401890f1  mov     eax, [rcx+4]
0x1401890f4  test    al, 8
0x1401890f6  jz      loc_140188FC8
0x1401890fc  lea     rax, [rcx+58h]
0x140189100  cmp     [rdx+8], rax
0x140189104  jz      loc_14018901B
0x14018910a  jmp     loc_140188FC8
0x14018910f  mov     rcx, rbx
0x140189112  call    TxfDetachBackupAttributeFromTxfVscb
0x140189117  jmp     loc_140189049
0x14018911c  xor     edx, edx; Tag
0x14018911e  call    cs:__imp_ExFreePoolWithTag
0x140189125  nop     dword ptr [rax+rax+00h]
0x14018912a  mov     [rbx+90h], r15
0x140189131  jmp     loc_140189079
0x140189136  lea     rax, [rbx+50h]
0x14018913a  cmp     rdx, rax
0x14018913d  jz      loc_140189089
0x140189143  lea     rcx, TxfVscbFileSizesLookasideList; Lookaside
0x14018914a  call    cs:__imp_ExFreeToLookasideListEx
0x140189151  nop     dword ptr [rax+rax+00h]
0x140189156  mov     [rbx+108h], r15
0x14018915d  jmp     loc_140189089
0x140189162  test    r14, r14
0x140189165  jz      loc_1401890B1
0x14018916b  mov     rcx, [r14+18h]
0x14018916f  add     rcx, 498h; Resource
0x140189176  mov     dl, 1; Wait
0x140189178  call    cs:__imp_ExAcquireResourceSharedLite
0x14018917f  nop     dword ptr [rax+rax+00h]
0x140189184  mov     [rsp+58h+var_30], r15b
0x140189189  mov     [rsp+58h+var_38], r15b
0x14018918e  mov     r9d, 1
0x140189194  mov     r8, rbx
0x140189197  mov     rdx, rdi
0x14018919a  mov     rcx, r14
0x14018919d  call    TxfFreeVersionInTopsStream
0x1401891a2  mov     rcx, [r14+18h]
0x1401891a6  add     rcx, 498h; Resource
0x1401891ad  test    al, al
0x1401891af  jz      short loc_1401891BF
0x1401891b1  call    cs:__imp_ExReleaseResourceLite
0x1401891b8  nop     dword ptr [rax+rax+00h]
0x1401891bd  jmp     short loc_1401891D0
0x1401891bf  call    cs:__imp_ExReleaseResourceLite
0x1401891c6  nop     dword ptr [rax+rax+00h]
0x1401891cb  jmp     loc_1401890B1
0x1401891d0  test    rdi, rdi
0x1401891d3  jz      short loc_1401891FD
0x1401891d5  test    rsi, rsi
0x1401891d8  jnz     short loc_1401891F7
0x1401891da  mov     rcx, [rdi+40h]
0x1401891de  mov     dl, 1; Wait
0x1401891e0  mov     rcx, [rcx+88h]; Resource
0x1401891e7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1401891ee  nop     dword ptr [rax+rax+00h]
0x1401891f3  mov     rsi, [rdi+40h]
0x1401891f7  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1401891fb  jz      short loc_14018922A
0x1401891fd  test    rsi, rsi
0x140189200  jz      short loc_140189215
0x140189202  mov     rcx, [rsi+88h]; Resource
0x140189209  call    cs:__imp_ExReleaseResourceLite
0x140189210  nop     dword ptr [rax+rax+00h]
0x140189215  mov     rbx, [rsp+58h+arg_0]
0x14018921a  mov     rsi, [rsp+58h+arg_10]
0x14018921f  add     rsp, 40h
0x140189223  pop     r15
0x140189225  pop     r14
0x140189227  pop     rdi
0x140189228  retn
0x14018922a  cmp     [rdi+38h], r15
0x14018922e  jnz     short loc_1401891FD
0x140189230  mov     rsi, r15
0x140189233  mov     rcx, rdi; P
0x140189236  call    TxfDeleteTxfScb
0x14018923b  jmp     short loc_1401891FD
0x1402aae1d  push    rbx
0x1402aae1f  push    rbp
0x1402aae20  sub     rsp, 38h
0x1402aae24  mov     rbp, rdx
0x1402aae27  test    cl, cl
0x1402aae29  jz      short loc_1402AAE31
0x1402aae2b  mov     al, cs:NtfsStatusDebugFlags
0x1402aae31  mov     rbx, [rbp+38h]
0x1402aae35  test    rbx, rbx
0x1402aae38  jz      short loc_1402AAE80
0x1402aae3a  cmp     qword ptr [rbp+30h], 0
0x1402aae3f  jnz     short loc_1402AAE62
0x1402aae41  mov     rcx, [rbx+40h]
0x1402aae45  mov     dl, 1; Wait
0x1402aae47  mov     rcx, [rcx+88h]; Resource
0x1402aae4e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402aae55  nop     dword ptr [rax+rax+00h]
0x1402aae5a  mov     rax, [rbx+40h]
0x1402aae5e  mov     [rbp+30h], rax
0x1402aae62  sub     dword ptr [rbx+1Ch], 1
0x1402aae66  jnz     short loc_1402AAE80
0x1402aae68  cmp     qword ptr [rbx+38h], 0
0x1402aae6d  jnz     short loc_1402AAE80
0x1402aae6f  mov     qword ptr [rbp+30h], 0
0x1402aae77  mov     rcx, rbx; P
0x1402aae7a  call    TxfDeleteTxfScb
0x1402aae7f  nop
0x1402aae80  mov     rcx, [rbp+30h]
0x1402aae84  test    rcx, rcx
0x1402aae87  jz      short loc_1402AAE9D
0x1402aae89  mov     rcx, [rcx+88h]; Resource
0x1402aae90  call    cs:__imp_ExReleaseResourceLite
0x1402aae97  nop     dword ptr [rax+rax+00h]
0x1402aae9c  nop
0x1402aae9d  add     rsp, 38h
0x1402aaea1  pop     rbp
0x1402aaea2  pop     rbx
0x1402aaea3  retn
```
