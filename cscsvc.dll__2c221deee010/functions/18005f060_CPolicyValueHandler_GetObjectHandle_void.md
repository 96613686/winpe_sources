# CPolicyValueHandler::_GetObjectHandle(void * *)

- ea: `0x18005f060`
- end: `0x18005f19a`
- name: `?_GetObjectHandle@CPolicyValueHandler@@EEAAJPEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(CPolicyValueHandler *__hidden this, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002f10c`
- `0x180036394`
- `0x18003c488`
- `0x18005f060`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f08e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005f08e`
- `USERENV!RegisterGPNotification` at `0x18005f13f`
- `USERENV!RegisterGPNotification` at `0x18005f13f`

## string_xrefs

- `0x18005f103`: `computer`

## pseudocode

```c
__int64 __fastcall CPolicyValueHandler::_GetObjectHandle(CPolicyValueHandler *this, void **a2)
{
  int v2; // ebx
  HANDLE EventW; // rax
  unsigned int Error; // eax
  CObjectMonitor *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  const wchar_t *v10; // r9
  int v11; // eax

  v2 = 0;
  *a2 = 0;
  if ( *((_QWORD *)this + 11) )
    goto LABEL_19;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( EventW )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000) != 0 )
    {
      v9 = (*(__int64 (__fastcall **)(CPolicyValueHandler *))(*(_QWORD *)this + 32LL))(this);
      v10 = L"computer";
      if ( !v9 )
        v10 = L"user";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids, v10);
    }
    v11 = (*(__int64 (__fastcall **)(CPolicyValueHandler *))(*(_QWORD *)this + 32LL))(this);
    if ( RegisterGPNotification(*((HANDLE *)this + 11), v11) )
    {
      *((_DWORD *)this + 24) = 1;
LABEL_19:
      *a2 = (void *)*((_QWORD *)this + 11);
      return (unsigned int)v2;
    }
    Error = ResultFromLastError();
    v2 = Error;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 32;
      goto LABEL_15;
    }
  }
  else
  {
    Error = ResultFromLastError();
    v2 = Error;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v8 = 30;
LABEL_15:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids, Error);
    }
  }
  if ( v2 >= 0 )
    goto LABEL_19;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005f060  push    rbx
0x18005f062  push    rsi
0x18005f063  push    rdi
0x18005f064  push    r14
0x18005f066  sub     rsp, 28h
0x18005f06a  xor     ebx, ebx
0x18005f06c  mov     qword ptr [rdx], 0
0x18005f073  mov     r14, rdx
0x18005f076  mov     rdi, rcx
0x18005f079  cmp     [rcx+58h], rbx
0x18005f07d  jnz     loc_18005F187
0x18005f083  xor     r9d, r9d; lpName
0x18005f086  lea     edx, [rbx+1]; bManualReset
0x18005f089  xor     r8d, r8d; bInitialState
0x18005f08c  xor     ecx, ecx; lpEventAttributes
0x18005f08e  call    cs:__imp_CreateEventW
0x18005f094  mov     [rdi+58h], rax
0x18005f098  test    rax, rax
0x18005f09b  jnz     short loc_18005F0CF
0x18005f09d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005f0a2  mov     ebx, eax
0x18005f0a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f0ab  lea     rsi, WPP_GLOBAL_Control
0x18005f0b2  cmp     rcx, rsi
0x18005f0b5  jz      loc_18005F17A
0x18005f0bb  test    byte ptr [rcx+1Ch], 2
0x18005f0bf  jz      loc_18005F17A
0x18005f0c5  mov     edx, 1Eh
0x18005f0ca  jmp     loc_18005F167
0x18005f0cf  mov     rax, cs:WPP_GLOBAL_Control
0x18005f0d6  lea     rsi, WPP_GLOBAL_Control
0x18005f0dd  cmp     rax, rsi
0x18005f0e0  jz      short loc_18005F12A
0x18005f0e2  test    dword ptr [rax+1Ch], 10000h
0x18005f0e9  jz      short loc_18005F12A
0x18005f0eb  mov     rax, [rdi]
0x18005f0ee  mov     rcx, rdi
0x18005f0f1  mov     rax, [rax+20h]
0x18005f0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f0fa  test    eax, eax
0x18005f0fc  lea     rcx, aUser; "user"
0x18005f103  lea     r9, aComputer_1; "computer"
0x18005f10a  mov     edx, 1Fh
0x18005f10f  cmovz   r9, rcx
0x18005f113  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005f11a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f121  mov     rcx, [rcx+10h]
0x18005f125  call    WPP_SF_S
0x18005f12a  mov     rax, [rdi]
0x18005f12d  mov     rcx, rdi
0x18005f130  mov     rax, [rax+20h]
0x18005f134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f139  mov     rcx, [rdi+58h]; hEvent
0x18005f13d  mov     edx, eax; bMachine
0x18005f13f  call    cs:__imp_RegisterGPNotification
0x18005f145  test    eax, eax
0x18005f147  jnz     short loc_18005F180
0x18005f149  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18005f14e  mov     ebx, eax
0x18005f150  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f157  cmp     rcx, rsi
0x18005f15a  jz      short loc_18005F17A
0x18005f15c  test    byte ptr [rcx+1Ch], 2
0x18005f160  jz      short loc_18005F17A
0x18005f162  mov     edx, 20h ; ' '
0x18005f167  mov     rcx, [rcx+10h]
0x18005f16b  lea     r8, WPP_9d3e204fa1593b4c7479993b85b659fe_Traceguids
0x18005f172  mov     r9d, eax
0x18005f175  call    WPP_SF_d
0x18005f17a  test    ebx, ebx
0x18005f17c  js      short loc_18005F18E
0x18005f17e  jmp     short loc_18005F187
0x18005f180  mov     dword ptr [rdi+60h], 1
0x18005f187  mov     rax, [rdi+58h]
0x18005f18b  mov     [r14], rax
0x18005f18e  mov     eax, ebx
0x18005f190  add     rsp, 28h
0x18005f194  pop     r14
0x18005f196  pop     rdi
0x18005f197  pop     rsi
0x18005f198  pop     rbx
0x18005f199  retn
```
