# CTxtRange::GetText(ushort * *)

- ea: `0x1800b61b0`
- end: `0x1800b640f`
- name: `?GetText@CTxtRange@@UEAAJPEAPEAG@Z`
- size: `607`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18000f358`
- `0x1800436a0`
- `0x180043e7c`
- `0x180043f84`
- `0x1800441ac`
- `0x18005921c`
- `0x1800b61b0`
- `0x1800b6418`
- `0x1800e3244`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b637e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b637e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b635c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b635c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b62de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b62de`

## string_xrefs

- `0x1800b634f`: `oleaut32.dll`

## pseudocode

```c
__int64 __fastcall CTxtRange::GetText(CTxtRange *this, unsigned __int16 **a2)
{
  __int64 v2; // rax
  int v5; // edi
  __int64 v6; // rcx
  __int64 (__fastcall *v7)(_QWORD, _QWORD); // rax
  unsigned int v8; // r14d
  int v9; // r15d
  unsigned __int16 *v10; // rdi
  __m128i v11; // xmm1
  __int64 v12; // rdx
  __int64 v13; // rcx
  WCHAR *v14; // rdi
  UINT32 v15; // eax
  __int64 result; // rax
  HMODULE Library; // rax
  CTxtEdit *v18; // rcx
  __int128 v19; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h]
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  PCNZWCH sourceString; // [rsp+90h] [rbp+40h] BYREF

  v2 = *((_QWORD *)this + 3);
  if ( !v2 || !*(_QWORD *)(v2 + 40) )
    return 2147746303LL;
  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 26);
  if ( !v5 )
    return 0;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 40);
  if ( (*(_BYTE *)(v6 + 176) & 0x10) != 0 && (*(_DWORD *)(v6 + 280) & 0x800) == 0 )
    return 2147500037LL;
  if ( (unsigned int)CTxtEdit::IsPlaceHolderStorySelected((CTxtEdit *)v6) )
    return 0;
  v7 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1802E26E8;
  v8 = -v5;
  if ( v5 > 0 )
    v8 = v5;
  v9 = *((_DWORD *)this + 10) - v5;
  if ( v5 < 0 )
    v9 = *((_DWORD *)this + 10);
  if ( !qword_1802E26E8 )
  {
    CWriteLock::CWriteLock(&string, 0);
    if ( !qword_1802E26E8 )
    {
      Library = qword_1802E4270;
      if ( qword_1802E4270 || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (qword_1802E4270 = Library) != 0) )
        qword_1802E26E8 = (__int64)GetProcAddress(Library, "SysAllocStringLen");
    }
    CWriteLock::~CWriteLock((CWriteLock *)&string);
    v7 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1802E26E8;
    if ( !qword_1802E26E8 )
    {
      sourceString = 0;
      return 2147942414LL;
    }
  }
  sourceString = (PCNZWCH)v7(0, v8);
  v10 = (unsigned __int16 *)sourceString;
  if ( !sourceString )
    return 2147942414LL;
  v11 = (__m128i)*((unsigned __int64 *)this + 5);
  v19 = *(_OWORD *)((char *)this + 24);
  v20 = v11.m128i_i64[0];
  CTxtPtr::Move((CTxtPtr *)&v19, v9 - _mm_cvtsi128_si32(v11));
  CTxtPtr::GetText((CTxtPtr *)&v19, v8, v10);
  v12 = *((_QWORD *)this + 3);
  if ( v12 )
    v13 = *(_QWORD *)(v12 + 40);
  else
    v13 = 0;
  if ( !*(_QWORD *)(v13 + 576)
    || ((string = 0, !v12) ? (v18 = 0) : (v18 = *(CTxtEdit **)(v12 + 40)),
        result = CTxtEdit::HostFilter(v18, 0x56Du, 0, (__int64)&sourceString, (__int64 *)&string),
        (int)result >= 0) )
  {
    v14 = (WCHAR *)sourceString;
    if ( (*((_DWORD *)this + 29) & 0x100000) != 0 )
    {
      string = 0;
      v15 = CW32System::SysStringLen((unsigned __int16 *)sourceString);
      WindowsCreateString(v14, v15, &string);
      *a2 = (unsigned __int16 *)string;
      CW32System::SysFreeString(v14);
    }
    else
    {
      *a2 = (unsigned __int16 *)sourceString;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b61b0  mov     [rsp-28h+arg_8], rbx
0x1800b61b5  push    rbp
0x1800b61b6  push    rsi
0x1800b61b7  push    rdi
0x1800b61b8  push    r14
0x1800b61ba  push    r15
0x1800b61bc  mov     rbp, rsp
0x1800b61bf  sub     rsp, 50h
0x1800b61c3  mov     rax, [rcx+18h]
0x1800b61c7  mov     rsi, rdx
0x1800b61ca  mov     rbx, rcx
0x1800b61cd  test    rax, rax
0x1800b61d0  jz      loc_1800B63B8
0x1800b61d6  cmp     qword ptr [rax+28h], 0
0x1800b61db  jz      loc_1800B63B8
0x1800b61e1  test    rdx, rdx
0x1800b61e4  jz      loc_1800B6405
0x1800b61ea  mov     qword ptr [rdx], 0
0x1800b61f1  mov     edi, [rcx+68h]
0x1800b61f4  test    edi, edi
0x1800b61f6  jz      loc_1800B62F9
0x1800b61fc  mov     rcx, [rcx+18h]
0x1800b6200  test    rcx, rcx
0x1800b6203  jz      short loc_1800B6209
0x1800b6205  mov     rcx, [rcx+28h]; this
0x1800b6209  test    byte ptr [rcx+0B0h], 10h
0x1800b6210  jnz     loc_1800B6315
0x1800b6216  call    ?IsPlaceHolderStorySelected@CTxtEdit@@QEAAHXZ; CTxtEdit::IsPlaceHolderStorySelected(void)
0x1800b621b  test    eax, eax
0x1800b621d  jnz     loc_1800B62F9
0x1800b6223  mov     r15d, [rbx+28h]
0x1800b6227  mov     r14d, edi
0x1800b622a  mov     rax, cs:qword_1802E26E8
0x1800b6231  neg     r14d
0x1800b6234  cmovs   r14d, edi
0x1800b6238  sub     r15d, edi
0x1800b623b  test    edi, edi
0x1800b623d  cmovs   r15d, [rbx+28h]
0x1800b6242  test    rax, rax
0x1800b6245  jz      loc_1800B632C
0x1800b624b  mov     edx, r14d
0x1800b624e  xor     ecx, ecx
0x1800b6250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6255  mov     [rbp+sourceString], rax
0x1800b6259  mov     rdi, rax
0x1800b625c  test    rax, rax
0x1800b625f  jz      loc_1800B63AE
0x1800b6265  movsd   xmm1, qword ptr [rbx+28h]
0x1800b626a  lea     rcx, [rbp+var_20]; this
0x1800b626e  movups  xmm0, xmmword ptr [rbx+18h]
0x1800b6272  movd    eax, xmm1
0x1800b6276  movups  [rbp+var_20], xmm0
0x1800b627a  sub     r15d, eax
0x1800b627d  movsd   [rbp+var_10], xmm1
0x1800b6282  mov     edx, r15d; int
0x1800b6285  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x1800b628a  mov     r8, rdi; unsigned __int16 *
0x1800b628d  lea     rcx, [rbp+var_20]; this
0x1800b6291  mov     edx, r14d; int
0x1800b6294  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x1800b6299  mov     rdx, [rbx+18h]
0x1800b629d  test    rdx, rdx
0x1800b62a0  jz      loc_1800B63C2
0x1800b62a6  mov     rcx, [rdx+28h]
0x1800b62aa  cmp     qword ptr [rcx+240h], 0
0x1800b62b2  jnz     loc_1800B63C9
0x1800b62b8  test    dword ptr [rbx+74h], 100000h
0x1800b62bf  mov     rdi, [rbp+sourceString]
0x1800b62c3  jz      short loc_1800B6310
0x1800b62c5  mov     rcx, rdi; unsigned __int16 *
0x1800b62c8  mov     [rbp+string], 0
0x1800b62d0  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1800b62d5  mov     edx, eax; length
0x1800b62d7  lea     r8, [rbp+string]; string
0x1800b62db  mov     rcx, rdi; sourceString
0x1800b62de  call    cs:__imp_WindowsCreateString
0x1800b62e5  nop     dword ptr [rax+rax+00h]
0x1800b62ea  mov     rax, [rbp+string]
0x1800b62ee  mov     rcx, rdi; unsigned __int16 *
0x1800b62f1  mov     [rsi], rax
0x1800b62f4  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800b62f9  xor     eax, eax
0x1800b62fb  mov     rbx, [rsp+50h+arg_8]
0x1800b6303  add     rsp, 50h
0x1800b6307  pop     r15
0x1800b6309  pop     r14
0x1800b630b  pop     rdi
0x1800b630c  pop     rsi
0x1800b630d  pop     rbp
0x1800b630e  retn
0x1800b6310  mov     [rsi], rdi
0x1800b6313  jmp     short loc_1800B62F9
0x1800b6315  test    dword ptr [rcx+118h], 800h
0x1800b631f  jnz     loc_1800B6216
0x1800b6325  mov     eax, 80004005h
0x1800b632a  jmp     short loc_1800B62FB
0x1800b632c  xor     edx, edx
0x1800b632e  lea     rcx, [rbp+string]
0x1800b6332  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800b6337  cmp     cs:qword_1802E26E8, 0
0x1800b633f  jnz     short loc_1800B6391
0x1800b6341  mov     rax, cs:qword_1802E4270
0x1800b6348  test    rax, rax
0x1800b634b  jnz     short loc_1800B6374
0x1800b634d  xor     edx, edx; hFile
0x1800b634f  lea     rcx, aOleaut32Dll_0; "oleaut32.dll"
0x1800b6356  mov     r8d, 800h; dwFlags
0x1800b635c  call    cs:__imp_LoadLibraryExW
0x1800b6363  nop     dword ptr [rax+rax+00h]
0x1800b6368  mov     cs:qword_1802E4270, rax
0x1800b636f  test    rax, rax
0x1800b6372  jz      short loc_1800B6391
0x1800b6374  lea     rdx, aSysallocstring_0; "SysAllocStringLen"
0x1800b637b  mov     rcx, rax; hModule
0x1800b637e  call    cs:__imp_GetProcAddress
0x1800b6385  nop     dword ptr [rax+rax+00h]
0x1800b638a  mov     cs:qword_1802E26E8, rax
0x1800b6391  lea     rcx, [rbp+string]; this
0x1800b6395  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800b639a  mov     rax, cs:qword_1802E26E8
0x1800b63a1  test    rax, rax
0x1800b63a4  jnz     loc_1800B624B
0x1800b63aa  mov     [rbp+sourceString], rax
0x1800b63ae  mov     eax, 8007000Eh
0x1800b63b3  jmp     loc_1800B62FB
0x1800b63b8  mov     eax, 800401FFh
0x1800b63bd  jmp     loc_1800B62FB
0x1800b63c2  xor     ecx, ecx
0x1800b63c4  jmp     loc_1800B62AA
0x1800b63c9  mov     [rbp+string], 0
0x1800b63d1  test    rdx, rdx
0x1800b63d4  jz      short loc_1800B6401
0x1800b63d6  mov     rcx, [rdx+28h]; this
0x1800b63da  lea     rax, [rbp+string]
0x1800b63de  xor     r8d, r8d; unsigned __int64
0x1800b63e1  lea     r9, [rbp+sourceString]; __int64
0x1800b63e5  mov     [rsp+50h+var_30], rax; __int64 *
0x1800b63ea  mov     edx, 56Dh; unsigned int
0x1800b63ef  call    ?HostFilter@CTxtEdit@@QEAAJI_K_JPEA_J@Z; CTxtEdit::HostFilter(uint,unsigned __int64,__int64,__int64 *)
0x1800b63f4  test    eax, eax
0x1800b63f6  js      loc_1800B62FB
0x1800b63fc  jmp     loc_1800B62B8
0x1800b6401  xor     ecx, ecx
0x1800b6403  jmp     short loc_1800B63DA
0x1800b6405  mov     eax, 80070057h
0x1800b640a  jmp     loc_1800B62FB
```
