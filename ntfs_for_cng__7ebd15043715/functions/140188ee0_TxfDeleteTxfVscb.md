# TxfDeleteTxfVscb

- ea: `0x140188ee0`
- end: `0x1401891ed`
- name: `TxfDeleteTxfVscb`
- size: `781`
- prototype: `void __fastcall(char *Entry)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002c840`
- `0x140037200`
- `0x1401879b0`
- `0x14018a06c`
- `0x14018a23c`
- `0x14018a850`
- `0x1401d4f40`
- `0x1401e4120`

## callees

- `0x1400527fc`
- `0x140188ee0`
- `0x1401db1cc`
- `0x14029afbc`

## import_xrefs

- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140189040`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x140189040`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140188fbf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189009`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189080`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401890fa`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140188fbf`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189009`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140189080`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401890fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018906a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401890ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018906a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401890ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140189197`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402aadfe`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140189197`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402aadfe`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188fdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140189161`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018916f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aae40`
- `ntoskrnl!ExReleaseResourceLite` at `0x140188fdb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140189161`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018916f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401891b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402aae40`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140189128`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140189128`

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
  __int64 v20; // [rsp+30h] [rbp-28h]
  __int64 v21; // [rsp+38h] [rbp-20h]

  v2 = 0;
  v21 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  v5 = *((_QWORD *)Entry + 2);
  if ( v5 )
  {
    ++*(_DWORD *)(v5 + 28);
    v2 = *((_QWORD *)Entry + 2);
    v21 = v2;
    v3 = *(_QWORD *)(v2 + 64);
    v20 = v3;
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
    v20 = 0;
  }
  if ( *((_QWORD *)Entry + 15) )
    TxfDetachBackupAttributeFromTxfVscb((__int64 *)Entry);
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
    v17 = TxfFreeVersionInTopsStream(v4, v2, (_DWORD)Entry, 1, 0, 0, v20, v21);
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
0x140188ee0  mov     r11, rsp
0x140188ee3  mov     [r11+8], rbx
0x140188ee7  mov     [r11+18h], rsi
0x140188eeb  push    rdi
0x140188eec  push    r14
0x140188eee  push    r15
0x140188ef0  sub     rsp, 40h
0x140188ef4  mov     rbx, rcx
0x140188ef7  xor     r15d, r15d
0x140188efa  mov     edi, r15d
0x140188efd  mov     [r11-20h], r15
0x140188f01  mov     esi, r15d
0x140188f04  mov     [r11-28h], r15
0x140188f08  mov     r14d, r15d
0x140188f0b  mov     rax, [rcx+10h]
0x140188f0f  test    rax, rax
0x140188f12  jz      short loc_140188F48
0x140188f14  inc     dword ptr [rax+1Ch]
0x140188f17  mov     rdi, [rcx+10h]
0x140188f1b  mov     [r11-20h], rdi
0x140188f1f  mov     rsi, [rdi+40h]
0x140188f23  mov     [r11-28h], rsi
0x140188f27  mov     r14, [rsi+28h]
0x140188f2b  mov     rax, [rcx+28h]
0x140188f2f  test    rax, rax
0x140188f32  jnz     loc_140189098
0x140188f38  mov     [rdi+38h], r15
0x140188f3c  mov     [rdi+28h], r15d
0x140188f40  mov     [rcx+28h], r15
0x140188f44  mov     [rcx+10h], r15
0x140188f48  mov     rax, [rcx+68h]
0x140188f4c  test    rax, rax
0x140188f4f  jz      short loc_140188FCF
0x140188f51  mov     ecx, 0FFFFh
0x140188f56  add     [rax+4Ch], cx
0x140188f5a  mov     rdx, [rbx+68h]
0x140188f5e  cmp     [rdx+4Ch], r15w
0x140188f63  jnz     short loc_140188FCB
0x140188f65  test    rdi, rdi
0x140188f68  jz      short loc_140188F8F
0x140188f6a  mov     rcx, [rdi+40h]
0x140188f6e  cmp     [rcx+18h], r15
0x140188f72  jnz     loc_1401890A1
0x140188f78  test    rdi, rdi
0x140188f7b  jz      short loc_140188F8F
0x140188f7d  mov     rcx, [rdi+40h]
0x140188f81  lea     rax, [rcx+58h]
0x140188f85  cmp     [rdx+8], rax
0x140188f89  jnz     short loc_140188F8F
0x140188f8b  and     dword ptr [rcx+4], 0FFFFFFF7h
0x140188f8f  mov     rax, [rbx+68h]
0x140188f93  mov     rcx, [rax]
0x140188f96  cmp     [rcx+8], rax
0x140188f9a  jnz     loc_140189091
0x140188fa0  mov     rdx, [rax+8]
0x140188fa4  cmp     [rdx], rax
0x140188fa7  jnz     loc_140189091
0x140188fad  mov     [rdx], rcx
0x140188fb0  mov     [rcx+8], rdx
0x140188fb4  mov     rdx, [rbx+68h]; Entry
0x140188fb8  lea     rcx, TxfFcbInfoLookasideList; Lookaside
0x140188fbf  call    cs:__imp_ExFreeToLookasideListEx
0x140188fc6  nop     dword ptr [rax+rax+00h]
0x140188fcb  mov     [rbx+68h], r15
0x140188fcf  test    rsi, rsi
0x140188fd2  jz      short loc_140188FEF
0x140188fd4  mov     rcx, [rsi+88h]; Resource
0x140188fdb  call    cs:__imp_ExReleaseResourceLite
0x140188fe2  nop     dword ptr [rax+rax+00h]
0x140188fe7  mov     rsi, r15
0x140188fea  mov     [rsp+58h+var_28], r15
0x140188fef  cmp     [rbx+78h], r15
0x140188ff3  jnz     loc_1401890BF
0x140188ff9  mov     rdx, [rbx+18h]; Entry
0x140188ffd  test    rdx, rdx
0x140189000  jz      short loc_140189019
0x140189002  lea     rcx, NtfsScbNonpagedLookasideList; Lookaside
0x140189009  call    cs:__imp_ExFreeToLookasideListEx
0x140189010  nop     dword ptr [rax+rax+00h]
0x140189015  mov     [rbx+18h], r15
0x140189019  mov     rcx, [rbx+90h]; P
0x140189020  test    rcx, rcx
0x140189023  jnz     loc_1401890CC
0x140189029  mov     rdx, [rbx+108h]; Entry
0x140189030  test    rdx, rdx
0x140189033  jnz     loc_1401890E6
0x140189039  lea     rcx, [rbx+98h]; Table
0x140189040  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140189047  nop     dword ptr [rax+rax+00h]
0x14018904c  test    al, al
0x14018904e  jz      loc_140189112
0x140189054  cmp     [rbx+120h], r15
0x14018905b  jnz     loc_140189112
0x140189061  xor     edx, edx; Tag
0x140189063  mov     rcx, [rbx+100h]; P
0x14018906a  call    cs:__imp_ExFreePoolWithTag
0x140189071  nop     dword ptr [rax+rax+00h]
0x140189076  mov     rdx, rbx; Entry
0x140189079  lea     rcx, TxfVscbLookasideList; Lookaside
0x140189080  call    cs:__imp_ExFreeToLookasideListEx
0x140189087  nop     dword ptr [rax+rax+00h]
0x14018908c  jmp     loc_140189180
0x140189091  mov     ecx, 3
0x140189096  int     29h; Win8: RtlFailFast(ecx)
0x140189098  mov     [rax+20h], r15
0x14018909c  jmp     loc_140188F40
0x1401890a1  mov     eax, [rcx+4]
0x1401890a4  test    al, 8
0x1401890a6  jz      loc_140188F78
0x1401890ac  lea     rax, [rcx+58h]
0x1401890b0  cmp     [rdx+8], rax
0x1401890b4  jz      loc_140188FCB
0x1401890ba  jmp     loc_140188F78
0x1401890bf  mov     rcx, rbx
0x1401890c2  call    TxfDetachBackupAttributeFromTxfVscb
0x1401890c7  jmp     loc_140188FF9
0x1401890cc  xor     edx, edx; Tag
0x1401890ce  call    cs:__imp_ExFreePoolWithTag
0x1401890d5  nop     dword ptr [rax+rax+00h]
0x1401890da  mov     [rbx+90h], r15
0x1401890e1  jmp     loc_140189029
0x1401890e6  lea     rax, [rbx+50h]
0x1401890ea  cmp     rdx, rax
0x1401890ed  jz      loc_140189039
0x1401890f3  lea     rcx, TxfVscbFileSizesLookasideList; Lookaside
0x1401890fa  call    cs:__imp_ExFreeToLookasideListEx
0x140189101  nop     dword ptr [rax+rax+00h]
0x140189106  mov     [rbx+108h], r15
0x14018910d  jmp     loc_140189039
0x140189112  test    r14, r14
0x140189115  jz      loc_140189061
0x14018911b  mov     rcx, [r14+18h]
0x14018911f  add     rcx, 498h; Resource
0x140189126  mov     dl, 1; Wait
0x140189128  call    cs:__imp_ExAcquireResourceSharedLite
0x14018912f  nop     dword ptr [rax+rax+00h]
0x140189134  mov     [rsp+58h+var_30], r15b
0x140189139  mov     [rsp+58h+var_38], r15b
0x14018913e  mov     r9d, 1
0x140189144  mov     r8, rbx
0x140189147  mov     rdx, rdi
0x14018914a  mov     rcx, r14
0x14018914d  call    TxfFreeVersionInTopsStream
0x140189152  mov     rcx, [r14+18h]
0x140189156  add     rcx, 498h; Resource
0x14018915d  test    al, al
0x14018915f  jz      short loc_14018916F
0x140189161  call    cs:__imp_ExReleaseResourceLite
0x140189168  nop     dword ptr [rax+rax+00h]
0x14018916d  jmp     short loc_140189180
0x14018916f  call    cs:__imp_ExReleaseResourceLite
0x140189176  nop     dword ptr [rax+rax+00h]
0x14018917b  jmp     loc_140189061
0x140189180  test    rdi, rdi
0x140189183  jz      short loc_1401891AD
0x140189185  test    rsi, rsi
0x140189188  jnz     short loc_1401891A7
0x14018918a  mov     rcx, [rdi+40h]
0x14018918e  mov     dl, 1; Wait
0x140189190  mov     rcx, [rcx+88h]; Resource
0x140189197  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018919e  nop     dword ptr [rax+rax+00h]
0x1401891a3  mov     rsi, [rdi+40h]
0x1401891a7  add     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1401891ab  jz      short loc_1401891DA
0x1401891ad  test    rsi, rsi
0x1401891b0  jz      short loc_1401891C5
0x1401891b2  mov     rcx, [rsi+88h]; Resource
0x1401891b9  call    cs:__imp_ExReleaseResourceLite
0x1401891c0  nop     dword ptr [rax+rax+00h]
0x1401891c5  mov     rbx, [rsp+58h+arg_0]
0x1401891ca  mov     rsi, [rsp+58h+arg_10]
0x1401891cf  add     rsp, 40h
0x1401891d3  pop     r15
0x1401891d5  pop     r14
0x1401891d7  pop     rdi
0x1401891d8  retn
0x1401891da  cmp     [rdi+38h], r15
0x1401891de  jnz     short loc_1401891AD
0x1401891e0  mov     rsi, r15
0x1401891e3  mov     rcx, rdi; P
0x1401891e6  call    TxfDeleteTxfScb
0x1401891eb  jmp     short loc_1401891AD
0x1402aadcd  push    rbx
0x1402aadcf  push    rbp
0x1402aadd0  sub     rsp, 38h
0x1402aadd4  mov     rbp, rdx
0x1402aadd7  test    cl, cl
0x1402aadd9  jz      short loc_1402AADE1
0x1402aaddb  mov     al, cs:NtfsStatusDebugFlags
0x1402aade1  mov     rbx, [rbp+38h]
0x1402aade5  test    rbx, rbx
0x1402aade8  jz      short loc_1402AAE30
0x1402aadea  cmp     qword ptr [rbp+30h], 0
0x1402aadef  jnz     short loc_1402AAE12
0x1402aadf1  mov     rcx, [rbx+40h]
0x1402aadf5  mov     dl, 1; Wait
0x1402aadf7  mov     rcx, [rcx+88h]; Resource
0x1402aadfe  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402aae05  nop     dword ptr [rax+rax+00h]
0x1402aae0a  mov     rax, [rbx+40h]
0x1402aae0e  mov     [rbp+30h], rax
0x1402aae12  sub     dword ptr [rbx+1Ch], 1
0x1402aae16  jnz     short loc_1402AAE30
0x1402aae18  cmp     qword ptr [rbx+38h], 0
0x1402aae1d  jnz     short loc_1402AAE30
0x1402aae1f  mov     qword ptr [rbp+30h], 0
0x1402aae27  mov     rcx, rbx; P
0x1402aae2a  call    TxfDeleteTxfScb
0x1402aae2f  nop
0x1402aae30  mov     rcx, [rbp+30h]
0x1402aae34  test    rcx, rcx
0x1402aae37  jz      short loc_1402AAE4D
0x1402aae39  mov     rcx, [rcx+88h]; Resource
0x1402aae40  call    cs:__imp_ExReleaseResourceLite
0x1402aae47  nop     dword ptr [rax+rax+00h]
0x1402aae4c  nop
0x1402aae4d  add     rsp, 38h
0x1402aae51  pop     rbp
0x1402aae52  pop     rbx
0x1402aae53  retn
```
