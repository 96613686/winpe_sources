# TargetedIOCtrlGenerateECP

- ea: `0x18005d850`
- end: `0x18005dc01`
- name: `TargetedIOCtrlGenerateECP`
- size: `945`
- prototype: `__int64 __fastcall(PVOID *, char, int, __int64, PVOID FltObject, __int64, PVOID, PECP_LIST *EcpList, PVOID *)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18001bf00`
- `0x180052cb0`
- `0x180053000`
- `0x18005aa30`
- `0x18005b920`
- `0x18005c8e0`
- `0x18005d470`
- `0x18005e410`
- `0x180071ed0`

## callees

- `0x1800031e0`
- `0x180009f20`
- `0x18000ff70`
- `0x18001cb90`
- `0x18005d850`
- `0x18005dc10`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x18005d88e`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x18005d88e`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005d8eb`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterFromLookasideList` at `0x18005d8eb`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005da1c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005db81`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005dbb1`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005da1c`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005db81`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x18005dbb1`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005db66`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x18005db66`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005dbe9`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x18005dbe9`

## pseudocode

```c
__int64 __fastcall TargetedIOCtrlGenerateECP(
        PVOID *a1,
        char a2,
        int a3,
        __int64 a4,
        PVOID FltObject,
        __int64 a6,
        PVOID a7,
        PECP_LIST *EcpList,
        PVOID *a9)
{
  PECP_LIST *v9; // r14
  __int16 v14; // r13
  unsigned int ParameterList; // ebx
  _WORD *v16; // rdx
  __int16 v17; // ax
  unsigned __int8 v18; // si
  __int64 NextCallbackNodeForInstance; // rax
  __int64 CallbackNodeForInstance; // rax
  PVOID *v22; // rdi
  struct _ECP_LIST *v23; // rcx
  PVOID EcpContext; // [rsp+30h] [rbp-18h] BYREF
  PVOID v25; // [rsp+38h] [rbp-10h] BYREF

  v9 = EcpList;
  EcpContext = 0;
  v25 = 0;
  v14 = 0;
  if ( !*EcpList )
  {
    ParameterList = FsRtlAllocateExtraCreateParameterList(0, EcpList);
    if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 157, 0) < 0 )
      return ParameterList;
    v14 = 8;
  }
  ParameterList = FsRtlAllocateExtraCreateParameterFromLookasideList(
                    &FLTMGR_TIOCTRL_ECP_GUID,
                    0x60u,
                    2u,
                    0,
                    qword_18003EA40,
                    &EcpContext);
  if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 180, 0) >= 0 )
  {
    *(_WORD *)EcpContext = -3824;
    *((_WORD *)EcpContext + 1) = 96;
    *((_WORD *)EcpContext + 2) = a3;
    *((_WORD *)EcpContext + 3) = v14;
    *((_QWORD *)EcpContext + 1) = a4;
    *((_QWORD *)EcpContext + 2) = 0;
    v16 = EcpContext;
    v17 = *((_WORD *)EcpContext + 2);
    if ( v17 )
    {
      if ( v17 != 2 )
        goto LABEL_15;
      if ( a7 )
      {
        ParameterList = FltObjectReference(a7);
        if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 346, 3223060491LL) < 0 )
          goto LABEL_18;
        *((_QWORD *)EcpContext + 8) = a7;
        v16 = EcpContext;
      }
      if ( (a3 & 0x1000000) != 0 )
      {
        v16[3] |= 2u;
        v16 = EcpContext;
      }
      goto LABEL_15;
    }
    *((_QWORD *)EcpContext + 8) = -1;
    *((_QWORD *)EcpContext + 9) = 0;
    *((_QWORD *)EcpContext + 10) = 0;
    ParameterList = FltObjectReference(FltObject);
    if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 235, 3223060491LL) >= 0 )
    {
      *((_QWORD *)EcpContext + 8) = FltObject;
      *((_QWORD *)EcpContext + 9) = a6;
      if ( (a3 & 0x1000000) != 0 )
        *((_WORD *)EcpContext + 3) |= 2u;
      if ( (a3 & 0x2000000) != 0 )
        *((_WORD *)EcpContext + 3) |= 0x20u;
      if ( a6 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(a6 + 4));
        v18 = a2 + 22;
        if ( (*((_BYTE *)EcpContext + 6) & 0x20) != 0 )
        {
          CallbackNodeForInstance = FltpGetCallbackNodeForInstance(a6, v18);
          *((_QWORD *)EcpContext + 2) = CallbackNodeForInstance;
          v16 = EcpContext;
          if ( (*((_BYTE *)EcpContext + 6) & 0x20) != 0 )
          {
            if ( *((_QWORD *)EcpContext + 2) )
              goto LABEL_15;
          }
        }
        NextCallbackNodeForInstance = FltpGetNextCallbackNodeForInstance(a6, v18, 0);
        *((_QWORD *)EcpContext + 2) = NextCallbackNodeForInstance;
      }
      v16 = EcpContext;
