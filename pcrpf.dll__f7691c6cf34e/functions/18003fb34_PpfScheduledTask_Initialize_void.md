# PpfScheduledTask::Initialize(void)

- ea: `0x18003fb34`
- end: `0x18003fca3`
- name: `?Initialize@PpfScheduledTask@@QEAAJXZ`
- size: `367`
- prototype: `__int64 __fastcall(PpfScheduledTask *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003c280`
- `0x18003fcac`

## callees

- `0x180009c64`
- `0x180033670`
- `0x18003c52c`
- `0x18003fb34`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fbf4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fc89`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fbf4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18003fc89`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003fb96`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18003fb96`

## string_xrefs

- `0x18003fb6b`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003fbc4`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`
- `0x18003fc2d`: `onecore\base\ngscb\pcrpf\helperlib\task.cpp`

## pseudocode

```c
__int64 __fastcall PpfScheduledTask::Initialize(PpfScheduledTask *this)
{
  int IsOSWinPEBased; // eax
  unsigned int v3; // ebx
  int v5; // ebx
  int Task; // eax
  unsigned int v7; // esi
  struct IRegisteredTask *v8; // rcx
  int v9; // eax
  struct IRegisteredTask *v10; // rcx
  struct IRegisteredTask *v11; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  int v14; // [rsp+50h] [rbp+30h] BYREF
  __int16 v15; // [rsp+58h] [rbp+38h] BYREF
  struct IRegisteredTask *v16; // [rsp+60h] [rbp+40h] BYREF

  if ( *(_BYTE *)this )
    return 0;
  LOBYTE(v14) = 0;
  IsOSWinPEBased = PpfhIsOSWinPEBased((bool *)&v14);
  v3 = IsOSWinPEBased;
  if ( IsOSWinPEBased < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)IsOSWinPEBased,
      savedregs);
    return v3;
  }
  if ( (_BYTE)v14 )
  {
    *((_BYTE *)this + 1) = v14;
    return 0;
  }
  v5 = RoInitialize(1);
  v14 = v5;
  v16 = 0;
  Task = PpfScheduledTask::GetTask((const unsigned __int16 **)this, &v16);
  v7 = Task;
  if ( Task >= 0 )
  {
    v15 = 0;
    v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int16 *))v16->lpVtbl->get_Enabled)(v16, &v15);
    v7 = v9;
    if ( v9 >= 0 )
    {
      *((_BYTE *)this + 2) = v15 != 0;
      *(_WORD *)this = 1;
      v11 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(struct IRegisteredTask *))v11->lpVtbl->Release)(v11);
      }
      if ( v5 >= 0 )
        RoUninitialize();
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    v10 = v16;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(struct IRegisteredTask *))v10->lpVtbl->Release)(v10);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\task.cpp",
      (const char *)(unsigned int)Task,
      savedregs);
    v8 = v16;
    if ( v16 )
    {
      v16 = 0;
      ((void (__fastcall *)(struct IRegisteredTask *))v8->lpVtbl->Release)(v8);
    }
  }
  if ( v5 >= 0 )
    RoUninitialize();
  return v7;
}

```

## disassembly

