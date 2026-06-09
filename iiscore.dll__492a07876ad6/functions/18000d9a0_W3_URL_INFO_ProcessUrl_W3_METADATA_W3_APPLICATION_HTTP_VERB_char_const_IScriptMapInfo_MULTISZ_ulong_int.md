# W3_URL_INFO::ProcessUrl(W3_METADATA *,W3_APPLICATION *,_HTTP_VERB,char const *,IScriptMapInfo * *,MULTISZ *,ulong *,int *)

- ea: `0x18000d9a0`
- end: `0x18000de70`
- name: `?ProcessUrl@W3_URL_INFO@@QEAAJPEAVW3_METADATA@@PEAVW3_APPLICATION@@W4_HTTP_VERB@@PEBDPEAPEAVIScriptMapInfo@@PEAVMULTISZ@@PEAKPEAH@Z`
- size: `1232`
- prototype: `__int64 __fastcall(W3_URL_INFO *this, struct W3_METADATA *, struct W3_APPLICATION *, enum _HTTP_VERB, char *, struct IScriptMapInfo **, struct MULTISZ *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000bce0`
- `0x180022a10`

## callees

- `0x18000d9a0`
- `0x18000e420`
- `0x18003773a`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000dbf5`
- `msvcrt!_wcsicmp` at `0x18000dbf5`
- `msvcrt!wcschr` at `0x18000db63`
- `msvcrt!wcschr` at `0x18000db63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dc61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dcb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dcb4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc3c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000dc3c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000dbc7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000dbc7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dba7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000dba7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dc26`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000dc26`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db43`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000db43`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000db8c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000db8c`

## string_xrefs

- `0x18000dd7f`: `DELETE`

## pseudocode

```c
__int64 __fastcall W3_URL_INFO::ProcessUrl(
        W3_URL_INFO *this,
        struct W3_METADATA *a2,
        struct W3_APPLICATION *a3,
        enum _HTTP_VERB a4,
        char *a5,
        struct IScriptMapInfo **a6,
        struct MULTISZ *a7,
        unsigned int *a8,
        int *a9)
{
  unsigned int v10; // ebx
  unsigned int *v12; // r8
  int *v14; // rdx
  int v15; // r12d
  __int64 v16; // r15
  struct IScriptMapInfo **v18; // r9
  __int64 result; // rax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rax
  struct META_SCRIPT_MAP_ENTRY *v22; // rax
  struct IScriptMapInfo *v23; // r14
  const wchar_t *v24; // rdi
  wchar_t *v25; // rax
  wchar_t *v26; // r14
  int v27; // eax
  const wchar_t *Str; // rbp
  __int64 i; // rbx
  __int64 v30; // rdi
  const wchar_t *v31; // rax
  _WORD *v32; // rax
  unsigned int v33; // edi
  bool v34; // zf
  unsigned __int8 v35; // si
  signed __int32 v36[8]; // [rsp+0h] [rbp-168h] BYREF
  char v37; // [rsp+30h] [rbp-138h]
  unsigned int v38; // [rsp+34h] [rbp-134h] BYREF
  struct IScriptMapInfo **v39; // [rsp+38h] [rbp-130h]
  unsigned int *v40; // [rsp+40h] [rbp-128h]
  int *v41; // [rsp+48h] [rbp-120h]
  struct META_SCRIPT_MAP_ENTRY *v42; // [rsp+50h] [rbp-118h]
  _BYTE v43[56]; // [rsp+58h] [rbp-110h] BYREF
  unsigned __int16 v44[64]; // [rsp+90h] [rbp-D8h] BYREF

  v10 = 0;
  v12 = a8;
  v14 = a9;
  v15 = 0;
  v16 = a4;
  v18 = a6;
  v39 = a6;
  v40 = a8;
  v41 = a9;
  v38 = 0;
  if ( (_DWORD)v16 != 1 )
  {
    if ( !a7 )
    {
      v15 = 1;
      if ( *((_BYTE *)this + v16 + 968) )
        goto LABEL_4;
    }
    if ( (_DWORD)v16 == 4 )
    {
      a5 = "GET";
    }
    else
    {
      switch ( (int)v16 )
      {
        case 3:
          a5 = "OPTIONS";
          break;
        case 5:
          a5 = "HEAD";
          break;
        case 6:
          a5 = "POST";
          break;
        case 7:
          a5 = "PUT";
          break;
        case 8:
          a5 = "DELETE";
          break;
        case 9:
          a5 = "TRACE";
          break;
        case 10:
          a5 = "CONNECT";
          break;
        case 11:
          a5 = "TRACK";
          break;
        case 12:
          a5 = "MOVE";
          break;
        case 13:
          a5 = "COPY";
          break;
        case 14:
          a5 = "PROPFIND";
          break;
        case 15:
          a5 = "PROPPATCH";
          break;
        case 16:
          a5 = "MKCOL";
          break;
        case 17:
          a5 = "LOCK";
          break;
        case 18:
          a5 = "UNLOCK";
          break;
        case 19:
          a5 = "SEARCH";
          break;
        default:
          a5 = 0;
          break;
      }
    }
  }
  v20 = *((_QWORD *)this + 2);
  v37 = 0;
  v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(char *))(v20 + 40))((char *)this + 16);
  v22 = META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(
          *((META_SCRIPT_MAP_TABLE **)a2 + 21),
          v21,
          a5,
          *((_DWORD *)a2 + 59),
          &v38,
          a7);
  v42 = v22;
  v23 = v22;
  if ( v22 )
  {
    if ( *(_WORD *)(*(__int64 (__fastcall **)(struct META_SCRIPT_MAP_ENTRY *, _QWORD))(*(_QWORD *)v22 + 32LL))(v22, 0) )
    {
      v37 = 1;
    }
    else if ( a3 )
    {
      v24 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IScriptMapInfo *, _QWORD))(*(_QWORD *)v23 + 16LL))(
                               v23,
                               0);
      memset_0(v44, 0, sizeof(v44));
      STRU::STRU((STRU *)v43, v44, 0x40u);
      while ( 1 )
      {
        v10 = 0;
        if ( !*v24 )
          break;
        v25 = wcschr(v24, 0x2Cu);
        v26 = v25;
        v27 = v25 ? STRU::Copy((STRU *)v43, v24, v25 - v24) : STRU::Copy((STRU *)v43, v24);
        v10 = v27;
        if ( v27 < 0 )
          break;
        Str = STRU::QueryStr((STRU *)v43);
        for ( i = 0; (unsigned int)i < *((_DWORD *)a3 + 58); i = (unsigned int)(i + 1) )
        {
          v30 = *((_QWORD *)BUFFER::QueryPtr((struct W3_APPLICATION *)((char *)a3 + 240)) + i);
          v31 = *(const wchar_t **)(v30 + 8);
          if ( !v31 )
            v31 = (const wchar_t *)(***(__int64 (__fastcall ****)(_QWORD))(v30 + 32))(*(_QWORD *)(v30 + 32));
          if ( !_wcsicmp(v31, Str) )
          {
            v32 = *(_WORD **)(v30 + 16);
            if ( v32 )
            {
              v10 = 0;
              if ( *v32 )
              {
                v37 = 1;
                goto LABEL_31;
              }
            }
            break;
          }
        }
        v10 = 0;
        if ( !v26 )
          break;
        v24 = v26 + 1;
      }
