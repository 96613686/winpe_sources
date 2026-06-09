# RxpCopyCreateParameters

- ea: `0x14000b0d0`
- end: `0x14000b349`
- name: `RxpCopyCreateParameters`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a830`

## callees

- `0x14000b0d0`
- `0x140017280`
- `0x140017370`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400274bc`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400274bc`

## pseudocode

```c
void __fastcall RxpCopyCreateParameters(__int64 a1)
{
  __int64 v2; // rbp
  __int64 v3; // rdi
  __int64 v4; // rax
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  void *v7; // rcx
  _DWORD *v8; // rax
  int v9; // edx
  int v10; // ecx
  _WORD *v11; // rax
  __int64 v12; // rax
  _WORD *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx

  if ( (*(_BYTE *)(a1 + 750) & 2) == 0 )
  {
    v2 = *(_QWORD *)(a1 + 40);
    v3 = *(_QWORD *)(v2 + 184);
    v4 = *(_QWORD *)(v3 + 8);
    v5 = *(_QWORD **)(v3 + 48);
    *(_QWORD *)(a1 + 544) = v4;
    v6 = *(_QWORD *)(v4 + 8);
    if ( v6 )
    {
      v7 = *(void **)(v6 + 64);
      if ( v7 )
      {
        *(_DWORD *)(a1 + 716) = RtlLengthSecurityDescriptor(v7);
        *(_QWORD *)(a1 + 704) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 544) + 8LL) + 64LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              *(_QWORD *)(a1 + 544));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              15,
              &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
              *(_QWORD *)(a1 + 544));
          }
        }
      }
    }
    v8 = *(_DWORD **)(a1 + 544);
    if ( *(_QWORD *)v8 )
      v9 = *(_DWORD *)(*(_QWORD *)v8 + 4LL);
    else
      v9 = 2;
    *(_DWORD *)(a1 + 552) = v9;
    *(_DWORD *)(a1 + 512) = v8[4];
    *(_QWORD *)(a1 + 520) = *(_QWORD *)(v2 + 88);
    *(_DWORD *)(a1 + 528) = *(_WORD *)(v3 + 24) & 0xFFB7;
    *(_DWORD *)(a1 + 532) = *(_WORD *)(v3 + 26) & 7;
    *(_DWORD *)(a1 + 536) = *(unsigned __int8 *)(v3 + 19);
    v10 = *(_DWORD *)(v3 + 16) & 0xFFFFFF;
    *(_DWORD *)(a1 + 540) = v10;
    *(_BYTE *)(a1 + 750) = *(_BYTE *)(a1 + 750) & 0xFB | BYTE1(v10) & 4;
    *(_DWORD *)(a1 + 540) &= ~0x400u;
    v11 = (_WORD *)v5[3];
    if ( v11 && (*v11 & 0xFFF0) != 0xEC20 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
      }
      v15 = v5[3];
      *(_QWORD *)(a1 + 568) = v15;
      *(_QWORD *)(a1 + 560) = *(_QWORD *)(v15 + 24);
      v5[3] = 0;
      *(_BYTE *)(a1 + 749) &= ~0x40u;
      v16 = *(_QWORD *)(v15 + 80);
      if ( v16 )
      {
        v17 = *(_QWORD *)(v16 + 24);
        if ( v17 )
        {
          if ( (*(_WORD *)v17 & 0xFFF0) == 0xEC20 && (*(_DWORD *)(v17 + 156) & 0x4000000) != 0 )
            *(_BYTE *)(a1 + 750) |= 4u;
        }
      }
    }
    v12 = v5[8];
    if ( v12 )
    {
      v14 = *(_QWORD *)(v12 + 24);
      if ( v14 )
      {
        if ( (*(_DWORD *)(v14 + 156) & 0x4000000) != 0 )
          *(_BYTE *)(a1 + 750) |= 4u;
      }
    }
    v13 = (_WORD *)v5[4];
    if ( v13 && *v13 == 0xEB0F )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
      }
      *(_QWORD *)(a1 + 576) = v5[4];
      v5[4] = 0;
    }
    if ( (*(_BYTE *)(a1 + 746) & 2) != 0 )
      *(_DWORD *)(a1 + 540) |= 1u;
    *(_BYTE *)(a1 + 750) |= 2u;
  }
}

