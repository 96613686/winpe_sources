# ValidateMapFile(CPageMap const &,void *,bool)

- ea: `0x18002496c`
- end: `0x180024c9a`
- name: `?ValidateMapFile@@YAKAEBUCPageMap@@PEAX_N@Z`
- size: `814`
- prototype: `unsigned int(const struct CPageMap *, void *, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e128`

## callees

- `0x18000f8f0`
- `0x18001a6b0`
- `0x1800235e4`
- `0x18002496c`
- `0x180024ca0`
- `0x1800309a8`
- `0x18003d184`
- `0x180043fa0`
- `0x180044170`

## import_xrefs

- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800249aa`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x1800249aa`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x1800249b4`
- `wbemcomn!?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ` at `0x1800249b4`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x1800249bd`
- `wbemcomn!?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ` at `0x1800249bd`
- `wbemcomn!GetMemLogObject` at `0x180024b0c`
- `wbemcomn!GetMemLogObject` at `0x180024c2c`
- `wbemcomn!GetMemLogObject` at `0x180024b0c`
- `wbemcomn!GetMemLogObject` at `0x180024c2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024b18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024c38`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024b18`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180024c38`

## string_xrefs

- `0x180024a07`: `NumWriteIdCheck`

## pseudocode

```c
__int64 __fastcall ValidateMapFile(const struct CPageMap *a1, void *a2, char a3)
{
  int v4; // eax
  HANDLE v5; // rdi
  unsigned int v7; // esi
  int v8; // r8d
  int RegistryPathCIMOM; // ebx
  int RegistryPathRoot; // eax
  int v11; // r8d
  int v12; // eax
  int v13; // r8d
  int Value; // ebx
  unsigned int v15; // eax
  unsigned int v16; // r14d
  unsigned int v17; // r14d
  __int64 i; // rcx
  __int64 v19; // r11
  unsigned __int64 v20; // rdx
  __int64 v21; // rbx
  unsigned int v22; // edx
  MemoryPage *v23; // rbx
  unsigned int v24; // edi
  CMemoryLog *MemLogObject; // rax
  __int64 v26; // r8
  __int64 v27; // rdi
  __int64 j; // r10
  __int64 k; // r9
  unsigned int v31; // ebx
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  CMemoryLog *v35; // rax
  __int64 v36; // r8
  __int64 v37; // [rsp+30h] [rbp-20h] BYREF
  MemoryPage *v38; // [rsp+38h] [rbp-18h] BYREF
  __int64 v39; // [rsp+40h] [rbp-10h]
  int v40; // [rsp+90h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+98h] [rbp+48h]
  MemoryPage *v42; // [rsp+A8h] [rbp+58h] BYREF

  hFile = a2;
  v4 = *((_DWORD *)a1 + 2) + 1;
  v40 = 0;
  v5 = a2;
  v37 = 0;
  if ( v4 == *((_DWORD *)a1 + 1) )
  {
    v7 = 0;
    if ( (unsigned __int8)CWbemInstallObject::IsOffline() )
    {
      RegistryPathCIMOM = CWbemInstallObject::GetRegistryPathCIMOM();
      RegistryPathRoot = CWbemInstallObject::GetRegistryPathRoot();
      v12 = DLRegOpenKeyExW(RegistryPathRoot, RegistryPathCIMOM, v11, 131097, (__int64)&v37);
    }
    else
    {
      v12 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", v8, 131097, (__int64)&v37);
    }
    if ( v12
      || (LODWORD(v42) = 4,
          Value = DLRegQueryValueExW(v37, (unsigned int)L"NumWriteIdCheck", v13, 0, (__int64)&v40, (__int64)&v42),
          DLRegCloseKey(v37),
          Value) )
    {
      v15 = 1;
      v40 = 1;
    }
    else
    {
      v15 = v40;
    }
    if ( v15 == -1 || (v16 = *((_DWORD *)a1 + 1), v16 <= v15) )
      v17 = 0;
    else
      v17 = v16 - v15;
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      v19 = *((_QWORD *)a1 + 2);
      v20 = 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)a1 + 3) - v19) >> 3);
      LODWORD(v42) = i;
      v39 = (unsigned int)i;
      if ( (unsigned int)i == v20 )
        break;
      v21 = 3 * i;
      v22 = *(_DWORD *)(v19 + 24 * i);
      if ( v22 != -1 )
      {
        if ( *(_DWORD *)(v19 + 24 * i + 16) != *((_DWORD *)a1 + 1) )
          goto LABEL_36;
        if ( *(_DWORD *)(v19 + 24 * i + 20) >= v17 )
        {
          v38 = 0;
          v7 = CPageCache::ReadPhysPage(v5, v22, &v38);
          if ( v7 )
          {
            if ( v7 != 14 )
            {
              MemLogObject = GetMemLogObject();
              CMemoryLog::Write(MemLogObject, -1);
              if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  v26,
                  *(unsigned int *)(*((_QWORD *)a1 + 2) + 8 * v21),
                  v7);
              }
              if ( !a3 )
                CRepositoryCorruption::SetRepositoryCorrupted(7, 0, 0);
            }
            return v7;
          }
          v23 = v38;
          v24 = ~(unsigned int)CreateCRC32(*((const unsigned __int8 **)v38 + 2));
          MemoryPage::Release(v23);
          if ( v24 != *(_DWORD *)(*((_QWORD *)a1 + 2) + 24 * v39 + 4) )
            goto LABEL_36;
          LODWORD(i) = (_DWORD)v42;
          v5 = hFile;
        }
      }
    }
    v27 = *((_QWORD *)a1 + 5);
    for ( j = 0; (unsigned int)j < (unsigned __int64)((*((_QWORD *)a1 + 6) - v27) >> 2); j = (unsigned int)(j + 1) )
    {
      for ( k = 0; (unsigned int)k != v20; k = (unsigned int)(k + 1) )
      {
        if ( *(_DWORD *)(v19 + 24 * k) == *(_DWORD *)(v27 + 4 * j) )
          goto LABEL_36;
      }
    }
    if ( v20 )
    {
      v31 = 0;
      v32 = 0;
      v33 = 0;
      do
      {
        v34 = 3 * v33;
        if ( *(_DWORD *)(v19 + 8 * v34) != -1 && v31 < *(_DWORD *)(v19 + 8 * v34) )
          v31 = *(_DWORD *)(v19 + 8 * v34);
        v33 = (unsigned int)++v32;
      }
      while ( v32 != v20 );
      if ( v31 )
      {
        v42 = 0;
        v7 = CPageCache::ReadPhysPage(hFile, v31, &v42);
        if ( v7 )
        {
          if ( v7 != 14 )
          {
            v35 = GetMemLogObject();
            CMemoryLog::Write(v35, -1);
            if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, v36, v31, v7);
            }
            if ( !a3 )
              CRepositoryCorruption::SetRepositoryCorrupted(3, 0, 0);
            return 1358;
          }
        }
        else
        {
          MemoryPage::Release(v42);
        }
      }
    }
    return v7;
  }
  else
  {
LABEL_36:
    if ( !a3 )
      CRepositoryCorruption::SetRepositoryCorrupted(4, 0, 0);
    return 1358;
  }
}

```

