# NCSI_INTERFACE_ATTRIBUTES::GetWlanProfileName(ushort *)

- ea: `0x180021e98`
- end: `0x180021fe9`
- name: `?GetWlanProfileName@NCSI_INTERFACE_ATTRIBUTES@@AEAAKPEAG@Z`
- size: `337`
- prototype: `unsigned int(NCSI_INTERFACE_ATTRIBUTES *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180021c38`

## callees

- `0x180021e98`
- `0x18002283c`
- `0x180047240`
- `0x180048e84`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180021ef9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x180021ef9`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180021fc5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanCloseHandle` at `0x180021fc5`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180021fac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180021fac`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x180021f33`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanQueryInterface` at `0x180021f33`

## pseudocode

```c
__int64 __fastcall NCSI_INTERFACE_ATTRIBUTES::GetWlanProfileName(NCSI_INTERFACE_ATTRIBUTES *this, unsigned __int16 *a2)
{
  DWORD v5; // ebx
  unsigned __int64 v6; // r11
  int v7; // eax
  unsigned __int64 v8; // r11
  const unsigned __int16 *v9; // r8
  PVOID pMemory; // [rsp+40h] [rbp-20h] BYREF
  void *phClientHandle; // [rsp+48h] [rbp-18h] BYREF
  DWORD pdwNegotiatedVersion; // [rsp+50h] [rbp-10h] BYREF
  DWORD pdwDataSize; // [rsp+54h] [rbp-Ch] BYREF

  if ( !(unsigned __int8)IsWlanOpenHandlePresent() )
    return 1168;
  phClientHandle = 0;
  pMemory = 0;
  pdwNegotiatedVersion = 0;
  pdwDataSize = 0;
  v5 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, &phClientHandle);
  if ( !v5 )
  {
    v5 = WlanQueryInterface(
           phClientHandle,
           (const GUID *)((char *)this + 8),
           wlan_intf_opcode_current_connection,
           0,
           &pdwDataSize,
           &pMemory,
           0);
    if ( !v5 )
    {
      if ( pMemory == (PVOID)-8LL )
      {
        v5 = 1168;
      }
      else if ( (int)StringCchCopyW(a2, 0x101u, (const unsigned __int16 *)pMemory + 4) < 0 )
      {
        v7 = StringCchCopyW(a2, v6, (const unsigned __int16 *)pMemory + 4);
        v9 = (const unsigned __int16 *)((char *)pMemory + 8);
        if ( (v7 & 0x1FFF0000) == 0x70000 )
          v5 = (unsigned __int16)StringCchCopyW(a2, v8, v9);
        else
          v5 = StringCchCopyW(a2, v8, v9);
      }
    }
  }
  if ( pMemory )
  {
    WlanFreeMemory(pMemory);
    pMemory = 0;
  }
  if ( phClientHandle )
    WlanCloseHandle(phClientHandle, 0);
  return v5;
}

```

## disassembly

```asm
0x180021e98  mov     [rsp-18h+arg_10], rbx
0x180021e9d  push    rbp
0x180021e9e  push    rsi
0x180021e9f  push    rdi
0x180021ea0  mov     rbp, rsp
0x180021ea3  sub     rsp, 60h
0x180021ea7  mov     rax, cs:__security_cookie
0x180021eae  xor     rax, rsp
0x180021eb1  mov     [rbp+var_8], rax
0x180021eb5  mov     rdi, rdx
0x180021eb8  mov     rsi, rcx
0x180021ebb  call    IsWlanOpenHandlePresent
0x180021ec0  test    al, al
0x180021ec2  jnz     short loc_180021ECE
0x180021ec4  mov     eax, 490h
0x180021ec9  jmp     loc_180021FCD
0x180021ece  xor     edx, edx; pReserved
0x180021ed0  mov     [rbp+phClientHandle], 0
0x180021ed8  lea     r9, [rbp+phClientHandle]; phClientHandle
0x180021edc  mov     [rbp+pMemory], 0
0x180021ee4  lea     r8, [rbp+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180021ee8  mov     [rbp+pdwNegotiatedVersion], 0
0x180021eef  mov     [rbp+var_C], 0
0x180021ef6  lea     ecx, [rdx+2]; dwClientVersion
0x180021ef9  call    cs:__imp_WlanOpenHandle
0x180021eff  mov     ebx, eax
0x180021f01  test    eax, eax
0x180021f03  jnz     loc_180021FA3
0x180021f09  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021f0d  lea     rax, [rbp+pMemory]
0x180021f11  mov     [rsp+60h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x180021f1a  lea     rdx, [rsi+8]; pInterfaceGuid
0x180021f1e  mov     [rsp+60h+ppData], rax; ppData
0x180021f23  lea     r8d, [rbx+7]; OpCode
0x180021f27  lea     rax, [rbp+var_C]
0x180021f2b  xor     r9d, r9d; pReserved
0x180021f2e  mov     [rsp+60h+pdwDataSize], rax; pdwDataSize
0x180021f33  call    cs:__imp_WlanQueryInterface
0x180021f39  mov     ebx, eax
0x180021f3b  test    eax, eax
0x180021f3d  jnz     short loc_180021FA3
0x180021f3f  mov     r8, [rbp+pMemory]
0x180021f43  add     r8, 8; unsigned __int16 *
0x180021f47  jz      short loc_180021F9E
0x180021f49  mov     r11d, 101h
0x180021f4f  mov     rcx, rdi; unsigned __int16 *
0x180021f52  mov     edx, r11d; unsigned __int64
0x180021f55  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021f5a  test    eax, eax
0x180021f5c  jns     short loc_180021FA3
0x180021f5e  mov     r8, [rbp+pMemory]
0x180021f62  mov     rdx, r11; unsigned __int64
0x180021f65  add     r8, 8; unsigned __int16 *
0x180021f69  mov     rcx, rdi; unsigned __int16 *
0x180021f6c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021f71  mov     r8, [rbp+pMemory]
0x180021f75  and     eax, 1FFF0000h
0x180021f7a  add     r8, 8; unsigned __int16 *
0x180021f7e  mov     rdx, r11; unsigned __int64
0x180021f81  mov     rcx, rdi; unsigned __int16 *
0x180021f84  cmp     eax, 70000h
0x180021f89  jnz     short loc_180021F95
0x180021f8b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021f90  movzx   ebx, ax
0x180021f93  jmp     short loc_180021FA3
0x180021f95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021f9a  mov     ebx, eax
0x180021f9c  jmp     short loc_180021FA3
0x180021f9e  mov     ebx, 490h
0x180021fa3  mov     rcx, [rbp+pMemory]; pMemory
0x180021fa7  test    rcx, rcx
0x180021faa  jz      short loc_180021FBA
0x180021fac  call    cs:__imp_WlanFreeMemory
0x180021fb2  mov     [rbp+pMemory], 0
0x180021fba  mov     rcx, [rbp+phClientHandle]; hClientHandle
0x180021fbe  test    rcx, rcx
0x180021fc1  jz      short loc_180021FCB
0x180021fc3  xor     edx, edx; pReserved
0x180021fc5  call    cs:__imp_WlanCloseHandle
0x180021fcb  mov     eax, ebx
0x180021fcd  mov     rcx, [rbp+var_8]
0x180021fd1  xor     rcx, rsp; StackCookie
0x180021fd4  call    __security_check_cookie
0x180021fd9  mov     rbx, [rsp+60h+arg_10]
0x180021fe1  add     rsp, 60h
0x180021fe5  pop     rdi
0x180021fe6  pop     rsi
0x180021fe7  pop     rbp
0x180021fe8  retn
```
