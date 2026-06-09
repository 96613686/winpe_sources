# CFtpObj::Load(IStream *)

- ea: `0x18001a010`
- end: `0x18001a297`
- name: `?Load@CFtpObj@@UEAAJPEAUIStream@@@Z`
- size: `647`
- prototype: `int(CFtpObj *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180016b4c`
- `0x180019bb8`
- `0x18001a010`
- `0x18001a770`
- `0x18001ddf4`
- `0x18001e11c`
- `0x180026cf4`
- `0x180028010`

## import_xrefs

- `SHELL32!SHGetDesktopFolder` at `0x18001a0b5`
- `SHELL32!SHGetDesktopFolder` at `0x18001a0b5`
- `SHELL32!__imp_ILFree` at `0x18001a116`
- `SHELL32!__imp_ILFree` at `0x18001a19b`
- `SHELL32!__imp_ILFree` at `0x18001a116`
- `SHELL32!__imp_ILFree` at `0x18001a19b`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18001a095`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18001a17c`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18001a095`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18001a17c`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a070`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a135`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a1bc`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a070`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a135`
- `SHLWAPI!__imp_IStream_Read` at `0x18001a1bc`

## pseudocode

```c
__int64 __fastcall CFtpObj::Load(CFtpObj *this, struct IStream *a2)
{
  HRESULT inserted; // ebx
  LPITEMIDLIST v5; // r15
  HRESULT v6; // r14d
  int v7; // r14d
  int v8; // r14d
  LPITEMIDLIST pidl; // [rsp+30h] [rbp-59h] BYREF
  int v11; // [rsp+38h] [rbp-51h] BYREF
  int v12; // [rsp+3Ch] [rbp-4Dh] BYREF
  IShellFolder *ppshf; // [rsp+40h] [rbp-49h] BYREF
  __int128 pv; // [rsp+48h] [rbp-41h] BYREF
  int v15; // [rsp+58h] [rbp-31h]
  _BYTE pitem[16]; // [rsp+60h] [rbp-29h] BYREF
  struct tagFORMATETC v17; // [rsp+70h] [rbp-19h] BYREF
  struct tagSTGMEDIUM v18; // [rsp+90h] [rbp+7h] BYREF

  inserted = -2147024809;
  if ( a2 )
  {
    pv = 0;
    v15 = 0;
    v11 = 0;
    v12 = 0;
    if ( *((_DWORD *)this + 18) )
    {
      inserted = -2147023649;
    }
    else
    {
      inserted = IStream_Read(a2, &pv, 0x14u);
      if ( inserted >= 0 )
      {
        *((_DWORD *)this + 28) = DWORD2(pv);
        pidl = 0;
        inserted = ILLoadFromStreamEx(a2, &pidl);
        if ( inserted >= 0 )
        {
          v5 = pidl;
          ppshf = 0;
          v6 = SHGetDesktopFolder(&ppshf);
          inserted = v6;
          if ( v6 >= 0 )
          {
            v6 = ((__int64 (__fastcall *)(IShellFolder *, LPITEMIDLIST, _QWORD, GUID *, char *))ppshf->lpVtbl->BindToObject)(
                   ppshf,
                   v5,
                   0,
                   &IID_CFtpFolder,
                   (char *)this + 32);
            ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
            inserted = v6;
            if ( v6 >= 0 )
              *((_QWORD *)this + 5) = CFtpFolder::GetFtpDir(*((CFtpFolder **)this + 4));
          }
          ILFree(pidl);
          if ( v6 >= 0 )
          {
            inserted = IStream_Read(a2, &v11, 4u);
            if ( inserted >= 0 )
            {
              inserted = CFtpPidlList_Create(0, 0, (struct CFtpPidlList **)this + 6);
              if ( inserted >= 0 )
              {
                v7 = 0;
                if ( v11 <= 0 )
                {
LABEL_17:
                  inserted = IStream_Read(a2, &v12, 4u);
                  if ( inserted >= 0 )
                  {
                    v8 = 0;
                    if ( v12 <= 0 )
                    {
LABEL_26:
                      if ( DWORD1(pv) )
                      {
                        pidl = (LPITEMIDLIST)DWORD1(pv);
                        inserted = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 40LL))(
                                     a2,
                                     DWORD1(pv),
                                     1,
                                     0);
                      }
                    }
                    else
                    {
                      while ( inserted >= 0 )
                      {
                        memset_0(pitem, 0, 0x48u);
                        inserted = FormatEtcLoadFromStream(a2, &v17);
                        if ( inserted >= 0 )
                          inserted = StgMediumLoadFromStream(a2, &v18);
                        if ( inserted >= 0 )
                          DSA_InsertItem(*((HDSA *)this + 8), 0x7FFFFFFF, pitem);
                        if ( ++v8 >= v12 )
                        {
                          if ( inserted < 0 )
                            break;
                          goto LABEL_26;
                        }
                      }
                    }
                  }
                }
                else
                {
                  while ( inserted >= 0 )
                  {
                    pidl = 0;
                    inserted = ILLoadFromStreamEx(a2, &pidl);
                    if ( inserted >= 0 )
                    {
                      inserted = CFtpPidlList::InsertSorted(*((CFtpPidlList **)this + 6), pidl);
                      ILFree(pidl);
                    }
                    if ( ++v7 >= v11 )
                    {
                      if ( inserted < 0 )
                        break;
                      goto LABEL_17;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( !*((_DWORD *)this + 18) )
      *((_DWORD *)this + 18) = (inserted >> 31) + 2;
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18001a010  mov     [rsp-8+arg_10], rbx
0x18001a015  push    rbp
0x18001a016  push    rsi
0x18001a017  push    rdi
0x18001a018  push    r14
0x18001a01a  push    r15
0x18001a01c  lea     rbp, [rsp-37h]
0x18001a021  sub     rsp, 0C0h
0x18001a028  mov     rax, cs:__security_cookie
0x18001a02f  xor     rax, rsp
0x18001a032  mov     [rbp+57h+var_30], rax
0x18001a036  mov     rsi, rdx
0x18001a039  mov     rdi, rcx
0x18001a03c  mov     ebx, 80070057h
0x18001a041  test    rdx, rdx
0x18001a044  jz      loc_18001A272
0x18001a04a  xor     eax, eax
0x18001a04c  xorps   xmm0, xmm0
0x18001a04f  movups  [rbp+57h+pv], xmm0
0x18001a053  mov     [rbp+57h+var_88], eax
0x18001a056  mov     [rbp+57h+var_A8], eax
0x18001a059  mov     [rbp+57h+var_A4], eax
0x18001a05c  cmp     [rcx+48h], eax
0x18001a05f  jnz     loc_18001A25C
0x18001a065  lea     r8d, [rax+14h]; cb
0x18001a069  mov     rcx, rsi; pstm
0x18001a06c  lea     rdx, [rbp+57h+pv]; pv
0x18001a070  call    cs:__imp_IStream_Read
0x18001a076  mov     ebx, eax
0x18001a078  test    eax, eax
0x18001a07a  js      loc_18001A261
0x18001a080  mov     eax, dword ptr [rbp+57h+pv+8]
0x18001a083  lea     rdx, [rbp+57h+pidl]; pidl
0x18001a087  mov     rcx, rsi; pstm
0x18001a08a  mov     [rdi+70h], eax
0x18001a08d  mov     [rbp+57h+pidl], 0
0x18001a095  call    cs:__imp_ILLoadFromStreamEx
0x18001a09b  mov     ebx, eax
0x18001a09d  test    eax, eax
0x18001a09f  js      loc_18001A261
0x18001a0a5  mov     r15, [rbp+57h+pidl]
0x18001a0a9  lea     rcx, [rbp+57h+ppshf]; ppshf
0x18001a0ad  mov     [rbp+57h+ppshf], 0
0x18001a0b5  call    cs:__imp_SHGetDesktopFolder
0x18001a0bb  mov     r14d, eax
0x18001a0be  mov     ebx, eax
0x18001a0c0  test    eax, eax
0x18001a0c2  js      short loc_18001A112
0x18001a0c4  mov     rcx, [rbp+57h+ppshf]
0x18001a0c8  lea     r8, [rdi+20h]
0x18001a0cc  mov     [rsp+0E0h+var_C0], r8
0x18001a0d1  lea     r9, ?IID_CFtpFolder@@3U_GUID@@B; _GUID const IID_CFtpFolder
0x18001a0d8  xor     r8d, r8d
0x18001a0db  mov     rdx, r15
0x18001a0de  mov     rax, [rcx]
0x18001a0e1  mov     rax, [rax+28h]
0x18001a0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0ea  mov     rcx, [rbp+57h+ppshf]
0x18001a0ee  mov     r14d, eax
0x18001a0f1  mov     rax, [rcx]
0x18001a0f4  mov     rax, [rax+10h]
0x18001a0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0fd  mov     ebx, r14d
0x18001a100  test    r14d, r14d
0x18001a103  js      short loc_18001A112
0x18001a105  mov     rcx, [rdi+20h]; this
0x18001a109  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x18001a10e  mov     [rdi+28h], rax
0x18001a112  mov     rcx, [rbp+57h+pidl]; pidl
0x18001a116  call    cs:__imp_ILFree
0x18001a11c  test    r14d, r14d
0x18001a11f  js      loc_18001A261
0x18001a125  mov     r15d, 4
0x18001a12b  lea     rdx, [rbp+57h+var_A8]; pv
0x18001a12f  mov     r8d, r15d; cb
0x18001a132  mov     rcx, rsi; pstm
0x18001a135  call    cs:__imp_IStream_Read
0x18001a13b  mov     ebx, eax
0x18001a13d  test    eax, eax
0x18001a13f  js      loc_18001A261
0x18001a145  lea     r8, [rdi+30h]; struct CFtpPidlList **
0x18001a149  xor     edx, edx; struct _ITEMIDLIST **
0x18001a14b  xor     ecx, ecx; int
0x18001a14d  call    ?CFtpPidlList_Create@@YAJHQEAPEFBU_ITEMIDLIST@@PEAPEAVCFtpPidlList@@@Z; CFtpPidlList_Create(int,_ITEMIDLIST const * * const,CFtpPidlList * *)
0x18001a152  mov     ebx, eax
0x18001a154  test    eax, eax
0x18001a156  js      loc_18001A261
0x18001a15c  xor     r14d, r14d
0x18001a15f  cmp     [rbp+57h+var_A8], r14d
0x18001a163  jle     short loc_18001A1B2
0x18001a165  test    ebx, ebx
0x18001a167  js      loc_18001A261
0x18001a16d  lea     rdx, [rbp+57h+pidl]; pidl
0x18001a171  mov     [rbp+57h+pidl], 0
0x18001a179  mov     rcx, rsi; pstm
0x18001a17c  call    cs:__imp_ILLoadFromStreamEx
0x18001a182  mov     ebx, eax
0x18001a184  test    eax, eax
0x18001a186  js      short loc_18001A1A1
0x18001a188  mov     rdx, [rbp+57h+pidl]; struct _ITEMIDLIST *
0x18001a18c  mov     rcx, [rdi+30h]; this
0x18001a190  call    ?InsertSorted@CFtpPidlList@@QEAAJPEFBU_ITEMIDLIST@@@Z; CFtpPidlList::InsertSorted(_ITEMIDLIST const *)
0x18001a195  mov     rcx, [rbp+57h+pidl]; pidl
0x18001a199  mov     ebx, eax
0x18001a19b  call    cs:__imp_ILFree
0x18001a1a1  inc     r14d
0x18001a1a4  cmp     r14d, [rbp+57h+var_A8]
0x18001a1a8  jl      short loc_18001A165
0x18001a1aa  test    ebx, ebx
0x18001a1ac  js      loc_18001A261
0x18001a1b2  mov     r8d, r15d; cb
0x18001a1b5  lea     rdx, [rbp+57h+var_A4]; pv
0x18001a1b9  mov     rcx, rsi; pstm
0x18001a1bc  call    cs:__imp_IStream_Read
0x18001a1c2  mov     ebx, eax
0x18001a1c4  test    eax, eax
0x18001a1c6  js      loc_18001A261
0x18001a1cc  xor     r14d, r14d
0x18001a1cf  cmp     [rbp+57h+var_A4], r14d
0x18001a1d3  jle     short loc_18001A22F
0x18001a1d5  test    ebx, ebx
0x18001a1d7  js      loc_18001A261
0x18001a1dd  xor     edx, edx; Val
0x18001a1df  lea     rcx, [rbp+57h+pitem]; void *
0x18001a1e3  lea     r8d, [rdx+48h]; Size
0x18001a1e7  call    memset_0
0x18001a1ec  lea     rdx, [rbp+57h+var_70]; struct tagFORMATETC *
0x18001a1f0  mov     rcx, rsi; pstm
0x18001a1f3  call    ?FormatEtcLoadFromStream@@YAJPEAUIStream@@PEAUtagFORMATETC@@@Z; FormatEtcLoadFromStream(IStream *,tagFORMATETC *)
0x18001a1f8  mov     ebx, eax
0x18001a1fa  test    eax, eax
0x18001a1fc  js      short loc_18001A20C
0x18001a1fe  lea     rdx, [rbp+57h+var_50]; struct tagSTGMEDIUM *
0x18001a202  mov     rcx, rsi; struct IStream *
0x18001a205  call    ?StgMediumLoadFromStream@@YAJPEAUIStream@@PEAUtagSTGMEDIUM@@@Z; StgMediumLoadFromStream(IStream *,tagSTGMEDIUM *)
0x18001a20a  mov     ebx, eax
0x18001a20c  test    ebx, ebx
0x18001a20e  js      short loc_18001A222
0x18001a210  mov     rcx, [rdi+40h]; hdsa
0x18001a214  lea     r8, [rbp+57h+pitem]; pitem
0x18001a218  mov     edx, 7FFFFFFFh; i
0x18001a21d  call    DSA_InsertItem
0x18001a222  inc     r14d
0x18001a225  cmp     r14d, [rbp+57h+var_A4]
0x18001a229  jl      short loc_18001A1D5
0x18001a22b  test    ebx, ebx
0x18001a22d  js      short loc_18001A261
0x18001a22f  mov     eax, dword ptr [rbp+57h+pv+4]
0x18001a232  test    eax, eax
0x18001a234  jz      short loc_18001A261
0x18001a236  xor     ecx, ecx
0x18001a238  mov     dword ptr [rbp+57h+pidl], eax
0x18001a23b  mov     rax, [rsi]
0x18001a23e  xor     r9d, r9d
0x18001a241  mov     dword ptr [rbp+57h+pidl+4], ecx
0x18001a244  mov     rdx, [rbp+57h+pidl]
0x18001a248  lea     r8d, [rcx+1]
0x18001a24c  mov     rcx, rsi
0x18001a24f  mov     rax, [rax+28h]
0x18001a253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a258  mov     ebx, eax
0x18001a25a  jmp     short loc_18001A261
0x18001a25c  mov     ebx, 800704DFh
0x18001a261  cmp     dword ptr [rdi+48h], 0
0x18001a265  jnz     short loc_18001A272
0x18001a267  mov     eax, ebx
0x18001a269  sar     eax, 1Fh
0x18001a26c  add     eax, 2
0x18001a26f  mov     [rdi+48h], eax
0x18001a272  mov     eax, ebx
0x18001a274  mov     rcx, [rbp+57h+var_30]
0x18001a278  xor     rcx, rsp; StackCookie
0x18001a27b  call    __security_check_cookie
0x18001a280  mov     rbx, [rsp+0E0h+arg_10]
0x18001a288  add     rsp, 0C0h
0x18001a28f  pop     r15
0x18001a291  pop     r14
0x18001a293  pop     rdi
0x18001a294  pop     rsi
0x18001a295  pop     rbp
0x18001a296  retn
```
