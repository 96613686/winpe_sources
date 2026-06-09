# TMetabaseMetaXmlFile::AddShippedColumnMetaToHeap(ulong,ColumnMeta const *)

- ea: `0x18001a444`
- end: `0x18001a90e`
- name: `?AddShippedColumnMetaToHeap@TMetabaseMetaXmlFile@@AEAAXKPEBUColumnMeta@@@Z`
- size: `1226`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this, unsigned int, const struct ColumnMeta *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001aac4`

## callees

- `0x18001a444`
- `0x18001b014`
- `0x18002e110`
- `0x180030010`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::AddShippedColumnMetaToHeap(
        TMetabaseMetaXmlFile *this,
        unsigned int a2,
        const struct ColumnMeta *a3)
{
  __int64 v3; // rax
  __int64 v5; // rdx
  __int64 (__fastcall *v8)(TMetabaseMetaXmlFile *, __int64); // rax
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 (__fastcall *v11)(TMetabaseMetaXmlFile *, __int64, __int64); // r9
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rax
  unsigned int *v21; // rdx
  unsigned int *v22; // rdx
  unsigned int *v23; // rdx
  unsigned int v24; // eax
  unsigned __int64 v25; // rdx
  unsigned int *v26; // rdx
  unsigned int *v27; // rdx
  unsigned int *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rax
  unsigned int *v33; // rdx
  unsigned int *v34; // rdx
  unsigned int *v35; // rdx
  unsigned int *v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rax
  int v45; // eax
  __int64 v46; // rcx
  unsigned int v47; // r14d
  __int64 v48; // rax
  const struct TagMetaPublic *i; // rsi
  unsigned int v50; // eax
  unsigned int v51[2]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v52; // [rsp+28h] [rbp-41h]
  __int64 v53; // [rsp+30h] [rbp-39h]
  __int64 v54; // [rsp+38h] [rbp-31h]
  __int64 v55; // [rsp+40h] [rbp-29h]
  __int64 v56; // [rsp+48h] [rbp-21h]
  __int64 v57; // [rsp+50h] [rbp-19h]
  __int64 v58; // [rsp+58h] [rbp-11h]
  __int64 v59; // [rsp+60h] [rbp-9h]
  __int64 v60; // [rsp+68h] [rbp-1h]
  int v61; // [rsp+70h] [rbp+7h]

  v3 = *(_QWORD *)this;
  *(_QWORD *)v51 = 0;
  v5 = *((unsigned int *)this + 643);
  v52 = 0;
  v8 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64))(v3 + 16);
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v9 = v8(this, v5);
  *((_DWORD *)this + 634) = v9;
  v51[1] = v9;
  v10 = *(_QWORD *)this;
  v51[0] = a2;
  v11 = *(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(v10 + 40);
  if ( *((_DWORD *)a3 + 2) )
  {
    v12 = *((_QWORD *)this + 323);
    v13 = *((unsigned int *)a3 + 2);
    v14 = *(_DWORD *)(v13 + *(unsigned int *)(v12 + 56) + v12 - 4) >> 1;
    v15 = v12 + v13 + *(unsigned int *)(v12 + 56);
  }
  else
  {
    v15 = 0;
    v14 = 0;
  }
  v16 = v11(this, v15, v14);
  v17 = *((unsigned int *)a3 + 3);
  LODWORD(v52) = v16;
  if ( (_DWORD)v17 != *((_DWORD *)a3 + 2) )
  {
    if ( (_DWORD)v17 )
    {
      v18 = *((_QWORD *)this + 323);
      v19 = *(_DWORD *)(v17 + *(unsigned int *)(v18 + 56) + v18 - 4) >> 1;
      v20 = v18 + v17 + *(unsigned int *)(v18 + 56);
    }
    else
    {
      v20 = 0;
      v19 = 0;
    }
    v16 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v20, v19);
  }
  HIDWORD(v52) = v16;
  if ( *((_DWORD *)a3 + 4) )
    v21 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 4));
  else
    v21 = 0;
  LODWORD(v53) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v21);
  if ( *((_DWORD *)a3 + 5) )
    v22 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 5));
  else
    v22 = 0;
  HIDWORD(v53) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v22);
  if ( *((_DWORD *)a3 + 6) )
    v23 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 6));
  else
    v23 = 0;
  LODWORD(v54) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v23);
  if ( *((_DWORD *)a3 + 7) )
  {
    v25 = *((_QWORD *)this + 323)
        + *((unsigned int *)a3 + 7)
        + (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 323) + 56LL);
    v24 = *(_DWORD *)(v25 - 4);
  }
  else
  {
    v24 = 0;
    v25 = 0;
  }
  HIDWORD(v54) = (**(__int64 (__fastcall ***)(TMetabaseMetaXmlFile *, unsigned __int64, _QWORD))this)(this, v25, v24);
  if ( *((_DWORD *)a3 + 8) )
    v26 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 8));
  else
    v26 = 0;
  LODWORD(v55) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v26);
  if ( *((_DWORD *)a3 + 9) )
    v27 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 9));
  else
    v27 = 0;
  HIDWORD(v55) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v27);
  if ( *((_DWORD *)a3 + 10) )
    v28 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 10));
  else
    v28 = 0;
  LODWORD(v56) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v28);
  if ( *((_DWORD *)a3 + 11) )
  {
    v29 = *((_QWORD *)this + 323);
    v30 = *((unsigned int *)a3 + 11);
    v31 = *(_DWORD *)(v30 + *(unsigned int *)(v29 + 56) + v29 - 4) >> 1;
    v32 = v29 + v30 + *(unsigned int *)(v29 + 56);
  }
  else
  {
    v32 = 0;
    v31 = 0;
  }
  HIDWORD(v56) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(
                   this,
                   v32,
                   v31);
  if ( *((_DWORD *)a3 + 12) )
    v33 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 12));
  else
    v33 = 0;
  LODWORD(v57) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v33);
  if ( *((_DWORD *)a3 + 13) )
    v34 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 13));
  else
    v34 = 0;
  HIDWORD(v57) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v34);
  if ( *((_DWORD *)a3 + 14) )
    v35 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 14));
  else
    v35 = 0;
  LODWORD(v58) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v35);
  if ( *((_DWORD *)a3 + 15) )
    v36 = (unsigned int *)(*((_QWORD *)this + 323)
                         + *(unsigned int *)(*((_QWORD *)this + 323) + 56LL)
                         + *((unsigned int *)a3 + 15));
  else
    v36 = 0;
  HIDWORD(v58) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, _QWORD))(*(_QWORD *)this + 16LL))(this, *v36);
  if ( *((_DWORD *)a3 + 16) )
  {
    v37 = *((_QWORD *)this + 323);
    v38 = *((unsigned int *)a3 + 16);
    v39 = *(_DWORD *)(v38 + *(unsigned int *)(v37 + 56) + v37 - 4) >> 1;
    v40 = v37 + v38 + *(unsigned int *)(v37 + 56);
  }
  else
  {
    v40 = 0;
    v39 = 0;
  }
  LODWORD(v59) = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(
                   this,
                   v40,
                   v39);
  if ( *((_DWORD *)a3 + 17) )
  {
    v41 = *((_QWORD *)this + 323);
    v42 = *((unsigned int *)a3 + 17);
    v43 = *(_DWORD *)(v42 + *(unsigned int *)(v41 + 56) + v41 - 4) >> 1;
    v44 = v41 + v42 + *(unsigned int *)(v41 + 56);
  }
  else
  {
    v44 = 0;
    v43 = 0;
  }
  v45 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, __int64, __int64))(*(_QWORD *)this + 40LL))(this, v44, v43);
  v46 = *((_QWORD *)this + 323);
  v47 = 0;
  HIDWORD(v59) = v45;
  v48 = *((unsigned int *)a3 + 19);
  v60 = 0;
  v61 = 0;
  for ( i = (const struct TagMetaPublic *)(*(unsigned int *)(v46 + 96) + v46 + 24 * v48);
        v47 < *((_DWORD *)a3 + 18);
        i = (const struct TagMetaPublic *)((char *)i + 24) )
  {
    TMetabaseMetaXmlFile::AddShippedTagMetaToHeap(this, a2, v51[1], i);
    ++v47;
  }
  v50 = (*(__int64 (__fastcall **)(TMetabaseMetaXmlFile *, unsigned int *, __int64))(*(_QWORD *)this + 56LL))(
          this,
          v51,
          1);
  *((_DWORD *)this + 634) = 0;
  ++*((_DWORD *)this + 643);
  *((_DWORD *)this + 640) = v50 / 0x54;
}

```

