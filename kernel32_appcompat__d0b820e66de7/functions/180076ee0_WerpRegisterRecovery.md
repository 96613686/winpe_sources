# WerpRegisterRecovery

- ea: `0x180076ee0`
- end: `0x18007714e`
- name: `WerpRegisterRecovery`
- size: `622`
- prototype: `__int64 __fastcall(PVOID Pointer)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180047490`
- `0x180068ac0`

## callees

- `0x180043134`
- `0x180050e58`
- `0x180050fe8`
- `0x1800510c4`
- `0x180076884`
- `0x180076ee0`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x180076f31`
- `ntdll!DbgPrintEx` at `0x180076f7d`
- `ntdll!DbgPrintEx` at `0x180076fd7`
- `ntdll!DbgPrintEx` at `0x180077130`
- `ntdll!DbgPrintEx` at `0x180076f31`
- `ntdll!DbgPrintEx` at `0x180076f7d`
- `ntdll!DbgPrintEx` at `0x180076fd7`
- `ntdll!DbgPrintEx` at `0x180077130`
- `ntdll!RtlReleasePebLock` at `0x18007713d`
- `ntdll!RtlReleasePebLock` at `0x180083cdc`
- `ntdll!RtlReleasePebLock` at `0x18007713d`
- `ntdll!RtlReleasePebLock` at `0x180083cdc`
- `ntdll!RtlEncodeSystemPointer` at `0x180077017`
- `ntdll!RtlEncodeSystemPointer` at `0x180077017`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007706f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800770b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800770eb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007706f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800770b2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800770eb`

## string_xrefs

- `0x18007708f`: `WER/CrashAPI/%u:%u: ERROR Unable to create the m_hAliveEvent event\n`

## pseudocode

```c
__int64 __fastcall WerpRegisterRecovery(PVOID Pointer, __int64 a2, int a3, int a4)
{
  __int64 v9; // rbx
  const CHAR *v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rbx
  HANDLE v13; // rax
  const CHAR *v14; // r8
  HANDLE v15; // rax
  HANDLE v16; // rax
  int v17; // [rsp+20h] [rbp-68h]
  int v18; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-58h] BYREF

  memset(&EventAttributes, 0, sizeof(EventAttributes));
  if ( !(unsigned int)WerpCheckOkToRegister() )
  {
    DbgPrintEx(0x96u, 0, "WER/CrashAPI/%u:%u: ERROR Invalid state\n", NtCurrentTeb()->ClientId.UniqueProcess, 2448);
    return 2147947423LL;
  }
  v9 = WerpCurrentPeb();
  if ( !v9 )
  {
    v17 = 2456;
    v10 = "WER/CrashAPI/%u:%u: ERROR Unable to get the pPeb, WerpCurrentPeb failed\n";
LABEL_5:
    DbgPrintEx(0x96u, 0, v10, NtCurrentTeb()->ClientId.UniqueProcess, v17);
    return 2147500037LL;
  }
  if ( (int)WerpAcquirePebLock() < 0 )
  {
    v17 = 2462;
    v10 = "WER/CrashAPI/%u:%u: ERROR Unable to get the peb lock\n";
    goto LABEL_5;
  }
  v11 = -2147467259;
  if ( (int)WerpInitPEBStore() >= 0 )
  {
    v12 = *(_QWORD *)(v9 + 856);
    if ( v12 && (int)WerpValidatePebHeader(v12) >= 0 )
    {
      *(_DWORD *)(v12 + 2216) = 64;
      *(_QWORD *)(v12 + 2224) = RtlEncodeSystemPointer(Pointer);
      *(_QWORD *)(v12 + 2232) = a2;
      *(_DWORD *)(v12 + 2272) = a3;
      *(_DWORD *)(v12 + 2276) = a4;
      EventAttributes.nLength = 24;
      EventAttributes.lpSecurityDescriptor = 0;
      EventAttributes.bInheritHandle = 1;
      if ( *(_QWORD *)(v12 + 2240)
        || (v13 = CreateEventW(&EventAttributes, 0, 0, 0), (*(_QWORD *)(v12 + 2240) = v13) != 0) )
      {
        if ( *(_QWORD *)(v12 + 2248)
          || (v15 = CreateEventW(&EventAttributes, 1, 0, 0), (*(_QWORD *)(v12 + 2248) = v15) != 0) )
        {
          if ( *(_QWORD *)(v12 + 2256)
            || (v16 = CreateEventW(&EventAttributes, 1, 0, 0), (*(_QWORD *)(v12 + 2256) = v16) != 0) )
          {
            v11 = 0;
LABEL_26:
            RtlReleasePebLock();
            return v11;
          }
          v18 = 2542;
        }
        else
        {
          v18 = 2527;
        }
      }
      else
      {
        v18 = 2512;
      }
      v14 = "WER/CrashAPI/%u:%u: ERROR Unable to create the m_hAliveEvent event\n";
    }
    else
    {
      v18 = 2479;
      v14 = "WER/CrashAPI/%u:%u: ERROR Invalid PEB entry\n";
    }
    DbgPrintEx(0x96u, 0, v14, NtCurrentTeb()->ClientId.UniqueProcess, v18);
    goto LABEL_26;
  }
  DbgPrintEx(
    0x96u,
    0,
    "WER/CrashAPI/%u:%u: ERROR WerpInitPEBStore failed\n",
    NtCurrentTeb()->ClientId.UniqueProcess,
    2468);
  return v11;
}

```

