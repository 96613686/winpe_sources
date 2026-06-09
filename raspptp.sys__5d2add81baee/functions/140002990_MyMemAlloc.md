# MyMemAlloc

- ea: `0x140002990`
- end: `0x140002a1c`
- name: `MyMemAlloc`
- size: `140`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400028f0`
- `0x140002b10`
- `0x14000360c`
- `0x140011920`
- `0x140013290`
- `0x14001a010`
- `0x14001ac10`

## callees

- `0x140002990`
- `0x140005190`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400029c7`
- `ntoskrnl!ExAllocatePool3` at `0x1400029c7`

## pseudocode

```c
__int64 __fastcall MyMemAlloc(unsigned int a1, unsigned int a2)
{
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF

  v7[1] = 16;
  v7[0] = 1;
  result = ExAllocatePool3(64, a1, a2, v7, 1);
  if ( !result )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, v5, v6, a1, a2);
    }
    result = 0;
    ++dword_14000B484;
  }
  return result;
}

```

## disassembly

```asm
0x140002990  mov     [rsp+arg_0], rbx
0x140002995  push    rdi
0x140002996  sub     rsp, 40h
0x14000299a  mov     ebx, edx
0x14000299c  mov     edi, ecx
0x14000299e  mov     edx, ecx
0x1400029a0  lea     r9, [rsp+48h+var_18]
0x1400029a5  mov     r8d, ebx
0x1400029a8  mov     [rsp+48h+var_10], 10h
0x1400029b1  mov     ecx, 40h ; '@'
0x1400029b6  mov     [rsp+48h+var_18], 1
0x1400029bf  mov     [rsp+48h+var_28], 1
0x1400029c7  call    cs:__imp_ExAllocatePool3
0x1400029ce  nop     dword ptr [rax+rax+00h]
0x1400029d3  test    rax, rax
0x1400029d6  jnz     short loc_140002A10
0x1400029d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029df  lea     rax, WPP_GLOBAL_Control
0x1400029e6  cmp     rcx, rax
0x1400029e9  jz      short loc_140002A08
0x1400029eb  mov     eax, [rcx+2Ch]
0x1400029ee  test    al, 1
0x1400029f0  jz      short loc_140002A08
0x1400029f2  cmp     byte ptr [rcx+29h], 1
0x1400029f6  jb      short loc_140002A08
0x1400029f8  mov     rcx, [rcx+18h]
0x1400029fc  mov     r9d, edi
0x1400029ff  mov     [rsp+48h+var_28], ebx
0x140002a03  call    WPP_SF_dD
0x140002a08  xor     eax, eax
0x140002a0a  inc     cs:dword_14000B484
0x140002a10  mov     rbx, [rsp+48h+arg_0]
0x140002a15  add     rsp, 40h
0x140002a19  pop     rdi
0x140002a1a  retn
```
