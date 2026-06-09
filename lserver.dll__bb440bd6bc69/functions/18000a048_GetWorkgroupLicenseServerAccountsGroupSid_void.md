# GetWorkgroupLicenseServerAccountsGroupSid(void * *)

- ea: `0x18000a048`
- end: `0x18000a2ac`
- name: `?GetWorkgroupLicenseServerAccountsGroupSid@@YAJPEAPEAX@Z`
- size: `612`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x18000a50c`

## callees

- `0x180006cbc`
- `0x180009b10`
- `0x18000a048`
- `0x18000a2d8`
- `0x18001ae3c`
- `0x18001aea4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a275`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a289`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a275`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a289`
- `ADVAPI32!RegGetValueW` at `0x18000a094`
- `ADVAPI32!RegGetValueW` at `0x18000a171`
- `ADVAPI32!RegGetValueW` at `0x18000a094`
- `ADVAPI32!RegGetValueW` at `0x18000a171`

## string_xrefs

- `0x18000a086`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18000a163`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18000a0d5`: `GetWorkgroupLicenseServerAccountsGroupSid`
- `0x18000a124`: `GetWorkgroupLicenseServerAccountsGroupSid`
- `0x18000a1a7`: `GetWorkgroupLicenseServerAccountsGroupSid`
- `0x18000a203`: `GetWorkgroupLicenseServerAccountsGroupSid`
- `0x18000a24c`: `GetWorkgroupLicenseServerAccountsGroupSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetWorkgroupLicenseServerAccountsGroupSid(void **a1)
{
  int v2; // edi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v4; // rcx
  char v5; // bl
  unsigned __int16 *v6; // rbx
  LSTATUS v7; // eax
  char v8; // si
  int SidForAccount; // eax
  void *v10; // rax
  DWORD pcbData; // [rsp+80h] [rbp+40h] BYREF
  enum _SID_NAME_USE v13; // [rsp+88h] [rbp+48h] BYREF
  void *v14; // [rsp+90h] [rbp+50h] BYREF
  PVOID pvData; // [rsp+98h] [rbp+58h] BYREF

  *a1 = 0;
  v2 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
             L"WorkgroupLicenseServerAccountsGroup",
             2u,
             0,
             0,
             &pcbData);
  v5 = ValueW;
  if ( ValueW )
  {
    v2 = HResultFromWin32Error(ValueW);
    v4 = (const unsigned __int16 *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"GetWorkgroupLicenseServerAccountsGroupSid",
        v5);
  }
  v6 = 0;
  pvData = 0;
  if ( v2 >= 0 )
  {
    if ( (unsigned __int8)ATL::CAutoVectorPtr<unsigned char>::Allocate(&pvData, pcbData) )
    {
      v6 = (unsigned __int16 *)pvData;
      v7 = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
             L"WorkgroupLicenseServerAccountsGroup",
             2u,
             0,
             pvData,
             &pcbData);
      v8 = v7;
      if ( v7 )
      {
        v2 = HResultFromWin32Error(v7);
        v4 = (const unsigned __int16 *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
            (unsigned int)L"GetWorkgroupLicenseServerAccountsGroupSid",
            v8);
      }
    }
    else
    {
      v2 = -2147024882;
      v4 = (const unsigned __int16 *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
          L"GetWorkgroupLicenseServerAccountsGroupSid");
      v6 = (unsigned __int16 *)pvData;
    }
  }
  v13 = SidTypeUnknown;
  v14 = 0;
  if ( v2 >= 0 )
  {
    SidForAccount = GetSidForAccount(v4, v6, &v13, &v14);
    v2 = SidForAccount;
    if ( SidForAccount >= 0 )
    {
      if ( ((v13 - 2) & 0xFFFFFFFD) != 0 )
      {
        v2 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
            (unsigned int)L"GetWorkgroupLicenseServerAccountsGroupSid",
            v13);
      }
      else
      {
        v10 = v14;
        v14 = 0;
        *a1 = v10;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)&WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
        (unsigned int)L"GetWorkgroupLicenseServerAccountsGroupSid",
        SidForAccount);
    }
  }
  operator delete[](v14);
  v14 = 0;
  operator delete[](v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000a048  push    rbp
0x18000a04a  push    rbx
0x18000a04b  push    rsi
0x18000a04c  push    rdi
0x18000a04d  push    r12
0x18000a04f  push    r13
0x18000a051  push    r14
0x18000a053  mov     rbp, rsp
0x18000a056  sub     rsp, 40h
0x18000a05a  mov     r14, rcx
0x18000a05d  and     qword ptr [rcx], 0
0x18000a061  xor     edi, edi
0x18000a063  and     [rbp+arg_0], edi
0x18000a066  lea     rax, [rbp+arg_0]
0x18000a06a  mov     [rsp+40h+pcbData], rax; pcbData
0x18000a06f  and     [rsp+40h+pvData], rdi
0x18000a074  and     [rsp+40h+pdwType], rdi
0x18000a079  lea     esi, [rdi+2]
0x18000a07c  mov     r9d, esi; dwFlags
0x18000a07f  lea     r8, Value; "WorkgroupLicenseServerAccountsGroup"
0x18000a086  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18000a08d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a094  call    cs:__imp_RegGetValueW
0x18000a09b  nop     dword ptr [rax+rax+00h]
0x18000a0a0  mov     ebx, eax
0x18000a0a2  mov     r12d, 1000h
0x18000a0a8  lea     r13, WPP_GLOBAL_Control
0x18000a0af  test    eax, eax
0x18000a0b1  jz      short loc_18000A0EC
0x18000a0b3  mov     ecx, eax; unsigned int
0x18000a0b5  call    ?HResultFromWin32Error@@YAJK@Z; HResultFromWin32Error(ulong)
0x18000a0ba  mov     edi, eax
0x18000a0bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0c3  cmp     rcx, r13
0x18000a0c6  jz      short loc_18000A0EC
0x18000a0c8  test    [rcx+1Ch], r12d
0x18000a0cc  jz      short loc_18000A0EC
0x18000a0ce  lea     edx, [rsi+0Fh]
0x18000a0d1  mov     dword ptr [rsp+40h+pdwType], ebx; pdwType
0x18000a0d5  lea     r9, aGetworkgroupli; "GetWorkgroupLicenseServerAccountsGroupS"...
0x18000a0dc  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a0e3  mov     rcx, [rcx+10h]
0x18000a0e7  call    WPP_SF_SD
0x18000a0ec  xor     ebx, ebx
0x18000a0ee  mov     [rbp+arg_18], rbx
0x18000a0f2  test    edi, edi
0x18000a0f4  js      loc_18000A1BE
0x18000a0fa  mov     edx, [rbp+arg_0]
0x18000a0fd  lea     rcx, [rbp+arg_18]
0x18000a101  call    ?Allocate@?$CAutoVectorPtr@E@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<uchar>::Allocate(unsigned __int64)
0x18000a106  test    al, al
0x18000a108  jnz     short loc_18000A141
0x18000a10a  mov     edi, 8007000Eh
0x18000a10f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a116  cmp     rcx, r13
0x18000a119  jz      short loc_18000A13B
0x18000a11b  test    [rcx+1Ch], r12d
0x18000a11f  jz      short loc_18000A13B
0x18000a121  lea     edx, [rbx+12h]
0x18000a124  lea     r9, aGetworkgroupli; "GetWorkgroupLicenseServerAccountsGroupS"...
0x18000a12b  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a132  mov     rcx, [rcx+10h]
0x18000a136  call    WPP_SF_S
0x18000a13b  mov     rbx, [rbp+arg_18]
0x18000a13f  jmp     short loc_18000A1BE
0x18000a141  lea     rax, [rbp+arg_0]
0x18000a145  mov     [rsp+40h+pcbData], rax; pcbData
0x18000a14a  mov     rbx, [rbp+arg_18]
0x18000a14e  mov     [rsp+40h+pvData], rbx; pvData
0x18000a153  and     [rsp+40h+pdwType], 0
0x18000a159  mov     r9d, esi; dwFlags
0x18000a15c  lea     r8, Value; "WorkgroupLicenseServerAccountsGroup"
0x18000a163  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18000a16a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a171  call    cs:__imp_RegGetValueW
0x18000a178  nop     dword ptr [rax+rax+00h]
0x18000a17d  mov     esi, eax
0x18000a17f  test    eax, eax
0x18000a181  jz      short loc_18000A1BE
0x18000a183  mov     ecx, eax; unsigned int
0x18000a185  call    ?HResultFromWin32Error@@YAJK@Z; HResultFromWin32Error(ulong)
0x18000a18a  mov     edi, eax
0x18000a18c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a193  cmp     rcx, r13
0x18000a196  jz      short loc_18000A1BE
0x18000a198  test    [rcx+1Ch], r12d
0x18000a19c  jz      short loc_18000A1BE
0x18000a19e  mov     edx, 13h
0x18000a1a3  mov     dword ptr [rsp+40h+pdwType], esi
0x18000a1a7  lea     r9, aGetworkgroupli; "GetWorkgroupLicenseServerAccountsGroupS"...
0x18000a1ae  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a1b5  mov     rcx, [rcx+10h]
0x18000a1b9  call    WPP_SF_SD
0x18000a1be  mov     [rbp+arg_8], 8
0x18000a1c5  and     [rbp+arg_10], 0
0x18000a1ca  test    edi, edi
0x18000a1cc  js      loc_18000A271
0x18000a1d2  lea     r9, [rbp+arg_10]; void **
0x18000a1d6  lea     r8, [rbp+arg_8]; enum _SID_NAME_USE *
0x18000a1da  mov     rdx, rbx; unsigned __int16 *
0x18000a1dd  call    ?GetSidForAccount@@YAJPEBG0PEAW4_SID_NAME_USE@@PEAPEAX@Z; GetSidForAccount(ushort const *,ushort const *,_SID_NAME_USE *,void * *)
0x18000a1e2  mov     edi, eax
0x18000a1e4  test    eax, eax
0x18000a1e6  jns     short loc_18000A21C
0x18000a1e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1ef  cmp     rcx, r13
0x18000a1f2  jz      short loc_18000A271
0x18000a1f4  test    [rcx+1Ch], r12d
0x18000a1f8  jz      short loc_18000A271
0x18000a1fa  mov     edx, 14h
0x18000a1ff  mov     dword ptr [rsp+40h+pdwType], eax
0x18000a203  lea     r9, aGetworkgroupli; "GetWorkgroupLicenseServerAccountsGroupS"...
0x18000a20a  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a211  mov     rcx, [rcx+10h]
0x18000a215  call    WPP_SF_SD
0x18000a21a  jmp     short loc_18000A271
0x18000a21c  mov     r8d, [rbp+arg_8]
0x18000a220  lea     eax, [r8-2]
0x18000a224  test    eax, 0FFFFFFFDh
0x18000a229  jz      short loc_18000A265
0x18000a22b  mov     edi, 8000FFFFh
0x18000a230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a237  cmp     rcx, r13
0x18000a23a  jz      short loc_18000A271
0x18000a23c  test    [rcx+1Ch], r12d
0x18000a240  jz      short loc_18000A271
0x18000a242  mov     edx, 15h
0x18000a247  mov     dword ptr [rsp+40h+pdwType], r8d
0x18000a24c  lea     r9, aGetworkgroupli; "GetWorkgroupLicenseServerAccountsGroupS"...
0x18000a253  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000a25a  mov     rcx, [rcx+10h]
0x18000a25e  call    WPP_SF_SD
0x18000a263  jmp     short loc_18000A271
0x18000a265  mov     rax, [rbp+arg_10]
0x18000a269  and     [rbp+arg_10], 0
0x18000a26e  mov     [r14], rax
0x18000a271  mov     rcx, [rbp+arg_10]
0x18000a275  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a27c  nop     dword ptr [rax+rax+00h]
0x18000a281  and     [rbp+arg_10], 0
0x18000a286  mov     rcx, rbx
0x18000a289  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a290  nop     dword ptr [rax+rax+00h]
0x18000a295  and     [rbp+arg_18], 0
0x18000a29a  mov     eax, edi
0x18000a29c  add     rsp, 40h
0x18000a2a0  pop     r14
0x18000a2a2  pop     r13
0x18000a2a4  pop     r12
0x18000a2a6  pop     rdi
0x18000a2a7  pop     rsi
0x18000a2a8  pop     rbx
0x18000a2a9  pop     rbp
0x18000a2aa  retn
```
