# MdaComputeNewBufferingState

- ea: `0x14001def0`
- end: `0x14001df68`
- name: `MdaComputeNewBufferingState`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400159cc`
- `0x14001def0`

## pseudocode

```c
__int64 __fastcall MdaComputeNewBufferingState(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
  *a4 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14001def0  mov     [rsp+arg_0], rbx
0x14001def5  push    rdi
0x14001def6  sub     rsp, 20h
0x14001defa  mov     rbx, r9
0x14001defd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df04  lea     rdi, WPP_GLOBAL_Control
0x14001df0b  cmp     rcx, rdi
0x14001df0e  jz      short loc_14001DF2C
0x14001df10  mov     eax, [rcx+2Ch]
0x14001df13  test    al, 8
0x14001df15  jz      short loc_14001DF2C
0x14001df17  mov     rcx, [rcx+18h]
0x14001df1b  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001df22  mov     edx, 22h ; '"'
0x14001df27  call    WPP_SF_
0x14001df2c  mov     dword ptr [rbx], 0
0x14001df32  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df39  cmp     rcx, rdi
0x14001df3c  jz      short loc_14001DF5A
0x14001df3e  mov     eax, [rcx+2Ch]
0x14001df41  test    al, 8
0x14001df43  jz      short loc_14001DF5A
0x14001df45  mov     rcx, [rcx+18h]
0x14001df49  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001df50  mov     edx, 23h ; '#'
0x14001df55  call    WPP_SF_
0x14001df5a  mov     rbx, [rsp+28h+arg_0]
0x14001df5f  xor     eax, eax
0x14001df61  add     rsp, 20h
0x14001df65  pop     rdi
0x14001df66  retn
```
