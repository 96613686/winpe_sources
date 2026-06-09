# CMBPropertyWriter::BeginWritePropertyLong(void)

- ea: `0x18002fb58`
- end: `0x180030202`
- name: `?BeginWritePropertyLong@CMBPropertyWriter@@AEAAJXZ`
- size: `1706`
- prototype: `__int64 __fastcall(CMBPropertyWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x18003059c`

## callees

- `0x18000674c`
- `0x180006d08`
- `0x180008a08`
- `0x18002bdb4`
- `0x18002c76c`
- `0x18002fb58`
- `0x180030208`
- `0x180030280`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_ultow` at `0x18002fc2e`
- `msvcrt!_ultow` at `0x18002fe79`
- `msvcrt!_ultow` at `0x18002fe95`
- `msvcrt!_ultow` at `0x18002fc2e`
- `msvcrt!_ultow` at `0x18002fe79`
- `msvcrt!_ultow` at `0x18002fe95`
- `msvcrt!wcschr` at `0x18002fbf3`
- `msvcrt!wcschr` at `0x18002fbf3`
- `IisRTL!PuDbgPrintW` at `0x18002fc77`
- `IisRTL!PuDbgPrintW` at `0x18002fd24`
- `IisRTL!PuDbgPrintW` at `0x1800301bd`
- `IisRTL!PuDbgPrintW` at `0x18002fc77`
- `IisRTL!PuDbgPrintW` at `0x18002fd24`
- `IisRTL!PuDbgPrintW` at `0x1800301bd`

## string_xrefs

- `0x18002fc5a`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`
- `0x18002fd0d`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`
- `0x180030187`: `inetsrv\iis\mb\xmlwriter\mbpropertywriter.cpp`
- `0x18002fc6b`: `[BeginWritePropertyLong] Type not found for PropertyID %d.\n`
- `0x18002fc4c`: `CMBPropertyWriter::BeginWritePropertyLong`
- `0x18002fcf6`: `CMBPropertyWriter::BeginWritePropertyLong`
- `0x180030192`: `CMBPropertyWriter::BeginWritePropertyLong`

## pseudocode

```c
__int64 __fastcall CMBPropertyWriter::BeginWritePropertyLong(
        CMBPropertyWriter *this,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  void *v4; // rbx
  __int64 v5; // r14
  unsigned __int16 *v7; // r13
  unsigned __int16 *v8; // r15
  unsigned __int16 *v9; // r12
  __int64 v10; // rsi
  wchar_t *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rdx
  int UserType; // ebx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  unsigned int v18; // edx
  int v19; // eax
  unsigned __int8 *v20; // rdx
  unsigned int v21; // r8d
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  int v29; // edx
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // r8
  CWriterGlobalHelper *v34; // [rsp+20h] [rbp-E0h]
  unsigned int v35; // [rsp+40h] [rbp-C0h] BYREF
  int v36; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  void *v41; // [rsp+68h] [rbp-98h]
  void *v42; // [rsp+70h] [rbp-90h]
  wchar_t Buffer[12]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v44[40]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t v45[40]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v46[40]; // [rsp+130h] [rbp+30h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  v5 = -1;
  Block = 0;
  v35 = 0;
  v36 = 0;
  v7 = 0;
  v39 = 0;
  v8 = 0;
  v37 = 0;
  v9 = 0;
  v38 = 0;
  v41 = v4;
  if ( v4 )
  {
    v11 = wcschr((const wchar_t *)v4, 0x2Cu);
    v12 = *((_QWORD *)this + 1);
    if ( v11 )
    {
      v10 = ((__int64)v11 - v12) >> 1;
    }
    else
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v12 + 2 * v10) );
    }
  }
  else
  {
    CMBPropertyWriter::CreateUnknownName(this, v46, 0x28u, a4);
    v10 = -1;
    v41 = v46;
    do
      ++v10;
    while ( v46[v10] );
  }
  Buffer[0] = 0;
  _ultow(*((_DWORD *)this + 9), Buffer, 10);
  v13 = *((_QWORD *)this + 2);
  if ( !v13 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
        789,
        "CMBPropertyWriter::BeginWritePropertyLong",
        L"[BeginWritePropertyLong] Type not found for PropertyID %d.\n",
        *((_DWORD *)this + 9));
    UserType = -2147023092;
    goto LABEL_78;
  }
  v15 = *(unsigned int *)(v13 + 8);
  if ( (unsigned int)(v15 - 1) > 0xB )
  {
    UserType = -2147024809;
  }
  else
  {
    UserType = 0;
    v42 = (&g_aSynIDToWszType)[v15];
    if ( v42 )
    {
      UserType = CWriterGlobalHelper::GetUserType(
                   *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                   *(_DWORD *)(v13 + 36),
                   (unsigned __int16 **)&Block,
                   &v35,
                   &v36);
      if ( UserType < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
            834,
            "CMBPropertyWriter::BeginWritePropertyLong",
            L"[GetUserType] PropertyID %d, usertype: %d is invalid.\n",
            *((_DWORD *)this + 9),
            *(_DWORD *)(*((_QWORD *)this + 2) + 36LL));
        goto LABEL_19;
      }
      v16 = CWriterGlobalHelper::FlagToString(
              *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
              *(_DWORD *)(*((_QWORD *)this + 2) + 32LL),
              &v39,
              L"COLUMNMETA",
              0xFu);
      v7 = v39;
      UserType = v16;
      if ( v16 >= 0 && v39 )
      {
        v17 = *((_QWORD *)this + 2);
        if ( *(_DWORD *)(v17 + 24) == 1 )
        {
          v18 = 1;
        }
        else
        {
          v18 = 2;
          if ( *(_DWORD *)(v17 + 24) != 2 )
          {
LABEL_30:
            v20 = (unsigned __int8 *)*((_QWORD *)this + 3);
            if ( !v20
              || (v21 = *((_DWORD *)this + 8)) == 0
              || (LODWORD(v34) = dword_1800428D0[*(unsigned int *)(*((_QWORD *)this + 2) + 8LL)],
                  v22 = CWriterGlobalHelper::ToString(
                          *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                          v20,
                          v21,
                          *((_DWORD *)this + 9),
                          v34,
                          0,
                          &v38),
                  v9 = v38,
                  UserType = v22,
                  v22 >= 0) )
            {
              v23 = *((_QWORD *)this + 2);
              v44[0] = 0;
              v45[0] = 0;
              if ( dword_1800428D0[*(unsigned int *)(v23 + 8)] == 1 )
              {
                v24 = *(_DWORD *)(v23 + 16);
                if ( v24 )
                  _ultow(v24, v44, 10);
                v25 = *(_DWORD *)(*((_QWORD *)this + 2) + 12LL);
                if ( v25 != -1 )
                  _ultow(v25, v45, 10);
              }
              UserType = CWriter::WriteToFile(
                           *(CWriter **)this,
                           L"\t\t\t<Property       InternalName =\"",
                           g_cchBeginPropertyLong,
                           0);
              if ( UserType >= 0 )
              {
                UserType = CWriter::WriteToFile(*(CWriter **)this, v41, v10, 0);
                if ( UserType >= 0 )
                {
                  UserType = CWriter::WriteToFile(*(CWriter **)this, L"\"\t\t\tID=\"", g_cchPropIDEq, 0);
                  if ( UserType >= 0 )
                  {
                    v26 = -1;
                    do
                      ++v26;
                    while ( Buffer[v26] );
                    UserType = CWriter::WriteToFile(*(CWriter **)this, Buffer, v26, 0);
                    if ( UserType >= 0 )
                    {
                      UserType = CWriter::WriteToFile(*(CWriter **)this, L"\"\t\t\tType=\"", g_cchPropTypeEq, 0);
                      if ( UserType >= 0 )
                      {
                        v27 = -1;
                        do
                          ++v27;
                        while ( *((_WORD *)v42 + v27) );
                        UserType = CWriter::WriteToFile(*(CWriter **)this, v42, v27, 0);
                        if ( UserType >= 0 )
                        {
                          UserType = CWriter::WriteToFile(
                                       *(CWriter **)this,
                                       L"\"\t\t\tUserType=\"",
                                       g_cchPropUserTypeEq,
                                       0);
                          if ( UserType >= 0 )
                          {
                            UserType = CWriter::WriteToFile(*(CWriter **)this, Block, v35, 0);
                            if ( UserType >= 0 )
                            {
                              UserType = CWriter::WriteToFile(
                                           *(CWriter **)this,
                                           L"\"\t\t\tAttributes=\"",
                                           g_cchPropAttributeEq,
                                           0);
                              if ( UserType >= 0 )
                              {
                                v28 = -1;
                                do
                                  ++v28;
                                while ( v7[v28] );
                                UserType = CWriter::WriteToFile(*(CWriter **)this, v7, v28, 0);
                                if ( UserType >= 0 )
                                {
                                  if ( !v8 )
                                    goto LABEL_59;
                                  UserType = CWriter::WriteToFile(
                                               *(CWriter **)this,
                                               L"\"\t\t\tMetaFlagsEx=\"",
                                               g_cchPropMetaFlagsExEq,
                                               0);
                                  if ( UserType >= 0 )
                                  {
                                    v30 = -1;
                                    do
                                      ++v30;
                                    while ( v8[v30] );
                                    UserType = CWriter::WriteToFile(*(CWriter **)this, v8, v30, 0);
                                    if ( UserType >= 0 )
                                    {
LABEL_59:
                                      if ( !v9 )
                                        goto LABEL_85;
                                      UserType = CWriter::WriteToFile(
                                                   *(CWriter **)this,
                                                   L"\"\t\t\tDefaultValue=\"",
                                                   g_cchPropDefaultEq,
                                                   0);
                                      if ( UserType >= 0 )
                                      {
                                        v31 = -1;
                                        do
                                          ++v31;
                                        while ( v9[v31] );
                                        UserType = CWriter::WriteToFile(*(CWriter **)this, v9, v31, 0);
                                        if ( UserType >= 0 )
                                        {
LABEL_85:
                                          if ( !v44[0] )
                                            goto LABEL_86;
                                          UserType = CWriter::WriteToFile(
                                                       *(CWriter **)this,
                                                       L"\"\t\t\tStartingNumber=\"",
                                                       g_cchPropMinValueEq,
                                                       0);
                                          if ( UserType >= 0 )
                                          {
                                            v32 = -1;
                                            do
                                              ++v32;
                                            while ( v44[v32] );
                                            UserType = CWriter::WriteToFile(*(CWriter **)this, v44, v32, 0);
                                            if ( UserType >= 0 )
                                            {
LABEL_86:
                                              if ( !v45[0] )
                                                goto LABEL_87;
                                              UserType = CWriter::WriteToFile(
                                                           *(CWriter **)this,
                                                           L"\"\t\t\tEndingNumber=\"",
                                                           g_cchPropMaxValueEq,
                                                           0);
                                              if ( UserType >= 0 )
                                              {
                                                do
                                                  ++v5;
                                                while ( v45[v5] );
                                                UserType = CWriter::WriteToFile(*(CWriter **)this, v45, v5, 0);
                                                if ( UserType >= 0 )
                                                {
LABEL_87:
                                                  if ( (unsigned int)CMBPropertyWriter::IsPropertyFlag(this, v29) )
                                                    UserType = CWriter::WriteToFile(
                                                                 *(CWriter **)this,
                                                                 L"\">\r\n",
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
            goto LABEL_19;
          }
        }
        v19 = CWriterGlobalHelper::FlagToString(
                *(CWriterGlobalHelper **)(*(_QWORD *)this + 65600LL),
                v18,
                &v37,
                L"COLUMNMETA",
                0xCu);
        v8 = v37;
        UserType = v19;
        if ( v19 >= 0 )
          goto LABEL_30;
      }
LABEL_19:
      if ( Block && v36 )
        operator delete(Block);
      if ( v7 )
        operator delete(v7);
      goto LABEL_78;
    }
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\xmlwriter\\mbpropertywriter.cpp",
      812,
      "CMBPropertyWriter::BeginWritePropertyLong",
      L"[GetType] PropertyID %d, type: %d from synid %d is invalid.\n",
      *((_DWORD *)this + 9),
      dword_180042908[v15],
      v15);
LABEL_78:
  if ( v8 )
    operator delete(v8);
  if ( v9 )
    operator delete(v9);
  return (unsigned int)UserType;
}

```

## disassembly

```asm
0x18002fb58  push    rbp
0x18002fb5a  push    rbx
0x18002fb5b  push    rsi
0x18002fb5c  push    rdi
0x18002fb5d  push    r12
0x18002fb5f  push    r13
0x18002fb61  push    r14
0x18002fb63  push    r15
0x18002fb65  lea     rbp, [rsp-98h]
0x18002fb6d  sub     rsp, 198h
0x18002fb74  mov     rax, cs:__security_cookie
0x18002fb7b  xor     rax, rsp
0x18002fb7e  mov     [rbp+0D0h+var_50], rax
0x18002fb85  mov     rbx, [rcx+8]
0x18002fb89  xor     eax, eax
0x18002fb8b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002fb8f  mov     [rsp+1D0h+Block], rax
0x18002fb94  mov     [rsp+1D0h+var_190], eax
0x18002fb98  mov     rdi, rcx
0x18002fb9b  mov     [rsp+1D0h+var_18C], eax
0x18002fb9f  mov     r13d, eax
0x18002fba2  mov     [rsp+1D0h+var_178], rax
0x18002fba7  mov     r15d, eax
0x18002fbaa  mov     [rsp+1D0h+var_188], rax
0x18002fbaf  mov     r12d, eax
0x18002fbb2  mov     [rsp+1D0h+var_180], rax
0x18002fbb7  mov     [rsp+1D0h+var_168], rbx
0x18002fbbc  test    rbx, rbx
0x18002fbbf  jnz     short loc_18002FBEB
0x18002fbc1  lea     r8d, [rax+28h]; unsigned int
0x18002fbc5  lea     rdx, [rbp+0D0h+var_A0]; unsigned __int16 *
0x18002fbc9  call    ?CreateUnknownName@CMBPropertyWriter@@AEAAXPEAGKK@Z; CMBPropertyWriter::CreateUnknownName(ushort *,ulong,ulong)
0x18002fbce  lea     rax, [rbp+0D0h+var_A0]
0x18002fbd2  mov     rsi, r14
0x18002fbd5  mov     [rsp+1D0h+var_168], rax
0x18002fbda  lea     rdx, [rbp+0D0h+var_A0]
0x18002fbde  xor     ecx, ecx
0x18002fbe0  inc     rsi
0x18002fbe3  cmp     [rdx+rsi*2], cx
0x18002fbe7  jnz     short loc_18002FBE0
0x18002fbe9  jmp     short loc_18002FC1B
0x18002fbeb  mov     edx, 2Ch ; ','; Ch
0x18002fbf0  mov     rcx, rbx; Str
0x18002fbf3  call    cs:__imp_wcschr
0x18002fbf9  mov     rsi, rax
0x18002fbfc  xor     ecx, ecx
0x18002fbfe  mov     rax, [rdi+8]
0x18002fc02  test    rsi, rsi
0x18002fc05  jnz     short loc_18002FC15
0x18002fc07  mov     rsi, r14
0x18002fc0a  inc     rsi
0x18002fc0d  cmp     [rax+rsi*2], cx
0x18002fc11  jnz     short loc_18002FC0A
0x18002fc13  jmp     short loc_18002FC1B
0x18002fc15  sub     rsi, rax
0x18002fc18  sar     rsi, 1
0x18002fc1b  mov     [rsp+1D0h+Buffer], cx
0x18002fc20  lea     rdx, [rsp+1D0h+Buffer]; Buffer
0x18002fc25  mov     ecx, [rdi+24h]; Value
0x18002fc28  mov     r8d, 0Ah; Radix
0x18002fc2e  call    cs:__imp__ultow
0x18002fc34  mov     rdx, [rdi+10h]
0x18002fc38  xor     r8d, r8d
0x18002fc3b  test    rdx, rdx
0x18002fc3e  jnz     short loc_18002FC87
0x18002fc40  test    byte ptr cs:g_dwDebugFlags, 3
0x18002fc47  jz      short loc_18002FC7D
0x18002fc49  mov     eax, [rdi+24h]
0x18002fc4c  lea     r9, aCmbpropertywri; "CMBPropertyWriter::BeginWritePropertyLo"...
0x18002fc53  mov     rcx, cs:g_pDebug
0x18002fc5a  lea     rdx, aInetsrvIisMbXm_0; "inetsrv\\iis\\mb\\xmlwriter\\mbproperty"...
0x18002fc61  mov     [rsp+1D0h+var_1A8], eax
0x18002fc65  mov     r8d, 315h
0x18002fc6b  lea     rax, aBeginwriteprop; "[BeginWritePropertyLong] Type not found"...
0x18002fc72  mov     [rsp+1D0h+var_1B0], rax
0x18002fc77  call    cs:__imp_PuDbgPrintW
0x18002fc7d  mov     ebx, 8007070Ch
0x18002fc82  jmp     loc_1800301C3
0x18002fc87  mov     ecx, [rdx+8]
0x18002fc8a  lea     r9, cs:180000000h
0x18002fc91  lea     eax, [rcx-1]
0x18002fc94  cmp     eax, 0Bh
0x18002fc97  ja      loc_180030171
0x18002fc9d  mov     rax, ds:rva ?g_aSynIDToWszType@@3PAPEBGA[r9+rcx*8]; ushort const * near * g_aSynIDToWszType ...
0x18002fca5  mov     ebx, r8d
0x18002fca8  mov     [rsp+1D0h+var_160], rax
0x18002fcad  test    rax, rax
0x18002fcb0  jz      loc_180030176
0x18002fcb6  mov     rcx, [rdi]
0x18002fcb9  lea     rax, [rsp+1D0h+var_18C]
0x18002fcbe  mov     edx, [rdx+24h]; unsigned int
0x18002fcc1  lea     r9, [rsp+1D0h+var_190]; unsigned int *
0x18002fcc6  lea     r8, [rsp+1D0h+Block]; unsigned __int16 **
0x18002fccb  mov     [rsp+1D0h+var_1B0], rax; int *
0x18002fcd0  mov     rcx, [rcx+10040h]; this
0x18002fcd7  call    ?GetUserType@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAKPEAH@Z; CWriterGlobalHelper::GetUserType(ulong,ushort * *,ulong *,int *)
0x18002fcdc  mov     ebx, eax
0x18002fcde  test    eax, eax
0x18002fce0  jns     short loc_18002FD5A
0x18002fce2  test    byte ptr cs:g_dwDebugFlags, 3
0x18002fce9  jz      short loc_18002FD2A
0x18002fceb  mov     rcx, [rdi+10h]
0x18002fcef  lea     rax, aGetusertypePro; "[GetUserType] PropertyID %d, usertype: "...
0x18002fcf6  lea     r9, aCmbpropertywri; "CMBPropertyWriter::BeginWritePropertyLo"...
0x18002fcfd  mov     r8d, 342h
0x18002fd03  mov     edx, [rcx+24h]
0x18002fd06  mov     ecx, [rdi+24h]
0x18002fd09  mov     dword ptr [rsp+1D0h+var_1A0], edx
0x18002fd0d  lea     rdx, aInetsrvIisMbXm_0; "inetsrv\\iis\\mb\\xmlwriter\\mbproperty"...
0x18002fd14  mov     [rsp+1D0h+var_1A8], ecx
0x18002fd18  mov     rcx, cs:g_pDebug
0x18002fd1f  mov     [rsp+1D0h+var_1B0], rax
0x18002fd24  call    cs:__imp_PuDbgPrintW
0x18002fd2a  xor     esi, esi
0x18002fd2c  mov     rdi, [rsp+1D0h+Block]
0x18002fd31  test    rdi, rdi
0x18002fd34  jz      short loc_18002FD44
0x18002fd36  cmp     [rsp+1D0h+var_18C], esi
0x18002fd3a  jz      short loc_18002FD44
0x18002fd3c  mov     rcx, rdi; Block
0x18002fd3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002fd44  test    r13, r13
0x18002fd47  jz      loc_1800301C3
0x18002fd4d  mov     rcx, r13; Block
0x18002fd50  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002fd55  jmp     loc_1800301C3
0x18002fd5a  mov     rdx, [rdi+10h]
0x18002fd5e  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002fd65  mov     rcx, [rdi]
0x18002fd68  lea     r8, [rsp+1D0h+var_178]; unsigned __int16 **
0x18002fd6d  mov     dword ptr [rsp+1D0h+var_1B0], 0Fh; unsigned int
0x18002fd75  mov     edx, [rdx+20h]; unsigned int
0x18002fd78  mov     rcx, [rcx+10040h]; this
0x18002fd7f  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002fd84  mov     r13, [rsp+1D0h+var_178]
0x18002fd89  xor     r10d, r10d
0x18002fd8c  mov     ebx, eax
0x18002fd8e  test    eax, eax
0x18002fd90  js      short loc_18002FD2A
0x18002fd92  test    r13, r13
0x18002fd95  jz      short loc_18002FD2A
0x18002fd97  mov     rax, [rdi+10h]
0x18002fd9b  cmp     dword ptr [rax+18h], 1
0x18002fd9f  jnz     short loc_18002FDA7
0x18002fda1  lea     edx, [r10+1]
0x18002fda5  jmp     short loc_18002FDB1
0x18002fda7  mov     edx, 2; unsigned int
0x18002fdac  cmp     [rax+18h], edx
0x18002fdaf  jnz     short loc_18002FDE6
0x18002fdb1  mov     rcx, [rdi]
0x18002fdb4  lea     r9, aColumnmeta; "COLUMNMETA"
0x18002fdbb  lea     r8, [rsp+1D0h+var_188]; unsigned __int16 **
0x18002fdc0  mov     dword ptr [rsp+1D0h+var_1B0], 0Ch; unsigned int
0x18002fdc8  mov     rcx, [rcx+10040h]; this
0x18002fdcf  call    ?FlagToString@CWriterGlobalHelper@@QEAAJKPEAPEAGPEAGK@Z; CWriterGlobalHelper::FlagToString(ulong,ushort * *,ushort *,ulong)
0x18002fdd4  mov     r15, [rsp+1D0h+var_188]
0x18002fdd9  xor     r10d, r10d
0x18002fddc  mov     ebx, eax
0x18002fdde  test    eax, eax
0x18002fde0  js      loc_18002FD2A
0x18002fde6  mov     rdx, [rdi+18h]; unsigned __int8 *
0x18002fdea  test    rdx, rdx
0x18002fded  jz      short loc_18002FE46
0x18002fdef  mov     r8d, [rdi+20h]; unsigned int
0x18002fdf3  test    r8d, r8d
0x18002fdf6  jz      short loc_18002FE46
0x18002fdf8  mov     rax, [rdi+10h]
0x18002fdfc  lea     r9, [rsp+1D0h+var_180]
0x18002fe01  mov     rcx, [rdi]
0x18002fe04  mov     [rsp+1D0h+var_1A0], r9; unsigned __int16 **
0x18002fe09  lea     r9, cs:180000000h
0x18002fe10  mov     [rsp+1D0h+var_1A8], r10d; unsigned int
0x18002fe15  mov     eax, [rax+8]
0x18002fe18  mov     rcx, [rcx+10040h]; this
0x18002fe1f  mov     eax, ds:rva dword_1800428D0[r9+rax*4]
0x18002fe27  mov     r9d, [rdi+24h]; unsigned int
0x18002fe2b  mov     dword ptr [rsp+1D0h+var_1B0], eax; CWriterGlobalHelper *
0x18002fe2f  call    ?ToString@CWriterGlobalHelper@@QEAAJPEAEKKKKPEAPEAG@Z; CWriterGlobalHelper::ToString(uchar *,ulong,ulong,ulong,ulong,ushort * *)
0x18002fe34  mov     r12, [rsp+1D0h+var_180]
0x18002fe39  xor     r10d, r10d
0x18002fe3c  mov     ebx, eax
0x18002fe3e  test    eax, eax
0x18002fe40  js      loc_18002FD2A
0x18002fe46  mov     rcx, [rdi+10h]
0x18002fe4a  lea     rdx, cs:180000000h
0x18002fe51  mov     [rbp+0D0h+var_140], r10w
0x18002fe56  mov     [rbp+0D0h+var_F0], r10w
0x18002fe5b  mov     eax, [rcx+8]
0x18002fe5e  cmp     ds:rva dword_1800428D0[rdx+rax*4], 1
0x18002fe66  jnz     short loc_18002FE9B
0x18002fe68  mov     ecx, [rcx+10h]; Value
0x18002fe6b  test    ecx, ecx
0x18002fe6d  jz      short loc_18002FE7F
0x18002fe6f  mov     r8d, 0Ah; Radix
0x18002fe75  lea     rdx, [rbp+0D0h+var_140]; Buffer
0x18002fe79  call    cs:__imp__ultow
0x18002fe7f  mov     rax, [rdi+10h]
0x18002fe83  mov     ecx, [rax+0Ch]; Value
0x18002fe86  cmp     ecx, 0FFFFFFFFh
0x18002fe89  jz      short loc_18002FE9B
0x18002fe8b  mov     r8d, 0Ah; Radix
0x18002fe91  lea     rdx, [rbp+0D0h+var_F0]; Buffer
0x18002fe95  call    cs:__imp__ultow
0x18002fe9b  mov     r8d, cs:?g_cchBeginPropertyLong@@3KA; unsigned int
0x18002fea2  lea     rdx, aPropertyIntern; "\t\t\t<Property       InternalName =\""
0x18002fea9  mov     rcx, [rdi]; this
0x18002feac  xor     r9d, r9d; int
0x18002feaf  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002feb4  mov     ebx, eax
0x18002feb6  test    eax, eax
0x18002feb8  js      loc_18002FD2A
0x18002febe  mov     rdx, [rsp+1D0h+var_168]; void *
0x18002fec3  mov     r8d, esi; unsigned int
0x18002fec6  mov     rcx, [rdi]; this
0x18002fec9  xor     r9d, r9d; int
0x18002fecc  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002fed1  xor     esi, esi
0x18002fed3  mov     ebx, eax
0x18002fed5  test    eax, eax
0x18002fed7  js      loc_18002FD2C
0x18002fedd  mov     r8d, cs:?g_cchPropIDEq@@3KA; unsigned int
0x18002fee4  lea     rdx, aId_0; "\"\t\t\tID=\""
0x18002feeb  mov     rcx, [rdi]; this
0x18002feee  xor     r9d, r9d; int
0x18002fef1  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002fef6  mov     ebx, eax
0x18002fef8  test    eax, eax
0x18002fefa  js      loc_18002FD2C
0x18002ff00  lea     rax, [rsp+1D0h+Buffer]
0x18002ff05  mov     r8, r14
0x18002ff08  inc     r8; unsigned int
0x18002ff0b  cmp     [rax+r8*2], si
0x18002ff10  jnz     short loc_18002FF08
0x18002ff12  mov     rcx, [rdi]; this
0x18002ff15  lea     rdx, [rsp+1D0h+Buffer]; void *
0x18002ff1a  xor     r9d, r9d; int
0x18002ff1d  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ff22  mov     ebx, eax
0x18002ff24  test    eax, eax
0x18002ff26  js      loc_18002FD2C
0x18002ff2c  mov     r8d, cs:?g_cchPropTypeEq@@3KA; unsigned int
0x18002ff33  lea     rdx, aType_0; "\"\t\t\tType=\""
0x18002ff3a  mov     rcx, [rdi]; this
0x18002ff3d  xor     r9d, r9d; int
0x18002ff40  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ff45  mov     ebx, eax
0x18002ff47  test    eax, eax
0x18002ff49  js      loc_18002FD2C
0x18002ff4f  mov     rdx, [rsp+1D0h+var_160]; void *
0x18002ff54  mov     r8, r14
0x18002ff57  inc     r8; unsigned int
0x18002ff5a  cmp     [rdx+r8*2], si
0x18002ff5f  jnz     short loc_18002FF57
0x18002ff61  mov     rcx, [rdi]; this
0x18002ff64  xor     r9d, r9d; int
0x18002ff67  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ff6c  mov     ebx, eax
0x18002ff6e  test    eax, eax
0x18002ff70  js      loc_18002FD2C
0x18002ff76  mov     r8d, cs:?g_cchPropUserTypeEq@@3KA; unsigned int
0x18002ff7d  lea     rdx, aUsertype; "\"\t\t\tUserType=\""
0x18002ff84  mov     rcx, [rdi]; this
0x18002ff87  xor     r9d, r9d; int
0x18002ff8a  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ff8f  mov     ebx, eax
0x18002ff91  test    eax, eax
0x18002ff93  js      loc_18002FD2C
0x18002ff99  mov     r8d, [rsp+1D0h+var_190]; unsigned int
0x18002ff9e  xor     r9d, r9d; int
0x18002ffa1  mov     rdx, [rsp+1D0h+Block]; void *
0x18002ffa6  mov     rcx, [rdi]; this
0x18002ffa9  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ffae  mov     ebx, eax
0x18002ffb0  test    eax, eax
0x18002ffb2  js      loc_18002FD2C
0x18002ffb8  mov     r8d, cs:?g_cchPropAttributeEq@@3KA; unsigned int
0x18002ffbf  lea     rdx, aAttributes_0; "\"\t\t\tAttributes=\""
0x18002ffc6  mov     rcx, [rdi]; this
0x18002ffc9  xor     r9d, r9d; int
0x18002ffcc  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002ffd1  mov     ebx, eax
0x18002ffd3  test    eax, eax
0x18002ffd5  js      loc_18002FD2C
0x18002ffdb  mov     r8, r14
0x18002ffde  inc     r8; unsigned int
0x18002ffe1  cmp     [r13+r8*2+0], si
0x18002ffe7  jnz     short loc_18002FFDE
0x18002ffe9  mov     rcx, [rdi]; this
0x18002ffec  xor     r9d, r9d; int
0x18002ffef  mov     rdx, r13; void *
0x18002fff2  call    ?WriteToFile@CWriter@@QEAAJPEAXKH@Z; CWriter::WriteToFile(void *,ulong,int)
0x18002fff7  mov     ebx, eax
0x18002fff9  test    eax, eax
0x18002fffb  js      loc_18002FD2C
0x180030001  test    r15, r15
0x180030004  jz      short loc_18003004E
0x180030006  mov     r8d, cs:?g_cchPropMetaFlagsExEq@@3KA; unsigned int
0x18003000d  lea     rdx, aMetaflagsex; "\"\t\t\tMetaFlagsEx=\""
0x180030014  mov     rcx, [rdi]; this
0x180030017  xor     r9d, r9d; int
  ... truncated ...
```
