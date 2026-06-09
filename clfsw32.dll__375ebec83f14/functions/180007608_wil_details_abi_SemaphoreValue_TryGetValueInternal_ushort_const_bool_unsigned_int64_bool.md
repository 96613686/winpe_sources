# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007608`
- end: `0x1800078b2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800037f4`
- `0x180003ba0`

## callees

- `0x180004fbc`
- `0x180006c88`
- `0x180006ca8`
- `0x18000710c`
- `0x180007608`
- `0x180007e10`
- `0x180014e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007800`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000775f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000775f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007794`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800077eb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000769c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000771d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000769c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000771d`

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
0x180007608  push    rbp
0x18000760a  push    rbx
0x18000760b  push    rsi
0x18000760c  push    rdi
0x18000760d  push    r14
0x18000760f  push    r15
0x180007611  lea     rbp, [rsp-158h]
0x180007619  sub     rsp, 258h
0x180007620  mov     rax, cs:__security_cookie
0x180007627  xor     rax, rsp
0x18000762a  mov     [rbp+180h+var_40], rax
0x180007631  xor     r15d, r15d
0x180007634  lea     rax, [rsp+280h+Name]
0x180007639  mov     [r8], r15
0x18000763c  mov     r14, r8
0x18000763f  mov     edx, 104h
0x180007644  mov     r9d, 7FFFFFFEh
0x18000764a  test    r9, r9
0x18000764d  jz      short loc_18000766E
0x18000764f  movzx   r8d, word ptr [rcx]
0x180007653  test    r8w, r8w
0x180007657  jz      short loc_18000766E
0x180007659  mov     [rax], r8w
0x18000765d  add     rcx, 2
0x180007661  add     rax, 2
0x180007665  dec     r9
0x180007668  sub     rdx, 1; unsigned __int64
0x18000766c  jnz     short loc_18000764A
0x18000766e  test    rdx, rdx
0x180007671  lea     rcx, [rax-2]
0x180007675  lea     r8, aP0; "_p0"
0x18000767c  cmovnz  rcx, rax
0x180007680  mov     [rcx], r15w
0x180007684  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007689  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000768e  mov     esi, 1F0003h
0x180007693  lea     r8, [rsp+280h+Name]; lpName
0x180007698  mov     ecx, esi; dwDesiredAccess
0x18000769a  xor     edx, edx; bInheritHandle
0x18000769c  call    cs:__imp_OpenSemaphoreW
0x1800076a3  nop     dword ptr [rax+rax+00h]
0x1800076a8  mov     rbx, rax
0x1800076ab  test    rax, rax
0x1800076ae  jz      loc_180007800
0x1800076b4  lea     rdx, [rsp+280h+var_25C]; int *
0x1800076b9  mov     [rsp+280h+var_25C], r15d
0x1800076be  mov     rcx, rax; hHandle
0x1800076c1  mov     [rsp+280h+var_260], r15d; int
0x1800076c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800076cb  mov     edi, eax
0x1800076cd  test    eax, eax
0x1800076cf  jns     short loc_180007703
0x1800076d1  mov     rcx, [rbp+188h]; this
0x1800076d8  mov     r9d, eax; char *
0x1800076db  mov     edx, 0D6h; void *
0x1800076e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800076e5  mov     rcx, rbx; hObject
0x1800076e8  call    cs:__imp_CloseHandle
0x1800076ef  nop     dword ptr [rax+rax+00h]
0x1800076f4  test    eax, eax
0x1800076f6  jz      loc_18000787C
0x1800076fc  mov     eax, edi
0x1800076fe  jmp     loc_180007826
0x180007703  lea     r8, asc_1800191F0; "h"
0x18000770a  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18000770f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007714  lea     r8, [rsp+280h+Name]; lpName
0x180007719  xor     edx, edx; bInheritHandle
0x18000771b  mov     ecx, esi; dwDesiredAccess
0x18000771d  call    cs:__imp_OpenSemaphoreW
0x180007724  nop     dword ptr [rax+rax+00h]
0x180007729  mov     rdi, rax
0x18000772c  test    rax, rax
0x18000772f  jz      loc_1800077D5
0x180007735  lea     rdx, [rsp+280h+var_260]; int *
0x18000773a  mov     rcx, rax; hHandle
0x18000773d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007742  mov     esi, eax
0x180007744  test    eax, eax
0x180007746  jns     short loc_180007791
0x180007748  mov     rcx, [rbp+188h]; this
0x18000774f  mov     r9d, eax; char *
0x180007752  mov     edx, 0DEh; void *
0x180007757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000775c  mov     rcx, rdi; hObject
0x18000775f  call    cs:__imp_CloseHandle
0x180007766  nop     dword ptr [rax+rax+00h]
0x18000776b  test    eax, eax
0x18000776d  jz      loc_18000788E
0x180007773  mov     rcx, rbx; hObject
0x180007776  call    cs:__imp_CloseHandle
0x18000777d  nop     dword ptr [rax+rax+00h]
0x180007782  test    eax, eax
0x180007784  jz      loc_1800078A0
0x18000778a  mov     eax, esi
0x18000778c  jmp     loc_180007826
0x180007791  mov     rcx, rdi; hObject
0x180007794  call    cs:__imp_CloseHandle
0x18000779b  nop     dword ptr [rax+rax+00h]
0x1800077a0  test    eax, eax
0x1800077a2  jz      loc_180007846
0x1800077a8  movsxd  rax, [rsp+280h+var_25C]
0x1800077ad  movsxd  rcx, [rsp+280h+var_260]
0x1800077b2  shl     rcx, 1Fh
0x1800077b6  or      rcx, rax
0x1800077b9  mov     [r14], rcx
0x1800077bc  mov     rcx, rbx; hObject
0x1800077bf  call    cs:__imp_CloseHandle
0x1800077c6  nop     dword ptr [rax+rax+00h]
0x1800077cb  test    eax, eax
0x1800077cd  jz      loc_180007858
0x1800077d3  jmp     short loc_180007811
0x1800077d5  mov     rcx, [rbp+188h]; this
0x1800077dc  mov     edx, 0DCh; void *
0x1800077e1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800077e6  mov     rcx, rbx; hObject
0x1800077e9  mov     edi, eax
0x1800077eb  call    cs:__imp_CloseHandle
0x1800077f2  nop     dword ptr [rax+rax+00h]
0x1800077f7  test    eax, eax
0x1800077f9  jz      short loc_18000786A
0x1800077fb  jmp     loc_1800076FC
0x180007800  call    cs:__imp_GetLastError
0x180007807  nop     dword ptr [rax+rax+00h]
0x18000780c  cmp     eax, 2
0x18000780f  jnz     short loc_180007815
0x180007811  xor     eax, eax
0x180007813  jmp     short loc_180007826
0x180007815  mov     rcx, [rbp+188h]; this
0x18000781c  mov     edx, 0D0h; void *
0x180007821  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007826  mov     rcx, [rbp+180h+var_40]
0x18000782d  xor     rcx, rsp; StackCookie
0x180007830  call    __security_check_cookie
0x180007835  add     rsp, 258h
0x18000783c  pop     r15
0x18000783e  pop     r14
0x180007840  pop     rdi
0x180007841  pop     rsi
0x180007842  pop     rbx
0x180007843  pop     rbp
0x180007844  retn
0x180007846  mov     rcx, [rbp+188h]; this
0x18000784d  mov     edx, 0A0Bh; void *
0x180007852  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007858  mov     rcx, [rbp+188h]; this
0x18000785f  mov     edx, 0A0Bh; void *
0x180007864  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000786a  mov     rcx, [rbp+188h]; this
0x180007871  mov     edx, 0A0Bh; void *
0x180007876  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000787c  mov     rcx, [rbp+188h]; this
0x180007883  mov     edx, 0A0Bh; void *
0x180007888  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000788e  mov     rcx, [rbp+188h]; this
0x180007895  mov     edx, 0A0Bh; void *
0x18000789a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800078a0  mov     rcx, [rbp+188h]; this
0x1800078a7  mov     edx, 0A0Bh; void *
0x1800078ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
