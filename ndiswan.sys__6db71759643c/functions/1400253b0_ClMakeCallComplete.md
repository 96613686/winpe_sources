# ClMakeCallComplete

- ea: `0x1400253b0`
- end: `0x14002542f`
- name: `ClMakeCallComplete`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000a290`
- `0x14000a68c`
- `0x1400253b0`

## pseudocode

```c
__int64 __fastcall ClMakeCallComplete(int a1, __int64 a2)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_qD(
                 WPP_GLOBAL_Control->AttachedDevice,
                 25,
                 WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
                 a2,
                 a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400253b0  push    rdi
0x1400253b2  sub     rsp, 30h
0x1400253b6  mov     r9, rdx
0x1400253b9  mov     r8d, ecx
0x1400253bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253c3  lea     rdi, WPP_GLOBAL_Control
0x1400253ca  cmp     rcx, rdi
0x1400253cd  jz      short loc_140025428
0x1400253cf  test    dword ptr [rcx+2Ch], 8000h
0x1400253d6  jz      short loc_1400253F8
0x1400253d8  cmp     byte ptr [rcx+29h], 5
0x1400253dc  jb      short loc_1400253F8
0x1400253de  mov     rcx, [rcx+18h]
0x1400253e2  mov     edx, 19h
0x1400253e7  mov     [rsp+38h+var_18], r8d
0x1400253ec  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x1400253f3  call    WPP_SF_qD
0x1400253f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253ff  cmp     rcx, rdi
0x140025402  jz      short loc_140025428
0x140025404  test    dword ptr [rcx+2Ch], 8000h
0x14002540b  jz      short loc_140025428
0x14002540d  cmp     byte ptr [rcx+29h], 5
0x140025411  jb      short loc_140025428
0x140025413  mov     rcx, [rcx+18h]
0x140025417  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14002541e  mov     edx, 1Ah
0x140025423  call    WPP_SF_
0x140025428  add     rsp, 30h
0x14002542c  pop     rdi
0x14002542d  retn
```
