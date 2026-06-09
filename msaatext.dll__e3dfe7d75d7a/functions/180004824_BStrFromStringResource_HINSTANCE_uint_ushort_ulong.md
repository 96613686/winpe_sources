# BStrFromStringResource(HINSTANCE__ *,uint,ushort,ulong &)

- ea: `0x180004824`
- end: `0x180004984`
- name: `?BStrFromStringResource@@YAPEAGPEAUHINSTANCE__@@IGAEAK@Z`
- size: `352`
- prototype: `unsigned __int16 *__fastcall(HINSTANCE hModule, unsigned int, unsigned __int16, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800049a0`
- `0x1800049d0`
- `0x180004d10`

## callees

- `0x180004824`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004969`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180004969`
- `KERNEL32!FindResourceW` at `0x18000491f`
- `KERNEL32!FindResourceW` at `0x18000491f`
- `KERNEL32!LoadResource` at `0x180004930`
- `KERNEL32!LoadResource` at `0x180004930`
- `KERNEL32!FindResourceExW` at `0x180004905`
- `KERNEL32!FindResourceExW` at `0x180004905`
- `KERNEL32!EnumResourceLanguagesW` at `0x180004872`
- `KERNEL32!EnumResourceLanguagesW` at `0x1800048ba`
- `KERNEL32!EnumResourceLanguagesW` at `0x180004872`
- `KERNEL32!EnumResourceLanguagesW` at `0x1800048ba`
- `KERNEL32!LockResource` at `0x18000493e`
- `KERNEL32!LockResource` at `0x18000493e`
- `KERNEL32!GetThreadLocale` at `0x18000488d`
- `KERNEL32!GetThreadLocale` at `0x18000488d`
- `KERNEL32!GetLastError` at `0x180004910`
- `KERNEL32!GetLastError` at `0x180004910`

## pseudocode

```c
BSTR __fastcall BStrFromStringResource(HINSTANCE hModule, unsigned int a2, unsigned __int16 a3, unsigned int *a4)
{
  unsigned int v4; // ebx
  const WCHAR *v5; // r14
  char v7; // di
  unsigned __int16 v9; // ax
  unsigned __int16 ThreadLocale; // bp
  unsigned int v11; // ecx
  HRSRC Resource; // rax
  HGLOBAL v13; // rax
  unsigned __int16 *v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // edi
  LONG_PTR lParam; // [rsp+90h] [rbp+18h] BYREF

  v4 = a3;
  LOWORD(lParam) = a3;
  v5 = (const WCHAR *)(unsigned __int16)((a2 >> 4) + 1);
  v7 = a2;
  EnumResourceLanguagesW(hModule, (LPCWSTR)6, v5, EnumResLangProc, (LONG_PTR)&lParam);
  v9 = lParam;
  if ( (_WORD)lParam )
  {
    if ( (_WORD)lParam == (_WORD)v4 )
    {
      ThreadLocale = GetThreadLocale();
      LOWORD(lParam) = ThreadLocale;
      EnumResourceLanguagesW(hModule, (LPCWSTR)6, (LPCWSTR)(unsigned int)v5, EnumResLangProc, (LONG_PTR)&lParam);
      v9 = lParam;
      if ( (_WORD)lParam == ThreadLocale )
        return 0;
      if ( !(_WORD)lParam )
      {
        v9 = ThreadLocale;
        LOWORD(lParam) = ThreadLocale;
      }
    }
    v11 = v9;
  }
  else
  {
    LOWORD(lParam) = v4;
    v11 = v4;
  }
  *a4 = v11;
  Resource = FindResourceExW(hModule, (LPCWSTR)6, v5, v4);
  if ( !Resource )
  {
    GetLastError();
    Resource = FindResourceW(hModule, v5, (LPCWSTR)6);
    if ( !Resource )
      return 0;
  }
  v13 = LoadResource(hModule, Resource);
  if ( !v13 )
    return 0;
  v14 = (unsigned __int16 *)LockResource(v13);
  if ( !v14 )
    return 0;
  v15 = 0;
  v16 = v7 & 0xF;
  if ( v16 )
  {
    do
    {
      ++v15;
      v14 += *v14 + 1;
    }
    while ( v15 < v16 );
  }
  return SysAllocStringLen(v14 + 1, *v14);
}

```

## disassembly

