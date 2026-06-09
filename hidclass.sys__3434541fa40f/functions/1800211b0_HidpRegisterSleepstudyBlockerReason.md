# HidpRegisterSleepstudyBlockerReason

- ea: `0x1800211b0`
- end: `0x180021366`
- name: `HidpRegisterSleepstudyBlockerReason`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002136c`

## callees

- `0x180013970`
- `0x18001d7b4`
- `0x1800211b0`
- `0x180027ba0`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x1800212b0`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_RegisterComponentEx` at `0x1800212b0`

## pseudocode

```c
__int64 __fastcall HidpRegisterSleepstudyBlockerReason(__int128 *a1, __int64 a2, __int128 *a3, __int64 a4, __int64 a5)
{
  __int128 v5; // xmm7
  __int128 v6; // xmm6
  int v7; // edx
  NTSTATUS v8; // ebx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v14; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+78h] [rbp-90h] BYREF
  char v16; // [rsp+88h] [rbp-80h] BYREF

  v5 = *a3;
  v6 = *a1;
  *(_QWORD *)&DestinationString.Length = 0x2000000;
  DestinationString.Buffer = (wchar_t *)&v16;
  v8 = RtlUnicodeStringPrintf(&DestinationString, L"%wZ (%s)", a2);
  if ( v8 >= 0 )
  {
    v14 = v5;
    v15 = v6;
    v8 = SleepstudyHelper_RegisterComponentEx(g_SleepstudyLibraryHandle, &v15, &v14, &DestinationString, a5);
    if ( v8 < 0 )
    {
      LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v11,
          g_RecorderLog,
          3,
          11,
          102,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          v8);
      }
    }
  }
  else
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v9,
        g_RecorderLog,
        2,
        11,
        101,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        v8);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800211b0  mov     rax, rsp
0x1800211b3  push    rbp
0x1800211b4  push    rbx
0x1800211b5  push    rdi
0x1800211b6  lea     rbp, [rax-1C8h]
0x1800211bd  sub     rsp, 2B0h
0x1800211c4  movaps  xmmword ptr [rax-28h], xmm6
0x1800211c8  movaps  xmmword ptr [rax-38h], xmm7
0x1800211cc  mov     rax, cs:__security_cookie
0x1800211d3  xor     rax, rsp
0x1800211d6  mov     [rbp+1C0h+var_40], rax
0x1800211dd  movaps  xmm7, xmmword ptr [r8]
0x1800211e1  lea     rax, [rbp+1C0h+var_240]
0x1800211e5  movaps  xmm6, xmmword ptr [rcx]
0x1800211e8  mov     r8, rdx
0x1800211eb  mov     rdi, [rbp+1C0h+arg_20]
0x1800211f2  lea     rdx, aWzS; "%wZ (%s)"
0x1800211f9  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x1800211fe  mov     qword ptr [rsp+2C0h+DestinationString.Length], 2000000h
0x180021207  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x18002120c  call    RtlUnicodeStringPrintf
0x180021211  mov     ebx, eax
0x180021213  test    eax, eax
0x180021215  jns     short loc_180021289
0x180021217  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002121e  lea     rcx, WPP_GLOBAL_Control
0x180021225  cmp     r10, rcx
0x180021228  jz      short loc_18002123F
0x18002122a  test    dword ptr [r10+2Ch], 400h
0x180021232  jz      short loc_18002123F
0x180021234  cmp     byte ptr [r10+29h], 2
0x180021239  jb      short loc_18002123F
0x18002123b  mov     dl, 1
0x18002123d  jmp     short loc_180021241
0x18002123f  xor     dl, dl
0x180021241  lea     rax, WPP_RECORDER_INITIALIZED
0x180021248  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002124f  setnz   r8b
0x180021253  test    dl, dl
0x180021255  jnz     short loc_180021260
0x180021257  test    r8b, r8b
0x18002125a  jz      loc_18002133B
0x180021260  mov     [rsp+2C0h+var_280], ebx
0x180021264  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18002126b  mov     qword ptr [rsp+2C0h+var_288], rax
0x180021270  mov     word ptr [rsp+2C0h+var_290], 65h ; 'e'
0x180021277  mov     dword ptr [rsp+2C0h+var_298], 0Bh
0x18002127f  mov     byte ptr [rsp+2C0h+var_2A0], 2
0x180021284  jmp     loc_18002132B
0x180021289  mov     rcx, cs:g_SleepstudyLibraryHandle
0x180021290  lea     r9, [rsp+2C0h+DestinationString]
0x180021295  lea     r8, [rsp+60h]
0x18002129a  movdqa  xmmword ptr [rsp+60h], xmm7
0x1800212a0  lea     rdx, [rsp+2C0h+var_258+8]
0x1800212a5  movdqa  xmmword ptr [rsp+2C0h+var_258+8], xmm6
0x1800212ab  mov     qword ptr [rsp+2C0h+var_2A0], rdi
0x1800212b0  call    cs:__imp_SleepstudyHelper_RegisterComponentEx
0x1800212b7  nop     dword ptr [rax+rax+00h]
0x1800212bc  mov     ebx, eax
0x1800212be  test    eax, eax
0x1800212c0  jns     short loc_18002133B
0x1800212c2  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800212c9  lea     rcx, WPP_GLOBAL_Control
0x1800212d0  cmp     r10, rcx
0x1800212d3  jz      short loc_1800212EA
0x1800212d5  test    dword ptr [r10+2Ch], 400h
0x1800212dd  jz      short loc_1800212EA
0x1800212df  cmp     byte ptr [r10+29h], 3
0x1800212e4  jb      short loc_1800212EA
0x1800212e6  mov     dl, 1
0x1800212e8  jmp     short loc_1800212EC
0x1800212ea  xor     dl, dl
0x1800212ec  lea     rax, WPP_RECORDER_INITIALIZED
0x1800212f3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800212fa  setnz   r8b
0x1800212fe  test    dl, dl
0x180021300  jnz     short loc_180021307
0x180021302  test    r8b, r8b
0x180021305  jz      short loc_18002133B
0x180021307  mov     [rsp+2C0h+var_280], ebx
0x18002130b  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x180021312  mov     qword ptr [rsp+2C0h+var_288], rax
0x180021317  mov     word ptr [rsp+2C0h+var_290], 66h ; 'f'
0x18002131e  mov     dword ptr [rsp+2C0h+var_298], 0Bh
0x180021326  mov     byte ptr [rsp+2C0h+var_2A0], 3
0x18002132b  mov     r9, cs:g_RecorderLog
0x180021332  mov     rcx, [r10+18h]
0x180021336  call    WPP_RECORDER_AND_TRACE_SF_d
0x18002133b  mov     eax, ebx
0x18002133d  mov     rcx, [rbp+1C0h+var_40]
0x180021344  xor     rcx, rsp; StackCookie
0x180021347  call    __security_check_cookie
0x18002134c  lea     r11, [rsp+2C0h+var_10]
0x180021354  movaps  xmm6, xmmword ptr [r11-10h]
0x180021359  movaps  xmm7, xmmword ptr [r11-20h]
0x18002135e  mov     rsp, r11
0x180021361  pop     rdi
0x180021362  pop     rbx
0x180021363  pop     rbp
0x180021364  retn
```
