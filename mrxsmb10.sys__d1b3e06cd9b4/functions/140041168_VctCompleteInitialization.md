# VctCompleteInitialization

- ea: `0x140041168`
- end: `0x14004131e`
- name: `VctCompleteInitialization`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400153a0`

## callees

- `0x14000dfa8`
- `0x14000ebd8`
- `0x1400169c0`
- `0x140041168`
- `0x140041360`
- `0x140041668`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400411b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400411b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041304`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041304`
- `mrxsmb!RxCeGetTransportAddresses` at `0x140041190`
- `mrxsmb!RxCeGetTransportAddresses` at `0x140041190`
- `mrxsmb!RxCeQueryInformation` at `0x1400411e0`
- `mrxsmb!RxCeQueryInformation` at `0x1400411e0`
- `mrxsmb!RxCeQueryLocalAddressInformation` at `0x14004122b`
- `mrxsmb!RxCeQueryLocalAddressInformation` at `0x14004122b`

## pseudocode

```c
__int64 __fastcall VctCompleteInitialization(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  void *v6; // rdi
  int TransportAddresses; // eax
  void *Pool2; // rax
  __int64 v10; // r8
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx

  v3 = *(_DWORD *)(a3 + 320) == 1;
  *(_BYTE *)(a3 + 324) = 0;
  if ( v3 )
  {
    v6 = 0;
    TransportAddresses = RxCeGetTransportAddresses(a3);
LABEL_9:
    if ( !TransportAddresses && !(unsigned int)VctEnablePerfEstimation(a3 + 400) )
    {
      *(_BYTE *)(a3 + 324) = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids, a3);
      }
    }
    goto LABEL_21;
  }
  Pool2 = (void *)ExAllocatePool2(66, 86, 1918070099);
  v6 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  if ( RxCeQueryInformation((PRXCE_VC)a3, RxCeTransportProviderInformation, Pool2, 0x56u) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      v12 = 29;
      goto LABEL_20;
    }
  }
  else
  {
    LOBYTE(v10) = 1;
    if ( !(unsigned int)VctpGetIPAddressFromTransportBuffer(v6, a3 + 400, v10) )
    {
      memset(v6, 0, 0x56u);
      if ( !(unsigned int)RxCeQueryLocalAddressInformation(a2, *(_QWORD *)(a3 + 112), v6, 86) )
      {
        TransportAddresses = VctpGetIPAddressFromTransportBuffer(v6, a3 + 400, 0);
        goto LABEL_9;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        v12 = 28;
LABEL_20:
        WPP_SF_(v11->AttachedDevice, v12, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids);
      }
    }
  }
LABEL_21:
  *(_QWORD *)(a3 + 32) = a2;
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return 0;
}

