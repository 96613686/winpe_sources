# CPrintTicketHandle::CPrintTicketHandle(IPrintTicketService *,int,int,PrintCore::ModernPrinterType,ushort *)

- ea: `0x180018838`
- end: `0x1800188b2`
- name: `??0CPrintTicketHandle@@QEAA@PEAUIPrintTicketService@@HHW4ModernPrinterType@PrintCore@@PEAG@Z`
- size: `122`
- prototype: `__int64 __fastcall(__int64, __int64, int, int, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180019300`
- `0x1800194e0`

## callees

- `0x1800056e0`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001885c`
- `KERNEL32!GetCurrentThreadId` at `0x18001885c`

## pseudocode

```c
__int64 __fastcall CPrintTicketHandle::CPrintTicketHandle(__int64 a1, __int64 a2, int a3, int a4, int a5, __int64 a6)
{
  DWORD CurrentThreadId; // eax

  *(_QWORD *)(a1 + 8) = a1;
  *(_QWORD *)a1 = &CPrintTicketHandle::`vftable';
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a1 + 24) = a2;
  *(_DWORD *)(a1 + 16) = CurrentThreadId;
  *(_DWORD *)(a1 + 40) = a5;
  *(_DWORD *)(a1 + 32) = a3;
  *(_DWORD *)(a1 + 36) = a4;
  *(_QWORD *)(a1 + 48) = 0;
  NCoreLibrary::TGenericSP<unsigned short *,NCoreLibrary::TAutoPtrBSTR,unsigned short *,0,unsigned short * const *>::Reset(a1 + 48);
  *(_QWORD *)(a1 + 48) = a6;
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 8LL))(*(_QWORD *)(a1 + 24));
  return a1;
}

```

## disassembly

```asm
0x180018838  push    rbx
0x18001883a  push    rsi
0x18001883b  push    rdi
0x18001883c  push    r14
0x18001883e  sub     rsp, 28h
0x180018842  lea     rax, ??_7CPrintTicketHandle@@6B@; const CPrintTicketHandle::`vftable'
0x180018849  mov     [rcx+8], rcx
0x18001884d  mov     [rcx], rax
0x180018850  mov     esi, r9d
0x180018853  mov     edi, r8d
0x180018856  mov     rbx, rdx
0x180018859  mov     r14, rcx
0x18001885c  call    cs:__imp_GetCurrentThreadId
0x180018862  mov     [r14+18h], rbx
0x180018866  lea     rbx, [r14+30h]
0x18001886a  mov     [r14+10h], eax
0x18001886e  mov     rcx, rbx
0x180018871  mov     eax, [rsp+48h+arg_20]
0x180018875  mov     [r14+28h], eax
0x180018879  mov     [r14+20h], edi
0x18001887d  mov     [r14+24h], esi
0x180018881  mov     qword ptr [rbx], 0
0x180018888  call    ?Reset@?$TGenericSP@PEAGVTAutoPtrBSTR@NCoreLibrary@@PEAG$0A@PEBQEAG@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<ushort *,NCoreLibrary::TAutoPtrBSTR,ushort *,0,ushort * const *>::Reset(void)
0x18001888d  mov     rax, [rsp+48h+arg_28]
0x180018892  mov     [rbx], rax
0x180018895  mov     rcx, [r14+18h]
0x180018899  mov     rax, [rcx]
0x18001889c  mov     rax, [rax+8]
0x1800188a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188a5  mov     rax, r14
0x1800188a8  add     rsp, 28h
0x1800188ac  pop     r14
0x1800188ae  pop     rdi
0x1800188af  pop     rsi
0x1800188b0  pop     rbx
0x1800188b1  retn
```
