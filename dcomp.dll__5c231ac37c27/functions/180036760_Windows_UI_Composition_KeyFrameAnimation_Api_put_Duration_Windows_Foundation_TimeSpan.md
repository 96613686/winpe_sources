# Windows::UI::Composition::KeyFrameAnimation::Api::put_Duration(Windows::Foundation::TimeSpan)

- ea: `0x180036760`
- end: `0x180036853`
- name: `?put_Duration@Api@KeyFrameAnimation@Composition@UI@Windows@@UEAAJUTimeSpan@Foundation@5@@Z`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180012da0`
- `0x180013528`
- `0x180036760`
- `0x180036f90`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036827`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180036827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036812`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180036812`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800367ef`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800367ef`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003683a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18003683a`

## string_xrefs

- `0x1800367e4`: `The given object has already been closed / disposed and may no longer be used.`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::KeyFrameAnimation::Api::put_Duration(__int64 a1, __int64 a2)
{
  Microsoft::WRL2::ContextSession *v2; // rdi
  unsigned int v5; // ebx
  HRESULT v7; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  v2 = *(Microsoft::WRL2::ContextSession **)(a1 - 336);
  Microsoft::WRL2::ContextSession::BeginApiEntry(v2);
  if ( (*(_BYTE *)(a1 - 312) & 2) != 0 )
  {
    if ( (unsigned __int64)(a2 - 10000) > 0x12DCE85500F0LL )
    {
      string = 0;
      v7 = WindowsCreateStringReference(
             L"An invalid Duration is specified. It must be >= 1ms and <= 24 days",
             0x42u,
             &hstringHeader,
             &string);
      if ( v7 < 0 )
      {
        RaiseException(v7, 1u, 0, 0);
        __debugbreak();
      }
      RoOriginateError(2147942487LL);
      v5 = -2147024809;
      DoStackCaptureDirect(-2147024809, 0x59Cu);
    }
    else
    {
      *(_QWORD *)(a1 + 96) = a2;
      v5 = 0;
    }
  }
  else
  {
    v5 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
  }
  Microsoft::WRL2::ContextSession::EndApiEntry(v2);
  return v5;
}

```

## disassembly

```asm
0x180036760  mov     [rsp+arg_10], rbx
0x180036765  mov     [rsp+arg_18], rsi
0x18003676a  push    rdi
0x18003676b  sub     rsp, 50h
0x18003676f  mov     rax, cs:__security_cookie
0x180036776  xor     rax, rsp
0x180036779  mov     [rsp+58h+var_18], rax
0x18003677e  mov     rdi, [rcx-150h]
0x180036785  mov     rsi, rcx
0x180036788  mov     rcx, rdi; this
0x18003678b  mov     rbx, rdx
0x18003678e  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180036793  test    byte ptr [rsi-138h], 2
0x18003679a  jz      short loc_1800367DF
0x18003679c  lea     rax, [rbx-2710h]
0x1800367a3  mov     rcx, 12DCE85500F0h
0x1800367ad  cmp     rax, rcx
0x1800367b0  ja      short loc_1800367F7
0x1800367b2  mov     [rsi+60h], rbx
0x1800367b6  xor     ebx, ebx
0x1800367b8  mov     rcx, rdi; this
0x1800367bb  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800367c0  mov     eax, ebx
0x1800367c2  mov     rcx, [rsp+58h+var_18]
0x1800367c7  xor     rcx, rsp; StackCookie
0x1800367ca  call    __security_check_cookie
0x1800367cf  mov     rbx, [rsp+58h+arg_10]
0x1800367d4  mov     rsi, [rsp+58h+arg_18]
0x1800367d9  add     rsp, 50h
0x1800367dd  pop     rdi
0x1800367de  retn
0x1800367df  mov     ebx, 80000013h
0x1800367e4  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800367eb  mov     ecx, ebx
0x1800367ed  xor     edx, edx
0x1800367ef  call    cs:__imp_RoOriginateErrorW
0x1800367f5  jmp     short loc_1800367B8
0x1800367f7  xor     ebx, ebx
0x1800367f9  lea     r9, [rsp+58h+string]; string
0x1800367fe  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180036803  mov     [rsp+58h+string], rbx
0x180036808  lea     rcx, sourceString; "An invalid Duration is specified. It mu"...
0x18003680f  lea     edx, [rbx+42h]; length
0x180036812  call    cs:__imp_WindowsCreateStringReference
0x180036818  test    eax, eax
0x18003681a  jns     short loc_18003682E
0x18003681c  xor     r9d, r9d; lpArguments
0x18003681f  lea     edx, [rbx+1]; dwExceptionFlags
0x180036822  xor     r8d, r8d; nNumberOfArguments
0x180036825  mov     ecx, eax; dwExceptionCode
0x180036827  call    cs:__imp_RaiseException
0x18003682d  int     3; Trap to Debugger
0x18003682e  mov     rdx, [rsp+58h+string]
0x180036833  mov     esi, 80070057h
0x180036838  mov     ecx, esi
0x18003683a  call    cs:__imp_RoOriginateError
0x180036840  mov     edx, 59Ch; unsigned int
0x180036845  mov     ecx, esi; int
0x180036847  mov     ebx, esi
0x180036849  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x18003684e  jmp     loc_1800367B8
```
