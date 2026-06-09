# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x1401c9f80`
- end: `0x1401ca05b`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `219`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1401c0694`
- `0x1401c9614`
- `0x1401c9708`
- `0x1401c9f80`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1401ca018`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1401ca018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c9fe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9fb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca046`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c9fb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401ca046`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_1401E4C20)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_1401E4C20 + 4 * i + 2);
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
0x1401c9f80  push    rbx
0x1401c9f82  push    rbp
0x1401c9f83  push    rsi
0x1401c9f84  push    rdi
0x1401c9f85  push    r12
0x1401c9f87  push    r14
0x1401c9f89  sub     rsp, 38h
0x1401c9f8d  mov     rdi, r8
0x1401c9f90  mov     rbx, rdx
0x1401c9f93  test    r8, r8
0x1401c9f96  jnz     short loc_1401C9F9D
0x1401c9f98  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pKind")
0x1401c9f9d  xor     edx, edx; length
0x1401c9f9f  mov     dword ptr [rdi], 0
0x1401c9fa5  mov     rcx, rbx; string
0x1401c9fa8  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c9fae  xor     ecx, ecx; string
0x1401c9fb0  mov     rsi, rax
0x1401c9fb3  call    cs:__imp_WindowsDeleteString
0x1401c9fb9  lea     rdx, [rsp+68h+string]; HSTRING *
0x1401c9fc1  mov     [rsp+68h+string], 0
0x1401c9fcd  mov     rcx, rbx; string
0x1401c9fd0  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1401c9fd5  mov     ebp, eax
0x1401c9fd7  test    eax, eax
0x1401c9fd9  js      short loc_1401C9FEE
0x1401c9fdb  mov     rcx, [rsp+68h+string]; string
0x1401c9fe3  xor     edx, edx; length
0x1401c9fe5  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c9feb  mov     rsi, rax
0x1401c9fee  xor     ebx, ebx
0x1401c9ff0  lea     r12, off_1401E4C20; "Windows.Launch"
0x1401c9ff7  mov     rcx, rsi; unsigned __int16 *
0x1401c9ffa  cmp     ebx, 2Eh ; '.'
0x1401c9ffd  jnb     short loc_1401CA030
0x1401c9fff  or      r9d, 0FFFFFFFFh; cchCount2
0x1401ca003  mov     r14d, ebx
0x1401ca006  add     r14, r14
0x1401ca009  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1401ca011  or      edx, r9d; cchCount1
0x1401ca014  mov     r8, [r12+r14*8]; lpString2
0x1401ca018  call    cs:__imp_CompareStringOrdinal
0x1401ca01e  cmp     eax, 2
0x1401ca021  jz      short loc_1401CA027
0x1401ca023  inc     ebx
0x1401ca025  jmp     short loc_1401C9FF7
0x1401ca027  mov     eax, [r12+r14*8+8]
0x1401ca02c  mov     [rdi], eax
0x1401ca02e  jmp     short loc_1401CA03E
0x1401ca030  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1401ca035  test    al, al
0x1401ca037  jnz     short loc_1401CA03E
0x1401ca039  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "fFound || IsBackgroundExtensionContract(pszContractId)")
0x1401ca03e  mov     rcx, [rsp+68h+string]; string
0x1401ca046  call    cs:__imp_WindowsDeleteString
0x1401ca04c  mov     eax, ebp
0x1401ca04e  add     rsp, 38h
0x1401ca052  pop     r14
0x1401ca054  pop     r12
0x1401ca056  pop     rdi
0x1401ca057  pop     rsi
0x1401ca058  pop     rbp
0x1401ca059  pop     rbx
0x1401ca05a  retn
```
