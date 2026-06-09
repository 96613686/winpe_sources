# CClipBase::CreateDataChannelEvents(void)

- ea: `0x14004f8ec`
- end: `0x14004f9d6`
- name: `?CreateDataChannelEvents@CClipBase@@AEAAJXZ`
- size: `234`
- prototype: `__int64 __fastcall(CClipBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140051830`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005704`
- `0x14004f8ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f9b0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004f992`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004f992`

## pseudocode

```c
signed int __fastcall CClipBase::CreateDataChannelEvents(CClipBase *this)
{
  PVOID *v2; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int i; // ebx
  unsigned int v5; // eax
  HANDLE EventW; // rax
  __int64 v7; // rcx
  signed int result; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
      return 0;
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v5, i);
    }
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
      break;
    v7 = i;
    *((_QWORD *)this + v7 + 13) = EventW;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x14004f8ec  mov     [rsp+arg_0], rbx
0x14004f8f1  mov     [rsp+arg_8], rsi
0x14004f8f6  push    rdi
0x14004f8f7  sub     rsp, 30h
0x14004f8fb  mov     rdi, rcx
0x14004f8fe  mov     rax, cs:WPP_GLOBAL_Control
0x14004f905  lea     rsi, WPP_GLOBAL_Control
0x14004f90c  cmp     rax, rsi
0x14004f90f  jz      short loc_14004F948
0x14004f911  test    byte ptr [rax+1Ch], 1
0x14004f915  jz      short loc_14004F948
0x14004f917  cmp     byte ptr [rax+19h], 5
0x14004f91b  jb      short loc_14004F948
0x14004f91d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004f922  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f929  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14004f930  mov     edx, 34h ; '4'
0x14004f935  mov     r9d, eax
0x14004f938  mov     rcx, [rcx+10h]
0x14004f93c  call    WPP_SF_d
0x14004f941  mov     rax, cs:WPP_GLOBAL_Control
0x14004f948  xor     ebx, ebx
0x14004f94a  cmp     ebx, 3
0x14004f94d  jge     short loc_14004F9C4
0x14004f94f  cmp     rax, rsi
0x14004f952  jz      short loc_14004F988
0x14004f954  test    byte ptr [rax+1Ch], 1
0x14004f958  jz      short loc_14004F988
0x14004f95a  cmp     byte ptr [rax+19h], 5
0x14004f95e  jb      short loc_14004F988
0x14004f960  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004f965  mov     rcx, cs:WPP_GLOBAL_Control
0x14004f96c  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14004f973  mov     edx, 35h ; '5'
0x14004f978  mov     [rsp+38h+var_18], ebx
0x14004f97c  mov     r9d, eax
0x14004f97f  mov     rcx, [rcx+10h]
0x14004f983  call    WPP_SF_Dd
0x14004f988  xor     r9d, r9d; lpName
0x14004f98b  xor     r8d, r8d; bInitialState
0x14004f98e  xor     edx, edx; bManualReset
0x14004f990  xor     ecx, ecx; lpEventAttributes
0x14004f992  call    cs:__imp_CreateEventW
0x14004f998  test    rax, rax
0x14004f99b  jz      short loc_14004F9B0
0x14004f99d  movsxd  rcx, ebx
0x14004f9a0  inc     ebx
0x14004f9a2  mov     [rdi+rcx*8+68h], rax
0x14004f9a7  mov     rax, cs:WPP_GLOBAL_Control
0x14004f9ae  jmp     short loc_14004F94A
0x14004f9b0  call    cs:__imp_GetLastError
0x14004f9b6  test    eax, eax
0x14004f9b8  jle     short loc_14004F9C6
0x14004f9ba  movzx   eax, ax
0x14004f9bd  or      eax, 80070000h
0x14004f9c2  jmp     short loc_14004F9C6
0x14004f9c4  xor     eax, eax
0x14004f9c6  mov     rbx, [rsp+38h+arg_0]
0x14004f9cb  mov     rsi, [rsp+38h+arg_8]
0x14004f9d0  add     rsp, 30h
0x14004f9d4  pop     rdi
0x14004f9d5  retn
```
