# GetNgcApplicationTicket(unsigned __int64,unsigned __int64,_NgcTicketContext * *,_NgcTicketContext * *)

- ea: `0x18006f97c`
- end: `0x18006fcc7`
- name: `?GetNgcApplicationTicket@@YAK_K0PEAPEAU_NgcTicketContext@@1@Z`
- size: `843`
- prototype: `unsigned int __fastcall(NCRYPT_HANDLE hObject, unsigned __int64, struct _NgcTicketContext **, struct _NgcTicketContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004ddc8`

## callees

- `0x180004bd0`
- `0x180036254`
- `0x18006f97c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fadb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fb75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f9b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fa86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006f9b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fa86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006fb1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fcae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006fcae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006facd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006fb6b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006facd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18006fb6b`
- `ncrypt!NCryptGetProperty` at `0x18006fa11`
- `ncrypt!NCryptGetProperty` at `0x18006fc1e`
- `ncrypt!NCryptGetProperty` at `0x18006fa11`
- `ncrypt!NCryptGetProperty` at `0x18006fc1e`
- `ncrypt!NCryptSetProperty` at `0x18006fbbc`
- `ncrypt!NCryptSetProperty` at `0x18006fbbc`

## string_xrefs

- `0x18006f9f3`: `PinCacheApplicationTicket`
- `0x18006fc07`: `PinCacheApplicationTicket`
- `0x18006fba2`: `PinCacheApplicationImage`
- `0x18006fab2`: `%windir%\System32\lsass.exe`
- `0x18006fb5e`: `%windir%\System32\lsass.exe`

## pseudocode

```c
__int64 __fastcall GetNgcApplicationTicket(
        NCRYPT_HANDLE hObject,
        NCRYPT_KEY_HANDLE a2,
        BYTE **a3,
        struct _NgcTicketContext **a4)
{
  BYTE *v6; // rax
  BYTE *v7; // rsi
  DWORD LastError; // ebx
  WCHAR *v9; // r13
  SECURITY_STATUS Property; // eax
  int v11; // edi
  struct _NgcTicketContext **v12; // rax
  struct _NgcTicketContext *v13; // rbp
  struct _NgcTicketContext *v14; // rax
  DWORD v15; // eax
  struct _EAPTLS_CONTROL_BLOCK *v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rax
  SECURITY_STATUS v19; // eax
  SECURITY_STATUS v20; // eax
  DWORD v22; // [rsp+30h] [rbp-38h]
  size_t Size; // [rsp+38h] [rbp-30h]
  DWORD cbOutput; // [rsp+80h] [rbp+18h] BYREF
  struct _NgcTicketContext **v26; // [rsp+88h] [rbp+20h]

  v26 = a4;
  cbOutput = 0;
  *a3 = 0;
  v6 = (BYTE *)LocalAlloc(0x40u, 0x70u);
  v7 = v6;
  if ( !v6 )
    return 14;
  v9 = 0;
  memset_0(v6, 0, 0x70u);
  cbOutput = 90;
  *((_QWORD *)v7 + 12) = hObject;
  Property = NCryptGetProperty(hObject, L"PinCacheApplicationTicket", v7, cbOutput, &cbOutput, 0x40u);
  v11 = Property;
  if ( Property < 0 )
  {
    LastError = (unsigned __int16)Property;
    if ( (Property & 0x1FFF0000) != 0x70000 )
      LastError = Property;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
    *a3 = v7;
    goto LABEL_38;
  }
  v12 = v26;
  v13 = 0;
  LastError = 0;
  if ( v26 )
  {
    *v26 = 0;
    v14 = (struct _NgcTicketContext *)LocalAlloc(0x40u, 0x70u);
    v13 = v14;
    if ( !v14 )
    {
      LastError = 14;
      *a3 = v7;
      return LastError;
    }
    memset_0(v14, 0, sizeof(struct _NgcTicketContext));
    cbOutput = 90;
    v13->hKey = a2;
    v15 = ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", 0, 0);
    v22 = v15;
    if ( !v15 )
    {
      LastError = GetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = 26;
LABEL_31:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, &WPP_c4e812f99669349517681909258710e2_Traceguids, LastError);
        goto LABEL_32;
      }
      goto LABEL_32;
    }
    Size = (int)(2 * v15 + 2);
    v18 = (WCHAR *)LocalAlloc(0x40u, Size);
    v9 = v18;
    if ( !v18 )
    {
      LastError = 14;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = 27;
        goto LABEL_31;
      }
LABEL_32:
      v12 = v26;
      *a3 = v7;
LABEL_36:
      *v12 = v13;
      goto LABEL_37;
    }
    memset_0(v18, 0, Size);
    if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\lsass.exe", v9, v22 + 1) )
    {
      LastError = GetLastError();
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = 28;
        goto LABEL_31;
      }
      goto LABEL_32;
    }
    v19 = NCryptSetProperty(v13->hKey, L"PinCacheApplicationImage", (PBYTE)v9, 2 * v22 + 2, 0);
    v11 = v19;
    if ( v19 < 0 )
    {
      LastError = (unsigned __int16)v19;
      if ( (v19 & 0x1FFF0000) != 0x70000 )
        LastError = v19;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_32;
      v17 = 29;
      goto LABEL_31;
    }
    v20 = NCryptGetProperty(v13->hKey, L"PinCacheApplicationTicket", (PBYTE)v13, cbOutput, &cbOutput, 0x40u);
    v11 = v20;
    if ( v20 < 0 )
    {
      LastError = (unsigned __int16)v20;
      if ( (v20 & 0x1FFF0000) != 0x70000 )
        LastError = v20;
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v17 = 30;
        goto LABEL_31;
      }
    }
    v12 = v26;
  }
  *a3 = v7;
  if ( v13 && v12 )
    goto LABEL_36;
LABEL_37:
  if ( v11 < 0 )
  {
LABEL_38:
    if ( !LastError )
    {
      LastError = (unsigned __int16)v11;
      if ( (v11 & 0x1FFF0000) != 0x70000 )
        LastError = v11;
    }
  }
  if ( v9 )
    LocalFree(v9);
  return LastError;
}

```

