# RemoveRegistryTree(HKEY__ *,ushort const *)

- ea: `0x180008044`
- end: `0x180008257`
- name: `?RemoveRegistryTree@@YAJPEAUHKEY__@@PEBG@Z`
- size: `531`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016554`
- `0x18001fdec`

## callees

- `0x180008044`
- `0x180008260`
- `0x180008520`
- `0x18001b914`
- `0x1800227f2`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008195`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008195`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008130`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800081e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180008130`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800081e1`

## string_xrefs

- `0x1800081bf`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x180008218`: `onecore\admin\appmodel\common\removeregistrytree.cpp`
- `0x18000823e`: `onecore\admin\appmodel\common\removeregistrytree.cpp`

## pseudocode

```c
__int64 __fastcall RemoveRegistryTree(HKEY a1, WCHAR *a2)
{
  void *v3; // rdi
  WCHAR *p_SubKey; // rax
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  WCHAR *i; // rdx
  WCHAR *v11; // rcx
  int CurrentUserSidInternal; // eax
  HKEY v13; // rcx
  int v14; // eax
  HANDLE ProcessHeap; // rax
  LSTATUS v17; // eax
  void *v18; // [rsp+20h] [rbp-258h] BYREF
  WCHAR SubKey; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v20[526]; // [rsp+32h] [rbp-246h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v18 = 0;
  SubKey = 0;
  v3 = 0;
  memset_0(v20, 0, 0x208u);
  p_SubKey = &SubKey;
  v5 = 261;
  do
  {
    if ( !*p_SubKey )
      break;
    ++p_SubKey;
    --v5;
  }
  while ( v5 );
  v6 = v5 == 0 ? 0x80070057 : 0;
  v7 = (261 - v5) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64);
  if ( !v5 )
    goto LABEL_19;
  v8 = 261 - v7;
  v9 = 2147483646;
  for ( i = (WCHAR *)&v20[2 * v7 - 2]; v8; --v8 )
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *i++ = *a2++;
    --v9;
  }
  v11 = i - 1;
  v6 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v11 = i;
  *v11 = 0;
  if ( !v8 )
  {
LABEL_19:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
      (const char *)v6,
      (int)v18);
    return v6;
  }
  if ( !RegDeleteTreeW(HKEY_USERS, &SubKey) )
    goto LABEL_15;
  CurrentUserSidInternal = GetCurrentUserSidInternal(&v18);
  v6 = CurrentUserSidInternal;
  if ( CurrentUserSidInternal < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
      (const char *)(unsigned int)CurrentUserSidInternal,
      (int)v18);
    v3 = v18;
  }
  else
  {
    v3 = v18;
    v14 = ResetRegTreeSecurityInternal(v13, &SubKey, (WCHAR *)v18);
    v6 = v14;
    if ( v14 == -2147024894 )
    {
LABEL_15:
      v6 = 0;
      goto LABEL_16;
    }
    if ( v14 >= 0 )
    {
      v17 = RegDeleteTreeW(HKEY_USERS, &SubKey);
      v6 = v17;
      if ( (v17 & 0xFFFFFFFD) != 0 )
      {
        if ( v17 > 0 )
          v6 = (unsigned __int16)v17 | 0x80070000;
        goto LABEL_16;
      }
      goto LABEL_15;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"onecore\\admin\\appmodel\\common\\removeregistrytree.cpp",
      (const char *)(unsigned int)v14,
      (int)v18);
  }
LABEL_16:
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return v6;
}

