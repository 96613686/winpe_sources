# PxTapiLineGetID

- ea: `0x140013770`
- end: `0x140013bac`
- name: `PxTapiLineGetID`
- size: `1084`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001b54`
- `0x140001c0c`
- `0x140007308`
- `0x140007670`
- `0x140007940`
- `0x1400113a0`
- `0x140013770`
- `0x1400156d8`
- `0x140015a18`
- `0x140016380`
- `0x140016450`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001384c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001396b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001399f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400139bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013aa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ad2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001384c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001396b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001399f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400139bd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013a70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013aa4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013ad2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400138fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013990`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400139e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013a95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013b87`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400138fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013990`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400139e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013a95`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013b87`
- `NDIS!NdisCoGetTapiCallId` at `0x140013b32`
- `NDIS!NdisCoGetTapiCallId` at `0x140013b32`
- `NDIS!NdisCmDispatchCallConnected` at `0x140013ac3`
- `NDIS!NdisCmDispatchCallConnected` at `0x140013ac3`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400139ff`
- `NDIS!NdisCmDispatchIncomingCall` at `0x1400139ff`
- `NDIS!NdisCoCreateVc` at `0x14001391d`
- `NDIS!NdisCoCreateVc` at `0x14001391d`
- `NDIS!NdisWaitEvent` at `0x140013a1d`
- `NDIS!NdisWaitEvent` at `0x140013a1d`

## pseudocode

```c
__int64 __fastcall PxTapiLineGetID(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int v5; // ecx
  unsigned int v6; // eax
  struct _VAR_STRING *v7; // r12
  __int64 v9; // r8
  char *v10; // rbx
  KSPIN_LOCK *v11; // r15
  unsigned int v12; // edi
  __int64 v13; // r13
  __int64 v14; // rdi
  PVOID v15; // rsi
  __int64 v16; // r12
  NDIS_STATUS v17; // eax
  int v18; // r8d
  KIRQL v19; // al
  bool v20; // zf
  KIRQL v21; // al
  __int64 v22; // [rsp+30h] [rbp-10h] BYREF
  PVOID Entry; // [rsp+80h] [rbp+40h] BYREF
  PVOID NdisVcHandle; // [rsp+88h] [rbp+48h] BYREF
  struct _VAR_STRING *v25; // [rsp+90h] [rbp+50h]
  PVOID P; // [rsp+98h] [rbp+58h] BYREF

  v3 = *(unsigned int *)(a1 + 88);
  Entry = 0;
  v5 = v3 + *(_DWORD *)(a1 + 84);
  NdisVcHandle = 0;
  P = 0;
  v22 = 0;
  if ( v5 < (unsigned int)v3 )
    return 3221299225LL;
  v6 = *(_DWORD *)(a1 + 40);
  if ( v6 < v5 )
    return 3221299225LL;
  v7 = (struct _VAR_STRING *)(a1 + 92);
  v25 = (struct _VAR_STRING *)(a1 + 92);
  if ( v6 < *(_DWORD *)(a1 + 92) )
    return 3221299225LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 34, a3, *(_QWORD *)(a1 + 72));
  if ( *(_DWORD *)(a1 + 80) != 4 )
    return 3221225473LL;
  if ( (unsigned __int8)IsVcValid(*(_QWORD *)(a1 + 72), &Entry) )
  {
    v10 = (char *)Entry;
    v11 = (KSPIN_LOCK *)((char *)Entry + 512);
    v10[520] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Entry + 64);
    if ( *((_QWORD *)v10 + 8) )
    {
      v12 = 0;
    }
    else if ( *((_DWORD *)v10 + 4) == 4 )
    {
      v13 = *((_QWORD *)v10 + 11);
      v14 = v3 + a1 + 48;
      if ( (unsigned __int8)PxAfAndSapFromDevClass(v13, v14, &P, &v22) )
      {
        v15 = P;
        v16 = v22;
        *((_DWORD *)v10 + 6) = 1;
        *((_QWORD *)v10 + 10) = v15;
        *((_QWORD *)v10 + 9) = v16;
        NdisVcHandle = (PVOID)*((_QWORD *)v10 + 5);
        KeReleaseSpinLock(v11, v10[520]);
        v17 = NdisCoCreateVc(
                *(NDIS_HANDLE *)(v13 + 72),
                *((NDIS_HANDLE *)v15 + 3),
                *((NDIS_HANDLE *)v10 + 35),
                &NdisVcHandle);
        if ( v17 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            WPP_SF_qSD(
              WPP_GLOBAL_Control->AttachedDevice,
              (unsigned int)&WPP_GLOBAL_Control,
              v18,
              (_DWORD)v15,
              v14,
              v17);
          v12 = -1073741823;
          v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v15 + 11);
          *((_BYTE *)v15 + 96) = v19;
          v20 = (*((_DWORD *)v15 + 5))-- == 1;
          if ( v20 )
            DoDerefCmAfWork(v15);
          else
            KeReleaseSpinLock((PKSPIN_LOCK)v15 + 11, v19);
          v10[520] = KeAcquireSpinLockRaiseToDpc(v11);
          *((_DWORD *)v10 + 6) = 0;
        }
        else
        {
          v10[520] = KeAcquireSpinLockRaiseToDpc(v11);
          *((_QWORD *)v10 + 8) = NdisVcHandle;
          ++*((_DWORD *)v10 + 7);
          KeReleaseSpinLock(v11, v10[520]);
          v12 = NdisCmDispatchIncomingCall(
                  *(NDIS_HANDLE *)(v16 + 40),
                  *((NDIS_HANDLE *)v10 + 8),
                  *((PCO_CALL_PARAMETERS *)v10 + 39));
          if ( v12 == 259 )
          {
            NdisWaitEvent((PNDIS_EVENT)(v10 + 448), 0);
            v12 = *((_DWORD *)v10 + 118);
          }
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                38,
                WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
                v10,
                v12);
            v21 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v15 + 11);
            *((_BYTE *)v15 + 96) = v21;
            v20 = (*((_DWORD *)v15 + 5))-- == 1;
            if ( v20 )
              DoDerefCmAfWork(v15);
            else
              KeReleaseSpinLock((PKSPIN_LOCK)v15 + 11, v21);
            v10[520] = KeAcquireSpinLockRaiseToDpc(v11);
            *((_DWORD *)v10 + 6) = 0;
            --*((_DWORD *)v10 + 7);
          }
          else
          {
            NdisCmDispatchCallConnected(*((NDIS_HANDLE *)v10 + 8));
            v10[520] = KeAcquireSpinLockRaiseToDpc(v11);
            if ( *((_DWORD *)v10 + 6) == 1 )
              *((_DWORD *)v10 + 6) = 3;
          }
        }
        v7 = v25;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
        v12 = -1073741823;
      }
    }
    else
    {
      v12 = -1073668081;
    }
    if ( *((_DWORD *)v10 + 4) == 4 )
    {
      if ( !v12 )
        v12 = NdisCoGetTapiCallId(*((NDIS_HANDLE *)v10 + 8), v7);
    }
    else
    {
      if ( (unsigned int)PxCloseCallWithCl(v10) != 259 && (*((_DWORD *)v10 + 8) & 8) != 0 )
        PxCloseCallWithCm(v10);
      v12 = -1073741823;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, v10, v12);
    v20 = (*((_DWORD *)v10 + 7))-- == 1;
    if ( v20 )
      DoDerefVcWork(v10);
    else
      KeReleaseSpinLock(v11, v10[520]);
    return v12;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 35, v9, *(_QWORD *)(a1 + 72));
    return 3221299213LL;
  }
}

