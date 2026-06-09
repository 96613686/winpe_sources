# RtlCheckHeldCriticalSections

- ea: `0x1800e4900`
- end: `0x1800e4d54`
- name: `RtlCheckHeldCriticalSections`
- size: `1108`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800e48d0`

## callees

- `0x18005c0c0`
- `0x18006fb30`
- `0x1800707b0`
- `0x1800e4900`
- `0x180138410`
- `0x18015ef80`

## string_xrefs

- `0x1800e4b7f`: `undeleted critical section in freed memory`
- `0x1800e4d11`: `Thread identifier`
- `0x1800e4d1b`: `Thread is in a state in which it cannot own a critical section`

## pseudocode

```c
struct _PEB *__fastcall RtlCheckHeldCriticalSections(__int64 a1, _QWORD *a2)
{
  struct _PEB *result; // rax
  void *UniqueThread; // rsi
  __int64 v6; // rdx
  void **i; // r15
  void **v8; // r14
  __int64 v9; // r12
  _QWORD *j; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // [rsp+30h] [rbp-128h]
  __int64 StackTraceAddress; // [rsp+40h] [rbp-118h]
  __int128 v15; // [rsp+70h] [rbp-E8h] BYREF
  _QWORD *v16; // [rsp+80h] [rbp-D8h]
  void **v17; // [rsp+88h] [rbp-D0h]
  __int128 v18; // [rsp+90h] [rbp-C8h]
  __int128 v19; // [rsp+A0h] [rbp-B8h]
  __int64 v20; // [rsp+B0h] [rbp-A8h]
  __int128 v21; // [rsp+B8h] [rbp-A0h]
  __int128 v22; // [rsp+C8h] [rbp-90h]
  __int128 v23; // [rsp+D8h] [rbp-80h]
  _OWORD v24[7]; // [rsp+E8h] [rbp-70h] BYREF
  int v25; // [rsp+170h] [rbp+18h] BYREF
  void *v26; // [rsp+178h] [rbp+20h]