LABEL_15:
      ParameterList = FsRtlInsertExtraCreateParameter(*v9, v16);
      if ( ParameterList == -1073741811 )
      {
        v22 = a9;
        if ( a9 )
        {
          v23 = *v9;
          LODWORD(EcpList) = 0;
          if ( !FsRtlRemoveExtraCreateParameter(v23, &FLTMGR_TIOCTRL_ECP_GUID, &v25, (ULONG *)&EcpList) )
          {
            ParameterList = FsRtlInsertExtraCreateParameter(*v9, EcpContext);
            if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 404, 0) >= 0 )
              *v22 = v25;
            else
              FsRtlInsertExtraCreateParameter(*v9, v25);
          }
        }
      }
      if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 426, 0) >= 0 )
        *((_WORD *)EcpContext + 3) |= 0x10u;
    }
  }
LABEL_18:
  if ( (int)FltpDbgStatus(ParameterList, "minkernel\\fs\\filtermgr\\filter\\targetediosup.c", 437, 0) < 0 )
  {
    if ( EcpContext )
      FreeTargetedIoCtrl(EcpContext);
    if ( v14 )
    {
      FsRtlFreeExtraCreateParameterList(*v9);
      *v9 = 0;
    }
  }
  else
  {
    *a1 = EcpContext;
  }
  return ParameterList;
}

