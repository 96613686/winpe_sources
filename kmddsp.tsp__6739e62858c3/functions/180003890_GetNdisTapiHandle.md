# GetNdisTapiHandle

- ea: `0x180003890`
- end: `0x180003926`
- name: `GetNdisTapiHandle`
- size: `150`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `15`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004310`
- `0x180004400`
- `0x180004670`
- `0x1800049a0`
- `0x180004bc0`
- `0x180004d30`
- `0x180005440`
- `0x180005550`
- `0x1800058b0`
- `0x180005db0`
- `0x180006d40`
- `0x180006fb0`
- `0x1800070c0`
- `0x1800071b0`
- `0x1800074c0`

## callees

- `0x180002494`
- `0x180003294`
- `0x180003890`
- `0x180007df8`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800038e5`
- `KERNEL32!Sleep` at `0x1800038e5`

## string_xrefs

- `0x1800038c7`: `GetNdisTapiHandle: wait for the outbound call to complete...`

## pseudocode

```c
__int64 __fastcall GetNdisTapiHandle(__int64 a1, _DWORD *a2)
{
  __int64 v2; // rsi
  int v5; // eax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  v7 = a1;
  if ( a2 )
    *a2 = 0;
  if ( *(_DWORD *)a1 == 1329807692 && *(_DWORD *)(a1 + 64) )
  {
    TspLog(4, "GetNdisTapiHandle: wait for the outbound call to complete...");
    while ( 1 )
    {
      ReleaseObjReadLock(v2);
      Sleep(0xFAu);
      v5 = GetCallObjWithReadLock(v2, &v7);
      if ( v5 )
        break;
      if ( !*(_DWORD *)(v7 + 64) )
        return *(_QWORD *)(a1 + 24);
    }
    *a2 = v5;
  }
  return *(_QWORD *)(a1 + 24);
}

```

## disassembly

```asm
0x180003890  mov     [rsp+arg_8], rbx
0x180003895  mov     [rsp+arg_10], rsi
0x18000389a  push    rdi
0x18000389b  sub     rsp, 20h
0x18000389f  mov     rsi, [rcx+10h]
0x1800038a3  mov     rdi, rdx
0x1800038a6  mov     [rsp+28h+arg_0], rcx
0x1800038ab  mov     rbx, rcx
0x1800038ae  test    rdx, rdx
0x1800038b1  jz      short loc_1800038B9
0x1800038b3  mov     dword ptr [rdx], 0
0x1800038b9  cmp     dword ptr [rcx], 4F43414Ch
0x1800038bf  jnz     short loc_180003911
0x1800038c1  cmp     dword ptr [rcx+40h], 0
0x1800038c5  jz      short loc_180003911
0x1800038c7  lea     rdx, aGetndistapihan; "GetNdisTapiHandle: wait for the outboun"...
0x1800038ce  mov     ecx, 4
0x1800038d3  call    TspLog
0x1800038d8  mov     rcx, rsi
0x1800038db  call    ReleaseObjReadLock
0x1800038e0  mov     ecx, 0FAh; dwMilliseconds
0x1800038e5  call    cs:__imp_Sleep
0x1800038ec  nop     dword ptr [rax+rax+00h]
0x1800038f1  lea     rdx, [rsp+28h+arg_0]
0x1800038f6  mov     rcx, rsi
0x1800038f9  call    GetCallObjWithReadLock
0x1800038fe  test    eax, eax
0x180003900  jnz     short loc_18000390F
0x180003902  mov     rax, [rsp+28h+arg_0]
0x180003907  cmp     dword ptr [rax+40h], 0
0x18000390b  jnz     short loc_1800038D8
0x18000390d  jmp     short loc_180003911
0x18000390f  mov     [rdi], eax
0x180003911  mov     rax, [rbx+18h]
0x180003915  mov     rbx, [rsp+28h+arg_8]
0x18000391a  mov     rsi, [rsp+28h+arg_10]
0x18000391f  add     rsp, 20h
0x180003923  pop     rdi
0x180003924  retn
```
