# ClCloseCallComplete

- ea: `0x140024fe0`
- end: `0x14002505f`
- name: `ClCloseCallComplete`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140025070`
- `0x140035960`

## callees

- `0x14000a290`
- `0x14000a68c`
- `0x140024fe0`

## pseudocode

```c
__int64 __fastcall ClCloseCallComplete(int a1, __int64 a2)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      result = WPP_SF_qD(
                 WPP_GLOBAL_Control->AttachedDevice,
                 29,
                 WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids,
                 a2,
                 a1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140024fe0  push    rdi
0x140024fe2  sub     rsp, 30h
0x140024fe6  mov     r9, rdx
0x140024fe9  mov     r8d, ecx
0x140024fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ff3  lea     rdi, WPP_GLOBAL_Control
0x140024ffa  cmp     rcx, rdi
0x140024ffd  jz      short loc_140025058
0x140024fff  test    dword ptr [rcx+2Ch], 8000h
0x140025006  jz      short loc_140025028
0x140025008  cmp     byte ptr [rcx+29h], 5
0x14002500c  jb      short loc_140025028
0x14002500e  mov     rcx, [rcx+18h]
0x140025012  mov     edx, 1Dh
0x140025017  mov     [rsp+38h+var_18], r8d
0x14002501c  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x140025023  call    WPP_SF_qD
0x140025028  mov     rcx, cs:WPP_GLOBAL_Control
0x14002502f  cmp     rcx, rdi
0x140025032  jz      short loc_140025058
0x140025034  test    dword ptr [rcx+2Ch], 8000h
0x14002503b  jz      short loc_140025058
0x14002503d  cmp     byte ptr [rcx+29h], 5
0x140025041  jb      short loc_140025058
0x140025043  mov     rcx, [rcx+18h]
0x140025047  lea     r8, WPP_c89acbadcb8439ee76877fe7e056e074_Traceguids
0x14002504e  mov     edx, 1Eh
0x140025053  call    WPP_SF_
0x140025058  add     rsp, 30h
0x14002505c  pop     rdi
0x14002505d  retn
```
