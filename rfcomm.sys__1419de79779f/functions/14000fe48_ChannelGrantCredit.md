# ChannelGrantCredit

- ea: `0x14000fe48`
- end: `0x140010077`
- name: `ChannelGrantCredit`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400097f4`

## callees

- `0x140003bf4`
- `0x14000c704`
- `0x14000fe48`
- `0x140010260`
- `0x1400135cc`
- `0x140013abc`
- `0x140016b84`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fecf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fecf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff2a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ff2a`

## string_xrefs

- `0x14000ffe6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
void __fastcall ChannelGrantCredit(__int64 a1, int a2)
{
  _DWORD *v3; // rdi
  _DWORD *v4; // rsi
  __int64 v5; // rbp
  char v6; // r14
  char v7; // r12
  __int64 v8; // r13
  unsigned int v9; // r15d
  _DWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-78h]
  unsigned int v14; // [rsp+A0h] [rbp+8h] BYREF

  v3 = (_DWORD *)(a1 + 192);
  v4 = (_DWORD *)(a1 + 188);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdd(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      26,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1,
      *v4,
      *v3);
  v5 = *(_QWORD *)(a1 + 56);
  if ( *(_BYTE *)(v5 + 465) )
  {
    v6 = 0;
    v7 = 0;
    v8 = 0;
    *(_BYTE *)(v5 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 56));
    v9 = ++*v4 - *v3;
    if ( 2 * *v3 <= *v4 )
    {
      v10 = v3;
    }
    else
    {
      if ( *v4 != 32 || v9 < 4 )
      {
LABEL_12:
        KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 56), *(_BYTE *)(v5 + 64));
        if ( v7 )
        {
          ChannelSendData(a1);
        }
        else if ( v6 )
        {
          RfcommFrameWrite(v5, v8);
        }
        goto LABEL_14;
      }
      v10 = (_DWORD *)(a1 + 192);
    }
    if ( *(_DWORD *)(a1 + 228) )
    {
      if ( *(_QWORD *)(a1 + 104) != a1 + 104 )
      {
        v7 = 1;
        goto LABEL_12;
      }
    }
    else
    {
      v10 = v3;
    }
    v6 = 0;
    v14 = 0;
    v11 = RfcommFrameAllocLockedEx(v5, (__int64 *)a1, 239, 0, *(_BYTE *)(a1 + 184), 0, &v14, a1 + 120, 0);
    v8 = v11;
    if ( v11 )
    {
      RefObj_AddRefEx(v11 + 24, 1346917442, 1208, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
      v12 = *(_QWORD *)(v8 + 144);
      v6 = 1;
      *v10 += v9;
      *(_BYTE *)(v12 - 1) = v9;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dDd(
          WPP_GLOBAL_Control->DeviceExtension,
          *(unsigned __int8 *)(a1 + 184),
          9,
          27,
          v13,
          v9,
          *(_BYTE *)(a1 + 184),
          *v10);
    }
    goto LABEL_12;
  }
LABEL_14:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      28,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
}

```

## disassembly

