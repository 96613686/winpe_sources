# W3_SERVER::NotifyResumeProcess(int)

- ea: `0x180018d8c`
- end: `0x180018e90`
- name: `?NotifyResumeProcess@W3_SERVER@@QEAAXH@Z`
- size: `260`
- prototype: `void __fastcall(W3_SERVER *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e7f0`

## callees

- `0x180014d00`
- `0x180018d8c`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018e49`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180018e49`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018daa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018df3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018daa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018df3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018dd3`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180018dd3`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018e77`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180018e77`

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
0x180018d8c  mov     [rsp+arg_8], rbx
0x180018d91  mov     [rsp+arg_10], rbp
0x180018d96  push    rsi
0x180018d97  push    rdi
0x180018d98  push    r14
0x180018d9a  sub     rsp, 20h
0x180018d9e  mov     rdi, rcx
0x180018da1  mov     ebp, edx
0x180018da3  add     rcx, 230h
0x180018daa  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018db0  cmp     dword ptr [rdi+630h], 0
0x180018db7  mov     r14, rax
0x180018dba  mov     qword ptr [rsp+38h+FileTime1.dwLowDateTime], 0
0x180018dc3  jz      loc_180018E7D
0x180018dc9  lea     rsi, [rdi+634h]
0x180018dd0  mov     rcx, rsi
0x180018dd3  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180018dd9  cmp     dword ptr [rdi+630h], 0
0x180018de0  jz      loc_180018E74
0x180018de6  mov     ebx, [rdi+49Ch]
0x180018dec  lea     rcx, [rdi+420h]
0x180018df3  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018df9  lea     rbx, [rax+rbx*4]
0x180018dfd  jmp     short loc_180018E0E
0x180018dff  mov     ecx, eax
0x180018e01  mov     rcx, [r14+rcx*8]; this
0x180018e05  call    ?Resume@VIRTUAL_MODULE@@QEAAXXZ; VIRTUAL_MODULE::Resume(void)
0x180018e0a  lea     rbx, [rbx+4]
0x180018e0e  mov     eax, [rbx]
0x180018e10  cmp     eax, 0FFFFFFFFh
0x180018e13  jnz     short loc_180018DFF
0x180018e15  test    ebp, ebp
0x180018e17  jz      short loc_180018E6A
0x180018e19  mov     rcx, [rdi+5D8h]
0x180018e20  test    rcx, rcx
0x180018e23  jz      short loc_180018E6A
0x180018e25  mov     rax, [rcx]
0x180018e28  lea     rdx, [rsp+38h+FileTime1]
0x180018e2d  mov     rax, [rax+0B0h]
0x180018e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e39  test    eax, eax
0x180018e3b  js      short loc_180018E6A
0x180018e3d  lea     rdx, [rdi+64Ch]; lpFileTime2
0x180018e44  lea     rcx, [rsp+38h+FileTime1]; lpFileTime1
0x180018e49  call    cs:__imp_CompareFileTime
0x180018e4f  cmp     eax, 1
0x180018e52  jnz     short loc_180018E6A
0x180018e54  mov     rax, [rdi]
0x180018e57  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180018e5e  mov     rcx, rdi
0x180018e61  mov     rax, [rax+70h]
0x180018e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e6a  mov     dword ptr [rdi+630h], 0
0x180018e74  mov     rcx, rsi
0x180018e77  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180018e7d  mov     rbx, [rsp+38h+arg_8]
0x180018e82  mov     rbp, [rsp+38h+arg_10]
0x180018e87  add     rsp, 20h
0x180018e8b  pop     r14
0x180018e8d  pop     rdi
0x180018e8e  pop     rsi
0x180018e8f  retn
```
