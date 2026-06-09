# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x180082a10`
- end: `0x180082aeb`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18007fe70`
- `0x180081a88`
- `0x1800821c0`
- `0x180082a10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180082aa8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180082aa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082a43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082a75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082a75`

## pseudocode

```c
__int64 __fastcall CActivatedEventArgsBase::v_GetActivationKind(
        CActivatedEventArgsBase *this,
        HSTRING a2,
        enum Windows::ApplicationModel::Activation::ActivationKind *a3)
{
  const WCHAR *StringRawBuffer; // rsi
  HSTRING *v6; // r8
  int v7; // ebp
  unsigned int i; // ebx
  __int64 v9; // rcx
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF

  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this);
  *(_DWORD *)a3 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  WindowsDeleteString(0);
  string = 0;
  v7 = SplitActionAndServiceId(a2, &string, v6);
  if ( v7 >= 0 )
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  for ( i = 0; i < 0x2E; ++i )
  {
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_18008D2C0)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_18008D2C0 + 4 * i + 2);
      goto LABEL_12;
    }
  }
  if ( !IsBackgroundExtensionContract(StringRawBuffer) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9);
LABEL_12:
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180082a10  push    rbx
0x180082a12  push    rbp
0x180082a13  push    rsi
0x180082a14  push    rdi
0x180082a15  push    r12
0x180082a17  push    r14
0x180082a19  sub     rsp, 38h
0x180082a1d  mov     rdi, r8
0x180082a20  mov     rbx, rdx
0x180082a23  test    r8, r8
0x180082a26  jnz     short loc_180082A2D
0x180082a28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180082a2d  xor     edx, edx; length
0x180082a2f  mov     dword ptr [rdi], 0
0x180082a35  mov     rcx, rbx; string
0x180082a38  call    cs:__imp_WindowsGetStringRawBuffer
0x180082a3e  xor     ecx, ecx; string
0x180082a40  mov     rsi, rax
0x180082a43  call    cs:__imp_WindowsDeleteString
0x180082a49  lea     rdx, [rsp+68h+string]; HSTRING *
0x180082a51  mov     [rsp+68h+string], 0
0x180082a5d  mov     rcx, rbx; string
0x180082a60  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x180082a65  mov     ebp, eax
0x180082a67  test    eax, eax
0x180082a69  js      short loc_180082A7E
0x180082a6b  mov     rcx, [rsp+68h+string]; string
0x180082a73  xor     edx, edx; length
0x180082a75  call    cs:__imp_WindowsGetStringRawBuffer
0x180082a7b  mov     rsi, rax
0x180082a7e  xor     ebx, ebx
0x180082a80  lea     r12, off_18008D2C0; "Windows.Launch"
0x180082a87  mov     rcx, rsi; unsigned __int16 *
0x180082a8a  cmp     ebx, 2Eh ; '.'
0x180082a8d  jnb     short loc_180082AC0
0x180082a8f  or      r9d, 0FFFFFFFFh; cchCount2
0x180082a93  mov     r14d, ebx
0x180082a96  add     r14, r14
0x180082a99  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x180082aa1  or      edx, r9d; cchCount1
0x180082aa4  mov     r8, [r12+r14*8]; lpString2
0x180082aa8  call    cs:__imp_CompareStringOrdinal
0x180082aae  cmp     eax, 2
0x180082ab1  jz      short loc_180082AB7
0x180082ab3  inc     ebx
0x180082ab5  jmp     short loc_180082A87
0x180082ab7  mov     eax, [r12+r14*8+8]
0x180082abc  mov     [rdi], eax
0x180082abe  jmp     short loc_180082ACE
0x180082ac0  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x180082ac5  test    al, al
0x180082ac7  jnz     short loc_180082ACE
0x180082ac9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180082ace  mov     rcx, [rsp+68h+string]; string
0x180082ad6  call    cs:__imp_WindowsDeleteString
0x180082adc  mov     eax, ebp
0x180082ade  add     rsp, 38h
0x180082ae2  pop     r14
0x180082ae4  pop     r12
0x180082ae6  pop     rdi
0x180082ae7  pop     rsi
0x180082ae8  pop     rbp
0x180082ae9  pop     rbx
0x180082aea  retn
```
