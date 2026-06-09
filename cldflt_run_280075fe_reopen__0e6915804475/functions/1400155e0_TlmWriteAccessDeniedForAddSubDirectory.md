# TlmWriteAccessDeniedForAddSubDirectory

- ea: `0x1400155e0`
- end: `0x140015862`
- name: `TlmWriteAccessDeniedForAddSubDirectory`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14006079c`

## callees

- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x1400155e0`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015611`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015611`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400157b8`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400157b8`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001573a`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001573a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001583b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001583b`
- `ntoskrnl!IoGetCurrentProcess` at `0x140015726`
- `ntoskrnl!IoGetCurrentProcess` at `0x140015726`

## pseudocode

```c
void TlmWriteAccessDeniedForAddSubDirectory()
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
    if ( UnbiasedInterruptTime > qword_1400295C8 && SHIDWORD(qword_1400295B8) >= 10 )
    {
      _InterlockedExchange(&dword_1400295B0, 0);
      _InterlockedExchange(&dword_1400295B4, 0);
      _InterlockedExchange((volatile __int32 *)&qword_1400295B8, 0);
      _InterlockedExchange((_DWORD *)&qword_1400295B8 + 1, 0);
      _InterlockedExchange(&dword_1400295C0, 0);
      _InterlockedExchange64(&qword_1400295C8, UnbiasedInterruptTime + 36000000000LL);
    }
    ++HIDWORD(qword_1400295B8);
    if ( SHIDWORD(qword_1400295B8) < 10 )
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
        v6 = 0;
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
        tlgWriteTransfer_EtwWriteTransfer(v4, (unsigned __int8 *)byte_140022BDF, 0, 0, 8u, &v11);
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
        v6 = 0;
        v16 = &v8;
        v15 = 4;
        v8 = 0x1000000;
        v17 = 8;
        tlgWriteAgg(v1, (unsigned __int8 *)&unk_140022DC8, v1, 5u, &v11);
      }
    }
  }
}

```

## disassembly

