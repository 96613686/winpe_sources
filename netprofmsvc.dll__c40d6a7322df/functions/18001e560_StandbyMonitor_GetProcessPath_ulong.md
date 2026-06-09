# StandbyMonitor::GetProcessPath(ulong)

- ea: `0x18001e560`
- end: `0x18001e7ed`
- name: `?GetProcessPath@StandbyMonitor@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@Z`
- size: `653`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180015ab0`
- `0x18001e4bc`
- `0x18001e560`
- `0x18001e920`
- `0x18004c5bc`
- `0x18006f500`
- `0x1800a88a0`
- `0x1800a9738`
- `0x180121280`
- `0x1801213c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e5f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e7e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e7e2`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e595`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001e595`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x18001e5e9`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x18001e6b3`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x18001e5e9`
- `api-ms-win-core-psapi-ansi-l1-1-0!QueryFullProcessImageNameA` at `0x18001e6b3`

## string_xrefs

- `0x18001e6c5`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitorshim.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StandbyMonitor::GetProcessPath(__int64 a1, DWORD a2)
{
  __int64 v3; // rdx
  char *v4; // rbx
  CHAR *v5; // r8
  BOOL FullProcessImageNameA; // edi
  __int64 v7; // r8
  DWORD v8; // edx
  DWORD v9; // eax
  unsigned __int64 v10; // rcx
  const char *v11; // r9
  unsigned __int64 v12; // rdx
  LPSTR *v13; // rax
  unsigned __int64 v14; // r14
  LPSTR *v15; // rdi
  char *v16; // rdi
  CHAR *v17; // r8
  LPSTR *v19; // rax
  LPSTR *v20; // rax
  unsigned __int64 v21; // rcx
  LPSTR *v22; // rax
  int v23; // [rsp+20h] [rbp-50h]
  DWORD dwSize[2]; // [rsp+40h] [rbp-30h] BYREF
  LPSTR lpExeName[2]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-18h]
  unsigned __int64 v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *(_QWORD *)dwSize = a1;
  v4 = (char *)OpenProcess(0x1000u, 0, a2);
  if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
LABEL_26:
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v4);
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    std::string::_Construct<1,char const *>(a1, &Src, 0);
    return a1;
  }
  dwSize[0] = 260;
  *(_OWORD *)lpExeName = 0;
  v26 = 0;
  v27 = 0;
  std::string::_Construct<0,char>(lpExeName, v3, 260);
  v5 = (CHAR *)lpExeName;
  if ( v27 > 0xF )
    v5 = lpExeName[0];
  FullProcessImageNameA = QueryFullProcessImageNameA(v4, 0, v5, dwSize);
  if ( !FullProcessImageNameA )
  {
    while ( GetLastError() == 122 )
    {
      v8 = dwSize[0];
      v9 = dwSize[0] + (dwSize[0] >> 1);
      v10 = 0xFFFFFFFFLL;
      if ( v9 >= dwSize[0] )
        v10 = v9;
      v11 = v9 < dwSize[0] ? (const char *)0x80070216LL : 0LL;
      dwSize[0] = v10;
      if ( v9 < v8 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x17,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitorshim.cpp",
          v11,
          v23);
LABEL_23:
        if ( FullProcessImageNameA )
          goto LABEL_30;
        break;
      }
      v12 = v26;
      if ( v10 > v26 )
      {
        v14 = v10 - v26;
        if ( v10 - v26 > v27 - v26 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAAEAV34__KD_Z__KD___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0D_Z__KD_Z(
            lpExeName,
            v10 - v26,
            v7,
            v10 - v26);
        }
        else
        {
          v26 = v10;
          v15 = lpExeName;
          if ( v27 > 0xF )
            v15 = (LPSTR *)lpExeName[0];
          v16 = (char *)v15 + v12;
          memset_0(v16, 0, v10 - v12);
          v16[v14] = 0;
        }
      }
      else
      {
        v26 = v10;
        v13 = lpExeName;
        if ( v27 > 0xF )
          v13 = (LPSTR *)lpExeName[0];
        *((_BYTE *)v13 + v10) = 0;
      }
      v17 = (CHAR *)lpExeName;
      if ( v27 > 0xF )
        v17 = lpExeName[0];
      FullProcessImageNameA = QueryFullProcessImageNameA(v4, 0, v17, dwSize);
      if ( FullProcessImageNameA )
        goto LABEL_23;
    }
    if ( v27 > 0xF )
      std::_Deallocate<16>(lpExeName[0], v27 + 1);
    goto LABEL_26;
  }