```asm
0x180004824  mov     r11, rsp
0x180004827  push    rbx
0x180004828  push    rbp
0x180004829  push    rsi
0x18000482a  push    rdi
0x18000482b  push    r12
0x18000482d  push    r13
0x18000482f  push    r14
0x180004831  push    r15
0x180004833  sub     rsp, 38h
0x180004837  mov     eax, edx
0x180004839  movzx   ebx, r8w
0x18000483d  shr     eax, 4
0x180004840  mov     ebp, 1
0x180004845  add     ax, bp
0x180004848  mov     [r11+18h], bx
0x18000484d  movzx   r14d, ax
0x180004851  mov     r15, r9
0x180004854  lea     rax, [r11+18h]
0x180004858  mov     edi, edx
0x18000485a  lea     r13d, [rbp+5]
0x18000485e  mov     [r11-58h], rax
0x180004862  mov     r8d, r14d; lpName
0x180004865  lea     r9, ?EnumResLangProc@@YAHPEAUHINSTANCE__@@PEBG1G_J@Z; lpEnumFunc
0x18000486c  mov     edx, r13d; lpType
0x18000486f  mov     rsi, rcx
0x180004872  call    cs:__imp_EnumResourceLanguagesW
0x180004878  movzx   eax, word ptr [rsp+78h+arg_10]
0x180004880  xor     r12d, r12d
0x180004883  test    ax, ax
0x180004886  jz      short loc_1800048EB
0x180004888  cmp     ax, bx
0x18000488b  jnz     short loc_1800048E6
0x18000488d  call    cs:__imp_GetThreadLocale
0x180004893  lea     r9, ?EnumResLangProc@@YAHPEAUHINSTANCE__@@PEBG1G_J@Z; lpEnumFunc
0x18000489a  mov     r8d, r14d; lpName
0x18000489d  mov     ebp, eax
0x18000489f  mov     edx, r13d; lpType
0x1800048a2  lea     rax, [rsp+78h+arg_10]
0x1800048aa  mov     word ptr [rsp+78h+arg_10], bp
0x1800048b2  mov     rcx, rsi; hModule
0x1800048b5  mov     [rsp+78h+lParam], rax; lParam
0x1800048ba  call    cs:__imp_EnumResourceLanguagesW
0x1800048c0  movzx   eax, word ptr [rsp+78h+arg_10]
0x1800048c8  cmp     ax, bp
0x1800048cb  jz      loc_180004971
0x1800048d1  test    ax, ax
0x1800048d4  jnz     short loc_1800048E1
0x1800048d6  movzx   eax, bp
0x1800048d9  mov     word ptr [rsp+78h+arg_10], ax
0x1800048e1  mov     ebp, 1
0x1800048e6  movzx   ecx, ax
0x1800048e9  jmp     short loc_1800048F5
0x1800048eb  mov     word ptr [rsp+78h+arg_10], bx
0x1800048f3  mov     ecx, ebx
0x1800048f5  mov     [r15], ecx
0x1800048f8  movzx   r9d, bx; wLanguage
0x1800048fc  mov     rcx, rsi; hModule
0x1800048ff  mov     r8, r14; lpName
0x180004902  mov     rdx, r13; lpType
0x180004905  call    cs:__imp_FindResourceExW
0x18000490b  test    rax, rax
0x18000490e  jnz     short loc_18000492A
0x180004910  call    cs:__imp_GetLastError
0x180004916  mov     r8, r13; lpType
0x180004919  mov     rdx, r14; lpName
0x18000491c  mov     rcx, rsi; hModule
0x18000491f  call    cs:__imp_FindResourceW
0x180004925  test    rax, rax
0x180004928  jz      short loc_180004971
0x18000492a  mov     rdx, rax; hResInfo
0x18000492d  mov     rcx, rsi; hModule
0x180004930  call    cs:__imp_LoadResource
0x180004936  test    rax, rax
0x180004939  jz      short loc_180004971
0x18000493b  mov     rcx, rax; hResData
0x18000493e  call    cs:__imp_LockResource
0x180004944  test    rax, rax
0x180004947  jz      short loc_180004971
0x180004949  mov     edx, r12d
0x18000494c  and     edi, 0Fh
0x18000494f  jbe     short loc_180004962
0x180004951  movzx   ecx, word ptr [rax]
0x180004954  add     edx, ebp
0x180004956  lea     rax, [rax+rcx*2]
0x18000495a  add     rax, 2
0x18000495e  cmp     edx, edi
0x180004960  jb      short loc_180004951
0x180004962  movzx   edx, word ptr [rax]; ui
0x180004965  lea     rcx, [rax+2]; strIn
0x180004969  call    cs:__imp_SysAllocStringLen
0x18000496f  jmp     short loc_180004973
0x180004971  xor     eax, eax
0x180004973  add     rsp, 38h
0x180004977  pop     r15
0x180004979  pop     r14
0x18000497b  pop     r13
0x18000497d  pop     r12
0x18000497f  pop     rdi
0x180004980  pop     rsi
0x180004981  pop     rbp
0x180004982  pop     rbx
0x180004983  retn
```
