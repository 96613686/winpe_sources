# PrjfCheckAndCancelTransactedOpen

- ea: `0x1400220d0`
- end: `0x140022316`
- name: `PrjfCheckAndCancelTransactedOpen`
- size: `582`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140022320`

## callees

- `0x140001008`
- `0x14000b1d0`
- `0x14000ba20`
- `0x14000d128`
- `0x14002208c`
- `0x1400220d0`

## import_xrefs

- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140022110`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140022110`
- `FLTMGR!FltRollbackEnlistment` at `0x140022273`
- `FLTMGR!FltRollbackEnlistment` at `0x140022273`

## string_xrefs

- `0x1400221dd`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x1400222ae`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfCheckAndCancelTransactedOpen(__int64 a1, _QWORD *a2)
{
  struct _FILE_OBJECT *v2; // rbx
  struct _FLT_INSTANCE *v4; // r14
  struct _KTRANSACTION *v5; // r15
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  NTSTATUS v10; // eax
  int v11; // edx
  int v12; // r8d
  __int64 v14; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v15[32]; // [rsp+70h] [rbp-29h] BYREF
  _DWORD *v16; // [rsp+90h] [rbp-9h]
  __int64 v17; // [rsp+98h] [rbp-1h]
  PWSTR Buffer; // [rsp+A0h] [rbp+7h]
  _DWORD v19[2]; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 *v20; // [rsp+B0h] [rbp+17h]
  __int64 v21; // [rsp+B8h] [rbp+1Fh]

  v2 = (struct _FILE_OBJECT *)a2[4];
  v4 = (struct _FLT_INSTANCE *)a2[3];
  v5 = (struct _KTRANSACTION *)a2[5];
  v6 = 0;
  if ( IoGetTransactionParameterBlock(v2) )
  {
    v6 = -1072103361;
    if ( (unsigned int)dword_14001A068 > 5 )
    {
      v8 = qword_14001A080;
      v7 = 0x400000000000LL;
      if ( (qword_14001A078 & 0x400000000000LL) != 0 && (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
      {
        v17 = 2;
        v16 = v19;
        Buffer = v2->FileName.Buffer;
        v19[0] = v2->FileName.Length;
        v20 = &v14;
        v19[1] = 0;
        v14 = 0x1000000;
        v21 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_14001A068, byte_140016463, 0, 0, 5, v15);
      }
    }
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v7) = BYTE9(xmmword_14001A3D0) & 4;
    if ( (BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_sDL(
        778,
        v7,
        v9,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        10,
        10,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        106,
        63);
    if ( v2->FsContext )
    {
      if ( (v2->Flags & 0x40000) != 0 )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v8, v7, v9);
      PrjfCancelFileOpen(a1, v4, v2, 3222863935LL);
    }
    else
    {
      *(_DWORD *)(a1 + 24) = -1072103361;
      *(_QWORD *)(a1 + 32) = 0;
    }
    v10 = FltRollbackEnlistment(v4, v5, 0);
    if ( v10 < 0
      && ((BYTE9(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
    {
      LOBYTE(v11) = BYTE9(xmmword_14001A3D0) & 4;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        778,
        v11,
        v12,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        10,
        11,
        (__int64)WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        137,
        v10);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1400220d0  mov     [rsp-8+arg_10], rbx
0x1400220d5  mov     [rsp-8+arg_18], rsi
0x1400220da  push    rbp
0x1400220db  push    rdi
0x1400220dc  push    r13
0x1400220de  push    r14
0x1400220e0  push    r15
0x1400220e2  lea     rbp, [rsp-37h]
0x1400220e7  sub     rsp, 0D0h
0x1400220ee  mov     rax, cs:__security_cookie
0x1400220f5  xor     rax, rsp
0x1400220f8  mov     [rbp+57h+var_30], rax
0x1400220fc  mov     rbx, [rdx+20h]
0x140022100  mov     rsi, rcx
0x140022103  mov     r14, [rdx+18h]
0x140022107  mov     rcx, rbx; FileObject
0x14002210a  mov     r15, [rdx+28h]
0x14002210e  xor     edi, edi
0x140022110  call    cs:__imp_IoGetTransactionParameterBlock
0x140022117  nop     dword ptr [rax+rax+00h]
0x14002211c  test    rax, rax
0x14002211f  jz      loc_1400222EB
0x140022125  mov     eax, cs:dword_14001A068
0x14002212b  mov     edi, 0C019003Fh
0x140022130  cmp     eax, 5
0x140022133  jbe     loc_1400221C9
0x140022139  mov     rcx, cs:qword_14001A080
0x140022140  mov     rdx, 400000000000h
0x14002214a  mov     rax, cs:qword_14001A078
0x140022151  test    rdx, rax
0x140022154  jz      short loc_1400221C9
0x140022156  mov     rax, rcx
0x140022159  and     rax, rdx
0x14002215c  cmp     rax, rcx
0x14002215f  jnz     short loc_1400221C9
0x140022161  lea     rax, [rbp+57h+var_48]
0x140022165  mov     [rbp+57h+var_58], 2
0x14002216d  mov     [rbp+57h+var_60], rax
0x140022171  lea     rdx, byte_140016463
0x140022178  mov     rax, [rbx+60h]
0x14002217c  lea     rcx, dword_14001A068
0x140022183  mov     [rbp+57h+var_50], rax
0x140022187  xor     r9d, r9d
0x14002218a  movzx   eax, word ptr [rbx+58h]
0x14002218e  xor     r8d, r8d
0x140022191  mov     [rbp+57h+var_48], eax
0x140022194  lea     rax, [rbp+57h+var_90]
0x140022198  mov     [rbp+57h+var_40], rax
0x14002219c  lea     rax, [rbp+57h+var_80]
0x1400221a0  mov     [rsp+0F0h+var_C8], rax
0x1400221a5  mov     [rsp+0F0h+var_D0], 5
0x1400221ad  mov     [rbp+57h+var_44], 0
0x1400221b4  mov     [rbp+57h+var_90], 1000000h
0x1400221bc  mov     [rbp+57h+var_38], 8
0x1400221c4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400221c9  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x1400221cf  lea     r13, WPP_RECORDER_INITIALIZED
0x1400221d6  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400221dd  lea     r9, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400221e4  mov     eax, 0Ah
0x1400221e9  lea     r10, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400221f0  setnz   r8b
0x1400221f4  and     dl, 4
0x1400221f7  jnz     short loc_1400221FE
0x1400221f9  test    r8b, r8b
0x1400221fc  jz      short loc_140022237
0x1400221fe  mov     [rsp+0F0h+var_A0], edi
0x140022202  mov     ecx, 30Ah
0x140022207  mov     [rsp+0F0h+var_A8], 6Ah ; 'j'
0x14002220f  mov     [rsp+0F0h+var_B0], r9
0x140022214  mov     r9, cs:WPP_GLOBAL_Control
0x14002221b  mov     [rsp+0F0h+var_B8], r10
0x140022220  mov     [rsp+0F0h+var_C0], ax
0x140022225  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140022229  mov     r9, [r9+40h]
0x14002222d  mov     byte ptr [rsp+0F0h+var_D0], 3
0x140022232  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140022237  cmp     qword ptr [rbx+18h], 0
0x14002223c  jz      short loc_14002225F
0x14002223e  test    dword ptr [rbx+50h], 40000h
0x140022245  jz      short loc_14002224C
0x140022247  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002224c  mov     r9d, edi
0x14002224f  mov     r8, rbx
0x140022252  mov     rdx, r14
0x140022255  mov     rcx, rsi
0x140022258  call    PrjfCancelFileOpen
0x14002225d  jmp     short loc_14002226A
0x14002225f  mov     [rsi+18h], edi
0x140022262  mov     qword ptr [rsi+20h], 0
0x14002226a  xor     r8d, r8d; TransactionContext
0x14002226d  mov     rdx, r15; Transaction
0x140022270  mov     rcx, r14; Instance
0x140022273  call    cs:__imp_FltRollbackEnlistment
0x14002227a  nop     dword ptr [rax+rax+00h]
0x14002227f  test    eax, eax
0x140022281  jns     short loc_1400222EB
0x140022283  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14002228a  mov     dl, byte ptr cs:xmmword_14001A3D0+9
0x140022290  setnz   r8b
0x140022294  and     dl, 4
0x140022297  jnz     short loc_14002229E
0x140022299  test    r8b, r8b
0x14002229c  jz      short loc_1400222EB
0x14002229e  mov     r9, cs:WPP_GLOBAL_Control
0x1400222a5  mov     ecx, 30Ah
0x1400222aa  mov     [rsp+0F0h+var_A0], eax
0x1400222ae  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400222b5  mov     [rsp+0F0h+var_A8], 89h
0x1400222bd  mov     [rsp+0F0h+var_B0], rax
0x1400222c2  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400222c9  mov     r9, [r9+40h]
0x1400222cd  mov     [rsp+0F0h+var_B8], rax
0x1400222d2  mov     [rsp+0F0h+var_C0], 0Bh
0x1400222d9  mov     dword ptr [rsp+0F0h+var_C8], 0Ah
0x1400222e1  mov     byte ptr [rsp+0F0h+var_D0], 3
0x1400222e6  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400222eb  mov     eax, edi
0x1400222ed  mov     rcx, [rbp+57h+var_30]
0x1400222f1  xor     rcx, rsp; StackCookie
0x1400222f4  call    __security_check_cookie
0x1400222f9  lea     r11, [rsp+0F0h+var_20]
0x140022301  mov     rbx, [r11+40h]
0x140022305  mov     rsi, [r11+48h]
0x140022309  mov     rsp, r11
0x14002230c  pop     r15
0x14002230e  pop     r14
0x140022310  pop     r13
0x140022312  pop     rdi
0x140022313  pop     rbp
0x140022314  retn
```
