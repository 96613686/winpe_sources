# CompleteVcs

- ea: `0x1400109d0`
- end: `0x140010d1a`
- name: `CompleteVcs`
- size: `842`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000faa0`
- `0x140010790`
- `0x140010998`
- `0x140011f9c`
- `0x1400122e0`
- `0x1400154b8`

## callees

- `0x1400013f0`
- `0x140001850`
- `0x140001990`
- `0x1400047f0`
- `0x14000f2ec`
- `0x1400106b4`
- `0x14001070c`
- `0x1400109d0`
- `0x1400187ac`
- `0x14001b830`
- `0x14001c390`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b0b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010af7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b0b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cd7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010cd7`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140010b89`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140010cb0`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140010b89`
- `NDIS!NdisCmDispatchIncomingCloseCall` at `0x140010cb0`
- `NDIS!NdisCmMakeCallComplete` at `0x140010c62`
- `NDIS!NdisCmMakeCallComplete` at `0x140010c62`
- `NDIS!NdisCmDispatchCallConnected` at `0x140010b2d`
- `NDIS!NdisCmDispatchCallConnected` at `0x140010b2d`
- `NDIS!NdisMCmActivateVc` at `0x140010bc7`
- `NDIS!NdisMCmActivateVc` at `0x140010bc7`

## pseudocode

```c
void __fastcall CompleteVcs(__int64 a1)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  KIRQL v6; // al
  int v7; // ebp
  __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned int v10; // edx
  NDIS_STATUS v11; // r14d
  __int64 v12; // rcx
  int v13; // edx
  __int128 v14; // [rsp+30h] [rbp-78h] BYREF
  __int128 v15; // [rsp+40h] [rbp-68h]

  v2 = (_QWORD **)(a1 + 144);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    v14 = 0;
    v15 = 0;
    v4 = (_QWORD *)*v3;
    if ( (_QWORD *)*v3 == v3 )
    {
      ++g_ulCompletingVcCorruption;
      *(_QWORD *)(a1 + 152) = v2;
      *v2 = v2;
    }
    else
    {
      if ( (_QWORD **)v3[1] != v2 || (_QWORD *)v4[1] != v3 )
        __fastfail(3u);
      *v2 = v4;
      v4[1] = v2;
    }
    v3[1] = v3;
    *v3 = v3;
    v5 = v3 - 14;
    ReferenceVc(v5);
    ClearFlags((char *)v5 + 60, 0x1000000);
    v6 = KeAcquireSpinLockRaiseToDpc(v5 + 5);
    v7 = *((_DWORD *)v5 + 15);
    *((_BYTE *)v5 + 48) = v6;
    ClearFlags((char *)v5 + 60, 61440);
    if ( (v7 & 0x8000) != 0 )
      SetFlags(v8, 0x20000);
    v9 = v5[3];
    *(_QWORD *)&v14 = *(_QWORD *)(v9 + 328);
    *((_QWORD *)&v14 + 1) = v5[38];
    LODWORD(v15) = *((_DWORD *)v5 + 51) >> 3;
    DWORD1(v15) = (unsigned int)v15 >> 3;
    v10 = *(_DWORD *)(v9 + 364);
    if ( *((_DWORD *)v5 + 62) < v10 )
      v10 = *((_DWORD *)v5 + 62);
    DWORD2(v15) = v10;
    v11 = *((_DWORD *)v5 + 32);
    KeReleaseSpinLock(v5 + 5, *((_BYTE *)v5 + 48));
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), *(_BYTE *)(a1 + 40));
    if ( (v7 & 0x1000) != 0 )
    {
      if ( !v11 )
      {
        NdisCmDispatchCallConnected((NDIS_HANDLE)v5[38]);
LABEL_15:
        IndicateLinkStatus(v12, &v14);
        CallSetupComplete(v5);
        goto LABEL_31;
      }
      if ( (v7 & 0x400) != 0 )
      {
        if ( !(unsigned __int8)ReferenceCall(v5) )
          goto LABEL_31;
        SetFlags((char *)v5 + 60, 0x200000);
        NdisCmDispatchIncomingCloseCall(v11, (NDIS_HANDLE)v5[38], 0, 0);
        if ( (*((_DWORD *)v5 + 15) & 0x200000) != 0 )
          CallCleanUp(v5);
LABEL_28:
        DereferenceCall(v5);
        goto LABEL_31;
      }
LABEL_30:
      CallCleanUp(v5);
      goto LABEL_31;
    }
    if ( (v7 & 0x2000) != 0 )
    {
      if ( !v11 )
      {
        NdisMCmActivateVc((NDIS_HANDLE)v5[38], (PCO_CALL_PARAMETERS)v5[21]);
        SetFlags((char *)v5 + 60, 512);
        ReferenceCall(v5);
      }
      v13 = *((_DWORD *)v5 + 51) >> 3;
      *(_DWORD *)(*(_QWORD *)(v5[21] + 8LL) + 32LL) = v13;
      *(_DWORD *)(*(_QWORD *)(v5[21] + 8LL) + 40LL) = v13;
      **(_DWORD **)(v5[21] + 8LL) = v13;
      *(_DWORD *)(*(_QWORD *)(v5[21] + 8LL) + 8LL) = v13;
      *(_DWORD *)v5[24] = 1396789842;
      *(_DWORD *)(v5[24] + 4LL) = *(_DWORD *)(v5[4] + 108LL);
      NdisCmMakeCallComplete(v11, (NDIS_HANDLE)v5[38], 0, 0, (PCO_CALL_PARAMETERS)v5[21]);
      if ( !v11 )
        goto LABEL_15;
      InactiveCallCleanUp(v5);
    }
    else
    {
      if ( (v7 & 0x4000) != 0 )
      {
        if ( !(unsigned __int8)ReferenceCall(v5) )
          goto LABEL_31;
        SetFlags((char *)v5 + 60, 0x200000);
        NdisCmDispatchIncomingCloseCall(v11, (NDIS_HANDLE)v5[38], 0, 0);
        goto LABEL_28;
      }
      if ( (v7 & 0x8000) != 0 )
        goto LABEL_30;
    }
