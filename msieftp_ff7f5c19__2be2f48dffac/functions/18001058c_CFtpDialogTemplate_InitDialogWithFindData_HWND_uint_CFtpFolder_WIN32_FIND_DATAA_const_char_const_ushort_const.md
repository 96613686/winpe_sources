# CFtpDialogTemplate::InitDialogWithFindData(HWND__ *,uint,CFtpFolder *,_WIN32_FIND_DATAA const *,char const *,ushort const *)

- ea: `0x18001058c`
- end: `0x18001071f`
- name: `?InitDialogWithFindData@CFtpDialogTemplate@@QEAAJPEAUHWND__@@IPEAVCFtpFolder@@PEBU_WIN32_FIND_DATAA@@PEBDPEBG@Z`
- size: `403`
- prototype: `__int64 __fastcall(CFtpDialogTemplate *__hidden this, HWND, unsigned int, struct CFtpFolder *, const struct _WIN32_FIND_DATAA *, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180011eec`

## callees

- `0x180002240`
- `0x180010390`
- `0x18001058c`
- `0x18001c0a4`
- `0x18001ddf4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800106f7`
- `SHELL32!__imp_ILFree` at `0x1800106f7`

## pseudocode

```c
__int64 __fastcall CFtpDialogTemplate::InitDialogWithFindData(
        CFtpDialogTemplate *this,
        HWND a2,
        int a3,
        struct CFtpFolder *a4,
        const struct _WIN32_FIND_DATAA *a5,
        const char *a6,
        unsigned __int16 *a7)
{
  __int64 v9; // rdx
  struct _WIN32_FIND_DATAA *v13; // rcx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v23; // xmm1
  __int64 v24; // rdx
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int64 v27; // rax
  CHAR *cFileName; // rcx
  CHAR *v29; // rax
  int inited; // edi
  struct CFtpPidlList *v31; // rbx
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-198h] BYREF
  struct CFtpPidlList *v34; // [rsp+38h] [rbp-190h] BYREF
  struct _WIN32_FIND_DATAA v35; // [rsp+40h] [rbp-188h] BYREF

  v9 = 2;
  v13 = &v35;
  do
  {
    v14 = *(_OWORD *)&a5->ftLastAccessTime.dwHighDateTime;
    *(_OWORD *)&v13->dwFileAttributes = *(_OWORD *)&a5->dwFileAttributes;
    v15 = *(_OWORD *)&a5->nFileSizeLow;
    *(_OWORD *)&v13->ftLastAccessTime.dwHighDateTime = v14;
    v16 = *(_OWORD *)&a5->cFileName[4];
    *(_OWORD *)&v13->nFileSizeLow = v15;
    v17 = *(_OWORD *)&a5->cFileName[20];
    *(_OWORD *)&v13->cFileName[4] = v16;
    v18 = *(_OWORD *)&a5->cFileName[36];
    *(_OWORD *)&v13->cFileName[20] = v17;
    v19 = *(_OWORD *)&a5->cFileName[52];
    *(_OWORD *)&v13->cFileName[36] = v18;
    v20 = *(_OWORD *)&a5->cFileName[68];
    a5 = (const struct _WIN32_FIND_DATAA *)((char *)a5 + 128);
    *(_OWORD *)&v13->cFileName[52] = v19;
    *(_OWORD *)&v13->cFileName[68] = v20;
    v13 = (struct _WIN32_FIND_DATAA *)((char *)v13 + 128);
    --v9;
  }
  while ( v9 );
  v21 = *(_OWORD *)&a5->dwFileAttributes;
  v23 = *(_OWORD *)&a5->ftLastAccessTime.dwHighDateTime;
  pidl = 0;
  v24 = 260;
  *(_OWORD *)&v13->dwFileAttributes = v21;
  v25 = *(_OWORD *)&a5->nFileSizeLow;
  *(_OWORD *)&v13->ftLastAccessTime.dwHighDateTime = v23;
  v26 = *(_OWORD *)&a5->cFileName[4];
  v27 = 2147483646;
  *(_OWORD *)&v13->nFileSizeLow = v25;
  *(_OWORD *)&v13->cFileName[4] = v26;
  cFileName = v35.cFileName;
  do
  {
    if ( !v27 )
      break;
    if ( !*a6 )
      break;
    *cFileName++ = *a6++;
    --v27;
    --v24;
  }
  while ( v24 );
  v29 = cFileName - 1;
  if ( v24 )
    v29 = cFileName;
  *v29 = 0;
  inited = FtpItemID_CreateReal(&v35, a7, &pidl);
  if ( inited >= 0 )
  {
    v34 = 0;
    inited = CFtpPidlList_Create(1, (const struct _ITEMIDLIST **const)&pidl, &v34);
    if ( inited >= 0 )
    {
      v31 = v34;
      inited = CFtpDialogTemplate::InitDialog(this, a2, 0, a3, a4, v34);
      (*(void (__fastcall **)(struct CFtpPidlList *))(*(_QWORD *)v31 + 16LL))(v31);
    }
    ILFree(pidl);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001058c  push    rbx
0x18001058e  push    rbp
0x18001058f  push    rsi
0x180010590  push    rdi
0x180010591  push    r14
0x180010593  push    r15
0x180010595  sub     rsp, 198h
0x18001059c  mov     rax, cs:__security_cookie
0x1800105a3  xor     rax, rsp
0x1800105a6  mov     [rsp+1C8h+var_48], rax
0x1800105ae  mov     rax, [rsp+1C8h+arg_20]
0x1800105b6  mov     rbp, rdx
0x1800105b9  mov     r10, [rsp+1C8h+arg_30]
0x1800105c1  mov     edx, 2
0x1800105c6  mov     r14d, r8d
0x1800105c9  mov     rsi, rcx
0x1800105cc  mov     r15, r9
0x1800105cf  lea     rcx, [rsp+1C8h+var_188]
0x1800105d4  lea     r8d, [rdx+7Eh]
0x1800105d8  movups  xmm0, xmmword ptr [rax]
0x1800105db  movups  xmm1, xmmword ptr [rax+10h]
0x1800105df  movups  xmmword ptr [rcx], xmm0
0x1800105e2  movups  xmm0, xmmword ptr [rax+20h]
0x1800105e6  movups  xmmword ptr [rcx+10h], xmm1
0x1800105ea  movups  xmm1, xmmword ptr [rax+30h]
0x1800105ee  movups  xmmword ptr [rcx+20h], xmm0
0x1800105f2  movups  xmm0, xmmword ptr [rax+40h]
0x1800105f6  movups  xmmword ptr [rcx+30h], xmm1
0x1800105fa  movups  xmm1, xmmword ptr [rax+50h]
0x1800105fe  movups  xmmword ptr [rcx+40h], xmm0
0x180010602  movups  xmm0, xmmword ptr [rax+60h]
0x180010606  movups  xmmword ptr [rcx+50h], xmm1
0x18001060a  movups  xmm1, xmmword ptr [rax+70h]
0x18001060e  add     rax, r8
0x180010611  movups  xmmword ptr [rcx+60h], xmm0
0x180010615  movups  xmmword ptr [rcx+70h], xmm1
0x180010619  add     rcx, r8
0x18001061c  sub     rdx, 1
0x180010620  jnz     short loc_1800105D8
0x180010622  movups  xmm0, xmmword ptr [rax]
0x180010625  mov     r8, [rsp+1C8h+arg_28]
0x18001062d  xor     ebx, ebx
0x18001062f  movups  xmm1, xmmword ptr [rax+10h]
0x180010633  mov     [rsp+1C8h+pidl], rbx
0x180010638  mov     edx, 104h
0x18001063d  movups  xmmword ptr [rcx], xmm0
0x180010640  movups  xmm0, xmmword ptr [rax+20h]
0x180010644  movups  xmmword ptr [rcx+10h], xmm1
0x180010648  movups  xmm1, xmmword ptr [rax+30h]
0x18001064c  mov     eax, 7FFFFFFEh
0x180010651  movups  xmmword ptr [rcx+20h], xmm0
0x180010655  movups  xmmword ptr [rcx+30h], xmm1
0x180010659  lea     rcx, [rsp+1C8h+var_188.cFileName]
0x18001065e  test    rax, rax
0x180010661  jz      short loc_18001067D
0x180010663  mov     r9b, [r8]
0x180010666  test    r9b, r9b
0x180010669  jz      short loc_18001067D
0x18001066b  mov     [rcx], r9b
0x18001066e  inc     r8
0x180010671  inc     rcx
0x180010674  dec     rax
0x180010677  sub     rdx, 1
0x18001067b  jnz     short loc_18001065E
0x18001067d  test    rdx, rdx
0x180010680  lea     rax, [rcx-1]
0x180010684  lea     r8, [rsp+1C8h+pidl]; struct _ITEMIDLIST **
0x180010689  mov     rdx, r10; unsigned __int16 *
0x18001068c  cmovnz  rax, rcx
0x180010690  lea     rcx, [rsp+1C8h+var_188]; struct _WIN32_FIND_DATAA *
0x180010695  mov     [rax], bl
0x180010697  call    ?FtpItemID_CreateReal@@YAJPEBU_WIN32_FIND_DATAA@@PEBGPEAPEFAU_ITEMIDLIST@@@Z; FtpItemID_CreateReal(_WIN32_FIND_DATAA const *,ushort const *,_ITEMIDLIST * *)
0x18001069c  mov     edi, eax
0x18001069e  test    eax, eax
0x1800106a0  js      short loc_1800106FD
0x1800106a2  lea     r8, [rsp+1C8h+var_190]; struct CFtpPidlList **
0x1800106a7  mov     [rsp+1C8h+var_190], rbx
0x1800106ac  lea     rdx, [rsp+1C8h+pidl]; struct _ITEMIDLIST **
0x1800106b1  mov     ecx, 1; int
0x1800106b6  call    ?CFtpPidlList_Create@@YAJHQEAPEFBU_ITEMIDLIST@@PEAPEAVCFtpPidlList@@@Z; CFtpPidlList_Create(int,_ITEMIDLIST const * * const,CFtpPidlList * *)
0x1800106bb  mov     edi, eax
0x1800106bd  test    eax, eax
0x1800106bf  js      short loc_1800106F2
0x1800106c1  mov     rbx, [rsp+1C8h+var_190]
0x1800106c6  mov     r9d, r14d; unsigned int
0x1800106c9  mov     [rsp+1C8h+var_1A0], rbx; struct CFtpPidlList *
0x1800106ce  xor     r8d, r8d; int
0x1800106d1  mov     rdx, rbp; HWND
0x1800106d4  mov     [rsp+1C8h+var_1A8], r15; struct CFtpFolder *
0x1800106d9  mov     rcx, rsi; this
0x1800106dc  call    ?InitDialog@CFtpDialogTemplate@@QEAAJPEAUHWND__@@HIPEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::InitDialog(HWND__ *,int,uint,CFtpFolder *,CFtpPidlList *)
0x1800106e1  mov     edi, eax
0x1800106e3  mov     rcx, rbx
0x1800106e6  mov     rax, [rbx]
0x1800106e9  mov     rax, [rax+10h]
0x1800106ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106f2  mov     rcx, [rsp+1C8h+pidl]; pidl
0x1800106f7  call    cs:__imp_ILFree
0x1800106fd  mov     eax, edi
0x1800106ff  mov     rcx, [rsp+1C8h+var_48]
0x180010707  xor     rcx, rsp; StackCookie
0x18001070a  call    __security_check_cookie
0x18001070f  add     rsp, 198h
0x180010716  pop     r15
0x180010718  pop     r14
0x18001071a  pop     rdi
0x18001071b  pop     rsi
0x18001071c  pop     rbp
0x18001071d  pop     rbx
0x18001071e  retn
```
