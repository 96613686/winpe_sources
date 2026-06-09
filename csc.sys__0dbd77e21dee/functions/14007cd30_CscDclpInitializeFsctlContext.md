# CscDclpInitializeFsctlContext

- ea: `0x14007cd30`
- end: `0x14007d2e3`
- name: `CscDclpInitializeFsctlContext`
- size: `1459`
- prototype: `__int64 __fastcall(unsigned int *, __int64, char, char, char)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x14007ae70`

## callees

- `0x1400125a4`
- `0x140012bd0`
- `0x1400169d4`
- `0x140018930`
- `0x1400190ec`
- `0x140019608`
- `0x14001a494`
- `0x14002e67c`
- `0x14002eaec`
- `0x14002f040`
- `0x14002f440`
- `0x1400623f4`
- `0x14007c5b4`
- `0x14007cd30`
- `0x14007d2ec`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x14007cdc6`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14007cdc6`
- `ntoskrnl!IoGetRequestorProcess` at `0x14007cdae`
- `ntoskrnl!IoGetRequestorProcess` at `0x14007cf9b`
- `ntoskrnl!IoGetRequestorProcess` at `0x14007cdae`
- `ntoskrnl!IoGetRequestorProcess` at `0x14007cf9b`

## pseudocode

```c
__int64 __fastcall CscDclpInitializeFsctlContext(unsigned int *a1, __int64 a2, char a3, char a4, char a5)
{
  unsigned int v8; // edi
  IRP *v9; // rcx
  __int64 v10; // rsi
  ULONG RequestorProcessId; // eax
  __int64 v12; // r8
  int v13; // ebx
  int v14; // edi
  const char *FsctlOperationString; // rax
  __int64 v16; // r8
  int v17; // edx
  char v18; // cl
  __int64 v19; // rsi
  char v20; // di
  int v21; // eax
  char v22; // r12
  int v23; // ebx
  unsigned int v24; // esi
  bool v25; // bl
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // ebx
  unsigned int v29; // ebx
  bool v30; // bl
  unsigned __int8 *v31; // rdx
  SIZE_T Length; // [rsp+20h] [rbp-B8h]
  SIZE_T Lengtha; // [rsp+20h] [rbp-B8h]
  _BYTE v35[8]; // [rsp+60h] [rbp-78h] BYREF
  int v36; // [rsp+68h] [rbp-70h] BYREF
  unsigned int v37; // [rsp+6Ch] [rbp-6Ch]
  int v38; // [rsp+70h] [rbp-68h] BYREF
  _DWORD v39[3]; // [rsp+74h] [rbp-64h]
  SIZE_T v40; // [rsp+80h] [rbp-58h]
  ULONG v41; // [rsp+88h] [rbp-50h]
  int v42[2]; // [rsp+90h] [rbp-48h]
  PEPROCESS RequestorProcess; // [rsp+98h] [rbp-40h]
  __int64 v44; // [rsp+A0h] [rbp-38h]
  KPROCESSOR_MODE RequestorMode; // [rsp+E8h] [rbp+10h]

  v8 = *(_DWORD *)(a2 + 568);
  LODWORD(v40) = v8;
  v39[0] = *(_DWORD *)(a2 + 572);
  *(_QWORD *)&v39[1] = *(_QWORD *)(a2 + 552);
  *(_QWORD *)v42 = *(_QWORD *)(a2 + 560);
  v36 = 0;
  v37 = 75;
  v9 = *(IRP **)(a2 + 40);
  LODWORD(v10) = v9->RequestorMode;
  RequestorMode = v9->RequestorMode;
  v35[2] = RequestorMode;
  RequestorProcess = IoGetRequestorProcess(v9);
  RequestorProcessId = IoGetRequestorProcessId(*(PIRP *)(a2 + 40));
  v41 = RequestorProcessId;
  v38 = 5;
  v35[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqDDqqDqD(
      WPP_GLOBAL_Control->AttachedDevice,
      RequestorProcess,
      v12,
      a1,
      a2,
      v8,
      v39[0],
      *(_QWORD *)&v39[1],
      *(_QWORD *)v42,
      v10,
      RequestorProcess,
      RequestorProcessId);
  memset(a1, 0, 0x60u);
  if ( !(unsigned __int8)CscDclIsInternalFsControl(a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
    v13 = -1073741811;
    v14 = 2184;
    goto LABEL_86;
  }
  v35[1] = v10;
  if ( v8 < 8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, 8, v8);
    v13 = -1073741811;
    v14 = 2204;
    goto LABEL_86;
  }
  if ( (_BYTE)v10 )
    RtlCopyFromUser(&v36, *(void **)&v39[1], 8u);
  else
    RtlCopyVolatileMemory(&v36, *(const void **)&v39[1], 8u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    FsctlOperationString = CscDclpGetFsctlOperationString(v37);
    WPP_SF_DDs(*(_QWORD *)(v16 + 24), v17, v16, v36, v18, (__int64)FsctlOperationString);
  }
  if ( v36 != 8 )
  {
    v13 = -1073741496;
    v14 = 2229;
    goto LABEL_86;
  }
  if ( v37 > 0x4A )
  {
    v13 = -1073741811;
    v14 = 2239;
    goto LABEL_86;
  }
  v19 = (__int64)(int)v37 << 6;
  v44 = v19;
  v20 = 1;
  if ( (*(_DWORD *)((_BYTE *)&qword_14003A790[1] + v19) & 1) != 0 )
  {
    if ( !*((_QWORD *)off_14003A6D0 + 14) || RequestorMode != 1 )
    {
      v14 = 2260;
      goto LABEL_29;
    }
    if ( IoGetRequestorProcess(*(PIRP *)(a2 + 40)) != *((PEPROCESS *)off_14003A6D0 + 14) )
    {
      v14 = 2269;
LABEL_29:
      v13 = -1073741790;
LABEL_30:
      LOBYTE(v10) = RequestorMode;
      goto LABEL_86;
    }
  }
  v21 = *(_DWORD *)((char *)&qword_14003A790[1] + v19);
  if ( (v21 & 2) != 0 && !a4 )
  {
    v14 = 2288;
    goto LABEL_29;
  }
  if ( (v21 & 4) != 0 && !a5 )
  {
    v14 = 2294;
    goto LABEL_29;
  }
  if ( (v21 & 8) != 0 && !a3 && !a4 )
  {
    v14 = 2301;
    goto LABEL_29;
  }
  CscDclMRxGetHandleType(a2, &v38, v35);
  v22 = v35[0];
  v23 = v38;
  v24 = *(_DWORD *)((char *)qword_14003A790 + v19 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_DDd(
      WPP_GLOBAL_Control->AttachedDevice,
      28,
      WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids,
      v24,
      v38,
      v35[0]);
  switch ( v24 )
  {
    case 2u:
    case 3u:
      v25 = v23 == v24;
      goto LABEL_57;
    case 4u:
    case 6u:
      goto LABEL_55;
    case 7u:
      if ( v23 != 2 && (v23 != 1 || !v22) )
        break;
LABEL_55:
      v25 = 1;
      goto LABEL_57;
    case 8u:
      v25 = (unsigned int)(v23 - 1) <= 1;
      goto LABEL_57;
  }
  v25 = 0;
LABEL_57:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v25);
  if ( !v25 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids);
    v13 = -1073741808;
    v14 = 2318;
    goto LABEL_30;
  }
  v10 = v44;
  if ( (*(_DWORD *)((_BYTE *)&qword_14003A790[1] + v44) & 0x10) != 0 )
    goto LABEL_78;
  v26 = *(_DWORD *)((char *)qword_14003A790 + v44 + 4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v26);
  v27 = v26 - 2;
  v30 = 1;
  if ( v27 )
  {
    v28 = v27 - 1;
    if ( !v28 || (v29 = v28 - 1) == 0 || v29 == 2 )
      v30 = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids, v30);
  if ( !v30 )
LABEL_78:
    v20 = 0;
  *((_BYTE *)a1 + 4) = v20 | a1[1] & 0xFE;
  LODWORD(Length) = v40;
  v13 = CscDclpInitializeFsctlBufferContext(
          (__int64)(a1 + 8),
          (unsigned __int8 *)qword_14003A7A0 + v10,
          RequestorMode,
          *(unsigned __int64 *)&v39[1],
          Length);
  if ( v13 < 0 )
  {
    v14 = 2339;
    goto LABEL_30;
  }
  v31 = (unsigned __int8 *)&qword_14003A7A0[3] + v10;
  LODWORD(Lengtha) = v39[0];
  LOBYTE(v10) = RequestorMode;
  v13 = CscDclpInitializeFsctlBufferContext((__int64)(a1 + 16), v31, RequestorMode, *(unsigned __int64 *)v42, Lengtha);
  v14 = 0;
  if ( v13 < 0 )
    v14 = 2347;
LABEL_86:
  if ( v13 >= 0 )
  {
    *a1 = v37;
    *((_QWORD *)a1 + 1) = RequestorProcess;
    a1[4] = v41;
    *((_BYTE *)a1 + 24) = v10;
  }
  else
  {
    CscDclpCleanupFsctlContext(a1, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      58,
      WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids,
      (unsigned int)v13,
      v14);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14007cd30  mov     [rsp+arg_18], rbx
0x14007cd35  mov     [rsp+arg_10], r8b
0x14007cd3a  mov     [rsp+arg_0], rcx
0x14007cd3f  push    rsi
0x14007cd40  push    rdi
0x14007cd41  push    r12
0x14007cd43  push    r13
0x14007cd45  push    r15
0x14007cd47  sub     rsp, 0B0h
0x14007cd4e  mov     r12b, r9b
0x14007cd51  mov     rbx, rdx
0x14007cd54  mov     r15, rcx
0x14007cd57  mov     edi, [rdx+238h]
0x14007cd5d  mov     dword ptr [rsp+0D8h+var_58], edi
0x14007cd64  mov     eax, [rdx+23Ch]
0x14007cd6a  mov     dword ptr [rsp+0D8h+var_64], eax
0x14007cd6e  mov     rax, [rdx+228h]
0x14007cd75  mov     qword ptr [rsp+0D8h+var_64+4], rax
0x14007cd7a  mov     rax, [rdx+230h]
0x14007cd81  mov     qword ptr [rsp+0D8h+var_48], rax
0x14007cd89  mov     [rsp+0D8h+var_70], 0
0x14007cd91  mov     [rsp+0D8h+var_6C], 4Bh ; 'K'
0x14007cd99  mov     rcx, [rdx+28h]; Irp
0x14007cd9d  movsx   esi, byte ptr [rcx+40h]
0x14007cda1  mov     byte ptr [rsp+0D8h+arg_8], sil
0x14007cda9  mov     [rsp+0D8h+var_76], sil
0x14007cdae  call    cs:__imp_IoGetRequestorProcess
0x14007cdb5  nop     dword ptr [rax+rax+00h]
0x14007cdba  mov     [rsp+0D8h+var_40], rax
0x14007cdc2  mov     rcx, [rbx+28h]; Irp
0x14007cdc6  call    cs:__imp_IoGetRequestorProcessId
0x14007cdcd  nop     dword ptr [rax+rax+00h]
0x14007cdd2  mov     [rsp+0D8h+var_50], eax
0x14007cdd9  mov     [rsp+0D8h+var_68], 5
0x14007cde1  mov     [rsp+0D8h+var_78], 0
0x14007cde6  lea     r13, WPP_GLOBAL_Control
0x14007cded  mov     rcx, cs:WPP_GLOBAL_Control
0x14007cdf4  cmp     rcx, r13
0x14007cdf7  jz      short loc_14007CE4A
0x14007cdf9  mov     edx, [rcx+2Ch]
0x14007cdfc  test    dl, 40h
0x14007cdff  jz      short loc_14007CE4A
0x14007ce01  mov     [rsp+0D8h+var_80], eax
0x14007ce05  mov     rdx, [rsp+0D8h+var_40]
0x14007ce0d  mov     [rsp+0D8h+var_88], rdx
0x14007ce12  mov     [rsp+0D8h+var_90], esi
0x14007ce16  mov     rax, qword ptr [rsp+0D8h+var_48]
0x14007ce1e  mov     [rsp+0D8h+var_98], rax
0x14007ce23  mov     rax, qword ptr [rsp+0D8h+var_64+4]
0x14007ce28  mov     [rsp+0D8h+var_A0], rax
0x14007ce2d  mov     eax, dword ptr [rsp+0D8h+var_64]
0x14007ce31  mov     [rsp+0D8h+var_A8], eax
0x14007ce35  mov     dword ptr [rsp+0D8h+var_B0], edi
0x14007ce39  mov     [rsp+0D8h+Length], rbx
0x14007ce3e  mov     r9, r15
0x14007ce41  mov     rcx, [rcx+18h]
0x14007ce45  call    WPP_SF_qqDDqqDqD
0x14007ce4a  xor     edx, edx; Val
0x14007ce4c  lea     r8d, [rdx+60h]; Size
0x14007ce50  mov     rcx, r15; void *
0x14007ce53  call    memset
0x14007ce58  mov     rcx, rbx
0x14007ce5b  call    CscDclIsInternalFsControl
0x14007ce60  test    al, al
0x14007ce62  jnz     short loc_14007CE9B
0x14007ce64  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ce6b  cmp     rcx, r13
0x14007ce6e  jz      short loc_14007CE8C
0x14007ce70  mov     eax, [rcx+2Ch]
0x14007ce73  test    al, 40h
0x14007ce75  jz      short loc_14007CE8C
0x14007ce77  mov     edx, 36h ; '6'
0x14007ce7c  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007ce83  mov     rcx, [rcx+18h]
0x14007ce87  call    WPP_SF_
0x14007ce8c  mov     ebx, 0C000000Dh
0x14007ce91  mov     edi, 888h
0x14007ce96  jmp     loc_14007D267
0x14007ce9b  mov     [rsp+0D8h+var_77], sil
0x14007cea0  mov     r8d, 8; Size
0x14007cea6  cmp     edi, r8d
0x14007cea9  jnb     short loc_14007CEE8
0x14007ceab  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ceb2  cmp     rcx, r13
0x14007ceb5  jz      short loc_14007CED9
0x14007ceb7  mov     eax, [rcx+2Ch]
0x14007ceba  test    al, 40h
0x14007cebc  jz      short loc_14007CED9
0x14007cebe  lea     edx, [r8+2Fh]
0x14007cec2  mov     dword ptr [rsp+0D8h+Length], edi
0x14007cec6  mov     r9d, r8d
0x14007cec9  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007ced0  mov     rcx, [rcx+18h]
0x14007ced4  call    WPP_SF_Dd
0x14007ced9  mov     ebx, 0C000000Dh
0x14007cede  mov     edi, 89Ch
0x14007cee3  jmp     loc_14007D267
0x14007cee8  mov     rdx, qword ptr [rsp+0D8h+var_64+4]; Src
0x14007ceed  lea     rcx, [rsp+0D8h+var_70]; void *
0x14007cef2  test    sil, sil
0x14007cef5  jz      short loc_14007CEFE
0x14007cef7  call    RtlCopyFromUser
0x14007cefc  jmp     short loc_14007CF04
0x14007cefe  call    RtlCopyVolatileMemory
0x14007cf03  nop
0x14007cf04  mov     r8, cs:WPP_GLOBAL_Control
0x14007cf0b  cmp     r8, r13
0x14007cf0e  jz      short loc_14007CF38
0x14007cf10  mov     eax, [r8+2Ch]
0x14007cf14  test    al, 40h
0x14007cf16  jz      short loc_14007CF38
0x14007cf18  mov     ecx, [rsp+0D8h+var_6C]
0x14007cf1c  call    CscDclpGetFsctlOperationString
0x14007cf21  mov     [rsp+0D8h+var_B0], rax
0x14007cf26  mov     dword ptr [rsp+0D8h+Length], ecx
0x14007cf2a  mov     r9d, [rsp+0D8h+var_70]
0x14007cf2f  mov     rcx, [r8+18h]
0x14007cf33  call    WPP_SF_DDs
0x14007cf38  cmp     [rsp+0D8h+var_70], 8
0x14007cf3d  jz      short loc_14007CF4E
0x14007cf3f  mov     ebx, 0C0000148h
0x14007cf44  mov     edi, 8B5h
0x14007cf49  jmp     loc_14007D267
0x14007cf4e  cmp     [rsp+0D8h+var_6C], 4Ah ; 'J'
0x14007cf53  ja      loc_14007D240
0x14007cf59  movsxd  rsi, [rsp+0D8h+var_6C]
0x14007cf5e  shl     rsi, 6
0x14007cf62  mov     [rsp+0D8h+var_38], rsi
0x14007cf6a  lea     rax, qword_14003A790
0x14007cf71  mov     eax, [rsi+rax+8]
0x14007cf75  mov     edi, 1
0x14007cf7a  test    dil, al
0x14007cf7d  jz      short loc_14007CFD2
0x14007cf7f  mov     rax, cs:off_14003A6D0
0x14007cf86  cmp     qword ptr [rax+70h], 0
0x14007cf8b  jz      short loc_14007CFBB
0x14007cf8d  cmp     byte ptr [rsp+0D8h+arg_8], dil
0x14007cf95  jnz     short loc_14007CFBB
0x14007cf97  mov     rcx, [rbx+28h]; Irp
0x14007cf9b  call    cs:__imp_IoGetRequestorProcess
0x14007cfa2  nop     dword ptr [rax+rax+00h]
0x14007cfa7  mov     rcx, cs:off_14003A6D0
0x14007cfae  cmp     rax, [rcx+70h]
0x14007cfb2  jz      short loc_14007CFD2
0x14007cfb4  mov     edi, 8DDh
0x14007cfb9  jmp     short loc_14007CFC0
0x14007cfbb  mov     edi, 8D4h
0x14007cfc0  mov     ebx, 0C0000022h
0x14007cfc5  mov     sil, byte ptr [rsp+0D8h+arg_8]
0x14007cfcd  jmp     loc_14007D267
0x14007cfd2  lea     rax, qword_14003A790
0x14007cfd9  mov     eax, [rsi+rax+8]
0x14007cfdd  test    al, 2
0x14007cfdf  jz      short loc_14007CFED
0x14007cfe1  test    r12b, r12b
0x14007cfe4  jnz     short loc_14007CFED
0x14007cfe6  mov     edi, 8F0h
0x14007cfeb  jmp     short loc_14007CFC0
0x14007cfed  test    al, 4
0x14007cfef  jz      short loc_14007D002
0x14007cff1  cmp     [rsp+0D8h+arg_20], 0
0x14007cff9  jnz     short loc_14007D002
0x14007cffb  mov     edi, 8F6h
0x14007d000  jmp     short loc_14007CFC0
0x14007d002  test    al, 8
0x14007d004  jz      short loc_14007D01C
0x14007d006  cmp     [rsp+0D8h+arg_10], 0
0x14007d00e  jnz     short loc_14007D01C
0x14007d010  test    r12b, r12b
0x14007d013  jnz     short loc_14007D01C
0x14007d015  mov     edi, 8FDh
0x14007d01a  jmp     short loc_14007CFC0
0x14007d01c  lea     r8, [rsp+0D8h+var_78]
0x14007d021  lea     rdx, [rsp+0D8h+var_68]
0x14007d026  mov     rcx, rbx
0x14007d029  call    CscDclMRxGetHandleType
0x14007d02e  movzx   r12d, [rsp+0D8h+var_78]
0x14007d034  mov     ebx, [rsp+0D8h+var_68]
0x14007d038  lea     rax, qword_14003A790
0x14007d03f  mov     esi, [rsi+rax+4]
0x14007d043  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d04a  cmp     rcx, r13
0x14007d04d  jz      short loc_14007D077
0x14007d04f  mov     eax, [rcx+2Ch]
0x14007d052  test    al, 40h
0x14007d054  jz      short loc_14007D077
0x14007d056  mov     edx, 1Ch
0x14007d05b  mov     dword ptr [rsp+0D8h+var_B0], r12d
0x14007d060  mov     dword ptr [rsp+0D8h+Length], ebx
0x14007d064  mov     r9d, esi
0x14007d067  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007d06e  mov     rcx, [rcx+18h]
0x14007d072  call    WPP_SF_DDd
0x14007d077  mov     ecx, esi
0x14007d079  sub     ecx, 2
0x14007d07c  jz      short loc_14007D0B4
0x14007d07e  sub     ecx, edi
0x14007d080  jz      short loc_14007D0B4
0x14007d082  sub     ecx, edi
0x14007d084  jz      short loc_14007D0AF
0x14007d086  sub     ecx, 2
0x14007d089  jz      short loc_14007D0AF
0x14007d08b  sub     ecx, edi
0x14007d08d  jz      short loc_14007D0A1
0x14007d08f  cmp     ecx, edi
0x14007d091  jz      short loc_14007D097
0x14007d093  xor     bl, bl
0x14007d095  jmp     short loc_14007D0B9
0x14007d097  lea     eax, [rbx-1]
0x14007d09a  cmp     eax, edi
0x14007d09c  setbe   bl
0x14007d09f  jmp     short loc_14007D0B9
0x14007d0a1  cmp     ebx, 2
0x14007d0a4  jz      short loc_14007D0AF
0x14007d0a6  cmp     ebx, edi
0x14007d0a8  jnz     short loc_14007D093
0x14007d0aa  test    r12b, r12b
0x14007d0ad  jz      short loc_14007D093
0x14007d0af  mov     bl, dil
0x14007d0b2  jmp     short loc_14007D0B9
0x14007d0b4  cmp     ebx, esi
0x14007d0b6  setz    bl
0x14007d0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d0c0  cmp     rcx, r13
0x14007d0c3  jz      short loc_14007D0E5
0x14007d0c5  mov     eax, [rcx+2Ch]
0x14007d0c8  test    al, 40h
0x14007d0ca  jz      short loc_14007D0E5
0x14007d0cc  movzx   r9d, bl
0x14007d0d0  mov     edx, 1Dh
0x14007d0d5  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007d0dc  mov     rcx, [rcx+18h]
0x14007d0e0  call    WPP_SF_d
0x14007d0e5  test    bl, bl
0x14007d0e7  jnz     short loc_14007D120
0x14007d0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d0f0  cmp     rcx, r13
0x14007d0f3  jz      short loc_14007D111
0x14007d0f5  mov     eax, [rcx+2Ch]
0x14007d0f8  test    al, 40h
0x14007d0fa  jz      short loc_14007D111
0x14007d0fc  mov     edx, 39h ; '9'
0x14007d101  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007d108  mov     rcx, [rcx+18h]
0x14007d10c  call    WPP_SF_
0x14007d111  mov     ebx, 0C0000010h
0x14007d116  mov     edi, 90Eh
0x14007d11b  jmp     loc_14007CFC5
0x14007d120  mov     rsi, [rsp+0D8h+var_38]
0x14007d128  lea     r12, qword_14003A790
0x14007d12f  mov     eax, [rsi+r12+8]
0x14007d134  test    al, 10h
0x14007d136  jnz     short loc_14007D1B7
0x14007d138  mov     ebx, [rsi+r12+4]
0x14007d13d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d144  cmp     rcx, r13
0x14007d147  jz      short loc_14007D168
0x14007d149  mov     eax, [rcx+2Ch]
0x14007d14c  test    al, 40h
0x14007d14e  jz      short loc_14007D168
0x14007d150  mov     edx, 1Eh
0x14007d155  mov     r9d, ebx
0x14007d158  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007d15f  mov     rcx, [rcx+18h]
0x14007d163  call    WPP_SF_d
0x14007d168  sub     ebx, 2
0x14007d16b  jz      short loc_14007D184
0x14007d16d  sub     ebx, edi
0x14007d16f  jz      loc_14007D200
0x14007d175  sub     ebx, edi
0x14007d177  jz      loc_14007D200
0x14007d17d  sub     ebx, 2
0x14007d180  jz      short loc_14007D200
0x14007d182  sub     ebx, edi
0x14007d184  mov     bl, dil
0x14007d187  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d18e  cmp     rcx, r13
0x14007d191  jz      short loc_14007D1B3
0x14007d193  mov     eax, [rcx+2Ch]
0x14007d196  test    al, 40h
0x14007d198  jz      short loc_14007D1B3
0x14007d19a  movzx   r9d, bl
0x14007d19e  mov     edx, 1Fh
0x14007d1a3  lea     r8, WPP_eecef44b7ac9316d867330dcd3fb60ff_Traceguids
0x14007d1aa  mov     rcx, [rcx+18h]
0x14007d1ae  call    WPP_SF_d
0x14007d1b3  test    bl, bl
0x14007d1b5  jnz     short loc_14007D1BA
0x14007d1b7  xor     dil, dil
0x14007d1ba  mov     al, [r15+4]
0x14007d1be  and     al, 0FEh
0x14007d1c0  or      al, dil
0x14007d1c3  mov     [r15+4], al
0x14007d1c7  lea     rdx, [r12+10h]
0x14007d1cc  add     rdx, rsi; int
0x14007d1cf  lea     rcx, [r15+20h]; int
0x14007d1d3  mov     eax, dword ptr [rsp+0D8h+var_58]
0x14007d1da  mov     dword ptr [rsp+0D8h+Length], eax; Length
0x14007d1de  mov     r9, qword ptr [rsp+0D8h+var_64+4]; int
0x14007d1e3  mov     r8b, byte ptr [rsp+0D8h+arg_8]; int
  ... truncated ...
```