```asm
0x18003fb34  push    rbp
0x18003fb36  push    rbx
0x18003fb37  push    rsi
0x18003fb38  push    rdi
0x18003fb39  push    r14; int
0x18003fb3b  mov     rbp, rsp
0x18003fb3e  sub     rsp, 20h
0x18003fb42  mov     rdi, rcx
0x18003fb45  xor     r14d, r14d
0x18003fb48  cmp     [rcx], r14b
0x18003fb4b  jnz     loc_18003FC95
0x18003fb51  mov     byte ptr [rbp+arg_0], r14b
0x18003fb55  lea     rcx, [rbp+arg_0]; bool *
0x18003fb59  call    ?PpfhIsOSWinPEBased@@YAJPEA_N@Z; PpfhIsOSWinPEBased(bool *)
0x18003fb5e  mov     ebx, eax
0x18003fb60  test    eax, eax
0x18003fb62  jns     short loc_18003FB82
0x18003fb64  mov     rcx, [rbp+28h]; this
0x18003fb68  mov     r9d, eax; char *
0x18003fb6b  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fb72  lea     edx, [r14+7Fh]; void *
0x18003fb76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb7b  mov     eax, ebx
0x18003fb7d  jmp     loc_18003FC97
0x18003fb82  mov     al, byte ptr [rbp+arg_0]
0x18003fb85  test    al, al
0x18003fb87  jz      short loc_18003FB91
0x18003fb89  mov     [rdi+1], al
0x18003fb8c  jmp     loc_18003FC95
0x18003fb91  mov     ecx, 1
0x18003fb96  call    cs:__imp_RoInitialize
0x18003fb9d  nop     dword ptr [rax+rax+00h]
0x18003fba2  mov     ebx, eax
0x18003fba4  mov     [rbp+arg_0], eax
0x18003fba7  mov     [rbp+arg_10], r14
0x18003fbab  lea     rdx, [rbp+arg_10]; struct IRegisteredTask **
0x18003fbaf  mov     rcx, rdi; this
0x18003fbb2  call    ?GetTask@PpfScheduledTask@@AEAAJPEAPEAUIRegisteredTask@@@Z; PpfScheduledTask::GetTask(IRegisteredTask * *)
0x18003fbb7  mov     esi, eax
0x18003fbb9  test    eax, eax
0x18003fbbb  jns     short loc_18003FC07
0x18003fbbd  mov     rcx, [rbp+28h]; this
0x18003fbc1  mov     r9d, eax; char *
0x18003fbc4  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fbcb  mov     edx, 89h; void *
0x18003fbd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fbd5  nop
0x18003fbd6  mov     rcx, [rbp+arg_10]
0x18003fbda  test    rcx, rcx
0x18003fbdd  jz      short loc_18003FBF0
0x18003fbdf  mov     [rbp+arg_10], r14
0x18003fbe3  mov     rax, [rcx]
0x18003fbe6  mov     rax, [rax+10h]
0x18003fbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbef  nop
0x18003fbf0  test    ebx, ebx
0x18003fbf2  js      short loc_18003FC00
0x18003fbf4  call    cs:__imp_RoUninitialize
0x18003fbfb  nop     dword ptr [rax+rax+00h]
0x18003fc00  mov     eax, esi
0x18003fc02  jmp     loc_18003FC97
0x18003fc07  mov     [rbp+arg_8], r14w
0x18003fc0c  mov     rcx, [rbp+arg_10]
0x18003fc10  mov     rax, [rcx]
0x18003fc13  lea     rdx, [rbp+arg_8]
0x18003fc17  mov     rax, [rax+50h]
0x18003fc1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc20  mov     esi, eax
0x18003fc22  test    eax, eax
0x18003fc24  jns     short loc_18003FC5B
0x18003fc26  mov     rcx, [rbp+28h]; this
0x18003fc2a  mov     r9d, eax; char *
0x18003fc2d  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18003fc34  mov     edx, 8Ch; void *
0x18003fc39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fc3e  nop
0x18003fc3f  mov     rcx, [rbp+arg_10]
0x18003fc43  test    rcx, rcx
0x18003fc46  jz      short loc_18003FC59
0x18003fc48  mov     [rbp+arg_10], r14
0x18003fc4c  mov     rax, [rcx]
0x18003fc4f  mov     rax, [rax+10h]
0x18003fc53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc58  nop
0x18003fc59  jmp     short loc_18003FBF0
0x18003fc5b  cmp     [rbp+arg_8], r14w
0x18003fc60  setnz   al
0x18003fc63  mov     [rdi+2], al
0x18003fc66  mov     word ptr [rdi], 1
0x18003fc6b  mov     rcx, [rbp+arg_10]
0x18003fc6f  test    rcx, rcx
0x18003fc72  jz      short loc_18003FC85
0x18003fc74  mov     [rbp+arg_10], r14
0x18003fc78  mov     rax, [rcx]
0x18003fc7b  mov     rax, [rax+10h]
0x18003fc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fc84  nop
0x18003fc85  test    ebx, ebx
0x18003fc87  js      short loc_18003FC95
0x18003fc89  call    cs:__imp_RoUninitialize
0x18003fc90  nop     dword ptr [rax+rax+00h]
0x18003fc95  xor     eax, eax
0x18003fc97  add     rsp, 20h
0x18003fc9b  pop     r14
0x18003fc9d  pop     rdi
0x18003fc9e  pop     rsi
0x18003fc9f  pop     rbx
0x18003fca0  pop     rbp
0x18003fca1  retn
```
