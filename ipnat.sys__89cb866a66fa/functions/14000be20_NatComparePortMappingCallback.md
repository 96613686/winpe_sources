# NatComparePortMappingCallback

- ea: `0x14000be20`
- end: `0x14000bec8`
- name: `NatComparePortMappingCallback`
- size: `168`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000be20`

## pseudocode

```c
_BOOL8 __fastcall NatComparePortMappingCallback(__int64 a1, __int64 a2)
{
  BOOL v4; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v4 = *(_BYTE *)a1 != *(_BYTE *)a2 || *(_WORD *)(a1 + 2) != *(_WORD *)(a2 + 2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14000be20  mov     [rsp+arg_0], rbx
0x14000be25  mov     [rsp+arg_8], rsi
0x14000be2a  push    rdi
0x14000be2b  sub     rsp, 20h
0x14000be2f  mov     rbx, rdx
0x14000be32  mov     rdi, rcx
0x14000be35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be3c  lea     rsi, WPP_GLOBAL_Control
0x14000be43  cmp     rcx, rsi
0x14000be46  jz      short loc_14000BE6A
0x14000be48  mov     eax, [rcx+2Ch]
0x14000be4b  test    al, 1
0x14000be4d  jz      short loc_14000BE6A
0x14000be4f  cmp     byte ptr [rcx+29h], 6
0x14000be53  jb      short loc_14000BE6A
0x14000be55  mov     rcx, [rcx+18h]
0x14000be59  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000be60  mov     edx, 0Eh
0x14000be65  call    WPP_SF_
0x14000be6a  mov     cl, [rdi]
0x14000be6c  cmp     cl, [rbx]
0x14000be6e  jnz     short loc_14000BE7E
0x14000be70  movzx   ecx, word ptr [rdi+2]
0x14000be74  cmp     cx, [rbx+2]
0x14000be78  jnz     short loc_14000BE7E
0x14000be7a  xor     ebx, ebx
0x14000be7c  jmp     short loc_14000BE83
0x14000be7e  mov     ebx, 1
0x14000be83  mov     rcx, cs:WPP_GLOBAL_Control
0x14000be8a  cmp     rcx, rsi
0x14000be8d  jz      short loc_14000BEB5
0x14000be8f  mov     edx, [rcx+2Ch]
0x14000be92  test    dl, 1
0x14000be95  jz      short loc_14000BEB5
0x14000be97  cmp     byte ptr [rcx+29h], 6
0x14000be9b  jb      short loc_14000BEB5
0x14000be9d  mov     rcx, [rcx+18h]
0x14000bea1  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000bea8  mov     edx, 0Fh
0x14000bead  mov     r9d, ebx
0x14000beb0  call    WPP_SF_d
0x14000beb5  mov     rsi, [rsp+28h+arg_8]
0x14000beba  mov     eax, ebx
0x14000bebc  mov     rbx, [rsp+28h+arg_0]
0x14000bec1  add     rsp, 20h
0x14000bec5  pop     rdi
0x14000bec6  retn
```
