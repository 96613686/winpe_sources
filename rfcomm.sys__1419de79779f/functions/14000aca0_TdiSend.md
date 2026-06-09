# TdiSend

- ea: `0x14000aca0`
- end: `0x14000b086`
- name: `TdiSend`
- size: `998`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004684`
- `0x140004a68`
- `0x140005c38`
- `0x14000aba8`
- `0x14000aca0`
- `0x14000c838`
- `0x140010810`
- `0x14001ea34`
- `0x14001ec2c`
- `0x14001ed50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ad1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ae41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ad1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ae41`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ad7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000adb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aff9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b041`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ad7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000adb2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ae95`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aff9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b041`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x14000af9a`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x14000af9a`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x14000aee5`
- `ntoskrnl!IoIncrementKeepAliveCount` at `0x14000aee5`

## string_xrefs

- `0x14000b060`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiSend(__int64 a1, IRP *a2, __int64 a3, _DWORD *a4, _QWORD *a5)
{
  _MDL *MdlAddress; // rax
  int v6; // ebx
  unsigned int v10; // ebx
  KIRQL v11; // al
  int v12; // edx
  int v13; // r9d
  int v14; // edx
  int v15; // edx
  __int64 v16; // r13
  int v17; // eax
  KIRQL v18; // dl
  KSPIN_LOCK *v19; // rcx
  int v20; // edx
  int v21; // r8d
  int v22; // edx
  int v23; // eax
  int v24; // edx
  int v25; // edx

  MdlAddress = a2->MdlAddress;
  v6 = 0;
  while ( MdlAddress )
  {
    v6 += MdlAddress->ByteCount;
    MdlAddress = MdlAddress->Next;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qdq(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)a2, a3, 122);
  if ( !a3 )
    return (unsigned int)-1073741811;
  v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  *(_BYTE *)(a3 + 56) = v11;
  if ( *(_BYTE *)(a3 + 828) && !*(_BYTE *)(a3 + 829) )
  {
    v10 = -1073741790;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_13:
      KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
      return v10;
    }
    v13 = 123;
LABEL_12:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      19,
      v13,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v10);
    goto LABEL_13;
  }
  if ( *(_BYTE *)(a3 + 820) )
  {
    v10 = -1073740682;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_13;
    v13 = 124;
    goto LABEL_12;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), v11);
  if ( v6 != *a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Dd(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        2,
        125,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v6,
        *a4);
    return (unsigned int)-1073741811;
  }
  if ( !*a4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        2,
        126,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    return 0;
  }
  *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  v16 = TdiReferenceChannelLocked(a3, 1313754947);
  if ( v16 && *(_BYTE *)(a3 + 97) )
  {
    v17 = IrpList_EnqueueEx(a3 + 456, a2);
    v18 = *(_BYTE *)(a3 + 56);
    v10 = v17;
    v19 = (KSPIN_LOCK *)(a3 + 48);
    if ( v17 < 0 )
    {
      KeReleaseSpinLock(v19, v18);
    }
    else
    {
      KeReleaseSpinLock(v19, v18);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qdq(WPP_GLOBAL_Control->DeviceExtension, v20, v21, 128);
      if ( *(_QWORD *)(a3 + 88)
        && (int)IoIncrementKeepAliveCount(*(_QWORD *)(a3 + 72)) < 0
        && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          2,
          129,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
      }
      v23 = ChannelWrite(v16, a2->MdlAddress, (unsigned int)*a4, a2);
      v10 = v23;
      if ( v23 != 259 )
      {
        if ( v23 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v24,
            1,
            130,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
        if ( (unsigned __int8)IrpList_DequeueIrp(a3 + 456, a2) )
        {
          if ( *(_QWORD *)(a3 + 88)
            && (int)IoDecrementKeepAliveCount(*(_QWORD *)(a3 + 72)) < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v25,
              2,
              131,
              (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
          }
          if ( (v10 & 0x80000000) != 0 )
          {
            *a5 = 0;
            RfcommCompleteTdiIrp(a2);
          }
        }
        v10 = 259;
      }
    }
LABEL_49:
    RefObj_ReleaseEx(v16 + 24, 1313754947, 3559, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    return v10;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      15,
      127,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a3);
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
  v10 = -1073741299;
  if ( v16 )
    goto LABEL_49;
  return v10;
}

```

