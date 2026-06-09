# HsmpCldGetSyncPolicyByPath

- ea: `0x1400516f0`
- end: `0x140051914`
- name: `HsmpCldGetSyncPolicyByPath`
- size: `548`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004f5f0`
- `0x140052454`
- `0x14006474c`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000dee4`
- `0x14001e220`
- `0x140033858`
- `0x1400516f0`
- `0x140057bb8`
- `0x14005f74c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400517de`
- `ntoskrnl!ObfDereferenceObject` at `0x1400517de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051811`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051811`
- `FLTMGR!FltClose` at `0x1400517f4`
- `FLTMGR!FltClose` at `0x1400517f4`

## pseudocode

```c
__int64 __fastcall HsmpCldGetSyncPolicyByPath(__int64 a1, unsigned __int16 *a2, _DWORD *a3)
{
  __int64 SyncRootInfoByFileObject; // rbx
  __int64 v5; // rcx
  PVOID v6; // rdi
  int v9; // eax
  __int64 v10; // rcx
  PVOID v12; // rbp
  PVOID P; // [rsp+60h] [rbp+8h] BYREF
  PVOID Object; // [rsp+70h] [rbp+18h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp+20h] BYREF

  LODWORD(SyncRootInfoByFileObject) = 0;
  v5 = *(_QWORD *)(a1 + 16);
  v6 = 0;
  FileHandle = 0;
  Object = 0;
  P = 0;
  v9 = ((__int64 (__fastcall *)(__int64))qword_1400296C0)(v5);
  v10 = *(_QWORD *)(a1 + 16);
  *a3 = v9;
  if ( ((__int64 (__fastcall *)(__int64, unsigned __int16 *))qword_1400296A0)(v10, a2) )
    return (unsigned int)SyncRootInfoByFileObject;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1);
  }
  LODWORD(SyncRootInfoByFileObject) = HsmiCldOpenSyncRoot(a1, a2, &FileHandle, (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus((unsigned int)SyncRootInfoByFileObject);
  v12 = Object;
  if ( (int)SyncRootInfoByFileObject < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
        a1,
        SyncRootInfoByFileObject);
    }
  }
  else
  {
    if ( !Object )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a1);
      }
      goto LABEL_10;
    }
    SyncRootInfoByFileObject = (unsigned int)HsmiCldLoadSyncRootInfoByFileObject(
                                               a1,
                                               (struct _FILE_OBJECT *)Object,
                                               (UCHAR **)&P);
    HsmDbgBreakOnStatus(SyncRootInfoByFileObject);
    if ( (int)SyncRootInfoByFileObject < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(
          WPP_GLOBAL_Control->AttachedDevice,
          42,
          WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids,
          a1,
          SyncRootInfoByFileObject);
      }
      v6 = P;
    }
    else
    {
      v6 = P;
      *a3 = HsmiCldBuildSyncPolicy(P);
    }
  }
  if ( v12 )
    ObfDereferenceObject(v12);
LABEL_10:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v6 )
    ExFreePoolWithTag(v6, 0x69537348u);
  return (unsigned int)SyncRootInfoByFileObject;
}

