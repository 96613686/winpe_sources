# CmsPinCache::DeleteDoomedCachedPins(CmsTransactionContext *,_LIST_ENTRY *)

- ea: `0x140031ae0`
- end: `0x140031cdc`
- name: `?DeleteDoomedCachedPins@CmsPinCache@@SAXPEAVCmsTransactionContext@@PEAU_LIST_ENTRY@@@Z`
- size: `508`
- prototype: `void __fastcall(struct CmsTransactionContext *, struct _LIST_ENTRY *)`
- caller_count: `17`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000cf50`
- `0x140013540`
- `0x1400137a0`
- `0x140014e40`
- `0x1400171e0`
- `0x140018ae0`
- `0x14002fce0`
- `0x1400305d0`
- `0x1400325d0`
- `0x1400340e0`
- `0x140056ee0`
- `0x14005f694`
- `0x14006bb40`
- `0x14008c450`
- `0x1400a6004`
- `0x1400c64fc`
- `0x1400c92a8`

## callees

- `0x140031ae0`
- `0x140031cf0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c4f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c0d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140031c4f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031c1e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031c60`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031c1e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140031c60`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f19f1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1a0f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f19f1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401f1a0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ccb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031c99`
- `ntoskrnl!ExFreePoolWithTag` at `0x140031ccb`

## pseudocode

```c
void __fastcall CmsPinCache::DeleteDoomedCachedPins(struct CmsTransactionContext *a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v5; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v7; // rbx
  int v8; // esi
  struct _LIST_ENTRY *v9; // rcx
  struct _LIST_ENTRY *v10; // r8
  struct _LIST_ENTRY *v11; // rbx
  struct _SLIST_ENTRY *v12; // r8
  struct _NPAGED_LOOKASIDE_LIST *v13; // rcx
  struct _LIST_ENTRY *v14; // rbp
  struct _SLIST_ENTRY *v15; // r8
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  struct _LIST_ENTRY *v17; // rcx
  struct _LIST_ENTRY *v18; // rcx

  while ( 1 )
  {
    Flink = a2->Flink;
    if ( a2->Flink == a2 )
      break;
    v5 = Flink->Flink;
    if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
      __fastfail(3u);
    v7 = Flink - 1;
    Blink->Flink = v5;
    v5->Blink = Blink;
    if ( ((__int64)Flink[5].Blink & 0x10) != 0 )
    {
      _InterlockedIncrement(&dword_140261F18);
      _InterlockedAdd(&dword_140261F14, HIDWORD(v7[9].Flink));
    }
    CmsCachedPin::Unpin((CmsCachedPin *)v7, a1);
    if ( v7 )
    {
      if ( ((__int64)v7[6].Blink & 8) != 0 )
        HIBYTE(v7[8].Blink[8].Flink) = 0;
      v8 = (__int64)v7[6].Blink & 8;
      if ( ((__int64)v7[6].Blink & 0x10) != 0 )
        _InterlockedAdd64(&CmsCachedPin::GlobalCachedPinPageCount, -LODWORD(v7[9].Blink));
      v9 = v7[3].Flink;
      if ( !v9 )
        goto LABEL_15;
      if ( ((__int64)v7[4].Blink & 8) != 0 )
      {
        BYTE1(v9[-152].Flink) = 0;
        LODWORD(v7[4].Blink) &= ~8u;
      }
      else
      {
        v14 = v9[-1].Flink;
        v15 = (struct _SLIST_ENTRY *)&v9[-1];
        if ( !v14 )
          goto LABEL_30;
        if ( LOBYTE(v14->Blink) )
        {
          v16 = (struct _NPAGED_LOOKASIDE_LIST *)&v14[4];
          if ( BYTE1(v14->Blink) )
            ExFreeToNPagedLookasideList(v16, v15);
          else
            ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v16, v15);
          goto LABEL_14;
        }
        v17 = v14[5].Blink;
        if ( (int)v17 < SLODWORD(v14[5].Flink) || SHIDWORD(v17) >= (int)v17 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)&v14[4], v15);
          _InterlockedIncrement((volatile signed __int32 *)&v14[5].Blink);
        }
        else
        {
LABEL_30:
          ExFreePoolWithTag(v15, 0);
        }
      }
LABEL_14:
      v7[3].Flink = 0;
      LODWORD(v7[3].Blink) = 0;
