# ISDKRegCopyKey

- ea: `0x18001151c`
- end: `0x18001187b`
- name: `ISDKRegCopyKey`
- size: `863`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18001151c`

## callees

- `0x180001901`
- `0x180010e14`
- `0x180011038`
- `0x180011424`
- `0x18001151c`
- `0x180011884`
- `0x180011964`
- `0x1800119dc`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18001159a`
- `KERNEL32!SetLastError` at `0x180011621`
- `KERNEL32!SetLastError` at `0x18001173a`
- `KERNEL32!SetLastError` at `0x180011820`
- `KERNEL32!SetLastError` at `0x18001159a`
- `KERNEL32!SetLastError` at `0x180011621`
- `KERNEL32!SetLastError` at `0x18001173a`
- `KERNEL32!SetLastError` at `0x180011820`
- `ADVAPI32!RegCreateKeyExW` at `0x1800115e1`
- `ADVAPI32!RegCreateKeyExW` at `0x1800115e1`
- `ADVAPI32!RegDeleteKeyW` at `0x180011814`
- `ADVAPI32!RegDeleteKeyW` at `0x180011814`
- `ADVAPI32!RegCloseKey` at `0x1800115f3`
- `ADVAPI32!RegCloseKey` at `0x180011764`
- `ADVAPI32!RegCloseKey` at `0x180011834`
- `ADVAPI32!RegCloseKey` at `0x180011842`
- `ADVAPI32!RegCloseKey` at `0x1800115f3`
- `ADVAPI32!RegCloseKey` at `0x180011764`
- `ADVAPI32!RegCloseKey` at `0x180011834`
- `ADVAPI32!RegCloseKey` at `0x180011842`
- `ADVAPI32!RegOpenKeyExW` at `0x18001158e`
- `ADVAPI32!RegOpenKeyExW` at `0x180011615`
- `ADVAPI32!RegOpenKeyExW` at `0x18001172e`
- `ADVAPI32!RegOpenKeyExW` at `0x18001158e`
- `ADVAPI32!RegOpenKeyExW` at `0x180011615`
- `ADVAPI32!RegOpenKeyExW` at `0x18001172e`

## pseudocode

