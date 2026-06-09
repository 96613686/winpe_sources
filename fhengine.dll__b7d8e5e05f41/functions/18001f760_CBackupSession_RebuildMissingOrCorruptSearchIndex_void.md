# CBackupSession::RebuildMissingOrCorruptSearchIndex(void)

- ea: `0x18001f760`
- end: `0x18001f924`
- name: `?RebuildMissingOrCorruptSearchIndex@CBackupSession@@AEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001fee4`

## callees

- `0x180007818`
- `0x1800122d8`
- `0x18001f760`
- `0x18001f92c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18001f7b9`
- `ADVAPI32!RegGetValueW` at `0x18001f7b9`
- `ADVAPI32!RegSetKeyValueW` at `0x18001f8bd`
- `ADVAPI32!RegSetKeyValueW` at `0x18001f8bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001f81e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001f832`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001f81e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001f832`

## pseudocode

```c
__int64 __fastcall CBackupSession::RebuildMissingOrCorruptSearchIndex(CBackupSession *this)
{
  LSTATUS ValueW; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  int v5; // edx
  __int64 v6; // rcx
  LSTATUS v7; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+28h] BYREF
  DWORD v11; // [rsp+80h] [rbp+30h] BYREF
  struct _FILETIME v12; // [rsp+88h] [rbp+38h] BYREF

  Data = 0;
  v11 = 4;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
             L"SearchRebuildRequired",
             0x10u,
             0,
             &Data,
             &v11);
  v3 = ValueW;
  if ( ValueW == 2 )
    return 0;
  if ( ValueW )
  {
    if ( ValueW > 0 )
      v3 = (unsigned __int16)ValueW | 0x80070000;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 428;
LABEL_23:
      WPP_SF_SSd(
        v4[2],
        v5,
        (unsigned int)&WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
        (__int64)L"SearchRebuildRequired",
        v3);
    }
  }
  else
  {
    v3 = 0;
    if ( !Data )
      return v3;
    SystemTimeAsFileTime = 0;
    v12 = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v3 = CBackupSession::RebuildSearchIndex(this);
    GetSystemTimeAsFileTime(&v12);
    v6 = *(_QWORD *)&v12 - *(_QWORD *)&SystemTimeAsFileTime;
    if ( (__int64)(*(_QWORD *)&v12 - *(_QWORD *)&SystemTimeAsFileTime) <= 0 )
      v6 = 0;
    *((_QWORD *)this + 104) += v6;
    if ( (v3 & 0x80000000) == 0 )
    {
      Data = 0;
      v7 = RegSetKeyValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
             L"SearchRebuildRequired",
             4u,
             &Data,
             4u);
      if ( v7 )
      {
        v3 = v7 > 0 ? (unsigned __int16)v7 | 0x80070000 : v7;
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 430;
          goto LABEL_23;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 429, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids, v3);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18001f760  mov     r11, rsp
0x18001f763  mov     [r11+8], rbx
0x18001f767  push    rbp
0x18001f768  push    rdi
0x18001f769  push    r15
0x18001f76b  mov     rbp, rsp
0x18001f76e  sub     rsp, 50h
0x18001f772  lea     rax, [rbp+arg_10]
0x18001f776  mov     [rbp+Data], 0
0x18001f77d  mov     [r11-38h], rax
0x18001f781  lea     r15, aSearchrebuildr; "SearchRebuildRequired"
0x18001f788  lea     rax, [rbp+Data]
0x18001f78c  mov     [rbp+arg_10], 4
0x18001f793  mov     rdi, rcx
0x18001f796  mov     [r11-40h], rax
0x18001f79a  mov     r9d, 10h; dwFlags
0x18001f7a0  mov     qword ptr [r11-48h], 0
0x18001f7a8  mov     r8, r15; lpValue
0x18001f7ab  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f7b2  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18001f7b9  call    cs:__imp_RegGetValueW
0x18001f7bf  mov     ebx, eax
0x18001f7c1  cmp     eax, 2
0x18001f7c4  jnz     short loc_18001F7CD
0x18001f7c6  xor     ebx, ebx
0x18001f7c8  jmp     loc_18001F914
0x18001f7cd  test    eax, eax
0x18001f7cf  jz      short loc_18001F807
0x18001f7d1  jle     short loc_18001F7DC
0x18001f7d3  movzx   ebx, ax
0x18001f7d6  or      ebx, 80070000h
0x18001f7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7e3  lea     rax, WPP_GLOBAL_Control
0x18001f7ea  cmp     rcx, rax
0x18001f7ed  jz      loc_18001F914
0x18001f7f3  test    byte ptr [rcx+1Ch], 1
0x18001f7f7  jz      loc_18001F914
0x18001f7fd  mov     edx, 1ACh
0x18001f802  jmp     loc_18001F8F4
0x18001f807  xor     ebx, ebx
0x18001f809  cmp     [rbp+Data], ebx
0x18001f80c  jz      loc_18001F914
0x18001f812  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001f816  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rbx
0x18001f81a  mov     qword ptr [rbp+arg_18.dwLowDateTime], rbx
0x18001f81e  call    cs:__imp_GetSystemTimeAsFileTime
0x18001f824  mov     rcx, rdi; this
0x18001f827  call    ?RebuildSearchIndex@CBackupSession@@AEAAJXZ; CBackupSession::RebuildSearchIndex(void)
0x18001f82c  lea     rcx, [rbp+arg_18]; lpSystemTimeAsFileTime
0x18001f830  mov     ebx, eax
0x18001f832  call    cs:__imp_GetSystemTimeAsFileTime
0x18001f838  mov     rcx, qword ptr [rbp+arg_18.dwLowDateTime]
0x18001f83c  xor     edx, edx
0x18001f83e  sub     rcx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001f842  test    rcx, rcx
0x18001f845  cmovle  rcx, rdx
0x18001f849  add     [rdi+340h], rcx
0x18001f850  test    ebx, ebx
0x18001f852  jns     short loc_18001F892
0x18001f854  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f85b  lea     rax, WPP_GLOBAL_Control
0x18001f862  cmp     rcx, rax
0x18001f865  jz      loc_18001F914
0x18001f86b  test    byte ptr [rcx+1Ch], 1
0x18001f86f  jz      loc_18001F914
0x18001f875  mov     rcx, [rcx+10h]
0x18001f879  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001f880  mov     edx, 1ADh
0x18001f885  mov     r9d, ebx
0x18001f888  call    WPP_SF_d
0x18001f88d  jmp     loc_18001F914
0x18001f892  mov     [rbp+Data], edx
0x18001f895  lea     rax, [rbp+Data]
0x18001f899  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f8a0  mov     [rsp+50h+cbData], 4; cbData
0x18001f8a8  mov     r9d, 4; dwType
0x18001f8ae  mov     [rsp+50h+lpData], rax; lpData
0x18001f8b3  mov     r8, r15; lpValueName
0x18001f8b6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001f8bd  call    cs:__imp_RegSetKeyValueW
0x18001f8c3  test    eax, eax
0x18001f8c5  jz      short loc_18001F914
0x18001f8c7  jg      short loc_18001F8CD
0x18001f8c9  mov     ebx, eax
0x18001f8cb  jmp     short loc_18001F8D6
0x18001f8cd  movzx   ebx, ax
0x18001f8d0  or      ebx, 80070000h
0x18001f8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f8dd  lea     rax, WPP_GLOBAL_Control
0x18001f8e4  cmp     rcx, rax
0x18001f8e7  jz      short loc_18001F914
0x18001f8e9  test    byte ptr [rcx+1Ch], 1
0x18001f8ed  jz      short loc_18001F914
0x18001f8ef  mov     edx, 1AEh
0x18001f8f4  mov     rcx, [rcx+10h]
0x18001f8f8  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001f8ff  mov     [rsp+50h+cbData], ebx
0x18001f903  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x18001f90a  mov     [rsp+50h+lpData], r15
0x18001f90f  call    WPP_SF_SSd
0x18001f914  mov     eax, ebx
0x18001f916  mov     rbx, [rsp+50h+arg_0]
0x18001f91b  add     rsp, 50h
0x18001f91f  pop     r15
0x18001f921  pop     rdi
0x18001f922  pop     rbp
0x18001f923  retn
```
