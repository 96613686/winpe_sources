# SmbCeNegotiate

- ea: `0x14003e6b4`
- end: `0x14003e8cb`
- name: `SmbCeNegotiate`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14000a000`

## callees

- `0x140001cd0`
- `0x1400054b0`
- `0x1400098d0`
- `0x14000a600`
- `0x14000b140`
- `0x14003df64`
- `0x14003e06c`
- `0x14003e364`
- `0x14003e6b4`
- `0x14003f6fc`
- `0x14004bc40`
- `0x14004dd50`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14003e8a8`
- `ntoskrnl!DbgPrint` at `0x14003e8a8`
- `ntoskrnl!KeInitializeEvent` at `0x14003e793`
- `ntoskrnl!KeInitializeEvent` at `0x14003e793`
- `ntoskrnl!ExAllocatePool2` at `0x14003e75f`
- `ntoskrnl!ExAllocatePool2` at `0x14003e75f`

## string_xrefs

- `0x14003e8a1`: `MRXSMB: Cannot talk to %wZ which doesn't support Security Signature.\n`

## pseudocode

```c
__int64 __fastcall SmbCeNegotiate(__int64 a1, __int64 a2, char a3)
{
  unsigned __int8 *Exchange; // rax
  signed __int64 v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // r8
  __int64 Pool2; // rax
  unsigned int v11; // r14d
  signed __int64 v12; // rdi
  int v13; // eax
  int v14; // edi
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+38h] [rbp-40h] BYREF
  struct _KEVENT Event[2]; // [rsp+48h] [rbp-30h] BYREF
  int v19; // [rsp+C8h] [rbp+50h] BYREF

  v19 = 0;
  v16 = 0;
  Exchange = SmbMmAllocateExchange(4);
  v7 = (signed __int64)Exchange;
  if ( !Exchange )
    return (unsigned int)-1073741670;
  v8 = SmbCeInitializeAdminExchange((__int64)Exchange, a1, 0, 0, 114);
  if ( v8 )
  {
    SmbMmFreeExchange((_BYTE *)v7);
  }
  else
  {
    LOBYTE(v9) = a3;
    v8 = BuildNegotiateSmb(&v16, &v19, v9);
    if ( !v8 )
    {
      *(_QWORD *)(v7 + 368) = v16;
      *(_DWORD *)(v7 + 360) = v19;
      *(_QWORD *)(v7 + 392) = a2;
      *(_DWORD *)(v7 + 400) = 17039360;
      Pool2 = ExAllocatePool2(66, 260, 1682009427);
      *(_QWORD *)(v7 + 408) = Pool2;
      if ( Pool2 )
      {
        v17 = 0;
        memset(Event, 0, 32);
        KeInitializeEvent(Event, NotificationEvent, 0);
        *(_QWORD *)&v17 = 0;
        v11 = v8 + 1;
        *(_QWORD *)(v7 + 384) = &v17;
        *((_QWORD *)&v17 + 1) = 0;
        *(_DWORD *)(v7 + 72) = 4099;
        SmbCeIncrementPendingOperations(v7, v8 + 1);
        SmbCeIncrementPendingOperations(v7, v8 + 1);
        v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 392), v7, 0);
        if ( v12 )
          SmbCeDecrementPendingOperationsAndFinalize((PVOID)v7);
        if ( *(_DWORD *)(a1 + 12) != 3 || v12 )
        {
          _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 392), 0, v7);
          SmbCeDiscardAdminExchange((PVOID)v7);
          v8 = -1073741300;
        }
        else
        {
          v13 = SmbCeInitiateExchange(v7);
          v14 = v13;
          if ( *(_DWORD *)(v7 + 40) || v13 != 259 && v13 )
          {
            if ( v7 == _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 392), 0, v7) )
              SmbCeDecrementPendingOperations(v7, v11);
            if ( *(_DWORD *)(v7 + 40) )
              v14 = *(_DWORD *)(v7 + 40);
            else
              *(_DWORD *)(v7 + 40) = v14;
            *(_DWORD *)(v7 + 48) = v14;
          }
          SmbCeDecrementPendingOperationsAndFinalize((PVOID)v7);
          SmbCeSuspendEx(&v17, 0, 0, 0);
          v8 = SmbCeCompleteAdminExchange((PVOID)v7);
        }
        goto LABEL_21;
      }
      return (unsigned int)-1073741670;
    }
  }
LABEL_21:
  if ( v8 == -1073741240 )
    DbgPrint("MRXSMB: Cannot talk to %wZ which doesn't support Security Signature.\n", a1 + 80);
  return v8;
}

```