```

## disassembly

```asm
0x1400516f0  mov     rax, rsp
0x1400516f3  mov     [rax+10h], rbx
0x1400516f7  push    rbp
0x1400516f8  push    rsi
0x1400516f9  push    rdi
0x1400516fa  push    r12
0x1400516fc  push    r14
0x1400516fe  sub     rsp, 30h
0x140051702  xor     ebx, ebx
0x140051704  mov     rsi, rcx
0x140051707  mov     rcx, [rcx+10h]
0x14005170b  xor     edi, edi
0x14005170d  mov     [rax+20h], rbx
0x140051711  mov     r14, r8
0x140051714  mov     [rax+18h], rbx
0x140051718  mov     rbp, rdx
0x14005171b  mov     [rax+8], rdi
0x14005171f  mov     rax, cs:qword_1400296C0
0x140051726  call    _guard_dispatch_icall
0x14005172b  mov     rcx, [rsi+10h]
0x14005172f  mov     rdx, rbp
0x140051732  mov     [r14], eax
0x140051735  mov     rax, cs:qword_1400296A0
0x14005173c  call    _guard_dispatch_icall
0x140051741  test    rax, rax
0x140051744  jz      short loc_14005175A
0x140051746  mov     eax, ebx
0x140051748  mov     rbx, [rsp+58h+arg_8]
0x14005174d  add     rsp, 30h
0x140051751  pop     r14
0x140051753  pop     r12
0x140051755  pop     rdi
0x140051756  pop     rsi
0x140051757  pop     rbp
0x140051758  retn
0x14005175a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051761  lea     r12, WPP_GLOBAL_Control
0x140051768  cmp     rcx, r12
0x14005176b  jnz     loc_140051822
0x140051771  lea     r9, [rsp+58h+Object]
0x140051776  mov     rdx, rbp
0x140051779  lea     r8, [rsp+58h+FileHandle]
0x14005177e  mov     rcx, rsi
0x140051781  call    HsmiCldOpenSyncRoot
0x140051786  mov     ecx, eax
0x140051788  mov     ebx, eax
0x14005178a  call    HsmDbgBreakOnStatus
0x14005178f  mov     rbp, [rsp+58h+Object]
0x140051794  test    ebx, ebx
0x140051796  js      loc_14005188E
0x14005179c  test    rbp, rbp
0x14005179f  jz      loc_140051854
0x1400517a5  lea     r8, [rsp+58h+P]
0x1400517aa  mov     rdx, rbp
0x1400517ad  mov     rcx, rsi
0x1400517b0  call    HsmiCldLoadSyncRootInfoByFileObject
0x1400517b5  mov     ecx, eax
0x1400517b7  mov     ebx, eax
0x1400517b9  call    HsmDbgBreakOnStatus
0x1400517be  test    ebx, ebx
0x1400517c0  js      loc_1400518D5
0x1400517c6  mov     rdi, [rsp+58h+P]
0x1400517cb  mov     rcx, rdi
0x1400517ce  call    HsmiCldBuildSyncPolicy
0x1400517d3  mov     [r14], eax
0x1400517d6  test    rbp, rbp
0x1400517d9  jz      short loc_1400517EA
0x1400517db  mov     rcx, rbp; Object
0x1400517de  call    cs:__imp_ObfDereferenceObject
0x1400517e5  nop     dword ptr [rax+rax+00h]
0x1400517ea  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x1400517ef  test    rcx, rcx
0x1400517f2  jz      short loc_140051800
0x1400517f4  call    cs:__imp_FltClose
0x1400517fb  nop     dword ptr [rax+rax+00h]
0x140051800  test    rdi, rdi
0x140051803  jz      loc_140051746
0x140051809  mov     edx, 69537348h; Tag
0x14005180e  mov     rcx, rdi; P
0x140051811  call    cs:__imp_ExFreePoolWithTag
0x140051818  nop     dword ptr [rax+rax+00h]
0x14005181d  jmp     loc_140051746
0x140051822  mov     eax, [rcx+2Ch]
0x140051825  test    al, 1
0x140051827  jz      loc_140051771
0x14005182d  cmp     byte ptr [rcx+29h], 3
0x140051831  jb      loc_140051771
0x140051837  mov     rcx, [rcx+18h]
0x14005183b  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140051842  mov     edx, 27h ; '''
0x140051847  mov     r9, rsi
0x14005184a  call    WPP_SF_q
0x14005184f  jmp     loc_140051771
0x140051854  mov     rcx, cs:WPP_GLOBAL_Control
0x14005185b  cmp     rcx, r12
0x14005185e  jz      short loc_1400517EA
0x140051860  mov     eax, [rcx+2Ch]
0x140051863  test    al, 1
0x140051865  jz      short loc_1400517EA
0x140051867  cmp     byte ptr [rcx+29h], 3
0x14005186b  jb      loc_1400517EA
0x140051871  mov     rcx, [rcx+18h]
0x140051875  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005187c  mov     edx, 29h ; ')'
0x140051881  mov     r9, rsi
0x140051884  call    WPP_SF_q
0x140051889  jmp     loc_1400517EA
0x14005188e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051895  cmp     rcx, r12
0x140051898  jz      loc_1400517D6
0x14005189e  mov     edx, [rcx+2Ch]
0x1400518a1  test    dl, 1
0x1400518a4  jz      loc_1400517D6
0x1400518aa  cmp     byte ptr [rcx+29h], 2
0x1400518ae  jb      loc_1400517D6
0x1400518b4  mov     rcx, [rcx+18h]
0x1400518b8  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x1400518bf  mov     edx, 28h ; '('
0x1400518c4  mov     [rsp+58h+var_38], ebx
0x1400518c8  mov     r9, rsi
0x1400518cb  call    WPP_SF_qd
0x1400518d0  jmp     loc_1400517D6
0x1400518d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400518dc  cmp     rcx, r12
0x1400518df  jz      short loc_14005190A
0x1400518e1  mov     eax, [rcx+2Ch]
0x1400518e4  test    al, 1
0x1400518e6  jz      short loc_14005190A
0x1400518e8  cmp     byte ptr [rcx+29h], 2
0x1400518ec  jb      short loc_14005190A
0x1400518ee  mov     rcx, [rcx+18h]
0x1400518f2  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x1400518f9  mov     edx, 2Ah ; '*'
0x1400518fe  mov     [rsp+58h+var_38], ebx
0x140051902  mov     r9, rsi
0x140051905  call    WPP_SF_qd
0x14005190a  mov     rdi, [rsp+58h+P]
0x14005190f  jmp     loc_1400517D6
```
