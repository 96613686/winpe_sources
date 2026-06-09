# WFDPeerDeviceCreate(_WFD_DEVICE_ROLE *,uchar (*)[6],void *,WFD_PEER_TYPE,_WFD_PEER_DEVICE * *)

- ea: `0x14008a7d0`
- end: `0x14008a96a`
- name: `?WFDPeerDeviceCreate@@YAHPEAU_WFD_DEVICE_ROLE@@PEAY05EPEAXW4WFD_PEER_TYPE@@PEAPEAU_WFD_PEER_DEVICE@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140086e00`
- `0x1400879a0`
- `0x140087ff0`

## callees

- `0x140020dc0`
- `0x14008a7d0`
- `0x14008d18c`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a7f3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14008a7f3`
- `ntoskrnl!KeInitializeTimer` at `0x14008a8c8`
- `ntoskrnl!KeInitializeTimer` at `0x14008a8c8`
- `ntoskrnl!KeInitializeDpc` at `0x14008a8e5`
- `ntoskrnl!KeInitializeDpc` at `0x14008a8e5`

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
0x14008a7d0  push    rbx
0x14008a7d2  push    rbp
0x14008a7d3  push    rsi
0x14008a7d4  push    rdi
0x14008a7d5  push    r14
0x14008a7d7  push    r15
0x14008a7d9  sub     rsp, 38h
0x14008a7dd  mov     rsi, rcx
0x14008a7e0  lea     rbx, Lookaside
0x14008a7e7  mov     rcx, rbx; Lookaside
0x14008a7ea  mov     edi, r9d
0x14008a7ed  mov     rbp, r8
0x14008a7f0  mov     r14, rdx
0x14008a7f3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14008a7fa  nop     dword ptr [rax+rax+00h]
0x14008a7ff  test    rax, rax
0x14008a802  jnz     short loc_14008A83D
0x14008a804  mov     edi, 0C000009Ah
0x14008a809  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a810  lea     rax, WPP_GLOBAL_Control
0x14008a817  cmp     rcx, rax
0x14008a81a  jz      loc_14008A95A
0x14008a820  mov     rcx, [rcx+18h]
0x14008a824  lea     r8, WPP_efc341ab2d9537303f1bc991c0cdd50d_Traceguids
0x14008a82b  mov     edx, 0Ah
0x14008a830  mov     r9d, edi
0x14008a833  call    WPP_SF_d
0x14008a838  jmp     loc_14008A95A
0x14008a83d  mov     [rax], rbx
0x14008a840  xor     edx, edx; Val
0x14008a842  lea     rbx, [rax+10h]
0x14008a846  mov     dword ptr [rax+8], 30337776h
0x14008a84d  mov     rcx, rbx; void *
0x14008a850  mov     r8d, 360h; Size
0x14008a856  call    memset
0x14008a85b  mov     [rbx+10h], rsi
0x14008a85f  lea     r15, [rbx+18h]
0x14008a863  mov     eax, [r14]
0x14008a866  mov     [r15], eax
0x14008a869  movzx   eax, word ptr [r14+4]
0x14008a86e  mov     [r15+4], ax
0x14008a873  mov     [rbx+30h], rbp
0x14008a877  mov     [rbx+20h], edi
0x14008a87a  mov     ecx, 1
0x14008a87f  lock xadd [rsi+30h], ecx
0x14008a884  inc     ecx
0x14008a886  mov     eax, 80008001h
0x14008a88b  mul     ecx
0x14008a88d  shr     edx, 0Fh
0x14008a890  imul    eax, edx, 0FFFFh
0x14008a896  sub     ecx, eax
0x14008a898  jz      short loc_14008A87A
0x14008a89a  mov     [rbx+38h], ecx
0x14008a89d  test    edi, edi
0x14008a89f  jz      short loc_14008A8BD
0x14008a8a1  sub     edi, 1
0x14008a8a4  jz      short loc_14008A8B4
0x14008a8a6  cmp     edi, 1
0x14008a8a9  jnz     short loc_14008A8C4
0x14008a8ab  mov     dword ptr [rbx+24h], 11h
0x14008a8b2  jmp     short loc_14008A8C4
0x14008a8b4  mov     dword ptr [rbx+24h], 9
0x14008a8bb  jmp     short loc_14008A8C4
0x14008a8bd  mov     dword ptr [rbx+24h], 0
0x14008a8c4  lea     rcx, [rbx+40h]; Timer
0x14008a8c8  call    cs:__imp_KeInitializeTimer
0x14008a8cf  nop     dword ptr [rax+rax+00h]
0x14008a8d4  lea     rcx, [rbx+80h]; Dpc
0x14008a8db  mov     r8, rbx; DeferredContext
0x14008a8de  lea     rdx, ?WFDPeerDeviceTimeoutDPC@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x14008a8e5  call    cs:__imp_KeInitializeDpc
0x14008a8ec  nop     dword ptr [rax+rax+00h]
0x14008a8f1  lea     rax, [rsi+50h]
0x14008a8f5  mov     rcx, [rax+8]
0x14008a8f9  cmp     [rcx], rax
0x14008a8fc  jz      short loc_14008A905
0x14008a8fe  mov     ecx, 3
0x14008a903  int     29h; Win8: RtlFailFast(ecx)
0x14008a905  mov     [rbx], rax
0x14008a908  xor     edi, edi
0x14008a90a  mov     [rbx+8], rcx
0x14008a90e  mov     [rcx], rbx
0x14008a911  mov     [rax+8], rbx
0x14008a915  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a91c  lea     rax, WPP_GLOBAL_Control
0x14008a923  cmp     rcx, rax
0x14008a926  jz      short loc_14008A94F
0x14008a928  cmp     byte ptr [rcx+29h], 3
0x14008a92c  jb      short loc_14008A94F
0x14008a92e  test    dword ptr [rcx+2Ch], 200000h
0x14008a935  jz      short loc_14008A94F
0x14008a937  mov     edx, [rbx+38h]
0x14008a93a  mov     r9, rbx
0x14008a93d  mov     rcx, [rcx+18h]
0x14008a941  mov     [rsp+68h+var_40], r15
0x14008a946  mov     [rsp+68h+var_48], edx
0x14008a94a  call    WPP_SF_qD_MAC_
0x14008a94f  mov     rcx, [rsp+68h+arg_20]
0x14008a957  mov     [rcx], rbx
0x14008a95a  mov     eax, edi
0x14008a95c  add     rsp, 38h
0x14008a960  pop     r15
0x14008a962  pop     r14
0x14008a964  pop     rdi
0x14008a965  pop     rsi
0x14008a966  pop     rbp
0x14008a967  pop     rbx
0x14008a968  retn
```
