# TlmWriteAccessDeniedForAddSubDirectory

- ea: `0x140015660`
- end: `0x1400158e2`
- name: `TlmWriteAccessDeniedForAddSubDirectory`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400608bc`

## callees

- `0x140001040`
- `0x1400081a4`
- `0x14000b5fc`
- `0x140015660`
- `0x14001e1c0`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015691`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140015691`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140015838`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140015838`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400157ba`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400157ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400158bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400158bb`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400157a6`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400157a6`

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
      if ( **(_DWORD **)&qword_1400295A8 > 5u && tlgKeywordOn(*(__int64 *)&qword_1400295A8, 0x400000000000LL) )
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
        tlgWriteTransfer_EtwWriteTransfer(v4, (unsigned __int8 *)word_140022C3A, 0, 0, 8u, &v11);
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
      v6 = 0;
      v16 = &v8;
      v15 = 4;
      v8 = 0x1000000;
      v17 = 8;
      tlgWriteAgg(v1, (unsigned __int8 *)&unk_140022DC8, v1, 5u, &v11);
    }
  }
}

```

## disassembly

```asm
0x140015660  push    rbp
0x140015662  push    rbx
0x140015663  push    rsi
0x140015664  push    rdi
0x140015665  push    r14
0x140015667  lea     rbp, [rsp-37h]
0x14001566c  sub     rsp, 0F0h
0x140015673  mov     rax, cs:__security_cookie
0x14001567a  xor     rax, rsp
0x14001567d  mov     [rbp+57h+var_30], rax
0x140015681  xor     r14d, r14d
0x140015684  cmp     cs:__TLM, r14b
0x14001568b  jz      loc_1400158C7
0x140015691  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x140015698  nop     dword ptr [rax+rax+00h]
0x14001569d  cmp     rax, cs:qword_1400295C8
0x1400156a4  mov     r8, rax
0x1400156a7  jle     short loc_1400156F3
0x1400156a9  cmp     dword ptr cs:qword_1400295B8+4, 0Ah
0x1400156b0  jl      short loc_1400156F3
0x1400156b2  mov     eax, r14d
0x1400156b5  mov     ecx, r14d
0x1400156b8  xchg    ecx, cs:dword_1400295B0
0x1400156be  mov     edx, r14d
0x1400156c1  mov     ecx, r14d
0x1400156c4  xchg    edx, cs:dword_1400295B4
0x1400156ca  xchg    ecx, dword ptr cs:qword_1400295B8
0x1400156d0  mov     edx, r14d
0x1400156d3  xchg    edx, dword ptr cs:qword_1400295B8+4
0x1400156d9  xchg    eax, cs:dword_1400295C0
0x1400156df  mov     rax, 861C46800h
0x1400156e9  add     rax, r8
0x1400156ec  xchg    rax, cs:qword_1400295C8
0x1400156f3  mov     eax, dword ptr cs:qword_1400295B8+4
0x1400156f9  mov     esi, 1
0x1400156fe  add     eax, esi
0x140015700  mov     dword ptr cs:qword_1400295B8+4, eax
0x140015706  cmp     eax, 0Ah
0x140015709  jl      loc_1400157A1
0x14001570f  mov     r8, cs:qword_1400295A8
0x140015716  mov     eax, [r8]
0x140015719  cmp     eax, 5
0x14001571c  jbe     loc_1400158C7
0x140015722  mov     rdx, 400000000000h
0x14001572c  mov     rcx, r8
0x14001572f  call    _tlgKeywordOn
0x140015734  test    al, al
0x140015736  jz      loc_1400158C7
0x14001573c  lea     rax, [rsp+110h+pImageFileName]
0x140015741  mov     [rsp+110h+pImageFileName], rsi
0x140015746  mov     [rbp+57h+var_90], rax
0x14001574a  lea     r9d, [rsi+4]; int
0x14001574e  lea     rax, [rsp+110h+var_E0]
0x140015753  mov     [rbp+57h+var_88], 8
0x14001575b  mov     [rbp+57h+var_80], rax
0x14001575f  lea     rdx, unk_140022DC8; int
0x140015766  lea     rax, [rbp+57h+var_D0]
0x14001576a  mov     [rsp+110h+var_E0], r14d
0x14001576f  mov     [rbp+57h+var_70], rax
0x140015773  mov     rcx, r8; int
0x140015776  lea     rax, [rbp+57h+var_B0]
0x14001577a  mov     [rbp+57h+var_78], 4
0x140015782  mov     [rsp+110h+var_F0], rax; PEVENT_DATA_DESCRIPTOR
0x140015787  mov     [rbp+57h+var_D0], 1000000h
0x14001578f  mov     [rbp+57h+var_68], 8
0x140015797  call    _tlgWriteAgg
0x14001579c  jmp     loc_1400158C7
0x1400157a1  mov     [rsp+110h+pImageFileName], r14
0x1400157a6  call    cs:__imp_IoGetCurrentProcess
0x1400157ad  nop     dword ptr [rax+rax+00h]
0x1400157b2  mov     rcx, rax; Process
0x1400157b5  lea     rdx, [rsp+110h+pImageFileName]; pImageFileName
0x1400157ba  call    cs:__imp_SeLocateProcessImageName
0x1400157c1  nop     dword ptr [rax+rax+00h]
0x1400157c6  test    eax, eax
0x1400157c8  js      short loc_1400157DA
0x1400157ca  mov     rbx, [rsp+110h+pImageFileName]
0x1400157cf  test    rbx, rbx
0x1400157d2  jz      short loc_1400157DA
0x1400157d4  cmp     [rbx+8], r14
0x1400157d8  jnz     short loc_1400157E1
0x1400157da  lea     rbx, TlmMsgNoImagePathFound
0x1400157e1  mov     rdi, cs:qword_1400295A8
0x1400157e8  mov     eax, [rdi]
0x1400157ea  cmp     eax, 5
0x1400157ed  jbe     loc_1400158AF
0x1400157f3  mov     rdx, 400000000000h
0x1400157fd  mov     rcx, rdi
0x140015800  call    _tlgKeywordOn
0x140015805  test    al, al
0x140015807  jz      loc_1400158AF
0x14001580d  lea     rax, [rbp+57h+var_C8]
0x140015811  mov     [rbp+57h+var_C8], rsi
0x140015815  mov     [rbp+57h+var_90], rax
0x140015819  mov     esi, 8
0x14001581e  lea     rax, [rsp+110h+var_E0]
0x140015823  mov     [rbp+57h+var_88], rsi
0x140015827  mov     [rbp+57h+var_80], rax
0x14001582b  mov     [rsp+110h+var_E0], r14d
0x140015830  mov     [rbp+57h+var_78], 4
0x140015838  call    cs:__imp_PsGetCurrentProcessId
0x14001583f  nop     dword ptr [rax+rax+00h]
0x140015844  xor     r9d, r9d
0x140015847  mov     [rbp+57h+var_68], 4
0x14001584f  mov     dword ptr [rbp+57h+var_D0], eax
0x140015852  lea     rdx, word_140022C3A
0x140015859  lea     rax, [rbp+57h+var_D0]
0x14001585d  mov     [rbp+57h+var_58], 2
0x140015865  mov     [rbp+57h+var_70], rax
0x140015869  xor     r8d, r8d
0x14001586c  lea     rax, [rbp+57h+var_48]
0x140015870  mov     [rbp+57h+var_44], r14d
0x140015874  mov     [rbp+57h+var_60], rax
0x140015878  mov     rcx, rdi
0x14001587b  mov     rax, [rbx+8]
0x14001587f  mov     [rbp+57h+var_50], rax
0x140015883  movzx   eax, word ptr [rbx]
0x140015886  mov     [rbp+57h+var_48], eax
0x140015889  lea     rax, [rbp+57h+var_C0]
0x14001588d  mov     [rbp+57h+var_40], rax
0x140015891  lea     rax, [rbp+57h+var_B0]
0x140015895  mov     [rsp+110h+var_E8], rax
0x14001589a  mov     dword ptr [rsp+110h+var_F0], esi
0x14001589e  mov     [rbp+57h+var_C0], 1000000h
0x1400158a6  mov     [rbp+57h+var_38], rsi
0x1400158aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400158af  mov     rcx, [rsp+110h+pImageFileName]; P
0x1400158b4  test    rcx, rcx
0x1400158b7  jz      short loc_1400158C7
0x1400158b9  xor     edx, edx; Tag
0x1400158bb  call    cs:__imp_ExFreePoolWithTag
0x1400158c2  nop     dword ptr [rax+rax+00h]
0x1400158c7  mov     rcx, [rbp+57h+var_30]
0x1400158cb  xor     rcx, rsp; StackCookie
0x1400158ce  call    __security_check_cookie
0x1400158d3  add     rsp, 0F0h
0x1400158da  pop     r14
0x1400158dc  pop     rdi
0x1400158dd  pop     rsi
0x1400158de  pop     rbx
0x1400158df  pop     rbp
0x1400158e0  retn
```
