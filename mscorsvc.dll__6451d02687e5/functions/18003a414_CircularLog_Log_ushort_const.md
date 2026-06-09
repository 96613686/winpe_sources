# CircularLog::Log(ushort const *)

- ea: `0x18003a414`
- end: `0x18003a682`
- name: `?Log@CircularLog@@QEAAXPEBG@Z`
- size: `622`
- prototype: `void __fastcall(CircularLog *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18002de54`

## callees

- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x1800323e4`
- `0x18003a414`
- `0x18003a740`
- `0x18003a8d4`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!WriteFile` at `0x18003a5e6`
- `KERNEL32!WriteFile` at `0x18003a5e6`
- `KERNEL32!GetFileSizeEx` at `0x18003a48a`
- `KERNEL32!GetFileSizeEx` at `0x18003a48a`
- `KERNEL32!CloseHandle` at `0x18003a4a4`
- `KERNEL32!CloseHandle` at `0x18003a5ef`
- `KERNEL32!CloseHandle` at `0x18003a4a4`
- `KERNEL32!CloseHandle` at `0x18003a5ef`
- `KERNEL32!HeapFree` at `0x18003a627`
- `KERNEL32!HeapFree` at `0x18003a627`
- `KERNEL32!GetProcessHeap` at `0x18003a612`
- `KERNEL32!GetProcessHeap` at `0x18003a612`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CircularLog::Log(CircularLog *this, const unsigned __int16 *a2)
{
  void *v3; // rax
  void *v4; // rdi
  int v5; // ecx
  CircularLog *v6; // rcx
  CircularLog *v7; // rcx
  __int64 v8; // rcx
  __int16 *v9; // rax
  unsigned __int16 *v10; // rsi
  BOOL v11; // r14d
  __int16 v12; // dx
  __int16 i; // cx
  const char *UTF8; // rax
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v17; // [rsp+38h] [rbp-D0h] BYREF
  _DWORD v18[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+48h] [rbp-C0h]
  void *v20; // [rsp+50h] [rbp-B8h]
  DWORD NumberOfBytesWritten[2]; // [rsp+58h] [rbp-B0h] BYREF
  LARGE_INTEGER FileSize; // [rsp+60h] [rbp-A8h] BYREF
  __int16 *v23; // [rsp+68h] [rbp-A0h]
  __int64 v24; // [rsp+70h] [rbp-98h]
  int v25; // [rsp+78h] [rbp-90h] BYREF
  __int64 v26; // [rsp+7Ch] [rbp-8Ch]
  LPVOID lpMem; // [rsp+88h] [rbp-80h]
  __int16 v28; // [rsp+90h] [rbp-78h] BYREF

  if ( NGENService::g_LogFile )
  {
    v3 = (void *)CircularLog::OpenFile(this);
    v4 = v3;
    if ( v3 != (void *)-1LL )
    {
      v5 = dword_18006F2BC;
      if ( (dword_18006F2BC & 0xF) == 0 )
      {
        if ( GetFileSizeEx(v3, &FileSize) )
        {
          if ( FileSize.QuadPart > (unsigned int)dword_18006F2B8 )
          {
            CloseHandle(v4);
            CircularLog::CheckForLogReset(v6, 1);
            v4 = (void *)CircularLog::OpenFile(v7);
            if ( v4 == (void *)-1LL )
              return;
          }
        }
        v5 = dword_18006F2BC;
      }
      dword_18006F2BC = v5 + 1;
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = (__int16 *)operator new(saturated_mul(2 * v8 + 1, 2u));
      v10 = (unsigned __int16 *)v9;
      v23 = v9;
      v11 = v9 != 0;
      LODWORD(v24) = v11;
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
      LODWORD(v19) = 16;
      v20 = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)v18, v10);
      v26 = 256;
      lpMem = &v28;
      v25 = 2;
      v28 = 0;
      v17 = 0;
      UTF8 = SString::GetUTF8((SString *)v18, (struct SString::AbstractScratchBuffer *)&v25, &v17);
      WriteFile(v4, UTF8, v17 - 1, NumberOfBytesWritten, 0);
      CloseHandle(v4);
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

```

## disassembly

```asm
0x18003a414  mov     rax, rsp
0x18003a417  mov     [rax+8], rbx
0x18003a41b  mov     [rax+18h], rsi
0x18003a41f  mov     [rax+20h], rdi
0x18003a423  push    rbp
0x18003a424  push    r12
0x18003a426  push    r13
0x18003a428  push    r14
0x18003a42a  push    r15
0x18003a42c  lea     rbp, [rax-0C8h]
0x18003a433  sub     rsp, 1A0h
0x18003a43a  mov     rax, cs:__security_cookie
0x18003a441  xor     rax, rsp
0x18003a444  mov     [rbp+0C0h+var_30], rax
0x18003a44b  mov     rbx, rdx
0x18003a44e  xor     r15d, r15d
0x18003a451  cmp     cs:?g_LogFile@NGENService@@3VCircularLog@@A, r15b; CircularLog NGENService::g_LogFile
0x18003a458  jz      loc_18003A652
0x18003a45e  call    ?OpenFile@CircularLog@@IEAAPEAXXZ; CircularLog::OpenFile(void)
0x18003a463  mov     rdi, rax
0x18003a466  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003a46a  cmp     rax, rsi
0x18003a46d  jz      loc_18003A652
0x18003a473  mov     ecx, cs:dword_18006F2BC
0x18003a479  lea     r13d, [r15+1]
0x18003a47d  test    cl, 0Fh
0x18003a480  jnz     short loc_18003A4C9
0x18003a482  lea     rdx, [rsp+1C0h+FileSize]; lpFileSize
0x18003a487  mov     rcx, rax; hFile
0x18003a48a  call    cs:__imp_GetFileSizeEx
0x18003a490  test    eax, eax
0x18003a492  jz      short loc_18003A4C3
0x18003a494  mov     eax, cs:dword_18006F2B8
0x18003a49a  cmp     qword ptr [rsp+1C0h+FileSize], rax
0x18003a49f  jle     short loc_18003A4C3
0x18003a4a1  mov     rcx, rdi; hObject
0x18003a4a4  call    cs:__imp_CloseHandle
0x18003a4aa  mov     edx, r13d; int
0x18003a4ad  call    ?CheckForLogReset@CircularLog@@IEAAXH@Z; CircularLog::CheckForLogReset(int)
0x18003a4b2  call    ?OpenFile@CircularLog@@IEAAPEAXXZ; CircularLog::OpenFile(void)
0x18003a4b7  mov     rdi, rax
0x18003a4ba  cmp     rax, rsi
0x18003a4bd  jz      loc_18003A652
0x18003a4c3  mov     ecx, cs:dword_18006F2BC
0x18003a4c9  add     ecx, r13d
0x18003a4cc  mov     cs:dword_18006F2BC, ecx
0x18003a4d2  mov     rcx, rsi
0x18003a4d5  inc     rcx
0x18003a4d8  cmp     [rbx+rcx*2], r15w
0x18003a4dd  jnz     short loc_18003A4D5
0x18003a4df  lea     rcx, ds:1[rcx*2]
0x18003a4e7  mov     r12d, 2
0x18003a4ed  mov     eax, r12d
0x18003a4f0  mul     rcx
0x18003a4f3  cmovo   rax, rsi
0x18003a4f7  mov     rcx, rax; dwBytes
0x18003a4fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a4ff  mov     rsi, rax
0x18003a502  mov     [rsp+1C0h+var_160], rax
0x18003a507  mov     dword ptr [rsp+1C0h+var_158], r15d
0x18003a50c  mov     r14d, r15d
0x18003a50f  test    rax, rax
0x18003a512  cmovnz  r14d, r13d
0x18003a516  mov     dword ptr [rsp+1C0h+var_158], r14d
0x18003a51b  movzx   edx, r15w
0x18003a51f  movzx   ecx, word ptr [rbx]
0x18003a522  test    cx, cx
0x18003a525  jz      short loc_18003A55E
0x18003a527  lea     r9d, [r12+8]
0x18003a52c  lea     r8d, [r12+0Bh]
0x18003a531  cmp     cx, r9w
0x18003a535  jnz     short loc_18003A54A
0x18003a537  mov     ecx, r9d
0x18003a53a  cmp     dx, r8w
0x18003a53e  jz      short loc_18003A54A
0x18003a540  mov     [rax], r8w
0x18003a544  add     rax, r12
0x18003a547  movzx   ecx, word ptr [rbx]
0x18003a54a  mov     [rax], cx
0x18003a54d  add     rax, r12
0x18003a550  movzx   edx, word ptr [rbx]
0x18003a553  add     rbx, r12
0x18003a556  movzx   ecx, word ptr [rbx]
0x18003a559  test    cx, cx
0x18003a55c  jnz     short loc_18003A531
0x18003a55e  mov     [rax], r15w
0x18003a562  mov     [rsp+1C0h+var_188], r12d
0x18003a567  mov     [rsp+1C0h+var_184], r12d
0x18003a56c  mov     dword ptr [rsp+1C0h+var_180], 10h
0x18003a574  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x18003a57b  mov     [rsp+1C0h+var_178], rax
0x18003a580  mov     rdx, rsi; unsigned __int16 *
0x18003a583  lea     rcx, [rsp+1C0h+var_188]; this
0x18003a588  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x18003a58d  nop
0x18003a58e  mov     qword ptr [rsp+1C0h+var_150], r15
0x18003a593  mov     [rsp+1C0h+var_14C], 100h
0x18003a59c  mov     [rbp+0C0h+lpMem], r15
0x18003a5a0  lea     rax, [rbp+0C0h+var_138]
0x18003a5a4  mov     [rbp+0C0h+lpMem], rax
0x18003a5a8  mov     [rsp+1C0h+var_150], r12d
0x18003a5ad  mov     rax, [rbp+0C0h+lpMem]
0x18003a5b1  mov     [rax], r15w
0x18003a5b5  mov     [rsp+1C0h+var_190], r15d
0x18003a5ba  lea     r8, [rsp+1C0h+var_190]; unsigned int *
0x18003a5bf  lea     rdx, [rsp+1C0h+var_150]; struct SString::AbstractScratchBuffer *
0x18003a5c4  lea     rcx, [rsp+1C0h+var_188]; this
0x18003a5c9  call    ?GetUTF8@SString@@QEBAPEBDAEAVAbstractScratchBuffer@1@PEAI@Z; SString::GetUTF8(SString::AbstractScratchBuffer &,uint *)
0x18003a5ce  mov     r8d, [rsp+1C0h+var_190]
0x18003a5d3  dec     r8d; nNumberOfBytesToWrite
0x18003a5d6  mov     [rsp+1C0h+lpOverlapped], r15; lpOverlapped
0x18003a5db  lea     r9, [rsp+1C0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18003a5e0  mov     rdx, rax; lpBuffer
0x18003a5e3  mov     rcx, rdi; hFile
0x18003a5e6  call    cs:__imp_WriteFile
0x18003a5ec  mov     rcx, rdi; hObject
0x18003a5ef  call    cs:__imp_CloseHandle
0x18003a5f5  nop
0x18003a5f6  test    byte ptr [rsp+1C0h+var_14C+4], 8
0x18003a5fb  jz      short loc_18003A62E
0x18003a5fd  mov     rbx, [rbp+0C0h+lpMem]
0x18003a601  test    rbx, rbx
0x18003a604  jz      short loc_18003A62E
0x18003a606  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003a60d  test    rax, rax
0x18003a610  jnz     short loc_18003A61F
0x18003a612  call    cs:__imp_GetProcessHeap
0x18003a618  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18003a61f  mov     r8, rbx; lpMem
0x18003a622  xor     edx, edx; dwFlags
0x18003a624  mov     rcx, rax; hHeap
0x18003a627  call    cs:__imp_HeapFree
0x18003a62d  nop
0x18003a62e  test    byte ptr [rsp+1C0h+var_180], 8
0x18003a633  jz      short loc_18003A640
0x18003a635  mov     rcx, [rsp+1C0h+var_178]; lpMem
0x18003a63a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a63f  nop
0x18003a640  test    r14d, r14d
0x18003a643  jz      short loc_18003A652
0x18003a645  mov     rcx, rsi; lpMem
0x18003a648  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003a64d  mov     dword ptr [rsp+1C0h+var_158], r15d
0x18003a652  mov     rcx, [rbp+0C0h+var_30]
0x18003a659  xor     rcx, rsp; StackCookie
0x18003a65c  call    __security_check_cookie
0x18003a661  lea     r11, [rsp+1C0h+var_20]
0x18003a669  mov     rbx, [r11+30h]
0x18003a66d  mov     rsi, [r11+40h]
0x18003a671  mov     rdi, [r11+48h]
0x18003a675  mov     rsp, r11
0x18003a678  pop     r15
0x18003a67a  pop     r14
0x18003a67c  pop     r13
0x18003a67e  pop     r12
0x18003a680  pop     rbp
0x18003a681  retn
```
