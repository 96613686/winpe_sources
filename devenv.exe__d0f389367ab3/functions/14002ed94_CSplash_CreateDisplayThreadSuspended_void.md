# CSplash::CreateDisplayThreadSuspended(void)

- ea: `0x14002ed94`
- end: `0x14002ef17`
- name: `?CreateDisplayThreadSuspended@CSplash@@AEAAPEAXXZ`
- size: `387`
- prototype: `void *__fastcall(CSplash *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14002e9c0`

## callees

- `0x140001020`
- `0x140002160`
- `0x140002190`
- `0x14002ed94`
- `0x14002ef20`
- `0x140039d5c`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14002ee5f`
- `KERNEL32!CreateThread` at `0x14002ee5f`
- `KERNEL32!CreateEventW` at `0x14002edc6`
- `KERNEL32!CreateEventW` at `0x14002ede7`
- `KERNEL32!CreateEventW` at `0x14002edc6`
- `KERNEL32!CreateEventW` at `0x14002ede7`
- `KERNEL32!CloseHandle` at `0x14002ee99`
- `KERNEL32!CloseHandle` at `0x14002eead`
- `KERNEL32!CloseHandle` at `0x14002eece`
- `KERNEL32!CloseHandle` at `0x14002eedd`
- `KERNEL32!CloseHandle` at `0x14002ee99`
- `KERNEL32!CloseHandle` at `0x14002eead`
- `KERNEL32!CloseHandle` at `0x14002eece`
- `KERNEL32!CloseHandle` at `0x14002eedd`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HANDLE __fastcall CSplash::CreateDisplayThreadSuspended(CSplash *this)
{
  HANDLE EventW; // rsi
  HANDLE v3; // rdi
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  __int64 v6; // rax
  HANDLE Thread; // rbp
  HANDLE v8; // rax
  HANDLE v9; // rax
  void *v10; // rcx
  void *v11; // rcx

  EventW = CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    ATL::AtlThrowLastWin32();
  v3 = CreateEventW(0, 1, 0, 0);
  if ( !v3 )
    ATL::AtlThrowLastWin32();
  v4 = operator new(0x18u);
  v5 = v4;
  if ( v4 )
  {
    v4[1] = 0;
    v4[2] = 0;
  }
  else
  {
    v5 = 0;
  }
  *v5 = this;
  v5[1] = anonymous_namespace_::DuplicateHandle(EventW);
  v6 = anonymous_namespace_::DuplicateHandle(v3);
  v5[2] = v6;
  if ( v5[1] && v6 && (Thread = CreateThread(0, 0, CSplash::ThreadProc, v5, 4u, 0)) != 0 )
  {
    v8 = EventW;
    EventW = 0;
    *((_QWORD *)this + 16) = v8;
    v9 = v3;
    v3 = 0;
    *((_QWORD *)this + 17) = v9;
    v5 = 0;
  }
  else
  {
    Thread = 0;
  }
  if ( v5 )
  {
    v10 = (void *)v5[2];
    if ( v10 )
    {
      CloseHandle(v10);
      v5[2] = 0;
    }
    v11 = (void *)v5[1];
    if ( v11 )
    {
      CloseHandle(v11);
      v5[1] = 0;
    }
    operator delete(v5, (const struct std::nothrow_t *)0x18);
  }
  if ( v3 )
    CloseHandle(v3);
  if ( EventW )
    CloseHandle(EventW);
  return Thread;
}

```

## disassembly

