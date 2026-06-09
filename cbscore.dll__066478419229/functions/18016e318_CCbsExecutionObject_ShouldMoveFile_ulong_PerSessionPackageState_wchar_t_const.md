# CCbsExecutionObject::ShouldMoveFile(ulong,PerSessionPackageState *,wchar_t const *)

- ea: `0x18016e318`
- end: `0x18016e484`
- name: `?ShouldMoveFile@CCbsExecutionObject@@AEAAHKPEAUPerSessionPackageState@@PEB_W@Z`
- size: `364`
- prototype: `__int64 __fastcall(CCbsExecutionObject *__hidden this, unsigned int, struct PerSessionPackageState *, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18015ac58`
- `0x18015c924`

## callees

- `0x180013250`
- `0x180028e24`
- `0x180033d50`
- `0x18004a864`
- `0x1800ad504`
- `0x18016e1f0`
- `0x18016e318`
- `0x1801c2cb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18016e448`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18016e448`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18016e383`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18016e383`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18016e3eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18016e411`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18016e3eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18016e411`

## string_xrefs

- `0x18016e35a`: `This is an offline Overlay image, will use copy.`
- `0x18016e3c0`: `Client specifies CbsMovePayload, or client is Windows Update, will move payload to system.`
- `0x18016e458`: `Client specifies CbsMovePayload, but the sandbox is not on system volume, will use copy instead.`

## pseudocode

```c
__int64 __fastcall CCbsExecutionObject::ShouldMoveFile(
        CCbsExecutionObject *this,
        char a2,
        struct PerSessionPackageState *a3,
        const wchar_t *a4)
{
  CCbsSession *v6; // rcx
  const char *v8; // rdx
  unsigned int v9; // edi
  UINT SystemWindowsDirectoryW; // esi
  __int64 v11; // rdx
  unsigned __int64 v12; // rax
  LPWSTR lpBuffer[5]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v15; // [rsp+50h] [rbp+8h] BYREF
  const wchar_t *v16; // [rsp+68h] [rbp+20h] BYREF

  v16 = a4;
  lpBuffer[0] = 0;
  v6 = (CCbsSession *)*((_QWORD *)this + 8);
  v15 = 0;
  LOBYTE(v16) = 0;
  if ( (int)CCbsSession::IsOfflineLayercake(v6, (bool *)&v16) >= 0 && (_BYTE)v16 )
  {
    v8 = "This is an offline Overlay image, will use copy.";
LABEL_17:
    LogAdapter::TraceAtLevel<>(1, v8);
    v9 = 0;
    goto LABEL_18;
  }
  if ( (unsigned int)CCbsSession::IsOffline(*((CCbsSession **)this + 8))
    && !GetEnvironmentVariableW(L"WINDOWS_WCP_INSKUASSEMBLY", 0, 0)
    && (WdsSetupInProgress(&v15, 1), v15)
    || (a2 & 0x10) != 0
    || (v9 = 0, (unsigned int)CCbsSession::IsClientWindowsUpdate(*((CCbsSession **)this + 8))) )
  {
    LogAdapter::TraceAtLevel<>(
      1,
      "Client specifies CbsMovePayload, or client is Windows Update, will move payload to system.");
    v9 = 1;
    if ( !(unsigned int)CCbsSession::IsOffline(*((CCbsSession **)this + 8)) )
    {
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
      if ( (int)SczAlloc(lpBuffer, SystemWindowsDirectoryW + 2) >= 0 )
      {
        if ( GetSystemWindowsDirectoryW(lpBuffer[0], SystemWindowsDirectoryW) )
        {
          v11 = *((_QWORD *)a3 + 3);
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)(v11 + 2 * v12) );
          if ( v12 > 5 && (unsigned int)_o__wcsnicmp(lpBuffer[0], v11 + 8, 2) )
          {
            v8 = "Client specifies CbsMovePayload, but the sandbox is not on system volume, will use copy instead.";
            goto LABEL_17;
          }
        }
      }
    }
  }
LABEL_18:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(lpBuffer);
  return v9;
}

