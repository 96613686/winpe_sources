# CPubDocFile::Stat(tagSTATSTG *,ulong)

- ea: `0x1800146d0`
- end: `0x18001501a`
- name: `?Stat@CPubDocFile@@QEAAJPEAUtagSTATSTG@@K@Z`
- size: `2378`
- prototype: `__int64 __fastcall(CPubDocFile *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015280`

## callees

- `0x18000f6b0`
- `0x180013160`
- `0x1800146d0`
- `0x18002e178`
- `0x18002e7e0`
- `0x180042800`
- `0x180043100`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014cd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014cd8`

## pseudocode

```c
__int64 __fastcall CPubDocFile::Stat(CPubDocFile *this, struct tagSTATSTG *a2, char a3)
{
  __int64 v4; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  _QWORD *v10; // r15
  unsigned int v11; // esi
  unsigned int *v12; // r15
  int DirEntry; // ebx
  __int64 v14; // r8
  __int64 v15; // rax
  unsigned int v16; // r10d
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  _QWORD *v23; // r15
  unsigned int v24; // esi
  unsigned int *v25; // r15
  __int64 v26; // r8
  __int64 v27; // rax
  unsigned int v28; // r10d
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rcx
  unsigned int v36; // esi
  __int64 v37; // r15
  __int64 v38; // r8
  __int64 v39; // rax
  unsigned int v40; // r10d
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rsi
  unsigned int v48; // r15d
  __int64 v49; // rsi
  __int64 v50; // r8
  __int64 v51; // rax
  unsigned int v52; // r10d
  __int64 v53; // rdx
  __int64 v54; // rdx
  __int64 v55; // rcx
  void *v57; // rax
  CMSFPageTable *v58; // rcx
  unsigned int v59; // r8d
  CMSFPageTable *v60; // rcx
  unsigned int v61; // r8d
  CMSFPageTable *v62; // rcx
  unsigned int v63; // r8d
  CMSFPageTable *v64; // rcx
  unsigned int v65; // r8d
  _QWORD *v66; // rcx
  _QWORD *v67; // rcx
  struct CMSFPage *v68[2]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v69[24]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v70; // [rsp+58h] [rbp-21h]
  __int64 v71; // [rsp+60h] [rbp-19h]

  v4 = *(_QWORD *)this - *(_QWORD *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1;
  if ( *(_QWORD *)this == *(_QWORD *)&GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1 )
    v4 = *((_QWORD *)this + 1) - *(_QWORD *)GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data4;
  if ( !v4 )
    return CRootPubDocFile::Stat(this, a2, a3);
  if ( (*((_BYTE *)this + 20) & 0x20) != 0 )
    return (unsigned int)-2147286782;
  *(_QWORD *)a2 = 0;
  v7 = *((_QWORD *)this + 15);
  if ( v7 )
    v8 = v7 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v8 = 0;
  if ( *(_DWORD *)v8 == 1279673411 )
  {
    v9 = *(_QWORD *)(v8 + 32);
    if ( v9 )
      v10 = (_QWORD *)(v9 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v10 = 0;
    v11 = *(_DWORD *)(v8 + 40);
    if ( v11 )
    {
      v12 = (unsigned int *)(v10 + 67);
      v68[0] = 0;
      DirEntry = CDirectory::GetDirEntry((CDirectory *)v12, v11, 0, v68);
      if ( DirEntry >= 0 )
      {
        *((_QWORD *)a2 + 4) = *(_QWORD *)((char *)v68[0] + 100);
        v14 = *((_QWORD *)v12 + 2);
        v15 = v11 / *((unsigned __int16 *)v12 + 36);
        v16 = v11 / *((unsigned __int16 *)v12 + 36);
        if ( v14
          && v14 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
          && (v17 = *(_QWORD *)(8 * v15 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v14)) != 0
          && v17 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
        {
          v18 = *(_QWORD *)(8 * v15 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v14);
          if ( v18 )
            v19 = v18 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v19 = 0;
          --*(_DWORD *)(v19 + 40);
        }
        else
        {
          if ( *(_QWORD *)v12 )
            v60 = (CMSFPageTable *)(*(_QWORD *)v12 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
          else
            v60 = 0;
          v61 = v12[8];
          v68[0] = 0;
          if ( (int)CMSFPageTable::FindPage(v60, (struct CPagedVector *)v12, v61, v16, v68) >= 0 )
            --*((_DWORD *)v68[0] + 10);
        }
      }
    }
    else
    {
      memset_0(v69, 0, 0x50u);
      if ( *v10 )
        v66 = (_QWORD *)(*v10 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v66 = 0;
      DirEntry = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(*(_QWORD *)*v66 + 72LL))(*v66, v69, 1);
      if ( DirEntry >= 0 )
        *((_QWORD *)a2 + 4) = v71;
    }
    if ( DirEntry < 0 )
      return (unsigned int)DirEntry;
  }
  else
  {
    if ( *(_DWORD *)v8 != 1279673431 )
      return (unsigned int)-2147287039;
    *((_QWORD *)a2 + 4) = *(_QWORD *)(v8 + 184);
  }
  v20 = *((_QWORD *)this + 15);
  if ( v20 )
    v21 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v20;
  else
    v21 = 0;
  if ( *(_DWORD *)v21 == 1279673411 )
  {
    v22 = *(_QWORD *)(v21 + 32);
    if ( v22 )
      v23 = (_QWORD *)(v22 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v23 = 0;
    v24 = *(_DWORD *)(v21 + 40);
    if ( v24 )
    {
      v25 = (unsigned int *)(v23 + 67);
      v68[0] = 0;
      DirEntry = CDirectory::GetDirEntry((CDirectory *)v25, v24, 0, v68);
      if ( DirEntry >= 0 )
      {
        *((_QWORD *)a2 + 3) = *(_QWORD *)((char *)v68[0] + 108);
        v26 = *((_QWORD *)v25 + 2);
        v27 = v24 / *((unsigned __int16 *)v25 + 36);
        v28 = v24 / *((unsigned __int16 *)v25 + 36);
        if ( v26
          && v26 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
          && (v29 = *(_QWORD *)(8 * v27 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v26)) != 0
          && v29 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
        {
          v30 = *(_QWORD *)(8 * v27 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v26);
          if ( v30 )
            v31 = v30 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v31 = 0;
          --*(_DWORD *)(v31 + 40);
        }
        else
        {
          if ( *(_QWORD *)v25 )
            v62 = (CMSFPageTable *)(*(_QWORD *)v25 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
          else
            v62 = 0;
          v63 = v25[8];
          v68[0] = 0;
          if ( (int)CMSFPageTable::FindPage(v62, (struct CPagedVector *)v25, v63, v28, v68) >= 0 )
            --*((_DWORD *)v68[0] + 10);
        }
      }
    }
    else
    {
      memset_0(v69, 0, 0x50u);
      if ( *v23 )
        v67 = (_QWORD *)(*v23 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
      else
        v67 = 0;
      DirEntry = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(*(_QWORD *)*v67 + 72LL))(*v67, v69, 1);
      if ( DirEntry >= 0 )
        *((_QWORD *)a2 + 3) = v70;
    }
    if ( DirEntry < 0 )
      return (unsigned int)DirEntry;
  }
  else
  {
    if ( *(_DWORD *)v21 != 1279673431 )
      return (unsigned int)-2147287039;
    *((_QWORD *)a2 + 3) = *(_QWORD *)(v21 + 192);
  }
  *((_QWORD *)a2 + 5) = 0;
  v32 = *((_QWORD *)this + 15);
  if ( v32 )
    v33 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v32;
  else
    v33 = 0;
  if ( *(_DWORD *)v33 == 1279673411 )
  {
    v34 = *(_QWORD *)(v33 + 32);
    if ( v34 )
      v35 = v34 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    else
      v35 = 0;
    v36 = *(_DWORD *)(v33 + 40);
    v37 = v35 + 536;
    v68[0] = 0;
    DirEntry = CDirectory::GetDirEntry((CDirectory *)(v35 + 536), v36, 0, v68);
    if ( DirEntry >= 0 )
    {
      *(_OWORD *)((char *)a2 + 56) = *((_OWORD *)v68[0] + 5);
      v38 = *(_QWORD *)(v37 + 16);
      v39 = v36 / *(unsigned __int16 *)(v37 + 72);
      v40 = v36 / *(unsigned __int16 *)(v37 + 72);
      if ( v38
        && v38 + *(_QWORD *)NtCurrentTeb()->ReservedForOle
        && (v41 = *(_QWORD *)(8 * v39 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v38)) != 0
        && v41 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
      {
        v42 = *(_QWORD *)(8 * v39 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v38);
        if ( v42 )
          v43 = v42 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
        else
          v43 = 0;
        --*(_DWORD *)(v43 + 40);
      }
      else
      {
        if ( *(_QWORD *)v37 )
          v58 = (CMSFPageTable *)(*(_QWORD *)v37 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
        else
          v58 = 0;
        v59 = *(_DWORD *)(v37 + 32);
        v68[0] = 0;
        if ( (int)CMSFPageTable::FindPage(v58, (struct CPagedVector *)v37, v59, v40, v68) >= 0 )
          --*((_DWORD *)v68[0] + 10);
      }
    }
    if ( DirEntry < 0 )
      return (unsigned int)DirEntry;
  }
  else
  {
    if ( *(_DWORD *)v33 != 1279673431 )
      return (unsigned int)-2147287039;
    *(_OWORD *)((char *)a2 + 56) = *(_OWORD *)(v33 + 216);
  }
  v44 = *((_QWORD *)this + 15);
  if ( v44 )
    v45 = *(_QWORD *)NtCurrentTeb()->ReservedForOle + v44;
  else
    v45 = 0;
  if ( *(_DWORD *)v45 != 1279673411 )
  {
    if ( *(_DWORD *)v45 == 1279673431 )
    {
      DirEntry = 0;
      *((_DWORD *)a2 + 18) = *(_DWORD *)(v45 + 232);
      goto LABEL_64;
    }
    return (unsigned int)-2147287039;
  }
  v46 = *(_QWORD *)(v45 + 32);
  if ( v46 )
    v47 = v46 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
  else
    v47 = 0;
  v48 = *(_DWORD *)(v45 + 40);
  v49 = v47 + 536;
  v68[0] = 0;
  DirEntry = CDirectory::GetDirEntry((CDirectory *)v49, v48, 0, v68);
  if ( DirEntry < 0 )
    goto LABEL_63;
  *((_DWORD *)a2 + 18) = *((_DWORD *)v68[0] + 24);
  v50 = *(_QWORD *)(v49 + 16);
  v51 = v48 / *(unsigned __int16 *)(v49 + 72);
  v52 = v48 / *(unsigned __int16 *)(v49 + 72);
  if ( v50 )
  {
    if ( v50 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
    {
      v53 = *(_QWORD *)(8 * v51 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v50);
      if ( v53 )
      {
        if ( v53 + *(_QWORD *)NtCurrentTeb()->ReservedForOle )
        {
          v54 = *(_QWORD *)(8 * v51 + *(_QWORD *)NtCurrentTeb()->ReservedForOle + v50);
          if ( v54 )
            v55 = v54 + *(_QWORD *)NtCurrentTeb()->ReservedForOle;
          else
            v55 = 0;
          --*(_DWORD *)(v55 + 40);
          goto LABEL_64;
        }
      }
    }
  }
  v64 = *(_QWORD *)v49 ? (CMSFPageTable *)(*(_QWORD *)v49 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
  v65 = *(_DWORD *)(v49 + 32);
  v68[0] = 0;
  if ( (int)CMSFPageTable::FindPage(v64, (struct CPagedVector *)v49, v65, v52, v68) < 0 )
  {
LABEL_63:
    if ( DirEntry < 0 )
      return (unsigned int)DirEntry;
    goto LABEL_64;
  }
  --*((_DWORD *)v68[0] + 10);
LABEL_64:
  if ( (a3 & 1) == 0 )
  {
    v57 = CoTaskMemAlloc(*((unsigned __int16 *)this + 44));
    *(_QWORD *)a2 = v57;
    if ( !v57 )
      return (unsigned int)-2147287032;
    memcpy_0(v57, (char *)this + 24, *((unsigned __int16 *)this + 44));
  }
  *((_DWORD *)a2 + 12) = DFlagsToMode(*((_DWORD *)this + 5));
  return (unsigned int)DirEntry;
}

```

## disassembly

```asm
0x1800146d0  push    rbp
0x1800146d2  push    rdi
0x1800146d3  push    r12
0x1800146d5  push    r14
0x1800146d7  lea     rbp, [rsp-3Fh]
0x1800146dc  sub     rsp, 0B8h
0x1800146e3  mov     rax, cs:__security_cookie
0x1800146ea  xor     rax, rsp
0x1800146ed  mov     [rbp+57h+var_40], rax
0x1800146f1  mov     rax, [rcx]
0x1800146f4  mov     r12d, r8d
0x1800146f7  sub     rax, qword ptr cs:_GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data1
0x1800146fe  mov     r14, rdx
0x180014701  mov     rdi, rcx
0x180014704  jnz     short loc_180014711
0x180014706  mov     rax, [rcx+8]
0x18001470a  sub     rax, qword ptr cs:_GUID_33c83c10_d239_4c83_98b3_9f2621c2df7f.Data4
0x180014711  test    rax, rax
0x180014714  jz      loc_180014C7B
0x18001471a  test    byte ptr [rcx+14h], 20h
0x18001471e  mov     [rsp+0D0h+arg_18], rbx
0x180014726  mov     [rsp+0D0h+var_20], rsi
0x18001472e  mov     [rsp+0D0h+var_28], r13
0x180014736  mov     [rsp+0D0h+var_30], r15
0x18001473e  jnz     loc_180015010
0x180014744  xor     r13d, r13d
0x180014747  mov     [rdx], r13
0x18001474a  mov     rdx, [rcx+78h]
0x18001474e  test    rdx, rdx
0x180014751  jz      loc_180014ED7
0x180014757  mov     rax, gs:30h
0x180014760  mov     rcx, [rax+1758h]
0x180014767  mov     r8, [rcx]
0x18001476a  add     r8, rdx
0x18001476d  mov     eax, [r8]
0x180014770  cmp     eax, 4C464443h
0x180014775  jnz     loc_180014E99
0x18001477b  mov     rdx, [r8+20h]
0x18001477f  test    rdx, rdx
0x180014782  jz      loc_180014E5D
0x180014788  mov     rax, gs:30h
0x180014791  mov     rcx, [rax+1758h]
0x180014798  mov     r15, [rcx]
0x18001479b  add     r15, rdx
0x18001479e  mov     esi, [r8+28h]
0x1800147a2  test    esi, esi
0x1800147a4  jz      loc_180014F34
0x1800147aa  add     r15, 218h
0x1800147b1  mov     [rbp+57h+var_A0], r13
0x1800147b5  mov     rcx, r15; this
0x1800147b8  lea     r9, [rbp+57h+var_A0]; struct CDirEntry **
0x1800147bc  xor     r8d, r8d; unsigned int
0x1800147bf  mov     edx, esi; unsigned int
0x1800147c1  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x1800147c6  mov     ebx, eax
0x1800147c8  test    eax, eax
0x1800147ca  js      loc_180014896
0x1800147d0  mov     rcx, [rbp+57h+var_A0]
0x1800147d4  mov     eax, esi
0x1800147d6  mov     rdx, [rcx+64h]
0x1800147da  mov     [r14+20h], rdx
0x1800147de  xor     edx, edx
0x1800147e0  movzx   ecx, word ptr [r15+48h]
0x1800147e5  mov     r8, [r15+10h]
0x1800147e9  div     ecx
0x1800147eb  mov     r10d, eax
0x1800147ee  test    r8, r8
0x1800147f1  jz      loc_180014D4F
0x1800147f7  mov     rcx, gs:30h
0x180014800  mov     rdx, [rcx+1758h]
0x180014807  mov     rcx, [rdx]
0x18001480a  add     rcx, r8
0x18001480d  jz      loc_180014D4F
0x180014813  mov     rcx, gs:30h
0x18001481c  lea     r9, ds:0[rax*8]
0x180014824  mov     rdx, [rcx+1758h]
0x18001482b  mov     rcx, [rdx]
0x18001482e  add     rcx, r9
0x180014831  mov     rdx, [rcx+r8]
0x180014835  test    rdx, rdx
0x180014838  jz      loc_180014D4F
0x18001483e  mov     rax, gs:30h
0x180014847  mov     rcx, [rax+1758h]
0x18001484e  mov     rax, [rcx]
0x180014851  add     rax, rdx
0x180014854  jz      loc_180014D4F
0x18001485a  mov     rax, gs:30h
0x180014863  mov     rcx, [rax+1758h]
0x18001486a  mov     rcx, [rcx]
0x18001486d  add     rcx, r9
0x180014870  mov     rdx, [rcx+r8]
0x180014874  test    rdx, rdx
0x180014877  jz      loc_180014E4D
0x18001487d  mov     rax, gs:30h
0x180014886  mov     rcx, [rax+1758h]
0x18001488d  mov     rcx, [rcx]
0x180014890  add     rcx, rdx
0x180014893  dec     dword ptr [rcx+28h]
0x180014896  test    ebx, ebx
0x180014898  js      loc_180014C98
0x18001489e  mov     rdx, [rdi+78h]
0x1800148a2  test    rdx, rdx
0x1800148a5  jz      loc_180014EDF
0x1800148ab  mov     rax, gs:30h
0x1800148b4  mov     rcx, [rax+1758h]
0x1800148bb  add     rdx, [rcx]
0x1800148be  mov     eax, [rdx]
0x1800148c0  cmp     eax, 4C464443h
0x1800148c5  jnz     loc_180014EB4
0x1800148cb  mov     r8, [rdx+20h]
0x1800148cf  test    r8, r8
0x1800148d2  jz      loc_180014E65
0x1800148d8  mov     rax, gs:30h
0x1800148e1  mov     rcx, [rax+1758h]
0x1800148e8  mov     r15, [rcx]
0x1800148eb  add     r15, r8
0x1800148ee  mov     esi, [rdx+28h]
0x1800148f1  test    esi, esi
0x1800148f3  jz      loc_180014F98
0x1800148f9  add     r15, 218h
0x180014900  mov     [rbp+57h+var_A0], r13
0x180014904  mov     rcx, r15; this
0x180014907  lea     r9, [rbp+57h+var_A0]; struct CDirEntry **
0x18001490b  xor     r8d, r8d; unsigned int
0x18001490e  mov     edx, esi; unsigned int
0x180014910  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x180014915  mov     ebx, eax
0x180014917  test    eax, eax
0x180014919  js      loc_1800149E5
0x18001491f  mov     rcx, [rbp+57h+var_A0]
0x180014923  mov     eax, esi
0x180014925  mov     rdx, [rcx+6Ch]
0x180014929  mov     [r14+18h], rdx
0x18001492d  xor     edx, edx
0x18001492f  movzx   ecx, word ptr [r15+48h]
0x180014934  mov     r8, [r15+10h]
0x180014938  div     ecx
0x18001493a  mov     r10d, eax
0x18001493d  test    r8, r8
0x180014940  jz      loc_180014DA1
0x180014946  mov     rcx, gs:30h
0x18001494f  mov     rdx, [rcx+1758h]
0x180014956  mov     rcx, [rdx]
0x180014959  add     rcx, r8
0x18001495c  jz      loc_180014DA1
0x180014962  mov     rcx, gs:30h
0x18001496b  lea     r9, ds:0[rax*8]
0x180014973  mov     rdx, [rcx+1758h]
0x18001497a  mov     rcx, [rdx]
0x18001497d  add     rcx, r9
0x180014980  mov     rdx, [rcx+r8]
0x180014984  test    rdx, rdx
0x180014987  jz      loc_180014DA1
0x18001498d  mov     rax, gs:30h
0x180014996  mov     rcx, [rax+1758h]
0x18001499d  mov     rax, [rcx]
0x1800149a0  add     rax, rdx
0x1800149a3  jz      loc_180014DA1
0x1800149a9  mov     rax, gs:30h
0x1800149b2  mov     rcx, [rax+1758h]
0x1800149b9  mov     rcx, [rcx]
0x1800149bc  add     rcx, r9
0x1800149bf  mov     rdx, [rcx+r8]
0x1800149c3  test    rdx, rdx
0x1800149c6  jz      loc_180014E55
0x1800149cc  mov     rax, gs:30h
0x1800149d5  mov     rcx, [rax+1758h]
0x1800149dc  mov     rcx, [rcx]
0x1800149df  add     rcx, rdx
0x1800149e2  dec     dword ptr [rcx+28h]
0x1800149e5  test    ebx, ebx
0x1800149e7  js      loc_180014C98
0x1800149ed  mov     [r14+28h], r13
0x1800149f1  mov     rdx, [rdi+78h]
0x1800149f5  test    rdx, rdx
0x1800149f8  jz      loc_180014F04
0x1800149fe  mov     rax, gs:30h
0x180014a07  mov     rcx, [rax+1758h]
0x180014a0e  add     rdx, [rcx]
0x180014a11  mov     eax, [rdx]
0x180014a13  cmp     eax, 4C464443h
0x180014a18  jnz     loc_180014E6D
0x180014a1e  mov     r8, [rdx+20h]
0x180014a22  test    r8, r8
0x180014a25  jz      loc_180014E91
0x180014a2b  mov     rax, gs:30h
0x180014a34  mov     rcx, [rax+1758h]
0x180014a3b  mov     rcx, [rcx]
0x180014a3e  add     rcx, r8
0x180014a41  mov     esi, [rdx+28h]
0x180014a44  lea     r15, [rcx+218h]
0x180014a4b  mov     rcx, r15; this
0x180014a4e  mov     [rbp+57h+var_A0], r13
0x180014a52  lea     r9, [rbp+57h+var_A0]; struct CDirEntry **
0x180014a56  xor     r8d, r8d; unsigned int
0x180014a59  mov     edx, esi; unsigned int
0x180014a5b  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x180014a60  mov     ebx, eax
0x180014a62  test    eax, eax
0x180014a64  js      loc_180014B31
0x180014a6a  mov     rcx, [rbp+57h+var_A0]
0x180014a6e  xor     edx, edx
0x180014a70  mov     eax, esi
0x180014a72  movups  xmm0, xmmword ptr [rcx+50h]
0x180014a76  movups  xmmword ptr [r14+38h], xmm0
0x180014a7b  movzx   ecx, word ptr [r15+48h]
0x180014a80  mov     r8, [r15+10h]
0x180014a84  div     ecx
0x180014a86  mov     r10d, eax
0x180014a89  test    r8, r8
0x180014a8c  jz      loc_180014CFD
0x180014a92  mov     rcx, gs:30h
0x180014a9b  mov     rdx, [rcx+1758h]
0x180014aa2  mov     rcx, [rdx]
0x180014aa5  add     rcx, r8
0x180014aa8  jz      loc_180014CFD
0x180014aae  mov     rcx, gs:30h
0x180014ab7  lea     r9, ds:0[rax*8]
0x180014abf  mov     rdx, [rcx+1758h]
0x180014ac6  mov     rcx, [rdx]
0x180014ac9  add     rcx, r9
0x180014acc  mov     rdx, [rcx+r8]
0x180014ad0  test    rdx, rdx
0x180014ad3  jz      loc_180014CFD
0x180014ad9  mov     rax, gs:30h
0x180014ae2  mov     rcx, [rax+1758h]
0x180014ae9  mov     rax, [rcx]
0x180014aec  add     rax, rdx
0x180014aef  jz      loc_180014CFD
0x180014af5  mov     rax, gs:30h
0x180014afe  mov     rcx, [rax+1758h]
0x180014b05  mov     rcx, [rcx]
0x180014b08  add     rcx, r9
0x180014b0b  mov     rdx, [rcx+r8]
0x180014b0f  test    rdx, rdx
0x180014b12  jz      loc_180014E45
0x180014b18  mov     rax, gs:30h
0x180014b21  mov     rcx, [rax+1758h]
0x180014b28  mov     rcx, [rcx]
0x180014b2b  add     rcx, rdx
0x180014b2e  dec     dword ptr [rcx+28h]
0x180014b31  test    ebx, ebx
0x180014b33  js      loc_180014C98
0x180014b39  mov     rdx, [rdi+78h]
0x180014b3d  test    rdx, rdx
0x180014b40  jz      loc_180014F0C
0x180014b46  mov     rax, gs:30h
0x180014b4f  mov     rcx, [rax+1758h]
0x180014b56  add     rdx, [rcx]
0x180014b59  mov     eax, [rdx]
0x180014b5b  cmp     eax, 4C464443h
0x180014b60  jnz     loc_180014EE7
0x180014b66  mov     r8, [rdx+20h]
0x180014b6a  test    r8, r8
0x180014b6d  jz      loc_180014ECF
0x180014b73  mov     rax, gs:30h
0x180014b7c  mov     rcx, [rax+1758h]
0x180014b83  mov     rsi, [rcx]
0x180014b86  add     rsi, r8
0x180014b89  mov     r15d, [rdx+28h]
0x180014b8d  lea     r9, [rbp+57h+var_A0]; struct CDirEntry **
0x180014b91  add     rsi, 218h
0x180014b98  mov     [rbp+57h+var_A0], r13
0x180014b9c  mov     rcx, rsi; this
0x180014b9f  xor     r8d, r8d; unsigned int
0x180014ba2  mov     edx, r15d; unsigned int
0x180014ba5  call    ?GetDirEntry@CDirectory@@QEAAJKKPEAPEAVCDirEntry@@@Z; CDirectory::GetDirEntry(ulong,ulong,CDirEntry * *)
0x180014baa  mov     ebx, eax
0x180014bac  test    eax, eax
0x180014bae  js      loc_180014C82
0x180014bb4  mov     rcx, [rbp+57h+var_A0]
0x180014bb8  mov     eax, r15d
0x180014bbb  mov     edx, [rcx+60h]
0x180014bbe  mov     [r14+48h], edx
0x180014bc2  xor     edx, edx
0x180014bc4  movzx   ecx, word ptr [rsi+48h]
0x180014bc8  mov     r8, [rsi+10h]; unsigned int
0x180014bcc  div     ecx
0x180014bce  mov     r10d, eax
0x180014bd1  test    r8, r8
0x180014bd4  jz      loc_180014DF3
0x180014bda  mov     rcx, gs:30h
0x180014be3  mov     rdx, [rcx+1758h]
0x180014bea  mov     rcx, [rdx]
0x180014bed  add     rcx, r8
0x180014bf0  jz      loc_180014DF3
0x180014bf6  mov     rcx, gs:30h
0x180014bff  lea     r9, ds:0[rax*8]
0x180014c07  mov     rdx, [rcx+1758h]
0x180014c0e  mov     rcx, [rdx]
0x180014c11  add     rcx, r9
0x180014c14  mov     rdx, [rcx+r8]
0x180014c18  test    rdx, rdx
0x180014c1b  jz      loc_180014DF3
0x180014c21  mov     rax, gs:30h
0x180014c2a  mov     rcx, [rax+1758h]
0x180014c31  mov     rax, [rcx]
0x180014c34  add     rax, rdx
0x180014c37  jz      loc_180014DF3
0x180014c3d  mov     rax, gs:30h
  ... truncated ...
```
