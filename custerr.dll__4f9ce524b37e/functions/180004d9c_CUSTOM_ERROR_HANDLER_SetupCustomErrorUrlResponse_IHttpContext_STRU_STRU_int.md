# CUSTOM_ERROR_HANDLER::SetupCustomErrorUrlResponse(IHttpContext *,STRU *,STRU *,int *)

- ea: `0x180004d9c`
- end: `0x180005186`
- name: `?SetupCustomErrorUrlResponse@CUSTOM_ERROR_HANDLER@@QEAAJPEAVIHttpContext@@PEAVSTRU@@1PEAH@Z`
- size: `1002`
- prototype: `__int64 __fastcall(CUSTOM_ERROR_HANDLER *__hidden this, struct IHttpContext *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800012c0`

## callees

- `0x180004d9c`
- `0x180007836`
- `0x180007870`
- `0x180008010`

## import_xrefs

- `msvcrt!_itow` at `0x180004ef6`
- `msvcrt!_itow` at `0x180004ef6`
- `msvcrt!wcschr` at `0x180004e4e`
- `msvcrt!wcschr` at `0x180004e4e`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180004e2e`
- `iisutil!?Copy@STRU@@QEAAJPEBV1@@Z` at `0x180004e2e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004e79`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000515d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004e79`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000515d`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e42`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004fc6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800050bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004e42`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180004fc6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800050bb`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004f92`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800050ae`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180004f92`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800050ae`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e68`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f05`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f21`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004fd4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005025`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000503f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005058`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004e68`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f05`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004f21`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004fd4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005025`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000503f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005058`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180004fb3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000517b`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180004fb3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000517b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004e0b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180004e0b`

## pseudocode

```c
__int64 __fastcall CUSTOM_ERROR_HANDLER::SetupCustomErrorUrlResponse(
        CUSTOM_ERROR_HANDLER *this,
        struct IHttpContext *a2,
        struct STRU *a3,
        struct STRU *a4,
        int *a5)
{
  __int64 v9; // rsi
  int v10; // ebx
  const wchar_t *Str; // rax
  const unsigned __int16 *v12; // rdx
  __int64 v14; // rax
  __int64 v15; // r14
  __int64 v16; // rax
  const unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, unsigned __int16 *, _QWORD, __int64); // rdi
  unsigned int CCH; // ebx
  unsigned __int16 *v22; // rax
  __int64 v23; // rax
  __int64 v24; // r9
  _WORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v26; // [rsp+64h] [rbp-9Ch] BYREF
  int v27; // [rsp+68h] [rbp-98h] BYREF
  const unsigned __int16 *v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[56]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t Buffer[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v31[64]; // [rsp+F0h] [rbp-10h] BYREF

  v9 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v29, v31, 0x40u);
  v25[0] = 0;
  v26 = 0;
  v28 = 0;
  v27 = 0;
  v10 = STRU::Copy((STRU *)v29, a3);
  if ( v10 < 0 )
    goto LABEL_5;
  Str = STRU::QueryStr(a3);
  v12 = wcschr(Str, 0x3Fu) ? L"&" : L"?";
  v10 = STRU::Append((STRU *)v29, v12);
  if ( v10 < 0 )
    goto LABEL_5;
  (*(void (__fastcall **)(__int64, _WORD *, __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v9 + 184LL))(
    v9,
    v25,
    &v26,
    0,
    0,
    0,
    0,
    0,
    0,
    0);
  _itow(v25[0], Buffer, 10);
  v10 = STRU::Append((STRU *)v29, Buffer);
  if ( v10 < 0 )
    goto LABEL_5;
  v10 = STRU::Append((STRU *)v29, L";");
  if ( v10 < 0 )
    goto LABEL_5;
  v14 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v16 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 24LL))(a2);
  if ( !(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 16LL))(v16, 28) && a4 && STRU::QueryCCH(a4) )
  {
    v10 = STRU::Append(
            (STRU *)v29,
            *(const unsigned __int16 **)(v15 + 72),
            (__int64)(*(_QWORD *)(v15 + 80) - *(_QWORD *)(v15 + 72)) >> 1);
    if ( v10 >= 0 )
    {
      v17 = STRU::QueryStr(a4);
      v10 = STRU::Append((STRU *)v29, v17);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(struct IHttpContext *, const char *, const unsigned __int16 **, int *))(*(_QWORD *)a2 + 128LL))(
                a2,
                "SERVER_PORT",
                &v28,
                &v27);
        if ( v10 >= 0 )
        {
          if ( !v28
            || (v10 = STRU::Append((STRU *)v29, L":"), v10 >= 0) && (v10 = STRU::Append((STRU *)v29, v28), v10 >= 0) )
          {
            v18 = STRU::Append((STRU *)v29, *(const unsigned __int16 **)(v15 + 88));
            goto LABEL_19;
          }
        }
      }
    }
LABEL_5:
    STRU::~STRU((STRU *)v29);
    return (unsigned int)v10;
  }
  v18 = STRU::Append((STRU *)v29, *(const unsigned __int16 **)(v15 + 72), *(unsigned __int16 *)(v15 + 64) >> 1);
LABEL_19:
  v10 = v18;
  if ( v18 < 0 )
    goto LABEL_5;
  v10 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64, char *))(*(_QWORD *)a2 + 248LL))(
          a2,
          31,
          (char *)this + 16);
  if ( v10 < 0 )
    goto LABEL_5;
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
  v20 = *(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, __int64))(*(_QWORD *)v19 + 88LL);
  CCH = STRU::QueryCCH((STRU *)v29);
  v22 = STRU::QueryStr((STRU *)v29);
  v10 = v20(v19, v22, CCH, 1);
  if ( v10 < 0 )
    goto LABEL_5;
  if ( *(_DWORD *)(v15 + 36) != 5 )
  {
    v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
    *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23) + 36) = 4;
  }
  v24 = 8;
  if ( CUSTOM_ERROR_HANDLER::sm_fIgnoreAppPoolForCustomErrors )
    v24 = 12;
  v10 = (*(__int64 (__fastcall **)(struct IHttpContext *, __int64, _QWORD, __int64, _QWORD, int *))(*(_QWORD *)a2 + 104LL))(
          a2,
          1,
          *((_QWORD *)this + 2),
          v24,
          0,
          a5);
  if ( v10 < 0 )
    goto LABEL_5;
  STRU::~STRU((STRU *)v29);
  return 0;
}

```

