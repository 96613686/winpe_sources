# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000af40`
- end: `0x18000b30a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `970`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000aa54`
- `0x18000aae0`

## callees

- `0x18000af40`
- `0x18000b310`
- `0x180017988`
- `0x1800179ac`
- `0x18002a3d0`
- `0x18002ed24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afe7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b051`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000afe7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b102`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b102`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b127`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b179`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1d1`

## string_xrefs

- `0x18000b18f`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b290`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b2aa`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b2c4`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b2de`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18000b2f8`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rdx
  __int64 v7; // r9
  WCHAR *v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  HANDLE v13; // rax
  void *v14; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v17; // rcx
  WCHAR *v18; // rax
  __int64 v19; // rdx
  HANDLE v20; // rax
  const char *v21; // r9
  void *v22; // rbx
  const char *v23; // r9
  const char *v25; // r9
  int v26; // eax
  unsigned int v27; // esi
  const char *v28; // r9
  const char *v29; // r9
  const char *v30; // r9
  const char *v31; // r9
  const char *v32; // r9
  const unsigned __int16 *v33; // r9
  __int64 v34; // rcx
  WCHAR *v35; // r8
  __int64 v36; // rax
  WCHAR *v37; // rcx
  WCHAR *v38; // rax
  const unsigned __int16 *v39; // rcx
  __int64 v40; // rsi
  WCHAR *v41; // rdx
  int v42; // [rsp+20h] [rbp-248h] BYREF
  int v43[3]; // [rsp+24h] [rbp-244h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v4 - 1;
  if ( v7 )
    v9 = v4;
  v10 = Name;
  *v9 = 0;
  v11 = 260;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v11;
  }
  while ( v11 );
  v12 = 260 - v11;
  if ( v11 )
  {
    v33 = L"_p0";
    v34 = 2147483646;
    v35 = &Name[v12];
    v36 = 260 - v12;
    if ( v12 != 260 )
    {
      do
      {
        if ( !v34 )
          break;
        if ( !*v33 )
          break;
        *v35++ = *v33++;
        --v34;
        --v36;
      }
      while ( v36 );
    }
    v37 = v35 - 1;
    if ( v36 )
      v37 = v35;
    *v37 = 0;
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v14 = v13;
  if ( !v13 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
    return 0;
  }
  v43[0] = 0;
  v42 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, v43);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v42);
    if ( !CloseHandle(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v30);
    return LastError;
  }
  v17 = 260;
  v18 = Name;
  do
  {
    if ( !*v18 )
      break;
    ++v18;
    --v17;
  }
  while ( v17 );
  v19 = 260 - v17;
  if ( v17 )
  {
    v38 = &Name[v19];
    v39 = L"h";
    v40 = 260 - v19;
    if ( 260 != v19 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v39 )
          break;
        *v38++ = *v39++;
        --v5;
        --v40;
      }
      while ( v40 );
    }
    v41 = v38 - 1;
    if ( v40 )
      v41 = v38;
    *v41 = 0;
  }
  v20 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22 = v20;
  if ( !v20 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v21);
    if ( !CloseHandle(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v23);
    return LastError;
  }
  v26 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v20, &v42);
  v27 = v26;
  if ( v26 >= 0 )
  {
    if ( !CloseHandle(v22) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v28);
    *a3 = v43[0] | (unsigned __int64)((__int64)v42 << 31);
    if ( !CloseHandle(v14) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v29);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v26, v42);
  if ( !CloseHandle(v22) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v31);
  if ( !CloseHandle(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v32);
  return v27;
}

