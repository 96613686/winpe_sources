# CpCreateDataSource

- ea: `0x18000b5f0`
- end: `0x18000b77d`
- name: `CpCreateDataSource`
- size: `397`
- prototype: `__int64 __fastcall(HWND hWnd, WORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000b9c0`

## callees

- `0x180002940`
- `0x180004bac`
- `0x180008570`
- `0x18000b5f0`
- `0x18000b850`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `USER32!SetFocus` at `0x18000b745`
- `USER32!SetFocus` at `0x18000b745`
- `COMCTL32!PropertySheetW` at `0x18000b6fd`
- `COMCTL32!PropertySheetW` at `0x18000b6fd`

## pseudocode

```c
__int64 __fastcall CpCreateDataSource(HWND hWnd, WORD a2)
{
  _BYTE *v5; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR *v6; // [rsp+28h] [rbp-D8h]
  __int64 v7; // [rsp+30h] [rbp-D0h]
  PROPSHEETHEADERW_V2 v8; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v9[2]; // [rsp+A0h] [rbp-60h] BYREF
  __m128i si128; // [rsp+B0h] [rbp-50h]
  __int64 (__fastcall *v11)(HWND); // [rsp+C8h] [rbp-38h]
  _QWORD *v12; // [rsp+D0h] [rbp-30h]
  _BYTE v13[96]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v14[24]; // [rsp+170h] [rbp+70h] BYREF
  int v15; // [rsp+188h] [rbp+88h]

  memset_0(v9, 0, 0x68u);
  memset_0(&v8, 0, sizeof(v8));
  v7 = 0;
  memset_0(v13, 0, 0x58u);
  memset_0(v14, 0, 0x230u);
  v6 = (LPCWSTR *)v13;
  v11 = DriverPageProc;
  v5 = v14;
  v9[1] = g_hResDLL;
  v8.hInstance = g_hResDLL;
  v8.ppsp = (LPCPROPSHEETPAGEW)v9;
  v12 = &v5;
  v8.pszCaption = &SubKey;
  v15 = 2;
  v9[0] = 104;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8.dwSize = 96;
  v8.dwFlags = 168;
  v8.hwndParent = hWnd;
  v8.nPages = 1;
  v8.nStartPage = 0;
  if ( PropertySheetW(&v8) == -1 )
  {
    PostInstError(11);
  }
  else if ( !(_DWORD)v7 && !SQLConfigDataSourceW(hWnd, a2, v6[4], &szAttributes) )
  {
    DisplayInstallerError(hWnd);
  }
  SetFocus(hWnd);
  return OFree(v6[4]);
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp-8+arg_10], rbx
0x18000b5f5  mov     [rsp-8+arg_18], rdi
0x18000b5fa  push    rbp
0x18000b5fb  lea     rbp, [rsp-2B0h]
0x18000b603  sub     rsp, 3B0h
0x18000b60a  mov     rax, cs:__security_cookie
0x18000b611  xor     rax, rsp
0x18000b614  mov     [rbp+2B0h+var_10], rax
0x18000b61b  movzx   edi, dx
0x18000b61e  mov     rbx, rcx
0x18000b621  xor     edx, edx; Val
0x18000b623  lea     rcx, [rbp+2B0h+var_310]; void *
0x18000b627  lea     r8d, [rdx+68h]; Size
0x18000b62b  call    memset_0
0x18000b630  xor     edx, edx; Val
0x18000b632  lea     rcx, [rsp+3B0h+var_370]; void *
0x18000b637  lea     r8d, [rdx+60h]; Size
0x18000b63b  call    memset_0
0x18000b640  xor     edx, edx; Val
0x18000b642  mov     [rsp+3B0h+var_380], 0
0x18000b64b  lea     rcx, [rbp+2B0h+var_2A0]; void *
0x18000b64f  lea     r8d, [rdx+58h]; Size
0x18000b653  call    memset_0
0x18000b658  xor     edx, edx; Val
0x18000b65a  lea     rcx, [rbp+2B0h+var_240]; void *
0x18000b65e  mov     r8d, 230h; Size
0x18000b664  call    memset_0
0x18000b669  movdqa  xmm0, cs:__xmm@00000000000000000000000000000600
0x18000b671  lea     rax, [rbp+2B0h+var_2A0]
0x18000b675  mov     [rsp+3B0h+var_388], rax
0x18000b67a  lea     rcx, DriverPageProc
0x18000b681  mov     [rbp+2B0h+var_2E8], rcx
0x18000b685  lea     rax, [rbp+2B0h+var_240]
0x18000b689  mov     [rsp+3B0h+var_390], rax
0x18000b68e  lea     rcx, [rsp+3B0h+var_390]
0x18000b693  mov     rax, cs:g_hResDLL
0x18000b69a  mov     [rbp+2B0h+var_308], rax
0x18000b69e  mov     [rsp+3B0h+var_370.hInstance], rax
0x18000b6a3  lea     rax, [rbp+2B0h+var_310]
0x18000b6a7  mov     qword ptr [rsp+3B0h+var_370.38h], rax
0x18000b6ac  lea     rax, SubKey
0x18000b6b3  mov     [rbp+2B0h+var_2E0], rcx
0x18000b6b7  lea     rcx, [rsp+3B0h+var_370]; LPCPROPSHEETHEADERW
0x18000b6bc  mov     [rsp+3B0h+var_370.pszCaption], rax
0x18000b6c1  mov     [rbp+2B0h+var_228], 2
0x18000b6cb  mov     [rbp+2B0h+var_310], 68h ; 'h'
0x18000b6d3  movdqa  [rbp+2B0h+var_300], xmm0
0x18000b6d8  mov     [rsp+3B0h+var_370.dwSize], 60h ; '`'
0x18000b6e0  mov     [rsp+3B0h+var_370.dwFlags], 0A8h
0x18000b6e8  mov     [rsp+3B0h+var_370.hwndParent], rbx
0x18000b6ed  mov     [rsp+3B0h+var_370.nPages], 1
0x18000b6f5  mov     dword ptr [rsp+3B0h+var_370.30h], 0
0x18000b6fd  call    cs:__imp_PropertySheetW
0x18000b703  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b707  jnz     short loc_18000B713
0x18000b709  lea     ecx, [rax+0Ch]
0x18000b70c  call    PostInstError
0x18000b711  jmp     short loc_18000B742
0x18000b713  cmp     dword ptr [rsp+3B0h+var_380], 0
0x18000b718  jnz     short loc_18000B742
0x18000b71a  mov     r8, [rsp+3B0h+var_388]
0x18000b71f  lea     r9, szAttributes; lpszAttributes
0x18000b726  movzx   edx, di; fRequest
0x18000b729  mov     rcx, rbx; hwndParent
0x18000b72c  mov     r8, [r8+20h]; lpszDriver
0x18000b730  call    SQLConfigDataSourceW
0x18000b735  cmp     eax, 1
0x18000b738  jz      short loc_18000B742
0x18000b73a  mov     rcx, rbx; hWnd
0x18000b73d  call    DisplayInstallerError
0x18000b742  mov     rcx, rbx; hWnd
0x18000b745  call    cs:__imp_SetFocus
0x18000b74b  mov     rcx, [rsp+3B0h+var_388]
0x18000b750  mov     rcx, [rcx+20h]
0x18000b754  call    OFree
0x18000b759  mov     rcx, [rbp+2B0h+var_10]
0x18000b760  xor     rcx, rsp; StackCookie
0x18000b763  call    __security_check_cookie
0x18000b768  lea     r11, [rsp+3B0h+var_s0]
0x18000b770  mov     rbx, [r11+20h]
0x18000b774  mov     rdi, [r11+28h]
0x18000b778  mov     rsp, r11
0x18000b77b  pop     rbp
0x18000b77c  retn
```
