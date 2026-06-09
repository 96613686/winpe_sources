# Dot11Translate80211ToEthernetNdisPacket

- ea: `0x1400131c0`
- end: `0x14001347c`
- name: `Dot11Translate80211ToEthernetNdisPacket`
- size: `700`
- prototype: `__int64 __fastcall(struct _VELAN *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400127bc`
- `0x1400130c8`

## callees

- `0x14000d22c`
- `0x1400131c0`
- `0x140016ed4`
- `0x1400173b4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400133d8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400133d8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013218`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013218`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140013447`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140013447`

## pseudocode

```c
__int64 __fastcall Dot11Translate80211ToEthernetNdisPacket(struct _VELAN *a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  int v4; // r12d
  bool v7; // zf
  char *v9; // rdx
  __int64 v10; // r9
  unsigned __int64 v11; // r10
  __int64 v12; // r15
  __int16 *v13; // rsi
  int v14; // r8d
  unsigned __int8 v15; // cl
  __int16 v16; // ax
  unsigned __int16 v17; // bx
  ULONG v18; // edi
  __int64 result; // rax
  _DWORD *v20; // rax
  char *v21; // rbx
  char *v22; // rcx
  __int64 v23; // xmm0_8
  int v24; // eax
  __int64 v25; // [rsp+30h] [rbp-58h] BYREF
  int v26; // [rsp+38h] [rbp-50h]
  __int16 v27; // [rsp+3Ch] [rbp-4Ch]
  __int64 v28; // [rsp+98h] [rbp+10h]

  v3 = *(_QWORD *)(a2 + 40);
  v4 = *(_DWORD *)(a2 + 60);
  v25 = 0;
  v26 = 0;
  v7 = (*(_BYTE *)(v3 + 10) & 5) == 0;
  v27 = 0;
  if ( v7 )
    v9 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000020u);
  else
    v9 = *(char **)(v3 + 24);
  v10 = *(unsigned int *)(a2 + 12);
  v11 = *(unsigned int *)(v3 + 40);
  if ( v11 < v10 + 8 )
    return 3221291023LL;
  v12 = *(_QWORD *)(a2 + 32);
  v13 = (__int16 *)&v9[*(unsigned int *)(a2 + 56)];
  v28 = *(_QWORD *)(v12 + 176);
  v14 = v28 & 0xFFFF0000;
  LODWORD(v28) = v28 & 0xFFFF0000;
  if ( (*v13 & 0x80u) != 0 && !v28 )
  {
    v15 = *(_BYTE *)(a2 + 12) - 6;
    if ( *v13 >= 0 )
      v15 = *(_BYTE *)(a2 + 12) - 2;
    v16 = *(__int16 *)((char *)v13 + v15);
    if ( (v16 & 0xFu) < 8 )
    {
      v14 = (v16 & 0xF) << 16;
      LODWORD(v28) = v14;
    }
  }
  v17 = *(__int16 *)((char *)v13 + v10 + 6);
  v18 = v10 - 14;
  if ( v17 != 129 )
    goto LABEL_21;
  if ( v11 < v10 + 12 )
    return 3221291023LL;
  LODWORD(v28) = v14
               ^ ((unsigned __int16)v14
                ^ (unsigned __int16)(16
                                   * (HIBYTE(*(unsigned __int16 *)((char *)v13 + v10 + 8))
                                    | ((unsigned __int8)*(__int16 *)((char *)v13 + v10 + 8) << 8))))
               & 0xFFF0;
  if ( ((HIBYTE(*(unsigned __int16 *)((char *)v13 + v10 + 8))
       | (unsigned __int16)((unsigned __int8)*(__int16 *)((char *)v13 + v10 + 8) << 8))
      & 0xFFF) != 0
    && (a1->MacOptions & 0x200) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_38fc73abf7313b8bec012c05ad7a4fa6_Traceguids);
    return 65539;
  }
  if ( (a1->MacOptions & 0x40) != 0 )
    LODWORD(v28) = ((unsigned __int8)*(__int16 *)((char *)v13 + v10 + 8) >> 5)
                 | (v14
                  ^ ((unsigned __int16)v14
                   ^ (unsigned __int16)(16
                                      * (HIBYTE(*(unsigned __int16 *)((char *)v13 + v10 + 8))
                                       | ((unsigned __int8)*(__int16 *)((char *)v13 + v10 + 8) << 8))))
                  & 0xFFF0)
                 & 0xFFFFFFF8;
  v17 = *(__int16 *)((char *)v13 + v10 + 10);
  v18 += 4;
