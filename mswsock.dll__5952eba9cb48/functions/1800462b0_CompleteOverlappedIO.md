# CompleteOverlappedIO

- ea: `0x1800462b0`
- end: `0x180046423`
- name: `CompleteOverlappedIO`
- size: `371`
- prototype: ``
- caller_count: `16`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003b760`
- `0x18003c7cc`
- `0x18003ec84`
- `0x180040d78`
- `0x1800411a8`
- `0x180044800`
- `0x1800453ec`
- `0x180045cfc`
- `0x18004642c`
- `0x180046c34`
- `0x180047cb0`
- `0x180049ba8`
- `0x18004b1d0`
- `0x18004b890`
- `0x18004c4b8`
- `0x180050074`

## callees

- `0x1800052a0`
- `0x180025048`
- `0x180038b18`
- `0x180038b88`
- `0x180038dc4`
- `0x1800462b0`
- `0x18004f27c`

## import_xrefs

- `ntdll!NtQueueApcThread` at `0x18004637f`
- `ntdll!NtQueueApcThread` at `0x18004637f`

## pseudocode

```c
__int64 __fastcall CompleteOverlappedIO(__int64 a1, __int64 a2, void *a3, void *a4, unsigned int a5, unsigned int a6)
{
  char v10; // al
  unsigned int v11; // r14d
  int v12; // edx
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edi
  __int64 v16; // r8
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  _OWORD v22[3]; // [rsp+40h] [rbp-38h] BYREF

  v22[0] = 0;
  v10 = xmmword_180063D60;
  if ( (xmmword_180063D60 & 0x80u) != 0LL )
  {
    WPP_SF_iqdd(1031, 222, a3, a1, a2, a5, a6);
    v10 = xmmword_180063D60;
  }
  if ( (v10 & 0x40) != 0 )
    WPP_SF_iqdd(1030, 223, a3, a1, a2, a5, a6);
  v11 = SocketErrorToNtStatus(a5);
  *(_QWORD *)(a2 + 8) = a6;
  *(_DWORD *)(a2 + 20) = v12;
  if ( a3 )
  {
    _InterlockedExchange64((volatile __int64 *)a2, v11);
    v15 = NtQueueApcThread(a4, SockIoCompletion, a3, (PVOID)a2, 0);
    if ( (v15 & 0x80000000) != 0 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_Lq(v14, v13, v16, v15, *(unsigned int *)(a2 + 16));
      return NtStatusToSocketError(v15);
    }
  }
  else
  {
    LODWORD(v22[0]) = v11;
    *((_QWORD *)&v22[0] + 1) = a6;
    v18 = AfdCompleteRequest(a1, a2, v22);
    v15 = v18;
    if ( v18 < 0 && v18 != v11 )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_Diqq(v20, v19, v21, (unsigned int)v18, a1, a2, v22);
      return NtStatusToSocketError(v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800462b0  mov     r11, rsp
0x1800462b3  push    rbx
0x1800462b4  push    rsi
0x1800462b5  push    rdi
0x1800462b6  push    r14
0x1800462b8  push    r15
0x1800462ba  sub     rsp, 50h
0x1800462be  mov     r15, r9
0x1800462c1  mov     rdi, r8
0x1800462c4  mov     rbx, rdx
0x1800462c7  mov     rsi, rcx
0x1800462ca  xorps   xmm0, xmm0
0x1800462cd  movups  [rsp+78h+var_38], xmm0
0x1800462d2  mov     al, byte ptr cs:xmmword_180063D60
0x1800462d8  test    al, al
0x1800462da  jns     short loc_18004630B
0x1800462dc  mov     edx, 0DEh
0x1800462e1  mov     ecx, 407h
0x1800462e6  mov     eax, [rsp+78h+arg_28]
0x1800462ed  mov     dword ptr [rsp+78h+var_48], eax
0x1800462f1  mov     eax, [r11+28h]
0x1800462f5  mov     dword ptr [rsp+78h+var_50], eax
0x1800462f9  mov     [r11-58h], rbx
0x1800462fd  mov     r9, rsi
0x180046300  call    WPP_SF_iqdd
0x180046305  mov     al, byte ptr cs:xmmword_180063D60
0x18004630b  test    al, 40h
0x18004630d  jz      short loc_18004633C
0x18004630f  mov     edx, 0DFh
0x180046314  mov     ecx, 406h
0x180046319  mov     eax, [rsp+78h+arg_28]
0x180046320  mov     dword ptr [rsp+78h+var_48], eax
0x180046324  mov     eax, [rsp+78h+arg_20]
0x18004632b  mov     dword ptr [rsp+78h+var_50], eax
0x18004632f  mov     [rsp+78h+SystemArgument2], rbx
0x180046334  mov     r9, rsi
0x180046337  call    WPP_SF_iqdd
0x18004633c  mov     edx, [rsp+78h+arg_20]
0x180046343  mov     ecx, edx
0x180046345  call    SocketErrorToNtStatus
0x18004634a  mov     r14d, eax
0x18004634d  mov     eax, [rsp+78h+arg_28]
0x180046354  mov     [rbx+8], rax
0x180046358  mov     [rbx+14h], edx
0x18004635b  test    rdi, rdi
0x18004635e  jz      short loc_1800463B3
0x180046360  mov     eax, r14d
0x180046363  xchg    rax, [rbx]
0x180046366  mov     [rsp+78h+SystemArgument2], 0; SystemArgument2
0x18004636f  mov     r9, rbx; SystemArgument1
0x180046372  mov     r8, rdi; NormalContext
0x180046375  lea     rdx, SockIoCompletion; ApcRoutine
0x18004637c  mov     rcx, r15; ThreadHandle
0x18004637f  call    cs:__imp_NtQueueApcThread
0x180046386  nop     dword ptr [rax+rax+00h]
0x18004638b  mov     edi, eax
0x18004638d  test    eax, eax
0x18004638f  jns     short loc_1800463FF
0x180046391  test    byte ptr cs:xmmword_180063D60, 2
0x180046398  jz      short loc_1800463AA
0x18004639a  mov     eax, [rbx+10h]
0x18004639d  mov     [rsp+78h+SystemArgument2], rax
0x1800463a2  mov     r9d, edi
0x1800463a5  call    WPP_SF_Lq
0x1800463aa  mov     ecx, edi
0x1800463ac  call    NtStatusToSocketError
0x1800463b1  jmp     short loc_180046401
0x1800463b3  mov     dword ptr [rsp+78h+var_38], r14d
0x1800463b8  mov     qword ptr [rsp+78h+var_38+8], rax
0x1800463bd  lea     r8, [rsp+78h+var_38]
0x1800463c2  mov     rdx, rbx
0x1800463c5  mov     rcx, rsi
0x1800463c8  call    AfdCompleteRequest
0x1800463cd  mov     edi, eax
0x1800463cf  test    eax, eax
0x1800463d1  jns     short loc_1800463FF
0x1800463d3  cmp     eax, r14d
0x1800463d6  jz      short loc_1800463FF
0x1800463d8  test    byte ptr cs:xmmword_180063D60, 2
0x1800463df  jz      short loc_1800463AA
0x1800463e1  lea     rax, [rsp+78h+var_38]
0x1800463e6  mov     [rsp+78h+var_48], rax
0x1800463eb  mov     [rsp+78h+var_50], rbx
0x1800463f0  mov     [rsp+78h+SystemArgument2], rsi
0x1800463f5  mov     r9d, edi
0x1800463f8  call    WPP_SF_Diqq
0x1800463fd  jmp     short loc_1800463AA
0x1800463ff  xor     eax, eax
0x180046401  mov     [rsp+78h+arg_20], eax
0x180046408  jmp     short loc_180046416
0x18004640a  mov     eax, 271Eh
0x18004640f  mov     [rsp+78h+arg_20], eax
0x180046416  add     rsp, 50h
0x18004641a  pop     r15
0x18004641c  pop     r14
0x18004641e  pop     rdi
0x18004641f  pop     rsi
0x180046420  pop     rbx
0x180046421  retn
```
