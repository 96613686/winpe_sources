# CSpeakAccessibilityTextTask::RuntimeClassInitialize(IObjectCollection *,HWND__ *)

- ea: `0x180027054`
- end: `0x18002712a`
- name: `?RuntimeClassInitialize@CSpeakAccessibilityTextTask@@QEAAJPEAUIObjectCollection@@PEAUHWND__@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(CSpeakAccessibilityTextTask *__hidden this, struct IObjectCollection *, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026bc4`

## callees

- `0x180008b54`
- `0x18000ac48`
- `0x180027054`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027095`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800270bc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180027095`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800270bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027114`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180027114`

## string_xrefs

- `0x18002706c`: `SpeakAccessibilityText`

## pseudocode

```c
HRESULT __fastcall CSpeakAccessibilityTextTask::RuntimeClassInitialize(
        CSpeakAccessibilityTextTask *this,
        struct IObjectCollection *a2,
        HWND a3)
{
  HRESULT result; // eax
  HANDLE EventW; // rax
  HANDLE v8; // rax

  result = StringCchCopyW((unsigned __int16 *)this + 8, 0x104u, L"SpeakAccessibilityText");
  if ( result >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 76) = EventW;
    if ( EventW || (result = ResultFromKnownLastError(), result >= 0) )
    {
      v8 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 77) = v8;
      if ( v8 || (result = ResultFromKnownLastError(), result >= 0) )
      {
        *((_QWORD *)this + 72) = a2;
        ((void (__fastcall *)(struct IObjectCollection *))a2->lpVtbl->AddRef)(a2);
        *((_QWORD *)this + 75) = a3;
        return CoCreateInstance(&CLSID_SpVoice, 0, 1u, &GUID_6c44df74_72b9_4992_a1ec_ef996e0422d4, (LPVOID *)this + 71);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027054  mov     [rsp+arg_0], rbx
0x180027059  mov     [rsp+arg_8], rsi
0x18002705e  push    rdi
0x18002705f  sub     rsp, 30h
0x180027063  mov     rsi, r8
0x180027066  mov     rdi, rdx
0x180027069  mov     rbx, rcx
0x18002706c  lea     r8, aSpeakaccessibi; "SpeakAccessibilityText"
0x180027073  add     rcx, 10h; unsigned __int16 *
0x180027077  mov     edx, 104h; unsigned __int64
0x18002707c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027081  test    eax, eax
0x180027083  js      loc_18002711A
0x180027089  xor     r9d, r9d; lpName
0x18002708c  xor     r8d, r8d; bInitialState
0x18002708f  xor     ecx, ecx; lpEventAttributes
0x180027091  lea     edx, [r9+1]; bManualReset
0x180027095  call    cs:__imp_CreateEventW
0x18002709b  mov     [rbx+260h], rax
0x1800270a2  test    rax, rax
0x1800270a5  jnz     short loc_1800270B0
0x1800270a7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800270ac  test    eax, eax
0x1800270ae  js      short loc_18002711A
0x1800270b0  xor     r9d, r9d; lpName
0x1800270b3  xor     r8d, r8d; bInitialState
0x1800270b6  xor     ecx, ecx; lpEventAttributes
0x1800270b8  lea     edx, [r9+1]; bManualReset
0x1800270bc  call    cs:__imp_CreateEventW
0x1800270c2  mov     [rbx+268h], rax
0x1800270c9  test    rax, rax
0x1800270cc  jnz     short loc_1800270D7
0x1800270ce  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800270d3  test    eax, eax
0x1800270d5  js      short loc_18002711A
0x1800270d7  mov     [rbx+240h], rdi
0x1800270de  mov     rcx, rdi
0x1800270e1  mov     rax, [rdi]
0x1800270e4  mov     rax, [rax+8]
0x1800270e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ed  xor     edx, edx; pUnkOuter
0x1800270ef  mov     [rbx+258h], rsi
0x1800270f6  lea     rax, [rbx+238h]
0x1800270fd  lea     r9, _GUID_6c44df74_72b9_4992_a1ec_ef996e0422d4; riid
0x180027104  mov     [rsp+38h+ppv], rax; ppv
0x180027109  lea     rcx, CLSID_SpVoice; rclsid
0x180027110  lea     r8d, [rdx+1]; dwClsContext
0x180027114  call    cs:__imp_CoCreateInstance
0x18002711a  mov     rbx, [rsp+38h+arg_0]
0x18002711f  mov     rsi, [rsp+38h+arg_8]
0x180027124  add     rsp, 30h
0x180027128  pop     rdi
0x180027129  retn
```
