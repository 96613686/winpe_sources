# Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)

- ea: `0x1800310b4`
- end: `0x180031558`
- name: `?WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ`
- size: `1188`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCacheItem *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18002ea40`

## callees

- `0x180005e40`
- `0x1800061f0`
- `0x18000642c`
- `0x180006494`
- `0x18000fa50`
- `0x180017600`
- `0x180018e90`
- `0x1800310b4`
- `0x180031688`
- `0x180066c10`
- `0x18007ee44`
- `0x1800e68c0`
- `0x1800e69c0`
- `0x1800e9be0`
- `0x1800ec8f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800313cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800313cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031477`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180031477`

## string_xrefs

- `0x180031200`: `Unsupported CacheItemPropertyType '%d' for column %d in SqliteInvCacheItem.`
- `0x18003115c`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x18003120d`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x180031431`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`
- `0x1800314b6`: `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb`

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
      std::vector<IAmiInventoryItem::_CacheItemProperty>::_Xrange(v12, v13, v6, ThreadLocalStoragePointer);
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
          qword_180156EC0 = 0;
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
    std::wstring::_Construct<1,unsigned short const *>(v45, &S2, 0);
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
0x1800310b4  mov     [rsp-8+arg_8], rbx
0x1800310b9  mov     [rsp-8+arg_10], rsi
0x1800310be  push    rbp
0x1800310bf  push    rdi
0x1800310c0  push    r13
0x1800310c2  push    r14
0x1800310c4  push    r15
0x1800310c6  lea     rbp, [rsp-37h]
0x1800310cb  sub     rsp, 0A0h
0x1800310d2  mov     rax, cs:__security_cookie
0x1800310d9  xor     rax, rsp
0x1800310dc  mov     [rbp+57h+var_28], rax
0x1800310e0  mov     rdi, rcx
0x1800310e3  xor     esi, esi
0x1800310e5  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x1800310e8  mov     rcx, [rcx+28h]
0x1800310ec  test    rcx, rcx
0x1800310ef  jz      loc_1800314DC
0x1800310f5  xor     ebx, ebx
0x1800310f7  cmp     [rdi+50h], bl
0x1800310fa  jz      loc_1800314D8
0x180031100  lea     r8, [rdi+8]
0x180031104  cmp     qword ptr [r8+18h], 7
0x180031109  jbe     short loc_18003110E
0x18003110b  mov     r8, [r8]
0x18003110e  mov     byte ptr [rsp+0C0h+var_98], 2
0x180031113  mov     [rsp+0C0h+var_A0], rbx
0x180031118  mov     edx, 1
0x18003111d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180031124  call    bindText
0x180031129  mov     r14d, eax
0x18003112c  test    eax, eax
0x18003112e  jz      short loc_180031183
0x180031130  mov     rax, [rdi+28h]
0x180031134  test    rax, rax
0x180031137  jz      short loc_18003113E
0x180031139  mov     rcx, [rax]
0x18003113c  jmp     short loc_180031140
0x18003113e  xor     ecx, ecx
0x180031140  call    sqlite3_errmsg
0x180031145  mov     [rsp+0C0h+var_98], rax
0x18003114a  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x18003114f  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180031156  mov     r8d, 144h
0x18003115c  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x180031163  mov     ecx, 1
0x180031168  call    AslLogCallPrintf
0x18003116d  test    r14d, r14d
0x180031170  jg      short loc_18003117A
0x180031172  mov     ebx, r14d
0x180031175  jmp     loc_1800314D8
0x18003117a  movzx   ebx, r14w
0x18003117e  jmp     loc_1800314D2
0x180031183  mov     rcx, [rdi+30h]
0x180031187  mov     rdx, [rcx]
0x18003118a  mov     rax, [rcx+8]
0x18003118e  sub     rax, rdx
0x180031191  sar     rax, 4
0x180031195  test    rax, rax
0x180031198  jz      loc_1800313C0
0x18003119e  xor     r15d, r15d
0x1800311a1  mov     r13d, cs:_tls_index
0x1800311a8  mov     r9, gs:58h
0x1800311b1  movsxd  r14, r15d
0x1800311b4  mov     rax, [rcx+8]
0x1800311b8  sub     rax, rdx
0x1800311bb  sar     rax, 4
0x1800311bf  cmp     rax, r14
0x1800311c2  jbe     loc_180031506
0x1800311c8  mov     rax, r14
0x1800311cb  add     rax, rax
0x1800311ce  mov     r8d, [rdx+rax*8+8]
0x1800311d3  mov     ecx, r8d
0x1800311d6  sub     ecx, 1
0x1800311d9  jz      loc_18003136A
0x1800311df  sub     ecx, 1
0x1800311e2  jz      loc_18003134E
0x1800311e8  sub     ecx, 1
0x1800311eb  jz      loc_180031286
0x1800311f1  cmp     ecx, 1
0x1800311f4  jz      short loc_180031223
0x1800311f6  mov     dword ptr [rsp+0C0h+var_98], r15d
0x1800311fb  mov     dword ptr [rsp+0C0h+var_A0], r8d
0x180031200  lea     r9, aUnsupportedCac; "Unsupported CacheItemPropertyType '%d' "...
0x180031207  mov     r8d, 15Fh
0x18003120d  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x180031214  mov     ecx, 1
0x180031219  call    AslLogCallPrintf
0x18003121e  jmp     loc_180031399
0x180031223  mov     ecx, 4
0x180031228  mov     rax, [r9+r13*8]
0x18003122c  mov     ecx, [rcx+rax]
0x18003122f  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, ecx
0x180031235  jg      loc_18003150C
0x18003123b  imul    rax, r14, 68h ; 'h'
0x18003123f  mov     rcx, [rdi+38h]
0x180031243  xor     r10d, r10d
0x180031246  cmp     [rcx+rax+58h], r10b
0x18003124b  jz      short loc_18003125E
0x18003124d  lea     r8, [rcx+40h]
0x180031251  add     r8, rax
0x180031254  cmp     [r8+18h], r10b
0x180031258  jnz     short loc_180031265
0x18003125a  int     2Ch; Windows NT - assertion failure
0x18003125c  jmp     short loc_180031265
0x18003125e  lea     r8, ?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x180031265  mov     r9d, [r8+8]
0x180031269  sub     r9d, [r8]
0x18003126c  lea     edx, [r15+2]
0x180031270  mov     [rsp+0C0h+var_A0], r10
0x180031275  mov     r8, [r8]
0x180031278  mov     rcx, [rdi+28h]
0x18003127c  call    sqlite3_bind_blob
0x180031281  jmp     loc_180031391
0x180031286  imul    rcx, r14, 68h ; 'h'
0x18003128a  mov     rdx, [rdi+38h]
0x18003128e  add     rdx, rcx
0x180031291  cmp     byte ptr [rdx+20h], 0
0x180031295  jz      short loc_1800312A6
0x180031297  lea     rcx, [rbp+57h+var_48]
0x18003129b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800312a0  nop
0x1800312a1  or      esi, 1
0x1800312a4  jmp     short loc_1800312CF
0x1800312a6  xorps   xmm0, xmm0
0x1800312a9  movups  [rbp+57h+var_88], xmm0
0x1800312ad  xorps   xmm1, xmm1
0x1800312b0  movdqu  [rbp+57h+var_78], xmm1
0x1800312b5  xor     r8d, r8d
0x1800312b8  lea     rdx, S2
0x1800312bf  lea     rcx, [rbp+57h+var_88]
0x1800312c3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800312c8  lea     rax, [rbp+57h+var_88]
0x1800312cc  or      esi, 2
0x1800312cf  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x1800312d2  mov     rdx, rax
0x1800312d5  lea     rcx, [rbp+57h+var_68]
0x1800312d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800312de  or      esi, 4
0x1800312e1  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x1800312e4  test    sil, 2
0x1800312e8  jz      short loc_1800312FA
0x1800312ea  and     esi, 0FFFFFFFDh
0x1800312ed  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x1800312f0  lea     rcx, [rbp+57h+var_88]; void *
0x1800312f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800312f9  nop
0x1800312fa  test    sil, 1
0x1800312fe  jz      short loc_180031310
0x180031300  and     esi, 0FFFFFFFEh
0x180031303  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180031306  lea     rcx, [rbp+57h+var_48]; void *
0x18003130a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003130f  nop
0x180031310  lea     r8, [rbp+57h+var_68]
0x180031314  cmp     [rbp+57h+var_50], 7
0x180031319  cmova   r8, [rbp+57h+var_68]
0x18003131e  lea     edx, [r15+2]
0x180031322  mov     byte ptr [rsp+0C0h+var_98], 2
0x180031327  mov     [rsp+0C0h+var_A0], 0
0x180031330  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180031337  mov     rcx, [rdi+28h]
0x18003133b  call    bindText
0x180031340  mov     r14d, eax
0x180031343  lea     rcx, [rbp+57h+var_68]; void *
0x180031347  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003134c  jmp     short loc_180031394
0x18003134e  imul    r8, r14, 68h ; 'h'
0x180031352  mov     rax, [rdi+38h]
0x180031356  cmp     byte ptr [rax+r8+38h], 0
0x18003135c  jz      short loc_180031365
0x18003135e  mov     r8, [rax+r8+30h]
0x180031363  jmp     short loc_180031384
0x180031365  xor     r8d, r8d
0x180031368  jmp     short loc_180031384
0x18003136a  imul    rax, r14, 68h ; 'h'
0x18003136e  mov     rcx, [rdi+38h]
0x180031372  cmp     byte ptr [rax+rcx+2Ch], 0
0x180031377  jz      short loc_18003137F
0x180031379  mov     eax, [rax+rcx+28h]
0x18003137d  jmp     short loc_180031381
0x18003137f  xor     eax, eax
0x180031381  movsxd  r8, eax
0x180031384  lea     edx, [r15+2]
0x180031388  mov     rcx, [rdi+28h]
0x18003138c  call    sqlite3_bind_int64
0x180031391  mov     r14d, eax
0x180031394  test    r14d, r14d
0x180031397  jnz     short loc_180031405
0x180031399  inc     r15
0x18003139c  mov     rcx, [rdi+30h]
0x1800313a0  mov     rdx, [rcx]
0x1800313a3  mov     rax, [rcx+8]
0x1800313a7  sub     rax, rdx
0x1800313aa  sar     rax, 4
0x1800313ae  cmp     r15, rax
0x1800313b1  mov     r9, gs:58h
0x1800313ba  jb      loc_1800311B1
0x1800313c0  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800313c8  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800313cc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800313d2  mov     rax, [rdi+30h]
0x1800313d6  mov     rdx, [rax+8]
0x1800313da  sub     rdx, [rax]
0x1800313dd  sar     rdx, 4
0x1800313e1  add     edx, 2
0x1800313e4  mov     r8, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800313e8  mov     rcx, [rdi+28h]
0x1800313ec  call    sqlite3_bind_int64
0x1800313f1  mov     esi, eax
0x1800313f3  mov     r15, [rdi+28h]
0x1800313f7  test    eax, eax
0x1800313f9  jz      short loc_18003145D
0x1800313fb  test    r15, r15
0x1800313fe  jz      short loc_180031447
0x180031400  mov     rcx, [r15]
0x180031403  jmp     short loc_180031449
0x180031405  mov     rax, [rdi+28h]
0x180031409  test    rax, rax
0x18003140c  jz      short loc_180031413
0x18003140e  mov     rcx, [rax]
0x180031411  jmp     short loc_180031415
0x180031413  xor     ecx, ecx
0x180031415  call    sqlite3_errmsg
0x18003141a  mov     [rsp+0C0h+var_98], rax
0x18003141f  mov     dword ptr [rsp+0C0h+var_A0], r14d
0x180031424  lea     r9, aSqlite3BindFai; "sqlite3_bind failed: [%d] %hs"
0x18003142b  mov     r8d, 164h
0x180031431  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x180031438  mov     ecx, 1
0x18003143d  call    AslLogCallPrintf
0x180031442  jmp     loc_1800314D8
0x180031447  xor     ecx, ecx
0x180031449  call    sqlite3_errmsg
0x18003144e  lea     r9, aSqlite3BindInt; "sqlite3_bind_int64 failed: [%d] %hs"
0x180031455  mov     r8d, 16Fh
0x18003145b  jmp     short loc_1800314AD
0x18003145d  xor     r14d, r14d
0x180031460  mov     rcx, r15
0x180031463  call    sqlite3_step
0x180031468  mov     esi, eax
0x18003146a  add     eax, 0FFFFFFFBh
0x18003146d  cmp     eax, 1
0x180031470  ja      short loc_180031486
0x180031472  mov     ecx, 5; dwMilliseconds
0x180031477  call    cs:__imp_Sleep
0x18003147d  inc     r14d
0x180031480  cmp     r14d, 64h ; 'd'
0x180031484  jl      short loc_180031460
0x180031486  cmp     esi, 65h ; 'e'
0x180031489  jz      short loc_1800314D8
0x18003148b  mov     rax, [rdi+28h]
0x18003148f  test    rax, rax
0x180031492  jz      short loc_180031499
0x180031494  mov     rcx, [rax]
0x180031497  jmp     short loc_18003149B
0x180031499  xor     ecx, ecx
0x18003149b  call    sqlite3_errmsg
0x1800314a0  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800314a7  mov     r8d, 177h
0x1800314ad  mov     [rsp+0C0h+var_98], rax
0x1800314b2  mov     dword ptr [rsp+0C0h+var_A0], esi
0x1800314b6  lea     rdx, aWindowsCompatI_3; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800314bd  mov     ecx, 1
0x1800314c2  call    AslLogCallPrintf
0x1800314c7  test    esi, esi
0x1800314c9  jg      short loc_1800314CF
0x1800314cb  mov     ebx, esi
0x1800314cd  jmp     short loc_1800314D8
0x1800314cf  movzx   ebx, si
0x1800314d2  or      ebx, 80070000h
0x1800314d8  mov     eax, ebx
0x1800314da  jmp     short loc_1800314DE
0x1800314dc  xor     eax, eax
0x1800314de  mov     rcx, [rbp+57h+var_28]
0x1800314e2  xor     rcx, rsp; StackCookie
0x1800314e5  call    __security_check_cookie
0x1800314ea  lea     r11, [rsp+0C0h+var_20]
0x1800314f2  mov     rbx, [r11+38h]
0x1800314f6  mov     rsi, [r11+40h]
0x1800314fa  mov     rsp, r11
0x1800314fd  pop     r15
0x1800314ff  pop     r14
0x180031501  pop     r13
0x180031503  pop     rdi
0x180031504  pop     rbp
0x180031505  retn
0x180031506  call    ?_Xrange@?$vector@U_CacheItemProperty@IAmiInventoryItem@@V?$allocator@U_CacheItemProperty@IAmiInventoryItem@@@std@@@std@@CAXXZ; std::vector<IAmiInventoryItem::_CacheItemProperty>::_Xrange(void)
0x18003150c  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x180031513  call    _Init_thread_header
0x180031518  cmp     cs:?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA, 0FFFFFFFFh
0x18003151f  jnz     loc_18003123B
0x180031525  xorps   xmm0, xmm0
0x180031528  movdqu  cs:?emptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4V?$vector@EV?$allocator@E@std@@@std@@A, xmm0; std::vector<uchar> `Windows::Compat::Inventory::SqliteInvCacheItem::WriteToDb(void)'::`16'::emptyVector
0x180031530  mov     cs:qword_180156EC0, 0
0x18003153b  lea     rcx, ??__FemptyVector@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@YAXXZ; void (__cdecl *)()
0x180031542  call    atexit
0x180031547  lea     rcx, ?$TSS0@?BA@??WriteToDb@SqliteInvCacheItem@Inventory@Compat@Windows@@QEAAJXZ@4HA
0x18003154e  call    _Init_thread_footer
0x180031553  jmp     loc_18003123B
  ... truncated ...
```
