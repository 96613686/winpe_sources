# GetCallObjWithWriteLock

- ea: `0x180003310`
- end: `0x180003385`
- name: `GetCallObjWithWriteLock`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ec0`
- `0x1800066e0`

## callees

- `0x180001fe4`
- `0x180002508`
- `0x180003310`
- `0x180007df8`

## string_xrefs

- `0x180003356`: `GetCallObjWithWriteLock: obj(%p) has bad key(%x)`

## pseudocode

```c
__int64 __fastcall GetCallObjWithWriteLock(const void *a1, _QWORD *a2)
{
  _DWORD *v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  if ( (unsigned int)GetObjWithWriteLock(a1, &v5) )
    return 2147483672LL;
  if ( *v5 != 1229144396 && *v5 != 1329807692 )
  {
    TspLog(2, "GetCallObjWithWriteLock: obj(%p) has bad key(%x)", a1, *v5);
    ReleaseObjWriteLock(a1);
    return 2147483672LL;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003310  mov     [rsp+arg_0], rbx
0x180003315  push    rdi
0x180003316  sub     rsp, 20h
0x18000331a  mov     rdi, rdx
0x18000331d  mov     [rsp+28h+arg_10], 0
0x180003326  lea     rdx, [rsp+28h+arg_10]
0x18000332b  mov     rbx, rcx
0x18000332e  call    GetObjWithWriteLock
0x180003333  test    eax, eax
0x180003335  jz      short loc_18000333E
0x180003337  mov     eax, 80000018h
0x18000333c  jmp     short loc_180003379
0x18000333e  mov     rax, [rsp+28h+arg_10]
0x180003343  cmp     dword ptr [rax], 4943414Ch
0x180003349  jz      short loc_180003374
0x18000334b  cmp     dword ptr [rax], 4F43414Ch
0x180003351  jz      short loc_180003374
0x180003353  mov     r9d, [rax]
0x180003356  lea     rdx, aGetcallobjwith; "GetCallObjWithWriteLock: obj(%p) has ba"...
0x18000335d  mov     r8, rbx
0x180003360  mov     ecx, 2
0x180003365  call    TspLog
0x18000336a  mov     rcx, rbx
0x18000336d  call    ReleaseObjWriteLock
0x180003372  jmp     short loc_180003337
0x180003374  mov     [rdi], rax
0x180003377  xor     eax, eax
0x180003379  mov     rbx, [rsp+28h+arg_0]
0x18000337e  add     rsp, 20h
0x180003382  pop     rdi
0x180003383  retn
```
