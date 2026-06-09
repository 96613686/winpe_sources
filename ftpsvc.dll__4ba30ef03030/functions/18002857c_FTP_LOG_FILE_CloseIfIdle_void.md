# FTP_LOG_FILE::CloseIfIdle(void)

- ea: `0x18002857c`
- end: `0x180028621`
- name: `?CloseIfIdle@FTP_LOG_FILE@@QEAAJXZ`
- size: `165`
- prototype: `__int64 __fastcall(FTP_LOG_FILE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180026960`

## callees

- `0x18002857c`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18002859f`
- `KERNEL32!GetTickCount64` at `0x1800285d0`
- `KERNEL32!GetTickCount64` at `0x18002859f`
- `KERNEL32!GetTickCount64` at `0x1800285d0`
- `KERNEL32!GetLastError` at `0x1800285ef`
- `KERNEL32!GetLastError` at `0x1800285ef`
- `KERNEL32!CloseHandle` at `0x1800285e5`
- `KERNEL32!CloseHandle` at `0x1800285e5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800285b5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800285b5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028610`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028610`

## pseudocode

```c
__int64 __fastcall FTP_LOG_FILE::CloseIfIdle(FTP_LOG_FILE *this)
{
  unsigned int v1; // esi
  __int64 v3; // rbx
  signed int LastError; // eax

  v1 = 0;
  if ( *((_QWORD *)this + 2) != -1
    && !*((_DWORD *)this + 12)
    && !*((_DWORD *)this + 30)
    && GetTickCount64() - *((_QWORD *)this + 5) >= 0x493E0 )
  {
    CReaderWriterLock3::WriteLock((FTP_LOG_FILE *)((char *)this + 124));
    if ( *((_QWORD *)this + 2) != -1 && !*((_DWORD *)this + 12) && !*((_DWORD *)this + 30) )
    {
      v3 = *((_QWORD *)this + 5);
      if ( GetTickCount64() - v3 >= 0x493E0 )
      {
        if ( !CloseHandle(*((HANDLE *)this + 2)) )
        {
          LastError = GetLastError();
          v1 = LastError;
          if ( LastError > 0 )
            v1 = (unsigned __int16)LastError | 0x80070000;
        }
        *((_QWORD *)this + 2) = -1;
      }
    }
    CReaderWriterLock3::WriteUnlock((FTP_LOG_FILE *)((char *)this + 124));
  }
  return v1;
}

```

## disassembly

```asm
0x18002857c  push    rbx
0x18002857e  push    rbp
0x18002857f  push    rsi
0x180028580  push    rdi
0x180028581  sub     rsp, 28h
0x180028585  xor     esi, esi
0x180028587  mov     rdi, rcx
0x18002858a  cmp     qword ptr [rcx+10h], 0FFFFFFFFFFFFFFFFh
0x18002858f  jz      loc_180028616
0x180028595  cmp     [rcx+30h], esi
0x180028598  jnz     short loc_180028616
0x18002859a  cmp     [rcx+78h], esi
0x18002859d  jnz     short loc_180028616
0x18002859f  call    cs:__imp_GetTickCount64
0x1800285a5  sub     rax, [rdi+28h]
0x1800285a9  cmp     rax, 493E0h
0x1800285af  jb      short loc_180028616
0x1800285b1  lea     rcx, [rdi+7Ch]
0x1800285b5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800285bb  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1800285c0  jz      short loc_18002860C
0x1800285c2  cmp     [rdi+30h], esi
0x1800285c5  jnz     short loc_18002860C
0x1800285c7  cmp     [rdi+78h], esi
0x1800285ca  jnz     short loc_18002860C
0x1800285cc  mov     rbx, [rdi+28h]
0x1800285d0  call    cs:__imp_GetTickCount64
0x1800285d6  sub     rax, rbx
0x1800285d9  cmp     rax, 493E0h
0x1800285df  jb      short loc_18002860C
0x1800285e1  mov     rcx, [rdi+10h]; hObject
0x1800285e5  call    cs:__imp_CloseHandle
0x1800285eb  test    eax, eax
0x1800285ed  jnz     short loc_180028604
0x1800285ef  call    cs:__imp_GetLastError
0x1800285f5  mov     esi, eax
0x1800285f7  test    eax, eax
0x1800285f9  jle     short loc_180028604
0x1800285fb  movzx   esi, ax
0x1800285fe  or      esi, 80070000h
0x180028604  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18002860c  lea     rcx, [rdi+7Ch]
0x180028610  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180028616  mov     eax, esi
0x180028618  add     rsp, 28h
0x18002861c  pop     rdi
0x18002861d  pop     rsi
0x18002861e  pop     rbp
0x18002861f  pop     rbx
0x180028620  retn
```
