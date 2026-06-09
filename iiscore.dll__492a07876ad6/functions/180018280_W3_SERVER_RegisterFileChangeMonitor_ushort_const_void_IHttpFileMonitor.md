# W3_SERVER::RegisterFileChangeMonitor(ushort const *,void *,IHttpFileMonitor * *)

- ea: `0x180018280`
- end: `0x18001844d`
- name: `?RegisterFileChangeMonitor@W3_SERVER@@UEAAJPEBGPEAXPEAPEAVIHttpFileMonitor@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(W3_SERVER *this, const unsigned __int16 *, void *, struct IHttpFileMonitor **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180018280`
- `0x18001ab30`
- `0x18001b830`
- `0x18003649c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800183da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800183da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018371`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018420`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180018420`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018311`
- `iisutil!?ReadUnlock@CLKRHashTable@@QEBAXXZ` at `0x180018311`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x1800182be`
- `iisutil!?ReadLock@CLKRHashTable@@QEBAXXZ` at `0x1800182be`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800182de`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x1800182de`

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
0x180018280  mov     [rsp+arg_0], rbx
0x180018285  mov     [rsp+arg_10], rbp
0x18001828a  push    rsi
0x18001828b  push    rdi
0x18001828c  push    r13
0x18001828e  push    r14
0x180018290  push    r15
0x180018292  sub     rsp, 30h
0x180018296  mov     r14, r9
0x180018299  mov     r15, r8
0x18001829c  mov     rbp, rdx
0x18001829f  mov     r13, rcx
0x1800182a2  test    rdx, rdx
0x1800182a5  jz      loc_180018443
0x1800182ab  test    r9, r9
0x1800182ae  jz      loc_180018443
0x1800182b4  mov     rdi, [rcx+5B8h]
0x1800182bb  mov     rcx, rdi
0x1800182be  call    cs:__imp_?ReadLock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadLock(void)
0x1800182c5  nop     dword ptr [rax+rax+00h]
0x1800182ca  lea     r8, [rsp+58h+arg_8]
0x1800182cf  mov     [rsp+58h+arg_8], 0
0x1800182d8  mov     rdx, rbp
0x1800182db  mov     rcx, rdi
0x1800182de  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800182e5  nop     dword ptr [rax+rax+00h]
0x1800182ea  mov     rbx, [rsp+58h+arg_8]
0x1800182ef  test    rbx, rbx
0x1800182f2  jz      short loc_18001830E
0x1800182f4  mov     eax, [rbx+68h]
0x1800182f7  test    eax, eax
0x1800182f9  jnz     loc_180018395
0x1800182ff  mov     rax, [rbx]
0x180018302  mov     rcx, rbx
0x180018305  mov     rax, [rax+8]
0x180018309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001830e  mov     rcx, rdi
0x180018311  call    cs:__imp_?ReadUnlock@CLKRHashTable@@QEBAXXZ; CLKRHashTable::ReadUnlock(void)
0x180018318  nop     dword ptr [rax+rax+00h]
0x18001831d  test    rbx, rbx
0x180018320  jz      short loc_18001839C
0x180018322  lea     rax, [rbx+70h]
0x180018326  mov     [r14], rax
0x180018329  xor     eax, eax
0x18001832b  mov     rbx, [rsp+58h+arg_0]
0x180018330  mov     rbp, [rsp+58h+arg_10]
0x180018335  add     rsp, 30h
0x180018339  pop     r15
0x18001833b  pop     r14
0x18001833d  pop     r13
0x18001833f  pop     rdi
0x180018340  pop     rsi
0x180018341  retn
0x180018343  call    cs:__imp_GetLastError
0x18001834a  nop     dword ptr [rax+rax+00h]
0x18001834f  mov     edi, eax
0x180018351  test    eax, eax
0x180018353  jle     short loc_18001835E
0x180018355  movzx   edi, ax
0x180018358  or      edi, 80070000h
0x18001835e  mov     rcx, [rbx]
0x180018361  mov     rax, [rcx+10h]
0x180018365  mov     rcx, rbx
0x180018368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001836d  mov     eax, edi
0x18001836f  jmp     short loc_18001832B
0x180018371  call    cs:__imp_GetLastError
0x180018378  nop     dword ptr [rax+rax+00h]
0x18001837d  mov     edi, eax
0x18001837f  test    eax, eax
0x180018381  jle     loc_18001841C
0x180018387  movzx   edi, ax
0x18001838a  or      edi, 80070000h
0x180018390  jmp     loc_18001841C
0x180018395  xor     ebx, ebx
0x180018397  jmp     loc_18001830E
0x18001839c  mov     ecx, 0D0h; Size
0x1800183a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800183a6  test    rax, rax
0x1800183a9  jz      loc_180018439
0x1800183af  mov     rcx, rax; this
0x1800183b2  call    ??0CacheDirMonitorEntry@@QEAA@XZ; CacheDirMonitorEntry::CacheDirMonitorEntry(void)
0x1800183b7  mov     rbx, rax
0x1800183ba  test    rax, rax
0x1800183bd  jz      short loc_180018439
0x1800183bf  mov     rcx, [rax]
0x1800183c2  xor     esi, esi
0x1800183c4  mov     rax, [rcx+8]
0x1800183c8  mov     rcx, rbx
0x1800183cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d0  test    r15, r15
0x1800183d3  jz      short loc_1800183F3
0x1800183d5  mov     rdx, r15; Token
0x1800183d8  xor     ecx, ecx; Thread
0x1800183da  call    cs:__imp_SetThreadToken
0x1800183e1  nop     dword ptr [rax+rax+00h]
0x1800183e6  test    eax, eax
0x1800183e8  jz      loc_180018343
0x1800183ee  mov     esi, 1
0x1800183f3  mov     eax, [r13+5C0h]
0x1800183fa  mov     r8, rbp; unsigned __int16 *
0x1800183fd  mov     rcx, [r13+5B8h]; this
0x180018404  mov     rdx, rbx; struct CDirMonitorEntry *
0x180018407  mov     [rsp+58h+var_30], eax; unsigned int
0x18001840b  xor     edi, edi
0x18001840d  call    ?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z; CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)
0x180018412  mov     ebp, eax
0x180018414  test    eax, eax
0x180018416  jz      loc_180018371
0x18001841c  test    esi, esi
0x18001841e  jz      short loc_18001842C
0x180018420  call    cs:__imp_RevertToSelf
0x180018427  nop     dword ptr [rax+rax+00h]
0x18001842c  test    ebp, ebp
0x18001842e  jnz     loc_180018322
0x180018434  jmp     loc_18001835E
0x180018439  mov     eax, 80070008h
0x18001843e  jmp     loc_18001832B
0x180018443  mov     eax, 80070057h
0x180018448  jmp     loc_18001832B
```
