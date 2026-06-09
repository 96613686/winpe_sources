# WriteOutputHeaders(int,int,int,_iobuf *)

- ea: `0x1400032c4`
- end: `0x140003577`
- name: `?WriteOutputHeaders@@YAXHHHPEAU_iobuf@@@Z`
- size: `691`
- prototype: `void __fastcall(int, int, int, struct _iobuf *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009ee0`

## callees

- `0x140001c50`
- `0x14000281c`
- `0x140002c84`
- `0x140002fb8`
- `0x140003088`
- `0x140003154`
- `0x1400032c4`

## string_xrefs

- `0x14000338f`: `#VolumeDetail,volumeType,fileId,parentId,allocatedSizeBytes,filePath,ruleName,attr`
- `0x1400033c0`: `#Metadata,buildLabEx,editionId,compactOs\n`
- `0x1400034c1`: `Compact`

## pseudocode

```c
void __fastcall WriteOutputHeaders(int a1, int a2, int a3, struct _iobuf *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int128 *v10; // r9
  __int128 *v11; // r8
  int v12; // [rsp+20h] [rbp-69h]
  int v13; // [rsp+30h] [rbp-59h] BYREF
  __int128 v14; // [rsp+38h] [rbp-51h] BYREF
  __int128 v15; // [rsp+48h] [rbp-41h]
  __int128 v16; // [rsp+58h] [rbp-31h] BYREF
  __int128 v17; // [rsp+68h] [rbp-21h]
  __int128 v18; // [rsp+78h] [rbp-11h] BYREF
  __int128 v19; // [rsp+88h] [rbp-1h]
  __int128 v20; // [rsp+98h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+A8h] [rbp+1Fh]

  if ( a1 )
    fwprintf(a4, L"volumeType,ruleName,allocatedSizeBytes,fileCount,growthSizeBytes,growthFileCount\n");
  if ( a2 )
  {
    v20 = 0;
    v21 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v20, &qword_14000E928, 0);
    v18 = 0;
    v19 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v18, &qword_14000E928, 0);
    v13 = 0;
    fwprintf(a4, L"#VolumeMftData,volumeType,recordSizeBytes,usedPercent,wastedBytes,slackPercent,slackBytes\n");
    fwprintf(
      a4,
      L"#VolumeSnapshot,snapshotTime,volumeType,volumeGuid,sizeBytes,sizeMB,freeBytes,freeMB,osDeploymentState,osArch\n");
    fwprintf(
      a4,
      L"#RuleSummary,volumeType,ruleName,sizeBytes,fileCount,growthSizeBytes,growthFileCount,detailCount,detail1,detail2,d"
       "etail3,detail4\n");
    fwprintf(
      a4,
      L"#VolumeSummary,volumeType,systemMB,userMB,otherMB,inboxAppMB,otherAppMB,growthSystemMB,growthUserMB,growthOtherMB,"
       "growthInboxAppMB,growthOtherAppMB,firstRun\n");
    fwprintf(a4, L"#VolumeDetail,volumeType,fileId,parentId,allocatedSizeBytes,filePath,ruleName,attr");
    if ( a3 )
      fwprintf(a4, L",checksum");
    fwprintf(a4, L"\n");
    fwprintf(a4, L"#Metadata,buildLabEx,editionId,compactOs\n");
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v16, L"BuildLabEx", 0xAu);
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v14, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0x2Cu);
    GetStringRegKey(v7, &v14, &v16, &v20);
    std::wstring::~wstring((char **)&v14);
    std::wstring::~wstring((char **)&v16);
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v14, L"EditionID", 9u);
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v16, L"Software\\Microsoft\\Windows NT\\CurrentVersion", 0x2Cu);
    GetStringRegKey(v8, &v16, &v14, &v18);
    std::wstring::~wstring((char **)&v16);
    std::wstring::~wstring((char **)&v14);
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v14, L"Compact", 7u);
    v16 = 0;
    v17 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v16, L"SYSTEM\\Setup", 0xCu);
    GetDwordRegKey(v9, &v16, &v14, &v13);
    std::wstring::~wstring((char **)&v16);
    std::wstring::~wstring((char **)&v14);
    v10 = &v18;
    if ( *((_QWORD *)&v19 + 1) > 7u )
      v10 = (__int128 *)v18;
    v11 = &v20;
    if ( *((_QWORD *)&v21 + 1) > 7u )
      v11 = (__int128 *)v20;
    v12 = v13;
    fwprintf(a4, L"Metadata,%s,%s,%u\n", v11, v10, v12);
    std::wstring::~wstring((char **)&v18);
    std::wstring::~wstring((char **)&v20);
  }
}

```

