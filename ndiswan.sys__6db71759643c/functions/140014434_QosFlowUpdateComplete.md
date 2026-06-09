# QosFlowUpdateComplete

- ea: `0x140014434`
- end: `0x140014560`
- name: `QosFlowUpdateComplete`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013570`

## callees

- `0x140009368`
- `0x140014434`
- `0x14001554c`
- `0x140016004`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400144ea`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400144ea`

## pseudocode

```c
__int64 __fastcall QosFlowUpdateComplete(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  int v11; // ecx
  __int64 v12; // r8
  char v13; // r14
  bool v14; // zf
  ULONG CurrentProcessorNumber; // eax
  __int64 v16; // r8
  __int64 v18; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+98h] [rbp+20h] BYREF

  v19 = 0;
  if ( a4 >= 0 )
  {
    v11 = *(_DWORD *)(a1 + 416);
    v12 = *(unsigned int *)(a3 + 60);
    if ( (((unsigned __int8)v12 ^ (unsigned __int8)v11) & 2) != 0 )
      *(_DWORD *)(a1 + 416) = v11 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v11) & 2;
    if ( *(_BYTE *)(a3 + 48) == *(_BYTE *)(a1 + 80)
      && *(_BYTE *)(a3 + 49) == *(_BYTE *)(a1 + 81)
      && *(_BYTE *)(a3 + 50) == *(_BYTE *)(a1 + 82)
      && *(_BYTE *)(a3 + 51) == *(_BYTE *)(a1 + 83)
      && *(_BYTE *)(a3 + 52) == *(_BYTE *)(a1 + 84)
      && *(_BYTE *)(a3 + 53) == *(_BYTE *)(a1 + 85) )
    {
      v13 = 1;
      v19 = *(_DWORD *)a1;
    }
    else
    {
      ++*(_DWORD *)a1;
      v13 = 0;
    }
    v14 = *(_QWORD *)(a1 + 64) == 0;
    *(_DWORD *)(a1 + 40) = *(_DWORD *)(a3 + 36);
    LOBYTE(v12) = v14;
    *(_QWORD *)(a1 + 80) = *(_QWORD *)(a3 + 48);
    QosUtilSetTokenSpec(a1 + 56, a3, v12);
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    LOBYTE(v16) = 1;
    *(_QWORD *)(a1 + 48) = QosTimerGetCurrentTime(CurrentProcessorNumber, 0, v16);
    QosTbcFlowUpdate(a1, a2, a3, (_DWORD *)((unsigned __int64)&v19 & -(__int64)(v13 != 0)), v18, a5, a6, a7);
  }
  *(_DWORD *)(a3 + 60) &= ~1u;
  return (unsigned int)a4;
}

```

## disassembly

```asm
0x140014434  mov     rax, rsp
0x140014437  push    rbx
0x140014438  push    rbp
0x140014439  push    rsi
0x14001443a  push    rdi
0x14001443b  push    r14
0x14001443d  push    r15
0x14001443f  sub     rsp, 48h
0x140014443  mov     dword ptr [rax+20h], 0
0x14001444a  mov     ebp, r9d
0x14001444d  mov     rdi, r8
0x140014450  mov     r15d, edx
0x140014453  mov     rbx, rcx
0x140014456  test    r9d, r9d
0x140014459  js      loc_14001454C
0x14001445f  mov     ecx, [rcx+1A0h]
0x140014465  mov     eax, ecx
0x140014467  mov     r8d, [r8+3Ch]
0x14001446b  xor     eax, r8d
0x14001446e  test    al, 2
0x140014470  jz      short loc_140014482
0x140014472  mov     eax, ecx
0x140014474  xor     eax, r8d
0x140014477  and     eax, 2
0x14001447a  xor     eax, ecx
0x14001447c  mov     [rbx+1A0h], eax
0x140014482  mov     al, [rbx+50h]
0x140014485  cmp     [rdi+30h], al
0x140014488  jnz     short loc_1400144C0
0x14001448a  mov     al, [rbx+51h]
0x14001448d  cmp     [rdi+31h], al
0x140014490  jnz     short loc_1400144C0
0x140014492  mov     al, [rbx+52h]
0x140014495  cmp     [rdi+32h], al
0x140014498  jnz     short loc_1400144C0
0x14001449a  mov     al, [rbx+53h]
0x14001449d  cmp     [rdi+33h], al
0x1400144a0  jnz     short loc_1400144C0
0x1400144a2  mov     al, [rbx+54h]
0x1400144a5  cmp     [rdi+34h], al
0x1400144a8  jnz     short loc_1400144C0
0x1400144aa  mov     al, [rbx+55h]
0x1400144ad  cmp     [rdi+35h], al
0x1400144b0  jnz     short loc_1400144C0
0x1400144b2  mov     eax, [rbx]
0x1400144b4  mov     r14b, 1
0x1400144b7  mov     [rsp+78h+arg_18], eax
0x1400144be  jmp     short loc_1400144C5
0x1400144c0  inc     dword ptr [rbx]
0x1400144c2  xor     r14b, r14b
0x1400144c5  mov     eax, [rdi+24h]
0x1400144c8  lea     rcx, [rbx+38h]
0x1400144cc  cmp     qword ptr [rcx+8], 0
0x1400144d1  mov     rdx, rdi
0x1400144d4  mov     [rbx+28h], eax
0x1400144d7  mov     rax, [rdi+30h]
0x1400144db  setz    r8b
0x1400144df  mov     [rbx+50h], rax
0x1400144e3  call    QosUtilSetTokenSpec
0x1400144e8  xor     ecx, ecx; ProcNumber
0x1400144ea  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400144f1  nop     dword ptr [rax+rax+00h]
0x1400144f6  mov     r8b, 1
0x1400144f9  xor     edx, edx
0x1400144fb  mov     ecx, eax
0x1400144fd  call    QosTimerGetCurrentTime
0x140014502  mov     [rbx+30h], rax
0x140014506  neg     r14b
0x140014509  lea     rax, [rsp+78h+arg_18]
0x140014511  mov     r8, rdi
0x140014514  sbb     r9, r9
0x140014517  mov     edx, r15d
0x14001451a  and     r9, rax
0x14001451d  mov     rcx, rbx
0x140014520  mov     rax, [rsp+78h+arg_30]
0x140014528  mov     [rsp+78h+var_40], rax
0x14001452d  mov     rax, [rsp+78h+arg_28]
0x140014535  mov     [rsp+78h+var_48], rax
0x14001453a  mov     rax, [rsp+78h+arg_20]
0x140014542  mov     [rsp+78h+var_50], rax
0x140014547  call    QosTbcFlowUpdate
0x14001454c  and     dword ptr [rdi+3Ch], 0FFFFFFFEh
0x140014550  mov     eax, ebp
0x140014552  add     rsp, 48h
0x140014556  pop     r15
0x140014558  pop     r14
0x14001455a  pop     rdi
0x14001455b  pop     rsi
0x14001455c  pop     rbp
0x14001455d  pop     rbx
0x14001455e  retn
```
