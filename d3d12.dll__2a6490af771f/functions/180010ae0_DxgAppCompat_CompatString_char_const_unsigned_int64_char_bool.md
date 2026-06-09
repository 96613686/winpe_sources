# DxgAppCompat::CompatString(char const *,unsigned __int64 *,char *,bool)

- ea: `0x180010ae0`
- end: `0x180010ce2`
- name: `?CompatString@DxgAppCompat@@YAHPEBDPEA_KPEAD_N@Z`
- size: `514`
- prototype: `int(DxgAppCompat *__hidden this, const char *, unsigned __int64 *, char *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180010ce8`

## callees

- `0x180007104`
- `0x18000a6cc`
- `0x18000acf4`
- `0x18000ae30`
- `0x18000b410`
- `0x18000de10`
- `0x180010ae0`
- `0x180010d8c`
- `0x180010ff4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall DxgAppCompat::CompatString(DxgAppCompat *this, char *a2, char *a3, char *a4)
{
  char *v7; // r8
  bool v8; // r9
  char *v9; // r8
  bool v10; // r9
  unsigned __int64 *v11; // rdx
  unsigned __int64 **v12; // rax
  unsigned __int64 i; // r8
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r8
  unsigned __int64 **v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rcx
  unsigned __int64 **v19; // rax
  unsigned __int64 v20; // r14
  unsigned __int64 v21; // rbx
  unsigned __int64 **v22; // rcx
  __int64 v23; // rax
  unsigned __int64 **v24; // r8
  const char *v25; // r8
  unsigned __int64 v26; // rdx
  __int64 v28; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int64 *v29[2]; // [rsp+28h] [rbp-40h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-30h]
  unsigned __int64 v31; // [rsp+40h] [rbp-28h]

  if ( a3 )
    *a3 = 0;
  std::string::string(v29, a2, a3, a4);
  v28 = 0;
  if ( DxgAppCompat::GetAppCompatString((DxgAppCompat *)&v28, 0, v7, v8) && v28 )
  {
    std::string::resize(v29, v28 - 1);
    v11 = (unsigned __int64 *)v29;
    if ( v31 > 0xF )
      v11 = v29[0];
    DxgAppCompat::GetAppCompatString((DxgAppCompat *)&v28, v11, v9, v10);
    v12 = v29;
    if ( v31 > 0xF )
      v12 = (unsigned __int64 **)v29[0];
    if ( *(_BYTE *)v12 && v28 - 1 == v30 )
    {
      for ( i = 0; ; i = v15 + 1 )
      {
        v14 = std::string::find(v29, this, i);
        v15 = v14;
        if ( v14 == -1 || v14 >= v30 )
          break;
        if ( !v14 )
          goto LABEL_23;
        v16 = v29;
        if ( v31 > 0xF )
          v16 = (unsigned __int64 **)v29[0];
        if ( *((_BYTE *)v16 + v15 - 1) == 59 )
        {
LABEL_23:
          v17 = -1;
          do
            ++v17;
          while ( *((_BYTE *)this + v17) );
          v18 = v17 + v15;
          if ( v17 + v15 < v30 )
          {
            v19 = v29;
            if ( v31 > 0xF )
              v19 = (unsigned __int64 **)v29[0];
            if ( *((_BYTE *)v19 + v18) == 61 )
            {
              v20 = v18 + 1;
              v21 = v30 - v18;
              v22 = v29;
              if ( v31 > 0xF )
                v22 = (unsigned __int64 **)v29[0];
              v23 = std::_Traits_find_ch<std::char_traits<char>>(v22, v30, v20, v31);
              if ( v23 != -1 )
                v21 = v23 - v20 + 1;
              if ( v21 )
              {
                if ( a3 )
                {
                  v24 = v29;
                  if ( v31 > 0xF )
                    v24 = (unsigned __int64 **)v29[0];
                  v25 = (char *)v24 + v20;
                  v26 = v21;
                  if ( v21 >= *(_QWORD *)a2 )
                    v26 = *(_QWORD *)a2;
                  StringCchCopyA(a3, v26, v25);
                }
                *(_QWORD *)a2 = v21;
                std::string::~string(v29);
                return 1;
              }
              else
              {
                *(_QWORD *)a2 = 0;
                std::string::~string(v29);
                return 0;
              }
            }
          }
        }
      }
    }
  }
  std::string::~string(v29);
  return 0;
}

```

## disassembly

