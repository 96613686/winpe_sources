# OneXFreeRuntimeState

- ea: `0x180019f7c`
- end: `0x180019ff8`
- name: `OneXFreeRuntimeState`
- size: `124`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b330`
- `0x18000ba30`
- `0x180010d40`
- `0x18001a198`
- `0x18001e930`

## callees

- `0x180019f7c`
- `0x18001f414`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f9f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019f9f`
- `MobileNetworking!FreeMemory` at `0x180019fcc`
- `MobileNetworking!FreeMemory` at `0x180019fec`
- `MobileNetworking!FreeMemory` at `0x180019fcc`
- `MobileNetworking!FreeMemory` at `0x180019fec`

## pseudocode

```c
void __fastcall OneXFreeRuntimeState(__int64 a1)
{
  __int64 v2; // rax
  void *v3; // rcx
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v4 = a1;
    v2 = a1;
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      v3 = *(void **)(a1 + 8);
      if ( v3 )
      {
        CloseHandle(v3);
        v2 = v4;
      }
    }
    if ( (*(_BYTE *)v2 & 2) != 0 && *(_DWORD *)(v2 + 16) )
    {
      if ( *(_QWORD *)(v2 + 24) )
        FreeMemory(v2 + 24, "OneXFreeRuntimeState", 307);
    }
    OneXDeleteEAPCredentials(a1);
    FreeMemory(&v4, "OneXFreeRuntimeState", 312);
  }
}

```

## disassembly

```asm
0x180019f7c  test    rcx, rcx
0x180019f7f  jz      short locret_180019FF7
0x180019f81  push    rbx
0x180019f82  sub     rsp, 20h
0x180019f86  mov     [rsp+28h+arg_0], rcx
0x180019f8b  mov     rbx, rcx
0x180019f8e  test    byte ptr [rcx], 1
0x180019f91  mov     rax, rcx
0x180019f94  jz      short loc_180019FAA
0x180019f96  mov     rcx, [rcx+8]; hObject
0x180019f9a  test    rcx, rcx
0x180019f9d  jz      short loc_180019FAA
0x180019f9f  call    cs:__imp_CloseHandle
0x180019fa5  mov     rax, [rsp+28h+arg_0]
0x180019faa  test    byte ptr [rax], 2
0x180019fad  jz      short loc_180019FD2
0x180019faf  cmp     dword ptr [rax+10h], 0
0x180019fb3  jz      short loc_180019FD2
0x180019fb5  lea     rcx, [rax+18h]
0x180019fb9  cmp     qword ptr [rcx], 0
0x180019fbd  jz      short loc_180019FD2
0x180019fbf  mov     r8d, 133h
0x180019fc5  lea     rdx, aOnexfreeruntim; "OneXFreeRuntimeState"
0x180019fcc  call    cs:__imp_FreeMemory
0x180019fd2  mov     rcx, rbx
0x180019fd5  call    OneXDeleteEAPCredentials
0x180019fda  mov     r8d, 138h
0x180019fe0  lea     rdx, aOnexfreeruntim; "OneXFreeRuntimeState"
0x180019fe7  lea     rcx, [rsp+28h+arg_0]
0x180019fec  call    cs:__imp_FreeMemory
0x180019ff2  add     rsp, 20h
0x180019ff6  pop     rbx
0x180019ff7  retn
```
