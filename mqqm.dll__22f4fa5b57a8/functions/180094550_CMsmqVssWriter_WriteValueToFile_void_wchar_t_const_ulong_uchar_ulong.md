# CMsmqVssWriter::WriteValueToFile(void *,wchar_t const *,ulong,uchar *,ulong)

- ea: `0x180094550`
- end: `0x180094729`
- name: `?WriteValueToFile@CMsmqVssWriter@@AEAAJPEAXPEB_WKPEAEK@Z`
- size: `473`
- prototype: `int(CMsmqVssWriter *__hidden this, void *, const wchar_t *, unsigned int, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18008e93c`

## callees

- `0x18000bb04`
- `0x18000cb80`
- `0x18002c61c`
- `0x180094550`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800945f0`
- `msvcrt!free` at `0x180094667`
- `msvcrt!free` at `0x180094692`
- `msvcrt!free` at `0x180094700`
- `msvcrt!free` at `0x18009470f`
- `msvcrt!free` at `0x1800945f0`
- `msvcrt!free` at `0x180094667`
- `msvcrt!free` at `0x180094692`
- `msvcrt!free` at `0x180094700`
- `msvcrt!free` at `0x18009470f`
- `KERNEL32!GetLastError` at `0x1800946cf`
- `KERNEL32!GetLastError` at `0x1800946cf`
- `KERNEL32!WriteFile` at `0x1800946c5`
- `KERNEL32!WriteFile` at `0x1800946c5`

## string_xrefs

- `0x1800945de`: `writer/mqwriter`
- `0x180094655`: `writer/mqwriter`
- `0x18009467b`: `writer/mqwriter`
- `0x1800946ee`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMsmqVssWriter::WriteValueToFile(
        CMsmqVssWriter *this,
        void *a2,
        const wchar_t *a3,
        int a4,
        unsigned __int8 *a5,
        unsigned int a6)
{
  unsigned int v9; // eax
  unsigned int v10; // r12d
  wchar_t *v11; // rbx
  int v12; // eax
  unsigned int v13; // edi
  unsigned __int8 *v15; // r15
  unsigned int v16; // eax
  wchar_t *v17; // r14
  unsigned int v18; // edi
  __int64 i; // rsi
  int v20; // eax
  unsigned int v21; // ebp
  signed int LastError; // eax
  CMsmqVssWriter *NumberOfBytesWritten; // [rsp+90h] [rbp+8h] BYREF

  NumberOfBytesWritten = this;
  v9 = mqwcslen(a3);
  v10 = a6;
  LODWORD(NumberOfBytesWritten) = v9 + 2 * a6 + 11;
  v11 = (wchar_t *)MmAllocate(saturated_mul((unsigned int)NumberOfBytesWritten, 2u));
  v12 = StringCchPrintfW(v11, (unsigned int)NumberOfBytesWritten, L"%s=%08u:", a3, a4);
  v13 = v12;
  if ( v12 < 0 )
  {
    LogMsgHR(v12, (wchar_t *)L"writer/mqwriter", 0xCD0u);
    free(v11);
    return v13;
  }
  v15 = a5;
  v16 = mqwcslen(v11);
  v17 = &v11[v16];
  v18 = (_DWORD)NumberOfBytesWritten - v16;
  for ( i = 0; (unsigned int)i < v10; i = (unsigned int)(i + 1) )
  {
    if ( !v18 )
    {
      v13 = -1072824314;
      LogMsgHR(-1072824314, (wchar_t *)L"writer/mqwriter", 0xCF8u);
      free(v11);
      return v13;
    }
    v20 = StringCchPrintfW(v17, v18, L"%02x", v15[i]);
    v21 = v20;
    if ( v20 < 0 )
    {
      LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0xCE4u);
      free(v11);
      return v21;
    }
    v17 += 2;
    v18 -= 2;
  }
  if ( !WriteFile(a2, v11, 2 * (_DWORD)NumberOfBytesWritten - 2, (LPDWORD)&NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (v13 & 0x80000000) != 0 )
      LogMsgHR(v13, (wchar_t *)L"writer/mqwriter", 0xD0Cu);
    free(v11);
    return v13;
  }
  free(v11);
  return 0;
}

```

## disassembly

