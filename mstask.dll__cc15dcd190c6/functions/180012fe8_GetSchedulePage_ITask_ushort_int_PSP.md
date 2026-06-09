# GetSchedulePage(ITask *,ushort *,int,_PSP * *)

- ea: `0x180012fe8`
- end: `0x1800132ab`
- name: `?GetSchedulePage@@YAJPEAUITask@@PEAGHPEAPEAU_PSP@@@Z`
- size: `707`
- prototype: `__int64 __fastcall(struct ITask *, unsigned __int16 *Src, int, struct _PSP **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010098`
- `0x180012f9c`

## callees

- `0x180009ef8`
- `0x180009f38`
- `0x18000fd74`
- `0x1800101b4`
- `0x180012c38`
- `0x180012fe8`
- `0x1800133cc`
- `0x18001aa82`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800130fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800130fe`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001310c`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001310c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800130d6`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800130cb`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x1800130cb`
- `COMCTL32!CreatePropertySheetPageW` at `0x180013265`
- `COMCTL32!CreatePropertySheetPageW` at `0x180013265`

## pseudocode

```c
__int64 __fastcall GetSchedulePage(struct ITask *a1, unsigned __int16 *Src, int a3, struct _PSP **a4)
{
  unsigned __int16 *v7; // rdi
  int JobPath; // ebx
  struct ITaskVtbl *lpVtbl; // rax
  BOOL v10; // ebp
  CSchedulePage *v11; // rax
  CSchedulePage *v12; // rsi
  HRSRC ResourceW; // rax
  signed int LastError; // eax
  HGLOBAL Resource; // rax
  const void *v16; // rax
  const void *v17; // rdi
  __int64 v18; // rcx
  const unsigned __int8 *v19; // rax
  const unsigned __int8 *v20; // rax
  __int16 v21; // dx
  _BYTE *v22; // r8
  unsigned __int16 v23; // r10
  __int16 v24; // r11
  __int64 v25; // rcx
  unsigned __int16 *v26; // rcx
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rcx
  __int64 v29; // rax
  unsigned __int16 v30; // r8
  __int64 v31; // r9
  unsigned __int16 *v32; // rax
  unsigned __int16 *v33; // rcx
  __int64 v34; // rcx
  unsigned __int16 *v35; // rcx
  __int64 v36; // rax
  size_t v37; // rcx
  unsigned int v38; // r14d
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rbp
  struct _PSP *PropertySheetPageW; // rax
  unsigned __int16 *v42; // rcx
  unsigned __int16 *v44; // [rsp+30h] [rbp-58h] BYREF
  __int16 v45; // [rsp+98h] [rbp+10h] BYREF

  v44 = 0;
  if ( Src )
  {
    v7 = NewDupString(Src);
    if ( !v7 )
      return (unsigned int)-2147024882;
  }
  else
  {
    JobPath = GetJobPath(a1, &v44);
    if ( JobPath < 0 )
      return (unsigned int)JobPath;
    v7 = v44;
  }
  lpVtbl = a1->lpVtbl;
  v45 = 0;
  JobPath = ((__int64 (__fastcall *)(struct ITask *, __int16 *))lpVtbl->GetTriggerCount)(a1, &v45);
  if ( JobPath < 0 )
  {
    operator delete(v7);
    return (unsigned int)JobPath;
  }
  v10 = v45 != 1;
  v11 = (CSchedulePage *)operator new(0x358u);
  if ( !v11 || (v12 = CSchedulePage::CSchedulePage(v11, a1, v7, v10, a3)) == 0 )
  {
    v42 = v7;
    goto LABEL_49;
  }
  ResourceW = FindResourceW(g_hInstance, (LPCWSTR)0x192, (LPCWSTR)5);
  if ( ResourceW )
  {
    Resource = LoadResource(g_hInstance, ResourceW);
    if ( Resource )
    {
      v16 = LockResource(Resource);
      v17 = v16;
      if ( v16 )
      {
        v18 = 26;
        if ( *((_WORD *)v16 + 1) != 0xFFFF )
          v18 = 18;
        v19 = SkipResourceTemplateArray((const unsigned __int8 *)v16 + v18);
        v20 = SkipResourceTemplateArray(v19);
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)&v20[2 * v25] );
        v26 = (unsigned __int16 *)&v20[2 * v25 + 2];
        v44 = v26;
        if ( (*v22 & 0x40) != 0 )
        {
          v27 = v26 + 1;
          v28 = v26 + 3;
          if ( v21 != v24 )
            v28 = v27;
          v29 = -1;
          do
            ++v29;
          while ( v28[v29] );
          v26 = &v28[v29 + 1];
        }
        v30 = 0;
        if ( v23 )
        {
          v31 = 12;
          if ( v21 != v24 )
            v31 = 9;
          do
          {
            if ( ((unsigned __int8)v26 & 3) != 0 )
              v26 = (unsigned __int16 *)((char *)v26 + 4LL - ((unsigned __int8)v26 & 3));
            v32 = &v26[v31];
            if ( v26[v31] == v24 )
            {
              v33 = v32 + 2;
            }
            else
            {
              v34 = -1;
              do
                ++v34;
              while ( v32[v34] );
              v33 = &v32[v34 + 1];
            }
            if ( *v33 == v24 )
            {
              v35 = v33 + 2;
            }
            else
            {
              v36 = -1;
              do
                ++v36;
              while ( v33[v36] );
              v35 = &v33[v36 + 1];
            }
            if ( *v35 )
              v26 = &v35[*v35];
            else
              v26 = v35 + 1;
            ++v30;
          }
          while ( v30 < v23 );
        }
        v37 = (unsigned int)((_DWORD)v26 - (_DWORD)v17);
        v38 = v37;
        v39 = (unsigned __int16 *)operator new(v37);
        v40 = v39;
        if ( !v39 )
          return (unsigned int)-2147024882;
        memcpy_0(v39, v17, v38);
        *((_QWORD *)v12 + 3) = v40;
        *((_DWORD *)v12 + 3) |= 1u;
        PropertySheetPageW = CreatePropertySheetPageW((LPCPROPSHEETPAGEW)((char *)v12 + 8));
        if ( PropertySheetPageW )
        {
          *a4 = PropertySheetPageW;
          return (unsigned int)JobPath;
        }
        (**(void (__fastcall ***)(CSchedulePage *, __int64))v12)(v12, 1);
        v42 = v40;
LABEL_49:
        operator delete(v42);
        return (unsigned int)-2147024882;
      }
    }
  }
  LastError = GetLastError();
  JobPath = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)JobPath;
}

