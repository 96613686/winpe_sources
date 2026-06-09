# FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)

- ea: `0x140003fec`
- end: `0x140004075`
- name: `?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z`
- size: `137`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int64, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003094`
- `0x140004640`

## callees

- `0x1400036d0`
- `0x140003fec`
- `0x14000461c`
- `0x140004a08`
- `0x140004cfc`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004016`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004016`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140004047`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140004047`

## string_xrefs

- `0x140004029`: `COM+ Failfast:  Unable to allocate memory for stack trace!`

## pseudocode

```c
void __fastcall FailFastStr(const unsigned __int16 *a1, const unsigned __int16 *a2, __int64 a3, int a4, int a5)
{
  _BYTE v6[8]; // [rsp+20h] [rbp-48h] BYREF
  const wchar_t *v7; // [rsp+28h] [rbp-40h]

  if ( !DebugFlags::sm_registryInitialized )
    DebugFlags::InitRegistry();
  if ( DebugFlags::sm_fDebugBreakOnFailFast )
  {
    if ( a5 )
    {
      if ( IsDebuggerPresent()
        || MEMORY[0x7FFE02D4]
        || (v7 = L"COM+ Failfast:  Unable to allocate memory for stack trace!",
            CStackDlg::DoModal((CStackDlg *)v6) == 603) )
      {
        DebugBreak();
      }
    }
  }
  if ( a4 )
    FF_DumpProcess();
  if ( !g_fKeepRunningAfterFailfast )
  {
    TerminateThisProcess();
    JUMPOUT(0x140004074LL);
  }
  g_fKeepRunningAfterFailfast = 0;
}

```

## disassembly

```asm
0x140003fec  push    rbx
0x140003fee  sub     rsp, 60h
0x140003ff2  cmp     cs:?sm_registryInitialized@DebugFlags@@0HA, 0; int DebugFlags::sm_registryInitialized
0x140003ff9  mov     ebx, r9d
0x140003ffc  jnz     short loc_140004003
0x140003ffe  call    ?InitRegistry@DebugFlags@@CAXXZ; DebugFlags::InitRegistry(void)
0x140004003  cmp     cs:?sm_fDebugBreakOnFailFast@DebugFlags@@0HA, 0; int DebugFlags::sm_fDebugBreakOnFailFast
0x14000400a  jz      short loc_14000404D
0x14000400c  cmp     [rsp+68h+arg_20], 0
0x140004014  jz      short loc_14000404D
0x140004016  call    cs:__imp_IsDebuggerPresent
0x14000401c  test    eax, eax
0x14000401e  jnz     short loc_140004047
0x140004020  cmp     ds:7FFE02D4h, al
0x140004027  jnz     short loc_140004047
0x140004029  lea     rax, aComFailfastUna; "COM+ Failfast:  Unable to allocate memo"...
0x140004030  lea     rcx, [rsp+68h+var_48]; this
0x140004035  mov     [rsp+68h+var_40], rax
0x14000403a  call    ?DoModal@CStackDlg@@QEAA_JXZ; CStackDlg::DoModal(void)
0x14000403f  cmp     rax, 25Bh
0x140004045  jnz     short loc_14000404D
0x140004047  call    cs:__imp_DebugBreak
0x14000404d  test    ebx, ebx
0x14000404f  jz      short loc_140004056
0x140004051  call    ?FF_DumpProcess@@YAXXZ; FF_DumpProcess(void)
0x140004056  cmp     cs:?g_fKeepRunningAfterFailfast@@3HA, 0; int g_fKeepRunningAfterFailfast
0x14000405d  jz      short loc_14000406F
0x14000405f  mov     cs:?g_fKeepRunningAfterFailfast@@3HA, 0; int g_fKeepRunningAfterFailfast
0x140004069  add     rsp, 60h
0x14000406d  pop     rbx
0x14000406e  retn
0x14000406f  call    ?TerminateThisProcess@@YAXXZ; TerminateThisProcess(void)
```
