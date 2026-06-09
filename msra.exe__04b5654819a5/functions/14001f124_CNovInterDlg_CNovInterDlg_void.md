# CNovInterDlg::~CNovInterDlg(void)

- ea: `0x14001f124`
- end: `0x14001f1fc`
- name: `??1CNovInterDlg@@UEAA@XZ`
- size: `216`
- prototype: `void __fastcall(CNovInterDlg *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c33c`
- `0x14001f250`

## callees

- `0x140016a34`
- `0x14001f124`
- `0x140034be8`
- `0x14004d010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14001f1c4`
- `KERNEL32!HeapFree` at `0x14001f1c4`
- `KERNEL32!GetProcessHeap` at `0x14001f1b0`
- `KERNEL32!GetProcessHeap` at `0x14001f1b0`
- `GDI32!DeleteObject` at `0x14001f18d`
- `GDI32!DeleteObject` at `0x14001f18d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CNovInterDlg::~CNovInterDlg(CNovInterDlg *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  AtlThunkData_t *v7; // rcx

  *(_QWORD *)this = &CNovInterDlg::`vftable';
  v2 = *((_QWORD *)this + 18);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 18) = 0;
  }
  v3 = *((_QWORD *)this + 26);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 26) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 19);
  if ( v4 )
  {
    DeleteObject(v4);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 16);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *((_QWORD *)this + 16) = 0;
  }
  CRemoteAssistanceApp::ResetTicketAndClearVC((CRemoteAssistanceApp *)v4);
  v7 = (AtlThunkData_t *)*((_QWORD *)this + 5);
  if ( v7 )
    AtlThunk_FreeData(v7);
}

```

## disassembly

```asm
0x14001f124  mov     [rsp+arg_0], rbx
0x14001f129  push    rdi
0x14001f12a  sub     rsp, 20h
0x14001f12e  mov     rbx, rcx
0x14001f131  lea     rax, ??_7CNovInterDlg@@6B@; const CNovInterDlg::`vftable'
0x14001f138  mov     [rcx], rax
0x14001f13b  mov     rcx, [rcx+90h]
0x14001f142  test    rcx, rcx
0x14001f145  jz      short loc_14001F15E
0x14001f147  mov     rax, [rcx]
0x14001f14a  mov     rax, [rax+10h]
0x14001f14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f153  mov     qword ptr [rbx+90h], 0
0x14001f15e  mov     rcx, [rbx+0D0h]
0x14001f165  test    rcx, rcx
0x14001f168  jz      short loc_14001F181
0x14001f16a  mov     rax, [rcx]
0x14001f16d  mov     rax, [rax+10h]
0x14001f171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f176  mov     qword ptr [rbx+0D0h], 0
0x14001f181  mov     rcx, [rbx+98h]; ho
0x14001f188  test    rcx, rcx
0x14001f18b  jz      short loc_14001F1A4
0x14001f18d  call    cs:__imp_DeleteObject
0x14001f194  nop     dword ptr [rax+rax+00h]
0x14001f199  mov     qword ptr [rbx+98h], 0
0x14001f1a4  mov     rdi, [rbx+80h]
0x14001f1ab  test    rdi, rdi
0x14001f1ae  jz      short loc_14001F1DB
0x14001f1b0  call    cs:__imp_GetProcessHeap
0x14001f1b7  nop     dword ptr [rax+rax+00h]
0x14001f1bc  mov     r8, rdi; lpMem
0x14001f1bf  xor     edx, edx; dwFlags
0x14001f1c1  mov     rcx, rax; hHeap
0x14001f1c4  call    cs:__imp_HeapFree
0x14001f1cb  nop     dword ptr [rax+rax+00h]
0x14001f1d0  mov     qword ptr [rbx+80h], 0
0x14001f1db  call    ?ResetTicketAndClearVC@CRemoteAssistanceApp@@QEAAJXZ; CRemoteAssistanceApp::ResetTicketAndClearVC(void)
0x14001f1e0  nop
0x14001f1e1  mov     rcx, [rbx+28h]; Thunk
0x14001f1e5  test    rcx, rcx
0x14001f1e8  jz      short loc_14001F1F0
0x14001f1ea  call    AtlThunk_FreeData
0x14001f1ef  nop
0x14001f1f0  mov     rbx, [rsp+28h+arg_0]
0x14001f1f5  add     rsp, 20h
0x14001f1f9  pop     rdi
0x14001f1fa  retn
```
