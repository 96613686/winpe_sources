# TppCallbackCheckThreadAfterCallback

- ea: `0x180018bc0`
- end: `0x180019040`
- name: `TppCallbackCheckThreadAfterCallback`
- size: `1152`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180016fa0`
- `0x180018640`

## callees

- `0x180018bc0`
- `0x1800195a0`
- `0x18001a080`
- `0x18001a0d0`
- `0x1800526f0`
- `0x18015e470`
- `0x18015ee80`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x180018ec9`: `ThreadPool: callback %p(%p) returned with background priorities set\n`
- `0x180018e42`: `ThreadPool: callback %p(%p) returned with preferred languages set\n`
- `0x180018d52`: `ThreadPool: callback %p(%p) returned with a transaction uncleared\n`
- `0x180018de2`: `ThreadPool: callback %p(%p) returned with the loader lock held\n`

## pseudocode

```c
void __fastcall TppCallbackCheckThreadAfterCallback(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _TEB *v5; // rax
  __int64 v6; // rdi
  void *SubProcessTag; // rdx
  _DWORD *SharedData; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  struct _TEB *v11; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  EXCEPTION_RECORD ExceptionRecord; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v14[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v15; // [rsp+100h] [rbp+0h]

  v12 = 0;
  memset(&ExceptionRecord, 0, sizeof(ExceptionRecord));
  if ( a1 )
  {
    NtCurrentTeb()->ActivityId = *(_GUID *)(a1 + 232);
    *(_QWORD *)(a1 + 248) = 0;
    *(_DWORD *)(a1 + 228) |= 2u;
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 && (*(_BYTE *)(a1 + 104) & 1) == 0 )
    {
      RtlDeactivateActivationContextUnsafeFast(a1);
      *(_BYTE *)(a1 + 76) &= ~1u;
    }
    if ( *(_QWORD *)(a1 + 80) && (*(_BYTE *)(a1 + 104) & 2) == 0 )
    {
      v5 = NtCurrentTeb();
      v6 = 2147353488;
      SubProcessTag = v5->SubProcessTag;
      v5->SubProcessTag = 0;
      SharedData = NtCurrentPeb()->SharedData;
      if ( SharedData && *SharedData )
        v9 = (__int64)NtCurrentPeb()->SharedData + 566;
      else
        v9 = 2147353488;
      if ( *(_BYTE *)v9 && SubProcessTag )
      {
        memset(v14, 0, sizeof(v14));
        WORD3(v14[0]) = 1349;
        v15 = (unsigned int)SubProcessTag;
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v9, SubProcessTag, a3, a4) )
          v6 = (__int64)NtCurrentPeb()->SharedData + 566;
        NtTraceEvent(*(unsigned __int8 *)v6, 1026, 8, v14);
      }
      *(_QWORD *)(a1 + 80) = 0;
    }
    v10 = *(_QWORD *)(a1 + 128);
    if ( v10 && (*(_BYTE *)(v10 + 436) & 1) == 0 )
    {
      if ( NtCurrentTeb()->IsImpersonating && (*(_BYTE *)(a1 + 104) & 4) == 0 )
      {
        memset_thunk_772440563353939046(&ExceptionRecord, 0, 0x98u);
        ExceptionRecord.ExceptionInformation[0] = *(_QWORD *)(a1 + 88);
        ExceptionRecord.ExceptionInformation[1] = *(_QWORD *)(a1 + 96);
        ExceptionRecord.ExceptionCode = -1073740016;
        ExceptionRecord.NumberParameters = 2;
        RtlRaiseException(&ExceptionRecord);
        v12 = 0;
        NtSetInformationThread(-2, 5, &v12, 8);
      }
      if ( (*(_BYTE *)(a1 + 104) & 0x10) == 0 )
      {
        v11 = NtCurrentTeb();
        if ( (((unsigned __int64)v11->CurrentTransactionHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
          || v11->TxnScopeEnterCallback
          || v11->TxnScopeExitCallback
          || v11->TxnScopeContext
          || v11->TxFsContext != 65534 )
        {
          DbgPrintEx(
            84,
            0,
            "ThreadPool: callback %p(%p) returned with a transaction uncleared\n",
            *(const void **)(a1 + 88),
            *(const void **)(a1 + 96));
          memset(&ExceptionRecord, 0, sizeof(ExceptionRecord));
          ExceptionRecord.ExceptionCode = -1073740003;
          ExceptionRecord.NumberParameters = 0;
          RtlRaiseException(&ExceptionRecord);
        }
      }
      if ( (*(_BYTE *)(a1 + 104) & 0x20) == 0
        && NtCurrentPeb()->LoaderLock->OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
      {
        DbgPrintEx(
          84,
          0,
          "ThreadPool: callback %p(%p) returned with the loader lock held\n",
          *(const void **)(a1 + 88),
          *(const void **)(a1 + 96));
        memset_thunk_772440563353939046(&ExceptionRecord, 0, 0x98u);
        ExceptionRecord.ExceptionCode = -1073740002;
        ExceptionRecord.NumberParameters = 0;
        RtlRaiseException(&ExceptionRecord);
      }
      if ( (*(_BYTE *)(a1 + 104) & 0x40) == 0 && NtCurrentTeb()->PreferredLanguages )
      {
        DbgPrintEx(
          84,
          0,
          "ThreadPool: callback %p(%p) returned with preferred languages set\n",
          *(const void **)(a1 + 88),
          *(const void **)(a1 + 96));
        memset(&ExceptionRecord, 0, sizeof(ExceptionRecord));
        ExceptionRecord.ExceptionCode = -1073740001;
        ExceptionRecord.NumberParameters = 0;
        RtlRaiseException(&ExceptionRecord);
      }
      if ( *(char *)(a1 + 104) >= 0 )
      {
        if ( NtCurrentTeb()->SavedPriorityState )
        {
          DbgPrintEx(
            84,
            0,
            "ThreadPool: callback %p(%p) returned with background priorities set\n",
            *(const void **)(a1 + 88),
            *(const void **)(a1 + 96));
          memset(&ExceptionRecord, 0, sizeof(ExceptionRecord));
          ExceptionRecord.ExceptionCode = -1073740000;
          ExceptionRecord.NumberParameters = 0;
          RtlRaiseException(&ExceptionRecord);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180018bc0  mov     [rsp-8+arg_10], rbx
0x180018bc5  mov     [rsp-8+arg_18], rsi
0x180018bca  push    rbp
0x180018bcb  lea     rbp, [rsp-10h]
0x180018bd0  sub     rsp, 110h
0x180018bd7  mov     rax, cs:__security_cookie
0x180018bde  xor     rax, rsp
0x180018be1  mov     [rbp+10h+var_8], rax
0x180018be5  xorps   xmm0, xmm0
0x180018be8  xor     eax, eax
0x180018bea  xor     esi, esi
0x180018bec  mov     [rbp+10h+ExceptionRecord.ExceptionInformation+70h], rax
0x180018bf0  mov     [rsp+110h+var_E0], rsi
0x180018bf5  mov     rbx, rcx
0x180018bf8  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionCode], xmm0
0x180018bfd  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionAddress], xmm0
0x180018c02  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation], xmm0
0x180018c07  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation+10h], xmm0
0x180018c0c  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+20h], xmm0
0x180018c10  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+30h], xmm0
0x180018c14  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+40h], xmm0
0x180018c18  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+50h], xmm0
0x180018c1c  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+60h], xmm0
0x180018c20  test    rcx, rcx
0x180018c23  jz      loc_180018CC7
0x180018c29  mov     rax, gs:30h
0x180018c32  movups  xmm0, xmmword ptr [rcx+0E8h]
0x180018c39  movups  xmmword ptr [rax+1710h], xmm0
0x180018c40  xor     eax, eax
0x180018c42  mov     [rcx+0F8h], rax
0x180018c49  or      dword ptr [rcx+0E4h], 2
0x180018c50  test    byte ptr [rcx+4Ch], 1
0x180018c54  jnz     loc_180018FBA
0x180018c5a  cmp     [rbx+50h], rsi
0x180018c5e  jz      short loc_180018CBB
0x180018c60  test    byte ptr [rbx+68h], 2
0x180018c64  jnz     short loc_180018CBB
0x180018c66  mov     rax, gs:30h
0x180018c6f  mov     [rsp+110h+arg_8], rdi
0x180018c77  mov     edi, 7FFE0390h
0x180018c7c  mov     rdx, [rax+1720h]
0x180018c83  mov     [rax+1720h], rsi
0x180018c8a  mov     rax, gs:60h
0x180018c93  mov     rcx, [rax+90h]
0x180018c9a  test    rcx, rcx
0x180018c9d  jnz     loc_180018F31
0x180018ca3  mov     rcx, rdi
0x180018ca6  cmp     [rcx], sil
0x180018ca9  jnz     loc_180018F55
0x180018caf  mov     rdi, [rsp+110h+arg_8]
0x180018cb7  mov     [rbx+50h], rsi
0x180018cbb  mov     rax, [rbx+80h]
0x180018cc2  test    rax, rax
0x180018cc5  jnz     short loc_180018CE9
0x180018cc7  mov     rcx, [rbp+10h+var_8]
0x180018ccb  xor     rcx, rsp; StackCookie
0x180018cce  call    __security_check_cookie
0x180018cd3  lea     r11, [rsp+110h+var_s0]
0x180018cdb  mov     rbx, [r11+20h]
0x180018cdf  mov     rsi, [r11+28h]
0x180018ce3  mov     rsp, r11
0x180018ce6  pop     rbp
0x180018ce7  retn
0x180018ce9  test    byte ptr [rax+1B4h], 1
0x180018cf0  jnz     short loc_180018CC7
0x180018cf2  mov     eax, gs:179Ch
0x180018cfa  test    eax, eax
0x180018cfc  jnz     loc_180018FD2
0x180018d02  test    byte ptr [rbx+68h], 10h
0x180018d06  jnz     loc_180018DB5
0x180018d0c  mov     rcx, gs:30h
0x180018d15  mov     rax, [rcx+17B8h]
0x180018d1c  inc     rax
0x180018d1f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180018d25  jnz     short loc_180018D4E
0x180018d27  cmp     [rcx+17F0h], rsi
0x180018d2e  jnz     short loc_180018D4E
0x180018d30  cmp     [rcx+17F8h], rsi
0x180018d37  jnz     short loc_180018D4E
0x180018d39  cmp     [rcx+1800h], rsi
0x180018d40  jnz     short loc_180018D4E
0x180018d42  cmp     dword ptr [rcx+2E8h], 0FFFEh
0x180018d4c  jz      short loc_180018DB5
0x180018d4e  mov     rax, [rbx+60h]
0x180018d52  lea     r8, aThreadpoolCall; "ThreadPool: callback %p(%p) returned wi"...
0x180018d59  mov     r9, [rbx+58h]
0x180018d5d  xor     edx, edx
0x180018d5f  mov     ecx, 54h ; 'T'
0x180018d64  mov     [rsp+110h+var_F0], rax
0x180018d69  call    DbgPrintEx
0x180018d6e  xorps   xmm0, xmm0
0x180018d71  lea     rcx, [rsp+110h+ExceptionRecord]; ExceptionRecord
0x180018d76  xor     eax, eax
0x180018d78  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionCode], xmm0
0x180018d7d  mov     [rsp+110h+ExceptionRecord.ExceptionCode], 0C000071Dh
0x180018d85  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionAddress], xmm0
0x180018d8a  mov     [rsp+110h+ExceptionRecord.NumberParameters], esi
0x180018d8e  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation], xmm0
0x180018d93  mov     [rbp+10h+ExceptionRecord.ExceptionInformation+70h], rax
0x180018d97  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation+10h], xmm0
0x180018d9c  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+20h], xmm0
0x180018da0  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+30h], xmm0
0x180018da4  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+40h], xmm0
0x180018da8  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+50h], xmm0
0x180018dac  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+60h], xmm0
0x180018db0  call    RtlRaiseException
0x180018db5  test    byte ptr [rbx+68h], 20h
0x180018db9  jnz     short loc_180018E26
0x180018dbb  mov     rax, gs:60h
0x180018dc4  mov     rdx, [rax+110h]
0x180018dcb  mov     rax, gs:30h
0x180018dd4  mov     rcx, [rax+48h]
0x180018dd8  cmp     [rdx+10h], rcx
0x180018ddc  jnz     short loc_180018E26
0x180018dde  mov     rax, [rbx+60h]
0x180018de2  lea     r8, aThreadpoolCall_2; "ThreadPool: callback %p(%p) returned wi"...
0x180018de9  mov     r9, [rbx+58h]
0x180018ded  xor     edx, edx
0x180018def  mov     ecx, 54h ; 'T'
0x180018df4  mov     [rsp+110h+var_F0], rax
0x180018df9  call    DbgPrintEx
0x180018dfe  xor     edx, edx; Val
0x180018e00  lea     rcx, [rsp+110h+ExceptionRecord]; void *
0x180018e05  mov     r8d, 98h; Size
0x180018e0b  call    memset$thunk$772440563353939046
0x180018e10  lea     rcx, [rsp+110h+ExceptionRecord]; ExceptionRecord
0x180018e15  mov     [rsp+110h+ExceptionRecord.ExceptionCode], 0C000071Eh
0x180018e1d  mov     [rsp+110h+ExceptionRecord.NumberParameters], esi
0x180018e21  call    RtlRaiseException
0x180018e26  test    byte ptr [rbx+68h], 40h
0x180018e2a  jnz     short loc_180018EA5
0x180018e2c  mov     rax, gs:30h
0x180018e35  cmp     [rax+17D0h], rsi
0x180018e3c  jz      short loc_180018EA5
0x180018e3e  mov     rax, [rbx+60h]
0x180018e42  lea     r8, aThreadpoolCall_0; "ThreadPool: callback %p(%p) returned wi"...
0x180018e49  mov     r9, [rbx+58h]
0x180018e4d  xor     edx, edx
0x180018e4f  mov     ecx, 54h ; 'T'
0x180018e54  mov     [rsp+110h+var_F0], rax
0x180018e59  call    DbgPrintEx
0x180018e5e  xorps   xmm0, xmm0
0x180018e61  lea     rcx, [rsp+110h+ExceptionRecord]; ExceptionRecord
0x180018e66  xor     eax, eax
0x180018e68  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionCode], xmm0
0x180018e6d  mov     [rsp+110h+ExceptionRecord.ExceptionCode], 0C000071Fh
0x180018e75  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionAddress], xmm0
0x180018e7a  mov     [rsp+110h+ExceptionRecord.NumberParameters], esi
0x180018e7e  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation], xmm0
0x180018e83  mov     [rbp+10h+ExceptionRecord.ExceptionInformation+70h], rax
0x180018e87  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation+10h], xmm0
0x180018e8c  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+20h], xmm0
0x180018e90  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+30h], xmm0
0x180018e94  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+40h], xmm0
0x180018e98  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+50h], xmm0
0x180018e9c  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+60h], xmm0
0x180018ea0  call    RtlRaiseException
0x180018ea5  test    byte ptr [rbx+68h], 80h
0x180018ea9  jnz     loc_180018CC7
0x180018eaf  mov     rax, gs:30h
0x180018eb8  cmp     [rax+1768h], rsi
0x180018ebf  jz      loc_180018CC7
0x180018ec5  mov     rax, [rbx+60h]
0x180018ec9  lea     r8, aThreadpoolCall_1; "ThreadPool: callback %p(%p) returned wi"...
0x180018ed0  mov     r9, [rbx+58h]
0x180018ed4  xor     edx, edx
0x180018ed6  mov     ecx, 54h ; 'T'
0x180018edb  mov     [rsp+110h+var_F0], rax
0x180018ee0  call    DbgPrintEx
0x180018ee5  xorps   xmm0, xmm0
0x180018ee8  lea     rcx, [rsp+110h+ExceptionRecord]; ExceptionRecord
0x180018eed  xor     eax, eax
0x180018eef  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionCode], xmm0
0x180018ef4  mov     [rsp+110h+ExceptionRecord.ExceptionCode], 0C0000720h
0x180018efc  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionAddress], xmm0
0x180018f01  mov     [rsp+110h+ExceptionRecord.NumberParameters], esi
0x180018f05  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation], xmm0
0x180018f0a  mov     [rbp+10h+ExceptionRecord.ExceptionInformation+70h], rax
0x180018f0e  movups  xmmword ptr [rsp+110h+ExceptionRecord.ExceptionInformation+10h], xmm0
0x180018f13  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+20h], xmm0
0x180018f17  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+30h], xmm0
0x180018f1b  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+40h], xmm0
0x180018f1f  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+50h], xmm0
0x180018f23  movups  xmmword ptr [rbp+10h+ExceptionRecord.ExceptionInformation+60h], xmm0
0x180018f27  call    RtlRaiseException
0x180018f2c  jmp     loc_180018CC7
0x180018f31  cmp     [rcx], esi
0x180018f33  jz      loc_180018CA3
0x180018f39  mov     rax, gs:60h
0x180018f42  mov     rcx, [rax+90h]
0x180018f49  add     rcx, 236h
0x180018f50  jmp     loc_180018CA6
0x180018f55  test    rdx, rdx
0x180018f58  jz      loc_180018CAF
0x180018f5e  xor     eax, eax
0x180018f60  xorps   xmm0, xmm0
0x180018f63  mov     [rbp+10h+var_10], rax
0x180018f67  mov     eax, 545h
0x180018f6c  movups  [rbp+10h+var_30], xmm0
0x180018f70  mov     word ptr [rbp+10h+var_30+6], ax
0x180018f74  movups  [rbp+10h+var_20], xmm0
0x180018f78  mov     dword ptr [rbp+10h+var_10], edx
0x180018f7b  mov     dword ptr [rbp+10h+var_10+4], esi
0x180018f7e  call    RtlGetCurrentServiceSessionId
0x180018f83  test    eax, eax
0x180018f85  jz      short loc_180018F9E
0x180018f87  mov     rax, gs:60h
0x180018f90  mov     rdi, [rax+90h]
0x180018f97  add     rdi, 236h
0x180018f9e  movzx   ecx, byte ptr [rdi]
0x180018fa1  lea     r9, [rbp+10h+var_30]
0x180018fa5  mov     edx, 402h
0x180018faa  mov     r8d, 8
0x180018fb0  call    NtTraceEvent
0x180018fb5  jmp     loc_180018CAF
0x180018fba  test    byte ptr [rcx+68h], 1
0x180018fbe  jnz     loc_180018C5A
0x180018fc4  call    RtlDeactivateActivationContextUnsafeFast
0x180018fc9  and     byte ptr [rbx+4Ch], 0FEh
0x180018fcd  jmp     loc_180018C5A
0x180018fd2  test    byte ptr [rbx+68h], 4
0x180018fd6  jnz     loc_180018D02
0x180018fdc  xor     edx, edx; Val
0x180018fde  lea     rcx, [rsp+110h+ExceptionRecord]; void *
0x180018fe3  mov     r8d, 98h; Size
0x180018fe9  call    memset$thunk$772440563353939046
0x180018fee  mov     rax, [rbx+58h]
0x180018ff2  lea     rcx, [rsp+110h+ExceptionRecord]; ExceptionRecord
0x180018ff7  mov     [rsp+110h+ExceptionRecord.ExceptionInformation], rax
0x180018ffc  mov     rax, [rbx+60h]
0x180019000  mov     [rsp+110h+ExceptionRecord.ExceptionInformation+8], rax
0x180019005  mov     [rsp+110h+ExceptionRecord.ExceptionCode], 0C0000710h
0x18001900d  mov     [rsp+110h+ExceptionRecord.NumberParameters], 2
0x180019015  call    RtlRaiseException
0x18001901a  mov     r9d, 8
0x180019020  mov     [rsp+110h+var_E0], rsi
0x180019025  lea     r8, [rsp+110h+var_E0]
0x18001902a  mov     edx, 5
0x18001902f  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180019036  call    NtSetInformationThread
0x18001903b  jmp     loc_180018D02
```
