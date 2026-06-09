# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000b9ec`
- end: `0x14000bca4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `696`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140004ce4`
- `0x140015fb4`

## callees

- `0x1400074c4`
- `0x14000b064`
- `0x14000b084`
- `0x14000b854`
- `0x14000b9ec`
- `0x14000bfd4`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ba80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bb08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000ba80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000bb08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bbf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbdd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bad3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bb86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000bbdd`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  unsigned __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v8; // rcx
  HANDLE v9; // rax
  void *v10; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // r8d
  const char *v24; // r9
  unsigned int v25; // r8d
  const char *v26; // r9
  unsigned int v27; // r8d
  const char *v28; // r9
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  int v35; // [rsp+20h] [rbp-E0h] BYREF
  int v36[3]; // [rsp+24h] [rbp-DCh] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v6;
  }
  while ( v6 );
  v8 = v4 - 1;
  if ( v6 )
    v8 = v4;
  *v8 = 0;
  StringCchCatW(Name, v6, L"_p0");
  v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v10 = v9;
  if ( !v9 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v33, v34);
    return 0;
  }
  v36[0] = 0;
  v35 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v36);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v35);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v35);
  v22 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
    *a3 = v36[0] | (unsigned __int64)((__int64)v35 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v21, v35);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v23, v24);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  return v22;
}

```

## disassembly