## disassembly

```asm
0x18002496c  mov     [rsp-38h+hFile], rdx
0x180024971  push    rbp
0x180024972  push    rbx
0x180024973  push    rsi
0x180024974  push    rdi
0x180024975  push    r12
0x180024977  push    r13
0x180024979  push    r14
0x18002497b  mov     rbp, rsp
0x18002497e  sub     rsp, 50h
0x180024982  mov     eax, [rcx+8]
0x180024985  mov     r12b, r8b
0x180024988  inc     eax
0x18002498a  mov     [rbp+arg_0], 0
0x180024991  mov     rdi, rdx
0x180024994  mov     r13, rcx
0x180024997  mov     [rbp+var_20], 0
0x18002499f  cmp     eax, [rcx+4]
0x1800249a2  jnz     loc_180024BAF
0x1800249a8  xor     esi, esi
0x1800249aa  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x1800249b0  test    al, al
0x1800249b2  jz      short loc_1800249D4
0x1800249b4  call    cs:__imp_?GetRegistryPathCIMOM@CWbemInstallObject@@SAPEBGXZ; CWbemInstallObject::GetRegistryPathCIMOM(void)
0x1800249ba  mov     rbx, rax
0x1800249bd  call    cs:__imp_?GetRegistryPathRoot@CWbemInstallObject@@SAPEAUHKEY__@@XZ; CWbemInstallObject::GetRegistryPathRoot(void)
0x1800249c3  lea     rcx, [rbp+var_20]
0x1800249c7  mov     rdx, rbx
0x1800249ca  mov     [rsp+50h+var_30], rcx
0x1800249cf  mov     rcx, rax
0x1800249d2  jmp     short loc_1800249EB
0x1800249d4  lea     rax, [rbp+var_20]
0x1800249d8  mov     rcx, 0FFFFFFFF80000002h
0x1800249df  mov     [rsp+50h+var_30], rax
0x1800249e4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x1800249eb  mov     r9d, 20019h
0x1800249f1  call    DLRegOpenKeyExW
0x1800249f6  test    eax, eax
0x1800249f8  jnz     short loc_180024A3A
0x1800249fa  mov     rcx, [rbp+var_20]
0x1800249fe  lea     rax, [rbp+arg_18]
0x180024a02  mov     [rsp+50h+var_28], rax
0x180024a07  lea     rdx, aNumwriteidchec; "NumWriteIdCheck"
0x180024a0e  lea     rax, [rbp+arg_0]
0x180024a12  mov     dword ptr [rbp+arg_18], 4
0x180024a19  xor     r9d, r9d
0x180024a1c  mov     [rsp+50h+var_30], rax
0x180024a21  call    DLRegQueryValueExW
0x180024a26  mov     rcx, [rbp+var_20]
0x180024a2a  mov     ebx, eax
0x180024a2c  call    DLRegCloseKey
0x180024a31  test    ebx, ebx
0x180024a33  jnz     short loc_180024A3A
0x180024a35  mov     eax, [rbp+arg_0]
0x180024a38  jmp     short loc_180024A42
0x180024a3a  mov     eax, 1
0x180024a3f  mov     [rbp+arg_0], eax
0x180024a42  cmp     eax, 0FFFFFFFFh
0x180024a45  jz      short loc_180024A55
0x180024a47  mov     r14d, [r13+4]
0x180024a4b  cmp     r14d, eax
0x180024a4e  jbe     short loc_180024A55
0x180024a50  sub     r14d, eax
0x180024a53  jmp     short loc_180024A58
0x180024a55  xor     r14d, r14d
0x180024a58  xor     ecx, ecx
0x180024a5a  mov     r11, [r13+10h]
0x180024a5e  mov     r8, 0AAAAAAAAAAAAAAABh
0x180024a68  mov     rdx, [r13+18h]
0x180024a6c  sub     rdx, r11
0x180024a6f  mov     eax, ecx
0x180024a71  sar     rdx, 3
0x180024a75  imul    rdx, r8
0x180024a79  mov     dword ptr [rbp+arg_18], ecx
0x180024a7c  mov     [rbp+var_10], rax
0x180024a80  cmp     rax, rdx
0x180024a83  jz      loc_180024B72
0x180024a89  lea     rbx, [rcx+rcx*2]
0x180024a8d  mov     edx, [r11+rbx*8]; unsigned int
0x180024a91  cmp     edx, 0FFFFFFFFh
0x180024a94  jz      short loc_180024AFC
0x180024a96  mov     eax, [r13+4]
0x180024a9a  cmp     [r11+rbx*8+10h], eax
0x180024a9f  jnz     loc_180024BAF
0x180024aa5  cmp     [r11+rbx*8+14h], r14d
0x180024aaa  jb      short loc_180024AFC
0x180024aac  lea     r8, [rbp+var_18]; struct MemoryPage **
0x180024ab0  mov     [rbp+var_18], 0
0x180024ab8  mov     rcx, rdi; hFile
0x180024abb  call    ?ReadPhysPage@CPageCache@@SAKPEAXKPEAPEAVMemoryPage@@@Z; CPageCache::ReadPhysPage(void *,ulong,MemoryPage * *)
0x180024ac0  mov     esi, eax
0x180024ac2  test    eax, eax
0x180024ac4  jnz     short loc_180024B03
0x180024ac6  mov     rbx, [rbp+var_18]
0x180024aca  mov     rcx, [rbx+10h]; unsigned __int8 *
0x180024ace  call    ?CreateCRC32@@YAKPEBEKK@Z; CreateCRC32(uchar const *,ulong,ulong)
0x180024ad3  mov     edi, eax
0x180024ad5  mov     rcx, rbx; this
0x180024ad8  not     edi
0x180024ada  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180024adf  mov     rdx, [rbp+var_10]
0x180024ae3  mov     rcx, [r13+10h]
0x180024ae7  lea     rax, [rdx+rdx*2]
0x180024aeb  cmp     edi, [rcx+rax*8+4]
0x180024aef  jnz     loc_180024BAF
0x180024af5  mov     ecx, dword ptr [rbp+arg_18]
0x180024af8  mov     rdi, [rbp+hFile]
0x180024afc  inc     ecx
0x180024afe  jmp     loc_180024A5A
0x180024b03  cmp     esi, 0Eh
0x180024b06  jz      loc_180024C89
0x180024b0c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024b12  mov     rcx, rax
0x180024b15  or      edx, 0FFFFFFFFh
0x180024b18  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024b1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b25  lea     rax, WPP_GLOBAL_Control
0x180024b2c  cmp     rcx, rax
0x180024b2f  jz      short loc_180024B57
0x180024b31  test    byte ptr [rcx+1Ch], 1
0x180024b35  jz      short loc_180024B57
0x180024b37  cmp     byte ptr [rcx+19h], 2
0x180024b3b  jb      short loc_180024B57
0x180024b3d  mov     r9, [r13+10h]
0x180024b41  mov     edx, 1Ah
0x180024b46  mov     rcx, [rcx+10h]
0x180024b4a  mov     dword ptr [rsp+50h+var_30], esi
0x180024b4e  mov     r9d, [r9+rbx*8]
0x180024b52  call    WPP_SF_DD
0x180024b57  test    r12b, r12b
0x180024b5a  jnz     loc_180024C89
0x180024b60  xor     edx, edx; bool
0x180024b62  xor     r8d, r8d; unsigned int
0x180024b65  lea     ecx, [rdx+7]; int
0x180024b68  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180024b6d  jmp     loc_180024C89
0x180024b72  mov     rdi, [r13+28h]
0x180024b76  xor     r10d, r10d
0x180024b79  mov     r8, [r13+30h]
0x180024b7d  sub     r8, rdi
0x180024b80  sar     r8, 2
0x180024b84  mov     ebx, r10d
0x180024b87  cmp     rbx, r8
0x180024b8a  jnb     short loc_180024BCB
0x180024b8c  xor     r9d, r9d
0x180024b8f  mov     eax, r9d
0x180024b92  cmp     rax, rdx
0x180024b95  jz      short loc_180024BAA
0x180024b97  mov     eax, [rdi+r10*4]
0x180024b9b  lea     rcx, [r9+r9*2]
0x180024b9f  cmp     [r11+rcx*8], eax
0x180024ba3  jz      short loc_180024BAF
0x180024ba5  inc     r9d
0x180024ba8  jmp     short loc_180024B8F
0x180024baa  inc     r10d
0x180024bad  jmp     short loc_180024B84
0x180024baf  test    r12b, r12b
0x180024bb2  jnz     short loc_180024BC1
0x180024bb4  xor     edx, edx; bool
0x180024bb6  xor     r8d, r8d; unsigned int
0x180024bb9  lea     ecx, [rdx+4]; int
0x180024bbc  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180024bc1  mov     eax, 54Eh
0x180024bc6  jmp     loc_180024C8B
0x180024bcb  test    rdx, rdx
0x180024bce  jz      loc_180024C89
0x180024bd4  xor     ebx, ebx
0x180024bd6  xor     ecx, ecx
0x180024bd8  xor     eax, eax
0x180024bda  lea     rax, [rax+rax*2]
0x180024bde  cmp     dword ptr [r11+rax*8], 0FFFFFFFFh
0x180024be3  jz      short loc_180024BEE
0x180024be5  cmp     ebx, [r11+rax*8]
0x180024be9  cmovb   ebx, [r11+rax*8]
0x180024bee  inc     ecx
0x180024bf0  mov     eax, ecx
0x180024bf2  cmp     rax, rdx
0x180024bf5  jnz     short loc_180024BDA
0x180024bf7  test    ebx, ebx
0x180024bf9  jz      loc_180024C89
0x180024bff  mov     rcx, [rbp+hFile]; hFile
0x180024c03  lea     r8, [rbp+arg_18]; struct MemoryPage **
0x180024c07  mov     edx, ebx; unsigned int
0x180024c09  mov     [rbp+arg_18], 0
0x180024c11  call    ?ReadPhysPage@CPageCache@@SAKPEAXKPEAPEAVMemoryPage@@@Z; CPageCache::ReadPhysPage(void *,ulong,MemoryPage * *)
0x180024c16  mov     esi, eax
0x180024c18  test    eax, eax
0x180024c1a  jnz     short loc_180024C27
0x180024c1c  mov     rcx, [rbp+arg_18]; this
0x180024c20  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180024c25  jmp     short loc_180024C89
0x180024c27  cmp     esi, 0Eh
0x180024c2a  jz      short loc_180024C89
0x180024c2c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180024c32  mov     rcx, rax
0x180024c35  or      edx, 0FFFFFFFFh
0x180024c38  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180024c3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c45  lea     rax, WPP_GLOBAL_Control
0x180024c4c  cmp     rcx, rax
0x180024c4f  jz      short loc_180024C72
0x180024c51  test    byte ptr [rcx+1Ch], 1
0x180024c55  jz      short loc_180024C72
0x180024c57  cmp     byte ptr [rcx+19h], 2
0x180024c5b  jb      short loc_180024C72
0x180024c5d  mov     rcx, [rcx+10h]
0x180024c61  mov     edx, 1Bh
0x180024c66  mov     r9d, ebx
0x180024c69  mov     dword ptr [rsp+50h+var_30], esi
0x180024c6d  call    WPP_SF_DD
0x180024c72  test    r12b, r12b
0x180024c75  jnz     short loc_180024C84
0x180024c77  xor     edx, edx; bool
0x180024c79  xor     r8d, r8d; unsigned int
0x180024c7c  lea     ecx, [rdx+3]; int
0x180024c7f  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180024c84  mov     esi, 54Eh
0x180024c89  mov     eax, esi
0x180024c8b  add     rsp, 50h
0x180024c8f  pop     r14
0x180024c91  pop     r13
0x180024c93  pop     r12
0x180024c95  pop     rdi
0x180024c96  pop     rsi
0x180024c97  pop     rbx
0x180024c98  pop     rbp
0x180024c99  retn
```
