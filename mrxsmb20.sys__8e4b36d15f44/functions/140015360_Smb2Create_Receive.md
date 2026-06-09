# Smb2Create_Receive

- ea: `0x140015360`
- end: `0x140015568`
- name: `Smb2Create_Receive`
- size: `520`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, unsigned int *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x140015360`
- `0x140015570`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140015556`
- `ntoskrnl!MmUnlockPages` at `0x140015556`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b53e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b53e`
- `rdbss!RxFreeMdl` at `0x14003b51f`
- `rdbss!RxFreeMdl` at `0x14003b51f`
- `rdbss!RxAllocateMdl2` at `0x14001552f`
- `rdbss!RxAllocateMdl2` at `0x14001552f`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x1400154b6`
- `mrxsmb!SmbCeAllocateExchangeBuffer` at `0x1400154b6`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001538e`
- `mrxsmb!RDR_PERF_ENTER` at `0x14001538e`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400153bf`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400153bf`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001545c`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x14001545c`

## pseudocode

```c
__int64 __fastcall Smb2Create_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6,
        __int64 a7)
{
  int v7; // esi
  __int64 v8; // rbp
  unsigned int v11; // r15d
  int v12; // r14d
  __int64 v13; // rcx
  unsigned int v14; // ebx
  __int64 ExchangeBuffer; // rax
  __int64 v17; // r13
  __int64 v18; // rcx
  struct _MDL *MemoryDescriptorList; // [rsp+60h] [rbp+8h]

  v7 = *(_DWORD *)(a3 + 16);
  v8 = a2;
  LOBYTE(a2) = 35;
  v11 = 0;
  v12 = 0;
  RDR_PERF_ENTER(a1 + 512, a2);
  if ( v7 )
  {
    if ( v7 == -2147483603 )
    {
      v11 = Smb2BufferErrorResponse(v8, a7, a4, a5, a6);
    }
    else
    {
      v12 = 15;
      *a6 = a5;
    }
  }
  else
  {
    v14 = a5 - 64;
    if ( a5 - 64 < 0x58 )
    {
      v7 = -1073741629;
      *a6 = a5;
    }
    else
    {
      if ( (*(_BYTE *)(MRxSmbGetConfigurationBlock(v13) + 64) & 1) != 0 )
        _InterlockedIncrement((volatile signed __int32 *)(192LL
                                                        * (unsigned int)(HIDWORD(KeGetPcr()[1].LockArray)
                                                                       % *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88)
                                                                                               + 424LL)
                                                                                   + 1488LL))
                                                        + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL) + 1480LL)
                                                        + 84));
      if ( v14 > *(_DWORD *)(v8 + 744) )
      {
        ExchangeBuffer = SmbCeAllocateExchangeBuffer(a1);
        v17 = ExchangeBuffer;
        if ( !ExchangeBuffer
          || (MemoryDescriptorList = (struct _MDL *)RxAllocateMdl2(ExchangeBuffer, v14, 0, 0, 0)) == 0 )
        {
          v7 = -1073741670;
          *a6 = a5;
          goto LABEL_8;
        }
        v18 = *(_QWORD *)(v8 + 720);
        if ( (*(_BYTE *)(v18 + 10) & 2) != 0 )
          MmUnlockPages((PMDL)v18);
        RxFreeMdl(*(_QWORD *)(v8 + 720));
        *(_QWORD *)(v8 + 720) = MemoryDescriptorList;
        *(_QWORD *)(v8 + 712) = v17;
        MmBuildMdlForNonPagedPool(MemoryDescriptorList);
      }
      *(_DWORD *)(v8 + 748) = v14;
      if ( a4 == a5 )
      {
        *a6 = a5;
        memmove(*(void **)(v8 + 712), (const void *)(a7 + 64), v14);
      }
      else
      {
        *a6 = 64;
        v11 = -1073741802;
      }
    }
  }
LABEL_8:
  SmbCseUpdateBufferContextStatus(v8, __PAIR64__(v12, v7));
  return v11;
}

