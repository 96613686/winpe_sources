# PrjfFsctlSetReparsePointPostOp

- ea: `0x14002e1a4`
- end: `0x14002e36e`
- name: `PrjfFsctlSetReparsePointPostOp`
- size: `458`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x14002eb70`

## callees

- `0x14000b1d0`
- `0x14000dab0`
- `0x14002e1a4`
- `0x14003875c`
- `0x14003a84c`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14002e29c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002e29c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002e271`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002e271`
- `FLTMGR!FltReleaseContext` at `0x14002e34a`
- `FLTMGR!FltReleaseContext` at `0x14002e34a`

## pseudocode

```c
__int64 __fastcall PrjfFsctlSetReparsePointPostOp(__int64 a1, __int64 a2, __int64 a3)
{
  int PrjReparseData; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // r8d
  struct _FLT_INSTANCE *v9; // r8
  struct _FILE_OBJECT *v10; // rdx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  __int128 v15; // [rsp+60h] [rbp-38h] BYREF
  __int128 v16; // [rsp+70h] [rbp-28h]
  __int64 v17; // [rsp+80h] [rbp-18h]

  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( *(int *)(a1 + 24) >= 0 )
  {
    PrjReparseData = PrjfGetPrjReparseData(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
    if ( PrjReparseData >= 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6);
      ExAcquireFastMutex((PFAST_MUTEX)(a3 + 8));
      *(_QWORD *)(a3 + 72) = 0;
      *(_QWORD *)(a3 + 112) = 32;
      *(_DWORD *)(a3 + 64) = 1;
      ExReleaseFastMutex((PFAST_MUTEX)(a3 + 8));
      v9 = *(struct _FLT_INSTANCE **)(a2 + 24);
      v10 = *(struct _FILE_OBJECT **)(a2 + 32);
      LODWORD(v17) = 0x400000;
      v11 = PrjfCopyFileBasicInformation(&v15, v10, v9, 64);
      if ( v11 < 0
        && ((xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
      {
        LOBYTE(v12) = xmmword_14001A3D0 & 0x80;
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDqd(
          519,
          v12,
          v13,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          7,
          48,
          (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
          78,
          *(_QWORD *)(a2 + 32),
          v11,
          v15,
          v16,
          v17);
      }
    }
    else if ( (xmmword_14001A3D0 & 0x80u) != 0LL || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = xmmword_14001A3D0 & 0x80;
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDqd(
        519,
        v6,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        7,
        47,
        (__int64)WPP_52333d08ad443511f3c222844b8995a6_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\fsctrl.c",
        45,
        *(_QWORD *)(a2 + 32),
        PrjReparseData,
        v15,
        v16,
        v17);
    }
  }
  FltReleaseContext((PFLT_CONTEXT)a3);
  return 0;
}

```

## disassembly

```asm
0x14002e1a4  mov     r11, rsp
0x14002e1a7  mov     [r11+10h], rbx
0x14002e1ab  mov     [r11+18h], rsi
0x14002e1af  push    rdi
0x14002e1b0  sub     rsp, 90h
0x14002e1b7  xorps   xmm0, xmm0
0x14002e1ba  mov     qword ptr [r11+20h], 0
0x14002e1c2  xor     eax, eax
0x14002e1c4  mov     byte ptr [r11+8], 0
0x14002e1c9  mov     rsi, r8
0x14002e1cc  mov     rdi, rdx
0x14002e1cf  movups  [rsp+98h+var_38], xmm0
0x14002e1d4  movups  [rsp+98h+var_28], xmm0
0x14002e1d9  mov     [r11-18h], rax
0x14002e1dd  cmp     [rcx+18h], eax
0x14002e1e0  jl      loc_14002E347
0x14002e1e6  mov     rdx, [rdx+20h]; FileObject
0x14002e1ea  lea     r9, [r11+8]
0x14002e1ee  mov     rcx, [rdi+18h]; Instance
0x14002e1f2  lea     r8, [r11+20h]
0x14002e1f6  call    PrjfGetPrjReparseData
0x14002e1fb  test    eax, eax
0x14002e1fd  jns     short loc_14002E25E
0x14002e1ff  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002e205  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002e20c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002e213  setnz   r8b
0x14002e217  and     dl, 80h
0x14002e21a  jnz     short loc_14002E225
0x14002e21c  test    r8b, r8b
0x14002e21f  jz      loc_14002E347
0x14002e225  mov     [rsp+98h+var_40], eax
0x14002e229  mov     rax, [rdi+20h]
0x14002e22d  mov     [rsp+98h+var_48], rax
0x14002e232  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002e239  mov     [rsp+98h+var_50], 62Dh
0x14002e241  mov     [rsp+98h+var_58], rax
0x14002e246  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002e24d  mov     [rsp+98h+var_60], rax
0x14002e252  mov     [rsp+98h+var_68], 2Fh ; '/'
0x14002e259  jmp     loc_14002E325
0x14002e25e  cmp     [rsp+98h+arg_0], 0
0x14002e266  jnz     short loc_14002E26D
0x14002e268  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002e26d  lea     rcx, [rsi+8]; FastMutex
0x14002e271  call    cs:__imp_ExAcquireFastMutex
0x14002e278  nop     dword ptr [rax+rax+00h]
0x14002e27d  mov     rax, [rsp+98h+arg_18]
0x14002e285  lea     rcx, [rsi+8]; FastMutex
0x14002e289  mov     [rsi+48h], rax
0x14002e28d  add     rax, 20h ; ' '
0x14002e291  mov     [rsi+70h], rax
0x14002e295  mov     dword ptr [rsi+40h], 1
0x14002e29c  call    cs:__imp_ExReleaseFastMutex
0x14002e2a3  nop     dword ptr [rax+rax+00h]
0x14002e2a8  mov     r8, [rdi+18h]
0x14002e2ac  lea     rcx, [rsp+98h+var_38]
0x14002e2b1  mov     rdx, [rdi+20h]
0x14002e2b5  mov     r9d, 40h ; '@'
0x14002e2bb  mov     dword ptr [rsp+98h+var_18], 400000h
0x14002e2c6  call    PrjfCopyFileBasicInformation
0x14002e2cb  test    eax, eax
0x14002e2cd  jns     short loc_14002E347
0x14002e2cf  mov     dl, byte ptr cs:xmmword_14001A3D0
0x14002e2d5  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002e2dc  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002e2e3  setnz   r8b
0x14002e2e7  and     dl, 80h
0x14002e2ea  jnz     short loc_14002E2F1
0x14002e2ec  test    r8b, r8b
0x14002e2ef  jz      short loc_14002E347
0x14002e2f1  mov     [rsp+98h+var_40], eax
0x14002e2f5  mov     rax, [rdi+20h]
0x14002e2f9  mov     [rsp+98h+var_48], rax
0x14002e2fe  lea     rax, aOnecoreBaseFsG_8; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002e305  mov     [rsp+98h+var_50], 64Eh
0x14002e30d  mov     [rsp+98h+var_58], rax
0x14002e312  lea     rax, WPP_52333d08ad443511f3c222844b8995a6_Traceguids
0x14002e319  mov     [rsp+98h+var_60], rax
0x14002e31e  mov     [rsp+98h+var_68], 30h ; '0'
0x14002e325  mov     r9, cs:WPP_GLOBAL_Control
0x14002e32c  mov     ecx, 207h
0x14002e331  mov     [rsp+98h+var_70], 7
0x14002e339  mov     [rsp+98h+var_78], 2
0x14002e33e  mov     r9, [r9+40h]
0x14002e342  call    WPP_RECORDER_AND_TRACE_SF_sDqd
0x14002e347  mov     rcx, rsi; Context
0x14002e34a  call    cs:__imp_FltReleaseContext
0x14002e351  nop     dword ptr [rax+rax+00h]
0x14002e356  lea     r11, [rsp+98h+var_8]
0x14002e35e  xor     eax, eax
0x14002e360  mov     rbx, [r11+18h]
0x14002e364  mov     rsi, [r11+20h]
0x14002e368  mov     rsp, r11
0x14002e36b  pop     rdi
0x14002e36c  retn
```
