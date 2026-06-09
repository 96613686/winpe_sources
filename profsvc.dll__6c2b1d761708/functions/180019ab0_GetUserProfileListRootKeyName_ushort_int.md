# GetUserProfileListRootKeyName(ushort * *,int *)

- ea: `0x180019ab0`
- end: `0x180019f6b`
- name: `?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z`
- size: `1211`
- prototype: `__int64 __fastcall(unsigned __int16 **, int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019594`
- `0x18001984c`
- `0x18002fa8c`
- `0x180037544`
- `0x18003797c`

## callees

- `0x18000e1a0`
- `0x180019ab0`
- `0x18001a0f0`
- `0x180030ad0`
- `0x18003c870`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019bb8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e3b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019bb8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019d5a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019e3b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019c6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ece`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019c6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ece`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019eba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c58`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019c9b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e27`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019eba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019b08`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019bef`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019c7c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019e0a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019e5c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019e0a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180019e5c`

## string_xrefs

- `0x180019ccc`: `onecore\internal\ds\inc\profiles\sid.h`
- `0x180019efb`: `onecore\internal\ds\inc\profiles\sid.h`

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
    v36 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(&v38, a1);
    v17 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
        (const char *)(unsigned int)v36,
        phkResult);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v38);
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
0x180019ab0  push    rbp
0x180019ab2  push    rbx
0x180019ab3  push    rsi
0x180019ab4  push    r12
0x180019ab6  push    r13
0x180019ab8  push    r15
0x180019aba  mov     rbp, rsp
0x180019abd  sub     rsp, 58h
0x180019ac1  xor     ebx, ebx
0x180019ac3  mov     r15, rdx
0x180019ac6  mov     [rcx], rbx
0x180019ac9  mov     rsi, rcx
0x180019acc  test    rdx, rdx
0x180019acf  jnz     loc_180019F43
0x180019ad5  lea     rax, [rbp+hKey]
0x180019ad9  mov     [rbp+var_28], rbx
0x180019add  mov     r9d, 20019h; samDesired
0x180019ae3  mov     [rsp+58h+phkResult], rax; phkResult
0x180019ae8  xor     r8d, r8d; ulOptions
0x180019aeb  mov     [rbp+var_20], rbx
0x180019aef  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pro"...
0x180019af6  mov     [rbp+var_18], rbx
0x180019afa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019b01  mov     [rbp+hKey], rbx
0x180019b05  mov     r12, rbx
0x180019b08  call    cs:__imp_RegOpenKeyExW
0x180019b0f  nop     dword ptr [rax+rax+00h]
0x180019b14  test    eax, eax
0x180019b16  jg      loc_180019D1E
0x180019b1c  mov     [rsp+58h+arg_18], rdi
0x180019b24  mov     r13d, 8007000Eh
0x180019b2a  test    eax, eax
0x180019b2c  js      loc_180019C9B
0x180019b32  lea     rax, [rbp+cbData]
0x180019b36  mov     [rsp+58h+var_8], r14
0x180019b3b  mov     r14, [rbp+hKey]
0x180019b3f  lea     r9, [rbp+Type]; lpType
0x180019b43  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180019b48  lea     rdx, aRedirectionkey; "RedirectionKey"
0x180019b4f  mov     rcx, r14; hKey
0x180019b52  mov     [rbp+Type], ebx
0x180019b55  xor     r8d, r8d; lpReserved
0x180019b58  mov     [rbp+cbData], ebx
0x180019b5b  mov     rdi, rbx
0x180019b5e  mov     [rsp+58h+phkResult], rbx; lpData
0x180019b63  call    cs:__imp_RegQueryValueExW
0x180019b6a  nop     dword ptr [rax+rax+00h]
0x180019b6f  mov     ebx, eax
0x180019b71  test    eax, eax
0x180019b73  jg      loc_180019D2B
0x180019b79  test    ebx, ebx
0x180019b7b  js      loc_180019C58
0x180019b81  mov     eax, [rbp+Type]
0x180019b84  dec     eax
0x180019b86  cmp     eax, 1
0x180019b89  ja      loc_180019EAB
0x180019b8f  mov     eax, [rbp+cbData]
0x180019b92  test    eax, eax
0x180019b94  jz      loc_180019EAB
0x180019b9a  test    al, 1
0x180019b9c  jnz     loc_180019EAB
0x180019ba2  mov     ebx, eax
0x180019ba4  call    cs:__imp_GetProcessHeap
0x180019bab  nop     dword ptr [rax+rax+00h]
0x180019bb0  mov     r8d, ebx; dwBytes
0x180019bb3  xor     edx, edx; dwFlags
0x180019bb5  mov     rcx, rax; hHeap
0x180019bb8  call    cs:__imp_HeapAlloc
0x180019bbf  nop     dword ptr [rax+rax+00h]
0x180019bc4  mov     rdi, rax
0x180019bc7  test    rax, rax
0x180019bca  jz      loc_180019D3F
0x180019bd0  lea     rax, [rbp+cbData]
0x180019bd4  xor     r8d, r8d; lpReserved
0x180019bd7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180019bdc  lea     r9, [rbp+Type]; lpType
0x180019be0  lea     rdx, aRedirectionkey; "RedirectionKey"
0x180019be7  mov     [rsp+58h+phkResult], rdi; int
0x180019bec  mov     rcx, r14; hKey
0x180019bef  call    cs:__imp_RegQueryValueExW
0x180019bf6  nop     dword ptr [rax+rax+00h]
0x180019bfb  mov     ebx, eax
0x180019bfd  test    eax, eax
0x180019bff  jg      loc_180019D47
0x180019c05  test    ebx, ebx
0x180019c07  js      short loc_180019C58
0x180019c09  mov     r14d, [rbp+cbData]
0x180019c0d  shr     r14d, 1
0x180019c10  dec     r14d
0x180019c13  cmp     [rbp+Type], 2
0x180019c17  jz      loc_180019E02
0x180019c1d  cmp     word ptr [rdi+r14*2], 0
0x180019c23  jnz     loc_180019EAB
0x180019c29  mov     [rbp+var_20], r12
0x180019c2d  mov     [rbp+var_18], r12
0x180019c31  test    rdi, rdi
0x180019c34  jz      short loc_180019C55
0x180019c36  lea     eax, [r14+1]
0x180019c3a  mov     ecx, eax
0x180019c3c  test    eax, eax
0x180019c3e  jz      short loc_180019C55
0x180019c40  dec     rax
0x180019c43  mov     [rbp+var_28], rdi
0x180019c47  mov     [rbp+var_20], rax
0x180019c4b  mov     [rbp+var_18], rcx
0x180019c4f  mov     [rdi+rcx*2-2], r12w
0x180019c55  mov     rdi, r12
0x180019c58  call    cs:__imp_GetProcessHeap
0x180019c5f  nop     dword ptr [rax+rax+00h]
0x180019c64  mov     r8, rdi; lpMem
0x180019c67  xor     edx, edx; dwFlags
0x180019c69  mov     rcx, rax; hHeap
0x180019c6c  call    cs:__imp_HeapFree
0x180019c73  nop     dword ptr [rax+rax+00h]
0x180019c78  mov     rcx, [rbp+hKey]; hKey
0x180019c7c  call    cs:__imp_RegCloseKey
0x180019c83  nop     dword ptr [rax+rax+00h]
0x180019c88  mov     r14, [rsp+58h+var_8]
0x180019c8d  test    ebx, ebx
0x180019c8f  jns     loc_180019EE5
0x180019c95  mov     r12, [rbp+var_28]
0x180019c99  xor     ebx, ebx
0x180019c9b  call    cs:__imp_GetProcessHeap
0x180019ca2  nop     dword ptr [rax+rax+00h]
0x180019ca7  mov     edi, 39h ; '9'
0x180019cac  mov     [rsi], rbx
0x180019caf  mov     rcx, rax; hHeap
0x180019cb2  mov     eax, 2
0x180019cb7  mul     rdi
0x180019cba  test    rdx, rdx
0x180019cbd  jz      loc_180019D55
0x180019cc3  mov     ebx, 80070216h
0x180019cc8  mov     rcx, [rbp+30h]; this
0x180019ccc  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x180019cd3  mov     r9d, ebx; char *
0x180019cd6  mov     edx, 5Ah ; 'Z'; void *
0x180019cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ce0  test    r12, r12
0x180019ce3  jz      short loc_180019D05
0x180019ce5  call    cs:__imp_GetProcessHeap
0x180019cec  nop     dword ptr [rax+rax+00h]
0x180019cf1  mov     r8, r12; lpMem
0x180019cf4  xor     edx, edx; dwFlags
0x180019cf6  mov     rcx, rax; hHeap
0x180019cf9  call    cs:__imp_HeapFree
0x180019d00  nop     dword ptr [rax+rax+00h]
0x180019d05  mov     eax, ebx
0x180019d07  mov     rdi, [rsp+58h+arg_18]
0x180019d0f  add     rsp, 58h
0x180019d13  pop     r15
0x180019d15  pop     r13
0x180019d17  pop     r12
0x180019d19  pop     rsi
0x180019d1a  pop     rbx
0x180019d1b  pop     rbp
0x180019d1c  retn
0x180019d1e  movzx   eax, ax
0x180019d21  or      eax, 80070000h
0x180019d26  jmp     loc_180019B1C
0x180019d2b  movzx   ebx, ax
0x180019d2e  or      ebx, 80070000h
0x180019d34  jmp     loc_180019B79
0x180019d39  mov     r13d, 8007000Eh
0x180019d3f  mov     ebx, r13d
0x180019d42  jmp     loc_180019C58
0x180019d47  movzx   ebx, ax
0x180019d4a  or      ebx, 80070000h
0x180019d50  jmp     loc_180019C05
0x180019d55  mov     r8, rax; dwBytes
0x180019d58  xor     edx, edx; dwFlags
0x180019d5a  call    cs:__imp_HeapAlloc
0x180019d61  nop     dword ptr [rax+rax+00h]
0x180019d66  test    rax, rax
0x180019d69  mov     [rsi], rax
0x180019d6c  mov     r8, rax
0x180019d6f  cmovz   ebx, r13d
0x180019d73  jz      loc_180019CC8
0x180019d79  mov     ecx, 38h ; '8'
0x180019d7e  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x180019d85  mov     r9, rdi
0x180019d88  xor     r10d, r10d
0x180019d8b  mov     r11, rax
0x180019d8e  xchg    ax, ax
0x180019d90  test    rcx, rcx
0x180019d93  jz      short loc_180019DC3
0x180019d95  movzx   eax, word ptr [rdx]
0x180019d98  test    ax, ax
0x180019d9b  jz      short loc_180019DBE
0x180019d9d  mov     [r8], ax
0x180019da1  add     rdx, 2
0x180019da5  add     r8, 2
0x180019da9  dec     rcx
0x180019dac  inc     r10
0x180019daf  sub     r9, 1
0x180019db3  jnz     short loc_180019D90
0x180019db5  xor     eax, eax
0x180019db7  mov     [r8-2], ax
0x180019dbc  jmp     short loc_180019DD6
0x180019dbe  test    r9, r9
0x180019dc1  jz      short loc_180019DB5
0x180019dc3  xor     eax, eax
0x180019dc5  sub     rdi, r10
0x180019dc8  mov     [r8], ax
0x180019dcc  cmp     rdi, 1
0x180019dd0  ja      loc_180019F1D
0x180019dd6  test    r12, r12
0x180019dd9  jz      short loc_180019DFB
0x180019ddb  call    cs:__imp_GetProcessHeap
0x180019de2  nop     dword ptr [rax+rax+00h]
0x180019de7  mov     r8, r12; lpMem
0x180019dea  xor     edx, edx; dwFlags
0x180019dec  mov     rcx, rax; hHeap
0x180019def  call    cs:__imp_HeapFree
0x180019df6  nop     dword ptr [rax+rax+00h]
0x180019dfb  xor     eax, eax
0x180019dfd  jmp     loc_180019D07
0x180019e02  xor     r8d, r8d; nSize
0x180019e05  xor     edx, edx; lpDst
0x180019e07  mov     rcx, rdi; lpSrc
0x180019e0a  call    cs:__imp_ExpandEnvironmentStringsW
0x180019e11  nop     dword ptr [rax+rax+00h]
0x180019e16  mov     r12d, eax
0x180019e19  test    eax, eax
0x180019e1b  jz      loc_180019F4A
0x180019e21  mov     ebx, r12d
0x180019e24  add     rbx, rbx
0x180019e27  call    cs:__imp_GetProcessHeap
0x180019e2e  nop     dword ptr [rax+rax+00h]
0x180019e33  mov     r8, rbx; dwBytes
0x180019e36  xor     edx, edx; dwFlags
0x180019e38  mov     rcx, rax; hHeap
0x180019e3b  call    cs:__imp_HeapAlloc
0x180019e42  nop     dword ptr [rax+rax+00h]
0x180019e47  mov     r13, rax
0x180019e4a  test    rax, rax
0x180019e4d  jz      loc_180019D39
0x180019e53  mov     r8d, r12d; nSize
0x180019e56  mov     rdx, rax; lpDst
0x180019e59  mov     rcx, rdi; lpSrc
0x180019e5c  call    cs:__imp_ExpandEnvironmentStringsW
0x180019e63  nop     dword ptr [rax+rax+00h]
0x180019e68  mov     r14d, eax
0x180019e6b  test    eax, eax
0x180019e6d  jz      short loc_180019EB5
0x180019e6f  cmp     eax, r12d
0x180019e72  ja      short loc_180019EB5
0x180019e74  xor     r12d, r12d
0x180019e77  mov     ebx, r12d
0x180019e7a  call    cs:__imp_GetProcessHeap
0x180019e81  nop     dword ptr [rax+rax+00h]
0x180019e86  mov     r8, rdi; lpMem
0x180019e89  xor     edx, edx; dwFlags
0x180019e8b  mov     rcx, rax; hHeap
0x180019e8e  call    cs:__imp_HeapFree
0x180019e95  nop     dword ptr [rax+rax+00h]
0x180019e9a  mov     rdi, r13
0x180019e9d  dec     r14d
0x180019ea0  mov     r13d, 8007000Eh
0x180019ea6  jmp     loc_180019C1D
0x180019eab  mov     ebx, 8007000Dh
0x180019eb0  jmp     loc_180019C58
0x180019eb5  mov     ebx, 8007007Ah
0x180019eba  call    cs:__imp_GetProcessHeap
0x180019ec1  nop     dword ptr [rax+rax+00h]
0x180019ec6  mov     r8, r13; lpMem
0x180019ec9  xor     edx, edx; dwFlags
0x180019ecb  mov     rcx, rax; hHeap
0x180019ece  call    cs:__imp_HeapFree
0x180019ed5  nop     dword ptr [rax+rax+00h]
0x180019eda  mov     r13d, 8007000Eh
0x180019ee0  jmp     loc_180019C58
0x180019ee5  mov     rdx, rsi
0x180019ee8  lea     rcx, [rbp+var_28]
0x180019eec  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180019ef1  mov     ebx, eax
0x180019ef3  test    eax, eax
0x180019ef5  jns     short loc_180019F52
0x180019ef7  mov     rcx, [rbp+30h]; this
0x180019efb  lea     r8, aOnecoreInterna_3; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x180019f02  mov     r9d, eax; char *
0x180019f05  mov     edx, 52h ; 'R'; void *
0x180019f0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f0f  lea     rcx, [rbp+var_28]
0x180019f13  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019f18  jmp     loc_180019D05
0x180019f1d  lea     r8, [rdi+rdi]
0x180019f21  cmp     r8, 2
0x180019f25  jbe     loc_180019DD6
0x180019f2b  add     r11, 2
0x180019f2f  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180019f33  xor     edx, edx; Val
0x180019f35  lea     rcx, [r11+r10*2]; void *
0x180019f39  call    memset_0
0x180019f3e  jmp     loc_180019DD6
0x180019f43  mov     [rdx], ebx
0x180019f45  jmp     loc_180019AD5
0x180019f4a  xor     r12d, r12d
0x180019f4d  jmp     loc_180019C1D
0x180019f52  mov     r12, [rbp+var_28]
0x180019f56  test    r15, r15
  ... truncated ...
```
