# PortablePDB::ConvertPortablePDB(PDB * *,char const *,long &)

- ea: `0x18004bd90`
- end: `0x18004c5b1`
- name: `?ConvertPortablePDB@PortablePDB@@QEAAHPEAPEAUPDB@@PEBDAEAJ@Z`
- size: `2081`
- prototype: `__int64 __fastcall(PortablePDB *__hidden this, struct PDB **, const char *, int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800333d0`

## callees

- `0x1800269d4`
- `0x180027440`
- `0x180033210`
- `0x1800352f0`
- `0x180038b30`
- `0x1800493c0`
- `0x180049540`
- `0x180049600`
- `0x180049650`
- `0x18004a730`
- `0x18004ac00`
- `0x18004bd90`
- `0x18004d210`
- `0x18004ecc0`
- `0x18004ef30`
- `0x18008a930`
- `0x1801d6350`
- `0x1801d63b0`

## string_xrefs

- `0x18004c548`: `Range error during default makeSubRange`
- `0x18004c525`: `Range error during currentVoidPtr`
- `0x18004c58e`: `Range error during currentVoidPtr`
- `0x18004bf4e`: `COM+_Entry_Point`
- `0x18004c502`: `Range error during peek`
- `0x18004c56b`: `Range error during peek`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PortablePDB::ConvertPortablePDB(PortablePDB *this, struct PDB **a2, const char *a3, int *a4)
{
  const char *v5; // r15
  struct PDB **v6; // rsi
  PdbMemStream *v8; // rax
  volatile signed __int32 *v9; // r13
  unsigned __int64 *v10; // r8
  __int128 *v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned int (__fastcall *v14)(PDB1 *, _QWORD, __int128 *, __int64); // rbx
  __int128 v15; // xmm6
  unsigned int v16; // eax
  unsigned int (__fastcall *v17)(__int64, const char *, _QWORD, _QWORD, _DWORD); // rbx
  unsigned int v18; // eax
  unsigned __int64 *v19; // r8
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // r15
  __int64 v27; // r12
  int v28; // r10d
  __int64 v29; // r9
  unsigned int v30; // r8d
  __int64 v31; // rdx
  __int64 v32; // r11
  __int64 v33; // r8
  _DWORD *v34; // rdx
  int EmbeddedSourceAndSourceLinkInfo; // eax
  int v36; // eax
  unsigned __int64 *v37; // r8
  __int128 *v38; // rdx
  unsigned __int64 v39; // rax
  unsigned __int64 v40; // rcx
  unsigned int (__fastcall *v41)(PDB1 *, _QWORD, __int128 *, __int64); // rbx
  __int128 v42; // xmm6
  unsigned int v43; // eax
  int v45; // eax
  PDB1 *v46; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49; // [rsp+58h] [rbp-A8h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+74h] [rbp-8Ch]
  int v53; // [rsp+7Ch] [rbp-84h]
  __int64 v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+90h] [rbp-70h] BYREF
  const char *v56; // [rsp+98h] [rbp-68h]
  struct PDB **v57; // [rsp+A0h] [rbp-60h]
  __int64 v58; // [rsp+A8h] [rbp-58h]
  _OWORD v59[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h]
  wchar_t v61[1024]; // [rsp+E0h] [rbp-20h] BYREF

  v58 = -2;
  v5 = a3;
  v56 = a3;
  v6 = a2;
  v57 = a2;
  v8 = (PdbMemStream *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&pExceptionObject = v8;
  if ( v8 )
    v9 = (volatile signed __int32 *)PdbMemStream::PdbMemStream(v8, 0x10000u);
  else
    v9 = 0;
  if ( v9 )
  {
    _InterlockedIncrement(v9 + 14);
    v46 = 0;
    if ( !PDB::OpenInStream((struct IStream *)v9, "wf", &v49, v61, 0x400u, &v46) || !v46 )
    {
LABEL_66:
      *a4 = v49;
      return 0;
    }
    v47 = 0;
    v48 = 0;
    v10 = (unsigned __int64 *)*((_QWORD *)this + 8);
    v11 = (__int128 *)*v10;
    v12 = *v10 + 16;
    if ( v12 >= *v10 )
    {
      v13 = v10[1];
      if ( v12 > v13 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during peek");
        throw (std::range_error *)&pExceptionObject;
      }
      if ( (unsigned __int64)v11 > v13 )
      {
        std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
        throw (std::range_error *)&pExceptionObject;
      }
      v14 = *(unsigned int (__fastcall **)(PDB1 *, _QWORD, __int128 *, __int64))(*(_QWORD *)v46 + 264LL);
      v15 = *v11;
      v16 = ReadOnlySafeSpanPtr::peek<unsigned long>(*((_QWORD *)this + 8), 16);
      pExceptionObject = v15;
      if ( !v14(v46, v16, &pExceptionObject, 1)
        || !(*(unsigned int (__fastcall **)(PDB1 *, _QWORD, __int64 *))(*(_QWORD *)v46 + 48LL))(v46, 0, &v47) )
      {
        goto LABEL_63;
      }
      if ( !v47 )
        goto LABEL_62;
      if ( (unsigned int)ReadOnlySafeSpanPtr::peek<unsigned long>(*((_QWORD *)this + 8), 20) )
      {
        v17 = *(unsigned int (__fastcall **)(__int64, const char *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v47 + 336LL);
        v18 = ReadOnlySafeSpanPtr::peek<unsigned long>(*((_QWORD *)this + 8), 20);
        if ( !v17(v47, "COM+_Entry_Point", 0, v18, 0) )
          goto LABEL_63;
      }
      if ( !(*(unsigned int (__fastcall **)(__int64, char *, char *, __int64 *))(*(_QWORD *)v47 + 296LL))(
              v47,
              (char *)this + 112,
              (char *)this + 112,
              &v48) )
        goto LABEL_63;
      if ( !v48 )
      {
LABEL_62:
        *a4 = 24;
        return 0;
      }
      v19 = (unsigned __int64 *)*((_QWORD *)this + 9);
      v20 = *v19 + (unsigned int)(4 * *((_DWORD *)this + 172) + 24);
      if ( v20 >= *v19 )
      {
        v21 = v19[1];
        if ( v20 > v21 )
        {
          std::range_error::range_error(
            (std::range_error *)&pExceptionObject,
            "Range error during default makeSubRange");
          throw (std::range_error *)&pExceptionObject;
        }
        *((_QWORD *)this + 12) = v20;
        *((_QWORD *)this + 13) = v21;
        if ( *((_DWORD *)this + 164) )
        {
          v22 = PortablePDB::CollectSourceFileInfo(this);
          *a4 = v22;
          if ( v22 )
          {
LABEL_65:
            (*(void (__fastcall **)(PDB1 *))(*(_QWORD *)v46 + 88LL))(v46);
            return 0;
          }
          if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 24LL))(
                  v48,
                  *((_QWORD *)this + 95),
                  (unsigned int)(*((_DWORD *)this + 192) - *((_DWORD *)this + 190)))
            || !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 24LL))(
                  v48,
                  *((_QWORD *)this + 88),
                  (unsigned int)(*((_DWORD *)this + 178) - *((_DWORD *)this + 176))) )
          {
            goto LABEL_63;
          }
        }
        if ( *((_DWORD *)this + 165) )
        {
          v23 = PortablePDB::CollectLineColumnInfo(this);
          *a4 = v23;
          if ( v23 )
            goto LABEL_65;
        }
        v24 = PortablePDB::CollectMethodInfo(this);
        *a4 = v24;
        if ( v24 )
          goto LABEL_65;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 24LL))(
                v48,
                *((_QWORD *)this + 102),
                (unsigned int)(*((_DWORD *)this + 206) - *((_DWORD *)this + 204))) )
          goto LABEL_63;
        if ( *((_DWORD *)this + 165) )
        {
          v25 = 0;
          if ( !*((_DWORD *)this + 260) )
            goto LABEL_40;
          do
          {
            v26 = 12LL * v25;
            v27 = *((_QWORD *)this + 129);
            v28 = *(_DWORD *)(v27 + v26);
            v29 = *(_QWORD *)(*((_QWORD *)this + 123)
                            + 8LL * ((unsigned int)(unsigned __int16)v28 % *((_DWORD *)this + 248)));
            if ( !v29 || (v30 = *(_DWORD *)(v29 + 16)) == 0 )
            {
LABEL_35:
              *a4 = 13;
              goto LABEL_65;
            }
            v31 = 0;
            v32 = *(_QWORD *)(v29 + 8);
            while ( *(_DWORD *)(*((_QWORD *)this + 117) + 4LL * HIDWORD(*(_QWORD *)(v32 + 8 * v31))) != v28 )
            {
              v31 = (unsigned int)(v31 + 1);
              if ( (unsigned int)v31 >= v30 )
                goto LABEL_35;
            }
            v33 = *(_QWORD *)(*((_QWORD *)this + 120) + 8LL * *(unsigned int *)(v32 + 8 * v31));
            v34 = (_DWORD *)(*((_QWORD *)this + 109) + *(unsigned int *)(v27 + v26 + 4));
            *v34 += v33;
            if ( *(_BYTE *)(v26 + *((_QWORD *)this + 129) + 8) )
              v34[2] = v33 + HIDWORD(v33) - *v34;
            ++v25;
          }
          while ( v25 < *((_DWORD *)this + 260) );
          v5 = v56;
LABEL_40:
          *a4 = 0;
          if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v48 + 24LL))(
                 v48,
                 *((_QWORD *)this + 109),
                 (unsigned int)(*((_DWORD *)this + 220) - *((_DWORD *)this + 218))) )
          {
            v6 = v57;
            goto LABEL_42;
          }
          goto LABEL_63;
        }
