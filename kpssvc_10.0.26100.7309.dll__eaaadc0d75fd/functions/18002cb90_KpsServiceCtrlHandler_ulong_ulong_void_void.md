# KpsServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18002cb90`
- end: `0x18002cc33`
- name: `?KpsServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `163`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18001ae38`
- `0x18002cb90`
- `0x18002d938`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cbed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002cbed`

## pseudocode

```c
__int64 __fastcall KpsServiceCtrlHandler(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  _QWORD *v5; // rcx
  unsigned int v6; // ebx

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_DDqq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      dwEventType,
      lpEventData,
      dwControl,
      dwEventType,
      lpEventData,
      lpContext);
    v5 = WPP_GLOBAL_Control;
  }
  if ( ((dwControl - 1) & 0xFFFFFFFB) != 0 )
  {
    v6 = 120;
  }
  else
  {
    SetEvent(qword_18003AD30);
    v5 = WPP_GLOBAL_Control;
    v6 = 0;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_D(v5[2], 13, &WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18002cb90  mov     rax, rsp
0x18002cb93  mov     [rax+8], rbx
0x18002cb97  push    rdi
0x18002cb98  sub     rsp, 40h
0x18002cb9c  mov     ebx, ecx
0x18002cb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cba5  lea     rdi, WPP_GLOBAL_Control
0x18002cbac  cmp     rcx, rdi
0x18002cbaf  jz      short loc_18002CBD5
0x18002cbb1  test    byte ptr [rcx+1Ch], 20h
0x18002cbb5  jz      short loc_18002CBD5
0x18002cbb7  mov     rcx, [rcx+10h]
0x18002cbbb  mov     [rax-18h], r9
0x18002cbbf  mov     r9d, ebx
0x18002cbc2  mov     [rax-20h], r8
0x18002cbc6  mov     [rax-28h], edx
0x18002cbc9  call    WPP_SF_DDqq
0x18002cbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbd5  lea     eax, [rbx-1]
0x18002cbd8  test    eax, 0FFFFFFFBh
0x18002cbdd  jz      short loc_18002CBE6
0x18002cbdf  mov     ebx, 78h ; 'x'
0x18002cbe4  jmp     short loc_18002CC02
0x18002cbe6  mov     rcx, cs:qword_18003AD30; hEvent
0x18002cbed  call    cs:__imp_SetEvent
0x18002cbf4  nop     dword ptr [rax+rax+00h]
0x18002cbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc00  xor     ebx, ebx
0x18002cc02  cmp     rcx, rdi
0x18002cc05  jz      short loc_18002CC25
0x18002cc07  test    byte ptr [rcx+1Ch], 20h
0x18002cc0b  jz      short loc_18002CC25
0x18002cc0d  mov     rcx, [rcx+10h]
0x18002cc11  lea     r8, WPP_15cd0f4c4a463b05036cd6f3e9a231d2_Traceguids
0x18002cc18  mov     edx, 0Dh
0x18002cc1d  mov     r9d, ebx
0x18002cc20  call    WPP_SF_D
0x18002cc25  mov     eax, ebx
0x18002cc27  mov     rbx, [rsp+48h+arg_0]
0x18002cc2c  add     rsp, 40h
0x18002cc30  pop     rdi
0x18002cc31  retn
```
