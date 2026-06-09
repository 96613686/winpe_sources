# CCscDirectoryFilter::GetChunk(tagSTAT_CHUNK *)

- ea: `0x1800032c0`
- end: `0x180003606`
- name: `?GetChunk@CCscDirectoryFilter@@UEAAJPEAUtagSTAT_CHUNK@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(CCscDirectoryFilter *__hidden this, struct tagSTAT_CHUNK *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800032c0`
- `0x180005210`
- `0x180006270`
- `0x180018034`
- `0x1800180f0`
- `0x18001869c`
- `0x180035c78`
- `0x180037064`
- `0x18003d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180003545`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180003545`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000349d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000349d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003531`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003482`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180003482`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180003493`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180003493`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCscDirectoryFilter::GetChunk(CCscDirectoryFilter *this, struct tagSTAT_CHUNK *a2)
{
  __int64 result; // rax
  int v5; // eax
  signed int v6; // ebx
  int v7; // edx
  signed int LastError; // eax
  wchar_t v9; // dx
  wchar_t v10; // r8
  wchar_t *v11; // rax
  LPVOID pv; // [rsp+40h] [rbp-19h] BYREF
  int v13; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v14; // [rsp+4Ch] [rbp-Dh] BYREF
  __int64 v15; // [rsp+50h] [rbp-9h] BYREF
  int v16; // [rsp+58h] [rbp-1h] BYREF
  __int64 v17; // [rsp+60h] [rbp+7h] BYREF
  __int64 v18; // [rsp+68h] [rbp+Fh] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp+17h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v5 = *((_DWORD *)this + 120);
  if ( v5 )
  {
    v6 = 0;
    if ( v5 != 1 )
      return (unsigned int)v6;
  }
  else
  {
    result = CCscFileFilter::GetChunk(this, a2);
    if ( (_DWORD)result != -2147215616 )
      return result;
    *((_DWORD *)this + 120) = 1;
  }
  v16 = 0;
  do
  {
    v15 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *, int *))(**((_QWORD **)this + 35) + 24LL))(
           *((_QWORD *)this + 35),
           1,
           &v15,
           &v16);
    if ( v6 )
      goto LABEL_28;
    v13 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 24LL))(v15, &v13);
    if ( v6 < 0 )
      goto LABEL_28;
    if ( (unsigned int)(v13 - 2) > 1 )
    {
      pv = 0;
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v15)(v15, &IID_IOfflineFilesFileSysInfo, &pv);
      if ( v6 >= 0 )
      {
        v14 = 0;
        v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, unsigned int *))(*(_QWORD *)pv + 24LL))(pv, 0, &v14);
        if ( v6 >= 0 )
        {
          if ( !*((_BYTE *)this + 472) && (*((_DWORD *)this + 19) & 0x4010) == 0x4000 )
          {
            *((_BYTE *)this + 472) = 1;
            *((_DWORD *)this + 119) = GetPolicyDwordAsBool(L"AllowIndexingEncryptedStoresOrItems", 1);
          }
          v6 = TestAttributes(v14, v7);
          if ( v6 >= 0 )
          {
            v18 = 0;
            *(_QWORD *)&SystemTime.wYear = 0;
            v17 = 0;
            v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _SYSTEMTIME *, __int64 *, char *, __int64 *))(*(_QWORD *)pv + 32LL))(
                   pv,
                   0,
                   &SystemTime,
                   &v18,
                   (char *)this + 460,
                   &v17);
          }
        }
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(&pv);
      goto LABEL_22;
    }
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    if ( !SystemTimeToFileTime(&SystemTime, (LPFILETIME)((char *)this + 460)) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
LABEL_22:
      if ( v6 < 0 )
        goto LABEL_28;
    }
    pv = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v15 + 32LL))(v15, &pv);
    if ( v6 >= 0 )
    {
      CLMString::Truncate((CCscDirectoryFilter *)((char *)this + 296), *((_DWORD *)this + 114));
      (*(void (__fastcall **)(char *, char *, _QWORD, __int64))(*((_QWORD *)this + 37) + 32LL))(
        (char *)this + 296,
        (char *)pv + 4,
        *((unsigned int *)this + 79),
        0xFFFFFFFFLL);
      CLMString::ReplaceAll((CCscDirectoryFilter *)((char *)this + 296), v9, v10, *((_DWORD *)this + 114));
      CoTaskMemFree(pv);
      v11 = wcsstr(*((const wchar_t **)this + 38), L"$RECYCLE.BIN");
      if ( !v11 || (unsigned int)(((__int64)v11 - *((_QWORD *)this + 38)) >> 1) == -1 )
      {
        a2->idChunk = ++*((_DWORD *)this + 72);
        a2->breakType = CHUNK_EOS;
        a2->locale = *((_DWORD *)this + 117);
        a2->attribute.guidPropSet = GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04;
        a2->attribute.psProperty.ulKind = 1;
        a2->flags = CHUNK_VALUE;
        LODWORD(a2->attribute.psProperty.propid) = 12;
        *(_QWORD *)&a2->idChunkSource = 0;
        a2->cwcLenSource = 0;
      }
      else
      {
        v6 = -2147218169;
      }
    }