```

## disassembly

```asm
0x18016e318  mov     rax, rsp
0x18016e31b  mov     [rax+10h], rbp
0x18016e31f  mov     [rax+20h], r9
0x18016e323  push    rsi
0x18016e324  push    rdi
0x18016e325  push    r14
0x18016e327  sub     rsp, 30h
0x18016e32b  xor     r14d, r14d
0x18016e32e  mov     edi, edx
0x18016e330  mov     rsi, rcx
0x18016e333  mov     [rax-28h], r14
0x18016e337  mov     rcx, [rcx+40h]; this
0x18016e33b  lea     rdx, [rax+20h]; bool *
0x18016e33f  mov     [rax+8], r14d
0x18016e343  mov     rbp, r8
0x18016e346  mov     [rax+20h], r14b
0x18016e34a  call    ?IsOfflineLayercake@CCbsSession@@QEAAJPEA_N@Z; CCbsSession::IsOfflineLayercake(bool *)
0x18016e34f  test    eax, eax
0x18016e351  js      short loc_18016E36A
0x18016e353  cmp     byte ptr [rsp+48h+arg_18], r14b
0x18016e358  jz      short loc_18016E36A
0x18016e35a  lea     rdx, aThisIsAnOfflin; "This is an offline Overlay image, will "...
0x18016e361  lea     ecx, [r14+1]
0x18016e365  jmp     loc_18016E461
0x18016e36a  mov     rcx, [rsi+40h]; this
0x18016e36e  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18016e373  test    eax, eax
0x18016e375  jz      short loc_18016E3A6
0x18016e377  xor     r8d, r8d; nSize
0x18016e37a  lea     rcx, aWindowsWcpInsk; "WINDOWS_WCP_INSKUASSEMBLY"
0x18016e381  xor     edx, edx; lpBuffer
0x18016e383  call    cs:__imp_GetEnvironmentVariableW
0x18016e38a  nop     dword ptr [rax+rax+00h]
0x18016e38f  test    eax, eax
0x18016e391  jnz     short loc_18016E3A6
0x18016e393  mov     dl, 1; bool
0x18016e395  lea     rcx, [rsp+48h+arg_0]; unsigned int *
0x18016e39a  call    ?WdsSetupInProgress@@YAJPEAK_N@Z; WdsSetupInProgress(ulong *,bool)
0x18016e39f  cmp     [rsp+48h+arg_0], r14d
0x18016e3a4  ja      short loc_18016E3C0
0x18016e3a6  test    dil, 10h
0x18016e3aa  jnz     short loc_18016E3C0
0x18016e3ac  mov     rcx, [rsi+40h]; this
0x18016e3b0  mov     edi, r14d
0x18016e3b3  call    ?IsClientWindowsUpdate@CCbsSession@@QEBAHXZ; CCbsSession::IsClientWindowsUpdate(void)
0x18016e3b8  test    eax, eax
0x18016e3ba  jz      loc_18016E469
0x18016e3c0  lea     rdx, aClientSpecifie_2; "Client specifies CbsMovePayload, or cli"...
0x18016e3c7  mov     ecx, 1
0x18016e3cc  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18016e3d1  mov     rcx, [rsi+40h]; this
0x18016e3d5  mov     edi, 1
0x18016e3da  call    ?IsOffline@CCbsSession@@QEBAHXZ; CCbsSession::IsOffline(void)
0x18016e3df  test    eax, eax
0x18016e3e1  jnz     loc_18016E469
0x18016e3e7  xor     edx, edx; uSize
0x18016e3e9  xor     ecx, ecx; lpBuffer
0x18016e3eb  call    cs:__imp_GetSystemWindowsDirectoryW
0x18016e3f2  nop     dword ptr [rax+rax+00h]
0x18016e3f7  lea     rcx, [rsp+48h+lpBuffer]
0x18016e3fc  mov     esi, eax
0x18016e3fe  lea     edx, [rax+2]
0x18016e401  call    SczAlloc
0x18016e406  test    eax, eax
0x18016e408  js      short loc_18016E469
0x18016e40a  mov     rcx, [rsp+48h+lpBuffer]; lpBuffer
0x18016e40f  mov     edx, esi; uSize
0x18016e411  call    cs:__imp_GetSystemWindowsDirectoryW
0x18016e418  nop     dword ptr [rax+rax+00h]
0x18016e41d  test    eax, eax
0x18016e41f  jz      short loc_18016E469
0x18016e421  mov     rdx, [rbp+18h]
0x18016e425  or      rax, 0FFFFFFFFFFFFFFFFh
0x18016e429  inc     rax
0x18016e42c  cmp     [rdx+rax*2], r14w
0x18016e431  jnz     short loc_18016E429
0x18016e433  cmp     rax, 5
0x18016e437  jbe     short loc_18016E469
0x18016e439  mov     rcx, [rsp+48h+lpBuffer]
0x18016e43e  add     rdx, 8
0x18016e442  mov     r8d, 2
0x18016e448  call    cs:__imp__o__wcsnicmp
0x18016e44f  nop     dword ptr [rax+rax+00h]
0x18016e454  test    eax, eax
0x18016e456  jz      short loc_18016E469
0x18016e458  lea     rdx, aClientSpecifie_5; "Client specifies CbsMovePayload, but th"...
0x18016e45f  mov     ecx, edi
0x18016e461  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x18016e466  mov     edi, r14d
0x18016e469  lea     rcx, [rsp+48h+lpBuffer]
0x18016e46e  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18016e473  mov     rbp, [rsp+48h+arg_8]
0x18016e478  mov     eax, edi
0x18016e47a  add     rsp, 30h
0x18016e47e  pop     r14
0x18016e480  pop     rdi
0x18016e481  pop     rsi
0x18016e482  retn
```
