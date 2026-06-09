# CActivatedEventArgsBase::v_GetActivationKind(HSTRING__ *,Windows::ApplicationModel::Activation::ActivationKind *)

- ea: `0x1401c8d20`
- end: `0x1401c8e1a`
- name: `?v_GetActivationKind@CActivatedEventArgsBase@@EEAAJPEAUHSTRING__@@PEAW4ActivationKind@Activation@ApplicationModel@Windows@@@Z`
- size: `250`
- prototype: `int(CActivatedEventArgsBase *__hidden this, HSTRING, enum Windows::ApplicationModel::Activation::ActivationKind *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1401bf000`
- `0x1401c8368`
- `0x1401c8464`
- `0x1401c8d20`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1401c8dca`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1401c8dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c8d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c8d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c8d48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1401c8d91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8dfe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8d59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1401c8dfe`

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
    if ( CompareStringOrdinal(StringRawBuffer, -1, (&off_1401E2760)[2 * i], -1, 0) == 2 )
    {
      *(_DWORD *)a3 = *((_DWORD *)&off_1401E2760 + 4 * i + 2);
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
0x1401c8d20  push    rbx
0x1401c8d22  push    rbp
0x1401c8d23  push    rsi
0x1401c8d24  push    rdi
0x1401c8d25  push    r12
0x1401c8d27  push    r14
0x1401c8d29  sub     rsp, 38h
0x1401c8d2d  mov     rdi, r8
0x1401c8d30  mov     rbx, rdx
0x1401c8d33  test    r8, r8
0x1401c8d36  jnz     short loc_1401C8D3D
0x1401c8d38  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1401c8d3d  xor     edx, edx; length
0x1401c8d3f  mov     dword ptr [rdi], 0
0x1401c8d45  mov     rcx, rbx; string
0x1401c8d48  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c8d4f  nop     dword ptr [rax+rax+00h]
0x1401c8d54  xor     ecx, ecx; string
0x1401c8d56  mov     rsi, rax
0x1401c8d59  call    cs:__imp_WindowsDeleteString
0x1401c8d60  nop     dword ptr [rax+rax+00h]
0x1401c8d65  lea     rdx, [rsp+68h+string]; HSTRING *
0x1401c8d6d  mov     [rsp+68h+string], 0
0x1401c8d79  mov     rcx, rbx; string
0x1401c8d7c  call    ?SplitActionAndServiceId@@YAJPEAUHSTRING__@@PEAPEAU1@1@Z; SplitActionAndServiceId(HSTRING__ *,HSTRING__ * *,HSTRING__ * *)
0x1401c8d81  mov     ebp, eax
0x1401c8d83  test    eax, eax
0x1401c8d85  js      short loc_1401C8DA0
0x1401c8d87  mov     rcx, [rsp+68h+string]; string
0x1401c8d8f  xor     edx, edx; length
0x1401c8d91  call    cs:__imp_WindowsGetStringRawBuffer
0x1401c8d98  nop     dword ptr [rax+rax+00h]
0x1401c8d9d  mov     rsi, rax
0x1401c8da0  xor     ebx, ebx
0x1401c8da2  lea     r12, off_1401E2760; "Windows.Launch"
0x1401c8da9  mov     rcx, rsi; unsigned __int16 *
0x1401c8dac  cmp     ebx, 2Eh ; '.'
0x1401c8daf  jnb     short loc_1401C8DE8
0x1401c8db1  or      r9d, 0FFFFFFFFh; cchCount2
0x1401c8db5  mov     r14d, ebx
0x1401c8db8  add     r14, r14
0x1401c8dbb  mov     [rsp+68h+bIgnoreCase], 0; bIgnoreCase
0x1401c8dc3  or      edx, r9d; cchCount1
0x1401c8dc6  mov     r8, [r12+r14*8]; lpString2
0x1401c8dca  call    cs:__imp_CompareStringOrdinal
0x1401c8dd1  nop     dword ptr [rax+rax+00h]
0x1401c8dd6  cmp     eax, 2
0x1401c8dd9  jz      short loc_1401C8DDF
0x1401c8ddb  inc     ebx
0x1401c8ddd  jmp     short loc_1401C8DA9
0x1401c8ddf  mov     eax, [r12+r14*8+8]
0x1401c8de4  mov     [rdi], eax
0x1401c8de6  jmp     short loc_1401C8DF6
0x1401c8de8  call    ?IsBackgroundExtensionContract@@YA_NPEBG@Z; IsBackgroundExtensionContract(ushort const *)
0x1401c8ded  test    al, al
0x1401c8def  jnz     short loc_1401C8DF6
0x1401c8df1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1401c8df6  mov     rcx, [rsp+68h+string]; string
0x1401c8dfe  call    cs:__imp_WindowsDeleteString
0x1401c8e05  nop     dword ptr [rax+rax+00h]
0x1401c8e0a  mov     eax, ebp
0x1401c8e0c  add     rsp, 38h
0x1401c8e10  pop     r14
0x1401c8e12  pop     r12
0x1401c8e14  pop     rdi
0x1401c8e15  pop     rsi
0x1401c8e16  pop     rbp
0x1401c8e17  pop     rbx
0x1401c8e18  retn
```
