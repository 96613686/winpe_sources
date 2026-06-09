# InvokeSecurePinUI(ulong,_EAPTLS_USER_PROPERTIES * *,ulong,HWND__ *)

- ea: `0x180074f94`
- end: `0x180075106`
- name: `?InvokeSecurePinUI@@YAKKPEAPEAU_EAPTLS_USER_PROPERTIES@@KPEAUHWND__@@@Z`
- size: `370`
- prototype: `unsigned int(unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074358`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180071b64`
- `0x180074a84`
- `0x180074f94`
- `0x180075a04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074ff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074ff0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800750b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800750b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800750c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800750c6`

## pseudocode

```c
__int64 __fastcall InvokeSecurePinUI(__int64 a1, struct _EAPTLS_USER_PROPERTIES **a2, unsigned int a3, HWND a4)
{
  WCHAR *v7; // rsi
  unsigned int PinForSingleCert; // ebx
  struct _EAPTLS_USER_PROPERTIES *v9; // rdx
  unsigned int v10; // eax
  _BYTE *v11; // rcx
  __int64 v12; // rax
  LPVOID pv; // [rsp+30h] [rbp-38h] BYREF
  _CREDUI_INFOW v15; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v16; // [rsp+A0h] [rbp+38h] BYREF

  pv = 0;
  v16 = 0;
  memset(&v15, 0, sizeof(v15));
  v7 = WszFromId(g_hInstance, 0x7D3u);
  if ( v7 )
  {
    v9 = *a2;
    v15.cbSize = 40;
    v15.hwndParent = a4;
    v15.pszCaptionText = v7;
    v15.hbmBanner = 0;
    PinForSingleCert = GetPinForSingleCert(&v15, v9, a3, &pv, &v16);
    if ( !PinForSingleCert )
    {
      v10 = SaveAuthBuffer(a2, (const unsigned __int8 *)pv, v16);
      PinForSingleCert = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_c4e812f99669349517681909258710e2_Traceguids, v10);
      }
    }
  }
  else
  {
    PinForSingleCert = GetLastError();
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_c4e812f99669349517681909258710e2_Traceguids);
  }
  v11 = pv;
  if ( pv )
  {
    v12 = v16;
    if ( v16 )
    {
      do
      {
        *v11++ = 0;
        --v12;
      }
      while ( v12 );
      v11 = pv;
    }
    CoTaskMemFree(v11);
  }
  LocalFree(v7);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      &WPP_c4e812f99669349517681909258710e2_Traceguids,
      PinForSingleCert);
  return PinForSingleCert;
}

