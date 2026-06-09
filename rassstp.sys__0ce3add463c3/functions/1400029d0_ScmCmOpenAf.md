# ScmCmOpenAf

- ea: `0x1400029d0`
- end: `0x140002a57`
- name: `ScmCmOpenAf`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400029d0`
- `0x140002bd8`

## pseudocode

```c
__int64 __fastcall ScmCmOpenAf(__int64 a1, __int64 a2, __int64 a3)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  *((_QWORD *)SstpGlobals + 6) = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x81) == 0x81 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400029d0  mov     [rsp+arg_0], rbx
0x1400029d5  push    rdi
0x1400029d6  sub     rsp, 20h
0x1400029da  mov     rbx, r8
0x1400029dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029e4  lea     rdi, WPP_GLOBAL_Control
0x1400029eb  cmp     rcx, rdi
0x1400029ee  jz      short loc_140002A11
0x1400029f0  mov     eax, [rcx+2Ch]
0x1400029f3  and     eax, 81h
0x1400029f8  cmp     al, 81h
0x1400029fa  jnz     short loc_140002A11
0x1400029fc  mov     rcx, [rcx+18h]
0x140002a00  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140002a07  mov     edx, 13h
0x140002a0c  call    WPP_SF_
0x140002a11  mov     rax, cs:SstpGlobals
0x140002a18  mov     [rax+30h], rbx
0x140002a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a23  cmp     rcx, rdi
0x140002a26  jz      short loc_140002A49
0x140002a28  mov     eax, [rcx+2Ch]
0x140002a2b  and     eax, 81h
0x140002a30  cmp     al, 81h
0x140002a32  jnz     short loc_140002A49
0x140002a34  mov     rcx, [rcx+18h]
0x140002a38  lea     r8, WPP_f061e284a7f133f0e4904ed0310bea13_Traceguids
0x140002a3f  mov     edx, 14h
0x140002a44  call    WPP_SF_
0x140002a49  mov     rbx, [rsp+28h+arg_0]
0x140002a4e  xor     eax, eax
0x140002a50  add     rsp, 20h
0x140002a54  pop     rdi
0x140002a55  retn
```
