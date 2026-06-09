# SmbExtSecuritySessionSetupExchangeFinalize

- ea: `0x14000bfc0`
- end: `0x14000c1e0`
- name: `SmbExtSecuritySessionSetupExchangeFinalize`
- size: `544`
- prototype: `__int64 __fastcall(unsigned int *pContext, _BYTE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005aa4`
- `0x14000b390`
- `0x14000bfc0`
- `0x14000d660`
- `0x14000dfd8`
- `0x1400166c0`
- `0x140029b20`
- `0x14004ccf0`
- `0x14004eb70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c13a`
- `ntoskrnl!ExAllocatePool2` at `0x14000c13a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c112`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c112`
- `rdbss!RxPostToWorkerThread` at `0x14000c0e6`
- `rdbss!RxPostToWorkerThread` at `0x14000c0e6`
- `mrxsmb!MRxSmbDeviceObject` at `0x14000c0c0`

## pseudocode

```c
__int64 __fastcall SmbExtSecuritySessionSetupExchangeFinalize(unsigned int *pContext, _BYTE *a2)
{
  bool v2; // zf
  unsigned int *v3; // rdi
  unsigned int v4; // ebx
  __int64 v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // rbx
  void *v8; // rcx
  void *Pool2; // rax
  __int64 v10; // rsi
  PVOID v12; // [rsp+60h] [rbp+8h] BYREF

  v2 = *((_BYTE *)pContext + 361) == 0;
  v3 = pContext;
  v12 = pContext;
  if ( v2 )
  {
    *((_BYTE *)pContext + 361) = 1;
    *a2 = 1;
    return 0;
  }
  *((_BYTE *)pContext + 361) = 0;
  *a2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, pContext[12]);
  v4 = v3[12];
  if ( v4 == -1073741802 )
  {
    if ( !v3[103] )
      goto LABEL_11;
    v8 = (void *)*((_QWORD *)v3 + 50);
    if ( v8 )
    {
      ExFreePoolWithTag(v8, 0);
      *((_QWORD *)v3 + 50) = 0;
    }
    Pool2 = (void *)ExAllocatePool2(258, v3[103], 1934323027);
    *((_QWORD *)v3 + 50) = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, (const void *)(*((_QWORD *)v3 + 47) + v3[102]), v3[103]);
      goto LABEL_11;
    }
    v4 = -1073741670;
  }
  else
  {
    if ( v4 )
      goto LABEL_10;
    if ( v3[103] )
    {
      v4 = ValidateServerExtendedSessionSetupResponse((__int64)v3, *((_QWORD *)v3 + 47) + v3[102]);
LABEL_10:
      if ( v4 != -1073741802 )
      {
LABEL_20:
        if ( v4 == 259 )
          return 0;
        goto LABEL_21;
      }
LABEL_11:
      v5 = *((_QWORD *)v3 + 11);
      v6 = *((_QWORD *)v3 + 3);
      v3[18] &= ~0x100u;
      SmbCePrepareExchangeForReuse(v3);
      v4 = SmbCepInitializeExchange((unsigned int)&v12, 0, 0, v5, 3, (__int64)&ExtendedSessionSetupExchangeDispatch);
      if ( !v4 )
      {
        v7 = v12;
        *((_DWORD *)v12 + 18) |= 0x1000u;
        v7[3] = v6;
        SmbCeDecrementActiveExchangeCount();
        *((_WORD *)v7 + 30) = 2;
        RxPostToWorkerThread(
          MRxSmbDeviceObject,
          HyperCriticalWorkQueue,
          (PRX_WORK_QUEUE_ITEM)(v3 + 44),
          SmbExtSessionSetupContinue,
          v7);
        return 0;
      }
      v3 = (unsigned int *)v12;
      goto LABEL_20;
    }
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids, v4);
  v10 = *((_QWORD *)v3 + 55);
  SmbCeDiscardExtendedSessionSetupExchange(v3);
  if ( v10 )
  {
    *(_DWORD *)(v10 + 4) = v4;
    SmbCeResume(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x14000bfc0  push    rbx
0x14000bfc2  push    rsi
0x14000bfc3  push    rdi
0x14000bfc4  push    r15
0x14000bfc6  sub     rsp, 38h
0x14000bfca  cmp     byte ptr [rcx+169h], 0
0x14000bfd1  mov     rdi, rcx
0x14000bfd4  mov     [rsp+58h+arg_0], rcx
0x14000bfd9  jnz     short loc_14000BFEA
0x14000bfdb  mov     byte ptr [rcx+169h], 1
0x14000bfe2  mov     byte ptr [rdx], 1
0x14000bfe5  jmp     loc_14000C1D3
0x14000bfea  mov     byte ptr [rcx+169h], 0
0x14000bff1  mov     byte ptr [rdx], 0
0x14000bff4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000bffb  lea     r15, WPP_GLOBAL_Control
0x14000c002  cmp     rcx, r15
0x14000c005  jz      short loc_14000C029
0x14000c007  test    dword ptr [rcx+2Ch], 400h
0x14000c00e  jz      short loc_14000C029
0x14000c010  mov     r9d, [rdi+30h]
0x14000c014  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14000c01b  mov     rcx, [rcx+18h]
0x14000c01f  mov     edx, 11h
0x14000c024  call    WPP_SF_d
0x14000c029  mov     ebx, [rdi+30h]
0x14000c02c  mov     esi, 0C0000016h
0x14000c031  cmp     ebx, esi
0x14000c033  jz      loc_14000C0F7
0x14000c039  test    ebx, ebx
0x14000c03b  jnz     short loc_14000C060
0x14000c03d  cmp     [rdi+19Ch], ebx
0x14000c043  jz      loc_14000C187
0x14000c049  mov     edx, [rdi+198h]
0x14000c04f  mov     rcx, rdi
0x14000c052  add     rdx, [rdi+178h]
0x14000c059  call    ValidateServerExtendedSessionSetupResponse
0x14000c05e  mov     ebx, eax
0x14000c060  cmp     ebx, esi
0x14000c062  jnz     loc_14000C17F
0x14000c068  mov     rbx, [rdi+58h]
0x14000c06c  mov     rcx, rdi
0x14000c06f  mov     rsi, [rdi+18h]
0x14000c073  btr     dword ptr [rdi+48h], 8
0x14000c078  call    SmbCePrepareExchangeForReuse
0x14000c07d  lea     rax, ExtendedSessionSetupExchangeDispatch
0x14000c084  mov     r9, rbx
0x14000c087  mov     [rsp+58h+var_30], rax
0x14000c08c  lea     rcx, [rsp+58h+arg_0]
0x14000c091  xor     r8d, r8d
0x14000c094  mov     dword ptr [rsp+58h+pContext], 3
0x14000c09c  xor     edx, edx
0x14000c09e  call    SmbCepInitializeExchange
0x14000c0a3  mov     ebx, eax
0x14000c0a5  test    eax, eax
0x14000c0a7  jnz     loc_14000C17A
0x14000c0ad  mov     rbx, [rsp+58h+arg_0]
0x14000c0b2  bts     dword ptr [rbx+48h], 0Ch
0x14000c0b7  mov     [rbx+18h], rsi
0x14000c0bb  call    SmbCeDecrementActiveExchangeCount
0x14000c0c0  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14000c0c7  lea     r8, [rdi+0B0h]; pWorkQueueItem
0x14000c0ce  mov     edx, 2; WorkQueueType
0x14000c0d3  mov     [rsp+58h+pContext], rbx; pContext
0x14000c0d8  mov     [rbx+3Ch], dx
0x14000c0dc  lea     r9, SmbExtSessionSetupContinue; Routine
0x14000c0e3  mov     rcx, [rcx]; pMRxDeviceObject
0x14000c0e6  call    cs:__imp_RxPostToWorkerThread
0x14000c0ed  nop     dword ptr [rax+rax+00h]
0x14000c0f2  jmp     loc_14000C1D3
0x14000c0f7  cmp     dword ptr [rdi+19Ch], 0
0x14000c0fe  jz      loc_14000C068
0x14000c104  mov     rcx, [rdi+190h]; P
0x14000c10b  test    rcx, rcx
0x14000c10e  jz      short loc_14000C129
0x14000c110  xor     edx, edx; Tag
0x14000c112  call    cs:__imp_ExFreePoolWithTag
0x14000c119  nop     dword ptr [rax+rax+00h]
0x14000c11e  mov     qword ptr [rdi+190h], 0
0x14000c129  mov     edx, [rdi+19Ch]
0x14000c12f  mov     ecx, 102h
0x14000c134  mov     r8d, 734B6D53h
0x14000c13a  call    cs:__imp_ExAllocatePool2
0x14000c141  nop     dword ptr [rax+rax+00h]
0x14000c146  mov     [rdi+190h], rax
0x14000c14d  test    rax, rax
0x14000c150  jz      short loc_14000C173
0x14000c152  mov     edx, [rdi+198h]
0x14000c158  mov     rcx, rax; void *
0x14000c15b  add     rdx, [rdi+178h]; Src
0x14000c162  mov     r8d, [rdi+19Ch]; Size
0x14000c169  call    memmove
0x14000c16e  jmp     loc_14000C068
0x14000c173  mov     ebx, 0C000009Ah
0x14000c178  jmp     short loc_14000C187
0x14000c17a  mov     rdi, [rsp+58h+arg_0]
0x14000c17f  cmp     ebx, 103h
0x14000c185  jz      short loc_14000C1D3
0x14000c187  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000c18e  cmp     rcx, r15
0x14000c191  jz      short loc_14000C1B4
0x14000c193  test    dword ptr [rcx+2Ch], 400h
0x14000c19a  jz      short loc_14000C1B4
0x14000c19c  mov     rcx, [rcx+18h]
0x14000c1a0  lea     r8, WPP_43394d5f7d713bd5b3e6605c91e75025_Traceguids
0x14000c1a7  mov     edx, 12h
0x14000c1ac  mov     r9d, ebx
0x14000c1af  call    WPP_SF_d
0x14000c1b4  mov     rsi, [rdi+1B8h]
0x14000c1bb  mov     rcx, rdi; pContext
0x14000c1be  call    SmbCeDiscardExtendedSessionSetupExchange
0x14000c1c3  test    rsi, rsi
0x14000c1c6  jz      short loc_14000C1D3
0x14000c1c8  mov     rcx, rsi
0x14000c1cb  mov     [rsi+4], ebx
0x14000c1ce  call    SmbCeResume
0x14000c1d3  xor     eax, eax
0x14000c1d5  add     rsp, 38h
0x14000c1d9  pop     r15
0x14000c1db  pop     rdi
0x14000c1dc  pop     rsi
0x14000c1dd  pop     rbx
0x14000c1de  retn
```