```asm
0x1400155e0  push    rbp
0x1400155e2  push    rbx
0x1400155e3  push    rsi
0x1400155e4  push    rdi
0x1400155e5  push    r14
0x1400155e7  lea     rbp, [rsp-37h]
0x1400155ec  sub     rsp, 0F0h
0x1400155f3  mov     rax, cs:__security_cookie
0x1400155fa  xor     rax, rsp
0x1400155fd  mov     [rbp+57h+var_30], rax
0x140015601  xor     r14d, r14d
0x140015604  cmp     cs:__TLM, r14b
0x14001560b  jz      loc_140015847
0x140015611  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140015618  nop     dword ptr [rax+rax+00h]
0x14001561d  cmp     rax, cs:qword_1400295C8
0x140015624  mov     r8, rax
0x140015627  jle     short loc_140015673
0x140015629  cmp     dword ptr cs:qword_1400295B8+4, 0Ah
0x140015630  jl      short loc_140015673
0x140015632  mov     eax, r14d
0x140015635  mov     ecx, r14d
0x140015638  xchg    ecx, cs:dword_1400295B0
0x14001563e  mov     edx, r14d
0x140015641  mov     ecx, r14d
0x140015644  xchg    edx, cs:dword_1400295B4
0x14001564a  xchg    ecx, dword ptr cs:qword_1400295B8
0x140015650  mov     edx, r14d
0x140015653  xchg    edx, dword ptr cs:qword_1400295B8+4
0x140015659  xchg    eax, cs:dword_1400295C0
0x14001565f  mov     rax, 861C46800h
0x140015669  add     rax, r8
0x14001566c  xchg    rax, cs:qword_1400295C8
0x140015673  mov     eax, dword ptr cs:qword_1400295B8+4
0x140015679  mov     esi, 1
0x14001567e  add     eax, esi
0x140015680  mov     dword ptr cs:qword_1400295B8+4, eax
0x140015686  cmp     eax, 0Ah
0x140015689  jl      loc_140015721
0x14001568f  mov     r8, cs:qword_1400295A8
0x140015696  mov     eax, [r8]
0x140015699  cmp     eax, 5
0x14001569c  jbe     loc_140015847
0x1400156a2  mov     rdx, 400000000000h
0x1400156ac  mov     rcx, r8
0x1400156af  call    _tlgKeywordOn
0x1400156b4  test    al, al
0x1400156b6  jz      loc_140015847
0x1400156bc  lea     rax, [rsp+110h+pImageFileName]
0x1400156c1  mov     [rsp+110h+pImageFileName], rsi
0x1400156c6  mov     [rbp+57h+var_90], rax
0x1400156ca  lea     r9d, [rsi+4]; int
0x1400156ce  lea     rax, [rsp+110h+var_E0]
0x1400156d3  mov     [rbp+57h+var_88], 8
0x1400156db  mov     [rbp+57h+var_80], rax
0x1400156df  lea     rdx, unk_140022DC8; int
0x1400156e6  lea     rax, [rbp+57h+var_D0]
0x1400156ea  mov     [rsp+110h+var_E0], r14d
0x1400156ef  mov     [rbp+57h+var_70], rax
0x1400156f3  mov     rcx, r8; int
0x1400156f6  lea     rax, [rbp+57h+var_B0]
0x1400156fa  mov     [rbp+57h+var_78], 4
0x140015702  mov     [rsp+110h+var_F0], rax; PEVENT_DATA_DESCRIPTOR
0x140015707  mov     [rbp+57h+var_D0], 1000000h
0x14001570f  mov     [rbp+57h+var_68], 8
0x140015717  call    _tlgWriteAgg
0x14001571c  jmp     loc_140015847
0x140015721  mov     [rsp+110h+pImageFileName], r14
0x140015726  call    cs:__imp_IoGetCurrentProcess
0x14001572d  nop     dword ptr [rax+rax+00h]
0x140015732  mov     rcx, rax; Process
0x140015735  lea     rdx, [rsp+110h+pImageFileName]; pImageFileName
0x14001573a  call    cs:__imp_SeLocateProcessImageName
0x140015741  nop     dword ptr [rax+rax+00h]
0x140015746  test    eax, eax
0x140015748  js      short loc_14001575A
0x14001574a  mov     rbx, [rsp+110h+pImageFileName]
0x14001574f  test    rbx, rbx
0x140015752  jz      short loc_14001575A
0x140015754  cmp     [rbx+8], r14
0x140015758  jnz     short loc_140015761
0x14001575a  lea     rbx, TlmMsgNoImagePathFound
0x140015761  mov     rdi, cs:qword_1400295A8
0x140015768  mov     eax, [rdi]
0x14001576a  cmp     eax, 5
0x14001576d  jbe     loc_14001582F
0x140015773  mov     rdx, 400000000000h
0x14001577d  mov     rcx, rdi
0x140015780  call    _tlgKeywordOn
0x140015785  test    al, al
0x140015787  jz      loc_14001582F
0x14001578d  lea     rax, [rbp+57h+var_C8]
0x140015791  mov     [rbp+57h+var_C8], rsi
0x140015795  mov     [rbp+57h+var_90], rax
0x140015799  mov     esi, 8
0x14001579e  lea     rax, [rsp+110h+var_E0]
0x1400157a3  mov     [rbp+57h+var_88], rsi
0x1400157a7  mov     [rbp+57h+var_80], rax
0x1400157ab  mov     [rsp+110h+var_E0], r14d
0x1400157b0  mov     [rbp+57h+var_78], 4
0x1400157b8  call    cs:__imp_PsGetCurrentProcessId
0x1400157bf  nop     dword ptr [rax+rax+00h]
0x1400157c4  xor     r9d, r9d
0x1400157c7  mov     [rbp+57h+var_68], 4
0x1400157cf  mov     dword ptr [rbp+57h+var_D0], eax
0x1400157d2  lea     rdx, byte_140022BDF
0x1400157d9  lea     rax, [rbp+57h+var_D0]
0x1400157dd  mov     [rbp+57h+var_58], 2
0x1400157e5  mov     [rbp+57h+var_70], rax
0x1400157e9  xor     r8d, r8d
0x1400157ec  lea     rax, [rbp+57h+var_48]
0x1400157f0  mov     [rbp+57h+var_44], r14d
0x1400157f4  mov     [rbp+57h+var_60], rax
0x1400157f8  mov     rcx, rdi
0x1400157fb  mov     rax, [rbx+8]
0x1400157ff  mov     [rbp+57h+var_50], rax
0x140015803  movzx   eax, word ptr [rbx]
0x140015806  mov     [rbp+57h+var_48], eax
0x140015809  lea     rax, [rbp+57h+var_C0]
0x14001580d  mov     [rbp+57h+var_40], rax
0x140015811  lea     rax, [rbp+57h+var_B0]
0x140015815  mov     [rsp+110h+var_E8], rax
0x14001581a  mov     dword ptr [rsp+110h+var_F0], esi
0x14001581e  mov     [rbp+57h+var_C0], 1000000h
0x140015826  mov     [rbp+57h+var_38], rsi
0x14001582a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001582f  mov     rcx, [rsp+110h+pImageFileName]; P
0x140015834  test    rcx, rcx
0x140015837  jz      short loc_140015847
0x140015839  xor     edx, edx; Tag
0x14001583b  call    cs:__imp_ExFreePoolWithTag
0x140015842  nop     dword ptr [rax+rax+00h]
0x140015847  mov     rcx, [rbp+57h+var_30]
0x14001584b  xor     rcx, rsp; StackCookie
0x14001584e  call    __security_check_cookie
0x140015853  add     rsp, 0F0h
0x14001585a  pop     r14
0x14001585c  pop     rdi
0x14001585d  pop     rsi
0x14001585e  pop     rbx
0x14001585f  pop     rbp
0x140015860  retn
```
