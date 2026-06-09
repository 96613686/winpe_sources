# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007048`
- end: `0x1800072b4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `620`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180003114`
- `0x1800034b8`

## callees

- `0x1800015d0`
- `0x180004b10`
- `0x1800067c0`
- `0x1800067e0`
- `0x180006bfc`
- `0x180007048`
- `0x18000783c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007151`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800070dc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007151`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000718d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000719e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007122`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000718d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000719e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800071fa`

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
0x180007048  push    rbp
0x18000704a  push    rbx
0x18000704b  push    rsi
0x18000704c  push    rdi
0x18000704d  push    r14
0x18000704f  push    r15
0x180007051  lea     rbp, [rsp-158h]
0x180007059  sub     rsp, 258h
0x180007060  mov     rax, cs:__security_cookie
0x180007067  xor     rax, rsp
0x18000706a  mov     [rbp+180h+var_40], rax
0x180007071  xor     r15d, r15d
0x180007074  lea     rax, [rsp+280h+Name]
0x180007079  mov     [r8], r15
0x18000707c  mov     r14, r8
0x18000707f  mov     edx, 104h
0x180007084  mov     r9d, 7FFFFFFEh
0x18000708a  test    r9, r9
0x18000708d  jz      short loc_1800070AE
0x18000708f  movzx   r8d, word ptr [rcx]
0x180007093  test    r8w, r8w
0x180007097  jz      short loc_1800070AE
0x180007099  mov     [rax], r8w
0x18000709d  add     rcx, 2
0x1800070a1  add     rax, 2
0x1800070a5  dec     r9
0x1800070a8  sub     rdx, 1; unsigned __int64
0x1800070ac  jnz     short loc_18000708A
0x1800070ae  test    rdx, rdx
0x1800070b1  lea     rcx, [rax-2]
0x1800070b5  lea     r8, aP0; "_p0"
0x1800070bc  cmovnz  rcx, rax
0x1800070c0  mov     [rcx], r15w
0x1800070c4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800070c9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070ce  mov     esi, 1F0003h
0x1800070d3  lea     r8, [rsp+280h+Name]; lpName
0x1800070d8  mov     ecx, esi; dwDesiredAccess
0x1800070da  xor     edx, edx; bInheritHandle
0x1800070dc  call    cs:__imp_OpenSemaphoreW
0x1800070e2  mov     rbx, rax
0x1800070e5  test    rax, rax
0x1800070e8  jz      loc_180007209
0x1800070ee  lea     rdx, [rsp+280h+var_25C]; int *
0x1800070f3  mov     [rsp+280h+var_25C], r15d
0x1800070f8  mov     rcx, rax; hHandle
0x1800070fb  mov     [rsp+280h+var_260], r15d; int
0x180007100  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007105  mov     edi, eax
0x180007107  test    eax, eax
0x180007109  jns     short loc_180007137
0x18000710b  mov     rcx, [rbp+188h]; this
0x180007112  mov     r9d, eax; char *
0x180007115  mov     edx, 0D6h; void *
0x18000711a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000711f  mov     rcx, rbx; hObject
0x180007122  call    cs:__imp_CloseHandle
0x180007128  test    eax, eax
0x18000712a  jz      loc_18000727E
0x180007130  mov     eax, edi
0x180007132  jmp     loc_180007229
0x180007137  lea     r8, asc_180011FC0; "h"
0x18000713e  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007143  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007148  lea     r8, [rsp+280h+Name]; lpName
0x18000714d  xor     edx, edx; bInheritHandle
0x18000714f  mov     ecx, esi; dwDesiredAccess
0x180007151  call    cs:__imp_OpenSemaphoreW
0x180007157  mov     rdi, rax
0x18000715a  test    rax, rax
0x18000715d  jz      loc_1800071E4
0x180007163  lea     rdx, [rsp+280h+var_260]; int *
0x180007168  mov     rcx, rax; hHandle
0x18000716b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007170  mov     esi, eax
0x180007172  test    eax, eax
0x180007174  jns     short loc_1800071B0
0x180007176  mov     rcx, [rbp+188h]; this
0x18000717d  mov     r9d, eax; char *
0x180007180  mov     edx, 0DEh; void *
0x180007185  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000718a  mov     rcx, rdi; hObject
0x18000718d  call    cs:__imp_CloseHandle
0x180007193  test    eax, eax
0x180007195  jz      loc_180007290
0x18000719b  mov     rcx, rbx; hObject
0x18000719e  call    cs:__imp_CloseHandle
0x1800071a4  test    eax, eax
0x1800071a6  jz      loc_1800072A2
0x1800071ac  mov     eax, esi
0x1800071ae  jmp     short loc_180007229
0x1800071b0  mov     rcx, rdi; hObject
0x1800071b3  call    cs:__imp_CloseHandle
0x1800071b9  test    eax, eax
0x1800071bb  jz      loc_180007248
0x1800071c1  movsxd  rax, [rsp+280h+var_25C]
0x1800071c6  movsxd  rcx, [rsp+280h+var_260]
0x1800071cb  shl     rcx, 1Fh
0x1800071cf  or      rcx, rax
0x1800071d2  mov     [r14], rcx
0x1800071d5  mov     rcx, rbx; hObject
0x1800071d8  call    cs:__imp_CloseHandle
0x1800071de  test    eax, eax
0x1800071e0  jz      short loc_18000725A
0x1800071e2  jmp     short loc_180007214
0x1800071e4  mov     rcx, [rbp+188h]; this
0x1800071eb  mov     edx, 0DCh; void *
0x1800071f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800071f5  mov     rcx, rbx; hObject
0x1800071f8  mov     edi, eax
0x1800071fa  call    cs:__imp_CloseHandle
0x180007200  test    eax, eax
0x180007202  jz      short loc_18000726C
0x180007204  jmp     loc_180007130
0x180007209  call    cs:__imp_GetLastError
0x18000720f  cmp     eax, 2
0x180007212  jnz     short loc_180007218
0x180007214  xor     eax, eax
0x180007216  jmp     short loc_180007229
0x180007218  mov     rcx, [rbp+188h]; this
0x18000721f  mov     edx, 0D0h; void *
0x180007224  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007229  mov     rcx, [rbp+180h+var_40]
0x180007230  xor     rcx, rsp; StackCookie
0x180007233  call    __security_check_cookie
0x180007238  add     rsp, 258h
0x18000723f  pop     r15
0x180007241  pop     r14
0x180007243  pop     rdi
0x180007244  pop     rsi
0x180007245  pop     rbx
0x180007246  pop     rbp
0x180007247  retn
0x180007248  mov     rcx, [rbp+188h]; this
0x18000724f  mov     edx, 0A0Bh; void *
0x180007254  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000725a  mov     rcx, [rbp+188h]; this
0x180007261  mov     edx, 0A0Bh; void *
0x180007266  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000726c  mov     rcx, [rbp+188h]; this
0x180007273  mov     edx, 0A0Bh; void *
0x180007278  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000727e  mov     rcx, [rbp+188h]; this
0x180007285  mov     edx, 0A0Bh; void *
0x18000728a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007290  mov     rcx, [rbp+188h]; this
0x180007297  mov     edx, 0A0Bh; void *
0x18000729c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800072a2  mov     rcx, [rbp+188h]; this
0x1800072a9  mov     edx, 0A0Bh; void *
0x1800072ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
