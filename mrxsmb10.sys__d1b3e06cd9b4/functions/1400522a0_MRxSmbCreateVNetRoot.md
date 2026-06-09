# MRxSmbCreateVNetRoot

- ea: `0x1400522a0`
- end: `0x14005269d`
- name: `MRxSmbCreateVNetRoot`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000ce24`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e52c`
- `0x14000e694`
- `0x14000ed10`
- `0x140016640`
- `0x1400358dc`
- `0x140035968`
- `0x14003eb2c`
- `0x140042e64`
- `0x1400522a0`

## import_xrefs

- `rdbss!RxDiagnosticTrace` at `0x140052664`
- `rdbss!RxDiagnosticTrace` at `0x140052664`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x1400522f6`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x1400525f4`

## pseudocode

```c
__int64 __fastcall MRxSmbCreateVNetRoot(__int64 a1)
{
  __int64 v1; // r13
  __int64 v3; // rbx
  bool v4; // di
  unsigned int LockArray_high; // ecx
  __int64 v6; // rbp
  __int64 v7; // r14
  __int64 v8; // rax
  int v9; // ecx
  __int64 v10; // rsi
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // edi
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // [rsp+70h] [rbp+8h]
  __int64 v20; // [rsp+78h] [rbp+10h]

  v1 = *(_QWORD *)(a1 + 264);
  v3 = *(_QWORD *)(a1 + 32);
  v4 = 0;
  LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
  v19 = LockArray_high;
  v6 = *(_QWORD *)(v1 + 32);
  v7 = *(_QWORD *)(v6 + 32);
  v8 = *(_QWORD *)(v7 + 32);
  v20 = v8;
  if ( v3 && !*(_BYTE *)(v3 + 32) )
  {
    if ( (*(_BYTE *)(v3 + 749) & 8) != 0 )
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)LockArray_high << 8)
                                                      + MRxSmbLegacyPerfCtrs
                                                      + 184));
    v4 = (*(_BYTE *)(v3 + 749) & 0x10) != 0;
  }
  v9 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        (unsigned int)WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids,
        v6,
        *(_QWORD *)(v6 + 88));
    v8 = v20;
  }
  v10 = *(_QWORD *)(v6 + 40);
  if ( v3 && !*(_BYTE *)(v3 + 32) )
  {
    if ( (*(_BYTE *)(v3 + 749) & 8) != 0 )
    {
      if ( (*(_DWORD *)(v3 + 528) & 4) != 0 )
      {
        v11 = -1073741637;
        v9 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            12,
            WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids,
            3221225659LL);
        }
        v12 = 267;
        goto LABEL_32;
      }
      if ( (*(_DWORD *)(v3 + 540) & 2) != 0 )
      {
        v11 = -1073741637;
        v9 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids,
            3221225659LL);
        }
        v12 = 275;
        goto LABEL_32;
      }
    }
    v8 = v20;
  }
  if ( *(_BYTE *)(v6 + 77) != 1
    || *(_DWORD *)(v8 + 12)
    || *(_DWORD *)(v8 + 4) != 2
    || (MRxSmbGetDialectFlagsFromSrvCall(v7) & 0x10) != 0 )
  {
    v12 = 229;
    v11 = -1073741802;
    if ( *(_DWORD *)(v1 + 184) == 3 )
    {
LABEL_45:
      v12 = 297;
      v14 = 0;
      v11 = -1073741311;
LABEL_46:
      if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
        McTemplateK0qqq_EtwWriteTransfer(v9, (unsigned int)CreateVNetRootError, v3 + 412, v11, v12, 0);
      *(_DWORD *)(v1 + 180) = v11;
      if ( !v10 )
      {
        v14 = v11;
        if ( *(_QWORD *)(v6 + 40) )
        {
          if ( v11 == -1073741715 || v11 == -1073741790 )
            v14 = 0;
        }
      }
      SmbCeDestroyAssociatedVNetRootContext(v1, v12);
      if ( v3 && !*(_BYTE *)(v3 + 32) && (*(_BYTE *)(v3 + 749) & 8) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)v19 << 8) + MRxSmbLegacyPerfCtrs + 188));
      goto LABEL_57;
    }
  }
  else
  {
    *(_QWORD *)(v1 + 40) = 0;
    v12 = 287;
    v11 = -1073741637;
    v9 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids);
      v12 = 287;
    }
  }
LABEL_32:
  if ( *(_DWORD *)(a1 + 144) == 3 )
    goto LABEL_45;
  if ( v11 != -1073741802 )
    goto LABEL_37;
  v13 = *(_QWORD *)(v1 + 40);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids, v13, v1);
  }
  else
  {
    v11 = SmbCeFindOrConstructVNetRootContext(v3, v1, v4);
    if ( v11 != -1073741802 )
    {
      v12 = 303;
      goto LABEL_37;
    }
  }
  v11 = SmbCeEstablishConnection(*(_QWORD *)(v1 + 40), a1, v10 == 0);
  v12 = 318;
LABEL_37:
  if ( v11 == 259 )
    return 259;
  v14 = 0;
  if ( v11 < 0 )
    goto LABEL_46;
LABEL_57:
  *(_DWORD *)(a1 + 280) = v11;
  *(_DWORD *)(a1 + 284) = v14;
  v16 = *(_QWORD *)(v6 + 40);
  if ( v16 )
    SmbCeUpdateNetRoot(v16, v6);
  v17 = *(_QWORD **)(v1 + 40);
  if ( v17 )
  {
    v18 = v17[12];
    if ( v18 )
      RxDiagnosticTrace(
        *(_QWORD *)(v18 + 16),
        1,
        "Callback rdbss VNetRoot %p VnrCtxt %p Status %x",
        (const void *)v1,
        v17,
        *(_DWORD *)(a1 + 280));
  }
  (*(void (__fastcall **)(__int64, __int64))(a1 + 272))(a1, v12);
  return 259;
}

```

