# FwBatchUpdateAbortRecord(_tag_FW_BATCH_UPDATE_RECORD *)

- ea: `0x18006fd78`
- end: `0x180070071`
- name: `?FwBatchUpdateAbortRecord@@YAXPEAU_tag_FW_BATCH_UPDATE_RECORD@@@Z`
- size: `761`
- prototype: `void __fastcall(struct _tag_FW_BATCH_UPDATE_RECORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18006fd00`

## callees

- `0x1800053c0`
- `0x180032430`
- `0x180032f50`
- `0x18005e394`
- `0x18006fd78`
- `0x1800729c0`
- `0x180073488`
- `0x18008bccc`
- `0x18008ed84`

## import_xrefs

- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe19`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe2d`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe42`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe19`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe2d`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006fe42`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x18006fdc4`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x18006fdc4`
- `fwbase!FwHashtableRemove` at `0x18006ffa4`
- `fwbase!FwHashtableRemove` at `0x18006ffa4`
- `fwbase!FwRestructureHashtable` at `0x18006ffb3`
- `fwbase!FwRestructureHashtable` at `0x18006ffb3`
- `fwbase!FwFree` at `0x18006ffcd`
- `fwbase!FwFree` at `0x18006ffcd`

## pseudocode

```c
void __fastcall FwBatchUpdateAbortRecord(struct _tag_FW_BATCH_UPDATE_RECORD *a1)
{
  __int64 v2; // rbp
  __int64 v3; // r14
  unsigned int v4; // edx
  int v5; // eax
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rcx
  __int64 v19; // r8
  int v20; // edx
  __int64 v21; // [rsp+20h] [rbp-118h] BYREF
  _BYTE v22[216]; // [rsp+28h] [rbp-110h] BYREF

  v2 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  FwMarshalledMetaDataInitialize(&v21);
  v3 = *((_QWORD *)a1 + 3);
  if ( *((_DWORD *)a1 + 14) == 1 )
  {
    v2 = *((_QWORD *)a1 + 5);
    FwSwapListHeads((struct _LIST_ENTRY *)((char *)a1 + 296), (struct _LIST_ENTRY *)(v2 + 264));
    FwSwapListHeads((struct _LIST_ENTRY *)((char *)a1 + 312), (struct _LIST_ENTRY *)(v2 + 280));
    FwMarshalledMetaDataCopy((char *)a1 + 72, &v21);
    FwMarshalledMetaDataCopy(v2 + 40, (char *)a1 + 72);
    FwMarshalledMetaDataCopy(&v21, v2 + 40);
    if ( (unsigned int)(*((_DWORD *)a1 + 4) - 4) > 1 )
    {
      FwBatchUpdateFreeFilters((struct _LIST_ENTRY *)((char *)a1 + 296), 0);
      v4 = *((_DWORD *)a1 + 15);
      if ( v4 )
        FwBatchUpdateFreeFilters((struct _LIST_ENTRY *)((char *)a1 + 312), v4);
    }
  }
  if ( (unsigned int)(*((_DWORD *)a1 + 4) - 4) > 1 )
    goto LABEL_26;
  v5 = *((_DWORD *)a1 + 15);
  if ( *((_DWORD *)a1 + 14) != 1 )
  {
    if ( v5 )
    {
      if ( v5 != 1 )
        goto LABEL_26;
      v11 = *((int *)a1 + 16) + 7LL;
    }
    else
    {
      v11 = *((int *)a1 + 16) + 4LL;
    }
    v9 = v3 + 24 * v11;
    goto LABEL_23;
  }
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      v2 = *((_QWORD *)a1 + 5);
      *(_DWORD *)(v2 + 32) = *((_DWORD *)a1 + 17);
      v8 = *((_QWORD *)a1 + 5);
      if ( *((_DWORD *)a1 + 17) )
        v9 = v3 + 72;
      else
        v9 = v3 + 24;
      v10 = *(_QWORD **)(v9 + 8);
      if ( *v10 != v9 )
        goto LABEL_14;
      goto LABEL_25;
    }
    if ( v5 != 2 )
      goto LABEL_26;
    v9 = v3 + 48;
LABEL_23:
    v10 = *(_QWORD **)(v9 + 8);
    if ( *v10 != v9 )
      goto LABEL_14;
    v8 = *((_QWORD *)a1 + 5);
LABEL_25:
    v12 = (_QWORD *)(v8 + 16);
    *v12 = v9;
    v12[1] = v10;
    *v10 = v12;
    *(_QWORD *)(v9 + 8) = v12;
    goto LABEL_26;
  }
  v6 = *(_QWORD **)(v3 + 8);
  if ( *v6 != v3 )
    goto LABEL_14;
  v7 = (_QWORD *)*((_QWORD *)a1 + 5);
  v7[3] = v6;
  v7 += 2;
  *v7 = v3;
  *v6 = v7;
  *(_QWORD *)(v3 + 8) = v7;
  FwIncreaseRuleCount(*((unsigned int *)a1 + 8), *(unsigned int *)(**((_QWORD **)a1 + 5) + 40LL));
LABEL_26:
  if ( *((_DWORD *)a1 + 4) == 1 )
  {
    v13 = *((_QWORD *)a1 + 5) + 16LL;
    v14 = *(_QWORD *)v13;
    if ( *(_QWORD *)(*(_QWORD *)v13 + 8LL) == v13 )
    {
      v15 = *(_QWORD **)(*((_QWORD *)a1 + 5) + 24LL);
      if ( *v15 == v13 )
      {
        *v15 = v14;
        *(_QWORD *)(v14 + 8) = v15;
        v16 = (_QWORD *)*((_QWORD *)a1 + 5);
        v17 = (_QWORD *)*v16;
        *(_QWORD *)*v16 = 0;
        if ( *((_DWORD *)a1 + 14) == 1 )
        {
          if ( !*((_DWORD *)a1 + 15) )
            FwDecreaseRuleCount(*((unsigned int *)a1 + 8), *((unsigned int *)v17 + 10));
          if ( *(_DWORD *)(v2 + 336) )
          {
            FwHashtableRemove(v3 + 240, v2 + 312);
            FwRestructureHashtable(v3 + 240);
            *(_DWORD *)(v2 + 336) = 0;
          }
        }
        FwFree(*((_QWORD *)a1 + 5));
        goto LABEL_40;
      }
    }
LABEL_14:
    __fastfail(3u);
  }
  v17 = 0;
  if ( *((_DWORD *)a1 + 4) == 2 )
  {
    if ( *((_QWORD *)a1 + 7) == 1 )
      FwUpdateProfileRuleCount(
        *((unsigned int *)a1 + 8),
        *(unsigned int *)(**((_QWORD **)a1 + 5) + 40LL),
        *(unsigned int *)(*((_QWORD *)a1 + 6) + 40LL));
    v18 = (_QWORD *)*((_QWORD *)a1 + 5);
    v17 = (_QWORD *)*v18;
    *v18 = *((_QWORD *)a1 + 6);
    *((_QWORD *)a1 + 6) = v17;
    if ( *((_QWORD *)a1 + 7) == 0x100000001LL )
    {
      v19 = *((_QWORD *)a1 + 5);
      v20 = *(_DWORD *)(v19 + 32);
      *(_DWORD *)(v19 + 32) = *((_DWORD *)a1 + 17);
      *((_DWORD *)a1 + 17) = v20;
    }
  }
LABEL_40:
  FwFreeBlobs(v17, *((unsigned int *)a1 + 14), *((unsigned int *)a1 + 15));
}

```

