# MRxSmbUpdateNetRootState

- ea: `0x140028310`
- end: `0x1400283f1`
- name: `MRxSmbUpdateNetRootState`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000c1f0`
- `0x14004245c`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x14000cbbc`
- `0x1400103bc`
- `0x140028310`

## string_xrefs

- `0x14002836b`: `MRxSmbUpdateNetRootState`
- `0x140028387`: `MRxSmbUpdateNetRootState`

## pseudocode

```c
__int64 __fastcall MRxSmbUpdateNetRootState(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // esi
  __int64 v5; // rax
  char *v6; // rdi
  int v7; // ecx
  int v8; // ecx
  unsigned __int8 v10; // [rsp+38h] [rbp-10h]

  v4 = *(unsigned __int8 *)(a1 + 76);
  if ( *(_QWORD *)(a1 + 40) && (v5 = SmbCeReferenceAssociatedServerEntry(*(_QWORD *)(a1 + 32)), (v6 = (char *)v5) != 0) )
  {
    v7 = *(_DWORD *)(v5 + 12);
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 2 )
          *(_BYTE *)(a1 + 76) = 5;
        else
          *(_BYTE *)(a1 + 76) = 3;
      }
      else
      {
        *(_BYTE *)(a1 + 76) = 2;
      }
    }
    else
    {
      *(_BYTE *)(a1 + 76) = 0;
    }
    MRxSmbTrackDerefCount(v5, "MRxSmbUpdateNetRootState", 145);
    SmbReferenceRecord(v6 + 792, "MRxSmbUpdateNetRootState", 145);
    SmbCepDereferenceServerEntry(v6);
  }
  else
  {
    *(_BYTE *)(a1 + 76) = 3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
  {
    v10 = *(_BYTE *)(a1 + 76);
    WPP_SF_qDcDc(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, v4, (_BYTE)v4, v10, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140028310  mov     [rsp+arg_0], rbx
0x140028315  mov     [rsp+arg_8], rsi
0x14002831a  push    rdi
0x14002831b  sub     rsp, 40h
0x14002831f  cmp     qword ptr [rcx+28h], 0
0x140028324  mov     rbx, rcx
0x140028327  movzx   esi, byte ptr [rcx+4Ch]
0x14002832b  jz      short loc_14002839D
0x14002832d  mov     rcx, [rcx+20h]
0x140028331  call    SmbCeReferenceAssociatedServerEntry
0x140028336  mov     rdi, rax
0x140028339  test    rax, rax
0x14002833c  jz      short loc_14002839D
0x14002833e  mov     ecx, [rax+0Ch]
0x140028341  test    ecx, ecx
0x140028343  jz      short loc_140028361
0x140028345  sub     ecx, 1
0x140028348  jz      short loc_14002835B
0x14002834a  cmp     ecx, 2
0x14002834d  jz      short loc_140028355
0x14002834f  mov     byte ptr [rbx+4Ch], 3
0x140028353  jmp     short loc_140028365
0x140028355  mov     byte ptr [rbx+4Ch], 5
0x140028359  jmp     short loc_140028365
0x14002835b  mov     byte ptr [rbx+4Ch], 2
0x14002835f  jmp     short loc_140028365
0x140028361  mov     byte ptr [rbx+4Ch], 0
0x140028365  mov     r8d, 91h
0x14002836b  lea     rdx, aMrxsmbupdatene; "MRxSmbUpdateNetRootState"
0x140028372  mov     rcx, rdi
0x140028375  call    MRxSmbTrackDerefCount
0x14002837a  lea     rcx, [rdi+318h]
0x140028381  mov     r8d, 91h
0x140028387  lea     rdx, aMrxsmbupdatene; "MRxSmbUpdateNetRootState"
0x14002838e  call    SmbReferenceRecord
0x140028393  mov     rcx, rdi; pContext
0x140028396  call    SmbCepDereferenceServerEntry
0x14002839b  jmp     short loc_1400283A1
0x14002839d  mov     byte ptr [rbx+4Ch], 3
0x1400283a1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400283a8  lea     rax, WPP_GLOBAL_Control
0x1400283af  cmp     rcx, rax
0x1400283b2  jz      short loc_1400283DE
0x1400283b4  test    dword ptr [rcx+2Ch], 200h
0x1400283bb  jz      short loc_1400283DE
0x1400283bd  movzx   eax, byte ptr [rbx+4Ch]
0x1400283c1  mov     r9, rbx
0x1400283c4  mov     rcx, [rcx+18h]
0x1400283c8  mov     [rsp+48h+var_10], al
0x1400283cc  mov     [rsp+48h+var_18], eax
0x1400283d0  mov     [rsp+48h+var_20], sil
0x1400283d5  mov     [rsp+48h+var_28], esi
0x1400283d9  call    WPP_SF_qDcDc
0x1400283de  mov     rbx, [rsp+48h+arg_0]
0x1400283e3  xor     eax, eax
0x1400283e5  mov     rsi, [rsp+48h+arg_8]
0x1400283ea  add     rsp, 40h
0x1400283ee  pop     rdi
0x1400283ef  retn
```
