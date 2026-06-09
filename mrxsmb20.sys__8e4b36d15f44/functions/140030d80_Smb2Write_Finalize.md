# Smb2Write_Finalize

- ea: `0x140030d80`
- end: `0x14003116b`
- name: `Smb2Write_Finalize`
- size: `1003`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000fa00`
- `0x140013b30`
- `0x14002ba20`
- `0x140030d80`
- `0x140036950`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400310b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030f04`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400310b0`
- `ntoskrnl!IoFreeMdl` at `0x14003108f`
- `ntoskrnl!IoFreeMdl` at `0x14003108f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030e69`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140030e69`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x140030eeb`
- `rdbss!RxUnlockAndFreeMdlChain` at `0x140030eeb`
- `rdbss!RxLowIoCompletion` at `0x140031054`
- `rdbss!RxLowIoCompletion` at `0x14003110f`
- `rdbss!RxLowIoCompletion` at `0x140031054`
- `rdbss!RxLowIoCompletion` at `0x14003110f`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14003113d`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14003113d`
- `mrxsmb!RDR_PERF_ENTER` at `0x140030dc7`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031045`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031065`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031100`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031120`
- `mrxsmb!RDR_PERF_ENTER` at `0x140030dc7`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031045`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031065`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031100`
- `mrxsmb!RDR_PERF_ENTER` at `0x140031120`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140030ed3`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140030ed3`

## pseudocode

