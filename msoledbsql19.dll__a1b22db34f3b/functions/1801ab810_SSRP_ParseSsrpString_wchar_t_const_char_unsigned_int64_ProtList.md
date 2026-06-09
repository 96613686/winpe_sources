# SSRP::ParseSsrpString(wchar_t const *,char *,unsigned __int64,ProtList *)

- ea: `0x1801ab810`
- end: `0x1801abd46`
- name: `?ParseSsrpString@SSRP@@YAKPEB_WPEAD_KPEAVProtList@@@Z`
- size: `1334`
- prototype: `unsigned int __fastcall(PCNZWCH lpString2, LPCSTR lpCurrentChar, char *, unsigned __int64, struct ProtList *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801ac440`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003824`
- `0x180003d80`
- `0x180013360`
- `0x180153280`
- `0x180159e10`
- `0x1801a664c`
- `0x1801a85b0`
- `0x1801ab810`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801abaab`
- `KERNEL32!CompareStringW` at `0x1801abaab`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x1801abb3f`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x1801abb3f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801ab9d5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801abca6`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801ab9d5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801abca6`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x1801aba76`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x1801aba76`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SSRP::ParseSsrpString(PCNZWCH lpString2, LPCSTR lpCurrentChar, char *a3, unsigned int **a4)
{
  unsigned int *v6; // rsi
  unsigned int v7; // ebp
  __int64 v8; // rax
  char *v9; // rax
  __int64 v10; // r9
  const char *v11; // rdi
  _DWORD *v12; // r14
  char *v13; // rax
  char *v14; // rbx
  char *v15; // rax
  char *v16; // rsi
  __int64 v17; // rdi
  char *v18; // rbx
  char v19; // cl
  __int64 v21; // rdi
  unsigned int *v22; // r14
  __int64 v23; // rbx
  __int64 i; // rax
  unsigned int v25; // edi
  unsigned int **v26; // rcx
  unsigned int *v27; // rax
  unsigned int *v28; // rdx
  _DWORD v29[10]; // [rsp+30h] [rbp-88h] BYREF
  void *Block; // [rsp+58h] [rbp-60h] BYREF
  __int64 v31; // [rsp+60h] [rbp-58h] BYREF

  v6 = 0;
  v7 = 0;
  Block = 0;
  if ( (unsigned __int64)a3 > 0x7FFFFFFF )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_180266120[0] || bidID == -1 )
    {
LABEL_23:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266130[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
          bidID,
          off_180262960[0],
          912384,
          off_180266130[0],
          0);
      return 0xFFFFFFFFLL;
    }
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
      bidID,
      off_180262950[0],
      649216,
      off_180266120[0],
      0);
LABEL_21:
    if ( Block )
      free(Block);
    goto LABEL_23;
  }
  v8 = StrStrA_SYS(lpCurrentChar);
  if ( !v8 )
    goto LABEL_21;
  v9 = strchr_0((const char *)(v8 + 8), 59);
  if ( !v9 )
    goto LABEL_21;
  v11 = v9 + 1;
  if ( v9[1] != 59 )
  {
    v12 = v29;
    while ( v7 < 0xA )
    {
      v13 = strchr_0(v11, 59);
      if ( !v13 )
        break;
      *v13 = 0;
      v14 = v13 + 1;
      v15 = strchr_0(v13 + 1, 59);
      v16 = v15;
      if ( !v15 )
        break;
      *v15 = 0;
      if ( (int)v15 - (int)v14 > 255 )
        break;
      switch ( *v11 )
      {
        case 'a':
        case 'b':
        case 'r':
        case 's':
        case 'v':
          goto LABEL_41;
        case 'n':
          v17 = ProtList::Find(a4, 1);
          if ( !v17 )
            goto LABEL_41;
          *v12 = 1;
          ++v7;
          ++v12;
          if ( *v14 != 92 )
            goto LABEL_21;
          if ( v14[1] != 92 )
            goto LABEL_21;
          v18 = v14 + 2;
          v19 = *v18;
          if ( !*v18 )
            goto LABEL_21;
          break;
        case 't':
          v21 = ProtList::Find(a4, 6);
          if ( !v21 )
            goto LABEL_41;
          *v12 = 6;
          ++v7;
          ++v12;
          if ( !atoi(v14) || (int)StringCchPrintfW((wchar_t *)(v21 + 1544), 256, L"%hs", v14) < 0 )
            goto LABEL_21;
          *(_BYTE *)(v21 + 2058) = 1;
          goto LABEL_41;
        default:
          goto LABEL_21;
      }
      while ( v19 != 92 )
      {
        v19 = *++v18;
        if ( !*v18 )
          goto LABEL_21;
      }
      if ( !*v18 )
        break;
      if ( !IsLocalHost(lpString2) )
        goto LABEL_35;
      if ( _wdupenv_s((wchar_t **)&Block, 0, L"_CLUSTER_NETWORK_NAME_") )
        goto LABEL_21;
      if ( Block && CompareStringW(0x800u, 0x20001u, (PCNZWCH)Block, -1, lpString2, -1) == 2 )
      {
LABEL_35:
        *(_WORD *)(v17 + 2054) = 0;
        if ( (int)StringCchPrintfW((wchar_t *)(v17 + 1544), 261, L"\\\\%s%hs", lpString2, v18) < 0 )
          goto LABEL_21;
      }
      else
      {
        *(_WORD *)(v17 + 2054) = 0;
        if ( (int)StringCchPrintfW((wchar_t *)(v17 + 1544), 261, L"\\\\.%hs", v18) < 0 )
          goto LABEL_21;
      }
LABEL_41:
      v11 = v16 + 1;
      if ( v16[1] == 59 )
      {
        v6 = 0;
        goto LABEL_43;
      }
    }
    goto LABEL_21;
  }
LABEL_43:
  v22 = *a4;
  if ( *a4 )
  {
    v23 = (int)v7;
    do
    {
      for ( i = 0; i < v23; ++i )
      {
        if ( v29[i] == *v22 )
          break;
      }
      if ( i == v23 )
      {
        v25 = *v22;
        v22 = (unsigned int *)*((_QWORD *)v22 + 321);
        if ( v25 != 3 )
        {
          v31 = -1;
          if ( (bidGblFlags & 0x20004) == 0x20004 && `ProtList::RemoveProt'::`7'::_bidPtrSA_040_946[0] )
            bidScopeEnterW(&v31, `ProtList::RemoveProt'::`7'::_bidPtrSA_040_946[0], v25, v10);
          v26 = a4;
          v27 = *a4;
          if ( *a4 )
          {
            v28 = *a4;
            while ( *v27 != v25 )
            {
              v26 = (unsigned int **)(v28 + 642);
              v27 = (unsigned int *)*((_QWORD *)v28 + 321);
              v28 = v27;
              if ( !v27 )
                goto LABEL_59;
            }
            v6 = v28;
            *v26 = (unsigned int *)*((_QWORD *)v28 + 321);
          }
LABEL_59:
          if ( (bidGblFlags & 0x20002) == 0x20002 && `ProtList::RemoveProt'::`21'::_bidPtrSA_030_961[0] )
            bidTraceW(
              `ProtList::RemoveProt'::`21'::_bidSrcFileA[0],
              984064,
              `ProtList::RemoveProt'::`21'::_bidPtrSA_030_961[0],
              v6);
          _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v31);
          if ( v6 )
            operator delete(v6, 0xA10u);
          v6 = 0;
        }
      }
      else
      {
        v29[i] = v29[--v23];
        v22 = (unsigned int *)*((_QWORD *)v22 + 321);
      }
    }
    while ( v22 );
  }
  if ( Block )
    free(Block);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180266128[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
      bidID,
      off_180262958[0],
      901120,
      off_180266128[0],
      0);
  return 0;
}

