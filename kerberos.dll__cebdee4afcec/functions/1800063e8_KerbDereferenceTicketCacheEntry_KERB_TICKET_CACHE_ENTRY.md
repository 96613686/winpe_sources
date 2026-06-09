# KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)

- ea: `0x1800063e8`
- end: `0x180006549`
- name: `?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z`
- size: `353`
- prototype: `void __fastcall(struct _KERB_TICKET_CACHE_ENTRY *)`
- caller_count: `70`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800063e8`
- `0x180006680`
- `0x180006ddc`
- `0x1800083b4`
- `0x1800097b0`
- `0x18000b430`
- `0x18000b5c0`
- `0x180019678`
- `0x180021574`
- `0x180025680`
- `0x18002bd40`
- `0x180034158`
- `0x1800376ec`
- `0x180037aa0`
- `0x18003d7d0`
- `0x18003e488`
- `0x18003eb80`
- `0x180041178`
- `0x180041758`
- `0x180041ff0`
- `0x180042a40`
- `0x180048f6c`
- `0x18004969c`
- `0x18004ed20`
- `0x18004fa28`
- `0x1800545ec`
- `0x1800548b4`
- `0x180054c88`
- `0x1800566a8`
- `0x180057f58`
- `0x180058f14`
- `0x18005b210`
- `0x180061e4c`
- `0x18006250c`
- `0x1800640b0`
- `0x1800654c8`
- `0x180065644`
- `0x180082ef4`
- `0x180086c14`
- `0x180086d4c`
- `0x1800872a0`
- `0x180088040`
- `0x180088264`
- `0x18008e4f4`
- `0x180090068`
- `0x180090d08`
- `0x180091024`
- `0x180091180`
- `0x1800911f0`
- `0x18009d1c4`

## callees

- `0x18000623c`
- `0x1800063e8`
- `0x1800068d0`
- `0x180006920`
- `0x1800069a0`
- `0x1800069e0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000647e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000647e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000645a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000645a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000646b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006478`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000646b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006478`
- `ntdll!NtQuerySystemInformation` at `0x18000642f`
- `ntdll!NtQuerySystemInformation` at `0x18000642f`
- `ntdll!RtlDeleteCriticalSection` at `0x180006519`
- `ntdll!RtlDeleteCriticalSection` at `0x180006519`

## string_xrefs

- `0x180006464`: `!TicketCacheEntry->Linked`

## pseudocode

```c
void __fastcall KerbDereferenceTicketCacheEntry(struct _KERB_TICKET_CACHE_ENTRY *a1)
{
  struct _KERB_TICKET_CACHE_ENTRY *v2; // rcx
  __int16 SystemInformation; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, 0xFFFFFFFF) == 1 )
  {
    if ( *((_DWORD *)a1 + 6) )
    {
      if ( !dword_18014549C )
      {
        SystemInformation = 0;
        if ( NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0) >= 0
          && (_BYTE)SystemInformation )
        {
          dword_180145498 = 1;
        }
        dword_18014549C = 1;
      }
      if ( dword_180145498 || IsDebuggerPresent() )
      {
        OutputDebugStringA("!TicketCacheEntry->Linked");
        OutputDebugStringA("\n");
        DebugBreak();
      }
    }
    _InterlockedDecrement(&GlobalTicketListSize);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 4);
    KerbFreeString((__int64)a1 + 48);
    KerbFreeString((__int64)a1 + 64);
    KerbFreeString((__int64)a1 + 80);
    KerbFreeString((__int64)a1 + 96);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 18);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 19);
    KerbFreeKdcName((struct _KERB_INTERNAL_NAME **)a1 + 5);
    KerbFreeDuplicatedTicket((char *)a1 + 272);
    KerbFreeKey((char *)a1 + 168);
    KerbFreeKey((char *)a1 + 208);
    KerbFreeString((__int64)a1 + 112);
    KerbFreeString((__int64)a1 + 128);
    RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)a1 + 368));
    v2 = (struct _KERB_TICKET_CACHE_ENTRY *)*((_QWORD *)a1 + 55);
    *((_QWORD *)a1 + 56) = 0;
    if ( v2 )
      KerbDereferenceTicketCacheEntry(v2);
    KerbFree(a1);
  }
}

```

## disassembly

