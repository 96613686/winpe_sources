# ClfsDeleteLogByPointer

- ea: `0x1400335a0`
- end: `0x1400337de`
- name: `ClfsDeleteLogByPointer`
- size: `574`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14004b920`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140011d90`
- `0x140017f20`
- `0x1400335a0`
- `0x140045da0`
- `0x14004d510`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14003366a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003366a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003378e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003378e`

## string_xrefs

- `0x1400335f1`: `ClfsDeleteLogByPointer`
- `0x140033636`: `ClfsDeleteLogByPointer`
- `0x14003375f`: `ClfsDeleteLogByPointer`
- `0x1400337c0`: `ClfsDeleteLogByPointer`

## pseudocode

```c
NTSTATUS __stdcall ClfsDeleteLogByPointer(PLOG_FILE_OBJECT plfoLog)
{
  CClfsLogFcbCommon *v3; // r15
  CClfsLogCcb *FsContext2; // r13
  NTSTATUS v5; // ebx
  __int64 v6; // [rsp+30h] [rbp-38h]
  _FILE_DISPOSITION_INFORMATION v7; // [rsp+70h] [rbp+8h] BYREF
  CClfsLogFcbCommon *v8; // [rsp+78h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      61,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsDeleteLogByPointer",
      238);
  }
  if ( plfoLog )
  {
    KeEnterCriticalRegion();
    v3 = (CClfsLogFcbCommon *)*((_QWORD *)plfoLog->FsContext + 15);
    v8 = v3;
    FsContext2 = (CClfsLogCcb *)plfoLog->FsContext2;
    (*(void (__fastcall **)(CClfsLogFcbCommon *))(*(_QWORD *)v3 + 64LL))(v3);
    CClfsLogCcb::AddRef(FsContext2);
    v5 = 0;
    if ( !*(_BYTE *)(*((_QWORD *)FsContext2 + 9) + 76LL) )
      v5 = -1073741790;
    HIDWORD(v6) = v5;
    LODWORD(v6) = v5;
    if ( v5 >= 0 )
    {
      v7.DeleteFile = 1;
      v5 = CClfsLogFcbCommon::DeleteLog(v3, plfoLog, &v7);
      LODWORD(v6) = v5;
      if ( v5 < 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          64,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsDeleteLogByPointer",
          58,
          v5,
          v6);
      }
    }
    else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        63,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDeleteLogByPointer",
        33,
        -1073741811,
        v6);
    }
    (*(void (__fastcall **)(CClfsLogFcbCommon *))(*(_QWORD *)v3 + 72LL))(v3);
    CClfsLogCcb::Release((volatile signed __int32 *)FsContext2);
    KeLeaveCriticalRegion();
    if ( v5 >= 0
      && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        65,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDeleteLogByPointer",
        95);
    }
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        62,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDeleteLogByPointer",
        250,
        -1073741811);
    }
    return -1073741811;
  }
}

