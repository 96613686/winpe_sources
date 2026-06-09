# CmActivateVcComplete

- ea: `0x140025720`
- end: `0x140025794`
- name: `CmActivateVcComplete`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x140025720`

## pseudocode

```c
__int64 CmActivateVcComplete()
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025720  push    rdi
0x140025722  sub     rsp, 20h
0x140025726  mov     rcx, cs:WPP_GLOBAL_Control
0x14002572d  lea     rdi, WPP_GLOBAL_Control
0x140025734  cmp     rcx, rdi
0x140025737  jz      short loc_14002578D
0x140025739  test    dword ptr [rcx+2Ch], 10000h
0x140025740  jz      short loc_14002575D
0x140025742  cmp     byte ptr [rcx+29h], 5
0x140025746  jb      short loc_14002575D
0x140025748  mov     rcx, [rcx+18h]
0x14002574c  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025753  mov     edx, 24h ; '$'
0x140025758  call    WPP_SF_
0x14002575d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025764  cmp     rcx, rdi
0x140025767  jz      short loc_14002578D
0x140025769  test    dword ptr [rcx+2Ch], 10000h
0x140025770  jz      short loc_14002578D
0x140025772  cmp     byte ptr [rcx+29h], 5
0x140025776  jb      short loc_14002578D
0x140025778  mov     rcx, [rcx+18h]
0x14002577c  lea     r8, WPP_4ebfda6e9b79317fa8839af4807e9648_Traceguids
0x140025783  mov     edx, 25h ; '%'
0x140025788  call    WPP_SF_
0x14002578d  add     rsp, 20h
0x140025791  pop     rdi
0x140025792  retn
```
