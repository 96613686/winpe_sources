# RtlCheckHeldCriticalSections

- ea: `0x1800e4580`
- end: `0x1800e49d4`
- name: `RtlCheckHeldCriticalSections`
- size: `1108`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800e4550`

## callees

- `0x180053150`
- `0x180053dd0`
- `0x18007c720`
- `0x1800e4580`
- `0x180137920`
- `0x18015e770`

## string_xrefs

- `0x1800e47ff`: `undeleted critical section in freed memory`
- `0x1800e4991`: `Thread identifier`
- `0x1800e499b`: `Thread is in a state in which it cannot own a critical section`

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
0x1800e4580  mov     r11, rsp
0x1800e4583  mov     [r11+10h], rdx
0x1800e4587  push    rbx
0x1800e4588  push    rsi
0x1800e4589  push    rdi
0x1800e458a  push    r12
0x1800e458c  push    r13
0x1800e458e  push    r14
0x1800e4590  push    r15
0x1800e4592  sub     rsp, 120h
0x1800e4599  mov     rdi, rdx
0x1800e459c  mov     rbx, rcx
0x1800e459f  xor     eax, eax
0x1800e45a1  xorps   xmm0, xmm0
0x1800e45a4  movups  xmmword ptr [r11-70h], xmm0
0x1800e45a9  movups  xmmword ptr [r11-60h], xmm0
0x1800e45ae  movups  xmmword ptr [r11-54h], xmm0
0x1800e45b3  movups  [rsp+158h+var_A0], xmm0
0x1800e45bb  movups  xmmword ptr [r11-80h], xmm0
0x1800e45c0  xorps   xmm1, xmm1
0x1800e45c3  movups  [rsp+158h+var_C8], xmm1
0x1800e45cb  movups  [rsp+158h+var_B8], xmm1
0x1800e45d3  mov     [r11+18h], eax
0x1800e45d7  movups  [rsp+158h+var_E8], xmm0
0x1800e45dc  cmp     cs:RtlpCriticalSectionVerifier, al
0x1800e45e2  jnz     short loc_1800E45F8
0x1800e45e4  add     rsp, 120h
0x1800e45eb  pop     r15
0x1800e45ed  pop     r14
0x1800e45ef  pop     r13
0x1800e45f1  pop     r12
0x1800e45f3  pop     rdi
0x1800e45f4  pop     rsi
0x1800e45f5  pop     rbx
0x1800e45f6  retn
0x1800e45f8  cmp     cs:RtlpCsVerifyDoNotBreak, al
0x1800e45fe  jnz     short loc_1800E45E4
0x1800e4600  mov     rax, gs:60h
0x1800e4609  mov     rcx, [rax+18h]
0x1800e460d  cmp     byte ptr [rcx+48h], 0
0x1800e4611  jnz     short loc_1800E45E4
0x1800e4613  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x1800e4617  jnz     short loc_1800E463A
0x1800e4619  mov     rax, gs:30h
0x1800e4622  cmp     dword ptr [rax+6Ch], 0
0x1800e4626  jz      short loc_1800E45E4
0x1800e4628  mov     rax, gs:30h
0x1800e4631  mov     rsi, [rax+48h]
0x1800e4635  jmp     loc_1800E46BF
0x1800e463a  lea     rax, [rsp+158h+arg_10]
0x1800e4642  mov     qword ptr [rsp+158h+var_E8], rax
0x1800e4647  mov     dword ptr [rsp+158h+var_E8+0Ch], 4
0x1800e464f  mov     dword ptr [rsp+158h+var_E8+8], 6Ch ; 'l'
0x1800e4657  mov     [rsp+158h+var_138], 0
0x1800e4660  mov     r9d, 10h
0x1800e4666  lea     r8, [rsp+158h+var_E8]
0x1800e466b  mov     edx, 1Ah
0x1800e4670  mov     rcx, rbx
0x1800e4673  call    ZwQueryInformationThread
0x1800e4678  test    eax, eax
0x1800e467a  js      loc_1800E45E4
0x1800e4680  cmp     [rsp+158h+arg_10], 0
0x1800e4688  jz      loc_1800E45E4
0x1800e468e  mov     [rsp+158h+var_138], 0
0x1800e4697  mov     r9d, 30h ; '0'
0x1800e469d  lea     r8, [rsp+158h+var_70]
0x1800e46a5  xor     edx, edx
0x1800e46a7  mov     rcx, rbx
0x1800e46aa  call    ZwQueryInformationThread
0x1800e46af  test    eax, eax
0x1800e46b1  js      loc_1800E45E4
0x1800e46b7  mov     rsi, [rsp+158h+var_58]
0x1800e46bf  mov     [rsp+158h+arg_18], rsi
0x1800e46c7  lea     rcx, RtlCriticalSectionLock
0x1800e46ce  call    RtlAcquireSRWLockShared
0x1800e46d3  nop
0x1800e46d4  mov     r15, cs:RtlCriticalSectionList
0x1800e46db  lea     rcx, RtlCriticalSectionList
0x1800e46e2  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e46e9  cmp     r15, rcx
0x1800e46ec  jz      loc_1800E49C3
0x1800e46f2  mov     [rsp+158h+var_F0], r15
0x1800e46f7  mov     [rsp+158h+var_D0], r15
0x1800e46ff  lea     r14, [r15-10h]
0x1800e4703  mov     [rsp+158h+var_100], r14
0x1800e4708  mov     r12, [r14+8]
0x1800e470c  mov     [rsp+158h+var_F8], r12
0x1800e4711  test    rdi, rdi
0x1800e4714  jz      short loc_1800E474C
0x1800e4716  mov     rax, rdi
0x1800e4719  mov     [rsp+158h+var_D8], rax
0x1800e4721  mov     rcx, [rax]
0x1800e4724  test    rcx, rcx
0x1800e4727  jz      short loc_1800E4745
0x1800e4729  cmp     r12, rcx
0x1800e472c  jz      short loc_1800E4734
0x1800e472e  add     rax, 8
0x1800e4732  jmp     short loc_1800E4719
0x1800e4734  test    rcx, rcx
0x1800e4737  jz      short loc_1800E4745
0x1800e4739  lea     rcx, RtlCriticalSectionList
0x1800e4740  jmp     loc_1800E49B3
0x1800e4745  lea     rcx, RtlCriticalSectionList
0x1800e474c  mov     al, 1
0x1800e474e  mov     [rsp+158h+var_108], al
0x1800e4752  movups  xmm0, xmmword ptr [r12]
0x1800e4757  movups  [rsp+158h+var_C8], xmm0
0x1800e475f  movups  xmm1, xmmword ptr [r12+10h]
0x1800e4765  movups  [rsp+158h+var_B8], xmm1
0x1800e476d  movsd   xmm0, qword ptr [r12+20h]
0x1800e4774  movsd   [rsp+158h+var_A8], xmm0
0x1800e477d  jmp     short loc_1800E47B2
0x1800e477f  xor     al, al
0x1800e4781  mov     [rsp+158h+var_108], al
0x1800e4785  lea     rcx, RtlCriticalSectionList
0x1800e478c  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e4793  mov     rdi, [rsp+158h+arg_8]
0x1800e479b  mov     r14, [rsp+158h+var_100]
0x1800e47a0  mov     r12, [rsp+158h+var_F8]
0x1800e47a5  mov     rsi, [rsp+158h+arg_18]
0x1800e47ad  mov     r15, [rsp+158h+var_F0]
0x1800e47b2  test    al, al
0x1800e47b4  jnz     short loc_1800E4810
0x1800e47b6  movzx   edx, word ptr [r14+2Ch]
0x1800e47bb  movzx   ecx, word ptr [r14+2]
0x1800e47c0  call    RtlpGetStackTraceAddressEx
0x1800e47c5  lea     rcx, byte_180175FF3
0x1800e47cc  mov     [rsp+158h+var_110], rcx
0x1800e47d1  mov     [rsp+158h+var_118], 0
0x1800e47da  mov     [rsp+158h+var_120], r13
0x1800e47df  mov     [rsp+158h+var_128], rax
0x1800e47e4  lea     rax, aCriticalSectio_2; "Critical section debug info address"
0x1800e47eb  mov     [rsp+158h+var_130], rax
0x1800e47f0  mov     [rsp+158h+var_138], r14
0x1800e47f5  lea     r9, aCriticalSectio; "Critical section address"
0x1800e47fc  mov     r8, r12
0x1800e47ff  lea     rdx, aUndeletedCriti; "undeleted critical section in freed mem"...
0x1800e4806  mov     ecx, 204h
0x1800e480b  jmp     loc_1800E49A7
0x1800e4810  mov     rbx, qword ptr [rsp+158h+var_C8]
0x1800e4818  cmp     rbx, r14
0x1800e481b  jz      loc_1800E494C
0x1800e4821  mov     al, 1
0x1800e4823  mov     [rsp+158h+var_108], al
0x1800e4827  movups  xmm0, xmmword ptr [rbx]
0x1800e482a  movups  [rsp+158h+var_A0], xmm0
0x1800e4832  movups  xmm1, xmmword ptr [rbx+10h]
0x1800e4836  movups  [rsp+158h+var_90], xmm1
0x1800e483e  movups  xmm0, xmmword ptr [rbx+20h]
0x1800e4842  movups  [rsp+158h+var_80], xmm0
0x1800e484a  jmp     short loc_1800E4880
0x1800e484c  xor     al, al
0x1800e484e  mov     [rsp+158h+var_108], al
0x1800e4852  lea     r13, aInitialization; "Initialization stack trace. Use dps to "...
0x1800e4859  mov     rdi, [rsp+158h+arg_8]
0x1800e4861  mov     r14, [rsp+158h+var_100]
0x1800e4866  mov     r12, [rsp+158h+var_F8]
0x1800e486b  mov     rbx, qword ptr [rsp+158h+var_C8]
0x1800e4873  mov     rsi, [rsp+158h+arg_18]
0x1800e487b  mov     r15, [rsp+158h+var_F0]
0x1800e4880  test    al, al
0x1800e4882  jnz     short loc_1800E48DA
0x1800e4884  movzx   edx, word ptr [r15+1Ch]
0x1800e4889  movzx   ecx, word ptr [r15-0Eh]
0x1800e488e  call    RtlpGetStackTraceAddressEx
0x1800e4893  mov     [rsp+158h+var_110], r13
0x1800e4898  mov     [rsp+158h+var_118], rax
0x1800e489d  lea     rax, aAddressOfTheDe; "Address of the debug info found in the "...
0x1800e48a4  mov     [rsp+158h+var_120], rax
0x1800e48a9  mov     [rsp+158h+var_128], r14
0x1800e48ae  lea     rax, aInvalidDebugIn; "Invalid debug info address of this crit"...
0x1800e48b5  mov     [rsp+158h+var_130], rax
0x1800e48ba  mov     [rsp+158h+var_138], rbx
0x1800e48bf  lea     r9, aCriticalSectio; "Critical section address"
0x1800e48c6  mov     r8, r12
0x1800e48c9  lea     rdx, aCorruptedCriti; "corrupted critical section"
0x1800e48d0  mov     ecx, 205h
0x1800e48d5  jmp     loc_1800E49A7
0x1800e48da  movzx   edx, word ptr [rsp+158h+var_80+0Ch]
0x1800e48e2  movzx   ecx, word ptr [rsp+158h+var_A0+2]
0x1800e48ea  call    RtlpGetStackTraceAddressEx
0x1800e48ef  mov     rbx, rax
0x1800e48f2  movzx   edx, word ptr [r15+1Ch]
0x1800e48f7  movzx   ecx, word ptr [r15-0Eh]
0x1800e48fc  call    RtlpGetStackTraceAddressEx
0x1800e4901  lea     rcx, aSecondInitiali; "Second initialization stack trace. Use "...
0x1800e4908  mov     [rsp+158h+var_110], rcx
0x1800e490d  mov     [rsp+158h+var_118], rbx
0x1800e4912  lea     rcx, aFirstInitializ; "First initialization stack trace. Use d"...
0x1800e4919  mov     [rsp+158h+var_120], rcx
0x1800e491e  mov     [rsp+158h+var_128], rax
0x1800e4923  lea     rax, aAddressOfTheDe; "Address of the debug info found in the "...
0x1800e492a  mov     [rsp+158h+var_130], rax
0x1800e492f  mov     [rsp+158h+var_138], r14
0x1800e4934  lea     r9, aCriticalSectio_0; "Critical section address."
0x1800e493b  mov     r8, r12
0x1800e493e  lea     rdx, aDoubleInitiali; "double initialized or corrupted critica"...
0x1800e4945  mov     ecx, 203h
0x1800e494a  jmp     short loc_1800E49A7
0x1800e494c  cmp     qword ptr [rsp+158h+var_B8], rsi
0x1800e4954  jnz     short loc_1800E49B3
0x1800e4956  movzx   edx, word ptr [r14+2Ch]
0x1800e495b  movzx   ecx, word ptr [r14+2]
0x1800e4960  call    RtlpGetStackTraceAddressEx
0x1800e4965  mov     [rsp+158h+var_110], r13
0x1800e496a  mov     [rsp+158h+var_118], rax
0x1800e496f  lea     rax, aCriticalSectio_2; "Critical section debug info address"
0x1800e4976  mov     [rsp+158h+var_120], rax
0x1800e497b  mov     [rsp+158h+var_128], r14
0x1800e4980  lea     rax, aCriticalSectio; "Critical section address"
0x1800e4987  mov     [rsp+158h+var_130], rax
0x1800e498c  mov     [rsp+158h+var_138], r12
0x1800e4991  lea     r9, aThreadIdentifi; "Thread identifier"
0x1800e4998  mov     r8, rsi
0x1800e499b  lea     rdx, aThreadIsInASta; "Thread is in a state in which it cannot"...
0x1800e49a2  mov     ecx, 200h
0x1800e49a7  call    RtlApplicationVerifierStop
0x1800e49ac  lea     rcx, RtlCriticalSectionList
0x1800e49b3  mov     rax, [rsp+158h+var_D0]
0x1800e49bb  mov     r15, [rax]
0x1800e49be  jmp     loc_1800E46E9
0x1800e49c3  lea     rcx, RtlCriticalSectionLock
0x1800e49ca  call    RtlReleaseSRWLockShared
0x1800e49cf  jmp     loc_1800E45E4
0x180167d10  push    rbp
0x180167d12  sub     rsp, 50h
0x180167d16  mov     rbp, rdx
0x180167d19  lea     rcx, RtlCriticalSectionLock
0x180167d20  call    RtlReleaseSRWLockShared
0x180167d25  nop
0x180167d26  add     rsp, 50h
0x180167d2a  pop     rbp
0x180167d2b  retn
```
