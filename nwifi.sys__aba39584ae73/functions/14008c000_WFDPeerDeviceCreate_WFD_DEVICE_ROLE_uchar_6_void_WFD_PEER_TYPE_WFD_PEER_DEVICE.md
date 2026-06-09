# WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)

- ea: `0x14008c000`
- end: `0x14008c19a`
- name: `?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140088630`
- `0x1400891d0`
- `0x140089820`

## callees

- `0x140020dc0`
- `0x14008c000`
- `0x14008e9bc`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008c023`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008c023`
- `ntoskrnl!KeInitializeTimer` at `0x14008c0f8`
- `ntoskrnl!KeInitializeTimer` at `0x14008c0f8`
- `ntoskrnl!KeInitializeDpc` at `0x14008c115`
- `ntoskrnl!KeInitializeDpc` at `0x14008c115`

## pseudocode

```c
__int64 __fastcall WFDPeerDeviceCreate(__int64 a1, __int64 a2, __int64 a3, int a4, _QWORD *a5)
{
  char *v9; // rax
  unsigned int v10; // edi
  _QWORD *v11; // rbx
  unsigned __int32 v12; // ecx
  int v13; // edi
  int v14; // r8d
  _QWORD *v15; // rcx

  v9 = (char *)ExAllocateFromNPagedLookasideList(&Lookaside);
  if ( v9 )
  {
    *(_QWORD *)v9 = &Lookaside;
    v11 = v9 + 16;
    *((_DWORD *)v9 + 2) = 808679286;
    memset(v9 + 16, 0, 0x360u);
    v11[2] = a1;
    *((_DWORD *)v11 + 6) = *(_DWORD *)a2;
    *((_WORD *)v11 + 14) = *(_WORD *)(a2 + 4);
    v11[6] = a3;
    *((_DWORD *)v11 + 8) = a4;
    do
      v12 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 48)) % 0xFFFFu;
    while ( !v12 );
    *((_DWORD *)v11 + 14) = v12;
    if ( a4 )
    {
      v13 = a4 - 1;
      if ( v13 )
      {
        if ( v13 == 1 )
          *((_DWORD *)v11 + 9) = 17;
      }
      else
      {
        *((_DWORD *)v11 + 9) = 9;
      }
    }
    else
    {
      *((_DWORD *)v11 + 9) = 0;
    }
    KeInitializeTimer((PKTIMER)v11 + 1);
    KeInitializeDpc((PRKDPC)v11 + 2, WFDPeerDeviceTimeoutDPC, v11);
    v15 = *(_QWORD **)(a1 + 88);
    if ( *v15 != a1 + 80 )
      __fastfail(3u);
    *v11 = a1 + 80;
    v10 = 0;
    v11[1] = v15;
    *v15 = v11;
    *(_QWORD *)(a1 + 88) = v11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    {
      WPP_SF_qD_MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        *((_DWORD *)v11 + 14),
        v14,
        (_DWORD)v11,
        *((_DWORD *)v11 + 14),
        (__int64)(v11 + 3));
    }
    *a5 = v11;
  }
  else
  {
    v10 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids, 3221225626LL);
  }
  return v10;
}

```

## disassembly

