# PolicyManager::ReadEnabledState

- ea: `0x180023cb0`
- end: `0x180023e13`
- name: `PolicyManager::ReadEnabledState`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180021a80`

## callees

- `0x180023cb0`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180023dd9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180023dd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023cfd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023cfd`

## pseudocode

```c
__int64 __fastcall PolicyManager::ReadEnabledState(HKEY a1, const WCHAR *a2, const WCHAR *a3, _DWORD *a4)
{
  LSTATUS ValueW; // ebx
  int pvData; // [rsp+40h] [rbp-78h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-74h] BYREF
  _DWORD v9[2]; // [rsp+48h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-58h] BYREF
  char *v12; // [rsp+70h] [rbp-48h]
  int v13; // [rsp+78h] [rbp-40h]
  int v14; // [rsp+7Ch] [rbp-3Ch]
  _DWORD *v15; // [rsp+80h] [rbp-38h]
  __int64 v16; // [rsp+88h] [rbp-30h]

  pcbData = 4;
  pvData = 0;
  ValueW = RegGetValueW(a1, a2, a3, 0x10u, 0, &pvData, &pcbData);
  if ( !ValueW )
  {
    *a4 = pvData != 0;
    return 0;
  }
  if ( ValueW == 2 )
  {
    *a4 = 2;
    return 0;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    v9[0] = ValueW;
    v15 = v9;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_18006E008;
    v16 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_18006E008;
    v12 = byte_180062A55;
    UserData.Reserved = 2;
    v13 = 24;
    v14 = 1;
    v9[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( ValueW > 0 )
    return (unsigned __int16)ValueW | 0x80070000;
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x180023cb0  push    rbx
0x180023cb2  push    rsi
0x180023cb3  push    rdi
0x180023cb4  sub     rsp, 0A0h
0x180023cbb  mov     rax, cs:__security_cookie
0x180023cc2  xor     rax, rsp
0x180023cc5  mov     [rsp+0B8h+var_28], rax
0x180023ccd  lea     rax, [rsp+0B8h+var_74]
0x180023cd2  mov     [rsp+0B8h+var_74], 4
0x180023cda  mov     [rsp+0B8h+pcbData], rax; pcbData
0x180023cdf  mov     rdi, r9
0x180023ce2  lea     rax, [rsp+0B8h+var_78]
0x180023ce7  xor     esi, esi
0x180023ce9  mov     [rsp+0B8h+pvData], rax; pvData
0x180023cee  mov     r9d, 10h; dwFlags
0x180023cf4  mov     [rsp+0B8h+pdwType], rsi; pdwType
0x180023cf9  mov     [rsp+0B8h+var_78], esi
0x180023cfd  call    cs:__imp_RegGetValueW
0x180023d03  mov     ebx, eax
0x180023d05  test    eax, eax
0x180023d07  jnz     short loc_180023D19
0x180023d09  cmp     [rsp+0B8h+var_78], esi
0x180023d0d  mov     eax, esi
0x180023d0f  setnz   al
0x180023d12  mov     [rdi], eax
0x180023d14  jmp     loc_180023DF6
0x180023d19  cmp     ebx, 2
0x180023d1c  jz      loc_180023DF0
0x180023d22  mov     eax, cs:dword_18006E000
0x180023d28  cmp     eax, 2
0x180023d2b  jbe     loc_180023DDF
0x180023d31  lea     rax, [rsp+0B8h+var_70]
0x180023d36  mov     [rsp+0B8h+var_70], ebx
0x180023d3a  mov     [rsp+0B8h+var_38], rax
0x180023d42  lea     rcx, _TraceLoggingMetadata
0x180023d49  movzx   eax, cs:word_180062A4B
0x180023d50  lea     rdx, [rsp+0B8h+EventDescriptor]; EventDescriptor
0x180023d55  mov     dword ptr [rsp+0B8h+EventDescriptor.Level], eax
0x180023d59  xor     r9d, r9d; RelatedActivityId
0x180023d5c  mov     rax, cs:off_18006E008
0x180023d63  xor     r8d, r8d; ActivityId
0x180023d66  mov     [rsp+0B8h+UserData.Ptr], rax
0x180023d6b  mov     [rsp+0B8h+var_30], 4
0x180023d77  mov     dword ptr [rsp+0B8h+EventDescriptor.Id], 0B000000h
0x180023d7f  mov     [rsp+0B8h+EventDescriptor.Keyword], rsi
0x180023d84  movzx   eax, word ptr [rax]
0x180023d87  mov     [rsp+0B8h+UserData.Size], eax
0x180023d8b  lea     rax, byte_180062A55
0x180023d92  mov     [rsp+0B8h+var_48], rax
0x180023d97  lea     rax, _TraceLoggingMetadataEnd
0x180023d9e  sub     eax, ecx
0x180023da0  mov     dword ptr [rsp+0B8h+UserData.0Ch], 2
0x180023da8  mov     [rsp+0B8h+var_40], 18h
0x180023db0  mov     [rsp+0B8h+var_3C], 1
0x180023db8  mov     [rsp+0B8h+var_6C], eax
0x180023dbc  mov     eax, [rsp+0B8h+var_6C]
0x180023dc0  mov     rcx, cs:RegHandle; RegHandle
0x180023dc7  lea     rax, [rsp+0B8h+UserData]
0x180023dcc  mov     [rsp+0B8h+pvData], rax; UserData
0x180023dd1  mov     dword ptr [rsp+0B8h+pdwType], 3; UserDataCount
0x180023dd9  call    cs:__imp_EventWriteTransfer
0x180023ddf  test    ebx, ebx
0x180023de1  jle     short loc_180023DEC
0x180023de3  movzx   ebx, bx
0x180023de6  or      ebx, 80070000h
0x180023dec  mov     eax, ebx
0x180023dee  jmp     short loc_180023DF8
0x180023df0  mov     dword ptr [rdi], 2
0x180023df6  xor     eax, eax
0x180023df8  mov     rcx, [rsp+0B8h+var_28]
0x180023e00  xor     rcx, rsp; StackCookie
0x180023e03  call    __security_check_cookie
0x180023e08  add     rsp, 0A0h
0x180023e0f  pop     rdi
0x180023e10  pop     rsi
0x180023e11  pop     rbx
0x180023e12  retn
```
