# PlaiLoadString(ushort const *,ushort * *)

- ea: `0x1800552fc`
- end: `0x180055862`
- name: `?PlaiLoadString@@YAJPEBGPEAPEAG@Z`
- size: `1382`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18008c8b0`
- `0x180092bb0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x18002b3a0`
- `0x180046c60`
- `0x1800552fc`
- `0x1800e4ffc`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800554c4`
- `msvcrt!wcschr` at `0x1800554c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005582f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005582f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055722`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180055722`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005567d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005567d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005568f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005568f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055730`

## pseudocode

```c
__int64 __fastcall PlaiLoadString(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax
  wchar_t *v5; // rdi
  UINT v6; // ebx
  __int64 v7; // rax
  HMODULE v8; // rsi
  signed int v9; // eax
  __int64 v10; // rax
  wchar_t *v11; // rax
  __int64 v12; // rax
  signed int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rax
  HMODULE Library; // rax
  DWORD v19; // eax
  __int64 v20; // rax
  DWORD LastError; // eax
  __int64 v22; // rax
  int v24; // [rsp+20h] [rbp-E0h]
  UINT uID; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v27[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v28[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v29[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v30[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v31[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v32[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v33[64]; // [rsp+380h] [rbp+280h] BYREF

  uID = 0;
  v4 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v24);
  v5 = v4;
  if ( v4 )
  {
    v8 = 0;
    v9 = StringCchCopyW(v4, 0x400u, a1);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v11 = wcschr(v5, 0x2Cu);
      if ( v11 )
      {
        *v11 = 0;
        if ( v11[1] != 35 && v11[1] != 45 )
        {
          v6 = -2147024809;
          goto LABEL_53;
        }
        v13 = PlaiHexToLong(v11 + 2, (int *)&uID);
        v6 = v13;
        if ( v13 >= 0 )
        {
          v16 = PlaiExpandVariables(v5, v14, v5);
          v6 = v16;
          if ( v16 >= 0 )
          {
            Library = LoadLibraryExW(v5, 0, 2u);
            v8 = Library;
            if ( Library )
            {
              if ( LoadStringW(Library, uID, v5, 1024) )
              {
                *a2 = v5;
                goto LABEL_56;
              }
              LastError = GetLastError();
              v6 = PlaiHResultFromWin32(LastError);
              v26 = 0;
              uID = v6;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v33, 0x4000000000000800uLL);
                v22 = -1;
                do
                  ++v22;
                while ( v33[v22] );
                goto LABEL_52;
              }
            }
            else
            {
              v19 = GetLastError();
              v6 = PlaiHResultFromWin32(v19);
              v26 = 0;
              uID = v6;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v32, 0x4000000000000800uLL);
                v20 = -1;
                do
                  ++v20;
                while ( v32[v20] );
                goto LABEL_52;
              }
            }
          }
          else
          {
            v26 = 0;
            uID = v16;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v31, 0x4000000000000800uLL);
              v17 = -1;
              do
                ++v17;
              while ( v31[v17] );
              goto LABEL_52;
            }
          }
        }
        else
        {
          v26 = 0;
          uID = v13;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v30, 0x4000000000000800uLL);
            v15 = -1;
            do
              ++v15;
            while ( v30[v15] );
            goto LABEL_52;
          }
        }
      }
      else
      {
        v6 = -2147024809;
        uID = -2147024809;
        v26 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v29, 0x4000000000000800uLL);
          v12 = -1;
          do
            ++v12;
          while ( v29[v12] );
          goto LABEL_52;
        }
      }
    }
    else
    {
      v26 = 0;
      uID = v9;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v10 = -1;
        do
          ++v10;
        while ( v28[v10] );
LABEL_52:
        EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&uID);
      }
    }
LABEL_53:
    PlaiFree(v5, 1);
    if ( !v8 )
      return v6;
LABEL_56:
    FreeLibrary(v8);
    return v6;
  }
  v6 = -2147024882;
  v26 = -2147024882;
  uID = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v27, 0x4000000000000800uLL);
    v7 = -1;
    do
      ++v7;
    while ( v27[v7] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v26);
  }
  return v6;
}

```

## disassembly

