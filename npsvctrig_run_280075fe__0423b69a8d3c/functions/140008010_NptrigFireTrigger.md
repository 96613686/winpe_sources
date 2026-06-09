# NptrigFireTrigger

- ea: `0x140008010`
- end: `0x1400080d7`
- name: `NptrigFireTrigger`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a460`

## callees

- `0x1400015f0`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall NptrigFireTrigger(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rax
  __int64 **v5; // rdx
  __int64 **v6; // rax
  __int64 v7; // rdx
  const char **v8; // rdi
  unsigned int v9; // ebx

  v4 = (__int64 *)*a1;
  if ( *(__int64 **)(*a1 + 8) != a1
    || (v5 = (__int64 **)a1[1], *v5 != a1)
    || (*v5 = v4,
        v4[1] = (__int64)v5,
        v6 = (__int64 **)((char *)WPP_MAIN_CB.DeviceExtension + 8),
        v7 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1),
        *(PVOID *)(v7 + 8) != (char *)WPP_MAIN_CB.DeviceExtension + 8) )
  {
    __fastfail(3u);
  }
  *a1 = v7;
  a1[1] = (__int64)v6;
  *(_QWORD *)(v7 + 8) = a1;
  *v6 = a1;
  *((_DWORD *)a1 + 8) = 2;
  v8 = (const char **)(a1 + 3);
  if ( (Microsoft_Windows_EndpointTriggerProviderEnableBits & 1) != 0 )
    v9 = McTemplateK0zz_EtwWriteTransfer(
           (REGHANDLE *)&NPTRIG_ETW_PROVIDER_GUID_Context,
           (const EVENT_DESCRIPTOR *)ClientWaiting,
           a3,
           a4,
           *v8);
  else
    v9 = 0;
  if ( (WPP_MAIN_CB.DeviceType & 1) != 0 )
    McTemplateK0zz_EtwWriteTransfer(
      (REGHANDLE *)&SERVICE_TRIGGER_PERF_EVENT_GUID_Context,
      (const EVENT_DESCRIPTOR *)ServiceTriggerPerfServiceTriggered,
      a3,
      a4,
      *v8);
  return v9;
}

```

## disassembly

```asm
0x140008010  sub     rsp, 38h
0x140008014  mov     rax, [rcx]
0x140008017  cmp     [rax+8], rcx
0x14000801b  jnz     loc_1400080D0
0x140008021  mov     rdx, [rcx+8]
0x140008025  cmp     [rdx], rcx
0x140008028  jnz     loc_1400080D0
0x14000802e  mov     [rdx], rax
0x140008031  mov     [rax+8], rdx
0x140008035  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14000803c  add     rax, 8
0x140008040  mov     rdx, [rax]
0x140008043  cmp     [rdx+8], rax
0x140008047  jnz     loc_1400080D0
0x14000804d  mov     [rcx], rdx
0x140008050  mov     [rcx+8], rax
0x140008054  mov     [rdx+8], rcx
0x140008058  mov     [rax], rcx
0x14000805b  mov     dword ptr [rcx+20h], 2
0x140008062  test    cs:Microsoft_Windows_EndpointTriggerProviderEnableBits, 1
0x140008069  mov     [rsp+38h+arg_0], rbx
0x14000806e  mov     [rsp+38h+var_8], rdi
0x140008073  lea     rdi, [rcx+18h]
0x140008077  jz      short loc_140008098
0x140008079  mov     rax, [rdi]
0x14000807c  lea     rdx, ClientWaiting
0x140008083  lea     rcx, NPTRIG_ETW_PROVIDER_GUID_Context; int
0x14000808a  mov     [rsp+38h+var_18], rax; __int64
0x14000808f  call    McTemplateK0zz_EtwWriteTransfer
0x140008094  mov     ebx, eax
0x140008096  jmp     short loc_14000809A
0x140008098  xor     ebx, ebx
0x14000809a  test    byte ptr cs:WPP_MAIN_CB.DeviceType, 1
0x1400080a1  jz      short loc_1400080BE
0x1400080a3  mov     rax, [rdi]
0x1400080a6  lea     rdx, ServiceTriggerPerfServiceTriggered
0x1400080ad  lea     rcx, SERVICE_TRIGGER_PERF_EVENT_GUID_Context; int
0x1400080b4  mov     [rsp+38h+var_18], rax; __int64
0x1400080b9  call    McTemplateK0zz_EtwWriteTransfer
0x1400080be  mov     rdi, [rsp+38h+var_8]
0x1400080c3  mov     eax, ebx
0x1400080c5  mov     rbx, [rsp+38h+arg_0]
0x1400080ca  add     rsp, 38h
0x1400080ce  retn
0x1400080d0  mov     ecx, 3
0x1400080d5  int     29h; Win8: RtlFailFast(ecx)
```
