# MRxSmb2QueryNetworkOpenInformationByName

- ea: `0x140032420`
- end: `0x140032639`
- name: `MRxSmb2QueryNetworkOpenInformationByName`
- size: `537`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1400286c0`
- `0x140029084`
- `0x140032420`

## import_xrefs

- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x1400325d2`
- `mrxsmb!SmbCseDereferenceCompoundingKey` at `0x1400325d2`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140032589`
- `mrxsmb!SmbCseReleaseCompoundingKey` at `0x140032589`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140032483`
- `mrxsmb!SmbCseAllocateCompoundingKey` at `0x140032483`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x14003255c`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x14003255c`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400325a9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400325be`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400325a9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x1400325be`
- `mrxsmb!SmbCeInitiateExchange` at `0x140032578`
- `mrxsmb!SmbCeInitiateExchange` at `0x140032578`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400324e7`
- `mrxsmb!SmbCeInitializeExchange` at `0x1400324e7`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryNetworkOpenInformationByName(__int64 a1, unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  unsigned __int16 *v4; // rsi
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 CompoundingKey; // r14
  int v12; // ebx
  char v13; // si
  int v14; // eax
  __int64 v16; // [rsp+80h] [rbp+38h] BYREF

  v4 = a2;
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  v16 = 0;
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(a4) = -76;
    McTemplateK0uq_EtwWriteTransfer(a1, a2, a1 + 412, a4, 0);
  }
  if ( !v4 )
    v4 = (unsigned __int16 *)(*(_QWORD *)(a1 + 56) + 360LL);
  CompoundingKey = SmbCseAllocateCompoundingKey(32);
  if ( !CompoundingKey )
  {
    v12 = -1073741670;
    v13 = 30;
LABEL_15:
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(v9, (unsigned int)CreateFileError, a1 + 412, v12, v13, 0);
    goto LABEL_17;
  }
  v14 = *v4;
  v16 = 0;
  v12 = SmbCeInitializeExchange(&v16, a1, 0, 0, 0, v7, ((v14 + 9) & 0xFFFFFFF8) + 4096, &CheckPathDispatch);
  if ( v12 )
  {
    v13 = 48;
  }
  else
  {
    if ( (*(_DWORD *)(v6 + 72) & 1) != 0 )
      _InterlockedOr((volatile signed __int32 *)(v16 + 68), 0x8000u);
    *(_QWORD *)(v16 + 3792) = v4;
    *(_BYTE *)(v16 + 3800) = 0;
    *(_QWORD *)(v16 + 3808) = *(_QWORD *)(a1 + 456);
    *(_DWORD *)(v16 + 3816) = *(_DWORD *)(a1 + 472);
    SmbCeAssociateExchangeWithCompoundingKeyEx(v16, CompoundingKey, 0xFFFF);
    _InterlockedOr((volatile signed __int32 *)(v16 + 68), 0x81u);
    v12 = SmbCeInitiateExchange(v16);
    SmbCseReleaseCompoundingKey(CompoundingKey);
    if ( v12 == 259 )
    {
      v12 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v16, 0, 0, 0);
      v13 = 77;
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v16, 0, 0, 0);
      v13 = 70;
    }
  }
  SmbCseDereferenceCompoundingKey(CompoundingKey);
  if ( v12 < 0 )
    goto LABEL_15;
LABEL_17:
  if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 )
  {
    LOBYTE(v10) = -75;
    McTemplateK0uq_EtwWriteTransfer(v9, v8, a1 + 412, v10, v12);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140032420  push    rbp
0x140032422  push    rbx
0x140032423  push    rsi
0x140032424  push    rdi
0x140032425  push    r14
0x140032427  push    r15
0x140032429  mov     rbp, rsp
0x14003242c  sub     rsp, 48h
0x140032430  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 2
0x140032437  mov     rsi, rdx
0x14003243a  mov     rax, [rcx+48h]
0x14003243e  mov     rdi, rcx
0x140032441  mov     r15, [rcx+40h]
0x140032445  mov     r8, [rax+28h]
0x140032449  mov     rbx, [r8+28h]
0x14003244d  mov     [rbp+arg_0], 0
0x140032455  jz      short loc_14003246E
0x140032457  lea     r8, [rcx+19Ch]
0x14003245e  mov     dword ptr [rsp+48h+var_28], 0
0x140032466  mov     r9b, 0B4h
0x140032469  call    McTemplateK0uq_EtwWriteTransfer
0x14003246e  test    rsi, rsi
0x140032471  jnz     short loc_14003247E
0x140032473  mov     rsi, [rdi+38h]
0x140032477  add     rsi, 168h
0x14003247e  mov     ecx, 20h ; ' '
0x140032483  call    cs:__imp_SmbCseAllocateCompoundingKey
0x14003248a  nop     dword ptr [rax+rax+00h]
0x14003248f  mov     r14, rax
0x140032492  test    rax, rax
0x140032495  jnz     short loc_1400324A6
0x140032497  mov     ebx, 0C000009Ah
0x14003249c  mov     esi, 2040031Eh
0x1400324a1  jmp     loc_1400325E2
0x1400324a6  movzx   eax, word ptr [rsi]
0x1400324a9  lea     rcx, CheckPathDispatch
0x1400324b0  mov     [rsp+48h+var_10], rcx
0x1400324b5  add     eax, 9
0x1400324b8  and     eax, 0FFFFFFF8h
0x1400324bb  mov     [rbp+arg_0], 0
0x1400324c3  add     eax, 1000h
0x1400324c8  lea     rcx, [rbp+arg_0]
0x1400324cc  mov     [rsp+48h+var_18], eax
0x1400324d0  xor     r9d, r9d
0x1400324d3  mov     [rsp+48h+var_20], rbx
0x1400324d8  xor     r8d, r8d
0x1400324db  mov     rdx, rdi
0x1400324de  mov     [rsp+48h+var_28], 0
0x1400324e7  call    cs:__imp_SmbCeInitializeExchange
0x1400324ee  nop     dword ptr [rax+rax+00h]
0x1400324f3  mov     ebx, eax
0x1400324f5  test    eax, eax
0x1400324f7  jz      short loc_140032503
0x1400324f9  mov     esi, 20400330h
0x1400324fe  jmp     loc_1400325CF
0x140032503  mov     eax, [r15+48h]
0x140032507  test    al, 1
0x140032509  jz      short loc_140032517
0x14003250b  mov     rax, [rbp+arg_0]
0x14003250f  lock or dword ptr [rax+44h], 8000h
0x140032517  mov     rax, [rbp+arg_0]
0x14003251b  mov     r8d, 0FFFFh
0x140032521  mov     rdx, r14
0x140032524  mov     [rax+0ED0h], rsi
0x14003252b  mov     rax, [rbp+arg_0]
0x14003252f  mov     byte ptr [rax+0ED8h], 0
0x140032536  mov     rcx, [rdi+1C8h]
0x14003253d  mov     rax, [rbp+arg_0]
0x140032541  mov     [rax+0EE0h], rcx
0x140032548  mov     ecx, [rdi+1D8h]
0x14003254e  mov     rax, [rbp+arg_0]
0x140032552  mov     [rax+0EE8h], ecx
0x140032558  mov     rcx, [rbp+arg_0]
0x14003255c  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140032563  nop     dword ptr [rax+rax+00h]
0x140032568  mov     rax, [rbp+arg_0]
0x14003256c  lock or dword ptr [rax+44h], 81h
0x140032574  mov     rcx, [rbp+arg_0]
0x140032578  call    cs:__imp_SmbCeInitiateExchange
0x14003257f  nop     dword ptr [rax+rax+00h]
0x140032584  mov     rcx, r14
0x140032587  mov     ebx, eax
0x140032589  call    cs:__imp_SmbCseReleaseCompoundingKey
0x140032590  nop     dword ptr [rax+rax+00h]
0x140032595  mov     rcx, [rbp+arg_0]
0x140032599  xor     r9d, r9d
0x14003259c  xor     r8d, r8d
0x14003259f  xor     edx, edx
0x1400325a1  cmp     ebx, 103h
0x1400325a7  jnz     short loc_1400325BE
0x1400325a9  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400325b0  nop     dword ptr [rax+rax+00h]
0x1400325b5  mov     ebx, eax
0x1400325b7  mov     esi, 2040034Dh
0x1400325bc  jmp     short loc_1400325CF
0x1400325be  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x1400325c5  nop     dword ptr [rax+rax+00h]
0x1400325ca  mov     esi, 20400346h
0x1400325cf  mov     rcx, r14
0x1400325d2  call    cs:__imp_SmbCseDereferenceCompoundingKey
0x1400325d9  nop     dword ptr [rax+rax+00h]
0x1400325de  test    ebx, ebx
0x1400325e0  jns     short loc_14003260D
0x1400325e2  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 1
0x1400325e9  jz      short loc_14003260D
0x1400325eb  lea     r8, [rdi+19Ch]
0x1400325f2  mov     dword ptr [rsp+48h+var_20], 0
0x1400325fa  mov     r9d, ebx
0x1400325fd  mov     dword ptr [rsp+48h+var_28], esi
0x140032601  lea     rdx, CreateFileError
0x140032608  call    McTemplateK0qqq_EtwWriteTransfer
0x14003260d  test    byte ptr cs:WPP_MAIN_CB.Queue+10h, 2
0x140032614  jz      short loc_140032629
0x140032616  lea     r8, [rdi+19Ch]
0x14003261d  mov     dword ptr [rsp+48h+var_28], ebx
0x140032621  mov     r9b, 0B5h
0x140032624  call    McTemplateK0uq_EtwWriteTransfer
0x140032629  mov     eax, ebx
0x14003262b  add     rsp, 48h
0x14003262f  pop     r15
0x140032631  pop     r14
0x140032633  pop     rdi
0x140032634  pop     rsi
0x140032635  pop     rbx
0x140032636  pop     rbp
0x140032637  retn
```
