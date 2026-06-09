# GetUserProfileListRootKeyName(ushort * *,int *)

- ea: `0x180015d00`
- end: `0x180016134`
- name: `?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z`
- size: `1076`
- prototype: `__int64 __fastcall(unsigned __int16 **, int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800157f4`
- `0x180015aa4`
- `0x18002b2a0`
- `0x18002e0cc`
- `0x18002f4fc`

## callees

- `0x1800111a0`
- `0x180015d00`
- `0x180016250`
- `0x18002d2d8`
- `0x18003b310`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015df6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016028`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015df6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016028`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001609d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015e98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001609d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015de8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ebb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015eff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001601a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001605b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001608f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015de8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015e8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015ebb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015eff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001601a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001605b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001608f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180015d58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015dad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015dad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015e27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ea2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015ea2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016003`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016043`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016003`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180016043`

## string_xrefs

- `0x180015ee6`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x1800160c4`: `onecore\internal\ds\inc\profiles\sid.h`

## pseudocode

```c
__int64 __fastcall GetUserProfileListRootKeyName(unsigned __int16 **a1, int *a2)
{
  BYTE *v4; // r12
  int v5; // eax
  HKEY v6; // r14
  BYTE *v7; // rdi
  LSTATUS v8; // eax
  signed int v9; // ebx
  DWORD v10; // ebx
  HANDLE ProcessHeap; // rax
  LSTATUS v12; // eax
  __int64 v13; // r14
  __int64 v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  unsigned int v17; // ebx
  HANDLE v18; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // r8
  __int64 v22; // rcx
  const WCHAR *v23; // rdx
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // rdi
  HANDLE v27; // rax
  DWORD v28; // r12d
  HANDLE v29; // rax
  WCHAR *v30; // rax
  WCHAR *v31; // r13
  DWORD v32; // eax
  DWORD v33; // r14d
  HANDLE v34; // rax
  HANDLE v35; // rax
  int v36; // eax
  int phkResult; // [rsp+20h] [rbp-38h]
  BYTE *v38; // [rsp+30h] [rbp-28h] BYREF
  __int64 v39; // [rsp+38h] [rbp-20h]
  __int64 v40; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  DWORD cbData; // [rsp+90h] [rbp+38h] BYREF
  DWORD Type; // [rsp+98h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+48h] BYREF

  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  hKey = 0;
  v4 = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\ProfileList", 0, 0x20019u, &hKey);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_24;
  v6 = hKey;
  Type = 0;
  cbData = 0;
  v7 = 0;
  v8 = RegQueryValueExW(hKey, L"RedirectionKey", 0, &Type, 0, &cbData);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    if ( Type - 1 > 1 || !cbData || (cbData & 1) != 0 )
    {
LABEL_46:
      v9 = -2147024883;
      goto LABEL_22;
    }
    v10 = cbData;
    ProcessHeap = GetProcessHeap();
    v7 = (BYTE *)HeapAlloc(ProcessHeap, 0, v10);
    if ( v7 )
    {
      v12 = RegQueryValueExW(v6, L"RedirectionKey", 0, &Type, v7, &cbData);
      v9 = v12;
      if ( v12 > 0 )
        v9 = (unsigned __int16)v12 | 0x80070000;
      if ( v9 < 0 )
        goto LABEL_22;
      v13 = (cbData >> 1) - 1;
      if ( Type != 2 || (v28 = ExpandEnvironmentStringsW((LPCWSTR)v7, 0, 0)) == 0 )
      {
LABEL_17:
        if ( !*(_WORD *)&v7[2 * v13] )
        {
          v39 = 0;
          v40 = 0;
          if ( v7 )
          {
            v14 = (unsigned int)(v13 + 1);
            if ( (_DWORD)v13 != -1 )
            {
              v38 = v7;
              v39 = v14 - 1;
              v40 = (unsigned int)v14;
              *(_WORD *)&v7[2 * (unsigned int)v14 - 2] = 0;
            }
          }
          v7 = 0;
          goto LABEL_22;
        }
        goto LABEL_46;
      }
      v29 = GetProcessHeap();
      v30 = (WCHAR *)HeapAlloc(v29, 0, 2LL * v28);
      v31 = v30;
      if ( v30 )
      {
        v32 = ExpandEnvironmentStringsW((LPCWSTR)v7, v30, v28);
        v33 = v32;
        if ( !v32 || v32 > v28 )
        {
          v9 = -2147024774;
          v35 = GetProcessHeap();
          HeapFree(v35, 0, v31);
          goto LABEL_22;
        }
        v9 = 0;
        v34 = GetProcessHeap();
        HeapFree(v34, 0, v7);
        v7 = (BYTE *)v31;
        v13 = v33 - 1;
        goto LABEL_17;
      }
    }
    v9 = -2147024882;
  }
