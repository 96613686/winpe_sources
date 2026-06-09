# CreateThreadpoolIo_0

- ea: `0x180043be4`
- end: `0x180043e1d`
- name: `CreateThreadpoolIo_0`
- size: `569`
- prototype: `PTP_IO __stdcall(HANDLE fl, PTP_WIN32_IO_CALLBACK pfnio, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005dbb0`

## callees

- `0x180043be4`
- `0x18008275d`

## import_xrefs

- `ntdll!TpAllocIoCompletion` at `0x180043d10`
- `ntdll!TpAllocIoCompletion` at `0x180043d10`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180043c6b`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180043c6b`
- `ntdll!RtlFreeHeap` at `0x180043e07`
- `ntdll!RtlFreeHeap` at `0x1800832d0`
- `ntdll!RtlFreeHeap` at `0x180043e07`
- `ntdll!RtlFreeHeap` at `0x1800832d0`
- `ntdll!RtlAllocateHeap` at `0x180043c4d`
- `ntdll!RtlAllocateHeap` at `0x180043c4d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043de0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043de0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043dc7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180043dc7`

## pseudocode

```c
PTP_IO __stdcall CreateThreadpoolIo_0(HANDLE fl, PTP_WIN32_IO_CALLBACK pfnio, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)
{
  PTP_WIN32_IO_CALLBACK *Heap; // rax
  PTP_WIN32_IO_CALLBACK *v9; // rbx
  NTSTATUS v10; // ecx
  void (__stdcall *v11)(PTP_CALLBACK_INSTANCE, PVOID, PVOID, ULONG, ULONG_PTR, PTP_IO); // rax
  int v12; // eax
  PTP_IO result; // rax
  __int128 v14; // [rsp+40h] [rbp-68h] BYREF
  __int128 v15; // [rsp+50h] [rbp-58h]
  __int128 v16; // [rsp+60h] [rbp-48h]
  __int128 v17; // [rsp+70h] [rbp-38h]
  __int64 v18; // [rsp+80h] [rbp-28h]
  struct _TP_IO *v19; // [rsp+B8h] [rbp+10h] BYREF

  DWORD1(v14) = 0;
  memset_0(&v14, 0, 0x44u);
  v19 = 0;
  if ( !pfnio )
  {
    SetLastError(0x57u);
    RaiseException(0xC000000D, 0, 0, 0);
    return 0;
  }
  Heap = (PTP_WIN32_IO_CALLBACK *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
  v9 = Heap;
  if ( Heap )
  {
    *Heap = pfnio;
    if ( pcbe )
    {
      v14 = *(_OWORD *)&pcbe->Version;
      v15 = *(_OWORD *)&pcbe->CleanupGroup;
      v16 = *(_OWORD *)&pcbe->RaceDll;
      v17 = *(_OWORD *)&pcbe->FinalizationCallback;
      v18 = *(_QWORD *)&pcbe->Size;
      v11 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PVOID, ULONG, ULONG_PTR, PTP_IO))v17;
    }
    else
    {
      LODWORD(v14) = 3;
      *((_QWORD *)&v14 + 1) = 0;
      v15 = 0u;
      v16 = 0;
      v11 = 0;
      *(_QWORD *)&v17 = 0;
      *((_QWORD *)&v17 + 1) = 0x100000000LL;
      LODWORD(v18) = 72;
    }
    v9[1] = v11;
    *(_QWORD *)&v17 = &BasepTpIoFinalizationCallback;
    if ( (_QWORD)v15 && *((_QWORD *)&v15 + 1) )
    {
      v9[2] = (PTP_WIN32_IO_CALLBACK)*((_QWORD *)&v15 + 1);
      *((_QWORD *)&v15 + 1) = BasepTpIoCleanupCallback;
    }
    else
    {
      v9[2] = 0;
    }
    *v9 = pfnio;
    v9[3] = (PTP_WIN32_IO_CALLBACK)pv;
    v12 = TpAllocIoCompletion(&v19, fl, BasepTpIoCallback, v9, &v14);
    if ( v12 >= 0 )
      goto LABEL_14;
    v19 = 0;
    v10 = v12;
  }
  else
  {
    v10 = -1073741801;
  }
  RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v10);
LABEL_14:
  result = v19;
  if ( !v19 )
  {
    if ( v9 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
      return v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180043be4  mov     [rsp+arg_0], rbx
0x180043be9  mov     [rsp+arg_10], rsi
0x180043bee  push    rdi
0x180043bef  push    r14
0x180043bf1  push    r15
0x180043bf3  sub     rsp, 90h
0x180043bfa  mov     rdi, r9
0x180043bfd  mov     r14, r8
0x180043c00  mov     rsi, rdx
0x180043c03  mov     r15, rcx
0x180043c06  xor     eax, eax
0x180043c08  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x180043c0c  xor     edx, edx; Val
0x180043c0e  lea     r8d, [rax+44h]; Size
0x180043c12  lea     rcx, [rsp+0A8h+var_68]; void *
0x180043c17  call    memset_0
0x180043c1c  mov     [rsp+0A8h+var_78], 0
0x180043c25  mov     [rsp+0A8h+arg_8], 0
0x180043c31  test    rsi, rsi
0x180043c34  jz      loc_180043DC2
0x180043c3a  mov     rcx, gs:60h
0x180043c43  xor     edx, edx; Flags
0x180043c45  lea     r8d, [rdx+20h]; Size
0x180043c49  mov     rcx, [rcx+30h]; HeapHandle
0x180043c4d  call    cs:__imp_RtlAllocateHeap
0x180043c54  nop     dword ptr [rax+rax+00h]
0x180043c59  mov     rbx, rax
0x180043c5c  mov     [rsp+0A8h+var_78], rax
0x180043c61  test    rax, rax
0x180043c64  jnz     short loc_180043C7C
0x180043c66  mov     ecx, 0C0000017h; Status
0x180043c6b  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x180043c72  nop     dword ptr [rax+rax+00h]
0x180043c77  jmp     loc_180043D9B
0x180043c7c  mov     [rax], rsi
0x180043c7f  test    rdi, rdi
0x180043c82  jnz     loc_180043D33
0x180043c88  mov     dword ptr [rsp+0A8h+var_68], 3
0x180043c90  mov     qword ptr [rsp+0A8h+var_68+8], rdi
0x180043c95  mov     qword ptr [rsp+0A8h+var_58], rdi
0x180043c9a  mov     qword ptr [rsp+0A8h+var_58+8], rdi
0x180043c9f  xorps   xmm0, xmm0
0x180043ca2  movdqa  [rsp+0A8h+var_48], xmm0
0x180043ca8  xor     eax, eax
0x180043caa  mov     qword ptr [rsp+0A8h+var_38], rax
0x180043caf  mov     dword ptr [rsp+0A8h+var_38+8], eax
0x180043cb3  mov     dword ptr [rsp+0A8h+var_38+0Ch], 1
0x180043cbb  mov     dword ptr [rsp+0A8h+var_28], 48h ; 'H'
0x180043cc6  mov     [rbx+8], rax
0x180043cca  lea     rax, BasepTpIoFinalizationCallback
0x180043cd1  mov     qword ptr [rsp+0A8h+var_38], rax
0x180043cd6  cmp     qword ptr [rsp+0A8h+var_58], 0
0x180043cdc  jnz     loc_180043D6E
0x180043ce2  mov     qword ptr [rbx+10h], 0
0x180043cea  mov     [rbx], rsi
0x180043ced  mov     [rbx+18h], r14
0x180043cf1  lea     rax, [rsp+0A8h+var_68]
0x180043cf6  mov     [rsp+0A8h+var_88], rax
0x180043cfb  mov     r9, rbx
0x180043cfe  lea     r8, BasepTpIoCallback
0x180043d05  mov     rdx, r15
0x180043d08  lea     rcx, [rsp+0A8h+arg_8]
0x180043d10  call    cs:__imp_TpAllocIoCompletion
0x180043d17  nop     dword ptr [rax+rax+00h]
0x180043d1c  test    eax, eax
0x180043d1e  jns     short loc_180043D9B
0x180043d20  mov     [rsp+0A8h+arg_8], 0
0x180043d2c  mov     ecx, eax
0x180043d2e  jmp     loc_180043C6B
0x180043d33  movups  xmm0, xmmword ptr [rdi]
0x180043d36  movaps  [rsp+0A8h+var_68], xmm0
0x180043d3b  movups  xmm1, xmmword ptr [rdi+10h]
0x180043d3f  movaps  [rsp+0A8h+var_58], xmm1
0x180043d44  movups  xmm0, xmmword ptr [rdi+20h]
0x180043d48  movaps  [rsp+0A8h+var_48], xmm0
0x180043d4d  movups  xmm1, xmmword ptr [rdi+30h]
0x180043d51  movaps  [rsp+0A8h+var_38], xmm1
0x180043d56  movsd   xmm0, qword ptr [rdi+40h]
0x180043d5b  movsd   [rsp+0A8h+var_28], xmm0
0x180043d64  movq    rax, xmm1
0x180043d69  jmp     loc_180043CC6
0x180043d6e  mov     rax, qword ptr [rsp+0A8h+var_58+8]
0x180043d73  test    rax, rax
0x180043d76  jz      loc_180043CE2
0x180043d7c  mov     [rbx+10h], rax
0x180043d80  mov     rax, qword ptr [rsp+0A8h+var_58]
0x180043d85  mov     qword ptr [rsp+0A8h+var_58], rax
0x180043d8a  lea     rax, BasepTpIoCleanupCallback
0x180043d91  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x180043d96  jmp     loc_180043CEA
0x180043d9b  mov     rax, [rsp+0A8h+arg_8]
0x180043da3  test    rax, rax
0x180043da6  jz      short loc_180043DF0
0x180043da8  lea     r11, [rsp+0A8h+var_18]
0x180043db0  mov     rbx, [r11+20h]
0x180043db4  mov     rsi, [r11+30h]
0x180043db8  mov     rsp, r11
0x180043dbb  pop     r15
0x180043dbd  pop     r14
0x180043dbf  pop     rdi
0x180043dc0  retn
0x180043dc2  mov     ecx, 57h ; 'W'; dwErrCode
0x180043dc7  call    cs:__imp_SetLastError
0x180043dce  nop     dword ptr [rax+rax+00h]
0x180043dd3  xor     r9d, r9d; lpArguments
0x180043dd6  xor     r8d, r8d; nNumberOfArguments
0x180043dd9  xor     edx, edx; dwExceptionFlags
0x180043ddb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180043de0  call    cs:__imp_RaiseException
0x180043de7  nop     dword ptr [rax+rax+00h]
0x180043dec  xor     eax, eax
0x180043dee  jmp     short loc_180043DA8
0x180043df0  test    rbx, rbx
0x180043df3  jz      short loc_180043DA8
0x180043df5  mov     rcx, gs:60h
0x180043dfe  mov     r8, rbx; P
0x180043e01  xor     edx, edx; Flags
0x180043e03  mov     rcx, [rcx+30h]; HeapHandle
0x180043e07  call    cs:__imp_RtlFreeHeap
0x180043e0e  nop     dword ptr [rax+rax+00h]
0x180043e13  mov     rax, [rsp+0A8h+arg_8]
0x180043e1b  jmp     short loc_180043DA8
0x18008329e  push    rbp
0x1800832a0  sub     rsp, 30h
0x1800832a4  mov     rbp, rdx
0x1800832a7  movzx   eax, cl
0x1800832aa  test    cl, cl
0x1800832ac  jnz     short loc_1800832B8
0x1800832ae  cmp     qword ptr [rbp+0B8h], 0
0x1800832b6  jnz     short loc_1800832DD
0x1800832b8  mov     r8, [rbp+30h]; P
0x1800832bc  test    r8, r8
0x1800832bf  jz      short loc_1800832DD
0x1800832c1  mov     rcx, gs:60h
0x1800832ca  xor     edx, edx; Flags
0x1800832cc  mov     rcx, [rcx+30h]; HeapHandle
0x1800832d0  call    cs:__imp_RtlFreeHeap
0x1800832d7  nop     dword ptr [rax+rax+00h]
0x1800832dc  nop
0x1800832dd  add     rsp, 30h
0x1800832e1  pop     rbp
0x1800832e2  retn
```
