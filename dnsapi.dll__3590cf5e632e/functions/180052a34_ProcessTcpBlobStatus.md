# ProcessTcpBlobStatus

- ea: `0x180052a34`
- end: `0x180052ba0`
- name: `ProcessTcpBlobStatus`
- size: `364`
- prototype: `__int64 __fastcall(int, int, int, int, PTP_CALLBACK_INSTANCE pci)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180051b5c`
- `0x1800528cc`
- `0x180073a30`

## callees

- `0x180020c64`
- `0x180051d34`
- `0x18005224c`
- `0x180052a34`
- `0x180053ce0`
- `0x180055ae8`
- `0x1800d2948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052a86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052a86`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052a9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052afd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052a9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052afd`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180052b8f`
- `api-ms-win-core-threadpool-l1-2-0!DisassociateCurrentThreadFromCallback` at `0x180052b8f`

## pseudocode

```c
void __fastcall ProcessTcpBlobStatus(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, PTP_CALLBACK_INSTANCE pci)
{
  int v6; // esi
  int v7; // ebp
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  int v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = 0;
  v6 = a3;
  v7 = a2;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qDll(a1, a2, a3, a1, a2, a3, a4);
  v9 = *(_QWORD *)(a1 + 88);
  if ( v6 )
    ThreadPool_WaitForTimer(*(PTP_TIMER *)(v9 + 512), 0);
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 528));
  if ( *(_DWORD *)(v9 + 580) || (*(_DWORD *)(v9 + 520) & 0x300) != 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 528));
  }
  else
  {
    v10 = *(_QWORD *)(a1 + 112);
    *(_DWORD *)(a1 + 196) = v7;
    if ( !*(_DWORD *)(v10 + 172) && v7 == 1460 )
      *(_DWORD *)(a1 + 196) = 10060;
    if ( pci )
      DisassociateCurrentThreadFromCallback(pci);
    *(_DWORD *)(v9 + 520) &= ~0x80u;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 528));
    if ( v7 == 1223 )
    {
      v11 = 1;
    }
    else
    {
      Recv_TcpComplete(a1, &v12);
      v11 = v12;
    }
    if ( v11 )
    {
      if ( !(unsigned int)Send_RemoveCancelWait(v9) )
        Send_AndRecvTcpComplete(a1);
    }
    else
    {
      Send_AndRecvTcp(a1, a4);
    }
  }
}

```

## disassembly

```asm
0x180052a34  mov     [rsp+arg_0], rbx
0x180052a39  mov     [rsp+arg_8], rbp
0x180052a3e  push    rsi
0x180052a3f  push    rdi
0x180052a40  push    r14
0x180052a42  sub     rsp, 40h
0x180052a46  mov     r14d, r9d
0x180052a49  mov     [rsp+58h+arg_10], 0
0x180052a51  mov     esi, r8d
0x180052a54  mov     ebp, edx
0x180052a56  mov     rbx, rcx
0x180052a59  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180052a60  jnz     loc_180052B5A
0x180052a66  mov     rdi, [rbx+58h]
0x180052a6a  test    esi, esi
0x180052a6c  jz      short loc_180052A7C
0x180052a6e  mov     rcx, [rdi+200h]; pti
0x180052a75  xor     edx, edx
0x180052a77  call    ThreadPool_WaitForTimer
0x180052a7c  lea     rsi, [rdi+210h]
0x180052a83  mov     rcx, rsi; lpCriticalSection
0x180052a86  call    cs:__imp_EnterCriticalSection
0x180052a8d  nop     dword ptr [rax+rax+00h]
0x180052a92  cmp     dword ptr [rdi+244h], 0
0x180052a99  jz      short loc_180052ABE
0x180052a9b  mov     rcx, rsi; lpCriticalSection
0x180052a9e  call    cs:__imp_LeaveCriticalSection
0x180052aa5  nop     dword ptr [rax+rax+00h]
0x180052aaa  mov     rbx, [rsp+58h+arg_0]
0x180052aaf  mov     rbp, [rsp+58h+arg_8]
0x180052ab4  add     rsp, 40h
0x180052ab8  pop     r14
0x180052aba  pop     rdi
0x180052abb  pop     rsi
0x180052abc  retn
0x180052abe  test    dword ptr [rdi+208h], 300h
0x180052ac8  jnz     short loc_180052A9B
0x180052aca  mov     rax, [rbx+70h]
0x180052ace  mov     [rbx+0C4h], ebp
0x180052ad4  cmp     dword ptr [rax+0ACh], 0
0x180052adb  jz      loc_180052B74
0x180052ae1  mov     rcx, [rsp+58h+pci]; pci
0x180052ae9  test    rcx, rcx
0x180052aec  jnz     loc_180052B8F
0x180052af2  btr     dword ptr [rdi+208h], 7
0x180052afa  mov     rcx, rsi; lpCriticalSection
0x180052afd  call    cs:__imp_LeaveCriticalSection
0x180052b04  nop     dword ptr [rax+rax+00h]
0x180052b09  cmp     ebp, 4C7h
0x180052b0f  jz      short loc_180052B36
0x180052b11  lea     rdx, [rsp+58h+arg_10]
0x180052b16  mov     rcx, rbx
0x180052b19  call    Recv_TcpComplete
0x180052b1e  mov     eax, [rsp+58h+arg_10]
0x180052b22  test    eax, eax
0x180052b24  jnz     short loc_180052B3D
0x180052b26  mov     edx, r14d
0x180052b29  mov     rcx, rbx
0x180052b2c  call    Send_AndRecvTcp
0x180052b31  jmp     loc_180052AAA
0x180052b36  mov     eax, 1
0x180052b3b  jmp     short loc_180052B22
0x180052b3d  mov     rcx, rdi
0x180052b40  call    Send_RemoveCancelWait
0x180052b45  test    eax, eax
0x180052b47  jnz     loc_180052AAA
0x180052b4d  mov     rcx, rbx
0x180052b50  call    Send_AndRecvTcpComplete
0x180052b55  jmp     loc_180052AAA
0x180052b5a  mov     [rsp+58h+var_28], r14d
0x180052b5f  mov     r9, rbx
0x180052b62  mov     [rsp+58h+var_30], esi
0x180052b66  mov     [rsp+58h+var_38], ebp
0x180052b6a  call    WPP_SF_qDll
0x180052b6f  jmp     loc_180052A66
0x180052b74  cmp     ebp, 5B4h
0x180052b7a  jnz     loc_180052AE1
0x180052b80  mov     dword ptr [rbx+0C4h], 274Ch
0x180052b8a  jmp     loc_180052AE1
0x180052b8f  call    cs:__imp_DisassociateCurrentThreadFromCallback
0x180052b96  nop     dword ptr [rax+rax+00h]
0x180052b9b  jmp     loc_180052AF2
```
