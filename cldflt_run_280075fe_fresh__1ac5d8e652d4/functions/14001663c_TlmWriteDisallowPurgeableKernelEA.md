# TlmWriteDisallowPurgeableKernelEA

- ea: `0x14001663c`
- end: `0x1400168c4`
- name: `TlmWriteDisallowPurgeableKernelEA`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400801f0`

## callees

- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x14001663c`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001666d`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001666d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001681a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001681a`
- `ntoskrnl!SeLocateProcessImageName` at `0x140016799`
- `ntoskrnl!SeLocateProcessImageName` at `0x140016799`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001689d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001689d`
- `ntoskrnl!IoGetCurrentProcess` at `0x140016785`
- `ntoskrnl!IoGetCurrentProcess` at `0x140016785`

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
      if ( **(_DWORD **)&qword_1400295A8 > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
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
    else if ( **(_DWORD **)&qword_1400295A8 > 5u )
    {
      if ( (unsigned __int8)tlgKeywordOn(*(_QWORD *)&qword_1400295A8, 0x400000000000LL) )
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
        tlgWriteAgg(v1, (unsigned __int8 *)&byte_14002316D, v1, 5u, &v11);
      }
    }
  }
}

```

## disassembly

```asm
0x14001663c  push    rbp
0x14001663e  push    rbx
0x14001663f  push    rsi
0x140016640  push    rdi
0x140016641  push    r14
0x140016643  lea     rbp, [rsp-37h]
0x140016648  sub     rsp, 0F0h
0x14001664f  mov     rax, cs:__security_cookie
0x140016656  xor     rax, rsp
0x140016659  mov     [rbp+57h+var_30], rax
0x14001665d  xor     r14d, r14d
0x140016660  cmp     cs:__TLM, r14b
0x140016667  jz      loc_1400168A9
0x14001666d  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140016674  nop     dword ptr [rax+rax+00h]
0x140016679  cmp     rax, cs:qword_1400295C8
0x140016680  mov     r8, rax
0x140016683  jle     short loc_1400166CF
0x140016685  cmp     cs:dword_1400295C0, 0Ah
0x14001668c  jl      short loc_1400166CF
0x14001668e  mov     eax, r14d
0x140016691  mov     ecx, r14d
0x140016694  xchg    ecx, cs:dword_1400295B0
0x14001669a  mov     edx, r14d
0x14001669d  mov     ecx, r14d
0x1400166a0  xchg    edx, cs:dword_1400295B4
0x1400166a6  xchg    ecx, dword ptr cs:qword_1400295B8
0x1400166ac  mov     edx, r14d
0x1400166af  xchg    edx, dword ptr cs:qword_1400295B8+4
0x1400166b5  xchg    eax, cs:dword_1400295C0
0x1400166bb  mov     rax, 861C46800h
0x1400166c5  add     rax, r8
0x1400166c8  xchg    rax, cs:qword_1400295C8
0x1400166cf  mov     eax, cs:dword_1400295C0
0x1400166d5  mov     esi, 1
0x1400166da  add     eax, esi
0x1400166dc  mov     cs:dword_1400295C0, eax
0x1400166e2  cmp     eax, 0Ah
0x1400166e5  jl      loc_140016780
0x1400166eb  mov     r8, cs:qword_1400295A8
0x1400166f2  mov     eax, [r8]
0x1400166f5  cmp     eax, 5
0x1400166f8  jbe     loc_1400168A9
0x1400166fe  mov     rdx, 400000000000h
0x140016708  mov     rcx, r8
0x14001670b  call    _tlgKeywordOn
0x140016710  test    al, al
0x140016712  jz      loc_1400168A9
0x140016718  lea     rax, [rsp+110h+pImageFileName]
0x14001671d  mov     [rsp+110h+pImageFileName], rsi
0x140016722  mov     [rbp+57h+var_90], rax
0x140016726  lea     r9d, [rsi+4]; int
0x14001672a  lea     rax, [rsp+110h+var_E0]
0x14001672f  mov     [rbp+57h+var_88], 8
0x140016737  mov     [rbp+57h+var_80], rax
0x14001673b  lea     rdx, byte_14002316D; int
0x140016742  lea     rax, [rbp+57h+var_D0]
0x140016746  mov     [rsp+110h+var_E0], 0C000004Fh
0x14001674e  mov     [rbp+57h+var_70], rax
0x140016752  mov     rcx, r8; int
0x140016755  lea     rax, [rbp+57h+var_B0]
0x140016759  mov     [rbp+57h+var_78], 4
0x140016761  mov     [rsp+110h+var_F0], rax; PEVENT_DATA_DESCRIPTOR
0x140016766  mov     [rbp+57h+var_D0], 1000000h
0x14001676e  mov     [rbp+57h+var_68], 8
0x140016776  call    _tlgWriteAgg
0x14001677b  jmp     loc_1400168A9
0x140016780  mov     [rsp+110h+pImageFileName], r14
0x140016785  call    cs:__imp_IoGetCurrentProcess
0x14001678c  nop     dword ptr [rax+rax+00h]
0x140016791  mov     rcx, rax; Process
0x140016794  lea     rdx, [rsp+110h+pImageFileName]; pImageFileName
0x140016799  call    cs:__imp_SeLocateProcessImageName
0x1400167a0  nop     dword ptr [rax+rax+00h]
0x1400167a5  test    eax, eax
0x1400167a7  js      short loc_1400167B9
0x1400167a9  mov     rbx, [rsp+110h+pImageFileName]
0x1400167ae  test    rbx, rbx
0x1400167b1  jz      short loc_1400167B9
0x1400167b3  cmp     [rbx+8], r14
0x1400167b7  jnz     short loc_1400167C0
0x1400167b9  lea     rbx, TlmMsgNoImagePathFound
0x1400167c0  mov     rdi, cs:qword_1400295A8
0x1400167c7  mov     eax, [rdi]
0x1400167c9  cmp     eax, 5
0x1400167cc  jbe     loc_140016891
0x1400167d2  mov     rdx, 400000000000h
0x1400167dc  mov     rcx, rdi
0x1400167df  call    _tlgKeywordOn
0x1400167e4  test    al, al
0x1400167e6  jz      loc_140016891
0x1400167ec  lea     rax, [rbp+57h+var_C8]
0x1400167f0  mov     [rbp+57h+var_C8], rsi
0x1400167f4  mov     [rbp+57h+var_90], rax
0x1400167f8  mov     esi, 8
0x1400167fd  lea     rax, [rsp+110h+var_E0]
0x140016802  mov     [rbp+57h+var_88], rsi
0x140016806  mov     [rbp+57h+var_80], rax
0x14001680a  mov     [rsp+110h+var_E0], 0C000004Fh
0x140016812  mov     [rbp+57h+var_78], 4
0x14001681a  call    cs:__imp_PsGetCurrentProcessId
0x140016821  nop     dword ptr [rax+rax+00h]
0x140016826  xor     r9d, r9d
0x140016829  mov     [rbp+57h+var_68], 4
0x140016831  mov     dword ptr [rbp+57h+var_D0], eax
0x140016834  lea     rdx, byte_1400231C9
0x14001683b  lea     rax, [rbp+57h+var_D0]
0x14001683f  mov     [rbp+57h+var_58], 2
0x140016847  mov     [rbp+57h+var_70], rax
0x14001684b  xor     r8d, r8d
0x14001684e  lea     rax, [rbp+57h+var_48]
0x140016852  mov     [rbp+57h+var_44], r14d
0x140016856  mov     [rbp+57h+var_60], rax
0x14001685a  mov     rcx, rdi
0x14001685d  mov     rax, [rbx+8]
0x140016861  mov     [rbp+57h+var_50], rax
0x140016865  movzx   eax, word ptr [rbx]
0x140016868  mov     [rbp+57h+var_48], eax
0x14001686b  lea     rax, [rbp+57h+var_C0]
0x14001686f  mov     [rbp+57h+var_40], rax
0x140016873  lea     rax, [rbp+57h+var_B0]
0x140016877  mov     [rsp+110h+var_E8], rax
0x14001687c  mov     dword ptr [rsp+110h+var_F0], esi
0x140016880  mov     [rbp+57h+var_C0], 1000000h
0x140016888  mov     [rbp+57h+var_38], rsi
0x14001688c  call    _tlgWriteTransfer_EtwWriteTransfer
0x140016891  mov     rcx, [rsp+110h+pImageFileName]; P
0x140016896  test    rcx, rcx
0x140016899  jz      short loc_1400168A9
0x14001689b  xor     edx, edx; Tag
0x14001689d  call    cs:__imp_ExFreePoolWithTag
0x1400168a4  nop     dword ptr [rax+rax+00h]
0x1400168a9  mov     rcx, [rbp+57h+var_30]
0x1400168ad  xor     rcx, rsp; StackCookie
0x1400168b0  call    __security_check_cookie
0x1400168b5  add     rsp, 0F0h
0x1400168bc  pop     r14
0x1400168be  pop     rdi
0x1400168bf  pop     rsi
0x1400168c0  pop     rbx
0x1400168c1  pop     rbp
0x1400168c2  retn
```
