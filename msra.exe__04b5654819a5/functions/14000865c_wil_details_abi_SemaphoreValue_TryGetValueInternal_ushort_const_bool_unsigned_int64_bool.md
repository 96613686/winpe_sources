# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000865c`
- end: `0x14000890f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `691`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140003d74`
- `0x140004120`

## callees

- `0x140005590`
- `0x1400076c4`
- `0x1400076e4`
- `0x140007fc4`
- `0x14000865c`
- `0x140009040`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000873f`
- `KERNEL32!CloseHandle` at `0x1400087bc`
- `KERNEL32!CloseHandle` at `0x1400087d3`
- `KERNEL32!CloseHandle` at `0x1400087f1`
- `KERNEL32!CloseHandle` at `0x14000881c`
- `KERNEL32!CloseHandle` at `0x140008848`
- `KERNEL32!CloseHandle` at `0x14000873f`
- `KERNEL32!CloseHandle` at `0x1400087bc`
- `KERNEL32!CloseHandle` at `0x1400087d3`
- `KERNEL32!CloseHandle` at `0x1400087f1`
- `KERNEL32!CloseHandle` at `0x14000881c`
- `KERNEL32!CloseHandle` at `0x140008848`
- `KERNEL32!OpenSemaphoreW` at `0x1400086f3`
- `KERNEL32!OpenSemaphoreW` at `0x14000877a`
- `KERNEL32!OpenSemaphoreW` at `0x1400086f3`
- `KERNEL32!OpenSemaphoreW` at `0x14000877a`
- `KERNEL32!GetLastError` at `0x14000885d`
- `KERNEL32!GetLastError` at `0x14000885d`

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
  unsigned int v12; // r8d
  unsigned int LastError; // edi
  unsigned int v14; // r8d
  const char *v15; // r9
  HANDLE v17; // rax
  unsigned int v18; // r8d
  const char *v19; // r9
  void *v20; // rdi
  int v21; // eax
  unsigned int v22; // r8d
  unsigned int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  unsigned int v28; // r8d
  const char *v29; // r9
  unsigned int v30; // r8d
  const char *v31; // r9
  unsigned int v32; // r8d
  const char *v33; // r9
  unsigned int v34; // r8d
  const char *v35; // r9
  int v36; // [rsp+20h] [rbp-E0h] BYREF
  int v37[3]; // [rsp+24h] [rbp-DCh] BYREF
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
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v34, v35);
    return 0;
  }
  v37[0] = 0;
  v36 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, v37);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v36);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    return LastError;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v17 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v17;
  if ( !v17 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v18, v19);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v32, v33);
    return LastError;
  }
  v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v17, &v36);
  v23 = v21;
  if ( v21 >= 0 )
  {
    if ( !CloseHandle(v20) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v28, v29);
    *a3 = v37[0] | (unsigned __int64)((__int64)v36 << 31);
    if ( !CloseHandle(v10) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v30, v31);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v22, (const char *)(unsigned int)v21, v36);
  if ( !CloseHandle(v20) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  if ( !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  return v23;
}

```

## disassembly

