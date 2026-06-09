# SSRP::ParseSsrpString(ushort const *,char *,unsigned __int64,ProtList *)

- ea: `0x100440ee8`
- end: `0x100441337`
- name: `?ParseSsrpString@SSRP@@YAKPEBGPEAD_KPEAVProtList@@@Z`
- size: `1103`
- prototype: `unsigned int __fastcall(LPCWCH lpString2, LPCSTR lpCurrentChar, char *, unsigned __int64, struct ProtList *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x100441a7c`

## callees

- `0x100405948`
- `0x100413da8`
- `0x100419d10`
- `0x10043cafc`
- `0x100440ee8`
- `0x100441614`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1004411e8`
- `KERNEL32!CompareStringOrdinal` at `0x1004411e8`
- `VCRUNTIME140!strchr` at `0x100441023`
- `VCRUNTIME140!strchr` at `0x100441055`
- `VCRUNTIME140!strchr` at `0x100441074`
- `VCRUNTIME140!strchr` at `0x100441023`
- `VCRUNTIME140!strchr` at `0x100441055`
- `VCRUNTIME140!strchr` at `0x100441074`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x100441107`
- `api-ms-win-crt-convert-l1-1-0!atoi` at `0x100441107`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100440f83`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004412e0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x100440f83`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1004412e0`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x1004411bc`
- `api-ms-win-crt-environment-l1-1-0!_wdupenv_s` at `0x1004411bc`

## pseudocode

```c
__int64 __fastcall SSRP::ParseSsrpString(LPCWCH lpString2, LPCSTR lpCurrentChar, char *a3, _DWORD **a4)
{
  unsigned int v6; // ebp
  __int64 v8; // rax
  char *v9; // rax
  const char *v10; // rdi
  _DWORD *v11; // r14
  char *v12; // rax
  char *v13; // rbx
  char *v14; // rax
  char *v15; // r15
  __int64 v16; // rdi
  __int64 v17; // rdi
  char *v18; // rbx
  char v19; // cl
  int v20; // eax
  _DWORD *v21; // rbx
  __int64 v22; // rdi
  __int64 i; // rcx
  _DWORD **v24; // r8
  int v25; // edx
  __int64 v26; // r8
  int v27; // eax
  void *Block; // [rsp+30h] [rbp-88h] BYREF
  _DWORD v29[10]; // [rsp+38h] [rbp-80h] BYREF

  Block = 0;
  v6 = 0;
  if ( (unsigned __int64)a3 > 0x7FFFFFFF )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_1005E60B0[0] || bidID == -1 )
    {
LABEL_8:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E60C0[0] && bidID != -1 )
        ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
          bidID,
          0,
          908288,
          off_1005E60C0[0],
          0);
      return 0xFFFFFFFFLL;
    }
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
      bidID,
      0,
      648192,
      off_1005E60B0[0],
      0);
LABEL_6:
    if ( Block )
      free(Block);
    goto LABEL_8;
  }
  v8 = StrStrA_SYS(lpCurrentChar);
  if ( !v8 )
    goto LABEL_6;
  v9 = strchr((const char *)(v8 + 8), 59);
  if ( !v9 )
    goto LABEL_6;
  v10 = v9 + 1;
  if ( v9[1] != 59 )
  {
    v11 = v29;
    while ( v6 < 0xA )
    {
      v12 = strchr(v10, 59);
      if ( !v12 )
        break;
      *v12 = 0;
      v13 = v12 + 1;
      v14 = strchr(v12 + 1, 59);
      v15 = v14;
      if ( !v14 )
        break;
      *v14 = 0;
      if ( (int)v14 - (int)v13 > 255 )
        break;
      if ( *v10 != 97 && *v10 != 98 )
      {
        if ( *v10 == 110 )
        {
          v17 = ProtList::Find(a4, 1);
          if ( v17 )
          {
            *v11 = 1;
            ++v6;
            ++v11;
            if ( *v13 != 92 )
              goto LABEL_6;
            if ( v13[1] != 92 )
              goto LABEL_6;
            v18 = v13 + 2;
            v19 = *v18;
            if ( !*v18 )
              goto LABEL_6;
            do
            {
              if ( v19 == 92 )
                break;
              v19 = *++v18;
            }
            while ( *v18 );
            if ( !*v18 )
              goto LABEL_6;
            if ( !IsLocalHost(lpString2) )
              goto LABEL_45;
            if ( _wdupenv_s((wchar_t **)&Block, 0, L"_CLUSTER_NETWORK_NAME_") )
              goto LABEL_6;
            if ( Block && CompareStringOrdinal((LPCWCH)Block, -1, lpString2, -1, 1) == 2 )
            {
LABEL_45:
              *(_WORD *)(v17 + 2054) = 0;
              v20 = StringCchPrintfW((unsigned __int16 *)(v17 + 1544), 0x105u, L"\\\\%s%hs", lpString2, v18);
            }
            else
            {
              *(_WORD *)(v17 + 2054) = 0;
              v20 = StringCchPrintfW((unsigned __int16 *)(v17 + 1544), 0x105u, L"\\\\.%hs", v18);
            }
            if ( v20 < 0 )
              goto LABEL_6;
          }
        }
        else if ( *v10 != 114 && *v10 != 115 )
        {
          if ( *v10 == 116 )
          {
            v16 = ProtList::Find(a4, 7);
            if ( v16 )
            {
              *v11++ = 7;
              ++v6;
              if ( !atoi(v13) || (int)StringCchPrintfW((unsigned __int16 *)(v16 + 1544), 0x100u, L"%hs", v13) < 0 )
                goto LABEL_6;
              *(_BYTE *)(v16 + 2058) = 1;
            }
          }
          else if ( *v10 != 118 )
          {
            goto LABEL_6;
          }
        }
      }
      v10 = v15 + 1;
      if ( v15[1] == 59 )
        goto LABEL_48;
    }
    goto LABEL_6;
  }
LABEL_48:
  v21 = *a4;
  if ( *a4 )
  {
    v22 = (int)v6;
    do
    {
      for ( i = 0; i < v22; ++i )
      {
        if ( v29[i] == *v21 )
          break;
      }
      v24 = (_DWORD **)(v21 + 642);
      if ( i == v22 )
      {
        v25 = *v21;
        v21 = *v24;
        if ( v25 != 4 )
        {
          v26 = ProtList::RemoveProt(a4);
          if ( v26 )
            ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v26);
        }
      }
      else
      {
        v27 = v29[--v22];
        v21 = *v24;
        v29[i] = v27;
      }
    }
    while ( v21 );
  }
  if ( Block )
    free(Block);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E60B8[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
      bidID,
      0,
      897024,
      off_1005E60B8[0],
      0);
  return 0;
}

```

