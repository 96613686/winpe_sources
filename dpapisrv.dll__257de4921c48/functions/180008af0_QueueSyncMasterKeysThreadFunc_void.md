# QueueSyncMasterKeysThreadFunc(void *)

- ea: `0x180008af0`
- end: `0x180008c35`
- name: `?QueueSyncMasterKeysThreadFunc@@YAKPEAX@Z`
- size: `325`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007f10`
- `0x180008af0`
- `0x180008c3c`
- `0x18001c9c0`
- `0x18001ff1c`
- `0x18002e130`
- `0x180039d90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c16`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c16`

## string_xrefs

- `0x180008b9f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180008bf3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall QueueSyncMasterKeysThreadFunc(PVOID Parameter)
{
  void *v2; // rdi
  unsigned int v3; // eax
  unsigned int v4; // esi

  if ( Parameter )
  {
    if ( *(_DWORD *)Parameter == 16 )
    {
      v2 = (void *)*((_QWORD *)Parameter + 1);
      if ( v2 )
      {
        if ( (unsigned int)IsMasterKeySyncRequired(*((void **)Parameter + 1)) )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
          v3 = SynchronizeMasterKeys(v2, 0, 0, 0, 0, 0, 0);
          v4 = v3;
          if ( v3 )
            DebugTraceError(v3, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 540);
          else
            UpdateLastMasterKeySync(v2);
        }
        else
        {
          v4 = 0;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
            WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        }
        CPSFreeContext(v2);
        goto LABEL_16;
      }
    }
  }
  v4 = 87;
  DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 523);
  if ( Parameter )
LABEL_16:
    LocalFree(Parameter);
  return v4;
}

```

## disassembly

```asm
0x180008af0  mov     [rsp+arg_0], rbx
0x180008af5  mov     [rsp+arg_8], rsi
0x180008afa  push    rdi
0x180008afb  sub     rsp, 40h
0x180008aff  mov     rbx, rcx
0x180008b02  test    rcx, rcx
0x180008b05  jz      loc_180008BEE
0x180008b0b  cmp     dword ptr [rcx], 10h
0x180008b0e  jnz     loc_180008BEE
0x180008b14  mov     rdi, [rcx+8]
0x180008b18  test    rdi, rdi
0x180008b1b  jz      loc_180008BEE
0x180008b21  mov     rcx, rdi; void *
0x180008b24  call    ?IsMasterKeySyncRequired@@YAHPEAX@Z; IsMasterKeySyncRequired(void *)
0x180008b29  test    eax, eax
0x180008b2b  jz      loc_180008BB6
0x180008b31  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b38  lea     rax, WPP_GLOBAL_Control
0x180008b3f  cmp     rcx, rax
0x180008b42  jz      short loc_180008B5F
0x180008b44  test    byte ptr [rcx+1Ch], 8
0x180008b48  jz      short loc_180008B5F
0x180008b4a  mov     rcx, [rcx+10h]
0x180008b4e  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180008b55  mov     edx, 0Bh
0x180008b5a  call    WPP_SF_
0x180008b5f  mov     [rsp+48h+var_18], 0; unsigned int *
0x180008b68  xor     r9d, r9d; struct DP_KEK *
0x180008b6b  mov     [rsp+48h+var_20], 0; unsigned int *
0x180008b74  xor     r8d, r8d; struct DP_KEK *
0x180008b77  xor     edx, edx; unsigned int
0x180008b79  mov     [rsp+48h+var_28], 0; unsigned int
0x180008b81  mov     rcx, rdi; void *
0x180008b84  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x180008b89  mov     esi, eax
0x180008b8b  test    eax, eax
0x180008b8d  jnz     short loc_180008B99
0x180008b8f  mov     rcx, rdi; void *
0x180008b92  call    ?UpdateLastMasterKeySync@@YAKPEAX@Z; UpdateLastMasterKeySync(void *)
0x180008b97  jmp     short loc_180008BE4
0x180008b99  mov     r9d, 21Ch
0x180008b9f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180008ba6  lea     rdx, aDwlasterror; "dwLastError"
0x180008bad  mov     ecx, eax
0x180008baf  call    DebugTraceError
0x180008bb4  jmp     short loc_180008BE4
0x180008bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bbd  lea     rax, WPP_GLOBAL_Control
0x180008bc4  xor     esi, esi
0x180008bc6  cmp     rcx, rax
0x180008bc9  jz      short loc_180008BE4
0x180008bcb  test    byte ptr [rcx+1Ch], 8
0x180008bcf  jz      short loc_180008BE4
0x180008bd1  mov     rcx, [rcx+10h]
0x180008bd5  lea     edx, [rsi+0Ch]
0x180008bd8  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x180008bdf  call    WPP_SF_
0x180008be4  mov     rcx, rdi; hMem
0x180008be7  call    ?CPSFreeContext@@YAKPEAX@Z; CPSFreeContext(void *)
0x180008bec  jmp     short loc_180008C13
0x180008bee  mov     esi, 57h ; 'W'
0x180008bf3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180008bfa  mov     ecx, esi
0x180008bfc  lea     rdx, aDwlasterror; "dwLastError"
0x180008c03  mov     r9d, 20Bh
0x180008c09  call    DebugTraceError
0x180008c0e  test    rbx, rbx
0x180008c11  jz      short loc_180008C22
0x180008c13  mov     rcx, rbx; hMem
0x180008c16  call    cs:__imp_LocalFree
0x180008c1d  nop     dword ptr [rax+rax+00h]
0x180008c22  mov     rbx, [rsp+48h+arg_0]
0x180008c27  mov     eax, esi
0x180008c29  mov     rsi, [rsp+48h+arg_8]
0x180008c2e  add     rsp, 40h
0x180008c32  pop     rdi
0x180008c33  retn
```
