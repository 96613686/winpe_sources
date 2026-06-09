# MRxDAVFastIoDeviceControl

- ea: `0x14000f780`
- end: `0x14000f9cc`
- name: `MRxDAVFastIoDeviceControl`
- size: `588`
- prototype: `char __fastcall(__int64, __int64, volatile void *, unsigned int, volatile void *Address, unsigned int Length, int, int *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x140001290`
- `0x1400015f0`
- `0x14000163c`
- `0x140001680`
- `0x1400062b0`
- `0x14000f780`
- `0x140010554`
- `0x140028510`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f7b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f813`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f7b7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000f813`
- `ntoskrnl!ProbeForRead` at `0x14000f8e8`
- `ntoskrnl!ProbeForRead` at `0x14000f8e8`
- `ntoskrnl!ProbeForWrite` at `0x14000f90c`
- `ntoskrnl!ProbeForWrite` at `0x14000f90c`

## pseudocode

```c
char __fastcall MRxDAVFastIoDeviceControl(
        __int64 a1,
        __int64 a2,
        volatile void *a3,
        unsigned int a4,
        volatile void *Address,
        unsigned int Length,
        int a7,
        int *a8,
        __int64 a9)
{
  SIZE_T v9; // r14
  __int64 v12; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v14; // rbx
  HANDLE v15; // rax
  int IsCallerPrivileged; // edi
  __int64 v18; // r8
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int *v21; // rax
  __int64 v22; // rcx

  v9 = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qD(v12, 41, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, CurrentThreadId, a7);
  }
  if ( *(_QWORD *)(a1 + 24) != *(_QWORD *)(a9 + 1640) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v14 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v15 = PsGetCurrentThreadId();
      WPP_SF_q(v14, 42, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids, v15);
    }
    return 0;
  }
  if ( a7 == 1311608 )
  {
    IsCallerPrivileged = MRxDavIsCallerPrivileged();
    if ( IsCallerPrivileged < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0 )
        goto LABEL_20;
      v20 = 43;
      goto LABEL_19;
    }
    UMRxReleaseCapturedThreads(a9);
LABEL_32:
    v21 = a8;
    *a8 = 0;
    goto LABEL_33;
  }
  if ( a7 == 1311614 || a7 == 1311618 || a7 == 1311622 )
    return 0;
  if ( a7 != 1311624 )
  {
    if ( a7 == 1311636 )
    {
      IsCallerPrivileged = MRxDavIsCallerPrivileged();
      if ( IsCallerPrivileged < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0 )
        {
          goto LABEL_20;
        }
        v20 = 44;
LABEL_19:
        WPP_SF_d(v19[3], v20, v18, (unsigned int)IsCallerPrivileged);
LABEL_20:
        v21 = a8;
        *a8 = IsCallerPrivileged;
LABEL_33:
        *((_QWORD *)v21 + 1) = 0;
        return 1;
      }
      UMRxPrepareWorkerQueue(a9);
      goto LABEL_32;
    }
    return 0;
  }
  IsCallerPrivileged = MRxDavIsCallerPrivileged();
  if ( IsCallerPrivileged < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x1000) == 0 )
      goto LABEL_20;
    v20 = 45;
    goto LABEL_19;
  }
  ProbeForRead(a3, v9, 1u);
  ProbeForWrite(Address, Length, 1u);
  MRxDAVGetLockOwnerFromFileName(v22, a3, (unsigned int)v9, Address, Length, a8);
  return 1;
}

```

## disassembly

