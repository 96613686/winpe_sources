# WriteTraceHeader(void)

- ea: `0x180008f90`
- end: `0x180009198`
- name: `?WriteTraceHeader@@YAXXZ`
- size: `520`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x180008f90`
- `0x18000ca14`
- `0x18000d840`
- `0x18000d910`
- `0x1800114b0`
- `0x1800115a4`
- `0x180011957`
- `0x180011980`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x180009008`
- `KERNEL32!GetVersionExW` at `0x180009008`
- `KERNEL32!GetSystemTime` at `0x1800090c4`
- `KERNEL32!GetSystemTime` at `0x1800090c4`
- `KERNEL32!GetComputerNameExW` at `0x180009146`
- `KERNEL32!GetComputerNameExW` at `0x180009146`
- `KERNEL32!GetLastError` at `0x18000908e`
- `KERNEL32!GetLastError` at `0x18000908e`

## pseudocode

```c
void WriteTraceHeader(void)
{
  WCHAR *szCSDVersion; // rax
  const wchar_t *v1; // rdx
  signed int LastError; // eax
  DWORD nSize; // [rsp+50h] [rbp-178h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-170h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-158h] BYREF
  WCHAR Buffer[16]; // [rsp+190h] [rbp-38h] BYREF

  memset_0(&VersionInformation, 0, 0x11Cu);
  nSize = 16;
  SystemTime = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      if ( VersionInformation.szCSDVersion[0] )
      {
        szCSDVersion = VersionInformation.szCSDVersion;
        v1 = (const wchar_t *)L" - ";
      }
      else
      {
        szCSDVersion = L" ";
        v1 = L" ";
      }
      WPP_SF_DDDSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        VersionInformation.dwMinorVersion,
        VersionInformation.dwBuildNumber,
        (__int64)v1,
        (__int64)szCSDVersion);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids,
      (unsigned int)LastError);
  }
  GetSystemTime(&SystemTime);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      SystemTime.wSecond,
      SystemTime.wMinute,
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      SystemTime.wHour,
      SystemTime.wMinute,
      SystemTime.wSecond,
      SystemTime.wMilliseconds,
      nSize);
  if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids, Buffer);
  }
}

```

## disassembly

