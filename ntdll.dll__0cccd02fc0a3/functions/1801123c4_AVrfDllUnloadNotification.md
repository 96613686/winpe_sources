# AVrfDllUnloadNotification

- ea: `0x1801123c4`
- end: `0x180112481`
- name: `AVrfDllUnloadNotification`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18004ca78`

## callees

- `0x180007060`
- `0x1800535c0`
- `0x180053ab0`
- `0x1800db30c`
- `0x180109bec`
- `0x1801123c4`
- `0x18016f020`

## string_xrefs

- `0x180112414`: `AVRF: AVrfDllUnloadNotification called for a provider (%p) \n`

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
0x1801123c4  mov     [rsp+arg_0], rbx
0x1801123c9  mov     [rsp+arg_8], rsi
0x1801123ce  push    rdi
0x1801123cf  sub     rsp, 30h
0x1801123d3  mov     rax, gs:60h
0x1801123dc  mov     rbx, rcx
0x1801123df  test    dword ptr [rax+0BCh], 100h
0x1801123e9  jz      loc_180112470
0x1801123ef  cmp     cs:AVrfpEnabled, 0
0x1801123f6  jz      short loc_180112470
0x1801123f8  lea     rcx, AVrfpVerifierLock
0x1801123ff  call    RtlEnterCriticalSection
0x180112404  mov     rcx, [rbx+30h]
0x180112408  call    AVrfpIsVerifierProviderDll
0x18011240d  test    al, al
0x18011240f  jz      short loc_180112423
0x180112411  mov     rdx, rbx
0x180112414  lea     rcx, aAvrfAvrfdllunl; "AVRF: AVrfDllUnloadNotification called "...
0x18011241b  call    DbgPrint
0x180112420  int     3; Trap to Debugger
0x180112421  jmp     short loc_180112464
0x180112423  mov     rcx, rbx
0x180112426  call    AVrfpDllUnloadNotificationInternal
0x18011242b  test    eax, eax
0x18011242d  js      short loc_180112464
0x18011242f  mov     rdi, cs:AVrfpVerifierProvidersList
0x180112436  lea     rsi, AVrfpVerifierProvidersList
0x18011243d  jmp     short loc_18011245F
0x18011243f  mov     rax, [rdi+38h]
0x180112443  mov     rdi, [rdi]
0x180112446  test    rax, rax
0x180112449  jz      short loc_18011245F
0x18011244b  mov     r8d, [rbx+40h]
0x18011244f  mov     r9, rbx
0x180112452  mov     rdx, [rbx+30h]
0x180112456  mov     rcx, [rbx+60h]
0x18011245a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011245f  cmp     rdi, rsi
0x180112462  jnz     short loc_18011243F
0x180112464  lea     rcx, AVrfpVerifierLock
0x18011246b  call    RtlLeaveCriticalSection
0x180112470  mov     rbx, [rsp+38h+arg_0]
0x180112475  mov     rsi, [rsp+38h+arg_8]
0x18011247a  add     rsp, 30h
0x18011247e  pop     rdi
0x18011247f  retn
```
