# WerpRegisterRecovery

- ea: `0x18006f404`
- end: `0x18006f638`
- name: `WerpRegisterRecovery`
- size: `564`
- prototype: `__int64 __fastcall(PVOID Pointer)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043330`
- `0x180062180`

## callees

- `0x18003f6a0`
- `0x18004c6cc`
- `0x18004c838`
- `0x18004c900`
- `0x18006ee18`
- `0x18006f404`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18006f455`
- `ntdll!DbgPrintEx` at `0x18006f49a`
- `ntdll!DbgPrintEx` at `0x18006f4ee`
- `ntdll!DbgPrintEx` at `0x18006f626`
- `ntdll!DbgPrintEx` at `0x18006f455`
- `ntdll!DbgPrintEx` at `0x18006f49a`
- `ntdll!DbgPrintEx` at `0x18006f4ee`
- `ntdll!DbgPrintEx` at `0x18006f626`
- `ntdll!RtlReleasePebLock` at `0x18006f62d`
- `ntdll!RtlReleasePebLock` at `0x18007bb35`
- `ntdll!RtlReleasePebLock` at `0x18006f62d`
- `ntdll!RtlReleasePebLock` at `0x18007bb35`
- `ntdll!RtlEncodeSystemPointer` at `0x18006f528`
- `ntdll!RtlEncodeSystemPointer` at `0x18006f528`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f57a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f5b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f5e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f57a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f5b4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f5e7`

## string_xrefs

