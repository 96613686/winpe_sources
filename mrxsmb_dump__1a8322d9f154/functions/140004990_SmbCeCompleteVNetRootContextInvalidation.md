# SmbCeCompleteVNetRootContextInvalidation

- ea: `0x140004990`
- end: `0x140004b7d`
- name: `SmbCeCompleteVNetRootContextInvalidation`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400189c0`

## callees

- `0x140004990`
- `0x140005540`
- `0x140005740`
- `0x140005b20`
- `0x140005f10`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140004ac5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140004ac5`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400049b9`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400049b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400049c9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400049c9`
- `rdbss!RxDiagnosticTrace` at `0x140004aa4`
- `rdbss!RxDiagnosticTrace` at `0x140004aa4`

## pseudocode

```c
void __fastcall SmbCeCompleteVNetRootContextInvalidation(unsigned __int16 *a1)
{
  __int64 v1; // rsi
  KIRQL v3; // r15
  __int64 v4; // rcx
  char *v5; // rdi
  int v6; // r14d
  int v7; // r8d
  __int32 v8; // edi
  int v9; // edx
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  int v13; // ecx

  v1 = *((_QWORD *)a1 + 3);
  SmbCeDecrementTotalVNetRootContextsOnSession(*((_QWORD *)a1 + 52));
  v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920));
  *(_DWORD *)(v1 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v4 = a1[1];
  if ( (_WORD)v4 )
    v5 = (char *)a1 + v4;
  else
    v5 = 0;
  v6 = 4;
  switch ( *a1 )
  {
    case 0xE200u:
      v6 = 0;
      break;
    case 0xE202u:
      v6 = 1;
      break;
    case 0xE204u:
      v6 = 2;
      break;
  }
  *((_QWORD *)v5 + 26) = 3221225673LL;
  *((_DWORD *)v5 + 50) = -1431655766;
  SmbCeUpperDisconnectAllBindingObjectsLite(a1, 3221225673LL);
  SmbCeResumeSuspendedExchangesLite((_DWORD)v5 + 248, 4, v6, *((_DWORD *)v5 + 50), 3221225673LL, 0);
  v8 = _InterlockedExchange((volatile __int32 *)a1 + 3, 9);
  v9 = *((_DWORD *)a1 + 3);
  if ( v8 != v9 )
  {
    if ( *a1 == 57858 )
    {
      if ( (byte_1400712A1 & 4) != 0 )
      {
        v10 = *((_QWORD *)a1 + 48);
        v11 = *(unsigned __int16 *)(v10 + 80);
        LOWORD(v11) = (unsigned __int16)v11 >> 1;
        McTemplateK0phhqhzr4_EtwWriteTransfer(
          v11,
          (unsigned int)SessionStateTransition,
          v7,
          (_DWORD)a1,
          v8,
          v9,
          201,
          v11,
          *(_QWORD *)(v10 + 88));
      }
    }
    else if ( *a1 == 57860 && (byte_1400712A1 & 4) != 0 )
    {
      v12 = *((_QWORD *)a1 + 53);
      v13 = *(unsigned __int16 *)(v12 + 96);
      LOWORD(v13) = (unsigned __int16)v13 >> 1;
      McTemplateK0phhqhzr4_EtwWriteTransfer(
        v13,
        (unsigned int)VNetRootStateTransition,
        v7,
        (_DWORD)a1,
        v8,
        v9,
        201,
        v13,
        *(_QWORD *)(v12 + 104));
    }
  }
  RxDiagnosticTrace(*((_QWORD *)a1 + 2), 1, "Transition %d --> %d", v8, *((_DWORD *)a1 + 3));
  *(_DWORD *)(v1 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v1 + 1920), v3);
}

```

## disassembly

