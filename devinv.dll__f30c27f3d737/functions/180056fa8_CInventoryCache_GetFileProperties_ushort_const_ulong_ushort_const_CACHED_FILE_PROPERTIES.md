# CInventoryCache::GetFileProperties(ushort const *,ulong,ushort const *,_CACHED_FILE_PROPERTIES *)

- ea: `0x180056fa8`
- end: `0x180057601`
- name: `?GetFileProperties@CInventoryCache@@QEAAJPEBGK0PEAU_CACHED_FILE_PROPERTIES@@@Z`
- size: `1625`
- prototype: `__int64 __usercall@<rax>(CInventoryCache *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const unsigned __int16 *@<r9>, struct _CACHED_FILE_PROPERTIES *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180049694`

## callees

- `0x180006d02`
- `0x180007014`
- `0x180014ce8`
- `0x18001509c`
- `0x180015268`
- `0x180056d08`
- `0x180056fa8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180057553`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056fe8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056fe8`

## string_xrefs

- `0x180057020`: `CInventoryCache::GetFileProperties`
- `0x18005710e`: `CInventoryCache::GetFileProperties`
- `0x1800571f0`: `CInventoryCache::GetFileProperties`
- `0x1800573da`: `CInventoryCache::GetFileProperties`
- `0x18005756c`: `CInventoryCache::GetFileProperties`

## pseudocode

```c
__int64 __fastcall CInventoryCache::GetFileProperties(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        char a3,
        const unsigned __int16 *a4,
        struct _CACHED_FILE_PROPERTIES *a5)
{
  struct _CACHED_FILE_PROPERTIES *v8; // rdi
  __int64 v9; // r9
  int CachedFile; // eax
  int v11; // r14d
  unsigned int v12; // ebx
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  int ImageProperties; // eax
  const char *v17; // r12
  FILE *v18; // rax
  FILE *v19; // rax
  FILE *v20; // rax
  __int64 v21; // rcx
  int VersionStrings; // eax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  FILE *v26; // rax
  FILE *v27; // rax
  FILE *v28; // rax
  FILE *v29; // rax
  int v30; // r9d
  FILE *v31; // rax
  FILE *v32; // rax
  int SignatureInfo; // eax
  FILE *v34; // rax
  FILE *v35; // rax
  FILE *v36; // rax
  FILE *v37; // rax
  FILE *v38; // rax
  FILE *v39; // rax
  FILE *v41; // rax
  FILE *v42; // rax
  FILE *v43; // rax
  __int64 v44; // [rsp+28h] [rbp-70h]
  __int64 v45; // [rsp+28h] [rbp-70h]
  __int64 v46; // [rsp+28h] [rbp-70h]
  __int64 v47; // [rsp+28h] [rbp-70h]
  __int64 v48; // [rsp+28h] [rbp-70h]
  struct CCachedFile *v49; // [rsp+A8h] [rbp+10h] BYREF

