# DisableLibrary(HKEY__ *,ushort *,ulong)

- ea: `0x18000b008`
- end: `0x18000b0e2`
- name: `?DisableLibrary@@YAKPEAUHKEY__@@PEAGK@Z`
- size: `218`
- prototype: `unsigned int __fastcall(HKEY hKey, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b0e8`
- `0x18000e1a8`

## callees

- `0x18000b008`
- `0x18000c6f4`
- `0x18000c774`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b093`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b093`

## pseudocode

```c
__int64 __fastcall DisableLibrary(HKEY hKey, unsigned __int16 *a2, int a3)
{
  LSTATUS v6; // eax
  __int64 v7; // rcx
  __int64 *v8; // rdx
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = 0;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      26,
      (unsigned int)WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids,
      (_DWORD)a2,
      a3);
  Data = a3;
  if ( ((a3 - 1) & 0xFFFFFFFC) != 0 || a3 == 3 )
    Data = 1;
  v6 = RegSetValueExW(hKey, L"Disable Performance Counters", 0, 4u, (const BYTE *)&Data, 4u);
  if ( lEventLogLevel >= 1 )
  {
    if ( v6 )
    {
      if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
      {
        v8 = PERFLIB_LIBRARY_TEMP_DISABLED;
        goto LABEL_13;
      }
    }
    else if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
    {
      v8 = PERFLIB_LIBRARY_DISABLED;
LABEL_13:
      McTemplateU0z_EtwEventWriteTransfer(v7, v8, a2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b008  mov     rax, rsp
0x18000b00b  mov     [rax+8], rbx
0x18000b00f  mov     [rax+10h], rsi
0x18000b013  push    rdi
0x18000b014  sub     rsp, 30h
0x18000b018  mov     ebx, r8d
0x18000b01b  mov     dword ptr [rax+18h], 0
0x18000b022  mov     rdi, rdx
0x18000b025  mov     rsi, rcx
0x18000b028  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b02f  test    byte ptr [rcx+1Ch], 80h
0x18000b033  jz      short loc_18000B056
0x18000b035  cmp     byte ptr [rcx+19h], 2
0x18000b039  jb      short loc_18000B056
0x18000b03b  mov     rcx, [rcx+10h]
0x18000b03f  lea     r8, WPP_b75a7a59dad53afbcb57d559c4580c05_Traceguids
0x18000b046  mov     edx, 1Ah
0x18000b04b  mov     [rax-18h], ebx
0x18000b04e  mov     r9, rdi
0x18000b051  call    WPP_SF_Sd
0x18000b056  lea     eax, [rbx-1]
0x18000b059  mov     [rsp+38h+Data], ebx
0x18000b05d  test    eax, 0FFFFFFFCh
0x18000b062  jnz     short loc_18000B069
0x18000b064  cmp     ebx, 3
0x18000b067  jnz     short loc_18000B071
0x18000b069  mov     [rsp+38h+Data], 1
0x18000b071  mov     r9d, 4; dwType
0x18000b077  lea     rax, [rsp+38h+Data]
0x18000b07c  mov     [rsp+38h+cbData], r9d; cbData
0x18000b081  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x18000b088  xor     r8d, r8d; Reserved
0x18000b08b  mov     [rsp+38h+lpData], rax; lpData
0x18000b090  mov     rcx, rsi; hKey
0x18000b093  call    cs:__imp_RegSetValueExW
0x18000b099  cmp     cs:?lEventLogLevel@@3JA, 1; long lEventLogLevel
0x18000b0a0  jl      short loc_18000B0D0
0x18000b0a2  test    eax, eax
0x18000b0a4  jnz     short loc_18000B0B8
0x18000b0a6  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x18000b0ad  jz      short loc_18000B0D0
0x18000b0af  lea     rdx, PERFLIB_LIBRARY_DISABLED
0x18000b0b6  jmp     short loc_18000B0C8
0x18000b0b8  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x18000b0bf  jz      short loc_18000B0D0
0x18000b0c1  lea     rdx, PERFLIB_LIBRARY_TEMP_DISABLED
0x18000b0c8  mov     r8, rdi
0x18000b0cb  call    McTemplateU0z_EtwEventWriteTransfer
0x18000b0d0  mov     rbx, [rsp+38h+arg_0]
0x18000b0d5  xor     eax, eax
0x18000b0d7  mov     rsi, [rsp+38h+arg_8]
0x18000b0dc  add     rsp, 30h
0x18000b0e0  pop     rdi
0x18000b0e1  retn
```
