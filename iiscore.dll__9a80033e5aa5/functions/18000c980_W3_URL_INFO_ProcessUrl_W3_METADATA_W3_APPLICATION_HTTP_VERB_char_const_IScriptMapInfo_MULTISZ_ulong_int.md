# W3_URL_INFO::ProcessUrl(W3_METADATA *,W3_APPLICATION *,_HTTP_VERB,char const *,IScriptMapInfo * *,MULTISZ *,ulong *,int *)

- ea: `0x18000c980`
- end: `0x18000ce10`
- name: `?ProcessUrl@W3_URL_INFO@@QEAAJPEAVW3_METADATA@@PEAVW3_APPLICATION@@W4_HTTP_VERB@@PEBDPEAPEAVIScriptMapInfo@@PEAVMULTISZ@@PEAKPEAH@Z`
- size: `1168`
- prototype: `__int64 __fastcall(W3_URL_INFO *__hidden this, struct W3_METADATA *, struct W3_APPLICATION *, enum _HTTP_VERB, const char *, struct IScriptMapInfo **, struct MULTISZ *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000aed0`
- `0x180020e20`

## callees

- `0x18000c980`
- `0x18000d8a0`
- `0x18003439a`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000cbb9`
- `msvcrt!_wcsicmp` at `0x18000cbb9`
- `msvcrt!wcschr` at `0x18000cb43`
- `msvcrt!wcschr` at `0x18000cb43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cc13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc60`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000cbf4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cb91`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000cb91`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb77`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000cb77`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cbe4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000cbe4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000cb22`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000cb22`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000cb66`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000cb66`

## string_xrefs

- `0x18000cd21`: `DELETE`

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
0x18000c980  push    rbx
0x18000c982  push    rbp
0x18000c983  push    rsi
0x18000c984  push    rdi
0x18000c985  push    r12
0x18000c987  push    r13
0x18000c989  push    r14
0x18000c98b  push    r15
0x18000c98d  sub     rsp, 128h
0x18000c994  mov     rax, cs:__security_cookie
0x18000c99b  xor     rax, rsp
0x18000c99e  mov     [rsp+168h+var_58], rax
0x18000c9a6  mov     rbp, [rsp+168h+arg_20]
0x18000c9ae  xor     ebx, ebx
0x18000c9b0  mov     rdi, [rsp+168h+arg_30]
0x18000c9b8  mov     rsi, r8
0x18000c9bb  mov     r8, [rsp+168h+arg_38]
0x18000c9c3  mov     r14, rdx
0x18000c9c6  mov     rdx, [rsp+168h+arg_40]
0x18000c9ce  xor     r12d, r12d
0x18000c9d1  movsxd  r15, r9d
0x18000c9d4  mov     r13, rcx
0x18000c9d7  mov     r9, [rsp+168h+arg_28]
0x18000c9df  mov     [rsp+168h+var_130], r9
0x18000c9e4  mov     [rsp+168h+var_128], r8
0x18000c9e9  mov     [rsp+168h+var_120], rdx
0x18000c9ee  mov     [rsp+168h+var_134], ebx
0x18000c9f2  cmp     r15d, 1
0x18000c9f6  jz      short loc_18000CA75
0x18000c9f8  test    rdi, rdi
0x18000c9fb  jnz     short loc_18000CA64
0x18000c9fd  mov     r12d, 1
0x18000ca03  cmp     [r15+rcx+3C8h], bl
0x18000ca0b  jz      short loc_18000CA64
0x18000ca0d  test    r9, r9
0x18000ca10  jz      short loc_18000CA1D
0x18000ca12  mov     rcx, [r13+r15*8+418h]
0x18000ca1a  mov     [r9], rcx
0x18000ca1d  test    r8, r8
0x18000ca20  jz      short loc_18000CA2E
0x18000ca22  movzx   ecx, word ptr [r13+r15*2+3F0h]
0x18000ca2b  mov     [r8], ecx
0x18000ca2e  mov     eax, ebx
0x18000ca30  test    rdx, rdx
0x18000ca33  jz      short loc_18000CA40
0x18000ca35  movzx   ecx, byte ptr [r15+r13+3DCh]
0x18000ca3e  mov     [rdx], ecx
0x18000ca40  mov     rcx, [rsp+168h+var_58]
0x18000ca48  xor     rcx, rsp; StackCookie
0x18000ca4b  call    __security_check_cookie
0x18000ca50  add     rsp, 128h
0x18000ca57  pop     r15
0x18000ca59  pop     r14
0x18000ca5b  pop     r13
0x18000ca5d  pop     r12
0x18000ca5f  pop     rdi
0x18000ca60  pop     rsi
0x18000ca61  pop     rbp
0x18000ca62  pop     rbx
0x18000ca63  retn
0x18000ca64  cmp     r15d, 4
0x18000ca68  jnz     loc_18000CCCF
0x18000ca6e  lea     rbp, aGet; "GET"
0x18000ca75  mov     rax, [r13+10h]
0x18000ca79  lea     rcx, [r13+10h]
0x18000ca7d  mov     [rsp+168h+var_138], bl
0x18000ca81  mov     rax, [rax+28h]
0x18000ca85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8a  mov     r9d, [r14+0ECh]; unsigned int
0x18000ca91  lea     rcx, [rsp+168h+var_134]
0x18000ca96  mov     [rsp+168h+var_140], rdi; struct MULTISZ *
0x18000ca9b  mov     r8, rbp; char *
0x18000ca9e  mov     [rsp+168h+var_148], rcx; unsigned int *
0x18000caa3  mov     rdx, rax; unsigned __int16 *
0x18000caa6  mov     rcx, [r14+0A8h]; this
0x18000caad  call    ?CalculateScriptMapEntry@META_SCRIPT_MAP_TABLE@@QEAAPEAVMETA_SCRIPT_MAP_ENTRY@@PEBGPEBDKPEAKPEAVMULTISZ@@@Z; META_SCRIPT_MAP_TABLE::CalculateScriptMapEntry(ushort const *,char const *,ulong,ulong *,MULTISZ *)
0x18000cab2  mov     [rsp+168h+var_118], rax
0x18000cab7  mov     r14, rax
0x18000caba  test    rax, rax
0x18000cabd  jz      loc_18000CBFF
0x18000cac3  mov     rcx, [rax]
0x18000cac6  xor     edx, edx
0x18000cac8  mov     rax, [rcx+20h]
0x18000cacc  mov     rcx, r14
0x18000cacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cad4  cmp     [rax], bx
0x18000cad7  jnz     loc_18000CDB8
0x18000cadd  test    rsi, rsi
0x18000cae0  jz      loc_18000CBFF
0x18000cae6  mov     rax, [r14]
0x18000cae9  xor     edx, edx
0x18000caeb  mov     rcx, r14
0x18000caee  mov     rax, [rax+10h]
0x18000caf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000caf7  xor     edx, edx; Val
0x18000caf9  lea     rcx, [rsp+168h+var_D8]; void *
0x18000cb01  mov     r8d, 80h; Size
0x18000cb07  mov     rdi, rax
0x18000cb0a  call    memset_0
0x18000cb0f  mov     r8d, 40h ; '@'
0x18000cb15  lea     rdx, [rsp+168h+var_D8]
0x18000cb1d  lea     rcx, [rsp+168h+var_110]
0x18000cb22  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000cb28  nop     dword ptr [rax+rax+00000000h]
0x18000cb30  xor     ebx, ebx
0x18000cb32  cmp     [rdi], bx
0x18000cb35  jz      loc_18000CBEF
0x18000cb3b  mov     edx, 2Ch ; ','; Ch
0x18000cb40  mov     rcx, rdi; Str
0x18000cb43  call    cs:__imp_wcschr
0x18000cb49  mov     rdx, rdi
0x18000cb4c  lea     rcx, [rsp+168h+var_110]
0x18000cb51  mov     r14, rax
0x18000cb54  test    rax, rax
0x18000cb57  jz      loc_18000CBE4
0x18000cb5d  mov     r8, rax
0x18000cb60  sub     r8, rdi
0x18000cb63  sar     r8, 1
0x18000cb66  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000cb6c  mov     ebx, eax
0x18000cb6e  test    eax, eax
0x18000cb70  js      short loc_18000CBEF
0x18000cb72  lea     rcx, [rsp+168h+var_110]
0x18000cb77  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000cb7d  mov     rbp, rax
0x18000cb80  xor     ebx, ebx
0x18000cb82  cmp     ebx, [rsi+0E8h]
0x18000cb88  jnb     short loc_18000CBD4
0x18000cb8a  lea     rcx, [rsi+0F0h]
0x18000cb91  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000cb97  mov     rdi, [rax+rbx*8]
0x18000cb9b  mov     rax, [rdi+8]
0x18000cb9f  test    rax, rax
0x18000cba2  jnz     short loc_18000CBB3
0x18000cba4  mov     rcx, [rdi+20h]
0x18000cba8  mov     rax, [rcx]
0x18000cbab  mov     rax, [rax]
0x18000cbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbb3  mov     rdx, rbp; String2
0x18000cbb6  mov     rcx, rax; String1
0x18000cbb9  call    cs:__imp__wcsicmp
0x18000cbbf  test    eax, eax
0x18000cbc1  jz      short loc_18000CBC7
0x18000cbc3  inc     ebx
0x18000cbc5  jmp     short loc_18000CB82
0x18000cbc7  mov     rax, [rdi+10h]
0x18000cbcb  test    rax, rax
0x18000cbce  jnz     loc_18000CCB3
0x18000cbd4  xor     ebx, ebx
0x18000cbd6  test    r14, r14
0x18000cbd9  jz      short loc_18000CBEF
0x18000cbdb  lea     rdi, [r14+2]
0x18000cbdf  jmp     loc_18000CB30
0x18000cbe4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000cbea  jmp     loc_18000CB6C
0x18000cbef  lea     rcx, [rsp+168h+var_110]
0x18000cbf4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000cbfa  mov     r14, [rsp+168h+var_118]
0x18000cbff  mov     edi, [rsp+168h+var_134]
0x18000cc03  test    r12d, r12d
0x18000cc06  jz      loc_18000CDC2
0x18000cc0c  lea     rcx, [r13+3C0h]; SRWLock
0x18000cc13  call    cs:__imp_AcquireSRWLockExclusive
0x18000cc19  cmp     byte ptr [r15+r13+3C8h], 0
0x18000cc22  jnz     loc_18000CCC8
0x18000cc28  test    rsi, rsi
0x18000cc2b  mov     [r13+r15*8+418h], r14
0x18000cc33  movzx   esi, [rsp+168h+var_138]
0x18000cc38  jz      short loc_18000CC59
0x18000cc3a  mov     [r13+r15*2+3F0h], di
0x18000cc43  mov     [r15+r13+3DCh], sil
0x18000cc4b  lock or [rsp+168h+var_168], 0
0x18000cc50  mov     byte ptr [r15+r13+3C8h], 1
0x18000cc59  lea     rcx, [r13+3C0h]; SRWLock
0x18000cc60  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc66  test    ebx, ebx
0x18000cc68  js      short loc_18000CCAC
0x18000cc6a  test    r12d, r12d
0x18000cc6d  jz      short loc_18000CC83
0x18000cc6f  mov     rdx, [rsp+168h+var_120]
0x18000cc74  mov     r8, [rsp+168h+var_128]
0x18000cc79  mov     r9, [rsp+168h+var_130]
0x18000cc7e  jmp     loc_18000CA0D
0x18000cc83  mov     rax, [rsp+168h+var_130]
0x18000cc88  test    rax, rax
0x18000cc8b  jz      short loc_18000CC90
0x18000cc8d  mov     [rax], r14
0x18000cc90  mov     rax, [rsp+168h+var_128]
0x18000cc95  test    rax, rax
0x18000cc98  jz      short loc_18000CC9C
0x18000cc9a  mov     [rax], edi
0x18000cc9c  mov     rcx, [rsp+168h+var_120]
0x18000cca1  test    rcx, rcx
0x18000cca4  jz      short loc_18000CCAC
0x18000cca6  movzx   eax, sil
0x18000ccaa  mov     [rcx], eax
0x18000ccac  mov     eax, ebx
0x18000ccae  jmp     loc_18000CA40
0x18000ccb3  xor     ebx, ebx
0x18000ccb5  cmp     [rax], bx
0x18000ccb8  jz      loc_18000CBD4
0x18000ccbe  mov     [rsp+168h+var_138], 1
0x18000ccc3  jmp     loc_18000CBEF
0x18000ccc8  movzx   esi, [rsp+168h+var_138]
0x18000cccd  jmp     short loc_18000CC59
0x18000cccf  lea     eax, [r15-3]; switch 17 cases
0x18000ccd3  cmp     eax, 10h
0x18000ccd6  ja      def_18000CCEF; jumptable 000000018000CCEF default case, case 4
0x18000ccdc  lea     rdx, __ImageBase
0x18000cce3  cdqe
0x18000cce5  mov     ecx, ds:(jpt_18000CCEF - 180000000h)[rdx+rax*4]
0x18000ccec  add     rcx, rdx
0x18000ccef  jmp     rcx; switch jump
0x18000ccf1  lea     rbp, aOptions; jumptable 000000018000CCEF case 3
0x18000ccf8  jmp     loc_18000CA75
0x18000ccfd  lea     rbp, aHead; jumptable 000000018000CCEF case 5
0x18000cd04  jmp     loc_18000CA75
0x18000cd09  lea     rbp, aPost; jumptable 000000018000CCEF case 6
0x18000cd10  jmp     loc_18000CA75
0x18000cd15  lea     rbp, aPut; jumptable 000000018000CCEF case 7
0x18000cd1c  jmp     loc_18000CA75
0x18000cd21  lea     rbp, aDelete; jumptable 000000018000CCEF case 8
0x18000cd28  jmp     loc_18000CA75
0x18000cd2d  lea     rbp, aTrace; jumptable 000000018000CCEF case 9
0x18000cd34  jmp     loc_18000CA75
0x18000cd39  lea     rbp, aConnect; jumptable 000000018000CCEF case 10
0x18000cd40  jmp     loc_18000CA75
0x18000cd45  lea     rbp, aTrack; jumptable 000000018000CCEF case 11
0x18000cd4c  jmp     loc_18000CA75
0x18000cd51  lea     rbp, aMove; jumptable 000000018000CCEF case 12
0x18000cd58  jmp     loc_18000CA75
0x18000cd5d  lea     rbp, aCopy; jumptable 000000018000CCEF case 13
0x18000cd64  jmp     loc_18000CA75
0x18000cd69  lea     rbp, aPropfind; jumptable 000000018000CCEF case 14
0x18000cd70  jmp     loc_18000CA75
0x18000cd75  lea     rbp, aProppatch; jumptable 000000018000CCEF case 15
0x18000cd7c  jmp     loc_18000CA75
0x18000cd81  lea     rbp, aMkcol; jumptable 000000018000CCEF case 16
0x18000cd88  jmp     loc_18000CA75
0x18000cd8d  lea     rbp, aLock; jumptable 000000018000CCEF case 17
0x18000cd94  jmp     loc_18000CA75
0x18000cd99  lea     rbp, aUnlock; jumptable 000000018000CCEF case 18
0x18000cda0  jmp     loc_18000CA75
0x18000cda5  lea     rbp, aSearch; jumptable 000000018000CCEF case 19
0x18000cdac  jmp     loc_18000CA75
0x18000cdb1  xor     ebp, ebp; jumptable 000000018000CCEF default case, case 4
0x18000cdb3  jmp     loc_18000CA75
0x18000cdb8  mov     [rsp+168h+var_138], 1
0x18000cdbd  jmp     loc_18000CBFF
0x18000cdc2  movzx   esi, [rsp+168h+var_138]
0x18000cdc7  jmp     loc_18000CC66
```