## disassembly

```asm
0x18001a444  push    rbp
0x18001a446  push    rbx
0x18001a447  push    rsi
0x18001a448  push    rdi
0x18001a449  push    r12
0x18001a44b  push    r14
0x18001a44d  push    r15
0x18001a44f  lea     rbp, [rsp-27h]
0x18001a454  sub     rsp, 90h
0x18001a45b  mov     rax, cs:__security_cookie
0x18001a462  xor     rax, rsp
0x18001a465  mov     [rbp+57h+var_40], rax
0x18001a469  mov     rax, [rcx]
0x18001a46c  xor     r12d, r12d
0x18001a46f  mov     r15d, edx
0x18001a472  mov     qword ptr [rbp+57h+var_A0], r12
0x18001a476  mov     edx, [rcx+0A0Ch]
0x18001a47c  mov     rdi, r8
0x18001a47f  mov     rbx, rcx
0x18001a482  mov     [rbp+57h+var_98], r12
0x18001a486  mov     rax, [rax+10h]
0x18001a48a  mov     [rbp+57h+var_90], r12
0x18001a48e  mov     [rbp+57h+var_88], r12
0x18001a492  mov     [rbp+57h+var_80], r12
0x18001a496  mov     [rbp+57h+var_78], r12
0x18001a49a  mov     [rbp+57h+var_70], r12
0x18001a49e  mov     [rbp+57h+var_68], r12
0x18001a4a2  mov     [rbp+57h+var_60], r12
0x18001a4a6  mov     [rbp+57h+var_58], r12
0x18001a4aa  mov     [rbp+57h+var_50], r12d
0x18001a4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4b3  mov     [rbx+9E8h], eax
0x18001a4b9  mov     [rbp+57h+var_A0+4], eax
0x18001a4bc  mov     rax, [rbx]
0x18001a4bf  mov     [rbp+57h+var_A0], r15d
0x18001a4c3  mov     r9, [rax+28h]
0x18001a4c7  cmp     [rdi+8], r12d
0x18001a4cb  jz      short loc_18001A4F0
0x18001a4cd  mov     rdx, [rbx+0A18h]
0x18001a4d4  mov     ecx, [rdi+8]
0x18001a4d7  mov     eax, [rdx+38h]
0x18001a4da  add     rax, rcx
0x18001a4dd  mov     r8d, [rax+rdx-4]
0x18001a4e2  mov     eax, [rdx+38h]
0x18001a4e5  add     rax, rcx
0x18001a4e8  shr     r8d, 1
0x18001a4eb  add     rax, rdx
0x18001a4ee  jmp     short loc_18001A4F6
0x18001a4f0  mov     rax, r12
0x18001a4f3  mov     r8d, r12d
0x18001a4f6  mov     rdx, rax
0x18001a4f9  mov     rcx, rbx
0x18001a4fc  mov     rax, r9
0x18001a4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a504  mov     ecx, [rdi+0Ch]
0x18001a507  mov     dword ptr [rbp+57h+var_98], eax
0x18001a50a  cmp     ecx, [rdi+8]
0x18001a50d  jz      short loc_18001A54E
0x18001a50f  mov     rax, [rbx]
0x18001a512  mov     r9, [rax+28h]
0x18001a516  test    ecx, ecx
0x18001a518  jz      short loc_18001A53A
0x18001a51a  mov     rdx, [rbx+0A18h]
0x18001a521  mov     eax, [rdx+38h]
0x18001a524  add     rax, rcx
0x18001a527  mov     r8d, [rax+rdx-4]
0x18001a52c  mov     eax, [rdx+38h]
0x18001a52f  add     rax, rcx
0x18001a532  shr     r8d, 1
0x18001a535  add     rax, rdx
0x18001a538  jmp     short loc_18001A540
0x18001a53a  mov     rax, r12
0x18001a53d  mov     r8d, r12d
0x18001a540  mov     rdx, rax
0x18001a543  mov     rcx, rbx
0x18001a546  mov     rax, r9
0x18001a549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a54e  mov     dword ptr [rbp+57h+var_98+4], eax
0x18001a551  mov     rax, [rbx]
0x18001a554  cmp     [rdi+10h], r12d
0x18001a558  jnz     short loc_18001A55F
0x18001a55a  mov     rdx, r12
0x18001a55d  jmp     short loc_18001A573
0x18001a55f  mov     r8, [rbx+0A18h]
0x18001a566  mov     edx, [rdi+10h]
0x18001a569  mov     ecx, [r8+38h]
0x18001a56d  add     rcx, r8
0x18001a570  add     rdx, rcx
0x18001a573  mov     edx, [rdx]
0x18001a575  mov     rcx, rbx
0x18001a578  mov     rax, [rax+10h]
0x18001a57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a581  mov     dword ptr [rbp+57h+var_90], eax
0x18001a584  mov     rax, [rbx]
0x18001a587  cmp     [rdi+14h], r12d
0x18001a58b  jnz     short loc_18001A592
0x18001a58d  mov     rdx, r12
0x18001a590  jmp     short loc_18001A5A6
0x18001a592  mov     r8, [rbx+0A18h]
0x18001a599  mov     edx, [rdi+14h]
0x18001a59c  mov     ecx, [r8+38h]
0x18001a5a0  add     rcx, r8
0x18001a5a3  add     rdx, rcx
0x18001a5a6  mov     edx, [rdx]
0x18001a5a8  mov     rcx, rbx
0x18001a5ab  mov     rax, [rax+10h]
0x18001a5af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5b4  mov     dword ptr [rbp+57h+var_90+4], eax
0x18001a5b7  mov     rax, [rbx]
0x18001a5ba  cmp     [rdi+18h], r12d
0x18001a5be  jnz     short loc_18001A5C5
0x18001a5c0  mov     rdx, r12
0x18001a5c3  jmp     short loc_18001A5D9
0x18001a5c5  mov     r8, [rbx+0A18h]
0x18001a5cc  mov     edx, [rdi+18h]
0x18001a5cf  mov     ecx, [r8+38h]
0x18001a5d3  add     rcx, r8
0x18001a5d6  add     rdx, rcx
0x18001a5d9  mov     edx, [rdx]
0x18001a5db  mov     rcx, rbx
0x18001a5de  mov     rax, [rax+10h]
0x18001a5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5e7  mov     dword ptr [rbp+57h+var_88], eax
0x18001a5ea  mov     rax, [rbx]
0x18001a5ed  mov     r9, [rax]
0x18001a5f0  cmp     [rdi+1Ch], r12d
0x18001a5f4  jnz     short loc_18001A5FE
0x18001a5f6  mov     eax, r12d
0x18001a5f9  mov     rdx, r12
0x18001a5fc  jmp     short loc_18001A615
0x18001a5fe  mov     r8, [rbx+0A18h]
0x18001a605  mov     ecx, [rdi+1Ch]
0x18001a608  mov     edx, [r8+38h]
0x18001a60c  add     rdx, rcx
0x18001a60f  add     rdx, r8
0x18001a612  mov     eax, [rdx-4]
0x18001a615  mov     r8d, eax
0x18001a618  mov     rcx, rbx
0x18001a61b  mov     rax, r9
0x18001a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a623  mov     dword ptr [rbp+57h+var_88+4], eax
0x18001a626  mov     rax, [rbx]
0x18001a629  cmp     [rdi+20h], r12d
0x18001a62d  jnz     short loc_18001A634
0x18001a62f  mov     rdx, r12
0x18001a632  jmp     short loc_18001A648
0x18001a634  mov     r8, [rbx+0A18h]
0x18001a63b  mov     edx, [rdi+20h]
0x18001a63e  mov     ecx, [r8+38h]
0x18001a642  add     rcx, r8
0x18001a645  add     rdx, rcx
0x18001a648  mov     edx, [rdx]
0x18001a64a  mov     rcx, rbx
0x18001a64d  mov     rax, [rax+10h]
0x18001a651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a656  mov     dword ptr [rbp+57h+var_80], eax
0x18001a659  mov     rax, [rbx]
0x18001a65c  cmp     [rdi+24h], r12d
0x18001a660  jnz     short loc_18001A667
0x18001a662  mov     rdx, r12
0x18001a665  jmp     short loc_18001A67B
0x18001a667  mov     r8, [rbx+0A18h]
0x18001a66e  mov     edx, [rdi+24h]
0x18001a671  mov     ecx, [r8+38h]
0x18001a675  add     rcx, r8
0x18001a678  add     rdx, rcx
0x18001a67b  mov     edx, [rdx]
0x18001a67d  mov     rcx, rbx
0x18001a680  mov     rax, [rax+10h]
0x18001a684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a689  mov     dword ptr [rbp+57h+var_80+4], eax
0x18001a68c  mov     rax, [rbx]
0x18001a68f  cmp     [rdi+28h], r12d
0x18001a693  jnz     short loc_18001A69A
0x18001a695  mov     rdx, r12
0x18001a698  jmp     short loc_18001A6AE
0x18001a69a  mov     r8, [rbx+0A18h]
0x18001a6a1  mov     edx, [rdi+28h]
0x18001a6a4  mov     ecx, [r8+38h]
0x18001a6a8  add     rcx, r8
0x18001a6ab  add     rdx, rcx
0x18001a6ae  mov     edx, [rdx]
0x18001a6b0  mov     rcx, rbx
0x18001a6b3  mov     rax, [rax+10h]
0x18001a6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a6bc  mov     dword ptr [rbp+57h+var_78], eax
0x18001a6bf  mov     rax, [rbx]
0x18001a6c2  mov     r9, [rax+28h]
0x18001a6c6  cmp     [rdi+2Ch], r12d
0x18001a6ca  jz      short loc_18001A6EF
0x18001a6cc  mov     rdx, [rbx+0A18h]
0x18001a6d3  mov     ecx, [rdi+2Ch]
0x18001a6d6  mov     eax, [rdx+38h]
0x18001a6d9  add     rax, rcx
0x18001a6dc  mov     r8d, [rax+rdx-4]
0x18001a6e1  mov     eax, [rdx+38h]
0x18001a6e4  add     rax, rcx
0x18001a6e7  shr     r8d, 1
0x18001a6ea  add     rax, rdx
0x18001a6ed  jmp     short loc_18001A6F5
0x18001a6ef  mov     rax, r12
0x18001a6f2  mov     r8d, r12d
0x18001a6f5  mov     rdx, rax
0x18001a6f8  mov     rcx, rbx
0x18001a6fb  mov     rax, r9
0x18001a6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a703  mov     dword ptr [rbp+57h+var_78+4], eax
0x18001a706  mov     rax, [rbx]
0x18001a709  cmp     [rdi+30h], r12d
0x18001a70d  jnz     short loc_18001A714
0x18001a70f  mov     rdx, r12
0x18001a712  jmp     short loc_18001A728
0x18001a714  mov     r8, [rbx+0A18h]
0x18001a71b  mov     edx, [rdi+30h]
0x18001a71e  mov     ecx, [r8+38h]
0x18001a722  add     rcx, r8
0x18001a725  add     rdx, rcx
0x18001a728  mov     edx, [rdx]
0x18001a72a  mov     rcx, rbx
0x18001a72d  mov     rax, [rax+10h]
0x18001a731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a736  mov     dword ptr [rbp+57h+var_70], eax
0x18001a739  mov     rax, [rbx]
0x18001a73c  cmp     [rdi+34h], r12d
0x18001a740  jnz     short loc_18001A747
0x18001a742  mov     rdx, r12
0x18001a745  jmp     short loc_18001A75B
0x18001a747  mov     r8, [rbx+0A18h]
0x18001a74e  mov     edx, [rdi+34h]
0x18001a751  mov     ecx, [r8+38h]
0x18001a755  add     rcx, r8
0x18001a758  add     rdx, rcx
0x18001a75b  mov     edx, [rdx]
0x18001a75d  mov     rcx, rbx
0x18001a760  mov     rax, [rax+10h]
0x18001a764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a769  mov     dword ptr [rbp+57h+var_70+4], eax
0x18001a76c  mov     rax, [rbx]
0x18001a76f  cmp     [rdi+38h], r12d
0x18001a773  jnz     short loc_18001A77A
0x18001a775  mov     rdx, r12
0x18001a778  jmp     short loc_18001A78E
0x18001a77a  mov     r8, [rbx+0A18h]
0x18001a781  mov     edx, [rdi+38h]
0x18001a784  mov     ecx, [r8+38h]
0x18001a788  add     rcx, r8
0x18001a78b  add     rdx, rcx
0x18001a78e  mov     edx, [rdx]
0x18001a790  mov     rcx, rbx
0x18001a793  mov     rax, [rax+10h]
0x18001a797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a79c  mov     dword ptr [rbp+57h+var_68], eax
0x18001a79f  mov     rax, [rbx]
0x18001a7a2  cmp     [rdi+3Ch], r12d
0x18001a7a6  jnz     short loc_18001A7AD
0x18001a7a8  mov     rdx, r12
0x18001a7ab  jmp     short loc_18001A7C1
0x18001a7ad  mov     r8, [rbx+0A18h]
0x18001a7b4  mov     edx, [rdi+3Ch]
0x18001a7b7  mov     ecx, [r8+38h]
0x18001a7bb  add     rcx, r8
0x18001a7be  add     rdx, rcx
0x18001a7c1  mov     edx, [rdx]
0x18001a7c3  mov     rcx, rbx
0x18001a7c6  mov     rax, [rax+10h]
0x18001a7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7cf  mov     dword ptr [rbp+57h+var_68+4], eax
0x18001a7d2  mov     rax, [rbx]
0x18001a7d5  mov     r9, [rax+28h]
0x18001a7d9  cmp     [rdi+40h], r12d
0x18001a7dd  jz      short loc_18001A802
0x18001a7df  mov     rdx, [rbx+0A18h]
0x18001a7e6  mov     ecx, [rdi+40h]
0x18001a7e9  mov     eax, [rdx+38h]
0x18001a7ec  add     rax, rcx
0x18001a7ef  mov     r8d, [rax+rdx-4]
0x18001a7f4  mov     eax, [rdx+38h]
0x18001a7f7  add     rax, rcx
0x18001a7fa  shr     r8d, 1
0x18001a7fd  add     rax, rdx
0x18001a800  jmp     short loc_18001A808
0x18001a802  mov     rax, r12
0x18001a805  mov     r8d, r12d
0x18001a808  mov     rdx, rax
0x18001a80b  mov     rcx, rbx
0x18001a80e  mov     rax, r9
0x18001a811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a816  mov     dword ptr [rbp+57h+var_60], eax
0x18001a819  mov     rax, [rbx]
0x18001a81c  mov     r9, [rax+28h]
0x18001a820  cmp     [rdi+44h], r12d
0x18001a824  jz      short loc_18001A849
0x18001a826  mov     rdx, [rbx+0A18h]
0x18001a82d  mov     ecx, [rdi+44h]
0x18001a830  mov     eax, [rdx+38h]
0x18001a833  add     rax, rcx
0x18001a836  mov     r8d, [rax+rdx-4]
0x18001a83b  mov     eax, [rdx+38h]
0x18001a83e  add     rax, rcx
0x18001a841  shr     r8d, 1
  ... truncated ...
```
