# SmbWskBufferedMessageReceiveComplete

- ea: `0x140012650`
- end: `0x140012830`
- name: `SmbWskBufferedMessageReceiveComplete`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140012650`
- `0x140013470`
- `0x1400137f0`
- `0x140017798`
- `0x1400215b0`
- `0x140054f68`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400126bc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400126bc`
- `rdbss!RxCeFreeIrp` at `0x140012802`
- `rdbss!RxCeFreeIrp` at `0x140012802`
- `rdbss!RxFreeMdl` at `0x140012764`
- `rdbss!RxFreeMdl` at `0x140012764`

## pseudocode

```c
__int64 __fastcall SmbWskBufferedMessageReceiveComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rsi
  unsigned int v5; // ebp
  int v7; // ebx
  int v9; // r12d
  _DWORD *v10; // r15
  int v11; // ecx
  _OWORD v13[3]; // [rsp+50h] [rbp-68h] BYREF
  __int64 v14; // [rsp+80h] [rbp-38h]
  __int64 v15; // [rsp+C8h] [rbp+10h]

  v3 = *(_QWORD *)(a3 + 16);
  v4 = *(_QWORD *)a3;
  v5 = *(_DWORD *)(a2 + 56);
  v7 = *(_DWORD *)(a2 + 48);
  memset(v13, 0, sizeof(v13));
  v9 = 410;
  v14 = 0;
  if ( (*(_BYTE *)(v3 + 10) & 5) != 0 )
    v10 = *(_DWORD **)(v3 + 24);
  else
    v10 = MmMapLockedPagesSpecifyCache((PMDL)v3, 0, MmCached, 0, 0, 0x40000000u);
  if ( v7 == -1073741643 || v7 >= 0 && v5 < *(_DWORD *)(a3 + 8) )
    v7 = -1073741300;
  v11 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqqDD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, v4, a2, *(_QWORD *)(a3 + 16), v5, v7);
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 0x40) != 0 )
    McTemplateK0pppqqq_EtwWriteTransfer(
      v11,
      (unsigned int)NetReceiveCompletionV2,
      a3,
      v4,
      *(_QWORD *)(v4 + 104),
      *(_QWORD *)(a3 + 16),
      v5,
      v7,
      1);
  RxFreeMdl(*(_QWORD *)(a3 + 16));
  *(_QWORD *)(a3 + 16) = 0;
  if ( v7 < 0
    || (LODWORD(v13[0]) |= 0x400u,
        BYTE4(v14) |= 2u,
        DWORD1(v13[0]) = v5,
        v9 = 409,
        (int)SmbWskIndicateFullMessageToRdr(v4, v10, v5, (__int64)v13) < 0) )
  {
    if ( (unsigned int)VctSetEndpointState(v4, 1, 0) != 1 )
    {
      LODWORD(v15) = -1073741300;
      HIDWORD(v15) = v9;
      (**(void (__fastcall ***)(__int64, __int64))(v4 + 392))(v4, v15);
    }
  }
  VctDereferenceEndpoint((PVOID)v4);
  ++*(_BYTE *)(a2 + 67);
  *(_QWORD *)(a2 + 184) += 72LL;
  RxCeFreeIrp((PIRP)a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140012650  mov     r11, rsp
0x140012653  mov     [r11+8], rbx
0x140012657  mov     [r11+18h], rbp
0x14001265b  push    rsi
0x14001265c  push    rdi
0x14001265d  push    r12
0x14001265f  push    r14
0x140012661  push    r15
0x140012663  sub     rsp, 90h
0x14001266a  mov     rcx, [r8+10h]; MemoryDescriptorList
0x14001266e  xorps   xmm0, xmm0
0x140012671  mov     rsi, [r8]
0x140012674  xor     eax, eax
0x140012676  mov     ebp, [rdx+38h]
0x140012679  mov     r14, r8
0x14001267c  mov     ebx, [rdx+30h]
0x14001267f  mov     rdi, rdx
0x140012682  movups  [rsp+0B8h+var_68], xmm0
0x140012687  mov     r12d, 19Ah
0x14001268d  movups  [rsp+0B8h+var_58], xmm0
0x140012692  movups  [rsp+0B8h+var_48], xmm0
0x140012697  mov     [r11-38h], rax
0x14001269b  test    byte ptr [rcx+0Ah], 5
0x14001269f  jz      short loc_1400126A7
0x1400126a1  mov     r15, [rcx+18h]
0x1400126a5  jmp     short loc_1400126CB
0x1400126a7  xor     r9d, r9d; RequestedAddress
0x1400126aa  mov     [rsp+0B8h+Priority], 40000000h; Priority
0x1400126b2  xor     edx, edx; AccessMode
0x1400126b4  mov     [rsp+0B8h+BugCheckOnFailure], eax; BugCheckOnFailure
0x1400126b8  lea     r8d, [r9+1]; CacheType
0x1400126bc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400126c3  nop     dword ptr [rax+rax+00h]
0x1400126c8  mov     r15, rax
0x1400126cb  mov     eax, 0C000020Ch
0x1400126d0  cmp     ebx, 0C00000B5h
0x1400126d6  jz      short loc_1400126E2
0x1400126d8  test    ebx, ebx
0x1400126da  js      short loc_1400126E4
0x1400126dc  cmp     ebp, [r14+8]
0x1400126e0  jnb     short loc_1400126E4
0x1400126e2  mov     ebx, eax
0x1400126e4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400126eb  lea     rax, WPP_GLOBAL_Control
0x1400126f2  cmp     rcx, rax
0x1400126f5  jz      short loc_140012726
0x1400126f7  mov     eax, [rcx+2Ch]
0x1400126fa  test    al, 4
0x1400126fc  jz      short loc_140012726
0x1400126fe  cmp     byte ptr [rcx+29h], 4
0x140012702  jb      short loc_140012726
0x140012704  mov     rax, [r14+10h]
0x140012708  mov     r9, rsi
0x14001270b  mov     rcx, [rcx+18h]
0x14001270f  mov     [rsp+0B8h+var_80], ebx
0x140012713  mov     [rsp+0B8h+var_88], ebp
0x140012717  mov     qword ptr [rsp+0B8h+Priority], rax
0x14001271c  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rdi
0x140012721  call    WPP_SF_qqqDD
0x140012726  test    cs:Microsoft_Windows_SMBClientEnableBits, 40h
0x14001272d  jz      short loc_140012760
0x14001272f  mov     rax, [r14+10h]
0x140012733  lea     rdx, NetReceiveCompletionV2
0x14001273a  mov     [rsp+0B8h+var_78], 1
0x140012742  mov     r9, rsi
0x140012745  mov     [rsp+0B8h+var_80], ebx
0x140012749  mov     [rsp+0B8h+var_88], ebp
0x14001274d  mov     qword ptr [rsp+0B8h+Priority], rax
0x140012752  mov     rax, [rsi+68h]
0x140012756  mov     qword ptr [rsp+0B8h+BugCheckOnFailure], rax
0x14001275b  call    McTemplateK0pppqqq_EtwWriteTransfer
0x140012760  mov     rcx, [r14+10h]
0x140012764  call    cs:__imp_RxFreeMdl
0x14001276b  nop     dword ptr [rax+rax+00h]
0x140012770  mov     qword ptr [r14+10h], 0
0x140012778  test    ebx, ebx
0x14001277a  js      short loc_1400127AB
0x14001277c  bts     dword ptr [rsp+0B8h+var_68], 0Ah
0x140012782  lea     r9, [rsp+0B8h+var_68]
0x140012787  or      [rsp+0B8h+var_34], 2
0x14001278f  mov     r8d, ebp
0x140012792  mov     rdx, r15
0x140012795  mov     dword ptr [rsp+0B8h+var_68+4], ebp
0x140012799  mov     rcx, rsi
0x14001279c  call    SmbWskIndicateFullMessageToRdr
0x1400127a1  mov     r12d, 199h
0x1400127a7  test    eax, eax
0x1400127a9  jns     short loc_1400127EC
0x1400127ab  xor     r8d, r8d
0x1400127ae  mov     rcx, rsi
0x1400127b1  lea     edx, [r8+1]
0x1400127b5  call    VctSetEndpointState
0x1400127ba  cmp     eax, 1
0x1400127bd  jz      short loc_1400127EC
0x1400127bf  mov     rax, [rsi+188h]
0x1400127c6  mov     rcx, rsi
0x1400127c9  mov     dword ptr [rsp+0B8h+arg_8], 0C000020Ch
0x1400127d4  mov     dword ptr [rsp+0B8h+arg_8+4], r12d
0x1400127dc  mov     rdx, [rsp+0B8h+arg_8]
0x1400127e4  mov     rax, [rax]
0x1400127e7  call    _guard_dispatch_icall
0x1400127ec  mov     rcx, rsi; pContext
0x1400127ef  call    VctDereferenceEndpoint
0x1400127f4  inc     byte ptr [rdi+43h]
0x1400127f7  mov     rcx, rdi; pIrp
0x1400127fa  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140012802  call    cs:__imp_RxCeFreeIrp
0x140012809  nop     dword ptr [rax+rax+00h]
0x14001280e  lea     r11, [rsp+0B8h+var_28]
0x140012816  mov     eax, 0C0000016h
0x14001281b  mov     rbx, [r11+30h]
0x14001281f  mov     rbp, [r11+40h]
0x140012823  mov     rsp, r11
0x140012826  pop     r15
0x140012828  pop     r14
0x14001282a  pop     r12
0x14001282c  pop     rdi
0x14001282d  pop     rsi
0x14001282e  retn
```