```asm
0x180010ae0  mov     [rsp+arg_18], rbx
0x180010ae5  push    rsi
0x180010ae6  push    rdi
0x180010ae7  push    r14
0x180010ae9  sub     rsp, 50h
0x180010aed  mov     rax, cs:__security_cookie
0x180010af4  xor     rax, rsp
0x180010af7  mov     [rsp+68h+var_20], rax
0x180010afc  mov     rdi, r8
0x180010aff  mov     rsi, rdx
0x180010b02  mov     rbx, rcx
0x180010b05  test    r8, r8
0x180010b08  jz      short loc_180010B0E
0x180010b0a  mov     byte ptr [r8], 0
0x180010b0e  lea     rcx, [rsp+68h+var_40]
0x180010b13  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180010b18  nop
0x180010b19  mov     [rsp+68h+var_48], 0
0x180010b22  xor     edx, edx; unsigned __int64 *
0x180010b24  lea     rcx, [rsp+68h+var_48]; this
0x180010b29  call    ?GetAppCompatString@DxgAppCompat@@YAHPEA_KPEAD_N@Z; DxgAppCompat::GetAppCompatString(unsigned __int64 *,char *,bool)
0x180010b2e  test    eax, eax
0x180010b30  jz      loc_180010CB2
0x180010b36  mov     rdx, [rsp+68h+var_48]
0x180010b3b  test    rdx, rdx
0x180010b3e  jz      loc_180010CB2
0x180010b44  dec     rdx
0x180010b47  lea     rcx, [rsp+68h+var_40]
0x180010b4c  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180010b51  lea     rdx, [rsp+68h+var_40]
0x180010b56  cmp     [rsp+68h+var_28], 0Fh
0x180010b5c  cmova   rdx, [rsp+68h+var_40]; unsigned __int64 *
0x180010b62  lea     rcx, [rsp+68h+var_48]; this
0x180010b67  call    ?GetAppCompatString@DxgAppCompat@@YAHPEA_KPEAD_N@Z; DxgAppCompat::GetAppCompatString(unsigned __int64 *,char *,bool)
0x180010b6c  lea     rax, [rsp+68h+var_40]
0x180010b71  cmp     [rsp+68h+var_28], 0Fh
0x180010b77  cmova   rax, [rsp+68h+var_40]
0x180010b7d  cmp     byte ptr [rax], 0
0x180010b80  jz      loc_180010CB2
0x180010b86  mov     rax, [rsp+68h+var_48]
0x180010b8b  dec     rax
0x180010b8e  cmp     rax, [rsp+68h+var_30]
0x180010b93  jnz     loc_180010CB2
0x180010b99  xor     r8d, r8d
0x180010b9c  mov     rdx, rbx
0x180010b9f  lea     rcx, [rsp+68h+var_40]
0x180010ba4  call    ?find@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA_KQEBD_K@Z; std::string::find(char const * const,unsigned __int64)
0x180010ba9  mov     r8, rax
0x180010bac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010bb0  jz      loc_180010CB2
0x180010bb6  mov     r10, [rsp+68h+var_30]
0x180010bbb  cmp     rax, r10
0x180010bbe  jnb     loc_180010CB2
0x180010bc4  mov     rdx, [rsp+68h+var_40]
0x180010bc9  mov     r9, [rsp+68h+var_28]
0x180010bce  test    rax, rax
0x180010bd1  jz      short loc_180010BEC
0x180010bd3  lea     rax, [rsp+68h+var_40]
0x180010bd8  cmp     r9, 0Fh
0x180010bdc  cmova   rax, rdx
0x180010be0  cmp     byte ptr [rax+r8-1], 3Bh ; ';'
0x180010be6  jnz     loc_180010CAA
0x180010bec  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010bf0  inc     rax
0x180010bf3  cmp     byte ptr [rbx+rax], 0
0x180010bf7  jnz     short loc_180010BF0
0x180010bf9  lea     rcx, [rax+r8]
0x180010bfd  cmp     rcx, r10
0x180010c00  jnb     loc_180010CAA
0x180010c06  lea     rax, [rsp+68h+var_40]
0x180010c0b  cmp     r9, 0Fh
0x180010c0f  cmova   rax, rdx
0x180010c13  cmp     byte ptr [rcx+rax], 3Dh ; '='
0x180010c17  jnz     loc_180010CAA
0x180010c1d  lea     r14, [rcx+1]
0x180010c21  mov     rbx, r10
0x180010c24  sub     rbx, r14
0x180010c27  inc     rbx
0x180010c2a  lea     rcx, [rsp+68h+var_40]
0x180010c2f  cmp     r9, 0Fh
0x180010c33  cmova   rcx, rdx
0x180010c37  mov     r8, r14
0x180010c3a  mov     rdx, r10
0x180010c3d  call    ??$_Traits_find_ch@U?$char_traits@D@std@@@std@@YA_KQEBD_K1D@Z; std::_Traits_find_ch<std::char_traits<char>>(char const * const,unsigned __int64,unsigned __int64,char)
0x180010c42  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010c46  jz      short loc_180010C51
0x180010c48  mov     rbx, rax
0x180010c4b  sub     rbx, r14
0x180010c4e  inc     rbx
0x180010c51  test    rbx, rbx
0x180010c54  jz      short loc_180010C95
0x180010c56  test    rdi, rdi
0x180010c59  jz      short loc_180010C81
0x180010c5b  lea     r8, [rsp+68h+var_40]
0x180010c60  cmp     [rsp+68h+var_28], 0Fh
0x180010c66  cmova   r8, [rsp+68h+var_40]
0x180010c6c  add     r8, r14; char *
0x180010c6f  mov     rdx, rbx
0x180010c72  cmp     rbx, [rsi]
0x180010c75  cmovnb  rdx, [rsi]; unsigned __int64
0x180010c79  mov     rcx, rdi; char *
0x180010c7c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180010c81  mov     [rsi], rbx
0x180010c84  lea     rcx, [rsp+68h+var_40]
0x180010c89  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180010c8e  mov     eax, 1
0x180010c93  jmp     short loc_180010CC3
0x180010c95  mov     qword ptr [rsi], 0
0x180010c9c  lea     rcx, [rsp+68h+var_40]
0x180010ca1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180010ca6  xor     eax, eax
0x180010ca8  jmp     short loc_180010CC3
0x180010caa  inc     r8
0x180010cad  jmp     loc_180010B9C
0x180010cb2  lea     rcx, [rsp+68h+var_40]
0x180010cb7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180010cbc  nop
0x180010cbd  jmp     short loc_180010CC1
0x180010cbf  jmp     short $+2
0x180010cc1  xor     eax, eax
0x180010cc3  mov     rcx, [rsp+68h+var_20]
0x180010cc8  xor     rcx, rsp; StackCookie
0x180010ccb  call    __security_check_cookie
0x180010cd0  mov     rbx, [rsp+68h+arg_18]
0x180010cd8  add     rsp, 50h
0x180010cdc  pop     r14
0x180010cde  pop     rdi
0x180010cdf  pop     rsi
0x180010ce0  retn
```
