# DfscFsctrlFlushRefCache

- ea: `0x14001520c`
- end: `0x140015519`
- name: `DfscFsctrlFlushRefCache`
- size: `781`
- prototype: `__int64 __fastcall(IRP *, _WORD *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x1400015c0`
- `0x140001744`
- `0x140002394`
- `0x140002fcc`
- `0x14001520c`
- `0x1400199e4`
- `0x14001a79c`
- `0x14001d090`
- `0x140020d10`

## import_xrefs

- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015417`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400154a6`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x140015417`
- `ntoskrnl!RtlNextUnicodePrefix` at `0x1400154a6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400154cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400154cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400154c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400154c3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001538e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001538e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001537c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001537c`

## pseudocode

```c
__int64 __fastcall DfscFsctrlFlushRefCache(IRP *a1, _WORD *a2, int a3)
{
  int v3; // ebx
  _WORD *v4; // rsi
  int ContainerContextFromIrp; // edi
  struct _UNICODE_PREFIX_TABLE *ReferralCache; // rax
  __int64 v8; // rdx
  struct _UNICODE_PREFIX_TABLE *v9; // r14
  unsigned __int64 v10; // rax
  char v11; // di
  char v12; // si
  PVOID v13; // r15
  __int64 v14; // rbx
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  UNICODE_STRING *p_RightChild; // rdi
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF
  PVOID P; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v21; // [rsp+B8h] [rbp+58h] BYREF

  P = 0;
  v3 = a3;
  v21 = 0;
  v4 = a2;
  v18 = 0;
  if ( (a3 & 1) == 0 && (unsigned int)(a3 - 2) <= 0xFFFC && a2 && *a2 )
  {
    ContainerContextFromIrp = DfscGetContainerContextFromIrp((__int64)a1, &v21);
    if ( ContainerContextFromIrp >= 0 )
    {
      ReferralCache = (struct _UNICODE_PREFIX_TABLE *)DfscGetReferralCache(v21);
      v9 = ReferralCache;
      if ( v3 == 2 && *v4 == 42 )
      {
        DfscCachePurge(ReferralCache);
      }
      else
      {
        *((_QWORD *)&v18 + 1) = v4;
        LOWORD(v18) = v3;
        WORD1(v18) = v3;
        if ( (unsigned __int16)v3 > 4u && *v4 == 92 && v4[1] == 92 )
        {
          LOWORD(v3) = v3 - 2;
          *((_QWORD *)&v18 + 1) = v4 + 1;
          LOWORD(v18) = v3;
          ++v4;
          WORD1(v18) = v3;
        }
        v19 = 0;
        if ( (unsigned __int16)v3 > 2u && v4[((unsigned __int64)(unsigned __int16)v3 >> 1) - 1] == 92 )
        {
          LOWORD(v3) = v3 - 2;
          LOWORD(v18) = v3;
        }
        if ( (unsigned __int16)v3 >= 4u
          && (v10 = (unsigned __int64)(unsigned __int16)v3 >> 1, v4[v10 - 2] == 92)
          && v4[v10 - 1] == 42 )
        {
          v11 = 1;
          LOWORD(v18) = v3 - 4;
        }
        else
        {
          v11 = 0;
        }
        if ( (int)DfscGetReferralFromPath(a1, 0, (IRP *)&v18, 3, v8, (__int64)&P, 0, (__int64)&v19) < 0 )
        {
          return (unsigned int)-1073741772;
        }
        else
        {
          v12 = 0;
          v13 = P;
          v14 = *((_QWORD *)P + 2);
          KeEnterCriticalRegion();
          ExAcquireResourceExclusiveLite((PERESOURCE)&v9[2].NextPrefixTree, 1u);
          if ( v11 && *(_DWORD *)(v14 + 8) != 2 )
            goto LABEL_47;
          if ( !(_WORD)v19 && (*(_BYTE *)(v14 + 12) & 1) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
            {
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                34,
                WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
                v14,
                a1);
            }
            DfscRmUnlinkReferral(v14);
            DfscRmDereferenceReferral((PVOID)v14);
            v12 = 1;
          }
          if ( v11 )
          {
LABEL_47:
            if ( *(_DWORD *)(v14 + 8) == 1 )
            {
              UnicodePrefix = RtlNextUnicodePrefix(v9, 1u);
              if ( UnicodePrefix )
              {
                do
                {
                  p_RightChild = (UNICODE_STRING *)&UnicodePrefix[-2].Links.RightChild;
                  if ( LODWORD(UnicodePrefix[-2].Prefix) == 2
                    && DfscPathPrefixMatch(
                         (PCUNICODE_STRING)(v14 + 112 * (*(unsigned __int16 *)(v14 + 26) + 2LL)),
                         p_RightChild + 9) )
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
                    {
                      WPP_SF_qq(
                        WPP_GLOBAL_Control->AttachedDevice,
                        35,
                        WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids,
                        p_RightChild,
                        a1);
                    }
                    DfscRmUnlinkReferral(p_RightChild);
                    DfscRmDereferenceReferral(p_RightChild);
                    v12 = 1;
                  }
                  UnicodePrefix = RtlNextUnicodePrefix(v9, 0);
                }
                while ( UnicodePrefix );
                v13 = P;
              }
            }
          }
          ExReleaseResourceLite((PERESOURCE)&v9[2].NextPrefixTree);
          KeLeaveCriticalRegion();
          DfscReferralRelease(v13);
          return v12 == 0 ? 0xC0000034 : 0;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)ContainerContextFromIrp;
}

```

## disassembly

```asm
0x14001520c  mov     [rsp-38h+arg_0], rbx
0x140015211  push    rbp
0x140015212  push    rsi
0x140015213  push    rdi
0x140015214  push    r12
0x140015216  push    r13
0x140015218  push    r14
0x14001521a  push    r15
0x14001521c  mov     rbp, rsp
0x14001521f  sub     rsp, 60h
0x140015223  xor     r15d, r15d
0x140015226  xorps   xmm0, xmm0
0x140015229  mov     [rbp+P], r15
0x14001522d  mov     ebx, r8d
0x140015230  mov     [rbp+arg_18], r15
0x140015234  mov     rsi, rdx
0x140015237  mov     r13, rcx
0x14001523a  movups  [rbp+var_20], xmm0
0x14001523e  test    r8b, 1
0x140015242  jnz     loc_1400154F9
0x140015248  lea     eax, [r8-2]
0x14001524c  mov     r12d, 0FFFCh
0x140015252  cmp     eax, r12d
0x140015255  ja      loc_1400154F9
0x14001525b  test    rdx, rdx
0x14001525e  jz      loc_1400154F9
0x140015264  cmp     [rdx], r15w
0x140015268  jz      loc_1400154F9
0x14001526e  lea     rdx, [rbp+arg_18]
0x140015272  call    DfscGetContainerContextFromIrp
0x140015277  mov     edi, eax
0x140015279  test    eax, eax
0x14001527b  js      loc_1400154FE
0x140015281  mov     rdx, [rbp+arg_18]
0x140015285  mov     rcx, rdx
0x140015288  call    DfscGetReferralCache
0x14001528d  lea     r9d, [r15+2]
0x140015291  mov     r14, rax
0x140015294  cmp     ebx, r9d
0x140015297  jnz     short loc_1400152AC
0x140015299  cmp     word ptr [rsi], 2Ah ; '*'
0x14001529d  jnz     short loc_1400152AC
0x14001529f  mov     rcx, rax; PrefixTable
0x1400152a2  call    DfscCachePurge
0x1400152a7  jmp     loc_1400154FE
0x1400152ac  mov     qword ptr [rbp+var_20+8], rsi
0x1400152b0  mov     r8w, 5Ch ; '\'
0x1400152b5  mov     word ptr [rbp+var_20], bx
0x1400152b9  mov     word ptr [rbp+var_20+2], bx
0x1400152bd  cmp     bx, 4
0x1400152c1  jbe     short loc_1400152E6
0x1400152c3  cmp     [rsi], r8w
0x1400152c7  jnz     short loc_1400152E6
0x1400152c9  lea     rcx, [rsi+2]
0x1400152cd  cmp     [rcx], r8w
0x1400152d1  jnz     short loc_1400152E6
0x1400152d3  sub     bx, r9w
0x1400152d7  mov     qword ptr [rbp+var_20+8], rcx
0x1400152db  mov     word ptr [rbp+var_20], bx
0x1400152df  mov     rsi, rcx
0x1400152e2  mov     word ptr [rbp+var_20+2], bx
0x1400152e6  xorps   xmm0, xmm0
0x1400152e9  movups  [rbp+var_10], xmm0
0x1400152ed  cmp     bx, r9w
0x1400152f1  jbe     short loc_14001530D
0x1400152f3  movzx   eax, bx
0x1400152f6  shr     rax, 1
0x1400152f9  cmp     [rsi+rax*2-2], r8w
0x1400152ff  jnz     short loc_14001530D
0x140015301  mov     eax, 0FFFEh
0x140015306  add     bx, ax
0x140015309  mov     word ptr [rbp+var_20], bx
0x14001530d  cmp     bx, 4
0x140015311  jb      short loc_140015336
0x140015313  movzx   eax, bx
0x140015316  shr     rax, 1
0x140015319  cmp     [rsi+rax*2-4], r8w
0x14001531f  jnz     short loc_140015336
0x140015321  cmp     word ptr [rsi+rax*2-2], 2Ah ; '*'
0x140015327  jnz     short loc_140015336
0x140015329  add     bx, r12w
0x14001532d  mov     dil, 1
0x140015330  mov     word ptr [rbp+var_20], bx
0x140015334  jmp     short loc_140015339
0x140015336  mov     dil, r15b
0x140015339  lea     rax, [rbp+var_10]
0x14001533d  mov     r9d, 3
0x140015343  mov     [rsp+60h+var_28], rax
0x140015348  lea     r8, [rbp+var_20]
0x14001534c  lea     rax, [rbp+P]
0x140015350  mov     [rsp+60h+var_30], r15
0x140015355  mov     [rsp+60h+var_38], rax
0x14001535a  mov     rcx, r13
0x14001535d  mov     [rsp+60h+var_40], rdx
0x140015362  xor     edx, edx
0x140015364  call    DfscGetReferralFromPath
0x140015369  test    eax, eax
0x14001536b  js      loc_1400154F2
0x140015371  mov     sil, r15b
0x140015374  mov     r15, [rbp+P]
0x140015378  mov     rbx, [r15+10h]
0x14001537c  call    cs:__imp_KeEnterCriticalRegion
0x140015383  nop     dword ptr [rax+rax+00h]
0x140015388  mov     dl, 1; Wait
0x14001538a  lea     rcx, [r14+38h]; Resource
0x14001538e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140015395  nop     dword ptr [rax+rax+00h]
0x14001539a  xor     ecx, ecx
0x14001539c  lea     rdx, WPP_GLOBAL_Control
0x1400153a3  test    dil, dil
0x1400153a6  jz      short loc_1400153AE
0x1400153a8  cmp     dword ptr [rbx+8], 2
0x1400153ac  jnz     short loc_140015408
0x1400153ae  cmp     word ptr [rbp+var_10], cx
0x1400153b2  jnz     short loc_1400153FF
0x1400153b4  test    byte ptr [rbx+0Ch], 1
0x1400153b8  jz      short loc_1400153FF
0x1400153ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400153c1  cmp     rcx, rdx
0x1400153c4  jz      short loc_1400153EC
0x1400153c6  test    dword ptr [rcx+2Ch], 200000h
0x1400153cd  jz      short loc_1400153EC
0x1400153cf  mov     rcx, [rcx+18h]
0x1400153d3  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x1400153da  mov     edx, 22h ; '"'
0x1400153df  mov     [rsp+60h+var_40], r13
0x1400153e4  mov     r9, rbx
0x1400153e7  call    WPP_SF_qq
0x1400153ec  mov     rcx, rbx
0x1400153ef  call    DfscRmUnlinkReferral
0x1400153f4  mov     rcx, rbx; P
0x1400153f7  call    DfscRmDereferenceReferral
0x1400153fc  mov     sil, 1
0x1400153ff  test    dil, dil
0x140015402  jz      loc_1400154BF
0x140015408  cmp     dword ptr [rbx+8], 1
0x14001540c  jnz     loc_1400154BF
0x140015412  mov     dl, 1; Restart
0x140015414  mov     rcx, r14; PrefixTable
0x140015417  call    cs:__imp_RtlNextUnicodePrefix
0x14001541e  nop     dword ptr [rax+rax+00h]
0x140015423  test    rax, rax
0x140015426  jz      loc_1400154BF
0x14001542c  lea     r15, WPP_GLOBAL_Control
0x140015433  lea     rdi, [rax-48h]
0x140015437  cmp     dword ptr [rdi+8], 2
0x14001543b  jnz     short loc_1400154A1
0x14001543d  movzx   eax, word ptr [rbx+1Ah]
0x140015441  lea     rdx, [rdi+90h]
0x140015448  add     rax, 2
0x14001544c  imul    rcx, rax, 70h ; 'p'
0x140015450  add     rcx, rbx; String1
0x140015453  call    DfscPathPrefixMatch
0x140015458  test    al, al
0x14001545a  jz      short loc_1400154A1
0x14001545c  mov     rcx, cs:WPP_GLOBAL_Control
0x140015463  cmp     rcx, r15
0x140015466  jz      short loc_14001548E
0x140015468  test    dword ptr [rcx+2Ch], 200000h
0x14001546f  jz      short loc_14001548E
0x140015471  mov     rcx, [rcx+18h]
0x140015475  lea     r8, WPP_7a55c31af6b536ac66ab0208a07549b0_Traceguids
0x14001547c  mov     edx, 23h ; '#'
0x140015481  mov     [rsp+60h+var_40], r13
0x140015486  mov     r9, rdi
0x140015489  call    WPP_SF_qq
0x14001548e  mov     rcx, rdi
0x140015491  call    DfscRmUnlinkReferral
0x140015496  mov     rcx, rdi; P
0x140015499  call    DfscRmDereferenceReferral
0x14001549e  mov     sil, 1
0x1400154a1  xor     edx, edx; Restart
0x1400154a3  mov     rcx, r14; PrefixTable
0x1400154a6  call    cs:__imp_RtlNextUnicodePrefix
0x1400154ad  nop     dword ptr [rax+rax+00h]
0x1400154b2  test    rax, rax
0x1400154b5  jnz     loc_140015433
0x1400154bb  mov     r15, [rbp+P]
0x1400154bf  lea     rcx, [r14+38h]; Resource
0x1400154c3  call    cs:__imp_ExReleaseResourceLite
0x1400154ca  nop     dword ptr [rax+rax+00h]
0x1400154cf  call    cs:__imp_KeLeaveCriticalRegion
0x1400154d6  nop     dword ptr [rax+rax+00h]
0x1400154db  mov     rcx, r15; P
0x1400154de  call    DfscReferralRelease
0x1400154e3  neg     sil
0x1400154e6  sbb     edi, edi
0x1400154e8  not     edi
0x1400154ea  and     edi, 0C0000034h
0x1400154f0  jmp     short loc_1400154FE
0x1400154f2  mov     edi, 0C0000034h
0x1400154f7  jmp     short loc_1400154FE
0x1400154f9  mov     edi, 0C000000Dh
0x1400154fe  mov     rbx, [rsp+60h+arg_0]
0x140015506  mov     eax, edi
0x140015508  add     rsp, 60h
0x14001550c  pop     r15
0x14001550e  pop     r14
0x140015510  pop     r13
0x140015512  pop     r12
0x140015514  pop     rdi
0x140015515  pop     rsi
0x140015516  pop     rbp
0x140015517  retn
```