## disassembly

```asm
0x180076ee0  push    rbx
0x180076ee2  push    rsi
0x180076ee3  push    rdi
0x180076ee4  push    r12
0x180076ee6  push    r14
0x180076ee8  push    r15
0x180076eea  sub     rsp, 58h
0x180076eee  mov     esi, r9d
0x180076ef1  mov     r14d, r8d
0x180076ef4  mov     r15, rdx
0x180076ef7  mov     r12, rcx
0x180076efa  xorps   xmm0, xmm0
0x180076efd  xor     eax, eax
0x180076eff  movups  xmmword ptr [rsp+88h+EventAttributes.nLength], xmm0
0x180076f04  mov     qword ptr [rsp+88h+EventAttributes.bInheritHandle], rax
0x180076f09  call    WerpCheckOkToRegister
0x180076f0e  test    eax, eax
0x180076f10  jnz     short loc_180076F51
0x180076f12  mov     r9, gs:40h
0x180076f1b  mov     [rsp+88h+var_68], 990h
0x180076f23  lea     r8, aWerCrashapiUUE_1; "WER/CrashAPI/%u:%u: ERROR Invalid state"...
0x180076f2a  xor     edx, edx; Level
0x180076f2c  mov     ecx, 96h; ComponentId
0x180076f31  call    cs:__imp_DbgPrintEx
0x180076f38  nop     dword ptr [rax+rax+00h]
0x180076f3d  mov     eax, 8007139Fh
0x180076f42  add     rsp, 58h
0x180076f46  pop     r15
0x180076f48  pop     r14
0x180076f4a  pop     r12
0x180076f4c  pop     rdi
0x180076f4d  pop     rsi
0x180076f4e  pop     rbx
0x180076f4f  retn
0x180076f51  call    WerpCurrentPeb
0x180076f56  mov     rbx, rax
0x180076f59  test    rax, rax
0x180076f5c  jnz     short loc_180076F90
0x180076f5e  mov     [rsp+88h+var_68], 998h
0x180076f66  lea     r8, aWerCrashapiUUE_45; "WER/CrashAPI/%u:%u: ERROR Unable to get"...
0x180076f6d  mov     r9, gs:40h
0x180076f76  xor     edx, edx; Level
0x180076f78  mov     ecx, 96h; ComponentId
0x180076f7d  call    cs:__imp_DbgPrintEx
0x180076f84  nop     dword ptr [rax+rax+00h]
0x180076f89  mov     eax, 80004005h
0x180076f8e  jmp     short loc_180076F42
0x180076f90  call    WerpAcquirePebLock
0x180076f95  test    eax, eax
0x180076f97  jns     short loc_180076FAA
0x180076f99  mov     [rsp+88h+var_68], 99Eh
0x180076fa1  lea     r8, aWerCrashapiUUE_14; "WER/CrashAPI/%u:%u: ERROR Unable to get"...
0x180076fa8  jmp     short loc_180076F6D
0x180076faa  mov     edi, 80004005h
0x180076faf  call    WerpInitPEBStore
0x180076fb4  test    eax, eax
0x180076fb6  jns     short loc_180076FEA
0x180076fb8  mov     r9, gs:40h
0x180076fc1  mov     [rsp+88h+var_68], 9A4h
0x180076fc9  lea     r8, aWerCrashapiUUE_13; "WER/CrashAPI/%u:%u: ERROR WerpInitPEBSt"...
0x180076fd0  xor     edx, edx; Level
0x180076fd2  mov     ecx, 96h; ComponentId
0x180076fd7  call    cs:__imp_DbgPrintEx
0x180076fde  nop     dword ptr [rax+rax+00h]
0x180076fe3  mov     eax, edi
0x180076fe5  jmp     loc_180076F42
0x180076fea  mov     rbx, [rbx+358h]
0x180076ff1  test    rbx, rbx
0x180076ff4  jz      loc_180077111
0x180076ffa  mov     rcx, rbx
0x180076ffd  call    WerpValidatePebHeader
0x180077002  test    eax, eax
0x180077004  js      loc_180077111
0x18007700a  mov     dword ptr [rbx+8A8h], 40h ; '@'
0x180077014  mov     rcx, r12; Pointer
0x180077017  call    cs:__imp_RtlEncodeSystemPointer
0x18007701e  nop     dword ptr [rax+rax+00h]
0x180077023  mov     [rbx+8B0h], rax
0x18007702a  mov     [rbx+8B8h], r15
0x180077031  mov     [rbx+8E0h], r14d
0x180077038  mov     [rbx+8E4h], esi
0x18007703e  mov     [rsp+88h+EventAttributes.nLength], 18h
0x180077046  mov     [rsp+88h+EventAttributes.lpSecurityDescriptor], 0
0x18007704f  mov     esi, 1
0x180077054  mov     [rsp+88h+EventAttributes.bInheritHandle], esi
0x180077058  cmp     qword ptr [rbx+8C0h], 0
0x180077060  jnz     short loc_18007709B
0x180077062  xor     r9d, r9d; lpName
0x180077065  xor     r8d, r8d; bInitialState
0x180077068  xor     edx, edx; bManualReset
0x18007706a  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x18007706f  call    cs:__imp_CreateEventW
0x180077076  nop     dword ptr [rax+rax+00h]
0x18007707b  mov     [rbx+8C0h], rax
0x180077082  test    rax, rax
0x180077085  jnz     short loc_18007709B
0x180077087  mov     [rsp+88h+var_68], 9D0h
0x18007708f  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR Unable to cre"...
0x180077096  jmp     loc_180077120
0x18007709b  cmp     qword ptr [rbx+8C8h], 0
0x1800770a3  jnz     short loc_1800770D4
0x1800770a5  xor     r9d, r9d; lpName
0x1800770a8  xor     r8d, r8d; bInitialState
0x1800770ab  mov     edx, esi; bManualReset
0x1800770ad  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x1800770b2  call    cs:__imp_CreateEventW
0x1800770b9  nop     dword ptr [rax+rax+00h]
0x1800770be  mov     [rbx+8C8h], rax
0x1800770c5  test    rax, rax
0x1800770c8  jnz     short loc_1800770D4
0x1800770ca  mov     [rsp+88h+var_68], 9DFh
0x1800770d2  jmp     short loc_18007708F
0x1800770d4  cmp     qword ptr [rbx+8D0h], 0
0x1800770dc  jnz     short loc_18007710D
0x1800770de  xor     r9d, r9d; lpName
0x1800770e1  xor     r8d, r8d; bInitialState
0x1800770e4  mov     edx, esi; bManualReset
0x1800770e6  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x1800770eb  call    cs:__imp_CreateEventW
0x1800770f2  nop     dword ptr [rax+rax+00h]
0x1800770f7  mov     [rbx+8D0h], rax
0x1800770fe  test    rax, rax
0x180077101  jnz     short loc_18007710D
0x180077103  mov     [rsp+88h+var_68], 9EEh
0x18007710b  jmp     short loc_18007708F
0x18007710d  xor     edi, edi
0x18007710f  jmp     short loc_18007713D
0x180077111  mov     [rsp+88h+var_68], 9AFh
0x180077119  lea     r8, aWerCrashapiUUE_16; "WER/CrashAPI/%u:%u: ERROR Invalid PEB e"...
0x180077120  mov     r9, gs:40h
0x180077129  xor     edx, edx; Level
0x18007712b  mov     ecx, 96h; ComponentId
0x180077130  call    cs:__imp_DbgPrintEx
0x180077137  nop     dword ptr [rax+rax+00h]
0x18007713c  nop
0x18007713d  call    cs:__imp_RtlReleasePebLock
0x180077144  nop     dword ptr [rax+rax+00h]
0x180077149  jmp     loc_180076FE3
0x180083cd3  push    rbp
0x180083cd5  sub     rsp, 30h
0x180083cd9  mov     rbp, rdx
0x180083cdc  call    cs:__imp_RtlReleasePebLock
0x180083ce3  nop     dword ptr [rax+rax+00h]
0x180083ce8  nop
0x180083ce9  add     rsp, 30h
0x180083ced  pop     rbp
0x180083cee  retn
```