LABEL_42:
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v48 + 160LL))(
                v48,
                1,
                0,
                *((unsigned int *)this + 14),
                0,
                0,
                0) )
          goto LABEL_63;
        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v48 + 128LL))(v48) )
          goto LABEL_63;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD, _DWORD))(*(_QWORD *)v47 + 56LL))(
                v47,
                1,
                269,
                0,
                *((_DWORD *)this + 14)) )
          goto LABEL_63;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64, _QWORD, int))(*(_QWORD *)v47 + 56LL))(
                v47,
                0,
                520,
                0,
                -1) )
          goto LABEL_63;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v47 + 200LL))(v47, 5, &v55) )
          goto LABEL_63;
        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v55 + 48LL))(v55) )
          goto LABEL_63;
        *(_QWORD *)&pExceptionObject = 0;
        *((_QWORD *)&pExceptionObject + 1) = *((unsigned int *)this + 14);
        v51 = DWORD2(pExceptionObject);
        v52 = 0;
        v53 = 0;
        v54 = 0;
        v59[0] = pExceptionObject;
        v59[1] = DWORD2(pExceptionObject);
        v60 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)v55 + 56LL))(v55, 1, v59)
          || !(**(unsigned int (__fastcall ***)(__int64))v55)(v55)
          || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v47 + 112LL))(v47) )
        {
          goto LABEL_63;
        }
        EmbeddedSourceAndSourceLinkInfo = PortablePDB::ReadEmbeddedSourceAndSourceLinkInfo(this);
        *a4 = EmbeddedSourceAndSourceLinkInfo;
        if ( EmbeddedSourceAndSourceLinkInfo )
          goto LABEL_65;
        v36 = PortablePDB::WriteSrcInfo(this, v46);
        *a4 = v36;
        if ( v36 )
          goto LABEL_65;
        if ( !PortablePDB::WriteSourceLinkInfo(this, v46) )
          goto LABEL_63;
        v37 = (unsigned __int64 *)*((_QWORD *)this + 8);
        v38 = (__int128 *)*v37;
        v39 = *v37 + 16;
        if ( v39 >= *v37 )
        {
          v40 = v37[1];
          if ( v39 > v40 )
          {
            std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during peek");
            throw (std::range_error *)&pExceptionObject;
          }
          if ( (unsigned __int64)v38 > v40 )
          {
            std::range_error::range_error((std::range_error *)&pExceptionObject, "Range error during currentVoidPtr");
            throw (std::range_error *)&pExceptionObject;
          }
          v41 = *(unsigned int (__fastcall **)(PDB1 *, _QWORD, __int128 *, __int64))(*(_QWORD *)v46 + 264LL);
          v42 = *v38;
          v43 = ReadOnlySafeSpanPtr::peek<unsigned long>(*((_QWORD *)this + 8), 16);
          pExceptionObject = v42;
          if ( v41(v46, v43, &pExceptionObject, 0xFFFFFFFFLL)
            && (*(unsigned int (__fastcall **)(PDB1 *))(*(_QWORD *)v46 + 80LL))(v46)
            && (*(unsigned int (__fastcall **)(PDB1 *))(*(_QWORD *)v46 + 88LL))(v46) )
          {
            PortablePDB::Close(this);
            if ( PDB::OpenInStream((struct IStream *)v9, v5, &v49, v61, 0x400u, v6) )
            {
              *((_BYTE *)*v6 + 946) |= 1u;
              return 1;
            }
            goto LABEL_66;
          }
LABEL_63:
          v45 = (*(__int64 (__fastcall **)(PDB1 *, _QWORD, _QWORD))(*(_QWORD *)v46 + 288LL))(v46, 0, 0);
          *a4 = v45;
          if ( !v45 )
          {
            PDB1::setLastError(v46, 24, 0);
            *a4 = 24;
          }
          goto LABEL_65;
        }
      }
    }
    msl::utilities::SafeIntErrorPolicy_SafeIntException::SafeIntOnOverflow();
  }
  *a4 = 2;
  return 0;
}