```asm
0x14008c000  push    rbx
0x14008c002  push    rbp
0x14008c003  push    rsi
0x14008c004  push    rdi
0x14008c005  push    r14
0x14008c007  push    r15
0x14008c009  sub     rsp, 38h
0x14008c00d  mov     rsi, rcx
0x14008c010  lea     rbx, Lookaside
0x14008c017  mov     rcx, rbx; Lookaside
0x14008c01a  mov     edi, r9d
0x14008c01d  mov     rbp, r8
0x14008c020  mov     r14, rdx
0x14008c023  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008c02a  nop     dword ptr [rax+rax+00h]
0x14008c02f  test    rax, rax
0x14008c032  jnz     short loc_14008C06D
0x14008c034  mov     edi, 0C000009Ah
0x14008c039  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c040  lea     rax, WPP_GLOBAL_Control
0x14008c047  cmp     rcx, rax
0x14008c04a  jz      loc_14008C18A
0x14008c050  mov     rcx, [rcx+18h]
0x14008c054  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008c05b  mov     edx, 0Ah
0x14008c060  mov     r9d, edi
0x14008c063  call    WPP_SF_d
0x14008c068  jmp     loc_14008C18A
0x14008c06d  mov     [rax], rbx
0x14008c070  xor     edx, edx; Val
0x14008c072  lea     rbx, [rax+10h]
0x14008c076  mov     dword ptr [rax+8], 30337776h
0x14008c07d  mov     rcx, rbx; void *
0x14008c080  mov     r8d, 360h; Size
0x14008c086  call    memset
0x14008c08b  mov     [rbx+10h], rsi
0x14008c08f  lea     r15, [rbx+18h]
0x14008c093  mov     eax, [r14]
0x14008c096  mov     [r15], eax
0x14008c099  movzx   eax, word ptr [r14+4]
0x14008c09e  mov     [r15+4], ax
0x14008c0a3  mov     [rbx+30h], rbp
0x14008c0a7  mov     [rbx+20h], edi
0x14008c0aa  mov     ecx, 1
0x14008c0af  lock xadd [rsi+30h], ecx
0x14008c0b4  inc     ecx
0x14008c0b6  mov     eax, 80008001h
0x14008c0bb  mul     ecx
0x14008c0bd  shr     edx, 0Fh
0x14008c0c0  imul    eax, edx, 0FFFFh
0x14008c0c6  sub     ecx, eax
0x14008c0c8  jz      short loc_14008C0AA
0x14008c0ca  mov     [rbx+38h], ecx
0x14008c0cd  test    edi, edi
0x14008c0cf  jz      short loc_14008C0ED
0x14008c0d1  sub     edi, 1
0x14008c0d4  jz      short loc_14008C0E4
0x14008c0d6  cmp     edi, 1
0x14008c0d9  jnz     short loc_14008C0F4
0x14008c0db  mov     dword ptr [rbx+24h], 11h
0x14008c0e2  jmp     short loc_14008C0F4
0x14008c0e4  mov     dword ptr [rbx+24h], 9
0x14008c0eb  jmp     short loc_14008C0F4
0x14008c0ed  mov     dword ptr [rbx+24h], 0
0x14008c0f4  lea     rcx, [rbx+40h]; Timer
0x14008c0f8  call    cs:__imp_KeInitializeTimer
0x14008c0ff  nop     dword ptr [rax+rax+00h]
0x14008c104  lea     rcx, [rbx+80h]; Dpc
0x14008c10b  mov     r8, rbx; DeferredContext
0x14008c10e  lea     rdx, ?WFDPeerDeviceTimeoutDPC@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x14008c115  call    cs:__imp_KeInitializeDpc
0x14008c11c  nop     dword ptr [rax+rax+00h]
0x14008c121  lea     rax, [rsi+50h]
0x14008c125  mov     rcx, [rax+8]
0x14008c129  cmp     [rcx], rax
0x14008c12c  jz      short loc_14008C135
0x14008c12e  mov     ecx, 3
0x14008c133  int     29h; Win8: RtlFailFast(ecx)
0x14008c135  mov     [rbx], rax
0x14008c138  xor     edi, edi
0x14008c13a  mov     [rbx+8], rcx
0x14008c13e  mov     [rcx], rbx
0x14008c141  mov     [rax+8], rbx
0x14008c145  mov     rcx, cs:WPP_GLOBAL_Control
0x14008c14c  lea     rax, WPP_GLOBAL_Control
0x14008c153  cmp     rcx, rax
0x14008c156  jz      short loc_14008C17F
0x14008c158  cmp     byte ptr [rcx+29h], 3
0x14008c15c  jb      short loc_14008C17F
0x14008c15e  test    dword ptr [rcx+2Ch], 200000h
0x14008c165  jz      short loc_14008C17F
0x14008c167  mov     edx, [rbx+38h]
0x14008c16a  mov     r9, rbx
0x14008c16d  mov     rcx, [rcx+18h]
0x14008c171  mov     [rsp+68h+var_40], r15
0x14008c176  mov     [rsp+68h+var_48], edx
0x14008c17a  call    WPP_SF_qD_MAC_
0x14008c17f  mov     rcx, [rsp+68h+arg_20]
0x14008c187  mov     [rcx], rbx
0x14008c18a  mov     eax, edi
0x14008c18c  add     rsp, 38h
0x14008c190  pop     r15
0x14008c192  pop     r14
0x14008c194  pop     rdi
0x14008c195  pop     rsi
0x14008c196  pop     rbp
0x14008c197  pop     rbx
0x14008c198  retn
```
