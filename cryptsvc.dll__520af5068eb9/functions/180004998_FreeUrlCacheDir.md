# FreeUrlCacheDir

- ea: `0x180004998`
- end: `0x180004aac`
- name: `FreeUrlCacheDir`
- size: `276`
- prototype: `__int64 __fastcall(HLOCAL hMem, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800041bc`
- `0x180005700`
- `0x18000fdac`

## callees

- `0x18000251c`
- `0x180003b60`
- `0x180004998`
- `0x1800068b0`
- `0x180008dc0`
- `0x18000d4c0`

## import_xrefs

- `CRYPT32!I_CryptFreeLruCache` at `0x180004a2b`
- `CRYPT32!I_CryptFreeLruCache` at `0x180004a2b`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x1800049cb`
- `api-ms-win-core-file-l1-1-0!FindCloseChangeNotification` at `0x1800049cb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004a50`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180004a50`

## pseudocode

```c
__int64 __fastcall FreeUrlCacheDir(HLOCAL hMem, int a2)
{
  void *v4; // rcx
  char *v5; // rcx
  __int64 result; // rax
  void *v7; // rcx

  if ( hMem )
  {
    v4 = (void *)*((_QWORD *)hMem + 8);
    if ( v4 )
    {
      UnregisterWaitEx(v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)hMem + 8) = 0;
    }
    v5 = (char *)*((_QWORD *)hMem + 7);
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      FindCloseChangeNotification(v5);
      *((_QWORD *)hMem + 7) = 0;
    }
    if ( *((_QWORD *)hMem + 10) )
    {
      RemoveToBeRunJob();
      FreeScanJob(*((HLOCAL *)hMem + 10));
      *((_QWORD *)hMem + 10) = 0;
    }
    if ( *((_QWORD *)hMem + 11) )
    {
      if ( !a2 )
        RemoveToBeRunJob();
      v7 = (void *)*((_QWORD *)hMem + 11);
      if ( v7 )
        PkiFree(v7);
      *((_QWORD *)hMem + 11) = 0;
    }
    while ( *((_QWORD *)hMem + 5) )
      RemovePreFetchJobFromDir(*((HLOCAL *)hMem + 5));
    PkiFree(*((HLOCAL *)hMem + 3));
    PkiFree(*((HLOCAL *)hMem + 4));
    if ( *((_QWORD *)hMem + 13) )
    {
      FreeCacheFileEntries(hMem, 1);
      I_CryptFreeLruCache(*((_QWORD *)hMem + 13), 0, 0);
      *((_QWORD *)hMem + 13) = 0;
    }
    return PkiFree(hMem);
  }
  return result;
}

```

## disassembly

```asm
0x180004998  test    rcx, rcx
0x18000499b  jz      locret_180004A4B
0x1800049a1  mov     [rsp+arg_0], rbx
0x1800049a6  push    rdi
0x1800049a7  sub     rsp, 20h
0x1800049ab  mov     rbx, rcx
0x1800049ae  mov     edi, edx
0x1800049b0  mov     rcx, [rcx+40h]; WaitHandle
0x1800049b4  test    rcx, rcx
0x1800049b7  jnz     loc_180004A4C
0x1800049bd  mov     rcx, [rbx+38h]; hChangeHandle
0x1800049c1  lea     rax, [rcx-1]
0x1800049c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800049c9  ja      short loc_1800049D9
0x1800049cb  call    cs:__imp_FindCloseChangeNotification
0x1800049d1  mov     qword ptr [rbx+38h], 0
0x1800049d9  mov     rcx, [rbx+50h]
0x1800049dd  test    rcx, rcx
0x1800049e0  jnz     loc_180004A6D
0x1800049e6  mov     rcx, [rbx+58h]
0x1800049ea  test    rcx, rcx
0x1800049ed  jnz     loc_180004A88
0x1800049f3  mov     rax, [rbx+28h]
0x1800049f7  test    rax, rax
0x1800049fa  jnz     short loc_180004A63
0x1800049fc  mov     rcx, [rbx+18h]; hMem
0x180004a00  call    PkiFree
0x180004a05  mov     rcx, [rbx+20h]; hMem
0x180004a09  call    PkiFree
0x180004a0e  cmp     qword ptr [rbx+68h], 0
0x180004a13  jz      short loc_180004A39
0x180004a15  mov     edx, 1
0x180004a1a  mov     rcx, rbx
0x180004a1d  call    _FreeCacheFileEntries
0x180004a22  mov     rcx, [rbx+68h]
0x180004a26  xor     r8d, r8d
0x180004a29  xor     edx, edx
0x180004a2b  call    cs:__imp_I_CryptFreeLruCache
0x180004a31  mov     qword ptr [rbx+68h], 0
0x180004a39  mov     rcx, rbx; hMem
0x180004a3c  call    PkiFree
0x180004a41  mov     rbx, [rsp+28h+arg_0]
0x180004a46  add     rsp, 20h
0x180004a4a  pop     rdi
0x180004a4b  retn
0x180004a4c  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180004a50  call    cs:__imp_UnregisterWaitEx
0x180004a56  mov     qword ptr [rbx+40h], 0
0x180004a5e  jmp     loc_1800049BD
0x180004a63  mov     rcx, rax; hMem
0x180004a66  call    RemovePreFetchJobFromDir
0x180004a6b  jmp     short loc_1800049F3
0x180004a6d  call    RemoveToBeRunJob
0x180004a72  mov     rcx, [rbx+50h]; hMem
0x180004a76  call    FreeScanJob
0x180004a7b  mov     qword ptr [rbx+50h], 0
0x180004a83  jmp     loc_1800049E6
0x180004a88  test    edi, edi
0x180004a8a  jnz     short loc_180004A91
0x180004a8c  call    RemoveToBeRunJob
0x180004a91  mov     rcx, [rbx+58h]; hMem
0x180004a95  test    rcx, rcx
0x180004a98  jz      short loc_180004A9F
0x180004a9a  call    PkiFree
0x180004a9f  mov     qword ptr [rbx+58h], 0
0x180004aa7  jmp     loc_1800049F3
```
