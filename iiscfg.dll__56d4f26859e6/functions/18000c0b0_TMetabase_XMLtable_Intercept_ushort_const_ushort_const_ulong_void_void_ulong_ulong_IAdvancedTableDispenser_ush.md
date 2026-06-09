# TMetabase_XMLtable::Intercept(ushort const *,ushort const *,ulong,void *,void *,ulong,ulong,IAdvancedTableDispenser *,ushort const *,void *,void * *)

- ea: `0x18000c0b0`
- end: `0x18000c490`
- name: `?Intercept@TMetabase_XMLtable@@UEAAJPEBG0KPEAX1KKPEAUIAdvancedTableDispenser@@01PEAPEAX@Z`
- size: `992`
- prototype: `int(TMetabase_XMLtable *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, void *, void *, unsigned int, unsigned int, struct IAdvancedTableDispenser *, const unsigned __int16 *, void *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000c0b0`
- `0x18000c4d0`
- `0x18002a134`
- `0x18002e110`
- `0x180030010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000c303`
- `msvcrt!wcscpy_s` at `0x18000c303`
- `msvcrt!_wcsicmp` at `0x18000c191`
- `msvcrt!_wcsicmp` at `0x18000c1bd`
- `msvcrt!_wcsicmp` at `0x18000c191`
- `msvcrt!_wcsicmp` at `0x18000c1bd`
- `KERNEL32!GetFileAttributesExW` at `0x18000c39c`
- `KERNEL32!GetFileAttributesExW` at `0x18000c39c`
- `ole32!CoTaskMemAlloc` at `0x18000c298`
- `ole32!CoTaskMemAlloc` at `0x18000c2dd`
- `ole32!CoTaskMemAlloc` at `0x18000c298`
- `ole32!CoTaskMemAlloc` at `0x18000c2dd`
- `ATL!__imp_AtlComPtrAssign` at `0x18000c1ec`
- `ATL!__imp_AtlComPtrAssign` at `0x18000c1ec`
- `ATL!__imp_AtlComQIPtrAssign` at `0x18000c444`
- `ATL!__imp_AtlComQIPtrAssign` at `0x18000c444`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c10a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c10a`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
int __fastcall TMetabase_XMLtable::Intercept(
        TMetabase_XMLtable *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        _DWORD *a5,
        int *a6,
        unsigned int a7,
        unsigned int a8,
        struct IAdvancedTableDispenser *a9,
        const unsigned __int16 *a10,
        void *a11,
        void **a12)
{
  int result; // eax
  int v17; // r14d
  int v18; // eax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rax
  rsize_t v21; // r15
  wchar_t *v22; // rax
  __int64 v23; // rax
  char *v24; // rdi
  int v25; // [rsp+50h] [rbp-98h] BYREF
  int v26; // [rsp+54h] [rbp-94h] BYREF
  struct IAdvancedTableDispenser *v27; // [rsp+58h] [rbp-90h]
  int *v28; // [rsp+60h] [rbp-88h] BYREF
  int v29; // [rsp+68h] [rbp-80h]
  int v30; // [rsp+6Ch] [rbp-7Ch]
  int v31; // [rsp+70h] [rbp-78h]
  int v32; // [rsp+74h] [rbp-74h]
  __int128 FileInformation; // [rsp+80h] [rbp-68h] BYREF
  __int128 v34; // [rsp+90h] [rbp-58h]
  int v35; // [rsp+A0h] [rbp-48h]

  v27 = a9;
  SetErrorInfo(0, 0);
  if ( *((_DWORD *)this + 416) )
    return -2147418113;
  if ( a11 )
    return -2147024809;
  if ( !v27 )
    return -2147024809;
  if ( !a12 )
    return -2147024809;
  *a12 = 0;
  if ( a7 != 3 )
    return -2147024809;
  if ( (a8 & 0x112) != 0 )
    return -2145318899;
  if ( _wcsicmp(a2, L"METABASE") )
    return -2145318902;
  if ( a4 != 1243892992 && (!a3 || _wcsicmp(a3, L"MBProperty")) )
    return -2145318902;
  *((_DWORD *)this + 411) = a8;
  AtlComPtrAssign((char *)this + 1696, v27);
  if ( a6 && a5 )
    v17 = *a6;
  else
    v17 = 0;
  while ( v17 )
  {
    v18 = a5[6 * --v17 + 3];
    if ( (v18 & 0xF0000000) != 0 )
    {
      v19 = *(const unsigned __int16 **)&a5[6 * v17];
      if ( v19 && a5[6 * v17 + 2] == 2 )
      {
        if ( v18 == -268435455 )
        {
          if ( a5[6 * v17 + 4] == 130 )
          {
            result = TXmlSDTBase::GetURLFromString((TMetabase_XMLtable *)((char *)this + 24), v19);
            if ( result < 0 )
              return result;
          }
        }
        else if ( v18 == -268435447 && a5[6 * v17 + 4] == 130 )
        {
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          v21 = v20 + 1;
          v22 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v20 + 1, 2u));
          *((_QWORD *)this + 220) = v22;
          if ( !v22 )
            return -2147024882;
          goto LABEL_42;
        }
      }
    }
    else
    {
      if ( v18 != 4 )
        return -2145318901;
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(*(_QWORD *)&a5[6 * v17] + 2 * v23) );
      v21 = v23 + 1;
      v22 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v23 + 1, 2u));
      *((_QWORD *)this + 219) = v22;
      if ( !v22 )
        return -2147024882;
LABEL_42:
      wcscpy_s(v22, v21, *(const wchar_t **)&a5[6 * v17]);
    }
  }
  if ( !*((_WORD *)this + 12) )
    return -2145319646;
  v24 = (char *)this - 16;
  result = TMetabase_XMLtable::InternalComplicatedInitialize((TMetabase_XMLtable *)((char *)this - 16));
  if ( result >= 0 )
  {
    v28 = 0;
    v25 = 1024;
    v26 = 1;
    FileInformation = 0;
    v34 = 0;
    v35 = 0;
    v30 = -268435449;
    v29 = 2;
    v31 = 19;
    v32 = 4;
    if ( GetFileAttributesExW((LPCWSTR)this + 12, GetFileExInfoStandard, &FileInformation) )
    {
      if ( HIDWORD(v34) )
        return -2147467263;
      v25 = 2 * v35;
    }
    v28 = &v25;
    result = (*(__int64 (__fastcall **)(struct IAdvancedTableDispenser *, const wchar_t *, const wchar_t *, __int64, int **, int *, int, unsigned int, char *))(*(_QWORD *)v27 + 32LL))(
               v27,
               L"METABASE",
               L"MBProperty",
               1243892992,
               &v28,
               &v26,
               3,
               a8,
               (char *)this + 1768);
    if ( result >= 0 )
    {
      AtlComQIPtrAssign((char *)this + 1776, *((_QWORD *)this + 221), &IID_ISimpleTableController);
      *a12 = v24;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v24 + 8LL))((char *)this - 16);
      _InterlockedIncrement((volatile signed __int32 *)this + 416);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c0b0  push    rbx
0x18000c0b2  push    rsi
0x18000c0b3  push    rdi
0x18000c0b4  push    r12
0x18000c0b6  push    r13
0x18000c0b8  push    r14
0x18000c0ba  push    r15
0x18000c0bc  sub     rsp, 0B0h
0x18000c0c3  mov     rax, cs:__security_cookie
0x18000c0ca  xor     rax, rsp
0x18000c0cd  mov     [rsp+0E8h+var_40], rax
0x18000c0d5  mov     r15d, r9d
0x18000c0d8  mov     rdi, r8
0x18000c0db  mov     r12, rdx
0x18000c0de  mov     rbx, rcx
0x18000c0e1  mov     rsi, [rsp+0E8h+arg_20]
0x18000c0e9  mov     r14, [rsp+0E8h+arg_28]
0x18000c0f1  mov     rax, [rsp+0E8h+arg_40]
0x18000c0f9  mov     [rsp+0E8h+var_90], rax
0x18000c0fe  mov     r13, [rsp+0E8h+arg_58]
0x18000c106  xor     edx, edx; perrinfo
0x18000c108  xor     ecx, ecx; dwReserved
0x18000c10a  call    cs:__imp_SetErrorInfo
0x18000c110  xor     eax, eax
0x18000c112  cmp     [rbx+680h], eax
0x18000c118  jz      short loc_18000C124
0x18000c11a  mov     eax, 8000FFFFh
0x18000c11f  jmp     loc_18000C46C
0x18000c124  cmp     [rsp+0E8h+arg_50], rax
0x18000c12c  jz      short loc_18000C138
0x18000c12e  mov     eax, 80070057h
0x18000c133  jmp     loc_18000C46C
0x18000c138  cmp     [rsp+0E8h+var_90], rax
0x18000c13d  jnz     short loc_18000C149
0x18000c13f  mov     eax, 80070057h
0x18000c144  jmp     loc_18000C46C
0x18000c149  test    r13, r13
0x18000c14c  jnz     short loc_18000C158
0x18000c14e  mov     eax, 80070057h
0x18000c153  jmp     loc_18000C46C
0x18000c158  mov     [r13+0], rax
0x18000c15c  cmp     [rsp+0E8h+arg_30], 3
0x18000c164  jz      short loc_18000C170
0x18000c166  mov     eax, 80070057h
0x18000c16b  jmp     loc_18000C46C
0x18000c170  test    [rsp+0E8h+arg_38], 112h
0x18000c17b  jz      short loc_18000C187
0x18000c17d  mov     eax, 8021080Dh
0x18000c182  jmp     loc_18000C46C
0x18000c187  lea     rdx, aMetabase; "METABASE"
0x18000c18e  mov     rcx, r12; String1
0x18000c191  call    cs:__imp__wcsicmp
0x18000c197  test    eax, eax
0x18000c199  jz      short loc_18000C1A5
0x18000c19b  mov     eax, 8021080Ah
0x18000c1a0  jmp     loc_18000C46C
0x18000c1a5  cmp     r15d, 4A244D00h
0x18000c1ac  jz      short loc_18000C1D1
0x18000c1ae  test    rdi, rdi
0x18000c1b1  jz      short loc_18000C1C7
0x18000c1b3  lea     rdx, aMbproperty; "MBProperty"
0x18000c1ba  mov     rcx, rdi; String1
0x18000c1bd  call    cs:__imp__wcsicmp
0x18000c1c3  test    eax, eax
0x18000c1c5  jz      short loc_18000C1D1
0x18000c1c7  mov     eax, 8021080Ah
0x18000c1cc  jmp     loc_18000C46C
0x18000c1d1  mov     r12d, [rsp+0E8h+arg_38]
0x18000c1d9  mov     [rbx+66Ch], r12d
0x18000c1e0  lea     rcx, [rbx+6A0h]
0x18000c1e7  mov     rdx, [rsp+0E8h+var_90]
0x18000c1ec  call    cs:__imp_AtlComPtrAssign
0x18000c1f2  xor     r12d, r12d
0x18000c1f5  test    r14, r14
0x18000c1f8  jz      short loc_18000C204
0x18000c1fa  test    rsi, rsi
0x18000c1fd  jz      short loc_18000C204
0x18000c1ff  mov     r14d, [r14]
0x18000c202  jmp     short loc_18000C207
0x18000c204  mov     r14d, r12d
0x18000c207  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000c20b  test    r14d, r14d
0x18000c20e  jz      loc_18000C318
0x18000c214  dec     r14d
0x18000c217  movsxd  rax, r14d
0x18000c21a  lea     rdi, [rax+rax*2]
0x18000c21e  mov     eax, [rsi+rdi*8+0Ch]
0x18000c222  test    eax, 0F0000000h
0x18000c227  jz      loc_18000C2B4
0x18000c22d  mov     rdx, [rsi+rdi*8]; unsigned __int16 *
0x18000c231  test    rdx, rdx
0x18000c234  jz      short loc_18000C20B
0x18000c236  cmp     dword ptr [rsi+rdi*8+8], 2
0x18000c23b  jnz     short loc_18000C20B
0x18000c23d  cmp     eax, 0F0000001h
0x18000c242  jnz     short loc_18000C267
0x18000c244  cmp     dword ptr [rsi+rdi*8+10h], 82h
0x18000c24c  jnz     short loc_18000C20B
0x18000c24e  lea     rcx, [rbx+18h]; this
0x18000c252  call    ?GetURLFromString@TXmlSDTBase@@IEAAJPEBG@Z; TXmlSDTBase::GetURLFromString(ushort const *)
0x18000c257  test    eax, eax
0x18000c259  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18000c260  jns     short loc_18000C20B
0x18000c262  jmp     loc_18000C46C
0x18000c267  cmp     eax, 0F0000009h
0x18000c26c  jnz     short loc_18000C20B
0x18000c26e  cmp     dword ptr [rsi+rdi*8+10h], 82h
0x18000c276  jnz     short loc_18000C20B
0x18000c278  mov     rax, r8
0x18000c27b  inc     rax
0x18000c27e  cmp     [rdx+rax*2], r12w
0x18000c283  jnz     short loc_18000C27B
0x18000c285  lea     r15, [rax+1]
0x18000c289  mov     eax, 2
0x18000c28e  mul     r15
0x18000c291  cmovb   rax, r8
0x18000c295  mov     rcx, rax; cb
0x18000c298  call    cs:__imp_CoTaskMemAlloc
0x18000c29e  mov     [rbx+6E0h], rax
0x18000c2a5  test    rax, rax
0x18000c2a8  jnz     short loc_18000C2F9
0x18000c2aa  mov     eax, 8007000Eh
0x18000c2af  jmp     loc_18000C46C
0x18000c2b4  cmp     eax, 4
0x18000c2b7  jnz     short loc_18000C30E
0x18000c2b9  mov     rcx, [rsi+rdi*8]
0x18000c2bd  mov     rax, r8
0x18000c2c0  inc     rax
0x18000c2c3  cmp     [rcx+rax*2], r12w
0x18000c2c8  jnz     short loc_18000C2C0
0x18000c2ca  lea     r15, [rax+1]
0x18000c2ce  mov     eax, 2
0x18000c2d3  mul     r15
0x18000c2d6  cmovb   rax, r8
0x18000c2da  mov     rcx, rax; cb
0x18000c2dd  call    cs:__imp_CoTaskMemAlloc
0x18000c2e3  mov     [rbx+6D8h], rax
0x18000c2ea  test    rax, rax
0x18000c2ed  jnz     short loc_18000C2F9
0x18000c2ef  mov     eax, 8007000Eh
0x18000c2f4  jmp     loc_18000C46C
0x18000c2f9  mov     r8, [rsi+rdi*8]; Source
0x18000c2fd  mov     rdx, r15; SizeInWords
0x18000c300  mov     rcx, rax; Destination
0x18000c303  call    cs:__imp_wcscpy_s
0x18000c309  jmp     loc_18000C207
0x18000c30e  mov     eax, 8021080Bh
0x18000c313  jmp     loc_18000C46C
0x18000c318  cmp     r12w, [rbx+18h]
0x18000c31d  jnz     short loc_18000C329
0x18000c31f  mov     eax, 80210522h
0x18000c324  jmp     loc_18000C46C
0x18000c329  lea     rdi, [rbx-10h]
0x18000c32d  mov     rcx, rdi; this
0x18000c330  call    ?InternalComplicatedInitialize@TMetabase_XMLtable@@AEAAJXZ; TMetabase_XMLtable::InternalComplicatedInitialize(void)
0x18000c335  test    eax, eax
0x18000c337  js      loc_18000C46C
0x18000c33d  mov     [rsp+0E8h+var_88], r12
0x18000c342  mov     [rsp+0E8h+var_98], 400h
0x18000c34a  mov     [rsp+0E8h+var_94], 1
0x18000c352  xorps   xmm0, xmm0
0x18000c355  xor     eax, eax
0x18000c357  movups  [rsp+0E8h+FileInformation], xmm0
0x18000c35f  movups  [rsp+0E8h+var_58], xmm0
0x18000c367  mov     [rsp+0E8h+var_48], eax
0x18000c36e  mov     [rsp+0E8h+var_7C], 0F0000007h
0x18000c376  mov     [rsp+0E8h+var_80], 2
0x18000c37e  mov     [rsp+0E8h+var_78], 13h
0x18000c386  mov     [rsp+0E8h+var_74], 4
0x18000c38e  lea     r8, [rsp+0E8h+FileInformation]; lpFileInformation
0x18000c396  xor     edx, edx; fInfoLevelId
0x18000c398  lea     rcx, [rbx+18h]; lpFileName
0x18000c39c  call    cs:__imp_GetFileAttributesExW
0x18000c3a2  test    eax, eax
0x18000c3a4  jz      short loc_18000C3C7
0x18000c3a6  cmp     dword ptr [rsp+0E8h+var_58+0Ch], r12d
0x18000c3ae  jz      short loc_18000C3BA
0x18000c3b0  mov     eax, 80004001h
0x18000c3b5  jmp     loc_18000C46C
0x18000c3ba  mov     eax, [rsp+0E8h+var_48]
0x18000c3c1  add     eax, eax
0x18000c3c3  mov     [rsp+0E8h+var_98], eax
0x18000c3c7  lea     rax, [rsp+0E8h+var_98]
0x18000c3cc  mov     [rsp+0E8h+var_88], rax
0x18000c3d1  lea     rsi, [rbx+6E8h]
0x18000c3d8  mov     r15, [rsp+0E8h+var_90]
0x18000c3dd  mov     rax, [r15]
0x18000c3e0  mov     [rsp+0E8h+var_A8], rsi
0x18000c3e5  mov     ecx, [rsp+0E8h+arg_38]
0x18000c3ec  mov     [rsp+0E8h+var_B0], ecx
0x18000c3f0  mov     ecx, [rsp+0E8h+arg_30]
0x18000c3f7  mov     [rsp+0E8h+var_B8], ecx
0x18000c3fb  lea     rcx, [rsp+0E8h+var_94]
0x18000c400  mov     [rsp+0E8h+var_C0], rcx
0x18000c405  lea     rcx, [rsp+0E8h+var_88]
0x18000c40a  mov     [rsp+0E8h+var_C8], rcx
0x18000c40f  mov     r9d, 4A244D00h
0x18000c415  lea     r8, aMbproperty; "MBProperty"
0x18000c41c  lea     rdx, aMetabase; "METABASE"
0x18000c423  mov     rcx, r15
0x18000c426  mov     rax, [rax+20h]
0x18000c42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c42f  test    eax, eax
0x18000c431  js      short loc_18000C46C
0x18000c433  lea     rcx, [rbx+6F0h]
0x18000c43a  lea     r8, IID_ISimpleTableController
0x18000c441  mov     rdx, [rsi]
0x18000c444  call    cs:__imp_AtlComQIPtrAssign
0x18000c44a  mov     [r13+0], rdi
0x18000c44e  mov     rax, [rdi]
0x18000c451  mov     rcx, rdi
0x18000c454  mov     rax, [rax+8]
0x18000c458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c45d  lock inc dword ptr [rbx+680h]
0x18000c464  xor     eax, eax
0x18000c466  jmp     short loc_18000C46C
0x18000c468  mov     eax, [rsp+0E8h+var_70]
0x18000c46c  mov     rcx, [rsp+0E8h+var_40]
0x18000c474  xor     rcx, rsp; StackCookie
0x18000c477  call    __security_check_cookie
0x18000c47c  add     rsp, 0B0h
0x18000c483  pop     r15
0x18000c485  pop     r14
0x18000c487  pop     r13
0x18000c489  pop     r12
0x18000c48b  pop     rdi
0x18000c48c  pop     rsi
0x18000c48d  pop     rbx
0x18000c48e  retn
```
