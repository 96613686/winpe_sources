# Win32LiveSystemProvider::GetAuxiliaryProviderFromImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)

- ea: `0x180012404`
- end: `0x18001259c`
- name: `?GetAuxiliaryProviderFromImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z`
- size: `408`
- prototype: `__int64 __usercall@<rax>(Win32LiveSystemProvider *__hidden this@<rcx>, HINSTANCE@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011430`

## callees

- `0x180012404`
- `0x1800125a4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012512`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180012512`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x180012465`
- `api-ms-win-core-libraryloader-l1-1-0!LoadResource` at `0x180012465`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180012477`
- `api-ms-win-core-libraryloader-l1-1-0!LockResource` at `0x180012477`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001256f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001255b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001255b`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::GetAuxiliaryProviderFromImageResource(
        Win32LiveSystemProvider *this,
        HINSTANCE a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        int *a6)
{
  __int64 (__fastcall *v6)(HINSTANCE, const char *, __int64); // rax
  const unsigned __int16 *v8; // rsi
  HRSRC v11; // rax
  HGLOBAL Resource; // rax
  const CHAR *v13; // rbp
  signed int result; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rcx
  wchar_t *v19; // rax
  __int64 v20; // rax
  bool v21; // sf

  v6 = (__int64 (__fastcall *)(HINSTANCE, const char *, __int64))*((_QWORD *)this + 49);
  v8 = a3;
  *a6 = 0;
  if ( !v6 )
    return Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(this, a2, a3, a4, a5, a6);
  v11 = (HRSRC)v6(a2, "MINIDUMP_AUXILIARY_PROVIDER", 10);
  if ( v11 )
  {
    Resource = LoadResource(a2, v11);
    if ( Resource )
    {
      v13 = (const CHAR *)LockResource(Resource);
      if ( v13 )
      {
        if ( !a5 )
          return Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(this, a2, a3, a4, a5, a6);
        if ( a5 > 0x7FFFFFFFuLL )
        {
          *a4 = 0;
          return Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(this, a2, a3, a4, a5, a6);
        }
        v15 = 2147483646;
        v16 = a5;
        v17 = a4;
        do
        {
          if ( !v15 )
            break;
          a3 = (const unsigned __int16 *)*v8;
          if ( !(_WORD)a3 )
            break;
          *v17 = (unsigned __int16)a3;
          ++v8;
          ++v17;
          --v15;
          --v16;
        }
        while ( v16 );
        v18 = v17 - 1;
        if ( v16 )
          v18 = v17;
        *v18 = 0;
        if ( !v16 )
          return Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(this, a2, a3, a4, a5, a6);
        v19 = wcsrchr(a4, 0x5Cu);
        if ( v19 && v19 + 1 < &a4[a5] )
          v19[1] = 0;
        v20 = -1;
        do
          ++v20;
        while ( a4[v20] );
        if ( MultiByteToWideChar(0xFDE9u, 0, v13, -1, &a4[v20], a5 - v20) )
          return 0;
      }
    }
  }
  if ( GetLastError() )
  {
    result = GetLastError();
    v21 = result < 0;
    if ( result <= 0 )
      goto LABEL_28;
    result = (unsigned __int16)result | 0x80070000;
  }
  else
  {
    result = -2147467259;
  }
  v21 = result < 0;
LABEL_28:
  if ( v21 )
    return Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(this, a2, a3, a4, a5, a6);
  return result;
}

