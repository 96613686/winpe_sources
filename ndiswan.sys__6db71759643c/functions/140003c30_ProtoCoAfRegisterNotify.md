# ProtoCoAfRegisterNotify

- ea: `0x140003c30`
- end: `0x14000408e`
- name: `ProtoCoAfRegisterNotify`
- size: `1118`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003c30`
- `0x1400048c0`
- `0x1400060f0`
- `0x14000a290`
- `0x14000a5f4`
- `0x14000a68c`
- `0x1400161f0`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140003d61`
- `ntoskrnl!KeInitializeEvent` at `0x140003ded`
- `ntoskrnl!KeInitializeEvent` at `0x140003d61`
- `ntoskrnl!KeInitializeEvent` at `0x140003ded`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f8c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003d81`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003edd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003f8c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003cc0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003cc0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003cf4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140003cf4`
- `NDIS!NdisClOpenAddressFamilyEx` at `0x140003d9c`
- `NDIS!NdisClOpenAddressFamilyEx` at `0x140003d9c`

## pseudocode

```c
void __fastcall ProtoCoAfRegisterNotify(__int64 a1, struct $0563D17F902D53081481BDEBB46755BB *a2)
{
  KIRQL v4; // al
  __int64 *i; // r8
  _DWORD *v6; // rax
  _DWORD *v7; // r14
  KIRQL v8; // dl
  __int64 v9; // r9
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  PVOID NdisAfHandle; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v16[21]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+190h] [rbp+90h] BYREF

  v14 = 0;
  NdisAfHandle = 0;
  memset(v16, 0, 0x148u);
  v17 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      57,
      WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids,
      a1,
      a2->AddressFamily);
  }
  if ( a2->AddressFamily == 2048 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    *(_BYTE *)(a1 + 512) = v4;
    for ( i = *(__int64 **)(a1 + 224); i != (__int64 *)(a1 + 224); i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 10) == a2->AddressFamily )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 504), v4);
        return;
      }
    }
    v6 = ExAllocateFromNPagedLookasideList(&AfSapVcCBList);
    v7 = v6;
    if ( v6 )
    {
      memset(v6, 0, 0x68u);
      v7[4] = 538995779;
      *((_QWORD *)v7 + 4) = a1;
      v7[10] = a2->AddressFamily;
      v7[11] = a2->MajorVersion;
      v7[12] = a2->MinorVersion;
      v7[5] = 1;
      v7[6] = 1;
      if ( !*(_DWORD *)(a1 + 448) )
        KeInitializeEvent((PRKEVENT)(a1 + 456), NotificationEvent, 0);
      v8 = *(_BYTE *)(a1 + 512);
      ++*(_DWORD *)(a1 + 448);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 504), v8);
      if ( NdisClOpenAddressFamilyEx(*(NDIS_HANDLE *)(a1 + 56), a2, v7, &NdisAfHandle) != 259 )
        ClOpenAfCompleteEx(v7);
      v16[0] = 0;
      *(_QWORD *)&v16[1] = 1;
      memset(&v16[2], 0, 296);
      *((_QWORD *)&v16[1] + 1) = a1;
      KeInitializeEvent((PRKEVENT)&v16[19], NotificationEvent, 0);
      *(_QWORD *)&v16[3] = 15466902;
      *((_QWORD *)&v16[5] + 1) = &v17;
      LODWORD(v16[5]) = 67174784;
      LODWORD(v16[6]) = 16;
      if ( (unsigned int)NdisWanSubmitNdisRequest(a1, v16) )
      {
        *(_QWORD *)(a1 + 200) = 256;
        *((_QWORD *)&v16[5] + 1) = &v14;
        *(_QWORD *)&v16[3] = 15466902;
        LODWORD(v16[5]) = 65813;
        LODWORD(v16[6]) = 4;
        if ( (unsigned int)NdisWanSubmitNdisRequest(a1, v16) || (v11 = v14) == 0 )
          v11 = 10;
        *(_DWORD *)(a1 + 172) = v11;
        DWORD1(v16[3]) = 0;
        *((_QWORD *)&v16[5] + 1) = &v14;
        LODWORD(v16[5]) = 65809;
        LODWORD(v16[6]) = 4;
        v12 = NdisWanSubmitNdisRequest(a1, v16);
        v13 = 1500;
        if ( !v12 )
          v13 = v14;
        *(_DWORD *)(a1 + 168) = v13;
      }
      else
      {
        v9 = (unsigned int)v17;
        v10 = DWORD1(v17);
        *(_QWORD *)(a1 + 200) = *((_QWORD *)&v17 + 1);
        *(_DWORD *)(a1 + 168) = v9;
        *(_DWORD *)(a1 + 172) = v10;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids, v9, v10);
        }
      }
      *(_DWORD *)(a1 + 184) = 1000;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 504), *(_BYTE *)(a1 + 512));
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids);
  }
}

```