LABEL_31:
    *(_BYTE *)(a1 + 40) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
    DereferenceVc(v5);
  }
}

```

## disassembly

```asm
0x1400109d0  push    rbx
0x1400109d2  push    rbp
0x1400109d3  push    rsi
0x1400109d4  push    rdi
0x1400109d5  push    r12
0x1400109d7  push    r13
0x1400109d9  push    r14
0x1400109db  push    r15
0x1400109dd  sub     rsp, 68h
0x1400109e1  mov     rax, cs:__security_cookie
0x1400109e8  xor     rax, rsp
0x1400109eb  mov     [rsp+0A8h+var_58], rax
0x1400109f0  mov     r15, rcx
0x1400109f3  lea     rdi, [rcx+90h]
0x1400109fa  mov     rbx, [rdi]
0x1400109fd  cmp     rbx, rdi
0x140010a00  jz      loc_140010CFB
0x140010a06  xorps   xmm0, xmm0
0x140010a09  movups  [rsp+0A8h+var_78], xmm0
0x140010a0e  movups  [rsp+0A8h+var_68], xmm0
0x140010a13  mov     rax, [rbx]
0x140010a16  cmp     rax, rbx
0x140010a19  jnz     short loc_140010A2D
0x140010a1b  inc     cs:g_ulCompletingVcCorruption
0x140010a21  mov     [r15+98h], rdi
0x140010a28  mov     [rdi], rdi
0x140010a2b  jmp     short loc_140010A48
0x140010a2d  cmp     [rbx+8], rdi
0x140010a31  jnz     loc_140010CF4
0x140010a37  cmp     [rax+8], rbx
0x140010a3b  jnz     loc_140010CF4
0x140010a41  mov     [rdi], rax
0x140010a44  mov     [rax+8], rdi
0x140010a48  mov     [rbx+8], rbx
0x140010a4c  mov     [rbx], rbx
0x140010a4f  add     rbx, 0FFFFFFFFFFFFFF90h
0x140010a53  mov     rcx, rbx
0x140010a56  call    ReferenceVc
0x140010a5b  lea     rsi, [rbx+3Ch]
0x140010a5f  mov     edx, 1000000h
0x140010a64  mov     rcx, rsi
0x140010a67  call    ClearFlags
0x140010a6c  lea     rcx, [rbx+28h]; SpinLock
0x140010a70  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010a77  nop     dword ptr [rax+rax+00h]
0x140010a7c  mov     ebp, [rsi]
0x140010a7e  mov     edx, 0F000h
0x140010a83  mov     rcx, rsi
0x140010a86  mov     [rbx+30h], al
0x140010a89  call    ClearFlags
0x140010a8e  mov     r12d, ebp
0x140010a91  and     r12d, 8000h
0x140010a98  jz      short loc_140010AA4
0x140010a9a  mov     edx, 20000h
0x140010a9f  call    SetFlags
0x140010aa4  mov     rdx, [rbx+18h]
0x140010aa8  lea     rcx, [rbx+28h]; SpinLock
0x140010aac  mov     rax, [rdx+148h]
0x140010ab3  mov     qword ptr [rsp+0A8h+var_78], rax
0x140010ab8  mov     rax, [rbx+130h]
0x140010abf  mov     qword ptr [rsp+0A8h+var_78+8], rax
0x140010ac4  mov     eax, [rbx+0CCh]
0x140010aca  shr     eax, 3
0x140010acd  mov     dword ptr [rsp+0A8h+var_68], eax
0x140010ad1  shr     eax, 3
0x140010ad4  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x140010ad8  mov     edx, [rdx+16Ch]
0x140010ade  mov     eax, [rbx+0F8h]
0x140010ae4  cmp     eax, edx
0x140010ae6  cmovb   edx, eax
0x140010ae9  mov     dword ptr [rsp+0A8h+var_68+8], edx
0x140010aed  mov     dl, [rbx+30h]; NewIrql
0x140010af0  mov     r14d, [rbx+80h]
0x140010af7  call    cs:__imp_KeReleaseSpinLock
0x140010afe  nop     dword ptr [rax+rax+00h]
0x140010b03  mov     dl, [r15+28h]; NewIrql
0x140010b07  lea     rcx, [r15+20h]; SpinLock
0x140010b0b  call    cs:__imp_KeReleaseSpinLock
0x140010b12  nop     dword ptr [rax+rax+00h]
0x140010b17  bt      ebp, 0Ch
0x140010b1b  jnb     loc_140010BAA
0x140010b21  test    r14d, r14d
0x140010b24  jnz     short loc_140010B50
0x140010b26  mov     rcx, [rbx+130h]; NdisVcHandle
0x140010b2d  call    cs:__imp_NdisCmDispatchCallConnected
0x140010b34  nop     dword ptr [rax+rax+00h]
0x140010b39  lea     rdx, [rsp+0A8h+var_78]
0x140010b3e  call    IndicateLinkStatus
0x140010b43  mov     rcx, rbx
0x140010b46  call    CallSetupComplete
0x140010b4b  jmp     loc_140010CD3
0x140010b50  bt      ebp, 0Ah
0x140010b54  jnb     loc_140010CCB
0x140010b5a  mov     rcx, rbx
0x140010b5d  call    ReferenceCall
0x140010b62  test    al, al
0x140010b64  jz      loc_140010CD3
0x140010b6a  mov     ebp, 200000h
0x140010b6f  mov     rcx, rsi
0x140010b72  mov     edx, ebp
0x140010b74  call    SetFlags
0x140010b79  mov     rdx, [rbx+130h]; NdisVcHandle
0x140010b80  xor     r8d, r8d; Buffer
0x140010b83  xor     r9d, r9d; Size
0x140010b86  mov     ecx, r14d; CloseStatus
0x140010b89  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x140010b90  nop     dword ptr [rax+rax+00h]
0x140010b95  test    [rsi], ebp
0x140010b97  jz      loc_140010CBC
0x140010b9d  mov     rcx, rbx
0x140010ba0  call    CallCleanUp
0x140010ba5  jmp     loc_140010CBC
0x140010baa  bt      ebp, 0Dh
0x140010bae  jnb     loc_140010C81
0x140010bb4  test    r14d, r14d
0x140010bb7  jnz     short loc_140010BE8
0x140010bb9  mov     rdx, [rbx+0A8h]; CallParameters
0x140010bc0  mov     rcx, [rbx+130h]; NdisVcHandle
0x140010bc7  call    cs:__imp_NdisMCmActivateVc
0x140010bce  nop     dword ptr [rax+rax+00h]
0x140010bd3  mov     edx, 200h
0x140010bd8  mov     rcx, rsi
0x140010bdb  call    SetFlags
0x140010be0  mov     rcx, rbx
0x140010be3  call    ReferenceCall
0x140010be8  mov     rax, [rbx+0A8h]
0x140010bef  xor     r9d, r9d; CallMgrPartyContext
0x140010bf2  mov     edx, [rbx+0CCh]
0x140010bf8  xor     r8d, r8d; NdisPartyHandle
0x140010bfb  shr     edx, 3
0x140010bfe  mov     rcx, [rax+8]
0x140010c02  mov     [rcx+20h], edx
0x140010c05  mov     rax, [rbx+0A8h]
0x140010c0c  mov     rcx, [rax+8]
0x140010c10  mov     [rcx+28h], edx
0x140010c13  mov     rax, [rbx+0A8h]
0x140010c1a  mov     rcx, [rax+8]
0x140010c1e  mov     [rcx], edx
0x140010c20  mov     rax, [rbx+0A8h]
0x140010c27  mov     rcx, [rax+8]
0x140010c2b  mov     [rcx+8], edx
0x140010c2e  mov     rax, [rbx+0C0h]
0x140010c35  mov     dword ptr [rax], 53415252h
0x140010c3b  mov     rax, [rbx+20h]
0x140010c3f  mov     rcx, [rbx+0C0h]
0x140010c46  mov     eax, [rax+6Ch]
0x140010c49  mov     [rcx+4], eax
0x140010c4c  mov     ecx, r14d; Status
0x140010c4f  mov     rax, [rbx+0A8h]
0x140010c56  mov     rdx, [rbx+130h]; NdisVcHandle
0x140010c5d  mov     [rsp+0A8h+CallParameters], rax; CallParameters
0x140010c62  call    cs:__imp_NdisCmMakeCallComplete
0x140010c69  nop     dword ptr [rax+rax+00h]
0x140010c6e  test    r14d, r14d
0x140010c71  jz      loc_140010B39
0x140010c77  mov     rcx, rbx
0x140010c7a  call    InactiveCallCleanUp
0x140010c7f  jmp     short loc_140010CD3
0x140010c81  bt      ebp, 0Eh
0x140010c85  jnb     short loc_140010CC6
0x140010c87  mov     rcx, rbx
0x140010c8a  call    ReferenceCall
0x140010c8f  test    al, al
0x140010c91  jz      short loc_140010CD3
0x140010c93  mov     edx, 200000h
0x140010c98  mov     rcx, rsi
0x140010c9b  call    SetFlags
0x140010ca0  mov     rdx, [rbx+130h]; NdisVcHandle
0x140010ca7  xor     r8d, r8d; Buffer
0x140010caa  xor     r9d, r9d; Size
0x140010cad  mov     ecx, r14d; CloseStatus
0x140010cb0  call    cs:__imp_NdisCmDispatchIncomingCloseCall
0x140010cb7  nop     dword ptr [rax+rax+00h]
0x140010cbc  mov     rcx, rbx
0x140010cbf  call    DereferenceCall
0x140010cc4  jmp     short loc_140010CD3
0x140010cc6  test    r12d, r12d
0x140010cc9  jz      short loc_140010CD3
0x140010ccb  mov     rcx, rbx
0x140010cce  call    CallCleanUp
0x140010cd3  lea     rcx, [r15+20h]; SpinLock
0x140010cd7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010cde  nop     dword ptr [rax+rax+00h]
0x140010ce3  mov     rcx, rbx
0x140010ce6  mov     [r15+28h], al
0x140010cea  call    DereferenceVc
0x140010cef  jmp     loc_1400109FA
0x140010cf4  mov     ecx, 3
0x140010cf9  int     29h; Win8: RtlFailFast(ecx)
0x140010cfb  mov     rcx, [rsp+0A8h+var_58]
0x140010d00  xor     rcx, rsp; StackCookie
0x140010d03  call    __security_check_cookie
0x140010d08  add     rsp, 68h
0x140010d0c  pop     r15
0x140010d0e  pop     r14
0x140010d10  pop     r13
0x140010d12  pop     r12
0x140010d14  pop     rdi
0x140010d15  pop     rsi
0x140010d16  pop     rbp
0x140010d17  pop     rbx
0x140010d18  retn
```
