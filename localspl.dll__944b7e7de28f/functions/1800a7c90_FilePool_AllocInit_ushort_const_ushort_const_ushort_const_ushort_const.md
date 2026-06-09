# FilePool::AllocInit(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800a7c90`
- end: `0x1800a7d8a`
- name: `?AllocInit@FilePool@@QEAAJPEBG000@Z`
- size: `250`
- prototype: `__int64 __fastcall(FilePool *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800a7e14`

## callees

- `0x180015e28`
- `0x1800a7c90`
- `0x1800a8118`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a7ca8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800a7ca8`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d3d`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d47`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d51`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d5e`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d3d`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d47`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d51`
- `SPOOLSS!DllFreeSplStr` at `0x1800a7d5e`
- `SPOOLSS!AllocSplStr` at `0x1800a7cc0`
- `SPOOLSS!AllocSplStr` at `0x1800a7cd9`
- `SPOOLSS!AllocSplStr` at `0x1800a7cef`
- `SPOOLSS!AllocSplStr` at `0x1800a7d05`
- `SPOOLSS!AllocSplStr` at `0x1800a7cc0`
- `SPOOLSS!AllocSplStr` at `0x1800a7cd9`
- `SPOOLSS!AllocSplStr` at `0x1800a7cef`
- `SPOOLSS!AllocSplStr` at `0x1800a7d05`

## pseudocode

```c
__int64 __fastcall FilePool::AllocInit(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int LastErrorAsFailHRNoBreak; // edi
  NCoreLibrary *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax

  LastErrorAsFailHRNoBreak = 0;
  if ( !InitializeCriticalSectionAndSpinCount(this, 0x80000000) )
  {
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v7);
    if ( LastErrorAsFailHRNoBreak )
      goto LABEL_10;
  }
  v8 = AllocSplStr(a2);
  this[4].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v8;
  if ( !v8 )
    goto LABEL_10;
  v9 = AllocSplStr(L"FP");
  this[2].LockSemaphore = (HANDLE)v9;
  if ( v9
    && (v10 = AllocSplStr(L".SPL"), (this[2].SpinCount = v10) != 0)
    && (v11 = AllocSplStr(L".SHD"), (*(_QWORD *)&this[3].LockCount = v11) != 0) )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(this[2].SpinCount + 2 * v12) );
    this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v12;
    FilePool::DeleteOrphanFiles((FilePool *)this);
  }
  else
  {
LABEL_10:
    DllFreeSplStr(this[4].DebugInfo);
    DllFreeSplStr(this[2].LockSemaphore);
    DllFreeSplStr(this[2].SpinCount);
    DllFreeSplStr(*(_QWORD *)&this[3].LockCount);
    this[4].DebugInfo = 0;
    LastErrorAsFailHRNoBreak = -2147467259;
    this[2].LockSemaphore = 0;
    this[2].SpinCount = 0;
    *(_QWORD *)&this[3].LockCount = 0;
  }
  return LastErrorAsFailHRNoBreak;
}

```

## disassembly

```asm
0x1800a7c90  push    rbx
0x1800a7c92  push    rbp
0x1800a7c93  push    rsi
0x1800a7c94  push    rdi
0x1800a7c95  sub     rsp, 28h
0x1800a7c99  mov     rsi, rdx
0x1800a7c9c  xor     ebp, ebp
0x1800a7c9e  mov     edx, 80000000h; dwSpinCount
0x1800a7ca3  mov     edi, ebp
0x1800a7ca5  mov     rbx, rcx
0x1800a7ca8  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800a7cae  test    eax, eax
0x1800a7cb0  jnz     short loc_1800A7CBD
0x1800a7cb2  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800a7cb7  mov     edi, eax
0x1800a7cb9  test    eax, eax
0x1800a7cbb  jnz     short loc_1800A7D36
0x1800a7cbd  mov     rcx, rsi
0x1800a7cc0  call    cs:__imp_AllocSplStr
0x1800a7cc6  mov     [rbx+0A0h], rax
0x1800a7ccd  test    rax, rax
0x1800a7cd0  jz      short loc_1800A7D36
0x1800a7cd2  lea     rcx, aFp; "FP"
0x1800a7cd9  call    cs:__imp_AllocSplStr
0x1800a7cdf  mov     [rbx+68h], rax
0x1800a7ce3  test    rax, rax
0x1800a7ce6  jz      short loc_1800A7D36
0x1800a7ce8  lea     rcx, aSpl; ".SPL"
0x1800a7cef  call    cs:__imp_AllocSplStr
0x1800a7cf5  mov     [rbx+70h], rax
0x1800a7cf9  test    rax, rax
0x1800a7cfc  jz      short loc_1800A7D36
0x1800a7cfe  lea     rcx, aShd_0; ".SHD"
0x1800a7d05  call    cs:__imp_AllocSplStr
0x1800a7d0b  mov     [rbx+80h], rax
0x1800a7d12  test    rax, rax
0x1800a7d15  jz      short loc_1800A7D36
0x1800a7d17  mov     rcx, [rbx+70h]
0x1800a7d1b  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a7d1f  inc     rax
0x1800a7d22  cmp     [rcx+rax*2], bp
0x1800a7d26  jnz     short loc_1800A7D1F
0x1800a7d28  mov     rcx, rbx; this
0x1800a7d2b  mov     [rbx+78h], rax
0x1800a7d2f  call    ?DeleteOrphanFiles@FilePool@@AEAAXXZ; FilePool::DeleteOrphanFiles(void)
0x1800a7d34  jmp     short loc_1800A7D7F
0x1800a7d36  mov     rcx, [rbx+0A0h]
0x1800a7d3d  call    cs:__imp_DllFreeSplStr
0x1800a7d43  mov     rcx, [rbx+68h]
0x1800a7d47  call    cs:__imp_DllFreeSplStr
0x1800a7d4d  mov     rcx, [rbx+70h]
0x1800a7d51  call    cs:__imp_DllFreeSplStr
0x1800a7d57  mov     rcx, [rbx+80h]
0x1800a7d5e  call    cs:__imp_DllFreeSplStr
0x1800a7d64  mov     [rbx+0A0h], rbp
0x1800a7d6b  mov     edi, 80004005h
0x1800a7d70  mov     [rbx+68h], rbp
0x1800a7d74  mov     [rbx+70h], rbp
0x1800a7d78  mov     [rbx+80h], rbp
0x1800a7d7f  mov     eax, edi
0x1800a7d81  add     rsp, 28h
0x1800a7d85  pop     rdi
0x1800a7d86  pop     rsi
0x1800a7d87  pop     rbp
0x1800a7d88  pop     rbx
0x1800a7d89  retn
```
