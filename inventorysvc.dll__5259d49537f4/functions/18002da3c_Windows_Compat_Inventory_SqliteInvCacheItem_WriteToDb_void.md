# Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)

- ea: `0x18002da3c`
- end: `0x18002dee0`
- name: `?WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ`
- size: `1188`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCacheItem *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029530`

## callees

- `0x180002bf0`
- `0x1800030e0`
- `0x1800052bc`
- `0x180005324`
- `0x180006a04`
- `0x180006e60`
- `0x1800074f0`
- `0x1800152d0`
- `0x18002da3c`
- `0x18002e010`
- `0x180036be4`
- `0x18009e660`
- `0x18009e760`
- `0x1800a1980`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ddff`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002ddff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002dd54`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002dd54`

## string_xrefs

- `0x18002db88`: `Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.`
- `0x18002dae4`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x18002db95`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x18002ddb9`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x18002de3e`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(
        Windows::Compat::Inventory::SqliteInvCacheItem *this)
{
  DWORD v2; // esi
  __int64 v3; // rcx
  unsigned int v4; // ebx
  _QWORD *v5; // r8
  __int64 v6; // r8
  int v7; // r14d
  __int64 *v8; // rax
  __int64 v9; // rcx
  const char *v10; // rax
  int v11; // ebx
  __int64 *v12; // rcx
  __int64 v13; // rdx
  unsigned __int64 v14; // r15
  __int64 v15; // r13
  _QWORD *ThreadLocalStoragePointer; // r9
  __int64 v17; // rcx
  __int128 *v18; // r8
  int v19; // eax
  __int64 v20; // rdx
  _OWORD *v21; // rax
  int v22; // esi
  _QWORD *v23; // r8
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rcx
  int v28; // eax
  int v29; // esi
  __int64 *v30; // r15
  __int64 v31; // rcx
  __int64 *v32; // rax
  __int64 v33; // rcx
  const char *v34; // rax
  __int64 v35; // rax
  const char *v36; // r9
  __int64 v37; // r8
  int i; // r14d
  __int64 *v39; // rax
  __int64 v40; // rcx
  __int64 v42; // [rsp+20h] [rbp-49h]
  __int64 v43; // [rsp+28h] [rbp-41h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-39h] BYREF
  _OWORD v45[2]; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v46[4]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v47[32]; // [rsp+78h] [rbp+Fh] BYREF

  v2 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  v3 = *((_QWORD *)this + 5);
  if ( !v3 )
    return 0;
  v4 = 0;
  if ( !*((_BYTE *)this + 80) )
    return v4;
  v5 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) > 7u )
    v5 = (_QWORD *)*v5;
  v7 = bindText(v3, 1, (_DWORD)v5, -2, 0, 2, SystemTimeAsFileTime);
  if ( v7 )
  {
    v8 = (__int64 *)*((_QWORD *)this + 5);
    if ( v8 )
      v9 = *v8;
    else
      v9 = 0;
    v10 = (const char *)sqlite3_errmsg(v9);
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
      324,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v7,
      v10);
    if ( v7 <= 0 )
      return (unsigned int)v7;
    v11 = (unsigned __int16)v7;
    return v11 | 0x80070000;
  }
  v12 = (__int64 *)*((_QWORD *)this + 6);
  v13 = *v12;
  if ( !((v12[1] - *v12) >> 4) )
  {
LABEL_47:
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v29 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))sqlite3_bind_int64)(
            *((_QWORD *)this + 5),
            (unsigned int)((__int64)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL) - **((_QWORD **)this + 6)) >> 4) + 2,
            SystemTimeAsFileTime);
    v30 = (__int64 *)*((_QWORD *)this + 5);
    if ( v29 )
    {
      if ( v30 )
        v31 = *v30;
      else
        v31 = 0;
      v35 = sqlite3_errmsg(v31);
      v36 = "sqlite3_bind_int64 failed: [%d] %hs";
      v37 = 367;
    }
    else
    {
      for ( i = 0; i < 100; ++i )
      {
        v29 = sqlite3_step(v30);
        if ( (unsigned int)(v29 - 5) > 1 )
          break;
        Sleep(5u);
      }
      if ( v29 == 101 )
        return v4;
      v39 = (__int64 *)*((_QWORD *)this + 5);
      if ( v39 )
        v40 = *v39;
      else
        v40 = 0;
      v35 = sqlite3_errmsg(v40);
      v36 = "sqlite3_step failed: [%d] %hs";
      v37 = 375;
    }
    LODWORD(v42) = v29;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb", v37, v36, v42, v35);
    if ( v29 <= 0 )
      return (unsigned int)v29;
    v11 = (unsigned __int16)v29;
    return v11 | 0x80070000;
  }
  v14 = 0;
  v15 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  while ( 1 )
  {
    if ( (v12[1] - v13) >> 4 <= (unsigned __int64)(int)v14 )
      std::vector<Windows::Compat::Inventory::Service::Win32AppInfo>::_Xrange(v12, v13, v6, ThreadLocalStoragePointer);
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 1 )
    {
      v27 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(104LL * (int)v14 + v27 + 44) )
        v28 = *(_DWORD *)(104LL * (int)v14 + v27 + 40);
      else
        v28 = 0;
      v26 = v28;
      goto LABEL_43;
    }
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 2 )
    {
      v25 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(v25 + 104LL * (int)v14 + 56) )
        v26 = *(_QWORD *)(v25 + 104LL * (int)v14 + 48);
      else
        v26 = 0;
LABEL_43:
      v19 = sqlite3_bind_int64(*((_QWORD *)this + 5), (unsigned int)(v14 + 2), v26);
LABEL_44:
      v24 = v19;
      goto LABEL_45;
    }
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 3 )
      break;
    if ( *(_DWORD *)(v13 + 16LL * (int)v14 + 8) == 4 )
    {
      if ( __TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA > *(_DWORD *)(ThreadLocalStoragePointer[v15] + 4LL) )
      {
        Init_thread_header(&__TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA);
        if ( __TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA == -1 )
        {
          `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::emptyVector = 0;
          qword_1800FF438 = 0;
          atexit(`Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::`dynamic atexit destructor for 'emptyVector'');
          Init_thread_footer(&__TSS0__BA___WriteToDb_SqliteInvCacheItem_Inventory_Compat_Windows__QEAAJXZ_4HA);
        }
      }
      v17 = *((_QWORD *)this + 7);
      if ( *(_BYTE *)(v17 + 104LL * (int)v14 + 88) )
      {
        v18 = (__int128 *)(104LL * (int)v14 + v17 + 64);
        if ( !*((_BYTE *)v18 + 24) )
          __int2c();
      }
      else
      {
        v18 = &`Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb'::`16'::emptyVector;
      }
      v19 = sqlite3_bind_blob(
              *((_QWORD *)this + 5),
              (int)v14 + 2,
              *(_QWORD *)v18,
              *((_DWORD *)v18 + 2) - *(_DWORD *)v18,
              0);
      goto LABEL_44;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
      351,
      "Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.",
      *(_DWORD *)(v13 + 16LL * (int)v14 + 8),
      v14);