## disassembly

```asm
0x14003e6b4  push    rbp
0x14003e6b6  push    rbx
0x14003e6b7  push    rsi
0x14003e6b8  push    rdi
0x14003e6b9  push    r14
0x14003e6bb  push    r15
0x14003e6bd  mov     rbp, rsp
0x14003e6c0  sub     rsp, 78h
0x14003e6c4  mov     rsi, rcx
0x14003e6c7  mov     [rbp+arg_18], 0
0x14003e6ce  mov     ecx, 4
0x14003e6d3  mov     [rbp+var_48], 0
0x14003e6db  mov     r14b, r8b
0x14003e6de  mov     r15, rdx
0x14003e6e1  call    SmbMmAllocateExchange
0x14003e6e6  mov     rbx, rax
0x14003e6e9  test    rax, rax
0x14003e6ec  jz      loc_14003E8B6
0x14003e6f2  xor     r9d, r9d
0x14003e6f5  mov     [rsp+78h+var_58], 72h ; 'r'
0x14003e6fa  xor     r8d, r8d
0x14003e6fd  mov     rdx, rsi
0x14003e700  mov     rcx, rax
0x14003e703  call    SmbCeInitializeAdminExchange
0x14003e708  mov     edi, eax
0x14003e70a  test    eax, eax
0x14003e70c  jnz     loc_14003E88D
0x14003e712  mov     r8b, r14b
0x14003e715  lea     rdx, [rbp+arg_18]
0x14003e719  lea     rcx, [rbp+var_48]
0x14003e71d  call    BuildNegotiateSmb
0x14003e722  mov     edi, eax
0x14003e724  test    eax, eax
0x14003e726  jnz     loc_14003E895
0x14003e72c  mov     rax, [rbp+var_48]
0x14003e730  lea     ecx, [rdi+42h]
0x14003e733  mov     [rbx+170h], rax
0x14003e73a  mov     edx, 104h
0x14003e73f  mov     eax, [rbp+arg_18]
0x14003e742  mov     r8d, 64416D53h
0x14003e748  mov     [rbx+168h], eax
0x14003e74e  mov     [rbx+188h], r15
0x14003e755  mov     dword ptr [rbx+190h], 1040000h
0x14003e75f  call    cs:__imp_ExAllocatePool2
0x14003e766  nop     dword ptr [rax+rax+00h]
0x14003e76b  mov     [rbx+198h], rax
0x14003e772  test    rax, rax
0x14003e775  jz      loc_14003E8B6
0x14003e77b  xorps   xmm0, xmm0
0x14003e77e  lea     rcx, [rbp+Event]; Event
0x14003e782  xor     r8d, r8d; State
0x14003e785  xor     edx, edx; Type
0x14003e787  movups  [rbp+var_40], xmm0
0x14003e78b  movups  xmmword ptr [rbp+Event.Header], xmm0
0x14003e78f  movups  xmmword ptr [rbp+Event.Header.WaitListHead.Blink], xmm0
0x14003e793  call    cs:__imp_KeInitializeEvent
0x14003e79a  nop     dword ptr [rax+rax+00h]
0x14003e79f  lea     rax, [rbp+var_40]
0x14003e7a3  mov     qword ptr [rbp+var_40], 0
0x14003e7ab  lea     r14d, [rdi+1]
0x14003e7af  mov     [rbx+180h], rax
0x14003e7b6  mov     edx, r14d
0x14003e7b9  mov     qword ptr [rbp+var_40+8], 0
0x14003e7c1  mov     rcx, rbx
0x14003e7c4  mov     dword ptr [rbx+48h], 1003h
0x14003e7cb  call    SmbCeIncrementPendingOperations
0x14003e7d0  mov     edx, r14d
0x14003e7d3  mov     rcx, rbx
0x14003e7d6  call    SmbCeIncrementPendingOperations
0x14003e7db  xor     eax, eax
0x14003e7dd  lock cmpxchg [rsi+188h], rbx
0x14003e7e6  mov     rdi, rax
0x14003e7e9  jz      short loc_14003E7F6
0x14003e7eb  mov     edx, r14d
0x14003e7ee  mov     rcx, rbx; pContext
0x14003e7f1  call    SmbCeDecrementPendingOperationsAndFinalize
0x14003e7f6  cmp     dword ptr [rsi+0Ch], 3
0x14003e7fa  jnz     short loc_14003E870
0x14003e7fc  test    rdi, rdi
0x14003e7ff  jnz     short loc_14003E870
0x14003e801  mov     rcx, rbx
0x14003e804  call    SmbCeInitiateExchange
0x14003e809  cmp     dword ptr [rbx+28h], 0
0x14003e80d  mov     edi, eax
0x14003e80f  jnz     short loc_14003E81C
0x14003e811  cmp     eax, 103h
0x14003e816  jz      short loc_14003E848
0x14003e818  test    eax, eax
0x14003e81a  jz      short loc_14003E848
0x14003e81c  xor     ecx, ecx
0x14003e81e  mov     rax, rbx
0x14003e821  lock cmpxchg [rsi+188h], rcx
0x14003e82a  jnz     short loc_14003E837
0x14003e82c  mov     edx, r14d
0x14003e82f  mov     rcx, rbx
0x14003e832  call    SmbCeDecrementPendingOperations
0x14003e837  mov     eax, [rbx+28h]
0x14003e83a  test    eax, eax
0x14003e83c  jnz     short loc_14003E843
0x14003e83e  mov     [rbx+28h], edi
0x14003e841  jmp     short loc_14003E845
0x14003e843  mov     edi, eax
0x14003e845  mov     [rbx+30h], edi
0x14003e848  mov     edx, r14d
0x14003e84b  mov     rcx, rbx; pContext
0x14003e84e  call    SmbCeDecrementPendingOperationsAndFinalize
0x14003e853  xor     r9d, r9d
0x14003e856  lea     rcx, [rbp+var_40]
0x14003e85a  xor     r8d, r8d
0x14003e85d  xor     edx, edx
0x14003e85f  call    SmbCeSuspendEx
0x14003e864  mov     rcx, rbx; Entry
0x14003e867  call    SmbCeCompleteAdminExchange
0x14003e86c  mov     edi, eax
0x14003e86e  jmp     short loc_14003E895
0x14003e870  xor     ecx, ecx
0x14003e872  mov     rax, rbx
0x14003e875  lock cmpxchg [rsi+188h], rcx
0x14003e87e  mov     rcx, rbx; Entry
0x14003e881  call    SmbCeDiscardAdminExchange
0x14003e886  mov     edi, 0C000020Ch
0x14003e88b  jmp     short loc_14003E895
0x14003e88d  mov     rcx, rbx; Entry
0x14003e890  call    SmbMmFreeExchange
0x14003e895  cmp     edi, 0C0000248h
0x14003e89b  jnz     short loc_14003E8BB
0x14003e89d  lea     rdx, [rsi+50h]
0x14003e8a1  lea     rcx, aMrxsmbCannotTa; "MRXSMB: Cannot talk to %wZ which doesn'"...
0x14003e8a8  call    cs:__imp_DbgPrint
0x14003e8af  nop     dword ptr [rax+rax+00h]
0x14003e8b4  jmp     short loc_14003E8BB
0x14003e8b6  mov     edi, 0C000009Ah
0x14003e8bb  mov     eax, edi
0x14003e8bd  add     rsp, 78h
0x14003e8c1  pop     r15
0x14003e8c3  pop     r14
0x14003e8c5  pop     rdi
0x14003e8c6  pop     rsi
0x14003e8c7  pop     rbx
0x14003e8c8  pop     rbp
0x14003e8c9  retn
```
