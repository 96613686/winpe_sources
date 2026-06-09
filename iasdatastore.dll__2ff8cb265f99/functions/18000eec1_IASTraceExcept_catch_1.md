# IASTraceExcept$catch$1

- ea: `0x18000eec1`
- end: `0x18000ef51`
- name: `IASTraceExcept$catch$1`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001938`
- `0x18000cb14`
- `0x18000ce90`
- `0x18000d990`
- `0x18000eec1`

## string_xrefs

- `0x18000ef0d`: `Caught COM exception: %s`

## pseudocode

```c
__int64 __fastcall IASTraceExcept_catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // r8d
  int v5; // r9d

  v3 = IASFormatSysErr(*(_DWORD *)(*(_QWORD *)(a2 + 56) + 8LL), (char *)(a2 + 64));
  if ( (unsigned int)v3 >= 0x100 )
    _report_rangecheckfailure();
  *(_BYTE *)(a2 + v3 + 64) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WppDbgPrint("Caught COM exception: %s");
    WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v4, v5, a2 + 64);
  }
  return 0;
}

```

## disassembly

```asm
0x18000eec1  mov     [rsp+arg_8], rdx
0x18000eec6  push    rbp
0x18000eec7  sub     rsp, 30h
0x18000eecb  mov     rbp, rdx
0x18000eece  lea     rdx, [rbp+40h]; Buffer
0x18000eed2  mov     rcx, [rbp+38h]
0x18000eed6  mov     ecx, [rcx+8]; dwMessageId
0x18000eed9  call    IASFormatSysErr
0x18000eede  cmp     eax, 100h
0x18000eee3  jnb     short loc_18000EF44
0x18000eee5  mov     byte ptr [rbp+rax+40h], 0
0x18000eeea  lea     rcx, WPP_GLOBAL_Control
0x18000eef1  mov     rax, cs:WPP_GLOBAL_Control
0x18000eef8  cmp     rax, rcx
0x18000eefb  jz      short loc_18000EF38
0x18000eefd  cmp     byte ptr [rax+19h], 2
0x18000ef01  jb      short loc_18000EF38
0x18000ef03  test    byte ptr [rax+1Ch], 1
0x18000ef07  jz      short loc_18000EF38
0x18000ef09  lea     rdx, [rbp+40h]
0x18000ef0d  lea     rcx, aCaughtComExcep; "Caught COM exception: %s"
0x18000ef14  call    WppDbgPrint
0x18000ef19  mov     edx, 0Bh
0x18000ef1e  lea     rax, [rbp+40h]
0x18000ef22  mov     [rsp+38h+var_18], rax
0x18000ef27  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef2e  mov     rcx, [rcx+10h]
0x18000ef32  call    WPP_SF_ss
0x18000ef37  nop
0x18000ef38  mov     rax, 0
0x18000ef42  jmp     short loc_18000EF4A
0x18000ef44  call    __report_rangecheckfailure
0x18000ef4a  add     rsp, 30h
0x18000ef4e  pop     rbp
0x18000ef4f  retn
```
