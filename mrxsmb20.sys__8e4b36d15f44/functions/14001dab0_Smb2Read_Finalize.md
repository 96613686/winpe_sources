# Smb2Read_Finalize

- ea: `0x14001dab0`
- end: `0x14001de9f`
- name: `Smb2Read_Finalize`
- size: `1007`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000fa00`
- `0x14001dab0`
- `0x1400287a0`
- `0x14002ba20`
- `0x140036950`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14001dc2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dc2e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001dba2`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001dba2`
- `rdbss!RxLowIoCompletion` at `0x14001ddc7`
- `rdbss!RxLowIoCompletion` at `0x14001de26`
- `rdbss!RxLowIoCompletion` at `0x14001ddc7`
- `rdbss!RxLowIoCompletion` at `0x14001de26`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14001de54`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14001de78`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14001de54`
- `mrxsmb!SmbMmFreeSmbBuffer` at `0x14001de78`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001daf8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001ddb8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001ddd8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001de17`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001de37`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001daf8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001ddb8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001ddd8`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001de17`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001de37`
- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001dd32`
- `mrxsmb!SmbCeUpdateExchangeHistory` at `0x14001dd32`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001dc15`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001dc15`

## pseudocode

```c
__int64 __fastcall Smb2Read_Finalize(__int64 a1, __int64 a2)
{
  struct _RX_CONTEXT *v2; // r14
  __int64 v4; // rax
  unsigned int v5; // ebp
  unsigned int v6; // esi
  __int64 v7; // r12
  char v8; // r13
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 v11; // rdi
  struct _RX_CONTEXT *v12; // rbp
  __int64 v13; // rcx
  __int64 v14; // r14
  __int64 v15; // rcx
  bool v16; // zf
  PVOID v17; // rax
  PIRP CurrentIrp; // rcx
  unsigned int v19; // r8d
  unsigned int v20; // ecx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v27; // [rsp+80h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+88h] [rbp+10h]
  unsigned __int8 *v29; // [rsp+90h] [rbp+18h] BYREF
  struct _RX_CONTEXT *v30; // [rsp+98h] [rbp+20h]

  v2 = *(struct _RX_CONTEXT **)(a1 + 48);
  v4 = *(_QWORD *)(a1 + 72);
  v5 = 0;
  v6 = *(_DWORD *)(a1 + 16);
  LOBYTE(a2) = 18;
  v30 = v2;
  v7 = a1 + 512;
  v28 = 0;
  v8 = *(_BYTE *)(*(_QWORD *)(v4 + 24) + 1313LL);
  RDR_PERF_ENTER(a1 + 512, a2);
  v10 = *(_QWORD *)(a1 + 160);
  if ( v10 != a1 + 160 )
  {
    v11 = v10 - 8;
    if ( v11 )
    {
      v12 = v2;
      do
      {
        v13 = *(_QWORD *)(v11 + 8);
        v14 = 0;
        if ( v13 != a1 + 160 )
          v14 = v13 - 8;
        ProcessChunkAndUpdateBlockState_0(a1, v11);
        if ( *(int *)(v11 + 48) < 0 )
        {
          if ( v8 )
          {
            v15 = *(_QWORD *)(v11 + 752);
            if ( v15 )
            {
              v16 = (*(_BYTE *)(v15 + 10) & 5) == 0;
              v29 = 0;
              v27 = 0;
              v17 = v16 ? MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u) : *(PVOID *)(v15 + 24);
              if ( (int)Smb2QueryErrorDataFromResponse(
                          (__int64)v17,
                          *(_DWORD *)(*(_QWORD *)(v11 + 752) + 40LL),
                          1164730963,
                          &v29,
                          &v27) >= 0 )
              {
                CurrentIrp = v12->CurrentIrp;
                if ( CurrentIrp )
                {
                  if ( v29 && v27 >= 8 )
                    StRtlIoStorInfoSetSenseCode(CurrentIrp, v29[4], v29[5], v29[6]);
                }
              }
            }
          }
        }
        SmbCseFinalizeBufferContext(v11);
        if ( v11 == a1 + 1056 )
          *(_BYTE *)(a1 + 1052) = 0;
        else
          ExFreePoolWithTag((PVOID)v11, 0x6D536352u);
        v11 = v14;
      }
      while ( v14 );
      v5 = v28;
      v7 = a1 + 512;
      v2 = v30;
    }
  }
  if ( (v6 & 0x80000000) == 0 )
  {
    v19 = *(_DWORD *)(a1 + 1044);
    v20 = 0;
    if ( !v19 )
      goto LABEL_39;
    do
    {
      v9 = *(unsigned int *)(a1 + 8LL * v20 + 2496);
      if ( (_DWORD)v9 == -1 )
        break;
      v6 = *(_DWORD *)(a1 + 8LL * v20 + 2496);
      if ( (int)v9 >= 0 )
      {
        v5 += *(_DWORD *)(a1 + 8LL * v20 + 2500);
        if ( *(_BYTE *)(a1 + 1040) == 1 )
          goto LABEL_39;
      }
      else
      {
        if ( *(_BYTE *)(a1 + 1040) != 1 || (_DWORD)v9 != -2147483643 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_DDq(
              WPP_GLOBAL_Control->AttachedDevice,
              44,
              WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
              (unsigned int)v9,
              v20,
              a1);
          }
          break;
        }
        v5 += *(_DWORD *)(a1 + 8LL * v20 + 2500);
      }
      ++v20;
    }
    while ( v20 < v19 );
  }
  if ( v6 == -1073741807 )
  {
    if ( v5 )
    {
      v6 = 0;
      goto LABEL_42;
    }
    goto LABEL_41;
  }
LABEL_39:
  if ( v6 && v6 != 259 )
  {
LABEL_41:
    _InterlockedExchange64((volatile __int64 *)(a1 + 16), v6);
    SmbCeUpdateExchangeHistory(a1, v6);
  }
LABEL_42:
  if ( *(_QWORD *)(a1 + 2456) )
  {
    if ( !*(_QWORD *)(a1 + 2464) || !*(_QWORD *)(a1 + 2472) || !*(_QWORD *)(a1 + 2480) )
      __int2c();
    **(_DWORD **)(a1 + 2472) = v6;
    *(_DWORD *)(*(_QWORD *)(a1 + 2472) + 4LL) = *(_DWORD *)(*(_QWORD *)(a1 + 2464) + 12LL);
    *(_QWORD *)(*(_QWORD *)(a1 + 2472) + 8LL) = **(_QWORD **)(a1 + 2464);
    v21 = (unsigned int)_InterlockedExchangeAdd(*(volatile signed __int32 **)(a1 + 2480), 0xFFFFFFFF);
    if ( (_DWORD)v21 == 1 )
    {
      LOBYTE(v21) = 22;
      RDR_PERF_ENTER(v7, v21);
      RxLowIoCompletion(v2);
      LOBYTE(v22) = 23;
      RDR_PERF_ENTER(v7, v22);
    }
    *(_QWORD *)(a1 + 2456) = 0;
    *(_QWORD *)(a1 + 2464) = 0;
    *(_QWORD *)(a1 + 2472) = 0;
    *(_QWORD *)(a1 + 2480) = 0;
  }
  else
  {
    LOBYTE(v9) = 22;
    v2->InformationToReturn = v5;
    v2->StoredStatus = v6;
    RDR_PERF_ENTER(v7, v9);
    RxLowIoCompletion(v2);
    LOBYTE(v23) = 23;
    RDR_PERF_ENTER(v7, v23);
  }
  v24 = *(_QWORD *)(a1 + 1032);
  if ( v24 )
  {
    SmbMmFreeSmbBuffer(v24, 1834184018);
    *(_QWORD *)(a1 + 1032) = 0;
  }
  v25 = *(_QWORD *)(a1 + 1024);
  if ( v25 )
  {
    SmbMmFreeSmbBuffer(v25, 1834185554);
    *(_QWORD *)(a1 + 1024) = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x14001dab0  push    rbx
0x14001dab2  push    rbp
0x14001dab3  push    rsi
0x14001dab4  push    rdi
0x14001dab5  push    r12
0x14001dab7  push    r13
0x14001dab9  push    r14
0x14001dabb  push    r15
0x14001dabd  sub     rsp, 38h
0x14001dac1  mov     r14, [rcx+30h]
0x14001dac5  mov     rbx, rcx
0x14001dac8  mov     rax, [rcx+48h]
0x14001dacc  xor     ebp, ebp
0x14001dace  mov     esi, [rcx+10h]
0x14001dad1  mov     dl, 12h
0x14001dad3  mov     [rsp+78h+arg_18], r14
0x14001dadb  lea     r12, [rbx+200h]
0x14001dae2  mov     [rsp+78h+arg_8], ebp
0x14001dae9  mov     rcx, [rax+18h]
0x14001daed  movzx   r13d, byte ptr [rcx+521h]
0x14001daf5  mov     rcx, r12
0x14001daf8  call    cs:__imp_RDR_PERF_ENTER
0x14001daff  nop     dword ptr [rax+rax+00h]
0x14001db04  lea     r15, [rbx+0A0h]
0x14001db0b  mov     rdi, [r15]
0x14001db0e  cmp     rdi, r15
0x14001db11  jz      loc_14001DC65
0x14001db17  add     rdi, 0FFFFFFFFFFFFFFF8h
0x14001db1b  jz      loc_14001DC65
0x14001db21  lea     r12, [rbx+420h]
0x14001db28  mov     rbp, r14
0x14001db2b  nop     dword ptr [rax+rax+00h]
0x14001db30  mov     rcx, [rdi+8]
0x14001db34  xor     r14d, r14d
0x14001db37  cmp     rcx, r15
0x14001db3a  mov     rdx, rdi
0x14001db3d  lea     rax, [rcx-8]
0x14001db41  mov     rcx, rbx
0x14001db44  cmovnz  r14, rax
0x14001db48  call    ProcessChunkAndUpdateBlockState_0
0x14001db4d  cmp     dword ptr [rdi+30h], 0
0x14001db51  jge     loc_14001DC12
0x14001db57  test    r13b, r13b
0x14001db5a  jz      loc_14001DC12
0x14001db60  mov     rcx, [rdi+2F0h]; MemoryDescriptorList
0x14001db67  test    rcx, rcx
0x14001db6a  jz      loc_14001DC12
0x14001db70  xor     edx, edx; AccessMode
0x14001db72  test    byte ptr [rcx+0Ah], 5
0x14001db76  mov     [rsp+78h+arg_10], rdx
0x14001db7e  mov     [rsp+78h+arg_0], edx
0x14001db85  jz      short loc_14001DB8D
0x14001db87  mov     rax, [rcx+18h]
0x14001db8b  jmp     short loc_14001DBAE
0x14001db8d  mov     [rsp+78h+Priority], 40000010h; Priority
0x14001db95  xor     r9d, r9d; RequestedAddress
0x14001db98  mov     r8d, 1; CacheType
0x14001db9e  mov     [rsp+78h+BugCheckOnFailure], edx; BugCheckOnFailure
0x14001dba2  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001dba9  nop     dword ptr [rax+rax+00h]
0x14001dbae  mov     rdx, [rdi+2F0h]
0x14001dbb5  lea     rcx, [rsp+78h+arg_0]
0x14001dbbd  mov     qword ptr [rsp+78h+BugCheckOnFailure], rcx
0x14001dbc2  lea     r9, [rsp+78h+arg_10]
0x14001dbca  mov     r8d, 456C6253h
0x14001dbd0  mov     rcx, rax
0x14001dbd3  mov     edx, [rdx+28h]
0x14001dbd6  call    Smb2QueryErrorDataFromResponse
0x14001dbdb  test    eax, eax
0x14001dbdd  js      short loc_14001DC12
0x14001dbdf  mov     rcx, [rbp+28h]
0x14001dbe3  test    rcx, rcx
0x14001dbe6  jz      short loc_14001DC12
0x14001dbe8  mov     rdx, [rsp+78h+arg_10]
0x14001dbf0  test    rdx, rdx
0x14001dbf3  jz      short loc_14001DC12
0x14001dbf5  cmp     [rsp+78h+arg_0], 8
0x14001dbfd  jb      short loc_14001DC12
0x14001dbff  movzx   r9d, byte ptr [rdx+6]
0x14001dc04  movzx   r8d, byte ptr [rdx+5]
0x14001dc09  movzx   edx, byte ptr [rdx+4]
0x14001dc0d  call    StRtlIoStorInfoSetSenseCode
0x14001dc12  mov     rcx, rdi
0x14001dc15  call    cs:__imp_SmbCseFinalizeBufferContext
0x14001dc1c  nop     dword ptr [rax+rax+00h]
0x14001dc21  cmp     rdi, r12
0x14001dc24  jz      short loc_14001DC3C
0x14001dc26  mov     edx, 6D536352h; Tag
0x14001dc2b  mov     rcx, rdi; P
0x14001dc2e  call    cs:__imp_ExFreePoolWithTag
0x14001dc35  nop     dword ptr [rax+rax+00h]
0x14001dc3a  jmp     short loc_14001DC43
0x14001dc3c  mov     byte ptr [rbx+41Ch], 0
0x14001dc43  mov     rdi, r14
0x14001dc46  test    r14, r14
0x14001dc49  jnz     loc_14001DB30
0x14001dc4f  mov     ebp, [rsp+78h+arg_8]
0x14001dc56  lea     r12, [rbx+200h]
0x14001dc5d  mov     r14, [rsp+78h+arg_18]
0x14001dc65  xor     edi, edi
0x14001dc67  test    esi, esi
0x14001dc69  js      loc_14001DD0B
0x14001dc6f  mov     r8d, [rbx+414h]
0x14001dc76  mov     ecx, edi
0x14001dc78  test    r8d, r8d
0x14001dc7b  jz      loc_14001DD1B
0x14001dc81  mov     eax, ecx
0x14001dc83  mov     edx, [rbx+rax*8+9C0h]
0x14001dc8a  cmp     edx, 0FFFFFFFFh
0x14001dc8d  jz      short loc_14001DD0B
0x14001dc8f  mov     esi, edx
0x14001dc91  test    edx, edx
0x14001dc93  jns     short loc_14001DCAF
0x14001dc95  cmp     byte ptr [rbx+410h], 1
0x14001dc9c  jnz     short loc_14001DCC8
0x14001dc9e  cmp     edx, 80000005h
0x14001dca4  jnz     short loc_14001DCC8
0x14001dca6  add     ebp, [rbx+rax*8+9C4h]
0x14001dcad  jmp     short loc_14001DCBF
0x14001dcaf  add     ebp, [rbx+rax*8+9C4h]
0x14001dcb6  cmp     byte ptr [rbx+410h], 1
0x14001dcbd  jz      short loc_14001DD1B
0x14001dcbf  inc     ecx
0x14001dcc1  cmp     ecx, r8d
0x14001dcc4  jb      short loc_14001DC81
0x14001dcc6  jmp     short loc_14001DD0B
0x14001dcc8  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001dccf  lea     rax, WPP_GLOBAL_Control
0x14001dcd6  cmp     r10, rax
0x14001dcd9  jz      short loc_14001DD0B
0x14001dcdb  mov     eax, [r10+2Ch]
0x14001dcdf  test    al, 1
0x14001dce1  jz      short loc_14001DD0B
0x14001dce3  cmp     byte ptr [r10+29h], 1
0x14001dce8  jb      short loc_14001DD0B
0x14001dcea  mov     qword ptr [rsp+78h+Priority], rbx
0x14001dcef  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14001dcf6  mov     [rsp+78h+BugCheckOnFailure], ecx
0x14001dcfa  mov     edx, 2Ch ; ','
0x14001dcff  mov     rcx, [r10+18h]
0x14001dd03  mov     r9d, esi
0x14001dd06  call    WPP_SF_DDq
0x14001dd0b  cmp     esi, 0C0000011h
0x14001dd11  jnz     short loc_14001DD1B
0x14001dd13  test    ebp, ebp
0x14001dd15  jz      short loc_14001DD27
0x14001dd17  mov     esi, edi
0x14001dd19  jmp     short loc_14001DD3E
0x14001dd1b  test    esi, esi
0x14001dd1d  jz      short loc_14001DD3E
0x14001dd1f  cmp     esi, 103h
0x14001dd25  jz      short loc_14001DD3E
0x14001dd27  mov     eax, esi
0x14001dd29  mov     rcx, rbx
0x14001dd2c  xchg    rax, [rbx+10h]
0x14001dd30  mov     edx, esi
0x14001dd32  call    cs:__imp_SmbCeUpdateExchangeHistory
0x14001dd39  nop     dword ptr [rax+rax+00h]
0x14001dd3e  cmp     qword ptr [rbx+998h], 0
0x14001dd46  jz      loc_14001DE02
0x14001dd4c  cmp     qword ptr [rbx+9A0h], 0
0x14001dd54  jz      short loc_14001DD6A
0x14001dd56  cmp     qword ptr [rbx+9A8h], 0
0x14001dd5e  jz      short loc_14001DD6A
0x14001dd60  cmp     qword ptr [rbx+9B0h], 0
0x14001dd68  jnz     short loc_14001DD6C
0x14001dd6a  int     2Ch; Windows NT - assertion failure
0x14001dd6c  mov     rax, [rbx+9A8h]
0x14001dd73  mov     [rax], esi
0x14001dd75  mov     rax, [rbx+9A0h]
0x14001dd7c  mov     rdx, [rbx+9A8h]
0x14001dd83  mov     eax, [rax+0Ch]
0x14001dd86  mov     [rdx+4], eax
0x14001dd89  mov     rax, [rbx+9A0h]
0x14001dd90  mov     rdx, [rbx+9A8h]
0x14001dd97  mov     rax, [rax]
0x14001dd9a  mov     [rdx+8], rax
0x14001dd9e  mov     edx, 0FFFFFFFFh
0x14001dda3  mov     rax, [rbx+9B0h]
0x14001ddaa  lock xadd [rax], edx
0x14001ddae  cmp     edx, 1
0x14001ddb1  jnz     short loc_14001DDE4
0x14001ddb3  mov     dl, 16h
0x14001ddb5  mov     rcx, r12
0x14001ddb8  call    cs:__imp_RDR_PERF_ENTER
0x14001ddbf  nop     dword ptr [rax+rax+00h]
0x14001ddc4  mov     rcx, r14; RxContext
0x14001ddc7  call    cs:__imp_RxLowIoCompletion
0x14001ddce  nop     dword ptr [rax+rax+00h]
0x14001ddd3  mov     dl, 17h
0x14001ddd5  mov     rcx, r12
0x14001ddd8  call    cs:__imp_RDR_PERF_ENTER
0x14001dddf  nop     dword ptr [rax+rax+00h]
0x14001dde4  mov     [rbx+998h], rdi
0x14001ddeb  mov     [rbx+9A0h], rdi
0x14001ddf2  mov     [rbx+9A8h], rdi
0x14001ddf9  mov     [rbx+9B0h], rdi
0x14001de00  jmp     short loc_14001DE43
0x14001de02  mov     eax, ebp
0x14001de04  mov     dl, 16h
0x14001de06  mov     rcx, r12
0x14001de09  mov     [r14+0B8h], rax
0x14001de10  mov     [r14+0B0h], esi
0x14001de17  call    cs:__imp_RDR_PERF_ENTER
0x14001de1e  nop     dword ptr [rax+rax+00h]
0x14001de23  mov     rcx, r14; RxContext
0x14001de26  call    cs:__imp_RxLowIoCompletion
0x14001de2d  nop     dword ptr [rax+rax+00h]
0x14001de32  mov     dl, 17h
0x14001de34  mov     rcx, r12
0x14001de37  call    cs:__imp_RDR_PERF_ENTER
0x14001de3e  nop     dword ptr [rax+rax+00h]
0x14001de43  mov     rcx, [rbx+408h]
0x14001de4a  test    rcx, rcx
0x14001de4d  jz      short loc_14001DE67
0x14001de4f  mov     edx, 6D536D52h
0x14001de54  call    cs:__imp_SmbMmFreeSmbBuffer
0x14001de5b  nop     dword ptr [rax+rax+00h]
0x14001de60  mov     [rbx+408h], rdi
0x14001de67  mov     rcx, [rbx+400h]
0x14001de6e  test    rcx, rcx
0x14001de71  jz      short loc_14001DE8B
0x14001de73  mov     edx, 6D537352h
0x14001de78  call    cs:__imp_SmbMmFreeSmbBuffer
0x14001de7f  nop     dword ptr [rax+rax+00h]
0x14001de84  mov     [rbx+400h], rdi
0x14001de8b  mov     eax, esi
0x14001de8d  add     rsp, 38h
0x14001de91  pop     r15
0x14001de93  pop     r14
0x14001de95  pop     r13
0x14001de97  pop     r12
0x14001de99  pop     rdi
0x14001de9a  pop     rsi
0x14001de9b  pop     rbp
0x14001de9c  pop     rbx
0x14001de9d  retn
```