```

## disassembly

```asm
0x1801ab810  push    rbx
0x1801ab812  push    rbp
0x1801ab813  push    rsi
0x1801ab814  push    rdi
0x1801ab815  push    r12
0x1801ab817  push    r13
0x1801ab819  push    r14
0x1801ab81b  push    r15
0x1801ab81d  sub     rsp, 78h
0x1801ab821  mov     rax, cs:__security_cookie
0x1801ab828  xor     rax, rsp
0x1801ab82b  mov     [rsp+0B8h+var_50], rax
0x1801ab830  mov     r12, r9
0x1801ab833  mov     rax, r8
0x1801ab836  mov     r10, rdx
0x1801ab839  mov     r15, rcx
0x1801ab83c  xor     esi, esi
0x1801ab83e  mov     ebp, esi
0x1801ab840  mov     [rsp+0B8h+Block], rsi
0x1801ab845  cmp     r8, 7FFFFFFFh
0x1801ab84c  jbe     short loc_1801AB8B4
0x1801ab84e  mov     eax, cs:_bidGblFlags
0x1801ab854  and     eax, 20002h
0x1801ab859  cmp     eax, 20002h
0x1801ab85e  jnz     loc_1801AB9DB
0x1801ab864  mov     rax, cs:off_180266120; "<SSRP::ParseSsrpString|SNI> String leng"...
0x1801ab86b  test    rax, rax
0x1801ab86e  jz      loc_1801AB9DB
0x1801ab874  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801ab87c  jz      loc_1801AB9DB
0x1801ab882  mov     rax, cs:off_180248050
0x1801ab889  mov     [rsp+0B8h+lpString2], rsi
0x1801ab88e  mov     r9, cs:off_180266120; "<SSRP::ParseSsrpString|SNI> String leng"...
0x1801ab895  mov     r8d, 9E800h
0x1801ab89b  mov     rdx, cs:off_180262950; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801ab8a2  mov     rcx, cs:_bidID
0x1801ab8a9  call    cs:__guard_dispatch_icall_fptr
0x1801ab8af  jmp     loc_1801AB9CB
0x1801ab8b4  mov     r9d, 8
0x1801ab8ba  lea     r8, aVersion; "Version;"
0x1801ab8c1  mov     edx, eax
0x1801ab8c3  mov     rcx, r10; lpCurrentChar
0x1801ab8c6  call    StrStrA_SYS
0x1801ab8cb  test    rax, rax
0x1801ab8ce  jz      loc_1801AB9CB
0x1801ab8d4  lea     rcx, [rax+8]; Str
0x1801ab8d8  mov     edx, 3Bh ; ';'; Val
0x1801ab8dd  call    strchr_0
0x1801ab8e2  mov     rdi, rax
0x1801ab8e5  test    rax, rax
0x1801ab8e8  jz      loc_1801AB9CB
0x1801ab8ee  inc     rdi
0x1801ab8f1  cmp     byte ptr [rdi], 3Bh ; ';'
0x1801ab8f4  jz      loc_1801ABB86
0x1801ab8fa  lea     r14, [rsp+0B8h+var_88]
0x1801ab8ff  lea     r13, cs:180000000h
0x1801ab906  cmp     ebp, 0Ah
0x1801ab909  jnb     def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab90f  mov     edx, 3Bh ; ';'; Val
0x1801ab914  mov     rcx, rdi; Str
0x1801ab917  call    strchr_0
0x1801ab91c  mov     rbx, rax
0x1801ab91f  test    rax, rax
0x1801ab922  jz      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab928  mov     byte ptr [rax], 0
0x1801ab92b  inc     rbx
0x1801ab92e  mov     edx, 3Bh ; ';'; Val
0x1801ab933  mov     rcx, rbx; Str
0x1801ab936  call    strchr_0
0x1801ab93b  mov     rsi, rax
0x1801ab93e  test    rax, rax
0x1801ab941  jz      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab947  mov     byte ptr [rax], 0
0x1801ab94a  mov     ecx, esi
0x1801ab94c  sub     ecx, ebx
0x1801ab94e  cmp     ecx, 0FFh
0x1801ab954  jg      short def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab956  movsx   ecx, byte ptr [rdi]
0x1801ab959  add     ecx, 0FFFFFF9Fh; switch 22 cases
0x1801ab95c  cmp     ecx, 15h
0x1801ab95f  ja      short def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab961  movsxd  rax, ecx
0x1801ab964  movzx   eax, ds:(byte_1801ABD30 - 180000000h)[rax+r13]
0x1801ab96d  mov     ecx, ds:(jpt_1801AB978 - 180000000h)[r13+rax*4]
0x1801ab975  add     rcx, r13
0x1801ab978  jmp     rcx; switch jump
0x1801ab97a  mov     edx, 1; jumptable 00000001801AB978 case 110
0x1801ab97f  mov     rcx, r12
0x1801ab982  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x1801ab987  mov     rdi, rax
0x1801ab98a  test    rax, rax
0x1801ab98d  jz      loc_1801ABB77; jumptable 00000001801AB978 cases 97,98,114,115,118
0x1801ab993  mov     dword ptr [r14], 1
0x1801ab99a  inc     ebp
0x1801ab99c  add     r14, 4
0x1801ab9a0  cmp     byte ptr [rbx], 5Ch ; '\'
0x1801ab9a3  jnz     short def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab9a5  cmp     byte ptr [rbx+1], 5Ch ; '\'
0x1801ab9a9  jnz     short def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab9ab  add     rbx, 2
0x1801ab9af  movzx   ecx, byte ptr [rbx]
0x1801ab9b2  test    cl, cl
0x1801ab9b4  jz      short def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab9b6  cmp     cl, 5Ch ; '\'
0x1801ab9b9  jz      loc_1801ABA53
0x1801ab9bf  inc     rbx
0x1801ab9c2  movzx   ecx, byte ptr [rbx]
0x1801ab9c5  test    cl, cl
0x1801ab9c7  jnz     short loc_1801AB9B6
0x1801ab9c9  xor     esi, esi; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801ab9cb  mov     rcx, [rsp+0B8h+Block]; Block
0x1801ab9d0  test    rcx, rcx
0x1801ab9d3  jz      short loc_1801AB9DB
0x1801ab9d5  call    cs:__imp_free
0x1801ab9db  mov     eax, cs:_bidGblFlags
0x1801ab9e1  and     eax, 20002h
0x1801ab9e6  cmp     eax, 20002h
0x1801ab9eb  jnz     short loc_1801ABA30
0x1801ab9ed  mov     rax, cs:off_180266130; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x1801ab9f4  test    rax, rax
0x1801ab9f7  jz      short loc_1801ABA30
0x1801ab9f9  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801aba01  jz      short loc_1801ABA30
0x1801aba03  mov     rax, cs:off_180248050
0x1801aba0a  mov     [rsp+0B8h+lpString2], rsi
0x1801aba0f  mov     r9, cs:off_180266130; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x1801aba16  mov     r8d, 0DEC00h
0x1801aba1c  mov     rdx, cs:off_180262960; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801aba23  mov     rcx, cs:_bidID
0x1801aba2a  call    cs:__guard_dispatch_icall_fptr
0x1801aba30  mov     eax, 0FFFFFFFFh
0x1801aba35  mov     rcx, [rsp+0B8h+var_50]
0x1801aba3a  xor     rcx, rsp; StackCookie
0x1801aba3d  call    __security_check_cookie
0x1801aba42  add     rsp, 78h
0x1801aba46  pop     r15
0x1801aba48  pop     r14
0x1801aba4a  pop     r13
0x1801aba4c  pop     r12
0x1801aba4e  pop     rdi
0x1801aba4f  pop     rsi
0x1801aba50  pop     rbp
0x1801aba51  pop     rbx
0x1801aba52  retn
0x1801aba53  cmp     byte ptr [rbx], 0
0x1801aba56  jz      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801aba5c  mov     rcx, r15; lpString2
0x1801aba5f  call    ?IsLocalHost@@YA_NPEB_W@Z; IsLocalHost(wchar_t const *)
0x1801aba64  test    al, al
0x1801aba66  jz      short loc_1801ABAE7
0x1801aba68  lea     r8, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x1801aba6f  xor     edx, edx; BufferCount
0x1801aba71  lea     rcx, [rsp+0B8h+Block]; Buffer
0x1801aba76  call    cs:__imp__wdupenv_s
0x1801aba7c  test    eax, eax
0x1801aba7e  jnz     def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801aba84  mov     r8, [rsp+0B8h+Block]; lpString1
0x1801aba89  test    r8, r8
0x1801aba8c  jz      short loc_1801ABAB6
0x1801aba8e  mov     [rsp+0B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1801aba96  mov     [rsp+0B8h+lpString2], r15; lpString2
0x1801aba9b  mov     edx, 20001h; dwCmpFlags
0x1801abaa0  mov     ecx, 800h; Locale
0x1801abaa5  mov     r9d, 0FFFFFFFFh; cchCount1
0x1801abaab  call    cs:__imp_CompareStringW
0x1801abab1  cmp     eax, 2
0x1801abab4  jz      short loc_1801ABAE7
0x1801abab6  xor     eax, eax
0x1801abab8  mov     [rdi+806h], ax
0x1801ababf  lea     rcx, [rdi+608h]; Buffer
0x1801abac6  mov     r9, rbx
0x1801abac9  lea     r8, aHs; "\\\\.%hs"
0x1801abad0  mov     edx, 105h; unsigned __int64
0x1801abad5  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801abada  test    eax, eax
0x1801abadc  js      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801abae2  jmp     loc_1801ABB77; jumptable 00000001801AB978 cases 97,98,114,115,118
0x1801abae7  xor     eax, eax
0x1801abae9  mov     [rdi+806h], ax
0x1801abaf0  lea     rcx, [rdi+608h]; Buffer
0x1801abaf7  mov     [rsp+0B8h+lpString2], rbx
0x1801abafc  mov     r9, r15
0x1801abaff  lea     r8, aSHs; "\\\\%s%hs"
0x1801abb06  mov     edx, 105h; unsigned __int64
0x1801abb0b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801abb10  test    eax, eax
0x1801abb12  js      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801abb18  jmp     short loc_1801ABB77; jumptable 00000001801AB978 cases 97,98,114,115,118
0x1801abb1a  mov     edx, 6; jumptable 00000001801AB978 case 116
0x1801abb1f  mov     rcx, r12
0x1801abb22  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x1801abb27  mov     rdi, rax
0x1801abb2a  test    rax, rax
0x1801abb2d  jz      short loc_1801ABB77; jumptable 00000001801AB978 cases 97,98,114,115,118
0x1801abb2f  mov     dword ptr [r14], 6
0x1801abb36  inc     ebp
0x1801abb38  add     r14, 4
0x1801abb3c  mov     rcx, rbx; String
0x1801abb3f  call    cs:__imp_atoi
0x1801abb45  test    eax, eax
0x1801abb47  jz      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801abb4d  lea     rcx, [rdi+608h]; Buffer
0x1801abb54  mov     r9, rbx
0x1801abb57  lea     r8, aHs_0; "%hs"
0x1801abb5e  mov     edx, 100h; unsigned __int64
0x1801abb63  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801abb68  test    eax, eax
0x1801abb6a  js      def_1801AB978; jumptable 00000001801AB978 default case, cases 99-109,111-113,117
0x1801abb70  mov     byte ptr [rdi+80Ah], 1
0x1801abb77  lea     rdi, [rsi+1]; jumptable 00000001801AB978 cases 97,98,114,115,118
0x1801abb7b  cmp     byte ptr [rdi], 3Bh ; ';'
0x1801abb7e  jnz     loc_1801AB906
0x1801abb84  xor     esi, esi
0x1801abb86  mov     r14, [r12]
0x1801abb8a  test    r14, r14
0x1801abb8d  jz      loc_1801ABC9C
0x1801abb93  movsxd  rbx, ebp
0x1801abb96  mov     rax, rsi
0x1801abb99  test    rbx, rbx
0x1801abb9c  jle     short loc_1801ABBAF
0x1801abb9e  mov     ecx, [r14]
0x1801abba1  cmp     [rsp+rax*4+0B8h+var_88], ecx
0x1801abba5  jz      short loc_1801ABBAF
0x1801abba7  inc     rax
0x1801abbaa  cmp     rax, rbx
0x1801abbad  jl      short loc_1801ABBA1
0x1801abbaf  cmp     rax, rbx
0x1801abbb2  jnz     loc_1801ABD08
0x1801abbb8  mov     edi, [r14]
0x1801abbbb  mov     r14, [r14+0A08h]
0x1801abbc2  cmp     edi, 3
0x1801abbc5  jz      loc_1801ABC93
0x1801abbcb  mov     [rsp+0B8h+var_58], 0FFFFFFFFFFFFFFFFh
0x1801abbd4  mov     eax, cs:_bidGblFlags
0x1801abbda  and     eax, 20004h
0x1801abbdf  cmp     eax, 20004h
0x1801abbe4  jnz     short loc_1801ABC06
0x1801abbe6  mov     rax, cs:?_bidPtrSA_040_946@?6??RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z@4REB_WEB; wchar_t const * const `ProtList::RemoveProt(ProviderNum)'::`7'::_bidPtrSA_040_946
0x1801abbed  test    rax, rax
0x1801abbf0  jz      short loc_1801ABC06
0x1801abbf2  mov     r8d, edi
0x1801abbf5  mov     rdx, cs:?_bidPtrSA_040_946@?6??RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z@4REB_WEB; wchar_t const * const `ProtList::RemoveProt(ProviderNum)'::`7'::_bidPtrSA_040_946
0x1801abbfc  lea     rcx, [rsp+0B8h+var_58]
0x1801abc01  call    _bidScopeEnterW
0x1801abc06  mov     rcx, r12
0x1801abc09  mov     rax, [r12]
0x1801abc0d  test    rax, rax
0x1801abc10  jz      short loc_1801ABC3A
0x1801abc12  mov     rdx, rax
0x1801abc15  cmp     [rax], edi
0x1801abc17  jz      short loc_1801ABC2D
0x1801abc19  lea     rcx, [rdx+0A08h]
0x1801abc20  mov     rax, [rcx]
0x1801abc23  mov     rdx, rax
0x1801abc26  test    rax, rax
0x1801abc29  jnz     short loc_1801ABC15
0x1801abc2b  jmp     short loc_1801ABC3A
0x1801abc2d  mov     rsi, rdx
0x1801abc30  mov     rax, [rdx+0A08h]
0x1801abc37  mov     [rcx], rax
0x1801abc3a  mov     eax, cs:_bidGblFlags
0x1801abc40  and     eax, 20002h
0x1801abc45  cmp     eax, 20002h
0x1801abc4a  jnz     short loc_1801ABC74
0x1801abc4c  mov     rax, cs:?_bidPtrSA_030_961@?BF@??RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z@4REB_WEB; wchar_t const * const `ProtList::RemoveProt(ProviderNum)'::`21'::_bidPtrSA_030_961
0x1801abc53  test    rax, rax
0x1801abc56  jz      short loc_1801ABC74
0x1801abc58  mov     r9, rsi
0x1801abc5b  mov     r8, cs:?_bidPtrSA_030_961@?BF@??RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z@4REB_WEB; wchar_t const * const `ProtList::RemoveProt(ProviderNum)'::`21'::_bidPtrSA_030_961
0x1801abc62  mov     edx, 0F0400h
0x1801abc67  mov     rcx, cs:?_bidSrcFileA@?BF@??RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z@4REBDEB; char const * const `ProtList::RemoveProt(ProviderNum)'::`21'::_bidSrcFileA
0x1801abc6e  call    _bidTraceW
0x1801abc73  nop
0x1801abc74  lea     rcx, [rsp+0B8h+var_58]; this
0x1801abc79  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1801abc7e  nop
0x1801abc7f  test    rsi, rsi
0x1801abc82  jz      short loc_1801ABC91
0x1801abc84  mov     edx, 0A10h; unsigned __int64
0x1801abc89  mov     rcx, rsi; void *
0x1801abc8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801abc91  xor     esi, esi
0x1801abc93  test    r14, r14
0x1801abc96  jnz     loc_1801ABB96
0x1801abc9c  mov     rcx, [rsp+0B8h+Block]; Block
0x1801abca1  test    rcx, rcx
0x1801abca4  jz      short loc_1801ABCAC
0x1801abca6  call    cs:__imp_free
0x1801abcac  mov     eax, cs:_bidGblFlags
0x1801abcb2  and     eax, 20002h
0x1801abcb7  cmp     eax, 20002h
0x1801abcbc  jnz     short loc_1801ABD01
0x1801abcbe  mov     rax, cs:off_180266128; "<SSRP::ParseSsrpString|RET|SNI> success"...
0x1801abcc5  test    rax, rax
0x1801abcc8  jz      short loc_1801ABD01
0x1801abcca  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1801abcd2  jz      short loc_1801ABD01
0x1801abcd4  mov     rax, cs:off_180248050
0x1801abcdb  mov     [rsp+0B8h+lpString2], rsi
0x1801abce0  mov     r9, cs:off_180266128; "<SSRP::ParseSsrpString|RET|SNI> success"...
  ... truncated ...
```