```

## disassembly

```asm
0x140015360  mov     [rsp+arg_18], rbp
0x140015365  push    rsi
0x140015366  push    r12
0x140015368  push    r13
0x14001536a  push    r14
0x14001536c  push    r15
0x14001536e  sub     rsp, 30h
0x140015372  mov     esi, [r8+10h]
0x140015376  mov     rbp, rdx
0x140015379  mov     r13, rcx
0x14001537c  mov     dl, 23h ; '#'
0x14001537e  add     rcx, 200h
0x140015385  mov     r12d, r9d
0x140015388  xor     r15d, r15d
0x14001538b  xor     r14d, r14d
0x14001538e  call    cs:__imp_RDR_PERF_ENTER
0x140015395  nop     dword ptr [rax+rax+00h]
0x14001539a  test    esi, esi
0x14001539c  jnz     loc_140015490
0x1400153a2  mov     [rsp+58h+arg_8], rbx
0x1400153a7  mov     [rsp+58h+arg_10], rdi
0x1400153ac  mov     edi, [rsp+58h+arg_20]
0x1400153b3  lea     ebx, [rdi-40h]
0x1400153b6  cmp     ebx, 58h ; 'X'
0x1400153b9  jb      loc_14001547F
0x1400153bf  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400153c6  nop     dword ptr [rax+rax+00h]
0x1400153cb  test    byte ptr [rax+40h], 1
0x1400153cf  jz      short loc_140015401
0x1400153d1  mov     rax, [r13+58h]
0x1400153d5  xor     edx, edx
0x1400153d7  mov     r8, [rax+1A8h]
0x1400153de  mov     eax, gs:1A4h
0x1400153e6  div     dword ptr [r8+5D0h]
0x1400153ed  mov     rax, [r8+5C8h]
0x1400153f4  lea     rdx, [rdx+rdx*2]
0x1400153f8  shl     rdx, 6
0x1400153fc  lock inc dword ptr [rdx+rax+54h]
0x140015401  cmp     ebx, [rbp+2E8h]
0x140015407  ja      loc_1400154B1
0x14001540d  mov     rax, [rsp+58h+arg_28]
0x140015415  mov     [rbp+2ECh], ebx
0x14001541b  cmp     r12d, edi
0x14001541e  jnz     loc_1400154DE
0x140015424  mov     rdx, [rsp+58h+arg_30]
0x14001542c  mov     [rax], edi
0x14001542e  add     rdx, 40h ; '@'; Src
0x140015432  mov     rcx, [rbp+2C8h]; void *
0x140015439  mov     r8d, ebx; Size
0x14001543c  call    memmove
0x140015441  mov     rbx, [rsp+58h+arg_8]
0x140015446  mov     rdi, [rsp+58h+arg_10]
0x14001544b  mov     dword ptr [rsp+58h+MemoryDescriptorList], esi
0x14001544f  mov     rcx, rbp
0x140015452  mov     dword ptr [rsp+58h+MemoryDescriptorList+4], r14d
0x140015457  mov     rdx, [rsp+58h+MemoryDescriptorList]
0x14001545c  call    cs:__imp_SmbCseUpdateBufferContextStatus
0x140015463  nop     dword ptr [rax+rax+00h]
0x140015468  mov     rbp, [rsp+58h+arg_18]
0x14001546d  mov     eax, r15d
0x140015470  add     rsp, 30h
0x140015474  pop     r15
0x140015476  pop     r14
0x140015478  pop     r13
0x14001547a  pop     r12
0x14001547c  pop     rsi
0x14001547d  retn
0x14001547f  mov     rax, [rsp+58h+arg_28]
0x140015487  mov     esi, 0C00000C3h
0x14001548c  mov     [rax], edi
0x14001548e  jmp     short loc_140015441
0x140015490  cmp     esi, 8000002Dh
0x140015496  jz      short loc_1400154EF
0x140015498  mov     rcx, [rsp+58h+arg_28]
0x1400154a0  mov     r14d, 0Fh
0x1400154a6  mov     eax, [rsp+58h+arg_20]
0x1400154ad  mov     [rcx], eax
0x1400154af  jmp     short loc_14001544B
0x1400154b1  mov     edx, ebx
0x1400154b3  mov     rcx, r13
0x1400154b6  call    cs:__imp_SmbCeAllocateExchangeBuffer
0x1400154bd  nop     dword ptr [rax+rax+00h]
0x1400154c2  mov     r13, rax
0x1400154c5  test    rax, rax
0x1400154c8  jnz     short loc_14001551F
0x1400154ca  mov     rax, [rsp+58h+arg_28]
0x1400154d2  mov     esi, 0C000009Ah
0x1400154d7  mov     [rax], edi
0x1400154d9  jmp     loc_140015441
0x1400154de  mov     dword ptr [rax], 40h ; '@'
0x1400154e4  mov     r15d, 0C0000016h
0x1400154ea  jmp     loc_140015441
0x1400154ef  mov     rax, [rsp+58h+arg_28]
0x1400154f7  mov     r8d, r12d
0x1400154fa  mov     r9d, [rsp+58h+arg_20]
0x140015502  mov     rcx, rbp
0x140015505  mov     rdx, [rsp+58h+arg_30]
0x14001550d  mov     [rsp+58h+var_38], rax
0x140015512  call    Smb2BufferErrorResponse
0x140015517  mov     r15d, eax
0x14001551a  jmp     loc_14001544B
0x14001551f  xor     r9d, r9d
0x140015522  mov     [rsp+58h+var_38], r14
0x140015527  xor     r8d, r8d
0x14001552a  mov     edx, ebx
0x14001552c  mov     rcx, r13
0x14001552f  call    cs:__imp_RxAllocateMdl2
0x140015536  nop     dword ptr [rax+rax+00h]
0x14001553b  mov     [rsp+58h+MemoryDescriptorList], rax
0x140015540  test    rax, rax
0x140015543  jz      short loc_1400154CA
0x140015545  mov     rcx, [rbp+2D0h]; MemoryDescriptorList
0x14001554c  test    byte ptr [rcx+0Ah], 2
0x140015550  jz      loc_14003B518
0x140015556  call    cs:__imp_MmUnlockPages
0x14001555d  nop     dword ptr [rax+rax+00h]
0x140015562  nop
0x140015563  jmp     loc_14003B518
0x14003b518  mov     rcx, [rbp+2D0h]
0x14003b51f  call    cs:__imp_RxFreeMdl
0x14003b526  nop     dword ptr [rax+rax+00h]
0x14003b52b  mov     rcx, [rsp+58h+MemoryDescriptorList]; MemoryDescriptorList
0x14003b530  mov     [rbp+2D0h], rcx
0x14003b537  mov     [rbp+2C8h], r13
0x14003b53e  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003b545  nop     dword ptr [rax+rax+00h]
0x14003b54a  nop
0x14003b54b  jmp     loc_14001540D
```