```asm
0x180008f90  push    rdi
0x180008f92  sub     rsp, 1C0h
0x180008f99  mov     rax, cs:__security_cookie
0x180008fa0  xor     rax, rsp
0x180008fa3  mov     [rsp+1C8h+var_18], rax
0x180008fab  xor     edx, edx; Val
0x180008fad  lea     rcx, [rsp+1C8h+VersionInformation]; void *
0x180008fb2  mov     r8d, 11Ch; Size
0x180008fb8  call    memset_0
0x180008fbd  xorps   xmm0, xmm0
0x180008fc0  mov     [rsp+1C8h+nSize], 10h
0x180008fc8  movups  xmmword ptr [rsp+1C8h+SystemTime.wYear], xmm0
0x180008fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fd4  lea     rdi, WPP_GLOBAL_Control
0x180008fdb  cmp     rcx, rdi
0x180008fde  jz      short loc_180008FFB
0x180008fe0  test    byte ptr [rcx+1Ch], 8
0x180008fe4  jz      short loc_180008FFB
0x180008fe6  mov     rcx, [rcx+10h]
0x180008fea  lea     r8, WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids
0x180008ff1  mov     edx, 0Ah
0x180008ff6  call    WPP_SF_
0x180008ffb  lea     rcx, [rsp+1C8h+VersionInformation]; lpVersionInformation
0x180009000  mov     [rsp+1C8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180009008  call    cs:__imp_GetVersionExW
0x18000900e  test    eax, eax
0x180009010  jz      short loc_18000907C
0x180009012  mov     rcx, cs:WPP_GLOBAL_Control
0x180009019  cmp     rcx, rdi
0x18000901c  jz      loc_1800090BF
0x180009022  test    byte ptr [rcx+1Ch], 8
0x180009026  jz      loc_1800090BF
0x18000902c  cmp     [rsp+1C8h+VersionInformation.szCSDVersion], 0
0x180009035  jz      short loc_180009048
0x180009037  lea     rax, [rsp+1C8h+VersionInformation.szCSDVersion]
0x18000903f  lea     rdx, asc_180016048; " - "
0x180009046  jmp     short loc_180009052
0x180009048  lea     rax, asc_180016044; " "
0x18000904f  mov     rdx, rax
0x180009052  mov     r9d, [rsp+1C8h+VersionInformation.dwMajorVersion]
0x180009057  mov     rcx, [rcx+10h]; LoggerHandle
0x18000905b  mov     [rsp+1C8h+var_190], rax; __int64
0x180009060  mov     eax, [rsp+1C8h+VersionInformation.dwBuildNumber]
0x180009064  mov     [rsp+1C8h+var_198], rdx; __int64
0x180009069  mov     dword ptr [rsp+1C8h+var_1A0], eax; char
0x18000906d  mov     eax, [rsp+1C8h+VersionInformation.dwMinorVersion]
0x180009071  mov     dword ptr [rsp+1C8h+var_1A8], eax; char
0x180009075  call    WPP_SF_DDDSS
0x18000907a  jmp     short loc_1800090BF
0x18000907c  mov     rax, cs:WPP_GLOBAL_Control
0x180009083  cmp     rax, rdi
0x180009086  jz      short loc_1800090BF
0x180009088  test    byte ptr [rax+1Ch], 2
0x18000908c  jz      short loc_1800090BF
0x18000908e  call    cs:__imp_GetLastError
0x180009094  test    eax, eax
0x180009096  jle     short loc_1800090A0
0x180009098  movzx   eax, ax
0x18000909b  or      eax, 80070000h
0x1800090a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a7  lea     r8, WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids
0x1800090ae  mov     edx, 0Ch
0x1800090b3  mov     r9d, eax
0x1800090b6  mov     rcx, [rcx+10h]
0x1800090ba  call    WPP_SF_d
0x1800090bf  lea     rcx, [rsp+1C8h+SystemTime]; lpSystemTime
0x1800090c4  call    cs:__imp_GetSystemTime
0x1800090ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090d1  cmp     rcx, rdi
0x1800090d4  jz      short loc_180009137
0x1800090d6  test    byte ptr [rcx+1Ch], 8
0x1800090da  jz      short loc_180009137
0x1800090dc  movzx   eax, [rsp+1C8h+SystemTime.wMilliseconds]
0x1800090e1  movzx   edx, [rsp+1C8h+SystemTime.wSecond]
0x1800090e6  movzx   r8d, [rsp+1C8h+SystemTime.wMinute]
0x1800090ec  movzx   r10d, [rsp+1C8h+SystemTime.wHour]
0x1800090f2  movzx   r11d, [rsp+1C8h+SystemTime.wDay]
0x1800090f8  movzx   r9d, [rsp+1C8h+SystemTime.wYear]
0x1800090fe  mov     rcx, [rcx+10h]
0x180009102  mov     [rsp+1C8h+var_180], eax
0x180009106  mov     [rsp+1C8h+var_188], edx
0x18000910a  mov     dword ptr [rsp+1C8h+var_190], r8d
0x18000910f  mov     dword ptr [rsp+1C8h+var_198], r10d
0x180009114  mov     dword ptr [rsp+1C8h+var_1A0], r11d
0x180009119  mov     [rsp+1C8h+arg_0], rbx
0x180009121  movzx   ebx, [rsp+1C8h+SystemTime.wMonth]
0x180009126  mov     dword ptr [rsp+1C8h+var_1A8], ebx
0x18000912a  call    WPP_SF_ddddddd
0x18000912f  mov     rbx, [rsp+1C8h+arg_0]
0x180009137  lea     r8, [rsp+1C8h+nSize]; nSize
0x18000913c  xor     ecx, ecx; NameType
0x18000913e  lea     rdx, [rsp+1C8h+Buffer]; lpBuffer
0x180009146  call    cs:__imp_GetComputerNameExW
0x18000914c  test    eax, eax
0x18000914e  jz      short loc_18000917F
0x180009150  mov     rcx, cs:WPP_GLOBAL_Control
0x180009157  cmp     rcx, rdi
0x18000915a  jz      short loc_18000917F
0x18000915c  test    byte ptr [rcx+1Ch], 8
0x180009160  jz      short loc_18000917F
0x180009162  mov     rcx, [rcx+10h]
0x180009166  lea     r9, [rsp+1C8h+Buffer]
0x18000916e  mov     edx, 0Eh
0x180009173  lea     r8, WPP_4fe620234e113e3bfbc70fc8e9003796_Traceguids
0x18000917a  call    WPP_SF_S
0x18000917f  mov     rcx, [rsp+1C8h+var_18]
0x180009187  xor     rcx, rsp; StackCookie
0x18000918a  call    __security_check_cookie
0x18000918f  add     rsp, 1C0h
0x180009196  pop     rdi
0x180009197  retn
```