```asm
0x140004990  push    rbx
0x140004992  push    rbp
0x140004993  push    rsi
0x140004994  push    rdi
0x140004995  push    r12
0x140004997  push    r14
0x140004999  push    r15
0x14000499b  sub     rsp, 50h
0x14000499f  mov     rsi, [rcx+18h]
0x1400049a3  mov     rbx, rcx
0x1400049a6  mov     rcx, [rcx+1A0h]
0x1400049ad  call    SmbCeDecrementTotalVNetRootContextsOnSession
0x1400049b2  lea     rcx, [rsi+780h]; SpinLock
0x1400049b9  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400049c0  nop     dword ptr [rax+rax+00h]
0x1400049c5  movzx   r15d, al
0x1400049c9  call    cs:__imp_PsGetCurrentThreadId
0x1400049d0  nop     dword ptr [rax+rax+00h]
0x1400049d5  mov     [rsi+930h], eax
0x1400049db  mov     r12d, 0C00000C9h
0x1400049e1  movzx   ecx, word ptr [rbx+2]
0x1400049e5  test    cx, cx
0x1400049e8  jz      loc_140004B19
0x1400049ee  lea     rdi, [rbx+rcx]
0x1400049f2  movzx   ecx, word ptr [rbx]
0x1400049f5  mov     r14d, 4
0x1400049fb  sub     ecx, 0E200h
0x140004a01  jz      loc_140004B75
0x140004a07  sub     ecx, 2
0x140004a0a  jz      loc_140004B6A
0x140004a10  cmp     ecx, 2
0x140004a13  jz      loc_140004B5F
0x140004a19  mov     rdx, r12
0x140004a1c  mov     [rdi+0D0h], r12
0x140004a23  mov     rcx, rbx
0x140004a26  mov     dword ptr [rdi+0C8h], 0AAAAAAAAh
0x140004a30  call    SmbCeUpperDisconnectAllBindingObjectsLite
0x140004a35  mov     r9d, [rdi+0C8h]
0x140004a3c  lea     rcx, [rdi+0F8h]
0x140004a43  mov     r8d, r14d
0x140004a46  mov     [rsp+88h+var_60], 0
0x140004a4f  mov     edx, 4
0x140004a54  mov     [rsp+88h+var_68], r12
0x140004a59  call    SmbCeResumeSuspendedExchangesLite
0x140004a5e  mov     edi, 9
0x140004a63  xchg    edi, [rbx+0Ch]
0x140004a66  mov     edx, [rbx+0Ch]
0x140004a69  cmp     edi, edx
0x140004a6b  jz      short loc_140004A8A
0x140004a6d  movzx   ecx, word ptr [rbx]
0x140004a70  sub     ecx, 0E202h
0x140004a76  jz      short loc_140004AE1
0x140004a78  cmp     ecx, 2
0x140004a7b  jnz     short loc_140004A8A
0x140004a7d  test    cs:byte_1400712A1, 4
0x140004a84  jnz     loc_140004B20
0x140004a8a  mov     eax, [rbx+0Ch]
0x140004a8d  lea     r8, aTransitionDD; "Transition %d --> %d"
0x140004a94  mov     rcx, [rbx+10h]
0x140004a98  mov     r9d, edi
0x140004a9b  mov     edx, 1
0x140004aa0  mov     dword ptr [rsp+88h+var_68], eax
0x140004aa4  call    cs:__imp_RxDiagnosticTrace
0x140004aab  nop     dword ptr [rax+rax+00h]
0x140004ab0  movzx   edx, r15b; OldIrql
0x140004ab4  mov     dword ptr [rsi+930h], 0FFFFFFFFh
0x140004abe  lea     rcx, [rsi+780h]; SpinLock
0x140004ac5  call    cs:__imp_ExReleaseSpinLockExclusive
0x140004acc  nop     dword ptr [rax+rax+00h]
0x140004ad1  add     rsp, 50h
0x140004ad5  pop     r15
0x140004ad7  pop     r14
0x140004ad9  pop     r12
0x140004adb  pop     rdi
0x140004adc  pop     rsi
0x140004add  pop     rbp
0x140004ade  pop     rbx
0x140004adf  retn
0x140004ae1  test    cs:byte_1400712A1, 4
0x140004ae8  jz      short loc_140004A8A
0x140004aea  mov     rax, [rbx+180h]
0x140004af1  movzx   ecx, word ptr [rax+50h]
0x140004af5  mov     rax, [rax+58h]
0x140004af9  mov     [rsp+88h+var_48], rax
0x140004afe  shr     cx, 1
0x140004b01  mov     [rsp+88h+var_50], cx
0x140004b06  mov     [rsp+88h+var_58], r12d
0x140004b0b  mov     word ptr [rsp+88h+var_60], dx
0x140004b10  lea     rdx, SessionStateTransition
0x140004b17  jmp     short loc_140004B4D
0x140004b19  xor     edi, edi
0x140004b1b  jmp     loc_1400049F2
0x140004b20  mov     rax, [rbx+1A8h]
0x140004b27  movzx   ecx, word ptr [rax+60h]
0x140004b2b  mov     rax, [rax+68h]
0x140004b2f  mov     [rsp+88h+var_48], rax
0x140004b34  shr     cx, 1
0x140004b37  mov     [rsp+88h+var_50], cx
0x140004b3c  mov     [rsp+88h+var_58], r12d
0x140004b41  mov     word ptr [rsp+88h+var_60], dx
0x140004b46  lea     rdx, VNetRootStateTransition
0x140004b4d  mov     r9, rbx
0x140004b50  mov     word ptr [rsp+88h+var_68], di
0x140004b55  call    McTemplateK0phhqhzr4_EtwWriteTransfer
0x140004b5a  jmp     loc_140004A8A
0x140004b5f  mov     r14d, 2
0x140004b65  jmp     loc_140004A19
0x140004b6a  mov     r14d, 1
0x140004b70  jmp     loc_140004A19
0x140004b75  xor     r14d, r14d
0x140004b78  jmp     loc_140004A19
```
