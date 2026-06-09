# SmbPseExchangeStart_Rename

- ea: `0x14003c550`
- end: `0x14003c816`
- name: `SmbPseExchangeStart_Rename`
- size: `710`
- prototype: `__int64 __fastcall(PVOID pContext, PMRX_FCB Fcb)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x1400360f4`
- `0x140036260`
- `0x1400381a0`
- `0x14003c230`
- `0x14003c2e8`
- `0x14003c550`
- `0x140045d50`
- `0x140046a50`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14003c6fe`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003c76f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003c6fe`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003c76f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c61b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c61b`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14003c7c3`
- `rdbss!RxAcquireExclusiveFcbResourceInMRx` at `0x14003c7c3`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14003c6a5`
- `rdbss!RxReleaseFcbResourceInMRx` at `0x14003c6a5`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeStart_Rename(char *pContext, PMRX_FCB Fcb)
{
  ULONG_PTR PushLock; // rbp
  char *v3; // rsi
  struct _LIST_ENTRY *Flink; // r12
  struct _LIST_ENTRY *Blink; // rbx
  _DWORD *v8; // r15
  __int16 v9; // r13
  struct _LIST_ENTRY *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r15
  _WORD *Context2; // rdx
  struct _LIST_ENTRY *v15; // rax
  int v16; // ebx
  int v17; // ebx
  unsigned int v18; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  __int64 v21; // [rsp+80h] [rbp+8h]

  PushLock = Fcb->Header.PushLock;
  v3 = pContext + 888;
  Flink = Fcb->Header.FilterContexts.Flink;
  Blink = Fcb->Header.FilterContexts.Blink;
  if ( PushLock )
    v8 = *(_DWORD **)(PushLock + 48);
  else
    v8 = 0;
  if ( Blink )
    Blink = Blink[3].Blink;
  v9 = (__int16)Flink->Flink;
  v21 = *((_QWORD *)pContext + 10);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
  MRxSmbSetInitialSMB(v3);
  if ( v9 == -5087 && (BYTE4(Blink[3].Flink) & 2) != 0 )
  {
    if ( !(unsigned int)MRxSmbBuildFindClose(v3) )
      SmbPseOrdinaryExchange(pContext);
    v10 = Blink->Blink;
    WORD2(Blink[3].Flink) &= 0xFFFCu;
    if ( v10 )
    {
      ExFreePoolWithTag(v10, 0);
      Blink->Blink = 0;
    }
  }
  if ( (*(_DWORD *)(PushLock + 72) & 0x100000) != 0 || (*v8 & 0x400) != 0 )
  {
    v13 = v21;
    goto LABEL_22;
  }
  v11 = MRxSmbBuildClose(v3);
  if ( !v11 )
  {
    if ( LODWORD(Fcb[2].Context) == 10 )
      *(_DWORD *)(PushLock + 72) |= 0x10u;
    SmbPseOrdinaryExchange(pContext);
    v12 = (unsigned int)v8[1];
    *v8 |= 0x400u;
    v13 = v21;
    MRxSmbDecrementSrvOpenCount(v21, v12, PushLock);
LABEL_22:
    MRxSmbSetInitialSMB(v3);
    RxReleaseFcbResourceInMRx(Fcb);
    if ( LOBYTE(Fcb[2].UncachedUncleanCount) )
    {
      Context2 = Fcb[2].Context2;
      v15 = Flink[7].Blink;
      String2 = 0;
      v16 = (int)v15[2].Flink[6].Flink;
      String2.Buffer = Context2 + 10;
      v17 = v16 & 8;
      String2.Length = Context2[8];
      if ( RtlCompareUnicodeString((PCUNICODE_STRING)&Flink[22].Blink, &String2, v17 != 0) )
      {
        if ( !(unsigned int)MRxSmbBuildDeleteForRename(v3) )
          SmbPseOrdinaryExchange(pContext);
      }
      else if ( !v17 || !RtlCompareUnicodeString((PCUNICODE_STRING)&Flink[22].Blink, &String2, 0) )
      {
        v11 = 0;
LABEL_38:
        RxAcquireExclusiveFcbResourceInMRx(Fcb);
        goto LABEL_39;
      }
    }
    v18 = MRxSmbBuildRename(v3);
    v11 = v18;
    if ( v18 == -2147483643 || (unsigned int)(*((_DWORD *)v3 + 20) - *((_DWORD *)v3 + 8)) > *(_DWORD *)(v13 + 468) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids);
      }
      v11 = -1073741773;
    }
    else if ( !v18 )
    {
      v11 = SmbPseOrdinaryExchange(pContext);
    }
    goto LABEL_38;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x14003c550  push    rbx
0x14003c552  push    rbp
0x14003c553  push    rsi
0x14003c554  push    rdi
0x14003c555  push    r12
0x14003c557  push    r13
0x14003c559  push    r14
0x14003c55b  push    r15
0x14003c55d  sub     rsp, 38h
0x14003c561  mov     rbp, [rdx+48h]
0x14003c565  lea     rsi, [rcx+378h]
0x14003c56c  mov     r12, [rdx+38h]
0x14003c570  mov     rdi, rdx
0x14003c573  mov     rbx, [rdx+40h]
0x14003c577  mov     r14, rcx
0x14003c57a  test    rbp, rbp
0x14003c57d  jnz     short loc_14003C584
0x14003c57f  xor     r15d, r15d
0x14003c582  jmp     short loc_14003C588
0x14003c584  mov     r15, [rbp+30h]
0x14003c588  test    rbx, rbx
0x14003c58b  jz      short loc_14003C591
0x14003c58d  mov     rbx, [rbx+38h]
0x14003c591  mov     rax, [rcx+50h]
0x14003c595  movzx   r13d, word ptr [r12]
0x14003c59a  mov     [rsp+78h+arg_0], rax
0x14003c5a2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c5a9  lea     rax, WPP_GLOBAL_Control
0x14003c5b0  cmp     rcx, rax
0x14003c5b3  jz      short loc_14003C5D3
0x14003c5b5  test    dword ptr [rcx+2Ch], 400h
0x14003c5bc  jz      short loc_14003C5D3
0x14003c5be  mov     rcx, [rcx+18h]
0x14003c5c2  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c5c9  mov     edx, 0Fh
0x14003c5ce  call    WPP_SF_
0x14003c5d3  mov     rcx, rsi
0x14003c5d6  call    MRxSmbSetInitialSMB
0x14003c5db  mov     eax, 0EC21h
0x14003c5e0  cmp     r13w, ax
0x14003c5e4  jnz     short loc_14003C62F
0x14003c5e6  test    byte ptr [rbx+34h], 2
0x14003c5ea  jz      short loc_14003C62F
0x14003c5ec  mov     rcx, rsi
0x14003c5ef  call    MRxSmbBuildFindClose
0x14003c5f4  test    eax, eax
0x14003c5f6  jnz     short loc_14003C607
0x14003c5f8  lea     r8d, [rax+3]
0x14003c5fc  mov     rdx, rdi
0x14003c5ff  mov     rcx, r14; pContext
0x14003c602  call    SmbPseOrdinaryExchange
0x14003c607  mov     rcx, [rbx+8]; P
0x14003c60b  mov     eax, 0FFFCh
0x14003c610  and     [rbx+34h], ax
0x14003c614  test    rcx, rcx
0x14003c617  jz      short loc_14003C62F
0x14003c619  xor     edx, edx; Tag
0x14003c61b  call    cs:__imp_ExFreePoolWithTag
0x14003c622  nop     dword ptr [rax+rax+00h]
0x14003c627  mov     qword ptr [rbx+8], 0
0x14003c62f  test    dword ptr [rbp+48h], 100000h
0x14003c636  mov     r13d, 400h
0x14003c63c  jnz     short loc_14003C68F
0x14003c63e  test    [r15], r13d
0x14003c641  jnz     short loc_14003C68F
0x14003c643  mov     rcx, rsi
0x14003c646  call    MRxSmbBuildClose
0x14003c64b  mov     ebx, eax
0x14003c64d  test    eax, eax
0x14003c64f  jnz     loc_14003C7D1
0x14003c655  cmp     dword ptr [rdi+1C0h], 0Ah
0x14003c65c  jnz     short loc_14003C662
0x14003c65e  or      dword ptr [rbp+48h], 10h
0x14003c662  mov     r8d, 0Bh
0x14003c668  mov     rdx, rdi
0x14003c66b  mov     rcx, r14; pContext
0x14003c66e  call    SmbPseOrdinaryExchange
0x14003c673  mov     edx, [r15+4]
0x14003c677  mov     r8, rbp
0x14003c67a  or      [r15], r13d
0x14003c67d  mov     r15, [rsp+78h+arg_0]
0x14003c685  mov     rcx, r15
0x14003c688  call    MRxSmbDecrementSrvOpenCount
0x14003c68d  jmp     short loc_14003C697
0x14003c68f  mov     r15, [rsp+78h+arg_0]
0x14003c697  mov     rcx, rsi
0x14003c69a  call    MRxSmbSetInitialSMB
0x14003c69f  mov     rdx, r12
0x14003c6a2  mov     rcx, rdi; Fcb
0x14003c6a5  call    cs:__imp_RxReleaseFcbResourceInMRx
0x14003c6ac  nop     dword ptr [rax+rax+00h]
0x14003c6b1  cmp     byte ptr [rdi+1DCh], 0
0x14003c6b8  jz      short loc_14003C729
0x14003c6ba  mov     rdx, [rdi+1C8h]
0x14003c6c1  lea     rbp, [r12+168h]
0x14003c6c9  mov     rax, [r12+78h]
0x14003c6ce  xorps   xmm0, xmm0
0x14003c6d1  movups  xmmword ptr [rsp+78h+String2.Length], xmm0
0x14003c6d6  mov     rcx, [rax+20h]
0x14003c6da  lea     rax, [rdx+14h]
0x14003c6de  mov     ebx, [rcx+60h]
0x14003c6e1  mov     rcx, rbp; String1
0x14003c6e4  mov     [rsp+78h+String2.Buffer], rax
0x14003c6e9  and     ebx, 8
0x14003c6ec  movzx   eax, word ptr [rdx+10h]
0x14003c6f0  lea     rdx, [rsp+78h+String2]; String2
0x14003c6f5  setnz   r8b; CaseInSensitive
0x14003c6f9  mov     [rsp+78h+String2.Length], ax
0x14003c6fe  call    cs:__imp_RtlCompareUnicodeString
0x14003c705  nop     dword ptr [rax+rax+00h]
0x14003c70a  test    eax, eax
0x14003c70c  jz      short loc_14003C760
0x14003c70e  mov     rcx, rsi
0x14003c711  call    MRxSmbBuildDeleteForRename
0x14003c716  test    eax, eax
0x14003c718  jnz     short loc_14003C729
0x14003c71a  lea     r8d, [rax+17h]
0x14003c71e  mov     rdx, rdi
0x14003c721  mov     rcx, r14; pContext
0x14003c724  call    SmbPseOrdinaryExchange
0x14003c729  mov     rcx, rsi
0x14003c72c  call    MRxSmbBuildRename
0x14003c731  mov     ebx, eax
0x14003c733  cmp     eax, 80000005h
0x14003c738  jz      short loc_14003C78A
0x14003c73a  mov     ecx, [rsi+50h]
0x14003c73d  sub     ecx, [rsi+20h]
0x14003c740  cmp     ecx, [r15+1D4h]
0x14003c747  ja      short loc_14003C78A
0x14003c749  test    eax, eax
0x14003c74b  jnz     short loc_14003C781
0x14003c74d  lea     r8d, [rax+0Dh]
0x14003c751  mov     rdx, rdi
0x14003c754  mov     rcx, r14; pContext
0x14003c757  call    SmbPseOrdinaryExchange
0x14003c75c  mov     ebx, eax
0x14003c75e  jmp     short loc_14003C781
0x14003c760  test    ebx, ebx
0x14003c762  jz      short loc_14003C77F
0x14003c764  xor     r8d, r8d; CaseInSensitive
0x14003c767  lea     rdx, [rsp+78h+String2]; String2
0x14003c76c  mov     rcx, rbp; String1
0x14003c76f  call    cs:__imp_RtlCompareUnicodeString
0x14003c776  nop     dword ptr [rax+rax+00h]
0x14003c77b  test    eax, eax
0x14003c77d  jnz     short loc_14003C729
0x14003c77f  xor     ebx, ebx
0x14003c781  lea     rsi, WPP_GLOBAL_Control
0x14003c788  jmp     short loc_14003C7BD
0x14003c78a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c791  lea     rsi, WPP_GLOBAL_Control
0x14003c798  cmp     rcx, rsi
0x14003c79b  jz      short loc_14003C7B8
0x14003c79d  test    [rcx+2Ch], r13d
0x14003c7a1  jz      short loc_14003C7B8
0x14003c7a3  mov     rcx, [rcx+18h]
0x14003c7a7  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c7ae  mov     edx, 10h
0x14003c7b3  call    WPP_SF_
0x14003c7b8  mov     ebx, 0C0000033h
0x14003c7bd  mov     rdx, r12
0x14003c7c0  mov     rcx, rdi; Fcb
0x14003c7c3  call    cs:__imp_RxAcquireExclusiveFcbResourceInMRx
0x14003c7ca  nop     dword ptr [rax+rax+00h]
0x14003c7cf  jmp     short loc_14003C7D8
0x14003c7d1  lea     rsi, WPP_GLOBAL_Control
0x14003c7d8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c7df  cmp     rcx, rsi
0x14003c7e2  jz      short loc_14003C802
0x14003c7e4  test    [rcx+2Ch], r13d
0x14003c7e8  jz      short loc_14003C802
0x14003c7ea  mov     rcx, [rcx+18h]
0x14003c7ee  lea     r8, WPP_b5c12b3c33fd3bcba111aad67a017491_Traceguids
0x14003c7f5  mov     edx, 11h
0x14003c7fa  mov     r9d, ebx
0x14003c7fd  call    WPP_SF_d
0x14003c802  mov     eax, ebx
0x14003c804  add     rsp, 38h
0x14003c808  pop     r15
0x14003c80a  pop     r14
0x14003c80c  pop     r13
0x14003c80e  pop     r12
0x14003c810  pop     rdi
0x14003c811  pop     rsi
0x14003c812  pop     rbp
0x14003c813  pop     rbx
0x14003c814  retn
```
