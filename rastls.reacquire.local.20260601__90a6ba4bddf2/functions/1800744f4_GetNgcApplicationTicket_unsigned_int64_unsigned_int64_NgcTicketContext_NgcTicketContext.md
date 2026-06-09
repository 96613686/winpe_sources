# GetNgcApplicationTicket(unsigned __int64,unsigned __int64,_NgcTicketContext * *,_NgcTicketContext * *)

- ea: `0x1800744f4`
- end: `0x180074886`
- name: `?GetNgcApplicationTicket@@YAK_K0PEAPEAU_NgcTicketContext@@1@Z`
- size: `914`
- prototype: `unsigned int __fastcall(NCRYPT_HANDLE hObject, unsigned __int64, struct _NgcTicketContext **, struct _NgcTicketContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800508d4`

## callees

- `0x180005010`
- `0x180038e64`
- `0x1800744f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007466b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007466b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074717`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007452e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007460a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800746b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007452e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007460a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800746b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074866`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180074657`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180074707`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180074657`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180074707`
- `ncrypt!NCryptGetProperty` at `0x18007458f`
- `ncrypt!NCryptGetProperty` at `0x1800747d0`
- `ncrypt!NCryptGetProperty` at `0x18007458f`
- `ncrypt!NCryptGetProperty` at `0x1800747d0`
- `ncrypt!NCryptSetProperty` at `0x180074764`
- `ncrypt!NCryptSetProperty` at `0x180074764`

## string_xrefs

- `0x18007463c`: `%windir%\System32\lsass.exe`
- `0x1800746fa`: `%windir%\System32\lsass.exe`
- `0x180074571`: `PinCacheApplicationTicket`
- `0x1800747b9`: `PinCacheApplicationTicket`
- `0x18007474a`: `PinCacheApplicationImage`

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
0x1800744f4  mov     rax, rsp
0x1800744f7  mov     [rax+8], rbx
0x1800744fb  mov     [rax+20h], r9
0x1800744ff  mov     [rax+10h], rdx
0x180074503  push    rbp
0x180074504  push    rsi
0x180074505  push    rdi
0x180074506  push    r13
0x180074508  push    r14
0x18007450a  sub     rsp, 40h
0x18007450e  mov     ebp, 70h ; 'p'
0x180074513  mov     dword ptr [rax+18h], 0
0x18007451a  mov     rbx, rcx
0x18007451d  mov     qword ptr [r8], 0
0x180074524  mov     edx, ebp; uBytes
0x180074526  mov     r14, r8
0x180074529  lea     edi, [rbp-30h]
0x18007452c  mov     ecx, edi; uFlags
0x18007452e  call    cs:__imp_LocalAlloc
0x180074535  nop     dword ptr [rax+rax+00h]
0x18007453a  mov     rsi, rax
0x18007453d  test    rax, rax
0x180074540  jnz     short loc_18007454A
0x180074542  lea     ebx, [rbp-62h]
0x180074545  jmp     loc_180074872
0x18007454a  mov     r8, rbp; Size
0x18007454d  xor     edx, edx; Val
0x18007454f  mov     rcx, rsi; void *
0x180074552  xor     r13d, r13d
0x180074555  call    memset_0
0x18007455a  mov     [rsp+68h+cbOutput], 5Ah ; 'Z'
0x180074565  lea     rax, [rsp+68h+cbOutput]
0x18007456d  mov     [rsi+60h], rbx
0x180074571  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x180074578  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x180074580  mov     r8, rsi; pbOutput
0x180074583  mov     [rsp+68h+dwFlags], edi; dwFlags
0x180074587  mov     rcx, rbx; hObject
0x18007458a  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18007458f  call    cs:__imp_NCryptGetProperty
0x180074596  nop     dword ptr [rax+rax+00h]
0x18007459b  mov     edi, eax
0x18007459d  test    eax, eax
0x18007459f  jns     short loc_1800745E9
0x1800745a1  mov     ecx, eax
0x1800745a3  movzx   ebx, ax
0x1800745a6  and     ecx, 1FFF0000h
0x1800745ac  cmp     ecx, 70000h
0x1800745b2  jz      short loc_1800745B6
0x1800745b4  mov     ebx, eax
0x1800745b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800745bd  lea     rax, WPP_GLOBAL_Control
0x1800745c4  cmp     rcx, rax
0x1800745c7  jz      short loc_1800745E1
0x1800745c9  mov     rcx, [rcx+10h]
0x1800745cd  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800745d4  mov     edx, 19h
0x1800745d9  mov     r9d, ebx
0x1800745dc  call    WPP_SF_d
0x1800745e1  mov     [r14], rsi
0x1800745e4  jmp     loc_180074847
0x1800745e9  mov     rax, [rsp+68h+arg_18]
0x1800745f1  xor     ebp, ebp
0x1800745f3  xor     ebx, ebx
0x1800745f5  test    rax, rax
0x1800745f8  jz      loc_180074833
0x1800745fe  lea     edx, [rbx+70h]; uBytes
0x180074601  mov     [rax], rbx
0x180074604  lea     ecx, [rbx+40h]; uFlags
0x180074607  mov     rbp, rax
0x18007460a  call    cs:__imp_LocalAlloc
0x180074611  nop     dword ptr [rax+rax+00h]
0x180074616  mov     rbp, rax
0x180074619  test    rax, rax
0x18007461c  jnz     short loc_180074629
0x18007461e  lea     ebx, [rax+0Eh]
0x180074621  mov     [r14], rsi
0x180074624  jmp     loc_180074872
0x180074629  xor     edx, edx; Val
0x18007462b  mov     rcx, rbp; void *
0x18007462e  lea     r8d, [rdx+70h]; Size
0x180074632  call    memset_0
0x180074637  mov     rax, [rsp+68h+arg_8]
0x18007463c  lea     rcx, Src; "%windir%\\System32\\lsass.exe"
0x180074643  mov     [rsp+68h+cbOutput], 5Ah ; 'Z'
0x18007464e  xor     r8d, r8d; nSize
0x180074651  xor     edx, edx; lpDst
0x180074653  mov     [rbp+60h], rax
0x180074657  call    cs:__imp_ExpandEnvironmentStringsW
0x18007465e  nop     dword ptr [rax+rax+00h]
0x180074663  mov     [rsp+68h+var_38], eax
0x180074667  test    eax, eax
0x180074669  jnz     short loc_18007469A
0x18007466b  call    cs:__imp_GetLastError
0x180074672  nop     dword ptr [rax+rax+00h]
0x180074677  mov     ebx, eax
0x180074679  mov     rcx, cs:WPP_GLOBAL_Control
0x180074680  lea     rax, WPP_GLOBAL_Control
0x180074687  cmp     rcx, rax
0x18007468a  jz      loc_18007481E
0x180074690  mov     edx, 1Ah
0x180074695  jmp     loc_18007480B
0x18007469a  lea     eax, ds:2[rax*2]
0x1800746a1  mov     ecx, 40h ; '@'; uFlags
0x1800746a6  cdqe
0x1800746a8  mov     rdx, rax; uBytes
0x1800746ab  mov     [rsp+68h+Size], rax
0x1800746b0  call    cs:__imp_LocalAlloc
0x1800746b7  nop     dword ptr [rax+rax+00h]
0x1800746bc  mov     r13, rax
0x1800746bf  test    rax, rax
0x1800746c2  jnz     short loc_1800746E6
0x1800746c4  lea     ebx, [rax+0Eh]
0x1800746c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800746ce  lea     rax, WPP_GLOBAL_Control
0x1800746d5  cmp     rcx, rax
0x1800746d8  jz      loc_18007481E
0x1800746de  lea     edx, [rbx+0Dh]
0x1800746e1  jmp     loc_18007480B
0x1800746e6  mov     r8, [rsp+68h+Size]; Size
0x1800746eb  xor     edx, edx; Val
0x1800746ed  mov     rcx, r13; void *
0x1800746f0  call    memset_0
0x1800746f5  mov     r8d, [rsp+68h+var_38]
0x1800746fa  lea     rcx, Src; "%windir%\\System32\\lsass.exe"
0x180074701  inc     r8d; nSize
0x180074704  mov     rdx, r13; lpDst
0x180074707  call    cs:__imp_ExpandEnvironmentStringsW
0x18007470e  nop     dword ptr [rax+rax+00h]
0x180074713  test    eax, eax
0x180074715  jnz     short loc_180074746
0x180074717  call    cs:__imp_GetLastError
0x18007471e  nop     dword ptr [rax+rax+00h]
0x180074723  mov     ebx, eax
0x180074725  mov     rcx, cs:WPP_GLOBAL_Control
0x18007472c  lea     rax, WPP_GLOBAL_Control
0x180074733  cmp     rcx, rax
0x180074736  jz      loc_18007481E
0x18007473c  mov     edx, 1Ch
0x180074741  jmp     loc_18007480B
0x180074746  mov     eax, [rsp+68h+var_38]
0x18007474a  lea     rdx, aPincacheapplic; "PinCacheApplicationImage"
0x180074751  mov     rcx, [rbp+60h]; hObject
0x180074755  mov     r8, r13; pbInput
0x180074758  mov     dword ptr [rsp+68h+pcbResult], ebx; dwFlags
0x18007475c  lea     r9d, ds:2[rax*2]; cbInput
0x180074764  call    cs:__imp_NCryptSetProperty
0x18007476b  nop     dword ptr [rax+rax+00h]
0x180074770  mov     edi, eax
0x180074772  test    eax, eax
0x180074774  jns     short loc_1800747A5
0x180074776  and     eax, 1FFF0000h
0x18007477b  movzx   ebx, di
0x18007477e  cmp     eax, 70000h
0x180074783  jz      short loc_180074787
0x180074785  mov     ebx, edi
0x180074787  mov     rcx, cs:WPP_GLOBAL_Control
0x18007478e  lea     rax, WPP_GLOBAL_Control
0x180074795  cmp     rcx, rax
0x180074798  jz      loc_18007481E
0x18007479e  mov     edx, 1Dh
0x1800747a3  jmp     short loc_18007480B
0x1800747a5  mov     r9d, [rsp+68h+cbOutput]; cbOutput
0x1800747ad  lea     rax, [rsp+68h+cbOutput]
0x1800747b5  mov     rcx, [rbp+60h]; hObject
0x1800747b9  lea     rdx, aPincacheapplic_0; "PinCacheApplicationTicket"
0x1800747c0  mov     [rsp+68h+dwFlags], 40h ; '@'; dwFlags
0x1800747c8  mov     r8, rbp; pbOutput
0x1800747cb  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800747d0  call    cs:__imp_NCryptGetProperty
0x1800747d7  nop     dword ptr [rax+rax+00h]
0x1800747dc  mov     edi, eax
0x1800747de  test    eax, eax
0x1800747e0  jns     short loc_18007482B
0x1800747e2  and     eax, 1FFF0000h
0x1800747e7  movzx   ebx, di
0x1800747ea  cmp     eax, 70000h
0x1800747ef  jz      short loc_1800747F3
0x1800747f1  mov     ebx, edi
0x1800747f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800747fa  lea     rax, WPP_GLOBAL_Control
0x180074801  cmp     rcx, rax
0x180074804  jz      short loc_18007482B
0x180074806  mov     edx, 1Eh
0x18007480b  mov     rcx, [rcx+10h]
0x18007480f  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180074816  mov     r9d, ebx
0x180074819  call    WPP_SF_d
0x18007481e  mov     rax, [rsp+68h+arg_18]
0x180074826  mov     [r14], rsi
0x180074829  jmp     short loc_180074840
0x18007482b  mov     rax, [rsp+68h+arg_18]
0x180074833  mov     [r14], rsi
0x180074836  test    rbp, rbp
0x180074839  jz      short loc_180074843
0x18007483b  test    rax, rax
0x18007483e  jz      short loc_180074843
0x180074840  mov     [rax], rbp
0x180074843  test    edi, edi
0x180074845  jns     short loc_18007485E
0x180074847  test    ebx, ebx
0x180074849  jnz     short loc_18007485E
0x18007484b  mov     eax, edi
0x18007484d  movzx   ebx, di
0x180074850  and     eax, 1FFF0000h
0x180074855  cmp     eax, 70000h
0x18007485a  jz      short loc_18007485E
0x18007485c  mov     ebx, edi
0x18007485e  test    r13, r13
0x180074861  jz      short loc_180074872
0x180074863  mov     rcx, r13; hMem
0x180074866  call    cs:__imp_LocalFree
0x18007486d  nop     dword ptr [rax+rax+00h]
0x180074872  mov     eax, ebx
0x180074874  mov     rbx, [rsp+68h+arg_0]
0x180074879  add     rsp, 40h
0x18007487d  pop     r14
0x18007487f  pop     r13
0x180074881  pop     rdi
0x180074882  pop     rsi
0x180074883  pop     rbp
0x180074884  retn
```
