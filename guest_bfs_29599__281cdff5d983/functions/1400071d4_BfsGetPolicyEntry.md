# BfsGetPolicyEntry

- ea: `0x1400071d4`
- end: `0x1400073da`
- name: `BfsGetPolicyEntry`
- size: `518`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140005768`
- `0x140005edc`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`
- `0x14000c7e8`
- `0x14000dc70`

## callees

- `0x140001008`
- `0x1400017b0`
- `0x1400061d0`
- `0x1400071d4`
- `0x140007fec`
- `0x140008e38`
- `0x140012d00`
- `0x140013860`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400072f5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400072f5`
- `ntoskrnl!RtlLengthSid` at `0x14000721b`
- `ntoskrnl!RtlLengthSid` at `0x140007238`
- `ntoskrnl!RtlLengthSid` at `0x14000721b`
- `ntoskrnl!RtlLengthSid` at `0x140007238`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140007276`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140007276`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400072bf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000735c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400072bf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000735c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007265`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140007265`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400072cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007368`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400072cb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140007368`

## pseudocode

```c
__int64 __fastcall BfsGetPolicyEntry(__int64 a1, __int64 a2, __int64 a3, void *a4, PSID Sid, __int64 *a6)
{
  ULONG v9; // eax
  ULONG v10; // eax
  __int64 v11; // r12
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // edi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  __int64 result; // rax
  int Timeout; // [rsp+20h] [rbp-69h]
  __int64 v20; // [rsp+40h] [rbp-49h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h]
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v23; // [rsp+70h] [rbp-19h]
  __int64 v24; // [rsp+78h] [rbp-11h]

  v21 = a2;
  v20 = 0;
  v9 = RtlLengthSid(a4);
  BfsUpdateHash(a4, v9, &v20);
  v10 = RtlLengthSid(Sid);
  BfsUpdateHash(Sid, v10, &v20);
  v11 = BfsFinalHash(&v20);
  *a6 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(a3, 0);
  v12 = BfsLookupPolicyEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a3 + 8));
  v20 = v12;
  v13 = v12;
  if ( v12 && (*(_DWORD *)(v12 + 56) & 0x10000000) != 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 144));
    v14 = 0;
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
    if ( *(_DWORD *)(v13 + 56) == 268435457 )
    {
      KeWaitForSingleObject(*(PVOID *)(v13 + 40), Executive, 0, 0, 0);
      if ( *(_DWORD *)(v13 + 56) != 0x10000000 )
      {
        v14 = -1073741823;
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v20) = -1073741823;
          v23 = &v20;
          v24 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v16, v17, Timeout, &v22);
        }
        if ( v13 )
          BfsDereferencePolicyEntryEx((PVOID)v13);
        return v14;
      }
    }
  }
  else
  {
    ExReleasePushLockSharedEx(a3, 0);
    KeLeaveCriticalRegion();
    result = BfsInsertPolicyEntry(a1, v21, a3, v11, (unsigned __int8 *)a4, (unsigned __int8 *)Sid, &v20);
    v14 = result;
    if ( (int)result < 0 )
      return result;
    v13 = v20;
  }
  _InterlockedExchange64((volatile __int64 *)(v13 + 96), MEMORY[0xFFFFF78000000014]);
  *a6 = v13;
  return v14;
}

