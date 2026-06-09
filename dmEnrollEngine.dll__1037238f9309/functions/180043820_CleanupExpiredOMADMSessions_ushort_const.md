# CleanupExpiredOMADMSessions(ushort const *)

- ea: `0x180043820`
- end: `0x1800439f4`
- name: `?CleanupExpiredOMADMSessions@@YAXPEBG@Z`
- size: `468`
- prototype: `void __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066f10`
- `0x18006ed20`

## callees

- `0x18002e1a0`
- `0x18002ec8c`
- `0x180043820`
- `0x18004c180`
- `0x18004c1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800438b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800439bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800439cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800439bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800439cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004389a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18004389a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043980`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043980`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800438a8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800438a8`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18004393a`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18004393a`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18004399c`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18004399c`
- `omadmapi!__imp_OmaDmCloseSession` at `0x180043992`
- `omadmapi!__imp_OmaDmCloseSession` at `0x180043992`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18004387e`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18004387e`
- `DMCmnUtils!OmaDmRegistryGetBinary` at `0x18004396e`
- `DMCmnUtils!OmaDmRegistryGetBinary` at `0x18004396e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CleanupExpiredOMADMSessions(const unsigned __int16 *a1)
{
  __int64 v1; // rbx
  __int64 i; // rbx
  unsigned int v3; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int64 v4; // [rsp+38h] [rbp-41h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v6; // [rsp+48h] [rbp-31h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-29h] BYREF
  FILETIME FileTime1; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v9; // [rsp+60h] [rbp-19h] BYREF
  FILETIME FileTime2; // [rsp+68h] [rbp-11h] BYREF
  _DWORD v11[16]; // [rsp+70h] [rbp-9h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp+37h] BYREF

  FileTime = 0;
  FileTime1 = 0;
  FileTime2 = 0;
  HIDWORD(v4) = 0;
  hMem = 0;
  SystemTime = 0;
  v3 = 0;
  v6 = 0;
  if ( (int)OmaDmEnumerateInitiationInfo(a1, 1, &hMem, &v3) >= 0 && v3 )
  {
    GetSystemTime(&SystemTime);
    if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      v4 = (unsigned __int64)FileTime;
      v9 = 1800;
      if ( (int)ULongLongMult(0x708u, 0x989680u, &v9) >= 0 && (int)ULongLongSub(v4, v9, &v4) >= 0 )
      {
        v1 = 0;
        for ( FileTime1 = (FILETIME)v4; (unsigned int)v1 < v3; v1 = (unsigned int)(v1 + 1) )
        {
          memset_0(v11, 0, sizeof(v11));
          v11[0] = 64;
          if ( (int)OmaDmGetInitiationInfo(*((_QWORD *)hMem + v1), v11) >= 0 )
          {
            v6 = 8;
            if ( (int)OmaDmRegistryGetBinary(
                        HKEY_LOCAL_MACHINE,
                        *((const unsigned __int16 **)hMem + v1),
                        L"SessionStateTimeStamp",
                        &FileTime2,
                        &v6) >= 0
              && CompareFileTime(&FileTime1, &FileTime2) > 0 )
            {
              OmaDmCloseSession(*((_QWORD *)hMem + v1));
            }
            OmaDmFreeInitiationInfo(v11);
          }
        }
      }
    }
    else
    {
      GetLastError();
    }
  }
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    LocalFree(*((HLOCAL *)hMem + i));
  LocalFree(hMem);
}

```

## disassembly

