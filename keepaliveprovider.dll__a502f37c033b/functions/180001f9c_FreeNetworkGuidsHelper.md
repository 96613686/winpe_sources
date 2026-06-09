# FreeNetworkGuidsHelper

- ea: `0x180001f9c`
- end: `0x18000201d`
- name: `FreeNetworkGuidsHelper`
- size: `129`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002cc0`
- `0x1800030a4`

## callees

- `0x180001e20`
- `0x180001f9c`
- `0x1800033a0`

## pseudocode

```c
__int64 __fastcall FreeNetworkGuidsHelper(LPVOID lpMem)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  result = UtillibFreeGuidListHelperTemplate(lpMem);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180001f9c  mov     [rsp+arg_0], rbx
0x180001fa1  push    rdi
0x180001fa2  sub     rsp, 20h
0x180001fa6  mov     rbx, rcx
0x180001fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fb0  lea     rdi, WPP_GLOBAL_Control
0x180001fb7  cmp     rcx, rdi
0x180001fba  jz      short loc_180001FDD
0x180001fbc  test    byte ptr [rcx+1Ch], 1
0x180001fc0  jz      short loc_180001FDD
0x180001fc2  cmp     byte ptr [rcx+19h], 6
0x180001fc6  jb      short loc_180001FDD
0x180001fc8  mov     rcx, [rcx+10h]
0x180001fcc  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180001fd3  mov     edx, 0Ch
0x180001fd8  call    WPP_SF_
0x180001fdd  mov     rcx, rbx; lpMem
0x180001fe0  call    UtillibFreeGuidListHelperTemplate
0x180001fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001fec  cmp     rcx, rdi
0x180001fef  jz      short loc_180002012
0x180001ff1  test    byte ptr [rcx+1Ch], 1
0x180001ff5  jz      short loc_180002012
0x180001ff7  cmp     byte ptr [rcx+19h], 6
0x180001ffb  jb      short loc_180002012
0x180001ffd  mov     rcx, [rcx+10h]
0x180002001  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002008  mov     edx, 0Dh
0x18000200d  call    WPP_SF_
0x180002012  mov     rbx, [rsp+28h+arg_0]
0x180002017  add     rsp, 20h
0x18000201b  pop     rdi
0x18000201c  retn
```
