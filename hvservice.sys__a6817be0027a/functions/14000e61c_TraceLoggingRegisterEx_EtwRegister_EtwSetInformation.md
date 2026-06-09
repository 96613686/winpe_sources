# TraceLoggingRegisterEx_EtwRegister_EtwSetInformation

- ea: `0x14000e61c`
- end: `0x14000e6c2`
- name: `TraceLoggingRegisterEx_EtwRegister_EtwSetInformation`
- size: `166`
- prototype: `__int64 __fastcall(char *CallbackContext, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140011760`
- `0x140015078`

## callees

- `0x140002ae0`
- `0x14000e61c`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14000e676`
- `ntoskrnl!EtwRegister` at `0x14000e676`
- `ntoskrnl!EtwSetInformation` at `0x14000e696`
- `ntoskrnl!EtwSetInformation` at `0x14000e696`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(char *CallbackContext, __int64 a2, __int64 a3)
{
  ULONGLONG *v3; // rsi
  bool v4; // zf
  unsigned int v6; // edi
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  v3 = (ULONGLONG *)(CallbackContext + 32);
  v4 = *((_QWORD *)CallbackContext + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
  if ( !v4 )
    __fastfail(5u);
  *((_QWORD *)CallbackContext + 5) = a2;
  *((_QWORD *)CallbackContext + 6) = a3;
  v6 = EtwRegister(&ProviderId, tlgEnableCallback, CallbackContext, v3);
  if ( !v6 )
    EtwSetInformation(
      *v3,
      EventProviderSetTraits,
      *((PVOID *)CallbackContext + 1),
      **((unsigned __int16 **)CallbackContext + 1));
  return v6;
}

```

## disassembly

```asm
0x14000e61c  mov     [rsp+arg_8], rbx
0x14000e621  mov     [rsp+arg_10], rsi
0x14000e626  push    rdi
0x14000e627  sub     rsp, 40h
0x14000e62b  mov     rax, cs:__security_cookie
0x14000e632  xor     rax, rsp
0x14000e635  mov     [rsp+48h+var_18], rax
0x14000e63a  mov     rax, [rcx+8]
0x14000e63e  lea     rsi, [rcx+20h]
0x14000e642  cmp     qword ptr [rsi], 0
0x14000e646  mov     rbx, rcx
0x14000e649  movups  xmm0, xmmword ptr [rax-10h]
0x14000e64d  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14000e653  jz      short loc_14000E65C
0x14000e655  mov     ecx, 5
0x14000e65a  int     29h; Win8: RtlFailFast(ecx)
0x14000e65c  mov     [rbx+28h], rdx
0x14000e660  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x14000e665  mov     [rbx+30h], r8
0x14000e669  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000e670  mov     r8, rbx; CallbackContext
0x14000e673  mov     r9, rsi; RegHandle
0x14000e676  call    cs:__imp_EtwRegister
0x14000e67d  nop     dword ptr [rax+rax+00h]
0x14000e682  mov     edi, eax
0x14000e684  test    eax, eax
0x14000e686  jnz     short loc_14000E6A2
0x14000e688  mov     r8, [rbx+8]; EventInformation
0x14000e68c  lea     edx, [rax+2]; InformationClass
0x14000e68f  mov     rcx, [rsi]; RegHandle
0x14000e692  movzx   r9d, word ptr [r8]; InformationLength
0x14000e696  call    cs:__imp_EtwSetInformation
0x14000e69d  nop     dword ptr [rax+rax+00h]
0x14000e6a2  mov     eax, edi
0x14000e6a4  mov     rcx, [rsp+48h+var_18]
0x14000e6a9  xor     rcx, rsp; StackCookie
0x14000e6ac  call    __security_check_cookie
0x14000e6b1  mov     rbx, [rsp+48h+arg_8]
0x14000e6b6  mov     rsi, [rsp+48h+arg_10]
0x14000e6bb  add     rsp, 40h
0x14000e6bf  pop     rdi
0x14000e6c0  retn
```
