# StartTracingSession(void)

- ea: `0x180010ed4`
- end: `0x18001141d`
- name: `?StartTracingSession@@YAXXZ`
- size: `1353`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000bec0`

## callees

- `0x180008580`
- `0x180010ed4`
- `0x180011424`
- `0x180011980`

## import_xrefs

- `ADVAPI32!ControlTraceW` at `0x1800113b5`
- `ADVAPI32!ControlTraceW` at `0x1800113b5`
- `ADVAPI32!EnableTrace` at `0x180011387`
- `ADVAPI32!EnableTrace` at `0x180011387`
- `ADVAPI32!StartTraceW` at `0x18001134b`
- `ADVAPI32!StartTraceW` at `0x18001134b`
- `ADVAPI32!RegQueryValueExW` at `0x180011042`
- `ADVAPI32!RegQueryValueExW` at `0x180011083`
- `ADVAPI32!RegQueryValueExW` at `0x1800110ce`
- `ADVAPI32!RegQueryValueExW` at `0x180011119`
- `ADVAPI32!RegQueryValueExW` at `0x18001115d`
- `ADVAPI32!RegQueryValueExW` at `0x180011042`
- `ADVAPI32!RegQueryValueExW` at `0x180011083`
- `ADVAPI32!RegQueryValueExW` at `0x1800110ce`
- `ADVAPI32!RegQueryValueExW` at `0x180011119`
- `ADVAPI32!RegQueryValueExW` at `0x18001115d`
- `ADVAPI32!RegCloseKey` at `0x1800113c5`
- `ADVAPI32!RegCloseKey` at `0x1800113c5`
- `ADVAPI32!RegOpenKeyExW` at `0x180011000`
- `ADVAPI32!RegOpenKeyExW` at `0x180011000`
- `KERNEL32!LocalFree` at `0x1800113d8`
- `KERNEL32!LocalFree` at `0x1800113e6`
- `KERNEL32!LocalFree` at `0x1800113f4`
- `KERNEL32!LocalFree` at `0x1800113d8`
- `KERNEL32!LocalFree` at `0x1800113e6`
- `KERNEL32!LocalFree` at `0x1800113f4`
- `KERNEL32!CloseHandle` at `0x180011322`
- `KERNEL32!CloseHandle` at `0x180011322`
- `KERNEL32!SetFileInformationByHandle` at `0x180011319`
- `KERNEL32!SetFileInformationByHandle` at `0x180011319`
- `KERNEL32!CreateFileW` at `0x1800112cf`
- `KERNEL32!CreateFileW` at `0x1800112cf`
- `KERNEL32!LocalAlloc` at `0x180011185`
- `KERNEL32!LocalAlloc` at `0x1800111ee`
- `KERNEL32!LocalAlloc` at `0x180011185`
- `KERNEL32!LocalAlloc` at `0x1800111ee`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800111a7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800111d0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011210`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800111a7`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800111d0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180011210`
- `KERNEL32!CreateDirectoryW` at `0x1800111ba`
- `KERNEL32!CreateDirectoryW` at `0x1800111e3`
- `KERNEL32!CreateDirectoryW` at `0x1800111ba`
- `KERNEL32!CreateDirectoryW` at `0x1800111e3`
- `KERNEL32!GetFileAttributesExW` at `0x180011227`
- `KERNEL32!GetFileAttributesExW` at `0x18001126a`
- `KERNEL32!GetFileAttributesExW` at `0x180011227`
- `KERNEL32!GetFileAttributesExW` at `0x18001126a`
- `RPCRT4!UuidFromStringW` at `0x180011363`
- `RPCRT4!UuidFromStringW` at `0x180011363`

## string_xrefs

- `0x18001119d`: `%windir%\system32\LogFiles`
- `0x1800111c6`: `%windir%\system32\LogFiles\FileHistory`
- `0x180011206`: `%windir%\system32\LogFiles\FileHistory\fhtrace.etl`

## pseudocode

