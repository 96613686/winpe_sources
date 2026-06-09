# util_ShowMessage(HINSTANCE__ *,uint,ushort *)

- ea: `0x140037a00`
- end: `0x140037c07`
- name: `?util_ShowMessage@@YAXPEAUHINSTANCE__@@IPEAG@Z`
- size: `519`
- prototype: `void __fastcall(HINSTANCE hInstance, UINT uID, LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140037980`
- `0x140037f60`

## callees

- `0x140001020`
- `0x1400020d0`
- `0x140003160`
- `0x14000fea8`
- `0x140012070`
- `0x140033ab0`
- `0x140037a00`
- `0x140039d7c`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x140037b38`
- `KERNEL32!lstrlenA` at `0x140037b38`
- `KERNEL32!WideCharToMultiByte` at `0x140037b27`
- `KERNEL32!WideCharToMultiByte` at `0x140037b27`
- `KERNEL32!WriteFile` at `0x140037b50`
- `KERNEL32!WriteFile` at `0x140037b50`
- `KERNEL32!GetStdHandle` at `0x140037a3f`
- `KERNEL32!GetStdHandle` at `0x140037a3f`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140037ae2`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x140037ae2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140037bcd`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140037bcd`
- `USER32!MessageBoxW` at `0x140037b9c`
- `USER32!MessageBoxW` at `0x140037b9c`
- `USER32!LoadStringW` at `0x140037b6c`
- `USER32!LoadStringW` at `0x140037b6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall util_ShowMessage(HINSTANCE hInstance, UINT uID, LPCWCH lpWideCharStr)
{
  _QWORD *v6; // rbx
  HANDLE StdHandle; // r15
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 cbMultiByte; // rsi
  unsigned __int64 v11; // rax
  void *v12; // rsp
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v14; // rax
  DWORD v15; // eax
  _QWORD *v16; // rdx
  void *v17; // rcx
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp+8h] BYREF
  WCHAR Buffer[256]; // [rsp+50h] [rbp+10h] BYREF

  v6 = 0;
  *(_QWORD *)MultiByteStr = 0;
  StdHandle = GetStdHandle(0xFFFFFFF5);
  if ( (unsigned int)util_FConsoleHandle(StdHandle) )
  {
    if ( lpWideCharStr )
    {
      v9 = -1;
      do
        ++v9;
      while ( lpWideCharStr[v9] );
      cbMultiByte = 2LL * ((int)v9 + 1);
      if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) <= 0xFFFFFFFF )
      {
        if ( (int)cbMultiByte <= 1024
          && (_mm_lfence(),
              ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte, v8)) )
        {
          v11 = (int)cbMultiByte + 15LL;
          if ( v11 < (int)cbMultiByte )
            v11 = 0xFFFFFFFFFFFFFF0LL;
          v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
          lpMultiByteStr = MultiByteStr;
        }
        else
        {
          if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
          {
            _mm_lfence();
            ATL::AtlThrowImpl(-2147024362);
          }
          v14 = malloc((int)cbMultiByte + 16LL);
          if ( v14 )
          {
            *v14 = 0;
            v6 = v14;
            lpMultiByteStr = (CHAR *)(v14 + 2);
          }
          else
          {
            lpMultiByteStr = 0;
          }
        }
        if ( lpMultiByteStr )
        {
          *lpMultiByteStr = 0;
          if ( WideCharToMultiByte(3u, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
          {
            v15 = lstrlenA(lpMultiByteStr);
            WriteFile(StdHandle, lpMultiByteStr, v15, NumberOfBytesWritten, 0);
          }
        }
      }
    }
  }
  else
  {
    Buffer[0] = 0;
    LoadStringW(hInstance, uID, Buffer, 256);
    *(_QWORD *)NumberOfBytesWritten = 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      NumberOfBytesWritten,
      lpWideCharStr);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(NumberOfBytesWritten);
    MessageBoxW(0, *(LPCWSTR *)NumberOfBytesWritten, Buffer, 0x10u);
    v16 = (_QWORD *)(*(_QWORD *)NumberOfBytesWritten - 24LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)NumberOfBytesWritten - 24LL + 16), 0xFFFFFFFF) <= 1 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v16 + 8LL))(*v16);
    }
  }
  while ( v6 )
  {
    v17 = v6;
    v6 = (_QWORD *)*v6;
    free(v17);
  }
}

```