```asm
0x14000fe48  push    rbx
0x14000fe4a  push    rbp
0x14000fe4b  push    rsi
0x14000fe4c  push    rdi
0x14000fe4d  push    r12
0x14000fe4f  push    r13
0x14000fe51  push    r14
0x14000fe53  push    r15
0x14000fe55  sub     rsp, 58h
0x14000fe59  mov     rbx, rcx
0x14000fe5c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fe63  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fe6a  lea     rdi, [rcx+0C0h]
0x14000fe71  lea     rsi, [rcx+0BCh]
0x14000fe78  lea     r14, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14000fe7f  jz      short loc_14000FEB1
0x14000fe81  mov     eax, [rdi]
0x14000fe83  mov     r9d, 1Ah
0x14000fe89  mov     dword ptr [rsp+98h+var_60], eax
0x14000fe8d  mov     eax, [rsi]
0x14000fe8f  mov     dword ptr [rsp+98h+var_68], eax
0x14000fe93  mov     [rsp+98h+var_70], rcx
0x14000fe98  lea     r8d, [r9-17h]
0x14000fe9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fea3  mov     [rsp+98h+var_78], r14
0x14000fea8  mov     rcx, [rcx+40h]
0x14000feac  call    WPP_RECORDER_SF_qdd
0x14000feb1  mov     rbp, [rbx+38h]
0x14000feb5  cmp     byte ptr [rbp+1D1h], 0
0x14000febc  jz      loc_14001006B
0x14000fec2  lea     rcx, [rbp+38h]; SpinLock
0x14000fec6  xor     r14b, r14b
0x14000fec9  xor     r12b, r12b
0x14000fecc  xor     r13d, r13d
0x14000fecf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fed6  nop     dword ptr [rax+rax+00h]
0x14000fedb  mov     [rbp+40h], al
0x14000fede  inc     dword ptr [rsi]
0x14000fee0  mov     ecx, [rsi]
0x14000fee2  mov     r15d, ecx
0x14000fee5  mov     eax, [rdi]
0x14000fee7  sub     r15d, eax
0x14000feea  add     eax, eax
0x14000feec  cmp     eax, ecx
0x14000feee  jle     short loc_14000FF04
0x14000fef0  cmp     ecx, 20h ; ' '
0x14000fef3  jnz     short loc_14000FF1C
0x14000fef5  cmp     r15d, 4
0x14000fef9  jb      short loc_14000FF1C
0x14000fefb  lea     rsi, [rbx+0C0h]
0x14000ff02  jmp     short loc_14000FF07
0x14000ff04  mov     rsi, rdi
0x14000ff07  cmp     [rbx+0E4h], r13d
0x14000ff0e  jz      short loc_14000FF88
0x14000ff10  lea     rax, [rbx+68h]
0x14000ff14  cmp     [rax], rax
0x14000ff17  jz      short loc_14000FF8B
0x14000ff19  mov     r12b, 1
0x14000ff1c  lea     rdi, WPP_RECORDER_INITIALIZED
0x14000ff23  mov     dl, [rbp+40h]; NewIrql
0x14000ff26  lea     rcx, [rbp+38h]; SpinLock
0x14000ff2a  call    cs:__imp_KeReleaseSpinLock
0x14000ff31  nop     dword ptr [rax+rax+00h]
0x14000ff36  test    r12b, r12b
0x14000ff39  jz      loc_140010052
0x14000ff3f  mov     rcx, rbx
0x14000ff42  call    ChannelSendData
0x14000ff47  lea     r14, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14000ff4e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000ff55  jz      short loc_14000FF76
0x14000ff57  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff5e  mov     r9d, 1Ch
0x14000ff64  mov     [rsp+98h+var_78], r14
0x14000ff69  mov     rcx, [rcx+40h]
0x14000ff6d  lea     r8d, [r9-19h]
0x14000ff71  call    WPP_RECORDER_SF_
0x14000ff76  add     rsp, 58h
0x14000ff7a  pop     r15
0x14000ff7c  pop     r14
0x14000ff7e  pop     r13
0x14000ff80  pop     r12
0x14000ff82  pop     rdi
0x14000ff83  pop     rsi
0x14000ff84  pop     rbp
0x14000ff85  pop     rbx
0x14000ff86  retn
0x14000ff88  mov     rsi, rdi
0x14000ff8b  xor     r14d, r14d
0x14000ff8e  lea     rax, [rbx+78h]
0x14000ff92  mov     [rsp+98h+var_58], r14b
0x14000ff97  xor     r9d, r9d
0x14000ff9a  mov     [rsp+98h+var_60], rax
0x14000ff9f  mov     r8b, 0EFh
0x14000ffa2  lea     rax, [rsp+98h+arg_0]
0x14000ffaa  mov     [rsp+98h+arg_0], r14d
0x14000ffb2  mov     [rsp+98h+var_68], rax
0x14000ffb7  mov     rdx, rbx
0x14000ffba  mov     al, [rbx+0B8h]
0x14000ffc0  mov     rcx, rbp
0x14000ffc3  mov     dword ptr [rsp+98h+var_70], r14d
0x14000ffc8  mov     byte ptr [rsp+98h+var_78], al
0x14000ffcc  call    RfcommFrameAllocLockedEx
0x14000ffd1  mov     r13, rax
0x14000ffd4  test    rax, rax
0x14000ffd7  jz      loc_14000FF1C
0x14000ffdd  lea     rcx, [rax+18h]
0x14000ffe1  mov     edx, 50485442h
0x14000ffe6  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ffed  mov     r8d, 4B8h
0x14000fff3  call    RefObj_AddRefEx
0x14000fff8  mov     rax, [r13+90h]
0x14000ffff  mov     r14b, 1
0x140010002  add     [rsi], r15d
0x140010005  mov     [rax-1], r15b
0x140010009  lea     rdi, WPP_RECORDER_INITIALIZED
0x140010010  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140010017  jz      loc_14000FF23
0x14001001d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010024  mov     r9d, 1Bh
0x14001002a  movzx   edx, byte ptr [rbx+0B8h]
0x140010031  mov     eax, [rsi]
0x140010033  mov     dword ptr [rsp+98h+var_60], eax
0x140010037  mov     rcx, [rcx+40h]
0x14001003b  lea     r8d, [r9-12h]
0x14001003f  mov     dword ptr [rsp+98h+var_68], edx
0x140010043  mov     dword ptr [rsp+98h+var_70], r15d
0x140010048  call    WPP_RECORDER_SF_dDd
0x14001004d  jmp     loc_14000FF23
0x140010052  test    r14b, r14b
0x140010055  jz      loc_14000FF47
0x14001005b  mov     rdx, r13
0x14001005e  mov     rcx, rbp
0x140010061  call    RfcommFrameWrite
0x140010066  jmp     loc_14000FF47
0x14001006b  lea     rdi, WPP_RECORDER_INITIALIZED
0x140010072  jmp     loc_14000FF4E
```
