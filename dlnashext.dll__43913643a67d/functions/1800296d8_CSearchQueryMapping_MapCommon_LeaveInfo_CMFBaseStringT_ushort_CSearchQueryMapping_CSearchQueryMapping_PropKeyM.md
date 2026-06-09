# CSearchQueryMapping::MapCommon(LeaveInfo *,CMFBaseStringT<ushort> *,CSearchQueryMapping *,CSearchQueryMapping::PropKeyMapping *)

- ea: `0x1800296d8`
- end: `0x180029cfb`
- name: `?MapCommon@CSearchQueryMapping@@KAJPEAULeaveInfo@@PEAV?$CMFBaseStringT@G@@PEAV1@PEAUPropKeyMapping@1@@Z`
- size: `1571`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180029d04`

## callees

- `0x18000bc18`
- `0x18000d9bc`
- `0x180011930`
- `0x18001bfc0`
- `0x18001c648`
- `0x18001d41c`
- `0x180028f14`
- `0x180028fb8`
- `0x1800296d8`
- `0x18002a9a8`
- `0x1800333e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a92`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180029a88`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x180029a88`
- `PROPSYS!PropVariantToString` at `0x180029afd`
- `PROPSYS!PropVariantToString` at `0x180029afd`

## pseudocode

```c
__int64 __fastcall CSearchQueryMapping::MapCommon(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // r9d
  int v8; // ebx
  __int64 v9; // rbx
  unsigned int v10; // r14d
  __int64 v11; // rbx
  const wchar_t *v12; // rdx
  _WORD *v13; // rsi
  unsigned __int64 v14; // rcx
  __int64 v15; // rbx
  _WORD *v16; // rsi
  __int64 v17; // rbx
  const unsigned __int16 *v18; // r8
  int v19; // eax
  signed int LastError; // eax
  unsigned int v21; // edx
  unsigned __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v27; // [rsp+20h] [rbp-E0h]
  __int64 v28; // [rsp+28h] [rbp-D8h]
  WORD FatTime[2]; // [rsp+30h] [rbp-D0h] BYREF
  WORD FatDate; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+44h] [rbp-BCh]
  int v33; // [rsp+4Ch] [rbp-B4h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  WCHAR psz[1024]; // [rsp+60h] [rbp-A0h] BYREF

  v31 &= 0xFFFFFFF8;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  if ( !*(_QWORD *)(a4 + 40) )
  {
LABEL_11:
    v8 = CSearchQueryMapping::OpMapping(
           *(unsigned int *)(a1 + 20),
           *(unsigned int *)(a1 + 48),
           *(unsigned __int16 *)(a1 + 24),
           &v31);
    goto LABEL_12;
  }
  *(_DWORD *)FatTime = -1;
  if ( (int)UIntPtrToLong(1u, (int *)FatTime) >= 0 )
  {
    v8 = *(_DWORD *)(a2 + 4);
    if ( v8 < 0 )
      goto LABEL_12;
    v9 = *(int *)FatTime;
    if ( *(_DWORD *)FatTime > 0x4000000u )
    {
      *(_DWORD *)(a2 + 4) = v7;
      v8 = v7;
    }
    else if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                     a2,
                     (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
    {
      memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), L"(", 2 * v9);
      CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v9 + *(_DWORD *)(a2 + 8)));
      v8 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a2 + 4);
    }
    if ( v8 < 0 )
      goto LABEL_12;
    goto LABEL_11;
  }
  *(_DWORD *)(a2 + 4) = v7;
  v8 = v7;
