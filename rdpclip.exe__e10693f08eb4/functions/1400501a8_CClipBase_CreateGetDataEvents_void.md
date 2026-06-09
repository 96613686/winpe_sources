# CClipBase::CreateGetDataEvents(void)

- ea: `0x1400501a8`
- end: `0x140050292`
- name: `?CreateGetDataEvents@CClipBase@@AEAAJXZ`
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
- `0x1400501a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005026c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005026c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005024e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14005024e`

## pseudocode

```c
signed int __fastcall CClipBase::CreateGetDataEvents(CClipBase *this)
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
      50,
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
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids, v5, i);
    }
    EventW = CreateEventW(0, 0, 0, 0);
    if ( !EventW )
      break;
    v7 = i;
    *((_QWORD *)this + v7 + 10) = EventW;
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
0x1400501a8  mov     [rsp+arg_0], rbx
0x1400501ad  mov     [rsp+arg_8], rsi
0x1400501b2  push    rdi
0x1400501b3  sub     rsp, 30h
0x1400501b7  mov     rdi, rcx
0x1400501ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400501c1  lea     rsi, WPP_GLOBAL_Control
0x1400501c8  cmp     rax, rsi
0x1400501cb  jz      short loc_140050204
0x1400501cd  test    byte ptr [rax+1Ch], 1
0x1400501d1  jz      short loc_140050204
0x1400501d3  cmp     byte ptr [rax+19h], 5
0x1400501d7  jb      short loc_140050204
0x1400501d9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400501de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400501e5  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400501ec  mov     edx, 32h ; '2'
0x1400501f1  mov     r9d, eax
0x1400501f4  mov     rcx, [rcx+10h]
0x1400501f8  call    WPP_SF_d
0x1400501fd  mov     rax, cs:WPP_GLOBAL_Control
0x140050204  xor     ebx, ebx
0x140050206  cmp     ebx, 3
0x140050209  jge     short loc_140050280
0x14005020b  cmp     rax, rsi
0x14005020e  jz      short loc_140050244
0x140050210  test    byte ptr [rax+1Ch], 1
0x140050214  jz      short loc_140050244
0x140050216  cmp     byte ptr [rax+19h], 5
0x14005021a  jb      short loc_140050244
0x14005021c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140050221  mov     rcx, cs:WPP_GLOBAL_Control
0x140050228  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x14005022f  mov     edx, 33h ; '3'
0x140050234  mov     [rsp+38h+var_18], ebx
0x140050238  mov     r9d, eax
0x14005023b  mov     rcx, [rcx+10h]
0x14005023f  call    WPP_SF_Dd
0x140050244  xor     r9d, r9d; lpName
0x140050247  xor     r8d, r8d; bInitialState
0x14005024a  xor     edx, edx; bManualReset
0x14005024c  xor     ecx, ecx; lpEventAttributes
0x14005024e  call    cs:__imp_CreateEventW
0x140050254  test    rax, rax
0x140050257  jz      short loc_14005026C
0x140050259  movsxd  rcx, ebx
0x14005025c  inc     ebx
0x14005025e  mov     [rdi+rcx*8+50h], rax
0x140050263  mov     rax, cs:WPP_GLOBAL_Control
0x14005026a  jmp     short loc_140050206
0x14005026c  call    cs:__imp_GetLastError
0x140050272  test    eax, eax
0x140050274  jle     short loc_140050282
0x140050276  movzx   eax, ax
0x140050279  or      eax, 80070000h
0x14005027e  jmp     short loc_140050282
0x140050280  xor     eax, eax
0x140050282  mov     rbx, [rsp+38h+arg_0]
0x140050287  mov     rsi, [rsp+38h+arg_8]
0x14005028c  add     rsp, 30h
0x140050290  pop     rdi
0x140050291  retn
```