LABEL_15:
      if ( !v8 )
      {
        v10 = v7[8].Flink;
        if ( v10 )
        {
          v11 = v10[-1].Flink;
          v12 = (struct _SLIST_ENTRY *)&v10[-1];
          if ( !v11 )
            goto LABEL_33;
          if ( LOBYTE(v11->Blink) )
          {
            v13 = (struct _NPAGED_LOOKASIDE_LIST *)&v11[4];
            if ( BYTE1(v11->Blink) )
              ExFreeToNPagedLookasideList(v13, v12);
            else
              ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)v13, v12);
          }
          else
          {
            v18 = v11[5].Blink;
            if ( (int)v18 < SLODWORD(v11[5].Flink) || SHIDWORD(v18) >= (int)v18 )
            {
              ExpInterlockedPushEntrySList((PSLIST_HEADER)&v11[4], v12);
              _InterlockedIncrement((volatile signed __int32 *)&v11[5].Blink);
            }
            else
            {
LABEL_33:
              ExFreePoolWithTag(v12, 0);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140031ae0  push    rdi
0x140031ae2  push    r14
0x140031ae4  push    r15
0x140031ae6  sub     rsp, 20h
0x140031aea  mov     [rsp+38h+arg_0], rbx
0x140031aef  mov     rdi, rdx
0x140031af2  mov     [rsp+38h+arg_8], rbp
0x140031af7  mov     r14, rcx
0x140031afa  mov     [rsp+38h+arg_10], rsi
0x140031aff  xor     r15d, r15d
0x140031b02  mov     rax, [rdi]
0x140031b05  cmp     rax, rdi
0x140031b08  jnz     short loc_140031B24
0x140031b0a  mov     rsi, [rsp+38h+arg_10]
0x140031b0f  mov     rbp, [rsp+38h+arg_8]
0x140031b14  mov     rbx, [rsp+38h+arg_0]
0x140031b19  add     rsp, 20h
0x140031b1d  pop     r15
0x140031b1f  pop     r14
0x140031b21  pop     rdi
0x140031b22  retn
0x140031b24  mov     rdx, [rax]
0x140031b27  cmp     [rdx+8], rax
0x140031b2b  jnz     loc_140031C71
0x140031b31  mov     rcx, [rax+8]
0x140031b35  cmp     [rcx], rax
0x140031b38  jnz     loc_140031C71
0x140031b3e  lea     rbx, [rax-10h]
0x140031b42  mov     [rcx], rdx
0x140031b45  mov     [rdx+8], rcx
0x140031b49  mov     eax, [rbx+68h]
0x140031b4c  test    al, 10h
0x140031b4e  jz      short loc_140031B64
0x140031b50  lock inc cs:dword_140261F18
0x140031b57  mov     eax, [rbx+94h]
0x140031b5d  lock add cs:dword_140261F14, eax
0x140031b64  mov     rdx, r14; struct CmsTransactionCore *
0x140031b67  mov     rcx, rbx; this
0x140031b6a  call    ?Unpin@CmsCachedPin@@QEAAXPEAVCmsTransactionCore@@@Z; CmsCachedPin::Unpin(CmsTransactionCore *)
0x140031b6f  test    rbx, rbx
0x140031b72  jz      short loc_140031B02
0x140031b74  mov     eax, [rbx+68h]
0x140031b77  test    al, 8
0x140031b79  jz      short loc_140031B89
0x140031b7b  mov     rax, [rbx+88h]
0x140031b82  mov     [rax+87h], r15b
0x140031b89  mov     eax, [rbx+68h]
0x140031b8c  mov     esi, eax
0x140031b8e  and     esi, 8
0x140031b91  test    al, 10h
0x140031b93  jz      short loc_140031BAA
0x140031b95  mov     eax, [rbx+98h]
0x140031b9b  nop
0x140031b9c  neg     eax
0x140031b9e  movsxd  rcx, eax
0x140031ba1  lock add cs:?GlobalCachedPinPageCount@CmsCachedPin@@2_JA, rcx; __int64 CmsCachedPin::GlobalCachedPinPageCount
0x140031ba9  nop
0x140031baa  mov     rcx, [rbx+30h]
0x140031bae  test    rcx, rcx
0x140031bb1  jz      short loc_140031BCD
0x140031bb3  mov     eax, [rbx+48h]
0x140031bb6  test    al, 8
0x140031bb8  jz      short loc_140031C2F
0x140031bba  mov     [rcx-97Fh], r15b
0x140031bc1  and     dword ptr [rbx+48h], 0FFFFFFF7h
0x140031bc5  mov     [rbx+30h], r15
0x140031bc9  mov     [rbx+38h], r15d
0x140031bcd  test    esi, esi
0x140031bcf  jnz     loc_140031B02
0x140031bd5  mov     r8, [rbx+80h]
0x140031bdc  test    r8, r8
0x140031bdf  jz      loc_140031B02
0x140031be5  mov     rbx, [r8-10h]
0x140031be9  add     r8, 0FFFFFFFFFFFFFFF0h
0x140031bed  test    rbx, rbx
0x140031bf0  jz      loc_140031CC6
0x140031bf6  cmp     [rbx+8], r15b
0x140031bfa  jz      loc_140031CAA
0x140031c00  lea     rcx, [rbx+40h]; Lookaside
0x140031c04  mov     rdx, r8; Entry
0x140031c07  cmp     [rbx+9], r15b
0x140031c0b  jz      short loc_140031C1E
0x140031c0d  call    cs:__imp_ExFreeToNPagedLookasideList
0x140031c14  nop     dword ptr [rax+rax+00h]
0x140031c19  jmp     loc_140031B02
0x140031c1e  call    cs:__imp_ExFreeToPagedLookasideList
0x140031c25  nop     dword ptr [rax+rax+00h]
0x140031c2a  jmp     loc_140031B02
0x140031c2f  mov     rbp, [rcx-10h]
0x140031c33  lea     r8, [rcx-10h]
0x140031c37  test    rbp, rbp
0x140031c3a  jz      short loc_140031C94
0x140031c3c  cmp     [rbp+8], r15b
0x140031c40  jz      short loc_140031C78
0x140031c42  lea     rcx, [rbp+40h]; Lookaside
0x140031c46  mov     rdx, r8; Entry
0x140031c49  cmp     [rbp+9], r15b
0x140031c4d  jz      short loc_140031C60
0x140031c4f  call    cs:__imp_ExFreeToNPagedLookasideList
0x140031c56  nop     dword ptr [rax+rax+00h]
0x140031c5b  jmp     loc_140031BC5
0x140031c60  call    cs:__imp_ExFreeToPagedLookasideList
0x140031c67  nop     dword ptr [rax+rax+00h]
0x140031c6c  jmp     loc_140031BC5
0x140031c71  mov     ecx, 3
0x140031c76  int     29h; Win8: RtlFailFast(ecx)
0x140031c78  mov     rcx, [rbp+58h]
0x140031c7c  cmp     ecx, [rbp+50h]
0x140031c7f  jl      loc_1401F19EA
0x140031c85  mov     rax, rcx
0x140031c88  shr     rax, 20h
0x140031c8c  cmp     eax, ecx
0x140031c8e  jge     loc_1401F19EA
0x140031c94  xor     edx, edx; Tag
0x140031c96  mov     rcx, r8; P
0x140031c99  call    cs:__imp_ExFreePoolWithTag
0x140031ca0  nop     dword ptr [rax+rax+00h]
0x140031ca5  jmp     loc_140031BC5
0x140031caa  mov     rcx, [rbx+58h]
0x140031cae  cmp     ecx, [rbx+50h]
0x140031cb1  jl      loc_1401F1A08
0x140031cb7  mov     rax, rcx
0x140031cba  shr     rax, 20h
0x140031cbe  cmp     eax, ecx
0x140031cc0  jge     loc_1401F1A08
0x140031cc6  xor     edx, edx; Tag
0x140031cc8  mov     rcx, r8; P
0x140031ccb  call    cs:__imp_ExFreePoolWithTag
0x140031cd2  nop     dword ptr [rax+rax+00h]
0x140031cd7  jmp     loc_140031B02
0x1401f19ea  lea     rcx, [rbp+40h]; ListHead
0x1401f19ee  mov     rdx, r8; ListEntry
0x1401f19f1  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f19f8  nop     dword ptr [rax+rax+00h]
0x1401f19fd  nop
0x1401f19fe  lock inc dword ptr [rbp+58h]
0x1401f1a02  nop
0x1401f1a03  jmp     loc_140031BC5
0x1401f1a08  lea     rcx, [rbx+40h]; ListHead
0x1401f1a0c  mov     rdx, r8; ListEntry
0x1401f1a0f  call    cs:__imp_ExpInterlockedPushEntrySList
0x1401f1a16  nop     dword ptr [rax+rax+00h]
0x1401f1a1b  nop
0x1401f1a1c  lock inc dword ptr [rbx+58h]
0x1401f1a20  nop
0x1401f1a21  jmp     loc_140031B02
```
