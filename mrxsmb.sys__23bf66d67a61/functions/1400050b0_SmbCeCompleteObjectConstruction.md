# SmbCeCompleteObjectConstruction

- ea: `0x1400050b0`
- end: `0x140005317`
- name: `SmbCeCompleteObjectConstruction`
- size: `615`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140023a70`
- `0x140024010`
- `0x140024330`
- `0x1400434d0`

## callees

- `0x1400050b0`
- `0x140005540`
- `0x140005740`
- `0x140005cd0`
- `0x140005f10`
- `0x1400093a0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140005202`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140005202`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400050ce`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400050ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050de`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400050de`
- `rdbss!RxDiagnosticTrace` at `0x140005179`
- `rdbss!RxDiagnosticTrace` at `0x140005306`
- `rdbss!RxDiagnosticTrace` at `0x140005179`
- `rdbss!RxDiagnosticTrace` at `0x140005306`

## pseudocode

```c
void __fastcall SmbCeCompleteObjectConstruction(unsigned __int16 *a1, __int64 a2)
{
  __int64 v2; // rsi
  KIRQL v5; // r14
  int v6; // r8d
  __int64 v7; // rcx
  char *v8; // rbp
  int v9; // r15d
  __int32 v10; // esi
  int v11; // edx
  int v12; // eax
  unsigned int v13; // eax
  unsigned __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  unsigned __int32 v20; // esi

  v2 = *((_QWORD *)a1 + 3);
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v2 + 1920));
  *(_DWORD *)(v2 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v7 = a1[1];
  if ( (_WORD)v7 )
    v8 = (char *)a1 + v7;
  else
    v8 = 0;
  v9 = 4;
  switch ( *a1 )
  {
    case 0xE200u:
      v9 = 0;
      break;
    case 0xE202u:
      v9 = 1;
      break;
    case 0xE204u:
      v9 = 2;
      break;
  }
  *((_QWORD *)v8 + 26) = a2;
  v10 = _InterlockedExchange((volatile __int32 *)a1 + 3, (unsigned int)a2 >> 31);
  v11 = *((_DWORD *)a1 + 3);
  if ( v10 != v11 )
  {
    if ( *a1 == 57858 )
    {
      if ( (byte_1400712C1 & 4) != 0 )
      {
        v16 = *((_QWORD *)a1 + 48);
        v17 = *(unsigned __int16 *)(v16 + 80);
        LOWORD(v17) = (unsigned __int16)v17 >> 1;
        McTemplateK0phhqhzr4_EtwWriteTransfer(
          v17,
          (unsigned int)SessionStateTransition,
          v6,
          (_DWORD)a1,
          v10,
          v11,
          a2,
          v17,
          *(_QWORD *)(v16 + 88));
      }
    }
    else if ( *a1 == 57860 && (byte_1400712C1 & 4) != 0 )
    {
      v18 = *((_QWORD *)a1 + 53);
      v19 = *(unsigned __int16 *)(v18 + 96);
      LOWORD(v19) = (unsigned __int16)v19 >> 1;
      McTemplateK0phhqhzr4_EtwWriteTransfer(
        v19,
        (unsigned int)VNetRootStateTransition,
        v6,
        (_DWORD)a1,
        v10,
        v11,
        a2,
        v19,
        *(_QWORD *)(v18 + 104));
    }
  }
  RxDiagnosticTrace(*((_QWORD *)a1 + 2), 1, "Transition %d --> %d", v10, *((_DWORD *)a1 + 3));
  if ( v10 == 3 )
  {
    v12 = *((_DWORD *)v8 + 50);
    if ( (int)a2 >= 0 )
      v13 = ((v12 + 1) & 0xFFFFFFFE) + 1;
    else
      v13 = (v12 & 0xFFFFFFFE) + 2;
    *((_DWORD *)v8 + 50) = v13;
  }
  if ( (unsigned __int8)SmbCeResumeSuspendedExchangesLite((int)v8 + 248, 4, v9, *((_DWORD *)v8 + 50), a2, (__int64)a1) )
  {
    v20 = _InterlockedExchange((volatile __int32 *)a1 + 3, 6);
    SmbEtwLogObjectStateTransition(a1, v20, *((unsigned int *)a1 + 3), (unsigned int)a2);
    RxDiagnosticTrace(*((_QWORD *)a1 + 2), 1, "Transition %d --> %d", v20, *((_DWORD *)a1 + 3));
  }
  if ( (int)a2 < 0 )
    SmbCeUpperDisconnectAllBindingObjectsLite(a1, a2);
  v14 = _InterlockedExchange64((volatile __int64 *)v8 + 33, 0);
  v15 = *((_QWORD *)a1 + 3);
  *(_DWORD *)(v15 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v15 + 1920), v5);
  if ( v14 )
    SmbCeDereferenceExchange(v14);
}