```

## disassembly

```asm
0x18005d850  push    rbp
0x18005d852  push    rbx
0x18005d853  push    rsi
0x18005d854  push    rdi
0x18005d855  push    r12
0x18005d857  push    r13
0x18005d859  push    r14
0x18005d85b  push    r15
0x18005d85d  mov     rbp, rsp
0x18005d860  sub     rsp, 48h
0x18005d864  mov     r14, [rbp+EcpList]
0x18005d86b  xor     eax, eax
0x18005d86d  mov     r15, r9
0x18005d870  mov     [rbp+var_18], rax
0x18005d874  mov     edi, r8d
0x18005d877  mov     [rbp+var_10], rax
0x18005d87b  movzx   esi, dl
0x18005d87e  mov     r12, rcx
0x18005d881  mov     r13d, eax
0x18005d884  cmp     [r14], rax
0x18005d887  jnz     short loc_18005D8C1
0x18005d889  mov     rdx, r14; EcpList
0x18005d88c  xor     ecx, ecx; Flags
0x18005d88e  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x18005d895  nop     dword ptr [rax+rax+00h]
0x18005d89a  mov     r8d, 9Dh
0x18005d8a0  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005d8a7  mov     ecx, eax
0x18005d8a9  xor     r9d, r9d
0x18005d8ac  mov     ebx, eax
0x18005d8ae  call    FltpDbgStatus
0x18005d8b3  test    eax, eax
0x18005d8b5  js      loc_18005DA80
0x18005d8bb  mov     r13d, 8
0x18005d8c1  lea     rax, [rbp+var_18]
0x18005d8c5  xor     r9d, r9d; CleanupCallback
0x18005d8c8  mov     [rsp+48h+EcpContext], rax; EcpContext
0x18005d8cd  lea     rcx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18005d8d4  lea     rax, qword_18003EA40
0x18005d8db  mov     edx, 60h ; '`'; SizeOfContext
0x18005d8e0  mov     r8d, 2; Flags
0x18005d8e6  mov     [rsp+48h+LookasideList], rax; LookasideList
0x18005d8eb  call    cs:__imp_FsRtlAllocateExtraCreateParameterFromLookasideList
0x18005d8f2  nop     dword ptr [rax+rax+00h]
0x18005d8f7  mov     r8d, 0B4h
0x18005d8fd  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005d904  mov     ecx, eax
0x18005d906  xor     r9d, r9d
0x18005d909  mov     ebx, eax
0x18005d90b  call    FltpDbgStatus
0x18005d910  test    eax, eax
0x18005d912  js      loc_18005DA59
0x18005d918  mov     rax, [rbp+var_18]
0x18005d91c  mov     word ptr [rax], 0F110h
0x18005d921  mov     rax, [rbp+var_18]
0x18005d925  mov     word ptr [rax+2], 60h ; '`'
0x18005d92b  mov     rax, [rbp+var_18]
0x18005d92f  mov     [rax+4], di
0x18005d933  mov     rax, [rbp+var_18]
0x18005d937  mov     [rax+6], r13w
0x18005d93c  mov     rax, [rbp+var_18]
0x18005d940  mov     [rax+8], r15
0x18005d944  xor     r15d, r15d
0x18005d947  mov     rax, [rbp+var_18]
0x18005d94b  mov     [rax+10h], r15
0x18005d94f  mov     rdx, [rbp+var_18]
0x18005d953  movzx   eax, word ptr [rdx+4]
0x18005d957  test    ax, ax
0x18005d95a  jnz     loc_18005DAD2
0x18005d960  mov     qword ptr [rdx+40h], 0FFFFFFFFFFFFFFFFh
0x18005d968  mov     rax, [rbp+var_18]
0x18005d96c  mov     [rax+48h], r15
0x18005d970  mov     rax, [rbp+var_18]
0x18005d974  mov     [rax+50h], r15
0x18005d978  mov     r15, [rbp+FltObject]
0x18005d97c  mov     rcx, r15; FltObject
0x18005d97f  call    FltObjectReference
0x18005d984  mov     r8d, 0EBh
0x18005d98a  mov     [rsp+48h+LookasideList], 0
0x18005d993  mov     r9d, 0C01C000Bh
0x18005d999  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005d9a0  mov     ecx, eax
0x18005d9a2  mov     ebx, eax
0x18005d9a4  call    FltpDbgStatus
0x18005d9a9  test    eax, eax
0x18005d9ab  js      loc_18005DA59
0x18005d9b1  mov     rax, [rbp+var_18]
0x18005d9b5  mov     rbx, [rbp+arg_28]
0x18005d9b9  mov     [rax+40h], r15
0x18005d9bd  mov     rax, [rbp+var_18]
0x18005d9c1  mov     [rax+48h], rbx
0x18005d9c5  bt      edi, 18h
0x18005d9c9  jnb     short loc_18005D9D4
0x18005d9cb  mov     rax, [rbp+var_18]
0x18005d9cf  or      word ptr [rax+6], 2
0x18005d9d4  bt      edi, 19h
0x18005d9d8  jb      loc_18005DA94
0x18005d9de  test    rbx, rbx
0x18005d9e1  jz      short loc_18005DA12
0x18005d9e3  lock inc dword ptr [rbx+4]
0x18005d9e7  mov     rdx, [rbp+var_18]
0x18005d9eb  add     sil, 16h
0x18005d9ef  movzx   edi, sil
0x18005d9f3  test    byte ptr [rdx+6], 20h
0x18005d9f7  jnz     loc_18005DAA2
0x18005d9fd  xor     r8d, r8d
0x18005da00  mov     edx, edi
0x18005da02  mov     rcx, rbx
0x18005da05  call    FltpGetNextCallbackNodeForInstance
0x18005da0a  mov     rcx, [rbp+var_18]
0x18005da0e  mov     [rcx+10h], rax
0x18005da12  mov     rdx, [rbp+var_18]; EcpContext
0x18005da16  xor     r15d, r15d
0x18005da19  mov     rcx, [r14]; EcpList
0x18005da1c  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005da23  nop     dword ptr [rax+rax+00h]
0x18005da28  mov     ebx, eax
0x18005da2a  cmp     eax, 0C000000Dh
0x18005da2f  jz      loc_18005DB3A
0x18005da35  mov     r8d, 1AAh
0x18005da3b  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005da42  xor     r9d, r9d
0x18005da45  mov     ecx, ebx
0x18005da47  call    FltpDbgStatus
0x18005da4c  test    eax, eax
0x18005da4e  js      short loc_18005DA59
0x18005da50  mov     rax, [rbp+var_18]
0x18005da54  or      word ptr [rax+6], 10h
0x18005da59  mov     r8d, 1B5h
0x18005da5f  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005da66  xor     r9d, r9d
0x18005da69  mov     ecx, ebx
0x18005da6b  call    FltpDbgStatus
0x18005da70  test    eax, eax
0x18005da72  js      loc_18005DBCE
0x18005da78  mov     rax, [rbp+var_18]
0x18005da7c  mov     [r12], rax
0x18005da80  mov     eax, ebx
0x18005da82  add     rsp, 48h
0x18005da86  pop     r15
0x18005da88  pop     r14
0x18005da8a  pop     r13
0x18005da8c  pop     r12
0x18005da8e  pop     rdi
0x18005da8f  pop     rsi
0x18005da90  pop     rbx
0x18005da91  pop     rbp
0x18005da92  retn
0x18005da94  mov     rax, [rbp+var_18]
0x18005da98  or      word ptr [rax+6], 20h
0x18005da9d  jmp     loc_18005D9DE
0x18005daa2  mov     edx, edi
0x18005daa4  mov     rcx, rbx
0x18005daa7  call    FltpGetCallbackNodeForInstance
0x18005daac  mov     rcx, [rbp+var_18]
0x18005dab0  mov     [rcx+10h], rax
0x18005dab4  mov     rdx, [rbp+var_18]
0x18005dab8  test    byte ptr [rdx+6], 20h
0x18005dabc  jz      loc_18005D9FD
0x18005dac2  cmp     qword ptr [rdx+10h], 0
0x18005dac7  jnz     loc_18005DA16
0x18005dacd  jmp     loc_18005D9FD
0x18005dad2  cmp     ax, 2
0x18005dad6  jnz     loc_18005DA19
0x18005dadc  mov     rsi, [rbp+arg_30]
0x18005dae0  test    rsi, rsi
0x18005dae3  jz      short loc_18005DB22
0x18005dae5  mov     rcx, rsi; FltObject
0x18005dae8  call    FltObjectReference
0x18005daed  mov     r8d, 15Ah
0x18005daf3  mov     [rsp+48h+LookasideList], r15
0x18005daf8  mov     r9d, 0C01C000Bh
0x18005dafe  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005db05  mov     ecx, eax
0x18005db07  mov     ebx, eax
0x18005db09  call    FltpDbgStatus
0x18005db0e  test    eax, eax
0x18005db10  js      loc_18005DA59
0x18005db16  mov     rax, [rbp+var_18]
0x18005db1a  mov     [rax+40h], rsi
0x18005db1e  mov     rdx, [rbp+var_18]
0x18005db22  bt      edi, 18h
0x18005db26  jnb     loc_18005DA19
0x18005db2c  or      word ptr [rdx+6], 2
0x18005db31  mov     rdx, [rbp+var_18]
0x18005db35  jmp     loc_18005DA19
0x18005db3a  mov     rdi, [rbp+arg_40]
0x18005db41  test    rdi, rdi
0x18005db44  jz      loc_18005DA35
0x18005db4a  mov     rcx, [r14]; EcpList
0x18005db4d  lea     r9, [rbp+EcpList]; EcpContextSize
0x18005db54  lea     r8, [rbp+var_10]; EcpContext
0x18005db58  mov     dword ptr [rbp+EcpList], r15d
0x18005db5f  lea     rdx, FLTMGR_TIOCTRL_ECP_GUID; EcpType
0x18005db66  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x18005db6d  nop     dword ptr [rax+rax+00h]
0x18005db72  test    eax, eax
0x18005db74  jnz     loc_18005DA35
0x18005db7a  mov     rdx, [rbp+var_18]; EcpContext
0x18005db7e  mov     rcx, [r14]; EcpList
0x18005db81  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005db88  nop     dword ptr [rax+rax+00h]
0x18005db8d  mov     r8d, 194h
0x18005db93  lea     rdx, aMinkernelFsFil_7; "minkernel\\fs\\filtermgr\\filter\\targe"...
0x18005db9a  mov     ecx, eax
0x18005db9c  xor     r9d, r9d
0x18005db9f  mov     ebx, eax
0x18005dba1  call    FltpDbgStatus
0x18005dba6  test    eax, eax
0x18005dba8  jns     short loc_18005DBC2
0x18005dbaa  mov     rdx, [rbp+var_10]; EcpContext
0x18005dbae  mov     rcx, [r14]; EcpList
0x18005dbb1  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x18005dbb8  nop     dword ptr [rax+rax+00h]
0x18005dbbd  jmp     loc_18005DA35
0x18005dbc2  mov     rax, [rbp+var_10]
0x18005dbc6  mov     [rdi], rax
0x18005dbc9  jmp     loc_18005DA35
0x18005dbce  mov     rcx, [rbp+var_18]; EcpContext
0x18005dbd2  test    rcx, rcx
0x18005dbd5  jz      short loc_18005DBDC
0x18005dbd7  call    FreeTargetedIoCtrl
0x18005dbdc  test    r13w, r13w
0x18005dbe0  jz      loc_18005DA80
0x18005dbe6  mov     rcx, [r14]; EcpList
0x18005dbe9  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x18005dbf0  nop     dword ptr [rax+rax+00h]
0x18005dbf5  mov     qword ptr [r14], 0
0x18005dbfc  jmp     loc_18005DA80
```
