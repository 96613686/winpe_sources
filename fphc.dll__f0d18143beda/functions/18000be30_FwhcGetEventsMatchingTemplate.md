# FwhcGetEventsMatchingTemplate

- ea: `0x18000be30`
- end: `0x18000bf36`
- name: `FwhcGetEventsMatchingTemplate`
- size: `262`
- prototype: `__int64 __fastcall(FWPM_NET_EVENT_ENUM_TEMPLATE0 *enumTemplate, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c154`

## callees

- `0x18000bc38`
- `0x18000be30`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18000bf1d`
- `fwpuclnt!FwpmEngineClose0` at `0x18000bf1d`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18000bea0`
- `fwpuclnt!FwpmNetEventCreateEnumHandle0` at `0x18000bea0`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18000bf0e`
- `fwpuclnt!FwpmNetEventDestroyEnumHandle0` at `0x18000bf0e`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000be79`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000be79`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18000bece`
- `fwpuclnt!FwpmNetEventEnum5` at `0x18000bece`

## pseudocode

```c
__int64 __fastcall FwhcGetEventsMatchingTemplate(
        FWPM_NET_EVENT_ENUM_TEMPLATE0 *enumTemplate,
        _QWORD *a2,
        unsigned int *a3)
{
  signed int v6; // eax
  signed int v7; // ebx
  char v8; // di
  signed int v9; // eax
  int v10; // eax
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  HANDLE engineHandle; // [rsp+70h] [rbp+30h] BYREF
  HANDLE enumHandle; // [rsp+88h] [rbp+48h] BYREF

  v12 = 0;
  engineHandle = 0;
  enumHandle = 0;
  v6 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    v9 = FwpmNetEventCreateEnumHandle0(engineHandle, enumTemplate, &enumHandle);
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
    if ( v7 >= 0 )
    {
      v10 = FwpmNetEventEnum5(engineHandle, enumHandle, 0xFFFFFFFFLL, &v12, a3);
      v7 = v10;
      if ( v10 > 0 )
        v7 = (unsigned __int16)v10 | 0x80070000;
      if ( v7 >= 0 )
      {
        *a2 = v12;
        FwhcDumpEvents(L"Matched events", *a3);
      }
    }
  }
  if ( enumHandle )
    FwpmNetEventDestroyEnumHandle0(engineHandle, enumHandle);
  if ( v8 )
    FwpmEngineClose0(engineHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000be30  mov     [rsp-28h+arg_8], rbx
0x18000be35  push    rbp
0x18000be36  push    rsi
0x18000be37  push    rdi
0x18000be38  push    r14
0x18000be3a  push    r15
0x18000be3c  mov     rbp, rsp
0x18000be3f  sub     rsp, 40h
0x18000be43  xor     r9d, r9d; session
0x18000be46  mov     [rbp+var_10], 0
0x18000be4e  mov     rsi, r8
0x18000be51  mov     [rbp+arg_0], 0
0x18000be59  mov     r15, rdx
0x18000be5c  mov     [rbp+enumHandle], 0
0x18000be64  mov     r14, rcx
0x18000be67  lea     rax, [rbp+arg_0]
0x18000be6b  lea     edx, [r9+0Ah]; authnService
0x18000be6f  mov     [rsp+40h+engineHandle], rax; engineHandle
0x18000be74  xor     r8d, r8d; authIdentity
0x18000be77  xor     ecx, ecx; serverName
0x18000be79  call    cs:__imp_FwpmEngineOpen0
0x18000be7f  mov     ebx, eax
0x18000be81  test    eax, eax
0x18000be83  jle     short loc_18000BE8E
0x18000be85  movzx   ebx, ax
0x18000be88  or      ebx, 80070000h
0x18000be8e  test    ebx, ebx
0x18000be90  js      short loc_18000BEFE
0x18000be92  mov     rcx, [rbp+arg_0]; engineHandle
0x18000be96  lea     r8, [rbp+enumHandle]; enumHandle
0x18000be9a  mov     rdx, r14; enumTemplate
0x18000be9d  mov     dil, 1
0x18000bea0  call    cs:__imp_FwpmNetEventCreateEnumHandle0
0x18000bea6  mov     ebx, eax
0x18000bea8  test    eax, eax
0x18000beaa  jle     short loc_18000BEB5
0x18000beac  movzx   ebx, ax
0x18000beaf  or      ebx, 80070000h
0x18000beb5  test    ebx, ebx
0x18000beb7  js      short loc_18000BF01
0x18000beb9  mov     rdx, [rbp+enumHandle]
0x18000bebd  lea     r9, [rbp+var_10]
0x18000bec1  mov     rcx, [rbp+arg_0]
0x18000bec5  or      r8d, 0FFFFFFFFh
0x18000bec9  mov     [rsp+40h+engineHandle], rsi
0x18000bece  call    cs:__imp_FwpmNetEventEnum5
0x18000bed4  mov     ebx, eax
0x18000bed6  test    eax, eax
0x18000bed8  jle     short loc_18000BEE3
0x18000beda  movzx   ebx, ax
0x18000bedd  or      ebx, 80070000h
0x18000bee3  test    ebx, ebx
0x18000bee5  js      short loc_18000BF01
0x18000bee7  mov     r8, [rbp+var_10]
0x18000beeb  lea     rcx, aMatchedEvents; "Matched events"
0x18000bef2  mov     [r15], r8
0x18000bef5  mov     edx, [rsi]
0x18000bef7  call    FwhcDumpEvents
0x18000befc  jmp     short loc_18000BF01
0x18000befe  xor     dil, dil
0x18000bf01  mov     rdx, [rbp+enumHandle]; enumHandle
0x18000bf05  test    rdx, rdx
0x18000bf08  jz      short loc_18000BF14
0x18000bf0a  mov     rcx, [rbp+arg_0]; engineHandle
0x18000bf0e  call    cs:__imp_FwpmNetEventDestroyEnumHandle0
0x18000bf14  test    dil, dil
0x18000bf17  jz      short loc_18000BF23
0x18000bf19  mov     rcx, [rbp+arg_0]; engineHandle
0x18000bf1d  call    cs:__imp_FwpmEngineClose0
0x18000bf23  mov     eax, ebx
0x18000bf25  mov     rbx, [rsp+40h+arg_8]
0x18000bf2a  add     rsp, 40h
0x18000bf2e  pop     r15
0x18000bf30  pop     r14
0x18000bf32  pop     rdi
0x18000bf33  pop     rsi
0x18000bf34  pop     rbp
0x18000bf35  retn
```