## disassembly

```asm
0x1400032c4  push    rbp
0x1400032c6  push    rbx
0x1400032c7  push    rsi
0x1400032c8  push    rdi
0x1400032c9  lea     rbp, [rsp-3Fh]
0x1400032ce  sub     rsp, 0C8h
0x1400032d5  mov     rax, cs:__security_cookie
0x1400032dc  xor     rax, rsp
0x1400032df  mov     [rbp+57h+var_28], rax
0x1400032e3  mov     rbx, r9
0x1400032e6  mov     esi, r8d
0x1400032e9  mov     edi, edx
0x1400032eb  test    ecx, ecx
0x1400032ed  jz      short loc_1400032FE
0x1400032ef  lea     rdx, aVolumetypeRule; "volumeType,ruleName,allocatedSizeBytes,"...
0x1400032f6  mov     rcx, rbx; Stream
0x1400032f9  call    fwprintf
0x1400032fe  test    edi, edi
0x140003300  jz      loc_14000355F
0x140003306  xorps   xmm0, xmm0
0x140003309  movups  [rbp+57h+var_48], xmm0
0x14000330d  xorps   xmm1, xmm1
0x140003310  movdqu  [rbp+57h+var_38], xmm1
0x140003315  xor     r8d, r8d
0x140003318  lea     rdx, qword_14000E928
0x14000331f  lea     rcx, [rbp+57h+var_48]
0x140003323  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003328  nop
0x140003329  xorps   xmm0, xmm0
0x14000332c  movups  [rbp+57h+var_68], xmm0
0x140003330  xorps   xmm1, xmm1
0x140003333  movdqu  [rbp+57h+var_58], xmm1
0x140003338  xor     r8d, r8d
0x14000333b  lea     rdx, qword_14000E928
0x140003342  lea     rcx, [rbp+57h+var_68]
0x140003346  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000334b  nop
0x14000334c  mov     [rbp+57h+var_B0], 0
0x140003353  lea     rdx, aVolumemftdataV; "#VolumeMftData,volumeType,recordSizeByt"...
0x14000335a  mov     rcx, rbx; Stream
0x14000335d  call    fwprintf
0x140003362  lea     rdx, aVolumesnapshot; "#VolumeSnapshot,snapshotTime,volumeType"...
0x140003369  mov     rcx, rbx; Stream
0x14000336c  call    fwprintf
0x140003371  lea     rdx, aRulesummaryVol; "#RuleSummary,volumeType,ruleName,sizeBy"...
0x140003378  mov     rcx, rbx; Stream
0x14000337b  call    fwprintf
0x140003380  lea     rdx, aVolumesummaryV; "#VolumeSummary,volumeType,systemMB,user"...
0x140003387  mov     rcx, rbx; Stream
0x14000338a  call    fwprintf
0x14000338f  lea     rdx, aVolumedetailVo; "#VolumeDetail,volumeType,fileId,parentI"...
0x140003396  mov     rcx, rbx; Stream
0x140003399  call    fwprintf
0x14000339e  test    esi, esi
0x1400033a0  jz      short loc_1400033B1
0x1400033a2  lea     rdx, aChecksum; ",checksum"
0x1400033a9  mov     rcx, rbx; Stream
0x1400033ac  call    fwprintf
0x1400033b1  lea     rdx, asc_14000EE8C; "\n"
0x1400033b8  mov     rcx, rbx; Stream
0x1400033bb  call    fwprintf
0x1400033c0  lea     rdx, aMetadataBuildl; "#Metadata,buildLabEx,editionId,compactO"...
0x1400033c7  mov     rcx, rbx; Stream
0x1400033ca  call    fwprintf
0x1400033cf  xorps   xmm0, xmm0
0x1400033d2  movups  [rbp+57h+var_88], xmm0
0x1400033d6  xorps   xmm1, xmm1
0x1400033d9  movdqu  [rbp+57h+var_78], xmm1
0x1400033de  mov     r8d, 0Ah
0x1400033e4  lea     rdx, aBuildlabex; "BuildLabEx"
0x1400033eb  lea     rcx, [rbp+57h+var_88]
0x1400033ef  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400033f4  nop
0x1400033f5  xorps   xmm0, xmm0
0x1400033f8  movups  [rbp+57h+var_A8], xmm0
0x1400033fc  xorps   xmm1, xmm1
0x1400033ff  movdqu  [rbp+57h+var_98], xmm1
0x140003404  mov     edi, 2Ch ; ','
0x140003409  mov     r8d, edi
0x14000340c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x140003413  lea     rcx, [rbp+57h+var_A8]
0x140003417  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14000341c  nop
0x14000341d  lea     r9, [rbp+57h+var_48]
0x140003421  lea     r8, [rbp+57h+var_88]
0x140003425  lea     rdx, [rbp+57h+var_A8]
0x140003429  call    GetStringRegKey
0x14000342e  nop
0x14000342f  lea     rcx, [rbp+57h+var_A8]
0x140003433  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140003438  nop
0x140003439  lea     rcx, [rbp+57h+var_88]
0x14000343d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140003442  xorps   xmm0, xmm0
0x140003445  movups  [rbp+57h+var_A8], xmm0
0x140003449  xorps   xmm1, xmm1
0x14000344c  movdqu  [rbp+57h+var_98], xmm1
0x140003451  lea     r8d, [rdi-23h]
0x140003455  lea     rdx, aEditionid; "EditionID"
0x14000345c  lea     rcx, [rbp+57h+var_A8]
0x140003460  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003465  nop
0x140003466  xorps   xmm0, xmm0
0x140003469  movups  [rbp+57h+var_88], xmm0
0x14000346d  xorps   xmm1, xmm1
0x140003470  movdqu  [rbp+57h+var_78], xmm1
0x140003475  mov     r8d, edi
0x140003478  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x14000347f  lea     rcx, [rbp+57h+var_88]
0x140003483  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140003488  nop
0x140003489  lea     r9, [rbp+57h+var_68]
0x14000348d  lea     r8, [rbp+57h+var_A8]
0x140003491  lea     rdx, [rbp+57h+var_88]
0x140003495  call    GetStringRegKey
0x14000349a  nop
0x14000349b  lea     rcx, [rbp+57h+var_88]
0x14000349f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400034a4  nop
0x1400034a5  lea     rcx, [rbp+57h+var_A8]
0x1400034a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400034ae  xorps   xmm0, xmm0
0x1400034b1  movups  [rbp+57h+var_A8], xmm0
0x1400034b5  xorps   xmm1, xmm1
0x1400034b8  movdqu  [rbp+57h+var_98], xmm1
0x1400034bd  lea     r8d, [rdi-25h]
0x1400034c1  lea     rdx, aCompact; "Compact"
0x1400034c8  lea     rcx, [rbp+57h+var_A8]
0x1400034cc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400034d1  nop
0x1400034d2  xorps   xmm0, xmm0
0x1400034d5  movups  [rbp+57h+var_88], xmm0
0x1400034d9  xorps   xmm1, xmm1
0x1400034dc  movdqu  [rbp+57h+var_78], xmm1
0x1400034e1  lea     r8d, [rdi-20h]
0x1400034e5  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x1400034ec  lea     rcx, [rbp+57h+var_88]
0x1400034f0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400034f5  lea     r9, [rbp+57h+var_B0]
0x1400034f9  lea     r8, [rbp+57h+var_A8]
0x1400034fd  lea     rdx, [rbp+57h+var_88]
0x140003501  call    GetDwordRegKey
0x140003506  lea     rcx, [rbp+57h+var_88]
0x14000350a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000350f  nop
0x140003510  lea     rcx, [rbp+57h+var_A8]
0x140003514  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140003519  mov     eax, [rbp+57h+var_B0]
0x14000351c  lea     r9, [rbp+57h+var_68]
0x140003520  cmp     qword ptr [rbp+57h+var_58+8], 7
0x140003525  cmova   r9, qword ptr [rbp+57h+var_68]
0x14000352a  lea     r8, [rbp+57h+var_48]
0x14000352e  cmp     qword ptr [rbp+57h+var_38+8], 7
0x140003533  cmova   r8, qword ptr [rbp+57h+var_48]
0x140003538  mov     [rsp+0E0h+var_C0], eax
0x14000353c  lea     rdx, aMetadataSSU; "Metadata,%s,%s,%u\n"
0x140003543  mov     rcx, rbx; Stream
0x140003546  call    fwprintf
0x14000354b  nop
0x14000354c  lea     rcx, [rbp+57h+var_68]
0x140003550  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140003555  nop
0x140003556  lea     rcx, [rbp+57h+var_48]
0x14000355a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000355f  mov     rcx, [rbp+57h+var_28]
0x140003563  xor     rcx, rsp; StackCookie
0x140003566  call    __security_check_cookie
0x14000356b  add     rsp, 0C8h
0x140003572  pop     rdi
0x140003573  pop     rsi
0x140003574  pop     rbx
0x140003575  pop     rbp
0x140003576  retn
```
