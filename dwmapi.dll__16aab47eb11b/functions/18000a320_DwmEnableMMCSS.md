# DwmEnableMMCSS

- ea: `0x18000a320`
- end: `0x18000a3b9`
- name: `DwmEnableMMCSS`
- size: `153`
- prototype: `HRESULT __stdcall(BOOL fEnableMMCSS)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003370`
- `0x180004594`
- `0x180005b5c`
- `0x18000a320`
- `0x18000d0a0`

## import_xrefs

- `win32u!NtDCompositionEnableMMCSS` at `0x18000a365`
- `win32u!NtDCompositionEnableMMCSS` at `0x18000a365`

## pseudocode

```c
HRESULT __stdcall DwmEnableMMCSS(BOOL fEnableMMCSS)
{
  __int64 v1; // r8
  int v3; // eax
  HRESULT v4; // ebx
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApiEnableMMCSS_Start,
      v1,
      1,
      (__int64)v6);
  v3 = NtDCompositionEnableMMCSS(fEnableMMCSS);
  if ( v3 >= 0 )
  {
    v4 = 0;
  }
  else
  {
    v4 = v3 | 0x10000000;
    DoStackCaptureDirect(v3 | 0x10000000, 0x18u);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiEnableMMCSS_Stop);
  return v4;
}

```

## disassembly

```asm
0x18000a320  push    rbx
0x18000a322  sub     rsp, 50h
0x18000a326  mov     rax, cs:__security_cookie
0x18000a32d  xor     rax, rsp
0x18000a330  mov     [rsp+58h+var_18], rax
0x18000a335  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18000a33c  mov     ebx, ecx
0x18000a33e  jz      short loc_18000A363
0x18000a340  lea     rax, [rsp+58h+var_28]
0x18000a345  mov     r9d, 1
0x18000a34b  lea     rdx, ApiEnableMMCSS_Start
0x18000a352  mov     [rsp+58h+var_38], rax
0x18000a357  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000a35e  call    McGenEventWrite_EtwEventWriteTransfer
0x18000a363  mov     ecx, ebx
0x18000a365  call    cs:__imp_NtDCompositionEnableMMCSS
0x18000a36b  mov     ebx, eax
0x18000a36d  test    eax, eax
0x18000a36f  jns     short loc_18000A383
0x18000a371  bts     ebx, 1Ch
0x18000a375  mov     edx, 18h; unsigned int
0x18000a37a  mov     ecx, ebx; int
0x18000a37c  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18000a381  jmp     short loc_18000A385
0x18000a383  xor     ebx, ebx
0x18000a385  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x18000a38c  jz      short loc_18000A3A4
0x18000a38e  mov     r8d, ebx
0x18000a391  lea     rdx, ApiEnableMMCSS_Stop
0x18000a398  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x18000a39f  call    McTemplateU0q_EtwEventWriteTransfer
0x18000a3a4  mov     eax, ebx
0x18000a3a6  mov     rcx, [rsp+58h+var_18]
0x18000a3ab  xor     rcx, rsp; StackCookie
0x18000a3ae  call    __security_check_cookie
0x18000a3b3  add     rsp, 50h
0x18000a3b7  pop     rbx
0x18000a3b8  retn
```