LABEL_12:
  v10 = 0;
  while ( *(_QWORD *)(a4 + 8LL * v10 + 24) && v8 >= 0 )
  {
    if ( v10 )
    {
      *(_DWORD *)FatTime = -1;
      if ( *(_DWORD *)(a1 + 48) )
      {
        if ( (int)UIntPtrToLong(5u, (int *)FatTime) >= 0 )
        {
          v8 = *(_DWORD *)(a2 + 4);
          if ( v8 < 0 )
            goto LABEL_81;
          v11 = *(int *)FatTime;
          if ( *(_DWORD *)FatTime <= 0x4000000u )
          {
            if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                        a2,
                        (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
            {
              v12 = L" and ";
              goto LABEL_28;
            }
LABEL_21:
            v8 = *(_DWORD *)(a2 + 4);
LABEL_30:
            if ( v8 < 0 )
              goto LABEL_81;
            goto LABEL_31;
          }
        }
      }
      else if ( (int)UIntPtrToLong(4u, (int *)FatTime) >= 0 )
      {
        v8 = *(_DWORD *)(a2 + 4);
        if ( v8 < 0 )
          goto LABEL_81;
        v11 = *(int *)FatTime;
        if ( *(_DWORD *)FatTime <= 0x4000000u )
        {
          if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                      a2,
                      (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) < 0 )
            goto LABEL_21;
          v12 = L" or ";
LABEL_28:
          memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), v12, 2 * v11);
          CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v11 + *(_DWORD *)(a2 + 8)));
          v8 = 0;
          goto LABEL_30;
        }
      }
      v8 = -2147024785;
      *(_DWORD *)(a2 + 4) = -2147024785;
      goto LABEL_30;
    }
LABEL_31:
    v13 = *(_WORD **)(a4 + 8LL * v10 + 24);
    *(_DWORD *)FatTime = -1;
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( v13[v14] );
      if ( (int)UIntPtrToLong(v14, (int *)FatTime) < 0 )
        goto LABEL_80;
      v8 = *(_DWORD *)(a2 + 4);
      if ( v8 < 0 )
        goto LABEL_81;
      v15 = *(int *)FatTime;
      if ( *(_DWORD *)FatTime > 0x4000000u )
      {
        *(_DWORD *)(a2 + 4) = -2147024785;
        v8 = -2147024785;
      }
      else if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                       a2,
                       (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
      {
        memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), v13, 2 * v15);
        CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v15 + *(_DWORD *)(a2 + 8)));
        v8 = 0;
      }
      else
      {
        v8 = *(_DWORD *)(a2 + 4);
      }
      if ( v8 < 0 )
        goto LABEL_81;
    }
    v8 = CMFBaseStringT<unsigned short>::Append(a2, &v31);
    if ( v8 < 0 )
      goto LABEL_81;
    v16 = (_WORD *)(a1 + 24);
    if ( *(_WORD *)(a1 + 24) == 1 )
      goto LABEL_81;
    *(_DWORD *)FatTime = -1;
    if ( (int)UIntPtrToLong(1u, (int *)FatTime) < 0 )
      goto LABEL_50;
    v8 = *(_DWORD *)(a2 + 4);
    if ( v8 < 0 )
      goto LABEL_81;
    v17 = *(int *)FatTime;
    if ( *(_DWORD *)FatTime > 0x4000000u )
    {
LABEL_50:
      v8 = -2147024785;
      *(_DWORD *)(a2 + 4) = -2147024785;
    }
    else if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                     a2,
                     (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
    {
      memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), L"\"", 2 * v17);
      CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v17 + *(_DWORD *)(a2 + 8)));
      v8 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a2 + 4);
    }
    if ( v8 >= 0 )
    {
      if ( *v16 == 11 )
      {
        v18 = L"true";
        if ( *(_WORD *)(a1 + 32) != 0xFFFF )
          v18 = L"false";
        v19 = StringCchPrintfW(psz, 0x400u, v18);
      }
      else if ( *v16 == 64 )
      {
        FatDate = 0;
        FatTime[0] = 0;
        if ( !FileTimeToDosDateTime((const FILETIME *)(a1 + 32), &FatDate, FatTime) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_81;
        }
        LODWORD(v28) = FatDate & 0x1F;
        LODWORD(v27) = (FatDate >> 5) & 0xF;
        v19 = StringCchPrintfW(psz, 0x400u, L"%d-%02d-%02d", (FatDate >> 9) + 1980, v27, v28);
      }
      else
      {
        v8 = PropVariantToString((const PROPVARIANT *const)(a1 + 24), psz, 0x400u);
        if ( v8 < 0 )
          goto LABEL_81;
        v19 = CSearchQueryMapping::AddBackSlashToBackSlach(psz, v21);
      }
      v8 = v19;
      if ( v19 >= 0 )
      {
        *(_DWORD *)FatTime = -1;
        v22 = -1;
        do
          ++v22;
        while ( psz[v22] );
        if ( (int)UIntPtrToLong(v22, (int *)FatTime) < 0 )
          goto LABEL_80;
        v8 = *(_DWORD *)(a2 + 4);
        if ( v8 >= 0 )
        {
          v23 = *(int *)FatTime;
          if ( *(_DWORD *)FatTime > 0x4000000u )
            goto LABEL_80;
          if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                      a2,
                      (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
          {
            memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), psz, 2 * v23);
            CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v23 + *(_DWORD *)(a2 + 8)));
          }
          else
          {
            v8 = *(_DWORD *)(a2 + 4);
            if ( v8 < 0 )
              goto LABEL_81;
          }
          *(_DWORD *)FatTime = -1;
          if ( (int)UIntPtrToLong(1u, (int *)FatTime) < 0 )
            goto LABEL_80;
          v8 = *(_DWORD *)(a2 + 4);
          if ( v8 >= 0 )
          {
            v24 = *(int *)FatTime;
            if ( *(_DWORD *)FatTime <= 0x4000000u )
            {
              if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(
                          a2,
                          (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
              {
                memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), L"\"", 2 * v24);
                CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v24 + *(_DWORD *)(a2 + 8)));
                v8 = 0;
              }
              else
              {
                v8 = *(_DWORD *)(a2 + 4);
              }
              goto LABEL_81;
            }
