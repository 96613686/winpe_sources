# GetDialInAdapterNameForRoutingDomain

- ea: `0x180041464`
- end: `0x180041626`
- name: `GetDialInAdapterNameForRoutingDomain`
- size: `450`
- prototype: `__int64 __fastcall(struct _GUID *, void *Destination)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180045e68`
- `0x180046858`

## callees

- `0x1800302d0`
- `0x180041464`
- `0x18004326c`
- `0x180050b2c`
- `0x180050be8`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800415e8`
- `msvcrt!memcpy_s` at `0x1800415e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004155a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004155a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041563`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041563`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041538`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041538`

## string_xrefs

- `0x18004152b`: `mprmsg.dll`

## pseudocode

```c
__int64 __fastcall GetDialInAdapterNameForRoutingDomain(struct _GUID *a1, void *Destination)
{
  void (*v4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  unsigned int v5; // ebx
  HMODULE Library; // rax
  HMODULE v7; // rdi
  __int64 v8; // rdx
  const wchar_t *v9; // r9
  __int64 v10; // r8
  WCHAR *p_Buffer; // rax
  WCHAR *v12; // rdx
  size_t v13; // rdx
  STRSAFE_LPWSTR *v14; // r9
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  DWORD v17; // [rsp+28h] [rbp-D8h]
  unsigned int v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+70h] [rbp-90h]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  WCHAR Buffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[510]; // [rsp+82h] [rbp-7Eh] BYREF
  wchar_t pszSrc; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v28[510]; // [rsp+282h] [rbp+182h] BYREF

  v18 = 0;
  Buffer = 0;
  memset_0(v26, 0, sizeof(v26));
  pszSrc = 0;
  memset_0(v28, 0, sizeof(v28));
  v19 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180078C60 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v19,
      L"GetDialInAdapterNameForRoutingDomain",
      &v18,
      v4,
      a1);
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
      v8 = 2147483646;
      v9 = L"Internal";
      v10 = 256;
      p_Buffer = &Buffer;
      do
      {
        if ( !v8 )
          break;
        if ( !*v9 )
          break;
        *p_Buffer++ = *v9++;
        --v8;
        --v10;
      }
      while ( v10 );
      v12 = p_Buffer - 1;
      if ( v10 )
        v12 = p_Buffer;
      *v12 = 0;
    }
    MprConvertGuidToString(a1, 256, &pszSrc);
    if ( StringCchCatExW(&Buffer, v13, &pszSrc, v14, pcchRemaining, v17) >= 0 )
      v5 = memcpy_s(Destination, 0x100u, &Buffer, 0x100u);
    else
      v5 = 31;
    v18 = v5;
  }
  else
  {
    v5 = 87;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v5;
}

```

## disassembly

