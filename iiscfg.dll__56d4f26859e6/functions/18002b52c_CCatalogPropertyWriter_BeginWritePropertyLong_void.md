# CCatalogPropertyWriter::BeginWritePropertyLong(void)

- ea: `0x18002b52c`
- end: `0x18002bb4b`
- name: `?BeginWritePropertyLong@CCatalogPropertyWriter@@AEAAJXZ`
- size: `1567`
- prototype: `__int64 __fastcall(CCatalogPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18002bda0`

## callees

- `0x18002ac94`
- `0x18002b52c`
- `0x18002c604`
- `0x18002cdb8`
- `0x18002d934`
- `0x18002e110`

## import_xrefs

- `msvcrt!_ultow` at `0x18002b60d`
- `msvcrt!_ultow` at `0x18002b9eb`
- `msvcrt!_ultow` at `0x18002ba5b`
- `msvcrt!_ultow` at `0x18002b60d`
- `msvcrt!_ultow` at `0x18002b9eb`
- `msvcrt!_ultow` at `0x18002ba5b`
- `ole32!CoTaskMemFree` at `0x18002baeb`
- `ole32!CoTaskMemFree` at `0x18002baf9`
- `ole32!CoTaskMemFree` at `0x18002bb07`
- `ole32!CoTaskMemFree` at `0x18002bb15`
- `ole32!CoTaskMemFree` at `0x18002bb23`
- `ole32!CoTaskMemFree` at `0x18002baeb`
- `ole32!CoTaskMemFree` at `0x18002baf9`
- `ole32!CoTaskMemFree` at `0x18002bb07`
- `ole32!CoTaskMemFree` at `0x18002bb15`
- `ole32!CoTaskMemFree` at `0x18002bb23`

## pseudocode