```c
__int64 __fastcall Smb2Write_Finalize(__int64 a1)
{
  __int64 v1; // rax
  __int64 v2; // rbp
  struct _RX_CONTEXT *v3; // r14
  int v5; // esi
  __int64 v6; // rdx
  unsigned int v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdi
  char v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rbp
  __int64 v15; // rcx
  bool v16; // zf
  PVOID v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  PIRP CurrentIrp; // rcx
  _BYTE *v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int i; // edi
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v31; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v32; // [rsp+78h] [rbp+10h]
  _BYTE *v33; // [rsp+80h] [rbp+18h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v2 = a1 + 512;
  v3 = *(struct _RX_CONTEXT **)(a1 + 48);
  v5 = *(_DWORD *)(a1 + 16);
  v32 = 0;
  v6 = *(_QWORD *)(v1 + 24);
  v7 = 0;
  LOBYTE(v1) = *(_BYTE *)(v6 + 1313);
  LOBYTE(v6) = 18;
  LOBYTE(v31) = v1;
  RDR_PERF_ENTER(a1 + 512, v6);
  v10 = *(_QWORD *)(a1 + 160);
  v11 = v10 - 8;
  if ( v10 == a1 + 160 )
    v11 = 0;
  if ( v11 )
  {
    v12 = v31;
    do
    {
      v13 = *(_QWORD *)(v11 + 8);
      v14 = 0;
      if ( v13 != a1 + 160 )
        v14 = v13 - 8;
      ProcessChunkAndUpdateBlockState(a1, v11, v9);
      if ( *(int *)(v11 + 48) < 0 )
      {
        if ( v12 )
        {
          v15 = *(_QWORD *)(v11 + 752);
          if ( v15 )
          {
            v16 = (*(_BYTE *)(v15 + 10) & 5) == 0;
            v33 = 0;
            v31 = 0;
            v17 = v16 ? MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u) : *(PVOID *)(v15 + 24);
            if ( (int)Smb2QueryErrorDataFromResponse(
                        (__int64)v17,
                        *(_DWORD *)(*(_QWORD *)(v11 + 752) + 40LL),
                        1164730963,
                        &v33,
                        &v31) >= 0 )
            {
              CurrentIrp = v3->CurrentIrp;
              if ( CurrentIrp )
              {
                v21 = v33;
                if ( v33 )
                {
                  if ( v31 >= 8 )
                  {
                    LOBYTE(v19) = v33[6];
                    LOBYTE(v18) = v33[5];
                    LOBYTE(v21) = v33[4];
                    StRtlIoStorInfoSetSenseCode(CurrentIrp, v21, v18, v19);
                  }
                }
              }
            }
          }
        }
      }
      SmbCseFinalizeBufferContext(v11);
      v22 = *(_QWORD *)(v11 + 1400);
      if ( v22 )
        RxUnlockAndFreeMdlChain(v22);
      if ( v11 == a1 + 1064 )
        *(_BYTE *)(a1 + 1056) = 0;
      else
        ExFreePoolWithTag((PVOID)v11, 0x6D536357u);
      v11 = v14;
    }
    while ( v14 );
    v7 = v32;
    v2 = a1 + 512;
  }
  if ( v5 >= 0 )
  {
    v23 = *(_DWORD *)(a1 + 1052);
    if ( v23 )
    {
      v24 = 0;
      while ( 1 )
      {
        v8 = *(unsigned int *)(a1 + 8LL * v24 + 2528);
        if ( (_DWORD)v8 == -1 )
          break;
        v5 = *(_DWORD *)(a1 + 8LL * v24 + 2528);
        if ( (int)v8 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_DDq(
              WPP_GLOBAL_Control->AttachedDevice,
              25,
              WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids,
              (unsigned int)v8,
              v24,
              a1);
          }
          break;
        }
        v7 += *(_DWORD *)(a1 + 8LL * v24 + 2532);
        if ( *(_BYTE *)(a1 + 1048) != 1 && ++v24 < v23 )
          continue;
        break;
      }
    }
  }
  if ( *(_QWORD *)(a1 + 2488) )
  {
    if ( !*(_QWORD *)(a1 + 2496) || !*(_QWORD *)(a1 + 2504) || !*(_QWORD *)(a1 + 2512) )
      __int2c();
    for ( i = 0; i < *(_DWORD *)(a1 + 2520); ++i )
    {
      v26 = 2LL * i;
      *(_DWORD *)(*(_QWORD *)(a1 + 2504) + 8 * v26) = v5;
      *(_DWORD *)(*(_QWORD *)(a1 + 2504) + 8 * v26 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 2496) + 16LL * i + 12);
      *(_QWORD *)(*(_QWORD *)(a1 + 2504) + 8 * v26 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 2496) + 16LL * i);
      if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 2512), 0xFFFFFFFF) == 1 )
      {
        LOBYTE(v26) = 22;
        RDR_PERF_ENTER(v2, v26);
        RxLowIoCompletion(v3);
        LOBYTE(v27) = 23;
        RDR_PERF_ENTER(v2, v27);
      }
    }
    if ( *(_BYTE *)(a1 + 2524) )
      IoFreeMdl(*(PMDL *)(a1 + 2488));
    if ( *(_BYTE *)(a1 + 2525) )
      ExFreePoolWithTag(*(PVOID *)(a1 + 2496), 0x77427852u);
    *(_QWORD *)(a1 + 2488) = 0;
    *(_QWORD *)(a1 + 2496) = 0;
    *(_QWORD *)(a1 + 2504) = 0;
    *(_QWORD *)(a1 + 2512) = 0;
    *(_DWORD *)(a1 + 2520) = 0;
    *(_WORD *)(a1 + 2524) = 0;
  }
  else
  {
    LOBYTE(v8) = 22;
    v3->InformationToReturn = v7;
    v3->StoredStatus = v5;
    RDR_PERF_ENTER(v2, v8);
    RxLowIoCompletion(v3);
    LOBYTE(v28) = 23;
    RDR_PERF_ENTER(v2, v28);
  }
  v29 = *(_QWORD *)(a1 + 1040);
  if ( v29 )
  {
    SmbMmFreeSmbBuffer(v29, 1834185559);
    *(_QWORD *)(a1 + 1040) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140030d80  mov     [rsp+arg_18], rbx
0x140030d85  push    rbp
0x140030d86  push    rsi
0x140030d87  push    rdi
0x140030d88  push    r12
0x140030d8a  push    r13
0x140030d8c  push    r14
0x140030d8e  push    r15
0x140030d90  sub     rsp, 30h
0x140030d94  mov     rax, [rcx+48h]
0x140030d98  lea     rbp, [rcx+200h]
0x140030d9f  mov     r14, [rcx+30h]
0x140030da3  mov     rbx, rcx
0x140030da6  mov     esi, [rcx+10h]
0x140030da9  xor     r13d, r13d
0x140030dac  mov     rcx, rbp
0x140030daf  mov     [rsp+68h+arg_8], r13d
0x140030db4  mov     rdx, [rax+18h]
0x140030db8  mov     r15d, r13d
0x140030dbb  mov     al, [rdx+521h]
0x140030dc1  mov     dl, 12h
0x140030dc3  mov     byte ptr [rsp+68h+arg_0], al
0x140030dc7  call    cs:__imp_RDR_PERF_ENTER
0x140030dce  nop     dword ptr [rax+rax+00h]
0x140030dd3  lea     r12, [rbx+0A0h]
0x140030dda  mov     rcx, [r12]
0x140030dde  cmp     rcx, r12
0x140030de1  lea     rdi, [rcx-8]
0x140030de5  cmovz   rdi, r13
0x140030de9  test    rdi, rdi
0x140030dec  jz      loc_140030F34
0x140030df2  mov     r15b, byte ptr [rsp+68h+arg_0]
0x140030df7  lea     r13, [rbx+428h]
0x140030dfe  mov     rcx, [rdi+8]
0x140030e02  xor     ebp, ebp
0x140030e04  cmp     rcx, r12
0x140030e07  mov     rdx, rdi
0x140030e0a  lea     rax, [rcx-8]
0x140030e0e  mov     rcx, rbx
0x140030e11  cmovnz  rbp, rax
0x140030e15  call    ProcessChunkAndUpdateBlockState
0x140030e1a  xor     edx, edx; AccessMode
0x140030e1c  cmp     [rdi+30h], edx
0x140030e1f  jge     loc_140030ED0
0x140030e25  test    r15b, r15b
0x140030e28  jz      loc_140030ED0
0x140030e2e  mov     rcx, [rdi+2F0h]; MemoryDescriptorList
0x140030e35  test    rcx, rcx
0x140030e38  jz      loc_140030ED0
0x140030e3e  test    byte ptr [rcx+0Ah], 5
0x140030e42  mov     [rsp+68h+arg_10], rdx
0x140030e4a  mov     [rsp+68h+arg_0], edx
0x140030e4e  jz      short loc_140030E56
0x140030e50  mov     rax, [rcx+18h]
0x140030e54  jmp     short loc_140030E75
0x140030e56  xor     r9d, r9d; RequestedAddress
0x140030e59  mov     [rsp+68h+Priority], 40000010h; Priority
0x140030e61  mov     [rsp+68h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140030e65  lea     r8d, [r9+1]; CacheType
0x140030e69  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140030e70  nop     dword ptr [rax+rax+00h]
0x140030e75  mov     rdx, [rdi+2F0h]
0x140030e7c  lea     rcx, [rsp+68h+arg_0]
0x140030e81  mov     qword ptr [rsp+68h+BugCheckOnFailure], rcx
0x140030e86  lea     r9, [rsp+68h+arg_10]
0x140030e8e  mov     r8d, 456C6253h
0x140030e94  mov     rcx, rax
0x140030e97  mov     edx, [rdx+28h]
0x140030e9a  call    Smb2QueryErrorDataFromResponse
0x140030e9f  test    eax, eax
0x140030ea1  js      short loc_140030ED0
0x140030ea3  mov     rcx, [r14+28h]
0x140030ea7  test    rcx, rcx
0x140030eaa  jz      short loc_140030ED0
0x140030eac  mov     rdx, [rsp+68h+arg_10]
0x140030eb4  test    rdx, rdx
0x140030eb7  jz      short loc_140030ED0
0x140030eb9  cmp     [rsp+68h+arg_0], 8
0x140030ebe  jb      short loc_140030ED0
0x140030ec0  mov     r9b, [rdx+6]
0x140030ec4  mov     r8b, [rdx+5]
0x140030ec8  mov     dl, [rdx+4]
0x140030ecb  call    StRtlIoStorInfoSetSenseCode
0x140030ed0  mov     rcx, rdi
0x140030ed3  call    cs:__imp_SmbCseFinalizeBufferContext
0x140030eda  nop     dword ptr [rax+rax+00h]
0x140030edf  mov     rcx, [rdi+578h]
0x140030ee6  test    rcx, rcx
0x140030ee9  jz      short loc_140030EF7
0x140030eeb  call    cs:__imp_RxUnlockAndFreeMdlChain
0x140030ef2  nop     dword ptr [rax+rax+00h]
0x140030ef7  cmp     rdi, r13
0x140030efa  jz      short loc_140030F12
0x140030efc  mov     edx, 6D536357h; Tag
0x140030f01  mov     rcx, rdi; P
0x140030f04  call    cs:__imp_ExFreePoolWithTag
0x140030f0b  nop     dword ptr [rax+rax+00h]
0x140030f10  jmp     short loc_140030F19
0x140030f12  mov     byte ptr [rbx+420h], 0
0x140030f19  mov     rdi, rbp
0x140030f1c  test    rbp, rbp
0x140030f1f  jnz     loc_140030DFE
0x140030f25  mov     r15d, [rsp+68h+arg_8]
0x140030f2a  lea     rbp, [rbx+200h]
0x140030f31  xor     r13d, r13d
0x140030f34  test    esi, esi
0x140030f36  js      short loc_140030FB7
0x140030f38  mov     eax, [rbx+41Ch]
0x140030f3e  test    eax, eax
0x140030f40  jz      short loc_140030FB7
0x140030f42  mov     ecx, r13d
0x140030f45  mov     r8d, ecx
0x140030f48  mov     edx, [rbx+r8*8+9E0h]
0x140030f50  cmp     edx, 0FFFFFFFFh
0x140030f53  jz      short loc_140030FB7
0x140030f55  mov     esi, edx
0x140030f57  test    edx, edx
0x140030f59  js      short loc_140030F74
0x140030f5b  add     r15d, [rbx+r8*8+9E4h]
0x140030f63  cmp     byte ptr [rbx+418h], 1
0x140030f6a  jz      short loc_140030FB7
0x140030f6c  inc     ecx
0x140030f6e  cmp     ecx, eax
0x140030f70  jb      short loc_140030F45
0x140030f72  jmp     short loc_140030FB7
0x140030f74  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140030f7b  lea     rax, WPP_GLOBAL_Control
0x140030f82  cmp     r10, rax
0x140030f85  jz      short loc_140030FB7
0x140030f87  mov     eax, [r10+2Ch]
0x140030f8b  test    al, 1
0x140030f8d  jz      short loc_140030FB7
0x140030f8f  cmp     byte ptr [r10+29h], 1
0x140030f94  jb      short loc_140030FB7
0x140030f96  mov     qword ptr [rsp+68h+Priority], rbx
0x140030f9b  lea     r8, WPP_37fe073fcb403a48ea10fb83da93c962_Traceguids
0x140030fa2  mov     [rsp+68h+BugCheckOnFailure], ecx
0x140030fa6  mov     edx, 19h
0x140030fab  mov     rcx, [r10+18h]
0x140030faf  mov     r9d, esi
0x140030fb2  call    WPP_SF_DDq
0x140030fb7  cmp     [rbx+9B8h], r13
0x140030fbe  jz      loc_1400310EA
0x140030fc4  cmp     [rbx+9C0h], r13
0x140030fcb  jz      short loc_140030FDF
0x140030fcd  cmp     [rbx+9C8h], r13
0x140030fd4  jz      short loc_140030FDF
0x140030fd6  cmp     [rbx+9D0h], r13
0x140030fdd  jnz     short loc_140030FE1
0x140030fdf  int     2Ch; Windows NT - assertion failure
0x140030fe1  mov     edi, r13d
0x140030fe4  cmp     [rbx+9D8h], r13d
0x140030feb  jbe     loc_14003107F
0x140030ff1  mov     rax, [rbx+9C8h]
0x140030ff8  mov     edx, edi
0x140030ffa  add     rdx, rdx
0x140030ffd  mov     [rax+rdx*8], esi
0x140031000  mov     rax, [rbx+9C0h]
0x140031007  mov     rcx, [rbx+9C8h]
0x14003100e  mov     eax, [rax+rdx*8+0Ch]
0x140031012  mov     [rcx+rdx*8+4], eax
0x140031016  mov     rax, [rbx+9C0h]
0x14003101d  mov     rcx, [rbx+9C8h]
0x140031024  mov     rax, [rax+rdx*8]
0x140031028  mov     [rcx+rdx*8+8], rax
0x14003102d  or      ecx, 0FFFFFFFFh
0x140031030  mov     rax, [rbx+9D0h]
0x140031037  lock xadd [rax], ecx
0x14003103b  cmp     ecx, 1
0x14003103e  jnz     short loc_140031071
0x140031040  mov     dl, 16h
0x140031042  mov     rcx, rbp
0x140031045  call    cs:__imp_RDR_PERF_ENTER
0x14003104c  nop     dword ptr [rax+rax+00h]
0x140031051  mov     rcx, r14; RxContext
0x140031054  call    cs:__imp_RxLowIoCompletion
0x14003105b  nop     dword ptr [rax+rax+00h]
0x140031060  mov     dl, 17h
0x140031062  mov     rcx, rbp
0x140031065  call    cs:__imp_RDR_PERF_ENTER
0x14003106c  nop     dword ptr [rax+rax+00h]
0x140031071  inc     edi
0x140031073  cmp     edi, [rbx+9D8h]
0x140031079  jb      loc_140030FF1
0x14003107f  cmp     [rbx+9DCh], r13b
0x140031086  jz      short loc_14003109B
0x140031088  mov     rcx, [rbx+9B8h]; Mdl
0x14003108f  call    cs:__imp_IoFreeMdl
0x140031096  nop     dword ptr [rax+rax+00h]
0x14003109b  cmp     [rbx+9DDh], r13b
0x1400310a2  jz      short loc_1400310BC
0x1400310a4  mov     rcx, [rbx+9C0h]; P
0x1400310ab  mov     edx, 77427852h; Tag
0x1400310b0  call    cs:__imp_ExFreePoolWithTag
0x1400310b7  nop     dword ptr [rax+rax+00h]
0x1400310bc  mov     [rbx+9B8h], r13
0x1400310c3  mov     [rbx+9C0h], r13
0x1400310ca  mov     [rbx+9C8h], r13
0x1400310d1  mov     [rbx+9D0h], r13
0x1400310d8  mov     [rbx+9D8h], r13d
0x1400310df  mov     word ptr [rbx+9DCh], 0
0x1400310e8  jmp     short loc_14003112C
0x1400310ea  mov     eax, r15d
0x1400310ed  mov     dl, 16h
0x1400310ef  mov     rcx, rbp
0x1400310f2  mov     [r14+0B8h], rax
0x1400310f9  mov     [r14+0B0h], esi
0x140031100  call    cs:__imp_RDR_PERF_ENTER
0x140031107  nop     dword ptr [rax+rax+00h]
0x14003110c  mov     rcx, r14; RxContext
0x14003110f  call    cs:__imp_RxLowIoCompletion
0x140031116  nop     dword ptr [rax+rax+00h]
0x14003111b  mov     dl, 17h
0x14003111d  mov     rcx, rbp
0x140031120  call    cs:__imp_RDR_PERF_ENTER
0x140031127  nop     dword ptr [rax+rax+00h]
0x14003112c  mov     rcx, [rbx+410h]
0x140031133  test    rcx, rcx
0x140031136  jz      short loc_140031150
0x140031138  mov     edx, 6D537357h
0x14003113d  call    cs:__imp_SmbMmFreeSmbBuffer
0x140031144  nop     dword ptr [rax+rax+00h]
0x140031149  mov     [rbx+410h], r13
0x140031150  mov     rbx, [rsp+68h+arg_18]
0x140031158  mov     eax, esi
0x14003115a  add     rsp, 30h
0x14003115e  pop     r15
0x140031160  pop     r14
0x140031162  pop     r13
0x140031164  pop     r12
0x140031166  pop     rdi
0x140031167  pop     rsi
0x140031168  pop     rbp
0x140031169  retn
```
