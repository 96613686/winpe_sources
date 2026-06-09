# UlFastCreateRangeCacheTracker

- ea: `0x1c012270c`
- end: `0x1c0122a5f`
- name: `UlFastCreateRangeCacheTracker`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00cc0e0`

## callees

- `0x1c0001118`
- `0x1c0019fc8`
- `0x1c001b610`
- `0x1c0051194`
- `0x1c00d0304`
- `0x1c012270c`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c0122741`
- `ntoskrnl!MmSizeOfMdl` at `0x1c0122741`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c01229dc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c0122a32`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c01229dc`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1c0122a32`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c01227d3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c01227d3`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0122766`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0122766`

## pseudocode

```c
PSLIST_ENTRY __fastcall UlFastCreateRangeCacheTracker(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5)
{
  __int64 v5; // rbp
  unsigned int v9; // esi
  __int64 v10; // rdi
  unsigned int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  PSLIST_ENTRY v17; // rdi
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, __int64, __int64, __int64); // rax
  __int64 v22; // rdx
  char *v23; // rcx
  char *v24; // rbx
  _BYTE *v25; // rax
  __int64 v26; // r9
  _BYTE *v27; // rax
  __int64 v28; // r9
  _WORD *v29; // r14
  _BYTE *v30; // rbx
  _BYTE *v31; // rbx
  struct _SLIST_ENTRY *Next; // rcx
  struct _SLIST_ENTRY *v33; // rdx
  __int64 v34; // r9
  __int64 v35; // r8
  __int64 v36; // rbx

  v5 = (unsigned int)g_UlRangeCacheFastPathVarHdrMdlSize;
  v9 = (MmSizeOfMdl((PVOID)0xFFF, 0x13u) + 7) & 0xFFFFFFF8;
  if ( UxCompactMode )
  {
    v10 = qword_1C00744B0;
    v11 = KeGetCurrentNodeNumber() + 1;
    v12 = *(_DWORD *)v10 - 1;
    if ( v11 < *(_DWORD *)v10 )
      v12 = v11;
    v13 = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 8LL * v12);
    if ( !*(_BYTE *)(v13 + 112) )
    {
      v14 = v10;
LABEL_9:
      PplpLazyInitializeLookasideList(v14, v13);
    }
  }
  else
  {
    v14 = qword_1C00744B0;
    v15 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v16 = *(_DWORD *)qword_1C00744B0 - 1;
    if ( v15 < *(_DWORD *)qword_1C00744B0 )
      v16 = v15;
    v13 = *(_QWORD *)(*(_QWORD *)(qword_1C00744B0 + 32) + 8LL * v16);
    if ( !*(_BYTE *)(v13 + 112) )
      goto LABEL_9;
  }
  ++*(_DWORD *)(v13 + 20);
  v17 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v13);
  if ( !v17 )
  {
    v18 = *(unsigned int *)(v13 + 40);
    v19 = *(unsigned int *)(v13 + 44);
    v20 = *(unsigned int *)(v13 + 36);
    v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v13 + 48);
    ++*(_DWORD *)(v13 + 24);
    v17 = (PSLIST_ENTRY)v21(v20, v19, v18, v13);
  }
  if ( v17 )
  {
    HIDWORD(v17[1].Next) = g_UlRangeCacheTrackerLookasideSize;
    v17[4].Next = v17 + 5;
    LODWORD(v17[1].Next) = 1163488341;
    *((_BYTE *)&v17[1].Next + 8) = 1;
    *((_DWORD *)&v17[4].Next + 2) = 1;
    v17[5].Next = 0;
    v17[3].Next = v17 + 7;
    v17[6].Next = 0;
    v22 = (__int64)&v17[7] + v9;
    *((_QWORD *)&v17[3].Next + 1) = v22;
    v17[2].Next = (struct _SLIST_ENTRY *)(v22 + v5);
    *((_QWORD *)&v17[2].Next + 1) = v22 + v5 + 19;
    qmemcpy((void *)(v22 + v5), "206 Partial Content", 19);
    if ( a5 )
      UlUpdateParsedHeader(a5, *(unsigned int *)(a5 + 24), "206 Partial Content", 3);
    v23 = (char *)*((_QWORD *)&v17[2].Next + 1);
    *(_OWORD *)v23 = *(_OWORD *)"Content-Range: bytes ";
    v24 = v23 + 14;
    qmemcpy(v23 + 16, "ytes ", 5);
    v25 = (_BYTE *)UlStrPrintUlong(v23 + 21, *a1, 0, 0);
    *v25 = 45;
    v27 = (_BYTE *)UlStrPrintUlong(v25 + 1, *a1 - 1 + a1[2], 0, v26);
    *v27 = 47;
    v29 = (_WORD *)UlStrPrintUlong(v27 + 1, a3, 0, v28);
    if ( (int)UlSetParsedHeader(a5, "Content-Range", 13, v24, (int)v29 - (int)v24) >= 0 )
    {
      *v29 = 2573;
      v30 = v29 + 1;
      if ( !a4 )
      {
LABEL_19:
        *v30 = 13;
        v31 = v30 + 1;
        *v31 = 10;
        Next = v17[2].Next;
        v33 = v17[3].Next;
        v33->Next = 0;
        *((_WORD *)&v33->Next + 4) = 8 * (((unsigned __int16)(((unsigned __int16)Next & 0xFFF) + 4114) >> 12) + 6);
        *((_WORD *)&v33->Next + 5) = 0;
        *((_DWORD *)&v33[2].Next + 3) = (unsigned __int16)Next & 0xFFF;
        v33[2].Next = (struct _SLIST_ENTRY *)((unsigned __int64)Next & 0xFFFFFFFFFFFFF000uLL);
        *((_DWORD *)&v33[2].Next + 2) = 19;
        MmBuildMdlForNonPagedPool((PMDL)v17[3].Next);
        v34 = *((_QWORD *)&v17[2].Next + 1);
        v35 = *((_QWORD *)&v17[3].Next + 1);
        v36 = (__int64)&v31[-v34 + 1];
        *(_QWORD *)v35 = 0;
        *(_WORD *)(v35 + 10) = 0;
        *(_WORD *)(v35 + 8) = 8 * (((v36 + (unsigned __int64)(v34 & 0xFFF) + 4095) >> 12) + 6);
        *(_QWORD *)(v35 + 32) = v34 & 0xFFFFFFFFFFFFF000uLL;
        *(_DWORD *)(v35 + 44) = v34 & 0xFFF;
        *(_DWORD *)(v35 + 40) = v36;
        MmBuildMdlForNonPagedPool(*((PMDL *)&v17[3].Next + 1));
        return v17;
      }
      qmemcpy(v29 + 1, "Accept-Ranges: bytes", 20);
      if ( (int)UlSetParsedHeader(a5, "Accept-Ranges", 13, "bytes", 5) >= 0 )
      {
        v29[11] = 2573;
        v30 = v29 + 12;
        goto LABEL_19;
      }
    }
  }
  return v17;
}

```