## disassembly

```asm
0x1400522a0  mov     [rsp+arg_10], rbx
0x1400522a5  push    rbp
0x1400522a6  push    rsi
0x1400522a7  push    rdi
0x1400522a8  push    r12
0x1400522aa  push    r13
0x1400522ac  push    r14
0x1400522ae  push    r15
0x1400522b0  sub     rsp, 30h
0x1400522b4  mov     r13, [rcx+108h]
0x1400522bb  mov     r15, rcx
0x1400522be  mov     rbx, [rcx+20h]
0x1400522c2  xor     dil, dil
0x1400522c5  mov     ecx, gs:1A4h
0x1400522cd  mov     [rsp+68h+arg_0], ecx
0x1400522d1  mov     rbp, [r13+20h]
0x1400522d5  mov     r14, [rbp+20h]
0x1400522d9  mov     rax, [r14+20h]
0x1400522dd  mov     [rsp+68h+arg_8], rax
0x1400522e2  test    rbx, rbx
0x1400522e5  jz      short loc_140052322
0x1400522e7  cmp     [rbx+20h], dil
0x1400522eb  jnz     short loc_140052322
0x1400522ed  test    byte ptr [rbx+2EDh], 8
0x1400522f4  jz      short loc_14005230E
0x1400522f6  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x1400522fd  mov     edx, ecx
0x1400522ff  shl     rdx, 8
0x140052303  mov     rcx, [rax]
0x140052306  lock inc dword ptr [rdx+rcx+0B8h]
0x14005230e  movzx   edi, byte ptr [rbx+2EDh]
0x140052315  mov     rax, [rsp+68h+arg_8]
0x14005231a  shr     dil, 4
0x14005231e  and     dil, 1
0x140052322  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052329  lea     r8, WPP_GLOBAL_Control
0x140052330  cmp     rcx, r8
0x140052333  jz      short loc_14005236B
0x140052335  test    dword ptr [rcx+2Ch], 200h
0x14005233c  jz      short loc_140052366
0x14005233e  mov     rax, [rbp+58h]
0x140052342  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x140052349  mov     rcx, [rcx+18h]
0x14005234d  mov     edx, 0Bh
0x140052352  mov     r9, rbp
0x140052355  mov     [rsp+68h+var_48], rax
0x14005235a  call    WPP_SF_qZ
0x14005235f  lea     r8, WPP_GLOBAL_Control
0x140052366  mov     rax, [rsp+68h+arg_8]
0x14005236b  mov     rsi, [rbp+28h]
0x14005236f  test    rsi, rsi
0x140052372  setz    r12b
0x140052376  test    rbx, rbx
0x140052379  jz      loc_14005243D
0x14005237f  cmp     byte ptr [rbx+20h], 0
0x140052383  jnz     loc_14005243D
0x140052389  test    byte ptr [rbx+2EDh], 8
0x140052390  jz      loc_140052438
0x140052396  mov     eax, [rbx+210h]
0x14005239c  test    al, 4
0x14005239e  jz      short loc_1400523E7
0x1400523a0  mov     r14d, 0C00000BBh
0x1400523a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400523ad  cmp     rcx, r8
0x1400523b0  jz      short loc_1400523DD
0x1400523b2  test    dword ptr [rcx+2Ch], 100h
0x1400523b9  jz      short loc_1400523DD
0x1400523bb  mov     rcx, [rcx+18h]
0x1400523bf  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x1400523c6  mov     edx, 0Ch
0x1400523cb  mov     r9d, 0C00000BBh
0x1400523d1  call    WPP_SF_d
0x1400523d6  lea     r8, WPP_GLOBAL_Control
0x1400523dd  mov     edx, 10Bh
0x1400523e2  jmp     loc_1400524CD
0x1400523e7  mov     eax, [rbx+21Ch]
0x1400523ed  test    al, 2
0x1400523ef  jz      short loc_140052438
0x1400523f1  mov     r14d, 0C00000BBh
0x1400523f7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400523fe  cmp     rcx, r8
0x140052401  jz      short loc_14005242E
0x140052403  test    dword ptr [rcx+2Ch], 100h
0x14005240a  jz      short loc_14005242E
0x14005240c  mov     rcx, [rcx+18h]
0x140052410  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x140052417  mov     edx, 0Dh
0x14005241c  mov     r9d, 0C00000BBh
0x140052422  call    WPP_SF_d
0x140052427  lea     r8, WPP_GLOBAL_Control
0x14005242e  mov     edx, 113h
0x140052433  jmp     loc_1400524CD
0x140052438  mov     rax, [rsp+68h+arg_8]
0x14005243d  cmp     byte ptr [rbp+4Dh], 1
0x140052441  jnz     short loc_1400524B4
0x140052443  cmp     dword ptr [rax+0Ch], 0
0x140052447  jnz     short loc_1400524B4
0x140052449  cmp     dword ptr [rax+4], 2
0x14005244d  jnz     short loc_1400524B4
0x14005244f  mov     rcx, r14
0x140052452  call    MRxSmbGetDialectFlagsFromSrvCall
0x140052457  test    al, 10h
0x140052459  jnz     short loc_1400524AD
0x14005245b  mov     qword ptr [r13+28h], 0
0x140052463  mov     edx, 11Fh
0x140052468  mov     r14d, 0C00000BBh
0x14005246e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052475  lea     r8, WPP_GLOBAL_Control
0x14005247c  cmp     rcx, r8
0x14005247f  jz      short loc_1400524CD
0x140052481  test    dword ptr [rcx+2Ch], 400h
0x140052488  jz      short loc_1400524CD
0x14005248a  mov     rcx, [rcx+18h]
0x14005248e  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x140052495  mov     edx, 0Eh
0x14005249a  call    WPP_SF_
0x14005249f  mov     edx, 11Fh
0x1400524a4  lea     r8, WPP_GLOBAL_Control
0x1400524ab  jmp     short loc_1400524CD
0x1400524ad  lea     r8, WPP_GLOBAL_Control
0x1400524b4  cmp     dword ptr [r13+0B8h], 3
0x1400524bc  mov     edx, 0E5h
0x1400524c1  mov     r14d, 0C0000016h
0x1400524c7  jz      loc_140052571
0x1400524cd  cmp     dword ptr [r15+90h], 3
0x1400524d5  jz      loc_140052571
0x1400524db  cmp     r14d, 0C0000016h
0x1400524e2  jnz     short loc_14005250B
0x1400524e4  mov     r9, [r13+28h]
0x1400524e8  test    r9, r9
0x1400524eb  jnz     short loc_140052520
0x1400524ed  movzx   r8d, dil
0x1400524f1  mov     rdx, r13
0x1400524f4  mov     rcx, rbx
0x1400524f7  call    SmbCeFindOrConstructVNetRootContext
0x1400524fc  mov     r14d, eax
0x1400524ff  cmp     eax, 0C0000016h
0x140052504  jz      short loc_14005254F
0x140052506  mov     edx, 12Fh
0x14005250b  cmp     r14d, 103h
0x140052512  jz      short loc_140052569
0x140052514  xor     edi, edi
0x140052516  test    r14d, r14d
0x140052519  js      short loc_14005257E
0x14005251b  jmp     loc_140052610
0x140052520  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140052527  cmp     rcx, r8
0x14005252a  jz      short loc_14005254F
0x14005252c  test    dword ptr [rcx+2Ch], 200h
0x140052533  jz      short loc_14005254F
0x140052535  mov     rcx, [rcx+18h]
0x140052539  lea     r8, WPP_aded42fed8fd339ff408f5df8f3419c3_Traceguids
0x140052540  mov     edx, 0Fh
0x140052545  mov     [rsp+68h+var_48], r13
0x14005254a  call    WPP_SF_qq
0x14005254f  mov     rcx, [r13+28h]
0x140052553  movzx   r8d, r12b
0x140052557  mov     rdx, r15
0x14005255a  call    SmbCeEstablishConnection
0x14005255f  mov     r14d, eax
0x140052562  mov     edx, 13Eh
0x140052567  jmp     short loc_14005250B
0x140052569  mov     eax, r14d
0x14005256c  jmp     loc_140052684
0x140052571  mov     edx, 129h
0x140052576  xor     edi, edi
0x140052578  mov     r14d, 0C0000201h
0x14005257e  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140052585  jz      short loc_1400525AF
0x140052587  or      edx, 10200000h
0x14005258d  mov     [rsp+68h+var_40], 0
0x140052595  mov     dword ptr [rsp+68h+var_48], edx
0x140052599  lea     r8, [rbx+19Ch]
0x1400525a0  lea     rdx, CreateVNetRootError
0x1400525a7  mov     r9d, r14d
0x1400525aa  call    McTemplateK0qqq_EtwWriteTransfer
0x1400525af  mov     [r13+0B4h], r14d
0x1400525b6  test    rsi, rsi
0x1400525b9  jnz     short loc_1400525D8
0x1400525bb  mov     edi, r14d
0x1400525be  cmp     [rbp+28h], rsi
0x1400525c2  jz      short loc_1400525D8
0x1400525c4  cmp     r14d, 0C000006Dh
0x1400525cb  jz      short loc_1400525D6
0x1400525cd  cmp     r14d, 0C0000022h
0x1400525d4  jnz     short loc_1400525D8
0x1400525d6  xor     edi, edi
0x1400525d8  mov     rcx, r13
0x1400525db  call    SmbCeDestroyAssociatedVNetRootContext
0x1400525e0  test    rbx, rbx
0x1400525e3  jz      short loc_140052610
0x1400525e5  cmp     byte ptr [rbx+20h], 0
0x1400525e9  jnz     short loc_140052610
0x1400525eb  test    byte ptr [rbx+2EDh], 8
0x1400525f2  jz      short loc_140052610
0x1400525f4  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x1400525fb  mov     r8d, [rsp+68h+arg_0]
0x140052600  shl     r8, 8
0x140052604  mov     rcx, [rax]
0x140052607  lock inc dword ptr [r8+rcx+0BCh]
0x140052610  mov     [r15+118h], r14d
0x140052617  mov     [r15+11Ch], edi
0x14005261e  mov     rcx, [rbp+28h]
0x140052622  test    rcx, rcx
0x140052625  jz      short loc_14005262F
0x140052627  mov     rdx, rbp
0x14005262a  call    SmbCeUpdateNetRoot
0x14005262f  mov     rax, [r13+28h]
0x140052633  test    rax, rax
0x140052636  jz      short loc_140052670
0x140052638  mov     rcx, [rax+60h]
0x14005263c  test    rcx, rcx
0x14005263f  jz      short loc_140052670
0x140052641  mov     edx, [r15+118h]
0x140052648  lea     r8, aCallbackRdbssV; "Callback rdbss VNetRoot %p VnrCtxt %p S"...
0x14005264f  mov     rcx, [rcx+10h]
0x140052653  mov     r9, r13
0x140052656  mov     [rsp+68h+var_40], edx
0x14005265a  mov     edx, 1
0x14005265f  mov     [rsp+68h+var_48], rax
0x140052664  call    cs:__imp_RxDiagnosticTrace
0x14005266b  nop     dword ptr [rax+rax+00h]
0x140052670  mov     rax, [r15+110h]
0x140052677  mov     rcx, r15
0x14005267a  call    _guard_dispatch_icall
0x14005267f  mov     eax, 103h
0x140052684  mov     rbx, [rsp+68h+arg_10]
0x14005268c  add     rsp, 30h
0x140052690  pop     r15
0x140052692  pop     r14
0x140052694  pop     r13
0x140052696  pop     r12
0x140052698  pop     rdi
0x140052699  pop     rsi
0x14005269a  pop     rbp
0x14005269b  retn
```