```

## disassembly

```asm
0x14000b0d0  push    rbx
0x14000b0d2  sub     rsp, 30h
0x14000b0d6  test    byte ptr [rcx+2EEh], 2
0x14000b0dd  mov     rbx, rcx
0x14000b0e0  jnz     loc_14000B200
0x14000b0e6  mov     [rsp+38h+arg_0], rbp
0x14000b0eb  mov     rbp, [rcx+28h]
0x14000b0ef  mov     [rsp+38h+arg_8], rsi
0x14000b0f4  mov     [rsp+38h+arg_10], rdi
0x14000b0f9  mov     [rsp+38h+arg_18], r14
0x14000b0fe  lea     r14, WPP_GLOBAL_Control
0x14000b105  mov     rdi, [rbp+0B8h]
0x14000b10c  mov     rax, [rdi+8]
0x14000b110  mov     rsi, [rdi+30h]
0x14000b114  mov     [rcx+220h], rax
0x14000b11b  mov     rcx, [rax+8]
0x14000b11f  test    rcx, rcx
0x14000b122  jz      short loc_14000B131
0x14000b124  mov     rcx, [rcx+40h]; SecurityDescriptor
0x14000b128  test    rcx, rcx
0x14000b12b  jnz     loc_1400274BC
0x14000b131  mov     rax, [rbx+220h]
0x14000b138  mov     rcx, [rax]
0x14000b13b  test    rcx, rcx
0x14000b13e  jnz     loc_14000B207
0x14000b144  mov     edx, 2
0x14000b149  mov     [rbx+228h], edx
0x14000b14f  mov     eax, [rax+10h]
0x14000b152  mov     [rbx+200h], eax
0x14000b158  mov     rax, [rbp+58h]
0x14000b15c  mov     [rbx+208h], rax
0x14000b163  movzx   eax, word ptr [rdi+18h]
0x14000b167  and     eax, 0DAFFB7h
0x14000b16c  mov     [rbx+210h], eax
0x14000b172  movzx   eax, word ptr [rdi+1Ah]
0x14000b176  and     eax, 7
0x14000b179  mov     [rbx+214h], eax
0x14000b17f  movzx   eax, byte ptr [rdi+13h]
0x14000b183  mov     [rbx+218h], eax
0x14000b189  mov     ecx, [rdi+10h]
0x14000b18c  and     ecx, 0FFFFFFh
0x14000b192  mov     [rbx+21Ch], ecx
0x14000b198  movzx   eax, byte ptr [rbx+2EEh]
0x14000b19f  shr     ecx, 8
0x14000b1a2  and     al, 0FBh
0x14000b1a4  and     cl, 4
0x14000b1a7  or      cl, al
0x14000b1a9  mov     [rbx+2EEh], cl
0x14000b1af  and     dword ptr [rbx+21Ch], 0FFFFFBFFh
0x14000b1b9  mov     rax, [rsi+18h]
0x14000b1bd  test    rax, rax
0x14000b1c0  jnz     short loc_14000B22D
0x14000b1c2  mov     rax, [rsi+40h]
0x14000b1c6  mov     rdi, [rsp+38h+arg_10]
0x14000b1cb  mov     rbp, [rsp+38h+arg_0]
0x14000b1d0  test    rax, rax
0x14000b1d3  jnz     short loc_14000B20F
0x14000b1d5  mov     rax, [rsi+20h]
0x14000b1d9  test    rax, rax
0x14000b1dc  jnz     loc_14000B2C3
0x14000b1e2  test    byte ptr [rbx+2EAh], 2
0x14000b1e9  mov     r14, [rsp+38h+arg_18]
0x14000b1ee  mov     rsi, [rsp+38h+arg_8]
0x14000b1f3  jnz     loc_14000B33D
0x14000b1f9  or      byte ptr [rbx+2EEh], 2
0x14000b200  add     rsp, 30h
0x14000b204  pop     rbx
0x14000b205  retn
0x14000b207  mov     edx, [rcx+4]
0x14000b20a  jmp     loc_14000B149
0x14000b20f  mov     rax, [rax+18h]
0x14000b213  test    rax, rax
0x14000b216  jz      short loc_14000B1D5
0x14000b218  test    dword ptr [rax+9Ch], 4000000h
0x14000b222  jz      short loc_14000B1D5
0x14000b224  or      byte ptr [rbx+2EEh], 4
0x14000b22b  jmp     short loc_14000B1D5
0x14000b22d  movzx   eax, word ptr [rax]
0x14000b230  mov     edi, 0FFF0h
0x14000b235  and     ax, di
0x14000b238  mov     ebp, 0EC20h
0x14000b23d  cmp     ax, bp
0x14000b240  jz      short loc_14000B1C2
0x14000b242  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b249  cmp     rcx, r14
0x14000b24c  jz      short loc_14000B259
0x14000b24e  mov     eax, [rcx+2Ch]
0x14000b251  test    al, 8
0x14000b253  jnz     loc_14000B2FC
0x14000b259  mov     rcx, [rsi+18h]
0x14000b25d  mov     [rbx+238h], rcx
0x14000b264  mov     rax, [rcx+18h]
0x14000b268  mov     [rbx+230h], rax
0x14000b26f  mov     qword ptr [rsi+18h], 0
0x14000b277  and     byte ptr [rbx+2EDh], 0BFh
0x14000b27e  mov     rax, [rcx+50h]
0x14000b282  test    rax, rax
0x14000b285  jz      loc_14000B1C2
0x14000b28b  mov     rcx, [rax+18h]
0x14000b28f  test    rcx, rcx
0x14000b292  jz      loc_14000B1C2
0x14000b298  movzx   eax, word ptr [rcx]
0x14000b29b  and     ax, di
0x14000b29e  cmp     ax, bp
0x14000b2a1  jnz     loc_14000B1C2
0x14000b2a7  test    dword ptr [rcx+9Ch], 4000000h
0x14000b2b1  jz      loc_14000B1C2
0x14000b2b7  or      byte ptr [rbx+2EEh], 4
0x14000b2be  jmp     loc_14000B1C2
0x14000b2c3  mov     ecx, 0EB0Fh
0x14000b2c8  cmp     cx, [rax]
0x14000b2cb  jnz     loc_14000B1E2
0x14000b2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b2d8  cmp     rcx, r14
0x14000b2db  jz      short loc_14000B2E4
0x14000b2dd  mov     eax, [rcx+2Ch]
0x14000b2e0  test    al, 8
0x14000b2e2  jnz     short loc_14000B320
0x14000b2e4  mov     rax, [rsi+20h]
0x14000b2e8  mov     [rbx+240h], rax
0x14000b2ef  mov     qword ptr [rsi+20h], 0
0x14000b2f7  jmp     loc_14000B1E2
0x14000b2fc  cmp     byte ptr [rcx+29h], 4
0x14000b300  jb      loc_14000B259
0x14000b306  mov     rcx, [rcx+18h]
0x14000b30a  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14000b311  mov     edx, 10h
0x14000b316  call    WPP_SF_
0x14000b31b  jmp     loc_14000B259
0x14000b320  cmp     byte ptr [rcx+29h], 4
0x14000b324  jb      short loc_14000B2E4
0x14000b326  mov     rcx, [rcx+18h]
0x14000b32a  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14000b331  mov     edx, 11h
0x14000b336  call    WPP_SF_
0x14000b33b  jmp     short loc_14000B2E4
0x14000b33d  or      dword ptr [rbx+21Ch], 1
0x14000b344  jmp     loc_14000B1F9
0x1400274bc  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400274c3  nop     dword ptr [rax+rax+00h]
0x1400274c8  mov     [rbx+2CCh], eax
0x1400274ce  mov     rcx, [rbx+220h]
0x1400274d5  mov     rdx, [rcx+8]
0x1400274d9  mov     rcx, [rdx+40h]
0x1400274dd  mov     [rbx+2C0h], rcx
0x1400274e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400274eb  cmp     rcx, r14
0x1400274ee  jz      loc_14000B131
0x1400274f4  mov     edx, [rcx+2Ch]
0x1400274f7  test    dl, 8
0x1400274fa  jz      short loc_140027522
0x1400274fc  cmp     byte ptr [rcx+29h], 4
0x140027500  jb      short loc_140027522
0x140027502  mov     r9, [rbx+220h]
0x140027509  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140027510  mov     rcx, [rcx+18h]
0x140027514  mov     edx, 0Eh
0x140027519  mov     [rsp+38h+var_18], eax
0x14002751d  call    WPP_SF_qD
0x140027522  mov     rcx, cs:WPP_GLOBAL_Control
0x140027529  cmp     rcx, r14
0x14002752c  jz      loc_14000B131
0x140027532  mov     eax, [rcx+2Ch]
0x140027535  test    al, 8
0x140027537  jz      loc_14000B131
0x14002753d  cmp     byte ptr [rcx+29h], 2
0x140027541  jb      loc_14000B131
0x140027547  mov     eax, [rbx+2CCh]
0x14002754d  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140027554  mov     r9, [rbx+220h]
0x14002755b  mov     edx, 0Fh
0x140027560  mov     rcx, [rcx+18h]
0x140027564  mov     [rsp+38h+var_18], eax
0x140027568  call    WPP_SF_qD
0x14002756d  nop
0x14002756e  jmp     loc_14000B131
```
