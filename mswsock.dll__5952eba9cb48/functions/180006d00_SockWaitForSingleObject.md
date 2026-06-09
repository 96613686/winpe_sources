# SockWaitForSingleObject

- ea: `0x180006d00`
- end: `0x18000706b`
- name: `SockWaitForSingleObject`
- size: `875`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `44`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001e60`
- `0x180004620`
- `0x180004700`
- `0x180005810`
- `0x1800060e0`
- `0x180007080`
- `0x180008320`
- `0x180008870`
- `0x180008cb0`
- `0x180009a08`
- `0x180009d20`
- `0x18000c2b0`
- `0x18000d000`
- `0x18000de00`
- `0x18000ea70`
- `0x18000faa0`
- `0x18000fe60`
- `0x180010030`
- `0x180012600`
- `0x180012c10`
- `0x180013234`
- `0x1800133cc`
- `0x180013520`
- `0x180013670`
- `0x180014420`
- `0x180014e38`
- `0x1800182d0`
- `0x1800198a0`
- `0x18001bc7c`
- `0x18001be40`
- `0x18001c2a0`
- `0x18001d4e8`
- `0x18001d600`
- `0x18001d8ac`
- `0x18001d990`
- `0x180021800`
- `0x180025530`
- `0x180027140`
- `0x180028aa0`
- `0x180028e50`
- `0x180040d78`
- `0x180044f0c`
- `0x18004b890`
- `0x18004d924`

## callees

- `0x180006d00`
- `0x180008190`
- `0x180008250`
- `0x18003ae8c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006d44`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006d44`
- `ntdll!NtWaitForSingleObject` at `0x180006e60`
- `ntdll!NtWaitForSingleObject` at `0x180006ed7`
- `ntdll!NtWaitForSingleObject` at `0x180006fd5`
- `ntdll!NtWaitForSingleObject` at `0x180006e60`
- `ntdll!NtWaitForSingleObject` at `0x180006ed7`
- `ntdll!NtWaitForSingleObject` at `0x180006fd5`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006f56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006f73`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006f56`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180006f73`

## pseudocode

```c
_BOOL8 __fastcall SockWaitForSingleObject(HANDLE Handle, void *a2, int a3, int a4)
{
  char v4; // r13
  __int64 v9; // rdx
  _BYTE *Value; // rdi
  __int64 v11; // r8
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // r12
  union _LARGE_INTEGER *p_Timeout; // r15
  NTSTATUS v16; // ebx
  NTSTATUS v17; // eax
  __int64 v19; // rax
  unsigned __int64 v20; // [rsp+30h] [rbp-30h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+38h] [rbp-28h] BYREF
  void (__fastcall *v22)(__int64); // [rsp+40h] [rbp-20h] BYREF
  __int64 v23; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+50h] [rbp-10h] BYREF

  v4 = 0;
  UnbiasedTime = 0;
  v22 = 0;
  v23 = 0;
  Value = TlsGetValue(MSAFD_SockTlsSlot);
  Timeout.QuadPart = -100000;
  if ( !SockSkipInitialShortWait && !NtWaitForSingleObject(Handle, 1u, &Timeout) )
    return 1;
  NtCurrentTeb()->WinSockData = a2;
  if ( (unsigned int)(a3 - 1) > 1 && a4 != 5 )
  {
    v12 = 0;
    if ( a4 != 6 )
    {
LABEL_32:
      if ( a3 != 2 || (*(_BYTE *)(v12 + 68) & 0x40) != 0 )
      {
        v22 = 0;
        v23 = 0;
LABEL_8:
        v14 = 0;
        if ( a4 == 4
          || (a4 == 5 ? (v19 = *(unsigned int *)(v12 + 52)) : (v19 = *(unsigned int *)(v12 + 56)), !(_DWORD)v19) )
        {
          p_Timeout = 0;
        }
        else
        {
          v14 = 10000 * v19;
          p_Timeout = &Timeout;
        }
        if ( v12 && _InterlockedExchangeAdd((volatile signed __int32 *)v12, 0xFFFFFFFF) == 1 )
          SockDestroySocket(v12, v9, v11);
        if ( v14 )
          QueryUnbiasedInterruptTime(&UnbiasedTime);
        else
          UnbiasedTime = 0;
        if ( v4 )
        {
          Timeout.QuadPart = -1;
          p_Timeout = &Timeout;
        }
        v16 = 0;
        Value[68] = 0;
        *((_QWORD *)Value + 3) = a2;
        while ( 1 )
        {
          if ( v4 )
            v22(v23);
          if ( Value[68] )
          {
            p_Timeout = 0;
          }
          else
          {
            if ( v16 == 258 && !v4 )
            {
LABEL_44:
              *((_QWORD *)Value + 3) = -1;
              NtCurrentTeb()->WinSockData = (PVOID)-1LL;
              return 0;
            }
            if ( v14 )
            {
              v20 = 0;
              QueryUnbiasedInterruptTime(&v20);
              if ( (__int64)(v20 - UnbiasedTime) > v14 )
                goto LABEL_44;
              if ( !v4 )
                Timeout.QuadPart = v20 - UnbiasedTime - v14;
            }
          }
          v17 = NtWaitForSingleObject(Handle, 1u, p_Timeout);
          v16 = v17;
          if ( v17 != 258 && v17 != 192 && v17 != 257 )
          {
            *((_QWORD *)Value + 3) = -1;
            NtCurrentTeb()->WinSockData = (PVOID)-1LL;
            return v17 == 0;
          }
        }
      }
LABEL_5:
      v22 = 0;
      v13 = *(unsigned int *)(v12 + 76);
      LODWORD(v20) = 0;
      if ( (*(unsigned int (__fastcall **)(__int64, void (__fastcall **)(__int64), __int64 *, unsigned __int64 *))(SockUpcallTable + 64))(
             v13,
             &v22,
             &v23,
             &v20) == -1
        && (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_d(1025, 19, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids, (unsigned int)v20);
      }
      if ( v22 )
        v4 = 1;
      goto LABEL_8;
    }
  }
  v12 = SockFindAndReferenceSocket(a2);
  if ( v12 )
  {
    if ( a3 == 1 )
      goto LABEL_5;
    goto LABEL_32;
  }
  NtWaitForSingleObject(Handle, 1u, 0);
  NtCurrentTeb()->WinSockData = (PVOID)-1LL;
  return 1;
}

