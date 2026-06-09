# NgcUtils::BuildFullRegKeyPath_0

- ea: `0x180024a20`
- end: `0x180024b69`
- name: `NgcUtils::BuildFullRegKeyPath_0`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024b70`

## callees

- `0x180005680`
- `0x180024a20`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024a5d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024b27`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180024b27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024b48`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024a4f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180024a4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::BuildFullRegKeyPath_0(PSID *a1, __int128 *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  LPWSTR StringSid; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v7[2]; // [rsp+38h] [rbp-60h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-48h] BYREF
  __int16 *v10; // [rsp+60h] [rbp-38h]
  int v11; // [rsp+68h] [rbp-30h]
  int v12; // [rsp+6Ch] [rbp-2Ch]
  _DWORD *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  StringSid = 0;
  if ( ConvertSidToStringSidW(*a1, &StringSid) )
  {
    v4 = NgcUtils::BuildFullRegKeyPath(StringSid, a2);
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v7[0] = v4;
      v13 = v7;
      v14 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      UserData.Reserved = 2;
      v10 = &word_180063816;
      v11 = 33;
      v12 = 1;
      v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v4;
}

```

## disassembly

```asm
0x180024a20  push    rbx
0x180024a22  sub     rsp, 90h
0x180024a29  mov     rax, cs:__security_cookie
0x180024a30  xor     rax, rsp
0x180024a33  mov     [rsp+98h+var_18], rax
0x180024a3b  mov     rbx, rdx
0x180024a3e  mov     [rsp+98h+StringSid], 0
0x180024a47  lea     rdx, [rsp+98h+StringSid]; StringSid
0x180024a4c  mov     rcx, [rcx]; Sid
0x180024a4f  call    cs:__imp_ConvertSidToStringSidW
0x180024a55  test    eax, eax
0x180024a57  jnz     loc_180024B2F
0x180024a5d  call    cs:__imp_GetLastError
0x180024a63  mov     ebx, eax
0x180024a65  test    eax, eax
0x180024a67  jle     short loc_180024A72
0x180024a69  movzx   ebx, ax
0x180024a6c  or      ebx, 80070000h
0x180024a72  mov     eax, cs:dword_18006E000
0x180024a78  cmp     eax, 2
0x180024a7b  jbe     loc_180024B3E
0x180024a81  mov     [rsp+98h+var_60], ebx
0x180024a85  lea     rax, [rsp+98h+var_60]
0x180024a8a  mov     [rsp+98h+var_28], rax
0x180024a8f  mov     [rsp+98h+var_20], 4
0x180024a98  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x180024aa0  movzx   eax, cs:word_18006380C
0x180024aa7  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x180024aab  mov     [rsp+98h+EventDescriptor.Keyword], 0
0x180024ab4  mov     rax, cs:off_18006E008
0x180024abb  mov     [rsp+98h+var_48.Ptr], rax
0x180024ac0  movzx   eax, word ptr [rax]
0x180024ac3  mov     [rsp+98h+var_48.Size], eax
0x180024ac7  mov     dword ptr [rsp+98h+var_48.0Ch], 2
0x180024acf  lea     rax, word_180063816
0x180024ad6  mov     [rsp+98h+var_38], rax
0x180024adb  mov     [rsp+98h+var_30], 21h ; '!'
0x180024ae3  mov     [rsp+98h+var_2C], 1
0x180024aeb  lea     rax, _TraceLoggingMetadataEnd
0x180024af2  lea     rcx, _TraceLoggingMetadata
0x180024af9  sub     eax, ecx
0x180024afb  mov     [rsp+98h+var_5C], eax
0x180024aff  mov     eax, [rsp+98h+var_5C]
0x180024b03  lea     rax, [rsp+98h+var_48]
0x180024b08  mov     [rsp+98h+UserData], rax; UserData
0x180024b0d  mov     [rsp+98h+UserDataCount], 3; UserDataCount
0x180024b15  xor     r9d, r9d; RelatedActivityId
0x180024b18  xor     r8d, r8d; ActivityId
0x180024b1b  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x180024b20  mov     rcx, cs:RegHandle; RegHandle
0x180024b27  call    cs:__imp_EventWriteTransfer
0x180024b2d  jmp     short loc_180024B3E
0x180024b2f  mov     rdx, rbx
0x180024b32  mov     rcx, [rsp+98h+StringSid]
0x180024b37  call    NgcUtils__BuildFullRegKeyPath
0x180024b3c  mov     ebx, eax
0x180024b3e  mov     rcx, [rsp+98h+StringSid]; hMem
0x180024b43  test    rcx, rcx
0x180024b46  jz      short loc_180024B4E
0x180024b48  call    cs:__imp_LocalFree
0x180024b4e  mov     eax, ebx
0x180024b50  mov     rcx, [rsp+98h+var_18]
0x180024b58  xor     rcx, rsp; StackCookie
0x180024b5b  call    __security_check_cookie
0x180024b60  add     rsp, 90h
0x180024b67  pop     rbx
0x180024b68  retn
```