```asm
0x14000f780  push    rbx
0x14000f782  push    rsi
0x14000f783  push    rdi
0x14000f784  push    r12
0x14000f786  push    r14
0x14000f788  push    r15
0x14000f78a  sub     rsp, 38h
0x14000f78e  mov     r14d, r9d
0x14000f791  mov     r15, r8
0x14000f794  mov     rdi, rcx
0x14000f797  lea     r12, WPP_GLOBAL_Control
0x14000f79e  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f7a5  cmp     rbx, r12
0x14000f7a8  jz      short loc_14000F7E5
0x14000f7aa  test    dword ptr [rbx+2Ch], 4000h
0x14000f7b1  jz      short loc_14000F7E5
0x14000f7b3  mov     rbx, [rbx+18h]
0x14000f7b7  call    cs:__imp_PsGetCurrentThreadId
0x14000f7be  nop     dword ptr [rax+rax+00h]
0x14000f7c3  mov     r9, rax
0x14000f7c6  mov     edx, 29h ; ')'
0x14000f7cb  mov     eax, [rsp+68h+arg_30]
0x14000f7d2  mov     [rsp+68h+var_48], eax
0x14000f7d6  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f7dd  mov     rcx, rbx
0x14000f7e0  call    WPP_SF_qD
0x14000f7e5  mov     rsi, [rsp+68h+arg_40]
0x14000f7ed  mov     rax, [rsi+668h]
0x14000f7f4  cmp     [rdi+18h], rax
0x14000f7f8  jz      short loc_14000F83D
0x14000f7fa  mov     rbx, cs:WPP_GLOBAL_Control
0x14000f801  cmp     rbx, r12
0x14000f804  jz      short loc_14000F836
0x14000f806  test    dword ptr [rbx+2Ch], 2000h
0x14000f80d  jz      short loc_14000F836
0x14000f80f  mov     rbx, [rbx+18h]
0x14000f813  call    cs:__imp_PsGetCurrentThreadId
0x14000f81a  nop     dword ptr [rax+rax+00h]
0x14000f81f  mov     r9, rax
0x14000f822  mov     edx, 2Ah ; '*'
0x14000f827  lea     r8, WPP_c9ea18f8c0d9351c3b8fa09e3aa5b77e_Traceguids
0x14000f82e  mov     rcx, rbx
0x14000f831  call    WPP_SF_q
0x14000f836  xor     al, al
0x14000f838  jmp     loc_14000F9BD
0x14000f83d  mov     eax, [rsp+68h+arg_30]
0x14000f844  sub     eax, 140378h
0x14000f849  jz      loc_14000F973
0x14000f84f  sub     eax, 6
0x14000f852  jz      short loc_14000F836
0x14000f854  sub     eax, 4
0x14000f857  jz      short loc_14000F836
0x14000f859  sub     eax, 4
0x14000f85c  jz      short loc_14000F836
0x14000f85e  sub     eax, 2
0x14000f861  jz      short loc_14000F8B5
0x14000f863  cmp     eax, 0Ch
0x14000f866  jnz     short loc_14000F836
0x14000f868  call    MRxDavIsCallerPrivileged
0x14000f86d  mov     edi, eax
0x14000f86f  xor     ebx, ebx
0x14000f871  test    eax, eax
0x14000f873  jns     short loc_14000F8A8
0x14000f875  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f87c  cmp     rcx, r12
0x14000f87f  jz      short loc_14000F899
0x14000f881  test    dword ptr [rcx+2Ch], 1000h
0x14000f888  jz      short loc_14000F899
0x14000f88a  lea     edx, [rbx+2Ch]
0x14000f88d  mov     r9d, edi
0x14000f890  mov     rcx, [rcx+18h]
0x14000f894  call    WPP_SF_d
0x14000f899  mov     rax, [rsp+68h+arg_38]
0x14000f8a1  mov     [rax], edi
0x14000f8a3  jmp     loc_14000F9B7
0x14000f8a8  mov     rcx, rsi
0x14000f8ab  call    UMRxPrepareWorkerQueue
0x14000f8b0  jmp     loc_14000F9AD
0x14000f8b5  call    MRxDavIsCallerPrivileged
0x14000f8ba  mov     edi, eax
0x14000f8bc  xor     ebx, ebx
0x14000f8be  test    eax, eax
0x14000f8c0  jns     short loc_14000F8DC
0x14000f8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8c9  cmp     rcx, r12
0x14000f8cc  jz      short loc_14000F899
0x14000f8ce  test    dword ptr [rcx+2Ch], 1000h
0x14000f8d5  jz      short loc_14000F899
0x14000f8d7  lea     edx, [rbx+2Dh]
0x14000f8da  jmp     short loc_14000F88D
0x14000f8dc  mov     rdx, r14; Length
0x14000f8df  mov     r8d, 1; Alignment
0x14000f8e5  mov     rcx, r15; Address
0x14000f8e8  call    cs:__imp_ProbeForRead
0x14000f8ef  nop     dword ptr [rax+rax+00h]
0x14000f8f4  nop
0x14000f8f5  mov     ebx, dword ptr [rsp+68h+Length]
0x14000f8fc  mov     edx, ebx; Length
0x14000f8fe  mov     r8d, 1; Alignment
0x14000f904  mov     rcx, [rsp+68h+Address]; Address
0x14000f90c  call    cs:__imp_ProbeForWrite
0x14000f913  nop     dword ptr [rax+rax+00h]
0x14000f918  nop
0x14000f919  mov     rax, [rsp+68h+arg_38]
0x14000f921  mov     [rsp+68h+var_40], rax
0x14000f926  mov     [rsp+68h+var_48], ebx
0x14000f92a  mov     r9, [rsp+68h+Address]
0x14000f932  mov     r8d, r14d
0x14000f935  mov     rdx, r15
0x14000f938  call    MRxDAVGetLockOwnerFromFileName
0x14000f93d  jmp     short loc_14000F9BB
0x14000f93f  mov     rax, [rsp+68h+arg_38]
0x14000f947  mov     dword ptr [rax], 0C00000E8h
0x14000f94d  mov     qword ptr [rax+8], 0
0x14000f955  xor     al, al
0x14000f957  jmp     short loc_14000F9BD
0x14000f959  mov     rax, [rsp+68h+arg_38]
0x14000f961  mov     dword ptr [rax], 0C00000E8h
0x14000f967  mov     qword ptr [rax+8], 0
0x14000f96f  xor     al, al
0x14000f971  jmp     short loc_14000F9BD
0x14000f973  call    MRxDavIsCallerPrivileged
0x14000f978  mov     edi, eax
0x14000f97a  xor     ebx, ebx
0x14000f97c  test    eax, eax
0x14000f97e  jns     short loc_14000F9A5
0x14000f980  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f987  cmp     rcx, r12
0x14000f98a  jz      loc_14000F899
0x14000f990  test    dword ptr [rcx+2Ch], 1000h
0x14000f997  jz      loc_14000F899
0x14000f99d  lea     edx, [rbx+2Bh]
0x14000f9a0  jmp     loc_14000F88D
0x14000f9a5  mov     rcx, rsi
0x14000f9a8  call    UMRxReleaseCapturedThreads
0x14000f9ad  mov     rax, [rsp+68h+arg_38]
0x14000f9b5  mov     [rax], ebx
0x14000f9b7  mov     [rax+8], rbx
0x14000f9bb  mov     al, 1
0x14000f9bd  add     rsp, 38h
0x14000f9c1  pop     r15
0x14000f9c3  pop     r14
0x14000f9c5  pop     r12
0x14000f9c7  pop     rdi
0x14000f9c8  pop     rsi
0x14000f9c9  pop     rbx
0x14000f9ca  retn
```