```

## disassembly

```asm
0x140041168  push    rbx
0x14004116a  push    rbp
0x14004116b  push    rsi
0x14004116c  push    rdi
0x14004116d  push    r14
0x14004116f  sub     rsp, 20h
0x140041173  cmp     dword ptr [r8+140h], 1
0x14004117b  mov     rbx, r8
0x14004117e  mov     rbp, rdx
0x140041181  mov     byte ptr [r8+144h], 0
0x140041189  jnz     short loc_1400411A1
0x14004118b  xor     edi, edi
0x14004118d  mov     rcx, rbx
0x140041190  call    cs:__imp_RxCeGetTransportAddresses
0x140041197  nop     dword ptr [rax+rax+00h]
0x14004119c  jmp     loc_140041249
0x1400411a1  mov     r14d, 56h ; 'V'
0x1400411a7  mov     r8d, 72536D53h
0x1400411ad  mov     edx, r14d
0x1400411b0  lea     ecx, [r14-14h]
0x1400411b4  call    cs:__imp_ExAllocatePool2
0x1400411bb  nop     dword ptr [rax+rax+00h]
0x1400411c0  mov     rdi, rax
0x1400411c3  test    rax, rax
0x1400411c6  jnz     short loc_1400411D2
0x1400411c8  mov     eax, 0C000009Ah
0x1400411cd  jmp     loc_140041312
0x1400411d2  mov     r9d, r14d; Length
0x1400411d5  mov     r8, rdi; pInformation
0x1400411d8  mov     edx, 1; InformationClass
0x1400411dd  mov     rcx, rbx; pVc
0x1400411e0  call    cs:__imp_RxCeQueryInformation
0x1400411e7  nop     dword ptr [rax+rax+00h]
0x1400411ec  test    eax, eax
0x1400411ee  jnz     loc_1400412C5
0x1400411f4  lea     rsi, [rbx+190h]
0x1400411fb  mov     r8b, 1
0x1400411fe  mov     rdx, rsi
0x140041201  mov     rcx, rdi
0x140041204  call    VctpGetIPAddressFromTransportBuffer
0x140041209  test    eax, eax
0x14004120b  jnz     loc_1400412F6
0x140041211  mov     r8, r14; Size
0x140041214  xor     edx, edx; Val
0x140041216  mov     rcx, rdi; void *
0x140041219  call    memset
0x14004121e  mov     rdx, [rbx+70h]
0x140041222  mov     r9d, r14d
0x140041225  mov     r8, rdi
0x140041228  mov     rcx, rbp
0x14004122b  call    cs:__imp_RxCeQueryLocalAddressInformation
0x140041232  nop     dword ptr [rax+rax+00h]
0x140041237  test    eax, eax
0x140041239  jnz     short loc_1400412A2
0x14004123b  xor     r8d, r8d
0x14004123e  mov     rdx, rsi
0x140041241  mov     rcx, rdi
0x140041244  call    VctpGetIPAddressFromTransportBuffer
0x140041249  test    eax, eax
0x14004124b  jnz     loc_1400412F6
0x140041251  lea     rcx, [rbx+190h]
0x140041258  call    VctEnablePerfEstimation
0x14004125d  test    eax, eax
0x14004125f  jnz     loc_1400412F6
0x140041265  mov     byte ptr [rbx+144h], 1
0x14004126c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140041273  lea     rax, WPP_GLOBAL_Control
0x14004127a  cmp     rcx, rax
0x14004127d  jz      short loc_1400412F6
0x14004127f  test    dword ptr [rcx+2Ch], 400h
0x140041286  jz      short loc_1400412F6
0x140041288  mov     rcx, [rcx+18h]
0x14004128c  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x140041293  mov     edx, 1Eh
0x140041298  mov     r9, rbx
0x14004129b  call    WPP_SF_q
0x1400412a0  jmp     short loc_1400412F6
0x1400412a2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400412a9  lea     rax, WPP_GLOBAL_Control
0x1400412b0  cmp     rcx, rax
0x1400412b3  jz      short loc_1400412F6
0x1400412b5  test    dword ptr [rcx+2Ch], 400h
0x1400412bc  jz      short loc_1400412F6
0x1400412be  mov     edx, 1Ch
0x1400412c3  jmp     short loc_1400412E6
0x1400412c5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400412cc  lea     rax, WPP_GLOBAL_Control
0x1400412d3  cmp     rcx, rax
0x1400412d6  jz      short loc_1400412F6
0x1400412d8  test    dword ptr [rcx+2Ch], 400h
0x1400412df  jz      short loc_1400412F6
0x1400412e1  mov     edx, 1Dh
0x1400412e6  mov     rcx, [rcx+18h]
0x1400412ea  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x1400412f1  call    WPP_SF_
0x1400412f6  mov     [rbx+20h], rbp
0x1400412fa  test    rdi, rdi
0x1400412fd  jz      short loc_140041310
0x1400412ff  xor     edx, edx; Tag
0x140041301  mov     rcx, rdi; P
0x140041304  call    cs:__imp_ExFreePoolWithTag
0x14004130b  nop     dword ptr [rax+rax+00h]
0x140041310  xor     eax, eax
0x140041312  add     rsp, 20h
0x140041316  pop     r14
0x140041318  pop     rdi
0x140041319  pop     rsi
0x14004131a  pop     rbp
0x14004131b  pop     rbx
0x14004131c  retn
```
