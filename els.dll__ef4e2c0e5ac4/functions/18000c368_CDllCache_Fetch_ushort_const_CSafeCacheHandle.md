# CDllCache::Fetch(ushort const *,CSafeCacheHandle *)

- ea: `0x18000c368`
- end: `0x18000c43a`
- name: `?Fetch@CDllCache@@QEAAJPEBGPEAVCSafeCacheHandle@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(CDllCache *this, unsigned __int16 *, struct CSafeCacheHandle *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000ca0c`
- `0x18000e824`
- `0x18000f09c`

## callees

- `0x18000c368`
- `0x18000c4a8`
- `0x18000c4f0`
- `0x180017e00`
- `0x18002134c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000c390`
- `KERNEL32!EnterCriticalSection` at `0x18000c390`
- `KERNEL32!LeaveCriticalSection` at `0x18000c422`
- `KERNEL32!LeaveCriticalSection` at `0x18000c422`
- `KERNEL32!GetLastError` at `0x18000c40a`
- `KERNEL32!GetLastError` at `0x18000c40a`
- `KERNEL32!FreeLibrary` at `0x18000c402`
- `KERNEL32!FreeLibrary` at `0x18000c402`

## pseudocode

```c
__int64 __fastcall CDllCache::Fetch(CDllCache *this, unsigned __int16 *a2, struct CSafeCacheHandle *a3)
{
  unsigned int v5; // ebx
  CDllCache *v6; // rcx
  signed int LastError; // eax
  HMODULE hLibModule; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+48h] [rbp+20h]

  hLibModule = (HMODULE)this;
  v10 = &stru_18002F138;
  EnterCriticalSection(&stru_18002F138);
  hLibModule = 0;
  if ( (unsigned int)CLruCache::Fetch((CLruCache *)&g_DllCache, a2, &hLibModule, 8u) )
  {
    hLibModule = (HMODULE)UtilLoadLibraryExWrapper(a2);
    if ( hLibModule )
    {
      v5 = CSafeCacheHandle::Set(a3, a2);
      if ( CDllCache::_Add(v6, a2, hLibModule) < 0 )
        FreeLibrary(hLibModule);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v5 = CSafeCacheHandle::Set(a3, a2);
  }
  LeaveCriticalSection(&stru_18002F138);
  return v5;
}

```

## disassembly

```asm
0x18000c368  mov     rax, rsp
0x18000c36b  mov     [rax+10h], rbx
0x18000c36f  mov     [rax+18h], rsi
0x18000c373  mov     [rax+8], rcx
0x18000c377  push    rdi
0x18000c378  sub     rsp, 20h
0x18000c37c  mov     rbx, r8
0x18000c37f  mov     rdi, rdx
0x18000c382  lea     rsi, stru_18002F138
0x18000c389  mov     [rax+20h], rsi
0x18000c38d  mov     rcx, rsi; lpCriticalSection
0x18000c390  call    cs:__imp_EnterCriticalSection
0x18000c396  nop
0x18000c397  mov     [rsp+28h+hLibModule], 0
0x18000c3a0  mov     r9d, 8; unsigned int
0x18000c3a6  lea     r8, [rsp+28h+hLibModule]; void *
0x18000c3ab  mov     rdx, rdi; void *
0x18000c3ae  lea     rcx, ?g_DllCache@@3VCDllCache@@A; this
0x18000c3b5  call    ?Fetch@CLruCache@@UEAAJPEAX0K@Z; CLruCache::Fetch(void *,void *,ulong)
0x18000c3ba  test    eax, eax
0x18000c3bc  jnz     short loc_18000C3CD
0x18000c3be  mov     rdx, rdi; unsigned __int16 *
0x18000c3c1  mov     rcx, rbx; this
0x18000c3c4  call    ?Set@CSafeCacheHandle@@QEAAJPEBG@Z; CSafeCacheHandle::Set(ushort const *)
0x18000c3c9  mov     ebx, eax
0x18000c3cb  jmp     short loc_18000C41F
0x18000c3cd  mov     rcx, rdi; unsigned __int16 *
0x18000c3d0  call    UtilLoadLibraryExWrapper
0x18000c3d5  mov     [rsp+28h+hLibModule], rax
0x18000c3da  test    rax, rax
0x18000c3dd  jz      short loc_18000C40A
0x18000c3df  mov     rdx, rdi; unsigned __int16 *
0x18000c3e2  mov     rcx, rbx; this
0x18000c3e5  call    ?Set@CSafeCacheHandle@@QEAAJPEBG@Z; CSafeCacheHandle::Set(ushort const *)
0x18000c3ea  mov     ebx, eax
0x18000c3ec  mov     r8, [rsp+28h+hLibModule]; HINSTANCE
0x18000c3f1  mov     rdx, rdi; unsigned __int16 *
0x18000c3f4  call    ?_Add@CDllCache@@AEAAJPEBGPEAUHINSTANCE__@@@Z; CDllCache::_Add(ushort const *,HINSTANCE__ *)
0x18000c3f9  test    eax, eax
0x18000c3fb  jns     short loc_18000C41F
0x18000c3fd  mov     rcx, [rsp+28h+hLibModule]; hLibModule
0x18000c402  call    cs:__imp_FreeLibrary
0x18000c408  jmp     short loc_18000C41F
0x18000c40a  call    cs:__imp_GetLastError
0x18000c410  mov     ebx, eax
0x18000c412  test    eax, eax
0x18000c414  jle     short loc_18000C41F
0x18000c416  movzx   ebx, ax
0x18000c419  or      ebx, 80070000h
0x18000c41f  mov     rcx, rsi; lpCriticalSection
0x18000c422  call    cs:__imp_LeaveCriticalSection
0x18000c428  mov     eax, ebx
0x18000c42a  mov     rbx, [rsp+28h+arg_8]
0x18000c42f  mov     rsi, [rsp+28h+arg_10]
0x18000c434  add     rsp, 20h
0x18000c438  pop     rdi
0x18000c439  retn
```
