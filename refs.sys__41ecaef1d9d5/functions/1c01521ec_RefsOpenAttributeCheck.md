# RefsOpenAttributeCheck

- ea: `0x1c01521ec`
- end: `0x1c015280d`
- name: `RefsOpenAttributeCheck`
- size: `1569`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, PIRP Irp@<rdx>, char, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1c01540e0`
- `0x1c0194f50`

## callees

- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c00689d4`
- `0x1c01521ec`

## import_xrefs

- `ntoskrnl!FsRtlCheckOplock` at `0x1c01524d8`
- `ntoskrnl!FsRtlCheckOplock` at `0x1c01524d8`
- `ntoskrnl!MmFlushImageSection` at `0x1c0152640`
- `ntoskrnl!MmFlushImageSection` at `0x1c0152640`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152245`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152245`
- `ntoskrnl!IoCheckShareAccess` at `0x1c0152300`
- `ntoskrnl!IoCheckShareAccess` at `0x1c0152300`

## string_xrefs

- `0x1c01522a2`: `Create.c`
- `0x1c0152360`: `Create.c`
- `0x1c015253c`: `Create.c`
- `0x1c01525d6`: `Create.c`
- `0x1c01526a4`: `Create.c`
- `0x1c015270c`: `Create.c`
- `0x1c0152782`: `Create.c`
- `0x1c01527ee`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenAttributeCheck(PVOID Context, PIRP Irp, __int64 a3, __int64 *a4, char a5, int *a6)
{
  unsigned int v10; // edi
  int IsEnabledDeviceUsage; // eax
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // eax
  int v16; // ecx
  char v17; // si
  __int64 v18; // rcx
  unsigned int Status; // [rsp+70h] [rbp+18h]

  v10 = 0;
  Status = 0;
  if ( (*(_BYTE *)(a3 + 26) & 2) == 0
    && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 0x10027) != 0
    && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(*a4 + 240) + 8LL)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225539LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741757);
    return 3221225539LL;
  }
  if ( *(_DWORD *)(*a4 + 144) )
  {
    v10 = IoCheckShareAccess(
            *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL),
            *(unsigned __int16 *)(a3 + 26),
            *(PFILE_OBJECT *)(a3 + 48),
            (PSHARE_ACCESS)(*a4 + 172),
            0);
    Status = v10;
    if ( (v10 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, v10);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(v10);
      return v10;
    }
    IsEnabledDeviceUsage = Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage();
    v13 = *a4;
    v14 = *(_DWORD *)(*a4 + 200);
    if ( IsEnabledDeviceUsage )
    {
      if ( (v14 != 128 && v14 != 176 || *(_WORD *)v13 != 2053 || *(_QWORD *)(*(_QWORD *)(v13 + 128) + 72LL) == v13)
        && (v14 != 160
         || *(_WORD *)(v13 + 208) != 8
         || **(_QWORD **)(v13 + 216) != 0x30003300490024LL
         || (unsigned __int16)(*(_WORD *)v13 - 2051) > 1u) )
      {
        v15 = 0;
LABEL_40:
        if ( v15 )
        {
          if ( (*(_DWORD *)(a3 + 16) & 0x100000) != 0 )
          {
            if ( *(_WORD *)v13 != 2053 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  153,
                  WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                  3221225485LL);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741811);
              RefsRaiseStatusInternal(Context, 3221225485LL);
              __debugbreak();
            }
            if ( *(_DWORD *)(v13 + 144) > 1u )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  154,
                  WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                  3221225698LL);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741598);
              RefsRaiseStatusInternal(Context, 3221225698LL);
              JUMPOUT(0x1C015280DLL);
            }
          }
          v10 = FsRtlCheckOplock((POPLOCK)(v13 + 88), Irp, Context, RefsOplockComplete, RefsOplockPrePostIrp);
          Status = v10;
          if ( v10 == 259 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 155, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 871);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(871);
            return 871;
          }
        }
        goto LABEL_37;
      }
    }
    else if ( (v14 != 128 && v14 != 176 || *(_WORD *)v13 != 2053)
           && (v14 != 160
            || *(_WORD *)(v13 + 208) != 8
            || **(_QWORD **)(v13 + 216) != 0x30003300490024LL
            || (unsigned __int16)(*(_WORD *)v13 - 2051) > 1u) )
    {
LABEL_37:
      v16 = 1;
      goto LABEL_53;
    }
    v15 = 1;
    goto LABEL_40;
  }
  v16 = 2;
