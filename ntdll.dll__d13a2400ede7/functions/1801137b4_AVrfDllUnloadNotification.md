# AVrfDllUnloadNotification

- ea: `0x1801137b4`
- end: `0x180113871`
- name: `AVrfDllUnloadNotification`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180069678`

## callees

- `0x180007060`
- `0x18006ffa0`
- `0x180070490`
- `0x1800dbd8c`
- `0x18010ab7c`
- `0x1801137b4`
- `0x18016f020`

## string_xrefs

- `0x180113804`: `AVRF: AVrfDllUnloadNotification called for a provider (%p) \n`

## pseudocode

```c
struct _PEB *__fastcall AVrfDllUnloadNotification(__int64 a1)
{
  struct _PEB *result; // rax
  __int64 *v3; // rdi
  void (__fastcall *v4)(_QWORD, _QWORD, _QWORD, __int64); // rax

  result = NtCurrentPeb();
  if ( (result->NtGlobalFlag & 0x100) != 0 && AVrfpEnabled )
  {
    RtlEnterCriticalSection(AVrfpVerifierLock);
    if ( (unsigned __int8)AVrfpIsVerifierProviderDll(*(_QWORD *)(a1 + 48)) )
    {
      DbgPrint("AVRF: AVrfDllUnloadNotification called for a provider (%p) \n", (const void *)a1);
      __debugbreak();
    }
    if ( (int)AVrfpDllUnloadNotificationInternal(a1) >= 0 )
    {
      v3 = (__int64 *)AVrfpVerifierProvidersList;
      while ( v3 != &AVrfpVerifierProvidersList )
      {
        v4 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))v3[7];
        v3 = (__int64 *)*v3;
        if ( v4 )
          v4(*(_QWORD *)(a1 + 96), *(_QWORD *)(a1 + 48), *(unsigned int *)(a1 + 64), a1);
      }
    }
    return (struct _PEB *)RtlLeaveCriticalSection(AVrfpVerifierLock);
  }
  return result;
}

```

## disassembly

```asm
0x1801137b4  mov     [rsp+arg_0], rbx
0x1801137b9  mov     [rsp+arg_8], rsi
0x1801137be  push    rdi
0x1801137bf  sub     rsp, 30h
0x1801137c3  mov     rax, gs:60h
0x1801137cc  mov     rbx, rcx
0x1801137cf  test    dword ptr [rax+0BCh], 100h
0x1801137d9  jz      loc_180113860
0x1801137df  cmp     cs:AVrfpEnabled, 0
0x1801137e6  jz      short loc_180113860
0x1801137e8  lea     rcx, AVrfpVerifierLock
0x1801137ef  call    RtlEnterCriticalSection
0x1801137f4  mov     rcx, [rbx+30h]
0x1801137f8  call    AVrfpIsVerifierProviderDll
0x1801137fd  test    al, al
0x1801137ff  jz      short loc_180113813
0x180113801  mov     rdx, rbx
0x180113804  lea     rcx, aAvrfAvrfdllunl; "AVRF: AVrfDllUnloadNotification called "...
0x18011380b  call    DbgPrint
0x180113810  int     3; Trap to Debugger
0x180113811  jmp     short loc_180113854
0x180113813  mov     rcx, rbx
0x180113816  call    AVrfpDllUnloadNotificationInternal
0x18011381b  test    eax, eax
0x18011381d  js      short loc_180113854
0x18011381f  mov     rdi, cs:AVrfpVerifierProvidersList
0x180113826  lea     rsi, AVrfpVerifierProvidersList
0x18011382d  jmp     short loc_18011384F
0x18011382f  mov     rax, [rdi+38h]
0x180113833  mov     rdi, [rdi]
0x180113836  test    rax, rax
0x180113839  jz      short loc_18011384F
0x18011383b  mov     r8d, [rbx+40h]
0x18011383f  mov     r9, rbx
0x180113842  mov     rdx, [rbx+30h]
0x180113846  mov     rcx, [rbx+60h]
0x18011384a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011384f  cmp     rdi, rsi
0x180113852  jnz     short loc_18011382F
0x180113854  lea     rcx, AVrfpVerifierLock
0x18011385b  call    RtlLeaveCriticalSection
0x180113860  mov     rbx, [rsp+38h+arg_0]
0x180113865  mov     rsi, [rsp+38h+arg_8]
0x18011386a  add     rsp, 30h
0x18011386e  pop     rdi
0x18011386f  retn
```