```c
void StartTracingSession(void)
{
  struct _EVENT_TRACE_PROPERTIES *v0; // r14
  WCHAR *v1; // rdi
  WCHAR *v2; // rax
  WCHAR *v3; // rbx
  WCHAR *v4; // rax
  unsigned __int64 v5; // r14
  int v6; // r15d
  unsigned int v7; // esi
  unsigned __int64 v8; // rdx
  int v9; // eax
  HANDLE FileW; // r14
  struct _EVENT_TRACE_PROPERTIES *v11; // rax
  int v12; // esi
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  BYTE v17[4]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v18[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v20[4]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v21[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[8]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG64 TraceHandle; // [rsp+68h] [rbp-98h] BYREF
  RPC_WSTR StringUuid[12]; // [rsp+70h] [rbp-90h]
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v26; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v27; // [rsp+F0h] [rbp-10h]
  int v28; // [rsp+100h] [rbp+0h]
  _OWORD FileInformation[2]; // [rsp+108h] [rbp+8h] BYREF
  int v30; // [rsp+128h] [rbp+28h]
  char v31[8]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v32; // [rsp+138h] [rbp+38h]
  int v33; // [rsp+140h] [rbp+40h]
  unsigned __int16 v34[270]; // [rsp+144h] [rbp+44h] BYREF

  v30 = 0;
  v28 = 0;
  TraceHandle = 0;
  StringUuid[0] = L"D5F5B066-729A-11DF-A7D3-18A90531A85A";
  hKey = 0;
  StringUuid[1] = L"D5F5B067-729A-11DF-A7D3-18A90531A85A";
  *(_DWORD *)Data = 0;
  StringUuid[2] = L"D5F5B068-729A-11DF-A7D3-18A90531A85A";
  *(_DWORD *)v21 = 0;
  StringUuid[3] = L"D5F5B069-729A-11DF-A7D3-18A90531A85A";
  *(_DWORD *)v20 = 0;
  StringUuid[4] = L"D5F5B06A-729A-11DF-A7D3-18A90531A85A";
  v0 = 0;
  *(_DWORD *)v18 = 0;
  StringUuid[5] = L"D5F5B06B-729A-11DF-A7D3-18A90531A85A";
  v1 = 0;
  *(_DWORD *)v17 = 0;
  StringUuid[6] = L"D5F5B06C-729A-11DF-A7D3-18A90531A85A";
  StringUuid[7] = L"D5F5B06D-729A-11DF-A7D3-18A90531A85A";
  StringUuid[8] = L"D5F5B06E-729A-11DF-A7D3-18A90531A85A";
  StringUuid[9] = L"D5F5B06F-729A-11DF-A7D3-18A90531A85A";
  StringUuid[10] = L"D5F5B070-729A-11DF-A7D3-18A90531A85A";
  StringUuid[11] = L"D5F5B071-729A-11DF-A7D3-18A90531A85AD5F5B072-729A-11DF-A7D3-18A90531A85A";
  memset(FileInformation, 0, sizeof(FileInformation));
  cbData = 0;
  Type = 0;
  v26 = 0;
  v27 = 0;
  Uuid = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\FileHistory",
         0,
         0x20019u,
         &hKey) )
  {
    v3 = 0;
LABEL_44:
    if ( TraceHandle )
      ControlTraceW(TraceHandle, L"FHSVCTRACE", v0, 1u);
    goto LABEL_46;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"TracingEnabled", 0, &Type, Data, &cbData) || Type != 4 )
    *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"TraceFileSize", 0, &Type, v18, &cbData) || Type != 4 || !*(_DWORD *)v18 )
    *(_DWORD *)v18 = 50;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"TraceFileCount", 0, &Type, v17, &cbData) || Type != 4 || !*(_DWORD *)v17 )
    *(_DWORD *)v17 = 10;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"ControlFlags", 0, &Type, v21, &cbData) || Type != 4 )
    *(_DWORD *)v21 = 15;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"ControlLevel", 0, &Type, v20, &cbData) || Type != 4 )
    *(_DWORD *)v20 = 255;
  v2 = (WCHAR *)LocalAlloc(0x40u, 0x20Au);
  v3 = v2;
  if ( v2 )
  {
    if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\LogFiles", v2, 0x105u) )
    {
      CreateDirectoryW(v3, 0);
      if ( ExpandEnvironmentStringsW(L"%windir%\\system32\\LogFiles\\FileHistory", v3, 0x105u) )
      {
        CreateDirectoryW(v3, 0);
        v4 = (WCHAR *)LocalAlloc(0x40u, 0x20Au);
        v1 = v4;
        if ( v4 )
        {
          if ( !ExpandEnvironmentStringsW(L"%windir%\\system32\\LogFiles\\FileHistory\\fhtrace.etl", v4, 0x105u) )
            goto LABEL_46;
          if ( GetFileAttributesExW(v1, GetFileExInfoStandard, FileInformation) )
          {
            v5 = -1;
            v6 = 1;
            v7 = 1;
            if ( !*(_DWORD *)v17 )
              goto LABEL_33;
            do
            {
              LODWORD(phkResult) = v7;
              StringCchPrintfW(v3, 0x105u, L"%s.%d", v1, phkResult);
              if ( !GetFileAttributesExW(v3, GetFileExInfoStandard, &v26) )
                break;
              v8 = DWORD1(v27) + ((unsigned __int64)DWORD2(v27) << 32);
              v9 = v7;
              if ( v8 >= v5 )
                v9 = v6;
              ++v7;
              v6 = v9;
              if ( v8 >= v5 )
                v8 = v5;
              v5 = v8;
            }
            while ( v7 <= *(_DWORD *)v17 );
            if ( v7 > *(_DWORD *)v17 )
LABEL_33:
              v7 = v6;
            FileW = CreateFileW(v1, 0x40010000u, 0, 0, 3u, 0x200000u, 0);
            if ( FileW != (HANDLE)-1LL )
            {
              v31[0] = 1;
              v32 = 0;
              v33 = 260;
              LODWORD(phkResulta) = v7;
              StringCchPrintfW(v34, 0x105u, L"%s.%d", v1, phkResulta);
              SetFileInformationByHandle(FileW, FileRenameInfo, v31, 0x222u);
              CloseHandle(FileW);
            }
          }
          v11 = AllocSessionProperties(v1, *(unsigned int *)v18);
          v0 = v11;
          if ( v11 && !StartTraceW(&TraceHandle, L"FHSVCTRACE", v11) )
          {
            v12 = 0;
            while ( !UuidFromStringW(StringUuid[v12], &Uuid)
                 && !EnableTrace(1u, *(ULONG *)v21, *(ULONG *)v20, &Uuid, TraceHandle) )
            {
              if ( (unsigned int)++v12 >= 0xC )
                goto LABEL_46;
            }
          }
        }
        goto LABEL_44;
      }
    }
  }
LABEL_46:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v0 )
    LocalFree(v0);
  if ( v1 )
    LocalFree(v1);
  if ( v3 )
    LocalFree(v3);
}

```