LABEL_80:
            *(_DWORD *)(a2 + 4) = -2147024785;
            v8 = -2147024785;
          }
        }
      }
    }
LABEL_81:
    if ( ++v10 >= 6 )
      break;
  }
  if ( *(_QWORD *)(a4 + 40) && v8 >= 0 )
  {
    *(_DWORD *)FatTime = -1;
    if ( (int)UIntPtrToLong(1u, (int *)FatTime) < 0 )
      goto LABEL_90;
    v8 = *(_DWORD *)(a2 + 4);
    if ( v8 < 0 )
      goto LABEL_91;
    v25 = *(int *)FatTime;
    if ( *(_DWORD *)FatTime > 0x4000000u )
    {
LABEL_90:
      v8 = -2147024785;
      *(_DWORD *)(a2 + 4) = -2147024785;
      goto LABEL_91;
    }
    if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(a2, (unsigned int)(*(_DWORD *)FatTime + *(_DWORD *)(a2 + 8))) >= 0 )
    {
      memcpy_0((void *)(*(_QWORD *)(a2 + 16) + 2LL * *(int *)(a2 + 8)), L")", 2 * v25);
      CMFBaseStringT<unsigned short>::ReleaseBuffer(a2, (unsigned int)(v25 + *(_DWORD *)(a2 + 8)));
      v8 = 0;
    }
    else
    {
      v8 = *(_DWORD *)(a2 + 4);
    }
  }
