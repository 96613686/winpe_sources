# GetLineHandleFromCallHandle

- ea: `0x180003720`
- end: `0x1800037a0`
- name: `GetLineHandleFromCallHandle`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180004670`
- `0x180004ec0`
- `0x1800066e0`

## callees

- `0x180001f48`
- `0x180002494`
- `0x180003720`
- `0x180007df8`

## pseudocode

```c
__int64 __fastcall GetLineHandleFromCallHandle(const void *a1, _QWORD *a2)
{
  __int64 v4; // rdx
  unsigned int v6; // ebx
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  if ( (unsigned int)GetObjWithReadLock(a1, &v7) )
    return 2147483672LL;
  if ( *(_DWORD *)v7 == 1229144396 || *(_DWORD *)v7 == 1329807692 )
  {
    *a2 = *(_QWORD *)(v7 + 32);
    v6 = 0;
  }
  else
  {
    TspLog(2, "GetLineHandleFromCallHandle: obj(%p) has bad key(%x)", a1, *(_DWORD *)v7);
    v6 = -2147483624;
  }
  ReleaseObjReadLock(a1, v4);
  return v6;
}

```

## disassembly

```asm
0x180003720  mov     [rsp+arg_0], rbx
0x180003725  push    rdi
0x180003726  sub     rsp, 20h
0x18000372a  mov     rbx, rdx
0x18000372d  mov     [rsp+28h+arg_10], 0
0x180003736  lea     rdx, [rsp+28h+arg_10]
0x18000373b  mov     rdi, rcx
0x18000373e  call    GetObjWithReadLock
0x180003743  test    eax, eax
0x180003745  jz      short loc_18000374E
0x180003747  mov     eax, 80000018h
0x18000374c  jmp     short loc_180003794
0x18000374e  mov     rax, [rsp+28h+arg_10]
0x180003753  cmp     dword ptr [rax], 4943414Ch
0x180003759  jz      short loc_180003781
0x18000375b  cmp     dword ptr [rax], 4F43414Ch
0x180003761  jz      short loc_180003781
0x180003763  mov     r9d, [rax]
0x180003766  lea     rdx, aGetlinehandlef; "GetLineHandleFromCallHandle: obj(%p) ha"...
0x18000376d  mov     r8, rdi
0x180003770  mov     ecx, 2
0x180003775  call    TspLog
0x18000377a  mov     ebx, 80000018h
0x18000377f  jmp     short loc_18000378A
0x180003781  mov     rax, [rax+20h]
0x180003785  mov     [rbx], rax
0x180003788  xor     ebx, ebx
0x18000378a  mov     rcx, rdi
0x18000378d  call    ReleaseObjReadLock
0x180003792  mov     eax, ebx
0x180003794  mov     rbx, [rsp+28h+arg_0]
0x180003799  add     rsp, 20h
0x18000379d  pop     rdi
0x18000379e  retn
```