## disassembly

```asm
0x1c012270c  mov     [rsp+arg_0], rbx
0x1c0122711  mov     [rsp+arg_8], rbp
0x1c0122716  mov     [rsp+arg_10], rsi
0x1c012271b  push    rdi
0x1c012271c  push    r12
0x1c012271e  push    r13
0x1c0122720  push    r14
0x1c0122722  push    r15
0x1c0122724  sub     rsp, 30h
0x1c0122728  mov     ebp, cs:g_UlRangeCacheFastPathVarHdrMdlSize
0x1c012272e  mov     r14, rcx
0x1c0122731  mov     ecx, 0FFFh; Base
0x1c0122736  mov     edx, 13h; Length
0x1c012273b  mov     r15b, r9b
0x1c012273e  mov     r12d, r8d
0x1c0122741  call    cs:__imp_MmSizeOfMdl
0x1c0122748  nop     dword ptr [rax+rax+00h]
0x1c012274d  xor     r13d, r13d
0x1c0122750  lea     esi, [rax+7]
0x1c0122753  and     esi, 0FFFFFFF8h
0x1c0122756  cmp     cs:UxCompactMode, r13b
0x1c012275d  jz      short loc_1C0122796
0x1c012275f  mov     rdi, cs:qword_1C00744B0
0x1c0122766  call    cs:__imp_KeGetCurrentNodeNumber
0x1c012276d  nop     dword ptr [rax+rax+00h]
0x1c0122772  mov     edx, [rdi]
0x1c0122774  movzx   ecx, ax
0x1c0122777  inc     ecx
0x1c0122779  cmp     ecx, edx
0x1c012277b  lea     eax, [rdx-1]
0x1c012277e  cmovb   eax, ecx
0x1c0122781  mov     edx, eax
0x1c0122783  mov     rax, [rdi+20h]
0x1c0122787  mov     rbx, [rax+rdx*8]
0x1c012278b  cmp     [rbx+70h], r13b
0x1c012278f  jnz     short loc_1C01227CD
0x1c0122791  mov     rcx, rdi
0x1c0122794  jmp     short loc_1C01227C5
0x1c0122796  mov     eax, gs:1A4h
0x1c012279e  mov     rcx, cs:qword_1C00744B0
0x1c01227a5  lea     r8d, [rax+1]
0x1c01227a9  mov     edx, [rcx]
0x1c01227ab  cmp     r8d, edx
0x1c01227ae  lea     eax, [rdx-1]
0x1c01227b1  cmovb   eax, r8d
0x1c01227b5  mov     edx, eax
0x1c01227b7  mov     rax, [rcx+20h]
0x1c01227bb  mov     rbx, [rax+rdx*8]
0x1c01227bf  cmp     [rbx+70h], r13b
0x1c01227c3  jnz     short loc_1C01227CD
0x1c01227c5  mov     rdx, rbx
0x1c01227c8  call    PplpLazyInitializeLookasideList
0x1c01227cd  inc     dword ptr [rbx+14h]
0x1c01227d0  mov     rcx, rbx; ListHead
0x1c01227d3  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c01227da  nop     dword ptr [rax+rax+00h]
0x1c01227df  mov     rdi, rax
0x1c01227e2  test    rax, rax
0x1c01227e5  jnz     short loc_1C0122804
0x1c01227e7  mov     r8d, [rbx+28h]
0x1c01227eb  mov     r9, rbx
0x1c01227ee  mov     edx, [rbx+2Ch]
0x1c01227f1  mov     ecx, [rbx+24h]
0x1c01227f4  mov     rax, [rbx+30h]
0x1c01227f8  inc     dword ptr [rbx+18h]
0x1c01227fb  call    cs:__guard_dispatch_icall_fptr
0x1c0122801  mov     rdi, rax
0x1c0122804  test    rdi, rdi
0x1c0122807  jz      loc_1C0122A3E
0x1c012280d  mov     eax, cs:g_UlRangeCacheTrackerLookasideSize
0x1c0122813  lea     rcx, [rdi+70h]
0x1c0122817  mov     [rdi+14h], eax
0x1c012281a  lea     rax, [rdi+50h]
0x1c012281e  mov     [rdi+40h], rax
0x1c0122822  mov     dword ptr [rdi+10h], 45596C55h
0x1c0122829  mov     byte ptr [rdi+18h], 1
0x1c012282d  mov     dword ptr [rdi+48h], 1
0x1c0122834  mov     [rax], r13
0x1c0122837  mov     [rdi+30h], rcx
0x1c012283b  mov     [rdi+60h], r13
0x1c012283f  mov     edx, esi
0x1c0122841  mov     rsi, [rsp+58h+arg_20]
0x1c0122849  add     rdx, rcx
0x1c012284c  mov     [rdi+38h], rdx
0x1c0122850  lea     rcx, [rdx+rbp]
0x1c0122854  mov     [rdi+20h], rcx
0x1c0122858  lea     rax, [rcx+13h]
0x1c012285c  mov     [rdi+28h], rax
0x1c0122860  movups  xmm0, xmmword ptr cs:a206PartialCont; "206 Partial Content"
0x1c0122867  movups  xmmword ptr [rcx], xmm0
0x1c012286a  movzx   eax, word ptr cs:a206PartialCont+10h; "ent"
0x1c0122871  mov     [rcx+10h], ax
0x1c0122875  mov     al, byte ptr cs:a206PartialCont+12h; "t"
0x1c012287b  mov     [rcx+12h], al
0x1c012287e  test    rsi, rsi
0x1c0122881  jz      short loc_1C012289B
0x1c0122883  mov     edx, [rsi+18h]
0x1c0122886  lea     r8, a206PartialCont; "206 Partial Content"
0x1c012288d  mov     r9d, 3
0x1c0122893  mov     rcx, rsi
0x1c0122896  call    UlUpdateParsedHeader
0x1c012289b  mov     rcx, [rdi+28h]
0x1c012289f  xor     r9d, r9d
0x1c01228a2  movups  xmm0, xmmword ptr cs:aContentRangeBy; "Content-Range: bytes "
0x1c01228a9  xor     r8d, r8d
0x1c01228ac  movups  xmmword ptr [rcx], xmm0
0x1c01228af  mov     eax, dword ptr cs:aContentRangeBy+10h; "ytes "
0x1c01228b5  lea     rbx, [rcx+0Eh]
0x1c01228b9  mov     [rcx+10h], eax
0x1c01228bc  mov     al, byte ptr cs:aContentRangeBy+14h; " "
0x1c01228c2  mov     [rcx+14h], al
0x1c01228c5  add     rcx, 15h
0x1c01228c9  mov     edx, [r14]
0x1c01228cc  call    UlStrPrintUlong
0x1c01228d1  xor     r8d, r8d
0x1c01228d4  mov     byte ptr [rax], 2Dh ; '-'
0x1c01228d7  mov     ecx, [r14]
0x1c01228da  mov     edx, [r14+8]
0x1c01228de  dec     ecx
0x1c01228e0  add     edx, ecx
0x1c01228e2  lea     rcx, [rax+1]
0x1c01228e6  call    UlStrPrintUlong
0x1c01228eb  xor     r8d, r8d
0x1c01228ee  mov     edx, r12d
0x1c01228f1  lea     rcx, [rax+1]
0x1c01228f5  mov     byte ptr [rax], 2Fh ; '/'
0x1c01228f8  call    UlStrPrintUlong
0x1c01228fd  mov     ecx, eax
0x1c01228ff  lea     rdx, aContentRange; "Content-Range"
0x1c0122906  sub     ecx, ebx
0x1c0122908  mov     ebp, 0Dh
0x1c012290d  mov     [rsp+58h+var_38], ecx
0x1c0122911  mov     r9, rbx
0x1c0122914  mov     rcx, rsi
0x1c0122917  mov     r8d, ebp
0x1c012291a  mov     r14, rax
0x1c012291d  call    UlSetParsedHeader
0x1c0122922  test    eax, eax
0x1c0122924  js      loc_1C0122A3E
0x1c012292a  mov     word ptr [r14], 0A0Dh
0x1c0122930  lea     rbx, [r14+2]
0x1c0122934  test    r15b, r15b
0x1c0122937  jz      short loc_1C012297F
0x1c0122939  movups  xmm0, xmmword ptr cs:aAcceptRangesBy; "Accept-Ranges: bytes"
0x1c0122940  lea     r9, aBytes_0; "bytes"
0x1c0122947  mov     [rsp+58h+var_38], 5
0x1c012294f  mov     r8d, ebp
0x1c0122952  lea     rdx, aAcceptRanges; "Accept-Ranges"
0x1c0122959  movups  xmmword ptr [rbx], xmm0
0x1c012295c  mov     eax, dword ptr cs:aAcceptRangesBy+10h; "ytes"
0x1c0122962  mov     rcx, rsi
0x1c0122965  mov     [rbx+10h], eax
0x1c0122968  call    UlSetParsedHeader
0x1c012296d  test    eax, eax
0x1c012296f  js      loc_1C0122A3E
0x1c0122975  mov     word ptr [rbx+14h], 0A0Dh
0x1c012297b  add     rbx, 16h
0x1c012297f  mov     [rbx], bpl
0x1c0122982  mov     rsi, 0FFFFFFFFFFFFF000h
0x1c0122989  mov     ebp, 0FFFh
0x1c012298e  inc     rbx
0x1c0122991  mov     byte ptr [rbx], 0Ah
0x1c0122994  lea     r8d, [rbp+13h]
0x1c0122998  mov     rcx, [rdi+20h]
0x1c012299c  mov     rdx, [rdi+30h]
0x1c01229a0  movzx   eax, cx
0x1c01229a3  and     ax, bp
0x1c01229a6  add     ax, r8w
0x1c01229aa  shr     ax, 0Ch
0x1c01229ae  add     ax, 6
0x1c01229b2  mov     [rdx], r13
0x1c01229b5  shl     ax, 3
0x1c01229b9  mov     [rdx+8], ax
0x1c01229bd  mov     rax, rcx
0x1c01229c0  and     ecx, ebp
0x1c01229c2  mov     [rdx+0Ah], r13w
0x1c01229c7  and     rax, rsi
0x1c01229ca  mov     [rdx+2Ch], ecx
0x1c01229cd  mov     [rdx+20h], rax
0x1c01229d1  mov     dword ptr [rdx+28h], 13h
0x1c01229d8  mov     rcx, [rdi+30h]; MemoryDescriptorList
0x1c01229dc  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c01229e3  nop     dword ptr [rax+rax+00h]
0x1c01229e8  mov     r9, [rdi+28h]
0x1c01229ec  mov     r8, [rdi+38h]
0x1c01229f0  mov     edx, r9d
0x1c01229f3  mov     ecx, edx
0x1c01229f5  sub     rbx, r9
0x1c01229f8  and     rcx, rbp
0x1c01229fb  inc     rbx
0x1c01229fe  add     rcx, rbp
0x1c0122a01  and     r9, rsi
0x1c0122a04  add     rcx, rbx
0x1c0122a07  mov     [r8], r13
0x1c0122a0a  shr     rcx, 0Ch
0x1c0122a0e  and     edx, ebp
0x1c0122a10  add     cx, 6
0x1c0122a14  mov     [r8+0Ah], r13w
0x1c0122a19  shl     cx, 3
0x1c0122a1d  mov     [r8+8], cx
0x1c0122a22  mov     [r8+20h], r9
0x1c0122a26  mov     [r8+2Ch], edx
0x1c0122a2a  mov     [r8+28h], ebx
0x1c0122a2e  mov     rcx, [rdi+38h]; MemoryDescriptorList
0x1c0122a32  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1c0122a39  nop     dword ptr [rax+rax+00h]
0x1c0122a3e  mov     rbx, [rsp+58h+arg_0]
0x1c0122a43  mov     rax, rdi
0x1c0122a46  mov     rbp, [rsp+58h+arg_8]
0x1c0122a4b  mov     rsi, [rsp+58h+arg_10]
0x1c0122a50  add     rsp, 30h
0x1c0122a54  pop     r15
0x1c0122a56  pop     r14
0x1c0122a58  pop     r13
0x1c0122a5a  pop     r12
0x1c0122a5c  pop     rdi
0x1c0122a5d  retn
```