```

## disassembly

```asm
0x1400335a0  mov     rax, rsp
0x1400335a3  mov     [rax+18h], rbx
0x1400335a7  mov     [rax+20h], rsi
0x1400335ab  push    r13
0x1400335ad  push    r14
0x1400335af  push    r15
0x1400335b1  sub     rsp, 50h
0x1400335b5  mov     r14, rcx
0x1400335b8  mov     qword ptr [rax-28h], 0
0x1400335c0  mov     qword ptr [rax-30h], 0
0x1400335c8  lea     rsi, WPP_GLOBAL_Control
0x1400335cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400335d6  cmp     rcx, rsi
0x1400335d9  jz      short loc_140033608
0x1400335db  mov     eax, [rcx+2Ch]
0x1400335de  bt      eax, 1Ah
0x1400335e2  jnb     short loc_140033608
0x1400335e4  mov     edx, 3Dh ; '='
0x1400335e9  mov     [rsp+68h+var_48], 7EEh
0x1400335f1  lea     r9, aClfsdeletelogb; "ClfsDeleteLogByPointer"
0x1400335f8  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400335ff  mov     rcx, [rcx+18h]
0x140033603  call    WPP_SF_sd
0x140033608  test    r14, r14
0x14003360b  jnz     short loc_14003366A
0x14003360d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033614  cmp     rcx, rsi
0x140033617  jz      short loc_14003364D
0x140033619  test    dword ptr [rcx+2Ch], 4000000h
0x140033620  jz      short loc_14003364D
0x140033622  lea     edx, [r14+3Eh]
0x140033626  mov     [rsp+68h+var_40], 0C000000Dh
0x14003362e  mov     [rsp+68h+var_48], 7FAh
0x140033636  lea     r9, aClfsdeletelogb; "ClfsDeleteLogByPointer"
0x14003363d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140033644  mov     rcx, [rcx+18h]
0x140033648  call    WPP_SF_slD
0x14003364d  mov     eax, 0C000000Dh
0x140033652  lea     r11, [rsp+68h+var_18]
0x140033657  mov     rbx, [r11+30h]
0x14003365b  mov     rsi, [r11+38h]
0x14003365f  mov     rsp, r11
0x140033662  pop     r15
0x140033664  pop     r14
0x140033666  pop     r13
0x140033668  retn
0x14003366a  call    cs:__imp_KeEnterCriticalRegion
0x140033671  nop     dword ptr [rax+rax+00h]
0x140033676  mov     rax, [r14+18h]
0x14003367a  mov     r15, [rax+78h]
0x14003367e  mov     [rsp+68h+arg_8], r15
0x140033683  mov     [rsp+68h+var_28], r15
0x140033688  mov     r13, [r14+20h]
0x14003368c  mov     [rsp+68h+var_30], r13
0x140033691  mov     rax, [r15]
0x140033694  mov     rax, [rax+40h]
0x140033698  mov     rcx, r15
0x14003369b  call    _guard_dispatch_icall
0x1400336a0  mov     rcx, r13; this
0x1400336a3  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x1400336a8  mov     [rsp+68h+var_34], 0
0x1400336b0  mov     rax, [r13+48h]
0x1400336b4  xor     ebx, ebx
0x1400336b6  mov     ecx, 0C0000022h
0x1400336bb  cmp     [rax+4Ch], bl
0x1400336be  cmovz   ebx, ecx
0x1400336c1  mov     [rsp+68h+var_34], ebx
0x1400336c5  mov     [rsp+68h+var_38], ebx
0x1400336c9  test    ebx, ebx
0x1400336cb  jns     short loc_140033701
0x1400336cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400336d4  cmp     rcx, rsi
0x1400336d7  jz      loc_140033777
0x1400336dd  mov     eax, [rcx+2Ch]
0x1400336e0  bt      eax, 1Ah
0x1400336e4  jnb     loc_140033777
0x1400336ea  mov     edx, 3Fh ; '?'
0x1400336ef  mov     [rsp+68h+var_40], 0C000000Dh
0x1400336f7  mov     [rsp+68h+var_48], 821h
0x1400336ff  jmp     short loc_14003375F
0x140033701  mov     [rsp+68h+arg_0.DeleteFile], 1
0x140033706  lea     r8, [rsp+68h+arg_0]; struct _FILE_DISPOSITION_INFORMATION *
0x14003370b  mov     rdx, r14; struct _FILE_OBJECT *
0x14003370e  mov     rcx, r15; this
0x140033711  call    ?DeleteLog@CClfsLogFcbCommon@@QEAAJPEAU_FILE_OBJECT@@PEAU_FILE_DISPOSITION_INFORMATION@@@Z; CClfsLogFcbCommon::DeleteLog(_FILE_OBJECT *,_FILE_DISPOSITION_INFORMATION *)
0x140033716  mov     ebx, eax
0x140033718  mov     [rsp+68h+var_38], eax
0x14003371c  jmp     short loc_140033735
0x14003371e  mov     ebx, eax
0x140033720  mov     [rsp+68h+var_38], eax
0x140033724  lea     rsi, WPP_GLOBAL_Control
0x14003372b  mov     r13, [rsp+68h+var_30]
0x140033730  mov     r15, [rsp+68h+arg_8]
0x140033735  test    ebx, ebx
0x140033737  jns     short loc_140033777
0x140033739  mov     rcx, cs:WPP_GLOBAL_Control
0x140033740  cmp     rcx, rsi
0x140033743  jz      short loc_140033777
0x140033745  mov     eax, [rcx+2Ch]
0x140033748  bt      eax, 1Ah
0x14003374c  jnb     short loc_140033777
0x14003374e  mov     edx, 40h ; '@'
0x140033753  mov     [rsp+68h+var_40], ebx
0x140033757  mov     [rsp+68h+var_48], 83Ah
0x14003375f  lea     r9, aClfsdeletelogb; "ClfsDeleteLogByPointer"
0x140033766  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14003376d  mov     rcx, [rcx+18h]
0x140033771  call    WPP_SF_slD
0x140033776  nop
0x140033777  mov     rax, [r15]
0x14003377a  mov     rax, [rax+48h]
0x14003377e  mov     rcx, r15
0x140033781  call    _guard_dispatch_icall
0x140033786  mov     rcx, r13; Entry
0x140033789  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14003378e  call    cs:__imp_KeLeaveCriticalRegion
0x140033795  nop     dword ptr [rax+rax+00h]
0x14003379a  test    ebx, ebx
0x14003379c  js      short loc_1400337D7
0x14003379e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400337a5  cmp     rcx, rsi
0x1400337a8  jz      short loc_1400337D7
0x1400337aa  test    dword ptr [rcx+2Ch], 4000000h
0x1400337b1  jz      short loc_1400337D7
0x1400337b3  mov     edx, 41h ; 'A'
0x1400337b8  mov     [rsp+68h+var_48], 85Fh
0x1400337c0  lea     r9, aClfsdeletelogb; "ClfsDeleteLogByPointer"
0x1400337c7  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400337ce  mov     rcx, [rcx+18h]
0x1400337d2  call    WPP_SF_sd
0x1400337d7  mov     eax, ebx
0x1400337d9  jmp     loc_140033652
0x14007cd7a  push    rbp
0x14007cd7c  sub     rsp, 30h
0x14007cd80  mov     rbp, rdx
0x14007cd83  mov     rcx, [rbp+40h]
0x14007cd87  test    rcx, rcx
0x14007cd8a  jz      short loc_14007CDA0
0x14007cd8c  mov     rax, [rcx]
0x14007cd8f  mov     rax, [rax+48h]
0x14007cd93  call    _guard_dispatch_icall
0x14007cd98  mov     qword ptr [rbp+40h], 0
0x14007cda0  mov     rcx, [rbp+38h]; Entry
0x14007cda4  test    rcx, rcx
0x14007cda7  jz      short loc_14007CDB6
0x14007cda9  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007cdae  mov     qword ptr [rbp+38h], 0
0x14007cdb6  call    cs:__imp_KeLeaveCriticalRegion
0x14007cdbd  nop     dword ptr [rax+rax+00h]
0x14007cdc2  nop
0x14007cdc3  add     rsp, 30h
0x14007cdc7  pop     rbp
0x14007cdc8  retn
```
