# DwmGetCompositionTimingInfo

- ea: `0x180002fc0`
- end: `0x18000302a`
- name: `DwmGetCompositionTimingInfo`
- size: `106`
- prototype: `HRESULT __stdcall(HWND hwnd, DWM_TIMING_INFO *pTimingInfo)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002fc0`
- `0x180003030`
- `0x180003370`

## pseudocode

```c
HRESULT __stdcall DwmGetCompositionTimingInfo(HWND hwnd, DWM_TIMING_INFO *pTimingInfo)
{
  HRESULT result; // eax
  HRESULT v3; // ebx

  if ( pTimingInfo )
  {
    if ( pTimingInfo->cbSize == 292 )
    {
      result = DwmpGetCompositionTimingInfoEx((__int64)hwnd, &pTimingInfo->cbSize);
      v3 = result;
      if ( result < 0 )
      {
        DoStackCaptureDirect(result, 0x90u);
        return v3;
      }
    }
    else
    {
      DoStackCaptureDirect(-2003304304, 0x8Cu);
      return -2003304304;
    }
  }
  else
  {
    DoStackCaptureDirect(-2147024809, 0x89u);
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x180002fc0  sub     rsp, 28h
0x180002fc4  test    rdx, rdx
0x180002fc7  jz      short loc_180002FEB
0x180002fc9  cmp     dword ptr [rdx], 124h
0x180002fcf  jnz     short loc_180003004
0x180002fd1  mov     [rsp+28h+var_8], rbx
0x180002fd6  call    DwmpGetCompositionTimingInfoEx
0x180002fdb  mov     ebx, eax
0x180002fdd  test    eax, eax
0x180002fdf  js      short loc_18000301A
0x180002fe1  mov     rbx, [rsp+28h+var_8]
0x180002fe6  add     rsp, 28h
0x180002fea  retn
0x180002feb  mov     edx, 89h; unsigned int
0x180002ff0  mov     ecx, 80070057h; int
0x180002ff5  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180002ffa  mov     eax, 80070057h
0x180002fff  add     rsp, 28h
0x180003003  retn
0x180003004  mov     edx, 8Ch; unsigned int
0x180003009  mov     ecx, 88980090h; int
0x18000300e  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003013  mov     eax, 88980090h
0x180003018  jmp     short loc_180002FE6
0x18000301a  mov     edx, 90h; unsigned int
0x18000301f  mov     ecx, ebx; int
0x180003021  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x180003026  mov     eax, ebx
0x180003028  jmp     short loc_180002FE1
```
