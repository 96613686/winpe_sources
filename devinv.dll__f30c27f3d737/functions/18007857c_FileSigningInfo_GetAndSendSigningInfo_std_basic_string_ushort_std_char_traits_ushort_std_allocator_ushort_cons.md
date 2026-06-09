# FileSigningInfo::GetAndSendSigningInfo(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18007857c`
- end: `0x1800787f6`
- name: `?GetAndSendSigningInfo@FileSigningInfo@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `634`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031cd0`
- `0x18004ddcc`

## callees

- `0x180005e40`
- `0x1800061f0`
- `0x18000642c`
- `0x180006494`
- `0x180014b80`
- `0x180078308`
- `0x18007857c`
- `0x1800787fc`
- `0x180078e9c`
- `0x1800795e0`
- `0x180079b58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078729`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800787d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800787d2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078675`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078675`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800786d5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800786d5`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180078719`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180078719`

## string_xrefs

- `0x1800786c7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18007870b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FileSigningInfo::GetAndSendSigningInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // ebx
  int Data; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+48h] [rbp-B8h]
  void **v13; // [rsp+50h] [rbp-B0h] BYREF
  char v14; // [rsp+58h] [rbp-A8h]
  __int128 v15; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h]
  _OWORD v17[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v18; // [rsp+A0h] [rbp-60h]
  __m128i v19; // [rsp+B0h] [rbp-50h]
  __int128 v20; // [rsp+C0h] [rbp-40h]
  __m128i v21; // [rsp+D0h] [rbp-30h]
  __int128 v22; // [rsp+E0h] [rbp-20h]
  __m128i v23; // [rsp+F0h] [rbp-10h]
  __int128 v24; // [rsp+100h] [rbp+0h]
  __m128i v25; // [rsp+110h] [rbp+10h]
  _OWORD v26[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v27[2]; // [rsp+140h] [rbp+40h] BYREF

  v8 = 0;
  v13 = &FileSigningInfo::`vftable';
  v14 = 1;
  v15 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v15) = 0;
  v17[0] = 0;
  v17[1] = si128;
  LOWORD(v17[0]) = 0;
  v18 = 0;
  v19 = si128;
  LOWORD(v18) = 0;
  v20 = 0;
  v21 = si128;
  LOWORD(v20) = 0;
  v22 = 0;
  v23 = si128;
  LOWORD(v22) = 0;
  v24 = 0;
  v25 = si128;
  LOWORD(v24) = 0;
  v26[0] = 0;
  v26[1] = si128;
  LOWORD(v26[0]) = 0;
  v27[0] = 0;
  v27[1] = si128;
  LOWORD(v27[0]) = 0;
  if ( !FileSigningInfo::syncIdAlreadySent )
  {
    if ( dword_180157DAC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_180157DAC);
      if ( dword_180157DAC == -1 )
      {
        InitializeCriticalSectionEx(&stru_180157DB0, 0, 0);
        atexit(FileSigningInfo::GetAndSendSigningInfo_::_5_::_dynamic_atexit_destructor_for__criticalSection__);
        Init_thread_footer(&dword_180157DAC);
      }
    }
    EnterCriticalSection(&stru_180157DB0);
    v12 = &stru_180157DB0;
    if ( !FileSigningInfo::syncIdAlreadySent )
    {
      Data = 0;
      pcbData = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
        L"fileSigningInitialized",
        0x20000018u,
        0,
        &Data,
        &pcbData);
      if ( !Data )
      {
        FileSigningInfo::SendStartSync();
        Data = 1;
        RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
          L"fileSigningInitialized",
          4u,
          &Data,
          4u);
      }
    }
    FileSigningInfo::syncIdAlreadySent = 1;
    LeaveCriticalSection(&stru_180157DB0);
  }
  std::wstring::operator=(&v15, a2);
  std::wstring::operator=(v17, a1);
  std::wstring::operator=(v26, a3);
  std::wstring::operator=(v27, a4);
  FileSigningInfo::GetCatalogSignerInfo((FileSigningInfo *)&v13);
  if ( v14 )
  {
    FileSigningInfo::GetEmbeddedSignerInfo((FileSigningInfo *)&v13);
    v8 = FileSigningInfo::SendSigningUTC((FileSigningInfo *)&v13);
  }
  FileSigningInfo::~FileSigningInfo((FileSigningInfo *)&v13);
  return v8;
}

```

## disassembly

```asm
0x18007857c  push    rbp
0x18007857e  push    rbx
0x18007857f  push    rsi
0x180078580  push    rdi
0x180078581  push    r13
0x180078583  push    r14
0x180078585  push    r15
0x180078587  lea     rbp, [rsp-70h]
0x18007858c  sub     rsp, 170h
0x180078593  mov     rax, cs:__security_cookie
0x18007859a  xor     rax, rsp
0x18007859d  mov     [rbp+0A0h+var_40], rax
0x1800785a1  mov     r15, r9
0x1800785a4  mov     r14, r8
0x1800785a7  mov     rsi, rdx
0x1800785aa  mov     rdi, rcx
0x1800785ad  xor     ebx, ebx
0x1800785af  lea     rax, ??_7FileSigningInfo@@6B@; const FileSigningInfo::`vftable'
0x1800785b6  mov     [rsp+1A0h+var_150], rax
0x1800785bb  mov     [rsp+1A0h+var_148], 1
0x1800785c0  xorps   xmm0, xmm0
0x1800785c3  movups  [rsp+1A0h+var_140], xmm0
0x1800785c8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800785d0  movdqa  [rsp+1A0h+var_130], xmm1
0x1800785d6  xor     eax, eax
0x1800785d8  mov     word ptr [rsp+1A0h+var_140], ax
0x1800785dd  movups  [rbp+0A0h+var_120], xmm0
0x1800785e1  movdqa  [rbp+0A0h+var_110], xmm1
0x1800785e6  mov     word ptr [rbp+0A0h+var_120], ax
0x1800785ea  movups  [rbp+0A0h+var_100], xmm0
0x1800785ee  movdqa  [rbp+0A0h+var_F0], xmm1
0x1800785f3  mov     word ptr [rbp+0A0h+var_100], ax
0x1800785f7  movups  [rbp+0A0h+var_E0], xmm0
0x1800785fb  movdqa  [rbp+0A0h+var_D0], xmm1
0x180078600  mov     word ptr [rbp+0A0h+var_E0], ax
0x180078604  movups  [rbp+0A0h+var_C0], xmm0
0x180078608  movdqa  [rbp+0A0h+var_B0], xmm1
0x18007860d  mov     word ptr [rbp+0A0h+var_C0], ax
0x180078611  movups  [rbp+0A0h+var_A0], xmm0
0x180078615  movdqa  [rbp+0A0h+var_90], xmm1
0x18007861a  mov     word ptr [rbp+0A0h+var_A0], ax
0x18007861e  movups  [rbp+0A0h+var_80], xmm0
0x180078622  movdqa  [rbp+0A0h+var_70], xmm1
0x180078627  mov     word ptr [rbp+0A0h+var_80], ax
0x18007862b  movups  [rbp+0A0h+var_60], xmm0
0x18007862f  movdqa  [rbp+0A0h+var_50], xmm1
0x180078634  mov     word ptr [rbp+0A0h+var_60], ax
0x180078638  cmp     cs:?syncIdAlreadySent@FileSigningInfo@@0_NA, al; bool FileSigningInfo::syncIdAlreadySent
0x18007863e  jnz     loc_18007872F
0x180078644  mov     ecx, cs:_tls_index
0x18007864a  mov     rax, gs:58h
0x180078653  mov     edx, 4
0x180078658  mov     rax, [rax+rcx*8]
0x18007865c  lea     r13, stru_180157DB0
0x180078663  mov     eax, [rdx+rax]
0x180078666  cmp     cs:dword_180157DAC, eax
0x18007866c  jg      loc_1800787B1
0x180078672  mov     rcx, r13; lpCriticalSection
0x180078675  call    cs:__imp_EnterCriticalSection
0x18007867b  mov     [rsp+1A0h+var_158], r13
0x180078680  cmp     cs:?syncIdAlreadySent@FileSigningInfo@@0_NA, 0; bool FileSigningInfo::syncIdAlreadySent
0x180078687  jnz     loc_18007871F
0x18007868d  mov     [rsp+1A0h+Data], 0
0x180078695  mov     [rsp+1A0h+var_15C], 4
0x18007869d  lea     rax, [rsp+1A0h+var_15C]
0x1800786a2  mov     [rsp+1A0h+pcbData], rax; pcbData
0x1800786a7  lea     rax, [rsp+1A0h+Data]
0x1800786ac  mov     [rsp+1A0h+pvData], rax; pvData
0x1800786b1  mov     [rsp+1A0h+pdwType], 0; pdwType
0x1800786ba  mov     r9d, 20000018h; dwFlags
0x1800786c0  lea     r8, aFilesigningini; "fileSigningInitialized"
0x1800786c7  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800786ce  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800786d5  call    cs:__imp_RegGetValueW
0x1800786db  cmp     [rsp+1A0h+Data], 0
0x1800786e0  jnz     short loc_18007871F
0x1800786e2  call    ?SendStartSync@FileSigningInfo@@CAXXZ; FileSigningInfo::SendStartSync(void)
0x1800786e7  mov     [rsp+1A0h+Data], 1
0x1800786ef  mov     r9d, 4; dwType
0x1800786f5  mov     dword ptr [rsp+1A0h+pvData], r9d; cbData
0x1800786fa  lea     rax, [rsp+1A0h+Data]
0x1800786ff  mov     [rsp+1A0h+pdwType], rax; lpData
0x180078704  lea     r8, aFilesigningini; "fileSigningInitialized"
0x18007870b  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180078712  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180078719  call    cs:__imp_RegSetKeyValueW
0x18007871f  mov     cs:?syncIdAlreadySent@FileSigningInfo@@0_NA, 1; bool FileSigningInfo::syncIdAlreadySent
0x180078726  mov     rcx, r13; lpCriticalSection
0x180078729  call    cs:__imp_LeaveCriticalSection
0x18007872f  mov     rdx, rsi
0x180078732  lea     rcx, [rsp+1A0h+var_140]
0x180078737  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18007873c  mov     rdx, rdi
0x18007873f  lea     rcx, [rbp+0A0h+var_120]
0x180078743  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180078748  mov     rdx, r14
0x18007874b  lea     rcx, [rbp+0A0h+var_80]
0x18007874f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180078754  mov     rdx, r15
0x180078757  lea     rcx, [rbp+0A0h+var_60]
0x18007875b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180078760  lea     rcx, [rsp+1A0h+var_150]; this
0x180078765  call    ?GetCatalogSignerInfo@FileSigningInfo@@AEAAJXZ; FileSigningInfo::GetCatalogSignerInfo(void)
0x18007876a  cmp     [rsp+1A0h+var_148], 0
0x18007876f  jz      short loc_180078787
0x180078771  lea     rcx, [rsp+1A0h+var_150]; this
0x180078776  call    ?GetEmbeddedSignerInfo@FileSigningInfo@@AEAAJXZ; FileSigningInfo::GetEmbeddedSignerInfo(void)
0x18007877b  lea     rcx, [rsp+1A0h+var_150]; this
0x180078780  call    ?SendSigningUTC@FileSigningInfo@@AEAAJXZ; FileSigningInfo::SendSigningUTC(void)
0x180078785  mov     ebx, eax
0x180078787  lea     rcx, [rsp+1A0h+var_150]; this
0x18007878c  call    ??1FileSigningInfo@@UEAA@XZ; FileSigningInfo::~FileSigningInfo(void)
0x180078791  mov     eax, ebx
0x180078793  mov     rcx, [rbp+0A0h+var_40]
0x180078797  xor     rcx, rsp; StackCookie
0x18007879a  call    __security_check_cookie
0x18007879f  add     rsp, 170h
0x1800787a6  pop     r15
0x1800787a8  pop     r14
0x1800787aa  pop     r13
0x1800787ac  pop     rdi
0x1800787ad  pop     rsi
0x1800787ae  pop     rbx
0x1800787af  pop     rbp
0x1800787b0  retn
0x1800787b1  lea     rcx, dword_180157DAC
0x1800787b8  call    _Init_thread_header
0x1800787bd  cmp     cs:dword_180157DAC, 0FFFFFFFFh
0x1800787c4  jnz     loc_180078672
0x1800787ca  xor     r8d, r8d; Flags
0x1800787cd  xor     edx, edx; dwSpinCount
0x1800787cf  mov     rcx, r13; lpCriticalSection
0x1800787d2  call    cs:__imp_InitializeCriticalSectionEx
0x1800787d8  lea     rcx, _FileSigningInfo__GetAndSendSigningInfo____5____dynamic_atexit_destructor_for__criticalSection__; void (__cdecl *)()
0x1800787df  call    atexit
0x1800787e4  lea     rcx, dword_180157DAC
0x1800787eb  call    _Init_thread_footer
0x1800787f0  jmp     loc_180078672
```
