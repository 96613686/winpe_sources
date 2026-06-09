# GpReadOnlyMemoryStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800c29e0`
- end: `0x1800c2b0f`
- name: `?Stat@GpReadOnlyMemoryStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `303`
- prototype: `int(GpReadOnlyMemoryStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cc00`
- `0x1800c29e0`
- `0x1800e7040`
- `0x1800ea0ec`
- `0x1801740cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2ade`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2ade`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800c2a86`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800c2a86`

## pseudocode

```c
__int64 __fastcall GpReadOnlyMemoryStream::Stat(GpReadOnlyMemoryStream *this, struct _FILETIME *a2, char a3)
{
  unsigned int Win32HRESULT; // ebx
  volatile signed __int32 *v7; // rcx
  signed __int32 v8; // eax
  const unsigned __int16 *v9; // rdx
  void *v10; // rcx
  GpRuntime *v12; // rbp
  SIZE_T v13; // rsi
  void *v14; // rax
  signed __int32 v15; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v16; // [rsp+28h] [rbp-10h]

  Win32HRESULT = 0;
  if ( !a2 )
    return 2147942487LL;
  v7 = (volatile signed __int32 *)((char *)this + 16);
  if ( v7 )
  {
    v16 = v7;
    v8 = _InterlockedIncrement(v7);
    v15 = v8;
  }
  else
  {
    v15 = 0;
    v16 = &v15;
    v8 = 0;
  }
  if ( v8 )
  {
    Win32HRESULT = -2005204991;
  }
  else
  {
    memset_0(a2, 0, 0x50u);
    a2[1].dwLowDateTime = 2;
    a2[2] = (struct _FILETIME)*((unsigned int *)this + 8);
    v10 = (void *)*((_QWORD *)this + 6);
    if ( v10 == (void *)-1LL || GetFileTime(v10, a2 + 4, a2 + 5, a2 + 3) )
    {
      if ( (a3 & 1) == 0 )
      {
        v12 = (GpRuntime *)&qword_18018B1D8;
        if ( *((_QWORD *)this + 7) )
          v12 = (GpRuntime *)*((_QWORD *)this + 7);
        v13 = 2 * GpRuntime::UnicodeStringLength(v12, v9) + 2;
        v14 = CoTaskMemAlloc(v13);
        *a2 = (struct _FILETIME)v14;
        if ( v14 )
          memcpy_0(v14, v12, v13);
        else
          Win32HRESULT = -2147024882;
      }
    }
    else
    {
      Win32HRESULT = GetWin32HRESULT();
    }
  }
  _InterlockedDecrement(v16);
  return Win32HRESULT;
}

```

## disassembly

```asm
0x1800c29e0  mov     rax, rsp
0x1800c29e3  mov     [rax+8], rbx
0x1800c29e7  mov     [rax+10h], rbp
0x1800c29eb  mov     [rax+18h], rsi
0x1800c29ef  push    rdi
0x1800c29f0  sub     rsp, 30h
0x1800c29f4  xor     ebx, ebx
0x1800c29f6  mov     ebp, r8d
0x1800c29f9  mov     rdi, rdx
0x1800c29fc  mov     rsi, rcx
0x1800c29ff  test    rdx, rdx
0x1800c2a02  jz      loc_1800C2A9F
0x1800c2a08  add     rcx, 10h
0x1800c2a0c  jz      loc_1800C2AA6
0x1800c2a12  mov     [rax-10h], rcx
0x1800c2a16  lea     eax, [rbx+1]
0x1800c2a19  lock xadd [rcx], eax
0x1800c2a1d  inc     eax
0x1800c2a1f  mov     [rsp+38h+var_18], eax
0x1800c2a23  test    eax, eax
0x1800c2a25  jnz     short loc_1800C2A73
0x1800c2a27  xor     edx, edx; Val
0x1800c2a29  lea     r8d, [rax+50h]; Size
0x1800c2a2d  mov     rcx, rdi; void *
0x1800c2a30  call    memset_0
0x1800c2a35  mov     dword ptr [rdi+8], 2
0x1800c2a3c  mov     eax, [rsi+20h]
0x1800c2a3f  mov     [rdi+10h], rax
0x1800c2a43  mov     rcx, [rsi+30h]; hFile
0x1800c2a47  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c2a4b  jnz     short loc_1800C2A7A
0x1800c2a4d  test    bpl, 1
0x1800c2a51  jz      short loc_1800C2ABB
0x1800c2a53  mov     rax, [rsp+38h+var_10]
0x1800c2a58  lock dec dword ptr [rax]
0x1800c2a5b  mov     eax, ebx
0x1800c2a5d  mov     rbx, [rsp+38h+arg_0]
0x1800c2a62  mov     rbp, [rsp+38h+arg_8]
0x1800c2a67  mov     rsi, [rsp+38h+arg_10]
0x1800c2a6c  add     rsp, 30h
0x1800c2a70  pop     rdi
0x1800c2a71  retn
0x1800c2a73  mov     ebx, 887B0001h
0x1800c2a78  jmp     short loc_1800C2A53
0x1800c2a7a  lea     r9, [rdi+18h]; lpLastWriteTime
0x1800c2a7e  lea     r8, [rdi+28h]; lpLastAccessTime
0x1800c2a82  lea     rdx, [rdi+20h]; lpCreationTime
0x1800c2a86  call    cs:__imp_GetFileTime
0x1800c2a8d  nop     dword ptr [rax+rax+00h]
0x1800c2a92  test    eax, eax
0x1800c2a94  jnz     short loc_1800C2A4D
0x1800c2a96  call    ?GetWin32HRESULT@@YAJXZ; GetWin32HRESULT(void)
0x1800c2a9b  mov     ebx, eax
0x1800c2a9d  jmp     short loc_1800C2A53
0x1800c2a9f  mov     eax, 80070057h
0x1800c2aa4  jmp     short loc_1800C2A5D
0x1800c2aa6  lea     rcx, [rsp+38h+var_18]
0x1800c2aab  mov     [rsp+38h+var_18], ebx
0x1800c2aaf  mov     [rsp+38h+var_10], rcx
0x1800c2ab4  mov     eax, ebx
0x1800c2ab6  jmp     loc_1800C2A23
0x1800c2abb  cmp     [rsi+38h], rbx
0x1800c2abf  lea     rbp, qword_18018B1D8
0x1800c2ac6  cmovnz  rbp, [rsi+38h]
0x1800c2acb  mov     rcx, rbp; this
0x1800c2ace  call    ?UnicodeStringLength@GpRuntime@@YA_KPEBG@Z; GpRuntime::UnicodeStringLength(ushort const *)
0x1800c2ad3  lea     rsi, ds:2[rax*2]
0x1800c2adb  mov     rcx, rsi; cb
0x1800c2ade  call    cs:__imp_CoTaskMemAlloc
0x1800c2ae5  nop     dword ptr [rax+rax+00h]
0x1800c2aea  mov     [rdi], rax
0x1800c2aed  test    rax, rax
0x1800c2af0  jnz     short loc_1800C2AFC
0x1800c2af2  mov     ebx, 8007000Eh
0x1800c2af7  jmp     loc_1800C2A53
0x1800c2afc  mov     r8, rsi; Size
0x1800c2aff  mov     rdx, rbp; Src
0x1800c2b02  mov     rcx, rax; void *
0x1800c2b05  call    memcpy_0
0x1800c2b0a  jmp     loc_1800C2A53
```
