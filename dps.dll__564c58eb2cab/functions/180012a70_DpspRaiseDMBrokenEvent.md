# DpspRaiseDMBrokenEvent

- ea: `0x180012a70`
- end: `0x180012b6e`
- name: `DpspRaiseDMBrokenEvent`
- size: `254`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c784`

## callees

- `0x180009090`
- `0x180009fb0`
- `0x180012a70`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180012af5`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180012af5`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012b48`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180012b48`

## pseudocode

```c
__int64 __fastcall DpspRaiseDMBrokenEvent(__int64 a1, __int64 a2, int a3)
{
  unsigned int v4; // ebx
  _BYTE UserData[24]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v7; // [rsp+48h] [rbp-28h]
  __int64 v8; // [rsp+58h] [rbp-18h]
  int v9; // [rsp+90h] [rbp+20h] BYREF

  v9 = a3;
  memset(UserData, 0, sizeof(UserData));
  v8 = 0;
  v7 = 0;
  if ( a2 )
  {
    v4 = 0;
    if ( EventEnabled(g_hETW, &WDI_DPS_EVENT_DM_BROKEN) )
    {
      *(_QWORD *)UserData = *(_QWORD *)(a2 + 128);
      *(_QWORD *)&UserData[8] = *(unsigned int *)(a2 + 148);
      *((_QWORD *)&v7 + 1) = &v9;
      *(_QWORD *)&UserData[16] = a2;
      *(_QWORD *)&v7 = 16;
      v8 = 4;
      EventWrite(g_hETW, &WDI_DPS_EVENT_DM_BROKEN, 3u, (PEVENT_DATA_DESCRIPTOR)UserData);
    }
  }
  else
  {
    v4 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (int)L"DpspRaiseDMBrokenEvent",
      628,
      (int)L"Error = %d",
      87);
  }
  return v4;
}

```

## disassembly

```asm
0x180012a70  mov     [rsp-8+arg_0], rbx
0x180012a75  mov     [rsp-8+arg_8], rdi
0x180012a7a  mov     [rsp-8+arg_10], r8d
0x180012a7f  push    rbp
0x180012a80  mov     rbp, rsp
0x180012a83  sub     rsp, 70h
0x180012a87  mov     rax, cs:__security_cookie
0x180012a8e  xor     rax, rsp
0x180012a91  mov     [rbp+var_10], rax
0x180012a95  xor     eax, eax
0x180012a97  mov     qword ptr [rbp+UserData], 0
0x180012a9f  mov     [rbp+var_18], rax
0x180012aa3  xorps   xmm0, xmm0
0x180012aa6  mov     rdi, rdx
0x180012aa9  movups  xmmword ptr [rbp+UserData+8], xmm0
0x180012aad  movups  [rbp+var_28], xmm0
0x180012ab1  test    rdx, rdx
0x180012ab4  jnz     short loc_180012AE5
0x180012ab6  lea     r9, aErrorD; "Error = %d"
0x180012abd  mov     dword ptr [rsp+70h+Args], 57h ; 'W'; Args
0x180012ac5  mov     r8d, 274h; int
0x180012acb  lea     rdx, aDpspraisedmbro; "DpspRaiseDMBrokenEvent"
0x180012ad2  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012ad9  mov     ebx, 80070057h
0x180012ade  call    WdipTraceError
0x180012ae3  jmp     short loc_180012B4E
0x180012ae5  mov     rcx, cs:g_hETW; RegHandle
0x180012aec  lea     rdx, WDI_DPS_EVENT_DM_BROKEN; EventDescriptor
0x180012af3  xor     ebx, ebx
0x180012af5  call    cs:__imp_EventEnabled
0x180012afb  test    al, al
0x180012afd  jz      short loc_180012B4E
0x180012aff  mov     rax, [rdi+80h]
0x180012b06  lea     r9, [rbp+UserData]; UserData
0x180012b0a  mov     rcx, cs:g_hETW; RegHandle
0x180012b11  lea     r8d, [rbx+3]; UserDataCount
0x180012b15  mov     qword ptr [rbp+UserData], rax
0x180012b19  lea     rdx, WDI_DPS_EVENT_DM_BROKEN; EventDescriptor
0x180012b20  mov     eax, [rdi+94h]
0x180012b26  mov     dword ptr [rbp+UserData+8], eax
0x180012b29  lea     rax, [rbp+arg_10]
0x180012b2d  mov     qword ptr [rbp+var_28+8], rax
0x180012b31  mov     dword ptr [rbp+UserData+0Ch], ebx
0x180012b34  mov     qword ptr [rbp+UserData+10h], rdi
0x180012b38  mov     qword ptr [rbp+var_28], 10h
0x180012b40  mov     [rbp+var_18], 4
0x180012b48  call    cs:__imp_EventWrite
0x180012b4e  mov     eax, ebx
0x180012b50  mov     rcx, [rbp+var_10]
0x180012b54  xor     rcx, rsp; StackCookie
0x180012b57  call    __security_check_cookie
0x180012b5c  lea     r11, [rsp+70h+var_s0]
0x180012b61  mov     rbx, [r11+10h]
0x180012b65  mov     rdi, [r11+18h]
0x180012b69  mov     rsp, r11
0x180012b6c  pop     rbp
0x180012b6d  retn
```
