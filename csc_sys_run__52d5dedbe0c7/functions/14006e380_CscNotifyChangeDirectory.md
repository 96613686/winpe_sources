# CscNotifyChangeDirectory

- ea: `0x14006e380`
- end: `0x14006e87b`
- name: `CscNotifyChangeDirectory`
- size: `1275`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003a00`
- `0x14000e100`
- `0x140019204`
- `0x14001b5bc`
- `0x14001fab8`
- `0x14001fe28`
- `0x14002f010`
- `0x14002f0f0`
- `0x1400490f8`
- `0x140051d70`
- `0x14006e380`
- `0x14006e884`
- `0x14006e954`
- `0x14006e9e4`
- `0x14006f058`
- `0x14007172c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14006e58d`
- `ntoskrnl!KeInitializeEvent` at `0x14006e5a2`
- `ntoskrnl!KeInitializeEvent` at `0x14006e58d`
- `ntoskrnl!KeInitializeEvent` at `0x14006e5a2`
- `ntoskrnl!IoCancelIrp` at `0x14006e7e9`
- `ntoskrnl!IoCancelIrp` at `0x14006e7e9`
- `rdbss!RxCompleteRequestEx` at `0x14006e832`
- `rdbss!RxCompleteRequestEx` at `0x14006e832`
- `rdbss!RxWaitSync` at `0x14006e6d2`
- `rdbss!RxWaitSync` at `0x14006e846`
- `rdbss!RxWaitSync` at `0x14006e6d2`
- `rdbss!RxWaitSync` at `0x14006e846`

## pseudocode

```c
__int64 __fastcall CscNotifyChangeDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _WORD *v4; // rdi
  __int64 v6; // r14
  bool v7; // si
  __int64 v8; // rbp
  int v9; // r9d
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // cl
  int v14; // ebp
  int v15; // esi
  unsigned int v16; // edi
  __int64 v18; // rax
  char *v19; // rsi
  int v20; // r15d
  __int64 v21; // [rsp+20h] [rbp-98h]
  __int128 v22; // [rsp+50h] [rbp-68h] BYREF
  __int128 v23; // [rsp+60h] [rbp-58h]
  __int64 v24; // [rsp+70h] [rbp-48h]
  __int128 v25; // [rsp+78h] [rbp-40h] BYREF

  v4 = *(_WORD **)(a1 + 56);
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_QWORD *)(a1 + 80) != (_QWORD)CscDeviceObject;
  v8 = *(_QWORD *)(a1 + 72);
  v24 = 0;
  v22 = 0;
  v23 = 0;
  v25 = 0;
  CscGetContexts(a1, &v22, a3, a4);
  LOBYTE(v9) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)v4, v8, v10, v9, (__int64)&v25, 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    HIDWORD(v21) = HIDWORD(a1);
    WPP_SF_cqqqDc(WPP_GLOBAL_Control->AttachedDevice);
  }
  if ( (_QWORD)v23 && (*(_DWORD *)(v23 + 24) & 9) != 0 )
  {
    v14 = 5258;
    v16 = -1073741811;
  }
  else
  {
    if ( (BYTE1(v25) & 0x40) != 0 )
    {
      v16 = CscDetermineAbortStatus(&v25);
      v14 = 5266;
      goto LABEL_17;
    }
    if ( *v4 != 0xEC21 )
    {
      v14 = 5272;
      v16 = -1073741811;
      goto LABEL_17;
    }
    v13 = v25;
    if ( (v25 & 0x20) != 0 )
    {
      if ( (*(_DWORD *)(*((_QWORD *)&v22 + 1) + 4LL) & 0x60) != 0 )
        return 3221225485LL;
      CscDirCtrlBackpatchIfPossible(a1, (_DWORD)v4, v8, (unsigned int)&v22, (__int64)&v25);
      v13 = v25;
    }
    v14 = 0;
    if ( !v7 || (v13 & 0x30) != 0x20 )
    {
      if ( (v13 & 0x20) != 0 )
      {
        v16 = CscNotifyFullChangeDirectory(a1, *(unsigned __int8 *)(a1 + 536), *(unsigned int *)(a1 + 540), 0);
        if ( v16 == 259 )
          RxCompleteRequestEx(a1, 0, 0);
      }
      else
      {
        v11 = *(unsigned __int16 *)(a1 + 520);
        if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 8 * v11 + 304) )
        {
          if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
          {
            v16 = -1073741536;
          }
          else
          {
            v15 = *(_DWORD *)(a1 + 120);
            *(_OWORD *)(a1 + 208) = 0;
            *(_OWORD *)(a1 + 224) = 0;
            *(_QWORD *)(a1 + 240) = 0;
            v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL)
                                                     + 8LL * *(unsigned __int16 *)(a1 + 520)
                                                     + 304))(a1);
            if ( v16 == 259 && (v15 & 0x1000) == 0 )
            {
              RxWaitSync(a1);
              v16 = *(_DWORD *)(a1 + 176);
            }
          }
        }
        else
        {
          v16 = -1073741822;
        }
      }
      goto LABEL_17;
    }
    v18 = CscNotifyAllocateAndReferenceContext(a1);
    v19 = (char *)v18;
    if ( v18 )
    {
      *(_QWORD *)(v18 + 8) = a1;
      *(_QWORD *)(v18 + 16) = *(_QWORD *)(a1 + 528);
      *(_QWORD *)(a1 + 528) = CscNotifyChangeDirectoryCompletionEntry;
      *(_QWORD *)(v18 + 104) = KeGetCurrentThread();
      KeInitializeEvent((PRKEVENT)(v18 + 40), NotificationEvent, 0);
      KeInitializeEvent((PRKEVENT)(v19 + 64), NotificationEvent, 0);
      *(_DWORD *)v19 = 7400101;
      *(_QWORD *)(a1 + 264) = v19;
      _InterlockedOr((volatile signed __int32 *)v19 + 22, 1u);
      CscNotifyReferenceContext_Real(v19);
      if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL) + 8LL * *(unsigned __int16 *)(a1 + 520) + 304) )
      {
        if ( (*(_DWORD *)(a1 + 128) & 2) != 0 )
        {
          v16 = -1073741536;
        }
        else
        {
          v20 = *(_DWORD *)(a1 + 120);
          *(_OWORD *)(a1 + 208) = 0;
          *(_OWORD *)(a1 + 224) = 0;
          *(_QWORD *)(a1 + 240) = 0;
          v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 80) + 352LL)
                                                   + 8LL * *(unsigned __int16 *)(a1 + 520)
                                                   + 304))(a1);
          if ( v16 == 259 )
          {
            if ( (v20 & 0x1000) != 0 || (RxWaitSync(a1), v16 = *(_DWORD *)(a1 + 176), v16 == 259) )
            {
              CscNotifyReferenceContext_Real(v19);
              v16 = CscNotifyQueueNewIrp(a1);
              if ( v16 != 259 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                {
                  WPP_SF_qqD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    53,
                    WPP_f1d0093ed16337749994f41f70b429cb_Traceguids,
                    a1,
                    v6,
                    v16);
                }
                IoCancelIrp(*(PIRP *)(a1 + 40));
                v16 = 259;
                v14 = 5438;
              }
              goto LABEL_37;
            }
          }
          if ( v16 == -1069481983 )
            CscNotifyDereferenceContextAndComplete_Real(v19);
        }
      }
      else
      {
        v16 = -1073741822;
      }
      CscNotifyContextSkipLocalIrpSubmit(v19, v16);