```

## disassembly

```asm
0x1400050b0  push    rbx
0x1400050b2  push    rbp
0x1400050b3  push    rsi
0x1400050b4  push    rdi
0x1400050b5  push    r14
0x1400050b7  push    r15
0x1400050b9  sub     rsp, 58h
0x1400050bd  mov     rsi, [rcx+18h]
0x1400050c1  mov     rdi, rcx
0x1400050c4  mov     rbx, rdx
0x1400050c7  lea     rcx, [rsi+780h]; SpinLock
0x1400050ce  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400050d5  nop     dword ptr [rax+rax+00h]
0x1400050da  movzx   r14d, al
0x1400050de  call    cs:__imp_PsGetCurrentThreadId
0x1400050e5  nop     dword ptr [rax+rax+00h]
0x1400050ea  mov     [rsi+930h], eax
0x1400050f0  movzx   ecx, word ptr [rdi+2]
0x1400050f4  test    cx, cx
0x1400050f7  jz      loc_140005270
0x1400050fd  lea     rbp, [rdi+rcx]
0x140005101  movzx   ecx, word ptr [rdi]
0x140005104  mov     r15d, 4
0x14000510a  sub     ecx, 0E200h
0x140005110  jz      loc_1400052CB
0x140005116  sub     ecx, 2
0x140005119  jz      loc_1400052C0
0x14000511f  cmp     ecx, 2
0x140005122  jz      loc_1400052B5
0x140005128  mov     [rbp+0D0h], rbx
0x14000512f  mov     esi, ebx
0x140005131  shr     esi, 1Fh
0x140005134  xchg    esi, [rdi+0Ch]
0x140005137  mov     edx, [rdi+0Ch]
0x14000513a  cmp     esi, edx
0x14000513c  jz      short loc_14000515F
0x14000513e  movzx   ecx, word ptr [rdi]
0x140005141  sub     ecx, 0E202h
0x140005147  jz      loc_140005229
0x14000514d  cmp     ecx, 2
0x140005150  jnz     short loc_14000515F
0x140005152  test    cs:byte_1400712C1, 4
0x140005159  jnz     loc_140005277
0x14000515f  mov     eax, [rdi+0Ch]
0x140005162  lea     r8, aTransitionDD; "Transition %d --> %d"
0x140005169  mov     rcx, [rdi+10h]
0x14000516d  mov     r9d, esi
0x140005170  mov     edx, 1
0x140005175  mov     dword ptr [rsp+88h+var_68], eax
0x140005179  call    cs:__imp_RxDiagnosticTrace
0x140005180  nop     dword ptr [rax+rax+00h]
0x140005185  cmp     esi, 3
0x140005188  jnz     short loc_1400051A4
0x14000518a  mov     eax, [rbp+0C8h]
0x140005190  test    ebx, ebx
0x140005192  jns     loc_140005264
0x140005198  and     eax, 0FFFFFFFEh
0x14000519b  add     eax, 2
0x14000519e  mov     [rbp+0C8h], eax
0x1400051a4  mov     r9d, [rbp+0C8h]
0x1400051ab  lea     rcx, [rbp+0F8h]
0x1400051b2  mov     [rsp+88h+var_60], rdi
0x1400051b7  mov     r8d, r15d
0x1400051ba  mov     edx, 4
0x1400051bf  mov     [rsp+88h+var_68], rbx
0x1400051c4  call    SmbCeResumeSuspendedExchangesLite
0x1400051c9  test    al, al
0x1400051cb  jnz     loc_1400052D3
0x1400051d1  test    ebx, ebx
0x1400051d3  jns     short loc_1400051E0
0x1400051d5  mov     rdx, rbx
0x1400051d8  mov     rcx, rdi
0x1400051db  call    SmbCeUpperDisconnectAllBindingObjectsLite
0x1400051e0  xor     ebx, ebx
0x1400051e2  movzx   edx, r14b; OldIrql
0x1400051e6  xchg    rbx, [rbp+108h]
0x1400051ed  mov     rcx, [rdi+18h]
0x1400051f1  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x1400051fb  add     rcx, 780h; SpinLock
0x140005202  call    cs:__imp_ExReleaseSpinLockExclusive
0x140005209  nop     dword ptr [rax+rax+00h]
0x14000520e  test    rbx, rbx
0x140005211  jz      short loc_14000521B
0x140005213  mov     rcx, rbx; pContext
0x140005216  call    SmbCeDereferenceExchange
0x14000521b  add     rsp, 58h
0x14000521f  pop     r15
0x140005221  pop     r14
0x140005223  pop     rdi
0x140005224  pop     rsi
0x140005225  pop     rbp
0x140005226  pop     rbx
0x140005227  retn
0x140005229  test    cs:byte_1400712C1, 4
0x140005230  jz      loc_14000515F
0x140005236  mov     rax, [rdi+180h]
0x14000523d  movzx   ecx, word ptr [rax+50h]
0x140005241  mov     rax, [rax+58h]
0x140005245  mov     [rsp+88h+var_48], rax
0x14000524a  shr     cx, 1
0x14000524d  mov     [rsp+88h+var_50], cx
0x140005252  mov     [rsp+88h+var_58], ebx
0x140005256  mov     word ptr [rsp+88h+var_60], dx
0x14000525b  lea     rdx, SessionStateTransition
0x140005262  jmp     short loc_1400052A3
0x140005264  inc     eax
0x140005266  and     eax, 0FFFFFFFEh
0x140005269  inc     eax
0x14000526b  jmp     loc_14000519E
0x140005270  xor     ebp, ebp
0x140005272  jmp     loc_140005101
0x140005277  mov     rax, [rdi+1A8h]
0x14000527e  movzx   ecx, word ptr [rax+60h]
0x140005282  mov     rax, [rax+68h]
0x140005286  mov     [rsp+88h+var_48], rax
0x14000528b  shr     cx, 1
0x14000528e  mov     [rsp+88h+var_50], cx
0x140005293  mov     [rsp+88h+var_58], ebx
0x140005297  mov     word ptr [rsp+88h+var_60], dx
0x14000529c  lea     rdx, VNetRootStateTransition
0x1400052a3  mov     r9, rdi
0x1400052a6  mov     word ptr [rsp+88h+var_68], si
0x1400052ab  call    McTemplateK0phhqhzr4_EtwWriteTransfer
0x1400052b0  jmp     loc_14000515F
0x1400052b5  mov     r15d, 2
0x1400052bb  jmp     loc_140005128
0x1400052c0  mov     r15d, 1
0x1400052c6  jmp     loc_140005128
0x1400052cb  xor     r15d, r15d
0x1400052ce  jmp     loc_140005128
0x1400052d3  mov     esi, 6
0x1400052d8  mov     r9d, ebx
0x1400052db  xchg    esi, [rdi+0Ch]
0x1400052de  mov     r8d, [rdi+0Ch]
0x1400052e2  mov     edx, esi
0x1400052e4  mov     rcx, rdi
0x1400052e7  call    SmbEtwLogObjectStateTransition
0x1400052ec  mov     eax, [rdi+0Ch]
0x1400052ef  lea     r8, aTransitionDD; "Transition %d --> %d"
0x1400052f6  mov     rcx, [rdi+10h]
0x1400052fa  mov     r9d, esi
0x1400052fd  mov     edx, 1
0x140005302  mov     dword ptr [rsp+88h+var_68], eax
0x140005306  call    cs:__imp_RxDiagnosticTrace
0x14000530d  nop     dword ptr [rax+rax+00h]
0x140005312  jmp     loc_1400051D1
```
