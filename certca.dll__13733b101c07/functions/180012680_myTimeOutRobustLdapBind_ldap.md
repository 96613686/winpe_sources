# myTimeOutRobustLdapBind(ldap * *)

- ea: `0x180012680`
- end: `0x1800127a1`
- name: `?myTimeOutRobustLdapBind@@YAJPEAPEAUldap@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct ldap **)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002a668`
- `0x18002bbb8`
- `0x18002bd08`
- `0x18002c028`
- `0x18002c24c`
- `0x18002c6a4`
- `0x18002cb60`

## callees

- `0x1800062d0`
- `0x180008400`
- `0x180008610`
- `0x18000ac20`
- `0x180012680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001278e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001278e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800126c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012777`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800126c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012777`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800126e2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800126e2`

## pseudocode

```c
__int64 __fastcall myTimeOutRobustLdapBind(struct ldap **a1)
{
  int DoesDSExist; // eax
  unsigned int v4; // ebx
  unsigned int v5; // edx
  int v6; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  if ( !g_fOidURL )
    return 2147943514LL;
  EnterCriticalSection(&g_csOidURL);
  if ( g_fFailedTime == 1 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    *(_QWORD *)&g_ftOidTime += 50000000LL;
    if ( CompareFileTime(&SystemTimeAsFileTime, &g_ftOidTime) < 0 )
    {
      *(_QWORD *)&g_ftOidTime -= 50000000LL;
      DoesDSExist = -2147023541;
      v4 = -2147023541;
      v5 = 5374774;
LABEL_9:
      CSPrintErrorLineFileData2(0, v5, DoesDSExist, -2147023541);
      goto LABEL_12;
    }
    g_fFailedTime = 0;
  }
  DoesDSExist = myDoesDSExist(1);
  v4 = DoesDSExist;
  if ( DoesDSExist )
  {
    v5 = 6095670;
    goto LABEL_9;
  }
  v6 = myRobustLdapBindEx(0, (const unsigned __int16 *)8, (const unsigned __int16 *)2, 0, a1, 0);
  v4 = v6;
  if ( v6 )
  {
    CSPrintErrorLineFile(0x660336u, v6);
LABEL_12:
    if ( !g_fFailedTime )
    {
      GetSystemTimeAsFileTime(&g_ftOidTime);
      g_fFailedTime = 1;
    }
  }
  LeaveCriticalSection(&g_csOidURL);
  return v4;
}

```

## disassembly

```asm
0x180012680  mov     [rsp+arg_0], rbx
0x180012685  push    rdi
0x180012686  sub     rsp, 30h
0x18001268a  cmp     cs:?g_fOidURL@@3HA, 0; int g_fOidURL
0x180012691  mov     rdi, rcx
0x180012694  mov     qword ptr [rsp+38h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001269d  jnz     short loc_1800126A9
0x18001269f  mov     eax, 8007045Ah
0x1800126a4  jmp     loc_180012796
0x1800126a9  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800126b0  call    cs:__imp_EnterCriticalSection
0x1800126b6  cmp     cs:?g_fFailedTime@@3HA, 1; int g_fFailedTime
0x1800126bd  jnz     short loc_18001270E
0x1800126bf  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800126c4  call    cs:__imp_GetSystemTimeAsFileTime
0x1800126ca  mov     ebx, 2FAF080h
0x1800126cf  lea     rdx, ?g_ftOidTime@@3T_ULARGE_INTEGER@@A; lpFileTime2
0x1800126d6  add     qword ptr cs:?g_ftOidTime@@3T_ULARGE_INTEGER@@A.dwLowDateTime, rbx; _ULARGE_INTEGER g_ftOidTime ...
0x1800126dd  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x1800126e2  call    cs:__imp_CompareFileTime
0x1800126e8  test    eax, eax
0x1800126ea  jns     short loc_180012704
0x1800126ec  sub     qword ptr cs:?g_ftOidTime@@3T_ULARGE_INTEGER@@A.dwLowDateTime, rbx; _ULARGE_INTEGER g_ftOidTime ...
0x1800126f3  mov     eax, 8007054Bh
0x1800126f8  mov     ebx, eax
0x1800126fa  mov     r9d, eax
0x1800126fd  mov     edx, 520336h
0x180012702  jmp     short loc_180012729
0x180012704  mov     cs:?g_fFailedTime@@3HA, 0; int g_fFailedTime
0x18001270e  mov     ecx, 1; int
0x180012713  call    ?myDoesDSExist@@YAJH@Z; myDoesDSExist(int)
0x180012718  mov     ebx, eax
0x18001271a  test    eax, eax
0x18001271c  jz      short loc_180012735
0x18001271e  mov     r9d, 8007054Bh; int
0x180012724  mov     edx, 5D0336h; unsigned int
0x180012729  mov     r8d, eax; int
0x18001272c  xor     ecx, ecx; unsigned __int16 *
0x18001272e  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180012733  jmp     short loc_180012767
0x180012735  xor     r9d, r9d
0x180012738  mov     [rsp+38h+var_10], 0
0x180012741  xor     ecx, ecx
0x180012743  mov     [rsp+38h+var_18], rdi
0x180012748  lea     edx, [r9+8]
0x18001274c  lea     r8d, [r9+2]
0x180012750  call    myRobustLdapBindEx
0x180012755  mov     ebx, eax
0x180012757  test    eax, eax
0x180012759  jz      short loc_180012787
0x18001275b  mov     edx, eax; int
0x18001275d  mov     ecx, 660336h; unsigned int
0x180012762  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180012767  cmp     cs:?g_fFailedTime@@3HA, 0; int g_fFailedTime
0x18001276e  jnz     short loc_180012787
0x180012770  lea     rcx, ?g_ftOidTime@@3T_ULARGE_INTEGER@@A; lpSystemTimeAsFileTime
0x180012777  call    cs:__imp_GetSystemTimeAsFileTime
0x18001277d  mov     cs:?g_fFailedTime@@3HA, 1; int g_fFailedTime
0x180012787  lea     rcx, ?g_csOidURL@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001278e  call    cs:__imp_LeaveCriticalSection
0x180012794  mov     eax, ebx
0x180012796  mov     rbx, [rsp+38h+arg_0]
0x18001279b  add     rsp, 30h
0x18001279f  pop     rdi
0x1800127a0  retn
```
