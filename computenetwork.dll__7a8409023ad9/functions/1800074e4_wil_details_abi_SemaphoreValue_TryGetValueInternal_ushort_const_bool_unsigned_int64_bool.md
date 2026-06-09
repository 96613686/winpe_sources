# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800074e4`
- end: `0x18000775e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800044f8`

## callees

- `0x180001600`
- `0x180005494`
- `0x180006a34`
- `0x180006a54`
- `0x180007330`
- `0x1800074e4`
- `0x1800078bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007578`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800075f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007578`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800075f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000765d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800075c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007648`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000765d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076a4`

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
0x1800074e4  push    rbp
0x1800074e6  push    rbx
0x1800074e7  push    rsi
0x1800074e8  push    rdi
0x1800074e9  push    r14
0x1800074eb  push    r15
0x1800074ed  lea     rbp, [rsp-158h]
0x1800074f5  sub     rsp, 258h
0x1800074fc  mov     rax, cs:__security_cookie
0x180007503  xor     rax, rsp
0x180007506  mov     [rbp+180h+var_40], rax
0x18000750d  xor     r15d, r15d
0x180007510  lea     rax, [rsp+280h+Name]
0x180007515  mov     [r8], r15
0x180007518  mov     r14, r8
0x18000751b  mov     edx, 104h
0x180007520  mov     r9d, 7FFFFFFEh
0x180007526  test    r9, r9
0x180007529  jz      short loc_18000754A
0x18000752b  movzx   r8d, word ptr [rcx]
0x18000752f  test    r8w, r8w
0x180007533  jz      short loc_18000754A
0x180007535  mov     [rax], r8w
0x180007539  add     rcx, 2
0x18000753d  add     rax, 2
0x180007541  dec     r9
0x180007544  sub     rdx, 1; unsigned __int64
0x180007548  jnz     short loc_180007526
0x18000754a  test    rdx, rdx
0x18000754d  lea     rcx, [rax-2]
0x180007551  lea     r8, aP0; "_p0"
0x180007558  cmovnz  rcx, rax
0x18000755c  mov     [rcx], r15w
0x180007560  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180007565  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000756a  mov     esi, 1F0003h
0x18000756f  lea     r8, [rsp+280h+Name]; lpName
0x180007574  mov     ecx, esi; dwDesiredAccess
0x180007576  xor     edx, edx; bInheritHandle
0x180007578  call    cs:__imp_OpenSemaphoreW
0x18000757e  mov     rbx, rax
0x180007581  test    rax, rax
0x180007584  jz      loc_1800076B3
0x18000758a  lea     rdx, [rsp+280h+var_25C]; int *
0x18000758f  mov     [rsp+280h+var_25C], r15d
0x180007594  mov     rcx, rax; hHandle
0x180007597  mov     [rsp+280h+var_260], r15d; int
0x18000759c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800075a1  mov     edi, eax
0x1800075a3  test    eax, eax
0x1800075a5  jns     short loc_1800075DA
0x1800075a7  mov     rcx, [rbp+188h]; this
0x1800075ae  lea     r8, aWil; "wil"
0x1800075b5  mov     r9d, eax; char *
0x1800075b8  mov     edx, 0D6h; void *
0x1800075bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075c2  mov     rcx, rbx; hObject
0x1800075c5  call    cs:__imp_CloseHandle
0x1800075cb  test    eax, eax
0x1800075cd  jz      loc_180007728
0x1800075d3  mov     eax, edi
0x1800075d5  jmp     loc_1800076D3
0x1800075da  lea     r8, asc_1800125F0; "h"
0x1800075e1  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x1800075e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800075eb  lea     r8, [rsp+280h+Name]; lpName
0x1800075f0  xor     edx, edx; bInheritHandle
0x1800075f2  mov     ecx, esi; dwDesiredAccess
0x1800075f4  call    cs:__imp_OpenSemaphoreW
0x1800075fa  mov     rdi, rax
0x1800075fd  test    rax, rax
0x180007600  jz      loc_18000768E
0x180007606  lea     rdx, [rsp+280h+var_260]; int *
0x18000760b  mov     rcx, rax; hHandle
0x18000760e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007613  mov     esi, eax
0x180007615  test    eax, eax
0x180007617  jns     short loc_18000765A
0x180007619  mov     rcx, [rbp+188h]; this
0x180007620  lea     r8, aWil; "wil"
0x180007627  mov     r9d, eax; char *
0x18000762a  mov     edx, 0DEh; void *
0x18000762f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007634  mov     rcx, rdi; hObject
0x180007637  call    cs:__imp_CloseHandle
0x18000763d  test    eax, eax
0x18000763f  jz      loc_18000773A
0x180007645  mov     rcx, rbx; hObject
0x180007648  call    cs:__imp_CloseHandle
0x18000764e  test    eax, eax
0x180007650  jz      loc_18000774C
0x180007656  mov     eax, esi
0x180007658  jmp     short loc_1800076D3
0x18000765a  mov     rcx, rdi; hObject
0x18000765d  call    cs:__imp_CloseHandle
0x180007663  test    eax, eax
0x180007665  jz      loc_1800076F2
0x18000766b  movsxd  rax, [rsp+280h+var_25C]
0x180007670  movsxd  rcx, [rsp+280h+var_260]
0x180007675  shl     rcx, 1Fh
0x180007679  or      rcx, rax
0x18000767c  mov     [r14], rcx
0x18000767f  mov     rcx, rbx; hObject
0x180007682  call    cs:__imp_CloseHandle
0x180007688  test    eax, eax
0x18000768a  jz      short loc_180007704
0x18000768c  jmp     short loc_1800076BE
0x18000768e  mov     rcx, [rbp+188h]; this
0x180007695  mov     edx, 0DCh; void *
0x18000769a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000769f  mov     rcx, rbx; hObject
0x1800076a2  mov     edi, eax
0x1800076a4  call    cs:__imp_CloseHandle
0x1800076aa  test    eax, eax
0x1800076ac  jz      short loc_180007716
0x1800076ae  jmp     loc_1800075D3
0x1800076b3  call    cs:__imp_GetLastError
0x1800076b9  cmp     eax, 2
0x1800076bc  jnz     short loc_1800076C2
0x1800076be  xor     eax, eax
0x1800076c0  jmp     short loc_1800076D3
0x1800076c2  mov     rcx, [rbp+188h]; this
0x1800076c9  mov     edx, 0D0h; void *
0x1800076ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800076d3  mov     rcx, [rbp+180h+var_40]
0x1800076da  xor     rcx, rsp; StackCookie
0x1800076dd  call    __security_check_cookie
0x1800076e2  add     rsp, 258h
0x1800076e9  pop     r15
0x1800076eb  pop     r14
0x1800076ed  pop     rdi
0x1800076ee  pop     rsi
0x1800076ef  pop     rbx
0x1800076f0  pop     rbp
0x1800076f1  retn
0x1800076f2  mov     rcx, [rbp+188h]; this
0x1800076f9  mov     edx, 0A0Bh; void *
0x1800076fe  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007704  mov     rcx, [rbp+188h]; this
0x18000770b  mov     edx, 0A0Bh; void *
0x180007710  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007716  mov     rcx, [rbp+188h]; this
0x18000771d  mov     edx, 0A0Bh; void *
0x180007722  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007728  mov     rcx, [rbp+188h]; this
0x18000772f  mov     edx, 0A0Bh; void *
0x180007734  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000773a  mov     rcx, [rbp+188h]; this
0x180007741  mov     edx, 0A0Bh; void *
0x180007746  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000774c  mov     rcx, [rbp+188h]; this
0x180007753  mov     edx, 0A0Bh; void *
0x180007758  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
