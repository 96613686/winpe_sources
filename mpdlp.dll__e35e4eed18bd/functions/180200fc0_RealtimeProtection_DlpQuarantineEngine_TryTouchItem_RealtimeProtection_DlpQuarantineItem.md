# RealtimeProtection::DlpQuarantineEngine::TryTouchItem(RealtimeProtection::_DlpQuarantineItem &)

- ea: `0x180200fc0`
- end: `0x180201261`
- name: `?TryTouchItem@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEAU_DlpQuarantineItem@2@@Z`
- size: `673`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpQuarantineEngine *__hidden this, struct RealtimeProtection::_DlpQuarantineItem *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180092dc0`

## callees

- `0x180080030`
- `0x1800809d0`
- `0x1801047b4`
- `0x180105f50`
- `0x18010cb40`
- `0x1801ff278`
- `0x180200fc0`

## import_xrefs

- `KERNEL32!SetFileTime` at `0x1802011ed`
- `KERNEL32!SetFileTime` at `0x1802011ed`
- `KERNEL32!SystemTimeToFileTime` at `0x1802011d7`
- `KERNEL32!SystemTimeToFileTime` at `0x1802011d7`
- `KERNEL32!GetSystemTime` at `0x1802011c9`
- `KERNEL32!GetSystemTime` at `0x1802011c9`
- `KERNEL32!GetFileTime` at `0x180201138`
- `KERNEL32!GetFileTime` at `0x180201138`
- `KERNEL32!CompareStringOrdinal` at `0x1802011b3`
- `KERNEL32!CompareStringOrdinal` at `0x1802011b3`
- `KERNEL32!CloseHandle` at `0x180201102`
- `KERNEL32!CloseHandle` at `0x180201181`
- `KERNEL32!CloseHandle` at `0x180201235`
- `KERNEL32!CloseHandle` at `0x180201102`
- `KERNEL32!CloseHandle` at `0x180201181`
- `KERNEL32!CloseHandle` at `0x180201235`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpQuarantineEngine::TryTouchItem(
        RealtimeProtection::DlpQuarantineEngine *this,
        struct RealtimeProtection::_DlpQuarantineItem *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v6; // r9
  void ***v7; // rbx
  void **v8; // rdx
  int File; // eax
  unsigned int v10; // r15d
  unsigned int LastFailure; // eax
  const WCHAR *v12; // rcx
  HANDLE hObject; // [rsp+40h] [rbp-40h] BYREF
  struct _FILETIME LastWriteTime; // [rsp+48h] [rbp-38h] BYREF
  struct _FILETIME LastAccessTime; // [rsp+50h] [rbp-30h] BYREF
  struct _FILETIME CreationTime; // [rsp+58h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  if ( !*((_BYTE *)a2 + 48) )
  {
    v3 = RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(this, a2);
    v4 = v3;
    if ( v3 < 0 )
    {
      *(_DWORD *)a2 = 7;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
          (unsigned int)v3);
      return v4;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = (_QWORD *)((char *)a2 + 224);
    if ( *((_QWORD *)a2 + 31) > 7u )
      v6 = (_QWORD *)*v6;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v6);
  }
  v7 = (void ***)((char *)a2 + 224);
  hObject = (HANDLE)-1LL;
  v8 = (void **)((char *)a2 + 224);
  if ( *((_QWORD *)a2 + 31) > 7u )
    v8 = *v7;
  File = CommonUtil::UtilCreateFile((CommonUtil *)&hObject, v8, (const wchar_t *)0x100100, 0, 3u, 0, 0, 0, hObject);
  v10 = File;
  if ( File >= 0 )
  {
    CreationTime = 0;
    LastAccessTime = 0;
    LastWriteTime = 0;
    if ( !GetFileTime(hObject, &CreationTime, &LastAccessTime, &LastWriteTime) )
    {
      LastFailure = HrGetLastFailure();
      v4 = LastFailure;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, LastFailure);
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      return v4;
    }
    v12 = (const WCHAR *)((char *)a2 + 568);
    if ( *((_QWORD *)a2 + 74) > 7u )
      v12 = *(const WCHAR **)v12;
    if ( CompareStringOrdinal(v12, -1, L"googledrivesync", -1, 1) == 2 )
    {
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      SystemTimeToFileTime(&SystemTime, &LastWriteTime);
    }
    if ( SetFileTime(hObject, &CreationTime, &LastAccessTime, &LastWriteTime)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      if ( *((_QWORD *)a2 + 31) > 7u )
        v7 = (void ***)*v7;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids, v7);
    }
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        89,
        &WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids,
        (unsigned int)File);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return v10;
  }
}

```

