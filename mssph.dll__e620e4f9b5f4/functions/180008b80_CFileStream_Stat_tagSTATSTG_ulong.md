# CFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x180008b80`
- end: `0x180008ce9`
- name: `?Stat@CFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `361`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002eb4`
- `0x180008b80`
- `0x180011135`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ca9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ca9`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180008c8e`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180008c8e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180008c4b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180008c4b`

## pseudocode

```c
signed int __fastcall CFileStream::Stat(CFileStream *this, struct tagSTATSTG *a2, char a3)
{
  signed int result; // eax
  DWORD FileSize; // eax
  CLMString *v8; // rsi
  LPVOID v9; // rax
  size_t v10; // rdi
  void *v11; // rbx
  wchar_t *Buffer; // rax

  if ( !a2 )
    return -2147467261;
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return -2147024890;
  *((_DWORD *)a2 + 2) = 2;
  if ( *((_DWORD *)this + 50) )
  {
    *((_QWORD *)a2 + 2) = *((_QWORD *)this + 29);
    *((_QWORD *)a2 + 4) = *(_QWORD *)((char *)this + 204);
    *((_QWORD *)a2 + 5) = *(_QWORD *)((char *)this + 212);
    *((_QWORD *)a2 + 3) = *(_QWORD *)((char *)this + 220);
    goto LABEL_8;
  }
  FileSize = GetFileSize(*((HANDLE *)this + 3), (LPDWORD)a2 + 5);
  *((_DWORD *)a2 + 4) = FileSize;
  if ( (FileSize != -1 || !GetLastError())
    && GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
  {
LABEL_8:
    *((_DWORD *)a2 + 12) = *((_DWORD *)this + 48);
    *((_DWORD *)a2 + 13) = 2;
    *((_QWORD *)a2 + 9) = 0;
    *(GUID *)((char *)a2 + 56) = GUID_NULL;
    if ( (a3 & 1) != 0 )
    {
      *(_QWORD *)a2 = 0;
    }
    else
    {
      v8 = (CFileStream *)((char *)this + 32);
      v9 = CoTaskMemAlloc(2LL * (unsigned int)(*((_DWORD *)this + 13) + 1));
      *(_QWORD *)a2 = v9;
      if ( !v9 )
        return -2147024882;
      v10 = 2LL * (unsigned int)(*((_DWORD *)this + 13) + 1);
      v11 = v9;
      Buffer = CLMString::GetBuffer(v8, 0);
      memcpy_0(v11, Buffer, v10);
    }
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008b80  mov     [rsp+arg_0], rbx
0x180008b85  mov     [rsp+arg_8], rsi
0x180008b8a  push    rdi
0x180008b8b  sub     rsp, 20h
0x180008b8f  mov     esi, r8d
0x180008b92  mov     rbx, rdx
0x180008b95  mov     rdi, rcx
0x180008b98  test    rdx, rdx
0x180008b9b  jz      short loc_180008BC1
0x180008b9d  mov     rax, [rcx+18h]
0x180008ba1  inc     rax
0x180008ba4  test    rax, 0FFFFFFFFFFFFFFFEh
0x180008baa  jnz     short loc_180008BD6
0x180008bac  mov     eax, 80070006h
0x180008bb1  mov     rbx, [rsp+28h+arg_0]
0x180008bb6  mov     rsi, [rsp+28h+arg_8]
0x180008bbb  add     rsp, 20h
0x180008bbf  pop     rdi
0x180008bc0  retn
0x180008bc1  mov     rbx, [rsp+28h+arg_0]
0x180008bc6  mov     eax, 80004003h
0x180008bcb  mov     rsi, [rsp+28h+arg_8]
0x180008bd0  add     rsp, 20h
0x180008bd4  pop     rdi
0x180008bd5  retn
0x180008bd6  mov     dword ptr [rdx+8], 2
0x180008bdd  cmp     dword ptr [rcx+0C8h], 0
0x180008be4  jz      short loc_180008C43
0x180008be6  mov     rax, [rcx+0E8h]
0x180008bed  mov     [rdx+10h], rax
0x180008bf1  mov     rax, [rcx+0CCh]
0x180008bf8  mov     [rdx+20h], rax
0x180008bfc  mov     rax, [rcx+0D4h]
0x180008c03  mov     [rdx+28h], rax
0x180008c07  mov     rax, [rcx+0DCh]
0x180008c0e  mov     [rdx+18h], rax
0x180008c12  mov     eax, [rdi+0C0h]
0x180008c18  mov     [rbx+30h], eax
0x180008c1b  xor     eax, eax
0x180008c1d  mov     dword ptr [rbx+34h], 2
0x180008c24  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180008c2b  mov     [rbx+48h], rax
0x180008c2f  movups  xmmword ptr [rbx+38h], xmm0
0x180008c33  test    sil, 1
0x180008c37  jz      short loc_180008C9D
0x180008c39  mov     [rbx], rax
0x180008c3c  xor     eax, eax
0x180008c3e  jmp     loc_180008BB1
0x180008c43  mov     rcx, [rcx+18h]; hFile
0x180008c47  add     rdx, 14h; lpFileSizeHigh
0x180008c4b  call    cs:__imp_GetFileSize
0x180008c51  mov     [rbx+10h], eax
0x180008c54  cmp     eax, 0FFFFFFFFh
0x180008c57  jnz     short loc_180008C7E
0x180008c59  call    cs:__imp_GetLastError
0x180008c5f  test    eax, eax
0x180008c61  jz      short loc_180008C7E
0x180008c63  call    cs:__imp_GetLastError
0x180008c69  test    eax, eax
0x180008c6b  jle     loc_180008BB1
0x180008c71  movzx   eax, ax
0x180008c74  or      eax, 80070000h
0x180008c79  jmp     loc_180008BB1
0x180008c7e  mov     rcx, [rdi+18h]; hFile
0x180008c82  lea     r9, [rbx+18h]; lpLastWriteTime
0x180008c86  lea     r8, [rbx+28h]; lpLastAccessTime
0x180008c8a  lea     rdx, [rbx+20h]; lpCreationTime
0x180008c8e  call    cs:__imp_GetFileTime
0x180008c94  test    eax, eax
0x180008c96  jz      short loc_180008C63
0x180008c98  jmp     loc_180008C12
0x180008c9d  mov     ecx, [rdi+34h]
0x180008ca0  lea     rsi, [rdi+20h]
0x180008ca4  inc     ecx
0x180008ca6  add     rcx, rcx; cb
0x180008ca9  call    cs:__imp_CoTaskMemAlloc
0x180008caf  mov     [rbx], rax
0x180008cb2  test    rax, rax
0x180008cb5  jnz     short loc_180008CC1
0x180008cb7  mov     eax, 8007000Eh
0x180008cbc  jmp     loc_180008BB1
0x180008cc1  mov     edi, [rdi+34h]
0x180008cc4  xor     edx, edx; int
0x180008cc6  inc     edi
0x180008cc8  mov     rcx, rsi; this
0x180008ccb  add     rdi, rdi
0x180008cce  mov     rbx, rax
0x180008cd1  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x180008cd6  mov     rdx, rax; Src
0x180008cd9  mov     r8, rdi; Size
0x180008cdc  mov     rcx, rbx; void *
0x180008cdf  call    memcpy_0
0x180008ce4  jmp     loc_180008C3C
```
