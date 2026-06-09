# Error::IAccessibleError(IUnknown *,ushort const *,long,HWND__ *,int)

- ea: `0x18000baa0`
- end: `0x18000bc1c`
- name: `?IAccessibleError@Error@@SAXPEAUIUnknown@@PEBGJPEAUHWND__@@H@Z`
- size: `380`
- prototype: `void __usercall(struct IUnknown *@<rcx>, const unsigned __int16 *@<rdx>, int@<r8d>, HWND@<r9>, int)`
- caller_count: `14`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800042c0`
- `0x180005220`
- `0x1800056a4`
- `0x180008870`
- `0x1800097e0`
- `0x18000b580`
- `0x18000bc30`
- `0x18000c780`
- `0x18000c810`
- `0x18000c8a0`
- `0x18000cb40`
- `0x180011140`
- `0x18001ae40`
- `0x1800240a0`

## callees

- `0x18000baa0`
- `0x18000c140`
- `0x18000c318`
- `0x18001e4c0`
- `0x180047c30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000baf6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000baf6`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bbca`
- `OLEAUT32!__imp_SysAllocString` at `0x18000bbca`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb84`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb95`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb84`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bb95`
- `USER32!GetClassNameW` at `0x18000bb21`
- `USER32!GetClassNameW` at `0x18000bb21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Error::IAccessibleError(struct IUnknown *a1, const unsigned __int16 *a2, char a3, HWND a4, UINT uID)
{
  __int64 *v9; // rdi
  unsigned __int16 *v10; // rbp
  int ClassNameW; // eax
  WCHAR *v12; // rdx
  unsigned __int16 *ProviderInfo; // rax
  OLECHAR *v14; // rbx
  __int64 *v15; // r8
  __int64 *v16; // rdx
  OLECHAR *bstrString; // [rsp+40h] [rbp-3C8h]
  WCHAR ClassName[64]; // [rsp+50h] [rbp-3B8h] BYREF
  unsigned __int16 v19[128]; // [rsp+D0h] [rbp-338h] BYREF
  WCHAR Buffer[256]; // [rsp+1D0h] [rbp-238h] BYREF

  bstrString = 0;
  if ( LoadStringW(hinstResDll, uID, Buffer, 256) )
    bstrString = SysAllocString(Buffer);
  v9 = &qword_1800542E0;
  v10 = (unsigned __int16 *)&qword_1800542E0;
  if ( a4 )
  {
    ClassNameW = GetClassNameW(a4, ClassName, 64);
    v12 = (WCHAR *)L"?";
    if ( ClassNameW )
      v12 = ClassName;
    v10 = v19;
    if ( (int)StringCchPrintfW(v19, 0x80u, L"0x%08p (%s)", a4, v12) < 0 )
      v10 = (unsigned __int16 *)&qword_1800542E0;
  }
  ProviderInfo = GetProviderInfo(a1);
  v14 = ProviderInfo;
  if ( (Microsoft_Windows_OLEACCEnableBits & 1) != 0 )
  {
    v15 = &qword_1800542E0;
    if ( ProviderInfo )
      v15 = (__int64 *)ProviderInfo;
    v16 = &qword_1800542E0;
    if ( bstrString )
      v16 = (__int64 *)bstrString;
    if ( a2 )
      LODWORD(v9) = (_DWORD)a2;
    McTemplateMofU0zqzzz(
      (_DWORD)bstrString,
      (_DWORD)v16,
      (_DWORD)v15,
      (_DWORD)v9,
      a3,
      (__int64)v16,
      (__int64)v10,
      (__int64)v15);
  }
  if ( v14 )
    SysFreeString(v14);
  if ( bstrString )
    SysFreeString(bstrString);
}

```

## disassembly

