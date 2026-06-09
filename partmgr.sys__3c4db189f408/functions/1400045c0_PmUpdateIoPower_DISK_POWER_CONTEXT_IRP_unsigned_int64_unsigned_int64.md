# PmUpdateIoPower(_DISK_POWER_CONTEXT *,_IRP *,unsigned __int64,unsigned __int64)

- ea: `0x1400045c0`
- end: `0x1400047f9`
- name: `?PmUpdateIoPower@@YAXPEAU_DISK_POWER_CONTEXT@@PEAU_IRP@@_K2@Z`
- size: `569`
- prototype: `void(struct _DISK_POWER_CONTEXT *, struct _IRP *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400021c0`

## callees

- `0x140003734`
- `0x140004190`
- `0x1400045c0`

## import_xrefs

- `ntoskrnl!PsUpdateComponentPower` at `0x140004716`
- `ntoskrnl!PsUpdateComponentPower` at `0x140004716`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400046be`
- `ntoskrnl!IoGetRequestorProcess` at `0x1400046be`

## pseudocode

```c
void __fastcall PmUpdateIoPower(
        struct _DISK_POWER_CONTEXT *a1,
        struct _IRP *a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r10
  int MajorFunction; // ecx
  LARGE_INTEGER ByteOffset; // r11
  __int64 Information_low; // rsi
  LONGLONG v11; // rbp
  unsigned __int64 v12; // rdx
  signed __int32 v13; // r14d
  __int64 v14; // rbx
  signed __int32 v15; // eax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  char v18; // r13
  unsigned __int8 v19; // bl
  __int64 v20; // rcx
  unsigned __int64 v21; // rax
  __int64 v22; // r8
  char *v23; // r9
  unsigned __int64 v24; // r14
  PEPROCESS RequestorProcess; // rax
  int v26; // edx
  int v27; // ecx
  int v28; // r8d
  PEPROCESS v29; // r15

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( (unsigned __int8)(MajorFunction - 3) <= 1u )
  {
    ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
    Information_low = LODWORD(a2->IoStatus.Information);
    v11 = ByteOffset.QuadPart + Information_low;
  }
  else
  {
    if ( (_BYTE)MajorFunction != 9 )
      return;
    ByteOffset.QuadPart = 0;
    LODWORD(Information_low) = 0;
    v11 = 0;
  }
  v12 = *((_QWORD *)a1 + 27);
  v13 = *((_DWORD *)a1 + 58);
  v14 = *((_QWORD *)a1 + 28);
  if ( v12 < a3 && v12 == _InterlockedCompareExchange64((volatile signed __int64 *)a1 + 27, a3, v12) )
  {
    v15 = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 58, 0, v13);
    *((_QWORD *)a1 + 28) = v11;
    v16 = a3 - a4;
    v17 = a3 - v12;
    v18 = v15;
    if ( v16 < v12 )
      a4 = v17;
    if ( v15 )
    {
      v19 = 1;
      v20 = 32LL * (unsigned int)(v15 - 1);
      v21 = a4;
      v22 = *(_QWORD *)((char *)a1 + v20 + 16);
      if ( a4 >= *(_QWORD *)((char *)a1 + v20 + 8) )
        v21 = *(_QWORD *)((char *)a1 + v20 + 8);
      a4 -= v21;
    }
    else
    {
      v22 = 0;
      if ( CurrentStackLocation->MajorFunction == 9 )
      {
        v19 = 1;
        goto LABEL_15;
      }
      v19 = ByteOffset.QuadPart != v14;
    }
    if ( CurrentStackLocation->MajorFunction == 3 )
    {
      if ( (unsigned int)Information_low >= 0x10000 )
      {
        if ( v19 )
          v23 = (char *)a1 + 184;
        else
          v23 = (char *)a1 + 192;
      }
      else
      {
        v23 = (char *)a1 + 8 * (v19 ^ 1LL) + 168;
      }
      goto LABEL_16;
    }
    if ( CurrentStackLocation->MajorFunction == 4 )
    {
      if ( (unsigned int)Information_low >= 0x10000 )
      {
        if ( v19 )
          v23 = (char *)a1 + 188;
        else
          v23 = (char *)a1 + 196;
      }
      else
      {
        v23 = (char *)a1 + 8 * (v19 ^ 1LL) + 172;
      }
LABEL_16:
      v24 = v22 + a4 * *(unsigned int *)v23;
      RequestorProcess = IoGetRequestorProcess(a2);
      v29 = RequestorProcess;
      if ( (Microsoft_Windows_PartitionEnableBits & 2) != 0 )
        McTemplateK0pxxxquu_EtwWriteTransfer(
          v27,
          v26,
          v28,
          (_DWORD)RequestorProcess,
          v24,
          a4,
          v11,
          Information_low,
          v18,
          v19);
      PsUpdateComponentPower(v29, 1, v24 / 0x2710);
      return;
    }
LABEL_15:
    v23 = (char *)a1 + 200;
    goto LABEL_16;
  }
  if ( (Microsoft_Windows_PartitionEnableBits & 2) != 0 )
    McTemplateK0xxx_EtwWriteTransfer(MajorFunction, v12, a3, v12, *((_QWORD *)a1 + 27), a3);
}

