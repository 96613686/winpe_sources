# CPacket::CompleteWriter(long)

- ea: `0x140014c48`
- end: `0x140014e0f`
- name: `?CompleteWriter@CPacket@@QEAAXJ@Z`
- size: `455`
- prototype: `void __fastcall(CPacket *__hidden this, int)`
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001569c`
- `0x140015ac4`
- `0x1400177c4`
- `0x14001821c`
- `0x1400183c4`

## callees

- `0x140001010`
- `0x14000b8e8`
- `0x14000d728`
- `0x140011d94`
- `0x140011dc4`
- `0x140014c48`
- `0x140017970`
- `0x14001979c`
- `0x140021280`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014de4`
- `ntoskrnl!IofCompleteRequest` at `0x140014de4`

## pseudocode

```c
void __fastcall CPacket::CompleteWriter(CPacket *this, int a2)
{
  int v4; // eax
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx
  struct _IRP *v7; // rax
  struct _IRP *v8; // rdi
  int v9; // ecx
  int v10; // edx
  struct CPacket *v11; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 43, &WPP_521cf5ef77973c292796e113f00b944d_Traceguids, this, a2);
  }
  v4 = *((_DWORD *)this + 13);
  if ( (v4 & 0x80000) != 0 )
  {
    *((_DWORD *)this + 13) = v4 & 0xFFF7FFFF;
    v7 = CStorage::GetWriteRequest((CStorage *)(*(_QWORD *)(*((_QWORD *)this + 13) + 64LL) + 368LL), this);
    v8 = v7;
    if ( v7 )
    {
      v11 = CIrp2Pkt::SafeDetachPacket(v7, this);
      if ( CIrp2Pkt::SafePeekFirstPacket(v8) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            46,
            &WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
            this,
            v8,
            a2);
        }
        CPacket::HoldWriteRequest(this, v8);
      }
      else
      {
        if ( a2 == -1072824234 && (v9 = *((_DWORD *)&v8->Tail.CompletionKey + 6), (v9 & 0x20) != 0) && (v9 & 7) == 2 )
          v10 = 0;
        else
          v10 = a2;
        irp_safe_set_final_status(v8, v10);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->Queue.ListEntry.Blink,
            47,
            &WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
            v8,
            this,
            a2);
        }
        v8->IoStatus.Information = 0;
        IofCompleteRequest(v8, 2);
      }
      R<CTransaction>::~R<CTransaction>(&v11);
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        v6 = 45;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      v6 = 44;
LABEL_8:
      WPP_SF_qD(v5->Queue.ListEntry.Blink, v6, &WPP_521cf5ef77973c292796e113f00b944d_Traceguids, this, a2);
    }
  }
}

```

## disassembly

