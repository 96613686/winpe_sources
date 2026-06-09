# WriteDetailedEvent

- ea: `0x140009834`
- end: `0x140009aa3`
- name: `WriteDetailedEvent`
- size: `623`
- prototype: `unsigned __int64 __fastcall(int, __int64 *, __int64, __int64 *, __int64, int)`
- caller_count: `1`
- callee_count: `25`
- tags: ``

## callers

- `0x140006198`

## callees

- `0x140003738`
- `0x140003828`
- `0x140003918`
- `0x140003a08`
- `0x140003af8`
- `0x140003be8`
- `0x140003cdc`
- `0x140003dcc`
- `0x140003ebc`
- `0x140003fac`
- `0x14000409c`
- `0x14000418c`
- `0x140004280`
- `0x140004370`
- `0x140004460`
- `0x140004550`
- `0x140004640`
- `0x140004730`
- `0x140004824`
- `0x140004914`
- `0x140004a04`
- `0x140004af4`
- `0x140004be4`
- `0x140004cd4`
- `0x140009834`

## pseudocode

```c
unsigned __int64 __fastcall WriteDetailedEvent(int a1, __int64 *a2, __int64 a3, __int64 *a4, __int64 a5, int a6)
{
  unsigned __int64 result; // rax

  result = *(_QWORD *)(a5 + 88);
  if ( result > 0x1000000 )
  {
    if ( result > 0x40000000 )
    {
      switch ( result )
      {
        case 0x80000000uLL:
          return WriteDetailedEvent<2147483648>(a1, a2, a3, a4, a5, a6);
        case 0x100000000uLL:
          return WriteDetailedEvent<4294967296>(a1, a2, a3, a4, a5, a6);
        case 0x200000000uLL:
          return WriteDetailedEvent<8589934592>(a1, a2, a3, a4, a5, a6);
        case 0x400000000uLL:
          return WriteDetailedEvent<17179869184>(a1, a2, a3, a4, a5, a6);
        case 0x800000000uLL:
          return WriteDetailedEvent<34359738368>(a1, a2, a3, a4, a5, a6);
      }
    }
    else
    {
      switch ( result )
      {
        case 0x40000000uLL:
          return WriteDetailedEvent<1073741824>(a1, a2, a3, a4, a5, a6);
        case 0x2000000uLL:
          return WriteDetailedEvent<33554432>(a1, a2, a3, a4, a5, a6);
        case 0x4000000uLL:
          return WriteDetailedEvent<67108864>(a1, a2, a3, a4, a5, a6);
        case 0x8000000uLL:
          return WriteDetailedEvent<134217728>(a1, a2, a3, a4, a5, a6);
        case 0x10000000uLL:
          return WriteDetailedEvent<268435456>(a1, a2, a3, a4, a5, a6);
        case 0x20000000uLL:
          return WriteDetailedEvent<536870912>(a1, a2, a3, a4, a5, a6);
      }
    }
  }
  else if ( result == 0x1000000 )
  {
    return WriteDetailedEvent<16777216>(a1, a2, a3, a4, a5, a6);
  }
  else if ( result > 0x40000 )
  {
    switch ( result )
    {
      case 0x80000uLL:
        return WriteDetailedEvent<524288>(a1, a2, a3, a4, a5, a6);
      case 0x100000uLL:
        return WriteDetailedEvent<1048576>(a1, a2, a3, a4, a5, a6);
      case 0x200000uLL:
        return WriteDetailedEvent<2097152>(a1, a2, a3, a4, a5, a6);
      case 0x400000uLL:
        return WriteDetailedEvent<4194304>(a1, a2, a3, a4, a5, a6);
      case 0x800000uLL:
        return WriteDetailedEvent<8388608>(a1, a2, a3, a4, a5, a6);
    }
  }
  else
  {
    switch ( result )
    {
      case 0x40000uLL:
        return WriteDetailedEvent<262144>(a1, a2, a3, a4, a5, a6);
      case 0x1000uLL:
        return WriteDetailedEvent<4096>(a1, a2, a3, a4, a5, a6);
      case 0x2000uLL:
        return WriteDetailedEvent<8192>(a1, a2, a3, a4, a5, a6);
      case 0x4000uLL:
        return WriteDetailedEvent<16384>(a1, a2, a3, a4, a5, a6);
      case 0x8000uLL:
        return WriteDetailedEvent<32768>(a1, a2, a3, a4, a5, a6);
      case 0x10000uLL:
        return WriteDetailedEvent<65536>(a1, a2, a3, a4, a5, a6);
      case 0x20000uLL:
        return WriteDetailedEvent<131072>(a1, a2, a3, a4, a5, a6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140009834  sub     rsp, 38h
0x140009838  mov     r10, [rsp+38h+arg_20]
0x14000983d  mov     r11d, 1000000h
0x140009843  mov     rax, [r10+58h]
0x140009847  cmp     rax, r11
0x14000984a  ja      loc_14000997C
0x140009850  jz      loc_14000996E
0x140009856  mov     r11d, 40000h
0x14000985c  cmp     rax, r11
0x14000985f  ja      loc_1400098FC
0x140009865  jz      loc_1400098EE
0x14000986b  cmp     rax, 1000h
0x140009871  jz      short loc_1400098E0
0x140009873  cmp     rax, 2000h
0x140009879  jz      short loc_1400098D2
0x14000987b  cmp     rax, 4000h
0x140009881  jz      short loc_1400098C4
0x140009883  cmp     rax, 8000h
0x140009889  jz      short loc_1400098B6
0x14000988b  cmp     rax, 10000h
0x140009891  jz      short loc_1400098A8
0x140009893  cmp     rax, 20000h
0x140009899  jnz     loc_140009A9E
0x14000989f  add     rsp, 38h
0x1400098a3  jmp     ??$WriteDetailedEvent@$0CAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<131072>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098a8  mov     [rsp+38h+arg_20], r10
0x1400098ad  add     rsp, 38h
0x1400098b1  jmp     ??$WriteDetailedEvent@$0BAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<65536>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098b6  mov     [rsp+38h+arg_20], r10
0x1400098bb  add     rsp, 38h
0x1400098bf  jmp     ??$WriteDetailedEvent@$0IAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<32768>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098c4  mov     [rsp+38h+arg_20], r10
0x1400098c9  add     rsp, 38h
0x1400098cd  jmp     ??$WriteDetailedEvent@$0EAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<16384>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098d2  mov     [rsp+38h+arg_20], r10
0x1400098d7  add     rsp, 38h
0x1400098db  jmp     ??$WriteDetailedEvent@$0CAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<8192>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098e0  mov     [rsp+38h+arg_20], r10
0x1400098e5  add     rsp, 38h
0x1400098e9  jmp     ??$WriteDetailedEvent@$0BAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<4096>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098ee  mov     [rsp+38h+arg_20], r10
0x1400098f3  add     rsp, 38h
0x1400098f7  jmp     ??$WriteDetailedEvent@$0EAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<262144>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400098fc  cmp     rax, 80000h
0x140009902  jz      short loc_140009960
0x140009904  cmp     rax, 100000h
0x14000990a  jz      short loc_140009952
0x14000990c  cmp     rax, 200000h
0x140009912  jz      short loc_140009944
0x140009914  cmp     rax, 400000h
0x14000991a  jz      short loc_140009936
0x14000991c  cmp     rax, 800000h
0x140009922  jnz     loc_140009A9E
0x140009928  mov     [rsp+38h+arg_20], r10
0x14000992d  add     rsp, 38h
0x140009931  jmp     ??$WriteDetailedEvent@$0IAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<8388608>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009936  mov     [rsp+38h+arg_20], r10
0x14000993b  add     rsp, 38h
0x14000993f  jmp     ??$WriteDetailedEvent@$0EAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<4194304>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009944  mov     [rsp+38h+arg_20], r10
0x140009949  add     rsp, 38h
0x14000994d  jmp     ??$WriteDetailedEvent@$0CAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<2097152>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009952  mov     [rsp+38h+arg_20], r10
0x140009957  add     rsp, 38h
0x14000995b  jmp     ??$WriteDetailedEvent@$0BAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<1048576>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009960  mov     [rsp+38h+arg_20], r10
0x140009965  add     rsp, 38h
0x140009969  jmp     ??$WriteDetailedEvent@$0IAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<524288>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x14000996e  mov     [rsp+38h+arg_20], r10
0x140009973  add     rsp, 38h
0x140009977  jmp     ??$WriteDetailedEvent@$0BAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<16777216>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x14000997c  mov     r11d, 40000000h
0x140009982  cmp     rax, r11
0x140009985  ja      loc_140009A0D
0x14000998b  jz      short loc_1400099FF
0x14000998d  cmp     rax, 2000000h
0x140009993  jz      short loc_1400099F1
0x140009995  cmp     rax, 4000000h
0x14000999b  jz      short loc_1400099E3
0x14000999d  cmp     rax, 8000000h
0x1400099a3  jz      short loc_1400099D5
0x1400099a5  cmp     rax, 10000000h
0x1400099ab  jz      short loc_1400099C7
0x1400099ad  cmp     rax, 20000000h
0x1400099b3  jnz     loc_140009A9E
0x1400099b9  mov     [rsp+38h+arg_20], r10
0x1400099be  add     rsp, 38h
0x1400099c2  jmp     ??$WriteDetailedEvent@$0CAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<536870912>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400099c7  mov     [rsp+38h+arg_20], r10
0x1400099cc  add     rsp, 38h
0x1400099d0  jmp     ??$WriteDetailedEvent@$0BAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<268435456>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400099d5  mov     [rsp+38h+arg_20], r10
0x1400099da  add     rsp, 38h
0x1400099de  jmp     ??$WriteDetailedEvent@$0IAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<134217728>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400099e3  mov     [rsp+38h+arg_20], r10
0x1400099e8  add     rsp, 38h
0x1400099ec  jmp     ??$WriteDetailedEvent@$0EAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<67108864>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400099f1  mov     [rsp+38h+arg_20], r10
0x1400099f6  add     rsp, 38h
0x1400099fa  jmp     ??$WriteDetailedEvent@$0CAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<33554432>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x1400099ff  mov     [rsp+38h+arg_20], r10
0x140009a04  add     rsp, 38h
0x140009a08  jmp     ??$WriteDetailedEvent@$0EAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<1073741824>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a0d  mov     r11d, 80000000h
0x140009a13  cmp     rax, r11
0x140009a16  jz      short loc_140009A8C
0x140009a18  mov     r11, 100000000h
0x140009a22  cmp     rax, r11
0x140009a25  jz      short loc_140009A7E
0x140009a27  mov     r11, 200000000h
0x140009a31  cmp     rax, r11
0x140009a34  jz      short loc_140009A70
0x140009a36  mov     r11, 400000000h
0x140009a40  cmp     rax, r11
0x140009a43  jz      short loc_140009A62
0x140009a45  mov     r11, 800000000h
0x140009a4f  cmp     rax, r11
0x140009a52  jnz     short loc_140009A9E
0x140009a54  mov     [rsp+38h+arg_20], r10
0x140009a59  add     rsp, 38h
0x140009a5d  jmp     ??$WriteDetailedEvent@$0IAAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<34359738368>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a62  mov     [rsp+38h+arg_20], r10
0x140009a67  add     rsp, 38h
0x140009a6b  jmp     ??$WriteDetailedEvent@$0EAAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<17179869184>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a70  mov     [rsp+38h+arg_20], r10
0x140009a75  add     rsp, 38h
0x140009a79  jmp     ??$WriteDetailedEvent@$0CAAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<8589934592>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a7e  mov     [rsp+38h+arg_20], r10
0x140009a83  add     rsp, 38h
0x140009a87  jmp     ??$WriteDetailedEvent@$0BAAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<4294967296>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a8c  mov     eax, [rsp+38h+arg_28]
0x140009a90  mov     [rsp+38h+var_10], eax
0x140009a94  mov     [rsp+38h+var_18], r10
0x140009a99  call    ??$WriteDetailedEvent@$0IAAAAAAA@@@YAXKQEAU_FILE_RECORD@@_KPEBGPEAU_RULE_BUCKET@@K@Z; WriteDetailedEvent<2147483648>(ulong,_FILE_RECORD * const,unsigned __int64,ushort const *,_RULE_BUCKET *,ulong)
0x140009a9e  add     rsp, 38h
0x140009aa2  retn
```