LABEL_21:
  *(_QWORD *)(v12 + 176) = v28;
  if ( __ROR2__(v17, 8) < 0x600u
    || (unsigned int)Dot11CheckSelectiveTranslationTable(a1, *(__int16 *)((char *)v13 + v10 + 6)) )
  {
    v17 = v4 - v18 - 14;
  }
  else
  {
    v18 += 8;
  }
  Dot11Construct8023HeaderFrom80211(v13, v17, &v25);
  v20 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceQueue);
  if ( !v20 )
    return 3221225626LL;
  *(_QWORD *)v20 = &WPP_MAIN_CB.DeviceQueue;
  v20[2] = 1953918531;
  v21 = (char *)(v20 + 4);
  v22 = (char *)v13 + v18;
  *((_OWORD *)v20 + 1) = 0;
  v20[8] = 0;
  *((_QWORD *)v20 + 2) = *(_QWORD *)v22;
  v23 = v25;
  v20[6] = *((_DWORD *)v22 + 2);
  *((_WORD *)v20 + 14) = *((_WORD *)v22 + 6);
  v24 = v26;
  *(_QWORD *)v22 = v23;
  *((_DWORD *)v22 + 2) = v24;
  *((_WORD *)v22 + 6) = v27;
  NdisAdvanceNetBufferListDataStart(*(PNET_BUFFER_LIST *)(a2 + 32), v18, 1u, ManufacturingShutdown);
  result = 0;
  *((_DWORD *)v21 + 4) = v18;
  *a3 = v21;
  return result;
}

