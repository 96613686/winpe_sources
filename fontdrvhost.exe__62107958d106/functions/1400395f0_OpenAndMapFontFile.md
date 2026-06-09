# OpenAndMapFontFile

- ea: `0x1400395f0`
- end: `0x140039683`
- name: `OpenAndMapFontFile`
- size: `147`
- prototype: `__int64 __fastcall(ULONG_PTR iFile, ULONG *pcjBuf)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140033950`
- `0x140037640`

## callees

- `0x14003425c`
- `0x1400395f0`
- `0x140048348`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140039616`
- `KERNEL32!LeaveCriticalSection` at `0x140039616`
- `KERNEL32!EnterCriticalSection` at `0x140039653`
- `KERNEL32!EnterCriticalSection` at `0x140096b8f`
- `KERNEL32!EnterCriticalSection` at `0x140039653`
- `KERNEL32!EnterCriticalSection` at `0x140096b8f`

## pseudocode

```c
PULONG __fastcall OpenAndMapFontFile(ULONG_PTR iFile, ULONG *pcjBuf, __int64 a3, ULONG a4)
{
  PULONG ppjBuf; // [rsp+20h] [rbp-38h] BYREF

  ppjBuf = 0;
  LeaveCriticalSection(hSem);
  if ( iFile )
  {
    if ( EngMapFontFileFD(iFile, &ppjBuf, pcjBuf) )
    {
      GetFileChangeTime(iFile, pcjBuf + 1);
      if ( *pcjBuf != a4 )
        a4 = *pcjBuf;
    }
    else
    {
      a4 = 0;
    }
  }
  EnterCriticalSection(hSem);
  BcException = 271;
  qword_1400B68B0 = 0;
  dword_1400B6264 += a4;
  return ppjBuf;
}

```

## disassembly

```asm
0x1400395f0  push    rbx
0x1400395f2  push    rsi
0x1400395f3  push    rdi
0x1400395f4  push    r14
0x1400395f6  sub     rsp, 38h
0x1400395fa  mov     ebx, r9d
0x1400395fd  mov     r14b, r8b
0x140039600  mov     rsi, rdx
0x140039603  mov     rdi, rcx
0x140039606  mov     [rsp+58h+ppjBuf], 0
0x14003960f  mov     rcx, cs:hSem; lpCriticalSection
0x140039616  call    cs:__imp_LeaveCriticalSection
0x14003961c  test    rdi, rdi
0x14003961f  jz      short loc_14003964C
0x140039621  mov     r8, rsi; pcjBuf
0x140039624  lea     rdx, [rsp+58h+ppjBuf]; ppjBuf
0x140039629  mov     rcx, rdi; iFile
0x14003962c  call    EngMapFontFileFD
0x140039631  test    eax, eax
0x140039633  jz      short loc_14003964A
0x140039635  lea     rdx, [rsi+4]
0x140039639  mov     rcx, rdi
0x14003963c  call    GetFileChangeTime
0x140039641  mov     eax, [rsi]
0x140039643  sub     eax, ebx
0x140039645  cmovnz  ebx, [rsi]
0x140039648  jmp     short loc_14003964C
0x14003964a  xor     ebx, ebx
0x14003964c  mov     rcx, cs:hSem; lpCriticalSection
0x140039653  call    cs:__imp_EnterCriticalSection
0x140039659  mov     cs:BcException, 10Fh
0x140039663  mov     cs:qword_1400B68B0, 0
0x14003966e  add     cs:dword_1400B6264, ebx
0x140039674  mov     rax, [rsp+58h+ppjBuf]
0x140039679  add     rsp, 38h
0x14003967d  pop     r14
0x14003967f  pop     rdi
0x140039680  pop     rsi
0x140039681  pop     rbx
0x140039682  retn
0x140096b7f  push    rbp
0x140096b81  sub     rsp, 20h
0x140096b85  mov     rbp, rdx
0x140096b88  mov     rcx, cs:hSem; lpCriticalSection
0x140096b8f  call    cs:__imp_EnterCriticalSection
0x140096b95  mov     cs:BcException, 10Fh
0x140096b9f  mov     cs:qword_1400B68B0, 0
0x140096baa  add     rsp, 20h
0x140096bae  pop     rbp
0x140096baf  retn
```
