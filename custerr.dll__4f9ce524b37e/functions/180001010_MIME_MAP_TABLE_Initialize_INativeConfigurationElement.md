# MIME_MAP_TABLE::Initialize(INativeConfigurationElement *)

- ea: `0x180001010`
- end: `0x1800012b5`
- name: `?Initialize@MIME_MAP_TABLE@@QEAAJPEAVINativeConfigurationElement@@@Z`
- size: `677`
- prototype: `__int64 __fastcall(MIME_MAP_TABLE *__hidden this, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180007524`

## callees

- `0x180001010`
- `0x180001ff0`
- `0x180002030`
- `0x180007334`
- `0x1800074d0`
- `0x1800074f4`
- `0x180008010`

## import_xrefs

- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x18000118b`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x18000118b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800011a0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800011a0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000117a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000117a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001159`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180001159`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800011ad`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800011ad`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001163`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180001163`

## string_xrefs

- `0x1800010da`: `fileExtension`

## pseudocode

```c
__int64 __fastcall MIME_MAP_TABLE::Initialize(MIME_MAP_TABLE *this, struct INativeConfigurationElement *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v4)(struct INativeConfigurationElement *, __int64 **); // rax
  int v5; // ebx
  unsigned int i; // esi
  __int64 v7; // rax
  const unsigned __int16 *v8; // rbp
  const unsigned __int16 *v9; // rbx
  char *v10; // rax
  _DWORD *v11; // rdi
  unsigned int v12; // edx
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r9
  const unsigned __int16 *v16; // [rsp+30h] [rbp-48h] BYREF
  const unsigned __int16 *v17; // [rsp+38h] [rbp-40h] BYREF
  unsigned int v18; // [rsp+88h] [rbp+10h] BYREF
  __int64 v19; // [rsp+90h] [rbp+18h] BYREF
  __int64 *v20; // [rsp+98h] [rbp+20h] BYREF

  v2 = *(_QWORD *)a2;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v4 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 **))(v2 + 40);
  v16 = 0;
  v17 = 0;
  v5 = v4(a2, &v20);
  if ( v5 < 0 || (v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v20 + 24))(v20, &v18), v5 < 0) )
  {
LABEL_21:
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    return (unsigned int)v5;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      v7 = *v20;
      if ( i >= v18 )
        break;
      v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v7 + 32))(v20, i, &v19);
      if ( v5 < 0 )
        goto LABEL_21;
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v19 + 64LL))(
             v19,
             L"fileExtension",
             &v16,
             0,
             0);
      if ( v5 < 0 )
        goto LABEL_21;
      v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v19 + 64LL))(
             v19,
             L"mimeType",
             &v17,
             0,
             0);
      if ( v5 < 0 )
        goto LABEL_21;
      v8 = v17;
      v9 = v16 + 1;
      if ( *v16 != 46 )
        v9 = v16;
      v10 = (char *)operator new(0x90u);
      v11 = v10;
      if ( !v10 )
        goto LABEL_20;
      STRU::STRU((STRU *)(v10 + 24));
      STRA::STRA((STRA *)(v11 + 20));
      v11[34] = 1;
      if ( (int)STRU::Copy((STRU *)(v11 + 6), v9) < 0 || (int)STRA::CopyWTruncate((STRA *)(v11 + 20), v8) < 0 )
        v11[34] = 0;
      *(_QWORD *)v11 = STRU::QueryStr((STRU *)(v11 + 6));
      *((_WORD *)v11 + 8) = STRU::QueryCCH((STRU *)(v11 + 6));
      *((_QWORD *)v11 + 1) = 0;
      if ( !v11[34] )
      {
        MIME_MAP_ENTRY::~MIME_MAP_ENTRY((MIME_MAP_ENTRY *)v11);
        operator delete(v11);
LABEL_20:
        v5 = -2147024888;
        goto LABEL_21;
      }
      v13 = *(const unsigned __int16 **)v11;
      if ( *((_DWORD *)this + 264) )
        v14 = HashString(v13, v12) % 0x83;
      else
        v14 = HashStringNoCase(v13, v12) % 0x83;
      *((_QWORD *)v11 + 1) = *((_QWORD *)this + v14 + 1);
      *((_QWORD *)this + v14 + 1) = v11;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    (*(void (**)(void))(v7 + 16))();
    return 0;
  }
}

