# FwBatchUpdateAbortRecord(_tag_FW_BATCH_UPDATE_RECORD *)

- ea: `0x18006cb2c`
- end: `0x18006cdf6`
- name: `?FwBatchUpdateAbortRecord@@YAXPEAU_tag_FW_BATCH_UPDATE_RECORD@@@Z`
- size: `714`
- prototype: `void __fastcall(struct _tag_FW_BATCH_UPDATE_RECORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18006cabc`

## callees

- `0x1800051f0`
- `0x18002eb40`
- `0x180034c10`
- `0x180059204`
- `0x18006cb2c`
- `0x18006f520`
- `0x18006ffc8`
- `0x180087634`
- `0x18008a58c`

## import_xrefs

- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbc3`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbd1`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbe0`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbc3`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbd1`
- `fwbase!FwMarshalledMetaDataCopy` at `0x18006cbe0`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x18006cb78`
- `fwbase!FwMarshalledMetaDataInitialize` at `0x18006cb78`
- `fwbase!FwHashtableRemove` at `0x18006cd3c`
- `fwbase!FwHashtableRemove` at `0x18006cd3c`
- `fwbase!FwRestructureHashtable` at `0x18006cd45`
- `fwbase!FwRestructureHashtable` at `0x18006cd45`
- `fwbase!FwFree` at `0x18006cd59`
- `fwbase!FwFree` at `0x18006cd59`

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
0x18006cb2c  mov     [rsp+arg_8], rbx
0x18006cb31  mov     [rsp+arg_10], rbp
0x18006cb36  push    rsi
0x18006cb37  push    rdi
0x18006cb38  push    r12
0x18006cb3a  push    r14
0x18006cb3c  push    r15
0x18006cb3e  sub     rsp, 110h
0x18006cb45  mov     rax, cs:__security_cookie
0x18006cb4c  xor     rax, rsp
0x18006cb4f  mov     [rsp+138h+var_38], rax
0x18006cb57  mov     rsi, rcx
0x18006cb5a  xor     ebp, ebp
0x18006cb5c  lea     rcx, [rsp+138h+var_110]; void *
0x18006cb61  mov     [rsp+138h+var_118], rbp
0x18006cb66  xor     edx, edx; Val
0x18006cb68  mov     r8d, 0D8h; Size
0x18006cb6e  call    memset_0
0x18006cb73  lea     rcx, [rsp+138h+var_118]
0x18006cb78  call    cs:__imp_FwMarshalledMetaDataInitialize
0x18006cb7e  mov     r14, [rsi+18h]
0x18006cb82  lea     ebx, [rbp+1]
0x18006cb85  cmp     [rsi+38h], ebx
0x18006cb88  jnz     short loc_18006CC09
0x18006cb8a  mov     rbp, [rsi+28h]
0x18006cb8e  lea     r15, [rsi+128h]
0x18006cb95  mov     rcx, r15; struct _LIST_ENTRY *
0x18006cb98  lea     rdx, [rbp+108h]; struct _LIST_ENTRY *
0x18006cb9f  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x18006cba4  lea     r12, [rsi+138h]
0x18006cbab  mov     rcx, r12; struct _LIST_ENTRY *
0x18006cbae  lea     rdx, [rbp+118h]; struct _LIST_ENTRY *
0x18006cbb5  call    ?FwSwapListHeads@@YAXPEAU_LIST_ENTRY@@0@Z; FwSwapListHeads(_LIST_ENTRY *,_LIST_ENTRY *)
0x18006cbba  lea     rcx, [rsi+48h]
0x18006cbbe  lea     rdx, [rsp+138h+var_118]
0x18006cbc3  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006cbc9  lea     rdx, [rsi+48h]
0x18006cbcd  lea     rcx, [rbp+28h]
0x18006cbd1  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006cbd7  lea     rdx, [rbp+28h]
0x18006cbdb  lea     rcx, [rsp+138h+var_118]
0x18006cbe0  call    cs:__imp_FwMarshalledMetaDataCopy
0x18006cbe6  mov     eax, [rsi+10h]
0x18006cbe9  sub     eax, 4
0x18006cbec  cmp     eax, ebx
0x18006cbee  jbe     short loc_18006CC09
0x18006cbf0  xor     edx, edx; unsigned int
0x18006cbf2  mov     rcx, r15; struct _LIST_ENTRY *
0x18006cbf5  call    ?FwBatchUpdateFreeFilters@@YAXPEAU_LIST_ENTRY@@K@Z; FwBatchUpdateFreeFilters(_LIST_ENTRY *,ulong)
0x18006cbfa  mov     edx, [rsi+3Ch]; unsigned int
0x18006cbfd  test    edx, edx
0x18006cbff  jz      short loc_18006CC09
0x18006cc01  mov     rcx, r12; struct _LIST_ENTRY *
0x18006cc04  call    ?FwBatchUpdateFreeFilters@@YAXPEAU_LIST_ENTRY@@K@Z; FwBatchUpdateFreeFilters(_LIST_ENTRY *,ulong)
0x18006cc09  mov     eax, [rsi+10h]
0x18006cc0c  sub     eax, 4
0x18006cc0f  cmp     eax, ebx
0x18006cc11  ja      loc_18006CCD4
0x18006cc17  mov     eax, [rsi+3Ch]
0x18006cc1a  cmp     [rsi+38h], ebx
0x18006cc1d  jnz     short loc_18006CC93
0x18006cc1f  test    eax, eax
0x18006cc21  jnz     short loc_18006CC56
0x18006cc23  mov     rcx, [r14+8]
0x18006cc27  cmp     [rcx], r14
0x18006cc2a  jnz     short loc_18006CC7B
0x18006cc2c  mov     rax, [rsi+28h]
0x18006cc30  mov     [rax+18h], rcx
0x18006cc34  add     rax, 10h
0x18006cc38  mov     [rax], r14
0x18006cc3b  mov     [rcx], rax
0x18006cc3e  mov     [r14+8], rax
0x18006cc42  mov     rax, [rsi+28h]
0x18006cc46  mov     ecx, [rsi+20h]
0x18006cc49  mov     rdx, [rax]
0x18006cc4c  mov     edx, [rdx+28h]
0x18006cc4f  call    FwIncreaseRuleCount
0x18006cc54  jmp     short loc_18006CCD4
0x18006cc56  cmp     eax, ebx
0x18006cc58  jnz     short loc_18006CC88
0x18006cc5a  mov     eax, [rsi+44h]
0x18006cc5d  mov     rbp, [rsi+28h]
0x18006cc61  mov     [rbp+20h], eax
0x18006cc64  cmp     dword ptr [rsi+44h], 0
0x18006cc68  mov     rax, [rsi+28h]
0x18006cc6c  jnz     short loc_18006CC82
0x18006cc6e  lea     rcx, [r14+18h]
0x18006cc72  mov     rdx, [rcx+8]
0x18006cc76  cmp     [rdx], rcx
0x18006cc79  jz      short loc_18006CCC2
0x18006cc7b  mov     ecx, 3
0x18006cc80  int     29h; Win8: RtlFailFast(ecx)
0x18006cc82  lea     rcx, [r14+48h]
0x18006cc86  jmp     short loc_18006CC72
0x18006cc88  cmp     eax, 2
0x18006cc8b  jnz     short loc_18006CCD4
0x18006cc8d  lea     rcx, [r14+30h]
0x18006cc91  jmp     short loc_18006CCB5
0x18006cc93  test    eax, eax
0x18006cc95  jnz     short loc_18006CCA1
0x18006cc97  movsxd  rax, dword ptr [rsi+40h]
0x18006cc9b  add     rax, 4
0x18006cc9f  jmp     short loc_18006CCAD
0x18006cca1  cmp     eax, ebx
0x18006cca3  jnz     short loc_18006CCD4
0x18006cca5  movsxd  rax, dword ptr [rsi+40h]
0x18006cca9  add     rax, 7
0x18006ccad  lea     rax, [rax+rax*2]
0x18006ccb1  lea     rcx, [r14+rax*8]
0x18006ccb5  mov     rdx, [rcx+8]
0x18006ccb9  cmp     [rdx], rcx
0x18006ccbc  jnz     short loc_18006CC7B
0x18006ccbe  mov     rax, [rsi+28h]
0x18006ccc2  add     rax, 10h
0x18006ccc6  mov     [rax], rcx
0x18006ccc9  mov     [rax+8], rdx
0x18006cccd  mov     [rdx], rax
0x18006ccd0  mov     [rcx+8], rax
0x18006ccd4  cmp     [rsi+10h], ebx
0x18006ccd7  jnz     loc_18006CD61
0x18006ccdd  mov     rax, [rsi+28h]
0x18006cce1  add     rax, 10h
0x18006cce5  mov     rdx, [rax]
0x18006cce8  cmp     [rdx+8], rax
0x18006ccec  jnz     short loc_18006CC7B
0x18006ccee  mov     rcx, [rax+8]
0x18006ccf2  cmp     [rcx], rax
0x18006ccf5  jnz     short loc_18006CC7B
0x18006ccf7  mov     [rcx], rdx
0x18006ccfa  mov     [rdx+8], rcx
0x18006ccfe  mov     rax, [rsi+28h]
0x18006cd02  mov     rdi, [rax]
0x18006cd05  mov     qword ptr [rdi], 0
0x18006cd0c  cmp     [rsi+38h], ebx
0x18006cd0f  jnz     short loc_18006CD55
0x18006cd11  cmp     dword ptr [rsi+3Ch], 0
0x18006cd15  jnz     short loc_18006CD22
0x18006cd17  mov     edx, [rdi+28h]
0x18006cd1a  mov     ecx, [rsi+20h]
0x18006cd1d  call    FwDecreaseRuleCount
0x18006cd22  cmp     dword ptr [rbp+150h], 0
0x18006cd29  jz      short loc_18006CD55
0x18006cd2b  lea     rbx, [r14+0F0h]
0x18006cd32  mov     rcx, rbx
0x18006cd35  lea     rdx, [rbp+138h]
0x18006cd3c  call    cs:__imp_FwHashtableRemove
0x18006cd42  mov     rcx, rbx
0x18006cd45  call    cs:__imp_FwRestructureHashtable
0x18006cd4b  mov     dword ptr [rbp+150h], 0
0x18006cd55  mov     rcx, [rsi+28h]
0x18006cd59  call    cs:__imp_FwFree
0x18006cd5f  jmp     short loc_18006CDBB
0x18006cd61  xor     edi, edi
0x18006cd63  cmp     dword ptr [rsi+10h], 2
0x18006cd67  jnz     short loc_18006CDBB
0x18006cd69  cmp     [rsi+38h], ebx
0x18006cd6c  jnz     short loc_18006CD8D
0x18006cd6e  cmp     [rsi+3Ch], edi
0x18006cd71  jnz     short loc_18006CD8D
0x18006cd73  mov     rax, [rsi+28h]
0x18006cd77  mov     r8, [rsi+30h]
0x18006cd7b  mov     ecx, [rsi+20h]
0x18006cd7e  mov     rdx, [rax]
0x18006cd81  mov     r8d, [r8+28h]
0x18006cd85  mov     edx, [rdx+28h]
0x18006cd88  call    FwUpdateProfileRuleCount
0x18006cd8d  mov     rcx, [rsi+28h]
0x18006cd91  mov     rax, [rsi+30h]
0x18006cd95  mov     rdi, [rcx]
0x18006cd98  mov     [rcx], rax
0x18006cd9b  mov     [rsi+30h], rdi
0x18006cd9f  cmp     [rsi+38h], ebx
0x18006cda2  jnz     short loc_18006CDBB
0x18006cda4  cmp     [rsi+3Ch], ebx
0x18006cda7  jnz     short loc_18006CDBB
0x18006cda9  mov     r8, [rsi+28h]
0x18006cdad  mov     eax, [rsi+44h]
0x18006cdb0  mov     edx, [r8+20h]
0x18006cdb4  mov     [r8+20h], eax
0x18006cdb8  mov     [rsi+44h], edx
0x18006cdbb  mov     r8d, [rsi+3Ch]
0x18006cdbf  mov     rcx, rdi
0x18006cdc2  mov     edx, [rsi+38h]
0x18006cdc5  call    FwFreeBlobs
0x18006cdca  mov     rcx, [rsp+138h+var_38]
0x18006cdd2  xor     rcx, rsp; StackCookie
0x18006cdd5  call    __security_check_cookie
0x18006cdda  lea     r11, [rsp+138h+var_28]
0x18006cde2  mov     rbx, [r11+38h]
0x18006cde6  mov     rbp, [r11+40h]
0x18006cdea  mov     rsp, r11
0x18006cded  pop     r15
0x18006cdef  pop     r14
0x18006cdf1  pop     r12
0x18006cdf3  pop     rdi
0x18006cdf4  pop     rsi
0x18006cdf5  retn
```
