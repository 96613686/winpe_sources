# QueueForceSyncMasterKeysThreadFunc(void *)

- ea: `0x18002d7e0`
- end: `0x18002d8e8`
- name: `?QueueForceSyncMasterKeysThreadFunc@@YAKPEAX@Z`
- size: `264`
- prototype: `__int64 __fastcall(_QWORD *Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007f10`
- `0x18001c9c0`
- `0x18001ff1c`
- `0x18002d7e0`
- `0x18002e130`
- `0x180039d90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d8c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d8c9`

## string_xrefs

- `0x18002d882`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d8a6`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall QueueForceSyncMasterKeysThreadFunc(_QWORD *Parameter)
{
  _DWORD *v2; // rdi
  unsigned int v3; // eax
  unsigned int v4; // esi

  if ( Parameter )
  {
    if ( *(_DWORD *)Parameter == 16 )
    {
      v2 = (_DWORD *)Parameter[1];
      if ( v2 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
        v3 = SynchronizeMasterKeys(v2, 0x8000000u, 0, 0, 0, 0, 0);
        v4 = v3;
        if ( v3 )
          DebugTraceError(v3, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 706);
        else
          UpdateLastMasterKeySync(v2);
        CPSFreeContext(v2);
        goto LABEL_12;
      }
    }
  }
  v4 = 87;
  DebugTraceError(87, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 691);
  if ( Parameter )
LABEL_12:
    LocalFree(Parameter);
  return v4;
}

```

## disassembly

```asm
0x18002d7e0  mov     [rsp+arg_0], rbx
0x18002d7e5  mov     [rsp+arg_8], rsi
0x18002d7ea  push    rdi
0x18002d7eb  sub     rsp, 40h
0x18002d7ef  mov     rbx, rcx
0x18002d7f2  test    rcx, rcx
0x18002d7f5  jz      loc_18002D8A1
0x18002d7fb  cmp     dword ptr [rcx], 10h
0x18002d7fe  jnz     loc_18002D8A1
0x18002d804  mov     rdi, [rcx+8]
0x18002d808  test    rdi, rdi
0x18002d80b  jz      loc_18002D8A1
0x18002d811  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d818  lea     rax, WPP_GLOBAL_Control
0x18002d81f  cmp     rcx, rax
0x18002d822  jz      short loc_18002D83F
0x18002d824  test    byte ptr [rcx+1Ch], 8
0x18002d828  jz      short loc_18002D83F
0x18002d82a  mov     rcx, [rcx+10h]
0x18002d82e  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002d835  mov     edx, 0Eh
0x18002d83a  call    WPP_SF_
0x18002d83f  mov     [rsp+48h+var_18], 0; unsigned int *
0x18002d848  xor     r9d, r9d; struct DP_KEK *
0x18002d84b  mov     [rsp+48h+var_20], 0; unsigned int *
0x18002d854  xor     r8d, r8d; struct DP_KEK *
0x18002d857  mov     edx, 8000000h; unsigned int
0x18002d85c  mov     [rsp+48h+var_28], 0; unsigned int
0x18002d864  mov     rcx, rdi; void *
0x18002d867  call    ?SynchronizeMasterKeys@@YAKPEAXKPEAUDP_KEK@@1KPEAK2@Z; SynchronizeMasterKeys(void *,ulong,DP_KEK *,DP_KEK *,ulong,ulong *,ulong *)
0x18002d86c  mov     esi, eax
0x18002d86e  test    eax, eax
0x18002d870  jnz     short loc_18002D87C
0x18002d872  mov     rcx, rdi; void *
0x18002d875  call    ?UpdateLastMasterKeySync@@YAKPEAX@Z; UpdateLastMasterKeySync(void *)
0x18002d87a  jmp     short loc_18002D897
0x18002d87c  mov     r9d, 2C2h
0x18002d882  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d889  lea     rdx, aDwlasterror; "dwLastError"
0x18002d890  mov     ecx, eax
0x18002d892  call    DebugTraceError
0x18002d897  mov     rcx, rdi; hMem
0x18002d89a  call    ?CPSFreeContext@@YAKPEAX@Z; CPSFreeContext(void *)
0x18002d89f  jmp     short loc_18002D8C6
0x18002d8a1  mov     esi, 57h ; 'W'
0x18002d8a6  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d8ad  mov     ecx, esi
0x18002d8af  lea     rdx, aDwlasterror; "dwLastError"
0x18002d8b6  mov     r9d, 2B3h
0x18002d8bc  call    DebugTraceError
0x18002d8c1  test    rbx, rbx
0x18002d8c4  jz      short loc_18002D8D5
0x18002d8c6  mov     rcx, rbx; hMem
0x18002d8c9  call    cs:__imp_LocalFree
0x18002d8d0  nop     dword ptr [rax+rax+00h]
0x18002d8d5  mov     rbx, [rsp+48h+arg_0]
0x18002d8da  mov     eax, esi
0x18002d8dc  mov     rsi, [rsp+48h+arg_8]
0x18002d8e1  add     rsp, 40h
0x18002d8e5  pop     rdi
0x18002d8e6  retn
```