## disassembly

```asm
0x14000aca0  push    rbx
0x14000aca2  push    rbp
0x14000aca3  push    rsi
0x14000aca4  push    rdi
0x14000aca5  push    r12
0x14000aca7  push    r13
0x14000aca9  push    r14
0x14000acab  push    r15
0x14000acad  sub     rsp, 48h
0x14000acb1  mov     rax, [rdx+8]
0x14000acb5  xor     r12d, r12d
0x14000acb8  mov     ebx, r12d
0x14000acbb  mov     r15, r9
0x14000acbe  mov     rdi, r8
0x14000acc1  mov     r14, rdx
0x14000acc4  jmp     short loc_14000ACCC
0x14000acc6  add     ebx, [rax+28h]
0x14000acc9  mov     rax, [rax]
0x14000accc  test    rax, rax
0x14000accf  jnz     short loc_14000ACC6
0x14000acd1  lea     rsi, WPP_RECORDER_INITIALIZED
0x14000acd8  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000acdf  jz      short loc_14000AD06
0x14000ace1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ace8  lea     r9d, [rax+7Ah]
0x14000acec  mov     eax, [r15]
0x14000acef  mov     [rsp+88h+var_50], r14
0x14000acf4  mov     [rsp+88h+var_58], eax
0x14000acf8  mov     rcx, [rcx+40h]
0x14000acfc  mov     [rsp+88h+var_60], rdi
0x14000ad01  call    WPP_RECORDER_SF_qdq
0x14000ad06  test    rdi, rdi
0x14000ad09  jnz     short loc_14000AD15
0x14000ad0b  mov     ebx, 0C000000Dh
0x14000ad10  jmp     loc_14000B072
0x14000ad15  lea     rbp, [rdi+30h]
0x14000ad19  mov     rcx, rbp; SpinLock
0x14000ad1c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ad23  nop     dword ptr [rax+rax+00h]
0x14000ad28  mov     [rdi+38h], al
0x14000ad2b  cmp     [rdi+33Ch], r12b
0x14000ad32  jz      short loc_14000AD8E
0x14000ad34  cmp     [rdi+33Dh], r12b
0x14000ad3b  jnz     short loc_14000AD8E
0x14000ad3d  mov     ebx, 0C0000022h
0x14000ad42  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000ad49  jz      short loc_14000AD77
0x14000ad4b  mov     r9d, 7Bh ; '{'
0x14000ad51  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad58  lea     rsi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000ad5f  mov     dword ptr [rsp+88h+var_60], ebx
0x14000ad63  mov     r8d, 13h
0x14000ad69  mov     [rsp+88h+var_68], rsi
0x14000ad6e  mov     rcx, [rcx+40h]
0x14000ad72  call    WPP_RECORDER_SF_d
0x14000ad77  mov     dl, [rdi+38h]; NewIrql
0x14000ad7a  mov     rcx, rbp; SpinLock
0x14000ad7d  call    cs:__imp_KeReleaseSpinLock
0x14000ad84  nop     dword ptr [rax+rax+00h]
0x14000ad89  jmp     loc_14000B072
0x14000ad8e  cmp     [rdi+334h], r12b
0x14000ad95  jz      short loc_14000ADAD
0x14000ad97  mov     ebx, 0C0000476h
0x14000ad9c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000ada3  jz      short loc_14000AD77
0x14000ada5  mov     r9d, 7Ch ; '|'
0x14000adab  jmp     short loc_14000AD51
0x14000adad  mov     dl, al; NewIrql
0x14000adaf  mov     rcx, rbp; SpinLock
0x14000adb2  call    cs:__imp_KeReleaseSpinLock
0x14000adb9  nop     dword ptr [rax+rax+00h]
0x14000adbe  mov     eax, [r15]
0x14000adc1  cmp     ebx, eax
0x14000adc3  jz      short loc_14000AE05
0x14000adc5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000adcc  jz      loc_14000AD0B
0x14000add2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000add9  lea     rsi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000ade0  mov     [rsp+88h+var_58], eax
0x14000ade4  mov     r9d, 7Dh ; '}'
0x14000adea  mov     dword ptr [rsp+88h+var_60], ebx
0x14000adee  mov     [rsp+88h+var_68], rsi
0x14000adf3  mov     rcx, [rcx+40h]
0x14000adf7  lea     r8d, [r9-7Bh]
0x14000adfb  call    WPP_RECORDER_SF_Dd
0x14000ae00  jmp     loc_14000AD0B
0x14000ae05  test    eax, eax
0x14000ae07  jnz     short loc_14000AE3E
0x14000ae09  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000ae10  jz      short loc_14000AE36
0x14000ae12  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae19  lea     rsi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000ae20  lea     r9d, [rax+7Eh]
0x14000ae24  mov     [rsp+88h+var_68], rsi
0x14000ae29  lea     r8d, [rax+2]
0x14000ae2d  mov     rcx, [rcx+40h]
0x14000ae31  call    WPP_RECORDER_SF_
0x14000ae36  mov     ebx, r12d
0x14000ae39  jmp     loc_14000B072
0x14000ae3e  mov     rcx, rbp; SpinLock
0x14000ae41  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ae48  nop     dword ptr [rax+rax+00h]
0x14000ae4d  mov     edx, 4E4E4F43h
0x14000ae52  mov     rcx, rdi
0x14000ae55  mov     [rdi+38h], al
0x14000ae58  call    TdiReferenceChannelLocked
0x14000ae5d  mov     r13, rax
0x14000ae60  test    rax, rax
0x14000ae63  jz      loc_14000B007
0x14000ae69  cmp     [rdi+61h], r12b
0x14000ae6d  jz      loc_14000B007
0x14000ae73  lea     r12, [rdi+1C8h]
0x14000ae7a  mov     rdx, r14
0x14000ae7d  mov     rcx, r12
0x14000ae80  call    IrpList_EnqueueEx
0x14000ae85  mov     dl, [rdi+38h]; NewIrql
0x14000ae88  mov     ebx, eax
0x14000ae8a  mov     rcx, rbp; SpinLock
0x14000ae8d  test    eax, eax
0x14000ae8f  js      loc_14000AFF9
0x14000ae95  call    cs:__imp_KeReleaseSpinLock
0x14000ae9c  nop     dword ptr [rax+rax+00h]
0x14000aea1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000aea8  jz      short loc_14000AED1
0x14000aeaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aeb1  mov     r9d, 80h
0x14000aeb7  mov     eax, [r15]
0x14000aeba  mov     [rsp+88h+var_50], r14
0x14000aebf  mov     [rsp+88h+var_58], eax
0x14000aec3  mov     rcx, [rcx+40h]
0x14000aec7  mov     [rsp+88h+var_60], rdi
0x14000aecc  call    WPP_RECORDER_SF_qdq
0x14000aed1  mov     rdx, [rdi+58h]
0x14000aed5  lea     rsi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000aedc  test    rdx, rdx
0x14000aedf  jz      short loc_14000AF26
0x14000aee1  mov     rcx, [rdi+48h]
0x14000aee5  call    cs:__imp_IoIncrementKeepAliveCount
0x14000aeec  nop     dword ptr [rax+rax+00h]
0x14000aef1  test    eax, eax
0x14000aef3  jns     short loc_14000AF26
0x14000aef5  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000aefc  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000af03  jz      short loc_14000AF2D
0x14000af05  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af0c  mov     r9d, 81h
0x14000af12  mov     [rsp+88h+var_68], rsi
0x14000af17  mov     rcx, [rcx+40h]
0x14000af1b  lea     r8d, [r9-7Fh]
0x14000af1f  call    WPP_RECORDER_SF_
0x14000af24  jmp     short loc_14000AF2D
0x14000af26  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000af2d  mov     r8d, [r15]
0x14000af30  mov     r9, r14
0x14000af33  mov     rdx, [r14+8]
0x14000af37  mov     rcx, r13
0x14000af3a  call    ChannelWrite
0x14000af3f  mov     r15d, 103h
0x14000af45  mov     ebx, eax
0x14000af47  cmp     eax, r15d
0x14000af4a  jz      loc_14000B057
0x14000af50  test    eax, eax
0x14000af52  jns     short loc_14000AF7E
0x14000af54  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000af5b  jz      short loc_14000AF7E
0x14000af5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af64  mov     r9d, 82h
0x14000af6a  mov     r8d, 1
0x14000af70  mov     [rsp+88h+var_68], rsi
0x14000af75  mov     rcx, [rcx+40h]
0x14000af79  call    WPP_RECORDER_SF_
0x14000af7e  mov     rdx, r14
0x14000af81  mov     rcx, r12
0x14000af84  call    IrpList_DequeueIrp
0x14000af89  test    al, al
0x14000af8b  jz      short loc_14000AFF4
0x14000af8d  mov     rdx, [rdi+58h]
0x14000af91  test    rdx, rdx
0x14000af94  jz      short loc_14000AFD4
0x14000af96  mov     rcx, [rdi+48h]
0x14000af9a  call    cs:__imp_IoDecrementKeepAliveCount
0x14000afa1  nop     dword ptr [rax+rax+00h]
0x14000afa6  test    eax, eax
0x14000afa8  jns     short loc_14000AFD4
0x14000afaa  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000afb1  jz      short loc_14000AFD4
0x14000afb3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000afba  mov     r9d, 83h
0x14000afc0  mov     r8d, 2
0x14000afc6  mov     [rsp+88h+var_68], rsi
0x14000afcb  mov     rcx, [rcx+40h]
0x14000afcf  call    WPP_RECORDER_SF_
0x14000afd4  test    ebx, ebx
0x14000afd6  jns     short loc_14000AFF4
0x14000afd8  mov     rax, [rsp+88h+arg_20]
0x14000afe0  xor     r8d, r8d
0x14000afe3  mov     edx, ebx
0x14000afe5  mov     rcx, r14; Irp
0x14000afe8  mov     qword ptr [rax], 0
0x14000afef  call    RfcommCompleteTdiIrp
0x14000aff4  mov     ebx, r15d
0x14000aff7  jmp     short loc_14000B057
0x14000aff9  call    cs:__imp_KeReleaseSpinLock
0x14000b000  nop     dword ptr [rax+rax+00h]
0x14000b005  jmp     short loc_14000B057
0x14000b007  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000b00e  jz      short loc_14000B03B
0x14000b010  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b017  lea     rsi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000b01e  mov     r9d, 7Fh
0x14000b024  mov     [rsp+88h+var_60], rdi
0x14000b029  mov     [rsp+88h+var_68], rsi
0x14000b02e  mov     rcx, [rcx+40h]
0x14000b032  lea     r8d, [r9-70h]
0x14000b036  call    WPP_RECORDER_SF_q
0x14000b03b  mov     dl, [rdi+38h]; NewIrql
0x14000b03e  mov     rcx, rbp; SpinLock
0x14000b041  call    cs:__imp_KeReleaseSpinLock
0x14000b048  nop     dword ptr [rax+rax+00h]
0x14000b04d  mov     ebx, 0C000020Dh
0x14000b052  test    r13, r13
0x14000b055  jz      short loc_14000B072
0x14000b057  lea     rcx, [r13+18h]
0x14000b05b  mov     edx, 4E4E4F43h
0x14000b060  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000b067  mov     r8d, 0DE7h
0x14000b06d  call    RefObj_ReleaseEx
0x14000b072  mov     eax, ebx
0x14000b074  add     rsp, 48h
0x14000b078  pop     r15
0x14000b07a  pop     r14
0x14000b07c  pop     r13
0x14000b07e  pop     r12
0x14000b080  pop     rdi
0x14000b081  pop     rsi
0x14000b082  pop     rbp
0x14000b083  pop     rbx
0x14000b084  retn
```
