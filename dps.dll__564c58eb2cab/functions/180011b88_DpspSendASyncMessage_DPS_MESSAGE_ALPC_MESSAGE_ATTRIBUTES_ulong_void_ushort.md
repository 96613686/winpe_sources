# DpspSendASyncMessage(_DPS_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *,ulong,void *,ushort)

- ea: `0x180011b88`
- end: `0x180011c66`
- name: `?DpspSendASyncMessage@@YAJPEAU_DPS_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@KPEAXG@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct _DPS_MESSAGE *, struct _ALPC_MESSAGE_ATTRIBUTES *, unsigned int, void *, unsigned __int16)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001100`
- `0x1800057b0`
- `0x1800065b8`
- `0x180011580`
- `0x180011714`
- `0x1800118f0`
- `0x180011c6c`
- `0x180011eec`
- `0x180011fd4`

## callees

- `0x180009090`
- `0x180011b88`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180011c1e`
- `ntdll!RtlNtStatusToDosError` at `0x180011c1e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180011c0e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x180011c0e`

## pseudocode

```c
__int64 __fastcall DpspSendASyncMessage(
        struct _DPS_MESSAGE *a1,
        struct _ALPC_MESSAGE_ATTRIBUTES *a2,
        unsigned int a3,
        void *a4,
        unsigned __int16 a5)
{
  signed int Args; // ebx
  NTSTATUS v6; // eax
  signed int v7; // eax

  if ( a1 )
  {
    *((_DWORD *)a1 + 6) = 0;
    *((_DWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 1) = 0;
    *((_QWORD *)a1 + 2) = 0;
    *((_WORD *)a1 + 1) = a5;
    *(_WORD *)a1 = a5 - 40;
    v6 = NtAlpcSendWaitReceivePort(a4, a3, a1, a2, 0, 0, 0, 0);
    if ( v6 < 0 )
    {
      v7 = RtlNtStatusToDosError(v6);
      Args = v7;
      if ( v7 > 0 )
        Args = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      Args = 0;
    }
    if ( Args < 0 )
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
        (int)L"DpspSendASyncMessage",
        71,
        (int)L"Error = %d",
        Args);
  }
  else
  {
    Args = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
      (int)L"DpspSendASyncMessage",
      50,
      (int)L"Error = %d",
      87);
  }
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x180011b88  push    rbx
0x180011b8a  sub     rsp, 40h
0x180011b8e  mov     r11d, r8d
0x180011b91  mov     r8, rcx
0x180011b94  mov     r10, r9
0x180011b97  test    rcx, rcx
0x180011b9a  jnz     short loc_180011BB2
0x180011b9c  mov     ebx, 80070057h
0x180011ba1  mov     dword ptr [rsp+48h+Args], 57h ; 'W'
0x180011ba9  lea     r8d, [rcx+32h]
0x180011bad  jmp     loc_180011C44
0x180011bb2  mov     dword ptr [rcx+18h], 0
0x180011bb9  mov     r9, rdx
0x180011bbc  mov     dword ptr [rcx+4], 0
0x180011bc3  mov     edx, r11d
0x180011bc6  mov     qword ptr [rcx+8], 0
0x180011bce  mov     qword ptr [rcx+10h], 0
0x180011bd6  movzx   ecx, [rsp+48h+arg_20]
0x180011bdb  mov     [rsp+48h+var_10], 0
0x180011be4  mov     [r8+2], cx
0x180011be9  mov     [rsp+48h+var_18], 0
0x180011bf2  lea     eax, [rcx-28h]
0x180011bf5  mov     [rsp+48h+var_20], 0
0x180011bfe  mov     rcx, r10
0x180011c01  mov     [r8], ax
0x180011c05  mov     qword ptr [rsp+48h+Args], 0
0x180011c0e  call    cs:__imp_NtAlpcSendWaitReceivePort
0x180011c14  test    eax, eax
0x180011c16  js      short loc_180011C1C
0x180011c18  xor     ebx, ebx
0x180011c1a  jmp     short loc_180011C33
0x180011c1c  mov     ecx, eax; Status
0x180011c1e  call    cs:__imp_RtlNtStatusToDosError
0x180011c24  mov     ebx, eax
0x180011c26  test    eax, eax
0x180011c28  jle     short loc_180011C33
0x180011c2a  movzx   ebx, ax
0x180011c2d  or      ebx, 80070000h
0x180011c33  test    ebx, ebx
0x180011c35  jns     short loc_180011C5E
0x180011c37  movzx   ecx, bx
0x180011c3a  mov     r8d, 47h ; 'G'; int
0x180011c40  mov     dword ptr [rsp+48h+Args], ecx; Args
0x180011c44  lea     r9, aErrorD; "Error = %d"
0x180011c4b  lea     rdx, aDpspsendasyncm; "DpspSendASyncMessage"
0x180011c52  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180011c59  call    WdipTraceError
0x180011c5e  mov     eax, ebx
0x180011c60  add     rsp, 40h
0x180011c64  pop     rbx
0x180011c65  retn
```