```asm
0x180094550  mov     [rsp+NumberOfBytesWritten], rcx
0x180094555  push    rbx
0x180094556  push    rbp
0x180094557  push    rsi
0x180094558  push    rdi
0x180094559  push    r12
0x18009455b  push    r13
0x18009455d  push    r14
0x18009455f  push    r15
0x180094561  sub     rsp, 48h
0x180094565  mov     edi, r9d
0x180094568  mov     rsi, r8
0x18009456b  mov     r13, rdx
0x18009456e  mov     rcx, r8; wchar_t *
0x180094571  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180094576  mov     r12d, [rsp+88h+arg_28]
0x18009457e  lea     ecx, ds:0Bh[r12*2]
0x180094586  add     ecx, eax
0x180094588  mov     dword ptr [rsp+88h+NumberOfBytesWritten], ecx
0x18009458f  mov     r10d, ecx
0x180094592  mov     eax, 2
0x180094597  mul     r10
0x18009459a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800945a1  cmovb   rax, rcx
0x1800945a5  mov     rcx, rax; unsigned __int64
0x1800945a8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800945ad  mov     rbx, rax
0x1800945b0  mov     [rsp+88h+var_58], rax
0x1800945b5  mov     edx, dword ptr [rsp+88h+NumberOfBytesWritten]; unsigned __int64
0x1800945bc  mov     dword ptr [rsp+88h+lpOverlapped], edi
0x1800945c0  mov     r9, rsi
0x1800945c3  lea     r8, aS08u; "%s=%08u:"
0x1800945ca  mov     rcx, rax; wchar_t *
0x1800945cd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800945d2  mov     edi, eax
0x1800945d4  test    eax, eax
0x1800945d6  jns     short loc_1800945FE
0x1800945d8  mov     r8d, 0CD0h; unsigned __int16
0x1800945de  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800945e5  mov     ecx, eax; int
0x1800945e7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800945ec  nop
0x1800945ed  mov     rcx, rbx; Block
0x1800945f0  call    cs:__imp_free
0x1800945f6  nop
0x1800945f7  mov     eax, edi
0x1800945f9  jmp     loc_180094718
0x1800945fe  mov     r15, [rsp+88h+arg_20]
0x180094606  mov     rcx, rbx; wchar_t *
0x180094609  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18009460e  mov     ecx, eax
0x180094610  lea     r14, [rbx+rcx*2]
0x180094614  mov     edi, dword ptr [rsp+88h+NumberOfBytesWritten]
0x18009461b  sub     edi, eax
0x18009461d  xor     esi, esi
0x18009461f  cmp     esi, r12d
0x180094622  jnb     short loc_18009469E
0x180094624  test    edi, edi
0x180094626  jz      short loc_180094675
0x180094628  movzx   r9d, byte ptr [rsi+r15]
0x18009462d  mov     edx, edi; unsigned __int64
0x18009462f  lea     r8, a02x; "%02x"
0x180094636  mov     rcx, r14; wchar_t *
0x180094639  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18009463e  mov     ebp, eax
0x180094640  test    eax, eax
0x180094642  js      short loc_18009464F
0x180094644  add     r14, 4
0x180094648  add     edi, 0FFFFFFFEh
0x18009464b  inc     esi
0x18009464d  jmp     short loc_18009461F
0x18009464f  mov     r8d, 0CE4h; unsigned __int16
0x180094655  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009465c  mov     ecx, ebp; int
0x18009465e  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180094663  nop
0x180094664  mov     rcx, rbx; Block
0x180094667  call    cs:__imp_free
0x18009466d  nop
0x18009466e  mov     eax, ebp
0x180094670  jmp     loc_180094718
0x180094675  mov     r8d, 0CF8h; unsigned __int16
0x18009467b  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180094682  mov     edi, 0C00E0006h
0x180094687  mov     ecx, edi; int
0x180094689  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009468e  nop
0x18009468f  mov     rcx, rbx; Block
0x180094692  call    cs:__imp_free
0x180094698  nop
0x180094699  jmp     loc_1800945F7
0x18009469e  mov     r8d, dword ptr [rsp+88h+NumberOfBytesWritten]
0x1800946a6  lea     r8d, ds:0FFFFFFFFFFFFFFFEh[r8*2]; nNumberOfBytesToWrite
0x1800946ae  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x1800946b7  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800946bf  mov     rdx, rbx; lpBuffer
0x1800946c2  mov     rcx, r13; hFile
0x1800946c5  call    cs:__imp_WriteFile
0x1800946cb  test    eax, eax
0x1800946cd  jnz     short loc_18009470C
0x1800946cf  call    cs:__imp_GetLastError
0x1800946d5  mov     edi, eax
0x1800946d7  test    eax, eax
0x1800946d9  jle     short loc_1800946E4
0x1800946db  movzx   edi, ax
0x1800946de  or      edi, 80070000h
0x1800946e4  test    edi, edi
0x1800946e6  jns     short loc_1800946FD
0x1800946e8  mov     r8d, 0D0Ch; unsigned __int16
0x1800946ee  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800946f5  mov     ecx, edi; int
0x1800946f7  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800946fc  nop
0x1800946fd  mov     rcx, rbx; Block
0x180094700  call    cs:__imp_free
0x180094706  nop
0x180094707  jmp     loc_1800945F7
0x18009470c  mov     rcx, rbx; Block
0x18009470f  call    cs:__imp_free
0x180094715  nop
0x180094716  xor     eax, eax
0x180094718  add     rsp, 48h
0x18009471c  pop     r15
0x18009471e  pop     r14
0x180094720  pop     r13
0x180094722  pop     r12
0x180094724  pop     rdi
0x180094725  pop     rsi
0x180094726  pop     rbp
0x180094727  pop     rbx
0x180094728  retn
```
