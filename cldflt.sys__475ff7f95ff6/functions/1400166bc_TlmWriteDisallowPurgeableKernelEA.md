# TlmWriteDisallowPurgeableKernelEA

- ea: `0x1400166bc`
- end: `0x140016944`
- name: `TlmWriteDisallowPurgeableKernelEA`
- size: `648`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140080390`

## callees

- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x1400166bc`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400166ed`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400166ed`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001689a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001689a`
- `ntoskrnl!SeLocateProcessImageName` at `0x140016819`
- `ntoskrnl!SeLocateProcessImageName` at `0x140016819`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001691d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001691d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140016805`
- `ntoskrnl!IoGetCurrentProcess` at `0x140016805`

## pseudocode

```c
void TlmWriteDisallowPurgeableKernelEA()
{
  signed __int64 UnbiasedInterruptTime; // rax
  __int64 v1; // r8
  struct _KPROCESS *CurrentProcess; // rax
  PUNICODE_STRING v3; // rbx
  __int64 v4; // rdi
  unsigned int CurrentProcessId; // eax
  int v6; // [rsp+30h] [rbp-89h] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+38h] [rbp-81h] BYREF
  __int64 v8; // [rsp+40h] [rbp-79h] BYREF
  __int64 v9; // [rsp+48h] [rbp-71h] BYREF
  __int64 v10; // [rsp+50h] [rbp-69h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+60h] [rbp-59h] BYREF
  PUNICODE_STRING *p_pImageFileName; // [rsp+80h] [rbp-39h]
  __int64 v13; // [rsp+88h] [rbp-31h]
  int *v14; // [rsp+90h] [rbp-29h]
  __int64 v15; // [rsp+98h] [rbp-21h]
  __int64 *v16; // [rsp+A0h] [rbp-19h]
  __int64 v17; // [rsp+A8h] [rbp-11h]
  _DWORD *v18; // [rsp+B0h] [rbp-9h]
  __int64 v19; // [rsp+B8h] [rbp-1h]
  PWSTR Buffer; // [rsp+C0h] [rbp+7h]
  _DWORD v21[2]; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h]
  __int64 v23; // [rsp+D8h] [rbp+1Fh]

  if ( _TLM )
  {
    UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
    if ( UnbiasedInterruptTime > qword_1400295C8 && dword_1400295C0 >= 10 )
    {
      _InterlockedExchange(&dword_1400295B0, 0);
      _InterlockedExchange(&dword_1400295B4, 0);
      _InterlockedExchange((volatile __int32 *)&qword_1400295B8, 0);
      _InterlockedExchange((_DWORD *)&qword_1400295B8 + 1, 0);
      _InterlockedExchange(&dword_1400295C0, 0);
      _InterlockedExchange64(&qword_1400295C8, UnbiasedInterruptTime + 36000000000LL);
    }
    if ( ++dword_1400295C0 < 10 )
    {
      pImageFileName = 0;
      CurrentProcess = IoGetCurrentProcess();
      if ( SeLocateProcessImageName(CurrentProcess, &pImageFileName) < 0
        || (v3 = pImageFileName) == 0
        || !pImageFileName->Buffer )
      {
        v3 = (PUNICODE_STRING)&TlmMsgNoImagePathFound;
      }
      v4 = *(_QWORD *)&qword_1400295A8;
      if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
      {
        v9 = 1;
        p_pImageFileName = (PUNICODE_STRING *)&v9;
        v13 = 8;
        v14 = &v6;
        v6 = -1073741745;
        v15 = 4;
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        v17 = 4;
        LODWORD(v8) = CurrentProcessId;
        v19 = 2;
        v16 = &v8;
        v21[1] = 0;
        v18 = v21;
        Buffer = v3->Buffer;
        v21[0] = v3->Length;
        v22 = &v10;
        v10 = 0x1000000;
        v23 = 8;
        tlgWriteTransfer_EtwWriteTransfer(v4, (unsigned __int8 *)byte_1400231C9, 0, 0, 8u, &v11);
      }
      if ( pImageFileName )
        ExFreePoolWithTag(pImageFileName, 0);
    }
    else if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
    {
      pImageFileName = (PUNICODE_STRING)1;
      p_pImageFileName = &pImageFileName;
      v13 = 8;
      v14 = &v6;
      v6 = -1073741745;
      v16 = &v8;
      v15 = 4;
      v8 = 0x1000000;
      v17 = 8;
      tlgWriteAgg(v1, (unsigned __int8 *)&word_140023102, v1, 5u, &v11);
    }
  }
}

```

