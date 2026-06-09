# SrvDereferenceKey

- ea: `0x1800055e0`
- end: `0x18000562b`
- name: `SrvDereferenceKey`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003880`
- `0x180003d40`
- `0x1800057a0`
- `0x180005bb0`
- `0x180005d00`
- `0x1800064b0`
- `0x180009ca0`
- `0x18000df70`
- `0x18000e2c0`
- `0x18000e560`
- `0x18000ef60`
- `0x18000f140`
- `0x18000f250`
- `0x18000f4a0`

## callees

- `0x180003cf0`
- `0x1800055e0`
- `0x18000a520`

## string_xrefs

- `0x180005612`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvutils.c`

## pseudocode

```c
__int64 __fastcall SrvDereferenceKey(volatile signed __int64 *a1)
{
  int v2; // eax
  unsigned int v3; // ebx

  if ( _InterlockedExchangeAdd64(a1 + 1, 0xFFFFFFFFFFFFFFFFuLL) != 1 )
    return 0;
  v2 = SrvFreeKey((PVOID)a1);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  DebugTraceError((unsigned int)v2, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvutils.c", 740);
  return v3;
}

```

## disassembly

```asm
0x1800055e0  push    rbx
0x1800055e2  sub     rsp, 20h
0x1800055e6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800055ed  lock xadd [rcx+8], rax
0x1800055f3  cmp     rax, 1
0x1800055f7  jz      short loc_180005601
0x1800055f9  xor     eax, eax
0x1800055fb  add     rsp, 20h
0x1800055ff  pop     rbx
0x180005600  retn
0x180005601  call    SrvFreeKey
0x180005606  mov     ebx, eax
0x180005608  test    eax, eax
0x18000560a  jns     short loc_1800055F9
0x18000560c  mov     r9d, 2E4h
0x180005612  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005619  lea     rdx, aStatus; "Status"
0x180005620  mov     ecx, eax
0x180005622  call    DebugTraceError
0x180005627  mov     eax, ebx
0x180005629  jmp     short loc_1800055FB
```
