# CWlanStatEngine::GetWlanConnectionAttributes(void)

- ea: `0x18000a730`
- end: `0x18000a80a`
- name: `?GetWlanConnectionAttributes@CWlanStatEngine@@IEAAJXZ`
- size: `218`
- prototype: `__int64 __fastcall(CWlanStatEngine *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007780`
- `0x180053af0`
- `0x18005985c`
- `0x180059d64`
- `0x18005a648`

## callees

- `0x18000a730`

## import_xrefs

- `wlanapi!WlanQueryInterface` at `0x18000a7be`
- `wlanapi!WlanQueryInterface` at `0x18000a7be`
- `wlanapi!WlanOpenHandle` at `0x18000a75e`
- `wlanapi!WlanOpenHandle` at `0x18000a75e`
- `wlanapi!WlanFreeMemory` at `0x18000a7ee`
- `wlanapi!WlanFreeMemory` at `0x18000a7ee`

## pseudocode

```c
__int64 __fastcall CWlanStatEngine::GetWlanConnectionAttributes(CWlanStatEngine *this)
{
  unsigned int v1; // ebx
  void **v2; // rsi
  signed int v4; // eax
  void *v5; // rcx
  signed int v6; // eax
  DWORD pdwNegotiatedVersion; // [rsp+60h] [rbp+8h] BYREF
  DWORD pdwDataSize; // [rsp+68h] [rbp+10h] BYREF
  PVOID ppData; // [rsp+70h] [rbp+18h] BYREF

  v1 = 0;
  pdwNegotiatedVersion = 0;
  v2 = (void **)((char *)this + 280);
  if ( !*((_QWORD *)this + 35) )
  {
    v4 = WlanOpenHandle(2u, 0, &pdwNegotiatedVersion, (PHANDLE)this + 35);
    if ( v4 )
    {
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
      else
        return (unsigned int)v4;
    }
    if ( pdwNegotiatedVersion != 2 )
      return (unsigned int)-2147023258;
  }
  v5 = *v2;
  pdwDataSize = 0;
  ppData = 0;
  v6 = WlanQueryInterface(
         v5,
         (const GUID *)((char *)this + 136),
         wlan_intf_opcode_current_connection,
         0,
         &pdwDataSize,
         &ppData,
         0);
  if ( v6 )
  {
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    else
      return (unsigned int)v6;
  }
  else
  {
    WlanFreeMemory(*((PVOID *)this + 36));
    *((_QWORD *)this + 36) = ppData;
  }
  return v1;
}

```

## disassembly

```asm
0x18000a730  push    rbx
0x18000a732  push    rsi
0x18000a733  push    rdi
0x18000a734  sub     rsp, 40h
0x18000a738  xor     ebx, ebx
0x18000a73a  mov     [rsp+58h+pdwNegotiatedVersion], 0
0x18000a742  lea     rsi, [rcx+118h]
0x18000a749  mov     rdi, rcx
0x18000a74c  cmp     [rsi], rbx
0x18000a74f  jnz     short loc_18000A77F
0x18000a751  mov     r9, rsi; phClientHandle
0x18000a754  lea     r8, [rsp+58h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x18000a759  xor     edx, edx; pReserved
0x18000a75b  lea     ecx, [rbx+2]; dwClientVersion
0x18000a75e  call    cs:__imp_WlanOpenHandle
0x18000a764  test    eax, eax
0x18000a766  jz      short loc_18000A7CE
0x18000a768  jg      short loc_18000A76E
0x18000a76a  mov     ebx, eax
0x18000a76c  jmp     short loc_18000A777
0x18000a76e  movzx   ebx, ax
0x18000a771  or      ebx, 80070000h
0x18000a777  test    ebx, ebx
0x18000a779  js      loc_18000A800
0x18000a77f  mov     rcx, [rsi]; hClientHandle
0x18000a782  lea     rax, [rsp+58h+arg_10]
0x18000a787  xor     r9d, r9d; pReserved
0x18000a78a  mov     [rsp+58h+pWlanOpcodeValueType], 0; pWlanOpcodeValueType
0x18000a793  mov     [rsp+58h+ppData], rax; ppData
0x18000a798  lea     rdx, [rdi+88h]; pInterfaceGuid
0x18000a79f  lea     rax, [rsp+58h+arg_8]
0x18000a7a4  mov     [rsp+58h+arg_8], 0
0x18000a7ac  mov     [rsp+58h+arg_10], 0
0x18000a7b5  lea     r8d, [r9+7]; OpCode
0x18000a7b9  mov     [rsp+58h+pdwDataSize], rax; pdwDataSize
0x18000a7be  call    cs:__imp_WlanQueryInterface
0x18000a7c4  test    eax, eax
0x18000a7c6  jz      short loc_18000A7E7
0x18000a7c8  jg      short loc_18000A7DC
0x18000a7ca  mov     ebx, eax
0x18000a7cc  jmp     short loc_18000A800
0x18000a7ce  cmp     [rsp+58h+pdwNegotiatedVersion], 2
0x18000a7d3  jz      short loc_18000A77F
0x18000a7d5  mov     ebx, 80070666h
0x18000a7da  jmp     short loc_18000A800
0x18000a7dc  movzx   ebx, ax
0x18000a7df  or      ebx, 80070000h
0x18000a7e5  jmp     short loc_18000A800
0x18000a7e7  mov     rcx, [rdi+120h]; pMemory
0x18000a7ee  call    cs:__imp_WlanFreeMemory
0x18000a7f4  mov     rcx, [rsp+58h+arg_10]
0x18000a7f9  mov     [rdi+120h], rcx
0x18000a800  mov     eax, ebx
0x18000a802  add     rsp, 40h
0x18000a806  pop     rdi
0x18000a807  pop     rsi
0x18000a808  pop     rbx
0x18000a809  retn
```