## disassembly

```asm
0x1400166bc  push    rbp
0x1400166be  push    rbx
0x1400166bf  push    rsi
0x1400166c0  push    rdi
0x1400166c1  push    r14
0x1400166c3  lea     rbp, [rsp-37h]
0x1400166c8  sub     rsp, 0F0h
0x1400166cf  mov     rax, cs:__security_cookie
0x1400166d6  xor     rax, rsp
0x1400166d9  mov     [rbp+57h+var_30], rax
0x1400166dd  xor     r14d, r14d
0x1400166e0  cmp     cs:__TLM, r14b
0x1400166e7  jz      loc_140016929
0x1400166ed  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400166f4  nop     dword ptr [rax+rax+00h]
0x1400166f9  cmp     rax, cs:qword_1400295C8
0x140016700  mov     r8, rax
0x140016703  jle     short loc_14001674F
0x140016705  cmp     cs:dword_1400295C0, 0Ah
0x14001670c  jl      short loc_14001674F
0x14001670e  mov     eax, r14d
0x140016711  mov     ecx, r14d
0x140016714  xchg    ecx, cs:dword_1400295B0
0x14001671a  mov     edx, r14d
0x14001671d  mov     ecx, r14d
0x140016720  xchg    edx, cs:dword_1400295B4
0x140016726  xchg    ecx, dword ptr cs:qword_1400295B8
0x14001672c  mov     edx, r14d
0x14001672f  xchg    edx, dword ptr cs:qword_1400295B8+4
0x140016735  xchg    eax, cs:dword_1400295C0
0x14001673b  mov     rax, 861C46800h
0x140016745  add     rax, r8
0x140016748  xchg    rax, cs:qword_1400295C8
0x14001674f  mov     eax, cs:dword_1400295C0
0x140016755  mov     esi, 1
0x14001675a  add     eax, esi
0x14001675c  mov     cs:dword_1400295C0, eax
0x140016762  cmp     eax, 0Ah
0x140016765  jl      loc_140016800
0x14001676b  mov     r8, cs:qword_1400295A8
0x140016772  mov     eax, [r8]
0x140016775  cmp     eax, 5
0x140016778  jbe     loc_140016929
0x14001677e  mov     rdx, 400000000000h
0x140016788  mov     rcx, r8
0x14001678b  call    _tlgKeywordOn
0x140016790  test    al, al
0x140016792  jz      loc_140016929
0x140016798  lea     rax, [rsp+110h+pImageFileName]
0x14001679d  mov     [rsp+110h+pImageFileName], rsi
0x1400167a2  mov     [rbp+57h+var_90], rax
0x1400167a6  lea     r9d, [rsi+4]; int
0x1400167aa  lea     rax, [rsp+110h+var_E0]
0x1400167af  mov     [rbp+57h+var_88], 8
0x1400167b7  mov     [rbp+57h+var_80], rax
0x1400167bb  lea     rdx, word_140023102; int
0x1400167c2  lea     rax, [rbp+57h+var_D0]
0x1400167c6  mov     [rsp+110h+var_E0], 0C000004Fh
0x1400167ce  mov     [rbp+57h+var_70], rax
0x1400167d2  mov     rcx, r8; int
0x1400167d5  lea     rax, [rbp+57h+var_B0]
0x1400167d9  mov     [rbp+57h+var_78], 4
0x1400167e1  mov     [rsp+110h+var_F0], rax; PEVENT_DATA_DESCRIPTOR
0x1400167e6  mov     [rbp+57h+var_D0], 1000000h
0x1400167ee  mov     [rbp+57h+var_68], 8
0x1400167f6  call    _tlgWriteAgg
0x1400167fb  jmp     loc_140016929
0x140016800  mov     [rsp+110h+pImageFileName], r14
0x140016805  call    cs:__imp_IoGetCurrentProcess
0x14001680c  nop     dword ptr [rax+rax+00h]
0x140016811  mov     rcx, rax; Process
0x140016814  lea     rdx, [rsp+110h+pImageFileName]; pImageFileName
0x140016819  call    cs:__imp_SeLocateProcessImageName
0x140016820  nop     dword ptr [rax+rax+00h]
0x140016825  test    eax, eax
0x140016827  js      short loc_140016839
0x140016829  mov     rbx, [rsp+110h+pImageFileName]
0x14001682e  test    rbx, rbx
0x140016831  jz      short loc_140016839
0x140016833  cmp     [rbx+8], r14
0x140016837  jnz     short loc_140016840
0x140016839  lea     rbx, TlmMsgNoImagePathFound
0x140016840  mov     rdi, cs:qword_1400295A8
0x140016847  mov     eax, [rdi]
0x140016849  cmp     eax, 5
0x14001684c  jbe     loc_140016911
0x140016852  mov     rdx, 400000000000h
0x14001685c  mov     rcx, rdi
0x14001685f  call    _tlgKeywordOn
0x140016864  test    al, al
0x140016866  jz      loc_140016911
0x14001686c  lea     rax, [rbp+57h+var_C8]
0x140016870  mov     [rbp+57h+var_C8], rsi
0x140016874  mov     [rbp+57h+var_90], rax
0x140016878  mov     esi, 8
0x14001687d  lea     rax, [rsp+110h+var_E0]
0x140016882  mov     [rbp+57h+var_88], rsi
0x140016886  mov     [rbp+57h+var_80], rax
0x14001688a  mov     [rsp+110h+var_E0], 0C000004Fh
0x140016892  mov     [rbp+57h+var_78], 4
0x14001689a  call    cs:__imp_PsGetCurrentProcessId
0x1400168a1  nop     dword ptr [rax+rax+00h]
0x1400168a6  xor     r9d, r9d
0x1400168a9  mov     [rbp+57h+var_68], 4
0x1400168b1  mov     dword ptr [rbp+57h+var_D0], eax
0x1400168b4  lea     rdx, byte_1400231C9
0x1400168bb  lea     rax, [rbp+57h+var_D0]
0x1400168bf  mov     [rbp+57h+var_58], 2
0x1400168c7  mov     [rbp+57h+var_70], rax
0x1400168cb  xor     r8d, r8d
0x1400168ce  lea     rax, [rbp+57h+var_48]
0x1400168d2  mov     [rbp+57h+var_44], r14d
0x1400168d6  mov     [rbp+57h+var_60], rax
0x1400168da  mov     rcx, rdi
0x1400168dd  mov     rax, [rbx+8]
0x1400168e1  mov     [rbp+57h+var_50], rax
0x1400168e5  movzx   eax, word ptr [rbx]
0x1400168e8  mov     [rbp+57h+var_48], eax
0x1400168eb  lea     rax, [rbp+57h+var_C0]
0x1400168ef  mov     [rbp+57h+var_40], rax
0x1400168f3  lea     rax, [rbp+57h+var_B0]
0x1400168f7  mov     [rsp+110h+var_E8], rax
0x1400168fc  mov     dword ptr [rsp+110h+var_F0], esi
0x140016900  mov     [rbp+57h+var_C0], 1000000h
0x140016908  mov     [rbp+57h+var_38], rsi
0x14001690c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016911  mov     rcx, [rsp+110h+pImageFileName]; P
0x140016916  test    rcx, rcx
0x140016919  jz      short loc_140016929
0x14001691b  xor     edx, edx; Tag
0x14001691d  call    cs:__imp_ExFreePoolWithTag
0x140016924  nop     dword ptr [rax+rax+00h]
0x140016929  mov     rcx, [rbp+57h+var_30]
0x14001692d  xor     rcx, rsp; StackCookie
0x140016930  call    __security_check_cookie
0x140016935  add     rsp, 0F0h
0x14001693c  pop     r14
0x14001693e  pop     rdi
0x14001693f  pop     rsi
0x140016940  pop     rbx
0x140016941  pop     rbp
0x140016942  retn
```
