# UpdateErrorDescription(IHttpContext *,FILTER_FAILURE_POINT,STRU *)

- ea: `0x1800082a0`
- end: `0x1800084a0`
- name: `?UpdateErrorDescription@@YAJPEAVIHttpContext@@W4FILTER_FAILURE_POINT@@PEAVSTRU@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180002fc0`

## callees

- `0x1800082a0`
- `0x18000a1d0`
- `0x18000c91e`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800082fe`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800082fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000847c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000847c`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180008397`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180008397`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800083c0`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800083c0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800083aa`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008443`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800083aa`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180008443`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083db`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083fb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008450`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083db`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800083fb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008450`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800083ee`
- `iisutil!?QuerySizeCCH@STRU@@QEBAKXZ` at `0x1800083ee`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000841c`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000841c`

## pseudocode

```c
__int64 __fastcall UpdateErrorDescription(__int64 a1, int a2, STRU *a3)
{
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  unsigned int v9; // ebx
  __int64 v10; // rax
  const char *v11; // rax
  int String; // ebx
  unsigned int CCH; // eax
  unsigned __int16 *Str; // rax
  unsigned __int16 *v15; // rsi
  unsigned __int16 *v16; // rdi
  unsigned int SizeCCH; // ebx
  unsigned __int16 *v18; // rax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, unsigned __int16 *, _QWORD, __int64); // rdi
  unsigned int v21; // ebx
  unsigned __int16 *v22; // rax
  _WORD v24[2]; // [rsp+30h] [rbp-178h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-174h] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-170h] BYREF
  _BYTE v27[64]; // [rsp+40h] [rbp-168h] BYREF
  unsigned __int16 v28[128]; // [rsp+80h] [rbp-128h] BYREF

  v24[0] = 0;
  v26 = 0;
  v25 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v27, v28, 0x80u);
  if ( a2 == 1 )
  {
    v9 = 12810;
  }
  else
  {
    v6 = a2 - 2;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 == 1 )
            v9 = 12814;
          else
            v9 = 12815;
        }
        else
        {
          v9 = 12813;
        }
      }
      else
      {
        v9 = 12812;
      }
    }
    else
    {
      v9 = 12811;
    }
  }
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v11 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _WORD *))(*(_QWORD *)v10 + 16LL))(v10, 23, v24);
  String = LANG_STRING::GetString((LANG_STRING *)g_pLangString, v11, v24[0], v9, (const unsigned __int16 **)&v26, &v25);
  if ( String >= 0 )
  {
    CCH = STRU::QueryCCH(a3);
    String = STRU::Resize((STRU *)v27, 2 * (v25 + CCH) + 2);
    if ( String >= 0 )
    {
      Str = STRU::QueryStr(a3);
      v15 = v26;
      v16 = Str;
      SizeCCH = STRU::QuerySizeCCH((STRU *)v27);
      v18 = STRU::QueryStr((STRU *)v27);
      String = StringCchPrintfW(v18, SizeCCH, v15, v16);
      if ( String >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v27);
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
        v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v19 + 192LL);
        v21 = STRU::QueryCCH((STRU *)v27);
        v22 = STRU::QueryStr((STRU *)v27);
        String = v20(v19, v22, v21, 1);
      }
    }
  }
  STRU::~STRU((STRU *)v27);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x1800082a0  push    rbx
0x1800082a2  push    rdi
0x1800082a3  push    r14
0x1800082a5  sub     rsp, 190h
0x1800082ac  mov     rax, cs:__security_cookie
0x1800082b3  xor     rax, rsp
0x1800082b6  mov     [rsp+1A8h+var_28], rax
0x1800082be  mov     r14, rcx
0x1800082c1  mov     rdi, r8
0x1800082c4  xor     ecx, ecx
0x1800082c6  mov     ebx, edx
0x1800082c8  mov     [rsp+1A8h+var_178], cx
0x1800082cd  xor     edx, edx; Val
0x1800082cf  mov     [rsp+1A8h+var_170], rcx
0x1800082d4  mov     r8d, 100h; Size
0x1800082da  mov     [rsp+1A8h+var_174], ecx
0x1800082de  lea     rcx, [rsp+1A8h+var_128]; void *
0x1800082e6  call    memset_0
0x1800082eb  mov     r8d, 80h
0x1800082f1  lea     rdx, [rsp+1A8h+var_128]
0x1800082f9  lea     rcx, [rsp+1A8h+var_168]
0x1800082fe  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180008304  cmp     ebx, 1
0x180008307  jz      short loc_180008340
0x180008309  sub     ebx, 2
0x18000830c  jz      short loc_180008339
0x18000830e  sub     ebx, 1
0x180008311  jz      short loc_180008332
0x180008313  sub     ebx, 1
0x180008316  jz      short loc_18000832B
0x180008318  cmp     ebx, 1
0x18000831b  jz      short loc_180008324
0x18000831d  mov     ebx, 320Fh
0x180008322  jmp     short loc_180008345
0x180008324  mov     ebx, 320Eh
0x180008329  jmp     short loc_180008345
0x18000832b  mov     ebx, 320Dh
0x180008330  jmp     short loc_180008345
0x180008332  mov     ebx, 320Ch
0x180008337  jmp     short loc_180008345
0x180008339  mov     ebx, 320Bh
0x18000833e  jmp     short loc_180008345
0x180008340  mov     ebx, 320Ah
0x180008345  mov     rax, [r14]
0x180008348  mov     rcx, r14
0x18000834b  mov     rax, [rax+18h]
0x18000834f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008354  mov     r10, rax
0x180008357  lea     r8, [rsp+1A8h+var_178]
0x18000835c  mov     edx, 17h
0x180008361  mov     rcx, [rax]
0x180008364  mov     rax, [rcx+10h]
0x180008368  mov     rcx, r10
0x18000836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008370  movzx   r8d, [rsp+1A8h+var_178]
0x180008376  lea     rcx, [rsp+1A8h+var_174]
0x18000837b  mov     [rsp+1A8h+var_180], rcx
0x180008380  mov     r9d, ebx
0x180008383  lea     rcx, [rsp+1A8h+var_170]
0x180008388  mov     rdx, rax
0x18000838b  mov     [rsp+1A8h+var_188], rcx
0x180008390  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLangString
0x180008397  call    cs:__imp_?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z; LANG_STRING::GetString(char const *,ulong,uint,ushort const * *,ulong *)
0x18000839d  mov     ebx, eax
0x18000839f  test    eax, eax
0x1800083a1  js      loc_180008477
0x1800083a7  mov     rcx, rdi
0x1800083aa  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800083b0  add     eax, [rsp+1A8h+var_174]
0x1800083b4  lea     rcx, [rsp+1A8h+var_168]
0x1800083b9  lea     edx, ds:2[rax*2]
0x1800083c0  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800083c6  mov     ebx, eax
0x1800083c8  test    eax, eax
0x1800083ca  js      loc_180008477
0x1800083d0  mov     rcx, rdi
0x1800083d3  mov     [rsp+1A8h+arg_8], rsi
0x1800083db  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800083e1  mov     rsi, [rsp+1A8h+var_170]
0x1800083e6  lea     rcx, [rsp+1A8h+var_168]
0x1800083eb  mov     rdi, rax
0x1800083ee  call    cs:__imp_?QuerySizeCCH@STRU@@QEBAKXZ; STRU::QuerySizeCCH(void)
0x1800083f4  lea     rcx, [rsp+1A8h+var_168]
0x1800083f9  mov     ebx, eax
0x1800083fb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008401  mov     r9, rdi
0x180008404  mov     r8, rsi; unsigned __int16 *
0x180008407  mov     rcx, rax; unsigned __int16 *
0x18000840a  mov     edx, ebx; unsigned __int64
0x18000840c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008411  mov     ebx, eax
0x180008413  test    eax, eax
0x180008415  js      short loc_18000846F
0x180008417  lea     rcx, [rsp+1A8h+var_168]
0x18000841c  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180008422  mov     rax, [r14]
0x180008425  mov     rcx, r14
0x180008428  mov     rax, [rax+20h]
0x18000842c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008431  mov     rsi, rax
0x180008434  mov     rcx, [rax]
0x180008437  mov     rdi, [rcx+0C0h]
0x18000843e  lea     rcx, [rsp+1A8h+var_168]
0x180008443  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180008449  lea     rcx, [rsp+1A8h+var_168]
0x18000844e  mov     ebx, eax
0x180008450  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008456  mov     r9d, 1
0x18000845c  mov     r8d, ebx
0x18000845f  mov     rdx, rax
0x180008462  mov     rcx, rsi
0x180008465  mov     rax, rdi
0x180008468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000846d  mov     ebx, eax
0x18000846f  mov     rsi, [rsp+1A8h+arg_8]
0x180008477  lea     rcx, [rsp+1A8h+var_168]
0x18000847c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008482  mov     eax, ebx
0x180008484  mov     rcx, [rsp+1A8h+var_28]
0x18000848c  xor     rcx, rsp; StackCookie
0x18000848f  call    __security_check_cookie
0x180008494  add     rsp, 190h
0x18000849b  pop     r14
0x18000849d  pop     rdi
0x18000849e  pop     rbx
0x18000849f  retn
```
