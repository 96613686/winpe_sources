# CuipGetThreadDesktopName(void)

- ea: `0x140004fb8`
- end: `0x14000503a`
- name: `?CuipGetThreadDesktopName@@YAPEAGXZ`
- size: `130`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001adb0`

## callees

- `0x140004fb8`
- `0x1400056a0`
- `0x14000fbec`

## import_xrefs

- `USER32!GetThreadDesktop` at `0x140004fca`
- `USER32!GetThreadDesktop` at `0x140004fca`
- `USER32!CloseDesktop` at `0x140004fe6`
- `USER32!CloseDesktop` at `0x140004fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005009`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004fc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004fc2`

## pseudocode

```c
unsigned __int16 *CuipGetThreadDesktopName(void)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HDESK v2; // rbx
  unsigned __int16 *DesktopName; // rdi
  DWORD LastError; // eax

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  v2 = ThreadDesktop;
  if ( ThreadDesktop )
  {
    DesktopName = CuipGetDesktopName(ThreadDesktop);
    CloseDesktop(v2);
  }
  else
  {
    DesktopName = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
    }
  }
  return DesktopName;
}

```

## disassembly

```asm
0x140004fb8  mov     [rsp+arg_0], rbx
0x140004fbd  push    rdi
0x140004fbe  sub     rsp, 20h
0x140004fc2  call    cs:__imp_GetCurrentThreadId
0x140004fc8  mov     ecx, eax; dwThreadId
0x140004fca  call    cs:__imp_GetThreadDesktop
0x140004fd0  mov     rbx, rax
0x140004fd3  test    rax, rax
0x140004fd6  jz      short loc_140004FEE
0x140004fd8  mov     rcx, rax; hObj
0x140004fdb  call    ?CuipGetDesktopName@@YAPEAGPEAUHDESK__@@@Z; CuipGetDesktopName(HDESK__ *)
0x140004fe0  mov     rcx, rbx; hDesktop
0x140004fe3  mov     rdi, rax
0x140004fe6  call    cs:__imp_CloseDesktop
0x140004fec  jmp     short loc_14000502C
0x140004fee  mov     rax, cs:WPP_GLOBAL_Control
0x140004ff5  lea     rcx, WPP_GLOBAL_Control
0x140004ffc  xor     edi, edi
0x140004ffe  cmp     rax, rcx
0x140005001  jz      short loc_14000502C
0x140005003  test    byte ptr [rax+1Ch], 4
0x140005007  jz      short loc_14000502C
0x140005009  call    cs:__imp_GetLastError
0x14000500f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005016  lea     edx, [rdi+0Dh]
0x140005019  mov     r9d, eax
0x14000501c  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140005023  mov     rcx, [rcx+10h]
0x140005027  call    WPP_SF_D
0x14000502c  mov     rbx, [rsp+28h+arg_0]
0x140005031  mov     rax, rdi
0x140005034  add     rsp, 20h
0x140005038  pop     rdi
0x140005039  retn
```
