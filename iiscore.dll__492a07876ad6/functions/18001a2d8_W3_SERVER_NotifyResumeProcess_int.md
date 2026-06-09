# W3_SERVER::NotifyResumeProcess(int)

- ea: `0x18001a2d8`
- end: `0x18001a3fb`
- name: `?NotifyResumeProcess@W3_SERVER@@QEAAXH@Z`
- size: `291`
- prototype: `void __fastcall(W3_SERVER *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800202bc`

## callees

- `0x180015e40`
- `0x18001a2d8`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001a3a7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001a3a7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a2f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a34b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a2f6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a34b`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a325`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a325`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a3db`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18001a3db`

## pseudocode

```c
void __fastcall W3_SERVER::NotifyResumeProcess(W3_SERVER *this, int a2)
{
  VIRTUAL_MODULE **Ptr; // rax
  bool v5; // zf
  VIRTUAL_MODULE **v6; // r14
  __int64 v7; // rbx
  _DWORD *i; // rbx
  __int64 v9; // rcx
  FILETIME FileTime1; // [rsp+40h] [rbp+8h] BYREF

  Ptr = (VIRTUAL_MODULE **)BUFFER::QueryPtr((W3_SERVER *)((char *)this + 560));
  v5 = *((_DWORD *)this + 396) == 0;
  v6 = Ptr;
  FileTime1 = 0;
  if ( !v5 )
  {
    CReaderWriterLock3::WriteLock((W3_SERVER *)((char *)this + 1588));
    if ( *((_DWORD *)this + 396) )
    {
      v7 = *((unsigned int *)this + 295);
      for ( i = (char *)BUFFER::QueryPtr((W3_SERVER *)((char *)this + 1056)) + 4 * v7; *i != -1; ++i )
        VIRTUAL_MODULE::Resume(v6[*i]);
      if ( a2 )
      {
        v9 = *((_QWORD *)this + 187);
        if ( v9 )
        {
          if ( (*(int (__fastcall **)(__int64, FILETIME *))(*(_QWORD *)v9 + 176LL))(v9, &FileTime1) >= 0
            && CompareFileTime(&FileTime1, (const FILETIME *)((char *)this + 1612)) == 1 )
          {
            (*(void (__fastcall **)(W3_SERVER *, const wchar_t *))(*(_QWORD *)this + 112LL))(
              this,
              L"MACHINE/WEBROOT/APPHOST");
          }
        }
      }
      *((_DWORD *)this + 396) = 0;
    }
    CReaderWriterLock3::WriteUnlock((W3_SERVER *)((char *)this + 1588));
  }
}

```

## disassembly

```asm
0x18001a2d8  mov     [rsp+arg_8], rbx
0x18001a2dd  mov     [rsp+arg_10], rbp
0x18001a2e2  push    rsi
0x18001a2e3  push    rdi
0x18001a2e4  push    r14
0x18001a2e6  sub     rsp, 20h
0x18001a2ea  mov     rdi, rcx
0x18001a2ed  mov     ebp, edx
0x18001a2ef  add     rcx, 230h
0x18001a2f6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001a2fd  nop     dword ptr [rax+rax+00h]
0x18001a302  cmp     dword ptr [rdi+630h], 0
0x18001a309  mov     r14, rax
0x18001a30c  mov     qword ptr [rsp+38h+FileTime1.dwLowDateTime], 0
0x18001a315  jz      loc_18001A3E7
0x18001a31b  lea     rsi, [rdi+634h]
0x18001a322  mov     rcx, rsi
0x18001a325  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18001a32c  nop     dword ptr [rax+rax+00h]
0x18001a331  cmp     dword ptr [rdi+630h], 0
0x18001a338  jz      loc_18001A3D8
0x18001a33e  mov     ebx, [rdi+49Ch]
0x18001a344  lea     rcx, [rdi+420h]
0x18001a34b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001a352  nop     dword ptr [rax+rax+00h]
0x18001a357  lea     rbx, [rax+rbx*4]
0x18001a35b  jmp     short loc_18001A36C
0x18001a35d  mov     ecx, eax
0x18001a35f  mov     rcx, [r14+rcx*8]; this
0x18001a363  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x18001a368  lea     rbx, [rbx+4]
0x18001a36c  mov     eax, [rbx]
0x18001a36e  cmp     eax, 0FFFFFFFFh
0x18001a371  jnz     short loc_18001A35D
0x18001a373  test    ebp, ebp
0x18001a375  jz      short loc_18001A3CE
0x18001a377  mov     rcx, [rdi+5D8h]
0x18001a37e  test    rcx, rcx
0x18001a381  jz      short loc_18001A3CE
0x18001a383  mov     rax, [rcx]
0x18001a386  lea     rdx, [rsp+38h+FileTime1]
0x18001a38b  mov     rax, [rax+0B0h]
0x18001a392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a397  test    eax, eax
0x18001a399  js      short loc_18001A3CE
0x18001a39b  lea     rdx, [rdi+64Ch]; lpFileTime2
0x18001a3a2  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x18001a3a7  call    cs:__imp_CompareFileTime
0x18001a3ae  nop     dword ptr [rax+rax+00h]
0x18001a3b3  cmp     eax, 1
0x18001a3b6  jnz     short loc_18001A3CE
0x18001a3b8  mov     rax, [rdi]
0x18001a3bb  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001a3c2  mov     rcx, rdi
0x18001a3c5  mov     rax, [rax+70h]
0x18001a3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3ce  mov     dword ptr [rdi+630h], 0
0x18001a3d8  mov     rcx, rsi
0x18001a3db  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18001a3e2  nop     dword ptr [rax+rax+00h]
0x18001a3e7  mov     rbx, [rsp+38h+arg_8]
0x18001a3ec  mov     rbp, [rsp+38h+arg_10]
0x18001a3f1  add     rsp, 20h
0x18001a3f5  pop     r14
0x18001a3f7  pop     rdi
0x18001a3f8  pop     rsi
0x18001a3f9  retn
```
