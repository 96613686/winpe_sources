# TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(TableMeta const *,bool,TMetabaseMetaXmlFile::TSizedString const *)

- ea: `0x18001aac4`
- end: `0x18001b00d`
- name: `?AddShippedTableMetaToHeap@TMetabaseMetaXmlFile@@AEAAXPEBUTableMeta@@_NPEBUTSizedString@1@@Z`
- size: `1353`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, const struct TableMeta *, bool, const struct TMetabaseMetaXmlFile::TSizedString *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180017e84`
- `0x18001c240`

## callees

- `0x180019f9c`
- `0x18001a2e0`
- `0x18001a444`
- `0x18001a914`
- `0x18001aac4`
- `0x18002e110`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddShippedTableMetaToHeap(
        TMetabaseMetaXmlFile *this,
        const struct TableMeta *a2,
        char a3,
        const struct TMetabaseMetaXmlFile::TSizedString *a4)
{
  __int64 v4; // rax
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  __int64 v19; // r8
  unsigned int *v20; // rdx
  unsigned int *v21; // rdx
  unsigned int *v22; // rdx
  unsigned int *v23; // rdx
  __int64 v24; // rax
  unsigned int *v25; // rdx
  unsigned __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  __int64 v29; // r8
  const unsigned __int16 *v30; // r8
  unsigned int v31; // r9d
  _DWORD *v32; // r8
  unsigned __int64 v33; // rdx
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rax
  unsigned int v38; // eax
  unsigned int v39; // edx
  const struct ColumnMeta *i; // rsi
  __int64 v41; // rdx
  _DWORD *v42; // rcx
  unsigned int v43; // r14d
  const struct IndexMeta *j; // rsi
  bool v45; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v46[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v47; // [rsp+48h] [rbp-41h]
  __int64 v48; // [rsp+50h] [rbp-39h]
  __int64 v49; // [rsp+58h] [rbp-31h]
  __int64 v50; // [rsp+60h] [rbp-29h]
  __int64 v51; // [rsp+68h] [rbp-21h]
  __int64 v52; // [rsp+70h] [rbp-19h]
  __int64 v53; // [rsp+78h] [rbp-11h]
  _QWORD v54[6]; // [rsp+80h] [rbp-9h] BYREF

  v4 = *(_QWORD *)this;
  *(_QWORD *)v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  memset(v54, 0, 44);
  if ( *(_DWORD *)a2 )
  {
    v9 = *((_QWORD *)this + 323)
       + *(unsigned int *)a2
       + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v10 = *(_DWORD *)(v9 - 4) >> 1;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  v11 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(v4 + 40))(this, v9, v10);
  *((_DWORD *)this + 635) = v11;
  v46[0] = v11;
  if ( *((_DWORD *)a2 + 1) )
  {
    v12 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 1)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v13 = *(_DWORD *)(v12 - 4) >> 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  v14 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
          this,
          v12,
          v13);
  v15 = *((unsigned int *)a2 + 2);
  v46[1] = v14;
  if ( (_DWORD)v15 != *((_DWORD *)a2 + 1) )
  {
    if ( (_DWORD)v15 )
    {
      v16 = *((_QWORD *)this + 323) + v15 + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
      v17 = *(_DWORD *)(v16 - 4) >> 1;
    }
    else
    {
      v16 = 0;
      v17 = 0;
    }
    v14 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v16, v17);
  }
  LODWORD(v47) = v14;
  if ( *((_DWORD *)a2 + 3) )
  {
    v18 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 3)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v19 = *(_DWORD *)(v18 - 4) >> 1;
  }
  else
  {
    v18 = 0;
    v19 = 0;
  }
  HIDWORD(v47) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
                   this,
                   v18,
                   v19);
  if ( *((_DWORD *)a2 + 4) )
    v20 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a2 + 4));
  else
    v20 = 0;
  LODWORD(v48) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v20);
  if ( *((_DWORD *)a2 + 5) )
    v21 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a2 + 5));
  else
    v21 = 0;
  HIDWORD(v48) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v21);
  if ( *((_DWORD *)a2 + 6) )
    v22 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a2 + 6));
  else
    v22 = 0;
  LODWORD(v49) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v22);
  if ( *((_DWORD *)a2 + 7) )
    v23 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a2 + 7));
  else
    v23 = 0;
  HIDWORD(v49) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v23);
  v24 = *(_QWORD *)this;
  LODWORD(v50) = 0;
  if ( *((_DWORD *)a2 + 9) )
    v25 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a2 + 9));
  else
    v25 = 0;
  HIDWORD(v50) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(v24 + 16))(this, *v25);
  if ( *((_DWORD *)a2 + 11) )
  {
    v26 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 11)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v27 = *(_DWORD *)(v26 - 4) >> 1;
  }
  else
  {
    v26 = 0;
    v27 = 0;
  }
  HIDWORD(v51) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
                   this,
                   v26,
                   v27);
  if ( *((_DWORD *)a2 + 12) )
  {
    v28 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 12)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v29 = *(_DWORD *)(v28 - 4) >> 1;
  }
  else
  {
    v28 = 0;
    v29 = 0;
  }
  v52 = (*(unsigned int (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
          this,
          v28,
          v29);
  v45 = 0;
  if ( *((_DWORD *)a2 + 14) )
  {
    v30 = (const unsigned __int16 *)(*((_QWORD *)this + 323)
                                   + *((unsigned int *)a2 + 14)
                                   + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL));
    v31 = *((_DWORD *)v30 - 1) >> 1;
  }
  else
  {
    v30 = 0;
    v31 = 0;
  }
  LODWORD(v53) = TMetabaseMetaXmlFile::AddMergedContainerClassListToList(this, a4, v30, v31, &v45);
  if ( *((_DWORD *)a2 + 10) )
    v32 = (_DWORD *)(*((_QWORD *)this + 323)
                   + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                   + *((unsigned int *)a2 + 10));
  else
    v32 = 0;
  LODWORD(v51) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(
                   this,
                   *v32 | (v45 ? 0x100 : 0));
  if ( *((_DWORD *)a2 + 15) )
  {
    v33 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 15)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v34 = *(_DWORD *)(v33 - 4) >> 1;
  }
  else
  {
    v33 = 0;
    v34 = 0;
  }
  HIDWORD(v53) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
                   this,
                   v33,
                   v34);
  if ( *((_DWORD *)a2 + 16) )
  {
    v35 = *((_QWORD *)this + 323)
        + *((unsigned int *)a2 + 16)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v36 = *(_DWORD *)(v35 - 4) >> 1;
  }
  else
  {
    v35 = 0;
    v36 = 0;
  }
  LODWORD(v54[0]) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned __int64, __int64))(*(_QWORD *)this + 40LL))(
                      this,
                      v35,
                      v36);
  v37 = *(_QWORD *)this;
  memset((char *)v54 + 4, 0, 40);
  v38 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned int *, __int64))(v37 + 112))(this, v46, 1);
  *((_DWORD *)this + 643) = 0;
  *((_DWORD *)this + 637) = v38 / 0x6C;
  *((_DWORD *)this + 639) = v38 / 0x6C;
  v39 = v46[1];
  *((_DWORD *)this + 636) = v46[1];
  TMetabaseMetaXmlFile::AddServerWiringMetaToHeap(this, v39, a3);
  for ( i = (const struct ColumnMeta *)(*((_QWORD *)this + 323)
                                      + 84LL * *((unsigned int *)a2 + 18)
                                      + *(unsigned int *)(*((_QWORD *)this + 323) + 24LL));
        ;
        i = (const struct ColumnMeta *)((char *)i + 84) )
  {
    v41 = *((_QWORD *)this + 323);
    v42 = *((_DWORD *)a2 + 8) ? (_DWORD *)(v41 + *(unsigned int *)(v41 + 56) + *((unsigned int *)a2 + 8)) : 0LL;
    if ( *((_DWORD *)this + 643) >= *v42 )
      break;
    TMetabaseMetaXmlFile::AddShippedColumnMetaToHeap(this, v46[1], i);
  }
  if ( a3 )
  {
    if ( *((_DWORD *)a2 + 22) != -1 )
    {
      v43 = 0;
      for ( j = (const struct IndexMeta *)(v41 + 28LL * *((unsigned int *)a2 + 22) + *(unsigned int *)(v41 + 48));
            v43 < *((_DWORD *)a2 + 21);
            j = (const struct IndexMeta *)((char *)j + 28) )
      {
        TMetabaseMetaXmlFile::AddShippedIndexMetaToHeap(this, v46[1], j);
        ++v43;
      }
    }
  }
}

```

