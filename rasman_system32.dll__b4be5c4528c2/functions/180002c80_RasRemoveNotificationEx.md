# RasRemoveNotificationEx

- ea: `0x180002c80`
- end: `0x180002d4c`
- name: `RasRemoveNotificationEx`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002c80`
- `0x1800030d0`
- `0x180021b14`

## pseudocode

```c
__int64 __fastcall RasRemoveNotificationEx(unsigned int a1)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  PVOID *v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 694, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, a1);
  }
  result = SubmitLocalRequest(0x8Cu, a1);
  v3 = result;
  if ( !(_DWORD)result )
    goto LABEL_4;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      695,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      (unsigned int)result);
LABEL_4:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 696, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180002c80  mov     [rsp+arg_0], rbx
0x180002c85  push    rdi
0x180002c86  sub     rsp, 20h
0x180002c8a  mov     ebx, ecx
0x180002c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c93  lea     rdi, WPP_GLOBAL_Control
0x180002c9a  cmp     rcx, rdi
0x180002c9d  jz      short loc_180002CA5
0x180002c9f  test    byte ptr [rcx+1Ch], 40h
0x180002ca3  jnz     short loc_180002CF7
0x180002ca5  mov     ecx, 8Ch
0x180002caa  mov     edx, ebx
0x180002cac  call    SubmitLocalRequest
0x180002cb1  mov     ebx, eax
0x180002cb3  test    eax, eax
0x180002cb5  jnz     short loc_180002D17
0x180002cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cbe  cmp     rcx, rdi
0x180002cc1  jnz     short loc_180002CD1
0x180002cc3  mov     eax, ebx
0x180002cc5  mov     rbx, [rsp+28h+arg_0]
0x180002cca  add     rsp, 20h
0x180002cce  pop     rdi
0x180002ccf  retn
0x180002cd1  test    byte ptr [rcx+1Ch], 40h
0x180002cd5  jz      short loc_180002CC3
0x180002cd7  cmp     byte ptr [rcx+19h], 6
0x180002cdb  jb      short loc_180002CC3
0x180002cdd  mov     rcx, [rcx+10h]
0x180002ce1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002ce8  mov     edx, 2B8h
0x180002ced  mov     r9d, ebx
0x180002cf0  call    WPP_SF_d
0x180002cf5  jmp     short loc_180002CC3
0x180002cf7  cmp     byte ptr [rcx+19h], 6
0x180002cfb  jb      short loc_180002CA5
0x180002cfd  mov     rcx, [rcx+10h]
0x180002d01  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002d08  mov     edx, 2B6h
0x180002d0d  mov     r9d, ebx
0x180002d10  call    WPP_SF_d
0x180002d15  jmp     short loc_180002CA5
0x180002d17  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d1e  cmp     rcx, rdi
0x180002d21  jz      short loc_180002CC5
0x180002d23  test    byte ptr [rcx+1Ch], 40h
0x180002d27  jz      short loc_180002CBE
0x180002d29  cmp     byte ptr [rcx+19h], 2
0x180002d2d  jb      short loc_180002CBE
0x180002d2f  mov     rcx, [rcx+10h]
0x180002d33  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180002d3a  mov     edx, 2B7h
0x180002d3f  mov     r9d, ebx
0x180002d42  call    WPP_SF_d
0x180002d47  jmp     loc_180002CB7
```