LABEL_22:
  v15 = GetProcessHeap();
  HeapFree(v15, 0, v7);
  RegCloseKey(hKey);
  if ( v9 >= 0 )
  {
    v36 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
            (__int64)&v38,
            a1);
    v17 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v36,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v38);
      return v17;
    }
    v4 = v38;
    if ( a2 )
      *a2 = 1;
    goto LABEL_38;
  }
  v4 = v38;
LABEL_24:
  v16 = GetProcessHeap();
  *a1 = 0;
  if ( !is_mul_ok(0x39u, 2u) )
  {
    v17 = -2147024362;
    goto LABEL_26;
  }
  v20 = (unsigned __int16 *)HeapAlloc(v16, 0, 0x72u);
  *a1 = v20;
  v21 = v20;
  if ( !v20 )
  {
    v17 = -2147024882;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
      (const char *)v17,
      phkResult);
    if ( v4 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v4);
    }
    return v17;
  }
  v22 = 56;
  v23 = L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  v24 = 57;
  v25 = 0;
  while ( v22 && *v23 )
  {
    *v21++ = *v23++;
    --v22;
    ++v25;
    if ( !--v24 )
    {
      *(v21 - 1) = 0;
      goto LABEL_38;
    }
  }
  v26 = 57 - v25;
  *v21 = 0;
  if ( (unsigned __int64)(57 - v25) > 1 && (unsigned __int64)(2 * v26) > 2 )
    memset_0(&v20[v25 + 1], 0, 2 * v26 - 2);