```

## disassembly

```asm
0x1400045c0  mov     [rsp+arg_18], rbp
0x1400045c5  push    rsi
0x1400045c6  push    rdi
0x1400045c7  push    r15
0x1400045c9  sub     rsp, 50h
0x1400045cd  mov     r10, [rdx+0B8h]
0x1400045d4  mov     rdi, r9
0x1400045d7  mov     r9, rcx
0x1400045da  mov     r15, rdx
0x1400045dd  movzx   ecx, byte ptr [r10]
0x1400045e1  lea     eax, [rcx-3]
0x1400045e4  cmp     al, 1
0x1400045e6  jbe     short loc_1400045FA
0x1400045e8  cmp     cl, 9
0x1400045eb  jnz     loc_1400047E7
0x1400045f1  xor     r11d, r11d
0x1400045f4  xor     esi, esi
0x1400045f6  xor     ebp, ebp
0x1400045f8  jmp     short loc_140004605
0x1400045fa  mov     r11, [r10+18h]
0x1400045fe  mov     esi, [rdx+38h]
0x140004601  lea     rbp, [r11+rsi]
0x140004605  mov     rdx, [r9+0D8h]
0x14000460c  mov     [rsp+68h+arg_0], rbx
0x140004611  mov     [rsp+68h+arg_10], r14
0x140004619  mov     r14d, [r9+0E8h]
0x140004620  mov     rbx, [r9+0E0h]
0x140004627  cmp     rdx, r8
0x14000462a  jnb     loc_1400047B8
0x140004630  mov     rax, rdx
0x140004633  lock cmpxchg [r9+0D8h], r8
0x14000463c  cmp     rdx, rax
0x14000463f  jnz     loc_1400047B8
0x140004645  mov     [rsp+68h+arg_8], r13
0x14000464a  xor     ecx, ecx
0x14000464c  mov     eax, r14d
0x14000464f  lock cmpxchg [r9+0E8h], ecx
0x140004658  mov     rcx, r8
0x14000465b  mov     [r9+0E0h], rbp
0x140004662  sub     rcx, rdi
0x140004665  sub     r8, rdx
0x140004668  cmp     rcx, rdx
0x14000466b  mov     r13d, eax
0x14000466e  cmovb   rdi, r8
0x140004672  test    eax, eax
0x140004674  jz      short loc_14000469B
0x140004676  lea     ecx, [rax-1]
0x140004679  mov     bl, 1
0x14000467b  shl     rcx, 5
0x14000467f  mov     rax, rdi
0x140004682  mov     rdx, [rcx+r9+8]
0x140004687  mov     r8, [rcx+r9+10h]
0x14000468c  cmp     rdi, rdx
0x14000468f  cmovnb  rax, rdx
0x140004693  sub     rdi, rax
0x140004696  jmp     loc_140004732
0x14000469b  xor     r8d, r8d
0x14000469e  cmp     byte ptr [r10], 9
0x1400046a2  jnz     loc_14000472C
0x1400046a8  mov     bl, 1
0x1400046aa  add     r9, 0C8h
0x1400046b1  mov     r14d, [r9]
0x1400046b4  mov     rcx, r15; Irp
0x1400046b7  imul    r14, rdi
0x1400046bb  add     r14, r8
0x1400046be  call    cs:__imp_IoGetRequestorProcess
0x1400046c5  nop     dword ptr [rax+rax+00h]
0x1400046ca  test    cs:Microsoft_Windows_PartitionEnableBits, 2
0x1400046d1  mov     r15, rax
0x1400046d4  jz      short loc_1400046FA
0x1400046d6  mov     [rsp+68h+var_20], bl
0x1400046da  mov     r9, rax
0x1400046dd  mov     [rsp+68h+var_28], r13b
0x1400046e2  mov     [rsp+68h+var_30], esi
0x1400046e6  mov     [rsp+68h+var_38], rbp
0x1400046eb  mov     [rsp+68h+var_40], rdi
0x1400046f0  mov     [rsp+68h+var_48], r14
0x1400046f5  call    McTemplateK0pxxxquu_EtwWriteTransfer
0x1400046fa  mov     rax, 346DC5D63886594Bh
0x140004704  mov     rcx, r15
0x140004707  mul     r14
0x14000470a  shr     rdx, 0Bh
0x14000470e  mov     r8, rdx
0x140004711  mov     edx, 1
0x140004716  call    cs:__imp_PsUpdateComponentPower
0x14000471d  nop     dword ptr [rax+rax+00h]
0x140004722  mov     r13, [rsp+68h+arg_8]
0x140004727  jmp     loc_1400047DA
0x14000472c  cmp     r11, rbx
0x14000472f  setnz   bl
0x140004732  movzx   eax, byte ptr [r10]
0x140004736  cmp     al, 3
0x140004738  jnz     short loc_140004775
0x14000473a  cmp     esi, 10000h
0x140004740  jnb     short loc_140004759
0x140004742  movzx   eax, bl
0x140004745  xor     rax, 1
0x140004749  lea     r9, [r9+rax*8]
0x14000474d  add     r9, 0A8h
0x140004754  jmp     loc_1400046B1
0x140004759  test    bl, bl
0x14000475b  jz      short loc_140004769
0x14000475d  add     r9, 0B8h
0x140004764  jmp     loc_1400046B1
0x140004769  add     r9, 0C0h
0x140004770  jmp     loc_1400046B1
0x140004775  cmp     al, 4
0x140004777  jnz     loc_1400046AA
0x14000477d  cmp     esi, 10000h
0x140004783  jnb     short loc_14000479C
0x140004785  movzx   eax, bl
0x140004788  xor     rax, 1
0x14000478c  lea     r9, [r9+rax*8]
0x140004790  add     r9, 0ACh
0x140004797  jmp     loc_1400046B1
0x14000479c  test    bl, bl
0x14000479e  jz      short loc_1400047AC
0x1400047a0  add     r9, 0BCh
0x1400047a7  jmp     loc_1400046B1
0x1400047ac  add     r9, 0C4h
0x1400047b3  jmp     loc_1400046B1
0x1400047b8  test    cs:Microsoft_Windows_PartitionEnableBits, 2
0x1400047bf  jz      short loc_1400047DA
0x1400047c1  mov     rax, [r9+0D8h]
0x1400047c8  mov     r9, rdx
0x1400047cb  mov     [rsp+68h+var_40], r8
0x1400047d0  mov     [rsp+68h+var_48], rax
0x1400047d5  call    McTemplateK0xxx_EtwWriteTransfer
0x1400047da  mov     rbx, [rsp+68h+arg_0]
0x1400047df  mov     r14, [rsp+68h+arg_10]
0x1400047e7  mov     rbp, [rsp+68h+arg_18]
0x1400047ef  add     rsp, 50h
0x1400047f3  pop     r15
0x1400047f5  pop     rdi
0x1400047f6  pop     rsi
0x1400047f7  retn
```
