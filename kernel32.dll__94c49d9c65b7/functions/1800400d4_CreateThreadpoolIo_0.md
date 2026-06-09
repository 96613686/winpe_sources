# CreateThreadpoolIo_0

- ea: `0x1800400d4`
- end: `0x1800402e8`
- name: `CreateThreadpoolIo_0`
- size: `532`
- prototype: `PTP_IO __stdcall(HANDLE fl, PTP_WIN32_IO_CALLBACK pfnio, PVOID pv, PTP_CALLBACK_ENVIRON pcbe)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800585a0`

## callees

- `0x1800400d4`
- `0x18007a7dd`

## import_xrefs

- `ntdll!TpAllocIoCompletion` at `0x1800401f4`
- `ntdll!TpAllocIoCompletion` at `0x1800401f4`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180040155`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180040155`
- `ntdll!RtlFreeHeap` at `0x1800402d8`
- `ntdll!RtlFreeHeap` at `0x18007b24e`
- `ntdll!RtlFreeHeap` at `0x1800402d8`
- `ntdll!RtlFreeHeap` at `0x18007b24e`
- `ntdll!RtlAllocateHeap` at `0x18004013d`
- `ntdll!RtlAllocateHeap` at `0x18004013d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800402b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800402b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800402a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800402a4`

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
0x1800400d4  mov     [rsp+arg_0], rbx
0x1800400d9  mov     [rsp+arg_10], rsi
0x1800400de  push    rdi
0x1800400df  push    r14
0x1800400e1  push    r15
0x1800400e3  sub     rsp, 90h
0x1800400ea  mov     rdi, r9
0x1800400ed  mov     r14, r8
0x1800400f0  mov     rsi, rdx
0x1800400f3  mov     r15, rcx
0x1800400f6  xor     eax, eax
0x1800400f8  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x1800400fc  xor     edx, edx; Val
0x1800400fe  lea     r8d, [rax+44h]; Size
0x180040102  lea     rcx, [rsp+0A8h+var_68]; void *
0x180040107  call    memset_0
0x18004010c  mov     [rsp+0A8h+var_78], 0
0x180040115  mov     [rsp+0A8h+arg_8], 0
0x180040121  test    rsi, rsi
0x180040124  jz      loc_18004029F
0x18004012a  mov     rcx, gs:60h
0x180040133  xor     edx, edx; Flags
0x180040135  lea     r8d, [rdx+20h]; Size
0x180040139  mov     rcx, [rcx+30h]; HeapHandle
0x18004013d  call    cs:__imp_RtlAllocateHeap
0x180040143  mov     rbx, rax
0x180040146  mov     [rsp+0A8h+var_78], rax
0x18004014b  test    rax, rax
0x18004014e  jnz     short loc_180040160
0x180040150  mov     ecx, 0C0000017h; Status
0x180040155  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18004015b  jmp     loc_180040279
0x180040160  mov     [rax], rsi
0x180040163  test    rdi, rdi
0x180040166  jnz     loc_180040211
0x18004016c  mov     dword ptr [rsp+0A8h+var_68], 3
0x180040174  mov     qword ptr [rsp+0A8h+var_68+8], rdi
0x180040179  mov     qword ptr [rsp+0A8h+var_58], rdi
0x18004017e  mov     qword ptr [rsp+0A8h+var_58+8], rdi
0x180040183  xorps   xmm0, xmm0
0x180040186  movdqa  [rsp+0A8h+var_48], xmm0
0x18004018c  xor     eax, eax
0x18004018e  mov     qword ptr [rsp+0A8h+var_38], rax
0x180040193  mov     dword ptr [rsp+0A8h+var_38+8], eax
0x180040197  mov     dword ptr [rsp+0A8h+var_38+0Ch], 1
0x18004019f  mov     dword ptr [rsp+0A8h+var_28], 48h ; 'H'
0x1800401aa  mov     [rbx+8], rax
0x1800401ae  lea     rax, BasepTpIoFinalizationCallback
0x1800401b5  mov     qword ptr [rsp+0A8h+var_38], rax
0x1800401ba  cmp     qword ptr [rsp+0A8h+var_58], 0
0x1800401c0  jnz     loc_18004024C
0x1800401c6  mov     qword ptr [rbx+10h], 0
0x1800401ce  mov     [rbx], rsi
0x1800401d1  mov     [rbx+18h], r14
0x1800401d5  lea     rax, [rsp+0A8h+var_68]
0x1800401da  mov     [rsp+0A8h+var_88], rax
0x1800401df  mov     r9, rbx
0x1800401e2  lea     r8, BasepTpIoCallback
0x1800401e9  mov     rdx, r15
0x1800401ec  lea     rcx, [rsp+0A8h+arg_8]
0x1800401f4  call    cs:__imp_TpAllocIoCompletion
0x1800401fa  test    eax, eax
0x1800401fc  jns     short loc_180040279
0x1800401fe  mov     [rsp+0A8h+arg_8], 0
0x18004020a  mov     ecx, eax
0x18004020c  jmp     loc_180040155
0x180040211  movups  xmm0, xmmword ptr [rdi]
0x180040214  movaps  [rsp+0A8h+var_68], xmm0
0x180040219  movups  xmm1, xmmword ptr [rdi+10h]
0x18004021d  movaps  [rsp+0A8h+var_58], xmm1
0x180040222  movups  xmm0, xmmword ptr [rdi+20h]
0x180040226  movaps  [rsp+0A8h+var_48], xmm0
0x18004022b  movups  xmm1, xmmword ptr [rdi+30h]
0x18004022f  movaps  [rsp+0A8h+var_38], xmm1
0x180040234  movsd   xmm0, qword ptr [rdi+40h]
0x180040239  movsd   [rsp+0A8h+var_28], xmm0
0x180040242  movq    rax, xmm1
0x180040247  jmp     loc_1800401AA
0x18004024c  mov     rax, qword ptr [rsp+0A8h+var_58+8]
0x180040251  test    rax, rax
0x180040254  jz      loc_1800401C6
0x18004025a  mov     [rbx+10h], rax
0x18004025e  mov     rax, qword ptr [rsp+0A8h+var_58]
0x180040263  mov     qword ptr [rsp+0A8h+var_58], rax
0x180040268  lea     rax, BasepTpIoCleanupCallback
0x18004026f  mov     qword ptr [rsp+0A8h+var_58+8], rax
0x180040274  jmp     loc_1800401CE
0x180040279  mov     rax, [rsp+0A8h+arg_8]
0x180040281  test    rax, rax
0x180040284  jz      short loc_1800402C1
0x180040286  lea     r11, [rsp+0A8h+var_18]
0x18004028e  mov     rbx, [r11+20h]
0x180040292  mov     rsi, [r11+30h]
0x180040296  mov     rsp, r11
0x180040299  pop     r15
0x18004029b  pop     r14
0x18004029d  pop     rdi
0x18004029e  retn
0x18004029f  mov     ecx, 57h ; 'W'; dwErrCode
0x1800402a4  call    cs:__imp_SetLastError
0x1800402aa  xor     r9d, r9d; lpArguments
0x1800402ad  xor     r8d, r8d; nNumberOfArguments
0x1800402b0  xor     edx, edx; dwExceptionFlags
0x1800402b2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800402b7  call    cs:__imp_RaiseException
0x1800402bd  xor     eax, eax
0x1800402bf  jmp     short loc_180040286
0x1800402c1  test    rbx, rbx
0x1800402c4  jz      short loc_180040286
0x1800402c6  mov     rcx, gs:60h
0x1800402cf  mov     r8, rbx; P
0x1800402d2  xor     edx, edx; Flags
0x1800402d4  mov     rcx, [rcx+30h]; HeapHandle
0x1800402d8  call    cs:__imp_RtlFreeHeap
0x1800402de  mov     rax, [rsp+0A8h+arg_8]
0x1800402e6  jmp     short loc_180040286
0x18007b21c  push    rbp
0x18007b21e  sub     rsp, 30h
0x18007b222  mov     rbp, rdx
0x18007b225  movzx   eax, cl
0x18007b228  test    cl, cl
0x18007b22a  jnz     short loc_18007B236
0x18007b22c  cmp     qword ptr [rbp+0B8h], 0
0x18007b234  jnz     short loc_18007B255
0x18007b236  mov     r8, [rbp+30h]; P
0x18007b23a  test    r8, r8
0x18007b23d  jz      short loc_18007B255
0x18007b23f  mov     rcx, gs:60h
0x18007b248  xor     edx, edx; Flags
0x18007b24a  mov     rcx, [rcx+30h]; HeapHandle
0x18007b24e  call    cs:__imp_RtlFreeHeap
0x18007b254  nop
0x18007b255  add     rsp, 30h
0x18007b259  pop     rbp
0x18007b25a  retn
```
