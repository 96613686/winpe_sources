# CPortClient::SendComplexAsyncRequest(ulong,void const *,short)

- ea: `0x140002cf0`
- end: `0x140002e1c`
- name: `?SendComplexAsyncRequest@CPortClient@@QEAAJKPEBXF@Z`
- size: `300`
- prototype: `__int64 __fastcall(CPortClient *__hidden this, unsigned int, const void *, __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002c64`

## callees

- `0x140002cf0`
- `0x140002e6c`
- `0x14000da7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002dfb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002d38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002dfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002e09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002e09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002d4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140002d4a`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140002daf`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x140002daf`

## pseudocode

```c
__int64 __fastcall CPortClient::SendComplexAsyncRequest(CPortClient *this, int a2, _QWORD *a3)
{
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v8; // rax
  void *v9; // rdi
  int v10; // r9d
  HANDLE v11; // rax

  if ( a3 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, 0x38u);
    v9 = v8;
    if ( v8 )
    {
      v8[10] = a2;
      *v8 = 3670032;
      *((_QWORD *)v8 + 6) = *a3;
      v6 = NtAlpcSendWaitReceivePort(*((_QWORD *)this + 2), 0x10000, v8, 0, 0, 0, 0, 0) | 0x10000000;
      CPortClient::CheckHRESULT(this, v6);
      if ( v10 >= 0 )
        v6 = 0;
      else
        MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v6, 0x19Cu, 0);
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v9);
    }
    else
    {
      v6 = -2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(
        4u,
        &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
        9u,
        -2147024882,
        0x18Bu,
        0);
    }
  }
  else
  {
    v6 = -2147024890;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, -2147024890, 0x188u, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x140002cf0  push    rbx
0x140002cf2  push    rbp
0x140002cf3  push    rsi
0x140002cf4  push    rdi
0x140002cf5  push    r15
0x140002cf7  sub     rsp, 40h
0x140002cfb  mov     rbx, r8
0x140002cfe  mov     ebp, edx
0x140002d00  mov     rsi, rcx
0x140002d03  test    r8, r8
0x140002d06  jnz     short loc_140002D38
0x140002d08  mov     [rsp+68h+var_40], r8; void *
0x140002d0d  mov     ebx, 80070006h
0x140002d12  mov     [rsp+68h+var_48], 188h; unsigned int
0x140002d1a  mov     r8d, 9; unsigned int
0x140002d20  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x140002d27  mov     r9d, ebx; int
0x140002d2a  lea     ecx, [r8-5]; unsigned int
0x140002d2e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140002d33  jmp     loc_140002E0F
0x140002d38  call    cs:__imp_GetProcessHeap
0x140002d3e  mov     edx, 8; dwFlags
0x140002d43  mov     rcx, rax; hHeap
0x140002d46  lea     r8d, [rdx+30h]; dwBytes
0x140002d4a  call    cs:__imp_HeapAlloc
0x140002d50  mov     rdi, rax
0x140002d53  test    rax, rax
0x140002d56  jnz     short loc_140002D6C
0x140002d58  mov     [rsp+68h+var_40], rax
0x140002d5d  mov     ebx, 8007000Eh
0x140002d62  mov     [rsp+68h+var_48], 18Bh
0x140002d6a  jmp     short loc_140002D1A
0x140002d6c  mov     [rax+28h], ebp
0x140002d6f  xor     r9d, r9d
0x140002d72  mov     dword ptr [rax], 380010h
0x140002d78  mov     r8, rdi
0x140002d7b  mov     rax, [rbx]
0x140002d7e  mov     edx, 10000h
0x140002d83  mov     [rsp+68h+var_30], 0
0x140002d8c  mov     [rdi+30h], rax
0x140002d90  mov     rcx, [rsi+10h]
0x140002d94  mov     [rsp+68h+var_38], 0
0x140002d9d  mov     [rsp+68h+var_40], 0
0x140002da6  mov     qword ptr [rsp+68h+var_48], 0
0x140002daf  call    cs:__imp_NtAlpcSendWaitReceivePort
0x140002db5  mov     ebx, eax
0x140002db7  mov     rcx, rsi; this
0x140002dba  bts     ebx, 1Ch
0x140002dbe  mov     r9d, eax
0x140002dc1  mov     edx, ebx; int
0x140002dc3  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x140002dc8  test    r9d, r9d
0x140002dcb  jns     short loc_140002DF9
0x140002dcd  mov     r8d, 9; unsigned int
0x140002dd3  mov     [rsp+68h+var_40], 0; void *
0x140002ddc  mov     r9d, ebx; int
0x140002ddf  mov     [rsp+68h+var_48], 19Ch; unsigned int
0x140002de7  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x140002dee  lea     ecx, [r8-5]; unsigned int
0x140002df2  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140002df7  jmp     short loc_140002DFB
0x140002df9  xor     ebx, ebx
0x140002dfb  call    cs:__imp_GetProcessHeap
0x140002e01  mov     r8, rdi; lpMem
0x140002e04  xor     edx, edx; dwFlags
0x140002e06  mov     rcx, rax; hHeap
0x140002e09  call    cs:__imp_HeapFree
0x140002e0f  mov     eax, ebx
0x140002e11  add     rsp, 40h
0x140002e15  pop     r15
0x140002e17  pop     rdi
0x140002e18  pop     rsi
0x140002e19  pop     rbp
0x140002e1a  pop     rbx
0x140002e1b  retn
```
