# CircularLog::Log(ushort const *)

- ea: `0x140010938`
- end: `0x140010b85`
- name: `?Log@CircularLog@@QEAAXPEBG@Z`
- size: `589`
- prototype: `void __fastcall(CircularLog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400068ec`

## callees

- `0x14000a05c`
- `0x14000a10c`
- `0x14000ad80`
- `0x14000bad0`
- `0x140010938`
- `0x140010c68`
- `0x140010e48`
- `0x140013200`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x1400109a2`
- `KERNEL32!GetFileSizeEx` at `0x1400109a2`
- `KERNEL32!CloseHandle` at `0x1400109b9`
- `KERNEL32!CloseHandle` at `0x140010af8`
- `KERNEL32!CloseHandle` at `0x1400109b9`
- `KERNEL32!CloseHandle` at `0x140010af8`
- `KERNEL32!WriteFile` at `0x140010aef`
- `KERNEL32!WriteFile` at `0x140010aef`
- `KERNEL32!HeapFree` at `0x140010b30`
- `KERNEL32!HeapFree` at `0x140010b30`
- `KERNEL32!GetProcessHeap` at `0x140010b1b`
- `KERNEL32!GetProcessHeap` at `0x140010b1b`

## pseudocode

```c
void __fastcall CircularLog::Log(CircularLog *this, const unsigned __int16 *a2)
{
  void *v4; // rax
  void *v5; // rsi
  void *v6; // r8
  int *v7; // r9
  __int64 v8; // rcx
  __int16 *v9; // rax
  unsigned __int16 *v10; // r14
  BOOL v11; // r15d
  __int16 v12; // dx
  __int16 i; // cx
  const char *UTF8; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v18[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h]
  void *v20; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  LARGE_INTEGER FileSize; // [rsp+58h] [rbp-A8h] BYREF
  __int16 *v23; // [rsp+60h] [rbp-A0h]
  BOOL v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+74h] [rbp-8Ch]
  LPVOID lpMem; // [rsp+80h] [rbp-80h]
  __int16 v28; // [rsp+88h] [rbp-78h] BYREF

  if ( *(_BYTE *)this )
  {
    v4 = CircularLog::OpenFile(this);
    v5 = v4;
    if ( v4 != (void *)-1LL )
    {
      if ( (*((_BYTE *)this + 108) & 0xF) != 0
        || !GetFileSizeEx(v4, &FileSize)
        || FileSize.QuadPart <= *((unsigned int *)this + 26)
        || (CloseHandle(v5),
            CircularLog::CheckForLogReset(this, 1, v6, v7),
            v5 = CircularLog::OpenFile(this),
            v5 != (void *)-1LL) )
      {
        ++*((_DWORD *)this + 27);
        v8 = -1;
        do
          ++v8;
        while ( a2[v8] );
        v9 = (__int16 *)operator new(saturated_mul(2 * v8 + 1, 2u));
        v10 = (unsigned __int16 *)v9;
        v23 = v9;
        v11 = v9 != 0;
        v24 = v11;
        v12 = 0;
        for ( i = *a2; *a2; i = *a2 )
        {
          if ( i == 10 )
          {
            i = 10;
            if ( v12 != 13 )
            {
              *v9++ = 13;
              i = *a2;
            }
          }
          *v9++ = i;
          v12 = *a2++;
        }
        *v9 = 0;
        v18[0] = 2;
        v18[1] = 2;
        v19 = 16;
        v20 = (void *)&SString::s_EmptyBuffer;
        SString::Set((SString *)v18, v10);
        v26 = 256;
        lpMem = &v28;
        v25 = 2;
        v28 = 0;
        v17 = 0;
        UTF8 = SString::GetUTF8((SString *)v18, (struct SString::AbstractScratchBuffer *)&v25, &v17);
        WriteFile(v5, UTF8, v17 - 1, &NumberOfBytesWritten, 0);
        CloseHandle(v5);
        if ( (v26 & 0x800000000LL) != 0 )
        {
          v15 = lpMem;
          if ( lpMem )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v15);
          }
        }
        if ( (v19 & 8) != 0 )
          operator delete(v20);
        if ( v11 )
          operator delete(v10);
      }
    }
  }
}