LABEL_91:
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v31);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800296d8  mov     [rsp-8+arg_10], rbx
0x1800296dd  push    rbp
0x1800296de  push    rsi
0x1800296df  push    rdi
0x1800296e0  push    r12
0x1800296e2  push    r13
0x1800296e4  push    r14
0x1800296e6  push    r15
0x1800296e8  lea     rbp, [rsp-770h]
0x1800296f0  sub     rsp, 870h
0x1800296f7  mov     rax, cs:__security_cookie
0x1800296fe  xor     rax, rsp
0x180029701  mov     [rbp+7A0h+var_40], rax
0x180029708  and     [rsp+8A0h+var_860], 0FFFFFFF8h
0x18002970d  xor     r13d, r13d
0x180029710  mov     r12, r9
0x180029713  mov     [rsp+8A0h+var_85C], r13
0x180029718  mov     rdi, rdx
0x18002971b  mov     [rsp+8A0h+var_850], r13
0x180029720  mov     r15, rcx
0x180029723  mov     [rsp+8A0h+var_854], r13d
0x180029728  mov     r9d, 8007006Fh
0x18002972e  cmp     [r12+28h], r13
0x180029733  jz      loc_1800297C1
0x180029739  lea     rdx, [rsp+8A0h+FatTime]; int *
0x18002973e  mov     dword ptr [rsp+8A0h+FatTime], 0FFFFFFFFh
0x180029746  lea     ecx, [r13+1]; unsigned __int64
0x18002974a  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002974f  test    eax, eax
0x180029751  jns     short loc_18002975C
0x180029753  mov     [rdi+4], r9d
0x180029757  mov     ebx, r9d
0x18002975a  jmp     short loc_1800297DA
0x18002975c  mov     ebx, [rdi+4]
0x18002975f  test    ebx, ebx
0x180029761  js      short loc_1800297DA
0x180029763  movsxd  rbx, dword ptr [rsp+8A0h+FatTime]
0x180029768  cmp     ebx, 4000000h
0x18002976e  ja      short loc_1800297B6
0x180029770  mov     edx, [rdi+8]
0x180029773  mov     rcx, rdi
0x180029776  add     edx, ebx
0x180029778  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002977d  test    eax, eax
0x18002977f  jns     short loc_180029786
0x180029781  mov     ebx, [rdi+4]
0x180029784  jmp     short loc_1800297BD
0x180029786  movsxd  rcx, dword ptr [rdi+8]
0x18002978a  lea     rdx, asc_18003D42C; "("
0x180029791  mov     rax, [rdi+10h]
0x180029795  mov     r8, rbx
0x180029798  add     r8, r8; Size
0x18002979b  lea     rcx, [rax+rcx*2]; void *
0x18002979f  call    memcpy_0
0x1800297a4  mov     edx, [rdi+8]
0x1800297a7  mov     rcx, rdi
0x1800297aa  add     edx, ebx
0x1800297ac  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x1800297b1  mov     ebx, r13d
0x1800297b4  jmp     short loc_1800297BD
0x1800297b6  mov     [rdi+4], r9d
0x1800297ba  mov     ebx, r9d
0x1800297bd  test    ebx, ebx
0x1800297bf  js      short loc_1800297DA
0x1800297c1  movzx   r8d, word ptr [r15+18h]
0x1800297c6  lea     r9, [rsp+8A0h+var_860]
0x1800297cb  mov     edx, [r15+30h]
0x1800297cf  mov     ecx, [r15+14h]
0x1800297d3  call    ?OpMapping@CSearchQueryMapping@@KAJW4tagCONDITION_OPERATION@@HGPEAV?$CMFBaseStringT@G@@@Z; CSearchQueryMapping::OpMapping(tagCONDITION_OPERATION,int,ushort,CMFBaseStringT<ushort> *)
0x1800297d8  mov     ebx, eax
0x1800297da  mov     r14d, r13d
0x1800297dd  mov     esi, r14d
0x1800297e0  cmp     [r12+rsi*8+18h], r13
0x1800297e5  jz      loc_180029C37
0x1800297eb  test    ebx, ebx
0x1800297ed  js      loc_180029C37
0x1800297f3  test    r14d, r14d
0x1800297f6  jz      loc_1800298D5
0x1800297fc  lea     rdx, [rsp+8A0h+FatTime]; int *
0x180029801  mov     dword ptr [rsp+8A0h+FatTime], 0FFFFFFFFh
0x180029809  cmp     [r15+30h], r13d
0x18002980d  jnz     short loc_18002985C
0x18002980f  mov     ecx, 4; unsigned __int64
0x180029814  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180029819  test    eax, eax
0x18002981b  js      loc_1800298C3
0x180029821  mov     ebx, [rdi+4]
0x180029824  test    ebx, ebx
0x180029826  js      loc_180029C2A
0x18002982c  movsxd  rbx, dword ptr [rsp+8A0h+FatTime]
0x180029831  cmp     ebx, 4000000h
0x180029837  ja      loc_1800298C3
0x18002983d  mov     edx, [rdi+8]
0x180029840  mov     rcx, rdi
0x180029843  add     edx, ebx
0x180029845  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002984a  test    eax, eax
0x18002984c  jns     short loc_180029853
0x18002984e  mov     ebx, [rdi+4]
0x180029851  jmp     short loc_1800298CD
0x180029853  lea     rdx, aOr_0; " or "
0x18002985a  jmp     short loc_18002989A
0x18002985c  mov     ecx, 5; unsigned __int64
0x180029861  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180029866  test    eax, eax
0x180029868  js      short loc_1800298C3
0x18002986a  mov     ebx, [rdi+4]
0x18002986d  test    ebx, ebx
0x18002986f  js      loc_180029C2A
0x180029875  movsxd  rbx, dword ptr [rsp+8A0h+FatTime]
0x18002987a  cmp     ebx, 4000000h
0x180029880  ja      short loc_1800298C3
0x180029882  mov     edx, [rdi+8]
0x180029885  mov     rcx, rdi
0x180029888  add     edx, ebx
0x18002988a  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002988f  test    eax, eax
0x180029891  js      short loc_18002984E
0x180029893  lea     rdx, aAnd_0; " and "
0x18002989a  movsxd  rcx, dword ptr [rdi+8]
0x18002989e  mov     r8, rbx
0x1800298a1  mov     rax, [rdi+10h]
0x1800298a5  add     r8, r8; Size
0x1800298a8  lea     rcx, [rax+rcx*2]; void *
0x1800298ac  call    memcpy_0
0x1800298b1  mov     edx, [rdi+8]
0x1800298b4  mov     rcx, rdi
0x1800298b7  add     edx, ebx
0x1800298b9  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x1800298be  mov     ebx, r13d
0x1800298c1  jmp     short loc_1800298CD
0x1800298c3  mov     eax, 8007006Fh
0x1800298c8  mov     ebx, eax
0x1800298ca  mov     [rdi+4], eax
0x1800298cd  test    ebx, ebx
0x1800298cf  js      loc_180029C2A
0x1800298d5  mov     rsi, [r12+rsi*8+18h]
0x1800298da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800298de  mov     dword ptr [rsp+8A0h+FatTime], eax
0x1800298e2  test    rsi, rsi
0x1800298e5  jz      loc_180029976
0x1800298eb  mov     rcx, rax
0x1800298ee  inc     rcx; unsigned __int64
0x1800298f1  cmp     [rsi+rcx*2], r13w
0x1800298f6  jnz     short loc_1800298EE
0x1800298f8  lea     rdx, [rsp+8A0h+FatTime]; int *
0x1800298fd  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180029902  test    eax, eax
0x180029904  js      loc_180029C20
0x18002990a  mov     ebx, [rdi+4]
0x18002990d  test    ebx, ebx
0x18002990f  js      loc_180029C2A
0x180029915  movsxd  rbx, dword ptr [rsp+8A0h+FatTime]
0x18002991a  cmp     ebx, 4000000h
0x180029920  ja      short loc_180029964
0x180029922  mov     edx, [rdi+8]
0x180029925  mov     rcx, rdi
0x180029928  add     edx, ebx
0x18002992a  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002992f  test    eax, eax
0x180029931  jns     short loc_180029938
0x180029933  mov     ebx, [rdi+4]
0x180029936  jmp     short loc_18002996E
0x180029938  movsxd  rcx, dword ptr [rdi+8]
0x18002993c  mov     r8, rbx
0x18002993f  mov     rax, [rdi+10h]
0x180029943  add     r8, r8; Size
0x180029946  mov     rdx, rsi; Src
0x180029949  lea     rcx, [rax+rcx*2]; void *
0x18002994d  call    memcpy_0
0x180029952  mov     edx, [rdi+8]
0x180029955  mov     rcx, rdi
0x180029958  add     edx, ebx
0x18002995a  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18002995f  mov     ebx, r13d
0x180029962  jmp     short loc_18002996E
0x180029964  mov     eax, 8007006Fh
0x180029969  mov     [rdi+4], eax
0x18002996c  mov     ebx, eax
0x18002996e  test    ebx, ebx
0x180029970  js      loc_180029C2A
0x180029976  lea     rdx, [rsp+8A0h+var_860]
0x18002997b  mov     rcx, rdi
0x18002997e  call    ?Append@?$CMFBaseStringT@G@@QEAAJAEAV1@@Z; CMFBaseStringT<ushort>::Append(CMFBaseStringT<ushort> &)
0x180029983  mov     ebx, eax
0x180029985  test    eax, eax
0x180029987  js      loc_180029C2A
0x18002998d  lea     rsi, [r15+18h]
0x180029991  mov     eax, 1
0x180029996  cmp     ax, [rsi]
0x180029999  jz      loc_180029C2A
0x18002999f  lea     rdx, [rsp+8A0h+FatTime]; int *
0x1800299a4  mov     dword ptr [rsp+8A0h+FatTime], 0FFFFFFFFh
0x1800299ac  mov     ecx, eax; unsigned __int64
0x1800299ae  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x1800299b3  test    eax, eax
0x1800299b5  js      short loc_180029A15
0x1800299b7  mov     ebx, [rdi+4]
0x1800299ba  test    ebx, ebx
0x1800299bc  js      loc_180029C2A
0x1800299c2  movsxd  rbx, dword ptr [rsp+8A0h+FatTime]
0x1800299c7  cmp     ebx, 4000000h
0x1800299cd  ja      short loc_180029A15
0x1800299cf  mov     edx, [rdi+8]
0x1800299d2  mov     rcx, rdi
0x1800299d5  add     edx, ebx
0x1800299d7  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x1800299dc  test    eax, eax
0x1800299de  jns     short loc_1800299E5
0x1800299e0  mov     ebx, [rdi+4]
0x1800299e3  jmp     short loc_180029A1F
0x1800299e5  movsxd  rcx, dword ptr [rdi+8]
0x1800299e9  lea     rdx, asc_18003C610; "\""
0x1800299f0  mov     rax, [rdi+10h]
0x1800299f4  mov     r8, rbx
0x1800299f7  add     r8, r8; Size
0x1800299fa  lea     rcx, [rax+rcx*2]; void *
0x1800299fe  call    memcpy_0
0x180029a03  mov     edx, [rdi+8]
0x180029a06  mov     rcx, rdi
0x180029a09  add     edx, ebx
0x180029a0b  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x180029a10  mov     ebx, r13d
0x180029a13  jmp     short loc_180029A1F
0x180029a15  mov     eax, 8007006Fh
0x180029a1a  mov     ebx, eax
0x180029a1c  mov     [rdi+4], eax
0x180029a1f  test    ebx, ebx
0x180029a21  js      loc_180029C2A
0x180029a27  mov     eax, 0Bh
0x180029a2c  cmp     ax, [rsi]
0x180029a2f  jnz     short loc_180029A60
0x180029a31  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180029a35  lea     rax, aFalse; "false"
0x180029a3c  cmp     si, [r15+20h]
0x180029a41  lea     r8, aTrue; "true"
0x180029a48  mov     edx, 400h; unsigned __int64
0x180029a4d  lea     rcx, [rsp+8A0h+psz]; unsigned __int16 *
0x180029a52  cmovnz  r8, rax; unsigned __int16 *
0x180029a56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029a5b  jmp     loc_180029B1B
0x180029a60  mov     eax, 40h ; '@'
0x180029a65  cmp     ax, [rsi]
0x180029a68  jnz     loc_180029AEF
0x180029a6e  lea     rcx, [rsi+8]; lpFileTime
0x180029a72  mov     [rsp+8A0h+FatDate], r13w
0x180029a78  lea     r8, [rsp+8A0h+FatTime]; lpFatTime
0x180029a7d  mov     [rsp+8A0h+FatTime], r13w
0x180029a83  lea     rdx, [rsp+8A0h+FatDate]; lpFatDate
0x180029a88  call    cs:__imp_FileTimeToDosDateTime
0x180029a8e  test    eax, eax
0x180029a90  jnz     short loc_180029AAF
0x180029a92  call    cs:__imp_GetLastError
0x180029a98  mov     ebx, eax
0x180029a9a  test    eax, eax
0x180029a9c  jle     short loc_180029AA7
0x180029a9e  movzx   ebx, ax
0x180029aa1  or      ebx, 80070000h
0x180029aa7  test    ebx, ebx
0x180029aa9  js      loc_180029C2A
0x180029aaf  movzx   r9d, [rsp+8A0h+FatDate]
0x180029ab5  lea     r8, aD02d02d; "%d-%02d-%02d"
0x180029abc  mov     ecx, r9d
0x180029abf  mov     eax, r9d
0x180029ac2  and     ecx, 1Fh
0x180029ac5  shr     eax, 5
0x180029ac8  mov     dword ptr [rsp+8A0h+var_878], ecx
0x180029acc  and     eax, 0Fh
0x180029acf  shr     r9d, 9
0x180029ad3  lea     rcx, [rsp+8A0h+psz]; unsigned __int16 *
0x180029ad8  add     r9d, 7BCh
0x180029adf  mov     dword ptr [rsp+8A0h+var_880], eax
0x180029ae3  mov     edx, 400h; unsigned __int64
0x180029ae8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029aed  jmp     short loc_180029B17
0x180029aef  mov     r8d, 400h; cch
0x180029af5  lea     rdx, [rsp+8A0h+psz]; psz
0x180029afa  mov     rcx, rsi; propvar
0x180029afd  call    cs:__imp_PropVariantToString
0x180029b03  mov     ebx, eax
0x180029b05  test    eax, eax
0x180029b07  js      loc_180029C2A
0x180029b0d  lea     rcx, [rsp+8A0h+psz]; unsigned __int16 *
0x180029b12  call    ?AddBackSlashToBackSlach@CSearchQueryMapping@@SAJPEAGK@Z; CSearchQueryMapping::AddBackSlashToBackSlach(ushort *,ulong)
0x180029b17  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180029b1b  mov     ebx, eax
0x180029b1d  test    eax, eax
0x180029b1f  js      loc_180029C2A
0x180029b25  mov     dword ptr [rsp+8A0h+FatTime], esi
0x180029b29  lea     rax, [rsp+8A0h+psz]
0x180029b2e  mov     rcx, rsi
0x180029b31  inc     rcx; unsigned __int64
0x180029b34  cmp     [rax+rcx*2], r13w
0x180029b39  jnz     short loc_180029B31
0x180029b3b  lea     rdx, [rsp+8A0h+FatTime]; int *
0x180029b40  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x180029b45  test    eax, eax
0x180029b47  js      loc_180029C20
0x180029b4d  mov     ebx, [rdi+4]
0x180029b50  test    ebx, ebx
  ... truncated ...
```