```

## disassembly

```asm
0x180006d00  mov     [rsp-28h+arg_10], rbx
0x180006d05  mov     [rsp-28h+arg_18], rdi
0x180006d0a  mov     [rsp-28h+Handle], rcx
0x180006d0f  push    rbp
0x180006d10  push    r12
0x180006d12  push    r13
0x180006d14  push    r14
0x180006d16  push    r15
0x180006d18  mov     rbp, rsp
0x180006d1b  sub     rsp, 60h
0x180006d1f  xor     r13d, r13d
0x180006d22  mov     r12, rcx
0x180006d25  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180006d2b  mov     r15d, r9d
0x180006d2e  mov     qword ptr [rbp+Timeout], r13
0x180006d32  mov     ebx, r8d
0x180006d35  mov     [rbp+UnbiasedTime], r13
0x180006d39  mov     r14, rdx
0x180006d3c  mov     [rbp+var_20], r13
0x180006d40  mov     [rbp+var_18], r13
0x180006d44  call    cs:__imp_TlsGetValue
0x180006d4b  nop     dword ptr [rax+rax+00h]
0x180006d50  cmp     cs:SockSkipInitialShortWait, r13b
0x180006d57  mov     rdi, rax
0x180006d5a  mov     qword ptr [rbp+Timeout], 0FFFFFFFFFFFE7960h
0x180006d62  jz      loc_180006ECE
0x180006d68  mov     rax, gs:30h
0x180006d71  mov     [rsp+60h+arg_8], rsi
0x180006d79  mov     [rax+1738h], r14
0x180006d80  lea     eax, [rbx-1]
0x180006d83  cmp     eax, 1
0x180006d86  ja      loc_180006EF2
0x180006d8c  xor     edx, edx
0x180006d8e  mov     rcx, r14
0x180006d91  call    SockFindAndReferenceSocket
0x180006d96  mov     rsi, rax
0x180006d99  test    rax, rax
0x180006d9c  jz      loc_180006FCD
0x180006da2  cmp     ebx, 1
0x180006da5  jnz     loc_180006F09
0x180006dab  mov     rax, cs:SockUpcallTable
0x180006db2  lea     r9, [rbp+var_30]
0x180006db6  mov     [rbp+var_20], r13
0x180006dba  lea     r8, [rbp+var_18]
0x180006dbe  mov     ecx, [rsi+4Ch]
0x180006dc1  lea     rdx, [rbp+var_20]
0x180006dc5  mov     dword ptr [rbp+var_30], r13d
0x180006dc9  mov     rax, [rax+40h]
0x180006dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd2  cmp     eax, 0FFFFFFFFh
0x180006dd5  jz      loc_18000700F
0x180006ddb  cmp     [rbp+var_20], r13
0x180006ddf  jnz     loc_180007007
0x180006de5  xor     r12d, r12d
0x180006de8  cmp     r15d, 4
0x180006dec  jnz     loc_180006F2D
0x180006df2  mov     r15, r12
0x180006df5  test    rsi, rsi
0x180006df8  jz      short loc_180006E0C
0x180006dfa  mov     eax, 0FFFFFFFFh
0x180006dff  lock xadd [rsi], eax
0x180006e03  cmp     eax, 1
0x180006e06  jz      loc_18000703B
0x180006e0c  test    r12, r12
0x180006e0f  jnz     loc_180006F52
0x180006e15  mov     [rbp+UnbiasedTime], r12
0x180006e19  test    r13b, r13b
0x180006e1c  jnz     loc_180007048
0x180006e22  mov     rsi, [rbp+Handle]
0x180006e26  xor     ebx, ebx
0x180006e28  mov     byte ptr [rdi+44h], 0
0x180006e2c  mov     [rdi+18h], r14
0x180006e30  test    r13b, r13b
0x180006e33  jnz     loc_180007059
0x180006e39  cmp     byte ptr [rdi+44h], 0
0x180006e3d  jnz     loc_180006EC9
0x180006e43  cmp     ebx, 102h
0x180006e49  jz      loc_180006FA1
0x180006e4f  test    r12, r12
0x180006e52  jnz     loc_180006F67
0x180006e58  mov     r8, r15; Timeout
0x180006e5b  mov     dl, 1; Alertable
0x180006e5d  mov     rcx, rsi; Handle
0x180006e60  call    cs:__imp_NtWaitForSingleObject
0x180006e67  nop     dword ptr [rax+rax+00h]
0x180006e6c  mov     ebx, eax
0x180006e6e  cmp     eax, 102h
0x180006e73  jz      short loc_180006E30
0x180006e75  cmp     eax, 0C0h
0x180006e7a  jz      short loc_180006E30
0x180006e7c  cmp     eax, 101h
0x180006e81  jz      short loc_180006E30
0x180006e83  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180006e8b  mov     rax, gs:30h
0x180006e94  mov     qword ptr [rax+1738h], 0FFFFFFFFFFFFFFFFh
0x180006e9f  xor     eax, eax
0x180006ea1  test    ebx, ebx
0x180006ea3  setz    al
0x180006ea6  mov     rsi, [rsp+60h+arg_8]
0x180006eae  lea     r11, [rsp+60h+var_s0]
0x180006eb3  mov     rbx, [r11+40h]
0x180006eb7  mov     rdi, [r11+48h]
0x180006ebb  mov     rsp, r11
0x180006ebe  pop     r15
0x180006ec0  pop     r14
0x180006ec2  pop     r13
0x180006ec4  pop     r12
0x180006ec6  pop     rbp
0x180006ec7  retn
0x180006ec9  xor     r15d, r15d
0x180006ecc  jmp     short loc_180006E58
0x180006ece  lea     r8, [rbp+Timeout]; Timeout
0x180006ed2  mov     dl, 1; Alertable
0x180006ed4  mov     rcx, r12; Handle
0x180006ed7  call    cs:__imp_NtWaitForSingleObject
0x180006ede  nop     dword ptr [rax+rax+00h]
0x180006ee3  test    eax, eax
0x180006ee5  jnz     loc_180006D68
0x180006eeb  mov     eax, 1
0x180006ef0  jmp     short loc_180006EAE
0x180006ef2  cmp     r15d, 5
0x180006ef6  jz      loc_180006D8C
0x180006efc  mov     rsi, r13
0x180006eff  cmp     r15d, 6
0x180006f03  jz      loc_180006D8C
0x180006f09  cmp     ebx, 2
0x180006f0c  jnz     short loc_180006F18
0x180006f0e  test    byte ptr [rsi+44h], 40h
0x180006f12  jz      loc_180006DAB
0x180006f18  mov     [rbp+var_20], 0
0x180006f20  mov     [rbp+var_18], 0
0x180006f28  jmp     loc_180006DE5
0x180006f2d  cmp     r15d, 5
0x180006f31  jz      loc_180006FFF
0x180006f37  mov     eax, [rsi+38h]
0x180006f3a  test    eax, eax
0x180006f3c  jz      loc_180006DF2
0x180006f42  imul    r12, rax, 2710h
0x180006f49  lea     r15, [rbp+Timeout]
0x180006f4d  jmp     loc_180006DF5
0x180006f52  lea     rcx, [rbp+UnbiasedTime]; UnbiasedTime
0x180006f56  call    cs:__imp_QueryUnbiasedInterruptTime
0x180006f5d  nop     dword ptr [rax+rax+00h]
0x180006f62  jmp     loc_180006E19
0x180006f67  lea     rcx, [rbp+var_30]; UnbiasedTime
0x180006f6b  mov     [rbp+var_30], 0
0x180006f73  call    cs:__imp_QueryUnbiasedInterruptTime
0x180006f7a  nop     dword ptr [rax+rax+00h]
0x180006f7f  mov     rax, [rbp+var_30]
0x180006f83  sub     rax, [rbp+UnbiasedTime]
0x180006f87  cmp     rax, r12
0x180006f8a  jg      short loc_180006FAA
0x180006f8c  test    r13b, r13b
0x180006f8f  jnz     loc_180006E58
0x180006f95  sub     rax, r12
0x180006f98  mov     qword ptr [rbp+Timeout], rax
0x180006f9c  jmp     loc_180006E58
0x180006fa1  test    r13b, r13b
0x180006fa4  jnz     loc_180006E4F
0x180006faa  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180006fb2  mov     rax, gs:30h
0x180006fbb  mov     qword ptr [rax+1738h], 0FFFFFFFFFFFFFFFFh
0x180006fc6  xor     eax, eax
0x180006fc8  jmp     loc_180006EA6
0x180006fcd  xor     r8d, r8d; Timeout
0x180006fd0  mov     dl, 1; Alertable
0x180006fd2  mov     rcx, r12; Handle
0x180006fd5  call    cs:__imp_NtWaitForSingleObject
0x180006fdc  nop     dword ptr [rax+rax+00h]
0x180006fe1  mov     rax, gs:30h
0x180006fea  mov     qword ptr [rax+1738h], 0FFFFFFFFFFFFFFFFh
0x180006ff5  mov     eax, 1
0x180006ffa  jmp     loc_180006EA6
0x180006fff  mov     eax, [rsi+34h]
0x180007002  jmp     loc_180006F3A
0x180007007  mov     r13b, 1
0x18000700a  jmp     loc_180006DE5
0x18000700f  test    byte ptr cs:xmmword_180063D60, 2
0x180007016  jz      loc_180006DDB
0x18000701c  mov     r9d, dword ptr [rbp+var_30]
0x180007020  lea     r8, WPP_7d3a2c81e5df3cefdd06dcec6b626151_Traceguids
0x180007027  mov     edx, 13h
0x18000702c  mov     ecx, 401h
0x180007031  call    WPP_SF_d
0x180007036  jmp     loc_180006DDB
0x18000703b  mov     rcx, rsi
0x18000703e  call    SockDestroySocket
0x180007043  jmp     loc_180006E0C
0x180007048  mov     qword ptr [rbp+Timeout], 0FFFFFFFFFFFFFFFFh
0x180007050  lea     r15, [rbp+Timeout]
0x180007054  jmp     loc_180006E22
0x180007059  mov     rcx, [rbp+var_18]
0x18000705d  mov     rax, [rbp+var_20]
0x180007061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007066  jmp     loc_180006E39
```