## disassembly

```asm
0x18001aac4  mov     [rsp-8+arg_10], rbx
0x18001aac9  push    rbp
0x18001aaca  push    rsi
0x18001aacb  push    rdi
0x18001aacc  push    r14
0x18001aace  push    r15
0x18001aad0  lea     rbp, [rsp-37h]
0x18001aad5  sub     rsp, 0C0h
0x18001aadc  mov     rax, cs:__security_cookie
0x18001aae3  xor     rax, rsp
0x18001aae6  mov     [rbp+57h+var_30], rax
0x18001aaea  mov     rax, [rcx]
0x18001aaed  xor     r15d, r15d
0x18001aaf0  mov     rsi, r9
0x18001aaf3  mov     r14b, r8b
0x18001aaf6  mov     rdi, rdx
0x18001aaf9  mov     rbx, rcx
0x18001aafc  mov     qword ptr [rbp+57h+var_A0], r15
0x18001ab00  mov     [rbp+57h+var_98], r15
0x18001ab04  mov     [rbp+57h+var_90], r15
0x18001ab08  mov     [rbp+57h+var_88], r15
0x18001ab0c  mov     [rbp+57h+var_80], r15
0x18001ab10  mov     [rbp+57h+var_78], r15
0x18001ab14  mov     [rbp+57h+var_70], r15
0x18001ab18  mov     [rbp+57h+var_68], r15
0x18001ab1c  mov     [rbp+57h+var_60], r15
0x18001ab20  mov     [rbp-1], r15
0x18001ab24  mov     [rbp+57h+var_50], r15
0x18001ab28  mov     [rbp+0Fh], r15
0x18001ab2c  mov     [rbp+57h+var_40], r15
0x18001ab30  mov     [rbp+57h+var_38], r15d
0x18001ab34  cmp     [rdx], r15d
0x18001ab37  jnz     short loc_18001AB41
0x18001ab39  mov     edx, r15d
0x18001ab3c  mov     r8d, r15d
0x18001ab3f  jmp     short loc_18001AB64
0x18001ab41  mov     r9, [rcx+0A18h]
0x18001ab48  mov     r8d, [rdx]
0x18001ab4b  mov     ecx, [r9+38h]
0x18001ab4f  mov     edx, [r9+38h]
0x18001ab53  add     rcx, r8
0x18001ab56  add     rdx, r8
0x18001ab59  add     rdx, r9
0x18001ab5c  mov     r8d, [rcx+r9-4]
0x18001ab61  shr     r8d, 1
0x18001ab64  mov     rax, [rax+28h]
0x18001ab68  mov     rcx, rbx
0x18001ab6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab70  mov     [rbx+9ECh], eax
0x18001ab76  mov     [rbp+57h+var_A0], eax
0x18001ab79  mov     rax, [rbx]
0x18001ab7c  cmp     [rdi+4], r15d
0x18001ab80  jnz     short loc_18001AB8A
0x18001ab82  mov     rdx, r15
0x18001ab85  mov     r8d, r15d
0x18001ab88  jmp     short loc_18001ABAE
0x18001ab8a  mov     r9, [rbx+0A18h]
0x18001ab91  mov     r8d, [rdi+4]
0x18001ab95  mov     ecx, [r9+38h]
0x18001ab99  mov     edx, [r9+38h]
0x18001ab9d  add     rcx, r8
0x18001aba0  add     rdx, r8
0x18001aba3  add     rdx, r9
0x18001aba6  mov     r8d, [rcx+r9-4]
0x18001abab  shr     r8d, 1
0x18001abae  mov     rax, [rax+28h]
0x18001abb2  mov     rcx, rbx
0x18001abb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abba  mov     ecx, [rdi+8]
0x18001abbd  mov     [rbp+57h+var_A0+4], eax
0x18001abc0  cmp     ecx, [rdi+4]
0x18001abc3  jz      short loc_18001AC03
0x18001abc5  mov     rax, [rbx]
0x18001abc8  test    ecx, ecx
0x18001abca  jnz     short loc_18001ABD4
0x18001abcc  mov     rdx, r15
0x18001abcf  mov     r8d, r15d
0x18001abd2  jmp     short loc_18001ABF7
0x18001abd4  mov     r9, [rbx+0A18h]
0x18001abdb  mov     r8, rcx
0x18001abde  mov     edx, [r9+38h]
0x18001abe2  add     rdx, rcx
0x18001abe5  mov     ecx, [r9+38h]
0x18001abe9  add     rcx, r8
0x18001abec  add     rdx, r9
0x18001abef  mov     r8d, [rcx+r9-4]
0x18001abf4  shr     r8d, 1
0x18001abf7  mov     rax, [rax+28h]
0x18001abfb  mov     rcx, rbx
0x18001abfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac03  mov     dword ptr [rbp+57h+var_98], eax
0x18001ac06  mov     rax, [rbx]
0x18001ac09  cmp     [rdi+0Ch], r15d
0x18001ac0d  jnz     short loc_18001AC17
0x18001ac0f  mov     rdx, r15
0x18001ac12  mov     r8d, r15d
0x18001ac15  jmp     short loc_18001AC3B
0x18001ac17  mov     r9, [rbx+0A18h]
0x18001ac1e  mov     r8d, [rdi+0Ch]
0x18001ac22  mov     ecx, [r9+38h]
0x18001ac26  mov     edx, [r9+38h]
0x18001ac2a  add     rcx, r8
0x18001ac2d  add     rdx, r8
0x18001ac30  add     rdx, r9
0x18001ac33  mov     r8d, [rcx+r9-4]
0x18001ac38  shr     r8d, 1
0x18001ac3b  mov     rax, [rax+28h]
0x18001ac3f  mov     rcx, rbx
0x18001ac42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac47  mov     dword ptr [rbp+57h+var_98+4], eax
0x18001ac4a  mov     rax, [rbx]
0x18001ac4d  cmp     [rdi+10h], r15d
0x18001ac51  jnz     short loc_18001AC58
0x18001ac53  mov     rdx, r15
0x18001ac56  jmp     short loc_18001AC6C
0x18001ac58  mov     r8, [rbx+0A18h]
0x18001ac5f  mov     edx, [rdi+10h]
0x18001ac62  mov     ecx, [r8+38h]
0x18001ac66  add     rcx, r8
0x18001ac69  add     rdx, rcx
0x18001ac6c  mov     edx, [rdx]
0x18001ac6e  mov     rcx, rbx
0x18001ac71  mov     rax, [rax+10h]
0x18001ac75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac7a  mov     dword ptr [rbp+57h+var_90], eax
0x18001ac7d  mov     rax, [rbx]
0x18001ac80  cmp     [rdi+14h], r15d
0x18001ac84  jnz     short loc_18001AC8B
0x18001ac86  mov     rdx, r15
0x18001ac89  jmp     short loc_18001AC9F
0x18001ac8b  mov     r8, [rbx+0A18h]
0x18001ac92  mov     edx, [rdi+14h]
0x18001ac95  mov     ecx, [r8+38h]
0x18001ac99  add     rcx, r8
0x18001ac9c  add     rdx, rcx
0x18001ac9f  mov     edx, [rdx]
0x18001aca1  mov     rcx, rbx
0x18001aca4  mov     rax, [rax+10h]
0x18001aca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acad  mov     dword ptr [rbp+57h+var_90+4], eax
0x18001acb0  mov     rax, [rbx]
0x18001acb3  cmp     [rdi+18h], r15d
0x18001acb7  jnz     short loc_18001ACBE
0x18001acb9  mov     rdx, r15
0x18001acbc  jmp     short loc_18001ACD2
0x18001acbe  mov     r8, [rbx+0A18h]
0x18001acc5  mov     edx, [rdi+18h]
0x18001acc8  mov     ecx, [r8+38h]
0x18001accc  add     rcx, r8
0x18001accf  add     rdx, rcx
0x18001acd2  mov     edx, [rdx]
0x18001acd4  mov     rcx, rbx
0x18001acd7  mov     rax, [rax+10h]
0x18001acdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ace0  mov     dword ptr [rbp+57h+var_88], eax
0x18001ace3  mov     rax, [rbx]
0x18001ace6  cmp     [rdi+1Ch], r15d
0x18001acea  jnz     short loc_18001ACF1
0x18001acec  mov     rdx, r15
0x18001acef  jmp     short loc_18001AD05
0x18001acf1  mov     r8, [rbx+0A18h]
0x18001acf8  mov     edx, [rdi+1Ch]
0x18001acfb  mov     ecx, [r8+38h]
0x18001acff  add     rcx, r8
0x18001ad02  add     rdx, rcx
0x18001ad05  mov     edx, [rdx]
0x18001ad07  mov     rcx, rbx
0x18001ad0a  mov     rax, [rax+10h]
0x18001ad0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad13  mov     dword ptr [rbp+57h+var_88+4], eax
0x18001ad16  mov     rax, [rbx]
0x18001ad19  mov     dword ptr [rbp+57h+var_80], r15d
0x18001ad1d  cmp     [rdi+24h], r15d
0x18001ad21  jnz     short loc_18001AD28
0x18001ad23  mov     rdx, r15
0x18001ad26  jmp     short loc_18001AD3C
0x18001ad28  mov     r8, [rbx+0A18h]
0x18001ad2f  mov     edx, [rdi+24h]
0x18001ad32  mov     ecx, [r8+38h]
0x18001ad36  add     rcx, r8
0x18001ad39  add     rdx, rcx
0x18001ad3c  mov     edx, [rdx]
0x18001ad3e  mov     rcx, rbx
0x18001ad41  mov     rax, [rax+10h]
0x18001ad45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad4a  mov     dword ptr [rbp+57h+var_80+4], eax
0x18001ad4d  mov     rax, [rbx]
0x18001ad50  cmp     [rdi+2Ch], r15d
0x18001ad54  jnz     short loc_18001AD5E
0x18001ad56  mov     rdx, r15
0x18001ad59  mov     r8d, r15d
0x18001ad5c  jmp     short loc_18001AD82
0x18001ad5e  mov     r9, [rbx+0A18h]
0x18001ad65  mov     r8d, [rdi+2Ch]
0x18001ad69  mov     ecx, [r9+38h]
0x18001ad6d  mov     edx, [r9+38h]
0x18001ad71  add     rcx, r8
0x18001ad74  add     rdx, r8
0x18001ad77  add     rdx, r9
0x18001ad7a  mov     r8d, [rcx+r9-4]
0x18001ad7f  shr     r8d, 1
0x18001ad82  mov     rax, [rax+28h]
0x18001ad86  mov     rcx, rbx
0x18001ad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad8e  mov     dword ptr [rbp+57h+var_78+4], eax
0x18001ad91  mov     rax, [rbx]
0x18001ad94  cmp     [rdi+30h], r15d
0x18001ad98  jnz     short loc_18001ADA2
0x18001ad9a  mov     rdx, r15
0x18001ad9d  mov     r8d, r15d
0x18001ada0  jmp     short loc_18001ADC6
0x18001ada2  mov     r9, [rbx+0A18h]
0x18001ada9  mov     r8d, [rdi+30h]
0x18001adad  mov     ecx, [r9+38h]
0x18001adb1  mov     edx, [r9+38h]
0x18001adb5  add     rcx, r8
0x18001adb8  add     rdx, r8
0x18001adbb  add     rdx, r9
0x18001adbe  mov     r8d, [rcx+r9-4]
0x18001adc3  shr     r8d, 1
0x18001adc6  mov     rax, [rax+28h]
0x18001adca  mov     rcx, rbx
0x18001adcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001add2  mov     dword ptr [rbp+57h+var_70], eax
0x18001add5  mov     dword ptr [rbp+57h+var_70+4], r15d
0x18001add9  mov     [rbp+57h+var_B0], r15b
0x18001addd  cmp     [rdi+38h], r15d
0x18001ade1  jnz     short loc_18001ADEB
0x18001ade3  mov     r8, r15
0x18001ade6  mov     r9d, r15d
0x18001ade9  jmp     short loc_18001AE0E
0x18001adeb  mov     r9, [rbx+0A18h]
0x18001adf2  mov     ecx, [rdi+38h]
0x18001adf5  mov     eax, [r9+38h]
0x18001adf9  mov     r8d, [r9+38h]
0x18001adfd  add     rax, rcx
0x18001ae00  add     r8, rcx
0x18001ae03  add     r8, r9; unsigned __int16 *
0x18001ae06  mov     r9d, [rax+r9-4]
0x18001ae0b  shr     r9d, 1; unsigned int
0x18001ae0e  lea     rax, [rbp+57h+var_B0]
0x18001ae12  mov     rdx, rsi; struct TMetabaseMetaXmlFile::TSizedString *
0x18001ae15  mov     rcx, rbx; this
0x18001ae18  mov     [rsp+0E0h+var_C0], rax; bool *
0x18001ae1d  call    ?AddMergedContainerClassListToList@TMetabaseMetaXmlFile@@AEAAKPEBUTSizedString@1@PEBGKAEA_N@Z; TMetabaseMetaXmlFile::AddMergedContainerClassListToList(TMetabaseMetaXmlFile::TSizedString const *,ushort const *,ulong,bool &)
0x18001ae22  mov     dword ptr [rbp+57h+var_68], eax
0x18001ae25  mov     rax, [rbx]
0x18001ae28  mov     r9, [rax+10h]
0x18001ae2c  cmp     [rdi+28h], r15d
0x18001ae30  jnz     short loc_18001AE37
0x18001ae32  mov     r8, r15
0x18001ae35  jmp     short loc_18001AE4B
0x18001ae37  mov     rcx, [rbx+0A18h]
0x18001ae3e  mov     r8d, [rdi+28h]
0x18001ae42  mov     eax, [rcx+38h]
0x18001ae45  add     rax, rcx
0x18001ae48  add     r8, rax
0x18001ae4b  mov     cl, [rbp+57h+var_B0]
0x18001ae4e  mov     rax, r9
0x18001ae51  neg     cl
0x18001ae53  mov     rcx, rbx
0x18001ae56  sbb     edx, edx
0x18001ae58  and     edx, 100h
0x18001ae5e  or      edx, [r8]
0x18001ae61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae66  mov     dword ptr [rbp+57h+var_78], eax
0x18001ae69  mov     rax, [rbx]
0x18001ae6c  cmp     [rdi+3Ch], r15d
0x18001ae70  jnz     short loc_18001AE7A
0x18001ae72  mov     rdx, r15
0x18001ae75  mov     r8d, r15d
0x18001ae78  jmp     short loc_18001AE9E
0x18001ae7a  mov     r9, [rbx+0A18h]
0x18001ae81  mov     r8d, [rdi+3Ch]
0x18001ae85  mov     ecx, [r9+38h]
0x18001ae89  mov     edx, [r9+38h]
0x18001ae8d  add     rcx, r8
0x18001ae90  add     rdx, r8
0x18001ae93  add     rdx, r9
0x18001ae96  mov     r8d, [rcx+r9-4]
0x18001ae9b  shr     r8d, 1
0x18001ae9e  mov     rax, [rax+28h]
0x18001aea2  mov     rcx, rbx
0x18001aea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aeaa  mov     dword ptr [rbp+57h+var_68+4], eax
0x18001aead  mov     rax, [rbx]
0x18001aeb0  cmp     [rdi+40h], r15d
0x18001aeb4  jnz     short loc_18001AEBE
0x18001aeb6  mov     rdx, r15
0x18001aeb9  mov     r8d, r15d
0x18001aebc  jmp     short loc_18001AEE2
0x18001aebe  mov     r9, [rbx+0A18h]
0x18001aec5  mov     r8d, [rdi+40h]
0x18001aec9  mov     ecx, [r9+38h]
0x18001aecd  mov     edx, [r9+38h]
0x18001aed1  add     rcx, r8
0x18001aed4  add     rdx, r8
0x18001aed7  add     rdx, r9
0x18001aeda  mov     r8d, [rcx+r9-4]
0x18001aedf  shr     r8d, 1
  ... truncated ...
```