```

## disassembly

```asm
0x140010938  mov     [rsp-8+arg_10], rbx
0x14001093d  push    rbp
0x14001093e  push    rsi
0x14001093f  push    rdi
0x140010940  push    r12
0x140010942  push    r13
0x140010944  push    r14
0x140010946  push    r15
0x140010948  lea     rbp, [rsp-0A0h]
0x140010950  sub     rsp, 1A0h
0x140010957  mov     rax, cs:__security_cookie
0x14001095e  xor     rax, rsp
0x140010961  mov     [rbp+0D0h+var_40], rax
0x140010968  mov     rdi, rdx
0x14001096b  mov     rbx, rcx
0x14001096e  xor     r12d, r12d
0x140010971  cmp     [rcx], r12b
0x140010974  jz      loc_140010B5B
0x14001097a  call    ?OpenFile@CircularLog@@IEAAPEAXXZ; CircularLog::OpenFile(void)
0x14001097f  mov     rsi, rax
0x140010982  or      r14, 0FFFFFFFFFFFFFFFFh
0x140010986  cmp     rax, r14
0x140010989  jz      loc_140010B5B
0x14001098f  lea     r13d, [r12+1]
0x140010994  test    byte ptr [rbx+6Ch], 0Fh
0x140010998  jnz     short loc_1400109DE
0x14001099a  lea     rdx, [rsp+1D0h+FileSize]; lpFileSize
0x14001099f  mov     rcx, rax; hFile
0x1400109a2  call    cs:__imp_GetFileSizeEx
0x1400109a8  test    eax, eax
0x1400109aa  jz      short loc_1400109DE
0x1400109ac  mov     eax, [rbx+68h]
0x1400109af  cmp     qword ptr [rsp+1D0h+FileSize], rax
0x1400109b4  jle     short loc_1400109DE
0x1400109b6  mov     rcx, rsi; hObject
0x1400109b9  call    cs:__imp_CloseHandle
0x1400109bf  mov     edx, r13d; int
0x1400109c2  mov     rcx, rbx; this
0x1400109c5  call    ?CheckForLogReset@CircularLog@@IEAAXH@Z; CircularLog::CheckForLogReset(int)
0x1400109ca  mov     rcx, rbx; this
0x1400109cd  call    ?OpenFile@CircularLog@@IEAAPEAXXZ; CircularLog::OpenFile(void)
0x1400109d2  mov     rsi, rax
0x1400109d5  cmp     rax, r14
0x1400109d8  jz      loc_140010B5B
0x1400109de  add     [rbx+6Ch], r13d
0x1400109e2  mov     rcx, r14
0x1400109e5  inc     rcx
0x1400109e8  cmp     [rdi+rcx*2], r12w
0x1400109ed  jnz     short loc_1400109E5
0x1400109ef  lea     rcx, ds:1[rcx*2]
0x1400109f7  mov     ebx, 2
0x1400109fc  mov     eax, ebx
0x1400109fe  mul     rcx
0x140010a01  cmovo   rax, r14
0x140010a05  mov     rcx, rax; dwBytes
0x140010a08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010a0d  mov     r14, rax
0x140010a10  mov     [rsp+1D0h+var_170], rax
0x140010a15  mov     [rsp+1D0h+var_168], r12d
0x140010a1a  mov     r15d, r12d
0x140010a1d  test    rax, rax
0x140010a20  cmovnz  r15d, r13d
0x140010a24  mov     [rsp+1D0h+var_168], r15d
0x140010a29  movzx   edx, r12w
0x140010a2d  movzx   ecx, word ptr [rdi]
0x140010a30  test    cx, cx
0x140010a33  jz      short loc_140010A6A
0x140010a35  lea     r9d, [rbx+8]
0x140010a39  lea     r8d, [rbx+0Bh]
0x140010a3d  cmp     cx, r9w
0x140010a41  jnz     short loc_140010A56
0x140010a43  mov     ecx, r9d
0x140010a46  cmp     dx, r8w
0x140010a4a  jz      short loc_140010A56
0x140010a4c  mov     [rax], r8w
0x140010a50  add     rax, rbx
0x140010a53  movzx   ecx, word ptr [rdi]
0x140010a56  mov     [rax], cx
0x140010a59  add     rax, rbx
0x140010a5c  movzx   edx, word ptr [rdi]
0x140010a5f  add     rdi, rbx
0x140010a62  movzx   ecx, word ptr [rdi]
0x140010a65  test    cx, cx
0x140010a68  jnz     short loc_140010A3D
0x140010a6a  mov     [rax], r12w
0x140010a6e  mov     [rsp+1D0h+var_198], ebx
0x140010a72  mov     [rsp+1D0h+var_194], ebx
0x140010a76  mov     [rsp+1D0h+var_190], 10h
0x140010a7e  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x140010a85  mov     [rsp+1D0h+var_188], rax
0x140010a8a  mov     rdx, r14; unsigned __int16 *
0x140010a8d  lea     rcx, [rsp+1D0h+var_198]; this
0x140010a92  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x140010a97  nop
0x140010a98  mov     [rsp+1D0h+var_160], r12
0x140010a9d  mov     [rsp+1D0h+var_160+4], 100h
0x140010aa6  mov     [rbp+0D0h+lpMem], r12
0x140010aaa  lea     rax, [rbp+0D0h+var_148]
0x140010aae  mov     [rbp+0D0h+lpMem], rax
0x140010ab2  mov     dword ptr [rsp+1D0h+var_160], ebx
0x140010ab6  mov     rax, [rbp+0D0h+lpMem]
0x140010aba  mov     [rax], r12w
0x140010abe  mov     [rsp+1D0h+var_1A0], r12d
0x140010ac3  lea     r8, [rsp+1D0h+var_1A0]; unsigned int *
0x140010ac8  lea     rdx, [rsp+1D0h+var_160]; struct SString::AbstractScratchBuffer *
0x140010acd  lea     rcx, [rsp+1D0h+var_198]; this
0x140010ad2  call    ?GetUTF8@SString@@QEBAPEBDAEAVAbstractScratchBuffer@1@PEAI@Z; SString::GetUTF8(SString::AbstractScratchBuffer &,uint *)
0x140010ad7  mov     r8d, [rsp+1D0h+var_1A0]
0x140010adc  dec     r8d; nNumberOfBytesToWrite
0x140010adf  mov     [rsp+1D0h+lpOverlapped], r12; lpOverlapped
0x140010ae4  lea     r9, [rsp+1D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140010ae9  mov     rdx, rax; lpBuffer
0x140010aec  mov     rcx, rsi; hFile
0x140010aef  call    cs:__imp_WriteFile
0x140010af5  mov     rcx, rsi; hObject
0x140010af8  call    cs:__imp_CloseHandle
0x140010afe  nop
0x140010aff  test    [rsp+1D0h+var_158], 8
0x140010b04  jz      short loc_140010B37
0x140010b06  mov     rbx, [rbp+0D0h+lpMem]
0x140010b0a  test    rbx, rbx
0x140010b0d  jz      short loc_140010B37
0x140010b0f  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140010b16  test    rax, rax
0x140010b19  jnz     short loc_140010B28
0x140010b1b  call    cs:__imp_GetProcessHeap
0x140010b21  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140010b28  mov     r8, rbx; lpMem
0x140010b2b  xor     edx, edx; dwFlags
0x140010b2d  mov     rcx, rax; hHeap
0x140010b30  call    cs:__imp_HeapFree
0x140010b36  nop
0x140010b37  test    byte ptr [rsp+1D0h+var_190], 8
0x140010b3c  jz      short loc_140010B49
0x140010b3e  mov     rcx, [rsp+1D0h+var_188]; lpMem
0x140010b43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010b48  nop
0x140010b49  test    r15d, r15d
0x140010b4c  jz      short loc_140010B5B
0x140010b4e  mov     rcx, r14; lpMem
0x140010b51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140010b56  mov     [rsp+1D0h+var_168], r12d
0x140010b5b  mov     rcx, [rbp+0D0h+var_40]
0x140010b62  xor     rcx, rsp; StackCookie
0x140010b65  call    __security_check_cookie
0x140010b6a  mov     rbx, [rsp+1D0h+arg_10]
0x140010b72  add     rsp, 1A0h
0x140010b79  pop     r15
0x140010b7b  pop     r14
0x140010b7d  pop     r13
0x140010b7f  pop     r12
0x140010b81  pop     rdi
0x140010b82  pop     rsi
0x140010b83  pop     rbp
0x140010b84  retn
```
