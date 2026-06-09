# COverlayContext::IsCandidateOverlayCompatible(CVisual *,CCompositionSurfaceInfo const *,ISwapChainRealization *,DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES &,OverlaySize,bool,uint,bool)

- ea: `0x180113b08`
- end: `0x180113cb5`
- name: `?IsCandidateOverlayCompatible@COverlayContext@@IEBA_NPEAVCVisual@@PEBVCCompositionSurfaceInfo@@PEAVISwapChainRealization@@AEAUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@W4OverlaySize@@_NI5@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180114a38`

## callees

- `0x180113898`
- `0x180113b08`
- `0x180113cbc`
- `0x1802b6010`

## import_xrefs

- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bac`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bba`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bc8`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bac`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bba`
- `ext-ms-win-ntuser-rectangle-ext-l1-1-0!IsRectEmpty` at `0x180113bc8`

## pseudocode

```c
char __fastcall COverlayContext::IsCandidateOverlayCompatible(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        unsigned int a8,
        char a9)
{
  char v12; // bp
  __int64 v13; // r10
  unsigned int v14; // r8d
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int i; // r8d
  __int64 v18; // r9
  __int64 v19; // rcx
  unsigned int v21; // [rsp+6Ch] [rbp+24h]

  v12 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a4 + 144LL))(a4) )
  {
    v13 = *(_QWORD *)(a1 + 96);
    v14 = 0;
    v15 = (*(_QWORD *)(a1 + 104) - v13) / 392;
    while ( v14 < (unsigned int)v15 )
    {
      if ( !a2 || *(_QWORD *)(392LL * v14 + v13 + 8) == a2 )
      {
        if ( v14 != -1 )
          return v12;
        break;
      }
      ++v14;
    }
    LODWORD(v16) = 0;
    v21 = 0;
    if ( a3 )
    {
      v16 = a3[5];
      v21 = HIDWORD(v16);
    }
    for ( i = 0; i < (unsigned int)v15; ++i )
    {
      if ( !a3 || *(_QWORD *)(*(_QWORD *)(392LL * i + v13 + 16) + 40LL) == __PAIR64__(v21, v16) )
      {
        if ( i != -1 )
          return v12;
        break;
      }
    }
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*a3 + 200LL))(a3)
      && !IsRectEmpty((const RECT *)(a5 + 4))
      && !IsRectEmpty((const RECT *)(a5 + 20))
      && !IsRectEmpty((const RECT *)(a5 + 36)) )
    {
      LOBYTE(v18) = a7;
      if ( (unsigned __int8)COverlayContext::IsOverlayCompatibleScale(a1, a5, a6, v18) )
      {
        if ( a9 && *(_BYTE *)(a1 + 19476) || *(_BYTE *)(a1 + 44) || a8 > 2 )
          return 1;
      }
      else if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x200) != 0 )
      {
        McTemplateU0xq_EventWriteTransfer(v19, &EVTDESC_DISPLAYSURFACE_REJECTCANDIDATE, a3[5], 4);
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180113b08  push    rbx
0x180113b0a  push    rbp
0x180113b0b  push    rsi
0x180113b0c  push    rdi
0x180113b0d  sub     rsp, 28h
0x180113b11  mov     rax, [r9]
0x180113b14  mov     rsi, rcx
0x180113b17  mov     rcx, r9
0x180113b1a  mov     rdi, r8
0x180113b1d  mov     rbx, rdx
0x180113b20  xor     bpl, bpl
0x180113b23  mov     rax, [rax+90h]
0x180113b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113b2f  test    al, al
0x180113b31  jz      loc_180113C08
0x180113b37  mov     r10, [rsi+60h]
0x180113b3b  mov     rax, 5397829CBC14E5E1h
0x180113b45  mov     rcx, [rsi+68h]
0x180113b49  xor     r8d, r8d
0x180113b4c  sub     rcx, r10
0x180113b4f  imul    rcx
0x180113b52  mov     r9, rdx
0x180113b55  sar     r9, 7
0x180113b59  mov     rax, r9
0x180113b5c  shr     rax, 3Fh
0x180113b60  add     r9, rax
0x180113b63  cmp     r8d, r9d
0x180113b66  jb      loc_180113C14
0x180113b6c  xor     eax, eax
0x180113b6e  mov     [rsp+48h+arg_18], rax
0x180113b73  test    rdi, rdi
0x180113b76  jz      short loc_180113B81
0x180113b78  mov     rax, [rdi+28h]
0x180113b7c  mov     [rsp+48h+arg_18], rax
0x180113b81  xor     r8d, r8d
0x180113b84  cmp     r8d, r9d
0x180113b87  jb      loc_180113C32
0x180113b8d  mov     rax, [rdi]
0x180113b90  mov     rcx, rdi
0x180113b93  mov     rax, [rax+0C8h]
0x180113b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113b9f  test    al, al
0x180113ba1  jz      short loc_180113C08
0x180113ba3  mov     rbx, [rsp+48h+arg_20]
0x180113ba8  lea     rcx, [rbx+4]; lprc
0x180113bac  call    cs:__imp_IsRectEmpty
0x180113bb2  test    eax, eax
0x180113bb4  jnz     short loc_180113C08
0x180113bb6  lea     rcx, [rbx+14h]; lprc
0x180113bba  call    cs:__imp_IsRectEmpty
0x180113bc0  test    eax, eax
0x180113bc2  jnz     short loc_180113C08
0x180113bc4  lea     rcx, [rbx+24h]; lprc
0x180113bc8  call    cs:__imp_IsRectEmpty
0x180113bce  test    eax, eax
0x180113bd0  jnz     short loc_180113C08
0x180113bd2  mov     r9b, [rsp+48h+arg_30]
0x180113bda  mov     rdx, rbx
0x180113bdd  mov     r8d, [rsp+48h+arg_28]
0x180113be2  mov     rcx, rsi
0x180113be5  call    ?IsOverlayCompatibleScale@COverlayContext@@IEBA_NPEAUDXGI_MULTIPLANE_OVERLAY_ATTRIBUTES@@W4OverlaySize@@_N@Z; COverlayContext::IsOverlayCompatibleScale(DXGI_MULTIPLANE_OVERLAY_ATTRIBUTES *,OverlaySize,bool)
0x180113bea  test    al, al
0x180113bec  jz      loc_180113C8D
0x180113bf2  cmp     [rsp+48h+arg_40], bpl
0x180113bfa  jz      short loc_180113C78
0x180113bfc  cmp     [rsi+4C14h], bpl
0x180113c03  jz      short loc_180113C78
0x180113c05  mov     bpl, 1
0x180113c08  mov     al, bpl
0x180113c0b  add     rsp, 28h
0x180113c0f  pop     rdi
0x180113c10  pop     rsi
0x180113c11  pop     rbp
0x180113c12  pop     rbx
0x180113c13  retn
0x180113c14  test    rbx, rbx
0x180113c17  jz      short loc_180113C64
0x180113c19  mov     eax, r8d
0x180113c1c  imul    rcx, rax, 188h
0x180113c23  cmp     [rcx+r10+8], rbx
0x180113c28  jz      short loc_180113C64
0x180113c2a  inc     r8d
0x180113c2d  jmp     loc_180113B63
0x180113c32  test    rdi, rdi
0x180113c35  jz      short loc_180113C58
0x180113c37  mov     ecx, r8d
0x180113c3a  imul    rdx, rcx, 188h
0x180113c41  mov     rcx, [rdx+r10+10h]
0x180113c46  mov     rcx, [rcx+28h]
0x180113c4a  cmp     ecx, eax
0x180113c4c  jnz     short loc_180113C70
0x180113c4e  shr     rcx, 20h
0x180113c52  cmp     ecx, dword ptr [rsp+48h+arg_18+4]
0x180113c56  jnz     short loc_180113C70
0x180113c58  cmp     r8d, 0FFFFFFFFh
0x180113c5c  jz      loc_180113B8D
0x180113c62  jmp     short loc_180113C08
0x180113c64  cmp     r8d, 0FFFFFFFFh
0x180113c68  jz      loc_180113B6C
0x180113c6e  jmp     short loc_180113C08
0x180113c70  inc     r8d
0x180113c73  jmp     loc_180113B84
0x180113c78  cmp     [rsi+2Ch], bpl
0x180113c7c  jnz     short loc_180113C05
0x180113c7e  cmp     [rsp+48h+arg_38], 2
0x180113c86  jbe     short loc_180113C08
0x180113c88  jmp     loc_180113C05
0x180113c8d  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 2
0x180113c94  jz      loc_180113C08
0x180113c9a  mov     r8, [rdi+28h]
0x180113c9e  lea     rdx, EVTDESC_DISPLAYSURFACE_REJECTCANDIDATE
0x180113ca5  mov     r9d, 4
0x180113cab  call    McTemplateU0xq_EventWriteTransfer
0x180113cb0  jmp     loc_180113C08
```