LABEL_46:
    ++v14;
    v12 = (__int64 *)*((_QWORD *)this + 6);
    v13 = *v12;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    if ( v14 >= (v12[1] - *v12) >> 4 )
      goto LABEL_47;
  }
  v20 = 104LL * (int)v14 + *((_QWORD *)this + 7);
  if ( *(_BYTE *)(v20 + 32) )
  {
    v21 = (_OWORD *)std::wstring::wstring(v47, v20);
    v22 = v2 | 1;
  }
  else
  {
    memset(v45, 0, sizeof(v45));
    std::wstring::_Construct<1,unsigned short const *>(v45, &cchOriginalDestLength, 0);
    v21 = v45;
    v22 = v2 | 2;
  }
  std::wstring::wstring(v46, v21);
  v2 = v22 | 4;
  SystemTimeAsFileTime.dwLowDateTime = v2;
  if ( (v2 & 2) != 0 )
  {
    v2 &= ~2u;
    SystemTimeAsFileTime.dwLowDateTime = v2;
    std::wstring::~wstring(v45);
  }
  if ( (v2 & 1) != 0 )
  {
    v2 &= ~1u;
    SystemTimeAsFileTime.dwLowDateTime = v2;
    std::wstring::~wstring(v47);
  }
  v23 = v46;
  if ( v46[3] > 7u )
    LODWORD(v23) = v46[0];
  LOBYTE(v43) = 2;
  v24 = bindText(*((_QWORD *)this + 5), (int)v14 + 2, (_DWORD)v23, -2, 0, v43, SystemTimeAsFileTime);
  std::wstring::~wstring(v46);
