# TdiDrainAndComplete

- ea: `0x140008fd4`
- end: `0x140009165`
- name: `TdiDrainAndComplete`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006a04`

## callees

- `0x140003bf4`
- `0x140005c38`
- `0x140008fd4`
- `0x14001ece8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000905b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000905b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400090aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400090aa`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x1400090ff`
- `ntoskrnl!IoDecrementKeepAliveCount` at `0x1400090ff`

## pseudocode

```c
__int128 *__fastcall TdiDrainAndComplete(__int64 a1, __int64 a2)
{
  char v4; // si
  KSPIN_LOCK *v5; // rcx
  _QWORD *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  int v10; // r9d
  _QWORD *v11; // rbx
  __int128 *result; // rax
  __int64 v13; // rax
  int v14; // edx
  __int128 v15; // [rsp+30h] [rbp-18h] BYREF

  v15 = 0;
  if ( a2 == a1 + 456 || a2 == a1 + 512 )
  {
    v4 = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        3,
        80,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  }
  else
  {
    v4 = 0;
  }
  v5 = *(KSPIN_LOCK **)(a2 + 24);
  *((_QWORD *)&v15 + 1) = &v15;
  *(_QWORD *)&v15 = &v15;
  LOBYTE(v8) = KeAcquireSpinLockRaiseToDpc(v5);
  while ( 1 )
  {
    v9 = IrpList_DequeueLocked(a2, v6, v7, v8);
    if ( !v9 )
      break;
    v6 = (_QWORD *)*((_QWORD *)&v15 + 1);
    if ( **((__int128 ***)&v15 + 1) != &v15 )
LABEL_20:
      __fastfail(3u);
    *(_QWORD *)(v9 + 176) = *((_QWORD *)&v15 + 1);
    *(_QWORD *)(v9 + 168) = &v15;
    *v6 = v9 + 168;
    *((_QWORD *)&v15 + 1) = v9 + 168;
  }
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a2 + 24), v8);
  while ( 1 )
  {
    v11 = (_QWORD *)v15;
    result = &v15;
    if ( (__int128 *)v15 == &v15 )
      return result;
    if ( *(__int128 **)(v15 + 8) != &v15 )
      goto LABEL_20;
    v13 = *(_QWORD *)v15;
    if ( *(_QWORD *)(*(_QWORD *)v15 + 8LL) != (_QWORD)v15 )
      goto LABEL_20;
    *(_QWORD *)&v15 = *(_QWORD *)v15;
    *(_QWORD *)(v13 + 8) = &v15;
    v11[1] = v11;
    *v11 = v11;
    if ( *(_QWORD *)(a1 + 88)
      && v4
      && (int)IoDecrementKeepAliveCount(*(_QWORD *)(a1 + 72)) < 0
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        2,
        81,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    }
    RfcommCompleteTdiIrp((PIRP)(v11 - 21), -1073741536, 0, v10);
  }
}

```

## disassembly

