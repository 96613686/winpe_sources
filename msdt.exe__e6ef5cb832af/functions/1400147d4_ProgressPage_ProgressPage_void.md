# ProgressPage::~ProgressPage(void)

- ea: `0x1400147d4`
- end: `0x140014889`
- name: `??1ProgressPage@@UEAA@XZ`
- size: `181`
- prototype: `void __fastcall(ProgressPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014890`

## callees

- `0x14000dce4`
- `0x1400147d4`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x140014800`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140014822`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140014800`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140014822`
- `OLEAUT32!__imp_SysFreeString` at `0x140014865`
- `OLEAUT32!__imp_SysFreeString` at `0x140014865`

## pseudocode

```c
void __fastcall ProgressPage::~ProgressPage(ProgressPage *this)
{
  void *v2; // rdx
  void *v3; // rdx
  __int64 v4; // rcx
  OLECHAR *v5; // rcx

  *(_QWORD *)this = &ProgressPage::`vftable'{for `DirectUI::IElementListener'};
  *((_QWORD *)this + 1) = &WizardPage::`vftable'{for `DirectUI::IXProviderCP'};
  v2 = (void *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    DeleteTimerQueueTimer(0, v2, 0);
    *((_QWORD *)this + 14) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 )
  {
    DeleteTimerQueueTimer(0, v3, 0);
    *((_QWORD *)this + 15) = 0;
  }
  v4 = *((_QWORD *)this + 19);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 19) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 18);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 18) = 0;
  }
  WizardPage::~WizardPage(this);
}

```

## disassembly

```asm
0x1400147d4  push    rbx
0x1400147d6  sub     rsp, 20h
0x1400147da  mov     rbx, rcx
0x1400147dd  lea     rax, ??_7ProgressPage@@6BIElementListener@DirectUI@@@; const ProgressPage::`vftable'{for `DirectUI::IElementListener'}
0x1400147e4  mov     [rcx], rax
0x1400147e7  lea     rax, ??_7WizardPage@@6BIXProviderCP@DirectUI@@@; const WizardPage::`vftable'{for `DirectUI::IXProviderCP'}
0x1400147ee  mov     [rcx+8], rax
0x1400147f2  mov     rdx, [rcx+70h]; Timer
0x1400147f6  test    rdx, rdx
0x1400147f9  jz      short loc_140014814
0x1400147fb  xor     r8d, r8d; CompletionEvent
0x1400147fe  xor     ecx, ecx; TimerQueue
0x140014800  call    cs:__imp_DeleteTimerQueueTimer
0x140014807  nop     dword ptr [rax+rax+00h]
0x14001480c  mov     qword ptr [rbx+70h], 0
0x140014814  mov     rdx, [rbx+78h]; Timer
0x140014818  test    rdx, rdx
0x14001481b  jz      short loc_140014836
0x14001481d  xor     r8d, r8d; CompletionEvent
0x140014820  xor     ecx, ecx; TimerQueue
0x140014822  call    cs:__imp_DeleteTimerQueueTimer
0x140014829  nop     dword ptr [rax+rax+00h]
0x14001482e  mov     qword ptr [rbx+78h], 0
0x140014836  mov     rcx, [rbx+98h]
0x14001483d  test    rcx, rcx
0x140014840  jz      short loc_140014859
0x140014842  mov     rax, [rcx]
0x140014845  mov     rax, [rax+10h]
0x140014849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001484e  mov     qword ptr [rbx+98h], 0
0x140014859  mov     rcx, [rbx+90h]; bstrString
0x140014860  test    rcx, rcx
0x140014863  jz      short loc_14001487C
0x140014865  call    cs:__imp_SysFreeString
0x14001486c  nop     dword ptr [rax+rax+00h]
0x140014871  mov     qword ptr [rbx+90h], 0
0x14001487c  mov     rcx, rbx; this
0x14001487f  add     rsp, 20h
0x140014883  pop     rbx
0x140014884  jmp     ??1WizardPage@@UEAA@XZ; WizardPage::~WizardPage(void)
```
