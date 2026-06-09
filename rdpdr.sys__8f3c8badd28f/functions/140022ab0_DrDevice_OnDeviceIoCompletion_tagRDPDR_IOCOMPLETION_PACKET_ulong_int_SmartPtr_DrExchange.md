# DrDevice::OnDeviceIoCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange> &)

- ea: `0x140022ab0`
- end: `0x140023024`
- name: `?OnDeviceIoCompletion@DrDevice@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHAEAV?$SmartPtr@VDrExchange@@@@@Z`
- size: `1396`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _DWORD *, RefCount *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400229b0`

## callees

- `0x1400010fc`
- `0x140001890`
- `0x14000324c`
- `0x140003704`
- `0x140006560`
- `0x1400117e0`
- `0x14001f5fc`
- `0x140022ab0`
- `0x140023030`
- `0x140024020`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140022ad7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140022ad7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022afa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022b34`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022afa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140022b34`

## pseudocode

```c
__int64 __fastcall DrDevice::OnDeviceIoCompletion(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        _DWORD *a4,
        RefCount *a5)
{
  __int64 v9; // rbx
  __int64 v10; // r10
  __int64 result; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdi
  RefCount *v15; // rcx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **); // rax
  RefCount *v18; // rcx
  __int64 v19; // r8
  RefCount *v20; // rcx
  RefCount *v21; // rcx
  RefCount *v22; // rcx
  __int64 v23; // rax
  RefCount *v24; // rcx
  __int64 v25; // rax
  RefCount *v26; // rcx
  __int64 v27; // rax
  RefCount *v28; // rcx
  __int64 v29; // rax
  RefCount *v30; // rcx
  __int64 v31; // rax
  RefCount *v32; // rcx
  __int64 v33; // rax
  RefCount *v34; // rcx
  __int64 v35; // rax
  RefCount *v36; // rcx
  __int64 v37; // rax

  ExAcquireFastMutex(&DrMutex);
  v9 = (__int64)a5;
  v10 = *(_QWORD *)(*(_QWORD *)a5 + 32LL);
  if ( v10 )
  {
    *(_DWORD *)(v10 + 24) = 1;
    ExReleaseFastMutex(&DrMutex);
    v14 = *(_QWORD *)(*(_QWORD *)v9 + 32LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_sL(
        WPP_GLOBAL_Control->AttachedDevice,
        68,
        (unsigned int)WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        0x140000000LL + 40LL * *(unsigned __int8 *)(v14 + 56) + 49600,
        a2[3]);
    if ( *(_DWORD *)(v14 + 36) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      DrDevice::DiscardBusyExchange(a1 - 24, v9);
      return 0;
    }
    else if ( *(_BYTE *)(v14 + 56) == 13 )
    {
LABEL_7:
      v15 = *(RefCount **)v9;
      v16 = *(_QWORD *)(a1 - 24);
      a5 = v15;
      v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v16 + 224);
      if ( v15 )
        RefCount::AddRef(v15);
      return v17(a1 - 24, a2, a3, a4, &a5);
    }
    else
    {
      switch ( *(_BYTE *)(v14 + 56) )
      {
        case 0:
          v20 = *(RefCount **)v9;
          a5 = v20;
          if ( v20 )
            RefCount::AddRef(v20);
          return DrDevice::OnCreateCompletion((int)a1 - 24, (_DWORD)a2, a3, (_DWORD)a4, (__int64)&a5);
        case 2:
          (*(void (__fastcall **)(__int64, __int64, __int64, unsigned __int64))(*(_QWORD *)(a1 - 24) + 216LL))(
            a1 - 24,
            v12,
            v13,
            0x140000000uLL);
          goto LABEL_15;
        case 3:
          v18 = *(RefCount **)v9;
          a5 = v18;
          if ( v18 )
            RefCount::AddRef(v18);
          return DrDevice::OnReadCompletion(a1 - 24, a2, a3, a4, &a5);
        case 4:
          v21 = *(RefCount **)v9;
          a5 = v21;
          if ( v21 )
            RefCount::AddRef(v21);
          return DrDevice::OnWriteCompletion((int)a1 - 24, (_DWORD)a2, a3, (_DWORD)a4, (__int64)&a5);
        case 5:
          v30 = *(RefCount **)v9;
          v31 = *(_QWORD *)(a1 - 24);
          a5 = v30;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v31 + 264);
          if ( v30 )
            RefCount::AddRef(v30);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 6:
          v32 = *(RefCount **)v9;
          v33 = *(_QWORD *)(a1 - 24);
          a5 = v32;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v33 + 272);
          if ( v32 )
            RefCount::AddRef(v32);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0xA:
          v26 = *(RefCount **)v9;
          v27 = *(_QWORD *)(a1 - 24);
          a5 = v26;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v27 + 248);
          if ( v26 )
            RefCount::AddRef(v26);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0xB:
          v28 = *(RefCount **)v9;
          v29 = *(_QWORD *)(a1 - 24);
          a5 = v28;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v29 + 256);
          if ( v28 )
            RefCount::AddRef(v28);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0xC:
          v24 = *(RefCount **)v9;
          v25 = *(_QWORD *)(a1 - 24);
          a5 = v24;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v25 + 240);
          if ( v24 )
            RefCount::AddRef(v24);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0xE:
          goto LABEL_7;
        case 0x11:
          v22 = *(RefCount **)v9;
          v23 = *(_QWORD *)(a1 - 24);
          a5 = v22;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v23 + 232);
          if ( v22 )
            RefCount::AddRef(v22);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0x14:
          v34 = *(RefCount **)v9;
          v35 = *(_QWORD *)(a1 - 24);
          a5 = v34;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v35 + 280);
          if ( v34 )
            RefCount::AddRef(v34);
          return v17(a1 - 24, a2, a3, a4, &a5);
        case 0x15:
          v36 = *(RefCount **)v9;
          v37 = *(_QWORD *)(a1 - 24);
          a5 = v36;
          v17 = *(__int64 (__fastcall **)(__int64, unsigned int *, _QWORD, _DWORD *, RefCount **))(v37 + 288);
          if ( v36 )
            RefCount::AddRef(v36);
          return v17(a1 - 24, a2, a3, a4, &a5);
        default:
LABEL_15:
          v19 = *(_QWORD *)(v14 + 48);
          if ( v19 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_sL(
                WPP_GLOBAL_Control->AttachedDevice,
                70,
                (unsigned int)WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                0x140000000LL + 40LL * *(unsigned __int8 *)(v19 + 32) + 49600,
                *(_DWORD *)(v19 + 176));
            DrDevice::CompleteBusyExchange(a1 - 24, v9, a2[3], 0);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
            DrDevice::DiscardBusyExchange(a1 - 24, v9);
          }
          result = 0;
          break;
      }
    }
  }
  else
  {
    ExReleaseFastMutex(&DrMutex);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    *a4 = 0;
    return 3221225473LL;
  }
  return result;
}

```

## disassembly

```asm
0x140022ab0  push    rbp
0x140022ab2  push    rbx
0x140022ab3  push    rsi
0x140022ab4  push    rdi
0x140022ab5  push    r12
0x140022ab7  push    r13
0x140022ab9  push    r14
0x140022abb  push    r15
0x140022abd  mov     rbp, rsp
0x140022ac0  sub     rsp, 38h
0x140022ac4  mov     rsi, rcx
0x140022ac7  mov     r15, r9
0x140022aca  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140022ad1  mov     r12d, r8d
0x140022ad4  mov     r13, rdx
0x140022ad7  call    cs:__imp_ExAcquireFastMutex
0x140022ade  nop     dword ptr [rax+rax+00h]
0x140022ae3  mov     rbx, [rbp+arg_20]
0x140022ae7  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140022aee  mov     rax, [rbx]
0x140022af1  mov     r10, [rax+20h]
0x140022af5  test    r10, r10
0x140022af8  jnz     short loc_140022B2C
0x140022afa  call    cs:__imp_ExReleaseFastMutex
0x140022b01  nop     dword ptr [rax+rax+00h]
0x140022b06  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b0d  lea     r14, WPP_GLOBAL_Control
0x140022b14  cmp     rcx, r14
0x140022b17  jnz     loc_140023000
0x140022b1d  xor     eax, eax
0x140022b1f  mov     [r15], eax
0x140022b22  mov     eax, 0C0000001h
0x140022b27  jmp     loc_140022BAE
0x140022b2c  mov     dword ptr [r10+18h], 1
0x140022b34  call    cs:__imp_ExReleaseFastMutex
0x140022b3b  nop     dword ptr [rax+rax+00h]
0x140022b40  mov     rax, [rbx]
0x140022b43  mov     rdi, [rax+20h]
0x140022b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b4e  lea     r14, WPP_GLOBAL_Control
0x140022b55  lea     r9, cs:140000000h
0x140022b5c  cmp     rcx, r14
0x140022b5f  jnz     loc_140022E8D
0x140022b65  cmp     dword ptr [rdi+24h], 0
0x140022b69  jnz     loc_140022ED3
0x140022b6f  movzx   eax, byte ptr [rdi+38h]
0x140022b73  cmp     eax, 0Dh
0x140022b76  jnz     short loc_140022BC0
0x140022b78  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 14
0x140022b7b  mov     rax, [rsi-18h]
0x140022b7f  mov     [rbp+arg_20], rcx
0x140022b83  mov     rax, [rax+0E0h]
0x140022b8a  test    rcx, rcx
0x140022b8d  jnz     loc_140022FF6
0x140022b93  lea     rcx, [rbp+arg_20]
0x140022b97  mov     r9, r15
0x140022b9a  mov     [rsp+38h+var_18], rcx
0x140022b9f  mov     r8d, r12d
0x140022ba2  lea     rcx, [rsi-18h]
0x140022ba6  mov     rdx, r13
0x140022ba9  call    _guard_dispatch_icall
0x140022bae  add     rsp, 38h
0x140022bb2  pop     r15
0x140022bb4  pop     r14
0x140022bb6  pop     r13
0x140022bb8  pop     r12
0x140022bba  pop     rdi
0x140022bbb  pop     rsi
0x140022bbc  pop     rbx
0x140022bbd  pop     rbp
0x140022bbe  retn
0x140022bc0  cmp     eax, 15h; switch 22 cases
0x140022bc3  ja      short def_140022BD0; jumptable 0000000140022BD0 default case, cases 1,7-9,13,15,16,18,19
0x140022bc5  mov     ecx, ds:(jpt_140022BD0 - 140000000h)[r9+rax*4]
0x140022bcd  add     rcx, r9
0x140022bd0  jmp     rcx; switch jump
0x140022bd6  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 3
0x140022bd9  mov     [rbp+arg_20], rcx
0x140022bdd  test    rcx, rcx
0x140022be0  jnz     loc_140022F21
0x140022be6  lea     rax, [rbp+arg_20]
0x140022bea  mov     r9, r15
0x140022bed  lea     rcx, [rsi-18h]
0x140022bf1  mov     [rsp+38h+var_18], rax
0x140022bf6  mov     r8d, r12d
0x140022bf9  mov     rdx, r13
0x140022bfc  call    ?OnReadCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::OnReadCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)
0x140022c01  jmp     short loc_140022BAE
0x140022c03  mov     rax, [rsi-18h]; jumptable 0000000140022BD0 case 2
0x140022c07  lea     rcx, [rsi-18h]
0x140022c0b  mov     rax, [rax+0D8h]
0x140022c12  call    _guard_dispatch_icall
0x140022c17  lea     r9, cs:140000000h
0x140022c1e  mov     r8, [rdi+30h]; jumptable 0000000140022BD0 default case, cases 1,7-9,13,15,16,18,19
0x140022c22  test    r8, r8
0x140022c25  jz      loc_140022FBE
0x140022c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022c32  cmp     rcx, r14
0x140022c35  jnz     loc_140022F7B
0x140022c3b  mov     r8d, [r13+0Ch]
0x140022c3f  lea     rcx, [rsi-18h]
0x140022c43  xor     r9d, r9d
0x140022c46  mov     rdx, rbx
0x140022c49  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140022c4e  xor     eax, eax
0x140022c50  jmp     loc_140022BAE
0x140022c55  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 0
0x140022c58  mov     [rbp+arg_20], rcx
0x140022c5c  test    rcx, rcx
0x140022c5f  jnz     loc_140022F0D
0x140022c65  lea     rax, [rbp+arg_20]
0x140022c69  mov     r9, r15
0x140022c6c  lea     rcx, [rsi-18h]
0x140022c70  mov     [rsp+38h+var_18], rax
0x140022c75  mov     r8d, r12d
0x140022c78  mov     rdx, r13
0x140022c7b  call    ?OnCreateCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::OnCreateCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)
0x140022c80  jmp     loc_140022BAE
0x140022c85  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 4
0x140022c88  mov     [rbp+arg_20], rcx
0x140022c8c  test    rcx, rcx
0x140022c8f  jnz     loc_140022F17
0x140022c95  lea     rax, [rbp+arg_20]
0x140022c99  mov     r9, r15
0x140022c9c  lea     rcx, [rsi-18h]
0x140022ca0  mov     [rsp+38h+var_18], rax
0x140022ca5  mov     r8d, r12d
0x140022ca8  mov     rdx, r13
0x140022cab  call    ?OnWriteCompletion@DrDevice@@QEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::OnWriteCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)
0x140022cb0  jmp     loc_140022BAE
0x140022cb5  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 17
0x140022cb8  mov     rax, [rsi-18h]
0x140022cbc  mov     [rbp+arg_20], rcx
0x140022cc0  mov     rax, [rax+0E8h]
0x140022cc7  test    rcx, rcx
0x140022cca  jnz     loc_140022F2B
0x140022cd0  lea     rcx, [rbp+arg_20]
0x140022cd4  mov     r9, r15
0x140022cd7  mov     [rsp+38h+var_18], rcx
0x140022cdc  mov     r8d, r12d
0x140022cdf  lea     rcx, [rsi-18h]
0x140022ce3  mov     rdx, r13
0x140022ce6  call    _guard_dispatch_icall
0x140022ceb  jmp     loc_140022BAE
0x140022cf0  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 12
0x140022cf3  mov     rax, [rsi-18h]
0x140022cf7  mov     [rbp+arg_20], rcx
0x140022cfb  mov     rax, [rax+0F0h]
0x140022d02  test    rcx, rcx
0x140022d05  jnz     loc_140022F35
0x140022d0b  lea     rcx, [rbp+arg_20]
0x140022d0f  mov     r9, r15
0x140022d12  mov     [rsp+38h+var_18], rcx
0x140022d17  mov     r8d, r12d
0x140022d1a  lea     rcx, [rsi-18h]
0x140022d1e  mov     rdx, r13
0x140022d21  call    _guard_dispatch_icall
0x140022d26  jmp     loc_140022BAE
0x140022d2b  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 10
0x140022d2e  mov     rax, [rsi-18h]
0x140022d32  mov     [rbp+arg_20], rcx
0x140022d36  mov     rax, [rax+0F8h]
0x140022d3d  test    rcx, rcx
0x140022d40  jnz     loc_140022F3F
0x140022d46  lea     rcx, [rbp+arg_20]
0x140022d4a  mov     r9, r15
0x140022d4d  mov     [rsp+38h+var_18], rcx
0x140022d52  mov     r8d, r12d
0x140022d55  lea     rcx, [rsi-18h]
0x140022d59  mov     rdx, r13
0x140022d5c  call    _guard_dispatch_icall
0x140022d61  jmp     loc_140022BAE
0x140022d66  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 11
0x140022d69  mov     rax, [rsi-18h]
0x140022d6d  mov     [rbp+arg_20], rcx
0x140022d71  mov     rax, [rax+100h]
0x140022d78  test    rcx, rcx
0x140022d7b  jnz     loc_140022F49
0x140022d81  lea     rcx, [rbp+arg_20]
0x140022d85  mov     r9, r15
0x140022d88  mov     [rsp+38h+var_18], rcx
0x140022d8d  mov     r8d, r12d
0x140022d90  lea     rcx, [rsi-18h]
0x140022d94  mov     rdx, r13
0x140022d97  call    _guard_dispatch_icall
0x140022d9c  jmp     loc_140022BAE
0x140022da1  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 5
0x140022da4  mov     rax, [rsi-18h]
0x140022da8  mov     [rbp+arg_20], rcx
0x140022dac  mov     rax, [rax+108h]
0x140022db3  test    rcx, rcx
0x140022db6  jnz     loc_140022F53
0x140022dbc  lea     rcx, [rbp+arg_20]
0x140022dc0  mov     r9, r15
0x140022dc3  mov     [rsp+38h+var_18], rcx
0x140022dc8  mov     r8d, r12d
0x140022dcb  lea     rcx, [rsi-18h]
0x140022dcf  mov     rdx, r13
0x140022dd2  call    _guard_dispatch_icall
0x140022dd7  jmp     loc_140022BAE
0x140022ddc  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 6
0x140022ddf  mov     rax, [rsi-18h]
0x140022de3  mov     [rbp+arg_20], rcx
0x140022de7  mov     rax, [rax+110h]
0x140022dee  test    rcx, rcx
0x140022df1  jnz     loc_140022F5D
0x140022df7  lea     rcx, [rbp+arg_20]
0x140022dfb  mov     r9, r15
0x140022dfe  mov     [rsp+38h+var_18], rcx
0x140022e03  mov     r8d, r12d
0x140022e06  lea     rcx, [rsi-18h]
0x140022e0a  mov     rdx, r13
0x140022e0d  call    _guard_dispatch_icall
0x140022e12  jmp     loc_140022BAE
0x140022e17  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 20
0x140022e1a  mov     rax, [rsi-18h]
0x140022e1e  mov     [rbp+arg_20], rcx
0x140022e22  mov     rax, [rax+118h]
0x140022e29  test    rcx, rcx
0x140022e2c  jnz     loc_140022F67
0x140022e32  lea     rcx, [rbp+arg_20]
0x140022e36  mov     r9, r15
0x140022e39  mov     [rsp+38h+var_18], rcx
0x140022e3e  mov     r8d, r12d
0x140022e41  lea     rcx, [rsi-18h]
0x140022e45  mov     rdx, r13
0x140022e48  call    _guard_dispatch_icall
0x140022e4d  jmp     loc_140022BAE
0x140022e52  mov     rcx, [rbx]; jumptable 0000000140022BD0 case 21
0x140022e55  mov     rax, [rsi-18h]
0x140022e59  mov     [rbp+arg_20], rcx
0x140022e5d  mov     rax, [rax+120h]
0x140022e64  test    rcx, rcx
0x140022e67  jnz     loc_140022F71
0x140022e6d  lea     rcx, [rbp+arg_20]
0x140022e71  mov     r9, r15
0x140022e74  mov     [rsp+38h+var_18], rcx
0x140022e79  mov     r8d, r12d
0x140022e7c  lea     rcx, [rsi-18h]
0x140022e80  mov     rdx, r13
0x140022e83  call    _guard_dispatch_icall
0x140022e88  jmp     loc_140022BAE
0x140022e8d  cmp     byte ptr [rcx+29h], 4
0x140022e91  jb      loc_140022B65
0x140022e97  movzx   eax, byte ptr [rdi+38h]
0x140022e9b  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140022ea2  mov     rcx, [rcx+18h]
0x140022ea6  lea     rdx, [rax+rax*4]
0x140022eaa  mov     eax, [r13+0Ch]
0x140022eae  lea     r9, [r9+rdx*8]
0x140022eb2  mov     dword ptr [rsp+38h+var_18], eax
0x140022eb6  lea     r9, [r9+0C1C0h]
0x140022ebd  mov     edx, 44h ; 'D'
0x140022ec2  call    WPP_SF_sL
0x140022ec7  lea     r9, cs:140000000h
0x140022ece  jmp     loc_140022B65
0x140022ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x140022eda  cmp     rcx, r14
0x140022edd  jz      short loc_140022EFA
0x140022edf  cmp     byte ptr [rcx+29h], 4
0x140022ee3  jb      short loc_140022EFA
0x140022ee5  mov     rcx, [rcx+18h]
0x140022ee9  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x140022ef0  mov     edx, 45h ; 'E'
0x140022ef5  call    WPP_SF_
0x140022efa  lea     rcx, [rsi-18h]
0x140022efe  mov     rdx, rbx
0x140022f01  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140022f06  xor     eax, eax
0x140022f08  jmp     loc_140022BAE
0x140022f0d  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f12  jmp     loc_140022C65
0x140022f17  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f1c  jmp     loc_140022C95
0x140022f21  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f26  jmp     loc_140022BE6
0x140022f2b  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f30  jmp     loc_140022CD0
0x140022f35  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f3a  jmp     loc_140022D0B
0x140022f3f  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f44  jmp     loc_140022D46
0x140022f49  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f4e  jmp     loc_140022D81
0x140022f53  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f58  jmp     loc_140022DBC
0x140022f5d  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f62  jmp     loc_140022DF7
0x140022f67  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f6c  jmp     loc_140022E32
0x140022f71  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140022f76  jmp     loc_140022E6D
0x140022f7b  cmp     byte ptr [rcx+29h], 5
0x140022f7f  jb      loc_140022C3B
0x140022f85  movzx   eax, byte ptr [r8+20h]
0x140022f8a  mov     rcx, [rcx+18h]
0x140022f8e  lea     rdx, [rax+rax*4]
0x140022f92  mov     eax, [r8+0B0h]
0x140022f99  lea     r9, [r9+rdx*8]
0x140022f9d  mov     dword ptr [rsp+38h+var_18], eax
  ... truncated ...
```
