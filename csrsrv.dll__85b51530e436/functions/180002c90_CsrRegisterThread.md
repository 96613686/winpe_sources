# CsrRegisterThread

- ea: `0x180002c90`
- end: `0x180002f4c`
- name: `CsrRegisterThread`
- size: `700`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800021f0`

## callees

- `0x180002c90`
- `0x180002f60`
- `0x180002fd0`
- `0x1800035c0`
- `0x180003780`
- `0x180003930`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtClose` at `0x180002e06`
- `ntdll!NtClose` at `0x180002e8f`
- `ntdll!NtClose` at `0x180002e06`
- `ntdll!NtClose` at `0x180002e8f`
- `ntdll!RtlFreeHeap` at `0x180002f3b`
- `ntdll!RtlFreeHeap` at `0x180002f3b`
- `ntdll!RtlEnterCriticalSection` at `0x180002d6f`
- `ntdll!RtlEnterCriticalSection` at `0x180002d6f`
- `ntdll!NtQueryInformationThread` at `0x180002d93`
- `ntdll!NtQueryInformationThread` at `0x180002d93`
- `ntdll!RtlLeaveCriticalSection` at `0x180002df7`
- `ntdll!RtlLeaveCriticalSection` at `0x180002e7a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002eda`
- `ntdll!RtlLeaveCriticalSection` at `0x180002eef`
- `ntdll!RtlLeaveCriticalSection` at `0x180002df7`
- `ntdll!RtlLeaveCriticalSection` at `0x180002e7a`
- `ntdll!RtlLeaveCriticalSection` at `0x180002eda`
- `ntdll!RtlLeaveCriticalSection` at `0x180002eef`
- `ntdll!NtAlpcOpenSenderThread` at `0x180002d11`
- `ntdll!NtAlpcOpenSenderThread` at `0x180002d11`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180002f09`
- `ntdll!NtRegisterThreadTerminatePort` at `0x180002f09`

## string_xrefs

- `0x180002ebf`: `CsrCreateThread`

## pseudocode

```c
__int64 __fastcall CsrRegisterThread(__int64 a1, __int64 a2)
{
  bool v2; // zf
  int v4; // eax
  __int64 result; // rax
  HANDLE v7; // rbp
  NTSTATUS InformationThread; // esi
  __int64 *v9; // rdx
  __int64 *i; // rax
  char *Thread; // r14
  __int128 v12; // xmm0
  HANDLE ThreadHandle; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v14[4]; // [rsp+38h] [rbp-80h] BYREF
  __int128 v15; // [rsp+58h] [rbp-60h]
  _OWORD ThreadInformation[2]; // [rsp+68h] [rbp-50h] BYREF

  v14[0] = 48;
  v2 = (*(_DWORD *)(a1 + 92) & 0x2000) == 0;
  v14[3] = 0;
  v4 = 0x1FFFFF;
  ThreadHandle = 0;
  if ( !v2 )
    v4 = 1055744;
  v14[1] = 0;
  v14[2] = 0;
  v15 = 0;
  result = NtAlpcOpenSenderThread(&ThreadHandle, CsrApiPort, a2, 0, v4, v14);
  if ( (int)result >= 0 )
  {
    v7 = ThreadHandle;
    memset(ThreadInformation, 0, sizeof(ThreadInformation));
    RtlEnterCriticalSection(&CsrProcessStructureLock);
    InformationThread = NtQueryInformationThread(v7, ThreadTimes, ThreadInformation, 0x20u, 0);
    if ( InformationThread >= 0 )
    {
      v9 = &CsrThreadHashTable[2 * ((*(_DWORD *)(a2 + 16) >> 2) & 0x3FF)];
      for ( i = (__int64 *)*v9; i != v9; i = (__int64 *)*i )
      {
        if ( i[3] == *(_QWORD *)(a2 + 16) && i[2] == *(_QWORD *)(a2 + 8) )
        {
          if ( *(i - 3) == *(_QWORD *)&ThreadInformation[0] )
          {
            RtlLeaveCriticalSection(&CsrProcessStructureLock);
            NtClose(v7);
            return 0;
          }
          break;
        }
      }
      if ( (*(_BYTE *)(a1 + 92) & 8) == 0 )
      {
        Thread = (char *)CsrAllocateThread(a1);
        if ( !Thread )
        {
          RtlLeaveCriticalSection(&CsrProcessStructureLock);
          InformationThread = -1073741801;
          goto LABEL_17;
        }
        *(_QWORD *)Thread = *(_QWORD *)&ThreadInformation[0];
        v12 = *(_OWORD *)(a2 + 8);
        *((_QWORD *)Thread + 8) = v7;
        *((_DWORD *)Thread + 18) = 0;
        *(_OWORD *)(Thread + 40) = v12;
        InformationThread = CsrInsertThread(a1, Thread);
        if ( InformationThread >= 0 )
        {
          if ( a1 != CsrRootProcess
            || (InformationThread = NtRegisterThreadTerminatePort(CsrApiPort), InformationThread >= 0) )
          {
LABEL_16:
            RtlLeaveCriticalSection(&CsrProcessStructureLock);
            if ( InformationThread >= 0 )
              return (unsigned int)InformationThread;
LABEL_17:
            NtClose(ThreadHandle);
            return (unsigned int)InformationThread;
          }
          CsrRemoveThread(Thread);
        }
        CsrLockedDereferenceProcess(a1);
        RtlFreeHeap(CsrHeap, 0, Thread);
        goto LABEL_16;
      }
      InformationThread = -1073741749;
      CsrpLogFailure("CsrCreateThread");
    }
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x180002c90  push    rbx
0x180002c92  push    rdi
0x180002c93  push    r15
0x180002c95  sub     rsp, 0A0h
0x180002c9c  mov     rax, cs:__security_cookie
0x180002ca3  xor     rax, rsp
0x180002ca6  mov     [rsp+0B8h+var_30], rax
0x180002cae  xor     r15d, r15d
0x180002cb1  mov     [rsp+0B8h+var_80], 30h ; '0'
0x180002cba  test    dword ptr [rcx+5Ch], 2000h
0x180002cc1  mov     rdi, rcx
0x180002cc4  mov     ecx, 101C00h
0x180002cc9  mov     [rsp+0B8h+var_68], r15
0x180002cce  mov     eax, 1FFFFFh
0x180002cd3  mov     [rsp+0B8h+ThreadHandle], r15
0x180002cd8  cmovnz  eax, ecx
0x180002cdb  mov     [rsp+0B8h+var_78], r15
0x180002ce0  lea     rcx, [rsp+0B8h+var_80]
0x180002ce5  mov     [rsp+0B8h+var_70], r15
0x180002cea  mov     [rsp+0B8h+var_90], rcx
0x180002cef  mov     rbx, rdx
0x180002cf2  xorps   xmm0, xmm0
0x180002cf5  mov     dword ptr [rsp+0B8h+ReturnLength], eax
0x180002cf9  mov     r8, rdx
0x180002cfc  lea     rcx, [rsp+0B8h+ThreadHandle]
0x180002d01  mov     rdx, cs:CsrApiPort
0x180002d08  xor     r9d, r9d
0x180002d0b  movdqu  [rsp+0B8h+var_60], xmm0
0x180002d11  call    cs:__imp_NtAlpcOpenSenderThread
0x180002d18  nop     dword ptr [rax+rax+00h]
0x180002d1d  test    eax, eax
0x180002d1f  jns     short loc_180002D3E
0x180002d21  mov     rcx, [rsp+0B8h+var_30]
0x180002d29  xor     rcx, rsp; StackCookie
0x180002d2c  call    __security_check_cookie
0x180002d31  add     rsp, 0A0h
0x180002d38  pop     r15
0x180002d3a  pop     rdi
0x180002d3b  pop     rbx
0x180002d3c  retn
0x180002d3e  mov     [rsp+0B8h+arg_10], rbp
0x180002d46  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002d4d  mov     rbp, [rsp+0B8h+ThreadHandle]
0x180002d52  xorps   xmm0, xmm0
0x180002d55  mov     [rsp+0B8h+var_20], rsi
0x180002d5d  mov     [rsp+0B8h+var_28], r14
0x180002d65  movups  [rsp+0B8h+ThreadInformation], xmm0
0x180002d6a  movups  [rsp+0B8h+var_40], xmm0
0x180002d6f  call    cs:__imp_RtlEnterCriticalSection
0x180002d76  nop     dword ptr [rax+rax+00h]
0x180002d7b  mov     r9d, 20h ; ' '; ThreadInformationLength
0x180002d81  mov     [rsp+0B8h+ReturnLength], r15; ReturnLength
0x180002d86  lea     r8, [rsp+0B8h+ThreadInformation]; ThreadInformation
0x180002d8b  mov     edx, 1; ThreadInformationClass
0x180002d90  mov     rcx, rbp; ThreadHandle
0x180002d93  call    cs:__imp_NtQueryInformationThread
0x180002d9a  nop     dword ptr [rax+rax+00h]
0x180002d9f  mov     esi, eax
0x180002da1  test    eax, eax
0x180002da3  js      loc_180002ED3
0x180002da9  mov     edx, [rbx+10h]
0x180002dac  lea     rcx, CsrThreadHashTable
0x180002db3  shr     rdx, 2
0x180002db7  and     edx, 3FFh
0x180002dbd  shl     rdx, 4
0x180002dc1  add     rdx, rcx
0x180002dc4  mov     rax, [rdx]
0x180002dc7  cmp     rax, rdx
0x180002dca  jz      short loc_180002E1A
0x180002dcc  mov     rcx, [rbx+10h]
0x180002dd0  cmp     [rax+18h], rcx
0x180002dd4  jz      short loc_180002DDB
0x180002dd6  mov     rax, [rax]
0x180002dd9  jmp     short loc_180002DC7
0x180002ddb  mov     rcx, [rbx+8]
0x180002ddf  cmp     [rax+10h], rcx
0x180002de3  jnz     short loc_180002DD6
0x180002de5  mov     rcx, qword ptr [rsp+0B8h+ThreadInformation]
0x180002dea  cmp     [rax-18h], rcx
0x180002dee  jnz     short loc_180002E1A
0x180002df0  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002df7  call    cs:__imp_RtlLeaveCriticalSection
0x180002dfe  nop     dword ptr [rax+rax+00h]
0x180002e03  mov     rcx, rbp; Handle
0x180002e06  call    cs:__imp_NtClose
0x180002e0d  nop     dword ptr [rax+rax+00h]
0x180002e12  mov     eax, r15d
0x180002e15  jmp     loc_180002E9D
0x180002e1a  test    byte ptr [rdi+5Ch], 8
0x180002e1e  jnz     loc_180002EBA
0x180002e24  mov     rcx, rdi
0x180002e27  call    CsrAllocateThread
0x180002e2c  mov     r14, rax
0x180002e2f  test    rax, rax
0x180002e32  jz      loc_180002EE8
0x180002e38  mov     rax, qword ptr [rsp+0B8h+ThreadInformation]
0x180002e3d  mov     rdx, r14
0x180002e40  mov     [r14], rax
0x180002e43  mov     rcx, rdi
0x180002e46  movups  xmm0, xmmword ptr [rbx+8]
0x180002e4a  mov     [r14+40h], rbp
0x180002e4e  mov     [r14+48h], r15d
0x180002e52  movups  xmmword ptr [r14+28h], xmm0
0x180002e57  call    CsrInsertThread
0x180002e5c  mov     esi, eax
0x180002e5e  test    eax, eax
0x180002e60  js      loc_180002F27
0x180002e66  cmp     rdi, cs:CsrRootProcess
0x180002e6d  jz      loc_180002F02
0x180002e73  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002e7a  call    cs:__imp_RtlLeaveCriticalSection
0x180002e81  nop     dword ptr [rax+rax+00h]
0x180002e86  test    esi, esi
0x180002e88  jns     short loc_180002E9B
0x180002e8a  mov     rcx, [rsp+0B8h+ThreadHandle]; Handle
0x180002e8f  call    cs:__imp_NtClose
0x180002e96  nop     dword ptr [rax+rax+00h]
0x180002e9b  mov     eax, esi
0x180002e9d  mov     r14, [rsp+0B8h+var_28]
0x180002ea5  mov     rbp, [rsp+0B8h+arg_10]
0x180002ead  mov     rsi, [rsp+0B8h+var_20]
0x180002eb5  jmp     loc_180002D21
0x180002eba  mov     esi, 0C000004Bh
0x180002ebf  lea     rcx, aCsrcreatethrea_0; "CsrCreateThread"
0x180002ec6  mov     r8d, esi
0x180002ec9  mov     edx, 4C5h
0x180002ece  call    CsrpLogFailure
0x180002ed3  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002eda  call    cs:__imp_RtlLeaveCriticalSection
0x180002ee1  nop     dword ptr [rax+rax+00h]
0x180002ee6  jmp     short loc_180002E8A
0x180002ee8  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002eef  call    cs:__imp_RtlLeaveCriticalSection
0x180002ef6  nop     dword ptr [rax+rax+00h]
0x180002efb  mov     esi, 0C0000017h
0x180002f00  jmp     short loc_180002E8A
0x180002f02  mov     rcx, cs:CsrApiPort; TerminationPort
0x180002f09  call    cs:__imp_NtRegisterThreadTerminatePort
0x180002f10  nop     dword ptr [rax+rax+00h]
0x180002f15  mov     esi, eax
0x180002f17  test    eax, eax
0x180002f19  jns     loc_180002E73
0x180002f1f  mov     rcx, r14
0x180002f22  call    CsrRemoveThread
0x180002f27  mov     rcx, rdi
0x180002f2a  call    CsrLockedDereferenceProcess
0x180002f2f  mov     rcx, cs:CsrHeap; HeapHandle
0x180002f36  mov     r8, r14; BaseAddress
0x180002f39  xor     edx, edx; Flags
0x180002f3b  call    cs:__imp_RtlFreeHeap
0x180002f42  nop     dword ptr [rax+rax+00h]
0x180002f47  jmp     loc_180002E73
```