```asm
0x180043820  mov     [rsp-8+arg_8], rbx
0x180043825  mov     [rsp-8+arg_10], rdi
0x18004382a  push    rbp
0x18004382b  lea     rbp, [rsp-57h]
0x180043830  sub     rsp, 0D0h
0x180043837  mov     rax, cs:__security_cookie
0x18004383e  xor     rax, rsp
0x180043841  mov     [rbp+57h+var_10], rax
0x180043845  xor     eax, eax
0x180043847  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], 0
0x18004384f  xorps   xmm0, xmm0
0x180043852  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], 0
0x18004385a  lea     r9, [rbp+57h+var_A0]
0x18004385e  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], 0
0x180043866  lea     r8, [rbp+57h+hMem]
0x18004386a  mov     dword ptr [rbp+57h+var_98+4], eax
0x18004386d  lea     edx, [rax+1]
0x180043870  mov     [rbp+57h+hMem], rax
0x180043874  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180043878  mov     [rbp+57h+var_A0], eax
0x18004387b  mov     [rbp+57h+var_88], eax
0x18004387e  call    cs:__imp_OmaDmEnumerateInitiationInfo
0x180043884  test    eax, eax
0x180043886  js      loc_1800439AD
0x18004388c  cmp     [rbp+57h+var_A0], 0
0x180043890  jz      loc_1800439AD
0x180043896  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18004389a  call    cs:__imp_GetSystemTime
0x1800438a0  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800438a4  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1800438a8  call    cs:__imp_SystemTimeToFileTime
0x1800438ae  test    eax, eax
0x1800438b0  jnz     short loc_1800438BD
0x1800438b2  call    cs:__imp_GetLastError
0x1800438b8  jmp     loc_1800439AD
0x1800438bd  mov     eax, [rbp+57h+FileTime.dwHighDateTime]
0x1800438c0  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x1800438c4  mov     dword ptr [rbp+57h+var_98+4], eax
0x1800438c7  mov     ecx, 708h; unsigned __int64
0x1800438cc  mov     eax, [rbp+57h+FileTime.dwLowDateTime]
0x1800438cf  mov     edx, 989680h; unsigned __int64
0x1800438d4  mov     dword ptr [rbp+57h+var_98], eax
0x1800438d7  mov     [rbp+57h+var_70], rcx
0x1800438db  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800438e0  test    eax, eax
0x1800438e2  js      loc_1800439AD
0x1800438e8  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800438ec  lea     r8, [rbp+57h+var_98]; unsigned __int64 *
0x1800438f0  mov     rcx, [rbp+57h+var_98]; unsigned __int64
0x1800438f4  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800438f9  test    eax, eax
0x1800438fb  js      loc_1800439AD
0x180043901  mov     eax, dword ptr [rbp+57h+var_98+4]
0x180043904  xor     ebx, ebx
0x180043906  mov     [rbp+57h+FileTime1.dwHighDateTime], eax
0x180043909  mov     eax, dword ptr [rbp+57h+var_98]
0x18004390c  mov     [rbp+57h+FileTime1.dwLowDateTime], eax
0x18004390f  cmp     [rbp+57h+var_A0], ebx
0x180043912  jbe     loc_1800439AD
0x180043918  xor     edx, edx; Val
0x18004391a  lea     rcx, [rbp+57h+var_60]; void *
0x18004391e  lea     r8d, [rdx+40h]; Size
0x180043922  call    memset_0
0x180043927  mov     rcx, [rbp+57h+hMem]
0x18004392b  lea     rdx, [rbp+57h+var_60]
0x18004392f  mov     [rbp+57h+var_60], 40h ; '@'
0x180043936  mov     rcx, [rcx+rbx*8]
0x18004393a  call    cs:__imp_OmaDmGetInitiationInfo
0x180043940  test    eax, eax
0x180043942  js      short loc_1800439A2
0x180043944  mov     rdx, [rbp+57h+hMem]
0x180043948  lea     rax, [rbp+57h+var_88]
0x18004394c  mov     [rbp+57h+var_88], 8
0x180043953  lea     r9, [rbp+57h+FileTime2]
0x180043957  lea     r8, aSessionstateti; "SessionStateTimeStamp"
0x18004395e  mov     [rsp+0D0h+var_B0], rax
0x180043963  mov     rcx, 0FFFFFFFF80000002h
0x18004396a  mov     rdx, [rdx+rbx*8]
0x18004396e  call    cs:__imp_?OmaDmRegistryGetBinary@@YAJPEAUHKEY__@@PEBG1PEAXPEAK@Z; OmaDmRegistryGetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong *)
0x180043974  test    eax, eax
0x180043976  js      short loc_180043998
0x180043978  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x18004397c  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180043980  call    cs:__imp_CompareFileTime
0x180043986  test    eax, eax
0x180043988  jle     short loc_180043998
0x18004398a  mov     rcx, [rbp+57h+hMem]
0x18004398e  mov     rcx, [rcx+rbx*8]
0x180043992  call    cs:__imp_OmaDmCloseSession
0x180043998  lea     rcx, [rbp+57h+var_60]
0x18004399c  call    cs:__imp_OmaDmFreeInitiationInfo
0x1800439a2  inc     ebx
0x1800439a4  cmp     ebx, [rbp+57h+var_A0]
0x1800439a7  jb      loc_180043918
0x1800439ad  xor     ebx, ebx
0x1800439af  cmp     [rbp+57h+var_A0], ebx
0x1800439b2  jbe     short loc_1800439C9
0x1800439b4  mov     rcx, [rbp+57h+hMem]
0x1800439b8  mov     rcx, [rcx+rbx*8]; hMem
0x1800439bc  call    cs:__imp_LocalFree
0x1800439c2  inc     ebx
0x1800439c4  cmp     ebx, [rbp+57h+var_A0]
0x1800439c7  jb      short loc_1800439B4
0x1800439c9  mov     rcx, [rbp+57h+hMem]; hMem
0x1800439cd  call    cs:__imp_LocalFree
0x1800439d3  mov     rcx, [rbp+57h+var_10]
0x1800439d7  xor     rcx, rsp; StackCookie
0x1800439da  call    __security_check_cookie
0x1800439df  lea     r11, [rsp+0D0h+var_s0]
0x1800439e7  mov     rbx, [r11+18h]
0x1800439eb  mov     rdi, [r11+20h]
0x1800439ef  mov     rsp, r11
0x1800439f2  pop     rbp
0x1800439f3  retn
```