```

## disassembly

```asm
0x180074f94  mov     [rsp-30h+arg_0], ecx
0x180074f98  push    rbp
0x180074f99  push    rbx
0x180074f9a  push    rsi
0x180074f9b  push    rdi
0x180074f9c  push    r12
0x180074f9e  push    r14
0x180074fa0  mov     rbp, rsp
0x180074fa3  sub     rsp, 68h
0x180074fa7  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180074fae  xorps   xmm0, xmm0
0x180074fb1  mov     rdi, rdx
0x180074fb4  mov     [rbp+pv], 0
0x180074fbc  xor     eax, eax
0x180074fbe  mov     [rbp+arg_0], 0
0x180074fc5  mov     edx, 7D3h; uID
0x180074fca  mov     [rbp+var_30.hbmBanner], rax
0x180074fce  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x180074fd2  mov     rbx, r9
0x180074fd5  mov     r14d, r8d
0x180074fd8  movups  xmmword ptr [rbp+var_30.pszMessageText], xmm0
0x180074fdc  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x180074fe1  lea     r12, WPP_GLOBAL_Control
0x180074fe8  mov     rsi, rax
0x180074feb  test    rax, rax
0x180074fee  jnz     short loc_180075023
0x180074ff0  call    cs:__imp_GetLastError
0x180074ff7  nop     dword ptr [rax+rax+00h]
0x180074ffc  mov     ebx, eax
0x180074ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180075005  cmp     rcx, r12
0x180075008  jz      loc_180075096
0x18007500e  mov     rcx, [rcx+10h]
0x180075012  lea     edx, [rsi+36h]
0x180075015  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18007501c  call    WPP_SF_
0x180075021  jmp     short loc_180075096
0x180075023  mov     rdx, [rdi]; struct _EAPTLS_USER_PROPERTIES *
0x180075026  lea     rax, [rbp+arg_0]
0x18007502a  lea     r9, [rbp+pv]; unsigned __int8 **
0x18007502e  mov     [rsp+68h+var_48], rax; unsigned int *
0x180075033  mov     r8d, r14d; unsigned int
0x180075036  mov     [rbp+var_30.cbSize], 28h ; '('
0x18007503d  lea     rcx, [rbp+var_30]; struct _CREDUI_INFOW *
0x180075041  mov     [rbp+var_30.hwndParent], rbx
0x180075045  mov     [rbp+var_30.pszCaptionText], rsi
0x180075049  mov     [rbp+var_30.hbmBanner], 0
0x180075051  call    ?GetPinForSingleCert@@YAKPEAU_CREDUI_INFOW@@PEAU_EAPTLS_USER_PROPERTIES@@KPEAPEAEPEAK@Z; GetPinForSingleCert(_CREDUI_INFOW *,_EAPTLS_USER_PROPERTIES *,ulong,uchar * *,ulong *)
0x180075056  mov     ebx, eax
0x180075058  test    eax, eax
0x18007505a  jnz     short loc_180075096
0x18007505c  mov     r8d, [rbp+arg_0]; unsigned int
0x180075060  mov     rcx, rdi; struct _EAPTLS_USER_PROPERTIES **
0x180075063  mov     rdx, [rbp+pv]; unsigned __int8 *
0x180075067  call    ?SaveAuthBuffer@@YAKPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBEK@Z; SaveAuthBuffer(_EAPTLS_USER_PROPERTIES * *,uchar const *,ulong)
0x18007506c  mov     ebx, eax
0x18007506e  test    eax, eax
0x180075070  jz      short loc_180075096
0x180075072  mov     rcx, cs:WPP_GLOBAL_Control
0x180075079  cmp     rcx, r12
0x18007507c  jz      short loc_180075096
0x18007507e  mov     rcx, [rcx+10h]
0x180075082  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180075089  mov     edx, 37h ; '7'
0x18007508e  mov     r9d, eax
0x180075091  call    WPP_SF_d
0x180075096  mov     rcx, [rbp+pv]
0x18007509a  test    rcx, rcx
0x18007509d  jz      short loc_1800750C3
0x18007509f  mov     eax, [rbp+arg_0]
0x1800750a2  test    rax, rax
0x1800750a5  jz      short loc_1800750B7
0x1800750a7  mov     byte ptr [rcx], 0
0x1800750aa  inc     rcx
0x1800750ad  sub     rax, 1
0x1800750b1  jnz     short loc_1800750A7
0x1800750b3  mov     rcx, [rbp+pv]; pv
0x1800750b7  call    cs:__imp_CoTaskMemFree
0x1800750be  nop     dword ptr [rax+rax+00h]
0x1800750c3  mov     rcx, rsi; hMem
0x1800750c6  call    cs:__imp_LocalFree
0x1800750cd  nop     dword ptr [rax+rax+00h]
0x1800750d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800750d9  cmp     rcx, r12
0x1800750dc  jz      short loc_1800750F6
0x1800750de  mov     rcx, [rcx+10h]
0x1800750e2  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800750e9  mov     edx, 38h ; '8'
0x1800750ee  mov     r9d, ebx
0x1800750f1  call    WPP_SF_d
0x1800750f6  mov     eax, ebx
0x1800750f8  add     rsp, 68h
0x1800750fc  pop     r14
0x1800750fe  pop     r12
0x180075100  pop     rdi
0x180075101  pop     rsi
0x180075102  pop     rbx
0x180075103  pop     rbp
0x180075104  retn
```