```asm
0x14000865c  push    rbp
0x14000865e  push    rbx
0x14000865f  push    rsi
0x140008660  push    rdi
0x140008661  push    r14
0x140008663  push    r15
0x140008665  lea     rbp, [rsp-158h]
0x14000866d  sub     rsp, 258h
0x140008674  mov     rax, cs:__security_cookie
0x14000867b  xor     rax, rsp
0x14000867e  mov     [rbp+180h+var_40], rax
0x140008685  xor     r15d, r15d
0x140008688  lea     rax, [rsp+280h+Name]
0x14000868d  mov     esi, 104h
0x140008692  mov     [r8], r15
0x140008695  mov     edx, esi
0x140008697  mov     r14, r8
0x14000869a  mov     r9d, 7FFFFFFEh
0x1400086a0  test    r9, r9
0x1400086a3  jz      short loc_1400086C4
0x1400086a5  movzx   r8d, word ptr [rcx]
0x1400086a9  test    r8w, r8w
0x1400086ad  jz      short loc_1400086C4
0x1400086af  mov     [rax], r8w
0x1400086b3  add     rcx, 2
0x1400086b7  add     rax, 2
0x1400086bb  dec     r9
0x1400086be  sub     rdx, 1
0x1400086c2  jnz     short loc_1400086A0
0x1400086c4  test    rdx, rdx
0x1400086c7  lea     rcx, [rax-2]
0x1400086cb  lea     r8, aP0; "_p0"
0x1400086d2  mov     rdx, rsi; unsigned __int64
0x1400086d5  cmovnz  rcx, rax
0x1400086d9  mov     [rcx], r15w
0x1400086dd  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1400086e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400086e7  lea     r8, [rsp+280h+Name]; lpName
0x1400086ec  xor     edx, edx; bInheritHandle
0x1400086ee  mov     ecx, 1F0003h; dwDesiredAccess
0x1400086f3  call    cs:__imp_OpenSemaphoreW
0x1400086fa  nop     dword ptr [rax+rax+00h]
0x1400086ff  mov     rbx, rax
0x140008702  test    rax, rax
0x140008705  jz      loc_14000885D
0x14000870b  lea     rdx, [rsp+280h+var_25C]; int *
0x140008710  mov     [rsp+280h+var_25C], r15d
0x140008715  mov     rcx, rax; hHandle
0x140008718  mov     [rsp+280h+var_260], r15d; int
0x14000871d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008722  mov     edi, eax
0x140008724  test    eax, eax
0x140008726  jns     short loc_14000875A
0x140008728  mov     rcx, [rbp+188h]; this
0x14000872f  mov     r9d, eax; char *
0x140008732  mov     edx, 0D6h; void *
0x140008737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000873c  mov     rcx, rbx; hObject
0x14000873f  call    cs:__imp_CloseHandle
0x140008746  nop     dword ptr [rax+rax+00h]
0x14000874b  test    eax, eax
0x14000874d  jz      loc_1400088D9
0x140008753  mov     eax, edi
0x140008755  jmp     loc_140008883
0x14000875a  lea     r8, asc_140052558; "h"
0x140008761  mov     rdx, rsi; unsigned __int64
0x140008764  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x140008769  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000876e  lea     r8, [rsp+280h+Name]; lpName
0x140008773  xor     edx, edx; bInheritHandle
0x140008775  mov     ecx, 1F0003h; dwDesiredAccess
0x14000877a  call    cs:__imp_OpenSemaphoreW
0x140008781  nop     dword ptr [rax+rax+00h]
0x140008786  mov     rdi, rax
0x140008789  test    rax, rax
0x14000878c  jz      loc_140008832
0x140008792  lea     rdx, [rsp+280h+var_260]; int *
0x140008797  mov     rcx, rax; hHandle
0x14000879a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000879f  mov     esi, eax
0x1400087a1  test    eax, eax
0x1400087a3  jns     short loc_1400087EE
0x1400087a5  mov     rcx, [rbp+188h]; this
0x1400087ac  mov     r9d, eax; char *
0x1400087af  mov     edx, 0DEh; void *
0x1400087b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400087b9  mov     rcx, rdi; hObject
0x1400087bc  call    cs:__imp_CloseHandle
0x1400087c3  nop     dword ptr [rax+rax+00h]
0x1400087c8  test    eax, eax
0x1400087ca  jz      loc_1400088EB
0x1400087d0  mov     rcx, rbx; hObject
0x1400087d3  call    cs:__imp_CloseHandle
0x1400087da  nop     dword ptr [rax+rax+00h]
0x1400087df  test    eax, eax
0x1400087e1  jz      loc_1400088FD
0x1400087e7  mov     eax, esi
0x1400087e9  jmp     loc_140008883
0x1400087ee  mov     rcx, rdi; hObject
0x1400087f1  call    cs:__imp_CloseHandle
0x1400087f8  nop     dword ptr [rax+rax+00h]
0x1400087fd  test    eax, eax
0x1400087ff  jz      loc_1400088A3
0x140008805  movsxd  rax, [rsp+280h+var_25C]
0x14000880a  movsxd  rcx, [rsp+280h+var_260]
0x14000880f  shl     rcx, 1Fh
0x140008813  or      rcx, rax
0x140008816  mov     [r14], rcx
0x140008819  mov     rcx, rbx; hObject
0x14000881c  call    cs:__imp_CloseHandle
0x140008823  nop     dword ptr [rax+rax+00h]
0x140008828  test    eax, eax
0x14000882a  jz      loc_1400088B5
0x140008830  jmp     short loc_14000886E
0x140008832  mov     rcx, [rbp+188h]; this
0x140008839  mov     edx, 0DCh; void *
0x14000883e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008843  mov     rcx, rbx; hObject
0x140008846  mov     edi, eax
0x140008848  call    cs:__imp_CloseHandle
0x14000884f  nop     dword ptr [rax+rax+00h]
0x140008854  test    eax, eax
0x140008856  jz      short loc_1400088C7
0x140008858  jmp     loc_140008753
0x14000885d  call    cs:__imp_GetLastError
0x140008864  nop     dword ptr [rax+rax+00h]
0x140008869  cmp     eax, 2
0x14000886c  jnz     short loc_140008872
0x14000886e  xor     eax, eax
0x140008870  jmp     short loc_140008883
0x140008872  mov     rcx, [rbp+188h]; this
0x140008879  mov     edx, 0D0h; void *
0x14000887e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008883  mov     rcx, [rbp+180h+var_40]
0x14000888a  xor     rcx, rsp; StackCookie
0x14000888d  call    __security_check_cookie
0x140008892  add     rsp, 258h
0x140008899  pop     r15
0x14000889b  pop     r14
0x14000889d  pop     rdi
0x14000889e  pop     rsi
0x14000889f  pop     rbx
0x1400088a0  pop     rbp
0x1400088a1  retn
0x1400088a3  mov     rcx, [rbp+188h]; this
0x1400088aa  mov     edx, 0A0Bh; void *
0x1400088af  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400088b5  mov     rcx, [rbp+188h]; this
0x1400088bc  mov     edx, 0A0Bh; void *
0x1400088c1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400088c7  mov     rcx, [rbp+188h]; this
0x1400088ce  mov     edx, 0A0Bh; void *
0x1400088d3  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400088d9  mov     rcx, [rbp+188h]; this
0x1400088e0  mov     edx, 0A0Bh; void *
0x1400088e5  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400088eb  mov     rcx, [rbp+188h]; this
0x1400088f2  mov     edx, 0A0Bh; void *
0x1400088f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400088fd  mov     rcx, [rbp+188h]; this
0x140008904  mov     edx, 0A0Bh; void *
0x140008909  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