## disassembly

```asm
0x140037a00  push    rbp
0x140037a02  push    rbx
0x140037a03  push    rsi
0x140037a04  push    rdi
0x140037a05  push    r12
0x140037a07  push    r14
0x140037a09  push    r15
0x140037a0b  sub     rsp, 260h
0x140037a12  lea     rbp, [rsp+40h]
0x140037a17  mov     rax, cs:__security_cookie
0x140037a1e  xor     rax, rbp
0x140037a21  mov     [rbp+250h+var_40], rax
0x140037a28  mov     r14, r8
0x140037a2b  mov     esi, edx
0x140037a2d  mov     rdi, rcx
0x140037a30  xor     r12d, r12d
0x140037a33  mov     ebx, r12d
0x140037a36  mov     qword ptr [rbp+250h+MultiByteStr], rbx
0x140037a3a  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140037a3f  call    cs:__imp_GetStdHandle
0x140037a45  mov     r15, rax
0x140037a48  mov     rcx, rax; void *
0x140037a4b  call    ?util_FConsoleHandle@@YAHPEAX@Z; util_FConsoleHandle(void *)
0x140037a50  test    eax, eax
0x140037a52  jz      loc_140037B58
0x140037a58  test    r14, r14
0x140037a5b  jz      loc_140037BC5
0x140037a61  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140037a65  inc     rcx
0x140037a68  cmp     [r14+rcx*2], r12w
0x140037a6d  jnz     short loc_140037A65
0x140037a6f  lea     eax, [rcx+1]
0x140037a72  cdqe
0x140037a74  lea     rsi, [rax+rax]
0x140037a78  mov     eax, 80000000h
0x140037a7d  add     rax, rsi
0x140037a80  mov     ecx, 0FFFFFFFFh
0x140037a85  cmp     rax, rcx
0x140037a88  ja      loc_140037BC5
0x140037a8e  movsxd  rdi, esi
0x140037a91  cmp     esi, 400h
0x140037a97  jg      short loc_140037ACE
0x140037a99  lfence
0x140037a9c  mov     rcx, rdi; this
0x140037a9f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x140037aa4  test    al, al
0x140037aa6  jz      short loc_140037ACE
0x140037aa8  lea     rax, [rdi+0Fh]
0x140037aac  cmp     rax, rdi
0x140037aaf  ja      short loc_140037ABB
0x140037ab1  mov     rax, 0FFFFFFFFFFFFFF0h
0x140037abb  and     rax, 0FFFFFFFFFFFFFFF0h
0x140037abf  call    _alloca_probe
0x140037ac4  sub     rsp, rax
0x140037ac7  lea     rdi, [rsp+290h+MultiByteStr]
0x140037acc  jmp     short loc_140037AFC
0x140037ace  mov     rax, rdi
0x140037ad1  not     rax
0x140037ad4  cmp     rax, 10h
0x140037ad8  jb      loc_140037BF9
0x140037ade  lea     rcx, [rdi+10h]; Size
0x140037ae2  call    cs:__imp_malloc
0x140037ae8  test    rax, rax
0x140037aeb  jnz     short loc_140037AF2
0x140037aed  mov     rdi, r12
0x140037af0  jmp     short loc_140037AFC
0x140037af2  mov     [rax], r12
0x140037af5  mov     rbx, rax
0x140037af8  lea     rdi, [rax+10h]
0x140037afc  test    rdi, rdi
0x140037aff  jz      loc_140037BC5
0x140037b05  mov     [rdi], r12b
0x140037b08  mov     [rsp+290h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x140037b0d  mov     [rsp+290h+lpDefaultChar], r12; lpDefaultChar
0x140037b12  mov     [rsp+290h+cbMultiByte], esi; cbMultiByte
0x140037b16  mov     [rsp+290h+lpMultiByteStr], rdi; lpMultiByteStr
0x140037b1b  or      r9d, 0FFFFFFFFh; cchWideChar
0x140037b1f  mov     r8, r14; lpWideCharStr
0x140037b22  xor     edx, edx; dwFlags
0x140037b24  lea     ecx, [rdx+3]; CodePage
0x140037b27  call    cs:__imp_WideCharToMultiByte
0x140037b2d  test    eax, eax
0x140037b2f  jz      loc_140037BC5
0x140037b35  mov     rcx, rdi; lpString
0x140037b38  call    cs:__imp_lstrlenA
0x140037b3e  mov     r8d, eax; nNumberOfBytesToWrite
0x140037b41  mov     [rsp+290h+lpMultiByteStr], r12; lpOverlapped
0x140037b46  lea     r9, [rbp+250h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140037b4a  mov     rdx, rdi; lpBuffer
0x140037b4d  mov     rcx, r15; hFile
0x140037b50  call    cs:__imp_WriteFile
0x140037b56  jmp     short loc_140037BC5
0x140037b58  mov     [rbp+250h+Buffer], r12w
0x140037b5d  mov     r9d, 100h; cchBufferMax
0x140037b63  lea     r8, [rbp+250h+Buffer]; lpBuffer
0x140037b67  mov     edx, esi; uID
0x140037b69  mov     rcx, rdi; hInstance
0x140037b6c  call    cs:__imp_LoadStringW
0x140037b72  mov     qword ptr [rbp+250h+NumberOfBytesWritten], r12
0x140037b76  mov     rdx, r14
0x140037b79  lea     rcx, [rbp+250h+NumberOfBytesWritten]
0x140037b7d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140037b82  nop
0x140037b83  lea     rcx, [rbp+250h+NumberOfBytesWritten]
0x140037b87  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x140037b8c  mov     r9d, 10h; uType
0x140037b92  lea     r8, [rbp+250h+Buffer]; lpCaption
0x140037b96  mov     rdx, qword ptr [rbp+250h+NumberOfBytesWritten]; lpText
0x140037b9a  xor     ecx, ecx; hWnd
0x140037b9c  call    cs:__imp_MessageBoxW
0x140037ba2  nop
0x140037ba3  mov     rdx, qword ptr [rbp+250h+NumberOfBytesWritten]
0x140037ba7  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140037bab  or      eax, 0FFFFFFFFh
0x140037bae  lock xadd [rdx+10h], eax
0x140037bb3  sub     eax, 1
0x140037bb6  jg      short loc_140037BC5
0x140037bb8  lfence
0x140037bbb  mov     rcx, [rdx]
0x140037bbe  mov     rax, [rcx]
0x140037bc1  call    qword ptr [rax+8]
0x140037bc4  nop
0x140037bc5  jmp     short loc_140037BD3
0x140037bc7  mov     rcx, rbx; Block
0x140037bca  mov     rbx, [rbx]
0x140037bcd  call    cs:__imp_free
0x140037bd3  test    rbx, rbx
0x140037bd6  jnz     short loc_140037BC7
0x140037bd8  mov     rcx, [rbp+250h+var_40]
0x140037bdf  xor     rcx, rbp; StackCookie
0x140037be2  call    __security_check_cookie
0x140037be7  lea     rsp, [rbp+220h]
0x140037bee  pop     r15
0x140037bf0  pop     r14
0x140037bf2  pop     r12
0x140037bf4  pop     rdi
0x140037bf5  pop     rsi
0x140037bf6  pop     rbx
0x140037bf7  pop     rbp
0x140037bf8  retn
0x140037bf9  lfence
0x140037bfc  mov     ecx, 80070216h; int
0x140037c01  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