```c
__int64 ISDKRegCopyKey(HKEY a1, const WCHAR *a2, HKEY a3, const WCHAR *a4, int a5, ...)
{
  unsigned int v5; // r12d
  unsigned int v8; // ebx
  unsigned int v9; // r13d
  unsigned int v10; // r14d
  LSTATUS v11; // eax
  HKEY v12; // r15
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  HKEY v15; // rdi
  __int64 v16; // rax
  _QWORD *v17; // rsi
  unsigned int v18; // r12d
  __int64 v19; // rax
  void **v20; // rsi
  LSTATUS v21; // eax
  HKEY v22; // r14
  DWORD dwDisposition; // [rsp+58h] [rbp-49h] BYREF
  HKEY v25; // [rsp+60h] [rbp-41h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-39h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-35h] BYREF
  void *Block; // [rsp+70h] [rbp-31h]
  HKEY phkResult; // [rsp+78h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-21h] BYREF
  HKEY v31; // [rsp+88h] [rbp-19h] BYREF
  __int64 v32; // [rsp+90h] [rbp-11h] BYREF
  __int64 v33[10]; // [rsp+98h] [rbp-9h] BYREF
  __int64 v38; // [rsp+120h] [rbp+7Fh] BYREF
  va_list va; // [rsp+120h] [rbp+7Fh]
  va_list va1; // [rsp+128h] [rbp+87h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v38 = va_arg(va1, _QWORD);
  v5 = 0;
  dwDisposition = 0;
  cbData = 0;
  Type = 0;
  LODWORD(v38) = 0;
  v33[0] = 0;
  v8 = 1;
  v32 = 0;
  v9 = 0;
  phkResult = 0;
  v10 = 0;
  v11 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &phkResult);
  if ( v11 )
    SetLastError(v11);
  v12 = phkResult;
  if ( !phkResult )
    goto LABEL_36;
  v25 = 0;
  v13 = RegCreateKeyExW(a3, a4, 0, 0, 0, 0xF003Fu, 0, &v25, &dwDisposition);
  if ( v13 )
  {
    v15 = 0;
LABEL_31:
    SetLastError(v13);
    v8 = 0;
    goto LABEL_34;
  }
  RegCloseKey(v25);
  hKey = 0;
  v14 = RegOpenKeyExW(a3, a4, 0, 0x20006u, &hKey);
  if ( v14 )
    SetLastError(v14);
  v15 = hKey;
  v8 = hKey != 0;
  if ( !hKey )
    goto LABEL_34;
  LODWORD(v25) = -1;
  v16 = ISDKEnumInfoKey(v12, &v25);
  v9 = (unsigned int)v25;
  v17 = (_QWORD *)v16;
  v33[0] = v16;
  if ( v16 && (_DWORD)v25 )
  {
    v18 = v8;
    do
    {
      v8 = (unsigned int)ISDKRegCopyKey((_DWORD)v12, *v17, (_DWORD)v15, *v17, a5) != 0 ? v18 : 0;
      if ( !v8 )
      {
        v10 = v38;
        v8 = 0;
        goto LABEL_34;
      }
      ++v10;
      v17 += 4;
      v18 = v8;
    }
    while ( v10 < v9 );
    v5 = 0;
  }
  LODWORD(v38) = -1;
  v19 = ISDKEnumInfoValue(v12, (__int64 *)va);
  v10 = v38;
  v20 = (void **)v19;
  v32 = v19;
  if ( !v19 || !(_DWORD)v38 )
  {
LABEL_29:
    if ( (a5 & 1) == 0 )
      goto LABEL_34;
    v13 = RegDeleteKeyW(a1, a2);
    if ( !v13 )
      goto LABEL_34;
    goto LABEL_31;
  }
  while ( 1 )
  {
    dwDisposition = 0;
    if ( (a5 & 4) == 0 )
      break;
    Type = 0;
    cbData = 0;
    Block = *v20;
    v31 = 0;
    v21 = RegOpenKeyExW(a3, a4, 0, 1u, &v31);
    if ( v21 )
      SetLastError(v21);
    v22 = v31;
    if ( v31 && (Block = (void *)ISDKQueryRegValue(v31, (LPCWSTR)Block, &Type, &cbData), RegCloseKey(v22), Block) )
    {
      free_0(Block);
      v8 = 1;
    }
    else
    {
      v8 &= -((unsigned int)ISDKSetRegValue(a3, a4, *v20, v20[2], *((_DWORD *)v20 + 2), *((_DWORD *)v20 + 6)) != 0);
    }
    v10 = v38;
LABEL_26:
    if ( !v8 )
      goto LABEL_33;
    ++v5;
    v20 += 4;
    if ( v5 >= v10 )
    {
      v9 = (unsigned int)v25;
      goto LABEL_29;
    }
  }
  if ( (unsigned int)ISDKSetRegValue(a3, a4, *v20, v20[2], *((_DWORD *)v20 + 2), *((_DWORD *)v20 + 6)) )
    goto LABEL_26;
  v8 = 0;
LABEL_33:
  v9 = (unsigned int)v25;
LABEL_34:
  RegCloseKey(v12);
  if ( v15 )
    RegCloseKey(v15);
LABEL_36:
  ISDKEnumInfoValueFree(&v32, v10);
  ISDKEnumInfoKeyFree(v33, v9);
  return v8;
}

```

## disassembly