```c
__int64 __fastcall CCatalogPropertyWriter::BeginWritePropertyLong(CCatalogPropertyWriter *this)
{
  CWriter *v2; // rcx
  unsigned __int16 *v3; // r12
  unsigned __int16 *v4; // r13
  unsigned __int16 *v5; // r15
  unsigned __int16 *v6; // r14
  int UserType; // ebx
  char *v8; // rdx
  __int64 v9; // rsi
  __int64 v10; // r8
  unsigned int *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // r8
  char *v15; // rdx
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // edx
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // edx
  int v22; // eax
  __int64 v23; // r8
  _DWORD *v24; // rcx
  int v25; // eax
  int v26; // ecx
  int v27; // eax
  __int64 v28; // r8
  _DWORD *v29; // rax
  unsigned int *v30; // rax
  __int64 v31; // r8
  unsigned int *v32; // rax
  CWriterGlobalHelper *v34; // [rsp+20h] [rbp-E0h]
  unsigned int v35; // [rsp+28h] [rbp-D8h]
  unsigned int v36; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v41; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Buffer[40]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v44[40]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t v45[40]; // [rsp+110h] [rbp+10h] BYREF

  v2 = *(CWriter **)this;
  pv = 0;
  v3 = 0;
  v36 = 0;
  v4 = 0;
  v37 = 0;
  v5 = 0;
  v41 = 0;
  v6 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  UserType = CWriter::WriteToFile(v2, (char *)L"\t\t\t<Property       InternalName =\"", g_cchBeginPropertyLong, 0);
  if ( UserType >= 0 )
  {
    v8 = (char *)*((_QWORD *)this + 3);
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&v8[2 * v10] );
    UserType = CWriter::WriteToFile(*(CWriter **)this, v8, v10, 0);
    if ( UserType >= 0 )
    {
      UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"\t\t\tID=\"", g_cchPropIDEq, 0);
      if ( UserType >= 0 )
      {
        v11 = (unsigned int *)*((_QWORD *)this + 14);
        Buffer[0] = 0;
        _ultow(*v11, Buffer, 10);
        v12 = -1;
        do
          ++v12;
        while ( Buffer[v12] );
        UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)Buffer, v12, 0);
        if ( UserType >= 0 )
        {
          UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"\t\t\tType=\"", g_cchPropTypeEq, 0);
          if ( UserType >= 0 )
          {
            v13 = (**((_DWORD **)this + 13) >> 2) & 0xF;
            if ( (unsigned int)(v13 - 1) > 0xB )
            {
              UserType = -2147024809;
            }
            else
            {
              v14 = -1;
              v15 = (char *)(&g_aSynIDToWszType)[v13];
              do
                ++v14;
              while ( *(_WORD *)&v15[2 * v14] );
              UserType = CWriter::WriteToFile(*(CWriter **)this, v15, v14, 0);
              if ( UserType < 0 )
                return (unsigned int)UserType;
              UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)L"\"\t\t\tUserType=\"", g_cchPropUserTypeEq, 0);
              if ( UserType < 0 )
                return (unsigned int)UserType;
              UserType = CWriterGlobalHelper::GetUserType(
                           *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                           **((_DWORD **)this + 15),
                           (unsigned __int16 **)&pv,
                           &v36,
                           &v37);
              if ( UserType >= 0 )
              {
                UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)pv, v36, 0);
                if ( UserType >= 0 )
                {
                  v16 = CWriterGlobalHelper::FlagToString(
                          *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                          **((_DWORD **)this + 16),
                          &v41,
                          L"COLUMNMETA",
                          0xFu);
                  v3 = v41;
                  UserType = v16;
                  if ( v16 >= 0 )
                  {
                    if ( !v41 )
                      goto LABEL_23;
                    UserType = CWriter::WriteToFile(
                                 *(CWriter **)this,
                                 (char *)L"\"\t\t\tAttributes=\"",
                                 g_cchPropAttributeEq,
                                 0);
                    if ( UserType >= 0 )
                    {
                      v17 = -1;
                      do
                        ++v17;
                      while ( v3[v17] );
                      UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v3, v17, 0);
                      if ( UserType >= 0 )
                      {
LABEL_23:
                        v18 = **((_DWORD **)this + 7) & 0x61C77F11;
                        if ( !v18 )
                          goto LABEL_84;
                        v19 = CWriterGlobalHelper::FlagToString(
                                *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                                v18,
                                &v38,
                                L"COLUMNMETA",
                                6u);
                        v4 = v38;
                        UserType = v19;
                        if ( v19 >= 0 )
                        {
                          if ( !v38 )
                            goto LABEL_84;
                          UserType = CWriter::WriteToFile(
                                       *(CWriter **)this,
                                       (char *)L"\"\t\t\tMetaFlags=\"",
                                       g_cchPropMetaFlagsEq,
                                       0);
                          if ( UserType >= 0 )
                          {
                            v20 = -1;
                            do
                              ++v20;
                            while ( v4[v20] );
                            UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v4, v20, 0);
                            if ( UserType >= 0 )
                            {
LABEL_84:
                              v21 = **((_DWORD **)this + 13) & 0x102C3;
                              if ( !v21 )
                                goto LABEL_85;
                              v22 = CWriterGlobalHelper::FlagToString(
                                      *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                                      v21,
                                      &v39,
                                      L"COLUMNMETA",
                                      0xCu);
                              v5 = v39;
                              UserType = v22;
                              if ( v22 >= 0 )
                              {
                                if ( !v39 )
                                  goto LABEL_85;
                                UserType = CWriter::WriteToFile(
                                             *(CWriter **)this,
                                             (char *)L"\"\t\t\tMetaFlagsEx=\"",
                                             g_cchPropMetaFlagsExEq,
                                             0);
                                if ( UserType >= 0 )
                                {
                                  v23 = -1;
                                  do
                                    ++v23;
                                  while ( v5[v23] );
                                  UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v5, v23, 0);
                                  if ( UserType >= 0 )
                                  {
LABEL_85:
                                    if ( !*((_QWORD *)this + 8) )
                                      goto LABEL_53;
                                    v24 = (_DWORD *)*((_QWORD *)this + 5);
                                    switch ( *v24 )
                                    {
                                      case 0x13:
                                        v25 = 1;
                                        break;
                                      case 0x80:
                                        v25 = 3;
                                        break;
                                      case 0x82:
                                        v26 = **((_DWORD **)this + 7);
                                        v25 = (v26 & 0x4000000) != 0 ? 4 : (v26 & 0x2000000) != 0 ? 5 : 2;
                                        break;
                                      default:
                                        v25 = 0;
                                        break;
                                    }
                                    LODWORD(v34) = v25;
                                    v27 = CWriterGlobalHelper::ToString(
                                            *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                                            *((unsigned __int8 **)this + 8),
                                            *((_DWORD *)this + 45),
                                            **((_DWORD **)this + 14),
                                            v34,
                                            v35,
                                            &v40);
                                    v6 = v40;
                                    UserType = v27;
                                    if ( v27 >= 0 )
                                    {
                                      if ( !v40 )
                                        goto LABEL_53;
                                      UserType = CWriter::WriteToFile(
                                                   *(CWriter **)this,
                                                   (char *)L"\"\t\t\tDefaultValue=\"",
                                                   g_cchPropDefaultEq,
                                                   0);
                                      if ( UserType >= 0 )
                                      {
                                        v28 = -1;
                                        do
                                          ++v28;
                                        while ( v6[v28] );
                                        UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v6, v28, 0);
                                        if ( UserType >= 0 )
                                        {
LABEL_53:
                                          v29 = (_DWORD *)*((_QWORD *)this + 5);
                                          v44[0] = 0;
                                          v45[0] = 0;
                                          if ( *v29 != 19 )
                                            goto LABEL_82;
                                          v30 = (unsigned int *)*((_QWORD *)this + 10);
                                          if ( !v30 )
                                            goto LABEL_83;
                                          if ( !*v30 )
                                            goto LABEL_83;
                                          _ultow(*v30, v44, 10);
                                          UserType = CWriter::WriteToFile(
                                                       *(CWriter **)this,
                                                       (char *)L"\"\t\t\tStartingNumber=\"",
                                                       g_cchPropMinValueEq,
                                                       0);
                                          if ( UserType >= 0 )
                                          {
                                            v31 = -1;
                                            do
                                              ++v31;
                                            while ( v44[v31] );
                                            UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v44, v31, 0);
                                            if ( UserType >= 0 )
                                            {
LABEL_83:
                                              v32 = (unsigned int *)*((_QWORD *)this + 11);
                                              if ( !v32 || *v32 == -1 )
                                                goto LABEL_82;
                                              _ultow(*v32, v45, 10);
                                              UserType = CWriter::WriteToFile(
                                                           *(CWriter **)this,
                                                           (char *)L"\"\t\t\tEndingNumber=\"",
                                                           g_cchPropMaxValueEq,
                                                           0);
                                              if ( UserType >= 0 )
                                              {
                                                do
                                                  ++v9;
                                                while ( v45[v9] );
                                                UserType = CWriter::WriteToFile(*(CWriter **)this, (char *)v45, v9, 0);
                                                if ( UserType >= 0 )
                                                {
LABEL_82:
                                                  if ( *((_QWORD *)this + 29) )
                                                    UserType = CWriter::WriteToFile(
                                                                 *(CWriter **)this,
                                                                 (char *)L"\">\r\n",
                                                                 g_cchEndPropertyLongBeforeFlag,
                                                                 0);
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            if ( pv && v37 )
              CoTaskMemFree(pv);
            if ( v3 )
              CoTaskMemFree(v3);
            if ( v4 )
              CoTaskMemFree(v4);
            if ( v5 )
              CoTaskMemFree(v5);
            if ( v6 )
              CoTaskMemFree(v6);
          }
        }
      }
    }
  }
  return (unsigned int)UserType;
}

```

