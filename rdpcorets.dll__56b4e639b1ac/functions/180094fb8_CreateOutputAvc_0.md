# CreateOutputAvc_0

- ea: `0x180094fb8`
- end: `0x180095301`
- name: `CreateOutputAvc_0`
- size: `841`
- prototype: `__int64 __fastcall(int, int, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180096c80`

## callees

- `0x180033964`
- `0x180033da0`
- `0x180034970`
- `0x180094fb8`
- `0x1800d8f18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095071`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800950be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009510b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095158`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800951a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800951ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009523a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095071`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800950be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009510b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180095158`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800951a5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800951ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009523a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095263`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095263`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095028`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095028`

## string_xrefs

- `0x180095233`: `RecordPath`
- `0x18009501a`: `Software\Policies\Microsoft\Windows NT\Terminal Services\HevcEncoding`

## pseudocode

```c
OutputAvc *__fastcall CreateOutputAvc_0(int a1, int a2, int a3, int a4)
{
  FILE **v8; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[4]; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v15; // [rsp+64h] [rbp-9Ch]
  BOOL v16; // [rsp+68h] [rbp-98h]
  BOOL v17; // [rsp+74h] [rbp-8Ch]
  BOOL v18; // [rsp+7Ch] [rbp-84h]
  BOOL v19; // [rsp+80h] [rbp-80h]
  BOOL v20; // [rsp+84h] [rbp-7Ch]
  BYTE v21[520]; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v22; // [rsp+29Ch] [rbp+19Ch]

  hKey = 0;
  memset_0(v14, 0, 0x240u);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\HevcEncoding",
          0,
          0x20019u,
          &hKey) )
  {
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableRecord264", 0, &Type, Data, &cbData) && Type == 4 )
      v15 = *(_DWORD *)Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableRecordYUV", 0, &Type, Data, &cbData) && Type == 4 )
      v16 = *(_DWORD *)Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Enable264Log", 0, &Type, Data, &cbData) && Type == 4 )
      v17 = *(_DWORD *)Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableAvcSourceDump", 0, &Type, Data, &cbData) && Type == 4 )
      v18 = *(_DWORD *)Data != 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableAvcRefDump", 0, &Type, Data, &cbData) && Type == 4 )
      v19 = *(_DWORD *)Data != 0;
    if ( !RegQueryValueExW(hKey, L"EnableAvcReconDump", 0, &Type, Data, &cbData) && Type == 4 )
      v20 = *(_DWORD *)Data != 0;
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"RecordPath", 0, &Type, v21, &cbData) || Type != 1 )
      v22 = 0;
    else
      v22 = cbData;
    RegCloseKey(hKey);
  }
  ++g_hevcidx;
  if ( !v22 || !v16 && !v15 && !v17 && !v18 && !v19 && !v20 )
    return 0;
  v8 = (FILE **)operator new(0x88u);
  if ( v8 )
    return OutputAvc::OutputAvc(v8, a1, a2, a3, a4, (struct RecordSettings *)v14, g_hevcidx);
  else
    return 0;
}