  result = 0;
  memset(v24, 0, 44);
  v21 = 0;
  v23 = 0;
  v18 = 0;
  v19 = 0;
  v25 = 0;
  v15 = 0;
  if ( RtlpCriticalSectionVerifier )
  {
    if ( !RtlpCsVerifyDoNotBreak )
    {
      result = NtCurrentPeb();
      if ( !result->Ldr->ShutdownInProgress )
      {
        if ( a1 == -2 )
        {
          result = (struct _PEB *)NtCurrentTeb();
          if ( !HIDWORD(result->ApiSetMap) )
            return result;
          UniqueThread = NtCurrentTeb()->ClientId.UniqueThread;
        }
        else
        {
          *(_QWORD *)&v15 = &v25;
          *((_QWORD *)&v15 + 1) = 0x40000006CLL;
          result = (struct _PEB *)ZwQueryInformationThread(a1, 26, &v15, 16, 0);
          if ( (int)result < 0 )
            return result;
          if ( !v25 )
            return result;
          result = (struct _PEB *)ZwQueryInformationThread(a1, 0, v24, 48, 0);
          if ( (int)result < 0 )
            return result;
          UniqueThread = (void *)*((_QWORD *)&v24[1] + 1);
        }
        v26 = UniqueThread;
        RtlAcquireSRWLockShared(&RtlCriticalSectionLock);
        for ( i = (void **)RtlCriticalSectionList; i != (void **)&RtlCriticalSectionList; i = (void **)*v17 )
        {
          v17 = i;
          v8 = i - 2;
          v9 = (__int64)*(i - 1);
          if ( a2 )
          {
            for ( j = a2; ; ++j )
            {
              v16 = j;
              v11 = *j;
              if ( !*j )
                break;
              if ( v9 == v11 )
              {
                if ( v11 )
                  goto LABEL_24;
                break;
              }
            }
          }
          v18 = *(_OWORD *)v9;
          v19 = *(_OWORD *)(v9 + 16);
          v20 = *(_QWORD *)(v9 + 32);
          if ( (void **)v18 == v8 )
          {
            if ( (void *)v19 == UniqueThread )
            {
              StackTraceAddress = RtlpGetStackTraceAddressEx(
                                    *((unsigned __int16 *)v8 + 1),
                                    *((unsigned __int16 *)v8 + 22));
              RtlApplicationVerifierStop(
                512,
                (unsigned int)"Thread is in a state in which it cannot own a critical section",
                (_DWORD)UniqueThread,
                (unsigned int)"Thread identifier",
                v9,
                (__int64)"Critical section address",
                (__int64)(i - 2),
                (__int64)"Critical section debug info address",
                StackTraceAddress,
                (__int64)"Initialization stack trace. Use dps to dump it if non-NULL.");
            }
          }
          else
          {
            v21 = *(_OWORD *)v18;
            v22 = *(_OWORD *)(v18 + 16);
            v23 = *(_OWORD *)(v18 + 32);
            v12 = RtlpGetStackTraceAddressEx(WORD1(v21), WORD6(v23));
            v13 = RtlpGetStackTraceAddressEx(*((unsigned __int16 *)i - 7), *((unsigned __int16 *)i + 14));
            RtlApplicationVerifierStop(
              515,
              (unsigned int)"double initialized or corrupted critical section",
              v9,
              (unsigned int)"Critical section address.",
              (__int64)(i - 2),
              (__int64)"Address of the debug info found in the active list.",
              v13,
              (__int64)"First initialization stack trace. Use dps to dump it if non-NULL.",
              v12,
              (__int64)"Second initialization stack trace. Use dps to dump it if non-NULL.");
          }
LABEL_24:
          ;
        }
        return (struct _PEB *)RtlReleaseSRWLockShared(&RtlCriticalSectionLock, v6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800e4900  mov     r11, rsp
0x1800e4903  mov     [r11+10h], rdx
0x1800e4907  push    rbx
0x1800e4908  push    rsi
0x1800e4909  push    rdi
0x1800e490a  push    r12
0x1800e490c  push    r13
0x1800e490e  push    r14
0x1800e4910  push    r15
0x1800e4912  sub     rsp, 120h
0x1800e4919  mov     rdi, rdx
0x1800e491c  mov     rbx, rcx
0x1800e491f  xor     eax, eax
0x1800e4921  xorps   xmm0, xmm0
0x1800e4924  movups  xmmword ptr [r11-70h], xmm0
0x1800e4929  movups  xmmword ptr [r11-60h], xmm0
0x1800e492e  movups  xmmword ptr [r11-54h], xmm0
0x1800e4933  movups  [rsp+158h+var_A0], xmm0
0x1800e493b  movups  xmmword ptr [r11-80h], xmm0
0x1800e4940  xorps   xmm1, xmm1
0x1800e4943  movups  [rsp+158h+var_C8], xmm1
0x1800e494b  movups  [rsp+158h+var_B8], xmm1
0x1800e4953  mov     [r11+18h], eax
0x1800e4957  movups  [rsp+158h+var_E8], xmm0
0x1800e495c  cmp     cs:RtlpCriticalSectionVerifier, al
0x1800e4962  jnz     short loc_1800E4978
0x1800e4964  add     rsp, 120h
0x1800e496b  pop     r15
0x1800e496d  pop     r14
0x1800e496f  pop     r13
0x1800e4971  pop     r12
0x1800e4973  pop     rdi
0x1800e4974  pop     rsi
0x1800e4975  pop     rbx
0x1800e4976  retn
0x1800e4978  cmp     cs:RtlpCsVerifyDoNotBreak, al
0x1800e497e  jnz     short loc_1800E4964
0x1800e4980  mov     rax, gs:60h
0x1800e4989  mov     rcx, [rax+18h]
0x1800e498d  cmp     byte ptr [rcx+48h], 0
0x1800e4991  jnz     short loc_1800E4964
0x1800e4993  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x1800e4997  jnz     short loc_1800E49BA
0x1800e4999  mov     rax, gs:30h
0x1800e49a2  cmp     dword ptr [rax+6Ch], 0
0x1800e49a6  jz      short loc_1800E4964
0x1800e49a8  mov     rax, gs:30h
0x1800e49b1  mov     rsi, [rax+48h]
0x1800e49b5  jmp     loc_1800E4A3F
0x1800e49ba  lea     rax, [rsp+158h+arg_10]
0x1800e49c2  mov     qword ptr [rsp+158h+var_E8], rax
0x1800e49c7  mov     dword ptr [rsp+158h+var_E8+0Ch], 4
0x1800e49cf  mov     dword ptr [rsp+158h+var_E8+8], 6Ch ; 'l'
0x1800e49d7  mov     [rsp+158h+var_138], 0
0x1800e49e0  mov     r9d, 10h
0x1800e49e6  lea     r8, [rsp+158h+var_E8]
0x1800e49eb  mov     edx, 1Ah
0x1800e49f0  mov     rcx, rbx
0x1800e49f3  call    ZwQueryInformationThread
0x1800e49f8  test    eax, eax
0x1800e49fa  js      loc_1800E4964
0x1800e4a00  cmp     [rsp+158h+arg_10], 0
0x1800e4a08  jz      loc_1800E4964
0x1800e4a0e  mov     [rsp+158h+var_138], 0
0x1800e4a17  mov     r9d, 30h ; '0'
0x1800e4a1d  lea     r8, [rsp+158h+var_70]
0x1800e4a25  xor     edx, edx
0x1800e4a27  mov     rcx, rbx
0x1800e4a2a  call    ZwQueryInformationThread
0x1800e4a2f  test    eax, eax
0x1800e4a31  js      loc_1800E4964
0x1800e4a37  mov     rsi, [rsp+158h+var_58]
0x1800e4a3f  mov     [rsp+158h+arg_18], rsi
0x1800e4a47  lea     rcx, RtlCriticalSectionLock
0x1800e4a4e  call    RtlAcquireSRWLockShared
0x1800e4a53  nop
0x1800e4a54  mov     r15, cs:RtlCriticalSectionList
0x1800e4a5b  lea     rcx, RtlCriticalSectionList
0x1800e4a62  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e4a69  cmp     r15, rcx
0x1800e4a6c  jz      loc_1800E4D43
0x1800e4a72  mov     [rsp+158h+var_F0], r15
0x1800e4a77  mov     [rsp+158h+var_D0], r15
0x1800e4a7f  lea     r14, [r15-10h]
0x1800e4a83  mov     [rsp+158h+var_100], r14
0x1800e4a88  mov     r12, [r14+8]
0x1800e4a8c  mov     [rsp+158h+var_F8], r12
0x1800e4a91  test    rdi, rdi
0x1800e4a94  jz      short loc_1800E4ACC
0x1800e4a96  mov     rax, rdi
0x1800e4a99  mov     [rsp+158h+var_D8], rax
0x1800e4aa1  mov     rcx, [rax]
0x1800e4aa4  test    rcx, rcx
0x1800e4aa7  jz      short loc_1800E4AC5
0x1800e4aa9  cmp     r12, rcx
0x1800e4aac  jz      short loc_1800E4AB4
0x1800e4aae  add     rax, 8
0x1800e4ab2  jmp     short loc_1800E4A99
0x1800e4ab4  test    rcx, rcx
0x1800e4ab7  jz      short loc_1800E4AC5
0x1800e4ab9  lea     rcx, RtlCriticalSectionList
0x1800e4ac0  jmp     loc_1800E4D33
0x1800e4ac5  lea     rcx, RtlCriticalSectionList
0x1800e4acc  mov     al, 1
0x1800e4ace  mov     [rsp+158h+var_108], al
0x1800e4ad2  movups  xmm0, xmmword ptr [r12]
0x1800e4ad7  movups  [rsp+158h+var_C8], xmm0
0x1800e4adf  movups  xmm1, xmmword ptr [r12+10h]
0x1800e4ae5  movups  [rsp+158h+var_B8], xmm1
0x1800e4aed  movsd   xmm0, qword ptr [r12+20h]
0x1800e4af4  movsd   [rsp+158h+var_A8], xmm0
0x1800e4afd  jmp     short loc_1800E4B32
0x1800e4aff  xor     al, al
0x1800e4b01  mov     [rsp+158h+var_108], al
0x1800e4b05  lea     rcx, RtlCriticalSectionList
0x1800e4b0c  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e4b13  mov     rdi, [rsp+158h+arg_8]
0x1800e4b1b  mov     r14, [rsp+158h+var_100]
0x1800e4b20  mov     r12, [rsp+158h+var_F8]
0x1800e4b25  mov     rsi, [rsp+158h+arg_18]
0x1800e4b2d  mov     r15, [rsp+158h+var_F0]
0x1800e4b32  test    al, al
0x1800e4b34  jnz     short loc_1800E4B90
0x1800e4b36  movzx   edx, word ptr [r14+2Ch]
0x1800e4b3b  movzx   ecx, word ptr [r14+2]
0x1800e4b40  call    RtlpGetStackTraceAddressEx
0x1800e4b45  lea     rcx, byte_180175FF3
0x1800e4b4c  mov     [rsp+158h+var_110], rcx
0x1800e4b51  mov     [rsp+158h+var_118], 0
0x1800e4b5a  mov     [rsp+158h+var_120], r13
0x1800e4b5f  mov     [rsp+158h+var_128], rax
0x1800e4b64  lea     rax, aCriticalSectio_2; "Critical section debug info address"
0x1800e4b6b  mov     [rsp+158h+var_130], rax
0x1800e4b70  mov     [rsp+158h+var_138], r14
0x1800e4b75  lea     r9, aCriticalSectio; "Critical section address"
0x1800e4b7c  mov     r8, r12
0x1800e4b7f  lea     rdx, aUndeletedCriti; "undeleted critical section in freed mem"...
0x1800e4b86  mov     ecx, 204h
0x1800e4b8b  jmp     loc_1800E4D27
0x1800e4b90  mov     rbx, qword ptr [rsp+158h+var_C8]
0x1800e4b98  cmp     rbx, r14
0x1800e4b9b  jz      loc_1800E4CCC
0x1800e4ba1  mov     al, 1
0x1800e4ba3  mov     [rsp+158h+var_108], al
0x1800e4ba7  movups  xmm0, xmmword ptr [rbx]
0x1800e4baa  movups  [rsp+158h+var_A0], xmm0
0x1800e4bb2  movups  xmm1, xmmword ptr [rbx+10h]
0x1800e4bb6  movups  [rsp+158h+var_90], xmm1
0x1800e4bbe  movups  xmm0, xmmword ptr [rbx+20h]
0x1800e4bc2  movups  [rsp+158h+var_80], xmm0
0x1800e4bca  jmp     short loc_1800E4C00
0x1800e4bcc  xor     al, al
0x1800e4bce  mov     [rsp+158h+var_108], al
0x1800e4bd2  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e4bd9  mov     rdi, [rsp+158h+arg_8]
0x1800e4be1  mov     r14, [rsp+158h+var_100]
0x1800e4be6  mov     r12, [rsp+158h+var_F8]
0x1800e4beb  mov     rbx, qword ptr [rsp+158h+var_C8]
0x1800e4bf3  mov     rsi, [rsp+158h+arg_18]
0x1800e4bfb  mov     r15, [rsp+158h+var_F0]
0x1800e4c00  test    al, al
0x1800e4c02  jnz     short loc_1800E4C5A
0x1800e4c04  movzx   edx, word ptr [r15+1Ch]
0x1800e4c09  movzx   ecx, word ptr [r15-0Eh]
0x1800e4c0e  call    RtlpGetStackTraceAddressEx
0x1800e4c13  mov     [rsp+158h+var_110], r13
0x1800e4c18  mov     [rsp+158h+var_118], rax
0x1800e4c1d  lea     rax, aAddressOfTheDe; "Address of the debug info found in the "...
0x1800e4c24  mov     [rsp+158h+var_120], rax
0x1800e4c29  mov     [rsp+158h+var_128], r14
0x1800e4c2e  lea     rax, aInvalidDebugIn; "Invalid debug info address of this crit"...
0x1800e4c35  mov     [rsp+158h+var_130], rax
0x1800e4c3a  mov     [rsp+158h+var_138], rbx
0x1800e4c3f  lea     r9, aCriticalSectio; "Critical section address"
0x1800e4c46  mov     r8, r12
0x1800e4c49  lea     rdx, aCorruptedCriti; "corrupted critical section"
0x1800e4c50  mov     ecx, 205h
0x1800e4c55  jmp     loc_1800E4D27
0x1800e4c5a  movzx   edx, word ptr [rsp+158h+var_80+0Ch]
0x1800e4c62  movzx   ecx, word ptr [rsp+158h+var_A0+2]
0x1800e4c6a  call    RtlpGetStackTraceAddressEx
0x1800e4c6f  mov     rbx, rax
0x1800e4c72  movzx   edx, word ptr [r15+1Ch]
0x1800e4c77  movzx   ecx, word ptr [r15-0Eh]
0x1800e4c7c  call    RtlpGetStackTraceAddressEx
0x1800e4c81  lea     rcx, aSecondInitiali; "Second initialization stack trace. Use "...
0x1800e4c88  mov     [rsp+158h+var_110], rcx
0x1800e4c8d  mov     [rsp+158h+var_118], rbx
0x1800e4c92  lea     rcx, aFirstInitializ; "First initialization stack trace. Use d"...
0x1800e4c99  mov     [rsp+158h+var_120], rcx
0x1800e4c9e  mov     [rsp+158h+var_128], rax
0x1800e4ca3  lea     rax, aAddressOfTheDe; "Address of the debug info found in the "...
0x1800e4caa  mov     [rsp+158h+var_130], rax
0x1800e4caf  mov     [rsp+158h+var_138], r14
0x1800e4cb4  lea     r9, aCriticalSectio_0; "Critical section address."
0x1800e4cbb  mov     r8, r12
0x1800e4cbe  lea     rdx, aDoubleInitiali; "double initialized or corrupted critica"...
0x1800e4cc5  mov     ecx, 203h
0x1800e4cca  jmp     short loc_1800E4D27
0x1800e4ccc  cmp     qword ptr [rsp+158h+var_B8], rsi
0x1800e4cd4  jnz     short loc_1800E4D33
0x1800e4cd6  movzx   edx, word ptr [r14+2Ch]
0x1800e4cdb  movzx   ecx, word ptr [r14+2]
0x1800e4ce0  call    RtlpGetStackTraceAddressEx
0x1800e4ce5  mov     [rsp+158h+var_110], r13
0x1800e4cea  mov     [rsp+158h+var_118], rax
0x1800e4cef  lea     rax, aCriticalSectio_2; "Critical section debug info address"
0x1800e4cf6  mov     [rsp+158h+var_120], rax
0x1800e4cfb  mov     [rsp+158h+var_128], r14
0x1800e4d00  lea     rax, aCriticalSectio; "Critical section address"
0x1800e4d07  mov     [rsp+158h+var_130], rax
0x1800e4d0c  mov     [rsp+158h+var_138], r12
0x1800e4d11  lea     r9, aThreadIdentifi; "Thread identifier"
0x1800e4d18  mov     r8, rsi
0x1800e4d1b  lea     rdx, aThreadIsInASta; "Thread is in a state in which it cannot"...
0x1800e4d22  mov     ecx, 200h
0x1800e4d27  call    RtlApplicationVerifierStop
0x1800e4d2c  lea     rcx, RtlCriticalSectionList
0x1800e4d33  mov     rax, [rsp+158h+var_D0]
0x1800e4d3b  mov     r15, [rax]
0x1800e4d3e  jmp     loc_1800E4A69
0x1800e4d43  lea     rcx, RtlCriticalSectionLock
0x1800e4d4a  call    RtlReleaseSRWLockShared
0x1800e4d4f  jmp     loc_1800E4964
0x180168530  push    rbp
0x180168532  sub     rsp, 50h
0x180168536  mov     rbp, rdx
0x180168539  lea     rcx, RtlCriticalSectionLock
0x180168540  call    RtlReleaseSRWLockShared
0x180168545  nop
0x180168546  add     rsp, 50h
0x18016854a  pop     rbp
0x18016854b  retn
```
