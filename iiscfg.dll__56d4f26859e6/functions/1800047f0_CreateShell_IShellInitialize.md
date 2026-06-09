# CreateShell(IShellInitialize * *)

- ea: `0x1800047f0`
- end: `0x1800048ad`
- name: `?CreateShell@@YAJPEAPEAUIShellInitialize@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct IShellInitialize **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002d6c`

## callees

- `0x180004700`
- `0x1800047f0`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180004802`
- `ole32!CoTaskMemAlloc` at `0x180004802`

## pseudocode

```c
__int64 __fastcall CreateShell(struct IShellInitialize **a1)
{
  CSTShell *v2; // rax
  CSTShell *v3; // rbx
  unsigned int v4; // edx
  int v5; // edi

  v2 = (CSTShell *)CoTaskMemAlloc(0x68u);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  *((_QWORD *)v2 + 3) = 0;
  *(_QWORD *)v2 = &CSTShell::`vftable'{for `ISimpleTableWrite2'};
  *((_DWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 1) = &CSTShell::`vftable'{for `ISimpleTableController'};
  *((_QWORD *)v2 + 2) = &CSTShell::`vftable'{for `IShellInitialize'};
  *((_QWORD *)v2 + 7) = 0;
  *((_QWORD *)v2 + 8) = 0;
  *((_QWORD *)v2 + 9) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 0;
  *((_QWORD *)v2 + 12) = 0;
  v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IShellInitialize **))v2)(v2, &IID_IShellInitialize, a1);
  if ( v5 < 0 )
    CSTShell::`scalar deleting destructor'(v3, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800047f0  mov     [rsp+arg_0], rbx
0x1800047f5  push    rdi
0x1800047f6  sub     rsp, 20h
0x1800047fa  mov     rdi, rcx
0x1800047fd  mov     ecx, 68h ; 'h'; cb
0x180004802  call    cs:__imp_CoTaskMemAlloc
0x180004808  mov     rbx, rax
0x18000480b  test    rax, rax
0x18000480e  jz      loc_18000489D
0x180004814  mov     qword ptr [rbx+18h], 0
0x18000481c  lea     rax, ??_7CSTShell@@6BISimpleTableWrite2@@@; const CSTShell::`vftable'{for `ISimpleTableWrite2'}
0x180004823  mov     [rbx], rax
0x180004826  lea     rdx, IID_IShellInitialize
0x18000482d  mov     dword ptr [rbx+30h], 0
0x180004834  lea     rax, ??_7CSTShell@@6BISimpleTableController@@@; const CSTShell::`vftable'{for `ISimpleTableController'}
0x18000483b  mov     [rbx+8], rax
0x18000483f  mov     r8, rdi
0x180004842  lea     rax, ??_7CSTShell@@6BIShellInitialize@@@; const CSTShell::`vftable'{for `IShellInitialize'}
0x180004849  mov     rcx, rbx
0x18000484c  mov     [rbx+10h], rax
0x180004850  mov     qword ptr [rbx+38h], 0
0x180004858  mov     qword ptr [rbx+40h], 0
0x180004860  mov     qword ptr [rbx+48h], 0
0x180004868  mov     qword ptr [rbx+50h], 0
0x180004870  mov     qword ptr [rbx+58h], 0
0x180004878  mov     qword ptr [rbx+60h], 0
0x180004880  mov     rax, [rbx]
0x180004883  mov     rax, [rax]
0x180004886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000488b  mov     edi, eax
0x18000488d  test    eax, eax
0x18000488f  jns     short loc_180004899
0x180004891  mov     rcx, rbx; this
0x180004894  call    ??_GCSTShell@@QEAAPEAXI@Z; CSTShell::`scalar deleting destructor'(uint)
0x180004899  mov     eax, edi
0x18000489b  jmp     short loc_1800048A2
0x18000489d  mov     eax, 8007000Eh
0x1800048a2  mov     rbx, [rsp+28h+arg_0]
0x1800048a7  add     rsp, 20h
0x1800048ab  pop     rdi
0x1800048ac  retn
```
