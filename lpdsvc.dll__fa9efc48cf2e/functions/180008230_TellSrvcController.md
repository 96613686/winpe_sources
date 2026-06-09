# TellSrvcController

- ea: `0x180008230`
- end: `0x1800082e2`
- name: `TellSrvcController`
- size: `178`
- prototype: `__int64 __fastcall(DWORD, __int64, DWORD, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007c10`

## callees

- `0x180002ea4`
- `0x180008230`
- `0x18000836c`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x1800082b1`
- `ADVAPI32!SetServiceStatus` at `0x1800082b1`

## pseudocode

```c
__int64 __fastcall TellSrvcController(DWORD a1, __int64 a2, DWORD a3, DWORD a4)
{
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids, a1);
  ssSvcStatusGLB.dwServiceType = 16;
  ssSvcStatusGLB.dwCurrentState = a1;
  *(_QWORD *)&ssSvcStatusGLB.dwControlsAccepted = 7;
  ssSvcStatusGLB.dwServiceSpecificExitCode = 0;
  ssSvcStatusGLB.dwCheckPoint = a3;
  ssSvcStatusGLB.dwWaitHint = a4;
  v7 = SetServiceStatus(hSvcHandleGLB, &ssSvcStatusGLB);
  v10 = v7;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v7);
  return v10;
}

```

## disassembly

```asm
0x180008230  push    rbx
0x180008232  push    rbp
0x180008233  push    rsi
0x180008234  push    rdi
0x180008235  sub     rsp, 28h
0x180008239  mov     edi, r9d
0x18000823c  mov     esi, r8d
0x18000823f  mov     ebx, ecx
0x180008241  mov     rcx, cs:WPP_GLOBAL_Control
0x180008248  lea     rbp, WPP_GLOBAL_Control
0x18000824f  cmp     rcx, rbp
0x180008252  jz      short loc_180008272
0x180008254  test    byte ptr [rcx+1Ch], 2
0x180008258  jz      short loc_180008272
0x18000825a  mov     rcx, [rcx+10h]
0x18000825e  lea     r8, WPP_aba322e9cdd73944fd42359f2444c51f_Traceguids
0x180008265  mov     edx, 16h
0x18000826a  mov     r9d, ebx
0x18000826d  call    WPP_SF_d
0x180008272  mov     rcx, cs:hSvcHandleGLB; hServiceStatus
0x180008279  lea     rdx, ssSvcStatusGLB; lpServiceStatus
0x180008280  mov     cs:ssSvcStatusGLB.dwServiceType, 10h
0x18000828a  mov     cs:ssSvcStatusGLB.dwCurrentState, ebx
0x180008290  mov     qword ptr cs:ssSvcStatusGLB.dwControlsAccepted, 7
0x18000829b  mov     cs:ssSvcStatusGLB.dwServiceSpecificExitCode, 0
0x1800082a5  mov     cs:ssSvcStatusGLB.dwCheckPoint, esi
0x1800082ab  mov     cs:ssSvcStatusGLB.dwWaitHint, edi
0x1800082b1  call    cs:__imp_SetServiceStatus
0x1800082b7  mov     ebx, eax
0x1800082b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082c0  cmp     rcx, rbp
0x1800082c3  jz      short loc_1800082D7
0x1800082c5  test    byte ptr [rcx+1Ch], 1
0x1800082c9  jz      short loc_1800082D7
0x1800082cb  mov     rcx, [rcx+10h]
0x1800082cf  mov     r9d, eax
0x1800082d2  call    WPP_SF_l
0x1800082d7  mov     eax, ebx
0x1800082d9  add     rsp, 28h
0x1800082dd  pop     rdi
0x1800082de  pop     rsi
0x1800082df  pop     rbp
0x1800082e0  pop     rbx
0x1800082e1  retn
```
