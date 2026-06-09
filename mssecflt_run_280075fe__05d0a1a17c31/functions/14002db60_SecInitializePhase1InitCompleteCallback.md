# SecInitializePhase1InitCompleteCallback

- ea: `0x14002db60`
- end: `0x14002dc0b`
- name: `SecInitializePhase1InitCompleteCallback`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002dc0c`

## callees

- `0x140011650`
- `0x14002db60`

## import_xrefs

- `ntoskrnl!ExCreateCallback` at `0x14002dbb3`
- `ntoskrnl!ExCreateCallback` at `0x14002dbb3`
- `ntoskrnl!ExRegisterCallback` at `0x14002dbd9`
- `ntoskrnl!ExRegisterCallback` at `0x14002dbd9`

## pseudocode

```c
NTSTATUS SecInitializePhase1InitCompleteCallback()
{
  NTSTATUS result; // eax
  struct _OBJECT_ATTRIBUTES v1; // [rsp+20h] [rbp-48h] BYREF

  *(_QWORD *)&v1.Length = 48;
  v1.ObjectName = (PUNICODE_STRING)L"8:";
  *(_QWORD *)&v1.Attributes = 80;
  v1.RootDirectory = 0;
  *(_OWORD *)&v1.SecurityDescriptor = 0;
  result = ExCreateCallback(&Object, &v1, 1u, 1u);
  if ( result >= 0 )
  {
    CallbackRegistration = ExRegisterCallback(Object, (PCALLBACK_FUNCTION)SecFinalizeSystemProcessContext, 0);
    return CallbackRegistration == 0 ? 0xC0000001 : 0;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x14002db60  mov     r11, rsp
0x14002db63  sub     rsp, 68h
0x14002db67  mov     rax, cs:__security_cookie
0x14002db6e  xor     rax, rsp
0x14002db71  mov     [rsp+68h+var_18], rax
0x14002db76  lea     rax, SecPhase1InitCompleteCallbackName; "8:"
0x14002db7d  mov     qword ptr [r11-48h], 30h ; '0'
0x14002db85  mov     r9b, 1; AllowMultipleCallbacks
0x14002db88  mov     [r11-38h], rax
0x14002db8c  xorps   xmm0, xmm0
0x14002db8f  mov     qword ptr [r11-30h], 50h ; 'P'
0x14002db97  mov     qword ptr [r11-40h], 0
0x14002db9f  lea     rdx, [r11-48h]; ObjectAttributes
0x14002dba3  mov     r8b, r9b; Create
0x14002dba6  lea     rcx, Object; CallbackObject
0x14002dbad  movdqu  [rsp+68h+var_28], xmm0
0x14002dbb3  call    cs:__imp_ExCreateCallback
0x14002dbba  nop     dword ptr [rax+rax+00h]
0x14002dbbf  test    eax, eax
0x14002dbc1  jns     short loc_14002DBC8
0x14002dbc3  lfence
0x14002dbc6  jmp     short loc_14002DBF8
0x14002dbc8  mov     rcx, cs:Object; CallbackObject
0x14002dbcf  lea     rdx, SecFinalizeSystemProcessContext; CallbackFunction
0x14002dbd6  xor     r8d, r8d; CallbackContext
0x14002dbd9  call    cs:__imp_ExRegisterCallback
0x14002dbe0  nop     dword ptr [rax+rax+00h]
0x14002dbe5  mov     cs:CallbackRegistration, rax
0x14002dbec  neg     rax
0x14002dbef  sbb     eax, eax
0x14002dbf1  not     eax
0x14002dbf3  and     eax, 0C0000001h
0x14002dbf8  mov     rcx, [rsp+68h+var_18]
0x14002dbfd  xor     rcx, rsp; StackCookie
0x14002dc00  call    __security_check_cookie
0x14002dc05  add     rsp, 68h
0x14002dc09  retn
```