  v49 = 0;
  if ( a2 )
  {
    v8 = a5;
    if ( a5 )
    {
      EnterCriticalSection(this);
      CachedFile = CInventoryCache::GetCachedFile((CInventoryCache *)this, a2, &v49, v9);
      v11 = 1;
      v12 = CachedFile;
      if ( CachedFile < 0 )
      {
        AslLogCallPrintf(2, "CInventoryCache::GetFileProperties", 403, "Failed to lookup file: 0x%x", CachedFile);
        if ( EnableDevInvStdErrLog )
        {
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "Error: %s, %u: ", "CInventoryCache::GetFileProperties", 403);
          v14 = o___acrt_iob_func_0(2u);
          fprintf(v14, "Failed to lookup file: 0x%x", v12);
          v15 = o___acrt_iob_func_0(2u);
          fprintf(v15, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Failed to lookup file: 0x%x", v12);
        goto LABEL_40;
      }
      ImageProperties = CCachedFile::GetImageProperties(
                          v49,
                          (__int64)v8 + 36,
                          (__int64)v8 + 40,
                          (__int64)v8 + 44,
                          (__int64)v8 + 48,
                          (__int64)v8 + 52,
                          (__int64)v8 + 56);
      v12 = ImageProperties;
      if ( ImageProperties < 0 )
      {
        LODWORD(v44) = ImageProperties;
        v17 = "Failed to get image properties for %ws: 0x%x";
        AslLogCallPrintf(
          2,
          "CInventoryCache::GetFileProperties",
          422,
          "Failed to get image properties for %ws: 0x%x",
          a2,
          v44);
        if ( EnableDevInvStdErrLog )
        {
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "Warning: %s, %u: ", "CInventoryCache::GetFileProperties", 422);
          v19 = o___acrt_iob_func_0(2u);
          fprintf(v19, "Failed to get image properties for %ws: 0x%x", a2, v12);
          v20 = o___acrt_iob_func_0(2u);
          fprintf(v20, "\n");
        }
        if ( !g_DeviceMapLogFunction )
          goto LABEL_40;
        v21 = 50331648;
        goto LABEL_13;
      }
      VersionStrings = CCachedFile::GetVersionStrings(
                         (_DWORD)v49,
                         (int)v8 + 160,
                         (int)v8 + 192,
                         (int)v8 + 224,
                         (__int64)v8 + 256);
      v12 = VersionStrings;
      if ( VersionStrings >= 0 )
      {
        if ( (a3 & 6) == 0
          || (a3 & 0x18) != 0
          || (SignatureInfo = CCachedFile::GetSignatureInfo(v49, (char *)v8 + 88, (char *)v8 + 96, (char *)v8 + 128),
              v12 = SignatureInfo,
              SignatureInfo >= 0) )
        {
          v12 = 0;
          goto LABEL_40;
        }
        LODWORD(v44) = SignatureInfo;
        v17 = "Failed to get image signature info for %ws: 0x%x";
        AslLogCallPrintf(
          2,
          "CInventoryCache::GetFileProperties",
          458,
          "Failed to get image signature info for %ws: 0x%x",
          a2,
          v44);
        if ( EnableDevInvStdErrLog )
        {
          v34 = o___acrt_iob_func_0(2u);
          fprintf(v34, "Error: %s, %u: ", "CInventoryCache::GetFileProperties", 458);
          v35 = o___acrt_iob_func_0(2u);
          fprintf(v35, "Failed to get image signature info for %ws: 0x%x", a2, v12);
          v36 = o___acrt_iob_func_0(2u);
          fprintf(v36, "\n");
        }
        if ( v12 + 2147024894 > 1 )
          goto LABEL_24;
        LODWORD(v47) = v12;
        AslLogCallPrintf(
          2,
          "CInventoryCache::GetFileProperties",
          458,
          "Failed to get image signature info for %ws: 0x%x",
          a2,
          v47);
        if ( EnableDevInvStdErrLog )
        {
          v37 = o___acrt_iob_func_0(2u);
          fprintf(v37, "Warning: %s, %u: ", "CInventoryCache::GetFileProperties", 458);
          v38 = o___acrt_iob_func_0(2u);
          fprintf(v38, "Failed to get image signature info for %ws: 0x%x", a2, v12);
          v39 = o___acrt_iob_func_0(2u);
          fprintf(v39, "\n");
        }
        if ( v12 + 2147024894 > 1 )
          goto LABEL_24;
        LODWORD(v48) = v12;
        AslLogCallPrintf(
          3,
          "CInventoryCache::GetFileProperties",
          458,
          "Failed to get image signature info for %ws: 0x%x",
          a2,
          v48);
        if ( !EnableDevInvStdErrLog )
          goto LABEL_24;
        v29 = o___acrt_iob_func_0(2u);
        v30 = 458;
      }
      else
      {
        LODWORD(v44) = VersionStrings;
        v17 = "Failed to get file version info for %ws: 0x%x";
        AslLogCallPrintf(
          2,
          "CInventoryCache::GetFileProperties",
          437,
          "Failed to get file version info for %ws: 0x%x",
          a2,
          v44);
        if ( EnableDevInvStdErrLog )
        {
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "Error: %s, %u: ", "CInventoryCache::GetFileProperties", 437);
          v24 = o___acrt_iob_func_0(2u);
          fprintf(v24, "Failed to get file version info for %ws: 0x%x", a2, v12);
          v25 = o___acrt_iob_func_0(2u);
          fprintf(v25, "\n");
        }
        if ( v12 + 2147024894 > 1 )
          goto LABEL_24;
        LODWORD(v45) = v12;
        AslLogCallPrintf(
          2,
          "CInventoryCache::GetFileProperties",
          437,
          "Failed to get file version info for %ws: 0x%x",
          a2,
          v45);
        if ( EnableDevInvStdErrLog )
        {
          v26 = o___acrt_iob_func_0(2u);
          fprintf(v26, "Warning: %s, %u: ", "CInventoryCache::GetFileProperties", 437);
          v27 = o___acrt_iob_func_0(2u);
          fprintf(v27, "Failed to get file version info for %ws: 0x%x", a2, v12);
          v28 = o___acrt_iob_func_0(2u);
          fprintf(v28, "\n");
        }
        if ( v12 + 2147024894 > 1 )
          goto LABEL_24;
        LODWORD(v46) = v12;
        AslLogCallPrintf(
          3,
          "CInventoryCache::GetFileProperties",
          437,
          "Failed to get file version info for %ws: 0x%x",
          a2,
          v46);
        if ( !EnableDevInvStdErrLog )
          goto LABEL_24;
        v29 = o___acrt_iob_func_0(2u);
        v30 = 437;
      }
      fprintf(v29, "Info: %s, %u: ", "CInventoryCache::GetFileProperties", v30);
      v31 = o___acrt_iob_func_0(2u);
      fprintf(v31, v17, a2, v12);
      v32 = o___acrt_iob_func_0(2u);
      fprintf(v32, "\n");
LABEL_24:
      if ( !g_DeviceMapLogFunction )
        goto LABEL_40;
      v21 = 0x2000000;
      if ( v12 + 2147024894 <= 1 )
        v21 = 50331648;
LABEL_13:
      TraceMessageCallback(v21, v17, a2, v12);
LABEL_40:
      if ( v49 )
      {
        if ( !this[1].LockCount && !*((_DWORD *)v49 + 265) )
          v11 = 0;
        this[1].LockCount = v11;
      }
      v49 = 0;
      LeaveCriticalSection(this);
      return v12;
    }
  }
  AslLogCallPrintf(2, "CInventoryCache::GetFileProperties", 393, "Unexpected NULL argument in call to function");
  if ( EnableDevInvStdErrLog )
  {
    v41 = o___acrt_iob_func_0(2u);
    fprintf(v41, "Error: %s, %u: ", "CInventoryCache::GetFileProperties", 393);
    v42 = o___acrt_iob_func_0(2u);
    fprintf(v42, "Unexpected NULL argument in call to function");
    v43 = o___acrt_iob_func_0(2u);
    fprintf(v43, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x2000000, "Unexpected NULL argument in call to function");
  return 2147942487LL;
}