```asm
0x140008fd4  push    rbp
0x140008fd6  push    rbx
0x140008fd7  push    rsi
0x140008fd8  push    rdi
0x140008fd9  push    r12
0x140008fdb  push    r15
0x140008fdd  mov     rbp, rsp
0x140008fe0  sub     rsp, 48h
0x140008fe4  lea     rax, [rcx+1C8h]
0x140008feb  xorps   xmm0, xmm0
0x140008fee  lea     r12, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140008ff5  mov     rbx, rdx
0x140008ff8  lea     r15, WPP_RECORDER_INITIALIZED
0x140008fff  mov     rdi, rcx
0x140009002  movups  [rbp+var_18], xmm0
0x140009006  cmp     rdx, rax
0x140009009  jz      short loc_14000901C
0x14000900b  lea     rax, [rcx+200h]
0x140009012  cmp     rdx, rax
0x140009015  jz      short loc_14000901C
0x140009017  xor     sil, sil
0x14000901a  jmp     short loc_140009047
0x14000901c  mov     sil, 1
0x14000901f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009026  jz      short loc_140009047
0x140009028  mov     rcx, cs:WPP_GLOBAL_Control
0x14000902f  mov     r9d, 50h ; 'P'
0x140009035  mov     [rsp+48h+var_28], r12
0x14000903a  mov     rcx, [rcx+40h]
0x14000903e  lea     r8d, [r9-4Dh]
0x140009042  call    WPP_RECORDER_SF_
0x140009047  mov     rcx, [rbx+18h]; SpinLock
0x14000904b  lea     rax, [rbp+var_18]
0x14000904f  mov     qword ptr [rbp+var_18+8], rax
0x140009053  lea     rax, [rbp+var_18]
0x140009057  mov     qword ptr [rbp+var_18], rax
0x14000905b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009062  nop     dword ptr [rax+rax+00h]
0x140009067  mov     r9b, al
0x14000906a  jmp     short loc_140009096
0x14000906c  mov     rdx, qword ptr [rbp+var_18+8]
0x140009070  lea     rcx, [rbp+var_18]
0x140009074  cmp     [rdx], rcx
0x140009077  jnz     loc_140009150
0x14000907d  lea     rcx, [rax+0A8h]
0x140009084  mov     [rcx+8], rdx
0x140009088  lea     rax, [rbp+var_18]
0x14000908c  mov     [rcx], rax
0x14000908f  mov     [rdx], rcx
0x140009092  mov     qword ptr [rbp+var_18+8], rcx
0x140009096  mov     rcx, rbx
0x140009099  call    IrpList_DequeueLocked
0x14000909e  test    rax, rax
0x1400090a1  jnz     short loc_14000906C
0x1400090a3  mov     rcx, [rbx+18h]; SpinLock
0x1400090a7  mov     dl, r9b; NewIrql
0x1400090aa  call    cs:__imp_KeReleaseSpinLock
0x1400090b1  nop     dword ptr [rax+rax+00h]
0x1400090b6  mov     rbx, qword ptr [rbp+var_18]
0x1400090ba  lea     rax, [rbp+var_18]
0x1400090be  cmp     rbx, rax
0x1400090c1  jz      loc_140009157
0x1400090c7  lea     rax, [rbp+var_18]
0x1400090cb  cmp     [rbx+8], rax
0x1400090cf  jnz     short loc_140009150
0x1400090d1  mov     rax, [rbx]
0x1400090d4  cmp     [rax+8], rbx
0x1400090d8  jnz     short loc_140009150
0x1400090da  mov     qword ptr [rbp+var_18], rax
0x1400090de  lea     rcx, [rbp+var_18]
0x1400090e2  mov     [rax+8], rcx
0x1400090e6  mov     [rbx+8], rbx
0x1400090ea  mov     [rbx], rbx
0x1400090ed  mov     rdx, [rdi+58h]
0x1400090f1  test    rdx, rdx
0x1400090f4  jz      short loc_140009137
0x1400090f6  test    sil, sil
0x1400090f9  jz      short loc_140009137
0x1400090fb  mov     rcx, [rdi+48h]
0x1400090ff  call    cs:__imp_IoDecrementKeepAliveCount
0x140009106  nop     dword ptr [rax+rax+00h]
0x14000910b  test    eax, eax
0x14000910d  jns     short loc_140009137
0x14000910f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009116  jz      short loc_140009137
0x140009118  mov     rcx, cs:WPP_GLOBAL_Control
0x14000911f  mov     r9d, 51h ; 'Q'
0x140009125  mov     [rsp+48h+var_28], r12
0x14000912a  mov     rcx, [rcx+40h]
0x14000912e  lea     r8d, [r9-4Fh]
0x140009132  call    WPP_RECORDER_SF_
0x140009137  lea     rcx, [rbx-0A8h]; Irp
0x14000913e  xor     r8d, r8d
0x140009141  mov     edx, 0C0000120h
0x140009146  call    RfcommCompleteTdiIrp
0x14000914b  jmp     loc_1400090B6
0x140009150  mov     ecx, 3
0x140009155  int     29h; Win8: RtlFailFast(ecx)
0x140009157  add     rsp, 48h
0x14000915b  pop     r15
0x14000915d  pop     r12
0x14000915f  pop     rdi
0x140009160  pop     rsi
0x140009161  pop     rbx
0x140009162  pop     rbp
0x140009163  retn
```
