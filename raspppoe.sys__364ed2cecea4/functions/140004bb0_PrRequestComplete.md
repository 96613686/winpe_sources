# PrRequestComplete

- ea: `0x140004bb0`
- end: `0x140004e01`
- name: `PrRequestComplete`
- size: `593`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000ec30`
- `0x14000ed48`
- `0x14000ee60`
- `0x14000f1ac`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140004bb0`

## import_xrefs

- `NDIS!NdisSetEvent` at `0x140004dbe`
- `NDIS!NdisSetEvent` at `0x140004dbe`

## pseudocode

```c
void __fastcall PrRequestComplete(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // r9
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  unsigned int v10; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v6 = *(unsigned int *)(a2 + 4);
  if ( !(_DWORD)v6 )
  {
    v6 = *(unsigned int *)(a2 + 32);
    switch ( *(_DWORD *)(a2 + 32) )
    {
      case 0x10106:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a3);
        }
        *(_DWORD *)(a1 + 24) |= 8u;
        break;
      case 0x10107:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a3);
        }
        *(_DWORD *)(a1 + 24) |= 4u;
        break;
      case 0x1010102:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a3);
        }
        *(_DWORD *)(a1 + 24) |= 2u;
        break;
      default:
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v8 = 56;
          goto LABEL_11;
        }
        goto LABEL_49;
    }
LABEL_48:
    *(_DWORD *)(a1 + 48) = a3;
    NdisSetEvent((PNDIS_EVENT)(a1 + 296));
    goto LABEL_49;
  }
  if ( (_DWORD)v6 != 1 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v8 = 59;
LABEL_11:
      WPP_SF_d(v7->AttachedDevice, v8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, v6);
      goto LABEL_49;
    }
    goto LABEL_49;
  }
  v6 = *(unsigned int *)(a2 + 32);
  if ( (_DWORD)v6 == 65806 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, a3);
    }
    if ( !a3 )
    {
      v9 = *(_DWORD *)(a1 + 24);
      if ( (v9 & 0x40) != 0 )
        v10 = v9 & 0xFFFFFFBF;
      else
        v10 = v9 | 0x40;
      *(_DWORD *)(a1 + 24) = v10;
    }
    goto LABEL_48;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    v8 = 58;
    goto LABEL_11;
  }
LABEL_49:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x140004bb0  push    rbx
0x140004bb2  push    rsi
0x140004bb3  push    rdi
0x140004bb4  push    r14
0x140004bb6  push    r15
0x140004bb8  sub     rsp, 20h
0x140004bbc  mov     esi, r8d
0x140004bbf  mov     rdi, rdx
0x140004bc2  mov     rbx, rcx
0x140004bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bcc  lea     r14, WPP_GLOBAL_Control
0x140004bd3  lea     r15, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140004bda  cmp     rcx, r14
0x140004bdd  jz      short loc_140004BFD
0x140004bdf  mov     eax, [rcx+2Ch]
0x140004be2  test    al, 4
0x140004be4  jz      short loc_140004BFD
0x140004be6  cmp     byte ptr [rcx+29h], 2
0x140004bea  jb      short loc_140004BFD
0x140004bec  mov     rcx, [rcx+18h]
0x140004bf0  mov     edx, 34h ; '4'
0x140004bf5  mov     r8, r15
0x140004bf8  call    WPP_SF_
0x140004bfd  mov     r9d, [rdi+4]
0x140004c01  test    r9d, r9d
0x140004c04  jz      loc_140004CD0
0x140004c0a  cmp     r9d, 1
0x140004c0e  jz      short loc_140004C4B
0x140004c10  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c17  cmp     rcx, r14
0x140004c1a  jz      loc_140004DCA
0x140004c20  mov     eax, [rcx+2Ch]
0x140004c23  test    al, 4
0x140004c25  jz      loc_140004DCA
0x140004c2b  cmp     byte ptr [rcx+29h], 3
0x140004c2f  jb      loc_140004DCA
0x140004c35  mov     edx, 3Bh ; ';'
0x140004c3a  mov     rcx, [rcx+18h]
0x140004c3e  mov     r8, r15
0x140004c41  call    WPP_SF_d
0x140004c46  jmp     loc_140004DCA
0x140004c4b  mov     r9d, [rdi+20h]
0x140004c4f  cmp     r9d, 1010Eh
0x140004c56  jz      short loc_140004C84
0x140004c58  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c5f  cmp     rcx, r14
0x140004c62  jz      loc_140004DCA
0x140004c68  mov     eax, [rcx+2Ch]
0x140004c6b  test    al, 4
0x140004c6d  jz      loc_140004DCA
0x140004c73  cmp     byte ptr [rcx+29h], 3
0x140004c77  jb      loc_140004DCA
0x140004c7d  mov     edx, 3Ah ; ':'
0x140004c82  jmp     short loc_140004C3A
0x140004c84  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c8b  cmp     rcx, r14
0x140004c8e  jz      short loc_140004CB1
0x140004c90  mov     eax, [rcx+2Ch]
0x140004c93  test    al, 4
0x140004c95  jz      short loc_140004CB1
0x140004c97  cmp     byte ptr [rcx+29h], 3
0x140004c9b  jb      short loc_140004CB1
0x140004c9d  mov     rcx, [rcx+18h]
0x140004ca1  mov     edx, 39h ; '9'
0x140004ca6  mov     r9d, esi
0x140004ca9  mov     r8, r15
0x140004cac  call    WPP_SF_d
0x140004cb1  test    esi, esi
0x140004cb3  jnz     loc_140004DB4
0x140004cb9  mov     eax, [rbx+18h]
0x140004cbc  test    al, 40h
0x140004cbe  jz      short loc_140004CCB
0x140004cc0  and     eax, 0FFFFFFBFh
0x140004cc3  mov     [rbx+18h], eax
0x140004cc6  jmp     loc_140004DB4
0x140004ccb  or      eax, 40h
0x140004cce  jmp     short loc_140004CC3
0x140004cd0  mov     r9d, [rdi+20h]
0x140004cd4  mov     eax, r9d
0x140004cd7  sub     eax, 10106h
0x140004cdc  jz      loc_140004D83
0x140004ce2  sub     eax, 1
0x140004ce5  jz      short loc_140004D50
0x140004ce7  cmp     eax, 0FFFFFBh
0x140004cec  jz      short loc_140004D1D
0x140004cee  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cf5  cmp     rcx, r14
0x140004cf8  jz      loc_140004DCA
0x140004cfe  mov     eax, [rcx+2Ch]
0x140004d01  test    al, 4
0x140004d03  jz      loc_140004DCA
0x140004d09  cmp     byte ptr [rcx+29h], 3
0x140004d0d  jb      loc_140004DCA
0x140004d13  mov     edx, 38h ; '8'
0x140004d18  jmp     loc_140004C3A
0x140004d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d24  cmp     rcx, r14
0x140004d27  jz      short loc_140004D4A
0x140004d29  mov     eax, [rcx+2Ch]
0x140004d2c  test    al, 4
0x140004d2e  jz      short loc_140004D4A
0x140004d30  cmp     byte ptr [rcx+29h], 3
0x140004d34  jb      short loc_140004D4A
0x140004d36  mov     rcx, [rcx+18h]
0x140004d3a  mov     edx, 35h ; '5'
0x140004d3f  mov     r9d, esi
0x140004d42  mov     r8, r15
0x140004d45  call    WPP_SF_d
0x140004d4a  or      dword ptr [rbx+18h], 2
0x140004d4e  jmp     short loc_140004DB4
0x140004d50  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d57  cmp     rcx, r14
0x140004d5a  jz      short loc_140004D7D
0x140004d5c  mov     eax, [rcx+2Ch]
0x140004d5f  test    al, 4
0x140004d61  jz      short loc_140004D7D
0x140004d63  cmp     byte ptr [rcx+29h], 3
0x140004d67  jb      short loc_140004D7D
0x140004d69  mov     rcx, [rcx+18h]
0x140004d6d  mov     edx, 36h ; '6'
0x140004d72  mov     r9d, esi
0x140004d75  mov     r8, r15
0x140004d78  call    WPP_SF_d
0x140004d7d  or      dword ptr [rbx+18h], 4
0x140004d81  jmp     short loc_140004DB4
0x140004d83  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d8a  cmp     rcx, r14
0x140004d8d  jz      short loc_140004DB0
0x140004d8f  mov     eax, [rcx+2Ch]
0x140004d92  test    al, 4
0x140004d94  jz      short loc_140004DB0
0x140004d96  cmp     byte ptr [rcx+29h], 3
0x140004d9a  jb      short loc_140004DB0
0x140004d9c  mov     rcx, [rcx+18h]
0x140004da0  mov     edx, 37h ; '7'
0x140004da5  mov     r9d, esi
0x140004da8  mov     r8, r15
0x140004dab  call    WPP_SF_d
0x140004db0  or      dword ptr [rbx+18h], 8
0x140004db4  lea     rcx, [rbx+128h]; Event
0x140004dbb  mov     [rbx+30h], esi
0x140004dbe  call    cs:__imp_NdisSetEvent
0x140004dc5  nop     dword ptr [rax+rax+00h]
0x140004dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dd1  cmp     rcx, r14
0x140004dd4  jz      short loc_140004DF4
0x140004dd6  mov     eax, [rcx+2Ch]
0x140004dd9  test    al, 4
0x140004ddb  jz      short loc_140004DF4
0x140004ddd  cmp     byte ptr [rcx+29h], 2
0x140004de1  jb      short loc_140004DF4
0x140004de3  mov     rcx, [rcx+18h]
0x140004de7  mov     edx, 3Ch ; '<'
0x140004dec  mov     r8, r15
0x140004def  call    WPP_SF_
0x140004df4  add     rsp, 20h
0x140004df8  pop     r15
0x140004dfa  pop     r14
0x140004dfc  pop     rdi
0x140004dfd  pop     rsi
0x140004dfe  pop     rbx
0x140004dff  retn
```
