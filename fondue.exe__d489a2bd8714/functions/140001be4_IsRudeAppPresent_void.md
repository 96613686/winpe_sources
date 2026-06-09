# IsRudeAppPresent(void)

- ea: `0x140001be4`
- end: `0x140001d54`
- name: `?IsRudeAppPresent@@YAHXZ`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001e24`

## callees

- `0x140001b28`
- `0x140001be4`
- `0x140004cd0`

## import_xrefs

- `USER32!IntersectRect` at `0x140001d17`
- `USER32!IntersectRect` at `0x140001d17`
- `USER32!IsRectEmpty` at `0x140001d21`
- `USER32!IsRectEmpty` at `0x140001d21`
- `USER32!GetForegroundWindow` at `0x140001c00`
- `USER32!GetForegroundWindow` at `0x140001c00`
- `USER32!MonitorFromWindow` at `0x140001ce8`
- `USER32!MonitorFromWindow` at `0x140001ce8`
- `USER32!EqualRect` at `0x140001d33`
- `USER32!EqualRect` at `0x140001d33`
- `USER32!GetWindowRect` at `0x140001d01`
- `USER32!GetWindowRect` at `0x140001d01`
- `USER32!GetWindowBand` at `0x140001cd0`
- `USER32!GetWindowBand` at `0x140001cd0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001c45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001c78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001c45`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140001c78`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140001c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140001ca8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140001c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140001ca8`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140001c2b`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140001c65`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140001c2b`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140001c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001cb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001c9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140001cb1`

## pseudocode

```c
BOOL IsRudeAppPresent(void)
{
  HWND ForegroundWindow; // r14
  HANDLE v1; // rax
  void *v2; // rsi
  DWORD v3; // eax
  BOOL v4; // edi
  HANDLE v5; // rax
  void *v6; // rbx
  DWORD v7; // eax
  BOOL result; // eax
  HMONITOR v9; // rax
  int v10; // r8d
  int v11; // [rsp+20h] [rbp-40h] BYREF
  RECT rcSrc2; // [rsp+28h] [rbp-38h] BYREF
  struct tagRECT Rect; // [rsp+38h] [rbp-28h] BYREF
  struct tagRECT rcDst; // [rsp+48h] [rbp-18h] BYREF

  Rect = 0;
  ForegroundWindow = GetForegroundWindow();
  rcSrc2 = 0;
  rcDst = 0;
  v1 = OpenMutexW(0x100000u, 0, L"Local\\__DDrawCheckExclMode__");
  v2 = v1;
  if ( v1 )
  {
    v3 = WaitForSingleObject(v1, 0x1Eu);
    if ( !v3 || (v4 = 0, v3 == 128) )
    {
      v4 = 0;
      v5 = OpenMutexW(0x100000u, 0, L"Local\\__DDrawExclMode__");
      v6 = v5;
      if ( v5 )
      {
        v7 = WaitForSingleObject(v5, 0);
        if ( (v7 & 0xFFFFFF7F) != 0 )
          v4 = v7 == 258;
        else
          ReleaseMutex(v6);
        CloseHandle(v6);
      }
      ReleaseMutex(v2);
    }
    CloseHandle(v2);
    if ( v4 )
      return 1;
  }
  v11 = 0;
  result = (unsigned int)GetWindowBand(ForegroundWindow, &v11)
        && v11 == 1
        && (v9 = MonitorFromWindow(ForegroundWindow, 1u),
            GetMonitorRects(v9, &rcSrc2, v10),
            GetWindowRect(ForegroundWindow, &Rect))
        && (IntersectRect(&rcDst, &Rect, &rcSrc2), !IsRectEmpty(&rcDst))
        && EqualRect(&Rect, &rcSrc2);
  return result;
}