```asm
0x1800552fc  mov     [rsp-8+arg_10], rbx
0x180055301  mov     [rsp-8+arg_18], rsi
0x180055306  push    rbp
0x180055307  push    rdi
0x180055308  push    r13
0x18005530a  push    r14
0x18005530c  push    r15
0x18005530e  lea     rbp, [rsp-310h]
0x180055316  sub     rsp, 410h
0x18005531d  mov     rax, cs:__security_cookie
0x180055324  xor     rax, rsp
0x180055327  mov     [rbp+330h+var_30], rax
0x18005532e  xor     r15d, r15d
0x180055331  lea     rsi, byte_180147320
0x180055338  mov     r14, rdx
0x18005533b  mov     [rsp+430h+uID], r15d
0x180055340  mov     rbx, rcx
0x180055343  mov     r9, rsi; char *
0x180055346  xor     r8d, r8d; int
0x180055349  mov     ecx, 800h; dwBytes
0x18005534e  lea     r13d, [r15+1]
0x180055352  mov     edx, r13d; int
0x180055355  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18005535a  mov     rdi, rax
0x18005535d  test    rax, rax
0x180055360  jnz     loc_180055438
0x180055366  cmp     dword ptr cs:xmmword_180169738, r15d
0x18005536d  mov     ebx, 8007000Eh
0x180055372  mov     [rsp+430h+var_3B8], ebx
0x180055376  mov     [rsp+430h+uID], r15d
0x18005537b  jz      loc_180055835
0x180055381  mov     rdx, 4000000000000800h; unsigned __int64
0x18005538b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180055392  jz      loc_180055835
0x180055398  mov     rax, cs:qword_180169748
0x18005539f  and     rax, rdx
0x1800553a2  cmp     cs:qword_180169748, rax
0x1800553a9  jnz     loc_180055835
0x1800553af  lea     rcx, [rbp+330h+var_3B0]; unsigned __int16 *
0x1800553b3  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800553b8  lea     rcx, [rbp+330h+var_3B0]
0x1800553bc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800553c0  inc     rax
0x1800553c3  cmp     [rcx+rax*2], r15w
0x1800553c8  jnz     short loc_1800553C0
0x1800553ca  lea     ecx, [rax+rax]
0x1800553cd  add     rcx, 2
0x1800553d1  lea     rax, [rbp+330h+var_3B0]
0x1800553d5  mov     [rsp+430h+var_3D0], rcx
0x1800553da  lea     r9, [rsp+430h+var_3B8]
0x1800553df  mov     [rsp+430h+var_3D8], rax
0x1800553e4  lea     rcx, [rsp+430h+uID]
0x1800553e9  mov     [rsp+430h+var_3E0], 0Fh
0x1800553f2  lea     rax, aPlailoadstring_0; "PlaiLoadString"
0x1800553f9  mov     [rsp+430h+var_3E8], rax
0x1800553fe  lea     rdx, PLA_EVENT_ERROR
0x180055405  mov     eax, 4
0x18005540a  mov     [rsp+430h+var_3F0], rax
0x18005540f  mov     [rsp+430h+var_3F8], rcx
0x180055414  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005541b  mov     [rsp+430h+var_400], r13
0x180055420  mov     [rsp+430h+var_408], rsi
0x180055425  lea     r8d, [rax+1]
0x180055429  mov     [rsp+430h+var_410], rax
0x18005542e  call    EventingWriteEvent
0x180055433  jmp     loc_180055835
0x180055438  mov     r8, rbx; unsigned __int16 *
0x18005543b  mov     edx, 400h; unsigned __int64
0x180055440  mov     rcx, rdi; unsigned __int16 *
0x180055443  mov     rsi, r15
0x180055446  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005544b  mov     ebx, eax
0x18005544d  test    eax, eax
0x18005544f  jns     short loc_1800554BC
0x180055451  cmp     dword ptr cs:xmmword_180169738, r15d
0x180055458  mov     [rsp+430h+var_3B8], r15d
0x18005545d  mov     [rsp+430h+uID], eax
0x180055461  jz      loc_180055817
0x180055467  mov     rdx, 4000000000000800h; unsigned __int64
0x180055471  test    qword ptr cs:xmmword_180169738+8, rdx
0x180055478  jz      loc_180055817
0x18005547e  mov     rax, cs:qword_180169748
0x180055485  and     rax, rdx
0x180055488  cmp     cs:qword_180169748, rax
0x18005548f  jnz     loc_180055817
0x180055495  lea     rcx, [rbp+330h+var_330]; unsigned __int16 *
0x180055499  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005549e  lea     rcx, [rbp+330h+var_330]
0x1800554a2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800554a6  inc     rax
0x1800554a9  cmp     [rcx+rax*2], r15w
0x1800554ae  jnz     short loc_1800554A6
0x1800554b0  lea     ecx, [rax+rax]
0x1800554b3  lea     rax, [rbp+330h+var_330]
0x1800554b7  jmp     loc_1800557AE
0x1800554bc  mov     edx, 2Ch ; ','; Ch
0x1800554c1  mov     rcx, rdi; Str
0x1800554c4  call    cs:__imp_wcschr
0x1800554ca  mov     rcx, rax
0x1800554cd  test    rax, rax
0x1800554d0  jnz     short loc_18005554B
0x1800554d2  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800554d9  mov     ebx, 80070057h
0x1800554de  mov     [rsp+430h+uID], ebx
0x1800554e2  mov     [rsp+430h+var_3B8], r15d
0x1800554e7  jz      loc_180055817
0x1800554ed  mov     rdx, 4000000000000800h; unsigned __int64
0x1800554f7  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800554fe  jz      loc_180055817
0x180055504  mov     rax, cs:qword_180169748
0x18005550b  and     rax, rdx
0x18005550e  cmp     cs:qword_180169748, rax
0x180055515  jnz     loc_180055817
0x18005551b  lea     rcx, [rbp+330h+var_2B0]; unsigned __int16 *
0x180055522  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180055527  lea     rcx, [rbp+330h+var_2B0]
0x18005552e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055532  inc     rax
0x180055535  cmp     [rcx+rax*2], r15w
0x18005553a  jnz     short loc_180055532
0x18005553c  lea     ecx, [rax+rax]
0x18005553f  lea     rax, [rbp+330h+var_2B0]
0x180055546  jmp     loc_1800557AE
0x18005554b  mov     [rax], r15w
0x18005554f  cmp     word ptr [rax+2], 23h ; '#'
0x180055554  jz      short loc_180055567
0x180055556  cmp     word ptr [rax+2], 2Dh ; '-'
0x18005555b  jz      short loc_180055567
0x18005555d  mov     ebx, 80070057h
0x180055562  jmp     loc_180055817
0x180055567  add     rcx, 4; unsigned __int16 *
0x18005556b  lea     rdx, [rsp+430h+uID]; int *
0x180055570  call    ?PlaiHexToLong@@YAJPEBGPEAJ@Z; PlaiHexToLong(ushort const *,long *)
0x180055575  mov     ebx, eax
0x180055577  test    eax, eax
0x180055579  jns     short loc_1800555EF
0x18005557b  cmp     dword ptr cs:xmmword_180169738, r15d
0x180055582  mov     [rsp+430h+var_3B8], r15d
0x180055587  mov     [rsp+430h+uID], eax
0x18005558b  jz      loc_180055817
0x180055591  mov     rdx, 4000000000000800h; unsigned __int64
0x18005559b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800555a2  jz      loc_180055817
0x1800555a8  mov     rax, cs:qword_180169748
0x1800555af  and     rax, rdx
0x1800555b2  cmp     cs:qword_180169748, rax
0x1800555b9  jnz     loc_180055817
0x1800555bf  lea     rcx, [rbp+330h+var_230]; unsigned __int16 *
0x1800555c6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800555cb  lea     rcx, [rbp+330h+var_230]
0x1800555d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800555d6  inc     rax
0x1800555d9  cmp     [rcx+rax*2], r15w
0x1800555de  jnz     short loc_1800555D6
0x1800555e0  lea     ecx, [rax+rax]
0x1800555e3  lea     rax, [rbp+330h+var_230]
0x1800555ea  jmp     loc_1800557AE
0x1800555ef  mov     r8, rdi; unsigned __int16 *
0x1800555f2  mov     rcx, rdi; unsigned __int16 *
0x1800555f5  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x1800555fa  mov     ebx, eax
0x1800555fc  test    eax, eax
0x1800555fe  jns     short loc_180055674
0x180055600  cmp     dword ptr cs:xmmword_180169738, r15d
0x180055607  mov     [rsp+430h+var_3B8], r15d
0x18005560c  mov     [rsp+430h+uID], eax
0x180055610  jz      loc_180055817
0x180055616  mov     rdx, 4000000000000800h; unsigned __int64
0x180055620  test    qword ptr cs:xmmword_180169738+8, rdx
0x180055627  jz      loc_180055817
0x18005562d  mov     rax, cs:qword_180169748
0x180055634  and     rax, rdx
0x180055637  cmp     cs:qword_180169748, rax
0x18005563e  jnz     loc_180055817
0x180055644  lea     rcx, [rbp+330h+var_1B0]; unsigned __int16 *
0x18005564b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180055650  lea     rcx, [rbp+330h+var_1B0]
0x180055657  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005565b  inc     rax
0x18005565e  cmp     [rcx+rax*2], r15w
0x180055663  jnz     short loc_18005565B
0x180055665  lea     ecx, [rax+rax]
0x180055668  lea     rax, [rbp+330h+var_1B0]
0x18005566f  jmp     loc_1800557AE
0x180055674  xor     edx, edx; hFile
0x180055676  mov     rcx, rdi; lpLibFileName
0x180055679  lea     r8d, [rdx+2]; dwFlags
0x18005567d  call    cs:__imp_LoadLibraryExW
0x180055683  mov     rsi, rax
0x180055686  test    rax, rax
0x180055689  jnz     loc_180055712
0x18005568f  call    cs:__imp_GetLastError
0x180055695  mov     ecx, eax; unsigned int
0x180055697  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18005569c  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800556a3  mov     ebx, eax
0x1800556a5  mov     [rsp+430h+var_3B8], r15d
0x1800556aa  mov     [rsp+430h+uID], eax
0x1800556ae  jz      loc_180055817
0x1800556b4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800556be  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800556c5  jz      loc_180055817
0x1800556cb  mov     rax, cs:qword_180169748
0x1800556d2  and     rax, rdx
0x1800556d5  cmp     cs:qword_180169748, rax
0x1800556dc  jnz     loc_180055817
0x1800556e2  lea     rcx, [rbp+330h+var_130]; unsigned __int16 *
0x1800556e9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800556ee  lea     rcx, [rbp+330h+var_130]
0x1800556f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800556f9  inc     rax
0x1800556fc  cmp     [rcx+rax*2], r15w
0x180055701  jnz     short loc_1800556F9
0x180055703  lea     ecx, [rax+rax]
0x180055706  lea     rax, [rbp+330h+var_130]
0x18005570d  jmp     loc_1800557AE
0x180055712  mov     edx, [rsp+430h+uID]; uID
0x180055716  mov     r9d, 400h; cchBufferMax
0x18005571c  mov     r8, rdi; lpBuffer
0x18005571f  mov     rcx, rax; hInstance
0x180055722  call    cs:__imp_LoadStringW
0x180055728  test    eax, eax
0x18005572a  jnz     loc_180055829
0x180055730  call    cs:__imp_GetLastError
0x180055736  mov     ecx, eax; unsigned int
0x180055738  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18005573d  cmp     dword ptr cs:xmmword_180169738, r15d
0x180055744  mov     ebx, eax
0x180055746  mov     [rsp+430h+var_3B8], r15d
0x18005574b  mov     [rsp+430h+uID], eax
0x18005574f  jz      loc_180055817
0x180055755  mov     rdx, 4000000000000800h; unsigned __int64
0x18005575f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180055766  jz      loc_180055817
0x18005576c  mov     rax, cs:qword_180169748
0x180055773  and     rax, rdx
0x180055776  cmp     cs:qword_180169748, rax
0x18005577d  jnz     loc_180055817
0x180055783  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x18005578a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18005578f  lea     rcx, [rbp+330h+var_B0]
0x180055796  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005579a  inc     rax
0x18005579d  cmp     [rcx+rax*2], r15w
0x1800557a2  jnz     short loc_18005579A
0x1800557a4  lea     ecx, [rax+rax]
0x1800557a7  lea     rax, [rbp+330h+var_B0]
0x1800557ae  add     rcx, 2
0x1800557b2  lea     r9, [rsp+430h+uID]
0x1800557b7  mov     [rsp+430h+var_3D0], rcx
0x1800557bc  lea     rdx, PLA_EVENT_ERROR
0x1800557c3  mov     [rsp+430h+var_3D8], rax
0x1800557c8  lea     rcx, [rsp+430h+var_3B8]
0x1800557cd  mov     [rsp+430h+var_3E0], 0Fh
0x1800557d6  lea     rax, aPlailoadstring_0; "PlaiLoadString"
0x1800557dd  mov     [rsp+430h+var_3E8], rax
0x1800557e2  mov     eax, 4
0x1800557e7  mov     [rsp+430h+var_3F0], rax
0x1800557ec  mov     [rsp+430h+var_3F8], rcx
0x1800557f1  lea     rcx, byte_180147320
0x1800557f8  mov     [rsp+430h+var_400], r13
0x1800557fd  mov     [rsp+430h+var_408], rcx
0x180055802  lea     r8d, [rax+1]
0x180055806  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18005580d  mov     [rsp+430h+var_410], rax
0x180055812  call    EventingWriteEvent
0x180055817  mov     edx, r13d; int
0x18005581a  mov     rcx, rdi; lpMem
0x18005581d  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x180055822  test    rsi, rsi
0x180055825  jz      short loc_180055835
0x180055827  jmp     short loc_18005582C
0x180055829  mov     [r14], rdi
0x18005582c  mov     rcx, rsi; hLibModule
0x18005582f  call    cs:__imp_FreeLibrary
0x180055835  mov     eax, ebx
0x180055837  mov     rcx, [rbp+330h+var_30]
0x18005583e  xor     rcx, rsp; StackCookie
0x180055841  call    __security_check_cookie
0x180055846  lea     r11, [rsp+430h+var_20]
0x18005584e  mov     rbx, [r11+40h]
0x180055852  mov     rsi, [r11+48h]
0x180055856  mov     rsp, r11
0x180055859  pop     r15
0x18005585b  pop     r14
0x18005585d  pop     r13
0x18005585f  pop     rdi
0x180055860  pop     rbp
0x180055861  retn
```