```asm
0x140014c48  mov     [rsp+arg_8], rbx
0x140014c4d  mov     [rsp+arg_10], rsi
0x140014c52  push    rdi
0x140014c53  push    r14
0x140014c55  push    r15
0x140014c57  sub     rsp, 30h
0x140014c5b  mov     esi, edx
0x140014c5d  mov     rbx, rcx
0x140014c60  mov     rcx, cs:WPP_GLOBAL_Control
0x140014c67  lea     r14, WPP_GLOBAL_Control
0x140014c6e  lea     r15, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x140014c75  cmp     rcx, r14
0x140014c78  jz      short loc_140014C99
0x140014c7a  mov     eax, [rcx+6Ch]
0x140014c7d  test    al, 4
0x140014c7f  jz      short loc_140014C99
0x140014c81  mov     rcx, [rcx+58h]
0x140014c85  mov     edx, 2Bh ; '+'
0x140014c8a  mov     r9, rbx
0x140014c8d  mov     dword ptr [rsp+48h+var_28], esi
0x140014c91  mov     r8, r15
0x140014c94  call    WPP_SF_qD
0x140014c99  mov     eax, [rbx+34h]
0x140014c9c  bt      eax, 13h
0x140014ca0  jb      short loc_140014CDA
0x140014ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140014ca9  cmp     rcx, r14
0x140014cac  jz      loc_140014DFA
0x140014cb2  mov     eax, [rcx+6Ch]
0x140014cb5  test    al, 4
0x140014cb7  jz      loc_140014DFA
0x140014cbd  mov     edx, 2Ch ; ','
0x140014cc2  mov     rcx, [rcx+58h]
0x140014cc6  mov     r9, rbx
0x140014cc9  mov     r8, r15
0x140014ccc  mov     dword ptr [rsp+48h+var_28], esi
0x140014cd0  call    WPP_SF_qD
0x140014cd5  jmp     loc_140014DFA
0x140014cda  btr     eax, 13h
0x140014cde  mov     rdx, rbx; struct CPacket *
0x140014ce1  mov     [rbx+34h], eax
0x140014ce4  mov     rax, [rbx+68h]
0x140014ce8  mov     rcx, [rax+40h]
0x140014cec  add     rcx, 170h; this
0x140014cf3  call    ?GetWriteRequest@CStorage@@QEAAPEAU_IRP@@PEAVCPacket@@@Z; CStorage::GetWriteRequest(CPacket *)
0x140014cf8  mov     rdi, rax
0x140014cfb  test    rax, rax
0x140014cfe  jnz     short loc_140014D20
0x140014d00  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d07  cmp     rcx, r14
0x140014d0a  jz      loc_140014DFA
0x140014d10  mov     eax, [rcx+6Ch]
0x140014d13  test    al, 4
0x140014d15  jz      loc_140014DFA
0x140014d1b  lea     edx, [rdi+2Dh]
0x140014d1e  jmp     short loc_140014CC2
0x140014d20  mov     rdx, rbx; struct CPacket *
0x140014d23  mov     rcx, rdi; struct _IRP *
0x140014d26  call    ?SafeDetachPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@PEAV2@@Z; CIrp2Pkt::SafeDetachPacket(_IRP *,CPacket *)
0x140014d2b  mov     rcx, rdi; struct _IRP *
0x140014d2e  mov     [rsp+48h+arg_0], rax
0x140014d33  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x140014d38  test    rax, rax
0x140014d3b  jz      short loc_140014D7A
0x140014d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140014d44  cmp     rcx, r14
0x140014d47  jz      short loc_140014D6D
0x140014d49  mov     eax, [rcx+6Ch]
0x140014d4c  test    al, 4
0x140014d4e  jz      short loc_140014D6D
0x140014d50  mov     rcx, [rcx+58h]
0x140014d54  mov     edx, 2Eh ; '.'
0x140014d59  mov     [rsp+48h+var_20], esi
0x140014d5d  mov     r9, rbx
0x140014d60  mov     r8, r15
0x140014d63  mov     [rsp+48h+var_28], rdi
0x140014d68  call    WPP_SF_qqD
0x140014d6d  mov     rdx, rdi; struct _IRP *
0x140014d70  mov     rcx, rbx; this
0x140014d73  call    ?HoldWriteRequest@CPacket@@AEAAXPEAU_IRP@@@Z; CPacket::HoldWriteRequest(_IRP *)
0x140014d78  jmp     short loc_140014DF0
0x140014d7a  cmp     esi, 0C00E0056h
0x140014d80  jnz     short loc_140014D9D
0x140014d82  mov     ecx, [rdi+90h]
0x140014d88  mov     eax, ecx
0x140014d8a  shr     eax, 5
0x140014d8d  test    al, 1
0x140014d8f  jz      short loc_140014D9D
0x140014d91  and     cl, 7
0x140014d94  cmp     cl, 2
0x140014d97  jnz     short loc_140014D9D
0x140014d99  xor     edx, edx
0x140014d9b  jmp     short loc_140014D9F
0x140014d9d  mov     edx, esi; int
0x140014d9f  mov     rcx, rdi; struct _IRP *
0x140014da2  call    ?irp_safe_set_final_status@@YAXPEAU_IRP@@J@Z; irp_safe_set_final_status(_IRP *,long)
0x140014da7  mov     rcx, cs:WPP_GLOBAL_Control
0x140014dae  cmp     rcx, r14
0x140014db1  jz      short loc_140014DD7
0x140014db3  mov     eax, [rcx+6Ch]
0x140014db6  test    al, 4
0x140014db8  jz      short loc_140014DD7
0x140014dba  mov     rcx, [rcx+58h]
0x140014dbe  mov     edx, 2Fh ; '/'
0x140014dc3  mov     [rsp+48h+var_20], esi
0x140014dc7  mov     r9, rdi
0x140014dca  mov     r8, r15
0x140014dcd  mov     [rsp+48h+var_28], rbx
0x140014dd2  call    WPP_SF_qqD
0x140014dd7  mov     dl, 2; PriorityBoost
0x140014dd9  mov     qword ptr [rdi+38h], 0
0x140014de1  mov     rcx, rdi; Irp
0x140014de4  call    cs:__imp_IofCompleteRequest
0x140014deb  nop     dword ptr [rax+rax+00h]
0x140014df0  lea     rcx, [rsp+48h+arg_0]
0x140014df5  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x140014dfa  mov     rbx, [rsp+48h+arg_8]
0x140014dff  mov     rsi, [rsp+48h+arg_10]
0x140014e04  add     rsp, 30h
0x140014e08  pop     r15
0x140014e0a  pop     r14
0x140014e0c  pop     rdi
0x140014e0d  retn
```
