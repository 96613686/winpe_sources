# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000aeb4`
- end: `0x18000b120`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008fc8`

## callees

- `0x180009dec`
- `0x18000ab10`
- `0x18000ab30`
- `0x18000ad78`
- `0x18000aeb4`
- `0x18000b214`
- `0x18000c3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b075`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af48`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afbd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af48`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b00a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000af8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000aff9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b00a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b066`

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
  unsigned int v13; // r8d
  unsigned int LastError; // edi
  unsigned int v15; // r8d
  const char *v16; // r9
  HANDLE v18; // rax
  unsigned int v19; // r8d
  const char *v20; // r9
  void *v21; // rdi
  int v22; // eax
  unsigned int v23; // r8d
  unsigned int v24; // esi
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
  unsigned int v35; // r8d
  const char *v36; // r9
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  int v38[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v35, v36);
    return 0;
  }
  v38[0] = 0;
  v37 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v38);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore, v37);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
    return LastError;
  }
  StringCchCatW(Name, v12, L"h");
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v18;
  if ( !v18 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v19, v20);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    return LastError;
  }
  v22 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v37);
  v24 = v22;
  if ( v22 >= 0 )
  {
    if ( !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
    *a3 = v38[0] | (unsigned __int64)((__int64)v37 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v23, (const char *)(unsigned int)v22, v37);
  if ( !CloseHandle(v21) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v27, v28);
  return v24;
}

```

## disassembly

```asm
0x18000aeb4  push    rbp
0x18000aeb6  push    rbx
0x18000aeb7  push    rsi
0x18000aeb8  push    rdi
0x18000aeb9  push    r14
0x18000aebb  push    r15
0x18000aebd  lea     rbp, [rsp-158h]
0x18000aec5  sub     rsp, 258h
0x18000aecc  mov     rax, cs:__security_cookie
0x18000aed3  xor     rax, rsp
0x18000aed6  mov     [rbp+180h+var_40], rax
0x18000aedd  xor     r15d, r15d
0x18000aee0  lea     rax, [rsp+280h+Name]
0x18000aee5  mov     [r8], r15
0x18000aee8  mov     r14, r8
0x18000aeeb  mov     edx, 104h
0x18000aef0  mov     r9d, 7FFFFFFEh
0x18000aef6  test    r9, r9
0x18000aef9  jz      short loc_18000AF1A
0x18000aefb  movzx   r8d, word ptr [rcx]
0x18000aeff  test    r8w, r8w
0x18000af03  jz      short loc_18000AF1A
0x18000af05  mov     [rax], r8w
0x18000af09  add     rcx, 2
0x18000af0d  add     rax, 2
0x18000af11  dec     r9
0x18000af14  sub     rdx, 1; unsigned __int64
0x18000af18  jnz     short loc_18000AEF6
0x18000af1a  test    rdx, rdx
0x18000af1d  lea     rcx, [rax-2]
0x18000af21  lea     r8, aP0; "_p0"
0x18000af28  cmovnz  rcx, rax
0x18000af2c  mov     [rcx], r15w
0x18000af30  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000af35  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000af3a  mov     esi, 1F0003h
0x18000af3f  lea     r8, [rsp+280h+Name]; lpName
0x18000af44  mov     ecx, esi; dwDesiredAccess
0x18000af46  xor     edx, edx; bInheritHandle
0x18000af48  call    cs:__imp_OpenSemaphoreW
0x18000af4e  mov     rbx, rax
0x18000af51  test    rax, rax
0x18000af54  jz      loc_18000B075
0x18000af5a  lea     rdx, [rsp+280h+var_25C]; int *
0x18000af5f  mov     [rsp+280h+var_25C], r15d
0x18000af64  mov     rcx, rax; hHandle
0x18000af67  mov     [rsp+280h+var_260], r15d; int
0x18000af6c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000af71  mov     edi, eax
0x18000af73  test    eax, eax
0x18000af75  jns     short loc_18000AFA3
0x18000af77  mov     rcx, [rbp+188h]; this
0x18000af7e  mov     r9d, eax; char *
0x18000af81  mov     edx, 0D6h; void *
0x18000af86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af8b  mov     rcx, rbx; hObject
0x18000af8e  call    cs:__imp_CloseHandle
0x18000af94  test    eax, eax
0x18000af96  jz      loc_18000B0EA
0x18000af9c  mov     eax, edi
0x18000af9e  jmp     loc_18000B095
0x18000afa3  lea     r8, asc_180013150; "h"
0x18000afaa  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000afaf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000afb4  lea     r8, [rsp+280h+Name]; lpName
0x18000afb9  xor     edx, edx; bInheritHandle
0x18000afbb  mov     ecx, esi; dwDesiredAccess
0x18000afbd  call    cs:__imp_OpenSemaphoreW
0x18000afc3  mov     rdi, rax
0x18000afc6  test    rax, rax
0x18000afc9  jz      loc_18000B050
0x18000afcf  lea     rdx, [rsp+280h+var_260]; int *
0x18000afd4  mov     rcx, rax; hHandle
0x18000afd7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000afdc  mov     esi, eax
0x18000afde  test    eax, eax
0x18000afe0  jns     short loc_18000B01C
0x18000afe2  mov     rcx, [rbp+188h]; this
0x18000afe9  mov     r9d, eax; char *
0x18000afec  mov     edx, 0DEh; void *
0x18000aff1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aff6  mov     rcx, rdi; hObject
0x18000aff9  call    cs:__imp_CloseHandle
0x18000afff  test    eax, eax
0x18000b001  jz      loc_18000B0FC
0x18000b007  mov     rcx, rbx; hObject
0x18000b00a  call    cs:__imp_CloseHandle
0x18000b010  test    eax, eax
0x18000b012  jz      loc_18000B10E
0x18000b018  mov     eax, esi
0x18000b01a  jmp     short loc_18000B095
0x18000b01c  mov     rcx, rdi; hObject
0x18000b01f  call    cs:__imp_CloseHandle
0x18000b025  test    eax, eax
0x18000b027  jz      loc_18000B0B4
0x18000b02d  movsxd  rax, [rsp+280h+var_25C]
0x18000b032  movsxd  rcx, [rsp+280h+var_260]
0x18000b037  shl     rcx, 1Fh
0x18000b03b  or      rcx, rax
0x18000b03e  mov     [r14], rcx
0x18000b041  mov     rcx, rbx; hObject
0x18000b044  call    cs:__imp_CloseHandle
0x18000b04a  test    eax, eax
0x18000b04c  jz      short loc_18000B0C6
0x18000b04e  jmp     short loc_18000B080
0x18000b050  mov     rcx, [rbp+188h]; this
0x18000b057  mov     edx, 0DCh; void *
0x18000b05c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b061  mov     rcx, rbx; hObject
0x18000b064  mov     edi, eax
0x18000b066  call    cs:__imp_CloseHandle
0x18000b06c  test    eax, eax
0x18000b06e  jz      short loc_18000B0D8
0x18000b070  jmp     loc_18000AF9C
0x18000b075  call    cs:__imp_GetLastError
0x18000b07b  cmp     eax, 2
0x18000b07e  jnz     short loc_18000B084
0x18000b080  xor     eax, eax
0x18000b082  jmp     short loc_18000B095
0x18000b084  mov     rcx, [rbp+188h]; this
0x18000b08b  mov     edx, 0D0h; void *
0x18000b090  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b095  mov     rcx, [rbp+180h+var_40]
0x18000b09c  xor     rcx, rsp; StackCookie
0x18000b09f  call    __security_check_cookie
0x18000b0a4  add     rsp, 258h
0x18000b0ab  pop     r15
0x18000b0ad  pop     r14
0x18000b0af  pop     rdi
0x18000b0b0  pop     rsi
0x18000b0b1  pop     rbx
0x18000b0b2  pop     rbp
0x18000b0b3  retn
0x18000b0b4  mov     rcx, [rbp+188h]; this
0x18000b0bb  mov     edx, 0A0Bh; void *
0x18000b0c0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0c6  mov     rcx, [rbp+188h]; this
0x18000b0cd  mov     edx, 0A0Bh; void *
0x18000b0d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0d8  mov     rcx, [rbp+188h]; this
0x18000b0df  mov     edx, 0A0Bh; void *
0x18000b0e4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0ea  mov     rcx, [rbp+188h]; this
0x18000b0f1  mov     edx, 0A0Bh; void *
0x18000b0f6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b0fc  mov     rcx, [rbp+188h]; this
0x18000b103  mov     edx, 0A0Bh; void *
0x18000b108  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b10e  mov     rcx, [rbp+188h]; this
0x18000b115  mov     edx, 0A0Bh; void *
0x18000b11a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