- `0x18006f594`: `WER/CrashAPI/%u:%u: ERROR Unable to create the m_hAliveEvent event\n`

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
0x18006f404  push    rbx
0x18006f406  push    rsi
0x18006f407  push    rdi
0x18006f408  push    r12
0x18006f40a  push    r14
0x18006f40c  push    r15
0x18006f40e  sub     rsp, 58h
0x18006f412  mov     esi, r9d
0x18006f415  mov     r14d, r8d
0x18006f418  mov     r15, rdx
0x18006f41b  mov     r12, rcx
0x18006f41e  xorps   xmm0, xmm0
0x18006f421  xor     eax, eax
0x18006f423  movups  xmmword ptr [rsp+88h+EventAttributes.nLength], xmm0
0x18006f428  mov     qword ptr [rsp+88h+EventAttributes.bInheritHandle], rax
0x18006f42d  call    WerpCheckOkToRegister
0x18006f432  test    eax, eax
0x18006f434  jnz     short loc_18006F46E
0x18006f436  mov     r9, gs:40h
0x18006f43f  mov     [rsp+88h+var_68], 990h
0x18006f447  lea     r8, aWerCrashapiUUE_1; "WER/CrashAPI/%u:%u: ERROR Invalid state"...
0x18006f44e  xor     edx, edx; Level
0x18006f450  mov     ecx, 96h; ComponentId
0x18006f455  call    cs:__imp_DbgPrintEx
0x18006f45b  mov     eax, 8007139Fh
0x18006f460  add     rsp, 58h
0x18006f464  pop     r15
0x18006f466  pop     r14
0x18006f468  pop     r12
0x18006f46a  pop     rdi
0x18006f46b  pop     rsi
0x18006f46c  pop     rbx
0x18006f46d  retn
0x18006f46e  call    WerpCurrentPeb
0x18006f473  mov     rbx, rax
0x18006f476  test    rax, rax
0x18006f479  jnz     short loc_18006F4A7
0x18006f47b  mov     [rsp+88h+var_68], 998h
0x18006f483  lea     r8, aWerCrashapiUUE_45; "WER/CrashAPI/%u:%u: ERROR Unable to get"...
0x18006f48a  mov     r9, gs:40h
0x18006f493  xor     edx, edx; Level
0x18006f495  mov     ecx, 96h; ComponentId
0x18006f49a  call    cs:__imp_DbgPrintEx
0x18006f4a0  mov     eax, 80004005h
0x18006f4a5  jmp     short loc_18006F460
0x18006f4a7  call    WerpAcquirePebLock
0x18006f4ac  test    eax, eax
0x18006f4ae  jns     short loc_18006F4C1
0x18006f4b0  mov     [rsp+88h+var_68], 99Eh
0x18006f4b8  lea     r8, aWerCrashapiUUE_14; "WER/CrashAPI/%u:%u: ERROR Unable to get"...
0x18006f4bf  jmp     short loc_18006F48A
0x18006f4c1  mov     edi, 80004005h
0x18006f4c6  call    WerpInitPEBStore
0x18006f4cb  test    eax, eax
0x18006f4cd  jns     short loc_18006F4FB
0x18006f4cf  mov     r9, gs:40h
0x18006f4d8  mov     [rsp+88h+var_68], 9A4h
0x18006f4e0  lea     r8, aWerCrashapiUUE_13; "WER/CrashAPI/%u:%u: ERROR WerpInitPEBSt"...
0x18006f4e7  xor     edx, edx; Level
0x18006f4e9  mov     ecx, 96h; ComponentId
0x18006f4ee  call    cs:__imp_DbgPrintEx
0x18006f4f4  mov     eax, edi
0x18006f4f6  jmp     loc_18006F460
0x18006f4fb  mov     rbx, [rbx+358h]
0x18006f502  test    rbx, rbx
0x18006f505  jz      loc_18006F607
0x18006f50b  mov     rcx, rbx
0x18006f50e  call    WerpValidatePebHeader
0x18006f513  test    eax, eax
0x18006f515  js      loc_18006F607
0x18006f51b  mov     dword ptr [rbx+8A8h], 40h ; '@'
0x18006f525  mov     rcx, r12; Pointer
0x18006f528  call    cs:__imp_RtlEncodeSystemPointer
0x18006f52e  mov     [rbx+8B0h], rax
0x18006f535  mov     [rbx+8B8h], r15
0x18006f53c  mov     [rbx+8E0h], r14d
0x18006f543  mov     [rbx+8E4h], esi
0x18006f549  mov     [rsp+88h+EventAttributes.nLength], 18h
0x18006f551  mov     [rsp+88h+EventAttributes.lpSecurityDescriptor], 0
0x18006f55a  mov     esi, 1
0x18006f55f  mov     [rsp+88h+EventAttributes.bInheritHandle], esi
0x18006f563  cmp     qword ptr [rbx+8C0h], 0
0x18006f56b  jnz     short loc_18006F59D
0x18006f56d  xor     r9d, r9d; lpName
0x18006f570  xor     r8d, r8d; bInitialState
0x18006f573  xor     edx, edx; bManualReset
0x18006f575  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x18006f57a  call    cs:__imp_CreateEventW
0x18006f580  mov     [rbx+8C0h], rax
0x18006f587  test    rax, rax
0x18006f58a  jnz     short loc_18006F59D
0x18006f58c  mov     [rsp+88h+var_68], 9D0h
0x18006f594  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR Unable to cre"...
0x18006f59b  jmp     short loc_18006F616
0x18006f59d  cmp     qword ptr [rbx+8C8h], 0
0x18006f5a5  jnz     short loc_18006F5D0
0x18006f5a7  xor     r9d, r9d; lpName
0x18006f5aa  xor     r8d, r8d; bInitialState
0x18006f5ad  mov     edx, esi; bManualReset
0x18006f5af  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x18006f5b4  call    cs:__imp_CreateEventW
0x18006f5ba  mov     [rbx+8C8h], rax
0x18006f5c1  test    rax, rax
0x18006f5c4  jnz     short loc_18006F5D0
0x18006f5c6  mov     [rsp+88h+var_68], 9DFh
0x18006f5ce  jmp     short loc_18006F594
0x18006f5d0  cmp     qword ptr [rbx+8D0h], 0
0x18006f5d8  jnz     short loc_18006F603
0x18006f5da  xor     r9d, r9d; lpName
0x18006f5dd  xor     r8d, r8d; bInitialState
0x18006f5e0  mov     edx, esi; bManualReset
0x18006f5e2  lea     rcx, [rsp+88h+EventAttributes]; lpEventAttributes
0x18006f5e7  call    cs:__imp_CreateEventW
0x18006f5ed  mov     [rbx+8D0h], rax
0x18006f5f4  test    rax, rax
0x18006f5f7  jnz     short loc_18006F603
0x18006f5f9  mov     [rsp+88h+var_68], 9EEh
0x18006f601  jmp     short loc_18006F594
0x18006f603  xor     edi, edi
0x18006f605  jmp     short loc_18006F62D
0x18006f607  mov     [rsp+88h+var_68], 9AFh
0x18006f60f  lea     r8, aWerCrashapiUUE_16; "WER/CrashAPI/%u:%u: ERROR Invalid PEB e"...
0x18006f616  mov     r9, gs:40h
0x18006f61f  xor     edx, edx; Level
0x18006f621  mov     ecx, 96h; ComponentId
0x18006f626  call    cs:__imp_DbgPrintEx
0x18006f62c  nop
0x18006f62d  call    cs:__imp_RtlReleasePebLock
0x18006f633  jmp     loc_18006F4F4
0x18007bb2c  push    rbp
0x18007bb2e  sub     rsp, 30h
0x18007bb32  mov     rbp, rdx
0x18007bb35  call    cs:__imp_RtlReleasePebLock
0x18007bb3b  nop
0x18007bb3c  add     rsp, 30h
0x18007bb40  pop     rbp
0x18007bb41  retn
```
