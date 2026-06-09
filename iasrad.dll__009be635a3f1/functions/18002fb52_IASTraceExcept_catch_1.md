# IASTraceExcept$catch$1

- ea: `0x18002fb52`
- end: `0x18002fbe2`
- name: `IASTraceExcept$catch$1`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001fc8`
- `0x18001d31c`
- `0x18002c9d8`
- `0x18002cd60`
- `0x18002fb52`

## string_xrefs

- `0x18002fb9e`: `Caught COM exception: %s`

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
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
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
0x18002fb52  mov     [rsp+arg_8], rdx
0x18002fb57  push    rbp
0x18002fb58  sub     rsp, 30h
0x18002fb5c  mov     rbp, rdx
0x18002fb5f  lea     rdx, [rbp+40h]; Buffer
0x18002fb63  mov     rcx, [rbp+38h]
0x18002fb67  mov     ecx, [rcx+8]; dwMessageId
0x18002fb6a  call    IASFormatSysErr
0x18002fb6f  cmp     eax, 100h
0x18002fb74  jnb     short loc_18002FBD5
0x18002fb76  mov     byte ptr [rbp+rax+40h], 0
0x18002fb7b  lea     rcx, WPP_GLOBAL_Control
0x18002fb82  mov     rax, cs:WPP_GLOBAL_Control
0x18002fb89  cmp     rax, rcx
0x18002fb8c  jz      short loc_18002FBC9
0x18002fb8e  cmp     byte ptr [rax+19h], 2
0x18002fb92  jb      short loc_18002FBC9
0x18002fb94  test    byte ptr [rax+1Ch], 1
0x18002fb98  jz      short loc_18002FBC9
0x18002fb9a  lea     rdx, [rbp+40h]
0x18002fb9e  lea     rcx, aCaughtComExcep; "Caught COM exception: %s"
0x18002fba5  call    WppDbgPrint
0x18002fbaa  mov     edx, 0Bh
0x18002fbaf  lea     rax, [rbp+40h]
0x18002fbb3  mov     [rsp+38h+var_18], rax
0x18002fbb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbbf  mov     rcx, [rcx+10h]
0x18002fbc3  call    WPP_SF_ss
0x18002fbc8  nop
0x18002fbc9  mov     rax, 0
0x18002fbd3  jmp     short loc_18002FBDB
0x18002fbd5  call    __report_rangecheckfailure
0x18002fbdb  add     rsp, 30h
0x18002fbdf  pop     rbp
0x18002fbe0  retn
```