```

## disassembly

```asm
0x18004bd90  push    rbp
0x18004bd92  push    rbx
0x18004bd93  push    rsi
0x18004bd94  push    rdi
0x18004bd95  push    r12
0x18004bd97  push    r13
0x18004bd99  push    r14
0x18004bd9b  push    r15
0x18004bd9d  lea     rbp, [rsp-808h]
0x18004bda5  sub     rsp, 908h
0x18004bdac  mov     [rbp+840h+var_898], 0FFFFFFFFFFFFFFFEh
0x18004bdb4  movaps  [rsp+940h+var_50], xmm6
0x18004bdbc  mov     rax, cs:__security_cookie
0x18004bdc3  xor     rax, rsp
0x18004bdc6  mov     [rbp+840h+var_60], rax
0x18004bdcd  mov     r14, r9
0x18004bdd0  mov     r15, r8
0x18004bdd3  mov     [rbp+840h+var_8A8], r8
0x18004bdd7  mov     rsi, rdx
0x18004bdda  mov     [rbp+840h+var_8A0], rdx
0x18004bdde  mov     rdi, rcx
0x18004bde1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004bde8  mov     ecx, 40h ; '@'; unsigned __int64
0x18004bded  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004bdf2  mov     qword ptr [rsp+940h+pExceptionObject], rax
0x18004bdf7  xor     r12d, r12d
0x18004bdfa  test    rax, rax
0x18004bdfd  jz      short loc_18004BE11
0x18004bdff  mov     edx, 10000h; unsigned int
0x18004be04  mov     rcx, rax; this
0x18004be07  call    ??0PdbMemStream@@QEAA@I@Z; PdbMemStream::PdbMemStream(uint)
0x18004be0c  mov     r13, rax
0x18004be0f  jmp     short loc_18004BE14
0x18004be11  mov     r13, r12
0x18004be14  test    r13, r13
0x18004be17  jnz     short loc_18004BE25
0x18004be19  mov     dword ptr [r14], 2
0x18004be20  jmp     loc_18004C4CF
0x18004be25  lock inc dword ptr [r13+38h]
0x18004be2a  mov     [rsp+940h+var_900], r12
0x18004be2f  lea     rax, [rsp+940h+var_900]
0x18004be34  mov     [rsp+940h+var_918], rax; struct PDB **
0x18004be39  mov     [rsp+940h+var_920], 400h; unsigned __int64
0x18004be42  lea     r9, [rbp+840h+var_860]; wchar_t *
0x18004be46  lea     r8, [rsp+940h+var_8E8]; int *
0x18004be4b  lea     rdx, aWf; "wf"
0x18004be52  mov     rcx, r13; struct IStream *
0x18004be55  call    ?OpenInStream@PDB@@SAHPEAUIStream@@PEBDPEAJPEA_W_KPEAPEAU1@@Z; PDB::OpenInStream(IStream *,char const *,long *,wchar_t *,unsigned __int64,PDB * *)
0x18004be5a  test    eax, eax
0x18004be5c  jz      loc_18004C4C8
0x18004be62  mov     r9, [rsp+940h+var_900]
0x18004be67  test    r9, r9
0x18004be6a  jz      loc_18004C4C8
0x18004be70  mov     [rsp+940h+var_8F8], r12
0x18004be75  mov     [rsp+940h+var_8F0], r12
0x18004be7a  mov     r8, [rdi+40h]
0x18004be7e  mov     rcx, [r8]
0x18004be81  lea     rax, [rcx+10h]
0x18004be85  cmp     rax, rcx
0x18004be88  jb      loc_18004C4FC
0x18004be8e  mov     rdx, [r8+8]
0x18004be92  cmp     rax, rdx
0x18004be95  ja      loc_18004C502
0x18004be9b  cmp     rcx, rdx
0x18004be9e  ja      loc_18004C525
0x18004bea4  mov     rax, [r9]
0x18004bea7  mov     rbx, [rax+108h]
0x18004beae  movups  xmm6, xmmword ptr [rcx]
0x18004beb1  mov     edx, 10h
0x18004beb6  mov     rcx, r8
0x18004beb9  call    ??$peek@K@ReadOnlySafeSpanPtr@@QEBAKV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<ulong>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004bebe  movdqa  [rsp+940h+pExceptionObject], xmm6
0x18004bec4  mov     r9d, 1
0x18004beca  lea     r8, [rsp+940h+pExceptionObject]
0x18004becf  mov     edx, eax
0x18004bed1  mov     rcx, [rsp+940h+var_900]
0x18004bed6  mov     rax, rbx
0x18004bed9  call    cs:__guard_dispatch_icall_fptr
0x18004bedf  test    eax, eax
0x18004bee1  jz      loc_18004C47A
0x18004bee7  mov     rcx, [rsp+940h+var_900]
0x18004beec  mov     rax, [rcx]
0x18004beef  lea     r8, [rsp+940h+var_8F8]
0x18004bef4  xor     edx, edx
0x18004bef6  mov     rax, [rax+30h]
0x18004befa  call    cs:__guard_dispatch_icall_fptr
0x18004bf00  test    eax, eax
0x18004bf02  jz      loc_18004C47A
0x18004bf08  cmp     [rsp+940h+var_8F8], 0
0x18004bf0e  jz      loc_18004C471
0x18004bf14  mov     edx, 14h
0x18004bf19  mov     rcx, [rdi+40h]
0x18004bf1d  call    ??$peek@K@ReadOnlySafeSpanPtr@@QEBAKV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<ulong>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004bf22  test    eax, eax
0x18004bf24  jz      short loc_18004BF6B
0x18004bf26  mov     rax, [rsp+940h+var_8F8]
0x18004bf2b  mov     rcx, [rax]
0x18004bf2e  mov     rbx, [rcx+150h]
0x18004bf35  mov     edx, 14h
0x18004bf3a  mov     rcx, [rdi+40h]
0x18004bf3e  call    ??$peek@K@ReadOnlySafeSpanPtr@@QEBAKV?$SafeInt@_KUSafeIntErrorPolicy_SafeIntException@utilities@msl@@@utilities@msl@@@Z; ReadOnlySafeSpanPtr::peek<ulong>(msl::utilities::SafeInt<unsigned __int64,msl::utilities::SafeIntErrorPolicy_SafeIntException>)
0x18004bf43  xor     r8d, r8d
0x18004bf46  mov     dword ptr [rsp+940h+var_920], r12d
0x18004bf4b  mov     r9d, eax
0x18004bf4e  lea     rdx, aComEntryPoint; "COM+_Entry_Point"
0x18004bf55  mov     rcx, [rsp+940h+var_8F8]
0x18004bf5a  mov     rax, rbx
0x18004bf5d  call    cs:__guard_dispatch_icall_fptr
0x18004bf63  test    eax, eax
0x18004bf65  jz      loc_18004C47A
0x18004bf6b  lea     rdx, [rdi+70h]
0x18004bf6f  mov     rcx, [rsp+940h+var_8F8]
0x18004bf74  mov     rax, [rcx]
0x18004bf77  lea     r9, [rsp+940h+var_8F0]
0x18004bf7c  mov     r8, rdx
0x18004bf7f  mov     rax, [rax+128h]
0x18004bf86  call    cs:__guard_dispatch_icall_fptr
0x18004bf8c  test    eax, eax
0x18004bf8e  jz      loc_18004C47A
0x18004bf94  cmp     [rsp+940h+var_8F0], 0
0x18004bf9a  jz      loc_18004C471
0x18004bfa0  mov     r8, [rdi+48h]
0x18004bfa4  mov     eax, [rdi+2B0h]
0x18004bfaa  lea     eax, ds:18h[rax*4]
0x18004bfb1  add     rax, [r8]
0x18004bfb4  cmp     rax, [r8]
0x18004bfb7  jb      loc_18004C4FC
0x18004bfbd  mov     rcx, [r8+8]
0x18004bfc1  cmp     rax, rcx
0x18004bfc4  ja      loc_18004C548
0x18004bfca  mov     [rdi+60h], rax
0x18004bfce  mov     [rdi+68h], rcx
0x18004bfd2  cmp     dword ptr [rdi+290h], 0
0x18004bfd9  jz      short loc_18004C04C
0x18004bfdb  mov     rcx, rdi; this
0x18004bfde  call    ?CollectSourceFileInfo@PortablePDB@@AEAAJXZ; PortablePDB::CollectSourceFileInfo(void)
0x18004bfe3  mov     [r14], eax
0x18004bfe6  test    eax, eax
0x18004bfe8  jnz     loc_18004C4B4
0x18004bfee  mov     r8d, [rdi+300h]
0x18004bff5  sub     r8d, [rdi+2F8h]
0x18004bffc  mov     rcx, [rsp+940h+var_8F0]
0x18004c001  mov     rax, [rcx]
0x18004c004  mov     rdx, [rdi+2F8h]
0x18004c00b  mov     rax, [rax+18h]
0x18004c00f  call    cs:__guard_dispatch_icall_fptr
0x18004c015  test    eax, eax
0x18004c017  jz      loc_18004C47A
0x18004c01d  mov     r8d, [rdi+2C8h]
0x18004c024  sub     r8d, [rdi+2C0h]
0x18004c02b  mov     rcx, [rsp+940h+var_8F0]
0x18004c030  mov     rax, [rcx]
0x18004c033  mov     rdx, [rdi+2C0h]
0x18004c03a  mov     rax, [rax+18h]
0x18004c03e  call    cs:__guard_dispatch_icall_fptr
0x18004c044  test    eax, eax
0x18004c046  jz      loc_18004C47A
0x18004c04c  cmp     dword ptr [rdi+294h], 0
0x18004c053  jz      short loc_18004C068
0x18004c055  mov     rcx, rdi; this
0x18004c058  call    ?CollectLineColumnInfo@PortablePDB@@AEAAJXZ; PortablePDB::CollectLineColumnInfo(void)
0x18004c05d  mov     [r14], eax
0x18004c060  test    eax, eax
0x18004c062  jnz     loc_18004C4B4
0x18004c068  mov     rcx, rdi; this
0x18004c06b  call    ?CollectMethodInfo@PortablePDB@@AEAAJXZ; PortablePDB::CollectMethodInfo(void)
0x18004c070  mov     [r14], eax
0x18004c073  test    eax, eax
0x18004c075  jnz     loc_18004C4B4
0x18004c07b  mov     r8d, [rdi+338h]
0x18004c082  sub     r8d, [rdi+330h]
0x18004c089  mov     rcx, [rsp+940h+var_8F0]
0x18004c08e  mov     rax, [rcx]
0x18004c091  mov     rdx, [rdi+330h]
0x18004c098  mov     rax, [rax+18h]
0x18004c09c  call    cs:__guard_dispatch_icall_fptr
0x18004c0a2  test    eax, eax
0x18004c0a4  jz      loc_18004C47A
0x18004c0aa  cmp     dword ptr [rdi+294h], 0
0x18004c0b1  jz      loc_18004C1C8
0x18004c0b7  mov     esi, r12d
0x18004c0ba  cmp     [rdi+410h], r12d
0x18004c0c1  jbe     loc_18004C192
0x18004c0c7  nop     word ptr [rax+rax+00000000h]
0x18004c0d0  mov     eax, esi
0x18004c0d2  lea     rcx, [rax+rax*2]
0x18004c0d6  lea     r15, ds:0[rcx*4]
0x18004c0de  mov     r12, [rdi+408h]
0x18004c0e5  mov     r10d, [r12+r15]
0x18004c0e9  movzx   eax, r10w
0x18004c0ed  xor     edx, edx
0x18004c0ef  div     dword ptr [rdi+3E0h]
0x18004c0f5  mov     rax, [rdi+3D8h]
0x18004c0fc  mov     r9, [rax+rdx*8]
0x18004c100  test    r9, r9
0x18004c103  jz      short loc_18004C139
0x18004c105  mov     r8d, [r9+10h]
0x18004c109  test    r8d, r8d
0x18004c10c  jz      short loc_18004C139
0x18004c10e  xor     edx, edx
0x18004c110  mov     r11, [r9+8]
0x18004c114  mov     rbx, [rdi+3A8h]
0x18004c11b  nop     dword ptr [rax+rax+00h]
0x18004c120  mov     r9d, [r11+rdx*8]
0x18004c124  mov     rcx, [r11+rdx*8]
0x18004c128  shr     rcx, 20h
0x18004c12c  cmp     [rbx+rcx*4], r10d
0x18004c130  jz      short loc_18004C145
0x18004c132  inc     edx
0x18004c134  cmp     edx, r8d
0x18004c137  jb      short loc_18004C120
0x18004c139  mov     dword ptr [r14], 0Dh
0x18004c140  jmp     loc_18004C4B4
0x18004c145  mov     rax, [rdi+3C0h]
0x18004c14c  mov     r8, [rax+r9*8]
0x18004c150  mov     edx, [r12+r15+4]
0x18004c155  add     rdx, [rdi+368h]
0x18004c15c  add     [rdx], r8d
0x18004c15f  mov     rax, [rdi+408h]
0x18004c166  cmp     byte ptr [r15+rax+8], 0
0x18004c16c  jz      short loc_18004C17D
0x18004c16e  mov     rax, r8
0x18004c171  shr     rax, 20h
0x18004c175  add     eax, r8d
0x18004c178  sub     eax, [rdx]
0x18004c17a  mov     [rdx+8], eax
0x18004c17d  inc     esi
0x18004c17f  cmp     esi, [rdi+410h]
0x18004c185  jb      loc_18004C0D0
0x18004c18b  mov     r15, [rbp+840h+var_8A8]
0x18004c18f  xor     r12d, r12d
0x18004c192  mov     [r14], r12d
0x18004c195  mov     r8d, [rdi+370h]
0x18004c19c  sub     r8d, [rdi+368h]
0x18004c1a3  mov     rcx, [rsp+940h+var_8F0]
0x18004c1a8  mov     rax, [rcx]
0x18004c1ab  mov     rdx, [rdi+368h]
0x18004c1b2  mov     rax, [rax+18h]
0x18004c1b6  call    cs:__guard_dispatch_icall_fptr
0x18004c1bc  test    eax, eax
0x18004c1be  jz      loc_18004C47A
0x18004c1c4  mov     rsi, [rbp+840h+var_8A0]
0x18004c1c8  mov     edx, 1
0x18004c1cd  mov     rcx, [rsp+940h+var_8F0]
0x18004c1d2  mov     rax, [rcx]
0x18004c1d5  mov     [rsp+940h+var_910], r12d
0x18004c1da  mov     dword ptr [rsp+940h+var_918], r12d
0x18004c1df  mov     dword ptr [rsp+940h+var_920], r12d
0x18004c1e4  mov     r9d, [rdi+38h]
0x18004c1e8  xor     r8d, r8d
0x18004c1eb  mov     rax, [rax+0A0h]
0x18004c1f2  call    cs:__guard_dispatch_icall_fptr
0x18004c1f8  test    eax, eax
0x18004c1fa  jz      loc_18004C47A
0x18004c200  mov     rcx, [rsp+940h+var_8F0]
0x18004c205  mov     rax, [rcx]
0x18004c208  mov     rax, [rax+80h]
0x18004c20f  call    cs:__guard_dispatch_icall_fptr
0x18004c215  test    eax, eax
0x18004c217  jz      loc_18004C47A
0x18004c21d  mov     edx, 1
0x18004c222  mov     r8d, 10Dh
0x18004c228  mov     r10, [rsp+940h+var_8F8]
0x18004c22d  mov     rax, [r10]
0x18004c230  mov     ecx, [rdi+38h]
0x18004c233  mov     dword ptr [rsp+940h+var_920], ecx
0x18004c237  xor     r9d, r9d
0x18004c23a  mov     rcx, r10
0x18004c23d  mov     rax, [rax+38h]
0x18004c241  call    cs:__guard_dispatch_icall_fptr
0x18004c247  test    eax, eax
0x18004c249  jz      loc_18004C47A
0x18004c24f  xor     edx, edx
0x18004c251  mov     r8d, 208h
0x18004c257  mov     rcx, [rsp+940h+var_8F8]
0x18004c25c  mov     rax, [rcx]
0x18004c25f  mov     dword ptr [rsp+940h+var_920], 0FFFFFFFFh
0x18004c267  xor     r9d, r9d
0x18004c26a  mov     rax, [rax+38h]
0x18004c26e  call    cs:__guard_dispatch_icall_fptr
0x18004c274  test    eax, eax
0x18004c276  jz      loc_18004C47A
0x18004c27c  mov     rcx, [rsp+940h+var_8F8]
0x18004c281  mov     rax, [rcx]
0x18004c284  lea     r8, [rbp+840h+var_8B0]
0x18004c288  mov     edx, 5
0x18004c28d  mov     rax, [rax+0C8h]
0x18004c294  call    cs:__guard_dispatch_icall_fptr
0x18004c29a  test    eax, eax
0x18004c29c  jz      loc_18004C47A
0x18004c2a2  mov     rcx, [rbp+840h+var_8B0]
0x18004c2a6  mov     rax, [rcx]
0x18004c2a9  mov     rax, [rax+30h]
0x18004c2ad  call    cs:__guard_dispatch_icall_fptr
0x18004c2b3  test    eax, eax
0x18004c2b5  jz      loc_18004C47A
0x18004c2bb  xor     eax, eax
0x18004c2bd  mov     qword ptr [rsp+940h+pExceptionObject], rax
0x18004c2c2  mov     eax, [rdi+38h]
0x18004c2c5  mov     dword ptr [rsp+940h+pExceptionObject+8], eax
  ... truncated ...
```