## disassembly

```asm
0x180004d9c  push    rbp
0x180004d9e  push    rbx
0x180004d9f  push    rsi
0x180004da0  push    rdi
0x180004da1  push    r12
0x180004da3  push    r13
0x180004da5  push    r14
0x180004da7  push    r15
0x180004da9  lea     rbp, [rsp-88h]
0x180004db1  sub     rsp, 188h
0x180004db8  mov     rax, cs:__security_cookie
0x180004dbf  xor     rax, rsp
0x180004dc2  mov     [rbp+0C0h+var_50], rax
0x180004dc6  mov     rax, [rdx]
0x180004dc9  mov     r12, rcx
0x180004dcc  mov     r13, [rbp+0C0h+arg_20]
0x180004dd3  mov     rcx, rdx
0x180004dd6  mov     rdi, r9
0x180004dd9  mov     r14, r8
0x180004ddc  mov     r15, rdx
0x180004ddf  mov     rax, [rax+20h]
0x180004de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de8  xor     edx, edx; Val
0x180004dea  lea     rcx, [rbp+0C0h+var_D0]; void *
0x180004dee  mov     r8d, 80h; Size
0x180004df4  mov     rsi, rax
0x180004df7  call    memset_0
0x180004dfc  mov     r8d, 40h ; '@'
0x180004e02  lea     rdx, [rbp+0C0h+var_D0]
0x180004e06  lea     rcx, [rsp+1C0h+var_148]
0x180004e0b  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180004e11  xor     ecx, ecx
0x180004e13  mov     rdx, r14
0x180004e16  mov     [rsp+1C0h+var_160], cx
0x180004e1b  mov     [rsp+1C0h+var_15C], cx
0x180004e20  mov     [rsp+1C0h+var_150], rcx
0x180004e25  mov     [rsp+1C0h+var_158], ecx
0x180004e29  lea     rcx, [rsp+1C0h+var_148]
0x180004e2e  call    cs:__imp_?Copy@STRU@@QEAAJPEBV1@@Z; STRU::Copy(STRU const *)
0x180004e34  mov     ebx, eax
0x180004e36  test    eax, eax
0x180004e38  js      short loc_180004E74
0x180004e3a  mov     rcx, r14
0x180004e3d  mov     ebx, 3Fh ; '?'
0x180004e42  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004e48  mov     rcx, rax; Str
0x180004e4b  movzx   edx, bx; Ch
0x180004e4e  call    cs:__imp_wcschr
0x180004e54  xor     r14d, r14d
0x180004e57  lea     rcx, [rsp+1C0h+var_148]
0x180004e5c  test    rax, rax
0x180004e5f  jnz     short loc_180004EA1
0x180004e61  lea     rdx, asc_180009B30; "?"
0x180004e68  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004e6e  mov     ebx, eax
0x180004e70  test    eax, eax
0x180004e72  jns     short loc_180004EAA
0x180004e74  lea     rcx, [rsp+1C0h+var_148]
0x180004e79  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004e7f  mov     eax, ebx
0x180004e81  mov     rcx, [rbp+0C0h+var_50]
0x180004e85  xor     rcx, rsp; StackCookie
0x180004e88  call    __security_check_cookie
0x180004e8d  add     rsp, 188h
0x180004e94  pop     r15
0x180004e96  pop     r14
0x180004e98  pop     r13
0x180004e9a  pop     r12
0x180004e9c  pop     rdi
0x180004e9d  pop     rsi
0x180004e9e  pop     rbx
0x180004e9f  pop     rbp
0x180004ea0  retn
0x180004ea1  lea     rdx, asc_180009B9C; "&"
0x180004ea8  jmp     short loc_180004E68
0x180004eaa  mov     rax, [rsi]
0x180004ead  lea     r8, [rsp+1C0h+var_15C]
0x180004eb2  mov     [rsp+1C0h+var_178], r14
0x180004eb7  lea     rdx, [rsp+1C0h+var_160]
0x180004ebc  mov     [rsp+1C0h+var_180], r14
0x180004ec1  xor     r9d, r9d
0x180004ec4  mov     [rsp+1C0h+var_188], r14
0x180004ec9  mov     rcx, rsi
0x180004ecc  mov     rax, [rax+0B8h]
0x180004ed3  mov     [rsp+1C0h+var_190], r14
0x180004ed8  mov     [rsp+1C0h+var_198], r14
0x180004edd  mov     [rsp+1C0h+var_1A0], r14
0x180004ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ee7  movzx   ecx, [rsp+1C0h+var_160]; Value
0x180004eec  lea     rdx, [rbp+0C0h+Buffer]; Buffer
0x180004ef0  mov     r8d, 0Ah; Radix
0x180004ef6  call    cs:__imp__itow
0x180004efc  lea     rdx, [rbp+0C0h+Buffer]
0x180004f00  lea     rcx, [rsp+1C0h+var_148]
0x180004f05  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004f0b  lea     rcx, [rsp+1C0h+var_148]
0x180004f10  mov     ebx, eax
0x180004f12  test    eax, eax
0x180004f14  js      loc_180004E79
0x180004f1a  lea     rdx, asc_180009BA0; ";"
0x180004f21  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004f27  mov     ebx, eax
0x180004f29  test    eax, eax
0x180004f2b  js      loc_180004E74
0x180004f31  mov     rax, [r15]
0x180004f34  mov     rcx, r15
0x180004f37  mov     rax, [rax+18h]
0x180004f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f40  mov     rdx, rax
0x180004f43  mov     rcx, [rax]
0x180004f46  mov     rax, [rcx+8]
0x180004f4a  mov     rcx, rdx
0x180004f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f52  mov     rcx, [r15]
0x180004f55  mov     r14, rax
0x180004f58  mov     rax, [rcx+18h]
0x180004f5c  mov     rcx, r15
0x180004f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f64  mov     r9, rax
0x180004f67  xor     r8d, r8d
0x180004f6a  mov     rcx, [rax]
0x180004f6d  lea     edx, [r8+1Ch]
0x180004f71  mov     rax, [rcx+10h]
0x180004f75  mov     rcx, r9
0x180004f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7d  test    rax, rax
0x180004f80  jnz     loc_18000516A
0x180004f86  test    rdi, rdi
0x180004f89  jz      loc_18000516A
0x180004f8f  mov     rcx, rdi
0x180004f92  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180004f98  test    eax, eax
0x180004f9a  jz      loc_18000516A
0x180004fa0  mov     rdx, [r14+48h]
0x180004fa4  lea     rcx, [rsp+1C0h+var_148]
0x180004fa9  mov     r8, [r14+50h]
0x180004fad  sub     r8, rdx
0x180004fb0  sar     r8, 1
0x180004fb3  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180004fb9  mov     ebx, eax
0x180004fbb  test    eax, eax
0x180004fbd  js      loc_180004E74
0x180004fc3  mov     rcx, rdi
0x180004fc6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180004fcc  mov     rdx, rax
0x180004fcf  lea     rcx, [rsp+1C0h+var_148]
0x180004fd4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180004fda  mov     ebx, eax
0x180004fdc  test    eax, eax
0x180004fde  js      loc_180004E74
0x180004fe4  mov     rax, [r15]
0x180004fe7  lea     r9, [rsp+1C0h+var_158]
0x180004fec  lea     r8, [rsp+1C0h+var_150]
0x180004ff1  mov     rcx, r15
0x180004ff4  lea     rdx, aServerPort; "SERVER_PORT"
0x180004ffb  mov     rax, [rax+80h]
0x180005002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005007  mov     ebx, eax
0x180005009  test    eax, eax
0x18000500b  js      loc_180004E74
0x180005011  cmp     [rsp+1C0h+var_150], 0
0x180005017  jz      short loc_18000504F
0x180005019  lea     rdx, asc_180009BB4; ":"
0x180005020  lea     rcx, [rsp+1C0h+var_148]
0x180005025  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000502b  lea     rcx, [rsp+1C0h+var_148]
0x180005030  mov     ebx, eax
0x180005032  test    eax, eax
0x180005034  js      loc_180004E79
0x18000503a  mov     rdx, [rsp+1C0h+var_150]
0x18000503f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005045  mov     ebx, eax
0x180005047  test    eax, eax
0x180005049  js      loc_180004E74
0x18000504f  mov     rdx, [r14+58h]
0x180005053  lea     rcx, [rsp+1C0h+var_148]
0x180005058  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000505e  mov     ebx, eax
0x180005060  test    eax, eax
0x180005062  js      loc_180004E74
0x180005068  mov     rax, [r15]
0x18000506b  lea     r8, [r12+10h]
0x180005070  mov     edx, 1Fh
0x180005075  mov     rcx, r15
0x180005078  mov     rax, [rax+0F8h]
0x18000507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005084  mov     ebx, eax
0x180005086  test    eax, eax
0x180005088  js      loc_180004E74
0x18000508e  mov     rcx, [r12+10h]
0x180005093  mov     rax, [rcx]
0x180005096  mov     rax, [rax+18h]
0x18000509a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000509f  mov     rsi, rax
0x1800050a2  mov     rcx, [rax]
0x1800050a5  mov     rdi, [rcx+58h]
0x1800050a9  lea     rcx, [rsp+1C0h+var_148]
0x1800050ae  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800050b4  lea     rcx, [rsp+1C0h+var_148]
0x1800050b9  mov     ebx, eax
0x1800050bb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800050c1  mov     r9d, 1
0x1800050c7  mov     r8d, ebx
0x1800050ca  mov     rdx, rax
0x1800050cd  mov     rcx, rsi
0x1800050d0  mov     rax, rdi
0x1800050d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d8  mov     ebx, eax
0x1800050da  test    eax, eax
0x1800050dc  js      loc_180004E74
0x1800050e2  cmp     dword ptr [r14+24h], 5
0x1800050e7  jz      short loc_180005113
0x1800050e9  mov     rcx, [r12+10h]
0x1800050ee  mov     rax, [rcx]
0x1800050f1  mov     rax, [rax+18h]
0x1800050f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fa  mov     rdx, rax
0x1800050fd  mov     rcx, [rax]
0x180005100  mov     rax, [rcx+8]
0x180005104  mov     rcx, rdx
0x180005107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510c  mov     dword ptr [rax+24h], 4
0x180005113  cmp     cs:?sm_fIgnoreAppPoolForCustomErrors@CUSTOM_ERROR_HANDLER@@0HA, 0; int CUSTOM_ERROR_HANDLER::sm_fIgnoreAppPoolForCustomErrors
0x18000511a  mov     eax, 0Ch
0x18000511f  mov     r8, [r12+10h]
0x180005124  mov     edx, 1
0x180005129  mov     [rsp+1C0h+var_198], r13
0x18000512e  mov     rcx, r15
0x180005131  mov     [rsp+1C0h+var_1A0], 0
0x18000513a  lea     r9d, [rax-4]
0x18000513e  cmovnz  r9d, eax
0x180005142  mov     rax, [r15]
0x180005145  mov     rax, [rax+68h]
0x180005149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514e  mov     ebx, eax
0x180005150  test    eax, eax
0x180005152  js      loc_180004E74
0x180005158  lea     rcx, [rsp+1C0h+var_148]
0x18000515d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005163  xor     eax, eax
0x180005165  jmp     loc_180004E81
0x18000516a  movzx   r8d, word ptr [r14+40h]
0x18000516f  lea     rcx, [rsp+1C0h+var_148]
0x180005174  mov     rdx, [r14+48h]
0x180005178  shr     r8d, 1
0x18000517b  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180005181  jmp     loc_18000505E
```