LABEL_31:
      STRU::~STRU((STRU *)v43);
      v23 = v42;
    }
  }
  v33 = v38;
  if ( v15 )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 120);
    if ( *((_BYTE *)this + v16 + 968) )
    {
      v35 = v37;
    }
    else
    {
      v34 = a3 == 0;
      *((_QWORD *)this + v16 + 131) = v23;
      v35 = v37;
      if ( !v34 )
      {
        *((_WORD *)this + v16 + 504) = v33;
        *((_BYTE *)this + v16 + 988) = v35;
        _InterlockedOr(v36, 0);
        *((_BYTE *)this + v16 + 968) = 1;
      }
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 120);
  }
  else
  {
    v35 = v37;
  }
  if ( (v10 & 0x80000000) != 0 )
    return v10;
  if ( !v15 )
  {
    if ( v39 )
      *v39 = v23;
    if ( v40 )
      *v40 = v33;
    if ( v41 )
      *v41 = v35;
    return v10;
  }
  v14 = v41;
  v12 = v40;
  v18 = v39;
LABEL_4:
  if ( v18 )
    *v18 = (struct IScriptMapInfo *)*((_QWORD *)this + v16 + 131);
  if ( v12 )
    *v12 = *((unsigned __int16 *)this + v16 + 504);
  result = v10;
  if ( v14 )
    *v14 = *((unsigned __int8 *)this + v16 + 988);
  return result;
}