```asm
0x14000b9ec  push    rbp
0x14000b9ee  push    rbx
0x14000b9ef  push    rsi
0x14000b9f0  push    rdi
0x14000b9f1  push    r14
0x14000b9f3  push    r15
0x14000b9f5  lea     rbp, [rsp-158h]
0x14000b9fd  sub     rsp, 258h
0x14000ba04  mov     rax, cs:__security_cookie
0x14000ba0b  xor     rax, rsp
0x14000ba0e  mov     [rbp+180h+var_40], rax
0x14000ba15  xor     r15d, r15d
0x14000ba18  lea     rax, [rsp+280h+Name]
0x14000ba1d  mov     [r8], r15
0x14000ba20  mov     r14, r8
0x14000ba23  mov     edx, 104h
0x14000ba28  mov     r9d, 7FFFFFFEh
0x14000ba2e  test    r9, r9
0x14000ba31  jz      short loc_14000BA52
0x14000ba33  movzx   r8d, word ptr [rcx]
0x14000ba37  test    r8w, r8w
0x14000ba3b  jz      short loc_14000BA52
0x14000ba3d  mov     [rax], r8w
0x14000ba41  add     rcx, 2
0x14000ba45  add     rax, 2
0x14000ba49  dec     r9
0x14000ba4c  sub     rdx, 1; unsigned __int64
0x14000ba50  jnz     short loc_14000BA2E
0x14000ba52  test    rdx, rdx
0x14000ba55  lea     rcx, [rax-2]
0x14000ba59  lea     r8, aP0; "_p0"
0x14000ba60  cmovnz  rcx, rax
0x14000ba64  mov     [rcx], r15w
0x14000ba68  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000ba6d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000ba72  mov     esi, 1F0003h
0x14000ba77  lea     r8, [rsp+280h+Name]; lpName
0x14000ba7c  mov     ecx, esi; dwDesiredAccess
0x14000ba7e  xor     edx, edx; bInheritHandle
0x14000ba80  call    cs:__imp_OpenSemaphoreW
0x14000ba87  nop     dword ptr [rax+rax+00h]
0x14000ba8c  mov     rbx, rax
0x14000ba8f  test    rax, rax
0x14000ba92  jz      loc_14000BBF2
0x14000ba98  lea     rdx, [rsp+280h+var_25C]; int *
0x14000ba9d  mov     [rsp+280h+var_25C], r15d
0x14000baa2  mov     rcx, rax; hHandle
0x14000baa5  mov     [rsp+280h+var_260], r15d; int
0x14000baaa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000baaf  mov     edi, eax
0x14000bab1  test    eax, eax
0x14000bab3  jns     short loc_14000BAEE
0x14000bab5  mov     rcx, [rbp+188h]; this
0x14000babc  lea     r8, aWil; "wil"
0x14000bac3  mov     r9d, eax; char *
0x14000bac6  mov     edx, 0D6h; void *
0x14000bacb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bad0  mov     rcx, rbx; hObject
0x14000bad3  call    cs:__imp_CloseHandle
0x14000bada  nop     dword ptr [rax+rax+00h]
0x14000badf  test    eax, eax
0x14000bae1  jz      loc_14000BC6E
0x14000bae7  mov     eax, edi
0x14000bae9  jmp     loc_14000BC18
0x14000baee  lea     r8, asc_14001D850; "h"
0x14000baf5  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x14000bafa  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000baff  lea     r8, [rsp+280h+Name]; lpName
0x14000bb04  xor     edx, edx; bInheritHandle
0x14000bb06  mov     ecx, esi; dwDesiredAccess
0x14000bb08  call    cs:__imp_OpenSemaphoreW
0x14000bb0f  nop     dword ptr [rax+rax+00h]
0x14000bb14  mov     rdi, rax
0x14000bb17  test    rax, rax
0x14000bb1a  jz      loc_14000BBC7
0x14000bb20  lea     rdx, [rsp+280h+var_260]; int *
0x14000bb25  mov     rcx, rax; hHandle
0x14000bb28  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000bb2d  mov     esi, eax
0x14000bb2f  test    eax, eax
0x14000bb31  jns     short loc_14000BB83
0x14000bb33  mov     rcx, [rbp+188h]; this
0x14000bb3a  lea     r8, aWil; "wil"
0x14000bb41  mov     r9d, eax; char *
0x14000bb44  mov     edx, 0DEh; void *
0x14000bb49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb4e  mov     rcx, rdi; hObject
0x14000bb51  call    cs:__imp_CloseHandle
0x14000bb58  nop     dword ptr [rax+rax+00h]
0x14000bb5d  test    eax, eax
0x14000bb5f  jz      loc_14000BC80
0x14000bb65  mov     rcx, rbx; hObject
0x14000bb68  call    cs:__imp_CloseHandle
0x14000bb6f  nop     dword ptr [rax+rax+00h]
0x14000bb74  test    eax, eax
0x14000bb76  jz      loc_14000BC92
0x14000bb7c  mov     eax, esi
0x14000bb7e  jmp     loc_14000BC18
0x14000bb83  mov     rcx, rdi; hObject
0x14000bb86  call    cs:__imp_CloseHandle
0x14000bb8d  nop     dword ptr [rax+rax+00h]
0x14000bb92  test    eax, eax
0x14000bb94  jz      loc_14000BC38
0x14000bb9a  movsxd  rax, [rsp+280h+var_25C]
0x14000bb9f  movsxd  rcx, [rsp+280h+var_260]
0x14000bba4  shl     rcx, 1Fh
0x14000bba8  or      rcx, rax
0x14000bbab  mov     [r14], rcx
0x14000bbae  mov     rcx, rbx; hObject
0x14000bbb1  call    cs:__imp_CloseHandle
0x14000bbb8  nop     dword ptr [rax+rax+00h]
0x14000bbbd  test    eax, eax
0x14000bbbf  jz      loc_14000BC4A
0x14000bbc5  jmp     short loc_14000BC03
0x14000bbc7  mov     rcx, [rbp+188h]; this
0x14000bbce  mov     edx, 0DCh; void *
0x14000bbd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bbd8  mov     rcx, rbx; hObject
0x14000bbdb  mov     edi, eax
0x14000bbdd  call    cs:__imp_CloseHandle
0x14000bbe4  nop     dword ptr [rax+rax+00h]
0x14000bbe9  test    eax, eax
0x14000bbeb  jz      short loc_14000BC5C
0x14000bbed  jmp     loc_14000BAE7
0x14000bbf2  call    cs:__imp_GetLastError
0x14000bbf9  nop     dword ptr [rax+rax+00h]
0x14000bbfe  cmp     eax, 2
0x14000bc01  jnz     short loc_14000BC07
0x14000bc03  xor     eax, eax
0x14000bc05  jmp     short loc_14000BC18
0x14000bc07  mov     rcx, [rbp+188h]; this
0x14000bc0e  mov     edx, 0D0h; void *
0x14000bc13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000bc18  mov     rcx, [rbp+180h+var_40]
0x14000bc1f  xor     rcx, rsp; StackCookie
0x14000bc22  call    __security_check_cookie
0x14000bc27  add     rsp, 258h
0x14000bc2e  pop     r15
0x14000bc30  pop     r14
0x14000bc32  pop     rdi
0x14000bc33  pop     rsi
0x14000bc34  pop     rbx
0x14000bc35  pop     rbp
0x14000bc36  retn
0x14000bc38  mov     rcx, [rbp+188h]; this
0x14000bc3f  mov     edx, 0A0Bh; void *
0x14000bc44  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc4a  mov     rcx, [rbp+188h]; this
0x14000bc51  mov     edx, 0A0Bh; void *
0x14000bc56  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc5c  mov     rcx, [rbp+188h]; this
0x14000bc63  mov     edx, 0A0Bh; void *
0x14000bc68  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc6e  mov     rcx, [rbp+188h]; this
0x14000bc75  mov     edx, 0A0Bh; void *
0x14000bc7a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc80  mov     rcx, [rbp+188h]; this
0x14000bc87  mov     edx, 0A0Bh; void *
0x14000bc8c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000bc92  mov     rcx, [rbp+188h]; this
0x14000bc99  mov     edx, 0A0Bh; void *
0x14000bc9e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
