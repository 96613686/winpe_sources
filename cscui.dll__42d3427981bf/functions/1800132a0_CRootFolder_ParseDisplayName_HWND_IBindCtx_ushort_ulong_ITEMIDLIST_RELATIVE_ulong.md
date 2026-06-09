# CRootFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800132a0`
- end: `0x18001341e`
- name: `?ParseDisplayName@CRootFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `382`
- prototype: `int(CRootFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180012678`
- `0x1800132a0`
- `0x180013d9c`
- `0x180013dfc`
- `0x18004d010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800133d7`
- `SHELL32!__imp_ILFree` at `0x1800133d7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013357`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013357`

## string_xrefs

- `0x180013304`: `Computers`

## pseudocode

```c
__int64 __fastcall CRootFolder::ParseDisplayName(
        CRootFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  int ID; // edi
  struct _ITEMIDLIST_RELATIVE **v10; // r14
  __int64 v11; // rbx
  ITEMIDLIST *v12; // rbx
  PCNZWCH lpString1[11]; // [rsp+30h] [rbp-58h]
  LPITEMIDLIST pidl; // [rsp+A8h] [rbp+20h] BYREF

  ID = -2147024809;
  if ( a4 )
  {
    v10 = a6;
    if ( a6 )
    {
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b6a94a73e1de37236966b46f5a0ae246_Traceguids, a4);
      }
      *v10 = 0;
      lpString1[0] = L"Computers";
      v11 = 0;
      lpString1[1] = L"KnownFolders";
      lpString1[2] = L"MappedDrives";
      while ( (unsigned int)v11 < 3 )
      {
        if ( CompareStringW(0x7Fu, 1u, lpString1[v11], -1, a4, -1) == 2 )
        {
          pidl = 0;
          ID = CRootFolder::CreateID((CRootFolder *)((char *)this - 16), v11, (struct _ITEMID_CHILD **)&pidl);
          if ( ID >= 0 )
          {
            v12 = pidl;
            if ( !a7
              || (ID = (*(__int64 (__fastcall **)(CRootFolder *, __int64, LPITEMIDLIST *))(*(_QWORD *)this + 72LL))(
                         this,
                         1,
                         &pidl),
                  ID >= 0) )
            {
              *v10 = (struct _ITEMIDLIST_RELATIVE *)v12;
              v12 = 0;
            }
            if ( v12 )
              ILFree(v12);
          }
          break;
        }
        v11 = (unsigned int)(v11 + 1);
      }
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_b6a94a73e1de37236966b46f5a0ae246_Traceguids,
          (_DWORD)a4,
          ID);
      }
    }
  }
  return (unsigned int)ID;
}

```

## disassembly

```asm
0x1800132a0  push    rbx
0x1800132a2  push    rsi
0x1800132a3  push    rdi
0x1800132a4  push    r13
0x1800132a6  push    r14
0x1800132a8  push    r15
0x1800132aa  sub     rsp, 58h
0x1800132ae  mov     rsi, r9
0x1800132b1  mov     r15, rcx
0x1800132b4  mov     edi, 80070057h
0x1800132b9  test    r9, r9
0x1800132bc  jz      loc_18001340E
0x1800132c2  mov     r14, [rsp+88h+arg_28]
0x1800132ca  test    r14, r14
0x1800132cd  jz      loc_18001340E
0x1800132d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132da  lea     r13, WPP_GLOBAL_Control
0x1800132e1  cmp     rcx, r13
0x1800132e4  jz      short loc_180013304
0x1800132e6  test    dword ptr [rcx+1Ch], 2000000h
0x1800132ed  jz      short loc_180013304
0x1800132ef  mov     rcx, [rcx+10h]
0x1800132f3  lea     r8, WPP_b6a94a73e1de37236966b46f5a0ae246_Traceguids
0x1800132fa  mov     edx, 0Bh
0x1800132ff  call    WPP_SF_S
0x180013304  lea     rax, aComputers; "Computers"
0x18001330b  mov     qword ptr [r14], 0
0x180013312  mov     [rsp+88h+lpString1], rax
0x180013317  xor     ebx, ebx
0x180013319  lea     rax, aKnownfolders; "KnownFolders"
0x180013320  mov     [rsp+88h+var_50], rax
0x180013325  lea     rax, aMappeddrives; "MappedDrives"
0x18001332c  mov     [rsp+88h+var_48], rax
0x180013331  cmp     ebx, 3
0x180013334  jnb     loc_1800133DD
0x18001333a  mov     r8, [rsp+rbx*8+88h+lpString1]; lpString1
0x18001333f  or      r9d, 0FFFFFFFFh; cchCount1
0x180013343  mov     [rsp+88h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001334b  mov     [rsp+88h+lpString2], rsi; lpString2
0x180013350  lea     edx, [r9+2]; dwCmpFlags
0x180013354  lea     ecx, [rdx+7Eh]; Locale
0x180013357  call    cs:__imp_CompareStringW
0x18001335d  cmp     eax, 2
0x180013360  jz      short loc_180013366
0x180013362  inc     ebx
0x180013364  jmp     short loc_180013331
0x180013366  lea     rcx, [r15-10h]; this
0x18001336a  mov     [rsp+88h+pidl], 0
0x180013376  lea     r8, [rsp+88h+pidl]; struct _ITEMID_CHILD **
0x18001337e  mov     edx, ebx; unsigned int
0x180013380  call    ?CreateID@CRootFolder@@QEAAJKPEAPEAU_ITEMID_CHILD@@@Z; CRootFolder::CreateID(ulong,_ITEMID_CHILD * *)
0x180013385  mov     edi, eax
0x180013387  test    eax, eax
0x180013389  js      short loc_1800133DD
0x18001338b  mov     r9, [rsp+88h+arg_30]
0x180013393  mov     rbx, [rsp+88h+pidl]
0x18001339b  test    r9, r9
0x18001339e  jz      short loc_1800133CA
0x1800133a0  mov     rax, [r15]
0x1800133a3  lea     r8, [rsp+88h+pidl]
0x1800133ab  mov     edx, 1
0x1800133b0  mov     [rsp+88h+pidl], rbx
0x1800133b8  mov     rcx, r15
0x1800133bb  mov     rax, [rax+48h]
0x1800133bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133c4  mov     edi, eax
0x1800133c6  test    eax, eax
0x1800133c8  js      short loc_1800133CF
0x1800133ca  mov     [r14], rbx
0x1800133cd  xor     ebx, ebx
0x1800133cf  test    rbx, rbx
0x1800133d2  jz      short loc_1800133DD
0x1800133d4  mov     rcx, rbx; pidl
0x1800133d7  call    cs:__imp_ILFree
0x1800133dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133e4  cmp     rcx, r13
0x1800133e7  jz      short loc_18001340E
0x1800133e9  test    dword ptr [rcx+1Ch], 2000000h
0x1800133f0  jz      short loc_18001340E
0x1800133f2  mov     rcx, [rcx+10h]
0x1800133f6  lea     r8, WPP_b6a94a73e1de37236966b46f5a0ae246_Traceguids
0x1800133fd  mov     edx, 0Ch
0x180013402  mov     dword ptr [rsp+88h+lpString2], edi
0x180013406  mov     r9, rsi
0x180013409  call    WPP_SF_Sd
0x18001340e  mov     eax, edi
0x180013410  add     rsp, 58h
0x180013414  pop     r15
0x180013416  pop     r14
0x180013418  pop     r13
0x18001341a  pop     rdi
0x18001341b  pop     rsi
0x18001341c  pop     rbx
0x18001341d  retn
```