## disassembly

```asm
0x180200fc0  mov     [rsp-18h+arg_10], rbx
0x180200fc5  mov     [rsp-18h+arg_18], rsi
0x180200fca  push    rbp
0x180200fcb  push    rdi
0x180200fcc  push    r15
0x180200fce  mov     rbp, rsp
0x180200fd1  sub     rsp, 80h
0x180200fd8  mov     rax, cs:__security_cookie
0x180200fdf  xor     rax, rsp
0x180200fe2  mov     [rbp+var_10], rax
0x180200fe6  cmp     byte ptr [rdx+30h], 0
0x180200fea  mov     rsi, rdx
0x180200fed  jnz     short loc_180201038
0x180200fef  call    ?ResolveQuarantineItemPaths@DlpQuarantineEngine@RealtimeProtection@@AEAAJAEAU_DlpQuarantineItem@2@@Z; RealtimeProtection::DlpQuarantineEngine::ResolveQuarantineItemPaths(RealtimeProtection::_DlpQuarantineItem &)
0x180200ff4  mov     ebx, eax
0x180200ff6  test    eax, eax
0x180200ff8  jns     short loc_180201038
0x180200ffa  mov     dword ptr [rsi], 7
0x180201000  mov     rcx, cs:WPP_GLOBAL_Control
0x180201007  lea     rdi, WPP_GLOBAL_Control
0x18020100e  cmp     rcx, rdi
0x180201011  jz      short loc_180201031
0x180201013  test    byte ptr [rcx+1Ch], 1
0x180201017  jz      short loc_180201031
0x180201019  mov     rcx, [rcx+10h]
0x18020101d  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180201024  mov     edx, 57h ; 'W'
0x180201029  mov     r9d, eax
0x18020102c  call    WPP_SF_d
0x180201031  mov     eax, ebx
0x180201033  jmp     loc_18020123D
0x180201038  mov     rcx, cs:WPP_GLOBAL_Control
0x18020103f  lea     rdi, WPP_GLOBAL_Control
0x180201046  cmp     rcx, rdi
0x180201049  jz      short loc_180201077
0x18020104b  test    byte ptr [rcx+1Ch], 4
0x18020104f  jz      short loc_180201077
0x180201051  lea     r9, [rsi+0E0h]
0x180201058  cmp     qword ptr [r9+18h], 7
0x18020105d  jbe     short loc_180201062
0x18020105f  mov     r9, [r9]
0x180201062  mov     rcx, [rcx+10h]
0x180201066  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x18020106d  mov     edx, 58h ; 'X'
0x180201072  call    WPP_SF_S
0x180201077  lea     rbx, [rsi+0E0h]
0x18020107e  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x180201086  cmp     qword ptr [rbx+18h], 7
0x18020108b  mov     rdx, rbx
0x18020108e  jbe     short loc_180201093
0x180201090  mov     rdx, [rbx]; void **
0x180201093  mov     [rsp+80h+var_48], 0; struct _SECURITY_ATTRIBUTES *
0x18020109c  lea     rcx, [rbp+hObject]; this
0x1802010a0  mov     qword ptr [rsp+80h+var_50], 0; unsigned int
0x1802010a9  xor     r9d, r9d; unsigned int
0x1802010ac  mov     [rsp+80h+var_58], 0; unsigned int
0x1802010b4  mov     r8d, 100100h; wchar_t *
0x1802010ba  mov     [rsp+80h+bIgnoreCase], 3; unsigned int
0x1802010c2  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x1802010c7  mov     r15d, eax
0x1802010ca  test    eax, eax
0x1802010cc  jns     short loc_180201110
0x1802010ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1802010d5  cmp     rcx, rdi
0x1802010d8  jz      short loc_1802010F8
0x1802010da  test    byte ptr [rcx+1Ch], 1
0x1802010de  jz      short loc_1802010F8
0x1802010e0  mov     rcx, [rcx+10h]
0x1802010e4  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x1802010eb  mov     edx, 59h ; 'Y'
0x1802010f0  mov     r9d, eax
0x1802010f3  call    WPP_SF_d
0x1802010f8  mov     rcx, [rbp+hObject]; hObject
0x1802010fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180201100  jz      short loc_180201108
0x180201102  call    cs:__imp_CloseHandle
0x180201108  mov     eax, r15d
0x18020110b  jmp     loc_18020123D
0x180201110  mov     rcx, [rbp+hObject]; hFile
0x180201114  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x180201118  lea     r8, [rbp+LastAccessTime]; lpLastAccessTime
0x18020111c  mov     qword ptr [rbp+CreationTime.dwLowDateTime], 0
0x180201124  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x180201128  mov     qword ptr [rbp+LastAccessTime.dwLowDateTime], 0
0x180201130  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], 0
0x180201138  call    cs:__imp_GetFileTime
0x18020113e  test    eax, eax
0x180201140  jnz     short loc_18020118C
0x180201142  call    HrGetLastFailure
0x180201147  mov     ebx, eax
0x180201149  mov     rcx, cs:WPP_GLOBAL_Control
0x180201150  cmp     rcx, rdi
0x180201153  jz      short loc_180201173
0x180201155  test    byte ptr [rcx+1Ch], 1
0x180201159  jz      short loc_180201173
0x18020115b  mov     rcx, [rcx+10h]
0x18020115f  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x180201166  mov     edx, 5Ah ; 'Z'
0x18020116b  mov     r9d, eax
0x18020116e  call    WPP_SF_d
0x180201173  mov     rcx, [rbp+hObject]; hObject
0x180201177  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18020117b  jz      loc_180201031
0x180201181  call    cs:__imp_CloseHandle
0x180201187  jmp     loc_180201031
0x18020118c  lea     rcx, [rsi+238h]
0x180201193  cmp     qword ptr [rcx+18h], 7
0x180201198  jbe     short loc_18020119D
0x18020119a  mov     rcx, [rcx]; lpString1
0x18020119d  or      r9d, 0FFFFFFFFh; cchCount2
0x1802011a1  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x1802011a9  or      edx, r9d; cchCount1
0x1802011ac  lea     r8, aGoogledrivesyn; "googledrivesync"
0x1802011b3  call    cs:__imp_CompareStringOrdinal
0x1802011b9  cmp     eax, 2
0x1802011bc  jnz     short loc_1802011DD
0x1802011be  xorps   xmm0, xmm0
0x1802011c1  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1802011c5  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1802011c9  call    cs:__imp_GetSystemTime
0x1802011cf  lea     rdx, [rbp+LastWriteTime]; lpFileTime
0x1802011d3  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1802011d7  call    cs:__imp_SystemTimeToFileTime
0x1802011dd  mov     rcx, [rbp+hObject]; hFile
0x1802011e1  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x1802011e5  lea     r8, [rbp+LastAccessTime]; lpLastAccessTime
0x1802011e9  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x1802011ed  call    cs:__imp_SetFileTime
0x1802011f3  test    eax, eax
0x1802011f5  jz      short loc_18020122B
0x1802011f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1802011fe  cmp     rcx, rdi
0x180201201  jz      short loc_18020122B
0x180201203  test    byte ptr [rcx+1Ch], 10h
0x180201207  jz      short loc_18020122B
0x180201209  cmp     qword ptr [rbx+18h], 7
0x18020120e  jbe     short loc_180201213
0x180201210  mov     rbx, [rbx]
0x180201213  mov     rcx, [rcx+10h]
0x180201217  lea     r8, WPP_279262f6a92d3ed3802ea32f23c6c9ff_Traceguids
0x18020121e  mov     edx, 5Bh ; '['
0x180201223  mov     r9, rbx
0x180201226  call    WPP_SF_S
0x18020122b  mov     rcx, [rbp+hObject]; hObject
0x18020122f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180201233  jz      short loc_18020123B
0x180201235  call    cs:__imp_CloseHandle
0x18020123b  xor     eax, eax
0x18020123d  mov     rcx, [rbp+var_10]
0x180201241  xor     rcx, rsp; StackCookie
0x180201244  call    __security_check_cookie
0x180201249  lea     r11, [rsp+80h+var_s0]
0x180201251  mov     rbx, [r11+30h]
0x180201255  mov     rsi, [r11+38h]
0x180201259  mov     rsp, r11
0x18020125c  pop     r15
0x18020125e  pop     rdi
0x18020125f  pop     rbp
0x180201260  retn
```