```asm
0x14002ed94  mov     [rsp+arg_8], rbx
0x14002ed99  mov     [rsp+arg_10], rbp
0x14002ed9e  push    rsi
0x14002ed9f  push    rdi
0x14002eda0  push    r14
0x14002eda2  sub     rsp, 50h
0x14002eda6  mov     rax, cs:__security_cookie
0x14002edad  xor     rax, rsp
0x14002edb0  mov     [rsp+68h+var_28], rax
0x14002edb5  mov     r14, rcx
0x14002edb8  xor     r9d, r9d; lpName
0x14002edbb  xor     r8d, r8d; bInitialState
0x14002edbe  lea     ebx, [r9+1]
0x14002edc2  mov     edx, ebx; bManualReset
0x14002edc4  xor     ecx, ecx; lpEventAttributes
0x14002edc6  call    cs:__imp_CreateEventW
0x14002edcc  mov     rsi, rax
0x14002edcf  mov     [rsp+68h+var_38], rax
0x14002edd4  test    rax, rax
0x14002edd7  jz      loc_14002EF11
0x14002eddd  xor     r9d, r9d; lpName
0x14002ede0  xor     r8d, r8d; bInitialState
0x14002ede3  mov     edx, ebx; bManualReset
0x14002ede5  xor     ecx, ecx; lpEventAttributes
0x14002ede7  call    cs:__imp_CreateEventW
0x14002eded  mov     rdi, rax
0x14002edf0  mov     [rsp+68h+var_30], rax
0x14002edf5  test    rax, rax
0x14002edf8  jz      loc_14002EF08
0x14002edfe  lea     ecx, [rbx+17h]; Size
0x14002ee01  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002ee06  mov     rbx, rax
0x14002ee09  test    rax, rax
0x14002ee0c  jz      short loc_14002EE1A
0x14002ee0e  and     qword ptr [rax+8], 0
0x14002ee13  and     qword ptr [rax+10h], 0
0x14002ee18  jmp     short loc_14002EE1C
0x14002ee1a  xor     ebx, ebx
0x14002ee1c  mov     [rbx], r14
0x14002ee1f  mov     rcx, rsi; hSourceHandle
0x14002ee22  call    _anonymous_namespace___DuplicateHandle
0x14002ee27  mov     [rbx+8], rax
0x14002ee2b  mov     rcx, rdi; hSourceHandle
0x14002ee2e  call    _anonymous_namespace___DuplicateHandle
0x14002ee33  mov     [rbx+10h], rax
0x14002ee37  cmp     qword ptr [rbx+8], 0
0x14002ee3c  jz      short loc_14002EE89
0x14002ee3e  test    rax, rax
0x14002ee41  jz      short loc_14002EE89
0x14002ee43  and     [rsp+68h+var_40], 0
0x14002ee49  mov     [rsp+68h+dwCreationFlags], 4; dwCreationFlags
0x14002ee51  mov     r9, rbx; lpParameter
0x14002ee54  lea     r8, ?ThreadProc@CSplash@@CAKPEAX@Z; lpStartAddress
0x14002ee5b  xor     edx, edx; dwStackSize
0x14002ee5d  xor     ecx, ecx; lpThreadAttributes
0x14002ee5f  call    cs:__imp_CreateThread
0x14002ee65  mov     rbp, rax
0x14002ee68  test    rax, rax
0x14002ee6b  jz      short loc_14002EE89
0x14002ee6d  mov     rax, rsi
0x14002ee70  xor     esi, esi
0x14002ee72  mov     [r14+80h], rax
0x14002ee79  mov     rax, rdi
0x14002ee7c  xor     edi, edi
0x14002ee7e  mov     [r14+88h], rax
0x14002ee85  xor     ebx, ebx
0x14002ee87  jmp     short loc_14002EE8B
0x14002ee89  xor     ebp, ebp
0x14002ee8b  test    rbx, rbx
0x14002ee8e  jz      short loc_14002EEC6
0x14002ee90  mov     rcx, [rbx+10h]; hObject
0x14002ee94  test    rcx, rcx
0x14002ee97  jz      short loc_14002EEA4
0x14002ee99  call    cs:__imp_CloseHandle
0x14002ee9f  and     qword ptr [rbx+10h], 0
0x14002eea4  mov     rcx, [rbx+8]; hObject
0x14002eea8  test    rcx, rcx
0x14002eeab  jz      short loc_14002EEB8
0x14002eead  call    cs:__imp_CloseHandle
0x14002eeb3  and     qword ptr [rbx+8], 0
0x14002eeb8  mov     edx, 18h; struct std::nothrow_t *
0x14002eebd  mov     rcx, rbx; void *
0x14002eec0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002eec5  nop
0x14002eec6  test    rdi, rdi
0x14002eec9  jz      short loc_14002EED5
0x14002eecb  mov     rcx, rdi; hObject
0x14002eece  call    cs:__imp_CloseHandle
0x14002eed4  nop
0x14002eed5  test    rsi, rsi
0x14002eed8  jz      short loc_14002EEE3
0x14002eeda  mov     rcx, rsi; hObject
0x14002eedd  call    cs:__imp_CloseHandle
0x14002eee3  mov     rax, rbp
0x14002eee6  mov     rcx, [rsp+68h+var_28]
0x14002eeeb  xor     rcx, rsp; StackCookie
0x14002eeee  call    __security_check_cookie
0x14002eef3  lea     r11, [rsp+68h+var_18]
0x14002eef8  mov     rbx, [r11+28h]
0x14002eefc  mov     rbp, [r11+30h]
0x14002ef00  mov     rsp, r11
0x14002ef03  pop     r14
0x14002ef05  pop     rdi
0x14002ef06  pop     rsi
0x14002ef07  retn
0x14002ef08  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x14002ef0e  jmp     short $+2
0x14002ef10  nop
0x14002ef11  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
```