LABEL_28:
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  while ( v6 == -2147218169 );
  if ( v6 == 1 )
    return (unsigned int)-2147215616;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800032c0  mov     [rsp-8+arg_10], rbx
0x1800032c5  mov     [rsp-8+arg_18], rsi
0x1800032ca  push    rbp
0x1800032cb  push    rdi
0x1800032cc  push    r12
0x1800032ce  push    r14
0x1800032d0  push    r15
0x1800032d2  lea     rbp, [rsp-37h]
0x1800032d7  sub     rsp, 90h
0x1800032de  mov     rax, cs:__security_cookie
0x1800032e5  xor     rax, rsp
0x1800032e8  mov     [rbp+57h+var_30], rax
0x1800032ec  mov     r14, rdx
0x1800032ef  mov     rsi, rcx
0x1800032f2  test    rdx, rdx
0x1800032f5  jnz     short loc_180003301
0x1800032f7  mov     eax, 80004003h
0x1800032fc  jmp     loc_1800035DE
0x180003301  mov     eax, [rcx+1E0h]
0x180003307  xor     r15d, r15d
0x18000330a  mov     r12d, 80041700h
0x180003310  test    eax, eax
0x180003312  jnz     short loc_18000332E
0x180003314  call    ?GetChunk@CCscFileFilter@@UEAAJPEAUtagSTAT_CHUNK@@@Z; CCscFileFilter::GetChunk(tagSTAT_CHUNK *)
0x180003319  cmp     eax, r12d
0x18000331c  jnz     loc_1800035DE
0x180003322  mov     dword ptr [rsi+1E0h], 1
0x18000332c  jmp     short loc_18000333A
0x18000332e  mov     ebx, r15d
0x180003331  cmp     eax, 1
0x180003334  jnz     loc_1800035DC
0x18000333a  mov     [rbp+57h+var_58], r15d
0x18000333e  xchg    ax, ax
0x180003340  mov     [rbp+57h+var_60], r15
0x180003344  mov     rcx, [rsi+118h]
0x18000334b  mov     rax, [rcx]
0x18000334e  lea     r9, [rbp+57h+var_58]
0x180003352  lea     r8, [rbp+57h+var_60]
0x180003356  mov     edx, 1
0x18000335b  mov     rax, [rax+18h]
0x18000335f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003364  mov     ebx, eax
0x180003366  test    eax, eax
0x180003368  jnz     loc_1800035B3
0x18000336e  mov     [rbp+57h+var_68], r15d
0x180003372  mov     rcx, [rbp+57h+var_60]
0x180003376  mov     rax, [rcx]
0x180003379  lea     rdx, [rbp+57h+var_68]
0x18000337d  mov     rax, [rax+18h]
0x180003381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003386  mov     ebx, eax
0x180003388  test    eax, eax
0x18000338a  js      loc_1800035B3
0x180003390  mov     eax, [rbp+57h+var_68]
0x180003393  add     eax, 0FFFFFFFEh
0x180003396  cmp     eax, 1
0x180003399  jbe     loc_180003477
0x18000339f  mov     [rbp+57h+pv], r15
0x1800033a3  mov     rcx, [rbp+57h+var_60]
0x1800033a7  mov     rax, [rcx]
0x1800033aa  lea     r8, [rbp+57h+pv]
0x1800033ae  lea     rdx, IID_IOfflineFilesFileSysInfo
0x1800033b5  mov     rax, [rax]
0x1800033b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033bd  mov     ebx, eax
0x1800033bf  test    eax, eax
0x1800033c1  js      loc_18000346C
0x1800033c7  mov     [rbp+57h+var_64], r15d
0x1800033cb  mov     rcx, [rbp+57h+pv]
0x1800033cf  mov     rax, [rcx]
0x1800033d2  lea     r8, [rbp+57h+var_64]
0x1800033d6  xor     edx, edx
0x1800033d8  mov     rax, [rax+18h]
0x1800033dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e1  mov     ebx, eax
0x1800033e3  test    eax, eax
0x1800033e5  js      loc_18000346C
0x1800033eb  cmp     byte ptr [rsi+1D8h], 0
0x1800033f2  jnz     short loc_180003421
0x1800033f4  mov     eax, [rsi+4Ch]
0x1800033f7  and     eax, 4010h
0x1800033fc  cmp     eax, 4000h
0x180003401  jnz     short loc_180003421
0x180003403  mov     byte ptr [rsi+1D8h], 1
0x18000340a  mov     edx, 1; int
0x18000340f  lea     rcx, aAllowindexinge; "AllowIndexingEncryptedStoresOrItems"
0x180003416  call    ?GetPolicyDwordAsBool@@YAHPEB_WH@Z; GetPolicyDwordAsBool(wchar_t const *,int)
0x18000341b  mov     [rsi+1DCh], eax
0x180003421  mov     ecx, [rbp+57h+var_64]; unsigned int
0x180003424  call    ?TestAttributes@@YAJKH@Z; TestAttributes(ulong,int)
0x180003429  mov     ebx, eax
0x18000342b  test    eax, eax
0x18000342d  js      short loc_18000346C
0x18000342f  mov     [rbp+57h+var_48], r15
0x180003433  mov     qword ptr [rbp+57h+SystemTime.wYear], r15
0x180003437  mov     [rbp+57h+var_50], r15
0x18000343b  mov     rcx, [rbp+57h+pv]
0x18000343f  mov     rax, [rcx]
0x180003442  lea     rdx, [rsi+1CCh]
0x180003449  lea     r8, [rbp+57h+var_50]
0x18000344d  mov     [rsp+0B0h+var_88], r8
0x180003452  mov     [rsp+0B0h+var_90], rdx
0x180003457  lea     r9, [rbp+57h+var_48]
0x18000345b  lea     r8, [rbp+57h+SystemTime]
0x18000345f  xor     edx, edx
0x180003461  mov     rax, [rax+20h]
0x180003465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346a  mov     ebx, eax
0x18000346c  lea     rcx, [rbp+57h+pv]
0x180003470  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x180003475  jmp     short loc_1800034B2
0x180003477  xorps   xmm0, xmm0
0x18000347a  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000347e  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180003482  call    cs:__imp_GetSystemTime
0x180003488  lea     rdx, [rsi+1CCh]; lpFileTime
0x18000348f  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180003493  call    cs:__imp_SystemTimeToFileTime
0x180003499  test    eax, eax
0x18000349b  jnz     short loc_1800034BA
0x18000349d  call    cs:__imp_GetLastError
0x1800034a3  mov     ebx, eax
0x1800034a5  test    eax, eax
0x1800034a7  jle     short loc_1800034B2
0x1800034a9  movzx   ebx, ax
0x1800034ac  or      ebx, 80070000h
0x1800034b2  test    ebx, ebx
0x1800034b4  js      loc_1800035B3
0x1800034ba  mov     [rbp+57h+pv], r15
0x1800034be  mov     rcx, [rbp+57h+var_60]
0x1800034c2  mov     rax, [rcx]
0x1800034c5  lea     rdx, [rbp+57h+pv]
0x1800034c9  mov     rax, [rax+20h]
0x1800034cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d2  mov     ebx, eax
0x1800034d4  test    eax, eax
0x1800034d6  js      loc_1800035B3
0x1800034dc  mov     edx, [rsi+1C8h]; unsigned int
0x1800034e2  lea     rcx, [rsi+128h]; this
0x1800034e9  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x1800034ee  mov     rax, [rsi+128h]
0x1800034f5  mov     rdx, [rbp+57h+pv]
0x1800034f9  add     rdx, 4
0x1800034fd  mov     r9d, 0FFFFFFFFh
0x180003503  mov     r8d, [rsi+13Ch]
0x18000350a  lea     rcx, [rsi+128h]
0x180003511  mov     rax, [rax+20h]
0x180003515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351a  mov     r9d, [rsi+1C8h]; unsigned int
0x180003521  lea     rcx, [rsi+128h]; this
0x180003528  call    ?ReplaceAll@CLMString@@QEAAX_W0I@Z; CLMString::ReplaceAll(wchar_t,wchar_t,uint)
0x18000352d  mov     rcx, [rbp+57h+pv]; pv
0x180003531  call    cs:__imp_CoTaskMemFree
0x180003537  lea     rdx, aRecycleBin; "$RECYCLE.BIN"
0x18000353e  mov     rcx, [rsi+130h]; Str
0x180003545  call    cs:__imp_wcsstr
0x18000354b  test    rax, rax
0x18000354e  jz      short loc_180003566
0x180003550  sub     rax, [rsi+130h]
0x180003557  sar     rax, 1
0x18000355a  cmp     eax, 0FFFFFFFFh
0x18000355d  jz      short loc_180003566
0x18000355f  mov     ebx, 80040D07h
0x180003564  jmp     short loc_1800035B3
0x180003566  inc     dword ptr [rsi+120h]
0x18000356c  mov     eax, [rsi+120h]
0x180003572  mov     [r14], eax
0x180003575  mov     dword ptr [r14+4], 2
0x18000357d  mov     eax, [rsi+1D4h]
0x180003583  mov     [r14+0Ch], eax
0x180003587  movups  xmm0, xmmword ptr cs:_GUID_0b63e343_9ccc_11d0_bcdb_00805fccce04.Data1
0x18000358e  movups  xmmword ptr [r14+10h], xmm0
0x180003593  mov     dword ptr [r14+20h], 1
0x18000359b  mov     dword ptr [r14+8], 2
0x1800035a3  mov     dword ptr [r14+28h], 0Ch
0x1800035ab  mov     [r14+30h], r15
0x1800035af  mov     [r14+38h], r15d
0x1800035b3  mov     rcx, [rbp+57h+var_60]
0x1800035b7  test    rcx, rcx
0x1800035ba  jz      short loc_1800035C9
0x1800035bc  mov     rax, [rcx]
0x1800035bf  mov     rax, [rax+10h]
0x1800035c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c8  nop
0x1800035c9  cmp     ebx, 80040D07h
0x1800035cf  jz      loc_180003340
0x1800035d5  cmp     ebx, 1
0x1800035d8  cmovz   ebx, r12d
0x1800035dc  mov     eax, ebx
0x1800035de  mov     rcx, [rbp+57h+var_30]
0x1800035e2  xor     rcx, rsp; StackCookie
0x1800035e5  call    __security_check_cookie
0x1800035ea  lea     r11, [rsp+0B0h+var_20]
0x1800035f2  mov     rbx, [r11+40h]
0x1800035f6  mov     rsi, [r11+48h]
0x1800035fa  mov     rsp, r11
0x1800035fd  pop     r15
0x1800035ff  pop     r14
0x180003601  pop     r12
0x180003603  pop     rdi
0x180003604  pop     rbp
0x180003605  retn
```
