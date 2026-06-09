# WppInitUm

- ea: `0x180012aa8`
- end: `0x180012b77`
- name: `WppInitUm`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180011df0`

## callees

- `0x180012aa8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180012b37`
- `ntdll!RtlInitUnicodeString` at `0x180012b37`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180012b0f`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180012b0f`
- `WppRecorderUM!WppAutoLogStart` at `0x180012b51`
- `WppRecorderUM!WppAutoLogStart` at `0x180012b51`

## string_xrefs

- `0x180012b26`: `Bluetooth Support Service`

## pseudocode

```c
__int64 *WppInitUm()
{
  _QWORD *v0; // rbx
  __int64 *v1; // rdi
  unsigned __int64 v2; // r8
  __int64 *result; // rax
  __int128 v4; // [rsp+40h] [rbp-28h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v0 = WPP_GLOBAL_Control;
  v1 = &WPP_REGISTRATION_GUIDS;
  v4 = 0;
  while ( v0 )
  {
    v2 = *v1++;
    v4 = v2;
    v0[4] = v2;
    ((void (__fastcall *)(__int64 (__fastcall *)(), _QWORD *, unsigned __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD *))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v0,
      v2,
      1,
      &v4,
      0,
      0,
      v0 + 1);
    v0 = (_QWORD *)*v0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Bluetooth Support Service");
  WppAutoLogStart(WPP_GLOBAL_Control, 0, &DestinationString);
  result = &WPP_MAIN_CB;
  WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  return result;
}

```

## disassembly

```asm
0x180012aa8  mov     [rsp+arg_0], rbx
0x180012aad  push    rdi
0x180012aae  sub     rsp, 60h
0x180012ab2  mov     rbx, cs:WPP_GLOBAL_Control
0x180012ab9  lea     rdi, WPP_REGISTRATION_GUIDS
0x180012ac0  xorps   xmm0, xmm0
0x180012ac3  movups  [rsp+68h+var_28], xmm0
0x180012ac8  jmp     short loc_180012B1E
0x180012aca  mov     r8, [rdi]
0x180012acd  lea     rax, [rbx+8]
0x180012ad1  and     qword ptr [rsp+68h+var_28+8], 0
0x180012ad7  lea     rcx, WppControlCallback
0x180012ade  mov     [rsp+68h+var_30], rax
0x180012ae3  lea     rdi, [rdi+8]
0x180012ae7  and     [rsp+68h+var_38], 0
0x180012aed  lea     rax, [rsp+68h+var_28]
0x180012af2  and     [rsp+68h+var_40], 0
0x180012af8  mov     r9d, 1
0x180012afe  mov     qword ptr [rsp+68h+var_28], r8
0x180012b03  mov     rdx, rbx
0x180012b06  mov     [rsp+68h+var_48], rax
0x180012b0b  mov     [rbx+20h], r8
0x180012b0f  call    cs:__imp_EtwRegisterTraceGuidsW
0x180012b16  nop     dword ptr [rax+rax+00h]
0x180012b1b  mov     rbx, [rbx]
0x180012b1e  test    rbx, rbx
0x180012b21  jnz     short loc_180012ACA
0x180012b23  xorps   xmm0, xmm0
0x180012b26  lea     rdx, SourceString; "Bluetooth Support Service"
0x180012b2d  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180012b32  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180012b37  call    cs:__imp_RtlInitUnicodeString
0x180012b3e  nop     dword ptr [rax+rax+00h]
0x180012b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b4a  lea     r8, [rsp+68h+DestinationString]
0x180012b4f  xor     edx, edx
0x180012b51  call    cs:__imp_WppAutoLogStart
0x180012b58  nop     dword ptr [rax+rax+00h]
0x180012b5d  mov     rbx, [rsp+68h+arg_0]
0x180012b62  lea     rax, WPP_MAIN_CB
0x180012b69  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x180012b70  add     rsp, 60h
0x180012b74  pop     rdi
0x180012b75  retn
```
