# HsmpCldGetSyncPolicyByPath

- ea: `0x140051810`
- end: `0x140051a34`
- name: `HsmpCldGetSyncPolicyByPath`
- size: `548`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004f710`
- `0x140052574`
- `0x14006486c`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000dee4`
- `0x14001e2a0`
- `0x140033858`
- `0x140051810`
- `0x140057cd8`
- `0x14005f86c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400518fe`
- `ntoskrnl!ObfDereferenceObject` at `0x1400518fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051931`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051931`
- `FLTMGR!FltClose` at `0x140051914`
- `FLTMGR!FltClose` at `0x140051914`

## pseudocode

```c
__int64 __fastcall HsmpCldGetSyncPolicyByPath(__int64 a1, unsigned __int16 *a2, _DWORD *a3)
{
  int SyncRootInfoByFileObject; // ebx
  __int64 v5; // rcx
  PVOID v6; // rdi
  int v9; // eax
  __int64 v10; // rcx
  PVOID v12; // rbp
  PVOID P; // [rsp+60h] [rbp+8h] BYREF
  PVOID Object; // [rsp+70h] [rbp+18h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp+20h] BYREF

  SyncRootInfoByFileObject = 0;
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
  SyncRootInfoByFileObject = HsmiCldOpenSyncRoot(a1, a2, &FileHandle, (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus(SyncRootInfoByFileObject);
  v12 = Object;
  if ( SyncRootInfoByFileObject < 0 )
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
    SyncRootInfoByFileObject = HsmiCldLoadSyncRootInfoByFileObject(a1, (__int64)Object, (UCHAR **)&P);
    HsmDbgBreakOnStatus(SyncRootInfoByFileObject);
    if ( SyncRootInfoByFileObject < 0 )
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
0x140051810  mov     rax, rsp
0x140051813  mov     [rax+10h], rbx
0x140051817  push    rbp
0x140051818  push    rsi
0x140051819  push    rdi
0x14005181a  push    r12
0x14005181c  push    r14
0x14005181e  sub     rsp, 30h
0x140051822  xor     ebx, ebx
0x140051824  mov     rsi, rcx
0x140051827  mov     rcx, [rcx+10h]
0x14005182b  xor     edi, edi
0x14005182d  mov     [rax+20h], rbx
0x140051831  mov     r14, r8
0x140051834  mov     [rax+18h], rbx
0x140051838  mov     rbp, rdx
0x14005183b  mov     [rax+8], rdi
0x14005183f  mov     rax, cs:qword_1400296C0
0x140051846  call    _guard_dispatch_icall
0x14005184b  mov     rcx, [rsi+10h]
0x14005184f  mov     rdx, rbp
0x140051852  mov     [r14], eax
0x140051855  mov     rax, cs:qword_1400296A0
0x14005185c  call    _guard_dispatch_icall
0x140051861  test    rax, rax
0x140051864  jz      short loc_14005187A
0x140051866  mov     eax, ebx
0x140051868  mov     rbx, [rsp+58h+arg_8]
0x14005186d  add     rsp, 30h
0x140051871  pop     r14
0x140051873  pop     r12
0x140051875  pop     rdi
0x140051876  pop     rsi
0x140051877  pop     rbp
0x140051878  retn
0x14005187a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051881  lea     r12, WPP_GLOBAL_Control
0x140051888  cmp     rcx, r12
0x14005188b  jnz     loc_140051942
0x140051891  lea     r9, [rsp+58h+Object]
0x140051896  mov     rdx, rbp
0x140051899  lea     r8, [rsp+58h+FileHandle]
0x14005189e  mov     rcx, rsi
0x1400518a1  call    HsmiCldOpenSyncRoot
0x1400518a6  mov     ecx, eax
0x1400518a8  mov     ebx, eax
0x1400518aa  call    HsmDbgBreakOnStatus
0x1400518af  mov     rbp, [rsp+58h+Object]
0x1400518b4  test    ebx, ebx
0x1400518b6  js      loc_1400519AE
0x1400518bc  test    rbp, rbp
0x1400518bf  jz      loc_140051974
0x1400518c5  lea     r8, [rsp+58h+P]
0x1400518ca  mov     rdx, rbp
0x1400518cd  mov     rcx, rsi
0x1400518d0  call    HsmiCldLoadSyncRootInfoByFileObject
0x1400518d5  mov     ecx, eax
0x1400518d7  mov     ebx, eax
0x1400518d9  call    HsmDbgBreakOnStatus
0x1400518de  test    ebx, ebx
0x1400518e0  js      loc_1400519F5
0x1400518e6  mov     rdi, [rsp+58h+P]
0x1400518eb  mov     rcx, rdi
0x1400518ee  call    HsmiCldBuildSyncPolicy
0x1400518f3  mov     [r14], eax
0x1400518f6  test    rbp, rbp
0x1400518f9  jz      short loc_14005190A
0x1400518fb  mov     rcx, rbp; Object
0x1400518fe  call    cs:__imp_ObfDereferenceObject
0x140051905  nop     dword ptr [rax+rax+00h]
0x14005190a  mov     rcx, [rsp+58h+FileHandle]; FileHandle
0x14005190f  test    rcx, rcx
0x140051912  jz      short loc_140051920
0x140051914  call    cs:__imp_FltClose
0x14005191b  nop     dword ptr [rax+rax+00h]
0x140051920  test    rdi, rdi
0x140051923  jz      loc_140051866
0x140051929  mov     edx, 69537348h; Tag
0x14005192e  mov     rcx, rdi; P
0x140051931  call    cs:__imp_ExFreePoolWithTag
0x140051938  nop     dword ptr [rax+rax+00h]
0x14005193d  jmp     loc_140051866
0x140051942  mov     eax, [rcx+2Ch]
0x140051945  test    al, 1
0x140051947  jz      loc_140051891
0x14005194d  cmp     byte ptr [rcx+29h], 3
0x140051951  jb      loc_140051891
0x140051957  mov     rcx, [rcx+18h]
0x14005195b  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140051962  mov     edx, 27h ; '''
0x140051967  mov     r9, rsi
0x14005196a  call    WPP_SF_q
0x14005196f  jmp     loc_140051891
0x140051974  mov     rcx, cs:WPP_GLOBAL_Control
0x14005197b  cmp     rcx, r12
0x14005197e  jz      short loc_14005190A
0x140051980  mov     eax, [rcx+2Ch]
0x140051983  test    al, 1
0x140051985  jz      short loc_14005190A
0x140051987  cmp     byte ptr [rcx+29h], 3
0x14005198b  jb      loc_14005190A
0x140051991  mov     rcx, [rcx+18h]
0x140051995  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x14005199c  mov     edx, 29h ; ')'
0x1400519a1  mov     r9, rsi
0x1400519a4  call    WPP_SF_q
0x1400519a9  jmp     loc_14005190A
0x1400519ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519b5  cmp     rcx, r12
0x1400519b8  jz      loc_1400518F6
0x1400519be  mov     edx, [rcx+2Ch]
0x1400519c1  test    dl, 1
0x1400519c4  jz      loc_1400518F6
0x1400519ca  cmp     byte ptr [rcx+29h], 2
0x1400519ce  jb      loc_1400518F6
0x1400519d4  mov     rcx, [rcx+18h]
0x1400519d8  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x1400519df  mov     edx, 28h ; '('
0x1400519e4  mov     [rsp+58h+var_38], ebx
0x1400519e8  mov     r9, rsi
0x1400519eb  call    WPP_SF_qd
0x1400519f0  jmp     loc_1400518F6
0x1400519f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519fc  cmp     rcx, r12
0x1400519ff  jz      short loc_140051A2A
0x140051a01  mov     eax, [rcx+2Ch]
0x140051a04  test    al, 1
0x140051a06  jz      short loc_140051A2A
0x140051a08  cmp     byte ptr [rcx+29h], 2
0x140051a0c  jb      short loc_140051A2A
0x140051a0e  mov     rcx, [rcx+18h]
0x140051a12  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140051a19  mov     edx, 2Ah ; '*'
0x140051a1e  mov     [rsp+58h+var_38], ebx
0x140051a22  mov     r9, rsi
0x140051a25  call    WPP_SF_qd
0x140051a2a  mov     rdi, [rsp+58h+P]
0x140051a2f  jmp     loc_1400518F6
```
