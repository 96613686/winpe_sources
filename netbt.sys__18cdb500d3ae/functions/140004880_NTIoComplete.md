# NTIoComplete

- ea: `0x140004880`
- end: `0x140004911`
- name: `NTIoComplete`
- size: `145`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400021d0`
- `0x14000312c`
- `0x140003d04`
- `0x1400043c8`
- `0x140004920`
- `0x14000ba70`
- `0x14000dd3c`
- `0x1400104d8`
- `0x140010c90`
- `0x14001212c`
- `0x1400133c0`
- `0x140017a3c`
- `0x1400182a0`
- `0x140018ea0`
- `0x14001ba80`
- `0x14001c600`
- `0x14001d460`
- `0x14001e168`
- `0x14001e8f4`
- `0x14001f8d0`
- `0x140020534`
- `0x140020900`
- `0x140021280`
- `0x140022ed0`
- `0x140024e10`
- `0x1400269a8`
- `0x140029420`
- `0x14002a8c0`
- `0x14002ca6c`
- `0x14002d9f8`
- `0x14002dcd0`
- `0x14003005c`
- `0x14003027c`
- `0x1400304c8`
- `0x140045128`
- `0x140047f20`
- `0x14004f08c`
- `0x140052864`

## callees

- `0x140004880`
- `0x140041e1c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400048d7`
- `ntoskrnl!IofCompleteRequest` at `0x1400048d7`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400048c6`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x1400048c6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400048af`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400048af`

## pseudocode

```c
void __fastcall NTIoComplete(PIRP Irp, NTSTATUS a2, unsigned int a3)
{
  KIRQL Irql; // [rsp+48h] [rbp+10h] BYREF

  Irql = 0;
  Irp->IoStatus.Status = a2;
  if ( a3 != -1 )
    Irp->IoStatus.Information = a3;
  if ( SBYTE2(xmmword_140038420) < 0 )
    WPP_SF_qdd(1047, 70, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, Irp, a2, Irp->IoStatus.Information);
  IoAcquireCancelSpinLock(&Irql);
  _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, 0);
  IoReleaseCancelSpinLock(Irql);
  IofCompleteRequest(Irp, 2);
}

```

## disassembly

```asm
0x140004880  push    rbx
0x140004882  sub     rsp, 30h
0x140004886  mov     [rsp+38h+Irql], 0
0x14000488b  mov     r10d, edx
0x14000488e  mov     [rcx+30h], edx
0x140004891  mov     rbx, rcx
0x140004894  cmp     r8d, 0FFFFFFFFh
0x140004898  jz      short loc_1400048A1
0x14000489a  mov     eax, r8d
0x14000489d  mov     [rcx+38h], rax
0x1400048a1  cmp     byte ptr cs:xmmword_140038420+2, 0
0x1400048a8  jl      short loc_1400048EA
0x1400048aa  lea     rcx, [rsp+38h+Irql]; Irql
0x1400048af  call    cs:__imp_IoAcquireCancelSpinLock
0x1400048b6  nop     dword ptr [rax+rax+00h]
0x1400048bb  xor     eax, eax
0x1400048bd  xchg    rax, [rbx+68h]
0x1400048c1  movzx   ecx, [rsp+38h+Irql]; Irql
0x1400048c6  call    cs:__imp_IoReleaseCancelSpinLock
0x1400048cd  nop     dword ptr [rax+rax+00h]
0x1400048d2  mov     dl, 2; PriorityBoost
0x1400048d4  mov     rcx, rbx; Irp
0x1400048d7  call    cs:__imp_IofCompleteRequest
0x1400048de  nop     dword ptr [rax+rax+00h]
0x1400048e3  add     rsp, 30h
0x1400048e7  pop     rbx
0x1400048e8  retn
0x1400048ea  mov     eax, [rbx+38h]
0x1400048ed  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x1400048f4  mov     [rsp+38h+var_10], eax
0x1400048f8  mov     edx, 46h ; 'F'
0x1400048fd  mov     ecx, 417h
0x140004902  mov     [rsp+38h+var_18], r10d
0x140004907  mov     r9, rbx
0x14000490a  call    WPP_SF_qdd
0x14000490f  jmp     short loc_1400048AA
```
