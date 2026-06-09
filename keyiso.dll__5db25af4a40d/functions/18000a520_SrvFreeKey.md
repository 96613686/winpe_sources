# SrvFreeKey

- ea: `0x18000a520`
- end: `0x18000a5b7`
- name: `SrvFreeKey`
- size: `151`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800023b0`
- `0x1800035c0`
- `0x1800041b0`
- `0x1800055e0`
- `0x180007140`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180005510`
- `0x180006e60`
- `0x18000a520`
- `0x18000a6cc`
- `0x18000a8e8`
- `0x180019010`

## string_xrefs

- `0x18000a554`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvFreeKey(PVOID P)
{
  int v2; // eax
  int v3; // ebx
  int v4; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)P + 4) + 128LL))(
         *(_QWORD *)(*((_QWORD *)P + 4) + 296LL),
         *((_QWORD *)P + 5));
  v3 = v2;
  if ( v2 < 0 )
  {
    DebugTraceError(
      (unsigned int)v2,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      3734);
    v3 = NormalizeNteStatus((unsigned int)v3);
  }
  if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
    DecrementKeyIsoPerfCounter(*(PPERF_COUNTERSET_INSTANCE *)(*((_QWORD *)P + 4) + 368LL), 2u);
  v4 = SrvDereferenceProvider(*((volatile signed __int64 **)P + 4));
  if ( v4 < 0 && v3 >= 0 )
    v3 = v4;
  SrvCryptLocalFree(P);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000a520  mov     [rsp+arg_0], rbx
0x18000a525  push    rdi
0x18000a526  sub     rsp, 20h
0x18000a52a  mov     rdi, rcx
0x18000a52d  mov     rcx, [rcx+20h]
0x18000a531  mov     rax, [rcx+80h]
0x18000a538  mov     rcx, [rcx+128h]
0x18000a53f  mov     rdx, [rdi+28h]
0x18000a543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a548  mov     ebx, eax
0x18000a54a  test    eax, eax
0x18000a54c  jns     short loc_18000A572
0x18000a54e  mov     r9d, 0E96h
0x18000a554  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a55b  lea     rdx, aStatus; "Status"
0x18000a562  mov     ecx, eax
0x18000a564  call    DebugTraceError
0x18000a569  mov     ecx, ebx
0x18000a56b  call    NormalizeNteStatus
0x18000a570  mov     ebx, eax
0x18000a572  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x18000a577  test    eax, eax
0x18000a579  jz      short loc_18000A590
0x18000a57b  mov     rcx, [rdi+20h]
0x18000a57f  mov     edx, 2; CounterId
0x18000a584  mov     rcx, [rcx+170h]; Instance
0x18000a58b  call    DecrementKeyIsoPerfCounter
0x18000a590  mov     rcx, [rdi+20h]
0x18000a594  call    SrvDereferenceProvider
0x18000a599  test    eax, eax
0x18000a59b  jns     short loc_18000A5A2
0x18000a59d  test    ebx, ebx
0x18000a59f  cmovns  ebx, eax
0x18000a5a2  mov     rcx, rdi; P
0x18000a5a5  call    SrvCryptLocalFree
0x18000a5aa  mov     eax, ebx
0x18000a5ac  mov     rbx, [rsp+28h+arg_0]
0x18000a5b1  add     rsp, 20h
0x18000a5b5  pop     rdi
0x18000a5b6  retn
```