```asm
0x18000baa0  mov     [rsp+arg_10], rbx
0x18000baa5  push    rbp
0x18000baa6  push    rsi
0x18000baa7  push    rdi
0x18000baa8  push    r14
0x18000baaa  push    r15
0x18000baac  sub     rsp, 3E0h
0x18000bab3  mov     rax, cs:__security_cookie
0x18000baba  xor     rax, rsp
0x18000babd  mov     [rsp+408h+var_38], rax
0x18000bac5  mov     rbx, r9
0x18000bac8  mov     r15d, r8d
0x18000bacb  mov     r14, rdx
0x18000bace  mov     rsi, rcx
0x18000bad1  mov     [rsp+408h+bstrString], 0
0x18000bada  mov     r9d, 100h; cchBufferMax
0x18000bae0  lea     r8, [rsp+408h+Buffer]; lpBuffer
0x18000bae8  mov     edx, [rsp+408h+uID]; uID
0x18000baef  mov     rcx, cs:?hinstResDll@@3PEAUHINSTANCE__@@EA; hInstance
0x18000baf6  call    cs:__imp_LoadStringW
0x18000bafc  test    eax, eax
0x18000bafe  jnz     loc_18000BBC2
0x18000bb04  lea     rdi, qword_1800542E0
0x18000bb0b  mov     rbp, rdi
0x18000bb0e  test    rbx, rbx
0x18000bb11  jz      short loc_18000BB68
0x18000bb13  mov     r8d, 40h ; '@'; nMaxCount
0x18000bb19  lea     rdx, [rsp+408h+ClassName]; lpClassName
0x18000bb1e  mov     rcx, rbx; hWnd
0x18000bb21  call    cs:__imp_GetClassNameW
0x18000bb27  lea     rdx, asc_180054300; "?"
0x18000bb2e  lea     rcx, [rsp+408h+ClassName]
0x18000bb33  test    eax, eax
0x18000bb35  cmovnz  rdx, rcx
0x18000bb39  mov     [rsp+408h+var_3E8], rdx
0x18000bb3e  mov     r9, rbx
0x18000bb41  lea     r8, a0x08pS; "0x%08p (%s)"
0x18000bb48  mov     edx, 80h; unsigned __int64
0x18000bb4d  lea     rcx, [rsp+408h+var_338]; unsigned __int16 *
0x18000bb55  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000bb5a  lea     rbp, [rsp+408h+var_338]
0x18000bb62  test    eax, eax
0x18000bb64  cmovs   rbp, rdi
0x18000bb68  mov     rcx, rsi; struct IUnknown *
0x18000bb6b  call    ?GetProviderInfo@@YAPEAGPEAUIUnknown@@@Z; GetProviderInfo(IUnknown *)
0x18000bb70  mov     rbx, rax
0x18000bb73  test    byte ptr cs:Microsoft_Windows_OLEACCEnableBits, 1
0x18000bb7a  jnz     short loc_18000BBDA
0x18000bb7c  test    rbx, rbx
0x18000bb7f  jz      short loc_18000BB8B
0x18000bb81  mov     rcx, rbx; bstrString
0x18000bb84  call    cs:__imp_SysFreeString
0x18000bb8a  nop
0x18000bb8b  mov     rcx, [rsp+408h+bstrString]; bstrString
0x18000bb90  test    rcx, rcx
0x18000bb93  jz      short loc_18000BB9B
0x18000bb95  call    cs:__imp_SysFreeString
0x18000bb9b  mov     rcx, [rsp+408h+var_38]
0x18000bba3  xor     rcx, rsp; StackCookie
0x18000bba6  call    __security_check_cookie
0x18000bbab  mov     rbx, [rsp+408h+arg_10]
0x18000bbb3  add     rsp, 3E0h
0x18000bbba  pop     r15
0x18000bbbc  pop     r14
0x18000bbbe  pop     rdi
0x18000bbbf  pop     rsi
0x18000bbc0  pop     rbp
0x18000bbc1  retn
0x18000bbc2  lea     rcx, [rsp+408h+Buffer]; psz
0x18000bbca  call    cs:__imp_SysAllocString
0x18000bbd0  mov     [rsp+408h+bstrString], rax
0x18000bbd5  jmp     loc_18000BB04
0x18000bbda  mov     r8, rdi
0x18000bbdd  test    rbx, rbx
0x18000bbe0  cmovnz  r8, rbx
0x18000bbe4  mov     rdx, rdi
0x18000bbe7  mov     rcx, [rsp+408h+bstrString]
0x18000bbec  test    rcx, rcx
0x18000bbef  cmovnz  rdx, rcx
0x18000bbf3  test    r14, r14
0x18000bbf6  cmovnz  rdi, r14
0x18000bbfa  mov     [rsp+408h+var_3D0], r8
0x18000bbff  mov     [rsp+408h+var_3D8], rbp
0x18000bc04  mov     [rsp+408h+var_3E0], rdx
0x18000bc09  mov     dword ptr [rsp+408h+var_3E8], r15d
0x18000bc0e  mov     r9, rdi
0x18000bc11  call    McTemplateMofU0zqzzz
0x18000bc16  jmp     loc_18000BB7C
```