```

## disassembly

```asm
0x180012fe8  push    rbx
0x180012fea  push    rbp
0x180012feb  push    rsi
0x180012fec  push    rdi
0x180012fed  push    r12
0x180012fef  push    r13
0x180012ff1  push    r14
0x180012ff3  push    r15
0x180012ff5  sub     rsp, 48h
0x180012ff9  xor     r12d, r12d
0x180012ffc  mov     r15, r9
0x180012fff  mov     [rsp+88h+var_58], r12
0x180013004  mov     r14d, r8d
0x180013007  mov     rsi, rcx
0x18001300a  test    rdx, rdx
0x18001300d  jz      short loc_180013024
0x18001300f  mov     rcx, rdx; Src
0x180013012  call    ?NewDupString@@YAPEAGPEBG@Z; NewDupString(ushort const *)
0x180013017  mov     rdi, rax
0x18001301a  test    rax, rax
0x18001301d  jnz     short loc_18001303D
0x18001301f  jmp     loc_180013293
0x180013024  lea     rdx, [rsp+88h+var_58]; unsigned __int16 **
0x180013029  call    ?GetJobPath@@YAJPEAUITask@@PEAPEAG@Z; GetJobPath(ITask *,ushort * *)
0x18001302e  mov     ebx, eax
0x180013030  test    eax, eax
0x180013032  js      loc_180013298
0x180013038  mov     rdi, [rsp+88h+var_58]
0x18001303d  mov     rax, [rsi]
0x180013040  lea     rdx, [rsp+88h+arg_8]
0x180013048  mov     rcx, rsi
0x18001304b  mov     [rsp+88h+arg_8], r12w
0x180013054  mov     rax, [rax+28h]
0x180013058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001305d  mov     ebx, eax
0x18001305f  test    eax, eax
0x180013061  jns     short loc_180013070
0x180013063  mov     rcx, rdi; Block
0x180013066  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001306b  jmp     loc_180013298
0x180013070  mov     r13d, 1
0x180013076  mov     ebp, r12d
0x180013079  cmp     [rsp+88h+arg_8], r13w
0x180013082  mov     ecx, 358h; Size
0x180013087  setnz   bpl
0x18001308b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013090  test    rax, rax
0x180013093  jz      loc_18001328B
0x180013099  mov     r9d, ebp; int
0x18001309c  mov     [rsp+88h+var_68], r14d; int
0x1800130a1  mov     r8, rdi; unsigned __int16 *
0x1800130a4  mov     rdx, rsi; struct ITask *
0x1800130a7  mov     rcx, rax; this
0x1800130aa  call    ??0CSchedulePage@@QEAA@PEAUITask@@PEAGHH@Z; CSchedulePage::CSchedulePage(ITask *,ushort *,int,int)
0x1800130af  mov     rsi, rax
0x1800130b2  test    rax, rax
0x1800130b5  jz      loc_18001328B
0x1800130bb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800130c2  lea     r8d, [r13+4]; lpType
0x1800130c6  mov     edx, 192h; lpName
0x1800130cb  call    cs:__imp_FindResourceW
0x1800130d1  test    rax, rax
0x1800130d4  jnz     short loc_1800130F4
0x1800130d6  call    cs:__imp_GetLastError
0x1800130dc  mov     ebx, eax
0x1800130de  test    eax, eax
0x1800130e0  jle     loc_180013298
0x1800130e6  movzx   ebx, ax
0x1800130e9  or      ebx, 80070000h
0x1800130ef  jmp     loc_180013298
0x1800130f4  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x1800130fb  mov     rdx, rax; hResInfo
0x1800130fe  call    cs:__imp_LoadResource
0x180013104  test    rax, rax
0x180013107  jz      short loc_1800130D6
0x180013109  mov     rcx, rax; hResData
0x18001310c  call    cs:__imp_LockResource
0x180013112  mov     rdi, rax
0x180013115  test    rax, rax
0x180013118  jz      short loc_1800130D6
0x18001311a  movzx   edx, word ptr [rax+2]
0x18001311e  lea     r8, [rax+0Ch]
0x180013122  mov     r11d, 0FFFFh
0x180013128  cmp     dx, r11w
0x18001312c  jz      short loc_180013131
0x18001312e  mov     r8, rax
0x180013131  mov     eax, 10h
0x180013136  lea     ecx, [rax-8]
0x180013139  cmovnz  eax, ecx
0x18001313c  mov     ecx, 1Ah
0x180013141  movzx   r10d, word ptr [rax+rdi]
0x180013146  lea     ebp, [rcx-8]
0x180013149  cmovnz  ecx, ebp
0x18001314c  add     rcx, rdi; unsigned __int8 *
0x18001314f  call    ?SkipResourceTemplateArray@@YAPEBEPEBE@Z; SkipResourceTemplateArray(uchar const *)
0x180013154  mov     rcx, rax; unsigned __int8 *
0x180013157  call    ?SkipResourceTemplateArray@@YAPEBEPEBE@Z; SkipResourceTemplateArray(uchar const *)
0x18001315c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180013160  mov     rcx, r14
0x180013163  inc     rcx
0x180013166  cmp     [rax+rcx*2], r12w
0x18001316b  jnz     short loc_180013163
0x18001316d  inc     rcx
0x180013170  lea     rcx, [rax+rcx*2]
0x180013174  mov     [rsp+88h+var_58], rcx
0x180013179  test    byte ptr [r8], 40h
0x18001317d  jz      short loc_1800131A4
0x18001317f  lea     rax, [rcx+2]
0x180013183  cmp     dx, r11w
0x180013187  lea     rcx, [rax+4]
0x18001318b  cmovnz  rcx, rax
0x18001318f  mov     rax, r14
0x180013192  inc     rax
0x180013195  cmp     [rcx+rax*2], r12w
0x18001319a  jnz     short loc_180013192
0x18001319c  lea     rcx, [rcx+rax*2]
0x1800131a0  add     rcx, 2
0x1800131a4  mov     r8d, r12d
0x1800131a7  cmp     r12w, r10w
0x1800131ab  jnb     loc_180013234
0x1800131b1  cmp     dx, r11w
0x1800131b5  mov     r9d, 18h
0x1800131bb  cmovnz  r9, rbp
0x1800131bf  mov     rdx, rcx
0x1800131c2  and     edx, 3
0x1800131c5  jz      short loc_1800131D2
0x1800131c7  mov     eax, 4
0x1800131cc  sub     rax, rdx
0x1800131cf  add     rcx, rax
0x1800131d2  lea     rax, [r9+rcx]
0x1800131d6  cmp     [rax], r11w
0x1800131da  jnz     short loc_1800131E2
0x1800131dc  lea     rcx, [rax+4]
0x1800131e0  jmp     short loc_1800131F6
0x1800131e2  mov     rcx, r14
0x1800131e5  inc     rcx
0x1800131e8  cmp     [rax+rcx*2], r12w
0x1800131ed  jnz     short loc_1800131E5
0x1800131ef  inc     rcx
0x1800131f2  lea     rcx, [rax+rcx*2]
0x1800131f6  cmp     [rcx], r11w
0x1800131fa  jnz     short loc_180013202
0x1800131fc  add     rcx, 4
0x180013200  jmp     short loc_180013217
0x180013202  mov     rax, r14
0x180013205  inc     rax
0x180013208  cmp     [rcx+rax*2], r12w
0x18001320d  jnz     short loc_180013205
0x18001320f  lea     rcx, [rcx+rax*2]
0x180013213  add     rcx, 2
0x180013217  cmp     [rcx], r12w
0x18001321b  jz      short loc_180013226
0x18001321d  movzx   eax, word ptr [rcx]
0x180013220  lea     rcx, [rcx+rax*2]
0x180013224  jmp     short loc_18001322A
0x180013226  add     rcx, 2
0x18001322a  add     r8w, r13w
0x18001322e  cmp     r8w, r10w
0x180013232  jb      short loc_1800131BF
0x180013234  sub     ecx, edi; Size
0x180013236  mov     r14d, ecx
0x180013239  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001323e  mov     rbp, rax
0x180013241  test    rax, rax
0x180013244  jz      short loc_180013293
0x180013246  mov     r8d, r14d; Size
0x180013249  mov     rdx, rdi; Src
0x18001324c  mov     rcx, rax; void *
0x18001324f  call    memcpy_0
0x180013254  lea     rcx, [rsi+8]; constPropSheetPagePointer
0x180013258  mov     [rsi+18h], rbp
0x18001325c  mov     eax, [rcx+4]
0x18001325f  or      eax, r13d
0x180013262  mov     [rsi+0Ch], eax
0x180013265  call    cs:__imp_CreatePropertySheetPageW
0x18001326b  test    rax, rax
0x18001326e  jnz     short loc_180013286
0x180013270  mov     rax, [rsi]
0x180013273  mov     edx, r13d
0x180013276  mov     rcx, rsi
0x180013279  mov     rax, [rax]
0x18001327c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013281  mov     rcx, rbp
0x180013284  jmp     short loc_18001328E
0x180013286  mov     [r15], rax
0x180013289  jmp     short loc_180013298
0x18001328b  mov     rcx, rdi; Block
0x18001328e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013293  mov     ebx, 8007000Eh
0x180013298  mov     eax, ebx
0x18001329a  add     rsp, 48h
0x18001329e  pop     r15
0x1800132a0  pop     r14
0x1800132a2  pop     r13
0x1800132a4  pop     r12
0x1800132a6  pop     rdi
0x1800132a7  pop     rsi
0x1800132a8  pop     rbp
0x1800132a9  pop     rbx
0x1800132aa  retn
```