```

## disassembly

```asm
0x180001010  mov     r11, rsp
0x180001013  mov     [r11+8], rbx
0x180001017  push    rbp
0x180001018  push    rsi
0x180001019  push    rdi
0x18000101a  push    r12
0x18000101c  push    r13
0x18000101e  push    r14
0x180001020  push    r15
0x180001022  sub     rsp, 40h
0x180001026  mov     rax, [rdx]
0x180001029  xor     r13d, r13d
0x18000102c  mov     r8, rdx
0x18000102f  mov     [r11+20h], r13
0x180001033  mov     r12, rcx
0x180001036  mov     [r11+18h], r13
0x18000103a  lea     rdx, [r11+20h]
0x18000103e  mov     [r11+10h], r13d
0x180001042  mov     rax, [rax+28h]
0x180001046  mov     rcx, r8
0x180001049  mov     [r11-48h], r13
0x18000104d  mov     [r11-40h], r13
0x180001051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001056  mov     ebx, eax
0x180001058  test    eax, eax
0x18000105a  js      loc_180001254
0x180001060  mov     rcx, [rsp+78h+arg_18]
0x180001068  lea     rdx, [rsp+78h+arg_8]
0x180001070  mov     rax, [rcx]
0x180001073  mov     rax, [rax+18h]
0x180001077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000107c  mov     ebx, eax
0x18000107e  test    eax, eax
0x180001080  js      loc_180001254
0x180001086  mov     esi, r13d
0x180001089  nop     dword ptr [rax+00000000h]
0x180001090  mov     rcx, [rsp+78h+arg_18]
0x180001098  mov     rax, [rcx]
0x18000109b  cmp     esi, [rsp+78h+arg_8]
0x1800010a2  jnb     loc_1800012A8
0x1800010a8  mov     rax, [rax+20h]
0x1800010ac  lea     r8, [rsp+78h+arg_10]
0x1800010b4  mov     edx, esi
0x1800010b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010bb  mov     ebx, eax
0x1800010bd  test    eax, eax
0x1800010bf  js      loc_180001254
0x1800010c5  mov     rcx, [rsp+78h+arg_10]
0x1800010cd  lea     r8, [rsp+78h+var_48]
0x1800010d2  xor     r9d, r9d
0x1800010d5  mov     [rsp+78h+var_58], r13
0x1800010da  lea     rdx, aFileextension; "fileExtension"
0x1800010e1  mov     rax, [rcx]
0x1800010e4  mov     rax, [rax+40h]
0x1800010e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800010ed  mov     ebx, eax
0x1800010ef  test    eax, eax
0x1800010f1  js      loc_180001254
0x1800010f7  mov     rcx, [rsp+78h+arg_10]
0x1800010ff  lea     r8, [rsp+78h+var_40]
0x180001104  xor     r9d, r9d
0x180001107  mov     [rsp+78h+var_58], r13
0x18000110c  lea     rdx, aMimetype; "mimeType"
0x180001113  mov     rax, [rcx]
0x180001116  mov     rax, [rax+40h]
0x18000111a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000111f  mov     ebx, eax
0x180001121  test    eax, eax
0x180001123  js      loc_180001254
0x180001129  mov     rax, [rsp+78h+var_48]
0x18000112e  mov     ecx, 90h; Size
0x180001133  mov     rbp, [rsp+78h+var_40]
0x180001138  cmp     word ptr [rax], 2Eh ; '.'
0x18000113c  lea     rbx, [rax+2]
0x180001140  cmovnz  rbx, rax
0x180001144  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001149  mov     rdi, rax
0x18000114c  test    rax, rax
0x18000114f  jz      loc_18000124F
0x180001155  lea     rcx, [rax+18h]
0x180001159  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000115f  lea     rcx, [rdi+50h]
0x180001163  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180001169  mov     rdx, rbx
0x18000116c  mov     dword ptr [rdi+88h], 1
0x180001176  lea     rcx, [rdi+18h]
0x18000117a  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001180  test    eax, eax
0x180001182  js      short loc_180001195
0x180001184  mov     rdx, rbp
0x180001187  lea     rcx, [rdi+50h]
0x18000118b  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x180001191  test    eax, eax
0x180001193  jns     short loc_18000119C
0x180001195  mov     [rdi+88h], r13d
0x18000119c  lea     rcx, [rdi+18h]
0x1800011a0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800011a6  lea     rcx, [rdi+18h]
0x1800011aa  mov     [rdi], rax
0x1800011ad  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800011b3  mov     [rdi+10h], ax
0x1800011b7  mov     [rdi+8], r13
0x1800011bb  cmp     [rdi+88h], r13d
0x1800011c2  jz      short loc_18000123F
0x1800011c4  mov     rcx, [rdi]; unsigned __int16 *
0x1800011c7  cmp     [r12+420h], r13d
0x1800011cf  jz      short loc_1800011EF
0x1800011d1  call    ?HashString@@YAKPEBGK@Z; HashString(ushort const *,ulong)
0x1800011d6  mov     r9d, eax
0x1800011d9  mov     eax, 0FA232CF3h
0x1800011de  mul     r9d
0x1800011e1  shr     edx, 7
0x1800011e4  imul    ecx, edx, 83h
0x1800011ea  sub     r9d, ecx
0x1800011ed  jmp     short loc_18000120B
0x1800011ef  call    ?HashStringNoCase@@YAKPEBGK@Z; HashStringNoCase(ushort const *,ulong)
0x1800011f4  mov     r9d, eax
0x1800011f7  mov     eax, 0FA232CF3h
0x1800011fc  mul     r9d
0x1800011ff  shr     edx, 7
0x180001202  imul    eax, edx, 83h
0x180001208  sub     r9d, eax
0x18000120b  mov     rax, [r12+r9*8+8]
0x180001210  lea     rcx, [r12+r9*8]
0x180001214  mov     [rdi+8], rax
0x180001218  mov     [rcx+8], rdi
0x18000121c  mov     rcx, [rsp+78h+arg_10]
0x180001224  mov     rax, [rcx]
0x180001227  mov     rax, [rax+10h]
0x18000122b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001230  inc     esi
0x180001232  mov     [rsp+78h+arg_10], r13
0x18000123a  jmp     loc_180001090
0x18000123f  mov     rcx, rdi; this
0x180001242  call    ??1MIME_MAP_ENTRY@@QEAA@XZ; MIME_MAP_ENTRY::~MIME_MAP_ENTRY(void)
0x180001247  mov     rcx, rdi; Block
0x18000124a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000124f  mov     ebx, 80070008h
0x180001254  mov     rcx, [rsp+78h+arg_10]
0x18000125c  test    rcx, rcx
0x18000125f  jz      short loc_180001275
0x180001261  mov     rax, [rcx]
0x180001264  mov     rax, [rax+10h]
0x180001268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126d  mov     [rsp+78h+arg_10], r13
0x180001275  mov     rcx, [rsp+78h+arg_18]
0x18000127d  test    rcx, rcx
0x180001280  jz      short loc_18000128E
0x180001282  mov     rax, [rcx]
0x180001285  mov     rax, [rax+10h]
0x180001289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000128e  mov     eax, ebx
0x180001290  mov     rbx, [rsp+78h+arg_0]
0x180001298  add     rsp, 40h
0x18000129c  pop     r15
0x18000129e  pop     r14
0x1800012a0  pop     r13
0x1800012a2  pop     r12
0x1800012a4  pop     rdi
0x1800012a5  pop     rsi
0x1800012a6  pop     rbp
0x1800012a7  retn
0x1800012a8  mov     rax, [rax+10h]
0x1800012ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012b1  xor     eax, eax
0x1800012b3  jmp     short loc_180001290
```
