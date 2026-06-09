# StopHidDevice

- ea: `0x180006978`
- end: `0x180006a5e`
- name: `StopHidDevice`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800026b4`
- `0x18000351c`
- `0x180006460`

## callees

- `0x1800025b8`
- `0x180005680`
- `0x180006978`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800069f8`
- `KERNEL32!WaitForSingleObject` at `0x1800069f8`
- `KERNEL32!CloseHandle` at `0x180006a05`
- `KERNEL32!CloseHandle` at `0x180006a0e`
- `KERNEL32!CloseHandle` at `0x180006a05`
- `KERNEL32!CloseHandle` at `0x180006a0e`
- `KERNEL32!SetEvent` at `0x1800069ec`
- `KERNEL32!SetEvent` at `0x1800069ec`
- `USER32!UnregisterDeviceNotification` at `0x1800069ce`
- `USER32!UnregisterDeviceNotification` at `0x1800069ce`

## pseudocode

```c
__int64 __fastcall StopHidDevice(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v6; // rcx
  void *v7; // rbx
  __int64 v8; // r9

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, a4);
  }
  if ( !a1 )
    return 0;
  UnregisterDeviceNotification(*(HDEVNOTIFY *)(a1 + 112));
  v6 = *(void **)(a1 + 152);
  v7 = *(void **)(a1 + 176);
  *(_DWORD *)(a1 + 168) = 0;
  SetEvent(v6);
  WaitForSingleObject(v7, 0xFFFFFFFF);
  CloseHandle(*(HANDLE *)(a1 + 152));
  CloseHandle(v7);
  FreeHidDevice(a1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids, v8);
  }
  return 1;
}

```

## disassembly

```asm
0x180006978  mov     [rsp+arg_0], rbx
0x18000697d  mov     [rsp+arg_8], rsi
0x180006982  push    rdi
0x180006983  sub     rsp, 20h
0x180006987  mov     rdi, rcx
0x18000698a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006991  lea     rsi, WPP_GLOBAL_Control
0x180006998  cmp     rcx, rsi
0x18000699b  jz      short loc_1800069BE
0x18000699d  test    byte ptr [rcx+1Ch], 2
0x1800069a1  jz      short loc_1800069BE
0x1800069a3  cmp     byte ptr [rcx+19h], 5
0x1800069a7  jb      short loc_1800069BE
0x1800069a9  mov     rcx, [rcx+10h]
0x1800069ad  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x1800069b4  mov     edx, 2Dh ; '-'
0x1800069b9  call    WPP_SF_
0x1800069be  test    rdi, rdi
0x1800069c1  jnz     short loc_1800069CA
0x1800069c3  xor     eax, eax
0x1800069c5  jmp     loc_180006A4E
0x1800069ca  mov     rcx, [rdi+70h]; Handle
0x1800069ce  call    cs:__imp_UnregisterDeviceNotification
0x1800069d4  mov     rcx, [rdi+98h]; hEvent
0x1800069db  mov     rbx, [rdi+0B0h]
0x1800069e2  mov     dword ptr [rdi+0A8h], 0
0x1800069ec  call    cs:__imp_SetEvent
0x1800069f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800069f5  mov     rcx, rbx; hHandle
0x1800069f8  call    cs:__imp_WaitForSingleObject
0x1800069fe  mov     rcx, [rdi+98h]; hObject
0x180006a05  call    cs:__imp_CloseHandle
0x180006a0b  mov     rcx, rbx; hObject
0x180006a0e  call    cs:__imp_CloseHandle
0x180006a14  mov     rcx, rdi
0x180006a17  call    FreeHidDevice
0x180006a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a23  cmp     rcx, rsi
0x180006a26  jz      short loc_180006A49
0x180006a28  test    byte ptr [rcx+1Ch], 2
0x180006a2c  jz      short loc_180006A49
0x180006a2e  cmp     byte ptr [rcx+19h], 5
0x180006a32  jb      short loc_180006A49
0x180006a34  mov     rcx, [rcx+10h]
0x180006a38  lea     r8, WPP_b7b37cc440ef38719be152b4993e4e1c_Traceguids
0x180006a3f  mov     edx, 2Eh ; '.'
0x180006a44  call    WPP_SF_
0x180006a49  mov     eax, 1
0x180006a4e  mov     rbx, [rsp+28h+arg_0]
0x180006a53  mov     rsi, [rsp+28h+arg_8]
0x180006a58  add     rsp, 20h
0x180006a5c  pop     rdi
0x180006a5d  retn
```
