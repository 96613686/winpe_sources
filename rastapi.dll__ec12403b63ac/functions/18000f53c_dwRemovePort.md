# dwRemovePort

- ea: `0x18000f53c`
- end: `0x18000f5e3`
- name: `dwRemovePort`
- size: `167`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180013040`
- `0x180014ca0`

## callees

- `0x18000d92c`
- `0x18000f53c`
- `0x180012340`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f56b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f56b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f5cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f5cb`

## string_xrefs

- `0x18000f553`: `dwRemovePort: %s`

## pseudocode

```c
__int64 __fastcall dwRemovePort(_QWORD *hMem, __int64 a2, __int64 a3, __int64 a4)
{
  void *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx

  GetMutex(hMem, a2, a3, a4);
  if ( hMem )
  {
    RasTapiTrace("dwRemovePort: %s");
    v5 = (void *)hMem[108];
    if ( v5 )
    {
      LocalFree(v5);
      hMem[108] = 0;
      *((_DWORD *)hMem + 218) = 0;
    }
    v6 = RasPortsList;
    if ( RasPortsList == hMem )
    {
      RasPortsList = (HLOCAL)*((_QWORD *)RasPortsList + 1);
LABEL_10:
      LocalFree(hMem);
    }
    else
    {
      while ( v6[1] )
      {
        v7 = v6 + 1;
        v6 = (_QWORD *)v6[1];
        if ( hMem == v6 )
        {
          *v7 = v6[1];
          goto LABEL_10;
        }
      }
    }
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return 0;
}

```

## disassembly

```asm
0x18000f53c  push    rbx
0x18000f53e  sub     rsp, 20h
0x18000f542  mov     rbx, rcx
0x18000f545  call    GetMutex
0x18000f54a  test    rbx, rbx
0x18000f54d  jz      short loc_18000F5C4
0x18000f54f  lea     rdx, [rbx+18h]
0x18000f553  lea     rcx, aDwremoveportS; "dwRemovePort: %s"
0x18000f55a  call    RasTapiTrace
0x18000f55f  mov     rcx, [rbx+360h]; hMem
0x18000f566  test    rcx, rcx
0x18000f569  jz      short loc_18000F586
0x18000f56b  call    cs:__imp_LocalFree
0x18000f571  mov     qword ptr [rbx+360h], 0
0x18000f57c  mov     dword ptr [rbx+368h], 0
0x18000f586  mov     rax, cs:RasPortsList
0x18000f58d  cmp     rax, rbx
0x18000f590  jnz     short loc_18000F5AB
0x18000f592  mov     rax, [rax+8]
0x18000f596  mov     cs:RasPortsList, rax
0x18000f59d  jmp     short loc_18000F5BB
0x18000f59f  lea     rcx, [rax+8]
0x18000f5a3  mov     rax, [rcx]
0x18000f5a6  cmp     rbx, rax
0x18000f5a9  jz      short loc_18000F5B4
0x18000f5ab  cmp     qword ptr [rax+8], 0
0x18000f5b0  jnz     short loc_18000F59F
0x18000f5b2  jmp     short loc_18000F5C4
0x18000f5b4  mov     rax, [rax+8]
0x18000f5b8  mov     [rcx], rax
0x18000f5bb  mov     rcx, rbx; hMem
0x18000f5be  call    cs:__imp_LocalFree
0x18000f5c4  mov     rcx, cs:RasTapiMutex; hMutex
0x18000f5cb  call    cs:__imp_ReleaseMutex
0x18000f5d1  test    eax, eax
0x18000f5d3  jnz     short loc_18000F5DB
0x18000f5d5  call    cs:__imp_GetLastError
0x18000f5db  xor     eax, eax
0x18000f5dd  add     rsp, 20h
0x18000f5e1  pop     rbx
0x18000f5e2  retn
```
