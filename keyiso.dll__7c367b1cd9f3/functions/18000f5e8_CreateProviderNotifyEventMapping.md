# _CreateProviderNotifyEventMapping

- ea: `0x18000f5e8`
- end: `0x18000f6c2`
- name: `_CreateProviderNotifyEventMapping`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ec30`

## callees

- `0x180002d20`
- `0x180003cf0`
- `0x180006280`
- `0x18000f5e8`
- `0x18000f88c`

## string_xrefs

- `0x18000f614`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000f675`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall CreateProviderNotifyEventMapping(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v14; // [rsp+40h] [rbp+18h] BYREF

  v14 = 0;
  if ( a3 )
  {
    v7 = MSCryptAlloc(40);
    *a3 = v7;
    if ( v7 )
    {
      v10 = RPCClientDuplicateHandle(a1, a2, &v14);
      v6 = v10;
      if ( v10 >= 0 )
      {
        v11 = *a3;
        v6 = 0;
        v12 = v14;
        *(_QWORD *)(v11 + 16) = a2;
        *(_QWORD *)(v11 + 24) = v12;
        return v6;
      }
      v8 = (unsigned int)v10;
      v9 = 397;
    }
    else
    {
      v6 = -1073741801;
      v8 = 3221225495LL;
      v9 = 382;
    }
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", v9);
    if ( *a3 )
    {
      MSCryptFree(*a3);
      *a3 = 0;
    }
  }
  else
  {
    v6 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 373);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f5e8  mov     [rsp+arg_0], rbx
0x18000f5ed  mov     [rsp+arg_8], rsi
0x18000f5f2  push    rdi
0x18000f5f3  sub     rsp, 20h
0x18000f5f7  mov     [rsp+28h+arg_10], 0
0x18000f600  mov     rdi, r8
0x18000f603  mov     rsi, rdx
0x18000f606  mov     rbx, rcx
0x18000f609  test    r8, r8
0x18000f60c  jnz     short loc_18000F633
0x18000f60e  mov     r9d, 175h
0x18000f614  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f61b  lea     rdx, aStatus; "Status"
0x18000f622  mov     ecx, 0C000000Dh
0x18000f627  mov     ebx, 0C000000Dh
0x18000f62c  call    DebugTraceError
0x18000f631  jmp     short loc_18000F6B0
0x18000f633  mov     ecx, 28h ; '('
0x18000f638  call    MSCryptAlloc
0x18000f63d  mov     [rdi], rax
0x18000f640  test    rax, rax
0x18000f643  jnz     short loc_18000F657
0x18000f645  mov     ebx, 0C0000017h
0x18000f64a  mov     ecx, 0C0000017h
0x18000f64f  mov     r9d, 17Eh
0x18000f655  jmp     short loc_18000F675
0x18000f657  lea     r8, [rsp+28h+arg_10]
0x18000f65c  mov     rdx, rsi
0x18000f65f  mov     rcx, rbx
0x18000f662  call    _RPCClientDuplicateHandle
0x18000f667  mov     ebx, eax
0x18000f669  test    eax, eax
0x18000f66b  jns     short loc_18000F69E
0x18000f66d  mov     ecx, eax
0x18000f66f  mov     r9d, 18Dh
0x18000f675  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f67c  lea     rdx, aStatus; "Status"
0x18000f683  call    DebugTraceError
0x18000f688  mov     rcx, [rdi]
0x18000f68b  test    rcx, rcx
0x18000f68e  jz      short loc_18000F6B0
0x18000f690  call    MSCryptFree
0x18000f695  mov     qword ptr [rdi], 0
0x18000f69c  jmp     short loc_18000F6B0
0x18000f69e  mov     rcx, [rdi]
0x18000f6a1  xor     ebx, ebx
0x18000f6a3  mov     rax, [rsp+28h+arg_10]
0x18000f6a8  mov     [rcx+10h], rsi
0x18000f6ac  mov     [rcx+18h], rax
0x18000f6b0  mov     rsi, [rsp+28h+arg_8]
0x18000f6b5  mov     eax, ebx
0x18000f6b7  mov     rbx, [rsp+28h+arg_0]
0x18000f6bc  add     rsp, 20h
0x18000f6c0  pop     rdi
0x18000f6c1  retn
```
