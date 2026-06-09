# Dot11Translate80211ToEthernetNdisPacket

- ea: `0x1400131b0`
- end: `0x14001346c`
- name: `Dot11Translate80211ToEthernetNdisPacket`
- size: `700`
- prototype: `__int64 __fastcall(struct _VELAN *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400127ac`
- `0x1400130b8`

## callees

- `0x14000d21c`
- `0x1400131b0`
- `0x140016ed4`
- `0x1400173b4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400133c8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400133c8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013208`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140013208`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140013437`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140013437`

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
0x1400131b0  push    rbx
0x1400131b2  push    rbp
0x1400131b3  push    rsi
0x1400131b4  push    rdi
0x1400131b5  push    r12
0x1400131b7  push    r13
0x1400131b9  push    r14
0x1400131bb  push    r15
0x1400131bd  sub     rsp, 48h
0x1400131c1  mov     rbx, [rdx+28h]
0x1400131c5  xor     eax, eax
0x1400131c7  mov     r12d, [rdx+3Ch]
0x1400131cb  xor     edi, edi
0x1400131cd  mov     r13, r8
0x1400131d0  mov     [rsp+88h+var_58], rax
0x1400131d5  mov     rbp, rdx
0x1400131d8  mov     [rsp+88h+var_50], eax
0x1400131dc  test    byte ptr [rbx+0Ah], 5
0x1400131e0  mov     r14, rcx
0x1400131e3  mov     [rsp+88h+var_4C], ax
0x1400131e8  jz      short loc_1400131F0
0x1400131ea  mov     rdx, [rbx+18h]
0x1400131ee  jmp     short loc_140013217
0x1400131f0  xor     r9d, r9d; RequestedAddress
0x1400131f3  mov     [rsp+88h+Priority], 40000020h; Priority
0x1400131fb  xor     edx, edx; AccessMode
0x1400131fd  mov     [rsp+88h+BugCheckOnFailure], edi; BugCheckOnFailure
0x140013201  mov     rcx, rbx; MemoryDescriptorList
0x140013204  lea     r8d, [r9+1]; CacheType
0x140013208  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001320f  nop     dword ptr [rax+rax+00h]
0x140013214  mov     rdx, rax
0x140013217  mov     r9d, [rbp+0Ch]
0x14001321b  lea     rcx, [r9+8]
0x14001321f  cmp     rcx, 8
0x140013223  jb      loc_140013455
0x140013229  mov     r10d, [rbx+28h]
0x14001322d  cmp     r10, rcx
0x140013230  jb      loc_140013455
0x140013236  mov     r15, [rbp+20h]
0x14001323a  mov     esi, [rbp+38h]
0x14001323d  add     rsi, rdx
0x140013240  mov     rax, [r15+0B0h]
0x140013247  mov     r8d, eax
0x14001324a  mov     [rsp+88h+arg_8], rax
0x140013252  movzx   r11d, word ptr [rsi]
0x140013256  and     r8d, 0FFFF0000h
0x14001325d  mov     dword ptr [rsp+88h+arg_8], r8d
0x140013265  test    r11b, r11b
0x140013268  jns     short loc_1400132AE
0x14001326a  cmp     [rsp+88h+arg_8], rdi
0x140013272  jnz     short loc_1400132AE
0x140013274  mov     al, [rbp+0Ch]
0x140013277  sub     al, 2
0x140013279  movzx   edx, al
0x14001327c  test    r11w, r11w
0x140013280  lea     eax, [rdx-4]
0x140013283  movzx   ecx, al
0x140013286  cmovns  ecx, edx
0x140013289  movzx   eax, cl
0x14001328c  movzx   eax, word ptr [rax+rsi]
0x140013290  mov     cl, al
0x140013292  and     cl, 0Fh
0x140013295  cmp     cl, 8
0x140013298  jnb     short loc_1400132AE
0x14001329a  movzx   r8d, al
0x14001329e  and     r8d, 0Fh
0x1400132a2  shl     r8d, 10h
0x1400132a6  mov     dword ptr [rsp+88h+arg_8], r8d
0x1400132ae  movzx   ebx, word ptr [rsi+r9+6]
0x1400132b4  lea     edi, [r9-0Eh]
0x1400132b8  mov     eax, 81h
0x1400132bd  cmp     bx, ax
0x1400132c0  jnz     loc_14001336C
0x1400132c6  lea     rax, [r9+0Ch]
0x1400132ca  cmp     r10, rax
0x1400132cd  jb      loc_140013455
0x1400132d3  movzx   eax, word ptr [rsi+r9+8]
0x1400132d9  movzx   r10d, al
0x1400132dd  shr     eax, 8
0x1400132e0  mov     ecx, r10d
0x1400132e3  shl     ecx, 8
0x1400132e6  or      ecx, eax
0x1400132e8  mov     edx, ecx
0x1400132ea  shl     edx, 4
0x1400132ed  xor     edx, r8d
0x1400132f0  and     edx, 0FFF0h
0x1400132f6  xor     edx, r8d
0x1400132f9  mov     dword ptr [rsp+88h+arg_8], edx
0x140013300  test    ecx, 0FFFh
0x140013306  jz      short loc_140013347
0x140013308  test    dword ptr [r14+80h], 200h
0x140013313  jnz     short loc_140013347
0x140013315  mov     rcx, cs:WPP_GLOBAL_Control
0x14001331c  lea     rax, WPP_GLOBAL_Control
0x140013323  cmp     rcx, rax
0x140013326  jz      short loc_14001333D
0x140013328  mov     rcx, [rcx+18h]
0x14001332c  lea     r8, WPP_38fc73abf7313b8bec012c05ad7a4fa6_Traceguids
0x140013333  mov     edx, 0Ah
0x140013338  call    WPP_SF_
0x14001333d  mov     eax, 10003h
0x140013342  jmp     loc_14001345A
0x140013347  mov     eax, [r14+80h]
0x14001334e  test    al, 40h
0x140013350  jz      short loc_140013363
0x140013352  and     edx, 0FFFFFFF8h
0x140013355  shr     r10d, 5
0x140013359  or      edx, r10d
0x14001335c  mov     dword ptr [rsp+88h+arg_8], edx
0x140013363  movzx   ebx, word ptr [rsi+r9+0Ah]
0x140013369  add     edi, 4
0x14001336c  mov     rax, [rsp+88h+arg_8]
0x140013374  mov     ecx, 600h
0x140013379  mov     [r15+0B0h], rax
0x140013380  movzx   eax, bx
0x140013383  ror     ax, 8
0x140013387  cmp     ax, cx
0x14001338a  jb      short loc_1400133A3
0x14001338c  movzx   edx, word ptr [rsi+r9+6]; unsigned __int16
0x140013392  mov     rcx, r14; struct _VELAN *
0x140013395  call    ?Dot11CheckSelectiveTranslationTable@@YAHPEAU_VELAN@@G@Z; Dot11CheckSelectiveTranslationTable(_VELAN *,ushort)
0x14001339a  test    eax, eax
0x14001339c  jnz     short loc_1400133A3
0x14001339e  add     edi, 8
0x1400133a1  jmp     short loc_1400133AE
0x1400133a3  movzx   ebx, r12w
0x1400133a7  sub     bx, di
0x1400133aa  sub     bx, 0Eh
0x1400133ae  lea     r8, [rsp+88h+var_58]
0x1400133b3  movzx   edx, bx
0x1400133b6  mov     rcx, rsi
0x1400133b9  call    Dot11Construct8023HeaderFrom80211
0x1400133be  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400133c5  mov     rcx, rbx; Lookaside
0x1400133c8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400133cf  nop     dword ptr [rax+rax+00h]
0x1400133d4  test    rax, rax
0x1400133d7  jz      short loc_14001344E
0x1400133d9  mov     [rax], rbx
0x1400133dc  lea     r9, ?ManufacturingShutdown@@YAXPEAUMANUFACTURING_VELAN@@@Z; FreeMdlMdlHandler
0x1400133e3  mov     dword ptr [rax+8], 74766E43h
0x1400133ea  lea     rbx, [rax+10h]
0x1400133ee  xor     eax, eax
0x1400133f0  mov     ecx, edi
0x1400133f2  add     rcx, rsi
0x1400133f5  xorps   xmm0, xmm0
0x1400133f8  movups  xmmword ptr [rbx], xmm0
0x1400133fb  mov     [rbx+10h], eax
0x1400133fe  mov     r8b, 1; FreeMdl
0x140013401  mov     edx, edi; DataOffsetDelta
0x140013403  movsd   xmm0, qword ptr [rcx]
0x140013407  movsd   qword ptr [rbx], xmm0
0x14001340b  mov     eax, [rcx+8]
0x14001340e  movsd   xmm0, [rsp+88h+var_58]
0x140013414  mov     [rbx+8], eax
0x140013417  movzx   eax, word ptr [rcx+0Ch]
0x14001341b  mov     [rbx+0Ch], ax
0x14001341f  mov     eax, [rsp+88h+var_50]
0x140013423  movsd   qword ptr [rcx], xmm0
0x140013427  mov     [rcx+8], eax
0x14001342a  movzx   eax, [rsp+88h+var_4C]
0x14001342f  mov     [rcx+0Ch], ax
0x140013433  mov     rcx, [rbp+20h]; NetBufferList
0x140013437  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14001343e  nop     dword ptr [rax+rax+00h]
0x140013443  xor     eax, eax
0x140013445  mov     [rbx+10h], edi
0x140013448  mov     [r13+0], rbx
0x14001344c  jmp     short loc_14001345A
0x14001344e  mov     eax, 0C000009Ah
0x140013453  jmp     short loc_14001345A
0x140013455  mov     eax, 0C001000Fh
0x14001345a  add     rsp, 48h
0x14001345e  pop     r15
0x140013460  pop     r14
0x140013462  pop     r13
0x140013464  pop     r12
0x140013466  pop     rdi
0x140013467  pop     rsi
0x140013468  pop     rbp
0x140013469  pop     rbx
0x14001346a  retn
```