```

## disassembly

```asm
0x180094fb8  push    rbp
0x180094fba  push    rbx
0x180094fbb  push    rsi
0x180094fbc  push    rdi
0x180094fbd  push    r12
0x180094fbf  push    r14
0x180094fc1  push    r15
0x180094fc3  lea     rbp, [rsp-1B0h]
0x180094fcb  sub     rsp, 2B0h
0x180094fd2  mov     rax, cs:__security_cookie
0x180094fd9  xor     rax, rsp
0x180094fdc  mov     [rbp+1E0h+var_40], rax
0x180094fe3  mov     r14d, r8d
0x180094fe6  mov     esi, edx
0x180094fe8  mov     edi, ecx
0x180094fea  xor     r15d, r15d
0x180094fed  xor     edx, edx; Val
0x180094fef  mov     [rsp+2E0h+hKey], r15
0x180094ff4  mov     r8d, 240h; Size
0x180094ffa  lea     rcx, [rsp+2E0h+var_280]; void *
0x180094fff  mov     ebx, r9d
0x180095002  call    memset_0
0x180095007  lea     rax, [rsp+2E0h+hKey]
0x18009500c  mov     r9d, 20019h; samDesired
0x180095012  xor     r8d, r8d; ulOptions
0x180095015  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18009501a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x180095021  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180095028  call    cs:__imp_RegOpenKeyExW
0x18009502e  test    eax, eax
0x180095030  jnz     loc_180095269
0x180095036  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18009503b  lea     rax, [rsp+2E0h+cbData]
0x180095040  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180095045  lea     r12d, [r15+4]
0x180095049  lea     rax, [rsp+2E0h+Data]
0x18009504e  mov     dword ptr [rsp+2E0h+Data], r15d
0x180095053  lea     r9, [rsp+2E0h+Type]; lpType
0x180095058  mov     [rsp+2E0h+phkResult], rax; lpData
0x18009505d  xor     r8d, r8d; lpReserved
0x180095060  mov     [rsp+2E0h+Type], r15d
0x180095065  lea     rdx, aEnablerecord26; "EnableRecord264"
0x18009506c  mov     [rsp+2E0h+cbData], r12d
0x180095071  call    cs:__imp_RegQueryValueExW
0x180095077  test    eax, eax
0x180095079  jnz     short loc_180095091
0x18009507b  cmp     [rsp+2E0h+Type], r12d
0x180095080  jnz     short loc_180095091
0x180095082  cmp     dword ptr [rsp+2E0h+Data], r15d
0x180095087  mov     eax, r15d
0x18009508a  setnz   al
0x18009508d  mov     [rsp+2E0h+var_27C], eax
0x180095091  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180095096  lea     rax, [rsp+2E0h+cbData]
0x18009509b  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800950a0  lea     r9, [rsp+2E0h+Type]; lpType
0x1800950a5  lea     rax, [rsp+2E0h+Data]
0x1800950aa  mov     [rsp+2E0h+cbData], r12d
0x1800950af  xor     r8d, r8d; lpReserved
0x1800950b2  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800950b7  lea     rdx, aEnablerecordyu; "EnableRecordYUV"
0x1800950be  call    cs:__imp_RegQueryValueExW
0x1800950c4  test    eax, eax
0x1800950c6  jnz     short loc_1800950DE
0x1800950c8  cmp     [rsp+2E0h+Type], r12d
0x1800950cd  jnz     short loc_1800950DE
0x1800950cf  cmp     dword ptr [rsp+2E0h+Data], r15d
0x1800950d4  mov     eax, r15d
0x1800950d7  setnz   al
0x1800950da  mov     [rsp+2E0h+var_278], eax
0x1800950de  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800950e3  lea     rax, [rsp+2E0h+cbData]
0x1800950e8  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800950ed  lea     r9, [rsp+2E0h+Type]; lpType
0x1800950f2  lea     rax, [rsp+2E0h+Data]
0x1800950f7  mov     [rsp+2E0h+cbData], r12d
0x1800950fc  xor     r8d, r8d; lpReserved
0x1800950ff  mov     [rsp+2E0h+phkResult], rax; lpData
0x180095104  lea     rdx, aEnable264log; "Enable264Log"
0x18009510b  call    cs:__imp_RegQueryValueExW
0x180095111  test    eax, eax
0x180095113  jnz     short loc_18009512B
0x180095115  cmp     [rsp+2E0h+Type], r12d
0x18009511a  jnz     short loc_18009512B
0x18009511c  cmp     dword ptr [rsp+2E0h+Data], r15d
0x180095121  mov     eax, r15d
0x180095124  setnz   al
0x180095127  mov     [rsp+2E0h+var_26C], eax
0x18009512b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180095130  lea     rax, [rsp+2E0h+cbData]
0x180095135  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18009513a  lea     r9, [rsp+2E0h+Type]; lpType
0x18009513f  lea     rax, [rsp+2E0h+Data]
0x180095144  mov     [rsp+2E0h+cbData], r12d
0x180095149  xor     r8d, r8d; lpReserved
0x18009514c  mov     [rsp+2E0h+phkResult], rax; lpData
0x180095151  lea     rdx, aEnableavcsourc; "EnableAvcSourceDump"
0x180095158  call    cs:__imp_RegQueryValueExW
0x18009515e  test    eax, eax
0x180095160  jnz     short loc_180095178
0x180095162  cmp     [rsp+2E0h+Type], r12d
0x180095167  jnz     short loc_180095178
0x180095169  cmp     dword ptr [rsp+2E0h+Data], r15d
0x18009516e  mov     eax, r15d
0x180095171  setnz   al
0x180095174  mov     [rsp+2E0h+var_264], eax
0x180095178  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18009517d  lea     rax, [rsp+2E0h+cbData]
0x180095182  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180095187  lea     r9, [rsp+2E0h+Type]; lpType
0x18009518c  lea     rax, [rsp+2E0h+Data]
0x180095191  mov     [rsp+2E0h+cbData], r12d
0x180095196  xor     r8d, r8d; lpReserved
0x180095199  mov     [rsp+2E0h+phkResult], rax; lpData
0x18009519e  lea     rdx, aEnableavcrefdu; "EnableAvcRefDump"
0x1800951a5  call    cs:__imp_RegQueryValueExW
0x1800951ab  test    eax, eax
0x1800951ad  jnz     short loc_1800951C4
0x1800951af  cmp     [rsp+2E0h+Type], r12d
0x1800951b4  jnz     short loc_1800951C4
0x1800951b6  cmp     dword ptr [rsp+2E0h+Data], r15d
0x1800951bb  mov     eax, r15d
0x1800951be  setnz   al
0x1800951c1  mov     [rbp+1E0h+var_260], eax
0x1800951c4  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800951c9  lea     rax, [rsp+2E0h+cbData]
0x1800951ce  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800951d3  lea     r9, [rsp+2E0h+Type]; lpType
0x1800951d8  lea     rax, [rsp+2E0h+Data]
0x1800951dd  xor     r8d, r8d; lpReserved
0x1800951e0  lea     rdx, aEnableavcrecon; "EnableAvcReconDump"
0x1800951e7  mov     [rsp+2E0h+phkResult], rax; lpData
0x1800951ec  call    cs:__imp_RegQueryValueExW
0x1800951f2  test    eax, eax
0x1800951f4  jnz     short loc_18009520B
0x1800951f6  cmp     [rsp+2E0h+Type], r12d
0x1800951fb  jnz     short loc_18009520B
0x1800951fd  cmp     dword ptr [rsp+2E0h+Data], r15d
0x180095202  mov     eax, r15d
0x180095205  setnz   al
0x180095208  mov     [rbp+1E0h+var_25C], eax
0x18009520b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180095210  lea     rax, [rsp+2E0h+cbData]
0x180095215  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18009521a  lea     r9, [rsp+2E0h+Type]; lpType
0x18009521f  lea     rax, [rbp+1E0h+var_24C]
0x180095223  mov     [rsp+2E0h+cbData], 208h
0x18009522b  xor     r8d, r8d; lpReserved
0x18009522e  mov     [rsp+2E0h+phkResult], rax; lpData
0x180095233  lea     rdx, aRecordpath; "RecordPath"
0x18009523a  call    cs:__imp_RegQueryValueExW
0x180095240  test    eax, eax
0x180095242  jnz     short loc_180095257
0x180095244  cmp     [rsp+2E0h+Type], 1
0x180095249  jnz     short loc_180095257
0x18009524b  mov     eax, [rsp+2E0h+cbData]
0x18009524f  mov     [rbp+1E0h+var_44], eax
0x180095255  jmp     short loc_18009525E
0x180095257  mov     [rbp+1E0h+var_44], r15d
0x18009525e  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180095263  call    cs:__imp_RegCloseKey
0x180095269  inc     cs:?g_hevcidx@@3HA; int g_hevcidx
0x18009526f  cmp     [rbp+1E0h+var_44], r15d
0x180095276  jz      short loc_1800952DE
0x180095278  cmp     [rsp+2E0h+var_278], r15d
0x18009527d  jnz     short loc_1800952A0
0x18009527f  cmp     [rsp+2E0h+var_27C], r15d
0x180095284  jnz     short loc_1800952A0
0x180095286  cmp     [rsp+2E0h+var_26C], r15d
0x18009528b  jnz     short loc_1800952A0
0x18009528d  cmp     [rsp+2E0h+var_264], r15d
0x180095292  jnz     short loc_1800952A0
0x180095294  cmp     [rbp+1E0h+var_260], r15d
0x180095298  jnz     short loc_1800952A0
0x18009529a  cmp     [rbp+1E0h+var_25C], r15d
0x18009529e  jz      short loc_1800952DE
0x1800952a0  mov     ecx, 88h; Size
0x1800952a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800952aa  test    rax, rax
0x1800952ad  jz      short loc_1800952D9
0x1800952af  mov     ecx, cs:?g_hevcidx@@3HA; int g_hevcidx
0x1800952b5  mov     r9d, r14d; int
0x1800952b8  mov     [rsp+2E0h+var_2B0], ecx; int
0x1800952bc  mov     r8d, esi; int
0x1800952bf  lea     rcx, [rsp+2E0h+var_280]
0x1800952c4  mov     edx, edi; int
0x1800952c6  mov     [rsp+2E0h+lpcbData], rcx; struct RecordSettings *
0x1800952cb  mov     rcx, rax; Stream
0x1800952ce  mov     dword ptr [rsp+2E0h+phkResult], ebx; int
0x1800952d2  call    ??0OutputAvc@@QEAA@HHHHAEAURecordSettings@@H@Z; OutputAvc::OutputAvc(int,int,int,int,RecordSettings &,int)
0x1800952d7  jmp     short loc_1800952E0
0x1800952d9  mov     rax, r15
0x1800952dc  jmp     short loc_1800952E0
0x1800952de  xor     eax, eax
0x1800952e0  mov     rcx, [rbp+1E0h+var_40]
0x1800952e7  xor     rcx, rsp; StackCookie
0x1800952ea  call    __security_check_cookie
0x1800952ef  add     rsp, 2B0h
0x1800952f6  pop     r15
0x1800952f8  pop     r14
0x1800952fa  pop     r12
0x1800952fc  pop     rdi
0x1800952fd  pop     rsi
0x1800952fe  pop     rbx
0x1800952ff  pop     rbp
0x180095300  retn
```
