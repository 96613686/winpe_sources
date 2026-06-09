# RasImpersonateUser

- ea: `0x18000de20`
- end: `0x18000df75`
- name: `RasImpersonateUser`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e0c0`
- `0x180052b1c`
- `0x180055174`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000de20`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18000ded2`
- `ntdll!NtSetInformationThread` at `0x18000ded2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de90`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000de80`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000de80`

## pseudocode

```c
__int64 __fastcall RasImpersonateUser(HANDLE ExistingTokenHandle)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  struct _LIST_ENTRY *v4; // rcx
  __int64 v5; // rdx
  void *DuplicateTokenHandle; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 10, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    LastError = NtSetInformationThread(
                  (HANDLE)0xFFFFFFFFFFFFFFFELL,
                  ThreadImpersonationToken,
                  &DuplicateTokenHandle,
                  8u);
    v3 = LastError;
    if ( !LastError )
    {
LABEL_16:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v5 = 12;
      goto LABEL_15;
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v5 = 11;
LABEL_15:
      WPP_SF_d(v4[1].Flink, v5, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      goto LABEL_16;
    }
  }
LABEL_17:
  if ( DuplicateTokenHandle )
  {
    CloseHandle(DuplicateTokenHandle);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v4[1].Blink) & 0x2000) != 0
    && BYTE1(v4[1].Blink) >= 6u )
  {
    WPP_SF_d(v4[1].Flink, 13, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000de20  mov     [rsp+arg_0], rbx
0x18000de25  mov     [rsp+arg_10], rsi
0x18000de2a  push    rdi
0x18000de2b  sub     rsp, 20h
0x18000de2f  mov     rbx, rcx
0x18000de32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de39  lea     rsi, WPP_GLOBAL_Control
0x18000de40  mov     edi, 2000h
0x18000de45  cmp     rcx, rsi
0x18000de48  jz      short loc_18000DE6A
0x18000de4a  test    [rcx+1Ch], edi
0x18000de4d  jz      short loc_18000DE6A
0x18000de4f  cmp     byte ptr [rcx+19h], 6
0x18000de53  jb      short loc_18000DE6A
0x18000de55  mov     rcx, [rcx+10h]
0x18000de59  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000de60  mov     edx, 0Ah
0x18000de65  call    WPP_SF_
0x18000de6a  lea     r8, [rsp+28h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18000de6f  mov     [rsp+28h+DuplicateTokenHandle], 0
0x18000de78  mov     edx, 2; ImpersonationLevel
0x18000de7d  mov     rcx, rbx; ExistingTokenHandle
0x18000de80  call    cs:__imp_DuplicateToken
0x18000de87  nop     dword ptr [rax+rax+00h]
0x18000de8c  test    eax, eax
0x18000de8e  jnz     short loc_18000DEBC
0x18000de90  call    cs:__imp_GetLastError
0x18000de97  nop     dword ptr [rax+rax+00h]
0x18000de9c  mov     ebx, eax
0x18000de9e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dea5  cmp     rcx, rsi
0x18000dea8  jz      short loc_18000DF1A
0x18000deaa  test    [rcx+1Ch], edi
0x18000dead  jz      short loc_18000DF1A
0x18000deaf  cmp     byte ptr [rcx+19h], 2
0x18000deb3  jb      short loc_18000DF1A
0x18000deb5  mov     edx, 0Bh
0x18000deba  jmp     short loc_18000DF00
0x18000debc  mov     r9d, 8; ThreadInformationLength
0x18000dec2  lea     r8, [rsp+28h+DuplicateTokenHandle]; ThreadInformation
0x18000dec7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000dece  lea     edx, [r9-3]; ThreadInformationClass
0x18000ded2  call    cs:__imp_NtSetInformationThread
0x18000ded9  nop     dword ptr [rax+rax+00h]
0x18000dede  mov     ebx, eax
0x18000dee0  test    eax, eax
0x18000dee2  jz      short loc_18000DF13
0x18000dee4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000deeb  cmp     rcx, rsi
0x18000deee  jz      short loc_18000DF1A
0x18000def0  test    [rcx+1Ch], edi
0x18000def3  jz      short loc_18000DF1A
0x18000def5  cmp     byte ptr [rcx+19h], 2
0x18000def9  jb      short loc_18000DF1A
0x18000defb  mov     edx, 0Ch
0x18000df00  mov     rcx, [rcx+10h]
0x18000df04  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000df0b  mov     r9d, eax
0x18000df0e  call    WPP_SF_d
0x18000df13  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df1a  mov     rax, [rsp+28h+DuplicateTokenHandle]
0x18000df1f  test    rax, rax
0x18000df22  jz      short loc_18000DF3A
0x18000df24  mov     rcx, rax; hObject
0x18000df27  call    cs:__imp_CloseHandle
0x18000df2e  nop     dword ptr [rax+rax+00h]
0x18000df33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df3a  cmp     rcx, rsi
0x18000df3d  jz      short loc_18000DF62
0x18000df3f  test    [rcx+1Ch], edi
0x18000df42  jz      short loc_18000DF62
0x18000df44  cmp     byte ptr [rcx+19h], 6
0x18000df48  jb      short loc_18000DF62
0x18000df4a  mov     rcx, [rcx+10h]
0x18000df4e  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000df55  mov     edx, 0Dh
0x18000df5a  mov     r9d, ebx
0x18000df5d  call    WPP_SF_d
0x18000df62  mov     rsi, [rsp+28h+arg_10]
0x18000df67  mov     eax, ebx
0x18000df69  mov     rbx, [rsp+28h+arg_0]
0x18000df6e  add     rsp, 20h
0x18000df72  pop     rdi
0x18000df73  retn
```
