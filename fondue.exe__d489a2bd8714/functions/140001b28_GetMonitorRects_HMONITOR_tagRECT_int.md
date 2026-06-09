# GetMonitorRects(HMONITOR__ *,tagRECT *,int)

- ea: `0x140001b28`
- end: `0x140001bdc`
- name: `?GetMonitorRects@@YAHPEAUHMONITOR__@@PEAUtagRECT@@H@Z`
- size: `180`
- prototype: `int(HMONITOR, struct tagRECT *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001be4`

## callees

- `0x140001b28`
- `0x140004cd0`

## import_xrefs

- `USER32!SetRect` at `0x140001bb9`
- `USER32!SetRect` at `0x140001bb9`
- `USER32!GetMonitorInfoW` at `0x140001b6a`
- `USER32!GetMonitorInfoW` at `0x140001b6a`
- `USER32!GetSystemMetrics` at `0x140001b9a`
- `USER32!GetSystemMetrics` at `0x140001ba4`
- `USER32!GetSystemMetrics` at `0x140001b9a`
- `USER32!GetSystemMetrics` at `0x140001ba4`
- `USER32!CopyRect` at `0x140001b88`
- `USER32!CopyRect` at `0x140001b88`

## pseudocode

```c
__int64 __fastcall GetMonitorRects(HMONITOR a1, struct tagRECT *a2)
{
  int yBottom; // ebx
  int SystemMetrics; // eax
  tagMONITORINFO mi; // [rsp+30h] [rbp-38h] BYREF

  memset(&mi, 0, sizeof(mi));
  mi.cbSize = 40;
  if ( a1 && GetMonitorInfoW(a1, &mi) )
  {
    if ( a2 )
      CopyRect(a2, &mi.rcMonitor);
    return 1;
  }
  else
  {
    if ( a2 )
    {
      yBottom = GetSystemMetrics(1);
      SystemMetrics = GetSystemMetrics(0);
      SetRect(a2, 0, 0, SystemMetrics, yBottom);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140001b28  mov     [rsp+arg_10], rbx
0x140001b2d  push    rdi
0x140001b2e  sub     rsp, 60h
0x140001b32  mov     rax, cs:__security_cookie
0x140001b39  xor     rax, rsp
0x140001b3c  mov     [rsp+68h+var_10], rax
0x140001b41  xorps   xmm0, xmm0
0x140001b44  xor     eax, eax
0x140001b46  mov     qword ptr [rsp+68h+mi.rcWork.bottom], rax
0x140001b4b  mov     rdi, rdx
0x140001b4e  movups  xmmword ptr [rsp+68h+mi.cbSize], xmm0
0x140001b53  mov     [rsp+68h+mi.cbSize], 28h ; '('
0x140001b5b  movups  xmmword ptr [rsp+68h+mi.rcMonitor.bottom], xmm0
0x140001b60  test    rcx, rcx
0x140001b63  jz      short loc_140001B90
0x140001b65  lea     rdx, [rsp+68h+mi]; lpmi
0x140001b6a  call    cs:__imp_GetMonitorInfoW
0x140001b70  test    eax, eax
0x140001b72  jz      short loc_140001B90
0x140001b74  test    rdi, rdi
0x140001b77  jnz     short loc_140001B80
0x140001b79  mov     eax, 1
0x140001b7e  jmp     short loc_140001BC1
0x140001b80  lea     rdx, [rsp+68h+mi.rcMonitor]; lprcSrc
0x140001b85  mov     rcx, rdi; lprcDst
0x140001b88  call    cs:__imp_CopyRect
0x140001b8e  jmp     short loc_140001B79
0x140001b90  test    rdi, rdi
0x140001b93  jz      short loc_140001BBF
0x140001b95  mov     ecx, 1; nIndex
0x140001b9a  call    cs:__imp_GetSystemMetrics
0x140001ba0  xor     ecx, ecx; nIndex
0x140001ba2  mov     ebx, eax
0x140001ba4  call    cs:__imp_GetSystemMetrics
0x140001baa  xor     r8d, r8d; yTop
0x140001bad  mov     [rsp+68h+yBottom], ebx; yBottom
0x140001bb1  mov     r9d, eax; xRight
0x140001bb4  xor     edx, edx; xLeft
0x140001bb6  mov     rcx, rdi; lprc
0x140001bb9  call    cs:__imp_SetRect
0x140001bbf  xor     eax, eax
0x140001bc1  mov     rcx, [rsp+68h+var_10]
0x140001bc6  xor     rcx, rsp; StackCookie
0x140001bc9  call    __security_check_cookie
0x140001bce  mov     rbx, [rsp+68h+arg_10]
0x140001bd6  add     rsp, 60h
0x140001bda  pop     rdi
0x140001bdb  retn
```
