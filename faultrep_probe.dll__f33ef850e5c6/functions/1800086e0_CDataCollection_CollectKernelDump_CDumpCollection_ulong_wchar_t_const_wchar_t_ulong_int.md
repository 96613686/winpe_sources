# CDataCollection::CollectKernelDump(CDumpCollection *,ulong,wchar_t const *,wchar_t *,ulong,int)

- ea: `0x1800086e0`
- end: `0x180008966`
- name: `?CollectKernelDump@CDataCollection@@AEAAJPEAVCDumpCollection@@KPEB_WPEA_WKH@Z`
- size: `646`
- prototype: `__int64 __fastcall(CDataCollection *this, struct _RTL_CRITICAL_SECTION *, unsigned int, const wchar_t *, wchar_t *lpFileName, unsigned int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180008970`

## callees

- `0x180002890`
- `0x18000760c`
- `0x1800086e0`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a154`
- `0x18003f144`
- `0x18003f334`
- `0x18003f740`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800088eb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800088fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800088fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataCollection::CollectKernelDump(
        CDataCollection *this,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned int a3,
        const wchar_t *a4,
        wchar_t *lpFileName,
        unsigned int a6,
        int a7)
{
  int ShortApplicationName; // eax
  __int64 v11; // rcx
  int v12; // edi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  HANDLE hObject[2]; // [rsp+40h] [rbp-258h] BYREF
  wchar_t v19[264]; // [rsp+50h] [rbp-248h] BYREF

  if ( lpFileName && a2 )
  {
    hObject[0] = 0;
    *lpFileName = 0;
    ShortApplicationName = CDumpCollection::GetShortApplicationName(a2, v19, a3);
    v12 = ShortApplicationName;
    if ( ShortApplicationName < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v14 = 17;
      goto LABEL_7;
    }
    if ( a7 )
    {
      ShortApplicationName = CFileCollection::CreateCollectionFileByName(
                               v11,
                               a4,
                               1,
                               (__int16 *)v19,
                               (__int64)L"full.odk.dmp",
                               0,
                               lpFileName,
                               hObject);
      v12 = ShortApplicationName;
      if ( ShortApplicationName < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        v14 = 18;
        goto LABEL_7;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, lpFileName);
      v16 = CDumpCollection::CollectLiveKernelFullDump((CDumpCollection *)a2, hObject[0], a3);
    }
    else
    {
      ShortApplicationName = CFileCollection::CreateCollectionFileByName(
                               v11,
                               a4,
                               1,
                               (__int16 *)v19,
                               (__int64)L"mini.odk.dmp",
                               0,
                               lpFileName,
                               hObject);
      v12 = ShortApplicationName;
      if ( ShortApplicationName < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_31;
        v14 = 20;
LABEL_7:
        v15 = (unsigned int)ShortApplicationName;
        goto LABEL_8;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, lpFileName);
      v16 = CDumpCollection::CollectLiveKernelMiniDump((CDumpCollection *)a2, hObject[0], a3);
    }
    v12 = v16;
    if ( v16 >= 0 )
    {
      v12 = 0;
      goto LABEL_31;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v14 = 22;
    v15 = (unsigned int)v16;
LABEL_8:
    WPP_SF_d(v13[2], v14, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids, v15);
LABEL_31:
    if ( (unsigned __int64)hObject[0] + 1 > 1 )
      CloseHandle(hObject[0]);
    if ( v12 < 0 )
    {
      if ( *lpFileName )
      {
        DeleteFileW(lpFileName);
        *lpFileName = 0;
      }
    }
    return (unsigned int)v12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800086e0  mov     [rsp+arg_0], rbx
0x1800086e5  push    rbp
0x1800086e6  push    rsi
0x1800086e7  push    rdi
0x1800086e8  push    r14
0x1800086ea  push    r15
0x1800086ec  sub     rsp, 270h
0x1800086f3  mov     rax, cs:__security_cookie
0x1800086fa  xor     rax, rsp
0x1800086fd  mov     [rsp+298h+var_38], rax
0x180008705  mov     rbx, r9
0x180008708  mov     r14d, r8d
0x18000870b  mov     rbp, rdx
0x18000870e  mov     rsi, [rsp+298h+lpFileName]
0x180008716  xor     r15d, r15d
0x180008719  test    rsi, rsi
0x18000871c  jz      loc_18000890C
0x180008722  test    rdx, rdx
0x180008725  jz      loc_18000890C
0x18000872b  mov     [rsp+298h+hObject], r15
0x180008730  mov     [rsi], r15w
0x180008734  lea     rdx, [rsp+298h+var_248]; wchar_t *
0x180008739  mov     rcx, rbp; lpCriticalSection
0x18000873c  call    ?GetShortApplicationName@CDumpCollection@@QEAAJPEA_WI@Z; CDumpCollection::GetShortApplicationName(wchar_t *,uint)
0x180008741  mov     edi, eax
0x180008743  test    eax, eax
0x180008745  jns     short loc_180008784
0x180008747  lea     rbx, WPP_GLOBAL_Control
0x18000874e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008755  cmp     rcx, rbx
0x180008758  jz      loc_1800088DC
0x18000875e  test    byte ptr [rcx+1Ch], 1
0x180008762  jz      loc_1800088DC
0x180008768  lea     edx, [r15+11h]
0x18000876c  mov     r9d, eax
0x18000876f  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008776  mov     rcx, [rcx+10h]
0x18000877a  call    WPP_SF_d
0x18000877f  jmp     loc_1800088DC
0x180008784  lea     rax, [rsp+298h+hObject]
0x180008789  lea     r9, [rsp+298h+var_248]
0x18000878e  mov     r8d, 1
0x180008794  mov     rdx, rbx
0x180008797  mov     [rsp+298h+var_260], rax
0x18000879c  mov     [rsp+298h+var_268], rsi
0x1800087a1  mov     [rsp+298h+var_270], r15d
0x1800087a6  cmp     [rsp+298h+arg_30], r15d
0x1800087ae  jz      loc_180008839
0x1800087b4  lea     rax, aFullOdkDmp; "full.odk.dmp"
0x1800087bb  mov     [rsp+298h+var_278], rax
0x1800087c0  call    ?CreateCollectionFileByName@CFileCollection@@QEAAJPEB_WW4_FILECOLLECTION_ACL_TYPE@@00HPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CFileCollection::CreateCollectionFileByName(wchar_t const *,_FILECOLLECTION_ACL_TYPE,wchar_t const *,wchar_t const *,int,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)
0x1800087c5  mov     edi, eax
0x1800087c7  test    eax, eax
0x1800087c9  jns     short loc_1800087F6
0x1800087cb  lea     rbx, WPP_GLOBAL_Control
0x1800087d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087d9  cmp     rcx, rbx
0x1800087dc  jz      loc_1800088DC
0x1800087e2  test    byte ptr [rcx+1Ch], 1
0x1800087e6  jz      loc_1800088DC
0x1800087ec  mov     edx, 12h
0x1800087f1  jmp     loc_18000876C
0x1800087f6  lea     rbx, WPP_GLOBAL_Control
0x1800087fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008804  cmp     rcx, rbx
0x180008807  jz      short loc_180008827
0x180008809  test    byte ptr [rcx+1Ch], 4
0x18000880d  jz      short loc_180008827
0x18000880f  mov     edx, 13h
0x180008814  mov     r9, rsi
0x180008817  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x18000881e  mov     rcx, [rcx+10h]
0x180008822  call    WPP_SF_S
0x180008827  mov     r8d, r14d; unsigned int
0x18000882a  mov     rdx, [rsp+298h+hObject]; void *
0x18000882f  mov     rcx, rbp; this
0x180008832  call    ?CollectLiveKernelFullDump@CDumpCollection@@QEAAJPEAXK@Z; CDumpCollection::CollectLiveKernelFullDump(void *,ulong)
0x180008837  jmp     short loc_1800088B4
0x180008839  lea     rax, aMiniOdkDmp; "mini.odk.dmp"
0x180008840  mov     [rsp+298h+var_278], rax
0x180008845  call    ?CreateCollectionFileByName@CFileCollection@@QEAAJPEB_WW4_FILECOLLECTION_ACL_TYPE@@00HPEA_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CFileCollection::CreateCollectionFileByName(wchar_t const *,_FILECOLLECTION_ACL_TYPE,wchar_t const *,wchar_t const *,int,wchar_t *,tlx::unique_any<tlx::file_handle_traits> *)
0x18000884a  mov     edi, eax
0x18000884c  test    eax, eax
0x18000884e  jns     short loc_180008873
0x180008850  lea     rbx, WPP_GLOBAL_Control
0x180008857  mov     rcx, cs:WPP_GLOBAL_Control
0x18000885e  cmp     rcx, rbx
0x180008861  jz      short loc_1800088DC
0x180008863  test    byte ptr [rcx+1Ch], 1
0x180008867  jz      short loc_1800088DC
0x180008869  mov     edx, 14h
0x18000886e  jmp     loc_18000876C
0x180008873  lea     rbx, WPP_GLOBAL_Control
0x18000887a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008881  cmp     rcx, rbx
0x180008884  jz      short loc_1800088A4
0x180008886  test    byte ptr [rcx+1Ch], 4
0x18000888a  jz      short loc_1800088A4
0x18000888c  mov     edx, 15h
0x180008891  mov     r9, rsi
0x180008894  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x18000889b  mov     rcx, [rcx+10h]
0x18000889f  call    WPP_SF_S
0x1800088a4  mov     r8d, r14d; unsigned int
0x1800088a7  mov     rdx, [rsp+298h+hObject]; hFile
0x1800088ac  mov     rcx, rbp; this
0x1800088af  call    ?CollectLiveKernelMiniDump@CDumpCollection@@QEAAJPEAXK@Z; CDumpCollection::CollectLiveKernelMiniDump(void *,ulong)
0x1800088b4  mov     edi, eax
0x1800088b6  test    eax, eax
0x1800088b8  jns     short loc_1800088D9
0x1800088ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088c1  cmp     rcx, rbx
0x1800088c4  jz      short loc_1800088DC
0x1800088c6  test    byte ptr [rcx+1Ch], 1
0x1800088ca  jz      short loc_1800088DC
0x1800088cc  mov     edx, 16h
0x1800088d1  mov     r9d, eax
0x1800088d4  jmp     loc_18000876F
0x1800088d9  mov     edi, r15d
0x1800088dc  mov     rcx, [rsp+298h+hObject]; hObject
0x1800088e1  lea     rax, [rcx+1]
0x1800088e5  cmp     rax, 1
0x1800088e9  jbe     short loc_1800088F1
0x1800088eb  call    cs:__imp_CloseHandle
0x1800088f1  test    edi, edi
0x1800088f3  jns     short loc_180008908
0x1800088f5  cmp     [rsi], r15w
0x1800088f9  jz      short loc_180008908
0x1800088fb  mov     rcx, rsi; lpFileName
0x1800088fe  call    cs:__imp_DeleteFileW
0x180008904  mov     [rsi], r15w
0x180008908  mov     eax, edi
0x18000890a  jmp     short loc_18000893F
0x18000890c  lea     rbx, WPP_GLOBAL_Control
0x180008913  mov     rcx, cs:WPP_GLOBAL_Control
0x18000891a  cmp     rcx, rbx
0x18000891d  jz      short loc_18000893A
0x18000891f  test    byte ptr [rcx+1Ch], 1
0x180008923  jz      short loc_18000893A
0x180008925  mov     edx, 0Fh
0x18000892a  lea     r8, WPP_cba5abcf89e239c36fe0f01eef0158e0_Traceguids
0x180008931  mov     rcx, [rcx+10h]
0x180008935  call    WPP_SF_
0x18000893a  mov     eax, 80070057h
0x18000893f  mov     rcx, [rsp+298h+var_38]
0x180008947  xor     rcx, rsp; StackCookie
0x18000894a  call    __security_check_cookie
0x18000894f  mov     rbx, [rsp+298h+arg_0]
0x180008957  add     rsp, 270h
0x18000895e  pop     r15
0x180008960  pop     r14
0x180008962  pop     rdi
0x180008963  pop     rsi
0x180008964  pop     rbp
0x180008965  retn
```
