# GetDialInAdapterNameForRoutingDomain

- ea: `0x180035964`
- end: `0x180035b06`
- name: `GetDialInAdapterNameForRoutingDomain`
- size: `418`
- prototype: `__int64 __fastcall(struct _GUID *, void *Destination)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000eb60`
- `0x18003a4d8`
- `0x18003b090`

## callees

- `0x18002223c`
- `0x180033e90`
- `0x180035964`
- `0x180037bbc`
- `0x18004583c`
- `0x1800459e8`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180035ac7`
- `msvcrt!memcpy_s` at `0x180035ac7`
- `USER32!LoadStringW` at `0x180035a6a`
- `USER32!LoadStringW` at `0x180035a6a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035a48`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180035a48`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035a73`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180035a73`

## string_xrefs

- `0x180035a3b`: `mprmsg.dll`

## pseudocode

```c
__int64 __fastcall GetDialInAdapterNameForRoutingDomain(struct _GUID *a1, void *Destination)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  size_t v8; // rdx
  STRSAFE_LPWSTR *v9; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v12; // [rsp+28h] [rbp-D8h]
  unsigned int v13; // [rsp+30h] [rbp-D0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+50h] [rbp-B0h]
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int64 v18; // [rsp+70h] [rbp-90h]
  int v19; // [rsp+78h] [rbp-88h]
  int v20; // [rsp+7Ch] [rbp-84h]
  WCHAR Buffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[510]; // [rsp+82h] [rbp-7Eh] BYREF
  wchar_t pszSrc; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v24[510]; // [rsp+282h] [rbp+182h] BYREF

  v14 = 0;
  Buffer = 0;
  memset_0(v22, 0, sizeof(v22));
  pszSrc = 0;
  memset_0(v24, 0, sizeof(v24));
  v15 = 0;
  v16 = 0;
  v18 = 0;
  v17 = 0;
  v19 = -1;
  v20 = 0;
  if ( *((_QWORD *)&xmmword_1800710A0 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v15,
      L"GetDialInAdapterNameForRoutingDomain",
      &v14,
      v4,
      a1,
      v12,
      v13);
  if ( a1 )
  {
    Library = LoadLibraryExW(L"mprmsg.dll", 0, 0x800u);
    v7 = Library;
    if ( Library )
    {
      LoadStringW(Library, 0x4A38u, &Buffer, 256);
      FreeLibrary(v7);
    }
    else
    {
      StringCchCopyW(&Buffer, 0x100u, L"Internal");
    }
    MprConvertGuidToString(a1, 256, &pszSrc);
    if ( StringCchCatExW(&Buffer, v8, &pszSrc, v9, pcchRemaining, (DWORD)v12) >= 0 )
      v5 = memcpy_s(Destination, 0x100u, &Buffer, 0x100u);
    else
      v5 = 31;
    v14 = v5;
  }
  else
  {
    v5 = 87;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v15);
  return v5;
}

```

## disassembly

