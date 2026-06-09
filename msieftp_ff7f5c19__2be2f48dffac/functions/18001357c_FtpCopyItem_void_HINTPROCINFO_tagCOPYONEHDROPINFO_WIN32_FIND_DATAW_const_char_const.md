# FtpCopyItem(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *,_WIN32_FIND_DATAW const *,char const *)

- ea: `0x18001357c`
- end: `0x1800138f3`
- name: `?FtpCopyItem@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@PEBU_WIN32_FIND_DATAW@@PEBD@Z`
- size: `887`
- prototype: `int(void *, struct HINTPROCINFO *, struct tagCOPYONEHDROPINFO *, const struct _WIN32_FIND_DATAW *, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013108`

## callees

- `0x180002240`
- `0x180009650`
- `0x1800121f0`
- `0x180012920`
- `0x18001357c`
- `0x18001d840`
- `0x18001f858`
- `0x180021538`
- `0x180024134`
- `0x180028010`

## import_xrefs

- `SHLWAPI!PathAppendW` at `0x180013719`
- `SHLWAPI!PathAppendW` at `0x180013837`
- `SHLWAPI!PathAppendW` at `0x180013719`
- `SHLWAPI!PathAppendW` at `0x180013837`

## pseudocode

```c
__int64 __fastcall FtpCopyItem(void *a1, HWND *a2, struct tagCOPYONEHDROPINFO *a3, const struct _WIN32_FIND_DATAW *a4)
{
  WCHAR *cFileName; // r13
  HWND v5; // r15
  const struct _WIN32_FIND_DATAW *v6; // r12
  unsigned int v9; // ebx
  __int64 v10; // r14
  __int64 v11; // rax
  const unsigned __int16 *v12; // r8
  __int64 v13; // r15
  WCHAR *v14; // r8
  WCHAR *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  unsigned int v19; // r12d
  WCHAR *v20; // rcx
  WCHAR *v21; // rax
  WCHAR *v22; // r8
  int v23; // edx
  unsigned int v24; // r9d
  unsigned int v26; // [rsp+28h] [rbp-D8h]
  unsigned int v27; // [rsp+30h] [rbp-D0h]
  HWND v30; // [rsp+60h] [rbp-A0h]
  _QWORD v31[4]; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+90h] [rbp-70h]
  int v33; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  int v36[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int128 v39; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v40[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR pszPath[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR v42[264]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v43[256]; // [rsp+710h] [rbp+610h] BYREF

  cFileName = a4->cFileName;
  v5 = *a2;
  v31[0] = *(_QWORD *)a3;
  v6 = a4;
  v38 = 0;
  v39 = 0;
  v31[1] = v42;
  v31[2] = a4->cFileName;
  v31[3] = v40;
  v32 = *((_DWORD *)a3 + 8);
  v9 = 0;
  v10 = 260;
  v33 = *((_DWORD *)a3 + 9);
  v35 = *((_QWORD *)a3 + 6);
  v36[0] = *((_DWORD *)a3 + 14);
  v36[1] = 0;
  v37 = *((_QWORD *)a3 + 8);
  *((_QWORD *)&v39 + 1) = *((_QWORD *)a3 + 12);
  v38 = *(_OWORD *)((char *)a3 + 72);
  v34 = 0;
  v30 = v5;
  UrlGetAbstractPathFromPidl(*((const struct _ITEMIDLIST **)v5 + 5), 0, 0, v40, 0x104u);
  DisplayPathAppend(v40, 0x104u, *((const unsigned __int16 **)a3 + 2));
  v11 = *((_QWORD *)v5 + 2);
  v12 = &lParam;
  if ( *(_QWORD *)(v11 + 64) )
    v12 = *(const unsigned __int16 **)(v11 + 64);
  StringCchCopyW(v43, 0x100u, v12);
  if ( (int)CFtpSite::GetFtpDir(*((CFtpSite **)v5 + 2), v43, v40, (struct CFtpDir **)a2) >= 0 )
  {
    v13 = 2147483646;
    if ( *((_DWORD *)a3 + 8) != 5 && (v6->dwFileAttributes & 0x10) == 0 )
    {
      v14 = (WCHAR *)*((_QWORD *)a3 + 1);
      v15 = pszPath;
      v16 = 2147483646;
      v17 = 260;
      do
      {
        if ( !v16 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v16;
        --v17;
      }
      while ( v17 );
      v18 = v15 - 1;
      if ( v17 )
        v18 = v15;
      *v18 = 0;
      if ( !PathAppendW(pszPath, cFileName) )
        goto LABEL_35;
      if ( v37 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 96LL))(v37, 2);
      v19 = ConfirmCopy(
              pszPath,
              cFileName,
              (enum OPS *)&v33,
              a2[1],
              *(struct CFtpFolder **)a3,
              (struct CFtpDir *)*a2,
              0,
              1,
              v36);
      if ( v37 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v37 + 96LL))(v37, 3, 0);
      v9 = 0;
      if ( v19 == 1 )
        goto LABEL_36;
      v9 = v19;
      if ( v19 )
        goto LABEL_36;
      v6 = a4;
    }
    if ( *cFileName == 46 && (!v6->cFileName[1] || v6->cFileName[1] == 46 && !v6->cFileName[2]) )
      goto LABEL_36;
    v20 = (WCHAR *)*((_QWORD *)a3 + 1);
    v21 = v42;
    do
    {
      if ( !v13 )
        break;
      if ( !*v20 )
        break;
      *v21++ = *v20++;
      --v13;
      --v10;
    }
    while ( v10 );
    v22 = v21 - 1;
    if ( v10 )
      v22 = v21;
    *v22 = 0;
    if ( PathAppendW(v42, cFileName) )
    {
      v9 = CopyFileSysItem(a1, (struct HINTPROCINFO *)a2, (struct tagCOPYONEHDROPINFO *)v31);
      if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147023673 && *((_DWORD *)a3 + 8) != 5 )
      {
        DisplayWininetError(a2[1], v23, v9, v24, 0x195u, v26, v27, *((struct IProgressDialog **)a3 + 8));
        v9 = -2147023673;
      }
      goto LABEL_36;
    }
LABEL_35:
    v9 = -2147024785;
LABEL_36:
    *((_QWORD *)a3 + 12) = *((_QWORD *)&v39 + 1);
    *(_OWORD *)((char *)a3 + 72) = v38;
    *((_DWORD *)a3 + 9) = v33;
    (*(void (__fastcall **)(HWND))(*(_QWORD *)*a2 + 16LL))(*a2);
    v5 = v30;
  }
  *a2 = v5;
  return v9;
}

```