## disassembly

```asm
0x140003c30  push    rbp
0x140003c32  push    rbx
0x140003c33  push    rdi
0x140003c34  push    r12
0x140003c36  push    r15
0x140003c38  lea     rbp, [rsp-0B0h]
0x140003c40  sub     rsp, 1B0h
0x140003c47  mov     rax, cs:__security_cookie
0x140003c4e  xor     rax, rsp
0x140003c51  mov     [rbp+0D0h+var_30], rax
0x140003c58  xor     r15d, r15d
0x140003c5b  mov     rdi, rdx
0x140003c5e  mov     rbx, rcx
0x140003c61  mov     [rsp+1D0h+var_1A0], r15d
0x140003c66  xor     edx, edx; Val
0x140003c68  mov     [rsp+1D0h+NdisAfHandle], r15
0x140003c6d  lea     rcx, [rsp+1D0h+var_190]; void *
0x140003c72  mov     r8d, 148h; Size
0x140003c78  call    memset
0x140003c7d  xorps   xmm0, xmm0
0x140003c80  movups  [rbp+0D0h+var_40], xmm0
0x140003c87  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c8e  lea     r12, WPP_GLOBAL_Control
0x140003c95  cmp     rcx, r12
0x140003c98  jz      short loc_140003CA5
0x140003c9a  mov     eax, [rcx+2Ch]
0x140003c9d  test    al, 4
0x140003c9f  jnz     loc_140003F1B
0x140003ca5  cmp     dword ptr [rdi], 800h
0x140003cab  jnz     loc_140003EEB
0x140003cb1  lea     rcx, [rbx+1F8h]; SpinLock
0x140003cb8  mov     [rsp+1D0h+arg_10], rsi
0x140003cc0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003cc7  nop     dword ptr [rax+rax+00h]
0x140003ccc  lea     rdx, [rbx+0E0h]
0x140003cd3  mov     [rbx+200h], al
0x140003cd9  mov     r8, [rdx]
0x140003cdc  cmp     r8, rdx
0x140003cdf  jnz     loc_140003ECB
0x140003ce5  lea     rcx, AfSapVcCBList; Lookaside
0x140003cec  mov     [rsp+1D0h+arg_18], r14
0x140003cf4  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140003cfb  nop     dword ptr [rax+rax+00h]
0x140003d00  mov     r14, rax
0x140003d03  test    rax, rax
0x140003d06  jz      loc_140003F50
0x140003d0c  xor     edx, edx; Val
0x140003d0e  mov     r8d, 68h ; 'h'; Size
0x140003d14  mov     rcx, rax; void *
0x140003d17  call    memset
0x140003d1c  mov     dword ptr [r14+10h], 20206C43h
0x140003d24  mov     [r14+20h], rbx
0x140003d28  mov     eax, [rdi]
0x140003d2a  mov     [r14+28h], eax
0x140003d2e  mov     eax, [rdi+4]
0x140003d31  mov     [r14+2Ch], eax
0x140003d35  mov     eax, [rdi+8]
0x140003d38  mov     [r14+30h], eax
0x140003d3c  mov     dword ptr [r14+14h], 1
0x140003d44  mov     dword ptr [r14+18h], 1
0x140003d4c  cmp     [rbx+1C0h], r15d
0x140003d53  jnz     short loc_140003D6D
0x140003d55  lea     rcx, [rbx+1C8h]; Event
0x140003d5c  xor     r8d, r8d; State
0x140003d5f  xor     edx, edx; Type
0x140003d61  call    cs:__imp_KeInitializeEvent
0x140003d68  nop     dword ptr [rax+rax+00h]
0x140003d6d  movzx   edx, byte ptr [rbx+200h]; NewIrql
0x140003d74  lea     rcx, [rbx+1F8h]; SpinLock
0x140003d7b  inc     dword ptr [rbx+1C0h]
0x140003d81  call    cs:__imp_KeReleaseSpinLock
0x140003d88  nop     dword ptr [rax+rax+00h]
0x140003d8d  mov     rcx, [rbx+38h]; NdisBindingHandle
0x140003d91  lea     r9, [rsp+1D0h+NdisAfHandle]; NdisAfHandle
0x140003d96  mov     r8, r14; ClientAfContext
0x140003d99  mov     rdx, rdi; AddressFamily
0x140003d9c  call    cs:__imp_NdisClOpenAddressFamilyEx
0x140003da3  nop     dword ptr [rax+rax+00h]
0x140003da8  cmp     eax, 103h
0x140003dad  jnz     loc_140003F9D
0x140003db3  xorps   xmm0, xmm0
0x140003db6  lea     rcx, [rsp+1D0h+var_160]; void *
0x140003dbb  xor     edx, edx; Val
0x140003dbd  mov     r8d, 118h; Size
0x140003dc3  movups  [rsp+1D0h+var_190], xmm0
0x140003dc8  call    memset
0x140003dcd  xorps   xmm0, xmm0
0x140003dd0  mov     [rsp+1D0h+var_180], 1
0x140003dd9  xor     r8d, r8d; State
0x140003ddc  movdqa  [rsp+1D0h+var_170], xmm0
0x140003de2  xor     edx, edx; Type
0x140003de4  mov     [rsp+1D0h+var_178], rbx
0x140003de9  lea     rcx, [rbp+0D0h+Event]; Event
0x140003ded  call    cs:__imp_KeInitializeEvent
0x140003df4  nop     dword ptr [rax+rax+00h]
0x140003df9  lea     rax, [rbp+0D0h+var_40]
0x140003e00  mov     [rsp+1D0h+var_160], 0EC0196h
0x140003e09  lea     rdx, [rsp+1D0h+var_190]
0x140003e0e  mov     [rbp+0D0h+var_138], rax
0x140003e12  mov     rcx, rbx
0x140003e15  mov     [rbp+0D0h+var_140], 4010180h
0x140003e1c  mov     [rbp+0D0h+var_130], 10h
0x140003e23  call    NdisWanSubmitNdisRequest
0x140003e28  test    eax, eax
0x140003e2a  jnz     loc_140003FDB
0x140003e30  mov     eax, dword ptr [rbp+0D0h+var_40+8]
0x140003e36  mov     r9d, dword ptr [rbp+0D0h+var_40]
0x140003e3d  mov     r8d, dword ptr [rbp+0D0h+var_40+4]
0x140003e44  mov     [rbx+0C8h], eax
0x140003e4a  mov     eax, dword ptr [rbp+0D0h+var_40+0Ch]
0x140003e50  mov     [rbx+0CCh], eax
0x140003e56  mov     [rbx+0A8h], r9d
0x140003e5d  mov     [rbx+0ACh], r8d
0x140003e64  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e6b  cmp     rcx, r12
0x140003e6e  jz      short loc_140003E7B
0x140003e70  mov     eax, [rcx+2Ch]
0x140003e73  test    al, 4
0x140003e75  jnz     loc_140003FB2
0x140003e7b  mov     dword ptr [rbx+0B8h], 3E8h
0x140003e85  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e8c  cmp     rcx, r12
0x140003e8f  jz      short loc_140003E9C
0x140003e91  mov     eax, [rcx+2Ch]
0x140003e94  test    al, 4
0x140003e96  jnz     loc_14000406A
0x140003e9c  mov     r14, [rsp+1D0h+arg_18]
0x140003ea4  mov     rsi, [rsp+1D0h+arg_10]
0x140003eac  mov     rcx, [rbp+0D0h+var_30]
0x140003eb3  xor     rcx, rsp; StackCookie
0x140003eb6  call    __security_check_cookie
0x140003ebb  add     rsp, 1B0h
0x140003ec2  pop     r15
0x140003ec4  pop     r12
0x140003ec6  pop     rdi
0x140003ec7  pop     rbx
0x140003ec8  pop     rbp
0x140003ec9  retn
0x140003ecb  mov     ecx, [rdi]
0x140003ecd  cmp     [r8+28h], ecx
0x140003ed1  jnz     short loc_140003F48
0x140003ed3  movzx   edx, al; NewIrql
0x140003ed6  lea     rcx, [rbx+1F8h]; SpinLock
0x140003edd  call    cs:__imp_KeReleaseSpinLock
0x140003ee4  nop     dword ptr [rax+rax+00h]
0x140003ee9  jmp     short loc_140003EA4
0x140003eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ef2  cmp     rcx, r12
0x140003ef5  jz      short loc_140003EAC
0x140003ef7  mov     eax, [rcx+2Ch]
0x140003efa  test    al, 4
0x140003efc  jz      short loc_140003EAC
0x140003efe  cmp     byte ptr [rcx+29h], 5
0x140003f02  jb      short loc_140003EAC
0x140003f04  mov     rcx, [rcx+18h]
0x140003f08  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140003f0f  mov     edx, 3Ah ; ':'
0x140003f14  call    WPP_SF_
0x140003f19  jmp     short loc_140003EAC
0x140003f1b  cmp     byte ptr [rcx+29h], 5
0x140003f1f  jb      loc_140003CA5
0x140003f25  mov     eax, [rdi]
0x140003f27  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140003f2e  mov     rcx, [rcx+18h]
0x140003f32  mov     edx, 39h ; '9'
0x140003f37  mov     r9, rbx
0x140003f3a  mov     [rsp+1D0h+var_1B0], eax
0x140003f3e  call    WPP_SF_qD
0x140003f43  jmp     loc_140003CA5
0x140003f48  mov     r8, [r8]
0x140003f4b  jmp     loc_140003CDC
0x140003f50  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f57  cmp     rcx, r12
0x140003f5a  jz      short loc_140003F7E
0x140003f5c  mov     eax, [rcx+2Ch]
0x140003f5f  test    al, 40h
0x140003f61  jz      short loc_140003F7E
0x140003f63  cmp     byte ptr [rcx+29h], 2
0x140003f67  jb      short loc_140003F7E
0x140003f69  mov     rcx, [rcx+18h]
0x140003f6d  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x140003f74  mov     edx, 26h ; '&'
0x140003f79  call    WPP_SF_
0x140003f7e  movzx   edx, byte ptr [rbx+200h]; NewIrql
0x140003f85  lea     rcx, [rbx+1F8h]; SpinLock
0x140003f8c  call    cs:__imp_KeReleaseSpinLock
0x140003f93  nop     dword ptr [rax+rax+00h]
0x140003f98  jmp     loc_140003E9C
0x140003f9d  mov     rdx, [rsp+1D0h+NdisAfHandle]
0x140003fa2  mov     r8d, eax
0x140003fa5  mov     rcx, r14; Entry
0x140003fa8  call    ClOpenAfCompleteEx
0x140003fad  jmp     loc_140003DB3
0x140003fb2  cmp     byte ptr [rcx+29h], 5
0x140003fb6  jb      loc_140003E7B
0x140003fbc  mov     rcx, [rcx+18h]
0x140003fc0  mov     edx, 3Bh ; ';'
0x140003fc5  mov     [rsp+1D0h+var_1B0], r8d
0x140003fca  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x140003fd1  call    WPP_SF_dd
0x140003fd6  jmp     loc_140003E7B
0x140003fdb  lea     rax, [rsp+1D0h+var_1A0]
0x140003fe0  mov     qword ptr [rbx+0C8h], 100h
0x140003feb  lea     rdx, [rsp+1D0h+var_190]
0x140003ff0  mov     [rbp+0D0h+var_138], rax
0x140003ff4  mov     rcx, rbx
0x140003ff7  mov     [rsp+1D0h+var_160], 0EC0196h
0x140004000  mov     [rbp+0D0h+var_140], 10115h
0x140004007  mov     [rbp+0D0h+var_130], 4
0x14000400e  call    NdisWanSubmitNdisRequest
0x140004013  test    eax, eax
0x140004015  jnz     short loc_14000401F
0x140004017  mov     eax, [rsp+1D0h+var_1A0]
0x14000401b  test    eax, eax
0x14000401d  jnz     short loc_140004024
0x14000401f  mov     eax, 0Ah
0x140004024  mov     [rbx+0ACh], eax
0x14000402a  lea     rdx, [rsp+1D0h+var_190]
0x14000402f  lea     rax, [rsp+1D0h+var_1A0]
0x140004034  mov     dword ptr [rsp+1D0h+var_160+4], r15d
0x140004039  mov     rcx, rbx
0x14000403c  mov     [rbp+0D0h+var_138], rax
0x140004040  mov     [rbp+0D0h+var_140], 10111h
0x140004047  mov     [rbp+0D0h+var_130], 4
0x14000404e  call    NdisWanSubmitNdisRequest
0x140004053  test    eax, eax
0x140004055  mov     ecx, 5DCh
0x14000405a  cmovz   ecx, [rsp+1D0h+var_1A0]
0x14000405f  mov     [rbx+0A8h], ecx
0x140004065  jmp     loc_140003E7B
0x14000406a  cmp     byte ptr [rcx+29h], 5
0x14000406e  jb      loc_140003E9C
0x140004074  mov     rcx, [rcx+18h]
0x140004078  lea     r8, WPP_d663ca8c1ac73e1b9c5552be2829f60b_Traceguids
0x14000407f  mov     edx, 3Ch ; '<'
0x140004084  call    WPP_SF_
0x140004089  jmp     loc_140003E9C
```
