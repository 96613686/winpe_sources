# NpCreateFcb

- ea: `0x140015878`
- end: `0x140015b33`
- name: `NpCreateFcb`
- size: `699`
- prototype: `__int64 __fastcall(struct _UNICODE_PREFIX_TABLE *, __int64, unsigned __int16 *, int, __int64, __int16, int, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001399c`

## callees

- `0x140001f40`
- `0x140002240`
- `0x140015878`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400158db`
- `ntoskrnl!ExAllocatePool2` at `0x140015946`
- `ntoskrnl!ExAllocatePool2` at `0x140015a33`
- `ntoskrnl!ExAllocatePool2` at `0x1400158db`
- `ntoskrnl!ExAllocatePool2` at `0x140015946`
- `ntoskrnl!ExAllocatePool2` at `0x140015a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ada`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ac9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ada`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140015a85`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x140015a85`
- `ntoskrnl!KeInitializeEvent` at `0x14001597a`
- `ntoskrnl!KeInitializeEvent` at `0x14001597a`

## pseudocode

```c
__int64 __fastcall NpCreateFcb(
        struct _UNICODE_PREFIX_TABLE *a1,
        __int64 a2,
        unsigned __int16 *a3,
        int a4,
        __int64 a5,
        __int16 a6,
        int a7,
        int a8,
        _QWORD *a9)
{
  unsigned __int16 v9; // di
  __int64 v13; // r13
  char *Pool2; // rax
  char *v15; // rbx
  char v16; // al
  __int64 v17; // rax
  struct _UNICODE_PREFIX_TABLE_ENTRY *v18; // r14
  _QWORD *v19; // rsi
  void *v20; // rax
  void *v21; // r12
  struct _UNICODE_PREFIX_TABLE **LastNextEntry; // rcx
  _QWORD *v24; // rcx

  v9 = *a3;
  if ( *a3 >= 2u && **((_WORD **)a3 + 1) == 92 )
  {
    v9 -= 2;
    if ( v9 < 2u )
      return 3221225485LL;
    v13 = 2;
  }
  else
  {
    v13 = 0;
  }
  Pool2 = (char *)ExAllocatePool2(257, 408, 1181118542);
  v15 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x198u);
    v16 = v15[7];
    v15[4] |= 0x40u;
    v15[6] |= 2u;
    v15[7] = v16 & 0xF | 0x50;
    *((_QWORD *)v15 + 8) = v15 + 56;
    *((_QWORD *)v15 + 7) = v15 + 56;
    *((_QWORD *)v15 + 9) = 0;
    *((_QWORD *)v15 + 10) = 0;
    *((_QWORD *)v15 + 11) = 0;
    *((_QWORD *)v15 + 12) = 0;
    *((_DWORD *)v15 + 26) = 0;
    *((_QWORD *)v15 + 14) = 0;
    v17 = ExAllocatePool2(65, 56, 1181118542);
    *((_QWORD *)v15 + 6) = v17;
    if ( v17 )
    {
      *(_QWORD *)(v17 + 8) = 0;
      *(_DWORD *)v17 = 1;
      *(_DWORD *)(v17 + 16) = 0;
      KeInitializeEvent((PRKEVENT)(v17 + 24), SynchronizationEvent, 0);
      *((_QWORD *)v15 + 34) = a5;
      *((_DWORD *)v15 + 31) = 1;
      v18 = (struct _UNICODE_PREFIX_TABLE_ENTRY *)(v15 + 136);
      *((_DWORD *)v15 + 63) = a4;
      v19 = v15 + 232;
      *(_DWORD *)v15 = 26739202;
      *((_QWORD *)v15 + 16) = 0;
      *((_QWORD *)v15 + 18) = v15 + 136;
      *((_QWORD *)v15 + 17) = v15 + 136;
      *((_QWORD *)v15 + 30) = v15 + 232;
      *((_QWORD *)v15 + 29) = v15 + 232;
      *((_QWORD *)v15 + 36) = v15 + 280;
      *((_QWORD *)v15 + 35) = v15 + 280;
      *((_QWORD *)v15 + 38) = v15 + 296;
      *((_QWORD *)v15 + 37) = v15 + 296;
      *((_QWORD *)v15 + 40) = v15 + 312;
      *((_QWORD *)v15 + 39) = v15 + 312;
      *((_WORD *)v15 + 128) = a6;
      *((_DWORD *)v15 + 65) = a7;
      *((_DWORD *)v15 + 66) = a8;
      if ( !v9 )
      {
LABEL_11:
        *a9 = v15;
        return 0;
      }
      v20 = (void *)ExAllocatePool2(65, v9, 1850110030);
      v21 = v20;
      if ( v20 )
      {
        memmove(v20, (const void *)(v13 + *((_QWORD *)a3 + 1)), v9);
        *((_WORD *)v15 + 81) = v9;
        *((_WORD *)v15 + 80) = v9;
        *((_QWORD *)v15 + 21) = v21;
        RtlInsertUnicodePrefix(a1 + 9, (PUNICODE_STRING)v15 + 10, (PUNICODE_PREFIX_TABLE_ENTRY)(v15 + 176));
        LastNextEntry = (struct _UNICODE_PREFIX_TABLE **)a1[8].LastNextEntry;
        if ( *LastNextEntry == (struct _UNICODE_PREFIX_TABLE *)&a1[8].NextPrefixTree )
        {
          *(_QWORD *)&v18->NodeTypeCode = (char *)a1 + 200;
          *((_QWORD *)v15 + 18) = LastNextEntry;
          *LastNextEntry = (struct _UNICODE_PREFIX_TABLE *)v18;
          a1[8].LastNextEntry = v18;
          if ( !a2 )
            goto LABEL_11;
          v24 = *(_QWORD **)(a2 + 256);
          if ( *v24 == a2 + 248 )
          {
            *v19 = a2 + 248;
            *((_QWORD *)v15 + 30) = v24;
            *v24 = v19;
            *(_QWORD *)(a2 + 256) = v19;
            goto LABEL_11;
          }
        }
        __fastfail(3u);
      }
      ExFreePoolWithTag(*((PVOID *)v15 + 6), 0);
    }
    ExFreePoolWithTag(v15, 0);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x140015878  mov     [rsp+arg_0], rcx
0x14001587d  push    rbx
0x14001587e  push    rbp
0x14001587f  push    rsi
0x140015880  push    rdi
0x140015881  push    r12
0x140015883  push    r13
0x140015885  push    r14
0x140015887  push    r15
0x140015889  sub     rsp, 28h
0x14001588d  movzx   edi, word ptr [r8]
0x140015891  xor     r12d, r12d
0x140015894  mov     esi, r9d
0x140015897  mov     r15, r8
0x14001589a  mov     rbp, rdx
0x14001589d  lea     r14d, [r12+2]
0x1400158a2  cmp     di, r14w
0x1400158a6  jb      loc_140015AFD
0x1400158ac  mov     rax, [r8+8]
0x1400158b0  cmp     word ptr [rax], 5Ch ; '\'
0x1400158b4  jnz     loc_140015AFD
0x1400158ba  sub     di, r14w
0x1400158be  cmp     di, r14w
0x1400158c2  jb      loc_140015B05
0x1400158c8  mov     r13d, r14d
0x1400158cb  mov     edx, 198h
0x1400158d0  mov     ecx, 101h
0x1400158d5  mov     r8d, 4666704Eh
0x1400158db  call    cs:__imp_ExAllocatePool2
0x1400158e2  nop     dword ptr [rax+rax+00h]
0x1400158e7  mov     rbx, rax
0x1400158ea  test    rax, rax
0x1400158ed  jz      loc_140015AE6
0x1400158f3  xor     edx, edx; Val
0x1400158f5  mov     r8d, 198h; Size
0x1400158fb  mov     rcx, rax; void *
0x1400158fe  call    memset
0x140015903  mov     al, [rbx+7]
0x140015906  mov     edx, 38h ; '8'
0x14001590b  or      byte ptr [rbx+4], 40h
0x14001590f  and     al, 0Fh
0x140015911  or      [rbx+6], r14b
0x140015915  or      al, 50h
0x140015917  mov     [rbx+7], al
0x14001591a  mov     r8d, 4666704Eh
0x140015920  lea     rax, [rbx+38h]
0x140015924  mov     [rax+8], rax
0x140015928  lea     ecx, [rdx+9]
0x14001592b  mov     [rax], rax
0x14001592e  mov     [rbx+48h], r12
0x140015932  mov     [rbx+50h], r12
0x140015936  mov     [rbx+58h], r12
0x14001593a  mov     [rbx+60h], r12
0x14001593e  mov     [rbx+68h], r12d
0x140015942  mov     [rbx+70h], r12
0x140015946  call    cs:__imp_ExAllocatePool2
0x14001594d  nop     dword ptr [rax+rax+00h]
0x140015952  mov     [rbx+30h], rax
0x140015956  test    rax, rax
0x140015959  jz      loc_140015AD5
0x14001595f  mov     r14d, 1
0x140015965  mov     [rax+8], r12
0x140015969  mov     edx, r14d; Type
0x14001596c  mov     [rax], r14d
0x14001596f  lea     rcx, [rax+18h]; Event
0x140015973  mov     [rax+10h], r12d
0x140015977  xor     r8d, r8d; State
0x14001597a  call    cs:__imp_KeInitializeEvent
0x140015981  nop     dword ptr [rax+rax+00h]
0x140015986  mov     rax, [rsp+68h+arg_20]
0x14001598e  mov     [rbx+110h], rax
0x140015995  lea     rax, [rbx+118h]
0x14001599c  mov     [rbx+7Ch], r14d
0x1400159a0  lea     r14, [rbx+88h]
0x1400159a7  mov     [rbx+0FCh], esi
0x1400159ad  lea     rsi, [rbx+0E8h]
0x1400159b4  mov     dword ptr [rbx], 1980202h
0x1400159ba  mov     [rbx+80h], r12
0x1400159c1  mov     [r14+8], r14
0x1400159c5  mov     [r14], r14
0x1400159c8  mov     [rsi+8], rsi
0x1400159cc  mov     [rsi], rsi
0x1400159cf  mov     [rax+8], rax
0x1400159d3  mov     [rax], rax
0x1400159d6  lea     rax, [rbx+128h]
0x1400159dd  mov     [rax+8], rax
0x1400159e1  mov     [rax], rax
0x1400159e4  lea     rax, [rbx+138h]
0x1400159eb  mov     [rax+8], rax
0x1400159ef  mov     [rax], rax
0x1400159f2  movzx   eax, [rsp+68h+arg_28]
0x1400159fa  mov     [rbx+100h], ax
0x140015a01  mov     eax, [rsp+68h+arg_30]
0x140015a08  mov     [rbx+104h], eax
0x140015a0e  mov     eax, [rsp+68h+arg_38]
0x140015a15  mov     [rbx+108h], eax
0x140015a1b  cmp     r12w, di
0x140015a1f  jz      loc_140015AB4
0x140015a25  movzx   edx, di
0x140015a28  mov     ecx, 41h ; 'A'
0x140015a2d  mov     r8d, 6E46704Eh
0x140015a33  call    cs:__imp_ExAllocatePool2
0x140015a3a  nop     dword ptr [rax+rax+00h]
0x140015a3f  mov     r12, rax
0x140015a42  test    rax, rax
0x140015a45  jz      short loc_140015AC3
0x140015a47  mov     rdx, [r15+8]
0x140015a4b  mov     rcx, rax; void *
0x140015a4e  add     rdx, r13; Src
0x140015a51  movzx   r8d, di; Size
0x140015a55  call    memmove
0x140015a5a  lea     rdx, [rbx+0A0h]; Prefix
0x140015a61  mov     [rbx+0A2h], di
0x140015a68  mov     [rdx], di
0x140015a6b  lea     r8, [rbx+0B0h]; PrefixTableEntry
0x140015a72  mov     rdi, [rsp+68h+arg_0]
0x140015a77  mov     [rbx+0A8h], r12
0x140015a7e  lea     rcx, [rdi+0D8h]; PrefixTable
0x140015a85  call    cs:__imp_RtlInsertUnicodePrefix
0x140015a8c  nop     dword ptr [rax+rax+00h]
0x140015a91  lea     rax, [rdi+0C8h]
0x140015a98  mov     rcx, [rax+8]
0x140015a9c  cmp     [rcx], rax
0x140015a9f  jnz     short loc_140015B0C
0x140015aa1  mov     [r14], rax
0x140015aa4  mov     [r14+8], rcx
0x140015aa8  mov     [rcx], r14
0x140015aab  mov     [rax+8], r14
0x140015aaf  test    rbp, rbp
0x140015ab2  jnz     short loc_140015B13
0x140015ab4  mov     rax, [rsp+68h+arg_40]
0x140015abc  mov     [rax], rbx
0x140015abf  xor     eax, eax
0x140015ac1  jmp     short loc_140015AEB
0x140015ac3  mov     rcx, [rbx+30h]; P
0x140015ac7  xor     edx, edx; Tag
0x140015ac9  call    cs:__imp_ExFreePoolWithTag
0x140015ad0  nop     dword ptr [rax+rax+00h]
0x140015ad5  xor     edx, edx; Tag
0x140015ad7  mov     rcx, rbx; P
0x140015ada  call    cs:__imp_ExFreePoolWithTag
0x140015ae1  nop     dword ptr [rax+rax+00h]
0x140015ae6  mov     eax, 0C000009Ah
0x140015aeb  add     rsp, 28h
0x140015aef  pop     r15
0x140015af1  pop     r14
0x140015af3  pop     r13
0x140015af5  pop     r12
0x140015af7  pop     rdi
0x140015af8  pop     rsi
0x140015af9  pop     rbp
0x140015afa  pop     rbx
0x140015afb  retn
0x140015afd  mov     r13, r12
0x140015b00  jmp     loc_1400158CB
0x140015b05  mov     eax, 0C000000Dh
0x140015b0a  jmp     short loc_140015AEB
0x140015b0c  mov     ecx, 3
0x140015b11  int     29h; Win8: RtlFailFast(ecx)
0x140015b13  lea     rax, [rbp+0F8h]
0x140015b1a  mov     rcx, [rax+8]
0x140015b1e  cmp     [rcx], rax
0x140015b21  jnz     short loc_140015B0C
0x140015b23  mov     [rsi], rax
0x140015b26  mov     [rsi+8], rcx
0x140015b2a  mov     [rcx], rsi
0x140015b2d  mov     [rax+8], rsi
0x140015b31  jmp     short loc_140015AB4
```
