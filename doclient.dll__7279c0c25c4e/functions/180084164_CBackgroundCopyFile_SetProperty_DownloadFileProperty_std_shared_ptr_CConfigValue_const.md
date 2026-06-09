# CBackgroundCopyFile::SetProperty(DownloadFileProperty,std::shared_ptr<CConfigValue> const *)

- ea: `0x180084164`
- end: `0x1800848a7`
- name: `?SetProperty@CBackgroundCopyFile@@QEAAJW4DownloadFileProperty@@PEBV?$shared_ptr@VCConfigValue@@@std@@@Z`
- size: `1859`
- prototype: `__int64 __fastcall(CBackgroundCopyFile *this, unsigned int, const char **)`
- caller_count: `3`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e410`
- `0x18008f0bc`
- `0x180090510`

## callees

- `0x18000933c`
- `0x18000cdd0`
- `0x1800199b4`
- `0x180019c5c`
- `0x18001dfc4`
- `0x1800604f8`
- `0x18007ca54`
- `0x180084164`
- `0x1800854d8`
- `0x180085a04`
- `0x180086060`
- `0x180086590`
- `0x1800866a0`
- `0x1800a1c5c`
- `0x1800a1ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800842a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800842cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008468d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180084258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800842a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800842cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008468d`

## string_xrefs

- `0x180084195`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x18008422c`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084280`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084313`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x1800843ef`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084447`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x1800845ad`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x1800846f5`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084772`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`
- `0x180084384`: `CBackgroundCopyFile::SetProperty`
- `0x1800843c4`: `CBackgroundCopyFile::SetProperty`
- `0x18008449b`: `CBackgroundCopyFile::SetProperty`
- `0x180084511`: `CBackgroundCopyFile::SetProperty`
- `0x180084566`: `CBackgroundCopyFile::SetProperty`
- `0x1800845fc`: `CBackgroundCopyFile::SetProperty`
- `0x1800846bb`: `CBackgroundCopyFile::SetProperty`
- `0x180084732`: `CBackgroundCopyFile::SetProperty`
- `0x1800847ed`: `CBackgroundCopyFile::SetProperty`
- `0x180084559`: `File %s, DownloadSinkFilePath: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBackgroundCopyFile::SetProperty(CBackgroundCopyFile *this, unsigned int a2, const char **a3)
{
  __int64 v4; // r12
  __int64 result; // rax
  char v7; // r14
  int v8; // eax
  int v9; // eax
  const char *v10; // r9
  bool v11; // zf
  const char *v12; // r8
  int v13; // r9d
  char *v14; // rbx
  unsigned __int64 v15; // r14
  struct CGlobalObjects *v16; // rax
  const char *v17; // r14
  const char *v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // r8
  const char *v21; // rax
  const char *v22; // rdx
  int v23; // eax
  unsigned int v24; // r14d
  const char *v25; // rax
  unsigned int v26; // ecx
  const char *v27; // rax
  int v28; // eax
  unsigned int v29; // r14d
  const char *v30; // rax
  const char *v31; // rdx
  int v32; // eax
  unsigned int v33; // r14d
  volatile signed __int32 *v34; // rax
  const char *v35; // rax
  int v36; // [rsp+20h] [rbp-68h]
  int v37; // [rsp+20h] [rbp-68h]
  int v38; // [rsp+20h] [rbp-68h]
  int v39; // [rsp+20h] [rbp-68h]
  int v40; // [rsp+20h] [rbp-68h]
  __int128 v41; // [rsp+40h] [rbp-48h] BYREF
  __int128 v42; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v4 = (int)a2;
  if ( a2 >= 5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x584,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
      (const char *)0x80D02011LL,
      v36);
    return 2161123345LL;
  }
  if ( !a3 || (v7 = 0, ((*a3)[32] < 8u ? (*a3)[32] : 0) == 0) )
    v7 = 1;
  v42 = (unsigned __int64)this + 264;
  v8 = mtx_do_lock((char *)this + 264);
  try
  {
    if ( v8 )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 85) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 85) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v42) = 1;
    v9 = *((_DWORD *)this + 122);
    if ( (v9 & 4) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x589,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
        (const char *)0x80D02013LL,
        v36);
      v11 = (*((_DWORD *)this + 85))-- == 1;
      if ( v11 )
      {
        *((_DWORD *)this + 84) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
      }
      return 2161123347LL;
    }
    if ( v7 && (v9 & 0x18) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
        (const char *)0x80D02013LL,
        v36);
      v11 = (*((_DWORD *)this + 85))-- == 1;
      if ( v11 )
      {
        *((_DWORD *)this + 84) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
      }
      return 2161123347LL;
    }
    if ( this == (CBackgroundCopyFile *)-264LL )
      std::_Throw_system_error(1);
    v11 = (*((_DWORD *)this + 85))-- == 1;
    if ( v11 )
    {
      *((_DWORD *)this + 84) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
    }
    BYTE8(v42) = 0;
    if ( v7 )
    {
      v35 = (char *)this + 144;
      if ( *((_QWORD *)this + 21) > 0xFu )
        v35 = *(const char **)v35;
      LogMessage(5u, "CBackgroundCopyFile::SetProperty", 0x5D0u, "File %s: removing propId: %d", v35, v4);
      CBackgroundCopyFile::_RemoveProperty(this, (unsigned int)v4);
    }
    else
    {
      v12 = *a3;
      v13 = (*a3)[32];
      if ( *(_DWORD *)&asc_180135AC8[4 * v4] != ((*a3)[32] < 8u ? v13 : 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x592,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
          (const char *)0x80020008LL,
          v36);
        return 2147614728LL;
      }
      if ( (_DWORD)v4 )
      {
        switch ( (_DWORD)v4 )
        {
          case 1:
            v27 = (char *)this + 144;
            if ( *((_QWORD *)this + 21) > 0xFu )
              v27 = *(const char **)v27;
            LogMessage(4u, "CBackgroundCopyFile::SetProperty", 0x59Eu, "File %s, IntegrityCheckInfo", v27);
            if ( (*a3)[32] != 7 )
              std::_Throw_bad_variant_access();
            v28 = CBackgroundCopyFile::_SetPhfInfo((__int64)this, *a3);
            v29 = v28;
            if ( v28 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x59F,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                (const char *)(unsigned int)v28,
                v39);
              return v29;
            }
            break;
          case 2:
            if ( (_BYTE)v13 != 1 )
              std::_Throw_bad_variant_access();
            v25 = (char *)this + 144;
            if ( *((_QWORD *)this + 21) > 0xFu )
              v25 = *(const char **)v25;
            LogMessage(
              4u,
              "CBackgroundCopyFile::SetProperty",
              0x5A4u,
              "File %s, IntegrityCheckMandatory: %u",
              v25,
              *(unsigned __int8 *)v12);
            v41 = (unsigned __int64)this + 264;
            if ( (unsigned int)mtx_do_lock((char *)this + 264) )
              std::_Throw_Cpp_error(5);
            if ( *((_DWORD *)this + 85) == 0x7FFFFFFF )
            {
              *((_DWORD *)this + 85) = 2147483646;
              std::_Throw_Cpp_error(6);
            }
            BYTE8(v41) = 1;
            if ( (*a3)[32] != 1 )
              std::_Throw_bad_variant_access();
            v26 = *((_DWORD *)this + 122) | 0x20000;
            if ( !**a3 )
              v26 = *((_DWORD *)this + 122) & 0xFFFDFFFF;
            *((_DWORD *)this + 122) = v26;
            v11 = (*((_DWORD *)this + 85))-- == 1;
            if ( v11 )
            {
              *((_DWORD *)this + 84) = -1;
              ReleaseSRWLockExclusive((PSRWLOCK)this + 35);
            }
            break;
          case 3:
            if ( (_BYTE)v13 != 7 )
              std::_Throw_bad_variant_access();
            if ( *((_QWORD *)v12 + 3) > 0xFu )
              v12 = *(const char **)v12;
            v21 = (char *)this + 144;
            if ( *((_QWORD *)this + 21) > 0xFu )
              v21 = *(const char **)v21;
            LogMessage(4u, "CBackgroundCopyFile::SetProperty", 0x5B2u, "File %s, DownloadSinkFilePath: %s", v21, v12);
            v22 = *a3;
            if ( (*a3)[32] != 7 )
              std::_Throw_bad_variant_access();
            if ( *((_QWORD *)v22 + 3) > 0xFu )
              v22 = *(const char **)v22;
            v23 = CBackgroundCopyFile::_SetDownloadSinkFilePath(this, v22, 0);
            v24 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5B3,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                (const char *)(unsigned int)v23,
                v38);
              return v24;
            }
            break;
          case 4:
            if ( (_BYTE)v13 != 5 )
              std::_Throw_bad_variant_access();
            v15 = *(_QWORD *)v12;
            v16 = CGlobalObjects::Instance();
            if ( v15 > (unsigned __int64)(unsigned int)CGlobalConfigManager::GetConfigValue<unsigned int>(
                                                         *((_QWORD *)v16 + 2),
                                                         85) << 30 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5B9,
                (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                (const char *)0x800700DFLL,
                v36);
              return 2147942623LL;
            }
            if ( (*a3)[32] != 5 )
              std::_Throw_bad_variant_access();
            v17 = (char *)this + 144;
            v18 = (char *)this + 144;
            if ( *((_QWORD *)this + 21) > 0xFu )
              v18 = *(const char **)v17;
            LogMessage(
              4u,
              "CBackgroundCopyFile::SetProperty",
              0x5BAu,
              "File %s, TotalSizeBytes: %llu",
              v18,
              *(_QWORD *)*a3);
            v19 = *((_QWORD *)this + 50);
            if ( v19 )
            {
              if ( (*a3)[32] != 5 )
                std::_Throw_bad_variant_access();
              v20 = *(_QWORD *)*a3;
              if ( v20 )
              {
                if ( !*(_DWORD *)(v19 + 8) || v20 % *(unsigned int *)(v19 + 8) )
                {
                  if ( *((_QWORD *)this + 21) > 0xFu )
                    v17 = *(const char **)v17;
                  LogMessage(
                    3u,
                    "CBackgroundCopyFile::SetProperty",
                    0x5C1u,
                    "File %s, Ignoring invalid encrypted file size: %llu",
                    v17,
                    v20);
                  return 0;
                }
              }
            }
            break;
          default:
            v14 = (char *)this + 144;
            if ( *((_QWORD *)v14 + 3) > 0xFu )
              v14 = *(char **)v14;
            LogMessage(3u, "CBackgroundCopyFile::SetProperty", 0x5C7u, "File %s: Unhandled set property: %d", v14, v4);
            LogMessage(
              2u,
              "CBackgroundCopyFile::SetProperty",
              0x5C8u,
              "TelemetryAssert (%s): %s (0x%x, 0x%x)",
              "false",
              "Failed",
              v4,
              0);
            DOTelemetryAssertTriggered(v4, 0);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5C9,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
              (const char *)0x8000FFFFLL,
              v37);
            return 2147549183LL;
        }
      }
      else
      {
        v30 = (char *)this + 144;
        if ( *((_QWORD *)this + 21) > 0xFu )
          v30 = *(const char **)v30;
        LogMessage(4u, "CBackgroundCopyFile::SetProperty", 0x598u, "File %s, DecryptionInfo", v30);
        v31 = *a3;
        if ( (*a3)[32] != 7 )
          std::_Throw_bad_variant_access();
        if ( *((_QWORD *)v31 + 3) > 0xFu )
          v31 = *(const char **)v31;
        v32 = CBackgroundCopyFile::_SetDecryptionInfo(this, v31);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x599,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
            (const char *)(unsigned int)v32,
            v40);
          return v33;
        }
      }
      v41 = 0;
      v34 = (volatile signed __int32 *)a3[1];
      if ( v34 )
        _InterlockedIncrement(v34 + 2);
      v41 = *(_OWORD *)a3;
      CBackgroundCopyFile::_UpdateProperty(this, (unsigned int)v4, &v41);
    }
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5D5,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180084164  mov     [rsp+arg_18], rbx
0x180084169  push    rdi
0x18008416a  push    r12
0x18008416c  push    r13
0x18008416e  push    r14
0x180084170  push    r15
0x180084172  sub     rsp, 60h
0x180084176  mov     r15, r8
0x180084179  movsxd  r12, edx
0x18008417c  mov     rbx, rcx
0x18008417f  cmp     r12d, 5
0x180084183  jb      short loc_1800841AD
0x180084185  mov     rcx, [rsp+88h]; this
0x18008418d  mov     ebx, 80D02011h
0x180084192  mov     r9d, ebx; char *
0x180084195  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008419c  mov     edx, 584h; void *
0x1800841a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800841a6  mov     eax, ebx
0x1800841a8  jmp     loc_180084819
0x1800841ad  xor     r13d, r13d
0x1800841b0  test    r15, r15
0x1800841b3  jz      short loc_1800841C9
0x1800841b5  mov     rax, [r8]
0x1800841b8  movsx   ecx, byte ptr [rax+20h]
0x1800841bc  cmp     byte ptr [rax+20h], 8
0x1800841c0  sbb     eax, eax
0x1800841c2  test    ecx, eax
0x1800841c4  mov     r14b, r13b
0x1800841c7  jnz     short loc_1800841CC
0x1800841c9  mov     r14b, 1
0x1800841cc  xorps   xmm0, xmm0
0x1800841cf  movups  [rsp+88h+var_38], xmm0
0x1800841d4  lea     rdi, [rbx+108h]
0x1800841db  mov     qword ptr [rsp+88h+var_38], rdi
0x1800841e0  mov     byte ptr [rsp+88h+var_38+8], r13b
0x1800841e5  mov     rcx, rdi
0x1800841e8  call    mtx_do_lock
0x1800841ed  test    eax, eax
0x1800841ef  jnz     loc_18008482F
0x1800841f5  cmp     dword ptr [rbx+154h], 7FFFFFFFh
0x1800841ff  jz      loc_180084839
0x180084205  mov     byte ptr [rsp+88h+var_38+8], 1
0x18008420a  mov     eax, [rbx+1E8h]
0x180084210  mov     r11d, 4
0x180084216  test    r11b, al
0x180084219  jz      short loc_180084266
0x18008421b  mov     rcx, [rsp+88h]; this
0x180084223  mov     r14d, 80D02013h
0x180084229  mov     r9d, r14d; char *
0x18008422c  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180084233  mov     edx, 589h; void *
0x180084238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008423d  nop
0x18008423e  sub     dword ptr [rbx+154h], 1
0x180084245  jnz     short loc_18008425E
0x180084247  mov     dword ptr [rbx+150h], 0FFFFFFFFh
0x180084251  lea     rcx, [rbx+118h]; SRWLock
0x180084258  call    cs:__imp_ReleaseSRWLockExclusive
0x18008425e  mov     eax, r14d
0x180084261  jmp     loc_180084819
0x180084266  test    r14b, r14b
0x180084269  jz      short loc_1800842B1
0x18008426b  test    al, 18h
0x18008426d  jz      short loc_1800842B1
0x18008426f  mov     rcx, [rsp+88h]; this
0x180084277  mov     r14d, 80D02013h
0x18008427d  mov     r9d, r14d; char *
0x180084280  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180084287  mov     edx, 58Ch; void *
0x18008428c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084291  nop
0x180084292  sub     dword ptr [rdi+4Ch], 1
0x180084296  jnz     short loc_1800842A9
0x180084298  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x18008429f  lea     rcx, [rdi+10h]; SRWLock
0x1800842a3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800842a9  mov     eax, r14d
0x1800842ac  jmp     loc_180084819
0x1800842b1  test    rdi, rdi
0x1800842b4  jz      loc_18008489B
0x1800842ba  sub     dword ptr [rdi+4Ch], 1
0x1800842be  jnz     short loc_1800842D7
0x1800842c0  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x1800842c7  lea     rcx, [rdi+10h]; SRWLock
0x1800842cb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800842d1  mov     r11d, 4
0x1800842d7  mov     byte ptr [rsp+88h+var_38+8], r13b
0x1800842dc  test    r14b, r14b
0x1800842df  jnz     loc_1800847C5
0x1800842e5  mov     r8, [r15]
0x1800842e8  movsx   r9d, byte ptr [r8+20h]
0x1800842ed  lea     r10, asc_180135AC8; "\a"
0x1800842f4  cmp     r9b, 8
0x1800842f8  sbb     eax, eax
0x1800842fa  and     eax, r9d
0x1800842fd  cmp     [r10+r12*4], eax
0x180084301  jz      short loc_18008432C
0x180084303  mov     rcx, [rsp+88h]; this
0x18008430b  mov     ebx, 80020008h
0x180084310  mov     r9d, ebx; char *
0x180084313  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008431a  mov     edx, 592h; void *
0x18008431f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084324  nop
0x180084325  mov     eax, ebx
0x180084327  jmp     loc_180084819
0x18008432c  mov     ecx, r12d
0x18008432f  test    r12d, r12d
0x180084332  jz      loc_18008470F
0x180084338  sub     ecx, 1
0x18008433b  jz      loc_180084698
0x180084341  sub     ecx, 1
0x180084344  jz      loc_1800845C7
0x18008434a  sub     ecx, 1
0x18008434d  jz      loc_18008452A
0x180084353  cmp     ecx, 1
0x180084356  jz      loc_180084408
0x18008435c  add     rbx, 90h
0x180084363  cmp     qword ptr [rbx+18h], 0Fh
0x180084368  jbe     short loc_18008436D
0x18008436a  mov     rbx, [rbx]
0x18008436d  mov     dword ptr [rsp+88h+var_60], r12d
0x180084372  mov     qword ptr [rsp+88h+var_68], rbx
0x180084377  lea     r9, aFileSUnhandled; "File %s: Unhandled set property: %d"
0x18008437e  mov     r8d, 5C7h; unsigned int
0x180084384  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x18008438b  mov     ecx, 3; unsigned __int8
0x180084390  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084395  mov     [rsp+88h+var_50], r13
0x18008439a  mov     [rsp+88h+var_58], r12d
0x18008439f  lea     rax, aFailed; "Failed"
0x1800843a6  mov     [rsp+88h+var_60], rax
0x1800843ab  lea     rax, aFalse; "false"
0x1800843b2  mov     qword ptr [rsp+88h+var_68], rax; int
0x1800843b7  lea     r9, aTelemetryasser_0; "TelemetryAssert (%s): %s (0x%x, 0x%x)"
0x1800843be  mov     r8d, 5C8h; unsigned int
0x1800843c4  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x1800843cb  mov     ecx, 2; unsigned __int8
0x1800843d0  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800843d5  xor     edx, edx; unsigned int
0x1800843d7  mov     ecx, r12d; unsigned int
0x1800843da  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x1800843df  mov     rcx, [rsp+88h]; this
0x1800843e7  mov     ebx, 8000FFFFh
0x1800843ec  mov     r9d, ebx; char *
0x1800843ef  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800843f6  mov     edx, 5C9h; void *
0x1800843fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084400  nop
0x180084401  mov     eax, ebx
0x180084403  jmp     loc_180084819
0x180084408  cmp     r9b, 5
0x18008440c  jnz     loc_180084858
0x180084412  mov     r14, [r8]
0x180084415  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x18008441a  nop
0x18008441b  xor     r8d, r8d
0x18008441e  lea     edx, [r8+55h]
0x180084422  mov     rcx, [rax+10h]
0x180084426  call    ??$GetConfigValue@I@CGlobalConfigManager@@QEBAIW4Index@DOConfig@@PEAW4_ConfigProviderType@@@Z; CGlobalConfigManager::GetConfigValue<uint>(DOConfig::Index,_ConfigProviderType *)
0x18008442b  nop
0x18008442c  mov     ecx, eax
0x18008442e  shl     rcx, 1Eh
0x180084432  cmp     r14, rcx
0x180084435  jbe     short loc_180084460
0x180084437  mov     rcx, [rsp+88h]; this
0x18008443f  mov     ebx, 800700DFh
0x180084444  mov     r9d, ebx; char *
0x180084447  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008444e  mov     edx, 5B9h; void *
0x180084453  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180084458  nop
0x180084459  mov     eax, ebx
0x18008445b  jmp     loc_180084819
0x180084460  mov     rax, [r15]
0x180084463  cmp     byte ptr [rax+20h], 5
0x180084467  jnz     loc_180084853
0x18008446d  mov     rdx, [rax]
0x180084470  lea     r14, [rbx+90h]
0x180084477  mov     rax, r14
0x18008447a  cmp     qword ptr [r14+18h], 0Fh
0x18008447f  jbe     short loc_180084484
0x180084481  mov     rax, [r14]
0x180084484  mov     [rsp+88h+var_60], rdx
0x180084489  mov     qword ptr [rsp+88h+var_68], rax
0x18008448e  lea     r9, aFileSTotalsize; "File %s, TotalSizeBytes: %llu"
0x180084495  mov     r8d, 5BAh; unsigned int
0x18008449b  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x1800844a2  mov     ecx, 4; unsigned __int8
0x1800844a7  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800844ac  mov     rax, [rbx+190h]
0x1800844b3  test    rax, rax
0x1800844b6  jz      loc_18008478C
0x1800844bc  mov     r8, [r15]
0x1800844bf  cmp     byte ptr [r8+20h], 5
0x1800844c4  jnz     loc_18008484E
0x1800844ca  mov     r8, [r8]
0x1800844cd  test    r8, r8
0x1800844d0  jz      loc_18008478C
0x1800844d6  cmp     [rax+8], r13d
0x1800844da  jz      short loc_1800844F0
0x1800844dc  mov     ecx, [rax+8]
0x1800844df  xor     edx, edx
0x1800844e1  mov     rax, r8
0x1800844e4  div     rcx
0x1800844e7  test    rdx, rdx
0x1800844ea  jz      loc_18008478C
0x1800844f0  cmp     qword ptr [r14+18h], 0Fh
0x1800844f5  jbe     short loc_1800844FA
0x1800844f7  mov     r14, [r14]
0x1800844fa  mov     [rsp+88h+var_60], r8
0x1800844ff  mov     qword ptr [rsp+88h+var_68], r14
0x180084504  lea     r9, aFileSIgnoringI; "File %s, Ignoring invalid encrypted fil"...
0x18008450b  mov     r8d, 5C1h; unsigned int
0x180084511  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x180084518  mov     ecx, 3; unsigned __int8
0x18008451d  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084522  nop
0x180084523  xor     eax, eax
0x180084525  jmp     loc_180084819
0x18008452a  cmp     r9b, 7
0x18008452e  jnz     loc_180084862
0x180084534  cmp     qword ptr [r8+18h], 0Fh
0x180084539  jbe     short loc_18008453E
0x18008453b  mov     r8, [r8]
0x18008453e  lea     rax, [rbx+90h]
0x180084545  cmp     qword ptr [rax+18h], 0Fh
0x18008454a  jbe     short loc_18008454F
0x18008454c  mov     rax, [rax]
0x18008454f  mov     [rsp+88h+var_60], r8
0x180084554  mov     qword ptr [rsp+88h+var_68], rax; int
0x180084559  lea     r9, aFileSDownloads; "File %s, DownloadSinkFilePath: %s"
0x180084560  mov     r8d, 5B2h; unsigned int
0x180084566  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x18008456d  mov     ecx, r11d; unsigned __int8
0x180084570  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180084575  mov     rdx, [r15]
0x180084578  cmp     byte ptr [rdx+20h], 7
0x18008457c  jnz     loc_18008485D
0x180084582  cmp     qword ptr [rdx+18h], 0Fh
0x180084587  jbe     short loc_18008458C
0x180084589  mov     rdx, [rdx]; Src
0x18008458c  xor     r8d, r8d; bool
0x18008458f  mov     rcx, rbx; this
0x180084592  call    ?_SetDownloadSinkFilePath@CBackgroundCopyFile@@AEAAJPEBD_N@Z; CBackgroundCopyFile::_SetDownloadSinkFilePath(char const *,bool)
0x180084597  mov     r14d, eax
0x18008459a  test    eax, eax
0x18008459c  jns     loc_18008478C
0x1800845a2  mov     rcx, [rsp+88h]; this
0x1800845aa  mov     r9d, eax; char *
0x1800845ad  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800845b4  mov     edx, 5B3h; void *
0x1800845b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800845be  nop
0x1800845bf  mov     eax, r14d
0x1800845c2  jmp     loc_180084819
0x1800845c7  cmp     r9b, 1
0x1800845cb  jnz     loc_18008488C
0x1800845d1  movzx   ecx, byte ptr [r8]
0x1800845d5  lea     rax, [rbx+90h]
0x1800845dc  cmp     qword ptr [rax+18h], 0Fh
0x1800845e1  jbe     short loc_1800845E6
0x1800845e3  mov     rax, [rax]
0x1800845e6  mov     dword ptr [rsp+88h+var_60], ecx
0x1800845ea  mov     qword ptr [rsp+88h+var_68], rax
0x1800845ef  lea     r9, aFileSIntegrity_0; "File %s, IntegrityCheckMandatory: %u"
0x1800845f6  mov     r8d, 5A4h; unsigned int
0x1800845fc  lea     rdx, aCbackgroundcop_3; "CBackgroundCopyFile::SetProperty"
0x180084603  mov     ecx, r11d; unsigned __int8
0x180084606  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18008460b  xorps   xmm0, xmm0
0x18008460e  movups  [rsp+88h+var_48], xmm0
0x180084613  lea     rcx, [rbx+108h]
0x18008461a  mov     qword ptr [rsp+88h+var_48], rcx
0x18008461f  mov     byte ptr [rsp+88h+var_48+8], r13b
0x180084624  call    mtx_do_lock
0x180084629  test    eax, eax
0x18008462b  jnz     loc_180084867
0x180084631  cmp     dword ptr [rbx+154h], 7FFFFFFFh
0x18008463b  jz      loc_180084871
0x180084641  mov     byte ptr [rsp+88h+var_48+8], 1
0x180084646  mov     rdx, [r15]
0x180084649  cmp     byte ptr [rdx+20h], 1
0x18008464d  jnz     loc_180084886
0x180084653  mov     ecx, [rbx+1E8h]
0x180084659  mov     eax, ecx
0x18008465b  btr     eax, 11h
0x18008465f  bts     ecx, 11h
0x180084663  cmp     [rdx], r13b
0x180084666  cmovz   ecx, eax
0x180084669  mov     [rbx+1E8h], ecx
0x18008466f  sub     dword ptr [rbx+154h], 1
0x180084676  jnz     loc_18008478C
0x18008467c  mov     dword ptr [rbx+150h], 0FFFFFFFFh
0x180084686  lea     rcx, [rbx+118h]; SRWLock
0x18008468d  call    cs:__imp_ReleaseSRWLockExclusive
0x180084693  jmp     loc_18008478C
0x180084698  lea     rax, [rbx+90h]
0x18008469f  cmp     qword ptr [rax+18h], 0Fh
  ... truncated ...
```
