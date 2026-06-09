# CPersistUserData::CreateSiteTable(void)

- ea: `0x180a5dc08`
- end: `0x180a5de3d`
- name: `?CreateSiteTable@CPersistUserData@@CAJXZ`
- size: `565`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180a5f478`

## callees

- `0x18005d080`
- `0x180a5dc08`
- `0x180a5eb8c`
- `0x180a5f0cc`
- `0x180b5c9c4`
- `0x1810f65c0`
- `0x181100f20`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a5dcfb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180a5dcfb`
- `KERNEL32!CompareFileTime` at `0x180a5dd2e`
- `KERNEL32!CompareFileTime` at `0x180a5dd48`
- `KERNEL32!CompareFileTime` at `0x180a5dd2e`
- `KERNEL32!CompareFileTime` at `0x180a5dd48`
- `KERNEL32!GetLastError` at `0x180a5dcba`
- `KERNEL32!GetLastError` at `0x180a5dcba`
- `KERNEL32!LeaveCriticalSection` at `0x180a5de0a`
- `KERNEL32!LeaveCriticalSection` at `0x180a5de0a`
- `KERNEL32!EnterCriticalSection` at `0x180a5dc42`
- `KERNEL32!EnterCriticalSection` at `0x180a5dc42`
- `WININET!FindCloseUrlCache` at `0x180a5dde9`
- `WININET!FindCloseUrlCache` at `0x180a5dde9`
- `WININET!FindNextUrlCacheEntryW` at `0x180a5ddd2`
- `WININET!FindNextUrlCacheEntryW` at `0x180a5ddd2`
- `WININET!FindFirstUrlCacheEntryW` at `0x180a5dca6`
- `WININET!FindFirstUrlCacheEntryW` at `0x180a5dca6`

## pseudocode

```c
__int64 CPersistUserData::CreateSiteTable(void)
{
  unsigned int v0; // ebx
  __int64 v1; // r8
  CSiteTable *v2; // rax
  HANDLE FirstUrlCacheEntryW; // rdi
  signed int LastError; // eax
  int SiteFromCacheUrl; // eax
  unsigned __int16 *v6; // r8
  unsigned int v7; // edx
  DWORD cbCacheEntryInfo; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v10; // [rsp+24h] [rbp-DCh] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v12; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime1; // [rsp+38h] [rbp-C8h] BYREF
  struct _INTERNET_CACHE_ENTRY_INFOW FirstCacheEntryInfo; // [rsp+40h] [rbp-C0h] BYREF

  v0 = 0;
  EnterCriticalSection(&CPersistUserData::s_csSiteTable);
  if ( !CPersistUserData::s_pSiteTable )
  {
    v2 = (CSiteTable *)MemoryProtection::HeapAlloc<0>(g_hProcessHeap, 16, v1);
    if ( !v2 )
    {
      CPersistUserData::s_pSiteTable = 0;
      v0 = -2147024882;
      goto LABEL_20;
    }
    *(_QWORD *)v2 = 0;
    *((_QWORD *)v2 + 1) = 128;
    cbCacheEntryInfo = 4800;
    FirstCacheEntryInfo.dwStructSize = 112;
    CPersistUserData::s_pSiteTable = v2;
    FirstUrlCacheEntryW = FindFirstUrlCacheEntryW(L"userdata:", &FirstCacheEntryInfo, &cbCacheEntryInfo);
    if ( FirstUrlCacheEntryW )
    {
      FileTime1 = 0;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      while ( 1 )
      {
        if ( FirstCacheEntryInfo.lpszSourceUrlName )
        {
          v10 = 0;
          v12 = 0;
          if ( CompareFileTime(&FileTime1, &FirstCacheEntryInfo.ExpireTime)
            && CompareFileTime(&SystemTimeAsFileTime, &FirstCacheEntryInfo.ExpireTime) > 0 )
          {
            DeleteUrlCacheEntryBugW(FirstCacheEntryInfo.lpszSourceUrlName);
          }
          else
          {
            SiteFromCacheUrl = CPersistUserData::GetSiteFromCacheUrl(FirstCacheEntryInfo.lpszSourceUrlName, &v12, &v10);
            v0 = SiteFromCacheUrl;
            if ( SiteFromCacheUrl == 1 )
            {
              v0 = 0;
            }
            else if ( SiteFromCacheUrl < 0
                   || (v6 = v12,
                       v7 = CPersistUserData::s_dwClusterSizeMinusOne,
                       v12[v10] = 0,
                       (v0 = CPersistUserData::ModifySitesSpaceUsage(
                               v6,
                               CPersistUserData::s_dwClusterSizeMask & (FirstCacheEntryInfo.dwSizeLow + v7))) != 0) )
            {
LABEL_18:
              FindCloseUrlCache(FirstUrlCacheEntryW);
              goto LABEL_20;
            }
          }
        }
        FirstCacheEntryInfo.dwStructSize = 112;
        cbCacheEntryInfo = 4800;
        if ( !FindNextUrlCacheEntryW(FirstUrlCacheEntryW, &FirstCacheEntryInfo, &cbCacheEntryInfo) )
          goto LABEL_18;
      }
    }
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError == 259 )
    {
      v0 = 0;
    }
    else if ( LastError > 0 )
    {
      v0 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_20:
  LeaveCriticalSection(&CPersistUserData::s_csSiteTable);
  return v0;
}

```

