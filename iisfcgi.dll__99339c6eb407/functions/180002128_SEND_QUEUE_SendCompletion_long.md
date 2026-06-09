# SEND_QUEUE::SendCompletion(long)

- ea: `0x180002128`
- end: `0x1800021f9`
- name: `?SendCompletion@SEND_QUEUE@@QEAAXJ@Z`
- size: `209`
- prototype: `void __fastcall(SEND_QUEUE *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003414`
- `0x180006670`
- `0x18000cfa0`

## callees

- `0x180001d50`
- `0x180002004`
- `0x180002128`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002165`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000213a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000213a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000215b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000215b`

## pseudocode

```c
void __fastcall SEND_QUEUE::SendCompletion(struct _RTL_CRITICAL_SECTION *this, signed int a2)
{
  bool v4; // zf
  void *v5; // rcx
  signed int LastError; // eax
  _DWORD *v7; // rdi
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  EnterCriticalSection(this + 1);
  v4 = LODWORD(this[3].DebugInfo) == 0;
  HIDWORD(this[2].SpinCount) = 0;
  if ( v4 || (v5 = *(void **)&this[3].LockCount, LODWORD(this[3].DebugInfo) = 0, SetEvent(v5)) )
  {
    v7 = (_DWORD *)&this[2].DebugInfo + 1;
    if ( HIDWORD(this[2].DebugInfo) )
    {
      a2 = -2147023901;
    }
    else if ( a2 >= 0 )
    {
      a2 = SEND_QUEUE::Send((SEND_QUEUE *)this);
      if ( a2 >= 0 && LODWORD(this[2].SpinCount) && HIDWORD(this->OwningThread) <= LODWORD(this->OwningThread) )
      {
        DebugInfo = this->DebugInfo;
        LODWORD(this[2].SpinCount) = 0;
        (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 8LL))(DebugInfo);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    a2 = LastError;
    if ( LastError > 0 )
      a2 = (unsigned __int16)LastError | 0x80070000;
    v7 = (_DWORD *)&this[2].DebugInfo + 1;
  }
  LeaveCriticalSection(this + 1);
  if ( a2 < 0 && !*v7 )
    (**(void (__fastcall ***)(PRTL_CRITICAL_SECTION_DEBUG, _QWORD))&this->DebugInfo->Type)(
      this->DebugInfo,
      (unsigned int)a2);
  SEND_QUEUE::DereferenceSendQueue((SEND_QUEUE *)this);
}

```

## disassembly

```asm
0x180002128  push    rbx
0x18000212a  push    rbp
0x18000212b  push    rsi
0x18000212c  push    rdi
0x18000212d  sub     rsp, 28h
0x180002131  mov     rbx, rcx
0x180002134  mov     esi, edx
0x180002136  add     rcx, 28h ; '('; lpCriticalSection
0x18000213a  call    cs:__imp_EnterCriticalSection
0x180002140  cmp     dword ptr [rbx+78h], 0
0x180002144  mov     dword ptr [rbx+74h], 0
0x18000214b  jz      short loc_180002180
0x18000214d  mov     rcx, [rbx+80h]; hEvent
0x180002154  mov     dword ptr [rbx+78h], 0
0x18000215b  call    cs:__imp_SetEvent
0x180002161  test    eax, eax
0x180002163  jnz     short loc_180002180
0x180002165  call    cs:__imp_GetLastError
0x18000216b  mov     esi, eax
0x18000216d  test    eax, eax
0x18000216f  jle     short loc_18000217A
0x180002171  movzx   esi, ax
0x180002174  or      esi, 80070000h
0x18000217a  lea     rdi, [rbx+54h]
0x18000217e  jmp     short loc_1800021C6
0x180002180  lea     rdi, [rbx+54h]
0x180002184  cmp     dword ptr [rdi], 0
0x180002187  jz      short loc_180002190
0x180002189  mov     esi, 800703E3h
0x18000218e  jmp     short loc_1800021C6
0x180002190  test    esi, esi
0x180002192  js      short loc_1800021C6
0x180002194  mov     rcx, rbx; this
0x180002197  call    ?Send@SEND_QUEUE@@AEAAJXZ; SEND_QUEUE::Send(void)
0x18000219c  mov     esi, eax
0x18000219e  test    eax, eax
0x1800021a0  js      short loc_1800021C6
0x1800021a2  cmp     dword ptr [rbx+70h], 0
0x1800021a6  jz      short loc_1800021C6
0x1800021a8  mov     ecx, [rbx+10h]
0x1800021ab  cmp     [rbx+14h], ecx
0x1800021ae  ja      short loc_1800021C6
0x1800021b0  mov     rcx, [rbx]
0x1800021b3  mov     dword ptr [rbx+70h], 0
0x1800021ba  mov     rax, [rcx]
0x1800021bd  mov     rax, [rax+8]
0x1800021c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021c6  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800021ca  call    cs:__imp_LeaveCriticalSection
0x1800021d0  test    esi, esi
0x1800021d2  jns     short loc_1800021E9
0x1800021d4  cmp     dword ptr [rdi], 0
0x1800021d7  jnz     short loc_1800021E9
0x1800021d9  mov     rcx, [rbx]
0x1800021dc  mov     edx, esi
0x1800021de  mov     rax, [rcx]
0x1800021e1  mov     rax, [rax]
0x1800021e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021e9  mov     rcx, rbx; this
0x1800021ec  add     rsp, 28h
0x1800021f0  pop     rdi
0x1800021f1  pop     rsi
0x1800021f2  pop     rbp
0x1800021f3  pop     rbx
0x1800021f4  jmp     ?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ; SEND_QUEUE::DereferenceSendQueue(void)
```