```asm
0x180041464  mov     [rsp-8+arg_10], rbx
0x180041469  push    rbp
0x18004146a  push    rsi
0x18004146b  push    rdi
0x18004146c  push    r14
0x18004146e  push    r15
0x180041470  lea     rbp, [rsp-390h]
0x180041478  sub     rsp, 490h
0x18004147f  mov     rax, cs:__security_cookie
0x180041486  xor     rax, rsp
0x180041489  mov     [rbp+3B0h+var_30], rax
0x180041490  mov     r14, rdx
0x180041493  mov     rsi, rcx
0x180041496  xor     r15d, r15d
0x180041499  lea     rcx, [rbp+3B0h+var_42E]; void *
0x18004149d  mov     ebx, 1FEh
0x1800414a2  mov     [rsp+4B0h+var_470], r15d
0x1800414a7  mov     r8d, ebx; Size
0x1800414aa  mov     [rbp+3B0h+Buffer], r15w
0x1800414af  xor     edx, edx; Val
0x1800414b1  call    memset_0
0x1800414b6  mov     r8d, ebx; Size
0x1800414b9  mov     [rbp+3B0h+pszSrc], r15w
0x1800414c1  xor     edx, edx; Val
0x1800414c3  lea     rcx, [rbp+3B0h+var_22E]; void *
0x1800414ca  call    memset_0
0x1800414cf  cmp     qword ptr cs:xmmword_180078C60+8, r15
0x1800414d6  xorps   xmm0, xmm0
0x1800414d9  xorps   xmm1, xmm1
0x1800414dc  mov     [rsp+4B0h+var_468], r15
0x1800414e1  movdqu  [rsp+4B0h+var_460], xmm0
0x1800414e7  mov     [rsp+4B0h+var_440], r15
0x1800414ec  movdqu  [rsp+4B0h+var_450], xmm1
0x1800414f2  mov     [rsp+4B0h+var_438], 0FFFFFFFFh
0x1800414fa  mov     [rsp+4B0h+var_434], r15d
0x1800414ff  jz      short loc_18004151C
0x180041501  lea     r8, [rsp+4B0h+var_470]; unsigned int *
0x180041506  mov     [rsp+4B0h+pcchRemaining], rsi; struct _GUID *
0x18004150b  lea     rdx, aGetdialinadapt; "GetDialInAdapterNameForRoutingDomain"
0x180041512  lea     rcx, [rsp+4B0h+var_468]; this
0x180041517  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18004151c  test    rsi, rsi
0x18004151f  jnz     short loc_180041529
0x180041521  lea     ebx, [rsi+57h]
0x180041524  jmp     loc_1800415F4
0x180041529  xor     edx, edx; hFile
0x18004152b  lea     rcx, LibFileName; "mprmsg.dll"
0x180041532  mov     r8d, 800h; dwFlags
0x180041538  call    cs:__imp_LoadLibraryExW
0x18004153e  mov     rdi, rax
0x180041541  mov     ebx, 100h
0x180041546  test    rax, rax
0x180041549  jz      short loc_18004156B
0x18004154b  mov     r9d, ebx; cchBufferMax
0x18004154e  lea     r8, [rbp+3B0h+Buffer]; lpBuffer
0x180041552  mov     edx, 4A38h; uID
0x180041557  mov     rcx, rax; hInstance
0x18004155a  call    cs:__imp_LoadStringW
0x180041560  mov     rcx, rdi; hLibModule
0x180041563  call    cs:__imp_FreeLibrary
0x180041569  jmp     short loc_1800415AF
0x18004156b  mov     edx, 7FFFFFFEh
0x180041570  lea     r9, aInternal; "Internal"
0x180041577  mov     r8, rbx
0x18004157a  lea     rax, [rbp+3B0h+Buffer]
0x18004157e  test    rdx, rdx
0x180041581  jz      short loc_1800415A0
0x180041583  movzx   ecx, word ptr [r9]
0x180041587  test    cx, cx
0x18004158a  jz      short loc_1800415A0
0x18004158c  mov     [rax], cx
0x18004158f  add     r9, 2
0x180041593  add     rax, 2
0x180041597  dec     rdx
0x18004159a  sub     r8, 1
0x18004159e  jnz     short loc_18004157E
0x1800415a0  test    r8, r8
0x1800415a3  lea     rdx, [rax-2]
0x1800415a7  cmovnz  rdx, rax
0x1800415ab  mov     [rdx], r15w
0x1800415af  lea     r8, [rbp+3B0h+pszSrc]
0x1800415b6  mov     edx, ebx
0x1800415b8  mov     rcx, rsi
0x1800415bb  call    MprConvertGuidToString
0x1800415c0  lea     r8, [rbp+3B0h+pszSrc]; pszSrc
0x1800415c7  lea     rcx, [rbp+3B0h+Buffer]; pszDest
0x1800415cb  call    StringCchCatExW
0x1800415d0  test    eax, eax
0x1800415d2  jns     short loc_1800415DB
0x1800415d4  mov     ebx, 1Fh
0x1800415d9  jmp     short loc_1800415F0
0x1800415db  mov     r9, rbx; SourceSize
0x1800415de  lea     r8, [rbp+3B0h+Buffer]; Source
0x1800415e2  mov     rdx, rbx; DestinationSize
0x1800415e5  mov     rcx, r14; Destination
0x1800415e8  call    cs:__imp_memcpy_s
0x1800415ee  mov     ebx, eax
0x1800415f0  mov     [rsp+4B0h+var_470], ebx
0x1800415f4  lea     rcx, [rsp+4B0h+var_468]; this
0x1800415f9  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800415fe  mov     eax, ebx
0x180041600  mov     rcx, [rbp+3B0h+var_30]
0x180041607  xor     rcx, rsp; StackCookie
0x18004160a  call    __security_check_cookie
0x18004160f  mov     rbx, [rsp+4B0h+arg_10]
0x180041617  add     rsp, 490h
0x18004161e  pop     r15
0x180041620  pop     r14
0x180041622  pop     rdi
0x180041623  pop     rsi
0x180041624  pop     rbp
0x180041625  retn
```
