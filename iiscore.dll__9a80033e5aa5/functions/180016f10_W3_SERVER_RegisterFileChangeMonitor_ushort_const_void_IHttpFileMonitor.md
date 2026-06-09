# W3_SERVER::RegisterFileChangeMonitor(ushort const *,void *,IHttpFileMonitor * *)

- ea: `0x180016f10`
- end: `0x1800170a8`
- name: `?RegisterFileChangeMonitor@W3_SERVER@@UEAAJPEBGPEAXPEAPEAVIHttpFileMonitor@@@Z`
- size: `408`
- prototype: `int(W3_SERVER *__hidden this, const unsigned __int16 *, void *, struct IHttpFileMonitor **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016f10`
- `0x180019558`
- `0x18001a234`
- `0x1800332a8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017041`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017041`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016fe8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017081`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017081`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180016f95`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180016f95`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x180016f4e`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x180016f4e`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180016f68`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180016f68`

## pseudocode

```c
__int64 __fastcall W3_SERVER::RegisterFileChangeMonitor(
        W3_SERVER *this,
        const unsigned __int16 *a2,
        void *a3,
        struct IHttpFileMonitor **a4)
{
  CLKRHashTable *v8; // rdi
  CacheDirMonitorEntry *v9; // rbx
  signed int LastError; // eax
  unsigned int v12; // edi
  signed int v13; // eax
  CacheDirMonitorEntry *v14; // rax
  CacheDirMonitorEntry *v15; // rax
  int v16; // esi
  __int64 v17; // r9
  int v18; // ebp
  unsigned int v19; // [rsp+20h] [rbp-38h]
  CacheDirMonitorEntry *v20; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a4 )
    return 2147942487LL;
  v8 = (CLKRHashTable *)*((_QWORD *)this + 183);
  CLKRHashTable::ReadLock(v8);
  v20 = 0;
  CLKRHashTable::FindKey(v8, a2, &v20);
  v9 = v20;
  if ( v20 )
  {
    if ( *((_DWORD *)v20 + 26) )
      v9 = 0;
    else
      (*(void (__fastcall **)(CacheDirMonitorEntry *))(*(_QWORD *)v20 + 8LL))(v20);
  }
  CLKRHashTable::ReadUnlock(v8);
  if ( v9 )
    goto LABEL_7;
  v14 = (CacheDirMonitorEntry *)operator new(0xD0u);
  if ( v14 )
  {
    v15 = CacheDirMonitorEntry::CacheDirMonitorEntry(v14);
    v9 = v15;
    if ( v15 )
    {
      v16 = 0;
      (*(void (__fastcall **)(CacheDirMonitorEntry *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( a3 )
      {
        if ( !SetThreadToken(0, a3) )
        {
          LastError = GetLastError();
          v12 = LastError;
          if ( LastError > 0 )
            v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
          (*(void (__fastcall **)(CacheDirMonitorEntry *))(*(_QWORD *)v9 + 16LL))(v9);
          return v12;
        }
        v16 = 1;
      }
      v12 = 0;
      v18 = CDirMonitor::Monitor(*((CDirMonitor **)this + 183), v9, a2, v17, v19, *((_DWORD *)this + 368));
      if ( !v18 )
      {
        v13 = GetLastError();
        v12 = v13;
        if ( v13 > 0 )
          v12 = (unsigned __int16)v13 | 0x80070000;
      }
      if ( v16 )
        RevertToSelf();
      if ( v18 )
      {
LABEL_7:
        *a4 = (CacheDirMonitorEntry *)((char *)v9 + 112);
        return 0;
      }
      goto LABEL_10;
    }
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180016f10  mov     [rsp+arg_0], rbx
0x180016f15  mov     [rsp+arg_10], rbp
0x180016f1a  push    rsi
0x180016f1b  push    rdi
0x180016f1c  push    r13
0x180016f1e  push    r14
0x180016f20  push    r15
0x180016f22  sub     rsp, 30h
0x180016f26  mov     r14, r9
0x180016f29  mov     r15, r8
0x180016f2c  mov     rbp, rdx
0x180016f2f  mov     r13, rcx
0x180016f32  test    rdx, rdx
0x180016f35  jz      loc_18001709E
0x180016f3b  test    r9, r9
0x180016f3e  jz      loc_18001709E
0x180016f44  mov     rdi, [rcx+5B8h]
0x180016f4b  mov     rcx, rdi
0x180016f4e  call    cs:__imp_?ReadLock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadLock(void)
0x180016f54  lea     r8, [rsp+58h+arg_8]
0x180016f59  mov     [rsp+58h+arg_8], 0
0x180016f62  mov     rdx, rbp
0x180016f65  mov     rcx, rdi
0x180016f68  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180016f6e  mov     rbx, [rsp+58h+arg_8]
0x180016f73  test    rbx, rbx
0x180016f76  jz      short loc_180016F92
0x180016f78  mov     eax, [rbx+68h]
0x180016f7b  test    eax, eax
0x180016f7d  jnz     loc_180017003
0x180016f83  mov     rax, [rbx]
0x180016f86  mov     rcx, rbx
0x180016f89  mov     rax, [rax+8]
0x180016f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f92  mov     rcx, rdi
0x180016f95  call    cs:__imp_?ReadUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadUnlock(void)
0x180016f9b  test    rbx, rbx
0x180016f9e  jz      short loc_180017007
0x180016fa0  lea     rax, [rbx+70h]
0x180016fa4  mov     [r14], rax
0x180016fa7  xor     eax, eax
0x180016fa9  mov     rbx, [rsp+58h+arg_0]
0x180016fae  mov     rbp, [rsp+58h+arg_10]
0x180016fb3  add     rsp, 30h
0x180016fb7  pop     r15
0x180016fb9  pop     r14
0x180016fbb  pop     r13
0x180016fbd  pop     rdi
0x180016fbe  pop     rsi
0x180016fbf  retn
0x180016fc0  call    cs:__imp_GetLastError
0x180016fc6  mov     edi, eax
0x180016fc8  test    eax, eax
0x180016fca  jle     short loc_180016FD5
0x180016fcc  movzx   edi, ax
0x180016fcf  or      edi, 80070000h
0x180016fd5  mov     rcx, [rbx]
0x180016fd8  mov     rax, [rcx+10h]
0x180016fdc  mov     rcx, rbx
0x180016fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fe4  mov     eax, edi
0x180016fe6  jmp     short loc_180016FA9
0x180016fe8  call    cs:__imp_GetLastError
0x180016fee  mov     edi, eax
0x180016ff0  test    eax, eax
0x180016ff2  jle     loc_18001707D
0x180016ff8  movzx   edi, ax
0x180016ffb  or      edi, 80070000h
0x180017001  jmp     short loc_18001707D
0x180017003  xor     ebx, ebx
0x180017005  jmp     short loc_180016F92
0x180017007  mov     ecx, 0D0h; Size
0x18001700c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017011  test    rax, rax
0x180017014  jz      short loc_180017094
0x180017016  mov     rcx, rax; this
0x180017019  call    ??0CacheDirMonitorEntry@@QEAA@XZ; CacheDirMonitorEntry::CacheDirMonitorEntry(void)
0x18001701e  mov     rbx, rax
0x180017021  test    rax, rax
0x180017024  jz      short loc_180017094
0x180017026  mov     rcx, [rax]
0x180017029  xor     esi, esi
0x18001702b  mov     rax, [rcx+8]
0x18001702f  mov     rcx, rbx
0x180017032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017037  test    r15, r15
0x18001703a  jz      short loc_180017054
0x18001703c  mov     rdx, r15; Token
0x18001703f  xor     ecx, ecx; Thread
0x180017041  call    cs:__imp_SetThreadToken
0x180017047  test    eax, eax
0x180017049  jz      loc_180016FC0
0x18001704f  mov     esi, 1
0x180017054  mov     eax, [r13+5C0h]
0x18001705b  mov     r8, rbp; unsigned __int16 *
0x18001705e  mov     rcx, [r13+5B8h]; this
0x180017065  mov     rdx, rbx; struct CDirMonitorEntry *
0x180017068  mov     [rsp+58h+var_30], eax; unsigned int
0x18001706c  xor     edi, edi
0x18001706e  call    ?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z; CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)
0x180017073  mov     ebp, eax
0x180017075  test    eax, eax
0x180017077  jz      loc_180016FE8
0x18001707d  test    esi, esi
0x18001707f  jz      short loc_180017087
0x180017081  call    cs:__imp_RevertToSelf
0x180017087  test    ebp, ebp
0x180017089  jnz     loc_180016FA0
0x18001708f  jmp     loc_180016FD5
0x180017094  mov     eax, 80070008h
0x180017099  jmp     loc_180016FA9
0x18001709e  mov     eax, 80070057h
0x1800170a3  jmp     loc_180016FA9
```
