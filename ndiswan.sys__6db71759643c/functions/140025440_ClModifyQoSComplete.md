# ClModifyQoSComplete

- ea: `0x140025440`
- end: `0x1400254bf`
- name: `ClModifyQoSComplete`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a68c`
- `0x140025440`

## pseudocode

```c
__int64 __fastcall ClModifyQoSComplete(int a1, __int64 a2)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_qD(
                 WPP_GLOBAL_Control->AttachedDevice,
                 27,
                 WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
                 a2,
                 a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025440  push    rdi
0x140025442  sub     rsp, 30h
0x140025446  mov     r9, rdx
0x140025449  mov     r8d, ecx
0x14002544c  mov     rcx, cs:WPP_GLOBAL_Control
0x140025453  lea     rdi, WPP_GLOBAL_Control
0x14002545a  cmp     rcx, rdi
0x14002545d  jz      short loc_1400254B8
0x14002545f  test    dword ptr [rcx+2Ch], 8000h
0x140025466  jz      short loc_140025488
0x140025468  cmp     byte ptr [rcx+29h], 5
0x14002546c  jb      short loc_140025488
0x14002546e  mov     rcx, [rcx+18h]
0x140025472  mov     edx, 1Bh
0x140025477  mov     [rsp+38h+var_18], r8d
0x14002547c  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140025483  call    WPP_SF_qD
0x140025488  mov     rcx, cs:WPP_GLOBAL_Control
0x14002548f  cmp     rcx, rdi
0x140025492  jz      short loc_1400254B8
0x140025494  test    dword ptr [rcx+2Ch], 8000h
0x14002549b  jz      short loc_1400254B8
0x14002549d  cmp     byte ptr [rcx+29h], 5
0x1400254a1  jb      short loc_1400254B8
0x1400254a3  mov     rcx, [rcx+18h]
0x1400254a7  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400254ae  mov     edx, 1Ch
0x1400254b3  call    WPP_SF_
0x1400254b8  add     rsp, 30h
0x1400254bc  pop     rdi
0x1400254bd  retn
```
