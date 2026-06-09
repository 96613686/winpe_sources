# CPackage::EmbedWriteToStream(IStream *,ulong *)

- ea: `0x1800080a8`
- end: `0x18000845d`
- name: `?EmbedWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z`
- size: `949`
- prototype: `__int64 __fastcall(CPackage *this, struct IStream *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a074`

## callees

- `0x1800080a8`
- `0x18000aa50`
- `0x18000af50`
- `0x18000cbf0`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800080f8`
- `SHLWAPI!__imp_SHUnicodeToAnsi` at `0x1800080f8`
- `KERNEL32!lstrlenW` at `0x1800082ac`
- `KERNEL32!lstrlenW` at `0x180008326`
- `KERNEL32!lstrlenW` at `0x1800083b7`
- `KERNEL32!lstrlenW` at `0x1800082ac`
- `KERNEL32!lstrlenW` at `0x180008326`
- `KERNEL32!lstrlenW` at `0x1800083b7`
- `KERNEL32!lstrlenA` at `0x180008103`
- `KERNEL32!lstrlenA` at `0x180008103`

## pseudocode

```c
__int64 __fastcall CPackage::EmbedWriteToStream(CPackage *this, struct IStream *a2, unsigned int *a3)
{
  __int64 v3; // rax
  const WCHAR *v7; // r14
  int v8; // edx
  struct IStreamVtbl *lpVtbl; // rax
  struct IStreamVtbl *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // r8d
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-CCh] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  CHAR pszDst[272]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = *((_QWORD *)this + 14);
  v16 = 0;
  v7 = *(const WCHAR **)(v3 + 592);
  SHUnicodeToAnsi(v7, pszDst, 260);
  v18 = lstrlenA(pszDst) + 1;
  v8 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64, int *))a2->lpVtbl->Write)(a2, &v18, 4, &v16);
  if ( v8 >= 0 )
  {
    v15 = 0;
    v8 = StringWriteToStream(a2, pszDst, &v15);
    if ( v8 >= 0 )
    {
      v16 += v15;
      lpVtbl = a2->lpVtbl;
      v17 = 0;
      v19 = 0;
      v8 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, __int64 *))lpVtbl->Seek)(a2, 0, 1, &v19);
      if ( v8 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(struct IStream *, __int64, __int64, unsigned int *))a2->lpVtbl->Write)(
               a2,
               *((_QWORD *)this + 14) + 68LL,
               4,
               &v15);
        if ( v8 >= 0 )
        {
          v16 += v15;
          if ( v7 )
          {
            v14 = 0;
            v8 = CopyFileToStream(v7, a2, &v14);
            if ( v8 >= 0 )
            {
              if ( *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) != v14 )
              {
                v10 = a2->lpVtbl;
                v17 = v19;
                v8 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))v10->Seek)(a2, v19, 0, 0);
                if ( v8 >= 0 )
                {
                  *(_DWORD *)(*((_QWORD *)this + 14) + 68LL) = v14;
                  v8 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Write)(
                         a2,
                         &v14,
                         4,
                         &v15);
                  if ( v8 >= 0 )
                  {
                    v17 = v14;
                    v8 = ((__int64 (__fastcall *)(struct IStream *, _QWORD, __int64, _QWORD))a2->lpVtbl->Seek)(
                           a2,
                           v14,
                           1,
                           0);
                  }
                }
              }
              v11 = v14 + v16;
              v16 += v14;
              if ( v8 >= 0 )
              {
                if ( a3 )
                  *a3 = v11;
                v14 = lstrlenW(v7);
                if ( ((int (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Write)(
                       a2,
                       &v14,
                       4,
                       &v15) >= 0 )
                {
                  v12 = v15;
                  if ( v15 == 4 )
                  {
                    *a3 += 4;
                    ((void (__fastcall *)(struct IStream *, const WCHAR *, _QWORD, unsigned int *))a2->lpVtbl->Write)(
                      a2,
                      v7,
                      2 * v14,
                      &v15);
                    v12 = v15;
                  }
                  if ( 2LL * v14 == v12 )
                    *a3 += v12;
                }
                v14 = lstrlenW((LPCWSTR)(*((_QWORD *)this + 12) + 528LL));
                v8 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Write)(
                       a2,
                       &v14,
                       4,
                       &v15);
                if ( v8 >= 0 && v15 == 4 )
                {
                  *a3 += 4;
                  v8 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned int *))a2->lpVtbl->Write)(
                         a2,
                         *((_QWORD *)this + 12) + 528LL,
                         2 * v14,
                         &v15);
                  if ( v8 >= 0 && 2LL * v14 == v15 )
                  {
                    *a3 += 2 * v14;
                    v14 = lstrlenW((LPCWSTR)(*((_QWORD *)this + 12) + 8LL));
                    v8 = ((__int64 (__fastcall *)(struct IStream *, unsigned int *, __int64, unsigned int *))a2->lpVtbl->Write)(
                           a2,
                           &v14,
                           4,
                           &v15);
                    if ( v8 >= 0 && v15 == 4 )
                    {
                      *a3 += 4;
                      v8 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, unsigned int *))a2->lpVtbl->Write)(
                             a2,
                             *((_QWORD *)this + 12) + 8LL,
                             2 * v14,
                             &v15);
                      if ( v8 >= 0 && v15 == 2LL * v14 )
                        *a3 += 2 * v14;
                    }
                  }
                }
              }
            }
          }
          else
          {
            return (unsigned int)-2147467259;
          }
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800080a8  mov     [rsp-8+arg_18], rbx
0x1800080ad  push    rbp
0x1800080ae  push    rsi
0x1800080af  push    rdi
0x1800080b0  push    r12
0x1800080b2  push    r14
0x1800080b4  lea     rbp, [rsp-80h]
0x1800080b9  sub     rsp, 180h
0x1800080c0  mov     rax, cs:__security_cookie
0x1800080c7  xor     rax, rsp
0x1800080ca  mov     [rbp+0A0h+var_30], rax
0x1800080ce  mov     rax, [rcx+70h]
0x1800080d2  mov     rdi, r8
0x1800080d5  mov     [rsp+1A0h+var_168], 0
0x1800080dd  mov     rbx, rdx
0x1800080e0  mov     rsi, rcx
0x1800080e3  lea     rdx, [rsp+1A0h+pszDst]; pszDst
0x1800080e8  mov     r8d, 104h; cchBuf
0x1800080ee  mov     r14, [rax+250h]
0x1800080f5  mov     rcx, r14; pwszSrc
0x1800080f8  call    cs:__imp_SHUnicodeToAnsi
0x1800080fe  lea     rcx, [rsp+1A0h+pszDst]; lpString
0x180008103  call    cs:__imp_lstrlenA
0x180008109  mov     r12d, 4
0x18000810f  lea     r9, [rsp+1A0h+var_168]
0x180008114  inc     eax
0x180008116  lea     rdx, [rsp+1A0h+var_158]
0x18000811b  mov     [rsp+1A0h+var_158], eax
0x18000811f  mov     r8d, r12d
0x180008122  mov     rax, [rbx]
0x180008125  mov     rcx, rbx
0x180008128  mov     rax, [rax+20h]
0x18000812c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008131  mov     edx, eax
0x180008133  test    eax, eax
0x180008135  js      loc_180008438
0x18000813b  lea     r8, [rsp+1A0h+var_16C]; unsigned int *
0x180008140  mov     [rsp+1A0h+var_16C], 0
0x180008148  lea     rdx, [rsp+1A0h+pszDst]; char *
0x18000814d  mov     rcx, rbx; struct IStream *
0x180008150  call    ?StringWriteToStream@@YAJPEAUIStream@@PEBDPEAK@Z; StringWriteToStream(IStream *,char const *,ulong *)
0x180008155  mov     edx, eax
0x180008157  test    eax, eax
0x180008159  js      loc_180008438
0x18000815f  mov     eax, [rsp+1A0h+var_16C]
0x180008163  lea     r9, [rsp+1A0h+var_150]
0x180008168  add     [rsp+1A0h+var_168], eax
0x18000816c  lea     r8d, [r12-3]
0x180008171  mov     rax, [rbx]
0x180008174  mov     rcx, rbx
0x180008177  mov     [rsp+1A0h+var_160], 0
0x180008180  mov     rdx, [rsp+1A0h+var_160]
0x180008185  mov     [rsp+1A0h+var_150], 0
0x18000818e  mov     rax, [rax+28h]
0x180008192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008197  mov     edx, eax
0x180008199  test    eax, eax
0x18000819b  js      loc_180008438
0x1800081a1  mov     rax, [rbx]
0x1800081a4  lea     r9, [rsp+1A0h+var_16C]
0x1800081a9  mov     rdx, [rsi+70h]
0x1800081ad  mov     r8d, r12d
0x1800081b0  add     rdx, 44h ; 'D'
0x1800081b4  mov     rcx, rbx
0x1800081b7  mov     rax, [rax+20h]
0x1800081bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081c0  mov     edx, eax
0x1800081c2  test    eax, eax
0x1800081c4  js      loc_180008438
0x1800081ca  mov     eax, [rsp+1A0h+var_16C]
0x1800081ce  add     [rsp+1A0h+var_168], eax
0x1800081d2  test    r14, r14
0x1800081d5  jz      loc_180008433
0x1800081db  lea     r8, [rsp+1A0h+var_170]; unsigned int *
0x1800081e0  mov     [rsp+1A0h+var_170], 0
0x1800081e8  mov     rdx, rbx; struct IStream *
0x1800081eb  mov     rcx, r14; lpFileName
0x1800081ee  call    ?CopyFileToStream@@YAJPEBGPEAUIStream@@PEAK@Z; CopyFileToStream(ushort const *,IStream *,ulong *)
0x1800081f3  mov     edx, eax
0x1800081f5  test    eax, eax
0x1800081f7  js      loc_180008438
0x1800081fd  mov     rcx, [rsi+70h]
0x180008201  mov     eax, [rsp+1A0h+var_170]
0x180008205  cmp     [rcx+44h], eax
0x180008208  jz      loc_18000828E
0x18000820e  mov     rax, [rbx]
0x180008211  xor     r9d, r9d
0x180008214  mov     rdx, [rsp+1A0h+var_150]
0x180008219  xor     r8d, r8d
0x18000821c  mov     rcx, rbx
0x18000821f  mov     [rsp+1A0h+var_160], rdx
0x180008224  mov     rax, [rax+28h]
0x180008228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000822d  mov     edx, eax
0x18000822f  test    eax, eax
0x180008231  js      short loc_18000828E
0x180008233  mov     rcx, [rsi+70h]
0x180008237  lea     r9, [rsp+1A0h+var_16C]
0x18000823c  mov     eax, [rsp+1A0h+var_170]
0x180008240  lea     rdx, [rsp+1A0h+var_170]
0x180008245  mov     r8d, r12d
0x180008248  mov     [rcx+44h], eax
0x18000824b  mov     rcx, rbx
0x18000824e  mov     rax, [rbx]
0x180008251  mov     rax, [rax+20h]
0x180008255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000825a  mov     edx, eax
0x18000825c  test    eax, eax
0x18000825e  js      short loc_18000828E
0x180008260  mov     eax, [rsp+1A0h+var_170]
0x180008264  lea     r8d, [r12-3]
0x180008269  mov     dword ptr [rsp+1A0h+var_160], eax
0x18000826d  xor     r9d, r9d
0x180008270  mov     rax, [rbx]
0x180008273  mov     rcx, rbx
0x180008276  mov     dword ptr [rsp+1A0h+var_160+4], 0
0x18000827e  mov     rdx, [rsp+1A0h+var_160]
0x180008283  mov     rax, [rax+28h]
0x180008287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000828c  mov     edx, eax
0x18000828e  mov     eax, [rsp+1A0h+var_168]
0x180008292  add     eax, [rsp+1A0h+var_170]
0x180008296  mov     [rsp+1A0h+var_168], eax
0x18000829a  test    edx, edx
0x18000829c  js      loc_180008438
0x1800082a2  test    rdi, rdi
0x1800082a5  jz      short loc_1800082A9
0x1800082a7  mov     [rdi], eax
0x1800082a9  mov     rcx, r14; lpString
0x1800082ac  call    cs:__imp_lstrlenW
0x1800082b2  mov     [rsp+1A0h+var_170], eax
0x1800082b6  lea     r9, [rsp+1A0h+var_16C]
0x1800082bb  mov     rax, [rbx]
0x1800082be  mov     r8d, r12d
0x1800082c1  lea     rdx, [rsp+1A0h+var_170]
0x1800082c6  mov     rcx, rbx
0x1800082c9  mov     rax, [rax+20h]
0x1800082cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082d2  test    eax, eax
0x1800082d4  js      short loc_180008319
0x1800082d6  mov     r8d, [rsp+1A0h+var_16C]
0x1800082db  cmp     r8d, r12d
0x1800082de  jnz     short loc_180008307
0x1800082e0  add     [rdi], r12d
0x1800082e3  lea     r9, [rsp+1A0h+var_16C]
0x1800082e8  mov     rax, [rbx]
0x1800082eb  mov     rdx, r14
0x1800082ee  mov     r8d, [rsp+1A0h+var_170]
0x1800082f3  mov     rcx, rbx
0x1800082f6  add     r8d, r8d
0x1800082f9  mov     rax, [rax+20h]
0x1800082fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008302  mov     r8d, [rsp+1A0h+var_16C]
0x180008307  mov     ecx, [rsp+1A0h+var_170]
0x18000830b  add     rcx, rcx
0x18000830e  mov     eax, r8d
0x180008311  cmp     rcx, rax
0x180008314  jnz     short loc_180008319
0x180008316  add     [rdi], r8d
0x180008319  mov     rcx, [rsi+60h]
0x18000831d  mov     r14d, 210h
0x180008323  add     rcx, r14; lpString
0x180008326  call    cs:__imp_lstrlenW
0x18000832c  mov     [rsp+1A0h+var_170], eax
0x180008330  lea     r9, [rsp+1A0h+var_16C]
0x180008335  mov     rax, [rbx]
0x180008338  mov     r8d, r12d
0x18000833b  lea     rdx, [rsp+1A0h+var_170]
0x180008340  mov     rcx, rbx
0x180008343  mov     rax, [rax+20h]
0x180008347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000834c  mov     edx, eax
0x18000834e  test    eax, eax
0x180008350  js      loc_180008438
0x180008356  cmp     [rsp+1A0h+var_16C], r12d
0x18000835b  jnz     loc_180008438
0x180008361  add     [rdi], r12d
0x180008364  lea     r9, [rsp+1A0h+var_16C]
0x180008369  mov     rax, [rbx]
0x18000836c  mov     rcx, rbx
0x18000836f  mov     r8d, [rsp+1A0h+var_170]
0x180008374  mov     rdx, [rsi+60h]
0x180008378  add     r8d, r8d
0x18000837b  add     rdx, r14
0x18000837e  mov     rax, [rax+20h]
0x180008382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008387  mov     edx, eax
0x180008389  test    eax, eax
0x18000838b  js      loc_180008438
0x180008391  mov     r8d, [rsp+1A0h+var_170]
0x180008396  mov     eax, [rsp+1A0h+var_16C]
0x18000839a  mov     ecx, r8d
0x18000839d  add     rcx, rcx
0x1800083a0  cmp     rcx, rax
0x1800083a3  jnz     loc_180008438
0x1800083a9  lea     eax, [r8+r8]
0x1800083ad  add     [rdi], eax
0x1800083af  mov     rcx, [rsi+60h]
0x1800083b3  add     rcx, 8; lpString
0x1800083b7  call    cs:__imp_lstrlenW
0x1800083bd  mov     [rsp+1A0h+var_170], eax
0x1800083c1  lea     r9, [rsp+1A0h+var_16C]
0x1800083c6  mov     rax, [rbx]
0x1800083c9  mov     r8d, r12d
0x1800083cc  lea     rdx, [rsp+1A0h+var_170]
0x1800083d1  mov     rcx, rbx
0x1800083d4  mov     rax, [rax+20h]
0x1800083d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083dd  mov     edx, eax
0x1800083df  test    eax, eax
0x1800083e1  js      short loc_180008438
0x1800083e3  cmp     [rsp+1A0h+var_16C], r12d
0x1800083e8  jnz     short loc_180008438
0x1800083ea  add     [rdi], r12d
0x1800083ed  lea     r9, [rsp+1A0h+var_16C]
0x1800083f2  mov     rax, [rbx]
0x1800083f5  mov     rcx, rbx
0x1800083f8  mov     r8d, [rsp+1A0h+var_170]
0x1800083fd  mov     rdx, [rsi+60h]
0x180008401  add     r8d, r8d
0x180008404  add     rdx, 8
0x180008408  mov     rax, [rax+20h]
0x18000840c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008411  mov     edx, eax
0x180008413  test    eax, eax
0x180008415  js      short loc_180008438
0x180008417  mov     r8d, [rsp+1A0h+var_170]
0x18000841c  mov     eax, [rsp+1A0h+var_16C]
0x180008420  mov     ecx, r8d
0x180008423  add     rcx, rcx
0x180008426  cmp     rax, rcx
0x180008429  jnz     short loc_180008438
0x18000842b  lea     eax, [r8+r8]
0x18000842f  add     [rdi], eax
0x180008431  jmp     short loc_180008438
0x180008433  mov     edx, 80004005h
0x180008438  mov     eax, edx
0x18000843a  mov     rcx, [rbp+0A0h+var_30]
0x18000843e  xor     rcx, rsp; StackCookie
0x180008441  call    __security_check_cookie
0x180008446  mov     rbx, [rsp+1A0h+arg_18]
0x18000844e  add     rsp, 180h
0x180008455  pop     r14
0x180008457  pop     r12
0x180008459  pop     rdi
0x18000845a  pop     rsi
0x18000845b  pop     rbp
0x18000845c  retn
```
