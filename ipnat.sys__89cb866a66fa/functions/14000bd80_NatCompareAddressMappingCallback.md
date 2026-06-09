# NatCompareAddressMappingCallback

- ea: `0x14000bd80`
- end: `0x14000be15`
- name: `NatCompareAddressMappingCallback`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000bd80`

## pseudocode

```c
__int64 __fastcall NatCompareAddressMappingCallback(_DWORD *a1, _DWORD *a2)
{
  unsigned int v4; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v4 = *a1 - *a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14000bd80  mov     [rsp+arg_0], rbx
0x14000bd85  mov     [rsp+arg_8], rsi
0x14000bd8a  push    rdi
0x14000bd8b  sub     rsp, 20h
0x14000bd8f  mov     rbx, rdx
0x14000bd92  mov     rdi, rcx
0x14000bd95  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd9c  lea     rsi, WPP_GLOBAL_Control
0x14000bda3  cmp     rcx, rsi
0x14000bda6  jz      short loc_14000BDCA
0x14000bda8  mov     eax, [rcx+2Ch]
0x14000bdab  test    al, 1
0x14000bdad  jz      short loc_14000BDCA
0x14000bdaf  cmp     byte ptr [rcx+29h], 6
0x14000bdb3  jb      short loc_14000BDCA
0x14000bdb5  mov     rcx, [rcx+18h]
0x14000bdb9  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000bdc0  mov     edx, 0Ch
0x14000bdc5  call    WPP_SF_
0x14000bdca  mov     eax, [rbx]
0x14000bdcc  mov     ebx, [rdi]
0x14000bdce  sub     ebx, eax
0x14000bdd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bdd7  cmp     rcx, rsi
0x14000bdda  jz      short loc_14000BE02
0x14000bddc  mov     edx, [rcx+2Ch]
0x14000bddf  test    dl, 1
0x14000bde2  jz      short loc_14000BE02
0x14000bde4  cmp     byte ptr [rcx+29h], 6
0x14000bde8  jb      short loc_14000BE02
0x14000bdea  mov     rcx, [rcx+18h]
0x14000bdee  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000bdf5  mov     edx, 0Dh
0x14000bdfa  mov     r9d, ebx
0x14000bdfd  call    WPP_SF_d
0x14000be02  mov     rsi, [rsp+28h+arg_8]
0x14000be07  mov     eax, ebx
0x14000be09  mov     rbx, [rsp+28h+arg_0]
0x14000be0e  add     rsp, 20h
0x14000be12  pop     rdi
0x14000be13  retn
```
