# CmsTxMemLog::DiscardPendingRecords(CmsDurableLog *)

- ea: `0x14001cbc0`
- end: `0x14001cd6a`
- name: `?DiscardPendingRecords@CmsTxMemLog@@QEAAXPEAVCmsDurableLog@@@Z`
- size: `426`
- prototype: `void __fastcall(CmsTxMemLog *__hidden this, struct CmsDurableLog *)`
- caller_count: `18`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140010d70`
- `0x140011d20`
- `0x14001b120`
- `0x14001c6c0`
- `0x14001db90`
- `0x14001f1a0`
- `0x14001fdf0`
- `0x1400242e4`
- `0x140027540`
- `0x14002a3d0`
- `0x14002b320`
- `0x14003234c`
- `0x1400325d0`
- `0x140032b20`
- `0x1400340e0`
- `0x14003586c`
- `0x140056ee0`
- `0x14005f694`

## callees

- `0x14001cbc0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc1b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc97`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc1b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001cc97`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001cce7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001ccf8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001cce7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001ccf8`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401eef3f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401eef5d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401eef3f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401eef5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ccad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cc31`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ccad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001cd59`

## pseudocode

```c
void __fastcall CmsTxMemLog::DiscardPendingRecords(CmsTxMemLog *this, struct CmsDurableLog *a2)
{
  __int64 *v2; // rbx
  __int64 v5; // r8
  __int64 *v6; // rdi
  __int64 v7; // rsi
  struct _SLIST_ENTRY *v8; // r8
  struct _NPAGED_LOOKASIDE_LIST *v9; // rcx
  __int64 *v10; // rbx
  __int64 v11; // rcx
  __int64 *v12; // rdi
  __int64 v13; // rsi
  struct _SLIST_ENTRY *v14; // r8
  struct _NPAGED_LOOKASIDE_LIST *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx

  v2 = (__int64 *)*((_QWORD *)this + 3);
  while ( v2 )
  {
    v5 = *v2;
    v6 = v2;
    v2 = (__int64 *)v2[6];
    if ( v5 )
    {
      v7 = *(_QWORD *)(v5 - 16);
      v8 = (struct _SLIST_ENTRY *)(v5 - 16);
      if ( !v7 )
        goto LABEL_20;
      if ( *(_BYTE *)(v7 + 8) )
      {
        v9 = (struct _NPAGED_LOOKASIDE_LIST *)(v7 + 64);
        if ( *(_BYTE *)(v7 + 9) )
          ExFreeToNPagedLookasideList(v9, v8);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v9, v8);
        goto LABEL_7;
      }
      v17 = *(_QWORD *)(v7 + 88);
      if ( (int)v17 < *(_DWORD *)(v7 + 80) || SHIDWORD(v17) >= (int)v17 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v7 + 64), v8);
        _InterlockedIncrement((volatile signed __int32 *)(v7 + 88));
      }
      else
      {
LABEL_20:
        ExFreePoolWithTag(v8, 0);
      }
    }
LABEL_7:
    ExFreePoolWithTag(v6, 0);
  }
  v10 = (__int64 *)*((_QWORD *)this + 2);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  while ( v10 )
  {
    v11 = *v10;
    v12 = v10;
    v10 = (__int64 *)v10[6];
    if ( v11 )
    {
      v13 = *(_QWORD *)(v11 - 16);
      v14 = (struct _SLIST_ENTRY *)(v11 - 16);
      if ( !v13 )
        goto LABEL_23;
      if ( *(_BYTE *)(v13 + 8) )
      {
        v15 = (struct _NPAGED_LOOKASIDE_LIST *)(v13 + 64);
        if ( *(_BYTE *)(v13 + 9) )
          ExFreeToNPagedLookasideList(v15, v14);
        else
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v15, v14);
        goto LABEL_14;
      }
      v18 = *(_QWORD *)(v13 + 88);
      if ( (int)v18 < *(_DWORD *)(v13 + 80) || SHIDWORD(v18) >= (int)v18 )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)(v13 + 64), v14);
        _InterlockedIncrement((volatile signed __int32 *)(v13 + 88));
      }
      else
      {
LABEL_23:
        ExFreePoolWithTag(v14, 0);
      }
    }