## disassembly

```asm
0x18002b52c  push    rbp
0x18002b52e  push    rbx
0x18002b52f  push    rsi
0x18002b530  push    rdi
0x18002b531  push    r12
0x18002b533  push    r13
0x18002b535  push    r14
0x18002b537  push    r15
0x18002b539  lea     rbp, [rsp-78h]
0x18002b53e  sub     rsp, 178h
0x18002b545  mov     rax, cs:__security_cookie
0x18002b54c  xor     rax, rsp
0x18002b54f  mov     [rbp+0B0h+var_50], rax
0x18002b553  mov     r8d, cs:?g_cchBeginPropertyLong@@3KA; unsigned int
0x18002b55a  lea     rdx, aPropertyIntern; "\t\t\t<Property       InternalName =\""
0x18002b561  xor     esi, esi
0x18002b563  mov     rdi, rcx
0x18002b566  mov     rcx, [rcx]; this
0x18002b569  xor     r9d, r9d; int
0x18002b56c  mov     [rsp+1B0h+pv], rsi
0x18002b571  mov     r12d, esi
0x18002b574  mov     [rsp+1B0h+var_170], esi
0x18002b578  mov     r13d, esi
0x18002b57b  mov     [rsp+1B0h+var_16C], esi
0x18002b57f  mov     r15d, esi
0x18002b582  mov     [rsp+1B0h+var_150], rsi
0x18002b587  mov     r14d, esi
0x18002b58a  mov     [rsp+1B0h+var_168], rsi
0x18002b58f  mov     [rsp+1B0h+var_160], rsi
0x18002b594  mov     [rsp+1B0h+var_158], rsi
0x18002b599  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b59e  mov     ebx, eax
0x18002b5a0  test    eax, eax
0x18002b5a2  js      loc_18002BB29
0x18002b5a8  mov     rdx, [rdi+18h]; void *
0x18002b5ac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002b5b0  mov     r8, rsi
0x18002b5b3  xor     eax, eax
0x18002b5b5  inc     r8; unsigned int
0x18002b5b8  cmp     [rdx+r8*2], ax
0x18002b5bd  jnz     short loc_18002B5B5
0x18002b5bf  mov     rcx, [rdi]; this
0x18002b5c2  xor     r9d, r9d; int
0x18002b5c5  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b5ca  mov     ebx, eax
0x18002b5cc  test    eax, eax
0x18002b5ce  js      loc_18002BB29
0x18002b5d4  mov     r8d, cs:?g_cchPropIDEq@@3KA; unsigned int
0x18002b5db  lea     rdx, aId_0; "\"\t\t\tID=\""
0x18002b5e2  mov     rcx, [rdi]; this
0x18002b5e5  xor     r9d, r9d; int
0x18002b5e8  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b5ed  mov     ebx, eax
0x18002b5ef  xor     eax, eax
0x18002b5f1  test    ebx, ebx
0x18002b5f3  js      loc_18002BB29
0x18002b5f9  mov     rcx, [rdi+70h]
0x18002b5fd  lea     r8d, [rax+0Ah]; Radix
0x18002b601  mov     [rsp+1B0h+Buffer], ax
0x18002b606  lea     rdx, [rsp+1B0h+Buffer]; Buffer
0x18002b60b  mov     ecx, [rcx]; Value
0x18002b60d  call    cs:__imp__ultow
0x18002b613  lea     rcx, [rsp+1B0h+Buffer]
0x18002b618  mov     r8, rsi
0x18002b61b  xor     eax, eax
0x18002b61d  inc     r8; unsigned int
0x18002b620  cmp     [rcx+r8*2], ax
0x18002b625  jnz     short loc_18002B61D
0x18002b627  mov     rcx, [rdi]; this
0x18002b62a  lea     rdx, [rsp+1B0h+Buffer]; void *
0x18002b62f  xor     r9d, r9d; int
0x18002b632  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b637  mov     ebx, eax
0x18002b639  test    eax, eax
0x18002b63b  js      loc_18002BB29
0x18002b641  mov     r8d, cs:?g_cchPropTypeEq@@3KA; unsigned int
0x18002b648  lea     rdx, aType; "\"\t\t\tType=\""
0x18002b64f  mov     rcx, [rdi]; this
0x18002b652  xor     r9d, r9d; int
0x18002b655  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b65a  xor     r9d, r9d; int
0x18002b65d  mov     ebx, eax
0x18002b65f  test    eax, eax
0x18002b661  js      loc_18002BB29
0x18002b667  mov     rax, [rdi+68h]
0x18002b66b  mov     ecx, [rax]
0x18002b66d  shr     ecx, 2
0x18002b670  and     ecx, 0Fh
0x18002b673  lea     eax, [rcx-1]
0x18002b676  cmp     eax, 0Bh
0x18002b679  ja      loc_18002BAD2
0x18002b67f  lea     rdx, ?g_aSynIDToWszType@@3PAPEBGA; ushort const * near * g_aSynIDToWszType
0x18002b686  mov     r8, rsi
0x18002b689  mov     rdx, [rdx+rcx*8]; void *
0x18002b68d  inc     r8; unsigned int
0x18002b690  cmp     [rdx+r8*2], r9w
0x18002b695  jnz     short loc_18002B68D
0x18002b697  mov     rcx, [rdi]; this
0x18002b69a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b69f  mov     ebx, eax
0x18002b6a1  test    eax, eax
0x18002b6a3  js      loc_18002BB29
0x18002b6a9  mov     r8d, cs:?g_cchPropUserTypeEq@@3KA; unsigned int
0x18002b6b0  lea     rdx, aUsertype_0; "\"\t\t\tUserType=\""
0x18002b6b7  mov     rcx, [rdi]; this
0x18002b6ba  xor     r9d, r9d; int
0x18002b6bd  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b6c2  mov     ebx, eax
0x18002b6c4  test    eax, eax
0x18002b6c6  js      loc_18002BB29
0x18002b6cc  mov     rdx, [rdi+78h]
0x18002b6d0  lea     rax, [rsp+1B0h+var_16C]
0x18002b6d5  mov     rcx, [rdi]
0x18002b6d8  lea     r9, [rsp+1B0h+var_170]; unsigned int *
0x18002b6dd  lea     r8, [rsp+1B0h+pv]; unsigned __int16 **
0x18002b6e2  mov     [rsp+1B0h+var_190], rax; int *
0x18002b6e7  mov     edx, [rdx]; unsigned int
0x18002b6e9  mov     rcx, [rcx+10040h]; this
0x18002b6f0  call    ?GetUserType@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAKPEAH@Z; CWriterGlobalHelper::GetUserType(ulong,ushort * *,ulong *,int *)
0x18002b6f5  xor     r9d, r9d; int
0x18002b6f8  mov     ebx, eax
0x18002b6fa  test    eax, eax
0x18002b6fc  js      loc_18002BAD7
0x18002b702  mov     r8d, [rsp+1B0h+var_170]; unsigned int
0x18002b707  mov     rdx, [rsp+1B0h+pv]; void *
0x18002b70c  mov     rcx, [rdi]; this
0x18002b70f  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b714  xor     r9d, r9d
0x18002b717  mov     ebx, eax
0x18002b719  test    eax, eax
0x18002b71b  js      loc_18002BAD7
0x18002b721  mov     rdx, [rdi+80h]
0x18002b728  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002b72f  mov     rcx, [rdi]
0x18002b732  lea     r8, [rsp+1B0h+var_150]; unsigned __int16 **
0x18002b737  mov     dword ptr [rsp+1B0h+var_190], 0Fh; unsigned int
0x18002b73f  mov     edx, [rdx]; unsigned int
0x18002b741  mov     rcx, [rcx+10040h]; this
0x18002b748  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002b74d  mov     r12, [rsp+1B0h+var_150]
0x18002b752  xor     r9d, r9d; int
0x18002b755  mov     ebx, eax
0x18002b757  test    eax, eax
0x18002b759  js      loc_18002BAD7
0x18002b75f  test    r12, r12
0x18002b762  jz      short loc_18002B7AC
0x18002b764  mov     r8d, cs:?g_cchPropAttributeEq@@3KA; unsigned int
0x18002b76b  lea     rdx, aAttributes; "\"\t\t\tAttributes=\""
0x18002b772  mov     rcx, [rdi]; this
0x18002b775  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b77a  xor     r9d, r9d; int
0x18002b77d  mov     ebx, eax
0x18002b77f  test    eax, eax
0x18002b781  js      loc_18002BAD7
0x18002b787  mov     r8, rsi
0x18002b78a  inc     r8; unsigned int
0x18002b78d  cmp     [r12+r8*2], r9w
0x18002b792  jnz     short loc_18002B78A
0x18002b794  mov     rcx, [rdi]; this
0x18002b797  mov     rdx, r12; void *
0x18002b79a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b79f  xor     r9d, r9d
0x18002b7a2  mov     ebx, eax
0x18002b7a4  test    eax, eax
0x18002b7a6  js      loc_18002BAD7
0x18002b7ac  mov     rax, [rdi+38h]
0x18002b7b0  mov     edx, [rax]
0x18002b7b2  and     edx, 61C77F11h; unsigned int
0x18002b7b8  jz      loc_18002B841
0x18002b7be  mov     rcx, [rdi]
0x18002b7c1  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002b7c8  lea     r8, [rsp+1B0h+var_168]; unsigned __int16 **
0x18002b7cd  mov     dword ptr [rsp+1B0h+var_190], 6; unsigned int
0x18002b7d5  mov     rcx, [rcx+10040h]; this
0x18002b7dc  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002b7e1  mov     r13, [rsp+1B0h+var_168]
0x18002b7e6  xor     r9d, r9d; int
0x18002b7e9  mov     ebx, eax
0x18002b7eb  test    eax, eax
0x18002b7ed  js      loc_18002BAD7
0x18002b7f3  test    r13, r13
0x18002b7f6  jz      short loc_18002B841
0x18002b7f8  mov     r8d, cs:?g_cchPropMetaFlagsEq@@3KA; unsigned int
0x18002b7ff  lea     rdx, aMetaflags_0; "\"\t\t\tMetaFlags=\""
0x18002b806  mov     rcx, [rdi]; this
0x18002b809  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b80e  xor     r9d, r9d; int
0x18002b811  mov     ebx, eax
0x18002b813  test    eax, eax
0x18002b815  js      loc_18002BAD7
0x18002b81b  mov     r8, rsi
0x18002b81e  inc     r8; unsigned int
0x18002b821  cmp     [r13+r8*2+0], r9w
0x18002b827  jnz     short loc_18002B81E
0x18002b829  mov     rcx, [rdi]; this
0x18002b82c  mov     rdx, r13; void *
0x18002b82f  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b834  xor     r9d, r9d
0x18002b837  mov     ebx, eax
0x18002b839  test    eax, eax
0x18002b83b  js      loc_18002BAD7
0x18002b841  mov     rax, [rdi+68h]
0x18002b845  mov     edx, [rax]
0x18002b847  and     edx, 102C3h; unsigned int
0x18002b84d  jz      loc_18002B8D5
0x18002b853  mov     rcx, [rdi]
0x18002b856  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002b85d  lea     r8, [rsp+1B0h+var_160]; unsigned __int16 **
0x18002b862  mov     dword ptr [rsp+1B0h+var_190], 0Ch; unsigned int
0x18002b86a  mov     rcx, [rcx+10040h]; this
0x18002b871  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002b876  mov     r15, [rsp+1B0h+var_160]
0x18002b87b  xor     r9d, r9d; int
0x18002b87e  mov     ebx, eax
0x18002b880  test    eax, eax
0x18002b882  js      loc_18002BAD7
0x18002b888  test    r15, r15
0x18002b88b  jz      short loc_18002B8D5
0x18002b88d  mov     r8d, cs:?g_cchPropMetaFlagsExEq@@3KA; unsigned int
0x18002b894  lea     rdx, aMetaflagsex; "\"\t\t\tMetaFlagsEx=\""
0x18002b89b  mov     rcx, [rdi]; this
0x18002b89e  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b8a3  xor     r9d, r9d; int
0x18002b8a6  mov     ebx, eax
0x18002b8a8  test    eax, eax
0x18002b8aa  js      loc_18002BAD7
0x18002b8b0  mov     r8, rsi
0x18002b8b3  inc     r8; unsigned int
0x18002b8b6  cmp     [r15+r8*2], r9w
0x18002b8bb  jnz     short loc_18002B8B3
0x18002b8bd  mov     rcx, [rdi]; this
0x18002b8c0  mov     rdx, r15; void *
0x18002b8c3  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b8c8  xor     r9d, r9d
0x18002b8cb  mov     ebx, eax
0x18002b8cd  test    eax, eax
0x18002b8cf  js      loc_18002BAD7
0x18002b8d5  cmp     [rdi+40h], r9
0x18002b8d9  jz      loc_18002B9BB
0x18002b8df  mov     rcx, [rdi+28h]
0x18002b8e3  mov     rax, [rdi]
0x18002b8e6  mov     edx, [rcx]
0x18002b8e8  mov     r10, [rax+10040h]
0x18002b8ef  sub     edx, 13h
0x18002b8f2  jz      short loc_18002B92F
0x18002b8f4  sub     edx, 6Dh ; 'm'
0x18002b8f7  jz      short loc_18002B928
0x18002b8f9  cmp     edx, 2
0x18002b8fc  jz      short loc_18002B903
0x18002b8fe  mov     eax, r9d
0x18002b901  jmp     short loc_18002B934
0x18002b903  mov     rax, [rdi+38h]
0x18002b907  mov     ecx, [rax]
0x18002b909  bt      ecx, 1Ah
0x18002b90d  jnb     short loc_18002B916
0x18002b90f  mov     eax, 4
0x18002b914  jmp     short loc_18002B934
0x18002b916  and     ecx, 2000000h
0x18002b91c  neg     ecx
0x18002b91e  sbb     eax, eax
0x18002b920  and     eax, 3
0x18002b923  add     eax, 2
0x18002b926  jmp     short loc_18002B934
0x18002b928  mov     eax, 3
0x18002b92d  jmp     short loc_18002B934
0x18002b92f  mov     eax, 1
0x18002b934  mov     r9, [rdi+70h]
0x18002b938  lea     rcx, [rsp+1B0h+var_158]
0x18002b93d  mov     r8d, [rdi+0B4h]; unsigned int
0x18002b944  mov     rdx, [rdi+40h]; unsigned __int8 *
0x18002b948  mov     [rsp+1B0h+var_180], rcx; unsigned __int16 **
0x18002b94d  mov     rcx, r10; this
0x18002b950  mov     r9d, [r9]; unsigned int
0x18002b953  mov     dword ptr [rsp+1B0h+var_190], eax; CWriterGlobalHelper *
0x18002b957  call    ?ToString@CWriterGlobalHelper@@QEAAJPEAEKKKKPEAPEAG@Z; CWriterGlobalHelper::ToString(uchar *,ulong,ulong,ulong,ulong,ushort * *)
0x18002b95c  mov     r14, [rsp+1B0h+var_158]
0x18002b961  xor     r9d, r9d; int
0x18002b964  mov     ebx, eax
0x18002b966  test    eax, eax
0x18002b968  js      loc_18002BAD7
0x18002b96e  test    r14, r14
0x18002b971  jz      short loc_18002B9BB
0x18002b973  mov     r8d, cs:?g_cchPropDefaultEq@@3KA; unsigned int
0x18002b97a  lea     rdx, aDefaultvalue_0; "\"\t\t\tDefaultValue=\""
0x18002b981  mov     rcx, [rdi]; this
0x18002b984  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b989  xor     r9d, r9d; int
0x18002b98c  mov     ebx, eax
0x18002b98e  test    eax, eax
0x18002b990  js      loc_18002BAD7
0x18002b996  mov     r8, rsi
0x18002b999  inc     r8; unsigned int
0x18002b99c  cmp     [r14+r8*2], r9w
0x18002b9a1  jnz     short loc_18002B999
0x18002b9a3  mov     rcx, [rdi]; this
0x18002b9a6  mov     rdx, r14; void *
0x18002b9a9  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002b9ae  xor     r9d, r9d
0x18002b9b1  mov     ebx, eax
0x18002b9b3  test    eax, eax
  ... truncated ...
```