```

## disassembly

```asm
0x180056fa8  mov     rax, rsp
0x180056fab  push    rbx
0x180056fac  push    rbp
0x180056fad  push    rsi
0x180056fae  push    rdi
0x180056faf  push    r12
0x180056fb1  push    r13
0x180056fb3  push    r14
0x180056fb5  push    r15
0x180056fb7  sub     rsp, 58h
0x180056fbb  xor     r13d, r13d
0x180056fbe  mov     r12, r9
0x180056fc1  mov     [rax+10h], r13
0x180056fc5  mov     esi, r8d
0x180056fc8  mov     rbp, rdx
0x180056fcb  mov     r15, rcx
0x180056fce  test    rdx, rdx
0x180056fd1  jz      loc_180057560
0x180056fd7  mov     rdi, [rsp+98h+arg_20]
0x180056fdf  test    rdi, rdi
0x180056fe2  jz      loc_180057560
0x180056fe8  call    cs:__imp_EnterCriticalSection
0x180056fee  lea     r8, [rsp+98h+arg_8]; struct CCachedFile **
0x180056ff6  mov     rdx, rbp; unsigned __int16 *
0x180056ff9  mov     rcx, r15; this
0x180056ffc  call    ?GetCachedFile@CInventoryCache@@AEAAJPEBGPEAPEAVCCachedFile@@@Z; CInventoryCache::GetCachedFile(ushort const *,CCachedFile * *)
0x180057001  lea     r14d, [r13+1]
0x180057005  mov     ebx, eax
0x180057007  test    eax, eax
0x180057009  jns     loc_1800570AD
0x18005700f  lea     rbp, aFailedToLookup_0; "Failed to lookup file: 0x%x"
0x180057016  mov     dword ptr [rsp+98h+var_78], eax
0x18005701a  mov     r12d, 193h
0x180057020  lea     rsi, aCinventorycach_0; "CInventoryCache::GetFileProperties"
0x180057027  lea     edi, [r13+2]
0x18005702b  mov     r9, rbp
0x18005702e  mov     r8d, r12d
0x180057031  mov     rdx, rsi
0x180057034  mov     ecx, edi
0x180057036  call    AslLogCallPrintf
0x18005703b  cmp     cs:EnableDevInvStdErrLog, r13d
0x180057042  jz      short loc_18005708B
0x180057044  mov     ecx, edi; Ix
0x180057046  call    _o___acrt_iob_func_0
0x18005704b  mov     rcx, rax; Stream
0x18005704e  lea     rdx, Format; "Error: %s, %u: "
0x180057055  mov     r9d, r12d
0x180057058  mov     r8, rsi
0x18005705b  call    fprintf
0x180057060  mov     ecx, edi; Ix
0x180057062  call    _o___acrt_iob_func_0
0x180057067  mov     rcx, rax; Stream
0x18005706a  mov     r8d, ebx
0x18005706d  mov     rdx, rbp; Format
0x180057070  call    fprintf
0x180057075  mov     ecx, edi; Ix
0x180057077  call    _o___acrt_iob_func_0
0x18005707c  mov     rcx, rax; Stream
0x18005707f  lea     rdx, asc_18011EAD8; "\n"
0x180057086  call    fprintf
0x18005708b  cmp     cs:g_DeviceMapLogFunction, r13
0x180057092  jz      loc_180057525
0x180057098  mov     r8d, ebx
0x18005709b  mov     rdx, rbp
0x18005709e  mov     ecx, 2000000h
0x1800570a3  call    TraceMessageCallback
0x1800570a8  jmp     loc_180057525
0x1800570ad  lea     rdx, [rdi+30h]
0x1800570b1  lea     rax, [rdi+38h]
0x1800570b5  mov     [rsp+98h+var_50], rax; __int64
0x1800570ba  lea     rcx, [rdi+34h]
0x1800570be  mov     [rsp+98h+var_58], rcx; __int64
0x1800570c3  lea     r8, [rdi+2Ch]
0x1800570c7  mov     rcx, [rsp+98h+arg_8]; this
0x1800570cf  lea     r10, [rdi+28h]
0x1800570d3  mov     [rsp+98h+var_60], rdx; __int64
0x1800570d8  lea     r11, [rdi+24h]
0x1800570dc  mov     [rsp+98h+var_68], r8; __int64
0x1800570e1  lea     r9, [rdi+20h]
0x1800570e5  mov     [rsp+98h+var_70], r10; __int64
0x1800570ea  mov     r8, r12
0x1800570ed  mov     edx, esi
0x1800570ef  mov     [rsp+98h+var_78], r11; __int64
0x1800570f4  call    ?GetImageProperties@CCachedFile@@QEAAJKPEBGPEAK11111AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CCachedFile::GetImageProperties(ulong,ushort const *,ulong *,ulong *,ulong *,ulong *,ulong *,ulong *,std::wstring &)
0x1800570f9  mov     ebx, eax
0x1800570fb  test    eax, eax
0x1800570fd  jns     loc_1800571AD
0x180057103  mov     dword ptr [rsp+98h+var_70], eax
0x180057107  lea     r12, aFailedToGetIma; "Failed to get image properties for %ws:"...
0x18005710e  lea     rsi, aCinventorycach_0; "CInventoryCache::GetFileProperties"
0x180057115  mov     [rsp+98h+var_78], rbp
0x18005711a  mov     edi, 2
0x18005711f  mov     r9, r12
0x180057122  mov     rdx, rsi
0x180057125  mov     ecx, edi
0x180057127  mov     r8d, 1A6h
0x18005712d  call    AslLogCallPrintf
0x180057132  cmp     cs:EnableDevInvStdErrLog, r13d
0x180057139  jz      short loc_180057188
0x18005713b  mov     ecx, edi; Ix
0x18005713d  call    _o___acrt_iob_func_0
0x180057142  mov     rcx, rax; Stream
0x180057145  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x18005714c  mov     r9d, 1A6h
0x180057152  mov     r8, rsi
0x180057155  call    fprintf
0x18005715a  mov     ecx, edi; Ix
0x18005715c  call    _o___acrt_iob_func_0
0x180057161  mov     rcx, rax; Stream
0x180057164  mov     r9d, ebx
0x180057167  mov     r8, rbp
0x18005716a  mov     rdx, r12; Format
0x18005716d  call    fprintf
0x180057172  mov     ecx, edi; Ix
0x180057174  call    _o___acrt_iob_func_0
0x180057179  mov     rcx, rax; Stream
0x18005717c  lea     rdx, asc_18011EAD8; "\n"
0x180057183  call    fprintf
0x180057188  cmp     cs:g_DeviceMapLogFunction, r13
0x18005718f  jz      loc_180057525
0x180057195  mov     ecx, 3000000h
0x18005719a  mov     rdx, r12
0x18005719d  mov     r8, rbp
0x1800571a0  mov     r9d, ebx
0x1800571a3  call    TraceMessageCallback
0x1800571a8  jmp     loc_180057525
0x1800571ad  mov     rcx, [rsp+98h+arg_8]
0x1800571b5  lea     rax, [rdi+100h]
0x1800571bc  lea     r9, [rdi+0E0h]
0x1800571c3  mov     [rsp+98h+var_78], rax
0x1800571c8  lea     r8, [rdi+0C0h]
0x1800571cf  lea     rdx, [rdi+0A0h]
0x1800571d6  call    ?GetVersionStrings@CCachedFile@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z; CCachedFile::GetVersionStrings(std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x1800571db  mov     ebx, eax
0x1800571dd  test    eax, eax
0x1800571df  jns     loc_180057395
0x1800571e5  mov     dword ptr [rsp+98h+var_70], eax
0x1800571e9  lea     r12, aFailedToGetFil_1; "Failed to get file version info for %ws"...
0x1800571f0  lea     rsi, aCinventorycach_0; "CInventoryCache::GetFileProperties"
0x1800571f7  mov     [rsp+98h+var_78], rbp
0x1800571fc  mov     edi, 2
0x180057201  mov     r9, r12
0x180057204  mov     rdx, rsi
0x180057207  mov     ecx, edi
0x180057209  mov     r8d, 1B5h
0x18005720f  call    AslLogCallPrintf
0x180057214  cmp     cs:EnableDevInvStdErrLog, r13d
0x18005721b  jz      short loc_18005726A
0x18005721d  mov     ecx, edi; Ix
0x18005721f  call    _o___acrt_iob_func_0
0x180057224  mov     rcx, rax; Stream
0x180057227  lea     rdx, Format; "Error: %s, %u: "
0x18005722e  mov     r9d, 1B5h
0x180057234  mov     r8, rsi
0x180057237  call    fprintf
0x18005723c  mov     ecx, edi; Ix
0x18005723e  call    _o___acrt_iob_func_0
0x180057243  mov     rcx, rax; Stream
0x180057246  mov     r9d, ebx
0x180057249  mov     r8, rbp
0x18005724c  mov     rdx, r12; Format
0x18005724f  call    fprintf
0x180057254  mov     ecx, edi; Ix
0x180057256  call    _o___acrt_iob_func_0
0x18005725b  mov     rcx, rax; Stream
0x18005725e  lea     rdx, asc_18011EAD8; "\n"
0x180057265  call    fprintf
0x18005726a  lea     eax, [rbx+7FF8FFFEh]
0x180057270  cmp     eax, r14d
0x180057273  ja      loc_18005736B
0x180057279  mov     dword ptr [rsp+98h+var_70], ebx
0x18005727d  mov     r9, r12
0x180057280  mov     r8d, 1B5h
0x180057286  mov     [rsp+98h+var_78], rbp
0x18005728b  mov     rdx, rsi
0x18005728e  mov     ecx, edi
0x180057290  call    AslLogCallPrintf
0x180057295  cmp     cs:EnableDevInvStdErrLog, r13d
0x18005729c  jz      short loc_1800572EB
0x18005729e  mov     ecx, edi; Ix
0x1800572a0  call    _o___acrt_iob_func_0
0x1800572a5  mov     rcx, rax; Stream
0x1800572a8  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x1800572af  mov     r9d, 1B5h
0x1800572b5  mov     r8, rsi
0x1800572b8  call    fprintf
0x1800572bd  mov     ecx, edi; Ix
0x1800572bf  call    _o___acrt_iob_func_0
0x1800572c4  mov     rcx, rax; Stream
0x1800572c7  mov     r9d, ebx
0x1800572ca  mov     r8, rbp
0x1800572cd  mov     rdx, r12; Format
0x1800572d0  call    fprintf
0x1800572d5  mov     ecx, edi; Ix
0x1800572d7  call    _o___acrt_iob_func_0
0x1800572dc  mov     rcx, rax; Stream
0x1800572df  lea     rdx, asc_18011EAD8; "\n"
0x1800572e6  call    fprintf
0x1800572eb  lea     eax, [rbx+7FF8FFFEh]
0x1800572f1  cmp     eax, r14d
0x1800572f4  ja      short loc_18005736B
0x1800572f6  mov     dword ptr [rsp+98h+var_70], ebx
0x1800572fa  mov     r9, r12
0x1800572fd  mov     r8d, 1B5h
0x180057303  mov     [rsp+98h+var_78], rbp
0x180057308  mov     rdx, rsi
0x18005730b  mov     ecx, 3
0x180057310  call    AslLogCallPrintf
0x180057315  cmp     cs:EnableDevInvStdErrLog, r13d
0x18005731c  jz      short loc_18005736B
0x18005731e  mov     ecx, edi; Ix
0x180057320  call    _o___acrt_iob_func_0
0x180057325  mov     r9d, 1B5h
0x18005732b  mov     rcx, rax; Stream
0x18005732e  lea     rdx, aInfoSU; "Info: %s, %u: "
0x180057335  mov     r8, rsi
0x180057338  call    fprintf
0x18005733d  mov     ecx, edi; Ix
0x18005733f  call    _o___acrt_iob_func_0
0x180057344  mov     rcx, rax; Stream
0x180057347  mov     r9d, ebx
0x18005734a  mov     r8, rbp
0x18005734d  mov     rdx, r12; Format
0x180057350  call    fprintf
0x180057355  mov     ecx, edi; Ix
0x180057357  call    _o___acrt_iob_func_0
0x18005735c  mov     rcx, rax; Stream
0x18005735f  lea     rdx, asc_18011EAD8; "\n"
0x180057366  call    fprintf
0x18005736b  cmp     cs:g_DeviceMapLogFunction, r13
0x180057372  jz      loc_180057525
0x180057378  lea     eax, [rbx+7FF8FFFEh]
0x18005737e  mov     ecx, 2000000h
0x180057383  cmp     eax, r14d
0x180057386  mov     r10d, 3000000h
0x18005738c  cmovbe  ecx, r10d
0x180057390  jmp     loc_18005719A
0x180057395  test    sil, 6
0x180057399  jz      loc_180057522
0x18005739f  test    sil, 18h
0x1800573a3  jnz     loc_180057522
0x1800573a9  mov     rcx, [rsp+98h+arg_8]
0x1800573b1  lea     r9, [rdi+80h]
0x1800573b8  lea     r8, [rdi+60h]
0x1800573bc  lea     rdx, [rdi+58h]
0x1800573c0  call    ?GetSignatureInfo@CCachedFile@@QEAAJPEAKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; CCachedFile::GetSignatureInfo(ulong *,std::wstring &,std::wstring &)
0x1800573c5  mov     ebx, eax
0x1800573c7  test    eax, eax
0x1800573c9  jns     loc_180057522
0x1800573cf  mov     dword ptr [rsp+98h+var_70], eax
0x1800573d3  lea     r12, aFailedToGetIma_0; "Failed to get image signature info for "...
0x1800573da  lea     rsi, aCinventorycach_0; "CInventoryCache::GetFileProperties"
0x1800573e1  mov     [rsp+98h+var_78], rbp
0x1800573e6  mov     edi, 2
0x1800573eb  mov     r9, r12
0x1800573ee  mov     rdx, rsi
0x1800573f1  mov     ecx, edi
0x1800573f3  mov     r8d, 1CAh
0x1800573f9  call    AslLogCallPrintf
0x1800573fe  cmp     cs:EnableDevInvStdErrLog, r13d
0x180057405  jz      short loc_180057454
0x180057407  mov     ecx, edi; Ix
0x180057409  call    _o___acrt_iob_func_0
0x18005740e  mov     rcx, rax; Stream
0x180057411  lea     rdx, Format; "Error: %s, %u: "
0x180057418  mov     r9d, 1CAh
0x18005741e  mov     r8, rsi
0x180057421  call    fprintf
0x180057426  mov     ecx, edi; Ix
0x180057428  call    _o___acrt_iob_func_0
0x18005742d  mov     rcx, rax; Stream
0x180057430  mov     r9d, ebx
0x180057433  mov     r8, rbp
0x180057436  mov     rdx, r12; Format
0x180057439  call    fprintf
0x18005743e  mov     ecx, edi; Ix
0x180057440  call    _o___acrt_iob_func_0
0x180057445  mov     rcx, rax; Stream
0x180057448  lea     rdx, asc_18011EAD8; "\n"
0x18005744f  call    fprintf
0x180057454  lea     eax, [rbx+7FF8FFFEh]
0x18005745a  cmp     eax, r14d
0x18005745d  ja      loc_18005736B
0x180057463  mov     dword ptr [rsp+98h+var_70], ebx
0x180057467  mov     r9, r12
0x18005746a  mov     r8d, 1CAh
0x180057470  mov     [rsp+98h+var_78], rbp
0x180057475  mov     rdx, rsi
0x180057478  mov     ecx, edi
0x18005747a  call    AslLogCallPrintf
0x18005747f  cmp     cs:EnableDevInvStdErrLog, r13d
0x180057486  jz      short loc_1800574D5
0x180057488  mov     ecx, edi; Ix
0x18005748a  call    _o___acrt_iob_func_0
0x18005748f  mov     rcx, rax; Stream
0x180057492  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180057499  mov     r9d, 1CAh
0x18005749f  mov     r8, rsi
0x1800574a2  call    fprintf
0x1800574a7  mov     ecx, edi; Ix
  ... truncated ...
```
