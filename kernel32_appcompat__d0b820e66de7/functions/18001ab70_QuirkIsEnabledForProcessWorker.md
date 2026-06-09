# QuirkIsEnabledForProcessWorker

- ea: `0x18001ab70`
- end: `0x18001ae36`
- name: `QuirkIsEnabledForProcessWorker`
- size: `710`
- prototype: `__int64 __fastcall(HANDLE hProcess)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001aa90`
- `0x18001aab8`
- `0x18001ab70`
- `0x18001bbe0`
- `0x18001bd4c`
- `0x18001c5a0`
- `0x18001c848`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001ad19`
- `ntdll!RtlFreeHeap` at `0x18001ad19`
- `ntdll!RtlAllocateHeap` at `0x18001abef`
- `ntdll!RtlAllocateHeap` at `0x18001abef`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001ac65`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18001ac65`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ac0f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ac2a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ac0f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18001ac2a`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001abaf`
- `api-ms-win-core-appcompat-l1-1-1!BaseReadAppCompatDataForProcess` at `0x18001abaf`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18001ad85`
- `api-ms-win-core-appcompat-l1-1-1!BaseFreeAppCompatDataForProcess` at `0x18001ad85`

## pseudocode

```c
__int64 __fastcall QuirkIsEnabledForProcessWorker(HANDLE hProcess, unsigned int a2, int *a3)
{
  PVOID Heap; // r14
  int v7; // eax
  int LastErrorValue; // ebx
  const void *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx
  char ProcessTargetPlatform; // cl
  unsigned __int64 v13; // r8
  __int64 v14; // r10
  int v15; // eax
  int v16; // ecx
  int v17; // ecx
  bool v19; // cf
  __int64 ProcessOsMaxVersionTested; // rax
  __int64 v21; // rcx
  char v22; // al
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  int inited; // ebx
  __int64 v26; // [rsp+30h] [rbp-10h] BYREF
  BOOL Wow64Process; // [rsp+70h] [rbp+30h] BYREF
  BOOL v28; // [rsp+88h] [rbp+48h] BYREF

  Heap = 0;
  v26 = 0;
  v28 = 0;
  Wow64Process = 0;
  if ( hProcess == (HANDLE)-1LL )
  {
    *a3 = QuirkIsEnabledWorker(a2);
    goto LABEL_15;
  }
  v7 = BaseReadAppCompatDataForProcess(hProcess, &v26, 0);
  LastErrorValue = v7;
  if ( v7 )
  {
    if ( v7 <= 0 )
      goto LABEL_16;
    LastErrorValue = (unsigned __int16)v7;
    goto LABEL_21;
  }
  v9 = *(const void **)(v26 + 4480);
  if ( v9 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)(v26 + 4488));
    if ( !Heap )
    {
      LastErrorValue = -2147024882;
      goto LABEL_16;
    }
    if ( IsWow64Process((HANDLE)0xFFFFFFFFFFFFFFFFLL, &Wow64Process) && IsWow64Process(hProcess, &v28) )
    {
      if ( Wow64Process && !v28 )
      {
        LastErrorValue = -805306367;
        goto LABEL_16;
      }
      if ( ReadProcessMemory(hProcess, v9, Heap, *(unsigned int *)(v26 + 4488), 0) )
      {
        if ( QuirksLookupById(Heap, a2) )
        {
          SbGetProcessOsMaxVersionTested(v26);
          ProcessTargetPlatform = SbGetProcessTargetPlatform(v11, v10);
          v15 = 1;
          if ( ((unsigned int)(1LL << ProcessTargetPlatform) & *(_QWORD *)(v14 + 268)) != 0 )
          {
            v16 = QuirksGlobalOverride;
            if ( QuirksGlobalOverride == -1 )
            {
              v17 = *(_DWORD *)(v14 + 552);
              if ( (v17 & 1) != 0 )
                goto LABEL_14;
              v15 = 0;
              if ( (v17 & 2) != 0 )
                goto LABEL_14;
              v19 = v13 < *(_QWORD *)(v14 + 260);
              goto LABEL_26;
            }
            v15 = 0;
            goto LABEL_29;
          }
          goto LABEL_30;
        }
        goto LABEL_27;
      }
    }
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    if ( LastErrorValue <= 0 )
      goto LABEL_16;
    LastErrorValue = (unsigned __int16)LastErrorValue;
LABEL_21:
    LastErrorValue |= 0x80070000;
    goto LABEL_16;
  }
  v24 = QuirksTable;
  if ( QuirksTable )
  {
LABEL_41:
    if ( QuirksLookupById(v24, a2) )
    {
      ProcessOsMaxVersionTested = SbGetProcessOsMaxVersionTested(v26);
      v22 = SbGetProcessTargetPlatform(v21, ProcessOsMaxVersionTested);
      if ( ((unsigned int)(1LL << v22) & *(_QWORD *)(v14 + 268)) != 0 )
      {
        v16 = QuirksGlobalOverride;
        v15 = 0;
        if ( QuirksGlobalOverride == -1 )
        {
          v19 = v23 < *(_QWORD *)(v14 + 260);
LABEL_26:
          LOBYTE(v15) = v19;
LABEL_14:
          *a3 = v15;
          CptpQuirkSendEtwEvent((wchar_t *)v14, 0);
LABEL_15:
          LastErrorValue = 0;
          goto LABEL_16;
        }
LABEL_29:
        LOBYTE(v15) = v16 != 0;
        goto LABEL_14;
      }
LABEL_30:
      v15 = 0;
      goto LABEL_14;
    }
LABEL_27:
    LastErrorValue = -2147023728;
    goto LABEL_16;
  }
  inited = CptpQuirksInitOnce();
  if ( inited >= 0 )
  {
    v24 = QuirksTable;
    goto LABEL_41;
  }
  LastErrorValue = inited | 0x10000000;
LABEL_16:
  if ( v26 )
    BaseFreeAppCompatDataForProcess();
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18001ab70  mov     [rsp-28h+arg_8], rbx
0x18001ab75  push    rbp
0x18001ab76  push    rsi
0x18001ab77  push    rdi
0x18001ab78  push    r14
0x18001ab7a  push    r15
0x18001ab7c  mov     rbp, rsp
0x18001ab7f  sub     rsp, 40h
0x18001ab83  xor     r14d, r14d
0x18001ab86  mov     [rbp+var_10], 0
0x18001ab8e  mov     [rbp+arg_18], r14d
0x18001ab92  mov     r15, r8
0x18001ab95  mov     [rbp+Wow64Process], r14d
0x18001ab99  mov     edi, edx
0x18001ab9b  mov     rsi, rcx
0x18001ab9e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001aba2  jz      loc_18001AD50
0x18001aba8  xor     r8d, r8d
0x18001abab  lea     rdx, [rbp+var_10]
0x18001abaf  call    cs:__imp_BaseReadAppCompatDataForProcess
0x18001abb6  nop     dword ptr [rax+rax+00h]
0x18001abbb  mov     ebx, eax
0x18001abbd  test    eax, eax
0x18001abbf  jnz     loc_18001AD5C
0x18001abc5  mov     rcx, [rbp+var_10]
0x18001abc9  mov     rbx, [rcx+1180h]
0x18001abd0  test    rbx, rbx
0x18001abd3  jz      loc_18001ADF7
0x18001abd9  mov     r8d, [rcx+1188h]; Size
0x18001abe0  xor     edx, edx; Flags
0x18001abe2  mov     rcx, gs:60h
0x18001abeb  mov     rcx, [rcx+30h]; HeapHandle
0x18001abef  call    cs:__imp_RtlAllocateHeap
0x18001abf6  nop     dword ptr [rax+rax+00h]
0x18001abfb  mov     r14, rax
0x18001abfe  test    rax, rax
0x18001ac01  jz      loc_18001ADD9
0x18001ac07  lea     rdx, [rbp+Wow64Process]; Wow64Process
0x18001ac0b  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18001ac0f  call    cs:__imp_IsWow64Process
0x18001ac16  nop     dword ptr [rax+rax+00h]
0x18001ac1b  test    eax, eax
0x18001ac1d  jz      loc_18001AD39
0x18001ac23  lea     rdx, [rbp+arg_18]; Wow64Process
0x18001ac27  mov     rcx, rsi; hProcess
0x18001ac2a  call    cs:__imp_IsWow64Process
0x18001ac31  nop     dword ptr [rax+rax+00h]
0x18001ac36  test    eax, eax
0x18001ac38  jz      loc_18001AD39
0x18001ac3e  cmp     [rbp+Wow64Process], 0
0x18001ac42  jnz     loc_18001ADE3
0x18001ac48  mov     rax, [rbp+var_10]
0x18001ac4c  mov     r8, r14; lpBuffer
0x18001ac4f  mov     rdx, rbx; lpBaseAddress
0x18001ac52  mov     [rsp+40h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18001ac5b  mov     rcx, rsi; hProcess
0x18001ac5e  mov     r9d, [rax+1188h]; nSize
0x18001ac65  call    cs:__imp_ReadProcessMemory
0x18001ac6c  nop     dword ptr [rax+rax+00h]
0x18001ac71  test    eax, eax
0x18001ac73  jz      loc_18001AD39
0x18001ac79  mov     edx, edi
0x18001ac7b  mov     rcx, r14
0x18001ac7e  call    QuirksLookupById
0x18001ac83  mov     r10, rax
0x18001ac86  test    rax, rax
0x18001ac89  jz      loc_18001AD72
0x18001ac8f  mov     rcx, [rbp+var_10]
0x18001ac93  call    SbGetProcessOsMaxVersionTested
0x18001ac98  mov     r8, rax
0x18001ac9b  call    SbGetProcessTargetPlatform
0x18001aca0  mov     ecx, eax
0x18001aca2  mov     eax, 1
0x18001aca7  mov     edx, eax
0x18001aca9  shl     rdx, cl
0x18001acac  mov     ecx, edx
0x18001acae  test    [r10+10Ch], rcx
0x18001acb5  jz      loc_18001AD96
0x18001acbb  mov     ecx, cs:QuirksGlobalOverride
0x18001acc1  cmp     ecx, 0FFFFFFFFh
0x18001acc4  jnz     loc_18001AD79
0x18001acca  mov     ecx, [r10+228h]
0x18001acd1  test    al, cl
0x18001acd3  jnz     short loc_18001ACE0
0x18001acd5  xor     eax, eax
0x18001acd7  test    cl, 2
0x18001acda  jz      loc_18001AD63
0x18001ace0  xor     r9d, r9d
0x18001ace3  mov     [r15], eax
0x18001ace6  mov     r8, rsi
0x18001ace9  mov     [rsp+40h+lpNumberOfBytesRead], 0; wchar_t *
0x18001acf2  mov     edx, eax
0x18001acf4  mov     rcx, r10; String
0x18001acf7  call    CptpQuirkSendEtwEvent
0x18001acfc  xor     ebx, ebx
0x18001acfe  mov     rcx, [rbp+var_10]
0x18001ad02  test    rcx, rcx
0x18001ad05  jnz     short loc_18001AD85
0x18001ad07  mov     rcx, gs:60h
0x18001ad10  mov     r8, r14; P
0x18001ad13  xor     edx, edx; Flags
0x18001ad15  mov     rcx, [rcx+30h]; HeapHandle
0x18001ad19  call    cs:__imp_RtlFreeHeap
0x18001ad20  nop     dword ptr [rax+rax+00h]
0x18001ad25  mov     eax, ebx
0x18001ad27  mov     rbx, [rsp+40h+arg_8]
0x18001ad2c  add     rsp, 40h
0x18001ad30  pop     r15
0x18001ad32  pop     r14
0x18001ad34  pop     rdi
0x18001ad35  pop     rsi
0x18001ad36  pop     rbp
0x18001ad37  retn
0x18001ad39  mov     ebx, gs:68h
0x18001ad41  test    ebx, ebx
0x18001ad43  jle     short loc_18001ACFE
0x18001ad45  movzx   ebx, bx
0x18001ad48  or      ebx, 80070000h
0x18001ad4e  jmp     short loc_18001ACFE
0x18001ad50  mov     ecx, edi
0x18001ad52  call    QuirkIsEnabledWorker
0x18001ad57  mov     [r15], eax
0x18001ad5a  jmp     short loc_18001ACFC
0x18001ad5c  jle     short loc_18001ACFE
0x18001ad5e  movzx   ebx, ax
0x18001ad61  jmp     short loc_18001AD48
0x18001ad63  cmp     r8, [r10+104h]
0x18001ad6a  setb    al
0x18001ad6d  jmp     loc_18001ACE0
0x18001ad72  mov     ebx, 80070490h
0x18001ad77  jmp     short loc_18001ACFE
0x18001ad79  xor     eax, eax
0x18001ad7b  test    ecx, ecx
0x18001ad7d  setnz   al
0x18001ad80  jmp     loc_18001ACE0
0x18001ad85  call    cs:__imp_BaseFreeAppCompatDataForProcess
0x18001ad8c  nop     dword ptr [rax+rax+00h]
0x18001ad91  jmp     loc_18001AD07
0x18001ad96  xor     eax, eax
0x18001ad98  jmp     loc_18001ACE0
0x18001ad9d  mov     rcx, [rbp+var_10]
0x18001ada1  call    SbGetProcessOsMaxVersionTested
0x18001ada6  mov     rdx, rax
0x18001ada9  call    SbGetProcessTargetPlatform
0x18001adae  mov     ecx, eax
0x18001adb0  mov     eax, 1
0x18001adb5  shl     rax, cl
0x18001adb8  mov     ecx, eax
0x18001adba  test    [r10+10Ch], rcx
0x18001adc1  jz      short loc_18001AD96
0x18001adc3  mov     ecx, cs:QuirksGlobalOverride
0x18001adc9  xor     eax, eax
0x18001adcb  cmp     ecx, 0FFFFFFFFh
0x18001adce  jnz     short loc_18001AD7B
0x18001add0  cmp     rdx, [r10+104h]
0x18001add7  jmp     short loc_18001AD6A
0x18001add9  mov     ebx, 8007000Eh
0x18001adde  jmp     loc_18001ACFE
0x18001ade3  cmp     [rbp+arg_18], 0
0x18001ade7  jnz     loc_18001AC48
0x18001aded  mov     ebx, 0D0000001h
0x18001adf2  jmp     loc_18001ACFE
0x18001adf7  mov     rcx, cs:QuirksTable
0x18001adfe  test    rcx, rcx
0x18001ae01  jnz     short loc_18001AE1E
0x18001ae03  call    CptpQuirksInitOnce
0x18001ae08  mov     ebx, eax
0x18001ae0a  test    eax, eax
0x18001ae0c  jns     short loc_18001AE17
0x18001ae0e  bts     ebx, 1Ch
0x18001ae12  jmp     loc_18001ACFE
0x18001ae17  mov     rcx, cs:QuirksTable
0x18001ae1e  mov     edx, edi
0x18001ae20  call    QuirksLookupById
0x18001ae25  mov     r10, rax
0x18001ae28  test    rax, rax
0x18001ae2b  jz      loc_18001AD72
0x18001ae31  jmp     loc_18001AD9D
```