## disassembly

```asm
0x18006f97c  mov     rax, rsp
0x18006f97f  mov     [rax+8], rbx
0x18006f983  mov     [rax+20h], r9
0x18006f987  mov     [rax+10h], rdx
0x18006f98b  push    rbp
0x18006f98c  push    rsi
0x18006f98d  push    rdi
0x18006f98e  push    r13
0x18006f990  push    r14
0x18006f992  sub     rsp, 40h
0x18006f996  mov     ebp, 70h ; 'p'
0x18006f99b  mov     dword ptr [rax+18h], 0
0x18006f9a2  mov     rbx, rcx
0x18006f9a5  mov     qword ptr [r8], 0
0x18006f9ac  mov     edx, ebp; uBytes
0x18006f9ae  mov     r14, r8
0x18006f9b1  lea     edi, [rbp-30h]
0x18006f9b4  mov     ecx, edi; uFlags
0x18006f9b6  call    cs:__imp_LocalAlloc
0x18006f9bc  mov     rsi, rax
0x18006f9bf  test    rax, rax
0x18006f9c2  jnz     short loc_18006F9CC
0x18006f9c4  lea     ebx, [rbp-62h]
0x18006f9c7  jmp     loc_18006FCB4
0x18006f9cc  mov     r8, rbp; Size
0x18006f9cf  xor     edx, edx; Val
0x18006f9d1  mov     rcx, rsi; void *
0x18006f9d4  xor     r13d, r13d
0x18006f9d7  call    memset_0
0x18006f9dc  mov     [rsp+68h+cbOutput], 5Ah ; 'Z'
0x18006f9e7  lea     rax, [rsp+68h+cbOutput]
0x18006f9ef  mov     [rsi+60h], rbx
0x18006f9f3  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x18006f9fa  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x18006fa02  mov     r8, rsi; pbOutput
0x18006fa05  mov     [rsp+68h+dwFlags], edi; dwFlags
0x18006fa09  mov     rcx, rbx; hObject
0x18006fa0c  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18006fa11  call    cs:__imp_NCryptGetProperty
0x18006fa17  mov     edi, eax
0x18006fa19  test    eax, eax
0x18006fa1b  jns     short loc_18006FA65
0x18006fa1d  mov     ecx, eax
0x18006fa1f  movzx   ebx, ax
0x18006fa22  and     ecx, 1FFF0000h
0x18006fa28  cmp     ecx, 70000h
0x18006fa2e  jz      short loc_18006FA32
0x18006fa30  mov     ebx, eax
0x18006fa32  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fa39  lea     rax, WPP_GLOBAL_Control
0x18006fa40  cmp     rcx, rax
0x18006fa43  jz      short loc_18006FA5D
0x18006fa45  mov     rcx, [rcx+10h]
0x18006fa49  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006fa50  mov     edx, 19h
0x18006fa55  mov     r9d, ebx
0x18006fa58  call    WPP_SF_d
0x18006fa5d  mov     [r14], rsi
0x18006fa60  jmp     loc_18006FC8F
0x18006fa65  mov     rax, [rsp+68h+arg_18]
0x18006fa6d  xor     ebp, ebp
0x18006fa6f  xor     ebx, ebx
0x18006fa71  test    rax, rax
0x18006fa74  jz      loc_18006FC7B
0x18006fa7a  lea     edx, [rbx+70h]; uBytes
0x18006fa7d  mov     [rax], rbx
0x18006fa80  lea     ecx, [rbx+40h]; uFlags
0x18006fa83  mov     rbp, rax
0x18006fa86  call    cs:__imp_LocalAlloc
0x18006fa8c  mov     rbp, rax
0x18006fa8f  test    rax, rax
0x18006fa92  jnz     short loc_18006FA9F
0x18006fa94  lea     ebx, [rax+0Eh]
0x18006fa97  mov     [r14], rsi
0x18006fa9a  jmp     loc_18006FCB4
0x18006fa9f  xor     edx, edx; Val
0x18006faa1  mov     rcx, rbp; void *
0x18006faa4  lea     r8d, [rdx+70h]; Size
0x18006faa8  call    memset_0
0x18006faad  mov     rax, [rsp+68h+arg_8]
0x18006fab2  lea     rcx, Src; "%windir%\\System32\\lsass.exe"
0x18006fab9  mov     [rsp+68h+cbOutput], 5Ah ; 'Z'
0x18006fac4  xor     r8d, r8d; nSize
0x18006fac7  xor     edx, edx; lpDst
0x18006fac9  mov     [rbp+60h], rax
0x18006facd  call    cs:__imp_ExpandEnvironmentStringsW
0x18006fad3  mov     [rsp+68h+var_38], eax
0x18006fad7  test    eax, eax
0x18006fad9  jnz     short loc_18006FB04
0x18006fadb  call    cs:__imp_GetLastError
0x18006fae1  mov     ebx, eax
0x18006fae3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006faea  lea     rax, WPP_GLOBAL_Control
0x18006faf1  cmp     rcx, rax
0x18006faf4  jz      loc_18006FC66
0x18006fafa  mov     edx, 1Ah
0x18006faff  jmp     loc_18006FC53
0x18006fb04  lea     eax, ds:2[rax*2]
0x18006fb0b  mov     ecx, 40h ; '@'; uFlags
0x18006fb10  cdqe
0x18006fb12  mov     rdx, rax; uBytes
0x18006fb15  mov     [rsp+68h+Size], rax
0x18006fb1a  call    cs:__imp_LocalAlloc
0x18006fb20  mov     r13, rax
0x18006fb23  test    rax, rax
0x18006fb26  jnz     short loc_18006FB4A
0x18006fb28  lea     ebx, [rax+0Eh]
0x18006fb2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fb32  lea     rax, WPP_GLOBAL_Control
0x18006fb39  cmp     rcx, rax
0x18006fb3c  jz      loc_18006FC66
0x18006fb42  lea     edx, [rbx+0Dh]
0x18006fb45  jmp     loc_18006FC53
0x18006fb4a  mov     r8, [rsp+68h+Size]; Size
0x18006fb4f  xor     edx, edx; Val
0x18006fb51  mov     rcx, r13; void *
0x18006fb54  call    memset_0
0x18006fb59  mov     r8d, [rsp+68h+var_38]
0x18006fb5e  lea     rcx, Src; "%windir%\\System32\\lsass.exe"
0x18006fb65  inc     r8d; nSize
0x18006fb68  mov     rdx, r13; lpDst
0x18006fb6b  call    cs:__imp_ExpandEnvironmentStringsW
0x18006fb71  test    eax, eax
0x18006fb73  jnz     short loc_18006FB9E
0x18006fb75  call    cs:__imp_GetLastError
0x18006fb7b  mov     ebx, eax
0x18006fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fb84  lea     rax, WPP_GLOBAL_Control
0x18006fb8b  cmp     rcx, rax
0x18006fb8e  jz      loc_18006FC66
0x18006fb94  mov     edx, 1Ch
0x18006fb99  jmp     loc_18006FC53
0x18006fb9e  mov     eax, [rsp+68h+var_38]
0x18006fba2  lea     rdx, aPincacheapplic; "PinCacheApplicationImage"
0x18006fba9  mov     rcx, [rbp+60h]; hObject
0x18006fbad  mov     r8, r13; pbInput
0x18006fbb0  mov     dword ptr [rsp+68h+pcbResult], ebx; dwFlags
0x18006fbb4  lea     r9d, ds:2[rax*2]; cbInput
0x18006fbbc  call    cs:__imp_NCryptSetProperty
0x18006fbc2  mov     edi, eax
0x18006fbc4  test    eax, eax
0x18006fbc6  jns     short loc_18006FBF3
0x18006fbc8  and     eax, 1FFF0000h
0x18006fbcd  movzx   ebx, di
0x18006fbd0  cmp     eax, 70000h
0x18006fbd5  jz      short loc_18006FBD9
0x18006fbd7  mov     ebx, edi
0x18006fbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fbe0  lea     rax, WPP_GLOBAL_Control
0x18006fbe7  cmp     rcx, rax
0x18006fbea  jz      short loc_18006FC66
0x18006fbec  mov     edx, 1Dh
0x18006fbf1  jmp     short loc_18006FC53
0x18006fbf3  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x18006fbfb  lea     rax, [rsp+68h+cbOutput]
0x18006fc03  mov     rcx, [rbp+60h]; hObject
0x18006fc07  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x18006fc0e  mov     [rsp+68h+dwFlags], 40h ; '@'; dwFlags
0x18006fc16  mov     r8, rbp; pbOutput
0x18006fc19  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18006fc1e  call    cs:__imp_NCryptGetProperty
0x18006fc24  mov     edi, eax
0x18006fc26  test    eax, eax
0x18006fc28  jns     short loc_18006FC73
0x18006fc2a  and     eax, 1FFF0000h
0x18006fc2f  movzx   ebx, di
0x18006fc32  cmp     eax, 70000h
0x18006fc37  jz      short loc_18006FC3B
0x18006fc39  mov     ebx, edi
0x18006fc3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fc42  lea     rax, WPP_GLOBAL_Control
0x18006fc49  cmp     rcx, rax
0x18006fc4c  jz      short loc_18006FC73
0x18006fc4e  mov     edx, 1Eh
0x18006fc53  mov     rcx, [rcx+10h]
0x18006fc57  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006fc5e  mov     r9d, ebx
0x18006fc61  call    WPP_SF_d
0x18006fc66  mov     rax, [rsp+68h+arg_18]
0x18006fc6e  mov     [r14], rsi
0x18006fc71  jmp     short loc_18006FC88
0x18006fc73  mov     rax, [rsp+68h+arg_18]
0x18006fc7b  mov     [r14], rsi
0x18006fc7e  test    rbp, rbp
0x18006fc81  jz      short loc_18006FC8B
0x18006fc83  test    rax, rax
0x18006fc86  jz      short loc_18006FC8B
0x18006fc88  mov     [rax], rbp
0x18006fc8b  test    edi, edi
0x18006fc8d  jns     short loc_18006FCA6
0x18006fc8f  test    ebx, ebx
0x18006fc91  jnz     short loc_18006FCA6
0x18006fc93  mov     eax, edi
0x18006fc95  movzx   ebx, di
0x18006fc98  and     eax, 1FFF0000h
0x18006fc9d  cmp     eax, 70000h
0x18006fca2  jz      short loc_18006FCA6
0x18006fca4  mov     ebx, edi
0x18006fca6  test    r13, r13
0x18006fca9  jz      short loc_18006FCB4
0x18006fcab  mov     rcx, r13; hMem
0x18006fcae  call    cs:__imp_LocalFree
0x18006fcb4  mov     eax, ebx
0x18006fcb6  mov     rbx, [rsp+68h+arg_0]
0x18006fcbb  add     rsp, 40h
0x18006fcbf  pop     r14
0x18006fcc1  pop     r13
0x18006fcc3  pop     rdi
0x18006fcc4  pop     rsi
0x18006fcc5  pop     rbp
0x18006fcc6  retn
```
