# CDriverMap::GetUserModeDriverPath(HKEY__ *,ulong,ulong,ushort *,ulong,ushort *)

- ea: `0x1800460b8`
- end: `0x180046380`
- name: `?GetUserModeDriverPath@CDriverMap@@AEAAJPEAUHKEY__@@KKPEAGK1@Z`
- size: `712`
- prototype: `int(CDriverMap *__hidden this, HKEY, unsigned int, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180043f54`

## callees

- `0x180006d02`
- `0x180007014`
- `0x1800460b8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046210`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046210`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046298`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046298`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800462a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800462a5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004612a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004612a`

## string_xrefs

- `0x180046166`: `CDriverMap::GetUserModeDriverPath`
- `0x180046196`: `CDriverMap::GetUserModeDriverPath`
- `0x180046237`: `CDriverMap::GetUserModeDriverPath`
- `0x1800462d3`: `CDriverMap::GetUserModeDriverPath`
- `0x1800462f2`: `CDriverMap::GetUserModeDriverPath`
- `0x180046227`: `0x%08x RegOpenKeyEx failed`
- `0x180046289`: `ImagePath`

## pseudocode

```c
__int64 __fastcall CDriverMap::GetUserModeDriverPath(
        CDriverMap *this,
        HKEY a2,
        DWORD a3,
        __int64 a4,
        unsigned __int16 *lpName,
        unsigned int a6,
        BYTE *lpData)
{
  const WCHAR *v7; // rsi
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  const char *v11; // rsi
  FILE *v12; // rax
  int v13; // r9d
  FILE *v14; // rax
  FILE *v15; // rax
  LSTATUS v16; // eax
  BYTE *v17; // rdi
  unsigned int v18; // ebx
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-38h]
  HKEY hKey; // [rsp+40h] [rbp-18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  int v26; // [rsp+64h] [rbp+Ch]
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  v26 = HIDWORD(this);
  v7 = lpName;
  cbData = 520;
  hKey = 0;
  Type = 1;
  a6 = 260;
  v9 = RegEnumKeyExW(a2, a3, lpName, &a6, 0, 0, 0, 0);
  v10 = v9;
  if ( v9 == 259 )
    return (unsigned int)-2147024637;
  if ( v9 )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v11 = "0x%08x RegEnumKeyEx failed";
    AslLogCallPrintf(2, "CDriverMap::GetUserModeDriverPath", 1348, "0x%08x RegEnumKeyEx failed", v10);
    if ( !EnableDevInvStdErrLog )
      goto LABEL_9;
    v12 = o___acrt_iob_func_0(2u);
    v13 = 1348;
LABEL_8:
    fprintf(v12, "Error: %s, %u: ", "CDriverMap::GetUserModeDriverPath", v13);
    v14 = o___acrt_iob_func_0(2u);
    fprintf(v14, v11, v10);
    v15 = o___acrt_iob_func_0(2u);
    fprintf(v15, "\n");
LABEL_9:
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v11, v10);
    return v10;
  }
  v16 = RegOpenKeyExW(a2, v7, 0, 0x20019u, &hKey);
  v10 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0x80070000;
    v11 = "0x%08x RegOpenKeyEx failed";
    AslLogCallPrintf(2, "CDriverMap::GetUserModeDriverPath", 1362, "0x%08x RegOpenKeyEx failed", v10);
    if ( !EnableDevInvStdErrLog )
      goto LABEL_9;
    v12 = o___acrt_iob_func_0(2u);
    v13 = 1362;
    goto LABEL_8;
  }
  v17 = lpData;
  v18 = RegQueryValueExW(hKey, L"ImagePath", 0, &Type, lpData, &cbData);
  RegCloseKey(hKey);
  if ( v18 )
  {
    *(_WORD *)v17 = 0;
    LODWORD(phkResult) = v18;
    AslLogCallPrintf(
      2,
      "CDriverMap::GetUserModeDriverPath",
      1384,
      "0x%08x RegQueryValueEx failed, keyName (%ws)",
      phkResult,
      v7);
    if ( EnableDevInvStdErrLog )
    {
      v19 = o___acrt_iob_func_0(2u);
      fprintf(v19, "Warning: %s, %u: ", "CDriverMap::GetUserModeDriverPath", 1384);
      v20 = o___acrt_iob_func_0(2u);
      fprintf(v20, "0x%08x RegQueryValueEx failed, keyName (%ws)", v18, v7);
      v21 = o___acrt_iob_func_0(2u);
      fprintf(v21, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(50331648, "0x%08x RegQueryValueEx failed, keyName (%ws)", v18, v7);
  }
  else
  {
    *(_WORD *)&v17[2 * ((unsigned __int64)cbData >> 1) - 2] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800460b8  mov     r11, rsp
0x1800460bb  mov     [r11+10h], rbx
0x1800460bf  mov     [r11+18h], rsi
0x1800460c3  mov     [r11+20h], r9d
0x1800460c7  mov     [r11+8], rcx
0x1800460cb  push    rdi
0x1800460cc  sub     rsp, 50h
0x1800460d0  mov     rsi, [rsp+58h+lpName]
0x1800460d8  lea     r9, [r11+30h]; lpcchName
0x1800460dc  mov     qword ptr [r11-20h], 0
0x1800460e4  mov     eax, r8d
0x1800460e7  mov     rdi, rdx
0x1800460ea  mov     qword ptr [r11-28h], 0
0x1800460f2  mov     qword ptr [r11-30h], 0
0x1800460fa  mov     r8, rsi; lpName
0x1800460fd  mov     edx, eax; dwIndex
0x1800460ff  mov     qword ptr [r11-38h], 0
0x180046107  mov     rcx, rdi; hKey
0x18004610a  mov     [rsp+58h+cbData], 208h
0x180046112  mov     qword ptr [r11-18h], 0
0x18004611a  mov     [rsp+58h+Type], 1
0x180046122  mov     dword ptr [r11+30h], 104h
0x18004612a  call    cs:__imp_RegEnumKeyExW
0x180046130  mov     ebx, eax
0x180046132  cmp     eax, 103h
0x180046137  jnz     short loc_180046143
0x180046139  mov     ebx, 80070103h
0x18004613e  jmp     loc_18004636E
0x180046143  test    eax, eax
0x180046145  jz      loc_1800461F7
0x18004614b  jle     short loc_180046156
0x18004614d  movzx   ebx, ax
0x180046150  or      ebx, 80070000h
0x180046156  lea     rsi, a0x08xRegenumke; "0x%08x RegEnumKeyEx failed"
0x18004615d  mov     dword ptr [rsp+58h+phkResult], ebx
0x180046161  mov     edi, 2
0x180046166  lea     rdx, aCdrivermapGetu; "CDriverMap::GetUserModeDriverPath"
0x18004616d  mov     r9, rsi
0x180046170  mov     ecx, edi
0x180046172  mov     r8d, 544h
0x180046178  call    AslLogCallPrintf
0x18004617d  cmp     cs:EnableDevInvStdErrLog, 0
0x180046184  jz      short loc_1800461D4
0x180046186  mov     ecx, edi; Ix
0x180046188  call    _o___acrt_iob_func_0
0x18004618d  mov     r9d, 544h
0x180046193  mov     rcx, rax; Stream
0x180046196  lea     r8, aCdrivermapGetu; "CDriverMap::GetUserModeDriverPath"
0x18004619d  lea     rdx, Format; "Error: %s, %u: "
0x1800461a4  call    fprintf
0x1800461a9  mov     ecx, edi; Ix
0x1800461ab  call    _o___acrt_iob_func_0
0x1800461b0  mov     rcx, rax; Stream
0x1800461b3  mov     r8d, ebx
0x1800461b6  mov     rdx, rsi; Format
0x1800461b9  call    fprintf
0x1800461be  mov     ecx, edi; Ix
0x1800461c0  call    _o___acrt_iob_func_0
0x1800461c5  mov     rcx, rax; Stream
0x1800461c8  lea     rdx, asc_18011EAD8; "\n"
0x1800461cf  call    fprintf
0x1800461d4  cmp     cs:g_DeviceMapLogFunction, 0
0x1800461dc  jz      loc_18004636E
0x1800461e2  mov     r8d, ebx
0x1800461e5  mov     rdx, rsi
0x1800461e8  mov     ecx, 2000000h
0x1800461ed  call    TraceMessageCallback
0x1800461f2  jmp     loc_18004636E
0x1800461f7  lea     rax, [rsp+58h+hKey]
0x1800461fc  mov     r9d, 20019h; samDesired
0x180046202  xor     r8d, r8d; ulOptions
0x180046205  mov     [rsp+58h+phkResult], rax; phkResult
0x18004620a  mov     rdx, rsi; lpSubKey
0x18004620d  mov     rcx, rdi; hKey
0x180046210  call    cs:__imp_RegOpenKeyExW
0x180046216  mov     ebx, eax
0x180046218  test    eax, eax
0x18004621a  jz      short loc_18004626D
0x18004621c  jle     short loc_180046227
0x18004621e  movzx   ebx, ax
0x180046221  or      ebx, 80070000h
0x180046227  lea     rsi, a0x08xRegopenke; "0x%08x RegOpenKeyEx failed"
0x18004622e  mov     dword ptr [rsp+58h+phkResult], ebx
0x180046232  mov     edi, 2
0x180046237  lea     rdx, aCdrivermapGetu; "CDriverMap::GetUserModeDriverPath"
0x18004623e  mov     r9, rsi
0x180046241  mov     ecx, edi
0x180046243  mov     r8d, 552h
0x180046249  call    AslLogCallPrintf
0x18004624e  cmp     cs:EnableDevInvStdErrLog, 0
0x180046255  jz      loc_1800461D4
0x18004625b  mov     ecx, edi; Ix
0x18004625d  call    _o___acrt_iob_func_0
0x180046262  mov     r9d, 552h
0x180046268  jmp     loc_180046193
0x18004626d  mov     rdi, [rsp+58h+lpData]
0x180046275  lea     rax, [rsp+58h+cbData]
0x18004627a  mov     rcx, [rsp+58h+hKey]; hKey
0x18004627f  lea     r9, [rsp+58h+Type]; lpType
0x180046284  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180046289  lea     rdx, aImagepath; "ImagePath"
0x180046290  xor     r8d, r8d; lpReserved
0x180046293  mov     [rsp+58h+phkResult], rdi; lpData
0x180046298  call    cs:__imp_RegQueryValueExW
0x18004629e  mov     rcx, [rsp+58h+hKey]; hKey
0x1800462a3  mov     ebx, eax
0x1800462a5  call    cs:__imp_RegCloseKey
0x1800462ab  xor     eax, eax
0x1800462ad  test    ebx, ebx
0x1800462af  jz      loc_180046360
0x1800462b5  mov     [rdi], ax
0x1800462b8  lea     r9, a0x08xRegqueryv; "0x%08x RegQueryValueEx failed, keyName "...
0x1800462bf  lea     edi, [rax+2]
0x1800462c2  mov     [rsp+58h+lpcbData], rsi
0x1800462c7  mov     ecx, edi
0x1800462c9  mov     dword ptr [rsp+58h+phkResult], ebx
0x1800462cd  mov     r8d, 568h
0x1800462d3  lea     rdx, aCdrivermapGetu; "CDriverMap::GetUserModeDriverPath"
0x1800462da  call    AslLogCallPrintf
0x1800462df  cmp     cs:EnableDevInvStdErrLog, 0
0x1800462e6  jz      short loc_18004633D
0x1800462e8  mov     ecx, edi; Ix
0x1800462ea  call    _o___acrt_iob_func_0
0x1800462ef  mov     rcx, rax; Stream
0x1800462f2  lea     r8, aCdrivermapGetu; "CDriverMap::GetUserModeDriverPath"
0x1800462f9  mov     r9d, 568h
0x1800462ff  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180046306  call    fprintf
0x18004630b  mov     ecx, edi; Ix
0x18004630d  call    _o___acrt_iob_func_0
0x180046312  mov     rcx, rax; Stream
0x180046315  lea     rdx, a0x08xRegqueryv; "0x%08x RegQueryValueEx failed, keyName "...
0x18004631c  mov     r9, rsi
0x18004631f  mov     r8d, ebx
0x180046322  call    fprintf
0x180046327  mov     ecx, edi; Ix
0x180046329  call    _o___acrt_iob_func_0
0x18004632e  mov     rcx, rax; Stream
0x180046331  lea     rdx, asc_18011EAD8; "\n"
0x180046338  call    fprintf
0x18004633d  cmp     cs:g_DeviceMapLogFunction, 0
0x180046345  jz      short loc_18004636C
0x180046347  mov     r9, rsi
0x18004634a  lea     rdx, a0x08xRegqueryv; "0x%08x RegQueryValueEx failed, keyName "...
0x180046351  mov     r8d, ebx
0x180046354  mov     ecx, 3000000h
0x180046359  call    TraceMessageCallback
0x18004635e  jmp     short loc_18004636C
0x180046360  mov     ecx, [rsp+58h+cbData]
0x180046364  shr     rcx, 1
0x180046367  mov     [rdi+rcx*2-2], ax
0x18004636c  xor     ebx, ebx
0x18004636e  mov     rsi, [rsp+58h+arg_10]
0x180046373  mov     eax, ebx
0x180046375  mov     rbx, [rsp+58h+arg_8]
0x18004637a  add     rsp, 50h
0x18004637e  pop     rdi
0x18004637f  retn
```