## disassembly

```asm
0x18006fd78  mov     [rsp+arg_8], rbx
0x18006fd7d  mov     [rsp+arg_10], rbp
0x18006fd82  push    rsi
0x18006fd83  push    rdi
0x18006fd84  push    r12
0x18006fd86  push    r14
0x18006fd88  push    r15
0x18006fd8a  sub     rsp, 110h
0x18006fd91  mov     rax, cs:__security_cookie
0x18006fd98  xor     rax, rsp
0x18006fd9b  mov     [rsp+138h+var_38], rax
0x18006fda3  mov     rsi, rcx
0x18006fda6  xor     ebp, ebp
0x18006fda8  lea     rcx, [rsp+138h+var_110]; void *
0x18006fdad  mov     [rsp+138h+var_118], rbp
0x18006fdb2  xor     edx, edx; Val
0x18006fdb4  mov     r8d, 0D8h; Size
0x18006fdba  call    memset_0
0x18006fdbf  lea     rcx, [rsp+138h+var_118]
0x18006fdc4  call    cs:__imp_FwMarshalledMetaDataInitialize
0x18006fdcb  nop     dword ptr [rax+rax+00h]
0x18006fdd0  mov     r14, [rsi+18h]
0x18006fdd4  lea     ebx, [rbp+1]
0x18006fdd7  cmp     [rsi+38h], ebx
0x18006fdda  jnz     loc_18006FE71
0x18006fde0  mov     rbp, [rsi+28h]
0x18006fde4  lea     r15, [rsi+128h]
0x18006fdeb  mov     rcx, r15; struct _LIST_ENTRY *
0x18006fdee  lea     rdx, [rbp+108h]; struct _LIST_ENTRY *
0x18006fdf5  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x18006fdfa  lea     r12, [rsi+138h]
0x18006fe01  mov     rcx, r12; struct _LIST_ENTRY *
0x18006fe04  lea     rdx, [rbp+118h]; struct _LIST_ENTRY *
0x18006fe0b  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x18006fe10  lea     rcx, [rsi+48h]
0x18006fe14  lea     rdx, [rsp+138h+var_118]
0x18006fe19  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006fe20  nop     dword ptr [rax+rax+00h]
0x18006fe25  lea     rdx, [rsi+48h]
0x18006fe29  lea     rcx, [rbp+28h]
0x18006fe2d  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006fe34  nop     dword ptr [rax+rax+00h]
0x18006fe39  lea     rdx, [rbp+28h]
0x18006fe3d  lea     rcx, [rsp+138h+var_118]
0x18006fe42  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006fe49  nop     dword ptr [rax+rax+00h]
0x18006fe4e  mov     eax, [rsi+10h]
0x18006fe51  sub     eax, 4
0x18006fe54  cmp     eax, ebx
0x18006fe56  jbe     short loc_18006FE71
0x18006fe58  xor     edx, edx; unsigned int
0x18006fe5a  mov     rcx, r15; struct _LIST_ENTRY *
0x18006fe5d  call    ?FwBatchUpdateFreeFilters@@YAXPEAU_LIST_ENTRY@@K@Z; FwBatchUpdateFreeFilters(_LIST_ENTRY *,ulong)
0x18006fe62  mov     edx, [rsi+3Ch]; unsigned int
0x18006fe65  test    edx, edx
0x18006fe67  jz      short loc_18006FE71
0x18006fe69  mov     rcx, r12; struct _LIST_ENTRY *
0x18006fe6c  call    ?FwBatchUpdateFreeFilters@@YAXPEAU_LIST_ENTRY@@K@Z; FwBatchUpdateFreeFilters(_LIST_ENTRY *,ulong)
0x18006fe71  mov     eax, [rsi+10h]
0x18006fe74  sub     eax, 4
0x18006fe77  cmp     eax, ebx
0x18006fe79  ja      loc_18006FF3C
0x18006fe7f  mov     eax, [rsi+3Ch]
0x18006fe82  cmp     [rsi+38h], ebx
0x18006fe85  jnz     short loc_18006FEFB
0x18006fe87  test    eax, eax
0x18006fe89  jnz     short loc_18006FEBE
0x18006fe8b  mov     rcx, [r14+8]
0x18006fe8f  cmp     [rcx], r14
0x18006fe92  jnz     short loc_18006FEE3
0x18006fe94  mov     rax, [rsi+28h]
0x18006fe98  mov     [rax+18h], rcx
0x18006fe9c  add     rax, 10h
0x18006fea0  mov     [rax], r14
0x18006fea3  mov     [rcx], rax
0x18006fea6  mov     [r14+8], rax
0x18006feaa  mov     rax, [rsi+28h]
0x18006feae  mov     ecx, [rsi+20h]
0x18006feb1  mov     rdx, [rax]
0x18006feb4  mov     edx, [rdx+28h]
0x18006feb7  call    FwIncreaseRuleCount
0x18006febc  jmp     short loc_18006FF3C
0x18006febe  cmp     eax, ebx
0x18006fec0  jnz     short loc_18006FEF0
0x18006fec2  mov     eax, [rsi+44h]
0x18006fec5  mov     rbp, [rsi+28h]
0x18006fec9  mov     [rbp+20h], eax
0x18006fecc  cmp     dword ptr [rsi+44h], 0
0x18006fed0  mov     rax, [rsi+28h]
0x18006fed4  jnz     short loc_18006FEEA
0x18006fed6  lea     rcx, [r14+18h]
0x18006feda  mov     rdx, [rcx+8]
0x18006fede  cmp     [rdx], rcx
0x18006fee1  jz      short loc_18006FF2A
0x18006fee3  mov     ecx, 3
0x18006fee8  int     29h; Win8: RtlFailFast(ecx)
0x18006feea  lea     rcx, [r14+48h]
0x18006feee  jmp     short loc_18006FEDA
0x18006fef0  cmp     eax, 2
0x18006fef3  jnz     short loc_18006FF3C
0x18006fef5  lea     rcx, [r14+30h]
0x18006fef9  jmp     short loc_18006FF1D
0x18006fefb  test    eax, eax
0x18006fefd  jnz     short loc_18006FF09
0x18006feff  movsxd  rax, dword ptr [rsi+40h]
0x18006ff03  add     rax, 4
0x18006ff07  jmp     short loc_18006FF15
0x18006ff09  cmp     eax, ebx
0x18006ff0b  jnz     short loc_18006FF3C
0x18006ff0d  movsxd  rax, dword ptr [rsi+40h]
0x18006ff11  add     rax, 7
0x18006ff15  lea     rax, [rax+rax*2]
0x18006ff19  lea     rcx, [r14+rax*8]
0x18006ff1d  mov     rdx, [rcx+8]
0x18006ff21  cmp     [rdx], rcx
0x18006ff24  jnz     short loc_18006FEE3
0x18006ff26  mov     rax, [rsi+28h]
0x18006ff2a  add     rax, 10h
0x18006ff2e  mov     [rax], rcx
0x18006ff31  mov     [rax+8], rdx
0x18006ff35  mov     [rdx], rax
0x18006ff38  mov     [rcx+8], rax
0x18006ff3c  cmp     [rsi+10h], ebx
0x18006ff3f  jnz     loc_18006FFDB
0x18006ff45  mov     rax, [rsi+28h]
0x18006ff49  add     rax, 10h
0x18006ff4d  mov     rdx, [rax]
0x18006ff50  cmp     [rdx+8], rax
0x18006ff54  jnz     short loc_18006FEE3
0x18006ff56  mov     rcx, [rax+8]
0x18006ff5a  cmp     [rcx], rax
0x18006ff5d  jnz     short loc_18006FEE3
0x18006ff5f  mov     [rcx], rdx
0x18006ff62  mov     [rdx+8], rcx
0x18006ff66  mov     rax, [rsi+28h]
0x18006ff6a  mov     rdi, [rax]
0x18006ff6d  mov     qword ptr [rdi], 0
0x18006ff74  cmp     [rsi+38h], ebx
0x18006ff77  jnz     short loc_18006FFC9
0x18006ff79  cmp     dword ptr [rsi+3Ch], 0
0x18006ff7d  jnz     short loc_18006FF8A
0x18006ff7f  mov     edx, [rdi+28h]
0x18006ff82  mov     ecx, [rsi+20h]
0x18006ff85  call    FwDecreaseRuleCount
0x18006ff8a  cmp     dword ptr [rbp+150h], 0
0x18006ff91  jz      short loc_18006FFC9
0x18006ff93  lea     rbx, [r14+0F0h]
0x18006ff9a  mov     rcx, rbx
0x18006ff9d  lea     rdx, [rbp+138h]
0x18006ffa4  call    cs:__imp_FwHashtableRemove
0x18006ffab  nop     dword ptr [rax+rax+00h]
0x18006ffb0  mov     rcx, rbx
0x18006ffb3  call    cs:__imp_FwRestructureHashtable
0x18006ffba  nop     dword ptr [rax+rax+00h]
0x18006ffbf  mov     dword ptr [rbp+150h], 0
0x18006ffc9  mov     rcx, [rsi+28h]
0x18006ffcd  call    cs:__imp_FwFree
0x18006ffd4  nop     dword ptr [rax+rax+00h]
0x18006ffd9  jmp     short loc_180070035
0x18006ffdb  xor     edi, edi
0x18006ffdd  cmp     dword ptr [rsi+10h], 2
0x18006ffe1  jnz     short loc_180070035
0x18006ffe3  cmp     [rsi+38h], ebx
0x18006ffe6  jnz     short loc_180070007
0x18006ffe8  cmp     [rsi+3Ch], edi
0x18006ffeb  jnz     short loc_180070007
0x18006ffed  mov     rax, [rsi+28h]
0x18006fff1  mov     r8, [rsi+30h]
0x18006fff5  mov     ecx, [rsi+20h]
0x18006fff8  mov     rdx, [rax]
0x18006fffb  mov     r8d, [r8+28h]
0x18006ffff  mov     edx, [rdx+28h]
0x180070002  call    FwUpdateProfileRuleCount
0x180070007  mov     rcx, [rsi+28h]
0x18007000b  mov     rax, [rsi+30h]
0x18007000f  mov     rdi, [rcx]
0x180070012  mov     [rcx], rax
0x180070015  mov     [rsi+30h], rdi
0x180070019  cmp     [rsi+38h], ebx
0x18007001c  jnz     short loc_180070035
0x18007001e  cmp     [rsi+3Ch], ebx
0x180070021  jnz     short loc_180070035
0x180070023  mov     r8, [rsi+28h]
0x180070027  mov     eax, [rsi+44h]
0x18007002a  mov     edx, [r8+20h]
0x18007002e  mov     [r8+20h], eax
0x180070032  mov     [rsi+44h], edx
0x180070035  mov     r8d, [rsi+3Ch]
0x180070039  mov     rcx, rdi
0x18007003c  mov     edx, [rsi+38h]
0x18007003f  call    FwFreeBlobs
0x180070044  mov     rcx, [rsp+138h+var_38]
0x18007004c  xor     rcx, rsp; StackCookie
0x18007004f  call    __security_check_cookie
0x180070054  lea     r11, [rsp+138h+var_28]
0x18007005c  mov     rbx, [r11+38h]
0x180070060  mov     rbp, [r11+40h]
0x180070064  mov     rsp, r11
0x180070067  pop     r15
0x180070069  pop     r14
0x18007006b  pop     r12
0x18007006d  pop     rdi
0x18007006e  pop     rsi
0x18007006f  retn
```