## disassembly

```asm
0x18001357c  push    rbp
0x18001357e  push    rbx
0x18001357f  push    rsi
0x180013580  push    rdi
0x180013581  push    r12
0x180013583  push    r13
0x180013585  push    r14
0x180013587  push    r15
0x180013589  lea     rbp, [rsp-828h]
0x180013591  sub     rsp, 928h
0x180013598  mov     rax, cs:__security_cookie
0x18001359f  xor     rax, rsp
0x1800135a2  mov     [rbp+860h+var_50], rax
0x1800135a9  mov     rax, [r8]
0x1800135ac  lea     r13, [r9+2Ch]
0x1800135b0  mov     r15, [rdx]
0x1800135b3  xorps   xmm0, xmm0
0x1800135b6  mov     [rsp+960h+var_8F0], rax
0x1800135bb  mov     r12, r9
0x1800135be  movups  [rbp+860h+var_8A8], xmm0
0x1800135c2  mov     [rsp+960h+var_908], rcx
0x1800135c7  xor     ecx, ecx
0x1800135c9  movups  [rbp+860h+var_898], xmm0
0x1800135cd  lea     rax, [rbp+860h+var_460]
0x1800135d4  mov     [rsp+960h+var_910], r9
0x1800135d9  mov     [rsp+960h+var_8E8], rax
0x1800135de  lea     r9, [rbp+860h+var_880]; void *
0x1800135e2  lea     rax, [rbp+860h+var_880]
0x1800135e6  mov     [rbp+860h+var_8E0], r13
0x1800135ea  mov     [rbp+860h+var_8D8], rax
0x1800135ee  mov     rdi, r8
0x1800135f1  mov     eax, [r8+20h]
0x1800135f5  mov     rsi, rdx
0x1800135f8  mov     [rbp+860h+var_8D0], eax
0x1800135fb  mov     ebx, ecx
0x1800135fd  mov     eax, [r8+24h]
0x180013601  mov     r14d, 104h
0x180013607  mov     [rbp+860h+var_8CC], eax
0x18001360a  xor     edx, edx; int
0x18001360c  mov     rax, [r8+30h]
0x180013610  mov     [rbp+860h+var_8C0], rax
0x180013614  mov     eax, [r8+38h]
0x180013618  mov     [rbp+860h+var_8B8], eax
0x18001361b  xor     eax, eax
0x18001361d  mov     [rbp+860h+var_8B4], eax
0x180013620  mov     rax, [r8+40h]
0x180013624  mov     [rbp+860h+var_8B0], rax
0x180013628  mov     rax, [r8+60h]
0x18001362c  mov     qword ptr [rbp+860h+var_898+8], rax
0x180013630  mov     rax, [r8+48h]
0x180013634  mov     qword ptr [rbp+860h+var_8A8], rax
0x180013638  mov     rax, [r8+50h]
0x18001363c  xor     r8d, r8d; int
0x18001363f  mov     qword ptr [rbp+860h+var_8A8+8], rax
0x180013643  mov     [rbp+860h+var_8C8], rcx
0x180013647  mov     rcx, [r15+28h]; struct _ITEMIDLIST *
0x18001364b  mov     [rsp+960h+var_900], r15
0x180013650  mov     dword ptr [rsp+960h+var_940], r14d; unsigned int
0x180013655  call    ?UrlGetAbstractPathFromPidl@@YAJPEFBU_ITEMIDLIST@@HHPEAXK@Z; UrlGetAbstractPathFromPidl(_ITEMIDLIST const *,int,int,void *,ulong)
0x18001365a  mov     r8, [rdi+10h]; unsigned __int16 *
0x18001365e  lea     rcx, [rbp+860h+var_880]; unsigned __int16 *
0x180013662  mov     edx, r14d; unsigned int
0x180013665  call    ?DisplayPathAppend@@YAJPEAGKPEBG@Z; DisplayPathAppend(ushort *,ulong,ushort const *)
0x18001366a  mov     rax, [r15+10h]
0x18001366e  lea     r8, lParam
0x180013675  lea     edx, [r14-4]; unsigned __int64
0x180013679  lea     rcx, [rbp+860h+var_250]; unsigned __int16 *
0x180013680  cmp     [rax+40h], rbx
0x180013684  cmovnz  r8, [rax+40h]; unsigned __int16 *
0x180013689  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001368e  mov     rcx, [r15+10h]; this
0x180013692  lea     r8, [rbp+860h+var_880]; unsigned __int16 *
0x180013696  mov     r9, rsi; struct CFtpDir **
0x180013699  lea     rdx, [rbp+860h+var_250]; unsigned __int16 *
0x1800136a0  call    ?GetFtpDir@CFtpSite@@QEAAJPEBG0PEAPEAVCFtpDir@@@Z; CFtpSite::GetFtpDir(ushort const *,ushort const *,CFtpDir * *)
0x1800136a5  xor     r10d, r10d
0x1800136a8  test    eax, eax
0x1800136aa  js      loc_1800138CB
0x1800136b0  cmp     dword ptr [rdi+20h], 5
0x1800136b4  mov     r15d, 7FFFFFFEh
0x1800136ba  jz      loc_1800137C6
0x1800136c0  test    byte ptr [r12], 10h
0x1800136c5  jnz     loc_1800137C6
0x1800136cb  mov     r8, [rdi+8]
0x1800136cf  lea     rax, [rbp+860h+pszPath]
0x1800136d6  mov     ecx, r15d
0x1800136d9  mov     edx, r14d
0x1800136dc  test    rcx, rcx
0x1800136df  jz      short loc_180013700
0x1800136e1  movzx   r9d, word ptr [r8]
0x1800136e5  test    r9w, r9w
0x1800136e9  jz      short loc_180013700
0x1800136eb  mov     [rax], r9w
0x1800136ef  add     r8, 2
0x1800136f3  add     rax, 2
0x1800136f7  dec     rcx
0x1800136fa  sub     rdx, 1
0x1800136fe  jnz     short loc_1800136DC
0x180013700  test    rdx, rdx
0x180013703  lea     rcx, [rax-2]
0x180013707  mov     rdx, r13; pszMore
0x18001370a  cmovnz  rcx, rax
0x18001370e  mov     [rcx], r10w
0x180013712  lea     rcx, [rbp+860h+pszPath]; pszPath
0x180013719  call    cs:__imp_PathAppendW
0x18001371f  test    eax, eax
0x180013721  jz      loc_180013894
0x180013727  mov     rcx, [rbp+860h+var_8B0]
0x18001372b  test    rcx, rcx
0x18001372e  jz      short loc_180013743
0x180013730  mov     rax, [rcx]
0x180013733  xor     r8d, r8d
0x180013736  mov     rax, [rax+60h]
0x18001373a  lea     edx, [r8+2]
0x18001373e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013743  mov     r9, [rsi+8]; HWND
0x180013747  lea     rax, [rbp+860h+var_8B8]
0x18001374b  mov     [rsp+960h+var_920], rax; int *
0x180013750  lea     r8, [rbp+860h+var_8CC]; enum OPS *
0x180013754  mov     rax, [rsi]
0x180013757  lea     rcx, [rbp+860h+pszPath]; lpFileName
0x18001375e  mov     dword ptr [rsp+960h+var_928], 1; int
0x180013766  mov     rdx, r13; unsigned __int16 *
0x180013769  mov     [rsp+960h+var_930], rbx; unsigned int
0x18001376e  mov     [rsp+960h+var_938], rax; unsigned int
0x180013773  mov     rax, [rdi]
0x180013776  mov     [rsp+960h+var_940], rax; struct CFtpFolder *
0x18001377b  call    ?ConfirmCopy@@YAJPEBG0PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAKHPEAH@Z; ConfirmCopy(ushort const *,ushort const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,ulong *,int,int *)
0x180013780  mov     r9, [rbp+860h+var_8B0]
0x180013784  xor     r10d, r10d
0x180013787  mov     r12d, eax
0x18001378a  test    r9, r9
0x18001378d  jz      short loc_1800137A8
0x18001378f  mov     rcx, [r9]
0x180013792  lea     edx, [r10+3]
0x180013796  xor     r8d, r8d
0x180013799  mov     rax, [rcx+60h]
0x18001379d  mov     rcx, r9
0x1800137a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137a5  xor     r10d, r10d
0x1800137a8  cmp     r12d, 1
0x1800137ac  mov     ebx, r10d
0x1800137af  cmovnz  ebx, r12d
0x1800137b3  jz      loc_180013899
0x1800137b9  test    ebx, ebx
0x1800137bb  jnz     loc_180013899
0x1800137c1  mov     r12, [rsp+960h+var_910]
0x1800137c6  mov     ecx, 2Eh ; '.'
0x1800137cb  cmp     cx, [r13+0]
0x1800137d0  jnz     short loc_1800137F2
0x1800137d2  cmp     r10w, [r12+2Eh]
0x1800137d8  jz      loc_180013899
0x1800137de  cmp     cx, [r12+2Eh]
0x1800137e4  jnz     short loc_1800137F2
0x1800137e6  cmp     r10w, [r12+30h]
0x1800137ec  jz      loc_180013899
0x1800137f2  mov     rcx, [rdi+8]
0x1800137f6  lea     rax, [rbp+860h+var_460]
0x1800137fd  test    r15, r15
0x180013800  jz      short loc_18001381E
0x180013802  movzx   edx, word ptr [rcx]
0x180013805  test    dx, dx
0x180013808  jz      short loc_18001381E
0x18001380a  mov     [rax], dx
0x18001380d  add     rcx, 2
0x180013811  add     rax, 2
0x180013815  dec     r15
0x180013818  sub     r14, 1
0x18001381c  jnz     short loc_1800137FD
0x18001381e  lea     r8, [rax-2]
0x180013822  test    r14, r14
0x180013825  mov     rdx, r13; pszMore
0x180013828  lea     rcx, [rbp+860h+var_460]; pszPath
0x18001382f  cmovnz  r8, rax
0x180013833  mov     [r8], r10w
0x180013837  call    cs:__imp_PathAppendW
0x18001383d  test    eax, eax
0x18001383f  jz      short loc_180013894
0x180013841  mov     rcx, [rsp+960h+var_908]; void *
0x180013846  lea     r8, [rsp+960h+var_8F0]; struct tagCOPYONEHDROPINFO *
0x18001384b  mov     rdx, rsi; struct HINTPROCINFO *
0x18001384e  call    ?CopyFileSysItem@@YAJPEAXPEAUHINTPROCINFO@@PEAUtagCOPYONEHDROPINFO@@@Z; CopyFileSysItem(void *,HINTPROCINFO *,tagCOPYONEHDROPINFO *)
0x180013853  mov     ebx, eax
0x180013855  mov     eax, 80000000h
0x18001385a  lea     ecx, [rbx+rax]
0x18001385d  test    eax, ecx
0x18001385f  jnz     short loc_180013899
0x180013861  mov     r14d, 800704C7h
0x180013867  cmp     ebx, r14d
0x18001386a  jz      short loc_180013899
0x18001386c  cmp     dword ptr [rdi+20h], 5
0x180013870  jz      short loc_180013899
0x180013872  mov     rcx, [rdi+40h]
0x180013876  mov     r8d, ebx; int
0x180013879  mov     [rsp+960h+var_928], rcx; struct IProgressDialog *
0x18001387e  mov     rcx, [rsi+8]; HWND
0x180013882  mov     dword ptr [rsp+960h+var_940], 195h; unsigned int
0x18001388a  call    ?DisplayWininetError@@YAHPEAUHWND__@@HJIIIIPEAUIProgressDialog@@@Z; DisplayWininetError(HWND__ *,int,long,uint,uint,uint,uint,IProgressDialog *)
0x18001388f  mov     ebx, r14d
0x180013892  jmp     short loc_180013899
0x180013894  mov     ebx, 8007006Fh
0x180013899  mov     rax, qword ptr [rbp+860h+var_898+8]
0x18001389d  mov     [rdi+60h], rax
0x1800138a1  mov     rax, qword ptr [rbp+860h+var_8A8]
0x1800138a5  mov     [rdi+48h], rax
0x1800138a9  mov     rax, qword ptr [rbp+860h+var_8A8+8]
0x1800138ad  mov     [rdi+50h], rax
0x1800138b1  mov     eax, [rbp+860h+var_8CC]
0x1800138b4  mov     [rdi+24h], eax
0x1800138b7  mov     rcx, [rsi]
0x1800138ba  mov     rax, [rcx]
0x1800138bd  mov     rax, [rax+10h]
0x1800138c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138c6  mov     r15, [rsp+960h+var_900]
0x1800138cb  mov     [rsi], r15
0x1800138ce  mov     eax, ebx
0x1800138d0  mov     rcx, [rbp+860h+var_50]
0x1800138d7  xor     rcx, rsp; StackCookie
0x1800138da  call    __security_check_cookie
0x1800138df  add     rsp, 928h
0x1800138e6  pop     r15
0x1800138e8  pop     r14
0x1800138ea  pop     r13
0x1800138ec  pop     r12
0x1800138ee  pop     rdi
0x1800138ef  pop     rsi
0x1800138f0  pop     rbx
0x1800138f1  pop     rbp
0x1800138f2  retn
```
