# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180012d7c`
- end: `0x180013014`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `664`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d7a8`
- `0x18000db78`

## callees

- `0x180008dc0`
- `0x18000f748`
- `0x180011cc4`
- `0x180011ce4`
- `0x180012734`
- `0x180012d7c`
- `0x180013708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012e13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012e95`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012e13`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180012e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ed8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012ee9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f01`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012f53`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned int LastError; // edi
  unsigned int v13; // r8d
  const char *v14; // r9
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rdi
  int v19; // eax
  unsigned int v20; // esi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  const char *v31; // r9
  int v32; // [rsp+20h] [rbp-E0h] BYREF
  int v33[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  if ( v5 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, 0x104u, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v31);
    return 0;
  }
  v33[0] = 0;
  v32 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v33);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v32);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18 = v16;
  if ( !v16 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return LastError;
  }
  v19 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v32);
  v20 = v19;
  if ( v19 >= 0 )
  {
    if ( !CloseHandle(v18) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
    *a3 = v33[0] | (unsigned __int64)((__int64)v32 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v19, v32);
  if ( !CloseHandle(v18) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v21, v22);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  return v20;
}

```

## disassembly

```asm
0x180012d7c  push    rbp
0x180012d7e  push    rbx
0x180012d7f  push    rsi
0x180012d80  push    rdi
0x180012d81  push    r14
0x180012d83  push    r15
0x180012d85  lea     rbp, [rsp-158h]
0x180012d8d  sub     rsp, 258h
0x180012d94  mov     rax, cs:__security_cookie
0x180012d9b  xor     rax, rsp
0x180012d9e  mov     [rbp+180h+var_40], rax
0x180012da5  xor     r15d, r15d
0x180012da8  lea     rax, [rsp+280h+Name]
0x180012dad  mov     esi, 104h
0x180012db2  mov     [r8], r15
0x180012db5  mov     edx, esi
0x180012db7  mov     r14, r8
0x180012dba  mov     r9d, 7FFFFFFEh
0x180012dc0  test    r9, r9
0x180012dc3  jz      short loc_180012DE4
0x180012dc5  movzx   r8d, word ptr [rcx]
0x180012dc9  test    r8w, r8w
0x180012dcd  jz      short loc_180012DE4
0x180012dcf  mov     [rax], r8w
0x180012dd3  add     rcx, 2
0x180012dd7  add     rax, 2
0x180012ddb  dec     r9
0x180012dde  sub     rdx, 1
0x180012de2  jnz     short loc_180012DC0
0x180012de4  test    rdx, rdx
0x180012de7  lea     rcx, [rax-2]
0x180012deb  lea     r8, aP0; "_p0"
0x180012df2  mov     rdx, rsi; unsigned __int64
0x180012df5  cmovnz  rcx, rax
0x180012df9  mov     [rcx], r15w
0x180012dfd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012e02  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e07  lea     r8, [rsp+280h+Name]; lpName
0x180012e0c  xor     edx, edx; bInheritHandle
0x180012e0e  mov     ecx, 1F0003h; dwDesiredAccess
0x180012e13  call    cs:__imp_OpenSemaphoreW
0x180012e19  mov     rbx, rax
0x180012e1c  test    rax, rax
0x180012e1f  jz      loc_180012F62
0x180012e25  lea     rdx, [rsp+280h+var_25C]; int *
0x180012e2a  mov     [rsp+280h+var_25C], r15d
0x180012e2f  mov     rcx, rax; hHandle
0x180012e32  mov     [rsp+280h+var_260], r15d; int
0x180012e37  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012e3c  mov     edi, eax
0x180012e3e  test    eax, eax
0x180012e40  jns     short loc_180012E75
0x180012e42  mov     rcx, [rbp+188h]; this
0x180012e49  lea     r8, aWil; "wil"
0x180012e50  mov     r9d, eax; char *
0x180012e53  mov     edx, 0D6h; void *
0x180012e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e5d  mov     rcx, rbx; hObject
0x180012e60  call    cs:__imp_CloseHandle
0x180012e66  test    eax, eax
0x180012e68  jz      loc_180012FDE
0x180012e6e  mov     eax, edi
0x180012e70  jmp     loc_180012F89
0x180012e75  lea     r8, asc_1801B4390; "h"
0x180012e7c  mov     rdx, rsi; unsigned __int64
0x180012e7f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180012e84  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180012e89  lea     r8, [rsp+280h+Name]; lpName
0x180012e8e  xor     edx, edx; bInheritHandle
0x180012e90  mov     ecx, 1F0003h; dwDesiredAccess
0x180012e95  call    cs:__imp_OpenSemaphoreW
0x180012e9b  mov     rdi, rax
0x180012e9e  test    rax, rax
0x180012ea1  jz      loc_180012F36
0x180012ea7  lea     rdx, [rsp+280h+var_260]; int *
0x180012eac  mov     rcx, rax; hHandle
0x180012eaf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180012eb4  mov     esi, eax
0x180012eb6  test    eax, eax
0x180012eb8  jns     short loc_180012EFE
0x180012eba  mov     rcx, [rbp+188h]; this
0x180012ec1  lea     r8, aWil; "wil"
0x180012ec8  mov     r9d, eax; char *
0x180012ecb  mov     edx, 0DEh; void *
0x180012ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ed5  mov     rcx, rdi; hObject
0x180012ed8  call    cs:__imp_CloseHandle
0x180012ede  test    eax, eax
0x180012ee0  jz      loc_180012FF0
0x180012ee6  mov     rcx, rbx; hObject
0x180012ee9  call    cs:__imp_CloseHandle
0x180012eef  test    eax, eax
0x180012ef1  jz      loc_180013002
0x180012ef7  mov     eax, esi
0x180012ef9  jmp     loc_180012F89
0x180012efe  mov     rcx, rdi; hObject
0x180012f01  call    cs:__imp_CloseHandle
0x180012f07  test    eax, eax
0x180012f09  jz      loc_180012FA8
0x180012f0f  movsxd  rax, [rsp+280h+var_25C]
0x180012f14  movsxd  rcx, [rsp+280h+var_260]
0x180012f19  shl     rcx, 1Fh
0x180012f1d  or      rcx, rax
0x180012f20  mov     [r14], rcx
0x180012f23  mov     rcx, rbx; hObject
0x180012f26  call    cs:__imp_CloseHandle
0x180012f2c  test    eax, eax
0x180012f2e  jz      loc_180012FBA
0x180012f34  jmp     short loc_180012F6D
0x180012f36  mov     rcx, [rbp+188h]; this
0x180012f3d  lea     r8, aWil; "wil"
0x180012f44  mov     edx, 0DCh; void *
0x180012f49  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012f4e  mov     rcx, rbx; hObject
0x180012f51  mov     edi, eax
0x180012f53  call    cs:__imp_CloseHandle
0x180012f59  test    eax, eax
0x180012f5b  jz      short loc_180012FCC
0x180012f5d  jmp     loc_180012E6E
0x180012f62  call    cs:__imp_GetLastError
0x180012f68  cmp     eax, 2
0x180012f6b  jnz     short loc_180012F71
0x180012f6d  xor     eax, eax
0x180012f6f  jmp     short loc_180012F89
0x180012f71  mov     rcx, [rbp+188h]; this
0x180012f78  lea     r8, aWil; "wil"
0x180012f7f  mov     edx, 0D0h; void *
0x180012f84  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012f89  mov     rcx, [rbp+180h+var_40]
0x180012f90  xor     rcx, rsp; StackCookie
0x180012f93  call    __security_check_cookie
0x180012f98  add     rsp, 258h
0x180012f9f  pop     r15
0x180012fa1  pop     r14
0x180012fa3  pop     rdi
0x180012fa4  pop     rsi
0x180012fa5  pop     rbx
0x180012fa6  pop     rbp
0x180012fa7  retn
0x180012fa8  mov     rcx, [rbp+188h]; this
0x180012faf  mov     edx, 0A0Bh; void *
0x180012fb4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012fba  mov     rcx, [rbp+188h]; this
0x180012fc1  mov     edx, 0A0Bh; void *
0x180012fc6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012fcc  mov     rcx, [rbp+188h]; this
0x180012fd3  mov     edx, 0A0Bh; void *
0x180012fd8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012fde  mov     rcx, [rbp+188h]; this
0x180012fe5  mov     edx, 0A0Bh; void *
0x180012fea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180012ff0  mov     rcx, [rbp+188h]; this
0x180012ff7  mov     edx, 0A0Bh; void *
0x180012ffc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180013002  mov     rcx, [rbp+188h]; this
0x180013009  mov     edx, 0A0Bh; void *
0x18001300e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