```

## disassembly

```asm
0x140013770  push    rbp
0x140013772  push    rbx
0x140013773  push    rsi
0x140013774  push    rdi
0x140013775  push    r12
0x140013777  push    r13
0x140013779  push    r15
0x14001377b  mov     rbp, rsp
0x14001377e  sub     rsp, 40h
0x140013782  mov     esi, [rcx+58h]
0x140013785  xor     r13d, r13d
0x140013788  mov     rdi, rcx
0x14001378b  mov     [rbp+Entry], r13
0x14001378f  mov     ecx, [rcx+54h]
0x140013792  add     ecx, esi
0x140013794  mov     [rbp+NdisVcHandle], r13
0x140013798  mov     [rbp+P], r13
0x14001379c  mov     [rbp+var_10], r13
0x1400137a0  cmp     ecx, esi
0x1400137a2  jb      loc_140013B97
0x1400137a8  mov     eax, [rdi+28h]
0x1400137ab  cmp     eax, ecx
0x1400137ad  jb      loc_140013B97
0x1400137b3  lea     r12, [rdi+5Ch]
0x1400137b7  mov     [rbp+arg_10], r12
0x1400137bb  cmp     eax, [r12]
0x1400137bf  jb      loc_140013B97
0x1400137c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137cc  lea     rbx, WPP_GLOBAL_Control
0x1400137d3  cmp     rcx, rbx
0x1400137d6  jz      short loc_1400137EF
0x1400137d8  cmp     byte ptr [rcx+29h], 4
0x1400137dc  jb      short loc_1400137EF
0x1400137de  mov     r9, [rdi+48h]
0x1400137e2  lea     edx, [r13+22h]
0x1400137e6  mov     rcx, [rcx+18h]
0x1400137ea  call    WPP_SF_P
0x1400137ef  cmp     dword ptr [rdi+50h], 4
0x1400137f3  jz      short loc_1400137FF
0x1400137f5  mov     eax, 0C0000001h
0x1400137fa  jmp     loc_140013B9C
0x1400137ff  mov     rcx, [rdi+48h]
0x140013803  lea     rdx, [rbp+Entry]
0x140013807  call    IsVcValid
0x14001380c  test    al, al
0x14001380e  jnz     short loc_14001383E
0x140013810  mov     rcx, cs:WPP_GLOBAL_Control
0x140013817  cmp     rcx, rbx
0x14001381a  jz      short loc_140013834
0x14001381c  cmp     byte ptr [rcx+29h], 3
0x140013820  jb      short loc_140013834
0x140013822  mov     r9, [rdi+48h]
0x140013826  mov     edx, 23h ; '#'
0x14001382b  mov     rcx, [rcx+18h]
0x14001382f  call    WPP_SF_P
0x140013834  mov     eax, 0C001200Dh
0x140013839  jmp     loc_140013B9C
0x14001383e  mov     rbx, [rbp+Entry]
0x140013842  lea     r15, [rbx+200h]
0x140013849  mov     rcx, r15; SpinLock
0x14001384c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013853  nop     dword ptr [rax+rax+00h]
0x140013858  mov     [rbx+208h], al
0x14001385e  cmp     [rbx+40h], r13
0x140013862  jz      short loc_14001386C
0x140013864  mov     edi, r13d
0x140013867  jmp     loc_140013AF5
0x14001386c  cmp     dword ptr [rbx+10h], 4
0x140013870  jz      short loc_14001387C
0x140013872  mov     edi, 0C001200Fh
0x140013877  jmp     loc_140013AF5
0x14001387c  mov     r13, [rbx+58h]
0x140013880  lea     r9, [rbp+var_10]
0x140013884  add     rdi, 30h ; '0'
0x140013888  lea     r8, [rbp+P]
0x14001388c  add     rdi, rsi
0x14001388f  mov     rcx, r13
0x140013892  mov     rdx, rdi
0x140013895  call    PxAfAndSapFromDevClass
0x14001389a  test    al, al
0x14001389c  jnz     short loc_1400138D6
0x14001389e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138a5  lea     rsi, WPP_GLOBAL_Control
0x1400138ac  cmp     rcx, rsi
0x1400138af  jz      short loc_1400138CC
0x1400138b1  cmp     byte ptr [rcx+29h], 3
0x1400138b5  jb      short loc_1400138CC
0x1400138b7  mov     rcx, [rcx+18h]
0x1400138bb  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400138c2  mov     edx, 24h ; '$'
0x1400138c7  call    WPP_SF_
0x1400138cc  mov     edi, 0C0000001h
0x1400138d1  jmp     loc_140013AFC
0x1400138d6  mov     rsi, [rbp+P]
0x1400138da  mov     rcx, r15; SpinLock
0x1400138dd  mov     r12, [rbp+var_10]
0x1400138e1  mov     dword ptr [rbx+18h], 1
0x1400138e8  mov     [rbx+50h], rsi
0x1400138ec  mov     [rbx+48h], r12
0x1400138f0  mov     rax, [rbx+28h]
0x1400138f4  mov     [rbp+NdisVcHandle], rax
0x1400138f8  mov     dl, [rbx+208h]; NewIrql
0x1400138fe  call    cs:__imp_KeReleaseSpinLock
0x140013905  nop     dword ptr [rax+rax+00h]
0x14001390a  mov     r8, [rbx+118h]; ProtocolVcContext
0x140013911  lea     r9, [rbp+NdisVcHandle]; NdisVcHandle
0x140013915  mov     rdx, [rsi+18h]; NdisAfHandle
0x140013919  mov     rcx, [r13+48h]; NdisBindingHandle
0x14001391d  call    cs:__imp_NdisCoCreateVc
0x140013924  nop     dword ptr [rax+rax+00h]
0x140013929  xor     r13d, r13d
0x14001392c  test    eax, eax
0x14001392e  jz      loc_1400139BA
0x140013934  mov     rcx, cs:WPP_GLOBAL_Control
0x14001393b  lea     rdx, WPP_GLOBAL_Control
0x140013942  cmp     rcx, rdx
0x140013945  jz      short loc_140013962
0x140013947  cmp     byte ptr [rcx+29h], 3
0x14001394b  jb      short loc_140013962
0x14001394d  mov     rcx, [rcx+18h]
0x140013951  mov     r9, rsi
0x140013954  mov     [rsp+40h+var_18], eax
0x140013958  mov     [rsp+40h+var_20], rdi
0x14001395d  call    WPP_SF_qSD
0x140013962  lea     rcx, [rsi+58h]; SpinLock
0x140013966  mov     edi, 0C0000001h
0x14001396b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013972  nop     dword ptr [rax+rax+00h]
0x140013977  mov     [rsi+60h], al
0x14001397a  add     dword ptr [rsi+14h], 0FFFFFFFFh
0x14001397e  jnz     short loc_14001398A
0x140013980  mov     rcx, rsi; P
0x140013983  call    DoDerefCmAfWork
0x140013988  jmp     short loc_14001399C
0x14001398a  mov     dl, al; NewIrql
0x14001398c  lea     rcx, [rsi+58h]; SpinLock
0x140013990  call    cs:__imp_KeReleaseSpinLock
0x140013997  nop     dword ptr [rax+rax+00h]
0x14001399c  mov     rcx, r15; SpinLock
0x14001399f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400139a6  nop     dword ptr [rax+rax+00h]
0x1400139ab  mov     [rbx+208h], al
0x1400139b1  mov     [rbx+18h], r13d
0x1400139b5  jmp     loc_140013AF1
0x1400139ba  mov     rcx, r15; SpinLock
0x1400139bd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400139c4  nop     dword ptr [rax+rax+00h]
0x1400139c9  mov     [rbx+208h], al
0x1400139cf  mov     rcx, r15; SpinLock
0x1400139d2  mov     rax, [rbp+NdisVcHandle]
0x1400139d6  mov     [rbx+40h], rax
0x1400139da  inc     dword ptr [rbx+1Ch]
0x1400139dd  mov     dl, [rbx+208h]; NewIrql
0x1400139e3  call    cs:__imp_KeReleaseSpinLock
0x1400139ea  nop     dword ptr [rax+rax+00h]
0x1400139ef  mov     r8, [rbx+138h]; CallParameters
0x1400139f6  mov     rdx, [rbx+40h]; NdisVcHandle
0x1400139fa  mov     rcx, [r12+28h]; NdisSapHandle
0x1400139ff  call    cs:__imp_NdisCmDispatchIncomingCall
0x140013a06  nop     dword ptr [rax+rax+00h]
0x140013a0b  mov     edi, eax
0x140013a0d  cmp     eax, 103h
0x140013a12  jnz     short loc_140013A2F
0x140013a14  lea     rcx, [rbx+1C0h]; Event
0x140013a1b  xor     edx, edx; MsToWait
0x140013a1d  call    cs:__imp_NdisWaitEvent
0x140013a24  nop     dword ptr [rax+rax+00h]
0x140013a29  mov     edi, [rbx+1D8h]
0x140013a2f  test    edi, edi
0x140013a31  jz      loc_140013ABF
0x140013a37  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a3e  lea     rdx, WPP_GLOBAL_Control
0x140013a45  cmp     rcx, rdx
0x140013a48  jz      short loc_140013A6C
0x140013a4a  cmp     byte ptr [rcx+29h], 3
0x140013a4e  jb      short loc_140013A6C
0x140013a50  mov     rcx, [rcx+18h]
0x140013a54  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013a5b  mov     edx, 26h ; '&'
0x140013a60  mov     dword ptr [rsp+40h+var_20], edi
0x140013a64  mov     r9, rbx
0x140013a67  call    WPP_SF_qD
0x140013a6c  lea     rcx, [rsi+58h]; SpinLock
0x140013a70  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013a77  nop     dword ptr [rax+rax+00h]
0x140013a7c  mov     [rsi+60h], al
0x140013a7f  add     dword ptr [rsi+14h], 0FFFFFFFFh
0x140013a83  jnz     short loc_140013A8F
0x140013a85  mov     rcx, rsi; P
0x140013a88  call    DoDerefCmAfWork
0x140013a8d  jmp     short loc_140013AA1
0x140013a8f  mov     dl, al; NewIrql
0x140013a91  lea     rcx, [rsi+58h]; SpinLock
0x140013a95  call    cs:__imp_KeReleaseSpinLock
0x140013a9c  nop     dword ptr [rax+rax+00h]
0x140013aa1  mov     rcx, r15; SpinLock
0x140013aa4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013aab  nop     dword ptr [rax+rax+00h]
0x140013ab0  mov     [rbx+208h], al
0x140013ab6  mov     [rbx+18h], r13d
0x140013aba  dec     dword ptr [rbx+1Ch]
0x140013abd  jmp     short loc_140013AF1
0x140013abf  mov     rcx, [rbx+40h]; NdisVcHandle
0x140013ac3  call    cs:__imp_NdisCmDispatchCallConnected
0x140013aca  nop     dword ptr [rax+rax+00h]
0x140013acf  mov     rcx, r15; SpinLock
0x140013ad2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013ad9  nop     dword ptr [rax+rax+00h]
0x140013ade  mov     [rbx+208h], al
0x140013ae4  cmp     dword ptr [rbx+18h], 1
0x140013ae8  jnz     short loc_140013AF1
0x140013aea  mov     dword ptr [rbx+18h], 3
0x140013af1  mov     r12, [rbp+arg_10]
0x140013af5  lea     rsi, WPP_GLOBAL_Control
0x140013afc  cmp     dword ptr [rbx+10h], 4
0x140013b00  jz      short loc_140013B27
0x140013b02  mov     rcx, rbx
0x140013b05  call    PxCloseCallWithCl
0x140013b0a  cmp     eax, 103h
0x140013b0f  jz      short loc_140013B20
0x140013b11  mov     eax, [rbx+20h]
0x140013b14  test    al, 8
0x140013b16  jz      short loc_140013B20
0x140013b18  mov     rcx, rbx
0x140013b1b  call    PxCloseCallWithCm
0x140013b20  mov     edi, 0C0000001h
0x140013b25  jmp     short loc_140013B40
0x140013b27  test    edi, edi
0x140013b29  jnz     short loc_140013B40
0x140013b2b  mov     rcx, [rbx+40h]; NdisVcHandle
0x140013b2f  mov     rdx, r12; TapiCallId
0x140013b32  call    cs:__imp_NdisCoGetTapiCallId
0x140013b39  nop     dword ptr [rax+rax+00h]
0x140013b3e  mov     edi, eax
0x140013b40  mov     rcx, cs:WPP_GLOBAL_Control
0x140013b47  cmp     rcx, rsi
0x140013b4a  jz      short loc_140013B6E
0x140013b4c  cmp     byte ptr [rcx+29h], 5
0x140013b50  jb      short loc_140013B6E
0x140013b52  mov     rcx, [rcx+18h]
0x140013b56  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140013b5d  mov     edx, 27h ; '''
0x140013b62  mov     dword ptr [rsp+40h+var_20], edi
0x140013b66  mov     r9, rbx
0x140013b69  call    WPP_SF_qD
0x140013b6e  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x140013b72  jnz     short loc_140013B7E
0x140013b74  mov     rcx, rbx; Entry
0x140013b77  call    DoDerefVcWork
0x140013b7c  jmp     short loc_140013B93
0x140013b7e  mov     dl, [rbx+208h]; NewIrql
0x140013b84  mov     rcx, r15; SpinLock
0x140013b87  call    cs:__imp_KeReleaseSpinLock
0x140013b8e  nop     dword ptr [rax+rax+00h]
0x140013b93  mov     eax, edi
0x140013b95  jmp     short loc_140013B9C
0x140013b97  mov     eax, 0C0012019h
0x140013b9c  add     rsp, 40h
0x140013ba0  pop     r15
0x140013ba2  pop     r13
0x140013ba4  pop     r12
0x140013ba6  pop     rdi
0x140013ba7  pop     rsi
0x140013ba8  pop     rbx
0x140013ba9  pop     rbp
0x140013baa  retn
```
