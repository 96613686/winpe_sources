# TpCallStateChangeHandler

- ea: `0x140002b4c`
- end: `0x140002e03`
- name: `TpCallStateChangeHandler`
- size: `695`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400035b8`
- `0x1400161c0`
- `0x140016534`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140002520`
- `0x140002b4c`
- `0x140003f00`
- `0x140017cf0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002c8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002dbf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c8d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002dbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ba0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d73`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002ba0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002d73`
- `NDIS!NdisMCmActivateVc` at `0x140002d18`
- `NDIS!NdisMCmActivateVc` at `0x140002d18`

## pseudocode

```c
void __fastcall TpCallStateChangeHandler(__int64 a1, int a2, int a3)
{
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  unsigned __int16 v8; // dx
  __int64 v9; // rcx
  int v10; // eax
  KIRQL v11; // dl
  __int64 v12; // rdx
  __int64 v13; // r8
  NDIS_STATUS v14; // eax
  unsigned int v15; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x56u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  if ( a2 != 256 || (v6 = *(_DWORD *)(a1 + 128), v6 == 2) || v6 == 512 )
  {
    if ( *(_DWORD *)(a1 + 128) == a2 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v8 = 88;
        goto LABEL_12;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 128) = a2;
      if ( a2 == 256 )
      {
        v9 = *(_QWORD *)(a1 + 96);
        *(_DWORD *)(a1 + 80) &= ~2u;
        *(_QWORD *)(a1 + 140) = 0;
        *(_QWORD *)(a1 + 148) = 0;
        *(_QWORD *)(a1 + 156) = 0;
        v10 = *(_DWORD *)(a1 + 124);
        v11 = *(_BYTE *)(a1 + 64);
        *(_DWORD *)(a1 + 132) = v10;
        *(_DWORD *)(a1 + 136) = v10;
        *(_DWORD *)(a1 + 140) = *(_DWORD *)(v9 + 116);
        *(_DWORD *)(a1 + 144) = *(_DWORD *)(v9 + 116);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), v11);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_dddd(
              WPP_GLOBAL_Control->AttachedDevice,
              v12,
              v13,
              *(unsigned int *)(a1 + 140),
              *(_DWORD *)(a1 + 144),
              *(_DWORD *)(a1 + 156),
              *(_DWORD *)(a1 + 160));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x5Au,
              (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
          }
        }
        v14 = NdisMCmActivateVc(*(NDIS_HANDLE *)(a1 + 168), *(PCO_CALL_PARAMETERS *)(a1 + 176));
        v15 = v14;
        if ( v14 != 259 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids, a1, v14);
          }
          PppoeCmActivateVcComplete(v15, a1);
        }
        *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
      }
      else if ( a2 == 0x4000
             && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_d(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x5Cu,
          (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids,
          a3);
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v8 = 87;
LABEL_12:
      WPP_SF_((__int64)v7->AttachedDevice, v8, (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x5Du,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
}

```

## disassembly

```asm
0x140002b4c  push    rbx
0x140002b4e  push    rbp
0x140002b4f  push    rsi
0x140002b50  push    rdi
0x140002b51  push    r12
0x140002b53  push    r13
0x140002b55  sub     rsp, 48h
0x140002b59  mov     ebp, r8d
0x140002b5c  mov     edi, edx
0x140002b5e  mov     rbx, rcx
0x140002b61  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b68  lea     r12, WPP_GLOBAL_Control
0x140002b6f  lea     r13, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002b76  cmp     rcx, r12
0x140002b79  jz      short loc_140002B99
0x140002b7b  mov     eax, [rcx+2Ch]
0x140002b7e  test    al, 2
0x140002b80  jz      short loc_140002B99
0x140002b82  cmp     byte ptr [rcx+29h], 3
0x140002b86  jb      short loc_140002B99
0x140002b88  mov     rcx, [rcx+18h]
0x140002b8c  mov     edx, 56h ; 'V'
0x140002b91  mov     r8, r13
0x140002b94  call    WPP_SF_
0x140002b99  lea     rsi, [rbx+38h]
0x140002b9d  mov     rcx, rsi; SpinLock
0x140002ba0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002ba7  nop     dword ptr [rax+rax+00h]
0x140002bac  mov     ecx, 100h
0x140002bb1  mov     [rbx+40h], al
0x140002bb4  cmp     edi, ecx
0x140002bb6  jnz     short loc_140002C05
0x140002bb8  mov     eax, [rbx+80h]
0x140002bbe  cmp     eax, 2
0x140002bc1  jz      short loc_140002C05
0x140002bc3  cmp     eax, 200h
0x140002bc8  jz      short loc_140002C05
0x140002bca  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bd1  cmp     rcx, r12
0x140002bd4  jz      loc_140002DB9
0x140002bda  mov     eax, [rcx+2Ch]
0x140002bdd  test    al, 2
0x140002bdf  jz      loc_140002DB9
0x140002be5  cmp     byte ptr [rcx+29h], 3
0x140002be9  jb      loc_140002DB9
0x140002bef  mov     edx, 57h ; 'W'
0x140002bf4  mov     rcx, [rcx+18h]
0x140002bf8  mov     r8, r13
0x140002bfb  call    WPP_SF_
0x140002c00  jmp     loc_140002DB9
0x140002c05  cmp     [rbx+80h], edi
0x140002c0b  jnz     short loc_140002C39
0x140002c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c14  cmp     rcx, r12
0x140002c17  jz      loc_140002DB9
0x140002c1d  mov     eax, [rcx+2Ch]
0x140002c20  test    al, 2
0x140002c22  jz      loc_140002DB9
0x140002c28  cmp     byte ptr [rcx+29h], 3
0x140002c2c  jb      loc_140002DB9
0x140002c32  mov     edx, 58h ; 'X'
0x140002c37  jmp     short loc_140002BF4
0x140002c39  mov     [rbx+80h], edi
0x140002c3f  cmp     edi, ecx
0x140002c41  jnz     loc_140002D84
0x140002c47  mov     rcx, [rbx+60h]
0x140002c4b  xor     eax, eax
0x140002c4d  and     dword ptr [rbx+50h], 0FFFFFFFDh
0x140002c51  mov     [rbx+8Ch], rax
0x140002c58  mov     [rbx+94h], rax
0x140002c5f  mov     [rbx+9Ch], rax
0x140002c66  mov     eax, [rbx+7Ch]
0x140002c69  mov     dl, [rbx+40h]; NewIrql
0x140002c6c  mov     [rbx+84h], eax
0x140002c72  mov     [rbx+88h], eax
0x140002c78  mov     eax, [rcx+74h]
0x140002c7b  mov     [rbx+8Ch], eax
0x140002c81  mov     eax, [rcx+74h]
0x140002c84  mov     rcx, rsi; SpinLock
0x140002c87  mov     [rbx+90h], eax
0x140002c8d  call    cs:__imp_KeReleaseSpinLock
0x140002c94  nop     dword ptr [rax+rax+00h]
0x140002c99  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ca0  cmp     rcx, r12
0x140002ca3  jz      short loc_140002D0A
0x140002ca5  mov     eax, [rcx+2Ch]
0x140002ca8  test    al, 2
0x140002caa  jz      short loc_140002CE0
0x140002cac  cmp     byte ptr [rcx+29h], 3
0x140002cb0  jb      short loc_140002CE0
0x140002cb2  mov     eax, [rbx+0A0h]
0x140002cb8  mov     r9d, [rbx+8Ch]
0x140002cbf  mov     rcx, [rcx+18h]
0x140002cc3  mov     [rsp+78h+var_48], eax
0x140002cc7  mov     eax, [rbx+9Ch]
0x140002ccd  mov     [rsp+78h+var_50], eax
0x140002cd1  mov     eax, [rbx+90h]
0x140002cd7  mov     [rsp+78h+var_58], eax
0x140002cdb  call    WPP_SF_dddd
0x140002ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x140002ce7  cmp     rcx, r12
0x140002cea  jz      short loc_140002D0A
0x140002cec  mov     eax, [rcx+2Ch]
0x140002cef  test    al, 2
0x140002cf1  jz      short loc_140002D0A
0x140002cf3  cmp     byte ptr [rcx+29h], 3
0x140002cf7  jb      short loc_140002D0A
0x140002cf9  mov     rcx, [rcx+18h]
0x140002cfd  mov     edx, 5Ah ; 'Z'
0x140002d02  mov     r8, r13
0x140002d05  call    WPP_SF_
0x140002d0a  mov     rdx, [rbx+0B0h]; CallParameters
0x140002d11  mov     rcx, [rbx+0A8h]; NdisVcHandle
0x140002d18  call    cs:__imp_NdisMCmActivateVc
0x140002d1f  nop     dword ptr [rax+rax+00h]
0x140002d24  mov     edi, eax
0x140002d26  cmp     eax, 103h
0x140002d2b  jz      short loc_140002D70
0x140002d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d34  cmp     rcx, r12
0x140002d37  jz      short loc_140002D5F
0x140002d39  mov     edx, [rcx+2Ch]
0x140002d3c  test    dl, 2
0x140002d3f  jz      short loc_140002D5F
0x140002d41  cmp     byte ptr [rcx+29h], 3
0x140002d45  jb      short loc_140002D5F
0x140002d47  mov     rcx, [rcx+18h]
0x140002d4b  mov     edx, 5Bh ; '['
0x140002d50  mov     r9, rbx
0x140002d53  mov     [rsp+78h+var_58], eax
0x140002d57  mov     r8, r13
0x140002d5a  call    WPP_SF_qd
0x140002d5f  mov     r8, [rbx+0B0h]
0x140002d66  mov     rdx, rbx
0x140002d69  mov     ecx, edi
0x140002d6b  call    PppoeCmActivateVcComplete
0x140002d70  mov     rcx, rsi; SpinLock
0x140002d73  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002d7a  nop     dword ptr [rax+rax+00h]
0x140002d7f  mov     [rbx+40h], al
0x140002d82  jmp     short loc_140002DB9
0x140002d84  cmp     edi, 4000h
0x140002d8a  jnz     short loc_140002DB9
0x140002d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d93  cmp     rcx, r12
0x140002d96  jz      short loc_140002DB9
0x140002d98  mov     eax, [rcx+2Ch]
0x140002d9b  test    al, 2
0x140002d9d  jz      short loc_140002DB9
0x140002d9f  cmp     byte ptr [rcx+29h], 3
0x140002da3  jb      short loc_140002DB9
0x140002da5  mov     rcx, [rcx+18h]
0x140002da9  mov     edx, 5Ch ; '\'
0x140002dae  mov     r9d, ebp
0x140002db1  mov     r8, r13
0x140002db4  call    WPP_SF_d
0x140002db9  mov     dl, [rbx+40h]; NewIrql
0x140002dbc  mov     rcx, rsi; SpinLock
0x140002dbf  call    cs:__imp_KeReleaseSpinLock
0x140002dc6  nop     dword ptr [rax+rax+00h]
0x140002dcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140002dd2  cmp     rcx, r12
0x140002dd5  jz      short loc_140002DF5
0x140002dd7  mov     eax, [rcx+2Ch]
0x140002dda  test    al, 2
0x140002ddc  jz      short loc_140002DF5
0x140002dde  cmp     byte ptr [rcx+29h], 3
0x140002de2  jb      short loc_140002DF5
0x140002de4  mov     rcx, [rcx+18h]
0x140002de8  mov     edx, 5Dh ; ']'
0x140002ded  mov     r8, r13
0x140002df0  call    WPP_SF_
0x140002df5  add     rsp, 48h
0x140002df9  pop     r13
0x140002dfb  pop     r12
0x140002dfd  pop     rdi
0x140002dfe  pop     rsi
0x140002dff  pop     rbp
0x140002e00  pop     rbx
0x140002e01  retn
```