## disassembly

```asm
0x180010ed4  push    rbp
0x180010ed6  push    rbx
0x180010ed7  push    rsi
0x180010ed8  push    rdi
0x180010ed9  push    r12
0x180010edb  push    r13
0x180010edd  push    r14
0x180010edf  push    r15
0x180010ee1  lea     rbp, [rsp-278h]
0x180010ee9  sub     rsp, 378h
0x180010ef0  mov     rax, cs:__security_cookie
0x180010ef7  xor     rax, rsp
0x180010efa  mov     [rbp+2B0h+var_50], rax
0x180010f01  xor     eax, eax
0x180010f03  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180010f0a  mov     [rbp+2B0h+var_288], eax
0x180010f0d  xor     r12d, r12d
0x180010f10  mov     [rbp+2B0h+var_2B0], eax
0x180010f13  xorps   xmm0, xmm0
0x180010f16  lea     rax, aD5f5b066729a11; "D5F5B066-729A-11DF-A7D3-18A90531A85A"
0x180010f1d  mov     [rsp+3B0h+TraceHandle], r12
0x180010f22  mov     [rsp+3B0h+StringUuid], rax
0x180010f27  xorps   xmm1, xmm1
0x180010f2a  lea     rax, aD5f5b067729a11; "D5F5B067-729A-11DF-A7D3-18A90531A85A"
0x180010f31  mov     [rsp+3B0h+hKey], r12
0x180010f36  mov     [rsp+3B0h+var_338], rax
0x180010f3b  mov     r9d, 20019h; samDesired
0x180010f41  lea     rax, aD5f5b068729a11; "D5F5B068-729A-11DF-A7D3-18A90531A85A"
0x180010f48  mov     dword ptr [rsp+3B0h+Data], r12d
0x180010f4d  mov     [rbp+2B0h+var_330], rax
0x180010f51  xor     r8d, r8d; ulOptions
0x180010f54  lea     rax, aD5f5b069729a11; "D5F5B069-729A-11DF-A7D3-18A90531A85A"
0x180010f5b  mov     dword ptr [rsp+3B0h+var_354], r12d
0x180010f60  mov     [rbp+2B0h+var_328], rax
0x180010f64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010f6b  lea     rax, aD5f5b06a729a11; "D5F5B06A-729A-11DF-A7D3-18A90531A85A"
0x180010f72  mov     dword ptr [rsp+3B0h+var_358], r12d
0x180010f77  mov     [rbp+2B0h+var_320], rax
0x180010f7b  mov     r14d, r12d
0x180010f7e  lea     rax, aD5f5b06b729a11; "D5F5B06B-729A-11DF-A7D3-18A90531A85A"
0x180010f85  mov     dword ptr [rsp+3B0h+var_364], r12d
0x180010f8a  mov     [rbp+2B0h+var_318], rax
0x180010f8e  mov     edi, r12d
0x180010f91  lea     rax, aD5f5b06c729a11; "D5F5B06C-729A-11DF-A7D3-18A90531A85A"
0x180010f98  mov     dword ptr [rsp+3B0h+var_368], r12d
0x180010f9d  mov     [rbp+2B0h+var_310], rax
0x180010fa1  lea     rax, aD5f5b06d729a11; "D5F5B06D-729A-11DF-A7D3-18A90531A85A"
0x180010fa8  mov     [rbp+2B0h+var_308], rax
0x180010fac  lea     rax, aD5f5b06e729a11; "D5F5B06E-729A-11DF-A7D3-18A90531A85A"
0x180010fb3  mov     [rbp+2B0h+var_300], rax
0x180010fb7  lea     rax, aD5f5b06f729a11; "D5F5B06F-729A-11DF-A7D3-18A90531A85A"
0x180010fbe  mov     [rbp+2B0h+var_2F8], rax
0x180010fc2  lea     rax, aD5f5b070729a11; "D5F5B070-729A-11DF-A7D3-18A90531A85A"
0x180010fc9  mov     [rbp+2B0h+var_2F0], rax
0x180010fcd  lea     rax, aD5f5b071729a11; "D5F5B071-729A-11DF-A7D3-18A90531A85AD5F"...
0x180010fd4  mov     [rbp+2B0h+var_2E8], rax
0x180010fd8  lea     rax, [rsp+3B0h+hKey]
0x180010fdd  mov     [rsp+3B0h+phkResult], rax; phkResult
0x180010fe2  movups  [rbp+2B0h+FileInformation], xmm0
0x180010fe6  mov     [rsp+3B0h+cbData], r12d
0x180010feb  movups  [rbp+2B0h+var_298], xmm0
0x180010fef  mov     [rsp+3B0h+Type], r12d
0x180010ff4  movups  [rbp+2B0h+var_2D0], xmm1
0x180010ff8  movups  [rbp+2B0h+var_2C0], xmm1
0x180010ffc  movups  xmmword ptr [rbp+2B0h+Uuid.Data1], xmm0
0x180011000  call    cs:__imp_RegOpenKeyExW
0x180011006  lea     r13d, [r12+1]
0x18001100b  test    eax, eax
0x18001100d  jnz     loc_18001139B
0x180011013  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180011018  lea     ebx, [rax+4]
0x18001101b  lea     rax, [rsp+3B0h+cbData]
0x180011020  mov     [rsp+3B0h+cbData], ebx
0x180011024  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180011029  lea     r9, [rsp+3B0h+Type]; lpType
0x18001102e  lea     rax, [rsp+3B0h+Data]
0x180011033  xor     r8d, r8d; lpReserved
0x180011036  lea     rdx, aTracingenabled; "TracingEnabled"
0x18001103d  mov     [rsp+3B0h+phkResult], rax; lpData
0x180011042  call    cs:__imp_RegQueryValueExW
0x180011048  test    eax, eax
0x18001104a  jnz     short loc_180011052
0x18001104c  cmp     [rsp+3B0h+Type], ebx
0x180011050  jz      short loc_180011057
0x180011052  mov     dword ptr [rsp+3B0h+Data], r12d
0x180011057  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18001105c  lea     rax, [rsp+3B0h+cbData]
0x180011061  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180011066  lea     r9, [rsp+3B0h+Type]; lpType
0x18001106b  lea     rax, [rsp+3B0h+var_364]
0x180011070  mov     [rsp+3B0h+cbData], ebx
0x180011074  xor     r8d, r8d; lpReserved
0x180011077  mov     [rsp+3B0h+phkResult], rax; lpData
0x18001107c  lea     rdx, aTracefilesize; "TraceFileSize"
0x180011083  call    cs:__imp_RegQueryValueExW
0x180011089  test    eax, eax
0x18001108b  jnz     short loc_18001109A
0x18001108d  cmp     [rsp+3B0h+Type], ebx
0x180011091  jnz     short loc_18001109A
0x180011093  cmp     dword ptr [rsp+3B0h+var_364], r12d
0x180011098  jnz     short loc_1800110A2
0x18001109a  mov     dword ptr [rsp+3B0h+var_364], 32h ; '2'
0x1800110a2  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800110a7  lea     rax, [rsp+3B0h+cbData]
0x1800110ac  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x1800110b1  lea     r9, [rsp+3B0h+Type]; lpType
0x1800110b6  lea     rax, [rsp+3B0h+var_368]
0x1800110bb  mov     [rsp+3B0h+cbData], ebx
0x1800110bf  xor     r8d, r8d; lpReserved
0x1800110c2  mov     [rsp+3B0h+phkResult], rax; lpData
0x1800110c7  lea     rdx, aTracefilecount; "TraceFileCount"
0x1800110ce  call    cs:__imp_RegQueryValueExW
0x1800110d4  test    eax, eax
0x1800110d6  jnz     short loc_1800110E5
0x1800110d8  cmp     [rsp+3B0h+Type], ebx
0x1800110dc  jnz     short loc_1800110E5
0x1800110de  cmp     dword ptr [rsp+3B0h+var_368], r12d
0x1800110e3  jnz     short loc_1800110ED
0x1800110e5  mov     dword ptr [rsp+3B0h+var_368], 0Ah
0x1800110ed  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800110f2  lea     rax, [rsp+3B0h+cbData]
0x1800110f7  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x1800110fc  lea     r9, [rsp+3B0h+Type]; lpType
0x180011101  lea     rax, [rsp+3B0h+var_354]
0x180011106  mov     [rsp+3B0h+cbData], ebx
0x18001110a  xor     r8d, r8d; lpReserved
0x18001110d  mov     [rsp+3B0h+phkResult], rax; lpData
0x180011112  lea     rdx, aControlflags; "ControlFlags"
0x180011119  call    cs:__imp_RegQueryValueExW
0x18001111f  test    eax, eax
0x180011121  jnz     short loc_180011129
0x180011123  cmp     [rsp+3B0h+Type], ebx
0x180011127  jz      short loc_180011131
0x180011129  mov     dword ptr [rsp+3B0h+var_354], 0Fh
0x180011131  mov     rcx, [rsp+3B0h+hKey]; hKey
0x180011136  lea     rax, [rsp+3B0h+cbData]
0x18001113b  mov     [rsp+3B0h+lpcbData], rax; lpcbData
0x180011140  lea     r9, [rsp+3B0h+Type]; lpType
0x180011145  lea     rax, [rsp+3B0h+var_358]
0x18001114a  mov     [rsp+3B0h+cbData], ebx
0x18001114e  xor     r8d, r8d; lpReserved
0x180011151  mov     [rsp+3B0h+phkResult], rax; lpData
0x180011156  lea     rdx, aControllevel; "ControlLevel"
0x18001115d  call    cs:__imp_RegQueryValueExW
0x180011163  test    eax, eax
0x180011165  jnz     short loc_18001116D
0x180011167  cmp     [rsp+3B0h+Type], ebx
0x18001116b  jz      short loc_180011175
0x18001116d  mov     dword ptr [rsp+3B0h+var_358], 0FFh
0x180011175  mov     esi, 20Ah
0x18001117a  mov     r15d, 40h ; '@'
0x180011180  mov     edx, esi; uBytes
0x180011182  mov     ecx, r15d; uFlags
0x180011185  call    cs:__imp_LocalAlloc
0x18001118b  mov     rbx, rax
0x18001118e  test    rax, rax
0x180011191  jz      loc_1800113BB
0x180011197  mov     r8d, 105h; nSize
0x18001119d  lea     rcx, Src; "%windir%\\system32\\LogFiles"
0x1800111a4  mov     rdx, rax; lpDst
0x1800111a7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800111ad  test    eax, eax
0x1800111af  jz      loc_1800113BB
0x1800111b5  xor     edx, edx; lpSecurityAttributes
0x1800111b7  mov     rcx, rbx; lpPathName
0x1800111ba  call    cs:__imp_CreateDirectoryW
0x1800111c0  mov     r8d, 105h; nSize
0x1800111c6  lea     rcx, aWindirSystem32_1; "%windir%\\system32\\LogFiles\\FileHisto"...
0x1800111cd  mov     rdx, rbx; lpDst
0x1800111d0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800111d6  test    eax, eax
0x1800111d8  jz      loc_1800113BB
0x1800111de  xor     edx, edx; lpSecurityAttributes
0x1800111e0  mov     rcx, rbx; lpPathName
0x1800111e3  call    cs:__imp_CreateDirectoryW
0x1800111e9  mov     edx, esi; uBytes
0x1800111eb  mov     ecx, r15d; uFlags
0x1800111ee  call    cs:__imp_LocalAlloc
0x1800111f4  mov     rdi, rax
0x1800111f7  test    rax, rax
0x1800111fa  jz      loc_18001139E
0x180011200  mov     r8d, 105h; nSize
0x180011206  lea     rcx, aWindirSystem32; "%windir%\\system32\\LogFiles\\FileHisto"...
0x18001120d  mov     rdx, rax; lpDst
0x180011210  call    cs:__imp_ExpandEnvironmentStringsW
0x180011216  test    eax, eax
0x180011218  jz      loc_1800113BB
0x18001121e  lea     r8, [rbp+2B0h+FileInformation]; lpFileInformation
0x180011222  xor     edx, edx; fInfoLevelId
0x180011224  mov     rcx, rdi; lpFileName
0x180011227  call    cs:__imp_GetFileAttributesExW
0x18001122d  test    eax, eax
0x18001122f  jz      loc_180011328
0x180011235  or      r14, 0FFFFFFFFFFFFFFFFh
0x180011239  mov     r15d, r13d
0x18001123c  mov     esi, r13d
0x18001123f  cmp     dword ptr [rsp+3B0h+var_368], r13d
0x180011244  jb      short loc_1800112A6
0x180011246  mov     r9, rdi
0x180011249  mov     dword ptr [rsp+3B0h+phkResult], esi
0x18001124d  lea     r8, aSD; "%s.%d"
0x180011254  mov     edx, 105h; unsigned __int64
0x180011259  mov     rcx, rbx; unsigned __int16 *
0x18001125c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011261  lea     r8, [rbp+2B0h+var_2D0]; lpFileInformation
0x180011265  xor     edx, edx; fInfoLevelId
0x180011267  mov     rcx, rbx; lpFileName
0x18001126a  call    cs:__imp_GetFileAttributesExW
0x180011270  test    eax, eax
0x180011272  jz      short loc_1800112A0
0x180011274  mov     eax, dword ptr [rbp+2B0h+var_2C0+4]
0x180011277  mov     edx, dword ptr [rbp+2B0h+var_2C0+8]
0x18001127a  shl     rdx, 20h
0x18001127e  add     rdx, rax
0x180011281  mov     eax, esi
0x180011283  cmp     rdx, r14
0x180011286  cmovnb  eax, r15d
0x18001128a  add     esi, r13d
0x18001128d  cmp     rdx, r14
0x180011290  mov     r15d, eax
0x180011293  cmovnb  rdx, r14
0x180011297  mov     r14, rdx
0x18001129a  cmp     esi, dword ptr [rsp+3B0h+var_368]
0x18001129e  jbe     short loc_180011246
0x1800112a0  cmp     esi, dword ptr [rsp+3B0h+var_368]
0x1800112a4  jbe     short loc_1800112A9
0x1800112a6  mov     esi, r15d
0x1800112a9  mov     [rsp+3B0h+hTemplateFile], r12; hTemplateFile
0x1800112ae  mov     r15d, 3
0x1800112b4  mov     dword ptr [rsp+3B0h+lpcbData], 200000h; dwFlagsAndAttributes
0x1800112bc  xor     r9d, r9d; lpSecurityAttributes
0x1800112bf  xor     r8d, r8d; dwShareMode
0x1800112c2  mov     dword ptr [rsp+3B0h+phkResult], r15d; dwCreationDisposition
0x1800112c7  mov     edx, 40010000h; dwDesiredAccess
0x1800112cc  mov     rcx, rdi; lpFileName
0x1800112cf  call    cs:__imp_CreateFileW
0x1800112d5  mov     r14, rax
0x1800112d8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800112dc  jz      short loc_180011328
0x1800112de  mov     r9, rdi
0x1800112e1  mov     [rbp+2B0h+var_280], r13b
0x1800112e5  lea     r8, aSD; "%s.%d"
0x1800112ec  mov     [rbp+2B0h+var_278], r12
0x1800112f0  mov     edx, 105h; unsigned __int64
0x1800112f5  mov     [rbp+2B0h+var_270], 104h
0x1800112fc  lea     rcx, [rbp+2B0h+var_26C]; unsigned __int16 *
0x180011300  mov     dword ptr [rsp+3B0h+phkResult], esi
0x180011304  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011309  mov     r9d, 222h; dwBufferSize
0x18001130f  lea     r8, [rbp+2B0h+var_280]; lpFileInformation
0x180011313  mov     edx, r15d; FileInformationClass
0x180011316  mov     rcx, r14; hFile
0x180011319  call    cs:__imp_SetFileInformationByHandle
0x18001131f  mov     rcx, r14; hObject
0x180011322  call    cs:__imp_CloseHandle
0x180011328  mov     edx, dword ptr [rsp+3B0h+var_364]; unsigned int
0x18001132c  mov     rcx, rdi; unsigned __int16 *
0x18001132f  call    ?AllocSessionProperties@@YAPEAU_EVENT_TRACE_PROPERTIES@@PEBGK@Z; AllocSessionProperties(ushort const *,ulong)
0x180011334  mov     r14, rax
0x180011337  test    rax, rax
0x18001133a  jz      short loc_18001139E
0x18001133c  mov     r8, rax; Properties
0x18001133f  lea     rdx, InstanceName; "FHSVCTRACE"
0x180011346  lea     rcx, [rsp+3B0h+TraceHandle]; TraceHandle
0x18001134b  call    cs:__imp_StartTraceW
0x180011351  test    eax, eax
0x180011353  jnz     short loc_18001139E
0x180011355  mov     esi, r12d
0x180011358  mov     ecx, esi
0x18001135a  lea     rdx, [rbp+2B0h+Uuid]; Uuid
0x18001135e  mov     rcx, [rsp+rcx*8+3B0h+StringUuid]; StringUuid
0x180011363  call    cs:__imp_UuidFromStringW
0x180011369  test    eax, eax
0x18001136b  jnz     short loc_18001139E
0x18001136d  mov     rax, [rsp+3B0h+TraceHandle]
0x180011372  lea     r9, [rbp+2B0h+Uuid]; ControlGuid
0x180011376  mov     r8d, dword ptr [rsp+3B0h+var_358]; EnableLevel
0x18001137b  mov     ecx, r13d; Enable
0x18001137e  mov     edx, dword ptr [rsp+3B0h+var_354]; EnableFlag
0x180011382  mov     [rsp+3B0h+phkResult], rax; TraceHandle
0x180011387  call    cs:__imp_EnableTrace
0x18001138d  test    eax, eax
0x18001138f  jnz     short loc_18001139E
0x180011391  add     esi, r13d
0x180011394  cmp     esi, 0Ch
0x180011397  jb      short loc_180011358
0x180011399  jmp     short loc_1800113BB
0x18001139b  mov     rbx, r12
0x18001139e  mov     rcx, [rsp+3B0h+TraceHandle]; TraceHandle
0x1800113a3  test    rcx, rcx
0x1800113a6  jz      short loc_1800113BB
0x1800113a8  mov     r9d, r13d; ControlCode
0x1800113ab  lea     rdx, InstanceName; "FHSVCTRACE"
0x1800113b2  mov     r8, r14; Properties
0x1800113b5  call    cs:__imp_ControlTraceW
0x1800113bb  mov     rcx, [rsp+3B0h+hKey]; hKey
0x1800113c0  test    rcx, rcx
0x1800113c3  jz      short loc_1800113D0
0x1800113c5  call    cs:__imp_RegCloseKey
0x1800113cb  mov     [rsp+3B0h+hKey], r12
  ... truncated ...
```