## disassembly

```asm
0x100440ee8  push    rbx
0x100440eea  push    rbp
0x100440eeb  push    rsi
0x100440eec  push    rdi
0x100440eed  push    r12
0x100440eef  push    r13
0x100440ef1  push    r14
0x100440ef3  push    r15
0x100440ef5  sub     rsp, 78h
0x100440ef9  mov     rax, cs:__security_cookie
0x100440f00  xor     rax, rsp
0x100440f03  mov     [rsp+0B8h+var_58], rax
0x100440f08  mov     r13, rcx
0x100440f0b  mov     r12, r9
0x100440f0e  xor     ecx, ecx
0x100440f10  mov     rax, r8
0x100440f13  mov     [rsp+0B8h+Block], rcx
0x100440f18  mov     r10, rdx
0x100440f1b  mov     ebp, ecx
0x100440f1d  mov     esi, 20002h
0x100440f22  cmp     r8, 7FFFFFFFh
0x100440f29  jbe     loc_100440FF6
0x100440f2f  mov     eax, cs:_bidGblFlags
0x100440f35  and     eax, esi
0x100440f37  cmp     eax, esi
0x100440f39  jnz     short loc_100440F8B
0x100440f3b  mov     rax, cs:off_1005E60B0; "<SSRP::ParseSsrpString|SNI> String leng"...
0x100440f42  test    rax, rax
0x100440f45  jz      short loc_100440F8B
0x100440f47  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100440f4f  jz      short loc_100440F8B
0x100440f51  mov     r9, cs:off_1005E60B0; "<SSRP::ParseSsrpString|SNI> String leng"...
0x100440f58  xor     edx, edx
0x100440f5a  mov     rax, cs:off_1005D39E0
0x100440f61  mov     r8d, 9E400h
0x100440f67  mov     qword ptr [rsp+0B8h+bIgnoreCase], rcx
0x100440f6c  mov     rcx, cs:_bidID
0x100440f73  call    cs:__guard_dispatch_icall_fptr
0x100440f79  mov     rcx, [rsp+0B8h+Block]; Block
0x100440f7e  test    rcx, rcx
0x100440f81  jz      short loc_100440F89
0x100440f83  call    cs:__imp_free
0x100440f89  xor     ecx, ecx
0x100440f8b  mov     eax, cs:_bidGblFlags
0x100440f91  and     eax, esi
0x100440f93  cmp     eax, esi
0x100440f95  jnz     short loc_100440FD5
0x100440f97  mov     rax, cs:off_1005E60C0; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x100440f9e  test    rax, rax
0x100440fa1  jz      short loc_100440FD5
0x100440fa3  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100440fab  jz      short loc_100440FD5
0x100440fad  mov     r9, cs:off_1005E60C0; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x100440fb4  xor     edx, edx
0x100440fb6  mov     rax, cs:off_1005D39E0
0x100440fbd  mov     r8d, 0DDC00h
0x100440fc3  mov     qword ptr [rsp+0B8h+bIgnoreCase], rcx
0x100440fc8  mov     rcx, cs:_bidID
0x100440fcf  call    cs:__guard_dispatch_icall_fptr
0x100440fd5  or      eax, 0FFFFFFFFh
0x100440fd8  mov     rcx, [rsp+0B8h+var_58]
0x100440fdd  xor     rcx, rsp; StackCookie
0x100440fe0  call    __security_check_cookie
0x100440fe5  add     rsp, 78h
0x100440fe9  pop     r15
0x100440feb  pop     r14
0x100440fed  pop     r13
0x100440fef  pop     r12
0x100440ff1  pop     rdi
0x100440ff2  pop     rsi
0x100440ff3  pop     rbp
0x100440ff4  pop     rbx
0x100440ff5  retn
0x100440ff6  mov     r9d, 8
0x100440ffc  lea     r8, aVersion; "Version;"
0x100441003  mov     edx, eax
0x100441005  mov     rcx, r10; lpCurrentChar
0x100441008  call    StrStrA_SYS
0x10044100d  test    rax, rax
0x100441010  jz      loc_100440F79
0x100441016  mov     r15d, 3Bh ; ';'
0x10044101c  lea     rcx, [rax+8]; Str
0x100441020  mov     edx, r15d; Val
0x100441023  call    cs:__imp_strchr
0x100441029  mov     rdi, rax
0x10044102c  test    rax, rax
0x10044102f  jz      loc_100440F79
0x100441035  inc     rdi
0x100441038  cmp     [rdi], r15b
0x10044103b  jz      loc_10044125D
0x100441041  lea     r14, [rsp+0B8h+var_80]
0x100441046  cmp     ebp, 0Ah
0x100441049  jnb     loc_100440F79
0x10044104f  mov     edx, r15d; Val
0x100441052  mov     rcx, rdi; Str
0x100441055  call    cs:__imp_strchr
0x10044105b  xor     ecx, ecx
0x10044105d  mov     rbx, rax
0x100441060  test    rax, rax
0x100441063  jz      loc_100440F79
0x100441069  mov     [rax], cl
0x10044106b  inc     rbx
0x10044106e  mov     rcx, rbx; Str
0x100441071  mov     edx, r15d; Val
0x100441074  call    cs:__imp_strchr
0x10044107a  xor     ecx, ecx
0x10044107c  mov     r15, rax
0x10044107f  test    rax, rax
0x100441082  jz      loc_100440F79
0x100441088  mov     [rax], cl
0x10044108a  mov     ecx, r15d
0x10044108d  sub     ecx, ebx
0x10044108f  cmp     ecx, 0FFh
0x100441095  jg      loc_100440F79
0x10044109b  movsx   edx, byte ptr [rdi]
0x10044109e  sub     edx, 61h ; 'a'
0x1004410a1  jz      loc_10044124A
0x1004410a7  sub     edx, 1
0x1004410aa  jz      loc_10044124A
0x1004410b0  sub     edx, 0Ch
0x1004410b3  jz      loc_100441144
0x1004410b9  sub     edx, 4
0x1004410bc  jz      loc_10044124A
0x1004410c2  sub     edx, 1
0x1004410c5  jz      loc_10044124A
0x1004410cb  sub     edx, 1
0x1004410ce  jz      short loc_1004410DE
0x1004410d0  cmp     edx, 2
0x1004410d3  jnz     loc_100440F79
0x1004410d9  jmp     loc_10044124A
0x1004410de  mov     edx, 7
0x1004410e3  mov     rcx, r12
0x1004410e6  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x1004410eb  mov     rdi, rax
0x1004410ee  test    rax, rax
0x1004410f1  jz      loc_10044124A
0x1004410f7  mov     dword ptr [r14], 7
0x1004410fe  mov     rcx, rbx; String
0x100441101  add     r14, 4
0x100441105  inc     ebp
0x100441107  call    cs:__imp_atoi
0x10044110d  test    eax, eax
0x10044110f  jz      loc_100440F79
0x100441115  lea     rcx, [rdi+608h]; unsigned __int16 *
0x10044111c  mov     r9, rbx
0x10044111f  lea     r8, aHs_0; "%hs"
0x100441126  mov     edx, 100h; unsigned __int64
0x10044112b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100441130  test    eax, eax
0x100441132  js      loc_100440F79
0x100441138  mov     byte ptr [rdi+80Ah], 1
0x10044113f  jmp     loc_10044124A
0x100441144  mov     edx, 1
0x100441149  mov     rcx, r12
0x10044114c  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x100441151  mov     rdi, rax
0x100441154  test    rax, rax
0x100441157  jz      loc_10044124A
0x10044115d  mov     dword ptr [r14], 1
0x100441164  inc     ebp
0x100441166  add     r14, 4
0x10044116a  mov     al, 5Ch ; '\'
0x10044116c  cmp     [rbx], al
0x10044116e  jnz     loc_100440F79
0x100441174  cmp     [rbx+1], al
0x100441177  jnz     loc_100440F79
0x10044117d  add     rbx, 2
0x100441181  xor     edx, edx
0x100441183  mov     cl, [rbx]
0x100441185  test    cl, cl
0x100441187  jz      loc_100440F79
0x10044118d  cmp     cl, al
0x10044118f  jz      short loc_10044119A
0x100441191  inc     rbx
0x100441194  mov     cl, [rbx]
0x100441196  test    cl, cl
0x100441198  jnz     short loc_10044118D
0x10044119a  cmp     [rbx], dl
0x10044119c  jz      loc_100440F79
0x1004411a2  mov     rcx, r13; lpString2
0x1004411a5  call    ?IsLocalHost@@YA_NPEBG@Z; IsLocalHost(ushort const *)
0x1004411aa  test    al, al
0x1004411ac  jz      short loc_100441219
0x1004411ae  lea     r8, aClusterNetwork; "_CLUSTER_NETWORK_NAME_"
0x1004411b5  xor     edx, edx; BufferCount
0x1004411b7  lea     rcx, [rsp+0B8h+Block]; Buffer
0x1004411bc  call    cs:__imp__wdupenv_s
0x1004411c2  test    eax, eax
0x1004411c4  jnz     loc_100440F79
0x1004411ca  mov     rcx, [rsp+0B8h+Block]; lpString1
0x1004411cf  xor     eax, eax
0x1004411d1  test    rcx, rcx
0x1004411d4  jz      short loc_1004411F5
0x1004411d6  or      r9d, 0FFFFFFFFh; cchCount2
0x1004411da  mov     [rsp+0B8h+bIgnoreCase], 1; bIgnoreCase
0x1004411e2  or      edx, r9d; cchCount1
0x1004411e5  mov     r8, r13; lpString2
0x1004411e8  call    cs:__imp_CompareStringOrdinal
0x1004411ee  cmp     eax, 2
0x1004411f1  jz      short loc_100441219
0x1004411f3  xor     eax, eax
0x1004411f5  lea     rcx, [rdi+608h]; unsigned __int16 *
0x1004411fc  mov     [rdi+806h], ax
0x100441203  mov     r9, rbx
0x100441206  lea     r8, aHs; "\\\\.%hs"
0x10044120d  mov     edx, 105h; unsigned __int64
0x100441212  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100441217  jmp     short loc_100441242
0x100441219  xor     eax, eax
0x10044121b  mov     qword ptr [rsp+0B8h+bIgnoreCase], rbx
0x100441220  lea     rcx, [rdi+608h]; unsigned __int16 *
0x100441227  mov     [rdi+806h], ax
0x10044122e  mov     r9, r13
0x100441231  lea     r8, aSHs; "\\\\%s%hs"
0x100441238  mov     edx, 105h; unsigned __int64
0x10044123d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100441242  test    eax, eax
0x100441244  js      loc_100440F79
0x10044124a  lea     rdi, [r15+1]
0x10044124e  mov     r15d, 3Bh ; ';'
0x100441254  cmp     [rdi], r15b
0x100441257  jnz     loc_100441046
0x10044125d  mov     rbx, [r12]
0x100441261  xor     r13d, r13d
0x100441264  test    rbx, rbx
0x100441267  jz      short loc_1004412D6
0x100441269  movsxd  rdi, ebp
0x10044126c  mov     rcx, r13
0x10044126f  test    rdi, rdi
0x100441272  jle     short loc_100441284
0x100441274  mov     eax, [rbx]
0x100441276  cmp     [rsp+rcx*4+0B8h+var_80], eax
0x10044127a  jz      short loc_100441284
0x10044127c  inc     rcx
0x10044127f  cmp     rcx, rdi
0x100441282  jl      short loc_100441276
0x100441284  lea     r8, [rbx+0A08h]
0x10044128b  cmp     rcx, rdi
0x10044128e  jnz     short loc_1004412C3
0x100441290  mov     edx, [rbx]
0x100441292  mov     rbx, [r8]
0x100441295  cmp     edx, 4
0x100441298  jz      short loc_1004412D1
0x10044129a  mov     rcx, r12
0x10044129d  call    ?RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::RemoveProt(ProviderNum)
0x1004412a2  mov     r8, rax
0x1004412a5  test    rax, rax
0x1004412a8  jz      short loc_1004412D1
0x1004412aa  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x1004412b1  mov     rdx, [rcx]
0x1004412b4  mov     rax, [rdx+68h]
0x1004412b8  mov     rdx, r8
0x1004412bb  call    cs:__guard_dispatch_icall_fptr
0x1004412c1  jmp     short loc_1004412D1
0x1004412c3  mov     eax, dword ptr [rsp+rdi*4+0B8h+Block+4]
0x1004412c7  dec     rdi
0x1004412ca  mov     rbx, [r8]
0x1004412cd  mov     [rsp+rcx*4+0B8h+var_80], eax
0x1004412d1  test    rbx, rbx
0x1004412d4  jnz     short loc_10044126C
0x1004412d6  mov     rcx, [rsp+0B8h+Block]; Block
0x1004412db  test    rcx, rcx
0x1004412de  jz      short loc_1004412E6
0x1004412e0  call    cs:__imp_free
0x1004412e6  mov     eax, cs:_bidGblFlags
0x1004412ec  and     eax, esi
0x1004412ee  cmp     eax, esi
0x1004412f0  jnz     short loc_100441330
0x1004412f2  mov     rax, cs:off_1005E60B8; "<SSRP::ParseSsrpString|RET|SNI> success"...
0x1004412f9  test    rax, rax
0x1004412fc  jz      short loc_100441330
0x1004412fe  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100441306  jz      short loc_100441330
0x100441308  mov     r9, cs:off_1005E60B8; "<SSRP::ParseSsrpString|RET|SNI> success"...
0x10044130f  xor     edx, edx
0x100441311  mov     rcx, cs:_bidID
0x100441318  mov     r8d, 0DB000h
0x10044131e  mov     rax, cs:off_1005D39E0
0x100441325  mov     qword ptr [rsp+0B8h+bIgnoreCase], r13
0x10044132a  call    cs:__guard_dispatch_icall_fptr
0x100441330  xor     eax, eax
0x100441332  jmp     loc_100440FD8
```