LABEL_45:
  if ( !v24 )
    goto LABEL_46;
  v32 = (__int64 *)*((_QWORD *)this + 5);
  if ( v32 )
    v33 = *v32;
  else
    v33 = 0;
  v34 = (const char *)sqlite3_errmsg(v33);
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb",
    356,
    "sqlite3_bind failed: [%d] %hs",
    v24,
    v34);
  return v4;
}

```

## disassembly

```asm
0x18002da3c  mov     [rsp-8+arg_8], rbx
0x18002da41  mov     [rsp-8+arg_10], rsi
0x18002da46  push    rbp
0x18002da47  push    rdi
0x18002da48  push    r13
0x18002da4a  push    r14
0x18002da4c  push    r15
0x18002da4e  lea     rbp, [rsp-37h]
0x18002da53  sub     rsp, 0A0h
0x18002da5a  mov     rax, cs:__security_cookie
0x18002da61  xor     rax, rsp
0x18002da64  mov     [rbp+57h+var_28], rax
0x18002da68  mov     rdi, rcx
0x18002da6b  xor     esi, esi
0x18002da6d  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x18002da70  mov     rcx, [rcx+28h]
0x18002da74  test    rcx, rcx
0x18002da77  jz      loc_18002DE64
0x18002da7d  xor     ebx, ebx
0x18002da7f  cmp     [rdi+50h], bl
0x18002da82  jz      loc_18002DE60
0x18002da88  lea     r8, [rdi+8]
0x18002da8c  cmp     qword ptr [r8+18h], 7
0x18002da91  jbe     short loc_18002DA96
0x18002da93  mov     r8, [r8]
0x18002da96  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002da9b  mov     [rsp+0C0h+var_A0], rbx
0x18002daa0  mov     edx, 1
0x18002daa5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002daac  call    bindText
0x18002dab1  mov     r14d, eax
0x18002dab4  test    eax, eax
0x18002dab6  jz      short loc_18002DB0B
0x18002dab8  mov     rax, [rdi+28h]
0x18002dabc  test    rax, rax
0x18002dabf  jz      short loc_18002DAC6
0x18002dac1  mov     rcx, [rax]
0x18002dac4  jmp     short loc_18002DAC8
0x18002dac6  xor     ecx, ecx
0x18002dac8  call    sqlite3_errmsg
0x18002dacd  mov     [rsp+0C0h+var_98], rax
0x18002dad2  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18002dad7  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x18002dade  mov     r8d, 144h
0x18002dae4  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002daeb  mov     ecx, 1
0x18002daf0  call    AslLogCallPrintf
0x18002daf5  test    r14d, r14d
0x18002daf8  jg      short loc_18002DB02
0x18002dafa  mov     ebx, r14d
0x18002dafd  jmp     loc_18002DE60
0x18002db02  movzx   ebx, r14w
0x18002db06  jmp     loc_18002DE5A
0x18002db0b  mov     rcx, [rdi+30h]
0x18002db0f  mov     rdx, [rcx]
0x18002db12  mov     rax, [rcx+8]
0x18002db16  sub     rax, rdx
0x18002db19  sar     rax, 4
0x18002db1d  test    rax, rax
0x18002db20  jz      loc_18002DD48
0x18002db26  xor     r15d, r15d
0x18002db29  mov     r13d, cs:_tls_index
0x18002db30  mov     r9, gs:58h
0x18002db39  movsxd  r14, r15d
0x18002db3c  mov     rax, [rcx+8]
0x18002db40  sub     rax, rdx
0x18002db43  sar     rax, 4
0x18002db47  cmp     rax, r14
0x18002db4a  jbe     loc_18002DE8E
0x18002db50  mov     rax, r14
0x18002db53  add     rax, rax
0x18002db56  mov     r8d, [rdx+rax*8+8]
0x18002db5b  mov     ecx, r8d
0x18002db5e  sub     ecx, 1
0x18002db61  jz      loc_18002DCF2
0x18002db67  sub     ecx, 1
0x18002db6a  jz      loc_18002DCD6
0x18002db70  sub     ecx, 1
0x18002db73  jz      loc_18002DC0E
0x18002db79  cmp     ecx, 1
0x18002db7c  jz      short loc_18002DBAB
0x18002db7e  mov     dword ptr [rsp+0C0h+var_98], r15d
0x18002db83  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x18002db88  lea     r9, aUnsupportedCac; "Unsupported CacheItemPropertyType '%d' "...
0x18002db8f  mov     r8d, 15Fh
0x18002db95  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002db9c  mov     ecx, 1
0x18002dba1  call    AslLogCallPrintf
0x18002dba6  jmp     loc_18002DD21
0x18002dbab  mov     ecx, 4
0x18002dbb0  mov     rax, [r9+r13*8]
0x18002dbb4  mov     ecx, [rcx+rax]
0x18002dbb7  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, ecx
0x18002dbbd  jg      loc_18002DE94
0x18002dbc3  imul    rax, r14, 68h ; 'h'
0x18002dbc7  mov     rcx, [rdi+38h]
0x18002dbcb  xor     r10d, r10d
0x18002dbce  cmp     [rcx+rax+58h], r10b
0x18002dbd3  jz      short loc_18002DBE6
0x18002dbd5  lea     r8, [rcx+40h]
0x18002dbd9  add     r8, rax
0x18002dbdc  cmp     [r8+18h], r10b
0x18002dbe0  jnz     short loc_18002DBED
0x18002dbe2  int     2Ch; Windows NT - assertion failure
0x18002dbe4  jmp     short loc_18002DBED
0x18002dbe6  lea     r8, ?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x18002dbed  mov     r9d, [r8+8]
0x18002dbf1  sub     r9d, [r8]
0x18002dbf4  lea     edx, [r15+2]
0x18002dbf8  mov     [rsp+0C0h+var_A0], r10
0x18002dbfd  mov     r8, [r8]
0x18002dc00  mov     rcx, [rdi+28h]
0x18002dc04  call    sqlite3_bind_blob
0x18002dc09  jmp     loc_18002DD19
0x18002dc0e  imul    rcx, r14, 68h ; 'h'
0x18002dc12  mov     rdx, [rdi+38h]
0x18002dc16  add     rdx, rcx
0x18002dc19  cmp     byte ptr [rdx+20h], 0
0x18002dc1d  jz      short loc_18002DC2E
0x18002dc1f  lea     rcx, [rbp+57h+var_48]
0x18002dc23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dc28  nop
0x18002dc29  or      esi, 1
0x18002dc2c  jmp     short loc_18002DC57
0x18002dc2e  xorps   xmm0, xmm0
0x18002dc31  movups  [rbp+57h+var_88], xmm0
0x18002dc35  xorps   xmm1, xmm1
0x18002dc38  movdqu  [rbp+57h+var_78], xmm1
0x18002dc3d  xor     r8d, r8d
0x18002dc40  lea     rdx, cchOriginalDestLength
0x18002dc47  lea     rcx, [rbp+57h+var_88]
0x18002dc4b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002dc50  lea     rax, [rbp+57h+var_88]
0x18002dc54  or      esi, 2
0x18002dc57  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x18002dc5a  mov     rdx, rax
0x18002dc5d  lea     rcx, [rbp+57h+var_68]
0x18002dc61  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002dc66  or      esi, 4
0x18002dc69  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x18002dc6c  test    sil, 2
0x18002dc70  jz      short loc_18002DC82
0x18002dc72  and     esi, 0FFFFFFFDh
0x18002dc75  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x18002dc78  lea     rcx, [rbp+57h+var_88]; void *
0x18002dc7c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dc81  nop
0x18002dc82  test    sil, 1
0x18002dc86  jz      short loc_18002DC98
0x18002dc88  and     esi, 0FFFFFFFEh
0x18002dc8b  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x18002dc8e  lea     rcx, [rbp+57h+var_48]; void *
0x18002dc92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dc97  nop
0x18002dc98  lea     r8, [rbp+57h+var_68]
0x18002dc9c  cmp     [rbp+57h+var_50], 7
0x18002dca1  cmova   r8, [rbp+57h+var_68]
0x18002dca6  lea     edx, [r15+2]
0x18002dcaa  mov     byte ptr [rsp+0C0h+var_98], 2
0x18002dcaf  mov     [rsp+0C0h+var_A0], 0
0x18002dcb8  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002dcbf  mov     rcx, [rdi+28h]
0x18002dcc3  call    bindText
0x18002dcc8  mov     r14d, eax
0x18002dccb  lea     rcx, [rbp+57h+var_68]; void *
0x18002dccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002dcd4  jmp     short loc_18002DD1C
0x18002dcd6  imul    r8, r14, 68h ; 'h'
0x18002dcda  mov     rax, [rdi+38h]
0x18002dcde  cmp     byte ptr [rax+r8+38h], 0
0x18002dce4  jz      short loc_18002DCED
0x18002dce6  mov     r8, [rax+r8+30h]
0x18002dceb  jmp     short loc_18002DD0C
0x18002dced  xor     r8d, r8d
0x18002dcf0  jmp     short loc_18002DD0C
0x18002dcf2  imul    rax, r14, 68h ; 'h'
0x18002dcf6  mov     rcx, [rdi+38h]
0x18002dcfa  cmp     byte ptr [rax+rcx+2Ch], 0
0x18002dcff  jz      short loc_18002DD07
0x18002dd01  mov     eax, [rax+rcx+28h]
0x18002dd05  jmp     short loc_18002DD09
0x18002dd07  xor     eax, eax
0x18002dd09  movsxd  r8, eax
0x18002dd0c  lea     edx, [r15+2]
0x18002dd10  mov     rcx, [rdi+28h]
0x18002dd14  call    sqlite3_bind_int64
0x18002dd19  mov     r14d, eax
0x18002dd1c  test    r14d, r14d
0x18002dd1f  jnz     short loc_18002DD8D
0x18002dd21  inc     r15
0x18002dd24  mov     rcx, [rdi+30h]
0x18002dd28  mov     rdx, [rcx]
0x18002dd2b  mov     rax, [rcx+8]
0x18002dd2f  sub     rax, rdx
0x18002dd32  sar     rax, 4
0x18002dd36  cmp     r15, rax
0x18002dd39  mov     r9, gs:58h
0x18002dd42  jb      loc_18002DB39
0x18002dd48  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002dd50  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002dd54  call    cs:__imp_GetSystemTimeAsFileTime
0x18002dd5a  mov     rax, [rdi+30h]
0x18002dd5e  mov     rdx, [rax+8]
0x18002dd62  sub     rdx, [rax]
0x18002dd65  sar     rdx, 4
0x18002dd69  add     edx, 2
0x18002dd6c  mov     r8, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x18002dd70  mov     rcx, [rdi+28h]
0x18002dd74  call    sqlite3_bind_int64
0x18002dd79  mov     esi, eax
0x18002dd7b  mov     r15, [rdi+28h]
0x18002dd7f  test    eax, eax
0x18002dd81  jz      short loc_18002DDE5
0x18002dd83  test    r15, r15
0x18002dd86  jz      short loc_18002DDCF
0x18002dd88  mov     rcx, [r15]
0x18002dd8b  jmp     short loc_18002DDD1
0x18002dd8d  mov     rax, [rdi+28h]
0x18002dd91  test    rax, rax
0x18002dd94  jz      short loc_18002DD9B
0x18002dd96  mov     rcx, [rax]
0x18002dd99  jmp     short loc_18002DD9D
0x18002dd9b  xor     ecx, ecx
0x18002dd9d  call    sqlite3_errmsg
0x18002dda2  mov     [rsp+0C0h+var_98], rax
0x18002dda7  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18002ddac  lea     r9, aSqlite3BindFai; "sqlite3_bind failed: [%d] %hs"
0x18002ddb3  mov     r8d, 164h
0x18002ddb9  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002ddc0  mov     ecx, 1
0x18002ddc5  call    AslLogCallPrintf
0x18002ddca  jmp     loc_18002DE60
0x18002ddcf  xor     ecx, ecx
0x18002ddd1  call    sqlite3_errmsg
0x18002ddd6  lea     r9, aSqlite3BindInt; "sqlite3_bind_int64 failed: [%d] %hs"
0x18002dddd  mov     r8d, 16Fh
0x18002dde3  jmp     short loc_18002DE35
0x18002dde5  xor     r14d, r14d
0x18002dde8  mov     rcx, r15
0x18002ddeb  call    sqlite3_step
0x18002ddf0  mov     esi, eax
0x18002ddf2  add     eax, 0FFFFFFFBh
0x18002ddf5  cmp     eax, 1
0x18002ddf8  ja      short loc_18002DE0E
0x18002ddfa  mov     ecx, 5; dwMilliseconds
0x18002ddff  call    cs:__imp_Sleep
0x18002de05  inc     r14d
0x18002de08  cmp     r14d, 64h ; 'd'
0x18002de0c  jl      short loc_18002DDE8
0x18002de0e  cmp     esi, 65h ; 'e'
0x18002de11  jz      short loc_18002DE60
0x18002de13  mov     rax, [rdi+28h]
0x18002de17  test    rax, rax
0x18002de1a  jz      short loc_18002DE21
0x18002de1c  mov     rcx, [rax]
0x18002de1f  jmp     short loc_18002DE23
0x18002de21  xor     ecx, ecx
0x18002de23  call    sqlite3_errmsg
0x18002de28  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x18002de2f  mov     r8d, 177h
0x18002de35  mov     [rsp+0C0h+var_98], rax
0x18002de3a  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18002de3e  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002de45  mov     ecx, 1
0x18002de4a  call    AslLogCallPrintf
0x18002de4f  test    esi, esi
0x18002de51  jg      short loc_18002DE57
0x18002de53  mov     ebx, esi
0x18002de55  jmp     short loc_18002DE60
0x18002de57  movzx   ebx, si
0x18002de5a  or      ebx, 80070000h
0x18002de60  mov     eax, ebx
0x18002de62  jmp     short loc_18002DE66
0x18002de64  xor     eax, eax
0x18002de66  mov     rcx, [rbp+57h+var_28]
0x18002de6a  xor     rcx, rsp; StackCookie
0x18002de6d  call    __security_check_cookie
0x18002de72  lea     r11, [rsp+0C0h+var_20]
0x18002de7a  mov     rbx, [r11+38h]
0x18002de7e  mov     rsi, [r11+40h]
0x18002de82  mov     rsp, r11
0x18002de85  pop     r15
0x18002de87  pop     r14
0x18002de89  pop     r13
0x18002de8b  pop     rdi
0x18002de8c  pop     rbp
0x18002de8d  retn
0x18002de8e  call    ?_Xrange@?$vector@UWin32AppInfo@Service@Inventory@Compat@Windows@@V?$allocator@UWin32AppInfo@Service@Inventory@Compat@Windows@@@std@@@std@@CAXXZ; std::vector<Windows::Compat::Inventory::Service::Win32AppInfo>::_Xrange(void)
0x18002de94  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x18002de9b  call    _Init_thread_header
0x18002dea0  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, 0FFFFFFFFh
0x18002dea7  jnz     loc_18002DBC3
0x18002dead  xorps   xmm0, xmm0
0x18002deb0  movdqu  cs:?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A, xmm0; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x18002deb8  mov     cs:qword_1800FF438, 0
0x18002dec3  lea     rcx, ??__FemptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@YAXXZ; void (__cdecl *)()
0x18002deca  call    atexit
0x18002decf  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x18002ded6  call    _Init_thread_footer
0x18002dedb  jmp     loc_18002DBC3
  ... truncated ...
```
