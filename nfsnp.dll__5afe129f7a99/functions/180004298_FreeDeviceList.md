# FreeDeviceList

- ea: `0x180004298`
- end: `0x18000433f`
- name: `FreeDeviceList`
- size: `167`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004348`
- `0x18000a61c`

## callees

- `0x180002508`
- `0x180004298`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800042ef`
- `KERNEL32!GlobalFree` at `0x1800042ef`

## pseudocode

```c
_QWORD *__fastcall FreeDeviceList(__int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *result; // rax
  _QWORD *v4; // rbx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  result = *(_QWORD **)(a1 + 72);
  if ( result )
  {
    do
    {
      v4 = (_QWORD *)result[2];
      GlobalFree(result);
      *(_QWORD *)(a1 + 72) = v4;
      result = v4;
    }
    while ( v4 );
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    return (_QWORD *)WPP_SF_(v2[2], 17, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180004298  mov     [rsp+arg_0], rbx
0x18000429d  mov     [rsp+arg_8], rsi
0x1800042a2  push    rdi
0x1800042a3  sub     rsp, 20h
0x1800042a7  mov     rdi, rcx
0x1800042aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042b1  lea     rsi, WPP_GLOBAL_Control
0x1800042b8  cmp     rcx, rsi
0x1800042bb  jz      short loc_1800042DF
0x1800042bd  test    byte ptr [rcx+1Ch], 1
0x1800042c1  jz      short loc_1800042DF
0x1800042c3  mov     rcx, [rcx+10h]
0x1800042c7  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800042ce  mov     edx, 10h
0x1800042d3  call    WPP_SF_
0x1800042d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800042df  mov     rax, [rdi+48h]
0x1800042e3  test    rax, rax
0x1800042e6  jz      short loc_18000430E
0x1800042e8  mov     rbx, [rax+10h]
0x1800042ec  mov     rcx, rax; hMem
0x1800042ef  call    cs:__imp_GlobalFree
0x1800042f6  nop     dword ptr [rax+rax+00h]
0x1800042fb  mov     [rdi+48h], rbx
0x1800042ff  mov     rax, rbx
0x180004302  test    rbx, rbx
0x180004305  jnz     short loc_1800042E8
0x180004307  mov     rcx, cs:WPP_GLOBAL_Control
0x18000430e  cmp     rcx, rsi
0x180004311  jz      short loc_18000432E
0x180004313  test    byte ptr [rcx+1Ch], 1
0x180004317  jz      short loc_18000432E
0x180004319  mov     rcx, [rcx+10h]
0x18000431d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180004324  mov     edx, 11h
0x180004329  call    WPP_SF_
0x18000432e  mov     rbx, [rsp+28h+arg_0]
0x180004333  mov     rsi, [rsp+28h+arg_8]
0x180004338  add     rsp, 20h
0x18000433c  pop     rdi
0x18000433d  retn
```