LABEL_30:
  if ( dwSize[0] > v26 )
  {
    std::string::append(lpExeName, dwSize[0] - v26);
  }
  else
  {
    v26 = dwSize[0];
    v19 = lpExeName;
    if ( v27 > 0xF )
      v19 = (LPSTR *)lpExeName[0];
    *((_BYTE *)v19 + dwSize[0]) = 0;
  }
  while ( 1 )
  {
    v20 = lpExeName;
    if ( v27 > 0xF )
      v20 = (LPSTR *)lpExeName[0];
    if ( *((_BYTE *)v20 + v26 - 1) )
      break;
    v21 = --v26;
    v22 = lpExeName;
    if ( v27 > 0xF )
      v22 = (LPSTR *)lpExeName[0];
    *((_BYTE *)v22 + v21) = 0;
  }
  std::string::string(a1, lpExeName);
  if ( v27 > 0xF )
    std::_Deallocate<16>(lpExeName[0], v27 + 1);
  v26 = 0;
  v27 = 15;
  LOBYTE(lpExeName[0]) = 0;
  CloseHandle(v4);
  return a1;
}

```

## disassembly

```asm
0x18001e560  mov     [rsp-28h+arg_10], rbx
0x18001e565  push    rbp
0x18001e566  push    rsi
0x18001e567  push    rdi
0x18001e568  push    r14
0x18001e56a  push    r15
0x18001e56c  mov     rbp, rsp
0x18001e56f  sub     rsp, 70h
0x18001e573  mov     rax, cs:__security_cookie
0x18001e57a  xor     rax, rsp
0x18001e57d  mov     [rbp+var_8], rax
0x18001e581  mov     rsi, rcx
0x18001e584  mov     qword ptr [rbp+dwSize], rcx
0x18001e588  xor     r15d, r15d
0x18001e58b  mov     r8d, edx; dwProcessId
0x18001e58e  xor     edx, edx; bInheritHandle
0x18001e590  mov     ecx, 1000h; dwDesiredAccess
0x18001e595  call    cs:__imp_OpenProcess
0x18001e59b  mov     rbx, rax
0x18001e59e  mov     [rbp+var_38], rax
0x18001e5a2  dec     rax
0x18001e5a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e5a9  ja      loc_18001E6F4
0x18001e5af  mov     r8d, 104h
0x18001e5b5  mov     [rbp+dwSize], r8d
0x18001e5b9  xorps   xmm0, xmm0
0x18001e5bc  movups  xmmword ptr [rbp+lpExeName], xmm0
0x18001e5c0  mov     [rbp+var_18], r15
0x18001e5c4  mov     [rbp+var_10], r15
0x18001e5c8  lea     rcx, [rbp+lpExeName]
0x18001e5cc  call    ??$_Construct@$0A@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXD_K@Z; std::string::_Construct<0,char>(char,unsigned __int64)
0x18001e5d1  nop
0x18001e5d2  lea     r8, [rbp+lpExeName]
0x18001e5d6  cmp     [rbp+var_10], 0Fh
0x18001e5db  cmova   r8, [rbp+lpExeName]; lpExeName
0x18001e5e0  lea     r9, [rbp+dwSize]; lpdwSize
0x18001e5e4  xor     edx, edx; dwFlags
0x18001e5e6  mov     rcx, rbx; hProcess
0x18001e5e9  call    cs:__imp_QueryFullProcessImageNameA
0x18001e5ef  mov     edi, eax
0x18001e5f1  test    eax, eax
0x18001e5f3  jnz     loc_18001E74A
0x18001e5f9  call    cs:__imp_GetLastError
0x18001e5ff  cmp     eax, 7Ah ; 'z'
0x18001e602  jnz     loc_18001E6DD
0x18001e608  mov     edx, [rbp+dwSize]
0x18001e60b  mov     eax, edx
0x18001e60d  shr     eax, 1
0x18001e60f  add     eax, edx
0x18001e611  or      ecx, 0FFFFFFFFh
0x18001e614  cmp     eax, edx
0x18001e616  cmovnb  ecx, eax
0x18001e619  sbb     r9d, r9d
0x18001e61c  and     r9d, 80070216h; char *
0x18001e623  mov     [rbp+dwSize], ecx
0x18001e626  mov     r10, [rbp+28h]
0x18001e62a  cmp     eax, edx
0x18001e62c  jb      loc_18001E6C5
0x18001e632  mov     rdx, [rbp+var_18]
0x18001e636  cmp     rcx, rdx
0x18001e639  ja      short loc_18001E653
0x18001e63b  mov     [rbp+var_18], rcx
0x18001e63f  lea     rax, [rbp+lpExeName]
0x18001e643  cmp     [rbp+var_10], 0Fh
0x18001e648  cmova   rax, [rbp+lpExeName]
0x18001e64d  mov     [rcx+rax], r15b
0x18001e651  jmp     short loc_18001E69C
0x18001e653  mov     r14, rcx
0x18001e656  sub     r14, rdx
0x18001e659  mov     rax, [rbp+var_10]
0x18001e65d  sub     rax, rdx
0x18001e660  cmp     r14, rax
0x18001e663  ja      short loc_18001E68D
0x18001e665  mov     [rbp+var_18], rcx
0x18001e669  lea     rdi, [rbp+lpExeName]
0x18001e66d  cmp     [rbp+var_10], 0Fh
0x18001e672  cmova   rdi, [rbp+lpExeName]
0x18001e677  add     rdi, rdx
0x18001e67a  mov     r8, r14; Size
0x18001e67d  xor     edx, edx; Val
0x18001e67f  mov     rcx, rdi; void *
0x18001e682  call    memset_0
0x18001e687  mov     [rdi+r14], r15b
0x18001e68b  jmp     short loc_18001E69C
0x18001e68d  mov     r9, r14
0x18001e690  mov     rdx, r14
0x18001e693  lea     rcx, [rbp+lpExeName]
0x18001e697  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV34@_KD@Z@_KD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0D@Z@_KD@Z; std::string::_Reallocate_grow_by<`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char>(unsigned __int64,`std::string::append(unsigned __int64,char)'::`2'::_lambda_1_,unsigned __int64,char)
0x18001e69c  lea     r8, [rbp+lpExeName]
0x18001e6a0  cmp     [rbp+var_10], 0Fh
0x18001e6a5  cmova   r8, [rbp+lpExeName]; lpExeName
0x18001e6aa  lea     r9, [rbp+dwSize]; lpdwSize
0x18001e6ae  xor     edx, edx; dwFlags
0x18001e6b0  mov     rcx, rbx; hProcess
0x18001e6b3  call    cs:__imp_QueryFullProcessImageNameA
0x18001e6b9  mov     edi, eax
0x18001e6bb  test    eax, eax
0x18001e6bd  jz      loc_18001E5F9
0x18001e6c3  jmp     short loc_18001E6D9
0x18001e6c5  lea     r8, aOnecoreNetNetp_32; "onecore\\net\\netprofiles\\service\\src"...
0x18001e6cc  mov     edx, 17h; void *
0x18001e6d1  mov     rcx, r10; this
0x18001e6d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e6d9  test    edi, edi
0x18001e6db  jnz     short loc_18001E74A
0x18001e6dd  mov     rdx, [rbp+var_10]
0x18001e6e1  cmp     rdx, 0Fh
0x18001e6e5  jbe     short loc_18001E6F4
0x18001e6e7  inc     rdx
0x18001e6ea  mov     rcx, [rbp+lpExeName]
0x18001e6ee  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e6f3  nop
0x18001e6f4  lea     rax, [rbx-1]
0x18001e6f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e6fc  ja      short loc_18001E707
0x18001e6fe  mov     rcx, rbx; hObject
0x18001e701  call    cs:__imp_CloseHandle
0x18001e707  xorps   xmm0, xmm0
0x18001e70a  movups  xmmword ptr [rsi], xmm0
0x18001e70d  mov     [rsi+10h], r15
0x18001e711  mov     [rsi+18h], r15
0x18001e715  xor     r8d, r8d
0x18001e718  lea     rdx, Src
0x18001e71f  mov     rcx, rsi
0x18001e722  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18001e727  mov     rax, rsi
0x18001e72a  mov     rcx, [rbp+var_8]
0x18001e72e  xor     rcx, rsp; StackCookie
0x18001e731  call    __security_check_cookie
0x18001e736  mov     rbx, [rsp+70h+arg_10]
0x18001e73e  add     rsp, 70h
0x18001e742  pop     r15
0x18001e744  pop     r14
0x18001e746  pop     rdi
0x18001e747  pop     rsi
0x18001e748  pop     rbp
0x18001e749  retn
0x18001e74a  mov     edx, [rbp+dwSize]
0x18001e74d  cmp     rdx, [rbp+var_18]
0x18001e751  ja      short loc_18001E76B
0x18001e753  mov     [rbp+var_18], rdx
0x18001e757  lea     rax, [rbp+lpExeName]
0x18001e75b  cmp     [rbp+var_10], 0Fh
0x18001e760  cmova   rax, [rbp+lpExeName]
0x18001e765  mov     [rdx+rax], r15b
0x18001e769  jmp     short loc_18001E778
0x18001e76b  sub     rdx, [rbp+var_18]
0x18001e76f  lea     rcx, [rbp+lpExeName]
0x18001e773  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x18001e778  lea     rax, [rbp+lpExeName]
0x18001e77c  cmp     [rbp+var_10], 0Fh
0x18001e781  cmova   rax, [rbp+lpExeName]
0x18001e786  mov     rcx, [rbp+var_18]
0x18001e78a  cmp     [rcx+rax-1], r15b
0x18001e78f  jnz     short loc_18001E7AC
0x18001e791  dec     rcx
0x18001e794  mov     [rbp+var_18], rcx
0x18001e798  lea     rax, [rbp+lpExeName]
0x18001e79c  cmp     [rbp+var_10], 0Fh
0x18001e7a1  cmova   rax, [rbp+lpExeName]
0x18001e7a6  mov     [rcx+rax], r15b
0x18001e7aa  jmp     short loc_18001E778
0x18001e7ac  lea     rdx, [rbp+lpExeName]
0x18001e7b0  mov     rcx, rsi
0x18001e7b3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x18001e7b8  nop
0x18001e7b9  mov     rdx, [rbp+var_10]
0x18001e7bd  cmp     rdx, 0Fh
0x18001e7c1  jbe     short loc_18001E7CF
0x18001e7c3  inc     rdx
0x18001e7c6  mov     rcx, [rbp+lpExeName]
0x18001e7ca  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e7cf  mov     [rbp+var_18], r15
0x18001e7d3  mov     [rbp+var_10], 0Fh
0x18001e7db  mov     byte ptr [rbp+lpExeName], r15b
0x18001e7df  mov     rcx, rbx; hObject
0x18001e7e2  call    cs:__imp_CloseHandle
0x18001e7e8  jmp     loc_18001E727
```
