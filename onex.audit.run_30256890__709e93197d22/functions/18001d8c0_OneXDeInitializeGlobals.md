# OneXDeInitializeGlobals

- ea: `0x18001d8c0`
- end: `0x18001d97b`
- name: `OneXDeInitializeGlobals`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019b60`
- `0x18001ee7c`

## callees

- `0x180005440`
- `0x18001d8c0`
- `0x18001d984`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!DeInitializeTimers` at `0x18001d914`
- `MobileNetworking!DeInitializeTimers` at `0x18001d914`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d921`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d92e`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d940`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d921`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d92e`
- `MobileNetworking!DeleteReadWriteLock` at `0x18001d940`

## pseudocode

```c
__int64 OneXDeInitializeGlobals()
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
  qword_18003DD8C = 0;
  qword_18003DD5C = 0;
  dword_18003DD88 = 0;
  DeInitializeTimers(qword_18003DE00);
  DeleteReadWriteLock(g_OneXSsoInfo);
  DeleteReadWriteLock(qword_18003DD98);
  OneXClearSqmRecords();
  DeleteReadWriteLock(qword_18003DE28);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x18001d8c0  push    rdi
0x18001d8c2  sub     rsp, 20h
0x18001d8c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d8cd  lea     rdi, WPP_GLOBAL_Control
0x18001d8d4  cmp     rcx, rdi
0x18001d8d7  jz      short loc_18001D8F7
0x18001d8d9  test    dword ptr [rcx+44h], 800h
0x18001d8e0  jz      short loc_18001D8F7
0x18001d8e2  mov     rcx, [rcx+38h]
0x18001d8e6  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001d8ed  mov     edx, 11h
0x18001d8f2  call    WPP_SF_
0x18001d8f7  mov     rcx, cs:qword_18003DE00
0x18001d8fe  xor     eax, eax
0x18001d900  mov     cs:qword_18003DD8C, rax
0x18001d907  mov     cs:qword_18003DD5C, rax
0x18001d90e  mov     cs:dword_18003DD88, eax
0x18001d914  call    cs:__imp_DeInitializeTimers
0x18001d91a  lea     rcx, g_OneXSsoInfo
0x18001d921  call    cs:__imp_DeleteReadWriteLock
0x18001d927  lea     rcx, qword_18003DD98
0x18001d92e  call    cs:__imp_DeleteReadWriteLock
0x18001d934  call    OneXClearSqmRecords
0x18001d939  lea     rcx, qword_18003DE28
0x18001d940  call    cs:__imp_DeleteReadWriteLock
0x18001d946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d94d  cmp     rcx, rdi
0x18001d950  jz      short loc_18001D973
0x18001d952  test    dword ptr [rcx+44h], 800h
0x18001d959  jz      short loc_18001D973
0x18001d95b  mov     rcx, [rcx+38h]
0x18001d95f  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18001d966  mov     edx, 12h
0x18001d96b  xor     r9d, r9d
0x18001d96e  call    WPP_SF_D
0x18001d973  xor     eax, eax
0x18001d975  add     rsp, 20h
0x18001d979  pop     rdi
0x18001d97a  retn
```
