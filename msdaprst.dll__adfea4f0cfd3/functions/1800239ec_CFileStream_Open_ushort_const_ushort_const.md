# CFileStream::Open(ushort const *,ushort const *)

- ea: `0x1800239ec`
- end: `0x180023aeb`
- name: `?Open@CFileStream@@QEAAJPEBG0@Z`
- size: `255`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022240`

## callees

- `0x1800158e0`
- `0x1800164dc`
- `0x1800218c8`
- `0x1800239ec`

## import_xrefs

- `msvcrt!_wfsopen` at `0x180023a30`
- `msvcrt!_wfsopen` at `0x180023a30`
- `msvcrt!_get_osfhandle` at `0x180023a86`
- `msvcrt!_get_osfhandle` at `0x180023a86`
- `msvcrt!_fileno` at `0x180023a78`
- `msvcrt!_fileno` at `0x180023a78`
- `KERNEL32!GetFileType` at `0x180023a9b`
- `KERNEL32!GetFileType` at `0x180023a9b`
- `KERNEL32!GetLastError` at `0x180023a45`
- `KERNEL32!GetLastError` at `0x180023a45`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180023a03`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180023a03`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileStream::Open(CFileStream *this, OLECHAR *psz, const unsigned __int16 *a3)
{
  FILE *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // eax
  void *osfhandle; // rax
  _BYTE v11[8]; // [rsp+20h] [rbp-28h] BYREF
  IErrorInfo *pperrinfo; // [rsp+28h] [rbp-20h] BYREF
  int v13; // [rsp+30h] [rbp-18h]
  __int64 v14; // [rsp+38h] [rbp-10h]

  GetErrorInfo(0, &pperrinfo);
  v13 = 0;
  v14 = 0;
  v5 = _wfsopen(psz, L"rb", 32);
  *((_QWORD *)this + 3) = v5;
  if ( v5 )
  {
    v8 = _fileno(v5);
    osfhandle = (void *)_get_osfhandle(v8);
    if ( osfhandle != (void *)-1LL && GetFileType(osfhandle) == 1 )
    {
      v7 = 0;
      goto LABEL_13;
    }
    CFileStream::Close(this);
LABEL_12:
    v7 = -2147287038;
    CPersistErrorCache::AddInternalError((CPersistErrorCache *)v11, -2147287038, psz, 0x82u);
    goto LABEL_13;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 )
  {
    if ( v7 != -2147024894 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v7 = -2147467259;
LABEL_13:
  CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v11);
  return v7;
}

```

## disassembly

```asm
0x1800239ec  mov     [rsp+arg_0], rbx
0x1800239f1  push    rdi
0x1800239f2  sub     rsp, 40h
0x1800239f6  mov     rdi, rdx
0x1800239f9  mov     rbx, rcx
0x1800239fc  lea     rdx, [rsp+48h+pperrinfo]; pperrinfo
0x180023a01  xor     ecx, ecx; dwReserved
0x180023a03  call    cs:__imp_GetErrorInfo
0x180023a0a  nop     dword ptr [rax+rax+00h]
0x180023a0f  mov     [rsp+48h+var_18], 0
0x180023a17  mov     [rsp+48h+var_10], 0
0x180023a20  mov     r8d, 20h ; ' '; ShFlag
0x180023a26  lea     rdx, aRb; "rb"
0x180023a2d  mov     rcx, rdi; FileName
0x180023a30  call    cs:__imp__wfsopen
0x180023a37  nop     dword ptr [rax+rax+00h]
0x180023a3c  mov     [rbx+18h], rax
0x180023a40  test    rax, rax
0x180023a43  jnz     short loc_180023A75
0x180023a45  call    cs:__imp_GetLastError
0x180023a4c  nop     dword ptr [rax+rax+00h]
0x180023a51  mov     ebx, eax
0x180023a53  test    eax, eax
0x180023a55  jle     short loc_180023A60
0x180023a57  movzx   ebx, ax
0x180023a5a  or      ebx, 80070000h
0x180023a60  test    ebx, ebx
0x180023a62  jnz     short loc_180023A6B
0x180023a64  mov     ebx, 80004005h
0x180023a69  jmp     short loc_180023AD3
0x180023a6b  cmp     ebx, 80070002h
0x180023a71  jz      short loc_180023AB8
0x180023a73  jmp     short loc_180023AD3
0x180023a75  mov     rcx, rax; Stream
0x180023a78  call    cs:__imp__fileno
0x180023a7f  nop     dword ptr [rax+rax+00h]
0x180023a84  mov     ecx, eax; FileHandle
0x180023a86  call    cs:__imp__get_osfhandle
0x180023a8d  nop     dword ptr [rax+rax+00h]
0x180023a92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023a96  jz      short loc_180023AB0
0x180023a98  mov     rcx, rax; hFile
0x180023a9b  call    cs:__imp_GetFileType
0x180023aa2  nop     dword ptr [rax+rax+00h]
0x180023aa7  cmp     eax, 1
0x180023aaa  jnz     short loc_180023AB0
0x180023aac  xor     ebx, ebx
0x180023aae  jmp     short loc_180023AD3
0x180023ab0  mov     rcx, rbx; this
0x180023ab3  call    ?Close@CFileStream@@QEAAXXZ; CFileStream::Close(void)
0x180023ab8  mov     ebx, 80030002h
0x180023abd  mov     r9d, 82h; unsigned int
0x180023ac3  mov     r8, rdi; psz
0x180023ac6  mov     edx, ebx; int
0x180023ac8  lea     rcx, [rsp+48h+var_28]; this
0x180023acd  call    ?AddInternalError@CPersistErrorCache@@QEAAXJPEBGK@Z; CPersistErrorCache::AddInternalError(long,ushort const *,ulong)
0x180023ad2  nop
0x180023ad3  lea     rcx, [rsp+48h+var_28]; this
0x180023ad8  call    ??1CPersistErrorCache@@QEAA@XZ; CPersistErrorCache::~CPersistErrorCache(void)
0x180023add  mov     eax, ebx
0x180023adf  mov     rbx, [rsp+48h+arg_0]
0x180023ae4  add     rsp, 40h
0x180023ae8  pop     rdi
0x180023ae9  retn
```
