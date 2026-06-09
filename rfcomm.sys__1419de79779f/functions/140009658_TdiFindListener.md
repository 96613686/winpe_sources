# TdiFindListener

- ea: `0x140009658`
- end: `0x1400097eb`
- name: `TdiFindListener`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005f2c`
- `0x14001190c`

## callees

- `0x140003cb4`
- `0x140004a68`
- `0x140004e58`
- `0x140009658`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400096b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009742`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009742`

## string_xrefs

- `0x140009799`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 *__fastcall TdiFindListener(__int64 a1, int a2)
{
  __int64 *v4; // rdi
  __int64 v5; // rbp
  int v6; // edx
  __int64 *i; // rbx
  int v8; // edx
  int v10; // edx

  v4 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 16LL);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      70,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a2);
  *(_BYTE *)(v5 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 48));
  for ( i = *(__int64 **)(v5 + 112); i != (__int64 *)(v5 + 112); i = (__int64 *)*i )
  {
    if ( a2 == *((_DWORD *)i + 28) && i[18] )
    {
      if ( !i[11] || i[10] == a1 )
      {
        v4 = i;
        RefObj_AddRefEx(i + 3, 1145981254, 1884, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            15,
            71,
            (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
            i);
        break;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          15,
          72,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
          a1,
          i[10]);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 48), *(_BYTE *)(v5 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      15,
      73,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v4);
  return v4;
}

```

## disassembly

```asm
0x140009658  push    rbx
0x14000965a  push    rbp
0x14000965b  push    rsi
0x14000965c  push    rdi
0x14000965d  push    r12
0x14000965f  push    r13
0x140009661  push    r14
0x140009663  push    r15
0x140009665  sub     rsp, 48h
0x140009669  mov     rax, [rcx+60h]
0x14000966d  mov     r14d, edx
0x140009670  mov     rsi, rcx
0x140009673  xor     edi, edi
0x140009675  mov     rbp, [rax+10h]
0x140009679  lea     r13, WPP_RECORDER_INITIALIZED
0x140009680  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009687  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000968e  jz      short loc_1400096B1
0x140009690  mov     rcx, cs:WPP_GLOBAL_Control
0x140009697  lea     r9d, [rdi+46h]
0x14000969b  mov     dword ptr [rsp+88h+var_60], edx
0x14000969f  lea     r8d, [rdi+0Fh]
0x1400096a3  mov     [rsp+88h+var_68], rax
0x1400096a8  mov     rcx, [rcx+40h]
0x1400096ac  call    WPP_RECORDER_SF_d
0x1400096b1  lea     rcx, [rbp+30h]; SpinLock
0x1400096b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400096bc  nop     dword ptr [rax+rax+00h]
0x1400096c1  lea     r15, [rbp+70h]
0x1400096c5  mov     [rbp+38h], al
0x1400096c8  mov     rbx, [r15]
0x1400096cb  jmp     short loc_14000972F
0x1400096cd  cmp     r14d, [rbx+70h]
0x1400096d1  jnz     short loc_14000972C
0x1400096d3  cmp     [rbx+90h], rdi
0x1400096da  jz      short loc_14000972C
0x1400096dc  cmp     [rbx+58h], rdi
0x1400096e0  jz      loc_140009790
0x1400096e6  mov     rax, [rbx+50h]
0x1400096ea  cmp     rax, rsi
0x1400096ed  jz      loc_140009790
0x1400096f3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400096fa  jz      short loc_14000972C
0x1400096fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140009703  mov     r9d, 48h ; 'H'
0x140009709  mov     [rsp+88h+var_58], rax
0x14000970e  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009715  mov     [rsp+88h+var_60], rsi
0x14000971a  mov     [rsp+88h+var_68], rax
0x14000971f  mov     rcx, [rcx+40h]
0x140009723  lea     r8d, [r9-39h]
0x140009727  call    WPP_RECORDER_SF_qq
0x14000972c  mov     rbx, [rbx]
0x14000972f  cmp     rbx, r15
0x140009732  jnz     short loc_1400096CD
0x140009734  lea     rbx, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000973b  mov     dl, [rbp+38h]; NewIrql
0x14000973e  lea     rcx, [rbp+30h]; SpinLock
0x140009742  call    cs:__imp_KeReleaseSpinLock
0x140009749  nop     dword ptr [rax+rax+00h]
0x14000974e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140009755  jz      short loc_14000977B
0x140009757  mov     rcx, cs:WPP_GLOBAL_Control
0x14000975e  mov     r9d, 49h ; 'I'
0x140009764  mov     [rsp+88h+var_60], rdi
0x140009769  mov     [rsp+88h+var_68], rbx
0x14000976e  mov     rcx, [rcx+40h]
0x140009772  lea     r8d, [r9-3Ah]
0x140009776  call    WPP_RECORDER_SF_q
0x14000977b  mov     rax, rdi
0x14000977e  add     rsp, 48h
0x140009782  pop     r15
0x140009784  pop     r14
0x140009786  pop     r13
0x140009788  pop     r12
0x14000978a  pop     rdi
0x14000978b  pop     rsi
0x14000978c  pop     rbp
0x14000978d  pop     rbx
0x14000978e  retn
0x140009790  lea     rcx, [rbx+18h]
0x140009794  mov     edx, 444E4946h
0x140009799  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400097a0  mov     r8d, 75Ch
0x1400097a6  mov     rdi, rbx
0x1400097a9  call    RefObj_AddRefEx
0x1400097ae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400097b5  jz      loc_140009734
0x1400097bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097c2  mov     r9d, 47h ; 'G'
0x1400097c8  mov     [rsp+88h+var_60], rbx
0x1400097cd  lea     rbx, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400097d4  mov     [rsp+88h+var_68], rbx
0x1400097d9  mov     rcx, [rcx+40h]
0x1400097dd  lea     r8d, [r9-38h]
0x1400097e1  call    WPP_RECORDER_SF_q
0x1400097e6  jmp     loc_14000973B
```
