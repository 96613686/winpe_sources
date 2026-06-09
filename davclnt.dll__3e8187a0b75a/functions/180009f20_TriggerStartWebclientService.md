# TriggerStartWebclientService

- ea: `0x180009f20`
- end: `0x180009fe1`
- name: `TriggerStartWebclientService`
- size: `193`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180004340`
- `0x180007ad0`

## callees

- `0x180009f20`
- `0x180010be8`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180009f40`
- `ntdll!EtwEventRegister` at `0x180009f40`
- `ntdll!EtwEventWrite` at `0x180009f91`
- `ntdll!EtwEventWrite` at `0x180009f91`
- `ntdll!EtwEventUnregister` at `0x180009fd3`
- `ntdll!EtwEventUnregister` at `0x180009fd3`

## pseudocode

```c
__int64 TriggerStartWebclientService()
{
  unsigned int v0; // ebx
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v0 = EtwEventRegister(MS_Windows_WebClntLookupServiceTrigger_Provider, 0, 0, &v2);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v0);
  }
  else
  {
    v0 = EtwEventWrite(v2, WebClntLookupServiceTriggerEvent, 0, 0);
    if ( v0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v0);
    EtwEventUnregister(v2);
  }
  return v0;
}

```

## disassembly

```asm
0x180009f20  push    rbx
0x180009f22  sub     rsp, 20h
0x180009f26  lea     r9, [rsp+28h+arg_0]
0x180009f2b  mov     [rsp+28h+arg_0], 0
0x180009f34  xor     r8d, r8d
0x180009f37  lea     rcx, MS_Windows_WebClntLookupServiceTrigger_Provider
0x180009f3e  xor     edx, edx
0x180009f40  call    cs:__imp_EtwEventRegister
0x180009f46  mov     ebx, eax
0x180009f48  test    eax, eax
0x180009f4a  jz      short loc_180009F7F
0x180009f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f53  lea     rax, WPP_GLOBAL_Control
0x180009f5a  cmp     rcx, rax
0x180009f5d  jz      short loc_180009FD9
0x180009f5f  test    byte ptr [rcx+1Ch], 1
0x180009f63  jz      short loc_180009FD9
0x180009f65  mov     rcx, [rcx+10h]
0x180009f69  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180009f70  mov     edx, 0Ah
0x180009f75  mov     r9d, ebx
0x180009f78  call    WPP_SF_d
0x180009f7d  jmp     short loc_180009FD9
0x180009f7f  mov     rcx, [rsp+28h+arg_0]
0x180009f84  lea     rdx, WebClntLookupServiceTriggerEvent
0x180009f8b  xor     r9d, r9d
0x180009f8e  xor     r8d, r8d
0x180009f91  call    cs:__imp_EtwEventWrite
0x180009f97  mov     ebx, eax
0x180009f99  test    eax, eax
0x180009f9b  jz      short loc_180009FCE
0x180009f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fa4  lea     rax, WPP_GLOBAL_Control
0x180009fab  cmp     rcx, rax
0x180009fae  jz      short loc_180009FCE
0x180009fb0  test    byte ptr [rcx+1Ch], 1
0x180009fb4  jz      short loc_180009FCE
0x180009fb6  mov     rcx, [rcx+10h]
0x180009fba  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180009fc1  mov     edx, 0Bh
0x180009fc6  mov     r9d, ebx
0x180009fc9  call    WPP_SF_d
0x180009fce  mov     rcx, [rsp+28h+arg_0]
0x180009fd3  call    cs:__imp_EtwEventUnregister
0x180009fd9  mov     eax, ebx
0x180009fdb  add     rsp, 20h
0x180009fdf  pop     rbx
0x180009fe0  retn
```