```

## disassembly

```asm
0x180012404  push    rbx
0x180012406  push    rbp
0x180012407  push    rsi
0x180012408  push    rdi
0x180012409  push    r12
0x18001240b  push    r13
0x18001240d  push    r14
0x18001240f  push    r15
0x180012411  sub     rsp, 38h
0x180012415  mov     r12, [rsp+78h+arg_28]
0x18001241d  xor     ebx, ebx
0x18001241f  mov     rax, [rcx+188h]
0x180012426  mov     rdi, r9
0x180012429  mov     r15d, [rsp+78h+arg_20]
0x180012431  mov     rsi, r8
0x180012434  mov     r14, rdx
0x180012437  mov     r13, rcx
0x18001243a  mov     [r12], ebx
0x18001243e  test    rax, rax
0x180012441  jz      short loc_1800124A1
0x180012443  lea     r8d, [rbx+0Ah]
0x180012447  mov     rcx, r14
0x18001244a  lea     rdx, aMinidumpAuxili; "MINIDUMP_AUXILIARY_PROVIDER"
0x180012451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012456  test    rax, rax
0x180012459  jz      loc_180012565
0x18001245f  mov     rdx, rax; hResInfo
0x180012462  mov     rcx, r14; hModule
0x180012465  call    cs:__imp_LoadResource
0x18001246b  test    rax, rax
0x18001246e  jz      loc_180012565
0x180012474  mov     rcx, rax; hResData
0x180012477  call    cs:__imp_LockResource
0x18001247d  mov     rbp, rax
0x180012480  test    rax, rax
0x180012483  jz      loc_180012565
0x180012489  xor     r9d, r9d
0x18001248c  mov     ebx, r15d
0x18001248f  test    r15d, r15d
0x180012492  jz      short loc_1800124A1
0x180012494  cmp     rbx, 7FFFFFFFh
0x18001249b  jbe     short loc_1800124CA
0x18001249d  mov     [rdi], r9w
0x1800124a1  mov     qword ptr [rsp+78h+cchWideChar], r12; int *
0x1800124a6  mov     r9, rdi; unsigned __int16 *
0x1800124a9  mov     rdx, r14; HINSTANCE
0x1800124ac  mov     dword ptr [rsp+78h+lpWideCharStr], r15d; unsigned int
0x1800124b1  mov     rcx, r13; this
0x1800124b4  call    ?GetAuxiliaryProviderPathFromEmbeddedImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z; Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)
0x1800124b9  add     rsp, 38h
0x1800124bd  pop     r15
0x1800124bf  pop     r14
0x1800124c1  pop     r13
0x1800124c3  pop     r12
0x1800124c5  pop     rdi
0x1800124c6  pop     rsi
0x1800124c7  pop     rbp
0x1800124c8  pop     rbx
0x1800124c9  retn
0x1800124ca  mov     ecx, 7FFFFFFEh
0x1800124cf  mov     rdx, rbx
0x1800124d2  mov     rax, rdi
0x1800124d5  test    rcx, rcx
0x1800124d8  jz      short loc_1800124F9
0x1800124da  movzx   r8d, word ptr [rsi]
0x1800124de  test    r8w, r8w
0x1800124e2  jz      short loc_1800124F9
0x1800124e4  mov     [rax], r8w
0x1800124e8  add     rsi, 2
0x1800124ec  add     rax, 2
0x1800124f0  dec     rcx
0x1800124f3  sub     rdx, 1
0x1800124f7  jnz     short loc_1800124D5
0x1800124f9  test    rdx, rdx
0x1800124fc  lea     rcx, [rax-2]
0x180012500  cmovnz  rcx, rax
0x180012504  mov     [rcx], r9w
0x180012508  jz      short loc_1800124A1
0x18001250a  mov     edx, 5Ch ; '\'; Ch
0x18001250f  mov     rcx, rdi; Str
0x180012512  call    cs:__imp_wcsrchr
0x180012518  xor     ebx, ebx
0x18001251a  test    rax, rax
0x18001251d  jz      short loc_18001252F
0x18001251f  lea     rcx, [rax+2]
0x180012523  lea     rax, [rdi+r15*2]
0x180012527  cmp     rcx, rax
0x18001252a  jnb     short loc_18001252F
0x18001252c  mov     [rcx], bx
0x18001252f  or      r9, 0FFFFFFFFFFFFFFFFh; cbMultiByte
0x180012533  mov     rax, r9
0x180012536  inc     rax
0x180012539  cmp     [rdi+rax*2], bx
0x18001253d  jnz     short loc_180012536
0x18001253f  mov     ecx, r15d
0x180012542  mov     r8, rbp; lpMultiByteStr
0x180012545  sub     ecx, eax
0x180012547  xor     edx, edx; dwFlags
0x180012549  mov     [rsp+78h+cchWideChar], ecx; cchWideChar
0x18001254d  lea     rax, [rdi+rax*2]
0x180012551  mov     ecx, 0FDE9h; CodePage
0x180012556  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x18001255b  call    cs:__imp_MultiByteToWideChar
0x180012561  test    eax, eax
0x180012563  jnz     short loc_180012595
0x180012565  call    cs:__imp_GetLastError
0x18001256b  test    eax, eax
0x18001256d  jz      short loc_180012583
0x18001256f  call    cs:__imp_GetLastError
0x180012575  test    eax, eax
0x180012577  jle     short loc_18001258A
0x180012579  movzx   eax, ax
0x18001257c  or      eax, 80070000h
0x180012581  jmp     short loc_180012588
0x180012583  mov     eax, 80004005h
0x180012588  test    eax, eax
0x18001258a  jns     loc_1800124B9
0x180012590  jmp     loc_1800124A1
0x180012595  mov     eax, ebx
0x180012597  jmp     loc_1800124B9
```
