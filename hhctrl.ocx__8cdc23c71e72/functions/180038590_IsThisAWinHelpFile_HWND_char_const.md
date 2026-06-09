# IsThisAWinHelpFile(HWND__ *,char const *)

- ea: `0x180038590`
- end: `0x180038639`
- name: `?IsThisAWinHelpFile@@YAHPEAUHWND__@@PEBD@Z`
- size: `169`
- prototype: `__int64 __fastcall(HWND, const char *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180038028`
- `0x1800399ec`

## callees

- `0x180003fc0`
- `0x1800269d0`
- `0x180038590`
- `0x18004f65c`

## import_xrefs

- `KERNEL32!_lclose` at `0x1800385fd`
- `KERNEL32!_lclose` at `0x1800385fd`
- `KERNEL32!_lread` at `0x1800385f5`
- `KERNEL32!_lread` at `0x1800385f5`
- `KERNEL32!_lopen` at `0x1800385db`
- `KERNEL32!_lopen` at `0x1800385db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsThisAWinHelpFile(HWND a1, const char *a2)
{
  HFILE v4; // eax
  HFILE v5; // ebx
  char Buffer; // [rsp+40h] [rbp+18h] BYREF
  char v8; // [rsp+41h] [rbp+19h]
  LPCSTR lpPathName; // [rsp+48h] [rbp+20h] BYREF

  if ( HHStrStrIA(a2, ".hlp") )
  {
    lpPathName = 0;
    if ( (unsigned int)FindThisFile(a1, a2, (struct CStr *)&lpPathName, 0) )
    {
      v4 = _lopen(lpPathName, 0);
      v5 = v4;
      if ( v4 != -1 )
      {
        _lread(v4, &Buffer, 2u);
        _lclose(v5);
        if ( Buffer == 63 && v8 == 95 )
        {
          CWStr::~CWStr((CWStr *)&lpPathName);
          return 1;
        }
      }
    }
    CWStr::~CWStr((CWStr *)&lpPathName);
  }
  return 0;
}

```

## disassembly

```asm
0x180038590  mov     [rsp+arg_0], rbx
0x180038595  push    rdi
0x180038596  sub     rsp, 20h
0x18003859a  mov     rbx, rdx
0x18003859d  mov     rdi, rcx
0x1800385a0  lea     rdx, aHlp; ".hlp"
0x1800385a7  mov     rcx, rbx; pszStart
0x1800385aa  call    HHStrStrIA
0x1800385af  test    rax, rax
0x1800385b2  jz      short loc_18003862C
0x1800385b4  mov     [rsp+28h+lpPathName], 0
0x1800385bd  xor     r9d, r9d; int
0x1800385c0  lea     r8, [rsp+28h+lpPathName]; struct CStr *
0x1800385c5  mov     rdx, rbx; char *
0x1800385c8  mov     rcx, rdi; HWND
0x1800385cb  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x1800385d0  test    eax, eax
0x1800385d2  jz      short loc_180038622
0x1800385d4  xor     edx, edx; iReadWrite
0x1800385d6  mov     rcx, [rsp+28h+lpPathName]; lpPathName
0x1800385db  call    cs:__imp__lopen
0x1800385e1  mov     ebx, eax
0x1800385e3  cmp     eax, 0FFFFFFFFh
0x1800385e6  jz      short loc_180038622
0x1800385e8  mov     r8d, 2; uBytes
0x1800385ee  lea     rdx, [rsp+28h+Buffer]; lpBuffer
0x1800385f3  mov     ecx, eax; hFile
0x1800385f5  call    cs:__imp__lread
0x1800385fb  mov     ecx, ebx; hFile
0x1800385fd  call    cs:__imp__lclose
0x180038603  cmp     [rsp+28h+Buffer], 3Fh ; '?'
0x180038608  jnz     short loc_180038622
0x18003860a  cmp     [rsp+28h+arg_11], 5Fh ; '_'
0x18003860f  jnz     short loc_180038622
0x180038611  lea     rcx, [rsp+28h+lpPathName]; this
0x180038616  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18003861b  mov     eax, 1
0x180038620  jmp     short loc_18003862E
0x180038622  lea     rcx, [rsp+28h+lpPathName]; this
0x180038627  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18003862c  xor     eax, eax
0x18003862e  mov     rbx, [rsp+28h+arg_0]
0x180038633  add     rsp, 20h
0x180038637  pop     rdi
0x180038638  retn
```