## disassembly

```asm
0x180a5dc08  mov     [rsp-8+arg_0], rbx
0x180a5dc0d  mov     [rsp-8+arg_8], rdi
0x180a5dc12  push    rbp
0x180a5dc13  lea     rbp, [rsp-1210h]
0x180a5dc1b  mov     eax, 1310h
0x180a5dc20  call    _alloca_probe
0x180a5dc25  sub     rsp, rax
0x180a5dc28  mov     rax, cs:__security_cookie
0x180a5dc2f  xor     rax, rsp
0x180a5dc32  mov     [rbp+1210h+var_10], rax
0x180a5dc39  lea     rcx, ?s_csSiteTable@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a5dc40  xor     ebx, ebx
0x180a5dc42  call    cs:__imp_EnterCriticalSection
0x180a5dc49  nop     dword ptr [rax+rax+00h]
0x180a5dc4e  cmp     cs:?s_pSiteTable@CPersistUserData@@0PEAVCSiteTable@@EA, rbx; CSiteTable * CPersistUserData::s_pSiteTable
0x180a5dc55  jnz     loc_180A5DE03
0x180a5dc5b  mov     rcx, cs:g_hProcessHeap
0x180a5dc62  lea     edx, [rbx+10h]
0x180a5dc65  call    ??$HeapAlloc@$0A@@MemoryProtection@@YAPEAXPEAX_K@Z; MemoryProtection::HeapAlloc<0>(void *,unsigned __int64)
0x180a5dc6a  test    rax, rax
0x180a5dc6d  jz      loc_180A5DDF7
0x180a5dc73  mov     [rax], rbx
0x180a5dc76  lea     r8, [rsp+1310h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a5dc7b  mov     qword ptr [rax+8], 80h
0x180a5dc83  lea     rdx, [rsp+1310h+FirstCacheEntryInfo]; lpFirstCacheEntryInfo
0x180a5dc88  lea     rcx, szUrlSearchPattern; "userdata:"
0x180a5dc8f  mov     [rsp+1310h+cbCacheEntryInfo], 12C0h
0x180a5dc97  mov     [rsp+1310h+FirstCacheEntryInfo.dwStructSize], 70h ; 'p'
0x180a5dc9f  mov     cs:?s_pSiteTable@CPersistUserData@@0PEAVCSiteTable@@EA, rax; CSiteTable * CPersistUserData::s_pSiteTable
0x180a5dca6  call    cs:__imp_FindFirstUrlCacheEntryW
0x180a5dcad  nop     dword ptr [rax+rax+00h]
0x180a5dcb2  mov     rdi, rax
0x180a5dcb5  test    rax, rax
0x180a5dcb8  jnz     short loc_180A5DCEC
0x180a5dcba  call    cs:__imp_GetLastError
0x180a5dcc1  nop     dword ptr [rax+rax+00h]
0x180a5dcc6  mov     ebx, eax
0x180a5dcc8  cmp     eax, 103h
0x180a5dccd  jnz     short loc_180A5DCD6
0x180a5dccf  xor     ebx, ebx
0x180a5dcd1  jmp     loc_180A5DE03
0x180a5dcd6  test    eax, eax
0x180a5dcd8  jle     loc_180A5DE03
0x180a5dcde  movzx   ebx, ax
0x180a5dce1  or      ebx, 80070000h
0x180a5dce7  jmp     loc_180A5DE03
0x180a5dcec  lea     rcx, [rsp+1310h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180a5dcf1  mov     qword ptr [rsp+1310h+FileTime1.dwLowDateTime], rbx
0x180a5dcf6  mov     qword ptr [rsp+1310h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180a5dcfb  call    cs:__imp_GetSystemTimeAsFileTime
0x180a5dd02  nop     dword ptr [rax+rax+00h]
0x180a5dd07  cmp     [rsp+1310h+FirstCacheEntryInfo.lpszSourceUrlName], 0
0x180a5dd0d  jz      loc_180A5DDB5
0x180a5dd13  lea     rdx, [rsp+1310h+FirstCacheEntryInfo.ExpireTime]; lpFileTime2
0x180a5dd18  mov     [rsp+1310h+var_12EC], 0
0x180a5dd20  lea     rcx, [rsp+1310h+FileTime1]; lpFileTime1
0x180a5dd25  mov     [rsp+1310h+var_12E0], 0
0x180a5dd2e  call    cs:__imp_CompareFileTime
0x180a5dd35  nop     dword ptr [rax+rax+00h]
0x180a5dd3a  test    eax, eax
0x180a5dd3c  jz      short loc_180A5DD64
0x180a5dd3e  lea     rdx, [rsp+1310h+FirstCacheEntryInfo.ExpireTime]; lpFileTime2
0x180a5dd43  lea     rcx, [rsp+1310h+SystemTimeAsFileTime]; lpFileTime1
0x180a5dd48  call    cs:__imp_CompareFileTime
0x180a5dd4f  nop     dword ptr [rax+rax+00h]
0x180a5dd54  test    eax, eax
0x180a5dd56  jle     short loc_180A5DD64
0x180a5dd58  mov     rcx, [rsp+1310h+FirstCacheEntryInfo.lpszSourceUrlName]; unsigned __int16 *
0x180a5dd5d  call    ?DeleteUrlCacheEntryBugW@@YAHPEBG@Z; DeleteUrlCacheEntryBugW(ushort const *)
0x180a5dd62  jmp     short loc_180A5DDB5
0x180a5dd64  mov     rcx, [rsp+1310h+FirstCacheEntryInfo.lpszSourceUrlName]; psz1
0x180a5dd69  lea     r8, [rsp+1310h+var_12EC]; unsigned int *
0x180a5dd6e  lea     rdx, [rsp+1310h+var_12E0]; unsigned __int16 **
0x180a5dd73  call    ?GetSiteFromCacheUrl@CPersistUserData@@CAJPEBGPEAPEAGPEAK@Z; CPersistUserData::GetSiteFromCacheUrl(ushort const *,ushort * *,ulong *)
0x180a5dd78  mov     ebx, eax
0x180a5dd7a  cmp     eax, 1
0x180a5dd7d  jnz     short loc_180A5DD83
0x180a5dd7f  xor     ebx, ebx
0x180a5dd81  jmp     short loc_180A5DDB5
0x180a5dd83  test    eax, eax
0x180a5dd85  js      short loc_180A5DDE6
0x180a5dd87  mov     r8, [rsp+1310h+var_12E0]
0x180a5dd8c  xor     eax, eax
0x180a5dd8e  mov     ecx, [rsp+1310h+var_12EC]
0x180a5dd92  mov     edx, cs:?s_dwClusterSizeMinusOne@CPersistUserData@@0KA; ulong CPersistUserData::s_dwClusterSizeMinusOne
0x180a5dd98  mov     [r8+rcx*2], ax
0x180a5dd9d  mov     rcx, r8; unsigned __int16 *
0x180a5dda0  add     edx, [rsp+1310h+FirstCacheEntryInfo.dwSizeLow]
0x180a5dda4  and     edx, cs:?s_dwClusterSizeMask@CPersistUserData@@0KA; int
0x180a5ddaa  call    ?ModifySitesSpaceUsage@CPersistUserData@@CAJPEBGH@Z; CPersistUserData::ModifySitesSpaceUsage(ushort const *,int)
0x180a5ddaf  mov     ebx, eax
0x180a5ddb1  test    eax, eax
0x180a5ddb3  jnz     short loc_180A5DDE6
0x180a5ddb5  lea     r8, [rsp+1310h+cbCacheEntryInfo]; lpcbCacheEntryInfo
0x180a5ddba  mov     [rsp+1310h+FirstCacheEntryInfo.dwStructSize], 70h ; 'p'
0x180a5ddc2  lea     rdx, [rsp+1310h+FirstCacheEntryInfo]; lpNextCacheEntryInfo
0x180a5ddc7  mov     [rsp+1310h+cbCacheEntryInfo], 12C0h
0x180a5ddcf  mov     rcx, rdi; hEnumHandle
0x180a5ddd2  call    cs:__imp_FindNextUrlCacheEntryW
0x180a5ddd9  nop     dword ptr [rax+rax+00h]
0x180a5ddde  test    eax, eax
0x180a5dde0  jnz     loc_180A5DD07
0x180a5dde6  mov     rcx, rdi; hEnumHandle
0x180a5dde9  call    cs:__imp_FindCloseUrlCache
0x180a5ddf0  nop     dword ptr [rax+rax+00h]
0x180a5ddf5  jmp     short loc_180A5DE03
0x180a5ddf7  mov     cs:?s_pSiteTable@CPersistUserData@@0PEAVCSiteTable@@EA, rbx; CSiteTable * CPersistUserData::s_pSiteTable
0x180a5ddfe  mov     ebx, 8007000Eh
0x180a5de03  lea     rcx, ?s_csSiteTable@CPersistUserData@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180a5de0a  call    cs:__imp_LeaveCriticalSection
0x180a5de11  nop     dword ptr [rax+rax+00h]
0x180a5de16  mov     eax, ebx
0x180a5de18  mov     rcx, [rbp+1210h+var_10]
0x180a5de1f  xor     rcx, rsp; StackCookie
0x180a5de22  call    __security_check_cookie
0x180a5de27  lea     r11, [rsp+1310h+var_s0]
0x180a5de2f  mov     rbx, [r11+10h]
0x180a5de33  mov     rdi, [r11+18h]
0x180a5de37  mov     rsp, r11
0x180a5de3a  pop     rbp
0x180a5de3b  retn
```
