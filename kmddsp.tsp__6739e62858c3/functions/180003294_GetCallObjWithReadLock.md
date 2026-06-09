# GetCallObjWithReadLock

- ea: `0x180003294`
- end: `0x180003309`
- name: `GetCallObjWithReadLock`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `4`
- tags: ``

## callers

- `0x180003890`
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

- `0x180001f48`
- `0x180002494`
- `0x180003294`
- `0x180007df8`

## string_xrefs

- `0x1800032da`: `GetCallObjWithReadLock: obj(%p) has bad key(%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithReadLock(const void *a1, _QWORD *a2)
{
  __int64 v5; // rdx
  _DWORD *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  if ( (unsigned int)GetObjWithReadLock(a1, &v6) )
    return 2147483672LL;
  if ( *v6 != 1229144396 && *v6 != 1329807692 )
  {
    TspLog(2, "GetCallObjWithReadLock: obj(%p) has bad key(%x)", a1, *v6);
    ReleaseObjReadLock(a1, v5);
    return 2147483672LL;
  }
  *a2 = v6;
  return 0;
}

```

## disassembly

```asm
0x180003294  mov     [rsp+arg_0], rbx
0x180003299  push    rdi
0x18000329a  sub     rsp, 20h
0x18000329e  mov     rdi, rdx
0x1800032a1  mov     [rsp+28h+arg_10], 0
0x1800032aa  lea     rdx, [rsp+28h+arg_10]
0x1800032af  mov     rbx, rcx
0x1800032b2  call    GetObjWithReadLock
0x1800032b7  test    eax, eax
0x1800032b9  jz      short loc_1800032C2
0x1800032bb  mov     eax, 80000018h
0x1800032c0  jmp     short loc_1800032FD
0x1800032c2  mov     rax, [rsp+28h+arg_10]
0x1800032c7  cmp     dword ptr [rax], 4943414Ch
0x1800032cd  jz      short loc_1800032F8
0x1800032cf  cmp     dword ptr [rax], 4F43414Ch
0x1800032d5  jz      short loc_1800032F8
0x1800032d7  mov     r9d, [rax]
0x1800032da  lea     rdx, aGetcallobjwith_0; "GetCallObjWithReadLock: obj(%p) has bad"...
0x1800032e1  mov     r8, rbx
0x1800032e4  mov     ecx, 2
0x1800032e9  call    TspLog
0x1800032ee  mov     rcx, rbx
0x1800032f1  call    ReleaseObjReadLock
0x1800032f6  jmp     short loc_1800032BB
0x1800032f8  mov     [rdi], rax
0x1800032fb  xor     eax, eax
0x1800032fd  mov     rbx, [rsp+28h+arg_0]
0x180003302  add     rsp, 20h
0x180003306  pop     rdi
0x180003307  retn
```