LABEL_38:
  if ( v4 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180015d00  push    rbp
0x180015d02  push    rbx
0x180015d03  push    rsi
0x180015d04  push    r12
0x180015d06  push    r13
0x180015d08  push    r15
0x180015d0a  mov     rbp, rsp
0x180015d0d  sub     rsp, 58h
0x180015d11  xor     ebx, ebx
0x180015d13  mov     r15, rdx
0x180015d16  mov     [rcx], rbx
0x180015d19  mov     rsi, rcx
0x180015d1c  test    rdx, rdx
0x180015d1f  jnz     loc_18001610C
0x180015d25  lea     rax, [rbp+hKey]
0x180015d29  mov     [rbp+var_28], rbx
0x180015d2d  mov     r9d, 20019h; samDesired
0x180015d33  mov     [rsp+58h+phkResult], rax; phkResult
0x180015d38  xor     r8d, r8d; ulOptions
0x180015d3b  mov     [rbp+var_20], rbx
0x180015d3f  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pro"...
0x180015d46  mov     [rbp+var_18], rbx
0x180015d4a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015d51  mov     [rbp+hKey], rbx
0x180015d55  mov     r12, rbx
0x180015d58  call    cs:__imp_RegOpenKeyExW
0x180015d5e  test    eax, eax
0x180015d60  jg      loc_180015F2B
0x180015d66  mov     [rsp+58h+arg_18], rdi
0x180015d6e  mov     r13d, 8007000Eh
0x180015d74  test    eax, eax
0x180015d76  js      loc_180015EBB
0x180015d7c  lea     rax, [rbp+cbData]
0x180015d80  mov     [rsp+58h+var_8], r14
0x180015d85  mov     r14, [rbp+hKey]
0x180015d89  lea     r9, [rbp+Type]; lpType
0x180015d8d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180015d92  lea     rdx, aRedirectionkey; "RedirectionKey"
0x180015d99  mov     rcx, r14; hKey
0x180015d9c  mov     [rbp+Type], ebx
0x180015d9f  xor     r8d, r8d; lpReserved
0x180015da2  mov     [rbp+cbData], ebx
0x180015da5  mov     rdi, rbx
0x180015da8  mov     [rsp+58h+phkResult], rbx; lpData
0x180015dad  call    cs:__imp_RegQueryValueExW
0x180015db3  mov     ebx, eax
0x180015db5  test    eax, eax
0x180015db7  jg      loc_180015F38
0x180015dbd  test    ebx, ebx
0x180015dbf  js      loc_180015E8A
0x180015dc5  mov     eax, [rbp+Type]
0x180015dc8  dec     eax
0x180015dca  cmp     eax, 1
0x180015dcd  ja      loc_180016080
0x180015dd3  mov     eax, [rbp+cbData]
0x180015dd6  test    eax, eax
0x180015dd8  jz      loc_180016080
0x180015dde  test    al, 1
0x180015de0  jnz     loc_180016080
0x180015de6  mov     ebx, eax
0x180015de8  call    cs:__imp_GetProcessHeap
0x180015dee  mov     r8d, ebx; dwBytes
0x180015df1  xor     edx, edx; dwFlags
0x180015df3  mov     rcx, rax; hHeap
0x180015df6  call    cs:__imp_HeapAlloc
0x180015dfc  mov     rdi, rax
0x180015dff  test    rax, rax
0x180015e02  jz      loc_180015F4C
0x180015e08  lea     rax, [rbp+cbData]
0x180015e0c  xor     r8d, r8d; lpReserved
0x180015e0f  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180015e14  lea     r9, [rbp+Type]; lpType
0x180015e18  lea     rdx, aRedirectionkey; "RedirectionKey"
0x180015e1f  mov     [rsp+58h+phkResult], rdi; int
0x180015e24  mov     rcx, r14; hKey
0x180015e27  call    cs:__imp_RegQueryValueExW
0x180015e2d  mov     ebx, eax
0x180015e2f  test    eax, eax
0x180015e31  jg      loc_180015F54
0x180015e37  test    ebx, ebx
0x180015e39  js      short loc_180015E8A
0x180015e3b  mov     r14d, [rbp+cbData]
0x180015e3f  shr     r14d, 1
0x180015e42  dec     r14d
0x180015e45  cmp     [rbp+Type], 2
0x180015e49  jz      loc_180015FFB
0x180015e4f  cmp     word ptr [rdi+r14*2], 0
0x180015e55  jnz     loc_180016080
0x180015e5b  mov     [rbp+var_20], r12
0x180015e5f  mov     [rbp+var_18], r12
0x180015e63  test    rdi, rdi
0x180015e66  jz      short loc_180015E87
0x180015e68  lea     eax, [r14+1]
0x180015e6c  mov     ecx, eax
0x180015e6e  test    eax, eax
0x180015e70  jz      short loc_180015E87
0x180015e72  dec     rax
0x180015e75  mov     [rbp+var_28], rdi
0x180015e79  mov     [rbp+var_20], rax
0x180015e7d  mov     [rbp+var_18], rcx
0x180015e81  mov     [rdi+rcx*2-2], r12w
0x180015e87  mov     rdi, r12
0x180015e8a  call    cs:__imp_GetProcessHeap
0x180015e90  mov     r8, rdi; lpMem
0x180015e93  xor     edx, edx; dwFlags
0x180015e95  mov     rcx, rax; hHeap
0x180015e98  call    cs:__imp_HeapFree
0x180015e9e  mov     rcx, [rbp+hKey]; hKey
0x180015ea2  call    cs:__imp_RegCloseKey
0x180015ea8  mov     r14, [rsp+58h+var_8]
0x180015ead  test    ebx, ebx
0x180015eaf  jns     loc_1800160AE
0x180015eb5  mov     r12, [rbp+var_28]
0x180015eb9  xor     ebx, ebx
0x180015ebb  call    cs:__imp_GetProcessHeap
0x180015ec1  mov     edi, 39h ; '9'
0x180015ec6  mov     [rsi], rbx
0x180015ec9  mov     rcx, rax; hHeap
0x180015ecc  mov     eax, 2
0x180015ed1  mul     rdi
0x180015ed4  test    rdx, rdx
0x180015ed7  jz      loc_180015F62
0x180015edd  mov     ebx, 80070216h
0x180015ee2  mov     rcx, [rbp+30h]; this
0x180015ee6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x180015eed  mov     r9d, ebx; char *
0x180015ef0  mov     edx, 5Ah ; 'Z'; void *
0x180015ef5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015efa  test    r12, r12
0x180015efd  jz      short loc_180015F13
0x180015eff  call    cs:__imp_GetProcessHeap
0x180015f05  mov     r8, r12; lpMem
0x180015f08  xor     edx, edx; dwFlags
0x180015f0a  mov     rcx, rax; hHeap
0x180015f0d  call    cs:__imp_HeapFree
0x180015f13  mov     eax, ebx
0x180015f15  mov     rdi, [rsp+58h+arg_18]
0x180015f1d  add     rsp, 58h
0x180015f21  pop     r15
0x180015f23  pop     r13
0x180015f25  pop     r12
0x180015f27  pop     rsi
0x180015f28  pop     rbx
0x180015f29  pop     rbp
0x180015f2a  retn
0x180015f2b  movzx   eax, ax
0x180015f2e  or      eax, 80070000h
0x180015f33  jmp     loc_180015D66
0x180015f38  movzx   ebx, ax
0x180015f3b  or      ebx, 80070000h
0x180015f41  jmp     loc_180015DBD
0x180015f46  mov     r13d, 8007000Eh
0x180015f4c  mov     ebx, r13d
0x180015f4f  jmp     loc_180015E8A
0x180015f54  movzx   ebx, ax
0x180015f57  or      ebx, 80070000h
0x180015f5d  jmp     loc_180015E37
0x180015f62  mov     r8, rax; dwBytes
0x180015f65  xor     edx, edx; dwFlags
0x180015f67  call    cs:__imp_HeapAlloc
0x180015f6d  test    rax, rax
0x180015f70  mov     [rsi], rax
0x180015f73  mov     r8, rax
0x180015f76  cmovz   ebx, r13d
0x180015f7a  jz      loc_180015EE2
0x180015f80  mov     ecx, 38h ; '8'
0x180015f85  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x180015f8c  mov     r9, rdi
0x180015f8f  xor     r10d, r10d
0x180015f92  mov     r11, rax
0x180015f95  test    rcx, rcx
0x180015f98  jz      short loc_180015FC8
0x180015f9a  movzx   eax, word ptr [rdx]
0x180015f9d  test    ax, ax
0x180015fa0  jz      short loc_180015FC3
0x180015fa2  mov     [r8], ax
0x180015fa6  add     rdx, 2
0x180015faa  add     r8, 2
0x180015fae  dec     rcx
0x180015fb1  inc     r10
0x180015fb4  sub     r9, 1
0x180015fb8  jnz     short loc_180015F95
0x180015fba  xor     eax, eax
0x180015fbc  mov     [r8-2], ax
0x180015fc1  jmp     short loc_180015FDB
0x180015fc3  test    r9, r9
0x180015fc6  jz      short loc_180015FBA
0x180015fc8  xor     eax, eax
0x180015fca  sub     rdi, r10
0x180015fcd  mov     [r8], ax
0x180015fd1  cmp     rdi, 1
0x180015fd5  ja      loc_1800160E6
0x180015fdb  test    r12, r12
0x180015fde  jz      short loc_180015FF4
0x180015fe0  call    cs:__imp_GetProcessHeap
0x180015fe6  mov     r8, r12; lpMem
0x180015fe9  xor     edx, edx; dwFlags
0x180015feb  mov     rcx, rax; hHeap
0x180015fee  call    cs:__imp_HeapFree
0x180015ff4  xor     eax, eax
0x180015ff6  jmp     loc_180015F15
0x180015ffb  xor     r8d, r8d; nSize
0x180015ffe  xor     edx, edx; lpDst
0x180016000  mov     rcx, rdi; lpSrc
0x180016003  call    cs:__imp_ExpandEnvironmentStringsW
0x180016009  mov     r12d, eax
0x18001600c  test    eax, eax
0x18001600e  jz      loc_180016113
0x180016014  mov     ebx, r12d
0x180016017  add     rbx, rbx
0x18001601a  call    cs:__imp_GetProcessHeap
0x180016020  mov     r8, rbx; dwBytes
0x180016023  xor     edx, edx; dwFlags
0x180016025  mov     rcx, rax; hHeap
0x180016028  call    cs:__imp_HeapAlloc
0x18001602e  mov     r13, rax
0x180016031  test    rax, rax
0x180016034  jz      loc_180015F46
0x18001603a  mov     r8d, r12d; nSize
0x18001603d  mov     rdx, rax; lpDst
0x180016040  mov     rcx, rdi; lpSrc
0x180016043  call    cs:__imp_ExpandEnvironmentStringsW
0x180016049  mov     r14d, eax
0x18001604c  test    eax, eax
0x18001604e  jz      short loc_18001608A
0x180016050  cmp     eax, r12d
0x180016053  ja      short loc_18001608A
0x180016055  xor     r12d, r12d
0x180016058  mov     ebx, r12d
0x18001605b  call    cs:__imp_GetProcessHeap
0x180016061  mov     r8, rdi; lpMem
0x180016064  xor     edx, edx; dwFlags
0x180016066  mov     rcx, rax; hHeap
0x180016069  call    cs:__imp_HeapFree
0x18001606f  mov     rdi, r13
0x180016072  dec     r14d
0x180016075  mov     r13d, 8007000Eh
0x18001607b  jmp     loc_180015E4F
0x180016080  mov     ebx, 8007000Dh
0x180016085  jmp     loc_180015E8A
0x18001608a  mov     ebx, 8007007Ah
0x18001608f  call    cs:__imp_GetProcessHeap
0x180016095  mov     r8, r13; lpMem
0x180016098  xor     edx, edx; dwFlags
0x18001609a  mov     rcx, rax; hHeap
0x18001609d  call    cs:__imp_HeapFree
0x1800160a3  mov     r13d, 8007000Eh
0x1800160a9  jmp     loc_180015E8A
0x1800160ae  mov     rdx, rsi
0x1800160b1  lea     rcx, [rbp+var_28]
0x1800160b5  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x1800160ba  mov     ebx, eax
0x1800160bc  test    eax, eax
0x1800160be  jns     short loc_18001611B
0x1800160c0  mov     rcx, [rbp+30h]; this
0x1800160c4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x1800160cb  mov     r9d, eax; char *
0x1800160ce  mov     edx, 52h ; 'R'; void *
0x1800160d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160d8  lea     rcx, [rbp+var_28]
0x1800160dc  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800160e1  jmp     loc_180015F13
0x1800160e6  lea     r8, [rdi+rdi]
0x1800160ea  cmp     r8, 2
0x1800160ee  jbe     loc_180015FDB
0x1800160f4  add     r11, 2
0x1800160f8  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800160fc  xor     edx, edx; Val
0x1800160fe  lea     rcx, [r11+r10*2]; void *
0x180016102  call    memset_0
0x180016107  jmp     loc_180015FDB
0x18001610c  mov     [rdx], ebx
0x18001610e  jmp     loc_180015D25
0x180016113  xor     r12d, r12d
0x180016116  jmp     loc_180015E4F
0x18001611b  mov     r12, [rbp+var_28]
0x18001611f  test    r15, r15
0x180016122  jz      loc_180015FDB
0x180016128  mov     dword ptr [r15], 1
0x18001612f  jmp     loc_180015FDB
```