LABEL_53:
  *a6 = v16;
  if ( (*(_DWORD *)(a3 + 16) & 0x1000) != 0 )
  {
    v17 = 1;
    if ( (*(_DWORD *)(*(_QWORD *)(*a4 + 128) + 4LL) & 0x2000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225761LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741535);
      return 3221225761LL;
    }
  }
  else
  {
    v17 = 0;
  }
  if ( !a5 && ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 2) != 0 || v17) )
  {
    _InterlockedAdd((volatile signed __int32 *)(*a4 + 148), 1u);
    v18 = *(_QWORD *)(*a4 + 240);
    if ( *(_QWORD *)(v18 + 24) && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v18 + 8), MmFlushForWrite) )
    {
      if ( v17 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            157,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225761LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741535);
        Status = -1073741535;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            158,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225539LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741757);
        Status = -1073741757;
      }
    }
    _InterlockedDecrement((volatile signed __int32 *)(*a4 + 148));
    return Status;
  }
  return v10;
}

```

## disassembly

```asm
0x1c01521ec  mov     [rsp+arg_0], rbx
0x1c01521f1  mov     [rsp+arg_18], r9
0x1c01521f6  push    rsi
0x1c01521f7  push    rdi
0x1c01521f8  push    r12
0x1c01521fa  push    r14
0x1c01521fc  push    r15
0x1c01521fe  sub     rsp, 30h
0x1c0152202  mov     r14, r9
0x1c0152205  mov     r15, r8
0x1c0152208  mov     r12, rdx
0x1c015220b  mov     rsi, rcx
0x1c015220e  xor     edi, edi
0x1c0152210  mov     [rsp+58h+Status], edi
0x1c0152214  test    byte ptr [r8+1Ah], 2
0x1c0152219  jnz     loc_1C01522CB
0x1c015221f  mov     rax, [r8+8]
0x1c0152223  mov     r9, [rax+8]
0x1c0152227  test    dword ptr [r9+14h], 10027h
0x1c015222f  jz      loc_1C01522CB
0x1c0152235  mov     rax, [r14]
0x1c0152238  mov     rcx, [rax+0F0h]
0x1c015223f  lea     ebx, [rdi+8]
0x1c0152242  add     rcx, rbx; SectionPointer
0x1c0152245  call    cs:__imp_MmDoesFileHaveUserWritableReferences
0x1c015224c  nop     dword ptr [rax+rax+00h]
0x1c0152251  test    eax, eax
0x1c0152253  jz      short loc_1C01522D0
0x1c0152255  lea     rax, WPP_GLOBAL_Control
0x1c015225c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152263  cmp     rcx, rax
0x1c0152266  jz      short loc_1C0152292
0x1c0152268  test    dword ptr [rcx+2Ch], 100h
0x1c015226f  jz      short loc_1C0152292
0x1c0152271  cmp     byte ptr [rcx+29h], 4
0x1c0152275  jb      short loc_1C0152292
0x1c0152277  mov     edx, 97h
0x1c015227c  mov     r9d, 0C0000043h
0x1c0152282  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152289  mov     rcx, [rcx+18h]
0x1c015228d  call    WPP_SF_D
0x1c0152292  mov     cl, cs:RefsStatusDebugEnabled
0x1c0152298  test    cl, cl
0x1c015229a  jz      short loc_1C01522B3
0x1c015229c  mov     r8d, 3437h
0x1c01522a2  lea     rdx, aCreateC; "Create.c"
0x1c01522a9  mov     ecx, 0C0000043h; Status
0x1c01522ae  call    RefsStatusDebug
0x1c01522b3  mov     eax, 0C0000043h
0x1c01522b8  mov     rbx, [rsp+58h+arg_0]
0x1c01522bd  add     rsp, 30h
0x1c01522c1  pop     r15
0x1c01522c3  pop     r14
0x1c01522c5  pop     r12
0x1c01522c7  pop     rdi
0x1c01522c8  pop     rsi
0x1c01522c9  retn
0x1c01522cb  mov     ebx, 8
0x1c01522d0  mov     r9, [r14]
0x1c01522d3  cmp     [r9+90h], edi
0x1c01522da  jz      loc_1C0152557
0x1c01522e0  add     r9, 0ACh; ShareAccess
0x1c01522e7  movzx   edx, word ptr [r15+1Ah]; DesiredShareAccess
0x1c01522ec  mov     rax, [r15+8]
0x1c01522f0  mov     rcx, [rax+8]
0x1c01522f4  mov     [rsp+58h+Update], dil; Update
0x1c01522f9  mov     r8, [r15+30h]; FileObject
0x1c01522fd  mov     ecx, [rcx+14h]; DesiredAccess
0x1c0152300  call    cs:__imp_IoCheckShareAccess
0x1c0152307  nop     dword ptr [rax+rax+00h]
0x1c015230c  mov     edi, eax
0x1c015230e  mov     [rsp+58h+Status], eax
0x1c0152312  test    eax, eax
0x1c0152314  jns     short loc_1C0152379
0x1c0152316  lea     rax, WPP_GLOBAL_Control
0x1c015231d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152324  cmp     rcx, rax
0x1c0152327  jz      short loc_1C0152350
0x1c0152329  test    dword ptr [rcx+2Ch], 100h
0x1c0152330  jz      short loc_1C0152350
0x1c0152332  cmp     byte ptr [rcx+29h], 4
0x1c0152336  jb      short loc_1C0152350
0x1c0152338  mov     edx, 98h
0x1c015233d  mov     r9d, edi
0x1c0152340  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152347  mov     rcx, [rcx+18h]
0x1c015234b  call    WPP_SF_D
0x1c0152350  mov     al, cs:RefsStatusDebugEnabled
0x1c0152356  test    al, al
0x1c0152358  jz      short loc_1C0152370
0x1c015235a  mov     r8d, 344Fh
0x1c0152360  lea     rdx, aCreateC; "Create.c"
0x1c0152367  mov     ecx, [rsp+58h+Status]; Status
0x1c015236b  call    RefsStatusDebug
0x1c0152370  mov     eax, [rsp+58h+Status]
0x1c0152374  jmp     loc_1C01522B8
0x1c0152379  call    Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage
0x1c015237e  xor     ecx, ecx
0x1c0152380  test    eax, eax
0x1c0152382  setnz   cl
0x1c0152385  mov     rdx, [r14]
0x1c0152388  mov     r8d, [rdx+0C8h]
0x1c015238f  test    ecx, ecx
0x1c0152391  jz      loc_1C015241C
0x1c0152397  cmp     r8d, 80h
0x1c015239e  jz      short loc_1C01523B1
0x1c01523a0  cmp     r8d, 0B0h
0x1c01523a7  jz      short loc_1C01523B1
0x1c01523a9  mov     r9d, 805h
0x1c01523af  jmp     short loc_1C01523CE
0x1c01523b1  mov     r9d, 805h
0x1c01523b7  cmp     [rdx], r9w
0x1c01523bb  jnz     short loc_1C01523CE
0x1c01523bd  mov     rax, [rdx+80h]
0x1c01523c4  cmp     [rax+48h], rdx
0x1c01523c8  jnz     loc_1C0152490
0x1c01523ce  cmp     r8d, 0A0h
0x1c01523d5  jnz     short loc_1C0152413
0x1c01523d7  cmp     [rdx+0D0h], bx
0x1c01523de  jnz     short loc_1C0152413
0x1c01523e0  mov     rax, [rdx+0D8h]
0x1c01523e7  mov     rcx, [rax]
0x1c01523ea  mov     rax, 30003300490024h
0x1c01523f4  cmp     rcx, rax
0x1c01523f7  jnz     short loc_1C0152413
0x1c01523f9  mov     ecx, 803h
0x1c01523fe  movzx   eax, word ptr [rdx]
0x1c0152401  sub     ax, cx
0x1c0152404  mov     ebx, 1
0x1c0152409  cmp     ax, bx
0x1c015240c  ja      short loc_1C0152418
0x1c015240e  jmp     loc_1C0152495
0x1c0152413  mov     ebx, 1
0x1c0152418  xor     eax, eax
0x1c015241a  jmp     short loc_1C0152497
0x1c015241c  cmp     r8d, 80h
0x1c0152423  jz      short loc_1C0152436
0x1c0152425  cmp     r8d, 0B0h
0x1c015242c  jz      short loc_1C0152436
0x1c015242e  mov     r9d, 805h
0x1c0152434  jmp     short loc_1C0152442
0x1c0152436  mov     r9d, 805h
0x1c015243c  cmp     [rdx], r9w
0x1c0152440  jz      short loc_1C0152490
0x1c0152442  cmp     r8d, 0A0h
0x1c0152449  jnz     short loc_1C0152489
0x1c015244b  cmp     [rdx+0D0h], bx
0x1c0152452  jnz     short loc_1C0152489
0x1c0152454  mov     rax, [rdx+0D8h]
0x1c015245b  mov     rcx, [rax]
0x1c015245e  mov     rax, 30003300490024h
0x1c0152468  cmp     rcx, rax
0x1c015246b  jnz     short loc_1C0152489
0x1c015246d  mov     ecx, 803h
0x1c0152472  movzx   eax, word ptr [rdx]
0x1c0152475  sub     ax, cx
0x1c0152478  mov     ebx, 1
0x1c015247d  cmp     ax, bx
0x1c0152480  jbe     short loc_1C0152495
0x1c0152482  mov     ecx, ebx
0x1c0152484  jmp     loc_1C015255F
0x1c0152489  mov     ebx, 1
0x1c015248e  jmp     short loc_1C0152482
0x1c0152490  mov     ebx, 1
0x1c0152495  mov     eax, ebx
0x1c0152497  test    eax, eax
0x1c0152499  jz      short loc_1C0152482
0x1c015249b  test    dword ptr [r15+10h], 100000h
0x1c01524a3  jz      short loc_1C01524BB
0x1c01524a5  cmp     [rdx], r9w
0x1c01524a9  jnz     loc_1C0152735
0x1c01524af  cmp     [rdx+90h], ebx
0x1c01524b5  ja      loc_1C01527A1
0x1c01524bb  lea     rcx, [rdx+58h]; Oplock
0x1c01524bf  lea     rax, RefsOplockPrePostIrp
0x1c01524c6  mov     qword ptr [rsp+58h+Update], rax; PostIrpRoutine
0x1c01524cb  lea     r9, RefsOplockComplete; CompletionRoutine
0x1c01524d2  mov     r8, rsi; Context
0x1c01524d5  mov     rdx, r12; Irp
0x1c01524d8  call    cs:__imp_FsRtlCheckOplock
0x1c01524df  nop     dword ptr [rax+rax+00h]
0x1c01524e4  mov     edi, eax
0x1c01524e6  mov     [rsp+58h+Status], eax
0x1c01524ea  cmp     eax, 103h
0x1c01524ef  jnz     short loc_1C0152482
0x1c01524f1  lea     rax, WPP_GLOBAL_Control
0x1c01524f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01524ff  cmp     rcx, rax
0x1c0152502  jz      short loc_1C015252C
0x1c0152504  test    dword ptr [rcx+2Ch], 100h
0x1c015250b  jz      short loc_1C015252C
0x1c015250d  cmp     byte ptr [rcx+29h], 5
0x1c0152511  jb      short loc_1C015252C
0x1c0152513  lea     edx, [rdi-68h]
0x1c0152516  mov     r9d, 367h
0x1c015251c  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152523  mov     rcx, [rcx+18h]
0x1c0152527  call    WPP_SF_D
0x1c015252c  mov     cl, cs:RefsStatusDebugEnabled
0x1c0152532  test    cl, cl
0x1c0152534  jz      short loc_1C015254D
0x1c0152536  mov     r8d, 3474h
0x1c015253c  lea     rdx, aCreateC; "Create.c"
0x1c0152543  mov     ecx, 367h; Status
0x1c0152548  call    RefsStatusDebug
0x1c015254d  mov     eax, 367h
0x1c0152552  jmp     loc_1C01522B8
0x1c0152557  mov     ecx, 2
0x1c015255c  lea     ebx, [rcx-1]
0x1c015255f  mov     rax, [rsp+58h+arg_28]
0x1c0152567  mov     [rax], ecx
0x1c0152569  test    dword ptr [r15+10h], 1000h
0x1c0152571  jz      short loc_1C01525F1
0x1c0152573  mov     sil, bl
0x1c0152576  mov     rax, [r14]
0x1c0152579  mov     rcx, [rax+80h]
0x1c0152580  test    dword ptr [rcx+4], 2000000h
0x1c0152587  jz      short loc_1C01525F4
0x1c0152589  lea     rax, WPP_GLOBAL_Control
0x1c0152590  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152597  cmp     rcx, rax
0x1c015259a  jz      short loc_1C01525C6
0x1c015259c  test    dword ptr [rcx+2Ch], 100h
0x1c01525a3  jz      short loc_1C01525C6
0x1c01525a5  cmp     byte ptr [rcx+29h], 4
0x1c01525a9  jb      short loc_1C01525C6
0x1c01525ab  mov     edx, 9Ch
0x1c01525b0  mov     r9d, 0C0000121h
0x1c01525b6  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01525bd  mov     rcx, [rcx+18h]
0x1c01525c1  call    WPP_SF_D
0x1c01525c6  mov     cl, cs:RefsStatusDebugEnabled
0x1c01525cc  test    cl, cl
0x1c01525ce  jz      short loc_1C01525E7
0x1c01525d0  mov     r8d, 348Bh
0x1c01525d6  lea     rdx, aCreateC; "Create.c"
0x1c01525dd  mov     ecx, 0C0000121h; Status
0x1c01525e2  call    RefsStatusDebug
0x1c01525e7  mov     eax, 0C0000121h
0x1c01525ec  jmp     loc_1C01522B8
0x1c01525f1  xor     sil, sil
0x1c01525f4  cmp     [rsp+58h+arg_20], 0
0x1c01525fc  jz      short loc_1C0152605
0x1c01525fe  mov     eax, edi
0x1c0152600  jmp     loc_1C01522B8
0x1c0152605  mov     rax, [r15+8]
0x1c0152609  mov     rcx, [rax+8]
0x1c015260d  mov     eax, [rcx+14h]
0x1c0152610  test    al, 2
0x1c0152612  jnz     short loc_1C0152619
0x1c0152614  test    sil, sil
0x1c0152617  jz      short loc_1C01525FE
0x1c0152619  mov     rax, [r14]
0x1c015261c  mov     edi, 94h
0x1c0152621  lock add [rax+rdi], ebx
0x1c0152625  mov     rax, [r14]
0x1c0152628  mov     rcx, [rax+0F0h]
0x1c015262f  cmp     qword ptr [rcx+18h], 0
0x1c0152634  jz      loc_1C0152725
0x1c015263a  add     rcx, 8; SectionObjectPointer
0x1c015263e  mov     edx, ebx; FlushType
0x1c0152640  call    cs:__imp_MmFlushImageSection
0x1c0152647  nop     dword ptr [rax+rax+00h]
0x1c015264c  test    al, al
0x1c015264e  jnz     loc_1C0152725
0x1c0152654  test    sil, sil
0x1c0152657  jz      short loc_1C01526BF
0x1c0152659  lea     rax, WPP_GLOBAL_Control
0x1c0152660  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152667  cmp     rcx, rax
0x1c015266a  jz      short loc_1C0152694
0x1c015266c  test    dword ptr [rcx+2Ch], 100h
0x1c0152673  jz      short loc_1C0152694
0x1c0152675  cmp     byte ptr [rcx+29h], 4
0x1c0152679  jb      short loc_1C0152694
0x1c015267b  lea     edx, [rdi+9]
0x1c015267e  mov     r9d, 0C0000121h
0x1c0152684  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c015268b  mov     rcx, [rcx+18h]
0x1c015268f  call    WPP_SF_D
0x1c0152694  mov     al, cs:RefsStatusDebugEnabled
0x1c015269a  test    al, al
0x1c015269c  jz      short loc_1C01526B5
0x1c015269e  mov     r8d, 34B3h
0x1c01526a4  lea     rdx, aCreateC; "Create.c"
0x1c01526ab  mov     ecx, 0C0000121h; Status
0x1c01526b0  call    RefsStatusDebug
0x1c01526b5  mov     [rsp+58h+Status], 0C0000121h
0x1c01526bd  jmp     short loc_1C0152725
0x1c01526bf  lea     rax, WPP_GLOBAL_Control
0x1c01526c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01526cd  cmp     rcx, rax
0x1c01526d0  jz      short loc_1C01526FC
0x1c01526d2  test    dword ptr [rcx+2Ch], 100h
0x1c01526d9  jz      short loc_1C01526FC
0x1c01526db  cmp     byte ptr [rcx+29h], 4
0x1c01526df  jb      short loc_1C01526FC
0x1c01526e1  mov     edx, 9Eh
0x1c01526e6  mov     r9d, 0C0000043h
0x1c01526ec  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
  ... truncated ...
```