LABEL_37:
      CscNotifyDereferenceContextAndComplete_Real(v19);
      goto LABEL_17;
    }
    v14 = 5310;
    v16 = -1073741670;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    LODWORD(v21) = v14;
    WPP_SF_Ddq(WPP_GLOBAL_Control->AttachedDevice, v11, v12, v16, v21, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x14006e380  mov     [rsp+arg_10], rbx
0x14006e385  push    rbp
0x14006e386  push    rsi
0x14006e387  push    rdi
0x14006e388  push    r12
0x14006e38a  push    r14
0x14006e38c  sub     rsp, 90h
0x14006e393  mov     rax, cs:__security_cookie
0x14006e39a  xor     rax, rsp
0x14006e39d  mov     [rsp+0B8h+var_30], rax
0x14006e3a5  mov     rax, cs:CscDeviceObject
0x14006e3ac  lea     rdx, [rsp+0B8h+var_68]
0x14006e3b1  cmp     [rcx+50h], rax
0x14006e3b5  xorps   xmm0, xmm0
0x14006e3b8  mov     rdi, [rcx+38h]
0x14006e3bc  mov     rbx, rcx
0x14006e3bf  mov     r14, [rcx+40h]
0x14006e3c3  setnz   sil
0x14006e3c7  mov     rbp, [rcx+48h]
0x14006e3cb  xor     eax, eax
0x14006e3cd  mov     [rsp+0B8h+var_48], rax
0x14006e3d2  movups  [rsp+0B8h+var_68], xmm0
0x14006e3d7  movups  [rsp+0B8h+var_58], xmm0
0x14006e3dc  movups  [rsp+0B8h+var_40], xmm0
0x14006e3e1  call    CscGetContexts
0x14006e3e6  lea     rax, [rsp+0B8h+var_40]
0x14006e3eb  mov     byte ptr [rsp+0B8h+var_90], 1
0x14006e3f0  mov     r8, rcx
0x14006e3f3  mov     [rsp+0B8h+var_98], rax
0x14006e3f8  mov     rcx, rdi
0x14006e3fb  mov     r9b, 1
0x14006e3fe  mov     rdx, rbp
0x14006e401  call    CscUpdateAndCaptureConnectionStateEx
0x14006e406  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e40d  lea     r12, WPP_GLOBAL_Control
0x14006e414  cmp     rcx, r12
0x14006e417  jz      short loc_14006E424
0x14006e419  mov     eax, [rcx+2Ch]
0x14006e41c  test    al, 20h
0x14006e41e  jnz     loc_14006E71E
0x14006e424  mov     rax, qword ptr [rsp+0B8h+var_58]
0x14006e429  test    rax, rax
0x14006e42c  jz      short loc_14006E439
0x14006e42e  mov     eax, [rax+18h]
0x14006e431  test    al, 9
0x14006e433  jnz     loc_14006E606
0x14006e439  test    byte ptr [rsp+0B8h+var_40+1], 40h
0x14006e43e  jnz     loc_14006E768
0x14006e444  mov     eax, 0EC21h
0x14006e449  cmp     [rdi], ax
0x14006e44c  jnz     loc_14006E77E
0x14006e452  movzx   ecx, byte ptr [rsp+0B8h+var_40]
0x14006e457  test    cl, 20h
0x14006e45a  jnz     loc_14006E61F
0x14006e460  xor     ebp, ebp
0x14006e462  test    sil, sil
0x14006e465  jz      short loc_14006E474
0x14006e467  movzx   eax, cl
0x14006e46a  and     al, 30h
0x14006e46c  cmp     al, 20h ; ' '
0x14006e46e  jz      loc_14006E53E
0x14006e474  test    cl, 20h
0x14006e477  jnz     loc_14006E804
0x14006e47d  mov     rax, [rbx+50h]
0x14006e481  movzx   edx, word ptr [rbx+208h]
0x14006e488  mov     rcx, [rax+160h]
0x14006e48f  cmp     [rcx+rdx*8+130h], rbp
0x14006e497  jz      loc_14006E5FC
0x14006e49d  mov     eax, [rbx+80h]
0x14006e4a3  test    al, 2
0x14006e4a5  jnz     loc_14006E615
0x14006e4ab  mov     esi, [rbx+78h]
0x14006e4ae  xor     eax, eax
0x14006e4b0  xorps   xmm0, xmm0
0x14006e4b3  movups  xmmword ptr [rbx+0D0h], xmm0
0x14006e4ba  movups  xmmword ptr [rbx+0E0h], xmm0
0x14006e4c1  mov     [rbx+0F0h], rax
0x14006e4c8  mov     rax, [rbx+50h]
0x14006e4cc  movzx   edx, word ptr [rbx+208h]
0x14006e4d3  mov     rcx, [rax+160h]
0x14006e4da  mov     rax, [rcx+rdx*8+130h]
0x14006e4e2  mov     rcx, rbx
0x14006e4e5  call    _guard_dispatch_icall
0x14006e4ea  mov     edi, eax
0x14006e4ec  cmp     eax, 103h
0x14006e4f1  jnz     short loc_14006E4FD
0x14006e4f3  bt      esi, 0Ch
0x14006e4f7  jnb     loc_14006E843
0x14006e4fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e504  cmp     rcx, r12
0x14006e507  jz      short loc_14006E514
0x14006e509  mov     eax, [rcx+2Ch]
0x14006e50c  test    al, 20h
0x14006e50e  jnz     loc_14006E85D
0x14006e514  mov     eax, edi
0x14006e516  mov     rcx, [rsp+0B8h+var_30]
0x14006e51e  xor     rcx, rsp; StackCookie
0x14006e521  call    __security_check_cookie
0x14006e526  mov     rbx, [rsp+0B8h+arg_10]
0x14006e52e  add     rsp, 90h
0x14006e535  pop     r14
0x14006e537  pop     r12
0x14006e539  pop     rdi
0x14006e53a  pop     rsi
0x14006e53b  pop     rbp
0x14006e53c  retn
0x14006e53e  mov     rcx, rbx
0x14006e541  call    CscNotifyAllocateAndReferenceContext
0x14006e546  mov     rsi, rax
0x14006e549  test    rax, rax
0x14006e54c  jz      loc_14006E657
0x14006e552  mov     [rax+8], rbx
0x14006e556  lea     rcx, [rsi+28h]; Event
0x14006e55a  mov     rax, [rbx+210h]
0x14006e561  xor     r8d, r8d; State
0x14006e564  mov     [rsi+10h], rax
0x14006e568  xor     edx, edx; Type
0x14006e56a  lea     rax, CscNotifyChangeDirectoryCompletionEntry
0x14006e571  mov     [rsp+0B8h+arg_8], r15
0x14006e579  mov     [rbx+210h], rax
0x14006e580  mov     rax, gs:188h
0x14006e589  mov     [rsi+68h], rax
0x14006e58d  call    cs:__imp_KeInitializeEvent
0x14006e594  nop     dword ptr [rax+rax+00h]
0x14006e599  lea     rcx, [rsi+40h]; Event
0x14006e59d  xor     r8d, r8d; State
0x14006e5a0  xor     edx, edx; Type
0x14006e5a2  call    cs:__imp_KeInitializeEvent
0x14006e5a9  nop     dword ptr [rax+rax+00h]
0x14006e5ae  mov     dword ptr [rsi], 70EAA5h
0x14006e5b4  mov     [rbx+108h], rsi
0x14006e5bb  lock or dword ptr [rsi+58h], 1
0x14006e5c0  mov     rcx, rsi
0x14006e5c3  call    CscNotifyReferenceContext_Real
0x14006e5c8  mov     rax, [rbx+50h]
0x14006e5cc  movzx   edx, word ptr [rbx+208h]
0x14006e5d3  mov     rcx, [rax+160h]
0x14006e5da  cmp     [rcx+rdx*8+130h], rbp
0x14006e5e2  jz      loc_14006E797
0x14006e5e8  mov     eax, [rbx+80h]
0x14006e5ee  test    al, 2
0x14006e5f0  jz      short loc_14006E666
0x14006e5f2  mov     edi, 0C0000120h
0x14006e5f7  jmp     loc_14006E6C3
0x14006e5fc  mov     edi, 0C0000002h
0x14006e601  jmp     loc_14006E4FD
0x14006e606  mov     ebp, 148Ah
0x14006e60b  mov     edi, 0C000000Dh
0x14006e610  jmp     loc_14006E4FD
0x14006e615  mov     edi, 0C0000120h
0x14006e61a  jmp     loc_14006E4FD
0x14006e61f  mov     rax, qword ptr [rsp+0B8h+var_68+8]
0x14006e624  mov     ecx, [rax+4]
0x14006e627  test    cl, 60h
0x14006e62a  jnz     loc_14006E78D
0x14006e630  lea     rax, [rsp+0B8h+var_40]
0x14006e635  mov     r8, rbp
0x14006e638  lea     r9, [rsp+0B8h+var_68]
0x14006e63d  mov     [rsp+0B8h+var_98], rax
0x14006e642  mov     rdx, rdi
0x14006e645  mov     rcx, rbx
0x14006e648  call    CscDirCtrlBackpatchIfPossible
0x14006e64d  movzx   ecx, byte ptr [rsp+0B8h+var_40]
0x14006e652  jmp     loc_14006E460
0x14006e657  mov     ebp, 14BEh
0x14006e65c  mov     edi, 0C000009Ah
0x14006e661  jmp     loc_14006E4FD
0x14006e666  mov     r15d, [rbx+78h]
0x14006e66a  xor     eax, eax
0x14006e66c  xorps   xmm0, xmm0
0x14006e66f  movups  xmmword ptr [rbx+0D0h], xmm0
0x14006e676  movups  xmmword ptr [rbx+0E0h], xmm0
0x14006e67d  mov     [rbx+0F0h], rax
0x14006e684  mov     rax, [rbx+50h]
0x14006e688  movzx   edx, word ptr [rbx+208h]
0x14006e68f  mov     rcx, [rax+160h]
0x14006e696  mov     rax, [rcx+rdx*8+130h]
0x14006e69e  mov     rcx, rbx
0x14006e6a1  call    _guard_dispatch_icall
0x14006e6a6  mov     edi, eax
0x14006e6a8  cmp     eax, 103h
0x14006e6ad  jz      loc_14006E7A1
0x14006e6b3  cmp     edi, 0C0410001h
0x14006e6b9  jnz     short loc_14006E6C3
0x14006e6bb  mov     rcx, rsi; P
0x14006e6be  call    CscNotifyDereferenceContextAndComplete_Real
0x14006e6c3  mov     edx, edi
0x14006e6c5  mov     rcx, rsi
0x14006e6c8  call    CscNotifyContextSkipLocalIrpSubmit
0x14006e6cd  jmp     short loc_14006E709
0x14006e6cf  mov     rcx, rbx
0x14006e6d2  call    cs:__imp_RxWaitSync
0x14006e6d9  nop     dword ptr [rax+rax+00h]
0x14006e6de  mov     edi, [rbx+0B0h]
0x14006e6e4  cmp     edi, 103h
0x14006e6ea  jnz     short loc_14006E6B3
0x14006e6ec  mov     rcx, rsi
0x14006e6ef  call    CscNotifyReferenceContext_Real
0x14006e6f4  mov     rcx, rbx
0x14006e6f7  call    CscNotifyQueueNewIrp
0x14006e6fc  mov     edi, eax
0x14006e6fe  cmp     eax, 103h
0x14006e703  jnz     loc_14006E7B1
0x14006e709  mov     rcx, rsi; P
0x14006e70c  call    CscNotifyDereferenceContextAndComplete_Real
0x14006e711  mov     r15, [rsp+0B8h+arg_8]
0x14006e719  jmp     loc_14006E4FD
0x14006e71e  cmp     byte ptr [rbx+218h], 0
0x14006e725  mov     r9d, 59h ; 'Y'
0x14006e72b  mov     rcx, [rcx+18h]
0x14006e72f  mov     eax, r9d
0x14006e732  mov     edx, 4Eh ; 'N'
0x14006e737  cmovz   eax, edx
0x14006e73a  test    sil, sil
0x14006e73d  mov     [rsp+0B8h+var_78], al
0x14006e741  mov     eax, [rbx+21Ch]
0x14006e747  cmovz   r9d, edx
0x14006e74b  mov     [rsp+0B8h+var_80], eax
0x14006e74f  mov     [rsp+0B8h+var_88], rbp
0x14006e754  mov     [rsp+0B8h+var_90], r14
0x14006e759  mov     [rsp+0B8h+var_98], rbx
0x14006e75e  call    WPP_SF_cqqqDc
0x14006e763  jmp     loc_14006E424
0x14006e768  lea     rcx, [rsp+0B8h+var_40]
0x14006e76d  call    CscDetermineAbortStatus
0x14006e772  mov     edi, eax
0x14006e774  mov     ebp, 1492h
0x14006e779  jmp     loc_14006E4FD
0x14006e77e  mov     ebp, 1498h
0x14006e783  mov     edi, 0C000000Dh
0x14006e788  jmp     loc_14006E4FD
0x14006e78d  mov     eax, 0C000000Dh
0x14006e792  jmp     loc_14006E516
0x14006e797  mov     edi, 0C0000002h
0x14006e79c  jmp     loc_14006E6C3
0x14006e7a1  bt      r15d, 0Ch
0x14006e7a6  jb      loc_14006E6EC
0x14006e7ac  jmp     loc_14006E6CF
0x14006e7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e7b8  cmp     rcx, r12
0x14006e7bb  jz      short loc_14006E7E5
0x14006e7bd  mov     eax, [rcx+2Ch]
0x14006e7c0  test    al, 20h
0x14006e7c2  jz      short loc_14006E7E5
0x14006e7c4  mov     rcx, [rcx+18h]
0x14006e7c8  lea     r8, WPP_f1d0093ed16337749994f41f70b429cb_Traceguids
0x14006e7cf  mov     edx, 35h ; '5'
0x14006e7d4  mov     dword ptr [rsp+0B8h+var_90], edi
0x14006e7d8  mov     r9, rbx
0x14006e7db  mov     [rsp+0B8h+var_98], r14
0x14006e7e0  call    WPP_SF_qqD
0x14006e7e5  mov     rcx, [rbx+28h]; Irp
0x14006e7e9  call    cs:__imp_IoCancelIrp
0x14006e7f0  nop     dword ptr [rax+rax+00h]
0x14006e7f5  mov     edi, 103h
0x14006e7fa  mov     ebp, 153Eh
0x14006e7ff  jmp     loc_14006E709
0x14006e804  mov     r8d, [rbx+21Ch]
0x14006e80b  xor     r9d, r9d
0x14006e80e  movzx   edx, byte ptr [rbx+218h]
0x14006e815  mov     rcx, rbx
0x14006e818  call    CscNotifyFullChangeDirectory
0x14006e81d  mov     edi, eax
0x14006e81f  cmp     eax, 103h
0x14006e824  jnz     loc_14006E4FD
0x14006e82a  xor     r8d, r8d
0x14006e82d  xor     edx, edx
0x14006e82f  mov     rcx, rbx
0x14006e832  call    cs:__imp_RxCompleteRequestEx
0x14006e839  nop     dword ptr [rax+rax+00h]
0x14006e83e  jmp     loc_14006E4FD
0x14006e843  mov     rcx, rbx
0x14006e846  call    cs:__imp_RxWaitSync
0x14006e84d  nop     dword ptr [rax+rax+00h]
0x14006e852  mov     edi, [rbx+0B0h]
0x14006e858  jmp     loc_14006E4FD
0x14006e85d  mov     rcx, [rcx+18h]
0x14006e861  mov     r9d, edi
0x14006e864  mov     [rsp+0B8h+var_90], 0
0x14006e86d  mov     dword ptr [rsp+0B8h+var_98], ebp
0x14006e871  call    WPP_SF_Ddq
0x14006e876  jmp     loc_14006E514
```
