# InvokeSecurePinUI(ulong,_EAPTLS_USER_PROPERTIES * *,ulong,HWND__ *)

- ea: `0x1800702c4`
- end: `0x180070423`
- name: `?InvokeSecurePinUI@@YAKKPEAPEAU_EAPTLS_USER_PROPERTIES@@KPEAUHWND__@@@Z`
- size: `351`
- prototype: `unsigned int(unsigned int, struct _EAPTLS_USER_PROPERTIES **, unsigned int, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f7a8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18006d2c8`
- `0x18006fe88`
- `0x1800702c4`
- `0x180070c8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070320`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800703e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800703e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800703ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800703ea`

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
0x1800702c4  mov     [rsp-30h+arg_0], ecx
0x1800702c8  push    rbp
0x1800702c9  push    rbx
0x1800702ca  push    rsi
0x1800702cb  push    rdi
0x1800702cc  push    r12
0x1800702ce  push    r14
0x1800702d0  mov     rbp, rsp
0x1800702d3  sub     rsp, 68h
0x1800702d7  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800702de  xorps   xmm0, xmm0
0x1800702e1  mov     rdi, rdx
0x1800702e4  mov     [rbp+pv], 0
0x1800702ec  xor     eax, eax
0x1800702ee  mov     [rbp+arg_0], 0
0x1800702f5  mov     edx, 7D3h; uID
0x1800702fa  mov     [rbp+var_30.hbmBanner], rax
0x1800702fe  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x180070302  mov     rbx, r9
0x180070305  mov     r14d, r8d
0x180070308  movups  xmmword ptr [rbp+var_30.pszMessageText], xmm0
0x18007030c  call    ?WszFromId@@YAPEAGPEAUHINSTANCE__@@K@Z; WszFromId(HINSTANCE__ *,ulong)
0x180070311  lea     r12, WPP_GLOBAL_Control
0x180070318  mov     rsi, rax
0x18007031b  test    rax, rax
0x18007031e  jnz     short loc_18007034D
0x180070320  call    cs:__imp_GetLastError
0x180070326  mov     ebx, eax
0x180070328  mov     rcx, cs:WPP_GLOBAL_Control
0x18007032f  cmp     rcx, r12
0x180070332  jz      loc_1800703C0
0x180070338  mov     rcx, [rcx+10h]
0x18007033c  lea     edx, [rsi+36h]
0x18007033f  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180070346  call    WPP_SF_
0x18007034b  jmp     short loc_1800703C0
0x18007034d  mov     rdx, [rdi]; struct _EAPTLS_USER_PROPERTIES *
0x180070350  lea     rax, [rbp+arg_0]
0x180070354  lea     r9, [rbp+pv]; unsigned __int8 **
0x180070358  mov     [rsp+68h+var_48], rax; unsigned int *
0x18007035d  mov     r8d, r14d; unsigned int
0x180070360  mov     [rbp+var_30.cbSize], 28h ; '('
0x180070367  lea     rcx, [rbp+var_30]; struct _CREDUI_INFOW *
0x18007036b  mov     [rbp+var_30.hwndParent], rbx
0x18007036f  mov     [rbp+var_30.pszCaptionText], rsi
0x180070373  mov     [rbp+var_30.hbmBanner], 0
0x18007037b  call    ?GetPinForSingleCert@@YAKPEAU_CREDUI_INFOW@@PEAU_EAPTLS_USER_PROPERTIES@@KPEAPEAEPEAK@Z; GetPinForSingleCert(_CREDUI_INFOW *,_EAPTLS_USER_PROPERTIES *,ulong,uchar * *,ulong *)
0x180070380  mov     ebx, eax
0x180070382  test    eax, eax
0x180070384  jnz     short loc_1800703C0
0x180070386  mov     r8d, [rbp+arg_0]; unsigned int
0x18007038a  mov     rcx, rdi; struct _EAPTLS_USER_PROPERTIES **
0x18007038d  mov     rdx, [rbp+pv]; unsigned __int8 *
0x180070391  call    ?SaveAuthBuffer@@YAKPEAPEAU_EAPTLS_USER_PROPERTIES@@PEBEK@Z; SaveAuthBuffer(_EAPTLS_USER_PROPERTIES * *,uchar const *,ulong)
0x180070396  mov     ebx, eax
0x180070398  test    eax, eax
0x18007039a  jz      short loc_1800703C0
0x18007039c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800703a3  cmp     rcx, r12
0x1800703a6  jz      short loc_1800703C0
0x1800703a8  mov     rcx, [rcx+10h]
0x1800703ac  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800703b3  mov     edx, 37h ; '7'
0x1800703b8  mov     r9d, eax
0x1800703bb  call    WPP_SF_d
0x1800703c0  mov     rcx, [rbp+pv]
0x1800703c4  test    rcx, rcx
0x1800703c7  jz      short loc_1800703E7
0x1800703c9  mov     eax, [rbp+arg_0]
0x1800703cc  test    rax, rax
0x1800703cf  jz      short loc_1800703E1
0x1800703d1  mov     byte ptr [rcx], 0
0x1800703d4  inc     rcx
0x1800703d7  sub     rax, 1
0x1800703db  jnz     short loc_1800703D1
0x1800703dd  mov     rcx, [rbp+pv]; pv
0x1800703e1  call    cs:__imp_CoTaskMemFree
0x1800703e7  mov     rcx, rsi; hMem
0x1800703ea  call    cs:__imp_LocalFree
0x1800703f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800703f7  cmp     rcx, r12
0x1800703fa  jz      short loc_180070414
0x1800703fc  mov     rcx, [rcx+10h]
0x180070400  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180070407  mov     edx, 38h ; '8'
0x18007040c  mov     r9d, ebx
0x18007040f  call    WPP_SF_d
0x180070414  mov     eax, ebx
0x180070416  add     rsp, 68h
0x18007041a  pop     r14
0x18007041c  pop     r12
0x18007041e  pop     rdi
0x18007041f  pop     rsi
0x180070420  pop     rbx
0x180070421  pop     rbp
0x180070422  retn
```
