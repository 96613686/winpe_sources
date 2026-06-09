# CFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800017a0`
- end: `0x180001900`
- name: `?Stat@CFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `352`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004dc0`
- `0x180038b28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000183f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000183f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001849`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800018b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800018b1`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180001874`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180001874`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001831`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180001831`

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
  }
  else
  {
    FileSize = GetFileSize(*((HANDLE *)this + 3), (LPDWORD)a2 + 5);
    *((_DWORD *)a2 + 4) = FileSize;
    if ( FileSize == -1 && GetLastError()
      || !GetFileTime(*((HANDLE *)this + 3), (LPFILETIME)a2 + 4, (LPFILETIME)a2 + 5, (LPFILETIME)a2 + 3) )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
  }
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

```

## disassembly

```asm
0x1800017a0  mov     [rsp+arg_0], rbx
0x1800017a5  mov     [rsp+arg_8], rsi
0x1800017aa  push    rdi
0x1800017ab  sub     rsp, 20h
0x1800017af  mov     esi, r8d
0x1800017b2  mov     rbx, rdx
0x1800017b5  mov     rdi, rcx
0x1800017b8  test    rdx, rdx
0x1800017bb  jnz     short loc_1800017C7
0x1800017bd  mov     eax, 80004003h
0x1800017c2  jmp     loc_1800018F0
0x1800017c7  mov     rax, [rcx+18h]
0x1800017cb  inc     rax
0x1800017ce  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800017d4  jnz     short loc_1800017EB
0x1800017d6  mov     eax, 80070006h
0x1800017db  mov     rbx, [rsp+28h+arg_0]
0x1800017e0  mov     rsi, [rsp+28h+arg_8]
0x1800017e5  add     rsp, 20h
0x1800017e9  pop     rdi
0x1800017ea  retn
0x1800017eb  mov     dword ptr [rdx+8], 2
0x1800017f2  cmp     dword ptr [rcx+0C8h], 0
0x1800017f9  jz      short loc_180001829
0x1800017fb  mov     rax, [rcx+0E8h]
0x180001802  mov     [rdx+10h], rax
0x180001806  mov     rax, [rcx+0CCh]
0x18000180d  mov     [rdx+20h], rax
0x180001811  mov     rax, [rcx+0D4h]
0x180001818  mov     [rdx+28h], rax
0x18000181c  mov     rax, [rcx+0DCh]
0x180001823  mov     [rdx+18h], rax
0x180001827  jmp     short loc_18000187E
0x180001829  mov     rcx, [rcx+18h]; hFile
0x18000182d  add     rdx, 14h; lpFileSizeHigh
0x180001831  call    cs:__imp_GetFileSize
0x180001837  mov     [rbx+10h], eax
0x18000183a  cmp     eax, 0FFFFFFFFh
0x18000183d  jnz     short loc_180001864
0x18000183f  call    cs:__imp_GetLastError
0x180001845  test    eax, eax
0x180001847  jz      short loc_180001864
0x180001849  call    cs:__imp_GetLastError
0x18000184f  test    eax, eax
0x180001851  jle     loc_1800018F0
0x180001857  movzx   eax, ax
0x18000185a  or      eax, 80070000h
0x18000185f  jmp     loc_1800018F0
0x180001864  mov     rcx, [rdi+18h]; hFile
0x180001868  lea     r9, [rbx+18h]; lpLastWriteTime
0x18000186c  lea     r8, [rbx+28h]; lpLastAccessTime
0x180001870  lea     rdx, [rbx+20h]; lpCreationTime
0x180001874  call    cs:__imp_GetFileTime
0x18000187a  test    eax, eax
0x18000187c  jz      short loc_180001849
0x18000187e  mov     eax, [rdi+0C0h]
0x180001884  mov     [rbx+30h], eax
0x180001887  xor     eax, eax
0x180001889  mov     dword ptr [rbx+34h], 2
0x180001890  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180001897  mov     [rbx+48h], rax
0x18000189b  movups  xmmword ptr [rbx+38h], xmm0
0x18000189f  test    sil, 1
0x1800018a3  jnz     short loc_1800018EB
0x1800018a5  mov     ecx, [rdi+34h]
0x1800018a8  lea     rsi, [rdi+20h]
0x1800018ac  inc     ecx
0x1800018ae  add     rcx, rcx; cb
0x1800018b1  call    cs:__imp_CoTaskMemAlloc
0x1800018b7  mov     [rbx], rax
0x1800018ba  test    rax, rax
0x1800018bd  jnz     short loc_1800018C6
0x1800018bf  mov     eax, 8007000Eh
0x1800018c4  jmp     short loc_1800018F0
0x1800018c6  mov     edi, [rdi+34h]
0x1800018c9  xor     edx, edx; int
0x1800018cb  inc     edi
0x1800018cd  mov     rcx, rsi; this
0x1800018d0  add     rdi, rdi
0x1800018d3  mov     rbx, rax
0x1800018d6  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800018db  mov     rdx, rax; Src
0x1800018de  mov     r8, rdi; Size
0x1800018e1  mov     rcx, rbx; void *
0x1800018e4  call    memcpy_0
0x1800018e9  jmp     short loc_1800018EE
0x1800018eb  mov     [rbx], rax
0x1800018ee  xor     eax, eax
0x1800018f0  mov     rbx, [rsp+28h+arg_0]
0x1800018f5  mov     rsi, [rsp+28h+arg_8]
0x1800018fa  add     rsp, 20h
0x1800018fe  pop     rdi
0x1800018ff  retn
```
