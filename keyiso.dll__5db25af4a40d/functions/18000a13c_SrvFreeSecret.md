# SrvFreeSecret

- ea: `0x18000a13c`
- end: `0x18000a1d3`
- name: `SrvFreeSecret`
- size: `151`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180008f00`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180005510`
- `0x180006e60`
- `0x18000a13c`
- `0x18000a6cc`
- `0x18000a8e8`
- `0x180019010`

## string_xrefs

- `0x18000a170`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvFreeSecret(PVOID P)
{
  int v2; // eax
  int v3; // ebx
  int v4; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)P + 4) + 248LL))(
         *(_QWORD *)(*((_QWORD *)P + 4) + 296LL),
         *((_QWORD *)P + 5));
  v3 = v2;
  if ( v2 < 0 )
  {
    DebugTraceError(
      (unsigned int)v2,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      3788);
    v3 = NormalizeNteStatus((unsigned int)v3);
  }
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    DecrementKeyIsoPerfCounter(*(PPERF_COUNTERSET_INSTANCE *)(*((_QWORD *)P + 4) + 368LL), 3u);
  v4 = SrvDereferenceProvider(*((volatile signed __int64 **)P + 4));
  if ( v4 < 0 && v3 >= 0 )
    v3 = v4;
  SrvCryptLocalFree(P);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a13c  mov     [rsp+arg_0], rbx
0x18000a141  push    rdi
0x18000a142  sub     rsp, 20h
0x18000a146  mov     rdi, rcx
0x18000a149  mov     rcx, [rcx+20h]
0x18000a14d  mov     rax, [rcx+0F8h]
0x18000a154  mov     rcx, [rcx+128h]
0x18000a15b  mov     rdx, [rdi+28h]
0x18000a15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a164  mov     ebx, eax
0x18000a166  test    eax, eax
0x18000a168  jns     short loc_18000A18E
0x18000a16a  mov     r9d, 0ECCh
0x18000a170  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a177  lea     rdx, aStatus; "Status"
0x18000a17e  mov     ecx, eax
0x18000a180  call    DebugTraceError
0x18000a185  mov     ecx, ebx
0x18000a187  call    NormalizeNteStatus
0x18000a18c  mov     ebx, eax
0x18000a18e  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x18000a193  test    eax, eax
0x18000a195  jz      short loc_18000A1AC
0x18000a197  mov     rcx, [rdi+20h]
0x18000a19b  mov     edx, 3; CounterId
0x18000a1a0  mov     rcx, [rcx+170h]; Instance
0x18000a1a7  call    DecrementKeyIsoPerfCounter
0x18000a1ac  mov     rcx, [rdi+20h]
0x18000a1b0  call    SrvDereferenceProvider
0x18000a1b5  test    eax, eax
0x18000a1b7  jns     short loc_18000A1BE
0x18000a1b9  test    ebx, ebx
0x18000a1bb  cmovns  ebx, eax
0x18000a1be  mov     rcx, rdi; P
0x18000a1c1  call    SrvCryptLocalFree
0x18000a1c6  mov     eax, ebx
0x18000a1c8  mov     rbx, [rsp+28h+arg_0]
0x18000a1cd  add     rsp, 20h
0x18000a1d1  pop     rdi
0x18000a1d2  retn
```