LABEL_14:
    ExFreePoolWithTag(v12, 0);
  }
  v16 = *((_DWORD *)this + 12);
  *((_QWORD *)this + 2) = 0;
  _InterlockedAdd((volatile signed __int32 *)a2 + 72, -v16);
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 5) = 0;
}

```

## disassembly

```asm
0x14001cbc0  push    rbx
0x14001cbc2  push    rbp
0x14001cbc3  push    rsi
0x14001cbc4  push    rdi
0x14001cbc5  push    r14
0x14001cbc7  push    r15
0x14001cbc9  sub     rsp, 28h
0x14001cbcd  mov     rbx, [rcx+18h]
0x14001cbd1  mov     rbp, rdx
0x14001cbd4  mov     r14, rcx
0x14001cbd7  test    rbx, rbx
0x14001cbda  jz      short loc_14001CC42
0x14001cbdc  nop     dword ptr [rax+00h]
0x14001cbe0  mov     r8, [rbx]
0x14001cbe3  mov     rdi, rbx
0x14001cbe6  mov     rbx, [rbx+30h]
0x14001cbea  test    r8, r8
0x14001cbed  jz      short loc_14001CC2C
0x14001cbef  mov     rsi, [r8-10h]
0x14001cbf3  add     r8, 0FFFFFFFFFFFFFFF0h
0x14001cbf7  test    rsi, rsi
0x14001cbfa  jz      loc_14001CD22
0x14001cc00  cmp     byte ptr [rsi+8], 0
0x14001cc04  jz      loc_14001CD06
0x14001cc0a  cmp     byte ptr [rsi+9], 0
0x14001cc0e  lea     rcx, [rsi+40h]; Lookaside
0x14001cc12  mov     rdx, r8; Entry
0x14001cc15  jz      loc_14001CCE7
0x14001cc1b  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001cc22  nop     dword ptr [rax+rax+00h]
0x14001cc27  test    rdi, rdi
0x14001cc2a  jz      short loc_14001CC3D
0x14001cc2c  xor     edx, edx; Tag
0x14001cc2e  mov     rcx, rdi; P
0x14001cc31  call    cs:__imp_ExFreePoolWithTag
0x14001cc38  nop     dword ptr [rax+rax+00h]
0x14001cc3d  test    rbx, rbx
0x14001cc40  jnz     short loc_14001CBE0
0x14001cc42  mov     rbx, [r14+10h]
0x14001cc46  xor     r15d, r15d
0x14001cc49  mov     [r14+18h], r15
0x14001cc4d  mov     [r14+20h], r15
0x14001cc51  mov     [r14], r15
0x14001cc54  mov     [r14+8], r15
0x14001cc58  test    rbx, rbx
0x14001cc5b  jz      short loc_14001CCBE
0x14001cc5d  nop     dword ptr [rax]
0x14001cc60  mov     rcx, [rbx]
0x14001cc63  mov     rdi, rbx
0x14001cc66  mov     rbx, [rbx+30h]
0x14001cc6a  test    rcx, rcx
0x14001cc6d  jz      short loc_14001CCA8
0x14001cc6f  mov     rsi, [rcx-10h]
0x14001cc73  lea     r8, [rcx-10h]
0x14001cc77  test    rsi, rsi
0x14001cc7a  jz      loc_14001CD54
0x14001cc80  cmp     [rsi+8], r15b
0x14001cc84  jz      loc_14001CD38
0x14001cc8a  lea     rcx, [rsi+40h]; Lookaside
0x14001cc8e  mov     rdx, r8; Entry
0x14001cc91  cmp     [rsi+9], r15b
0x14001cc95  jz      short loc_14001CCF8
0x14001cc97  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001cc9e  nop     dword ptr [rax+rax+00h]
0x14001cca3  test    rdi, rdi
0x14001cca6  jz      short loc_14001CCB9
0x14001cca8  xor     edx, edx; Tag
0x14001ccaa  mov     rcx, rdi; P
0x14001ccad  call    cs:__imp_ExFreePoolWithTag
0x14001ccb4  nop     dword ptr [rax+rax+00h]
0x14001ccb9  test    rbx, rbx
0x14001ccbc  jnz     short loc_14001CC60
0x14001ccbe  mov     eax, [r14+30h]
0x14001ccc2  mov     [r14+10h], r15
0x14001ccc6  neg     eax
0x14001ccc8  nop
0x14001ccc9  lock add [rbp+120h], eax
0x14001ccd0  nop
0x14001ccd1  mov     [r14+30h], r15d
0x14001ccd5  mov     [r14+28h], r15
0x14001ccd9  add     rsp, 28h
0x14001ccdd  pop     r15
0x14001ccdf  pop     r14
0x14001cce1  pop     rdi
0x14001cce2  pop     rsi
0x14001cce3  pop     rbp
0x14001cce4  pop     rbx
0x14001cce5  retn
0x14001cce7  call    cs:__imp_ExFreeToPagedLookasideList
0x14001ccee  nop     dword ptr [rax+rax+00h]
0x14001ccf3  jmp     loc_14001CC27
0x14001ccf8  call    cs:__imp_ExFreeToPagedLookasideList
0x14001ccff  nop     dword ptr [rax+rax+00h]
0x14001cd04  jmp     short loc_14001CCA3
0x14001cd06  mov     rcx, [rsi+58h]
0x14001cd0a  cmp     ecx, [rsi+50h]
0x14001cd0d  jl      loc_1401EEF38
0x14001cd13  mov     rax, rcx
0x14001cd16  shr     rax, 20h
0x14001cd1a  cmp     eax, ecx
0x14001cd1c  jge     loc_1401EEF38
0x14001cd22  xor     edx, edx; Tag
0x14001cd24  mov     rcx, r8; P
0x14001cd27  call    cs:__imp_ExFreePoolWithTag
0x14001cd2e  nop     dword ptr [rax+rax+00h]
0x14001cd33  jmp     loc_14001CC27
0x14001cd38  mov     rcx, [rsi+58h]
0x14001cd3c  cmp     ecx, [rsi+50h]
0x14001cd3f  jl      loc_1401EEF56
0x14001cd45  mov     rax, rcx
0x14001cd48  shr     rax, 20h
0x14001cd4c  cmp     eax, ecx
0x14001cd4e  jge     loc_1401EEF56
0x14001cd54  xor     edx, edx; Tag
0x14001cd56  mov     rcx, r8; P
0x14001cd59  call    cs:__imp_ExFreePoolWithTag
0x14001cd60  nop     dword ptr [rax+rax+00h]
0x14001cd65  jmp     loc_14001CCA3
0x1401eef38  lea     rcx, [rsi+40h]; ListHead
0x1401eef3c  mov     rdx, r8; ListEntry
0x1401eef3f  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401eef46  nop     dword ptr [rax+rax+00h]
0x1401eef4b  nop
0x1401eef4c  lock inc dword ptr [rsi+58h]
0x1401eef50  nop
0x1401eef51  jmp     loc_14001CC27
0x1401eef56  lea     rcx, [rsi+40h]; ListHead
0x1401eef5a  mov     rdx, r8; ListEntry
0x1401eef5d  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401eef64  nop     dword ptr [rax+rax+00h]
0x1401eef69  nop
0x1401eef6a  lock inc dword ptr [rsi+58h]
0x1401eef6e  nop
0x1401eef6f  jmp     loc_14001CCA3
```