```

## disassembly

```asm
0x140001be4  push    rbp
0x140001be6  push    rbx
0x140001be7  push    rsi
0x140001be8  push    rdi
0x140001be9  push    r14
0x140001beb  mov     rbp, rsp
0x140001bee  sub     rsp, 60h
0x140001bf2  mov     rax, cs:__security_cookie
0x140001bf9  xor     rax, rsp
0x140001bfc  mov     [rbp+var_8], rax
0x140001c00  call    cs:__imp_GetForegroundWindow
0x140001c06  xorps   xmm0, xmm0
0x140001c09  lea     r8, Name; "Local\\__DDrawCheckExclMode__"
0x140001c10  xorps   xmm1, xmm1
0x140001c13  mov     ebx, 100000h
0x140001c18  mov     ecx, ebx; dwDesiredAccess
0x140001c1a  xor     edx, edx; bInheritHandle
0x140001c1c  movups  xmmword ptr [rbp+Rect.left], xmm0
0x140001c20  mov     r14, rax
0x140001c23  movups  xmmword ptr [rbp+rcSrc2.left], xmm1
0x140001c27  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x140001c2b  call    cs:__imp_OpenMutexW
0x140001c31  mov     rsi, rax
0x140001c34  test    rax, rax
0x140001c37  jz      loc_140001CC2
0x140001c3d  mov     edx, 1Eh; dwMilliseconds
0x140001c42  mov     rcx, rax; hHandle
0x140001c45  call    cs:__imp_WaitForSingleObject
0x140001c4b  test    eax, eax
0x140001c4d  jz      short loc_140001C58
0x140001c4f  xor     edi, edi
0x140001c51  cmp     eax, 80h
0x140001c56  jnz     short loc_140001CAE
0x140001c58  lea     r8, aLocalDdrawexcl; "Local\\__DDrawExclMode__"
0x140001c5f  xor     edx, edx; bInheritHandle
0x140001c61  mov     ecx, ebx; dwDesiredAccess
0x140001c63  xor     edi, edi
0x140001c65  call    cs:__imp_OpenMutexW
0x140001c6b  mov     rbx, rax
0x140001c6e  test    rax, rax
0x140001c71  jz      short loc_140001CA5
0x140001c73  xor     edx, edx; dwMilliseconds
0x140001c75  mov     rcx, rax; hHandle
0x140001c78  call    cs:__imp_WaitForSingleObject
0x140001c7e  test    eax, 0FFFFFF7Fh
0x140001c83  jz      short loc_140001C93
0x140001c85  cmp     eax, 102h
0x140001c8a  jnz     short loc_140001C9C
0x140001c8c  mov     edi, 1
0x140001c91  jmp     short loc_140001C9C
0x140001c93  mov     rcx, rbx; hMutex
0x140001c96  call    cs:__imp_ReleaseMutex
0x140001c9c  mov     rcx, rbx; hObject
0x140001c9f  call    cs:__imp_CloseHandle
0x140001ca5  mov     rcx, rsi; hMutex
0x140001ca8  call    cs:__imp_ReleaseMutex
0x140001cae  mov     rcx, rsi; hObject
0x140001cb1  call    cs:__imp_CloseHandle
0x140001cb7  test    edi, edi
0x140001cb9  jz      short loc_140001CC2
0x140001cbb  mov     eax, 1
0x140001cc0  jmp     short loc_140001D3D
0x140001cc2  lea     rdx, [rbp+var_40]
0x140001cc6  mov     [rbp+var_40], 0
0x140001ccd  mov     rcx, r14
0x140001cd0  call    cs:__imp_GetWindowBand
0x140001cd6  test    eax, eax
0x140001cd8  jz      short loc_140001D3B
0x140001cda  cmp     [rbp+var_40], 1
0x140001cde  jnz     short loc_140001D3B
0x140001ce0  mov     edx, 1; dwFlags
0x140001ce5  mov     rcx, r14; hwnd
0x140001ce8  call    cs:__imp_MonitorFromWindow
0x140001cee  mov     rcx, rax; HMONITOR
0x140001cf1  lea     rdx, [rbp+rcSrc2]; struct tagRECT *
0x140001cf5  call    ?GetMonitorRects@@YAHPEAUHMONITOR__@@PEAUtagRECT@@H@Z; GetMonitorRects(HMONITOR__ *,tagRECT *,int)
0x140001cfa  lea     rdx, [rbp+Rect]; lpRect
0x140001cfe  mov     rcx, r14; hWnd
0x140001d01  call    cs:__imp_GetWindowRect
0x140001d07  test    eax, eax
0x140001d09  jz      short loc_140001D3B
0x140001d0b  lea     r8, [rbp+rcSrc2]; lprcSrc2
0x140001d0f  lea     rdx, [rbp+Rect]; lprcSrc1
0x140001d13  lea     rcx, [rbp+rcDst]; lprcDst
0x140001d17  call    cs:__imp_IntersectRect
0x140001d1d  lea     rcx, [rbp+rcDst]; lprc
0x140001d21  call    cs:__imp_IsRectEmpty
0x140001d27  test    eax, eax
0x140001d29  jnz     short loc_140001D3B
0x140001d2b  lea     rdx, [rbp+rcSrc2]; lprc2
0x140001d2f  lea     rcx, [rbp+Rect]; lprc1
0x140001d33  call    cs:__imp_EqualRect
0x140001d39  jmp     short loc_140001D3D
0x140001d3b  xor     eax, eax
0x140001d3d  mov     rcx, [rbp+var_8]
0x140001d41  xor     rcx, rsp; StackCookie
0x140001d44  call    __security_check_cookie
0x140001d49  add     rsp, 60h
0x140001d4d  pop     r14
0x140001d4f  pop     rdi
0x140001d50  pop     rsi
0x140001d51  pop     rbx
0x140001d52  pop     rbp
0x140001d53  retn
```
