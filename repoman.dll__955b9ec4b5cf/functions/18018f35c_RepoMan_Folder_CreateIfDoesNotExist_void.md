# RepoMan::Folder::CreateIfDoesNotExist(void)

- ea: `0x18018f35c`
- end: `0x18018f531`
- name: `?CreateIfDoesNotExist@Folder@RepoMan@@QEAAXXZ`
- size: `469`
- prototype: `void __fastcall(LPCCH lpMultiByteStr)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a3460`
- `0x1800a6430`
- `0x1800be964`
- `0x1800bec80`
- `0x18018e8a4`
- `0x18018f35c`

## callees

- `0x180008574`
- `0x180008770`
- `0x180024748`
- `0x18002f940`
- `0x18018b53c`
- `0x18018cdf8`
- `0x18018f35c`
- `0x18018f7a4`
- `0x18019a840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018f483`
- `KERNEL32!GetLastError` at `0x18018f483`
- `KERNEL32!CreateDirectoryW` at `0x18018f479`
- `KERNEL32!CreateDirectoryW` at `0x18018f479`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f44d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f4f9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f44d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18018f4f9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f446`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f4f2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f446`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18018f4f2`

## string_xrefs

- `0x18018f51f`: `CreateDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RepoMan::Folder::CreateIfDoesNotExist(_QWORD *lpMultiByteStr)
{
  size_t last_of; // rax
  _QWORD *v3; // rdx
  void **v4; // rdx
  void *v5; // rcx
  const WCHAR *v6; // rcx
  DWORD LastError; // eax
  __int64 v8; // rdx
  void *v9; // rcx
  void *Block[2]; // [rsp+38h] [rbp-11h] BYREF
  __int128 v11; // [rsp+48h] [rbp-1h]
  LPCWSTR lpPathName[2]; // [rsp+58h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+68h] [rbp+1Fh]
  CHAR MultiByteStr[16]; // [rsp+78h] [rbp+2Fh] BYREF
  __int128 v15; // [rsp+88h] [rbp+3Fh]

  if ( !RepoMan::Folder::Exists((LPCCH)lpMultiByteStr) )
  {
    last_of = std::string::find_last_of(lpMultiByteStr, "\\");
    if ( last_of - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *(_OWORD *)Block = 0;
      v11 = 0;
      if ( lpMultiByteStr[2] < last_of )
        last_of = lpMultiByteStr[2];
      v3 = lpMultiByteStr;
      if ( lpMultiByteStr[3] > 0xFu )
        v3 = (_QWORD *)*lpMultiByteStr;
      std::string::_Construct<1,char const *>(Block, v3, last_of);
      *(_OWORD *)MultiByteStr = 0;
      v15 = 0;
      v4 = Block;
      if ( *((_QWORD *)&v11 + 1) > 0xFu )
        v4 = (void **)Block[0];
      std::string::_Construct<2,char const *>(MultiByteStr, v4, v11);
      if ( *((_QWORD *)&v11 + 1) > 0xFu )
      {
        v5 = Block[0];
        if ( (unsigned __int64)(*((_QWORD *)&v11 + 1) + 1LL) >= 0x1000 )
        {
          v5 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v5 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v5);
      }
      RepoMan::Folder::CreateIfDoesNotExist(MultiByteStr);
      RepoMan::utf8_to_wstring((LPWSTR)lpPathName, (LPCCH)lpMultiByteStr);
      v6 = (const WCHAR *)lpPathName;
      if ( si128.m128i_i64[1] > 7uLL )
        v6 = lpPathName[0];
      if ( !CreateDirectoryW(v6, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 183 )
          RepoMan::RaiseException<RepoMan::Win32Exception,unsigned long>(773, v8, "CreateDirectory", LastError);
      }
      std::wstring::_Tidy_deallocate(lpPathName);
      lpPathName[0] = (LPCWSTR)19937;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      if ( *((_QWORD *)&v15 + 1) > 0xFu )
      {
        v9 = *(void **)MultiByteStr;
        if ( (unsigned __int64)(*((_QWORD *)&v15 + 1) + 1LL) >= 0x1000 )
        {
          v9 = *(void **)(*(_QWORD *)MultiByteStr - 8LL);
          if ( (unsigned __int64)(*(_QWORD *)MultiByteStr - (_QWORD)v9 - 8LL) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v9);
      }
    }
  }
}

```

## disassembly

```asm
0x18018f35c  mov     [rsp-8+arg_8], rbx
0x18018f361  push    rbp
0x18018f362  lea     rbp, [rsp-57h]
0x18018f367  sub     rsp, 0A0h
0x18018f36e  mov     rax, cs:__security_cookie
0x18018f375  xor     rax, rsp
0x18018f378  mov     [rbp+57h+var_8], rax
0x18018f37c  mov     rbx, rcx
0x18018f37f  call    ?Exists@Folder@RepoMan@@QEBA_NXZ; RepoMan::Folder::Exists(void)
0x18018f384  test    al, al
0x18018f386  jnz     loc_18018F4FF
0x18018f38c  lea     rdx, asc_1801DE32C; "\\"
0x18018f393  mov     rcx, rbx
0x18018f396  call    ?find_last_of@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KQEBD_K@Z; std::string::find_last_of(char const * const,unsigned __int64)
0x18018f39b  lea     rcx, [rax-1]
0x18018f39f  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18018f3a3  ja      loc_18018F4FF
0x18018f3a9  xorps   xmm0, xmm0
0x18018f3ac  movups  xmmword ptr [rbp+57h+Block], xmm0
0x18018f3b0  xorps   xmm1, xmm1
0x18018f3b3  movdqu  [rbp+57h+var_58], xmm1
0x18018f3b8  cmp     [rbx+10h], rax
0x18018f3bc  cmovb   rax, [rbx+10h]
0x18018f3c1  mov     rdx, rbx
0x18018f3c4  cmp     qword ptr [rbx+18h], 0Fh
0x18018f3c9  jbe     short loc_18018F3CE
0x18018f3cb  mov     rdx, [rbx]
0x18018f3ce  mov     r8, rax
0x18018f3d1  lea     rcx, [rbp+57h+Block]
0x18018f3d5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18018f3da  nop
0x18018f3db  xorps   xmm0, xmm0
0x18018f3de  movups  xmmword ptr [rbp+57h+MultiByteStr], xmm0
0x18018f3e2  xorps   xmm1, xmm1
0x18018f3e5  movdqu  [rbp+57h+var_18], xmm1
0x18018f3ea  lea     rdx, [rbp+57h+Block]
0x18018f3ee  cmp     qword ptr [rbp+57h+var_58+8], 0Fh
0x18018f3f3  cmova   rdx, [rbp+57h+Block]
0x18018f3f8  mov     r8, qword ptr [rbp+57h+var_58]
0x18018f3fc  lea     rcx, [rbp+57h+MultiByteStr]
0x18018f400  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x18018f405  nop
0x18018f406  mov     rax, qword ptr [rbp+57h+var_58+8]
0x18018f40a  cmp     rax, 0Fh
0x18018f40e  jbe     short loc_18018F453
0x18018f410  mov     rcx, [rbp+57h+Block]; Block
0x18018f414  mov     rdx, rcx
0x18018f417  inc     rax
0x18018f41a  cmp     rax, 1000h
0x18018f420  jb      short loc_18018F44D
0x18018f422  mov     rcx, [rcx-8]
0x18018f426  sub     rdx, rcx
0x18018f429  lea     rax, [rdx-8]
0x18018f42d  cmp     rax, 1Fh
0x18018f431  jbe     short loc_18018F44D
0x18018f433  mov     [rsp+0A0h+Reserved], 0; Reserved
0x18018f43c  xor     r9d, r9d; LineNo
0x18018f43f  xor     r8d, r8d; FileName
0x18018f442  xor     edx, edx; FunctionName
0x18018f444  xor     ecx, ecx; Expression
0x18018f446  call    cs:__imp__invoke_watson
0x18018f44d  call    cs:__imp_free
0x18018f453  lea     rcx, [rbp+57h+MultiByteStr]; lpMultiByteStr
0x18018f457  call    ?CreateIfDoesNotExist@Folder@RepoMan@@QEAAXXZ; RepoMan::Folder::CreateIfDoesNotExist(void)
0x18018f45c  mov     rdx, rbx; lpMultiByteStr
0x18018f45f  lea     rcx, [rbp+57h+lpPathName]; lpWideCharStr
0x18018f463  call    ?utf8_to_wstring@RepoMan@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; RepoMan::utf8_to_wstring(std::string const &)
0x18018f468  nop
0x18018f469  lea     rcx, [rbp+57h+lpPathName]
0x18018f46d  cmp     [rbp+57h+var_30], 7
0x18018f472  cmova   rcx, [rbp+57h+lpPathName]; lpPathName
0x18018f477  xor     edx, edx; lpSecurityAttributes
0x18018f479  call    cs:__imp_CreateDirectoryW
0x18018f47f  test    eax, eax
0x18018f481  jnz     short loc_18018F494
0x18018f483  call    cs:__imp_GetLastError
0x18018f489  cmp     eax, 0B7h
0x18018f48e  jnz     loc_18018F51C
0x18018f494  lea     rcx, [rbp+57h+lpPathName]
0x18018f498  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18018f49d  mov     [rbp+57h+lpPathName], 4DE1h
0x18018f4a5  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18018f4ad  movdqu  xmmword ptr [rbp+1Fh], xmm0
0x18018f4b2  mov     rax, qword ptr [rbp+57h+var_18+8]
0x18018f4b6  cmp     rax, 0Fh
0x18018f4ba  jbe     short loc_18018F4FF
0x18018f4bc  mov     rcx, qword ptr [rbp+57h+MultiByteStr]; Block
0x18018f4c0  mov     rdx, rcx
0x18018f4c3  inc     rax
0x18018f4c6  cmp     rax, 1000h
0x18018f4cc  jb      short loc_18018F4F9
0x18018f4ce  mov     rcx, [rcx-8]
0x18018f4d2  sub     rdx, rcx
0x18018f4d5  lea     rax, [rdx-8]
0x18018f4d9  cmp     rax, 1Fh
0x18018f4dd  jbe     short loc_18018F4F9
0x18018f4df  mov     [rsp+0A0h+Reserved], 0; Reserved
0x18018f4e8  xor     r9d, r9d; LineNo
0x18018f4eb  xor     r8d, r8d; FileName
0x18018f4ee  xor     edx, edx; FunctionName
0x18018f4f0  xor     ecx, ecx; Expression
0x18018f4f2  call    cs:__imp__invoke_watson
0x18018f4f9  call    cs:__imp_free
0x18018f4ff  mov     rcx, [rbp+57h+var_8]
0x18018f503  xor     rcx, rsp; StackCookie
0x18018f506  call    __security_check_cookie
0x18018f50b  mov     rbx, [rsp+0A0h+arg_8]
0x18018f513  add     rsp, 0A0h
0x18018f51a  pop     rbp
0x18018f51b  retn
0x18018f51c  mov     r9d, eax
0x18018f51f  lea     r8, aCreatedirector; "CreateDirectory"
0x18018f526  mov     ecx, 305h
0x18018f52b  call    ??$RaiseException@VWin32Exception@RepoMan@@K@RepoMan@@YAXHQEBDPEBDKW4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Win32Exception,ulong>(int,char const * const,char const *,ulong,RepoMan::ILogger::Verbosity)
```