```

## disassembly

```asm
0x180008044  push    rbx
0x180008046  push    rbp
0x180008047  push    rsi
0x180008048  push    rdi
0x180008049  sub     rsp, 258h
0x180008050  mov     rax, cs:__security_cookie
0x180008057  xor     rax, rsp
0x18000805a  mov     [rsp+278h+var_38], rax
0x180008062  xor     ebp, ebp
0x180008064  lea     rcx, [rsp+278h+var_246]; void *
0x180008069  mov     rsi, rdx
0x18000806c  mov     [rsp+278h+var_258], rbp; int
0x180008071  xor     edx, edx; Val
0x180008073  mov     [rsp+278h+SubKey], bp
0x180008078  mov     r8d, 208h; Size
0x18000807e  mov     edi, ebp
0x180008080  call    memset_0
0x180008085  mov     r8d, 105h
0x18000808b  lea     rax, [rsp+278h+SubKey]
0x180008090  mov     r9d, r8d
0x180008093  cmp     [rax], bp
0x180008096  jz      short loc_1800080A2
0x180008098  add     rax, 2
0x18000809c  sub     r9, 1
0x1800080a0  jnz     short loc_180008093
0x1800080a2  mov     rax, r9
0x1800080a5  mov     rcx, r8
0x1800080a8  neg     rax
0x1800080ab  mov     rax, r9
0x1800080ae  sbb     ebx, ebx
0x1800080b0  sub     rcx, r9
0x1800080b3  not     ebx
0x1800080b5  and     ebx, 80070057h
0x1800080bb  neg     rax
0x1800080be  sbb     rdx, rdx
0x1800080c1  and     rdx, rcx
0x1800080c4  test    r9, r9
0x1800080c7  jz      loc_1800081B7
0x1800080cd  sub     r8, rdx
0x1800080d0  mov     eax, 7FFFFFFEh
0x1800080d5  lea     rdx, [rsp+rdx*2+278h+SubKey]
0x1800080da  jz      short loc_1800080FD
0x1800080dc  test    rax, rax
0x1800080df  jz      short loc_1800080FD
0x1800080e1  movzx   ecx, word ptr [rsi]
0x1800080e4  test    cx, cx
0x1800080e7  jz      short loc_1800080FD
0x1800080e9  mov     [rdx], cx
0x1800080ec  add     rsi, 2
0x1800080f0  add     rdx, 2
0x1800080f4  dec     rax
0x1800080f7  sub     r8, 1
0x1800080fb  jnz     short loc_1800080DC
0x1800080fd  mov     rax, r8
0x180008100  lea     rcx, [rdx-2]
0x180008104  neg     rax
0x180008107  sbb     ebx, ebx
0x180008109  not     ebx
0x18000810b  and     ebx, 8007007Ah
0x180008111  test    r8, r8
0x180008114  cmovnz  rcx, rdx
0x180008118  mov     [rcx], bp
0x18000811b  jz      loc_1800081B7
0x180008121  mov     rsi, 0FFFFFFFF80000003h
0x180008128  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18000812d  mov     rcx, rsi; hKey
0x180008130  call    cs:__imp_RegDeleteTreeW
0x180008137  nop     dword ptr [rax+rax+00h]
0x18000813c  test    eax, eax
0x18000813e  jz      short loc_18000816F
0x180008140  lea     rcx, [rsp+278h+var_258]; void **
0x180008145  call    ?GetCurrentUserSidInternal@@YAJPEAPEAX@Z; GetCurrentUserSidInternal(void * *)
0x18000814a  mov     ebx, eax
0x18000814c  test    eax, eax
0x18000814e  js      loc_180008210
0x180008154  mov     rdi, [rsp+278h+var_258]
0x180008159  lea     rdx, [rsp+278h+SubKey]; unsigned __int16 *
0x18000815e  mov     r8, rdi; void *
0x180008161  call    ?ResetRegTreeSecurityInternal@@YAJPEAUHKEY__@@PEBGPEAX@Z; ResetRegTreeSecurityInternal(HKEY__ *,ushort const *,void *)
0x180008166  mov     ebx, eax
0x180008168  cmp     eax, 80070002h
0x18000816d  jnz     short loc_1800081D5
0x18000816f  mov     ebx, ebp
0x180008171  test    rdi, rdi
0x180008174  jnz     short loc_180008195
0x180008176  mov     eax, ebx
0x180008178  mov     rcx, [rsp+278h+var_38]
0x180008180  xor     rcx, rsp; StackCookie
0x180008183  call    __security_check_cookie
0x180008188  add     rsp, 258h
0x18000818f  pop     rdi
0x180008190  pop     rsi
0x180008191  pop     rbp
0x180008192  pop     rbx
0x180008193  retn
0x180008195  call    cs:__imp_GetProcessHeap
0x18000819c  nop     dword ptr [rax+rax+00h]
0x1800081a1  mov     r8, rdi; lpMem
0x1800081a4  xor     edx, edx; dwFlags
0x1800081a6  mov     rcx, rax; hHeap
0x1800081a9  call    cs:__imp_HeapFree
0x1800081b0  nop     dword ptr [rax+rax+00h]
0x1800081b5  jmp     short loc_180008176
0x1800081b7  mov     rcx, [rsp+278h]; this
0x1800081bf  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x1800081c6  mov     r9d, ebx; char *
0x1800081c9  mov     edx, 11Dh; void *
0x1800081ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800081d3  jmp     short loc_180008176
0x1800081d5  test    eax, eax
0x1800081d7  js      short loc_180008236
0x1800081d9  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x1800081de  mov     rcx, rsi; hKey
0x1800081e1  call    cs:__imp_RegDeleteTreeW
0x1800081e8  nop     dword ptr [rax+rax+00h]
0x1800081ed  mov     ebx, eax
0x1800081ef  test    eax, 0FFFFFFFDh
0x1800081f4  jz      loc_18000816F
0x1800081fa  test    eax, eax
0x1800081fc  jle     loc_180008171
0x180008202  movzx   ebx, ax
0x180008205  or      ebx, 80070000h
0x18000820b  jmp     loc_180008171
0x180008210  mov     rcx, [rsp+278h]; this
0x180008218  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x18000821f  mov     r9d, eax; char *
0x180008222  mov     edx, 124h; void *
0x180008227  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000822c  mov     rdi, [rsp+278h+var_258]
0x180008231  jmp     loc_180008171
0x180008236  mov     rcx, [rsp+278h]; this
0x18000823e  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\common\\remov"...
0x180008245  mov     r9d, eax; char *
0x180008248  mov     edx, 12Eh; void *
0x18000824d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008252  jmp     loc_180008171
```