```

## disassembly

```asm
0x18000d9a0  push    rbx
0x18000d9a2  push    rbp
0x18000d9a3  push    rsi
0x18000d9a4  push    rdi
0x18000d9a5  push    r12
0x18000d9a7  push    r13
0x18000d9a9  push    r14
0x18000d9ab  push    r15
0x18000d9ad  sub     rsp, 128h
0x18000d9b4  mov     rax, cs:__security_cookie
0x18000d9bb  xor     rax, rsp
0x18000d9be  mov     [rsp+168h+var_58], rax
0x18000d9c6  mov     rbp, [rsp+168h+arg_20]
0x18000d9ce  xor     ebx, ebx
0x18000d9d0  mov     rdi, [rsp+168h+arg_30]
0x18000d9d8  mov     rsi, r8
0x18000d9db  mov     r8, [rsp+168h+arg_38]
0x18000d9e3  mov     r14, rdx
0x18000d9e6  mov     rdx, [rsp+168h+arg_40]
0x18000d9ee  xor     r12d, r12d
0x18000d9f1  movsxd  r15, r9d
0x18000d9f4  mov     r13, rcx
0x18000d9f7  mov     r9, [rsp+168h+arg_28]
0x18000d9ff  mov     [rsp+168h+var_130], r9
0x18000da04  mov     [rsp+168h+var_128], r8
0x18000da09  mov     [rsp+168h+var_120], rdx
0x18000da0e  mov     [rsp+168h+var_134], ebx
0x18000da12  cmp     r15d, 1
0x18000da16  jz      short loc_18000DA96
0x18000da18  test    rdi, rdi
0x18000da1b  jnz     short loc_18000DA85
0x18000da1d  mov     r12d, 1
0x18000da23  cmp     [r15+rcx+3C8h], bl
0x18000da2b  jz      short loc_18000DA85
0x18000da2d  test    r9, r9
0x18000da30  jz      short loc_18000DA3D
0x18000da32  mov     rcx, [r13+r15*8+418h]
0x18000da3a  mov     [r9], rcx
0x18000da3d  test    r8, r8
0x18000da40  jz      short loc_18000DA4E
0x18000da42  movzx   ecx, word ptr [r13+r15*2+3F0h]
0x18000da4b  mov     [r8], ecx
0x18000da4e  mov     eax, ebx
0x18000da50  test    rdx, rdx
0x18000da53  jz      short loc_18000DA60
0x18000da55  movzx   ecx, byte ptr [r15+r13+3DCh]
0x18000da5e  mov     [rdx], ecx
0x18000da60  mov     rcx, [rsp+168h+var_58]
0x18000da68  xor     rcx, rsp; StackCookie
0x18000da6b  call    __security_check_cookie
0x18000da70  add     rsp, 128h
0x18000da77  pop     r15
0x18000da79  pop     r14
0x18000da7b  pop     r13
0x18000da7d  pop     r12
0x18000da7f  pop     rdi
0x18000da80  pop     rsi
0x18000da81  pop     rbp
0x18000da82  pop     rbx
0x18000da83  retn
0x18000da85  cmp     r15d, 4
0x18000da89  jnz     loc_18000DD29
0x18000da8f  lea     rbp, aGet; "GET"
0x18000da96  mov     rax, [r13+10h]
0x18000da9a  lea     rcx, [r13+10h]
0x18000da9e  mov     [rsp+168h+var_138], bl
0x18000daa2  mov     rax, [rax+28h]
0x18000daa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daab  mov     r9d, [r14+0ECh]; unsigned int
0x18000dab2  lea     rcx, [rsp+168h+var_134]
0x18000dab7  mov     [rsp+168h+var_140], rdi; struct MULTISZ *
0x18000dabc  mov     r8, rbp; char *
0x18000dabf  mov     [rsp+168h+var_148], rcx; unsigned int *
0x18000dac4  mov     rdx, rax; unsigned __int16 *
0x18000dac7  mov     rcx, [r14+0A8h]; this
0x18000dace  call    ?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z; META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)
0x18000dad3  mov     [rsp+168h+var_118], rax
0x18000dad8  mov     r14, rax
0x18000dadb  test    rax, rax
0x18000dade  jz      loc_18000DC4D
0x18000dae4  mov     rcx, [rax]
0x18000dae7  xor     edx, edx
0x18000dae9  mov     rax, [rcx+20h]
0x18000daed  mov     rcx, r14
0x18000daf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf5  cmp     [rax], bx
0x18000daf8  jnz     loc_18000DE16
0x18000dafe  test    rsi, rsi
0x18000db01  jz      loc_18000DC4D
0x18000db07  mov     rax, [r14]
0x18000db0a  xor     edx, edx
0x18000db0c  mov     rcx, r14
0x18000db0f  mov     rax, [rax+10h]
0x18000db13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db18  xor     edx, edx; Val
0x18000db1a  lea     rcx, [rsp+168h+var_D8]; void *
0x18000db22  mov     r8d, 80h; Size
0x18000db28  mov     rdi, rax
0x18000db2b  call    memset_0
0x18000db30  mov     r8d, 40h ; '@'
0x18000db36  lea     rdx, [rsp+168h+var_D8]
0x18000db3e  lea     rcx, [rsp+168h+var_110]
0x18000db43  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000db4a  nop     dword ptr [rax+rax+00h]
0x18000db4f  nop
0x18000db50  xor     ebx, ebx
0x18000db52  cmp     [rdi], bx
0x18000db55  jz      loc_18000DC37
0x18000db5b  mov     edx, 2Ch ; ','; Ch
0x18000db60  mov     rcx, rdi; Str
0x18000db63  call    cs:__imp_wcschr
0x18000db6a  nop     dword ptr [rax+rax+00h]
0x18000db6f  mov     rdx, rdi
0x18000db72  lea     rcx, [rsp+168h+var_110]
0x18000db77  mov     r14, rax
0x18000db7a  test    rax, rax
0x18000db7d  jz      loc_18000DC26
0x18000db83  mov     r8, rax
0x18000db86  sub     r8, rdi
0x18000db89  sar     r8, 1
0x18000db8c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000db93  nop     dword ptr [rax+rax+00h]
0x18000db98  mov     ebx, eax
0x18000db9a  test    eax, eax
0x18000db9c  js      loc_18000DC37
0x18000dba2  lea     rcx, [rsp+168h+var_110]
0x18000dba7  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000dbae  nop     dword ptr [rax+rax+00h]
0x18000dbb3  mov     rbp, rax
0x18000dbb6  xor     ebx, ebx
0x18000dbb8  cmp     ebx, [rsi+0E8h]
0x18000dbbe  jnb     short loc_18000DC16
0x18000dbc0  lea     rcx, [rsi+0F0h]
0x18000dbc7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000dbce  nop     dword ptr [rax+rax+00h]
0x18000dbd3  mov     rdi, [rax+rbx*8]
0x18000dbd7  mov     rax, [rdi+8]
0x18000dbdb  test    rax, rax
0x18000dbde  jnz     short loc_18000DBEF
0x18000dbe0  mov     rcx, [rdi+20h]
0x18000dbe4  mov     rax, [rcx]
0x18000dbe7  mov     rax, [rax]
0x18000dbea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbef  mov     rdx, rbp; String2
0x18000dbf2  mov     rcx, rax; String1
0x18000dbf5  call    cs:__imp__wcsicmp
0x18000dbfc  nop     dword ptr [rax+rax+00h]
0x18000dc01  test    eax, eax
0x18000dc03  jz      short loc_18000DC09
0x18000dc05  inc     ebx
0x18000dc07  jmp     short loc_18000DBB8
0x18000dc09  mov     rax, [rdi+10h]
0x18000dc0d  test    rax, rax
0x18000dc10  jnz     loc_18000DD0D
0x18000dc16  xor     ebx, ebx
0x18000dc18  test    r14, r14
0x18000dc1b  jz      short loc_18000DC37
0x18000dc1d  lea     rdi, [r14+2]
0x18000dc21  jmp     loc_18000DB50
0x18000dc26  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000dc2d  nop     dword ptr [rax+rax+00h]
0x18000dc32  jmp     loc_18000DB98
0x18000dc37  lea     rcx, [rsp+168h+var_110]
0x18000dc3c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000dc43  nop     dword ptr [rax+rax+00h]
0x18000dc48  mov     r14, [rsp+168h+var_118]
0x18000dc4d  mov     edi, [rsp+168h+var_134]
0x18000dc51  test    r12d, r12d
0x18000dc54  jz      loc_18000DE20
0x18000dc5a  lea     rcx, [r13+3C0h]; SRWLock
0x18000dc61  call    cs:__imp_AcquireSRWLockExclusive
0x18000dc68  nop     dword ptr [rax+rax+00h]
0x18000dc6d  cmp     byte ptr [r15+r13+3C8h], 0
0x18000dc76  jnz     loc_18000DD22
0x18000dc7c  test    rsi, rsi
0x18000dc7f  mov     [r13+r15*8+418h], r14
0x18000dc87  movzx   esi, [rsp+168h+var_138]
0x18000dc8c  jz      short loc_18000DCAD
0x18000dc8e  mov     [r13+r15*2+3F0h], di
0x18000dc97  mov     [r15+r13+3DCh], sil
0x18000dc9f  lock or [rsp+168h+var_168], 0
0x18000dca4  mov     byte ptr [r15+r13+3C8h], 1
0x18000dcad  lea     rcx, [r13+3C0h]; SRWLock
0x18000dcb4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dcbb  nop     dword ptr [rax+rax+00h]
0x18000dcc0  test    ebx, ebx
0x18000dcc2  js      short loc_18000DD06
0x18000dcc4  test    r12d, r12d
0x18000dcc7  jz      short loc_18000DCDD
0x18000dcc9  mov     rdx, [rsp+168h+var_120]
0x18000dcce  mov     r8, [rsp+168h+var_128]
0x18000dcd3  mov     r9, [rsp+168h+var_130]
0x18000dcd8  jmp     loc_18000DA2D
0x18000dcdd  mov     rax, [rsp+168h+var_130]
0x18000dce2  test    rax, rax
0x18000dce5  jz      short loc_18000DCEA
0x18000dce7  mov     [rax], r14
0x18000dcea  mov     rax, [rsp+168h+var_128]
0x18000dcef  test    rax, rax
0x18000dcf2  jz      short loc_18000DCF6
0x18000dcf4  mov     [rax], edi
0x18000dcf6  mov     rcx, [rsp+168h+var_120]
0x18000dcfb  test    rcx, rcx
0x18000dcfe  jz      short loc_18000DD06
0x18000dd00  movzx   eax, sil
0x18000dd04  mov     [rcx], eax
0x18000dd06  mov     eax, ebx
0x18000dd08  jmp     loc_18000DA60
0x18000dd0d  xor     ebx, ebx
0x18000dd0f  cmp     [rax], bx
0x18000dd12  jz      loc_18000DC16
0x18000dd18  mov     [rsp+168h+var_138], 1
0x18000dd1d  jmp     loc_18000DC37
0x18000dd22  movzx   esi, [rsp+168h+var_138]
0x18000dd27  jmp     short loc_18000DCAD
0x18000dd29  lea     eax, [r15-3]; switch 17 cases
0x18000dd2d  cmp     eax, 10h
0x18000dd30  ja      def_18000DD49; jumptable 000000018000DD49 default case, case 4
0x18000dd36  lea     rdx, __ImageBase
0x18000dd3d  cdqe
0x18000dd3f  mov     ecx, ds:(jpt_18000DD49 - 180000000h)[rdx+rax*4]
0x18000dd46  add     rcx, rdx
0x18000dd49  jmp     rcx; switch jump
0x18000dd4f  lea     rbp, aOptions; jumptable 000000018000DD49 case 3
0x18000dd56  jmp     loc_18000DA96
0x18000dd5b  lea     rbp, aHead; jumptable 000000018000DD49 case 5
0x18000dd62  jmp     loc_18000DA96
0x18000dd67  lea     rbp, aPost; jumptable 000000018000DD49 case 6
0x18000dd6e  jmp     loc_18000DA96
0x18000dd73  lea     rbp, aPut; jumptable 000000018000DD49 case 7
0x18000dd7a  jmp     loc_18000DA96
0x18000dd7f  lea     rbp, aDelete; jumptable 000000018000DD49 case 8
0x18000dd86  jmp     loc_18000DA96
0x18000dd8b  lea     rbp, aTrace; jumptable 000000018000DD49 case 9
0x18000dd92  jmp     loc_18000DA96
0x18000dd97  lea     rbp, aConnect; jumptable 000000018000DD49 case 10
0x18000dd9e  jmp     loc_18000DA96
0x18000dda3  lea     rbp, aTrack; jumptable 000000018000DD49 case 11
0x18000ddaa  jmp     loc_18000DA96
0x18000ddaf  lea     rbp, aMove; jumptable 000000018000DD49 case 12
0x18000ddb6  jmp     loc_18000DA96
0x18000ddbb  lea     rbp, aCopy; jumptable 000000018000DD49 case 13
0x18000ddc2  jmp     loc_18000DA96
0x18000ddc7  lea     rbp, aPropfind; jumptable 000000018000DD49 case 14
0x18000ddce  jmp     loc_18000DA96
0x18000ddd3  lea     rbp, aProppatch; jumptable 000000018000DD49 case 15
0x18000ddda  jmp     loc_18000DA96
0x18000dddf  lea     rbp, aMkcol; jumptable 000000018000DD49 case 16
0x18000dde6  jmp     loc_18000DA96
0x18000ddeb  lea     rbp, aLock; jumptable 000000018000DD49 case 17
0x18000ddf2  jmp     loc_18000DA96
0x18000ddf7  lea     rbp, aUnlock; jumptable 000000018000DD49 case 18
0x18000ddfe  jmp     loc_18000DA96
0x18000de03  lea     rbp, aSearch; jumptable 000000018000DD49 case 19
0x18000de0a  jmp     loc_18000DA96
0x18000de0f  xor     ebp, ebp; jumptable 000000018000DD49 default case, case 4
0x18000de11  jmp     loc_18000DA96
0x18000de16  mov     [rsp+168h+var_138], 1
0x18000de1b  jmp     loc_18000DC4D
0x18000de20  movzx   esi, [rsp+168h+var_138]
0x18000de25  jmp     loc_18000DCC0
```