```

## disassembly

```asm
0x1400071d4  push    rbp
0x1400071d6  push    rbx
0x1400071d7  push    rsi
0x1400071d8  push    rdi
0x1400071d9  push    r12
0x1400071db  push    r13
0x1400071dd  push    r14
0x1400071df  push    r15
0x1400071e1  lea     rbp, [rsp-0Fh]
0x1400071e6  sub     rsp, 98h
0x1400071ed  mov     rax, cs:__security_cookie
0x1400071f4  xor     rax, rsp
0x1400071f7  mov     [rbp+47h+var_50], rax
0x1400071fb  mov     r14, [rbp+47h+Sid]
0x1400071ff  mov     r13, rcx
0x140007202  mov     r15, [rbp+47h+arg_28]
0x140007206  mov     rcx, r9; Sid
0x140007209  mov     rdi, r9
0x14000720c  mov     [rbp+47h+var_88], rdx
0x140007210  mov     rsi, r8
0x140007213  mov     [rbp+47h+var_90], 0
0x14000721b  call    cs:__imp_RtlLengthSid
0x140007222  nop     dword ptr [rax+rax+00h]
0x140007227  lea     r8, [rbp+47h+var_90]
0x14000722b  mov     rcx, rdi
0x14000722e  mov     edx, eax
0x140007230  call    BfsUpdateHash
0x140007235  mov     rcx, r14; Sid
0x140007238  call    cs:__imp_RtlLengthSid
0x14000723f  nop     dword ptr [rax+rax+00h]
0x140007244  lea     r8, [rbp+47h+var_90]
0x140007248  mov     rcx, r14
0x14000724b  mov     edx, eax
0x14000724d  call    BfsUpdateHash
0x140007252  lea     rcx, [rbp+47h+var_90]
0x140007256  call    BfsFinalHash
0x14000725b  mov     r12, rax
0x14000725e  mov     qword ptr [r15], 0
0x140007265  call    cs:__imp_KeEnterCriticalRegion
0x14000726c  nop     dword ptr [rax+rax+00h]
0x140007271  xor     edx, edx
0x140007273  mov     rcx, rsi
0x140007276  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000727d  nop     dword ptr [rax+rax+00h]
0x140007282  mov     rcx, [rsi+8]; HashTable
0x140007286  mov     r9, r14
0x140007289  mov     r8, rdi
0x14000728c  mov     rdx, r12
0x14000728f  call    BfsLookupPolicyEntryHashTable
0x140007294  mov     [rbp+47h+var_90], rax
0x140007298  mov     rbx, rax
0x14000729b  test    rax, rax
0x14000729e  jz      loc_140007357
0x1400072a4  test    dword ptr [rax+38h], 10000000h
0x1400072ab  jz      loc_140007357
0x1400072b1  lock inc dword ptr [rax+90h]
0x1400072b8  xor     edx, edx
0x1400072ba  mov     rcx, rsi
0x1400072bd  xor     edi, edi
0x1400072bf  call    cs:__imp_ExReleasePushLockSharedEx
0x1400072c6  nop     dword ptr [rax+rax+00h]
0x1400072cb  call    cs:__imp_KeLeaveCriticalRegion
0x1400072d2  nop     dword ptr [rax+rax+00h]
0x1400072d7  cmp     dword ptr [rbx+38h], 10000001h
0x1400072de  jnz     loc_1400073A3
0x1400072e4  mov     rcx, [rbx+28h]; Object
0x1400072e8  xor     r9d, r9d; Alertable
0x1400072eb  xor     r8d, r8d; WaitMode
0x1400072ee  mov     [rsp+0D0h+Timeout], rdi; int
0x1400072f3  xor     edx, edx; WaitReason
0x1400072f5  call    cs:__imp_KeWaitForSingleObject
0x1400072fc  nop     dword ptr [rax+rax+00h]
0x140007301  cmp     dword ptr [rbx+38h], 10000000h
0x140007308  jz      loc_1400073A3
0x14000730e  mov     eax, cs:dword_140019000
0x140007314  mov     edi, 0C0000001h
0x140007319  cmp     eax, 3
0x14000731c  jbe     short loc_140007346
0x14000731e  lea     rax, [rbp+47h+var_90]
0x140007322  mov     dword ptr [rbp+47h+var_90], edi
0x140007325  mov     [rbp+47h+var_60], rax
0x140007329  lea     rdx, byte_140016D91; int
0x140007330  lea     rax, [rbp+47h+var_80]
0x140007334  mov     [rbp+47h+var_58], 4
0x14000733c  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x140007341  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007346  test    rbx, rbx
0x140007349  jz      short loc_1400073B7
0x14000734b  xor     edx, edx
0x14000734d  mov     rcx, rbx; P
0x140007350  call    BfsDereferencePolicyEntryEx
0x140007355  jmp     short loc_1400073B7
0x140007357  xor     edx, edx
0x140007359  mov     rcx, rsi
0x14000735c  call    cs:__imp_ExReleasePushLockSharedEx
0x140007363  nop     dword ptr [rax+rax+00h]
0x140007368  call    cs:__imp_KeLeaveCriticalRegion
0x14000736f  nop     dword ptr [rax+rax+00h]
0x140007374  mov     rdx, [rbp+47h+var_88]
0x140007378  lea     rax, [rbp+47h+var_90]
0x14000737c  mov     [rsp+0D0h+var_A0], rax
0x140007381  mov     r9, r12
0x140007384  mov     [rsp+0D0h+var_A8], r14
0x140007389  mov     r8, rsi
0x14000738c  mov     rcx, r13
0x14000738f  mov     [rsp+0D0h+Timeout], rdi
0x140007394  call    BfsInsertPolicyEntry
0x140007399  mov     edi, eax
0x14000739b  test    eax, eax
0x14000739d  js      short loc_1400073B9
0x14000739f  mov     rbx, [rbp+47h+var_90]
0x1400073a3  mov     rax, 0FFFFF78000000014h
0x1400073ad  mov     rax, [rax]
0x1400073b0  xchg    rax, [rbx+60h]
0x1400073b4  mov     [r15], rbx
0x1400073b7  mov     eax, edi
0x1400073b9  mov     rcx, [rbp+47h+var_50]
0x1400073bd  xor     rcx, rsp; StackCookie
0x1400073c0  call    __security_check_cookie
0x1400073c5  add     rsp, 98h
0x1400073cc  pop     r15
0x1400073ce  pop     r14
0x1400073d0  pop     r13
0x1400073d2  pop     r12
0x1400073d4  pop     rdi
0x1400073d5  pop     rsi
0x1400073d6  pop     rbx
0x1400073d7  pop     rbp
0x1400073d8  retn
```
