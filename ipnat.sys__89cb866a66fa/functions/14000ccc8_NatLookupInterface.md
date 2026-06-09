# NatLookupInterface

- ea: `0x14000ccc8`
- end: `0x14000cda5`
- name: `NatLookupInterface`
- size: `221`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: ``

## callers

- `0x14000bed0`
- `0x14000c49c`
- `0x14000c9b8`
- `0x14000cf88`
- `0x14000d318`
- `0x14000f2a4`
- `0x14001e1f0`
- `0x14001e4e4`
- `0x14001e874`
- `0x140024b18`
- `0x140024cc0`
- `0x14002597c`
- `0x14002633c`
- `0x14002665c`
- `0x1400273f8`
- `0x1400275d0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14000ccc8`

## pseudocode

```c
PVOID *__fastcall NatLookupInterface(unsigned int a1, PVOID **a2)
{
  PVOID *i; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x36u,
      (__int64)WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids,
      a1);
  }
  for ( i = (PVOID *)InterfaceList; ; i = (PVOID *)*i )
  {
    if ( i == &InterfaceList )
      goto LABEL_9;
    if ( *((_DWORD *)i + 8) <= a1 )
      break;
  }
  if ( *((_DWORD *)i + 8) < a1 )
  {
LABEL_9:
    if ( a2 )
      *a2 = i;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x38u,
        (__int64)WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x37u,
      (__int64)WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  return i;
}

```

## disassembly

```asm
0x14000ccc8  push    rbx
0x14000ccca  push    rsi
0x14000cccb  push    rdi
0x14000cccc  push    r15
0x14000ccce  sub     rsp, 28h
0x14000ccd2  mov     rsi, rdx
0x14000ccd5  mov     edi, ecx
0x14000ccd7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccde  lea     r15, WPP_GLOBAL_Control
0x14000cce5  cmp     rcx, r15
0x14000cce8  jz      short loc_14000CD0F
0x14000ccea  mov     eax, [rcx+2Ch]
0x14000cced  test    al, 1
0x14000ccef  jz      short loc_14000CD0F
0x14000ccf1  cmp     byte ptr [rcx+29h], 6
0x14000ccf5  jb      short loc_14000CD0F
0x14000ccf7  mov     rcx, [rcx+18h]
0x14000ccfb  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000cd02  mov     edx, 36h ; '6'
0x14000cd07  mov     r9d, edi
0x14000cd0a  call    WPP_SF_d
0x14000cd0f  mov     rbx, cs:InterfaceList
0x14000cd16  lea     rcx, InterfaceList
0x14000cd1d  jmp     short loc_14000CD27
0x14000cd1f  cmp     [rbx+20h], edi
0x14000cd22  jbe     short loc_14000CD6F
0x14000cd24  mov     rbx, [rbx]
0x14000cd27  cmp     rbx, rcx
0x14000cd2a  jnz     short loc_14000CD1F
0x14000cd2c  test    rsi, rsi
0x14000cd2f  jz      short loc_14000CD34
0x14000cd31  mov     [rsi], rbx
0x14000cd34  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd3b  cmp     rcx, r15
0x14000cd3e  jz      short loc_14000CD62
0x14000cd40  mov     eax, [rcx+2Ch]
0x14000cd43  test    al, 1
0x14000cd45  jz      short loc_14000CD62
0x14000cd47  cmp     byte ptr [rcx+29h], 6
0x14000cd4b  jb      short loc_14000CD62
0x14000cd4d  mov     rcx, [rcx+18h]
0x14000cd51  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000cd58  mov     edx, 38h ; '8'
0x14000cd5d  call    WPP_SF_
0x14000cd62  xor     eax, eax
0x14000cd64  add     rsp, 28h
0x14000cd68  pop     r15
0x14000cd6a  pop     rdi
0x14000cd6b  pop     rsi
0x14000cd6c  pop     rbx
0x14000cd6d  retn
0x14000cd6f  jb      short loc_14000CD2C
0x14000cd71  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd78  cmp     rcx, r15
0x14000cd7b  jz      short loc_14000CDA0
0x14000cd7d  mov     edx, [rcx+2Ch]
0x14000cd80  test    dl, 1
0x14000cd83  jz      short loc_14000CDA0
0x14000cd85  cmp     byte ptr [rcx+29h], 6
0x14000cd89  jb      short loc_14000CDA0
0x14000cd8b  mov     rcx, [rcx+18h]
0x14000cd8f  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000cd96  mov     edx, 37h ; '7'
0x14000cd9b  call    WPP_SF_
0x14000cda0  mov     rax, rbx
0x14000cda3  jmp     short loc_14000CD64
```