```asm
0x180035964  mov     [rsp-8+arg_10], rbx
0x180035969  mov     [rsp-8+arg_18], rsi
0x18003596e  push    rbp
0x18003596f  push    rdi
0x180035970  push    r14
0x180035972  lea     rbp, [rsp-390h]
0x18003597a  sub     rsp, 490h
0x180035981  mov     rax, cs:__security_cookie
0x180035988  xor     rax, rsp
0x18003598b  mov     [rbp+3A0h+var_20], rax
0x180035992  mov     r14, rdx
0x180035995  mov     [rsp+4A0h+var_460], 0
0x18003599d  mov     rsi, rcx
0x1800359a0  xor     eax, eax
0x1800359a2  mov     ebx, 1FEh
0x1800359a7  mov     [rbp+3A0h+Buffer], ax
0x1800359ab  mov     r8d, ebx; Size
0x1800359ae  lea     rcx, [rbp+3A0h+var_41E]; void *
0x1800359b2  xor     edx, edx; Val
0x1800359b4  call    memset_0
0x1800359b9  xor     eax, eax
0x1800359bb  lea     rcx, [rbp+3A0h+var_21E]; void *
0x1800359c2  mov     r8d, ebx; Size
0x1800359c5  mov     [rbp+3A0h+pszSrc], ax
0x1800359cc  xor     edx, edx; Val
0x1800359ce  call    memset_0
0x1800359d3  cmp     qword ptr cs:xmmword_1800710A0+8, 0
0x1800359db  xorps   xmm0, xmm0
0x1800359de  xorps   xmm1, xmm1
0x1800359e1  mov     [rsp+4A0h+var_458], 0
0x1800359ea  movdqu  [rsp+4A0h+var_450], xmm0
0x1800359f0  mov     [rsp+4A0h+var_430], 0
0x1800359f9  movdqu  [rsp+4A0h+var_440], xmm1
0x1800359ff  mov     [rsp+4A0h+var_428], 0FFFFFFFFh
0x180035a07  mov     [rsp+4A0h+var_424], 0
0x180035a0f  jz      short loc_180035A2C
0x180035a11  lea     r8, [rsp+4A0h+var_460]; unsigned int *
0x180035a16  mov     [rsp+4A0h+pcchRemaining], rsi; struct _GUID *
0x180035a1b  lea     rdx, aGetdialinadapt; "GetDialInAdapterNameForRoutingDomain"
0x180035a22  lea     rcx, [rsp+4A0h+var_458]; this
0x180035a27  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180035a2c  test    rsi, rsi
0x180035a2f  jnz     short loc_180035A39
0x180035a31  lea     ebx, [rsi+57h]
0x180035a34  jmp     loc_180035AD3
0x180035a39  xor     edx, edx; hFile
0x180035a3b  lea     rcx, LibFileName; "mprmsg.dll"
0x180035a42  mov     r8d, 800h; dwFlags
0x180035a48  call    cs:__imp_LoadLibraryExW
0x180035a4e  mov     rdi, rax
0x180035a51  mov     ebx, 100h
0x180035a56  test    rax, rax
0x180035a59  jz      short loc_180035A7B
0x180035a5b  mov     r9d, ebx; cchBufferMax
0x180035a5e  lea     r8, [rbp+3A0h+Buffer]; lpBuffer
0x180035a62  mov     edx, 4A38h; uID
0x180035a67  mov     rcx, rax; hInstance
0x180035a6a  call    cs:__imp_LoadStringW
0x180035a70  mov     rcx, rdi; hLibModule
0x180035a73  call    cs:__imp_FreeLibrary
0x180035a79  jmp     short loc_180035A8E
0x180035a7b  lea     r8, aInternal; "Internal"
0x180035a82  mov     rdx, rbx; cchDest
0x180035a85  lea     rcx, [rbp+3A0h+Buffer]; pszDest
0x180035a89  call    StringCchCopyW
0x180035a8e  lea     r8, [rbp+3A0h+pszSrc]
0x180035a95  mov     edx, ebx
0x180035a97  mov     rcx, rsi
0x180035a9a  call    MprConvertGuidToString
0x180035a9f  lea     r8, [rbp+3A0h+pszSrc]; pszSrc
0x180035aa6  lea     rcx, [rbp+3A0h+Buffer]; pszDest
0x180035aaa  call    StringCchCatExW
0x180035aaf  test    eax, eax
0x180035ab1  jns     short loc_180035ABA
0x180035ab3  mov     ebx, 1Fh
0x180035ab8  jmp     short loc_180035ACF
0x180035aba  mov     r9, rbx; SourceSize
0x180035abd  lea     r8, [rbp+3A0h+Buffer]; Source
0x180035ac1  mov     rdx, rbx; DestinationSize
0x180035ac4  mov     rcx, r14; Destination
0x180035ac7  call    cs:__imp_memcpy_s
0x180035acd  mov     ebx, eax
0x180035acf  mov     [rsp+4A0h+var_460], ebx
0x180035ad3  lea     rcx, [rsp+4A0h+var_458]; this
0x180035ad8  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180035add  mov     eax, ebx
0x180035adf  mov     rcx, [rbp+3A0h+var_20]
0x180035ae6  xor     rcx, rsp; StackCookie
0x180035ae9  call    __security_check_cookie
0x180035aee  lea     r11, [rsp+4A0h+var_10]
0x180035af6  mov     rbx, [r11+30h]
0x180035afa  mov     rsi, [r11+38h]
0x180035afe  mov     rsp, r11
0x180035b01  pop     r14
0x180035b03  pop     rdi
0x180035b04  pop     rbp
0x180035b05  retn
```
