# NgcCachedCertPolicy::GetCertPolicy(bool,int *,int *)

- ea: `0x18001a5f0`
- end: `0x18001a7b2`
- name: `?GetCertPolicy@NgcCachedCertPolicy@@QEAAJ_NPEAH1@Z`
- size: `450`
- prototype: `__int64 __fastcall(NgcCachedCertPolicy *__hidden this, bool, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a5b0`

## callees

- `0x18001a5f0`
- `0x18001de44`
- `0x18002f338`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a758`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a758`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a624`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a665`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a665`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a711`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001a711`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18001a648`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18001a648`

## pseudocode

```c
__int64 __fastcall NgcCachedCertPolicy::GetCertPolicy(NgcCachedCertPolicy *this, char a2, int *a3, int *a4)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  _BOOL8 v9; // rcx
  DWORD LastError; // eax
  char v11; // al
  int refreshed; // ebx
  _BYTE v14[4]; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v15[3]; // [rsp+34h] [rbp-64h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-48h] BYREF
  void *v18; // [rsp+60h] [rbp-38h]
  int v19; // [rsp+68h] [rbp-30h]
  int v20; // [rsp+6Ch] [rbp-2Ch]
  _DWORD *v21; // [rsp+70h] [rbp-28h]
  __int64 v22; // [rsp+78h] [rbp-20h]

  AcquireSRWLockExclusive(&stru_18006EFA0);
  if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent(v8, v7) )
  {
    v14[0] = 0;
    if ( (unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v14) )
    {
      v9 = v14[0] != 0;
      if ( v9 != byte_18006EFAB )
        byte_18006EFA8 = 0;
      if ( v14[0] )
      {
        v11 = 1;
        goto LABEL_6;
      }
    }
    else if ( (unsigned int)dword_18006E000 > 3 )
    {
      LastError = GetLastError();
      v22 = 4;
      v15[0] = LastError;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v21 = v15;
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = (ULONGLONG)off_18006E008;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_18006E008;
      v18 = &unk_18005F550;
      UserData.Reserved = 2;
      v19 = 41;
      v20 = 1;
      v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v11 = 0;
LABEL_6:
    byte_18006EFAB = v11;
  }
  if ( a2 )
  {
    refreshed = 0;
    if ( byte_18006EFA8 )
      goto LABEL_11;
  }
  refreshed = NgcCachedCertPolicy::RefreshPolicy((NgcCachedCertPolicy *)v9);
  if ( refreshed >= 0 )
  {
    byte_18006EFA8 = 1;
LABEL_11:
    *a3 = (unsigned __int8)byte_18006EFA9;
    *a4 = (unsigned __int8)byte_18006EFAA;
  }
  ReleaseSRWLockExclusive(&stru_18006EFA0);
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x18001a5f0  mov     [rsp+arg_0], rbx
0x18001a5f5  mov     [rsp+arg_8], rsi
0x18001a5fa  push    rdi
0x18001a5fb  sub     rsp, 90h
0x18001a602  mov     rax, cs:__security_cookie
0x18001a609  xor     rax, rsp
0x18001a60c  mov     [rsp+98h+var_18], rax
0x18001a614  lea     rcx, stru_18006EFA0; SRWLock
0x18001a61b  mov     rsi, r9
0x18001a61e  mov     rdi, r8
0x18001a621  movzx   ebx, dl
0x18001a624  call    cs:__imp_AcquireSRWLockExclusive
0x18001a62a  call    IsWinStationIsSessionRemoteablePresent
0x18001a62f  test    al, al
0x18001a631  jz      loc_18001A71F
0x18001a637  lea     r8, [rsp+98h+var_68]
0x18001a63c  mov     [rsp+98h+var_68], 0
0x18001a641  mov     edx, 0FFFFFFFFh
0x18001a646  xor     ecx, ecx
0x18001a648  call    cs:__imp_WinStationIsSessionRemoteable
0x18001a64e  test    al, al
0x18001a650  jnz     loc_18001A785
0x18001a656  mov     eax, cs:dword_18006E000
0x18001a65c  cmp     eax, 3
0x18001a65f  jbe     loc_18001A717
0x18001a665  call    cs:__imp_GetLastError
0x18001a66b  mov     [rsp+98h+var_20], 4
0x18001a674  lea     rcx, _TraceLoggingMetadata
0x18001a67b  mov     [rsp+98h+var_64], eax
0x18001a67f  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x18001a684  lea     rax, [rsp+98h+var_64]
0x18001a689  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x18001a691  mov     [rsp+98h+var_28], rax
0x18001a696  xor     r9d, r9d; RelatedActivityId
0x18001a699  movzx   eax, cs:word_18005F546
0x18001a6a0  xor     r8d, r8d; ActivityId
0x18001a6a3  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18001a6a7  mov     rax, cs:off_18006E008
0x18001a6ae  mov     [rsp+98h+var_48.Ptr], rax
0x18001a6b3  mov     [rsp+98h+EventDescriptor.Keyword], 0
0x18001a6bc  movzx   eax, word ptr [rax]
0x18001a6bf  mov     [rsp+98h+var_48.Size], eax
0x18001a6c3  lea     rax, unk_18005F550
0x18001a6ca  mov     [rsp+98h+var_38], rax
0x18001a6cf  lea     rax, _TraceLoggingMetadataEnd
0x18001a6d6  sub     eax, ecx
0x18001a6d8  mov     dword ptr [rsp+98h+var_48.0Ch], 2
0x18001a6e0  mov     [rsp+98h+var_30], 29h ; ')'
0x18001a6e8  mov     [rsp+98h+var_2C], 1
0x18001a6f0  mov     [rsp+98h+var_60], eax
0x18001a6f4  mov     eax, [rsp+98h+var_60]
0x18001a6f8  mov     rcx, cs:RegHandle; RegHandle
0x18001a6ff  lea     rax, [rsp+98h+var_48]
0x18001a704  mov     [rsp+98h+UserData], rax; UserData
0x18001a709  mov     [rsp+98h+UserDataCount], 3; UserDataCount
0x18001a711  call    cs:__imp_EventWriteTransfer
0x18001a717  xor     al, al
0x18001a719  mov     cs:byte_18006EFAB, al
0x18001a71f  test    bl, bl
0x18001a721  jz      short loc_18001A72D
0x18001a723  xor     ebx, ebx
0x18001a725  cmp     cs:byte_18006EFA8, bl
0x18001a72b  jnz     short loc_18001A73F
0x18001a72d  call    ?RefreshPolicy@NgcCachedCertPolicy@@AEAAJXZ; NgcCachedCertPolicy::RefreshPolicy(void)
0x18001a732  mov     ebx, eax
0x18001a734  test    eax, eax
0x18001a736  js      short loc_18001A751
0x18001a738  mov     cs:byte_18006EFA8, 1
0x18001a73f  movzx   eax, cs:byte_18006EFA9
0x18001a746  mov     [rdi], eax
0x18001a748  movzx   eax, cs:byte_18006EFAA
0x18001a74f  mov     [rsi], eax
0x18001a751  lea     rcx, stru_18006EFA0; SRWLock
0x18001a758  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a75e  mov     eax, ebx
0x18001a760  mov     rcx, [rsp+98h+var_18]
0x18001a768  xor     rcx, rsp; StackCookie
0x18001a76b  call    __security_check_cookie
0x18001a770  lea     r11, [rsp+98h+var_8]
0x18001a778  mov     rbx, [r11+10h]
0x18001a77c  mov     rsi, [r11+18h]
0x18001a780  mov     rsp, r11
0x18001a783  pop     rdi
0x18001a784  retn
0x18001a785  movzx   edx, [rsp+98h+var_68]
0x18001a78a  xor     ecx, ecx
0x18001a78c  movzx   eax, cs:byte_18006EFAB
0x18001a793  test    dl, dl
0x18001a795  setnz   cl
0x18001a798  cmp     ecx, eax
0x18001a79a  jz      short loc_18001A7A3
0x18001a79c  mov     cs:byte_18006EFA8, 0
0x18001a7a3  test    dl, dl
0x18001a7a5  jz      loc_18001A717
0x18001a7ab  mov     al, 1
0x18001a7ad  jmp     loc_18001A719
```
