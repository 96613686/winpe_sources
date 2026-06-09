# ThreadPool_CreateTimer

- ea: `0x180046bf4`
- end: `0x180046d4b`
- name: `ThreadPool_CreateTimer`
- size: `343`
- prototype: `__int64 __usercall@<rax>(PTP_TIMER_CALLBACK pfnti@<rcx>, PVOID pv@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180046abc`
- `0x180046b58`
- `0x18004feb4`
- `0x180079b18`

## callees

- `0x180046bf4`
- `0x18008b5f0`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046ccb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180046c38`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180046c38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180046c98`

## pseudocode

```c
__int64 __fastcall ThreadPool_CreateTimer(
        PTP_TIMER_CALLBACK pfnti,
        PVOID pv,
        unsigned int a3,
        int a4,
        struct _TP_TIMER **a5)
{
  __int64 v6; // rbp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v10; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v13; // r9
  __int64 v14; // [rsp+30h] [rbp-38h] BYREF

  v6 = a3;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 20, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, pv, a3);
  ThreadpoolTimer = CreateThreadpoolTimer(pfnti, pv, 0);
  v10 = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    LastError = 0;
    if ( a4 )
    {
      v14 = 0;
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_qD(1035, 19, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, ThreadpoolTimer, v6);
      v14 = -10000 * v6;
      SetThreadpoolTimer(
        v10,
        (PFILETIME)((unsigned __int64)&v14 & -(__int64)((_DWORD)v6 != 0)),
        0,
        (unsigned int)v6 / 0xA);
    }
    *a5 = v10;
  }
  else
  {
    LastError = GetLastError();
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    if ( a5 )
      v13 = *a5;
    else
      v13 = 0;
    WPP_SF_qD(1035, 21, WPP_0ee542721a7b375122a881c30985be4a_Traceguids, v13, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180046bf4  push    rbx
0x180046bf6  push    rbp
0x180046bf7  push    rsi
0x180046bf8  push    rdi
0x180046bf9  push    r14
0x180046bfb  sub     rsp, 40h
0x180046bff  mov     rax, cs:__security_cookie
0x180046c06  xor     rax, rsp
0x180046c09  mov     [rsp+68h+var_30], rax
0x180046c0e  mov     rdi, [rsp+68h+arg_20]
0x180046c16  mov     r14d, r9d
0x180046c19  mov     ebp, r8d
0x180046c1c  mov     rbx, rdx
0x180046c1f  mov     rsi, rcx
0x180046c22  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180046c29  jnz     loc_180046CFD
0x180046c2f  xor     r8d, r8d; pcbe
0x180046c32  mov     rdx, rbx; pv
0x180046c35  mov     rcx, rsi; pfnti
0x180046c38  call    cs:__imp_CreateThreadpoolTimer
0x180046c3f  nop     dword ptr [rax+rax+00h]
0x180046c44  mov     rsi, rax
0x180046c47  test    rax, rax
0x180046c4a  jz      short loc_180046CCB
0x180046c4c  xor     ebx, ebx
0x180046c4e  test    r14d, r14d
0x180046c51  jz      short loc_180046CA4
0x180046c53  mov     [rsp+68h+var_38], rbx
0x180046c58  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180046c5f  jnz     short loc_180046CDB
0x180046c61  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x180046c68  mov     rcx, rax
0x180046c6b  mov     dword ptr [rsp+68h+var_38], eax
0x180046c6f  shr     rcx, 20h
0x180046c73  mov     eax, 0CCCCCCCDh
0x180046c78  mul     ebp
0x180046c7a  lea     rax, [rsp+68h+var_38]
0x180046c7f  mov     dword ptr [rsp+68h+var_38+4], ecx
0x180046c83  mov     r9d, edx
0x180046c86  mov     rcx, rsi; pti
0x180046c89  shr     r9d, 3; msWindowLength
0x180046c8d  neg     ebp
0x180046c8f  sbb     rdx, rdx
0x180046c92  xor     r8d, r8d; msPeriod
0x180046c95  and     rdx, rax; pftDueTime
0x180046c98  call    cs:__imp_SetThreadpoolTimer
0x180046c9f  nop     dword ptr [rax+rax+00h]
0x180046ca4  mov     [rdi], rsi
0x180046ca7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180046cae  jnz     short loc_180046D1F
0x180046cb0  mov     eax, ebx
0x180046cb2  mov     rcx, [rsp+68h+var_30]
0x180046cb7  xor     rcx, rsp; StackCookie
0x180046cba  call    __security_check_cookie
0x180046cbf  add     rsp, 40h
0x180046cc3  pop     r14
0x180046cc5  pop     rdi
0x180046cc6  pop     rsi
0x180046cc7  pop     rbp
0x180046cc8  pop     rbx
0x180046cc9  retn
0x180046ccb  call    cs:__imp_GetLastError
0x180046cd2  nop     dword ptr [rax+rax+00h]
0x180046cd7  mov     ebx, eax
0x180046cd9  jmp     short loc_180046CA7
0x180046cdb  mov     edx, 13h
0x180046ce0  mov     [rsp+68h+var_48], ebp
0x180046ce4  mov     ecx, 40Bh
0x180046ce9  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180046cf0  mov     r9, rsi
0x180046cf3  call    WPP_SF_qD
0x180046cf8  jmp     loc_180046C61
0x180046cfd  mov     edx, 14h
0x180046d02  mov     [rsp+68h+var_48], ebp
0x180046d06  mov     ecx, 40Bh
0x180046d0b  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180046d12  mov     r9, rbx
0x180046d15  call    WPP_SF_qD
0x180046d1a  jmp     loc_180046C2F
0x180046d1f  test    rdi, rdi
0x180046d22  jz      short loc_180046D29
0x180046d24  mov     r9, [rdi]
0x180046d27  jmp     short loc_180046D2C
0x180046d29  xor     r9d, r9d
0x180046d2c  mov     edx, 15h
0x180046d31  mov     [rsp+68h+var_48], ebx
0x180046d35  mov     ecx, 40Bh
0x180046d3a  lea     r8, WPP_0ee542721a7b375122a881c30985be4a_Traceguids
0x180046d41  call    WPP_SF_qD
0x180046d46  jmp     loc_180046CB0
```