```asm
0x18001151c  mov     rax, rsp
0x18001151f  mov     [rax+20h], r9
0x180011523  mov     [rax+18h], r8
0x180011527  mov     [rax+10h], rdx
0x18001152b  mov     [rax+8], rcx
0x18001152f  push    rbp
0x180011530  push    rbx
0x180011531  push    rsi
0x180011532  push    rdi
0x180011533  push    r12
0x180011535  push    r13
0x180011537  push    r14
0x180011539  push    r15
0x18001153b  lea     rbp, [rax-4Fh]
0x18001153f  sub     rsp, 0A8h
0x180011546  xor     r12d, r12d
0x180011549  mov     rax, rdx
0x18001154c  lea     rdx, [rbp+47h+var_70]
0x180011550  mov     [rbp+47h+dwDisposition], r12d
0x180011554  mov     [rsp+0E0h+phkResult], rdx; phkResult
0x180011559  mov     rdi, r9
0x18001155c  mov     rsi, r8
0x18001155f  mov     [rbp+47h+cbData], r12d
0x180011563  mov     rdx, rax; lpSubKey
0x180011566  mov     [rbp+47h+Type], r12d
0x18001156a  mov     r9d, 20019h; samDesired
0x180011570  mov     dword ptr [rbp+47h+arg_28], r12d
0x180011574  xor     r8d, r8d; ulOptions
0x180011577  mov     [rbp+47h+var_50], r12
0x18001157b  mov     ebx, 1
0x180011580  mov     [rbp+47h+var_58], r12
0x180011584  mov     r13d, r12d
0x180011587  mov     [rbp+47h+var_70], r12
0x18001158b  mov     r14d, r12d
0x18001158e  call    cs:__imp_RegOpenKeyExW
0x180011594  test    eax, eax
0x180011596  jz      short loc_1800115A0
0x180011598  mov     ecx, eax; dwErrCode
0x18001159a  call    cs:__imp_SetLastError
0x1800115a0  mov     r15, [rbp+47h+var_70]
0x1800115a4  test    r15, r15
0x1800115a7  jz      loc_180011848
0x1800115ad  lea     rax, [rbp+47h+dwDisposition]
0x1800115b1  mov     [rbp+47h+var_88], r12
0x1800115b5  mov     [rsp+40h], rax; lpdwDisposition
0x1800115ba  xor     r9d, r9d; lpClass
0x1800115bd  lea     rax, [rbp+47h+var_88]
0x1800115c1  xor     r8d, r8d; Reserved
0x1800115c4  mov     [rsp+0E0h+var_A8], rax; phkResult
0x1800115c9  mov     rdx, rdi; lpSubKey
0x1800115cc  mov     [rsp+0E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800115d1  mov     rcx, rsi; hKey
0x1800115d4  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x1800115dc  mov     dword ptr [rsp+0E0h+phkResult], r12d; dwOptions
0x1800115e1  call    cs:__imp_RegCreateKeyExW
0x1800115e7  test    eax, eax
0x1800115e9  jnz     loc_180011876
0x1800115ef  mov     rcx, [rbp+47h+var_88]; hKey
0x1800115f3  call    cs:__imp_RegCloseKey
0x1800115f9  lea     rax, [rbp+47h+hKey]
0x1800115fd  mov     [rbp+47h+hKey], r12
0x180011601  mov     r9d, 20006h; samDesired
0x180011607  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18001160c  xor     r8d, r8d; ulOptions
0x18001160f  mov     rdx, rdi; lpSubKey
0x180011612  mov     rcx, rsi; hKey
0x180011615  call    cs:__imp_RegOpenKeyExW
0x18001161b  test    eax, eax
0x18001161d  jz      short loc_180011627
0x18001161f  mov     ecx, eax; dwErrCode
0x180011621  call    cs:__imp_SetLastError
0x180011627  mov     rdi, [rbp+47h+hKey]
0x18001162b  mov     ebx, r12d
0x18001162e  test    rdi, rdi
0x180011631  setnz   bl
0x180011634  test    rdi, rdi
0x180011637  jz      loc_180011831
0x18001163d  lea     rdx, [rbp+47h+var_88]
0x180011641  mov     dword ptr [rbp+47h+var_88], 0FFFFFFFFh
0x180011648  mov     rcx, r15
0x18001164b  call    ISDKEnumInfoKey
0x180011650  mov     r13d, dword ptr [rbp+47h+var_88]
0x180011654  mov     rsi, rax
0x180011657  mov     [rbp+47h+var_50], rax
0x18001165b  mov     dword ptr [rbp+47h+var_88], r13d
0x18001165f  test    rax, rax
0x180011662  jz      short loc_1800116AB
0x180011664  test    r13d, r13d
0x180011667  jz      short loc_1800116AB
0x180011669  mov     r12d, ebx
0x18001166c  mov     r9, [rsi]
0x18001166f  mov     r8, rdi
0x180011672  mov     eax, [rbp+47h+arg_20]
0x180011675  mov     rdx, r9
0x180011678  mov     [rsp+0E0h+samDesired], 0
0x180011680  mov     rcx, r15
0x180011683  mov     dword ptr [rsp+0E0h+phkResult], eax
0x180011687  call    ISDKRegCopyKey
0x18001168c  neg     eax
0x18001168e  sbb     ebx, ebx
0x180011690  and     ebx, r12d
0x180011693  jz      loc_180011786
0x180011699  inc     r14d
0x18001169c  add     rsi, 20h ; ' '
0x1800116a0  mov     r12d, ebx
0x1800116a3  cmp     r14d, r13d
0x1800116a6  jb      short loc_18001166C
0x1800116a8  xor     r12d, r12d
0x1800116ab  lea     rdx, [rbp+47h+arg_28]
0x1800116af  mov     dword ptr [rbp+47h+arg_28], 0FFFFFFFFh
0x1800116b6  mov     rcx, r15
0x1800116b9  call    ISDKEnumInfoValue
0x1800116be  mov     r14d, dword ptr [rbp+47h+arg_28]
0x1800116c2  mov     rsi, rax
0x1800116c5  mov     [rbp+47h+var_58], rax
0x1800116c9  mov     dword ptr [rbp+47h+arg_28], r14d
0x1800116cd  test    rax, rax
0x1800116d0  jz      loc_180011806
0x1800116d6  test    r14d, r14d
0x1800116d9  jz      loc_180011806
0x1800116df  mov     r13d, [rbp+47h+arg_20]
0x1800116e3  and     r13d, 4
0x1800116e7  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x1800116eb  mov     rcx, [rbp+47h+arg_10]; hKey
0x1800116ef  mov     [rbp+47h+dwDisposition], 0
0x1800116f6  test    r13d, r13d
0x1800116f9  jz      loc_1800117C4
0x1800116ff  mov     [rbp+47h+Type], 0
0x180011706  mov     r9d, 1; samDesired
0x18001170c  mov     [rbp+47h+cbData], 0
0x180011713  xor     r8d, r8d; ulOptions
0x180011716  mov     rax, [rsi]
0x180011719  mov     [rbp+47h+Block], rax
0x18001171d  lea     rax, [rbp+47h+var_60]
0x180011721  mov     [rsp+0E0h+phkResult], rax; phkResult
0x180011726  mov     [rbp+47h+var_60], 0
0x18001172e  call    cs:__imp_RegOpenKeyExW
0x180011734  test    eax, eax
0x180011736  jz      short loc_180011740
0x180011738  mov     ecx, eax; dwErrCode
0x18001173a  call    cs:__imp_SetLastError
0x180011740  mov     r14, [rbp+47h+var_60]
0x180011744  test    r14, r14
0x180011747  jz      short loc_180011791
0x180011749  mov     rdx, [rbp+47h+Block]; lpValueName
0x18001174d  lea     r9, [rbp+47h+cbData]; lpcbData
0x180011751  lea     r8, [rbp+47h+Type]; lpType
0x180011755  mov     rcx, r14; hKey
0x180011758  call    ISDKQueryRegValue
0x18001175d  mov     rcx, r14; hKey
0x180011760  mov     [rbp+47h+Block], rax
0x180011764  call    cs:__imp_RegCloseKey
0x18001176a  mov     rax, [rbp+47h+Block]
0x18001176e  test    rax, rax
0x180011771  jz      short loc_180011791
0x180011773  mov     rcx, rax; Block
0x180011776  call    free_0
0x18001177b  mov     ebx, 1
0x180011780  mov     r14d, dword ptr [rbp+47h+arg_28]
0x180011784  jmp     short loc_1800117EB
0x180011786  mov     r14d, dword ptr [rbp+47h+arg_28]
0x18001178a  xor     ebx, ebx
0x18001178c  jmp     loc_180011831
0x180011791  mov     r9, [rsi+10h]
0x180011795  lea     rax, [rbp+47h+dwDisposition]
0x180011799  mov     r8, [rsi]
0x18001179c  mov     rdx, [rbp+47h+lpSubKey]
0x1800117a0  mov     rcx, [rbp+47h+arg_10]
0x1800117a4  mov     [rsp+40h], rax
0x1800117a9  mov     eax, [rsi+18h]
0x1800117ac  mov     [rsp+0E0h+samDesired], eax
0x1800117b0  mov     eax, [rsi+8]
0x1800117b3  mov     dword ptr [rsp+0E0h+phkResult], eax
0x1800117b7  call    ISDKSetRegValue
0x1800117bc  neg     eax
0x1800117be  sbb     ecx, ecx
0x1800117c0  and     ebx, ecx
0x1800117c2  jmp     short loc_180011780
0x1800117c4  mov     r9, [rsi+10h]
0x1800117c8  lea     rax, [rbp+47h+dwDisposition]
0x1800117cc  mov     r8, [rsi]
0x1800117cf  mov     [rsp+40h], rax
0x1800117d4  mov     eax, [rsi+18h]
0x1800117d7  mov     [rsp+0E0h+samDesired], eax
0x1800117db  mov     eax, [rsi+8]
0x1800117de  mov     dword ptr [rsp+0E0h+phkResult], eax
0x1800117e2  call    ISDKSetRegValue
0x1800117e7  test    eax, eax
0x1800117e9  jz      short loc_18001182B
0x1800117eb  test    ebx, ebx
0x1800117ed  jz      short loc_18001182D
0x1800117ef  inc     r12d
0x1800117f2  add     rsi, 20h ; ' '
0x1800117f6  cmp     r12d, r14d
0x1800117f9  jb      loc_1800116E7
0x1800117ff  mov     r13d, dword ptr [rbp+47h+var_88]
0x180011803  xor     r12d, r12d
0x180011806  test    byte ptr [rbp+47h+arg_20], 1
0x18001180a  jz      short loc_180011831
0x18001180c  mov     rdx, [rbp+47h+arg_8]; lpSubKey
0x180011810  mov     rcx, [rbp+47h+arg_0]; hKey
0x180011814  call    cs:__imp_RegDeleteKeyW
0x18001181a  test    eax, eax
0x18001181c  jz      short loc_180011831
0x18001181e  mov     ecx, eax; dwErrCode
0x180011820  call    cs:__imp_SetLastError
0x180011826  mov     ebx, r12d
0x180011829  jmp     short loc_180011831
0x18001182b  xor     ebx, ebx
0x18001182d  mov     r13d, dword ptr [rbp+47h+var_88]
0x180011831  mov     rcx, r15; hKey
0x180011834  call    cs:__imp_RegCloseKey
0x18001183a  test    rdi, rdi
0x18001183d  jz      short loc_180011848
0x18001183f  mov     rcx, rdi; hKey
0x180011842  call    cs:__imp_RegCloseKey
0x180011848  mov     edx, r14d
0x18001184b  lea     rcx, [rbp+47h+var_58]
0x18001184f  call    ISDKEnumInfoValueFree
0x180011854  mov     edx, r13d
0x180011857  lea     rcx, [rbp+47h+var_50]
0x18001185b  call    ISDKEnumInfoKeyFree
0x180011860  mov     eax, ebx
0x180011862  add     rsp, 0A8h
0x180011869  pop     r15
0x18001186b  pop     r14
0x18001186d  pop     r13
0x18001186f  pop     r12
0x180011871  pop     rdi
0x180011872  pop     rsi
0x180011873  pop     rbx
0x180011874  pop     rbp
0x180011875  retn
0x180011876  mov     rdi, r12
0x180011879  jmp     short loc_18001181E
```