```

## disassembly

```asm
0x18000af40  mov     [rsp+arg_8], rbp
0x18000af45  mov     [rsp+arg_18], rsi
0x18000af4a  push    rdi
0x18000af4b  push    r14
0x18000af4d  push    r15
0x18000af4f  sub     rsp, 250h
0x18000af56  mov     rax, cs:__security_cookie
0x18000af5d  xor     rax, rsp
0x18000af60  mov     [rsp+268h+var_28], rax
0x18000af68  xor     r15d, r15d
0x18000af6b  lea     rax, [rsp+268h+Name]
0x18000af70  mov     ebp, 7FFFFFFEh
0x18000af75  mov     [r8], r15
0x18000af78  mov     esi, 104h
0x18000af7d  mov     edx, ebp
0x18000af7f  mov     r9d, esi
0x18000af82  mov     r14, r8
0x18000af85  test    rdx, rdx
0x18000af88  jz      short loc_18000AF98
0x18000af8a  movzx   r8d, word ptr [rcx]
0x18000af8e  test    r8w, r8w
0x18000af92  jnz     loc_18000B13C
0x18000af98  lea     rcx, [rax-2]
0x18000af9c  test    r9, r9
0x18000af9f  cmovnz  rcx, rax
0x18000afa3  lea     rax, [rsp+268h+Name]
0x18000afa8  mov     [rcx], r15w
0x18000afac  mov     rcx, rsi
0x18000afaf  nop
0x18000afb0  cmp     [rax], r15w
0x18000afb4  jz      short loc_18000AFC0
0x18000afb6  add     rax, 2
0x18000afba  sub     rcx, 1
0x18000afbe  jnz     short loc_18000AFB0
0x18000afc0  mov     rdx, rsi
0x18000afc3  sub     rdx, rcx
0x18000afc6  test    rcx, rcx
0x18000afc9  cmovz   rdx, r15
0x18000afcd  jnz     loc_18000B1E6
0x18000afd3  lea     r8, [rsp+268h+Name]; lpName
0x18000afd8  mov     [rsp+268h+arg_0], rbx
0x18000afe0  xor     edx, edx; bInheritHandle
0x18000afe2  mov     ecx, 1F0003h; dwDesiredAccess
0x18000afe7  call    cs:__imp_OpenSemaphoreW
0x18000afed  mov     rdi, rax
0x18000aff0  test    rax, rax
0x18000aff3  jz      loc_18000B0C2
0x18000aff9  lea     rdx, [rsp+268h+var_244]; int *
0x18000affe  mov     [rsp+268h+var_244], r15d
0x18000b003  mov     rcx, rax; hHandle
0x18000b006  mov     [rsp+268h+var_248], r15d; int
0x18000b00b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b010  mov     ebx, eax
0x18000b012  test    eax, eax
0x18000b014  js      loc_18000B15A
0x18000b01a  mov     rcx, rsi
0x18000b01d  lea     rax, [rsp+268h+Name]
0x18000b022  cmp     [rax], r15w
0x18000b026  jz      short loc_18000B032
0x18000b028  add     rax, 2
0x18000b02c  sub     rcx, 1
0x18000b030  jnz     short loc_18000B022
0x18000b032  mov     rdx, rsi
0x18000b035  sub     rdx, rcx
0x18000b038  test    rcx, rcx
0x18000b03b  cmovz   rdx, r15
0x18000b03f  jnz     loc_18000B215
0x18000b045  lea     r8, [rsp+268h+Name]; lpName
0x18000b04a  xor     edx, edx; bInheritHandle
0x18000b04c  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b051  call    cs:__imp_OpenSemaphoreW
0x18000b057  mov     rbx, rax
0x18000b05a  test    rax, rax
0x18000b05d  jnz     loc_18000B0E8
0x18000b063  mov     rcx, [rsp+268h]; this
0x18000b06b  lea     r8, aWil; "wil"
0x18000b072  mov     edx, 0DCh; void *
0x18000b077  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b07c  mov     rcx, rdi; hObject
0x18000b07f  mov     ebx, eax
0x18000b081  call    cs:__imp_CloseHandle
0x18000b087  test    eax, eax
0x18000b089  jz      loc_18000B2F0
0x18000b08f  mov     eax, ebx
0x18000b091  mov     rbx, [rsp+268h+arg_0]
0x18000b099  mov     rcx, [rsp+268h+var_28]
0x18000b0a1  xor     rcx, rsp; StackCookie
0x18000b0a4  call    __security_check_cookie
0x18000b0a9  lea     r11, [rsp+268h+var_18]
0x18000b0b1  mov     rbp, [r11+28h]
0x18000b0b5  mov     rsi, [r11+38h]
0x18000b0b9  mov     rsp, r11
0x18000b0bc  pop     r15
0x18000b0be  pop     r14
0x18000b0c0  pop     rdi
0x18000b0c1  retn
0x18000b0c2  call    cs:__imp_GetLastError
0x18000b0c8  cmp     eax, 2
0x18000b0cb  jz      short loc_18000B135
0x18000b0cd  mov     rcx, [rsp+268h]; this
0x18000b0d5  lea     r8, aWil; "wil"
0x18000b0dc  mov     edx, 0D0h; void *
0x18000b0e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b0e6  jmp     short loc_18000B091
0x18000b0e8  lea     rdx, [rsp+268h+var_248]; int *
0x18000b0ed  mov     rcx, rbx; hHandle
0x18000b0f0  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b0f5  mov     esi, eax
0x18000b0f7  test    eax, eax
0x18000b0f9  js      loc_18000B1A1
0x18000b0ff  mov     rcx, rbx; hObject
0x18000b102  call    cs:__imp_CloseHandle
0x18000b108  test    eax, eax
0x18000b10a  jz      loc_18000B2BC
0x18000b110  movsxd  rax, [rsp+268h+var_244]
0x18000b115  movsxd  rcx, [rsp+268h+var_248]
0x18000b11a  shl     rcx, 1Fh
0x18000b11e  or      rcx, rax
0x18000b121  mov     [r14], rcx
0x18000b124  mov     rcx, rdi; hObject
0x18000b127  call    cs:__imp_CloseHandle
0x18000b12d  test    eax, eax
0x18000b12f  jz      loc_18000B2D6
0x18000b135  xor     eax, eax
0x18000b137  jmp     loc_18000B091
0x18000b13c  mov     [rax], r8w
0x18000b140  add     rcx, 2
0x18000b144  add     rax, 2
0x18000b148  dec     rdx
0x18000b14b  sub     r9, 1
0x18000b14f  jz      loc_18000AF98
0x18000b155  jmp     loc_18000AF85
0x18000b15a  mov     rcx, [rsp+268h]; this
0x18000b162  lea     r8, aWil; "wil"
0x18000b169  mov     r9d, ebx; char *
0x18000b16c  mov     edx, 0D6h; void *
0x18000b171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b176  mov     rcx, rdi; hObject
0x18000b179  call    cs:__imp_CloseHandle
0x18000b17f  test    eax, eax
0x18000b181  jnz     loc_18000B08F
0x18000b187  mov     rcx, [rsp+268h]; this
0x18000b18f  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b196  mov     edx, 0A0Bh; void *
0x18000b19b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b1a1  mov     rcx, [rsp+268h]; this
0x18000b1a9  lea     r8, aWil; "wil"
0x18000b1b0  mov     r9d, esi; char *
0x18000b1b3  mov     edx, 0DEh; void *
0x18000b1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b1bd  mov     rcx, rbx; hObject
0x18000b1c0  call    cs:__imp_CloseHandle
0x18000b1c6  test    eax, eax
0x18000b1c8  jz      loc_18000B288
0x18000b1ce  mov     rcx, rdi; hObject
0x18000b1d1  call    cs:__imp_CloseHandle
0x18000b1d7  test    eax, eax
0x18000b1d9  jz      loc_18000B2A2
0x18000b1df  mov     eax, esi
0x18000b1e1  jmp     loc_18000B091
0x18000b1e6  mov     rax, rsi
0x18000b1e9  lea     r8, [rsp+268h+Name]
0x18000b1ee  lea     r9, aP0; "_p0"
0x18000b1f5  mov     rcx, rbp
0x18000b1f8  lea     r8, [r8+rdx*2]
0x18000b1fc  sub     rax, rdx
0x18000b1ff  jnz     short loc_18000B240
0x18000b201  test    rax, rax
0x18000b204  lea     rcx, [r8-2]
0x18000b208  cmovnz  rcx, r8
0x18000b20c  mov     [rcx], r15w
0x18000b210  jmp     loc_18000AFD3
0x18000b215  lea     rax, [rsp+268h+Name]
0x18000b21a  lea     rax, [rax+rdx*2]
0x18000b21e  lea     rcx, asc_18008FC20; "h"
0x18000b225  sub     rsi, rdx
0x18000b228  jnz     short loc_18000B265
0x18000b22a  test    rsi, rsi
0x18000b22d  lea     rdx, [rax-2]
0x18000b231  cmovnz  rdx, rax
0x18000b235  mov     [rdx], r15w
0x18000b239  jmp     loc_18000B045
0x18000b240  test    rcx, rcx
0x18000b243  jz      short loc_18000B201
0x18000b245  movzx   edx, word ptr [r9]
0x18000b249  test    dx, dx
0x18000b24c  jz      short loc_18000B201
0x18000b24e  mov     [r8], dx
0x18000b252  add     r9, 2
0x18000b256  add     r8, 2
0x18000b25a  dec     rcx
0x18000b25d  sub     rax, 1
0x18000b261  jz      short loc_18000B201
0x18000b263  jmp     short loc_18000B240
0x18000b265  test    rbp, rbp
0x18000b268  jz      short loc_18000B22A
0x18000b26a  movzx   edx, word ptr [rcx]
0x18000b26d  test    dx, dx
0x18000b270  jz      short loc_18000B22A
0x18000b272  mov     [rax], dx
0x18000b275  add     rcx, 2
0x18000b279  add     rax, 2
0x18000b27d  dec     rbp
0x18000b280  sub     rsi, 1
0x18000b284  jz      short loc_18000B22A
0x18000b286  jmp     short loc_18000B265
0x18000b288  mov     rcx, [rsp+268h]; this
0x18000b290  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b297  mov     edx, 0A0Bh; void *
0x18000b29c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2a2  mov     rcx, [rsp+268h]; this
0x18000b2aa  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2b1  mov     edx, 0A0Bh; void *
0x18000b2b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2bc  mov     rcx, [rsp+268h]; this
0x18000b2c4  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2cb  mov     edx, 0A0Bh; void *
0x18000b2d0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2d6  mov     rcx, [rsp+268h]; this
0x18000b2de  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2e5  mov     edx, 0A0Bh; void *
0x18000b2ea  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000b2f0  mov     rcx, [rsp+268h]; this
0x18000b2f8  lea     r8, aOnecoreInterna_17; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b2ff  mov     edx, 0A0Bh; void *
0x18000b304  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
