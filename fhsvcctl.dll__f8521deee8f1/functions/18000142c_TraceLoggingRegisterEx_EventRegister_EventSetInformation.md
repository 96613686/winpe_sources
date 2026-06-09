# TraceLoggingRegisterEx_EventRegister_EventSetInformation

- ea: `0x18000142c`
- end: `0x1800014d4`
- name: `TraceLoggingRegisterEx_EventRegister_EventSetInformation`
- size: `168`
- prototype: `__int64 __fastcall(ULONGLONG *CallbackContext, ULONGLONG, ULONGLONG)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004998`

## callees

- `0x18000142c`
- `0x180004f20`

## import_xrefs

- `ADVAPI32!EventRegister` at `0x180001486`
- `ADVAPI32!EventRegister` at `0x180001486`
- `ADVAPI32!EventSetInformation` at `0x1800014af`
- `ADVAPI32!EventSetInformation` at `0x1800014af`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegisterEx_EventRegister_EventSetInformation(
        ULONGLONG *CallbackContext,
        ULONGLONG a2,
        ULONGLONG a3)
{
  ULONGLONG *v3; // rsi
  bool v4; // zf
  signed int v6; // eax
  unsigned int v7; // ebx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  v3 = CallbackContext + 4;
  v4 = CallbackContext[4] == 0;
  ProviderId = *(GUID *)(CallbackContext[1] - 16);
  if ( !v4 )
    __fastfail(5u);
  CallbackContext[5] = a2;
  CallbackContext[6] = a3;
  v6 = EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, CallbackContext, v3);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    EventSetInformation(
      *v3,
      2,
      CallbackContext[1],
      *(unsigned __int16 *)CallbackContext[1],
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  }
  return v7;
}

```

## disassembly

```asm
0x18000142c  mov     [rsp+arg_8], rbx
0x180001431  mov     [rsp+arg_10], rsi
0x180001436  push    rdi
0x180001437  sub     rsp, 40h
0x18000143b  mov     rax, cs:__security_cookie
0x180001442  xor     rax, rsp
0x180001445  mov     [rsp+48h+var_18], rax
0x18000144a  mov     rax, [rcx+8]
0x18000144e  lea     rsi, [rcx+20h]
0x180001452  cmp     qword ptr [rsi], 0
0x180001456  mov     rdi, rcx
0x180001459  movups  xmm0, xmmword ptr [rax-10h]
0x18000145d  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180001463  jz      short loc_18000146C
0x180001465  mov     ecx, 5
0x18000146a  int     29h; Win8: RtlFailFast(ecx)
0x18000146c  mov     [rdi+28h], rdx
0x180001470  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x180001475  mov     [rdi+30h], r8
0x180001479  lea     rdx, _tlgEnableCallback; EnableCallback
0x180001480  mov     r8, rdi; CallbackContext
0x180001483  mov     r9, rsi; RegHandle
0x180001486  call    cs:__imp_EventRegister
0x18000148c  mov     ebx, eax
0x18000148e  test    eax, eax
0x180001490  jz      short loc_18000149F
0x180001492  jle     short loc_1800014B5
0x180001494  movzx   ebx, ax
0x180001497  or      ebx, 80070000h
0x18000149d  jmp     short loc_1800014B5
0x18000149f  mov     r8, [rdi+8]
0x1800014a3  mov     edx, 2
0x1800014a8  mov     rcx, [rsi]
0x1800014ab  movzx   r9d, word ptr [r8]
0x1800014af  call    cs:__imp_EventSetInformation
0x1800014b5  mov     eax, ebx
0x1800014b7  mov     rcx, [rsp+48h+var_18]
0x1800014bc  xor     rcx, rsp; StackCookie
0x1800014bf  call    __security_check_cookie
0x1800014c4  mov     rbx, [rsp+48h+arg_8]
0x1800014c9  mov     rsi, [rsp+48h+arg_10]
0x1800014ce  add     rsp, 40h
0x1800014d2  pop     rdi
0x1800014d3  retn
```
