# PcwCreateInstance

- ea: `0x14000db70`
- end: `0x14000dbf8`
- name: `PcwCreateInstance`
- size: `136`
- prototype: `NTSTATUS __stdcall(PPCW_INSTANCE *Instance, PPCW_REGISTRATION Registration, PCUNICODE_STRING Name, ULONG Count, PPCW_DATA Data)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000d0b8`
- `0x14000d98c`
- `0x14000db70`

## pseudocode

```c
NTSTATUS __stdcall PcwCreateInstance(
        PPCW_INSTANCE *Instance,
        PPCW_REGISTRATION Registration,
        PCUNICODE_STRING Name,
        ULONG Count,
        PPCW_DATA Data)
{
  int v7; // eax
  NTSTATUS v8; // edi
  __int64 v9; // rdx

  v7 = _PCW_INSTANCE::Create(Instance, Registration, Name, Count, Data);
  v8 = v7;
  if ( v7 < 0 )
  {
    v9 = *((_QWORD *)Registration + 4);
    if ( !v9 )
      v9 = *((_QWORD *)Registration + 5);
    if ( (Microsoft_Windows_Diagnosis_PCWEnableBits & 1) != 0 )
      McTemplateU0qhzr1hzr3_EtwWriteTransfer(
        Name->Length >> 1,
        (const EVENT_DESCRIPTOR *)PcwCreateFail,
        v7,
        *(_WORD *)(v9 + 24) >> 1,
        *(_QWORD *)(v9 + 32),
        Name->Length >> 1,
        (__int64)Name->Buffer);
  }
  return v8;
}

```

## disassembly

```asm
0x14000db70  mov     [rsp+arg_0], rbx
0x14000db75  mov     [rsp+arg_8], rsi
0x14000db7a  push    rdi
0x14000db7b  sub     rsp, 40h
0x14000db7f  mov     rax, [rsp+48h+Data]
0x14000db84  mov     rsi, r8
0x14000db87  mov     [rsp+48h+var_28], rax; struct _PCW_DATA *
0x14000db8c  mov     rbx, rdx
0x14000db8f  call    ?Create@_PCW_INSTANCE@@SAJPEAPEAU1@PEBU_PCW_REGISTRATION@@PEBU_UNICODE_STRING@@KPEBU_PCW_DATA@@@Z; _PCW_INSTANCE::Create(_PCW_INSTANCE * *,_PCW_REGISTRATION const *,_UNICODE_STRING const *,ulong,_PCW_DATA const *)
0x14000db94  mov     edi, eax
0x14000db96  test    eax, eax
0x14000db98  jns     short loc_14000DBE5
0x14000db9a  mov     rdx, [rbx+20h]
0x14000db9e  test    rdx, rdx
0x14000dba1  jnz     short loc_14000DBA7
0x14000dba3  mov     rdx, [rbx+28h]
0x14000dba7  test    byte ptr cs:Microsoft_Windows_Diagnosis_PCWEnableBits, 1
0x14000dbae  jz      short loc_14000DBE5
0x14000dbb0  mov     rax, [rsi+8]
0x14000dbb4  mov     r8d, edi
0x14000dbb7  movzx   r9d, word ptr [rdx+18h]
0x14000dbbc  movzx   ecx, word ptr [rsi]
0x14000dbbf  mov     [rsp+48h+var_18], rax
0x14000dbc4  mov     rax, [rdx+20h]
0x14000dbc8  lea     rdx, PcwCreateFail
0x14000dbcf  shr     cx, 1
0x14000dbd2  mov     [rsp+48h+var_20], cx
0x14000dbd7  shr     r9w, 1
0x14000dbdb  mov     [rsp+48h+var_28], rax
0x14000dbe0  call    McTemplateU0qhzr1hzr3_EtwWriteTransfer
0x14000dbe5  mov     rbx, [rsp+48h+arg_0]
0x14000dbea  mov     eax, edi
0x14000dbec  mov     rsi, [rsp+48h+arg_8]
0x14000dbf1  add     rsp, 40h
0x14000dbf5  pop     rdi
0x14000dbf6  retn
```
