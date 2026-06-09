# NatEditorCreateTicket

- ea: `0x140005780`
- end: `0x1400058ba`
- name: `NatEditorCreateTicket`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140005780`
- `0x14001d05c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400057d6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400057d6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000586d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000586d`

## pseudocode

```c
__int64 __fastcall NatEditorCreateTicket(
        __int64 a1,
        char a2,
        unsigned int a3,
        unsigned __int16 a4,
        unsigned int a5,
        unsigned __int16 a6,
        unsigned int *a7,
        unsigned __int16 *a8)
{
  KSPIN_LOCK *v12; // rdi
  __int64 v13; // rdx
  unsigned int Ticket; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
  v12 = (KSPIN_LOCK *)(a1 + 24);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a1 + 24));
  v13 = a6;
  LOBYTE(v13) = a2;
  Ticket = NatCreateTicket(a1, v13, a3, a4, a5, a6, 0, 0, 0, a7, a8);
  if ( Ticket
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids);
  }
  KeReleaseSpinLockFromDpcLevel(v12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids, Ticket);
  }
  return Ticket;
}

```

## disassembly

```asm
0x140005780  push    rbx
0x140005782  push    rbp
0x140005783  push    rsi
0x140005784  push    rdi
0x140005785  push    r13
0x140005787  push    r14
0x140005789  sub     rsp, 68h
0x14000578d  movzx   esi, r9w
0x140005791  mov     ebp, r8d
0x140005794  mov     r14b, dl
0x140005797  mov     rbx, rcx
0x14000579a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400057a1  lea     r13, WPP_GLOBAL_Control
0x1400057a8  cmp     rcx, r13
0x1400057ab  jz      short loc_1400057CF
0x1400057ad  mov     eax, [rcx+2Ch]
0x1400057b0  test    al, 1
0x1400057b2  jz      short loc_1400057CF
0x1400057b4  cmp     byte ptr [rcx+29h], 6
0x1400057b8  jb      short loc_1400057CF
0x1400057ba  mov     rcx, [rcx+18h]
0x1400057be  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x1400057c5  mov     edx, 29h ; ')'
0x1400057ca  call    WPP_SF_
0x1400057cf  lea     rdi, [rbx+18h]
0x1400057d3  mov     rcx, rdi; SpinLock
0x1400057d6  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400057dd  nop     dword ptr [rax+rax+00h]
0x1400057e2  movzx   edx, [rsp+98h+arg_28]
0x1400057ea  xor     ecx, ecx
0x1400057ec  mov     rax, [rsp+98h+arg_38]
0x1400057f4  movzx   r9d, si
0x1400057f8  mov     [rsp+98h+var_48], rax
0x1400057fd  mov     r8d, ebp
0x140005800  mov     rax, [rsp+98h+arg_30]
0x140005808  mov     [rsp+98h+var_50], rax
0x14000580d  mov     eax, [rsp+98h+arg_20]
0x140005814  mov     [rsp+98h+var_58], cx
0x140005819  mov     [rsp+98h+var_60], rcx
0x14000581e  mov     [rsp+98h+var_68], ecx
0x140005822  mov     rcx, rbx
0x140005825  mov     [rsp+98h+var_70], edx
0x140005829  mov     dl, r14b
0x14000582c  mov     [rsp+98h+var_78], eax
0x140005830  call    NatCreateTicket
0x140005835  mov     ebx, eax
0x140005837  test    eax, eax
0x140005839  jz      short loc_14000586A
0x14000583b  mov     rcx, cs:WPP_GLOBAL_Control
0x140005842  cmp     rcx, r13
0x140005845  jz      short loc_14000586A
0x140005847  mov     edx, [rcx+2Ch]
0x14000584a  test    dl, 1
0x14000584d  jz      short loc_14000586A
0x14000584f  cmp     byte ptr [rcx+29h], 2
0x140005853  jb      short loc_14000586A
0x140005855  mov     rcx, [rcx+18h]
0x140005859  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x140005860  mov     edx, 2Ah ; '*'
0x140005865  call    WPP_SF_
0x14000586a  mov     rcx, rdi; SpinLock
0x14000586d  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140005874  nop     dword ptr [rax+rax+00h]
0x140005879  mov     rcx, cs:WPP_GLOBAL_Control
0x140005880  cmp     rcx, r13
0x140005883  jz      short loc_1400058AA
0x140005885  mov     eax, [rcx+2Ch]
0x140005888  test    al, 1
0x14000588a  jz      short loc_1400058AA
0x14000588c  cmp     byte ptr [rcx+29h], 6
0x140005890  jb      short loc_1400058AA
0x140005892  mov     rcx, [rcx+18h]
0x140005896  lea     r8, WPP_37d479de965b38db5e5cf32a4e7b4389_Traceguids
0x14000589d  mov     edx, 2Bh ; '+'
0x1400058a2  mov     r9d, ebx
0x1400058a5  call    WPP_SF_d
0x1400058aa  mov     eax, ebx
0x1400058ac  add     rsp, 68h
0x1400058b0  pop     r14
0x1400058b2  pop     r13
0x1400058b4  pop     rdi
0x1400058b5  pop     rsi
0x1400058b6  pop     rbp
0x1400058b7  pop     rbx
0x1400058b8  retn
```
