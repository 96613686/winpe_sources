# McGenEventWrite_EventWriteTransfer

- ea: `0x18001ada8`
- end: `0x18001ae03`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180019dcc`
- `0x18001a1e0`
- `0x18001eb40`
- `0x18001f5ec`
- `0x1800208d8`
- `0x180020d0c`
- `0x1800210f4`
- `0x180021828`
- `0x180021b10`
- `0x1800268f0`
- `0x1800291e4`
- `0x18002b7cc`
- `0x18002b894`
- `0x18002b94c`
- `0x18002ba2c`
- `0x18002c99c`
- `0x18002ccd0`
- `0x18002cf60`

## callees

- `0x18001ada8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001adf1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001adf1`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // eax
  ULONG v7; // r8d

  v5 = (unsigned __int16 *)qword_18003A008;
  v6 = 0;
  if ( qword_18003A008 )
  {
    UserData->Ptr = qword_18003A008;
    v6 = 2;
    v7 = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v7 = 0;
  }
  UserData->Size = v7;
  UserData->Reserved = v6;
  return EventWriteTransfer(Microsoft_Windows_Kerberos_KdcProxy_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x18001ada8  sub     rsp, 38h
0x18001adac  mov     r8, cs:qword_18003A008
0x18001adb3  xor     eax, eax
0x18001adb5  mov     rcx, [rsp+38h+arg_20]
0x18001adba  test    r8, r8
0x18001adbd  jnz     short loc_18001ADC7
0x18001adbf  mov     [rcx], rax
0x18001adc2  mov     r8d, eax
0x18001adc5  jmp     short loc_18001ADD3
0x18001adc7  mov     [rcx], r8
0x18001adca  mov     eax, 2
0x18001adcf  movzx   r8d, word ptr [r8]
0x18001add3  mov     [rcx+8], r8d
0x18001add7  xor     r8d, r8d; ActivityId
0x18001adda  mov     [rsp+38h+UserData], rcx; UserData
0x18001addf  mov     [rcx+0Ch], eax
0x18001ade2  mov     rcx, cs:Microsoft_Windows_Kerberos_KdcProxy_Context; RegHandle
0x18001ade9  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x18001adee  xor     r9d, r9d; RelatedActivityId
0x18001adf1  call    cs:__imp_EventWriteTransfer
0x18001adf8  nop     dword ptr [rax+rax+00h]
0x18001adfd  add     rsp, 38h
0x18001ae01  retn
```