```asm
0x1800063e8  test    rcx, rcx
0x1800063eb  jz      locret_180006548
0x1800063f1  push    rbx
0x1800063f2  sub     rsp, 20h
0x1800063f6  mov     rbx, rcx
0x1800063f9  or      eax, 0FFFFFFFFh
0x1800063fc  lock xadd [rcx+10h], eax
0x180006401  cmp     eax, 1
0x180006404  jnz     loc_180006543
0x18000640a  cmp     dword ptr [rcx+18h], 0
0x18000640e  jz      short loc_180006484
0x180006410  cmp     cs:dword_18014549C, 0
0x180006417  jnz     short loc_180006451
0x180006419  xor     eax, eax
0x18000641b  lea     rdx, [rsp+28h+SystemInformation]; SystemInformation
0x180006420  xor     r9d, r9d; ReturnLength
0x180006423  mov     [rsp+28h+SystemInformation], ax
0x180006428  lea     r8d, [rax+2]; SystemInformationLength
0x18000642c  lea     ecx, [rax+23h]; SystemInformationClass
0x18000642f  call    cs:__imp_NtQuerySystemInformation
0x180006435  mov     ecx, 1
0x18000643a  test    eax, eax
0x18000643c  js      short loc_18000644B
0x18000643e  cmp     byte ptr [rsp+28h+SystemInformation], 0
0x180006443  jz      short loc_18000644B
0x180006445  mov     cs:dword_180145498, ecx
0x18000644b  mov     cs:dword_18014549C, ecx
0x180006451  cmp     cs:dword_180145498, 0
0x180006458  jnz     short loc_180006464
0x18000645a  call    cs:__imp_IsDebuggerPresent
0x180006460  test    eax, eax
0x180006462  jz      short loc_180006484
0x180006464  lea     rcx, OutputString; "!TicketCacheEntry->Linked"
0x18000646b  call    cs:__imp_OutputDebugStringA
0x180006471  lea     rcx, asc_180103DF0; "\n"
0x180006478  call    cs:__imp_OutputDebugStringA
0x18000647e  call    cs:__imp_DebugBreak
0x180006484  lock dec cs:?GlobalTicketListSize@@3JA; long GlobalTicketListSize
0x18000648b  lea     rcx, [rbx+20h]; struct _KERB_INTERNAL_NAME **
0x18000648f  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x180006494  lea     rcx, [rbx+30h]
0x180006498  call    KerbFreeString
0x18000649d  lea     rcx, [rbx+40h]
0x1800064a1  call    KerbFreeString
0x1800064a6  lea     rcx, [rbx+50h]
0x1800064aa  call    KerbFreeString
0x1800064af  lea     rcx, [rbx+60h]
0x1800064b3  call    KerbFreeString
0x1800064b8  lea     rcx, [rbx+90h]; struct _KERB_INTERNAL_NAME **
0x1800064bf  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x1800064c4  lea     rcx, [rbx+98h]; struct _KERB_INTERNAL_NAME **
0x1800064cb  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x1800064d0  lea     rcx, [rbx+28h]; struct _KERB_INTERNAL_NAME **
0x1800064d4  call    ?KerbFreeKdcName@@YAXPEAPEAU_KERB_INTERNAL_NAME@@@Z; KerbFreeKdcName(_KERB_INTERNAL_NAME * *)
0x1800064d9  lea     rcx, [rbx+110h]
0x1800064e0  call    KerbFreeDuplicatedTicket
0x1800064e5  lea     rcx, [rbx+0A8h]
0x1800064ec  call    KerbFreeKey
0x1800064f1  lea     rcx, [rbx+0D0h]
0x1800064f8  call    KerbFreeKey
0x1800064fd  lea     rcx, [rbx+70h]
0x180006501  call    KerbFreeString
0x180006506  lea     rcx, [rbx+80h]
0x18000650d  call    KerbFreeString
0x180006512  lea     rcx, [rbx+170h]; CriticalSection
0x180006519  call    cs:__imp_RtlDeleteCriticalSection
0x18000651f  mov     rcx, [rbx+1B8h]; struct _KERB_TICKET_CACHE_ENTRY *
0x180006526  mov     qword ptr [rbx+1C0h], 0
0x180006531  test    rcx, rcx
0x180006534  jz      short loc_18000653B
0x180006536  call    ?KerbDereferenceTicketCacheEntry@@YAXPEAU_KERB_TICKET_CACHE_ENTRY@@@Z; KerbDereferenceTicketCacheEntry(_KERB_TICKET_CACHE_ENTRY *)
0x18000653b  mov     rcx, rbx
0x18000653e  call    KerbFree
0x180006543  add     rsp, 20h
0x180006547  pop     rbx
0x180006548  retn
```
