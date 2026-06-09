# CMapViewOfFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1801b52c0`
- end: `0x1801b53f5`
- name: `?Stat@CMapViewOfFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `309`
- prototype: `int(CMapViewOfFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022f7c`
- `0x180027430`
- `0x1801b52c0`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801b5355`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1801b5355`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b53eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b53eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b53a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b53a8`

## pseudocode

```c
__int64 __fastcall CMapViewOfFileStream::Stat(CMapViewOfFileStream *this, struct tagSTATSTG *a2, int a3)
{
  __int64 v7; // rcx
  unsigned __int16 *v8; // r11
  unsigned __int16 *v9; // rax
  const unsigned __int16 *v10; // r8
  int v11; // ebx
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+20h] [rbp-58h] BYREF

  if ( !a2 )
    return 2147942487LL;
  memset_0(a2, 0, 0x50u);
  if ( !*((_QWORD *)this + 3) )
    return 2147549183LL;
  *((_DWORD *)a2 + 2) = 2;
  *((_QWORD *)a2 + 2) = *(_QWORD *)(*((_QWORD *)this + 3) + 544LL);
  *((_DWORD *)a2 + 12) = 32;
  v7 = *((_QWORD *)this + 3);
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( GetFileInformationByHandle(*(HANDLE *)(v7 + 536), &FileInformation) )
  {
    *((_QWORD *)a2 + 3) = FileInformation.ftLastWriteTime;
    *((_QWORD *)a2 + 4) = FileInformation.ftCreationTime;
    *((_QWORD *)a2 + 5) = FileInformation.ftLastAccessTime;
  }
  if ( a3 )
  {
    v8 = 0;
LABEL_9:
    *(_QWORD *)a2 = v8;
    return 0;
  }
  v9 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  v8 = v9;
  if ( !v9 )
    return 2147942414LL;
  v10 = (const unsigned __int16 *)(*((_QWORD *)this + 3) + 16LL);
  *v9 = 0;
  if ( *v10 )
  {
    v11 = StringCchCopyW(v9, 0x104u, v10);
    if ( v11 >= 0 )
      goto LABEL_9;
  }
  else
  {
    v11 = -2147418113;
  }
  CoTaskMemFree(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801b52c0  mov     [rsp+arg_10], rbx
0x1801b52c5  push    rbp
0x1801b52c6  push    rsi
0x1801b52c7  push    rdi
0x1801b52c8  sub     rsp, 60h
0x1801b52cc  mov     rax, cs:__security_cookie
0x1801b52d3  xor     rax, rsp
0x1801b52d6  mov     [rsp+78h+var_20], rax
0x1801b52db  xor     ebp, ebp
0x1801b52dd  mov     ebx, r8d
0x1801b52e0  mov     rdi, rdx
0x1801b52e3  mov     rsi, rcx
0x1801b52e6  test    rdx, rdx
0x1801b52e9  jnz     short loc_1801B52F5
0x1801b52eb  mov     eax, 80070057h
0x1801b52f0  jmp     loc_1801B5386
0x1801b52f5  xor     edx, edx; Val
0x1801b52f7  mov     rcx, rdi; void *
0x1801b52fa  lea     r8d, [rdx+50h]; Size
0x1801b52fe  call    memset_0
0x1801b5303  cmp     [rsi+18h], rbp
0x1801b5307  jnz     short loc_1801B5310
0x1801b5309  mov     eax, 8000FFFFh
0x1801b530e  jmp     short loc_1801B5386
0x1801b5310  mov     dword ptr [rdi+8], 2
0x1801b5317  lea     rdx, [rsp+78h+FileInformation]; lpFileInformation
0x1801b531c  mov     rax, [rsi+18h]
0x1801b5320  xorps   xmm0, xmm0
0x1801b5323  mov     rcx, [rax+220h]
0x1801b532a  xor     eax, eax
0x1801b532c  mov     [rdi+10h], rcx
0x1801b5330  mov     dword ptr [rdi+30h], 20h ; ' '
0x1801b5337  mov     rcx, [rsi+18h]
0x1801b533b  movups  xmmword ptr [rsp+78h+FileInformation.dwFileAttributes], xmm0
0x1801b5340  mov     [rsp+78h+FileInformation.nFileIndexLow], eax
0x1801b5344  movups  xmmword ptr [rsp+78h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1801b5349  movups  xmmword ptr [rsp+78h+FileInformation.nFileSizeHigh], xmm0
0x1801b534e  mov     rcx, [rcx+218h]; hFile
0x1801b5355  call    cs:__imp_GetFileInformationByHandle
0x1801b535b  test    eax, eax
0x1801b535d  jz      short loc_1801B537A
0x1801b535f  mov     rax, qword ptr [rsp+78h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x1801b5364  mov     [rdi+18h], rax
0x1801b5368  mov     rax, qword ptr [rsp+78h+FileInformation.ftCreationTime.dwLowDateTime]
0x1801b536d  mov     [rdi+20h], rax
0x1801b5371  mov     rax, qword ptr [rsp+78h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x1801b5376  mov     [rdi+28h], rax
0x1801b537a  test    ebx, ebx
0x1801b537c  jz      short loc_1801B53A3
0x1801b537e  mov     r11, rbp
0x1801b5381  mov     [rdi], r11
0x1801b5384  xor     eax, eax
0x1801b5386  mov     rcx, [rsp+78h+var_20]
0x1801b538b  xor     rcx, rsp; StackCookie
0x1801b538e  call    __security_check_cookie
0x1801b5393  mov     rbx, [rsp+78h+arg_10]
0x1801b539b  add     rsp, 60h
0x1801b539f  pop     rdi
0x1801b53a0  pop     rsi
0x1801b53a1  pop     rbp
0x1801b53a2  retn
0x1801b53a3  mov     ecx, 208h; cb
0x1801b53a8  call    cs:__imp_CoTaskMemAlloc
0x1801b53ae  mov     r11, rax
0x1801b53b1  test    rax, rax
0x1801b53b4  jnz     short loc_1801B53BD
0x1801b53b6  mov     eax, 8007000Eh
0x1801b53bb  jmp     short loc_1801B5386
0x1801b53bd  mov     r8, [rsi+18h]
0x1801b53c1  add     r8, 10h; unsigned __int16 *
0x1801b53c5  mov     [rax], bp
0x1801b53c8  cmp     [r8], bp
0x1801b53cc  jnz     short loc_1801B53D5
0x1801b53ce  mov     ebx, 8000FFFFh
0x1801b53d3  jmp     short loc_1801B53E8
0x1801b53d5  mov     edx, 104h; unsigned __int64
0x1801b53da  mov     rcx, r11; unsigned __int16 *
0x1801b53dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801b53e2  mov     ebx, eax
0x1801b53e4  test    eax, eax
0x1801b53e6  jns     short loc_1801B5381
0x1801b53e8  mov     rcx, r11; pv
0x1801b53eb  call    cs:__imp_CoTaskMemFree
0x1801b53f1  mov     eax, ebx
0x1801b53f3  jmp     short loc_1801B5386
```
