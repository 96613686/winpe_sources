# CSimpStorageOpen::Stat(tagSTATSTG *,ulong)

- ea: `0x18004f140`
- end: `0x18004f234`
- name: `?Stat@CSimpStorageOpen@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `244`
- prototype: `int(CSimpStorageOpen *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001e2f0`
- `0x180023e70`
- `0x180026bc4`
- `0x18004f140`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f19e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f19e`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004f194`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18004f194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f1d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f1d3`

## pseudocode

```c
__int64 __fastcall CSimpStorageOpen::Stat(CSimpStorageOpen *this, struct tagSTATSTG *a2, int a3)
{
  __int64 result; // rax
  DWORD LastError; // eax
  __int64 v8; // rax
  SIZE_T v9; // rbp
  unsigned __int16 *v10; // rax

  if ( !(unsigned int)IsValidReadPtrIn(a2, 0x50u) )
    return 2147680265LL;
  if ( (a3 & 0xFFFFFFFE) != 0 )
    return 2147680511LL;
  if ( !GetFileTime(*((HANDLE *)this + 8), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
  {
    LastError = GetLastError();
    return Win32ErrorToScode(LastError);
  }
  if ( (a3 & 1) == 0 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)this + v8 + 328) );
    v9 = (unsigned int)(2 * v8 + 2);
    v10 = (unsigned __int16 *)CoTaskMemAlloc(v9);
    *(_QWORD *)a2 = v10;
    if ( !v10 )
      return 2147680264LL;
    StringCbCopyW(v10, v9, (const unsigned __int16 *)this + 328);
  }
  *((_DWORD *)a2 + 12) = *((_DWORD *)this + 162);
  *(_OWORD *)((char *)a2 + 56) = *(_OWORD *)((char *)this + 604);
  *((_DWORD *)a2 + 18) = *((_DWORD *)this + 163);
  result = 0;
  *((_DWORD *)a2 + 2) = 1;
  *((_QWORD *)a2 + 2) = 0;
  *((_DWORD *)a2 + 13) = 0;
  *((_DWORD *)a2 + 19) = 0;
  return result;
}

```

## disassembly

```asm
0x18004f140  push    rbx
0x18004f142  push    rbp
0x18004f143  push    rsi
0x18004f144  push    rdi
0x18004f145  push    r14
0x18004f147  sub     rsp, 20h
0x18004f14b  mov     rbx, rdx
0x18004f14e  mov     rdi, rcx
0x18004f151  mov     rcx, rbx; void *
0x18004f154  mov     edx, 50h ; 'P'; unsigned __int64
0x18004f159  mov     esi, r8d
0x18004f15c  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x18004f161  xor     r14d, r14d
0x18004f164  test    eax, eax
0x18004f166  jnz     short loc_18004F172
0x18004f168  mov     eax, 80030009h
0x18004f16d  jmp     loc_18004F229
0x18004f172  test    esi, 0FFFFFFFEh
0x18004f178  jz      short loc_18004F184
0x18004f17a  mov     eax, 800300FFh
0x18004f17f  jmp     loc_18004F229
0x18004f184  mov     rcx, [rdi+40h]; hFile
0x18004f188  lea     r9, [rbx+18h]; lpLastWriteTime
0x18004f18c  lea     r8, [rbx+28h]; lpLastAccessTime
0x18004f190  lea     rdx, [rbx+20h]; lpCreationTime
0x18004f194  call    cs:__imp_GetFileTime
0x18004f19a  test    eax, eax
0x18004f19c  jnz     short loc_18004F1AD
0x18004f19e  call    cs:__imp_GetLastError
0x18004f1a4  mov     ecx, eax; unsigned int
0x18004f1a6  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004f1ab  jmp     short loc_18004F229
0x18004f1ad  test    sil, 1
0x18004f1b1  jnz     short loc_18004F1F6
0x18004f1b3  lea     rsi, [rdi+290h]
0x18004f1ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f1be  inc     rax
0x18004f1c1  cmp     [rsi+rax*2], r14w
0x18004f1c6  jnz     short loc_18004F1BE
0x18004f1c8  lea     eax, ds:2[rax*2]
0x18004f1cf  mov     ecx, eax; cb
0x18004f1d1  mov     ebp, eax
0x18004f1d3  call    cs:__imp_CoTaskMemAlloc
0x18004f1d9  mov     [rbx], rax
0x18004f1dc  test    rax, rax
0x18004f1df  jnz     short loc_18004F1E8
0x18004f1e1  mov     eax, 80030008h
0x18004f1e6  jmp     short loc_18004F229
0x18004f1e8  mov     r8, rsi; unsigned __int16 *
0x18004f1eb  mov     rdx, rbp; unsigned __int64
0x18004f1ee  mov     rcx, rax; unsigned __int16 *
0x18004f1f1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18004f1f6  mov     eax, [rdi+288h]
0x18004f1fc  mov     [rbx+30h], eax
0x18004f1ff  movups  xmm0, xmmword ptr [rdi+25Ch]
0x18004f206  movdqu  xmmword ptr [rbx+38h], xmm0
0x18004f20b  mov     eax, [rdi+28Ch]
0x18004f211  mov     [rbx+48h], eax
0x18004f214  xor     eax, eax
0x18004f216  mov     dword ptr [rbx+8], 1
0x18004f21d  mov     [rbx+10h], r14
0x18004f221  mov     [rbx+34h], r14d
0x18004f225  mov     [rbx+4Ch], r14d
0x18004f229  add     rsp, 20h
0x18004f22d  pop     r14
0x18004f22f  pop     rdi
0x18004f230  pop     rsi
0x18004f231  pop     rbp
0x18004f232  pop     rbx
0x18004f233  retn
```
