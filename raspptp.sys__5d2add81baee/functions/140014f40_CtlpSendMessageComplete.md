# CtlpSendMessageComplete

- ea: `0x140014f40`
- end: `0x140014fcf`
- name: `CtlpSendMessageComplete`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140003e38`
- `0x140007710`
- `0x140011c00`
- `0x140012cf4`
- `0x1400131e4`
- `0x140014f40`

## pseudocode

```c
__int64 __fastcall CtlpSendMessageComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, unsigned int a6)
{
  __int64 result; // rax

  _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
  CtlFreePacket(a1, a5);
  if ( a6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, a6);
    }
    CtlSetState(a1, 7);
    CtlCleanup(a1, 0);
  }
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return (*(__int64 (__fastcall **)(__int64))(a1 + 24))(a1);
  return result;
}

```

## disassembly

```asm
0x140014f40  push    rbx
0x140014f42  sub     rsp, 20h
0x140014f46  mov     rbx, rcx
0x140014f49  lock inc dword ptr [rcx+10h]
0x140014f4d  mov     rdx, [rsp+28h+arg_20]
0x140014f52  call    CtlFreePacket
0x140014f57  mov     r9d, [rsp+28h+arg_28]
0x140014f5c  test    r9d, r9d
0x140014f5f  jz      short loc_140014FAF
0x140014f61  mov     rcx, cs:WPP_GLOBAL_Control
0x140014f68  lea     rax, WPP_GLOBAL_Control
0x140014f6f  cmp     rcx, rax
0x140014f72  jz      short loc_140014F96
0x140014f74  mov     eax, [rcx+2Ch]
0x140014f77  test    al, 8
0x140014f79  jz      short loc_140014F96
0x140014f7b  cmp     byte ptr [rcx+29h], 1
0x140014f7f  jb      short loc_140014F96
0x140014f81  mov     rcx, [rcx+18h]
0x140014f85  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140014f8c  mov     edx, 53h ; 'S'
0x140014f91  call    WPP_SF_d
0x140014f96  xor     r9d, r9d
0x140014f99  mov     rcx, rbx
0x140014f9c  lea     edx, [r9+7]
0x140014fa0  call    CtlSetState
0x140014fa5  xor     edx, edx
0x140014fa7  mov     rcx, rbx
0x140014faa  call    CtlCleanup
0x140014faf  or      eax, 0FFFFFFFFh
0x140014fb2  lock xadd [rbx+10h], eax
0x140014fb7  cmp     eax, 1
0x140014fba  jnz     short loc_140014FC8
0x140014fbc  mov     rax, [rbx+18h]
0x140014fc0  mov     rcx, rbx
0x140014fc3  call    _guard_dispatch_icall
0x140014fc8  add     rsp, 20h
0x140014fcc  pop     rbx
0x140014fcd  retn
```