```

## disassembly

```asm
0x1400131c0  push    rbx
0x1400131c2  push    rbp
0x1400131c3  push    rsi
0x1400131c4  push    rdi
0x1400131c5  push    r12
0x1400131c7  push    r13
0x1400131c9  push    r14
0x1400131cb  push    r15
0x1400131cd  sub     rsp, 48h
0x1400131d1  mov     rbx, [rdx+28h]
0x1400131d5  xor     eax, eax
0x1400131d7  mov     r12d, [rdx+3Ch]
0x1400131db  xor     edi, edi
0x1400131dd  mov     r13, r8
0x1400131e0  mov     [rsp+88h+var_58], rax
0x1400131e5  mov     rbp, rdx
0x1400131e8  mov     [rsp+88h+var_50], eax
0x1400131ec  test    byte ptr [rbx+0Ah], 5
0x1400131f0  mov     r14, rcx
0x1400131f3  mov     [rsp+88h+var_4C], ax
0x1400131f8  jz      short loc_140013200
0x1400131fa  mov     rdx, [rbx+18h]
0x1400131fe  jmp     short loc_140013227
0x140013200  xor     r9d, r9d; RequestedAddress
0x140013203  mov     [rsp+88h+Priority], 40000020h; Priority
0x14001320b  xor     edx, edx; AccessMode
0x14001320d  mov     [rsp+88h+BugCheckOnFailure], edi; BugCheckOnFailure
0x140013211  mov     rcx, rbx; MemoryDescriptorList
0x140013214  lea     r8d, [r9+1]; CacheType
0x140013218  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001321f  nop     dword ptr [rax+rax+00h]
0x140013224  mov     rdx, rax
0x140013227  mov     r9d, [rbp+0Ch]
0x14001322b  lea     rcx, [r9+8]
0x14001322f  cmp     rcx, 8
0x140013233  jb      loc_140013465
0x140013239  mov     r10d, [rbx+28h]
0x14001323d  cmp     r10, rcx
0x140013240  jb      loc_140013465
0x140013246  mov     r15, [rbp+20h]
0x14001324a  mov     esi, [rbp+38h]
0x14001324d  add     rsi, rdx
0x140013250  mov     rax, [r15+0B0h]
0x140013257  mov     r8d, eax
0x14001325a  mov     [rsp+88h+arg_8], rax
0x140013262  movzx   r11d, word ptr [rsi]
0x140013266  and     r8d, 0FFFF0000h
0x14001326d  mov     dword ptr [rsp+88h+arg_8], r8d
0x140013275  test    r11b, r11b
0x140013278  jns     short loc_1400132BE
0x14001327a  cmp     [rsp+88h+arg_8], rdi
0x140013282  jnz     short loc_1400132BE
0x140013284  mov     al, [rbp+0Ch]
0x140013287  sub     al, 2
0x140013289  movzx   edx, al
0x14001328c  test    r11w, r11w
0x140013290  lea     eax, [rdx-4]
0x140013293  movzx   ecx, al
0x140013296  cmovns  ecx, edx
0x140013299  movzx   eax, cl
0x14001329c  movzx   eax, word ptr [rax+rsi]
0x1400132a0  mov     cl, al
0x1400132a2  and     cl, 0Fh
0x1400132a5  cmp     cl, 8
0x1400132a8  jnb     short loc_1400132BE
0x1400132aa  movzx   r8d, al
0x1400132ae  and     r8d, 0Fh
0x1400132b2  shl     r8d, 10h
0x1400132b6  mov     dword ptr [rsp+88h+arg_8], r8d
0x1400132be  movzx   ebx, word ptr [rsi+r9+6]
0x1400132c4  lea     edi, [r9-0Eh]
0x1400132c8  mov     eax, 81h
0x1400132cd  cmp     bx, ax
0x1400132d0  jnz     loc_14001337C
0x1400132d6  lea     rax, [r9+0Ch]
0x1400132da  cmp     r10, rax
0x1400132dd  jb      loc_140013465
0x1400132e3  movzx   eax, word ptr [rsi+r9+8]
0x1400132e9  movzx   r10d, al
0x1400132ed  shr     eax, 8
0x1400132f0  mov     ecx, r10d
0x1400132f3  shl     ecx, 8
0x1400132f6  or      ecx, eax
0x1400132f8  mov     edx, ecx
0x1400132fa  shl     edx, 4
0x1400132fd  xor     edx, r8d
0x140013300  and     edx, 0FFF0h
0x140013306  xor     edx, r8d
0x140013309  mov     dword ptr [rsp+88h+arg_8], edx
0x140013310  test    ecx, 0FFFh
0x140013316  jz      short loc_140013357
0x140013318  test    dword ptr [r14+80h], 200h
0x140013323  jnz     short loc_140013357
0x140013325  mov     rcx, cs:WPP_GLOBAL_Control
0x14001332c  lea     rax, WPP_GLOBAL_Control
0x140013333  cmp     rcx, rax
0x140013336  jz      short loc_14001334D
0x140013338  mov     rcx, [rcx+18h]
0x14001333c  lea     r8, WPP_38fc73abf7313b8bec012c05ad7a4fa6_Traceguids
0x140013343  mov     edx, 0Ah
0x140013348  call    WPP_SF_
0x14001334d  mov     eax, 10003h
0x140013352  jmp     loc_14001346A
0x140013357  mov     eax, [r14+80h]
0x14001335e  test    al, 40h
0x140013360  jz      short loc_140013373
0x140013362  and     edx, 0FFFFFFF8h
0x140013365  shr     r10d, 5
0x140013369  or      edx, r10d
0x14001336c  mov     dword ptr [rsp+88h+arg_8], edx
0x140013373  movzx   ebx, word ptr [rsi+r9+0Ah]
0x140013379  add     edi, 4
0x14001337c  mov     rax, [rsp+88h+arg_8]
0x140013384  mov     ecx, 600h
0x140013389  mov     [r15+0B0h], rax
0x140013390  movzx   eax, bx
0x140013393  ror     ax, 8
0x140013397  cmp     ax, cx
0x14001339a  jb      short loc_1400133B3
0x14001339c  movzx   edx, word ptr [rsi+r9+6]; unsigned __int16
0x1400133a2  mov     rcx, r14; struct _VELAN *
0x1400133a5  call    ?Dot11CheckSelectiveTranslationTable@@YAHPEAU_VELAN@@G@Z; Dot11CheckSelectiveTranslationTable(_VELAN *,ushort)
0x1400133aa  test    eax, eax
0x1400133ac  jnz     short loc_1400133B3
0x1400133ae  add     edi, 8
0x1400133b1  jmp     short loc_1400133BE
0x1400133b3  movzx   ebx, r12w
0x1400133b7  sub     bx, di
0x1400133ba  sub     bx, 0Eh
0x1400133be  lea     r8, [rsp+88h+var_58]
0x1400133c3  movzx   edx, bx
0x1400133c6  mov     rcx, rsi
0x1400133c9  call    Dot11Construct8023HeaderFrom80211
0x1400133ce  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400133d5  mov     rcx, rbx; Lookaside
0x1400133d8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400133df  nop     dword ptr [rax+rax+00h]
0x1400133e4  test    rax, rax
0x1400133e7  jz      short loc_14001345E
0x1400133e9  mov     [rax], rbx
0x1400133ec  lea     r9, ?ManufacturingShutdown@@YAXPEAUMANUFACTURING_VELAN@@@Z; FreeMdlMdlHandler
0x1400133f3  mov     dword ptr [rax+8], 74766E43h
0x1400133fa  lea     rbx, [rax+10h]
0x1400133fe  xor     eax, eax
0x140013400  mov     ecx, edi
0x140013402  add     rcx, rsi
0x140013405  xorps   xmm0, xmm0
0x140013408  movups  xmmword ptr [rbx], xmm0
0x14001340b  mov     [rbx+10h], eax
0x14001340e  mov     r8b, 1; FreeMdl
0x140013411  mov     edx, edi; DataOffsetDelta
0x140013413  movsd   xmm0, qword ptr [rcx]
0x140013417  movsd   qword ptr [rbx], xmm0
0x14001341b  mov     eax, [rcx+8]
0x14001341e  movsd   xmm0, [rsp+88h+var_58]
0x140013424  mov     [rbx+8], eax
0x140013427  movzx   eax, word ptr [rcx+0Ch]
0x14001342b  mov     [rbx+0Ch], ax
0x14001342f  mov     eax, [rsp+88h+var_50]
0x140013433  movsd   qword ptr [rcx], xmm0
0x140013437  mov     [rcx+8], eax
0x14001343a  movzx   eax, [rsp+88h+var_4C]
0x14001343f  mov     [rcx+0Ch], ax
0x140013443  mov     rcx, [rbp+20h]; NetBufferList
0x140013447  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14001344e  nop     dword ptr [rax+rax+00h]
0x140013453  xor     eax, eax
0x140013455  mov     [rbx+10h], edi
0x140013458  mov     [r13+0], rbx
0x14001345c  jmp     short loc_14001346A
0x14001345e  mov     eax, 0C000009Ah
0x140013463  jmp     short loc_14001346A
0x140013465  mov     eax, 0C001000Fh
0x14001346a  add     rsp, 48h
0x14001346e  pop     r15
0x140013470  pop     r14
0x140013472  pop     r13
0x140013474  pop     r12
0x140013476  pop     rdi
0x140013477  pop     rsi
0x140013478  pop     rbp
0x140013479  pop     rbx
0x14001347a  retn
```
