# WicaPostInstallp_SetupNotifications(HKEY__ *,int,int)

- ea: `0x1800aea50`
- end: `0x1800aef24`
- name: `?WicaPostInstallp_SetupNotifications@@YAKPEAUHKEY__@@HH@Z`
- size: `1236`
- prototype: `unsigned int __fastcall(HKEY hkey, int, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800ae890`
- `0x1800af3d0`

## callees

- `0x180012920`
- `0x1800212b0`
- `0x180056262`
- `0x18007a9cf`
- `0x1800ae594`
- `0x1800ae97c`
- `0x1800aea50`
- `0x1800aef2c`
- `0x1800ead68`

## import_xrefs

- `ntdll!RtlReAllocateHeap` at `0x1800aed34`
- `ntdll!RtlReAllocateHeap` at `0x1800aed34`
- `ntdll!RtlAllocateHeap` at `0x1800aed14`
- `ntdll!RtlAllocateHeap` at `0x1800aed14`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800aeb86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800aeb86`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aed92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aedda`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aed92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800aedda`

## string_xrefs

- `0x1800aeb90`: `RegDeleteKeyEx Failed [%d]`
- `0x1800aea92`: `WicaPostInstallp_SetupNotifications`
- `0x1800aeaaf`: `WicaPostInstallp_SetupNotifications`
- `0x1800aee8b`: `WicaPostInstallp_ShowApphelps Failed [%d]`
- `0x1800aee31`: `WicaPostInstallp_SetInitialized Failed [%d]`
- `0x1800aeec4`: `WicaPostInstallp_SetInitialized Failed [%d]`
- `0x1800aee13`: `SdbTagExeForReinstallUpgrade Failed [%ls]`

## pseudocode

```c
__int64 __fastcall WicaPostInstallp_SetupNotifications(HKEY hkey, __int64 a2, int a3)
{
  unsigned int ValueW; // edi
  ULONGLONG i; // r15
  ULONGLONG v6; // rbx
  char *v7; // rdi
  ULONGLONG v8; // rbx
  ULONGLONG v9; // rcx
  unsigned __int64 v10; // rbx
  ULONGLONG v11; // rbx
  size_t v12; // r12
  PVOID v13; // rax
  PVOID Heap; // rdi
  int v15; // eax
  int v16; // ecx
  const char *v17; // r9
  int v18; // r8d
  bool v19; // zf
  const char *v20; // r9
  int v21; // r8d
  unsigned int v23; // [rsp+40h] [rbp-28h] BYREF
  int v24; // [rsp+44h] [rbp-24h] BYREF
  ULONGLONG pullResult; // [rsp+48h] [rbp-20h] BYREF
  ULONGLONG Size[3]; // [rsp+50h] [rbp-18h] BYREF
  int pvData; // [rsp+B0h] [rbp+48h] BYREF
  DWORD pcbData; // [rsp+B8h] [rbp+50h] BYREF
  int v29; // [rsp+C0h] [rbp+58h]
  unsigned int v30; // [rsp+C8h] [rbp+60h] BYREF

  v29 = a3;
  ValueW = 0;
  v30 = 0;
  v23 = 0;
  pvData = 0;
  v24 = 0;
  pcbData = 0;
  if ( hkey )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= xmmword_1801598D8 )
        return ValueW;
      pullResult = 0;
      if ( ULongLongMult((ULONGLONG)*(&xmmword_1801598C8 + 1), i, &pullResult) < 0
        || (v6 = *((_QWORD *)&xmmword_1801598E8 + 1) + pullResult,
            *((_QWORD *)&xmmword_1801598E8 + 1) + pullResult < *((_QWORD *)&xmmword_1801598E8 + 1)) )
      {
        v6 = 0;
      }
      if ( ((*(_DWORD *)(v6 + 8228) - 8) & 0xFFFFFFF7) != 0
        && *(_DWORD *)(v6 + 8236)
        && *(_DWORD *)(v6 + 8240)
        && !WicaPostInstallp_GetNTFSFileID((const unsigned __int16 *)(v6 + 7196), &v30, &v23)
        && (v30 != *(_DWORD *)(v6 + 8236) || v23 != *(_DWORD *)(v6 + 8240)) )
      {
        break;
      }
      pcbData = 4;
      ValueW = RegGetValueW(hkey, (LPCWSTR)(v6 + 7716), L"CentralNotificationInit", 0x20000010u, 0, &pvData, &pcbData);
      if ( (ValueW & 0xFFFFFFFD) != 0 )
      {
        v20 = "RegGetValue Failed [%d]";
        v21 = 566;
        goto LABEL_60;
      }
      pcbData = 4;
      ValueW = RegGetValueW(hkey, (LPCWSTR)(v6 + 7716), L"RuntimeNotificationInit", 0x20000010u, 0, &v24, &pcbData);
      if ( (ValueW & 0xFFFFFFFD) != 0 )
      {
        v20 = "RegGetValueFailed [%d]";
        v21 = 583;
LABEL_60:
        AslLogCallPrintf(1, (unsigned int)"WicaPostInstallp_SetupNotifications", v21, (_DWORD)v20);
        return ValueW;
      }
      ValueW = 0;
      if ( !v24 && v29 && *(_DWORD *)(v6 + 8228) == 1 )
      {
        v15 = SdbTagExeForReinstallUpgrade(v6 + 7196);
        v16 = 1;
        if ( v15 )
        {
          if ( (unsigned int)WicaPostInstallp_SetInitialized(1, hkey, v6 + 7716) )
            AslLogCallPrintf(
              1,
              (unsigned int)"WicaPostInstallp_SetupNotifications",
              605,
              (unsigned int)"WicaPostInstallp_SetInitialized Failed [%d]");
          v17 = "ADS set for %ls and initialization bit set.";
          v18 = 613;
          v16 = 3;
        }
        else
        {
          v17 = "SdbTagExeForReinstallUpgrade Failed [%ls]";
          v18 = 595;
        }
        AslLogCallPrintf(v16, (unsigned int)"WicaPostInstallp_SetupNotifications", v18, (_DWORD)v17);
      }
      v19 = *(_DWORD *)(v6 + 8232) == 0;
      if ( !*(_DWORD *)(v6 + 8232) )
      {
        if ( !pvData && (unsigned int)WicaPostInstallp_ShowApphelps((wchar_t *)v6) )
          AslLogCallPrintf(
            1,
            (unsigned int)"WicaPostInstallp_SetupNotifications",
            630,
            (unsigned int)"WicaPostInstallp_ShowApphelps Failed [%d]");
        v19 = *(_DWORD *)(v6 + 8232) == 0;
      }
      if ( !v19 && !pvData && (unsigned int)WicaPostInstallp_SetInitialized(0, hkey, v6 + 7716) )
        AslLogCallPrintf(
          1,
          (unsigned int)"WicaPostInstallp_SetupNotifications",
          646,
          (unsigned int)"WicaPostInstallp_SetInitialized Failed [%d]");
LABEL_57:
      ;
    }
    AslLogCallPrintf(
      1,
      (unsigned int)"WicaPostInstallp_SetupNotifications",
      515,
      (unsigned int)"Error: The NTFS file IDs don't match. Skipping this EXE.");
    if ( RegDeleteKeyExW(hkey, (LPCWSTR)(v6 + 7716), 0x100u, 0) )
      AslLogCallPrintf(
        1,
        (unsigned int)"WicaPostInstallp_SetupNotifications",
        525,
        (unsigned int)"RegDeleteKeyEx Failed [%d]");
    if ( i >= xmmword_1801598D8
      || (pullResult = 0, ULongLongMult((ULONGLONG)*(&xmmword_1801598C8 + 1), i, &pullResult) < 0) )
    {
LABEL_36:
      --i;
      goto LABEL_57;
    }
    v7 = (char *)(*((_QWORD *)&xmmword_1801598E8 + 1) + pullResult);
    if ( *((_QWORD *)&xmmword_1801598E8 + 1) + pullResult >= *((_QWORD *)&xmmword_1801598E8 + 1) )
    {
      v8 = xmmword_1801598D8 + ~i;
      Size[0] = v8;
      if ( !v8 )
      {
LABEL_24:
        memset_0(&v7[v8], 0, (size_t)*(&xmmword_1801598C8 + 1));
        v9 = xmmword_1801598D8 - 1;
        xmmword_1801598D8 = v9;
        if ( v9 > 0x10 )
        {
          v10 = *(&xmmword_1801598D8 + 1);
          if ( (unsigned __int64)*(&xmmword_1801598C8 + 1) * *(&xmmword_1801598D8 + 1) >= 0x400
            && v9 < *(&xmmword_1801598D8 + 1) >> 2 )
          {
            Size[0] = 0;
            if ( ULongLongMult(*(&xmmword_1801598D8 + 1), (ULONGLONG)*(&xmmword_1801598C8 + 1), &pullResult) >= 0 )
            {
              v11 = v10 >> 1;
              if ( ULongLongMult(v11, (ULONGLONG)*(&xmmword_1801598C8 + 1), Size) >= 0 )
              {
                v12 = Size[0];
                if ( *((_QWORD *)&xmmword_1801598E8 + 1) )
                {
                  Heap = RtlReAllocateHeap(xmmword_1801598C8, 0, *((PVOID *)&xmmword_1801598E8 + 1), Size[0]);
                }
                else
                {
                  v13 = RtlAllocateHeap(xmmword_1801598C8, 0, Size[0]);
                  Heap = v13;
                  if ( v13 )
                    memset_0(v13, 0, v12);
                }
                if ( Heap )
                {
                  *((_QWORD *)&xmmword_1801598E8 + 1) = Heap;
                  *(&xmmword_1801598D8 + 1) = v11;
                }
              }
            }
          }
        }
        goto LABEL_35;
      }
      if ( ULongLongMult(xmmword_1801598D8 + ~i, (ULONGLONG)*(&xmmword_1801598C8 + 1), Size) >= 0 )
      {
        pullResult = 0;
        if ( ULongLongMult((ULONGLONG)*(&xmmword_1801598C8 + 1), i + 1, &pullResult) >= 0
          && *((_QWORD *)&xmmword_1801598E8 + 1) + pullResult >= *((_QWORD *)&xmmword_1801598E8 + 1) )
        {
          v8 = Size[0];
          memmove_0(v7, (const void *)(*((_QWORD *)&xmmword_1801598E8 + 1) + pullResult), Size[0]);
          goto LABEL_24;
        }
      }
    }
LABEL_35:
    ValueW = 0;
    goto LABEL_36;
  }
  ValueW = 1359;
  AslLogCallPrintf(
    1,
    (unsigned int)"WicaPostInstallp_SetupNotifications",
    484,
    (unsigned int)"Null arguments passed in.");
  return ValueW;
}

```

## disassembly

```asm
0x1800aea50  mov     [rsp-40h+arg_10], r8d
0x1800aea55  mov     [rsp-40h+arg_8], edx
0x1800aea59  push    rbp
0x1800aea5a  push    rbx
0x1800aea5b  push    rsi
0x1800aea5c  push    rdi
0x1800aea5d  push    r12
0x1800aea5f  push    r13
0x1800aea61  push    r14
0x1800aea63  push    r15
0x1800aea65  mov     rbp, rsp
0x1800aea68  sub     rsp, 68h
0x1800aea6c  xor     edi, edi
0x1800aea6e  mov     r13, rcx
0x1800aea71  mov     [rbp+arg_18], edi
0x1800aea74  mov     [rbp+var_28], edi
0x1800aea77  mov     [rbp+arg_0], edi
0x1800aea7a  mov     [rbp+var_24], edi
0x1800aea7d  mov     [rbp+arg_8], edi
0x1800aea80  test    rcx, rcx
0x1800aea83  jnz     short loc_1800AEAAC
0x1800aea85  lea     r9, aNullArgumentsP; "Null arguments passed in."
0x1800aea8c  mov     r8d, 1E4h
0x1800aea92  lea     rdx, aWicapostinstal_0; "WicaPostInstallp_SetupNotifications"
0x1800aea99  mov     edi, 54Fh
0x1800aea9e  lea     ecx, [r13+1]
0x1800aeaa2  call    AslLogCallPrintf
0x1800aeaa7  jmp     loc_1800AEF11
0x1800aeaac  mov     r15, rdi
0x1800aeaaf  lea     r14, aWicapostinstal_0; "WicaPostInstallp_SetupNotifications"
0x1800aeab6  mov     esi, 1
0x1800aeabb  cmp     r15, qword ptr cs:xmmword_1801598D8
0x1800aeac2  jnb     loc_1800AEF11
0x1800aeac8  mov     rcx, qword ptr cs:xmmword_1801598C8+8; ullMultiplicand
0x1800aeacf  lea     r8, [rbp+pullResult]; pullResult
0x1800aead3  mov     rdx, r15; ullMultiplier
0x1800aead6  mov     [rbp+pullResult], rdi
0x1800aeada  call    ULongLongMult
0x1800aeadf  test    eax, eax
0x1800aeae1  js      short loc_1800AEAF7
0x1800aeae3  mov     rbx, [rbp+pullResult]
0x1800aeae7  add     rbx, qword ptr cs:xmmword_1801598E8+8
0x1800aeaee  cmp     rbx, qword ptr cs:xmmword_1801598E8+8
0x1800aeaf5  jnb     short loc_1800AEAFA
0x1800aeaf7  mov     rbx, rdi
0x1800aeafa  mov     eax, [rbx+2024h]
0x1800aeb00  sub     eax, 8
0x1800aeb03  test    eax, 0FFFFFFF7h
0x1800aeb08  jz      loc_1800AED5A
0x1800aeb0e  cmp     [rbx+202Ch], edi
0x1800aeb14  jz      loc_1800AED5A
0x1800aeb1a  cmp     [rbx+2030h], edi
0x1800aeb20  jz      loc_1800AED5A
0x1800aeb26  lea     rcx, [rbx+1C1Ch]; unsigned __int16 *
0x1800aeb2d  lea     r8, [rbp+var_28]; unsigned int *
0x1800aeb31  lea     rdx, [rbp+arg_18]; unsigned int *
0x1800aeb35  call    ?WicaPostInstallp_GetNTFSFileID@@YAKPEBGPEAK1@Z; WicaPostInstallp_GetNTFSFileID(ushort const *,ulong *,ulong *)
0x1800aeb3a  test    eax, eax
0x1800aeb3c  jnz     loc_1800AED5A
0x1800aeb42  mov     eax, [rbx+202Ch]
0x1800aeb48  cmp     [rbp+arg_18], eax
0x1800aeb4b  jnz     short loc_1800AEB5C
0x1800aeb4d  mov     eax, [rbx+2030h]
0x1800aeb53  cmp     [rbp+var_28], eax
0x1800aeb56  jz      loc_1800AED5A
0x1800aeb5c  lea     r9, aErrorTheNtfsFi; "Error: The NTFS file IDs don't match. S"...
0x1800aeb63  mov     r8d, 203h
0x1800aeb69  mov     rdx, r14
0x1800aeb6c  mov     ecx, esi
0x1800aeb6e  call    AslLogCallPrintf
0x1800aeb73  lea     rdx, [rbx+1E24h]; lpSubKey
0x1800aeb7a  xor     r9d, r9d; Reserved
0x1800aeb7d  mov     r8d, 100h; samDesired
0x1800aeb83  mov     rcx, r13; hKey
0x1800aeb86  call    cs:__imp_RegDeleteKeyExW
0x1800aeb8c  test    eax, eax
0x1800aeb8e  jz      short loc_1800AEBAB
0x1800aeb90  lea     r9, aRegdeletekeyex; "RegDeleteKeyEx Failed [%d]"
0x1800aeb97  mov     dword ptr [rsp+68h+pdwType], eax
0x1800aeb9b  mov     r8d, 20Dh
0x1800aeba1  mov     rdx, r14
0x1800aeba4  mov     ecx, esi
0x1800aeba6  call    AslLogCallPrintf
0x1800aebab  cmp     r15, qword ptr cs:xmmword_1801598D8
0x1800aebb2  jnb     loc_1800AED52
0x1800aebb8  mov     rcx, qword ptr cs:xmmword_1801598C8+8; ullMultiplicand
0x1800aebbf  lea     r8, [rbp+pullResult]; pullResult
0x1800aebc3  mov     rdx, r15; ullMultiplier
0x1800aebc6  mov     [rbp+pullResult], rdi
0x1800aebca  call    ULongLongMult
0x1800aebcf  test    eax, eax
0x1800aebd1  js      loc_1800AED52
0x1800aebd7  mov     rdi, [rbp+pullResult]
0x1800aebdb  add     rdi, qword ptr cs:xmmword_1801598E8+8
0x1800aebe2  cmp     rdi, qword ptr cs:xmmword_1801598E8+8
0x1800aebe9  jb      loc_1800AED50
0x1800aebef  mov     rbx, r15
0x1800aebf2  not     rbx
0x1800aebf5  add     rbx, qword ptr cs:xmmword_1801598D8
0x1800aebfc  mov     [rbp+Size], rbx
0x1800aec00  jz      short loc_1800AEC68
0x1800aec02  mov     rdx, qword ptr cs:xmmword_1801598C8+8; ullMultiplier
0x1800aec09  lea     r8, [rbp+Size]; pullResult
0x1800aec0d  mov     rcx, rbx; ullMultiplicand
0x1800aec10  call    ULongLongMult
0x1800aec15  test    eax, eax
0x1800aec17  js      loc_1800AED50
0x1800aec1d  mov     rcx, qword ptr cs:xmmword_1801598C8+8; ullMultiplicand
0x1800aec24  lea     rdx, [r15+1]; ullMultiplier
0x1800aec28  lea     r8, [rbp+pullResult]; pullResult
0x1800aec2c  mov     [rbp+pullResult], 0
0x1800aec34  call    ULongLongMult
0x1800aec39  test    eax, eax
0x1800aec3b  js      loc_1800AED50
0x1800aec41  mov     rdx, [rbp+pullResult]
0x1800aec45  add     rdx, qword ptr cs:xmmword_1801598E8+8; Src
0x1800aec4c  cmp     rdx, qword ptr cs:xmmword_1801598E8+8
0x1800aec53  jb      loc_1800AED50
0x1800aec59  mov     rbx, [rbp+Size]
0x1800aec5d  mov     rcx, rdi; void *
0x1800aec60  mov     r8, rbx; Size
0x1800aec63  call    memmove_0
0x1800aec68  mov     r8, qword ptr cs:xmmword_1801598C8+8; Size
0x1800aec6f  lea     rcx, [rdi+rbx]; void *
0x1800aec73  xor     edx, edx; Val
0x1800aec75  call    memset_0
0x1800aec7a  mov     rcx, qword ptr cs:xmmword_1801598D8
0x1800aec81  dec     rcx
0x1800aec84  mov     qword ptr cs:xmmword_1801598D8, rcx
0x1800aec8b  cmp     rcx, 10h
0x1800aec8f  jbe     loc_1800AED50
0x1800aec95  mov     rbx, qword ptr cs:xmmword_1801598D8+8
0x1800aec9c  mov     rdx, qword ptr cs:xmmword_1801598C8+8; ullMultiplier
0x1800aeca3  mov     rax, rbx
0x1800aeca6  imul    rax, rdx
0x1800aecaa  cmp     rax, 400h
0x1800aecb0  jb      loc_1800AED50
0x1800aecb6  mov     rax, rbx
0x1800aecb9  shr     rax, 2
0x1800aecbd  cmp     rcx, rax
0x1800aecc0  jnb     loc_1800AED50
0x1800aecc6  lea     r8, [rbp+pullResult]; pullResult
0x1800aecca  mov     [rbp+Size], 0
0x1800aecd2  mov     rcx, rbx; ullMultiplicand
0x1800aecd5  call    ULongLongMult
0x1800aecda  test    eax, eax
0x1800aecdc  js      short loc_1800AED50
0x1800aecde  mov     rdx, qword ptr cs:xmmword_1801598C8+8; ullMultiplier
0x1800aece5  lea     r8, [rbp+Size]; pullResult
0x1800aece9  shr     rbx, 1
0x1800aecec  mov     rcx, rbx; ullMultiplicand
0x1800aecef  call    ULongLongMult
0x1800aecf4  test    eax, eax
0x1800aecf6  js      short loc_1800AED50
0x1800aecf8  mov     r8, qword ptr cs:xmmword_1801598E8+8; Ptr
0x1800aecff  xor     edx, edx; Flags
0x1800aed01  mov     r12, [rbp+Size]
0x1800aed05  mov     rcx, qword ptr cs:xmmword_1801598C8; Heap
0x1800aed0c  test    r8, r8
0x1800aed0f  jnz     short loc_1800AED31
0x1800aed11  mov     r8, r12; Size
0x1800aed14  call    cs:__imp_RtlAllocateHeap
0x1800aed1a  mov     rdi, rax
0x1800aed1d  test    rax, rax
0x1800aed20  jz      short loc_1800AED3D
0x1800aed22  mov     r8, r12; Size
0x1800aed25  xor     edx, edx; Val
0x1800aed27  mov     rcx, rax; void *
0x1800aed2a  call    memset_0
0x1800aed2f  jmp     short loc_1800AED3D
0x1800aed31  mov     r9, r12; Size
0x1800aed34  call    cs:__imp_RtlReAllocateHeap
0x1800aed3a  mov     rdi, rax
0x1800aed3d  test    rdi, rdi
0x1800aed40  jz      short loc_1800AED50
0x1800aed42  mov     qword ptr cs:xmmword_1801598E8+8, rdi
0x1800aed49  mov     qword ptr cs:xmmword_1801598D8+8, rbx
0x1800aed50  xor     edi, edi
0x1800aed52  sub     r15, rsi
0x1800aed55  jmp     loc_1800AEEDF
0x1800aed5a  lea     rax, [rbp+arg_8]
0x1800aed5e  mov     [rbp+arg_8], 4
0x1800aed65  mov     [rsp+68h+pcbData], rax; pcbData
0x1800aed6a  lea     r12, [rbx+1E24h]
0x1800aed71  lea     rax, [rbp+arg_0]
0x1800aed75  mov     r9d, 20000010h; dwFlags
0x1800aed7b  mov     [rsp+68h+pvData], rax; pvData
0x1800aed80  lea     r8, aCentralnotific; "CentralNotificationInit"
0x1800aed87  mov     rdx, r12; lpSubKey
0x1800aed8a  mov     [rsp+68h+pdwType], rdi; pdwType
0x1800aed8f  mov     rcx, r13; hkey
0x1800aed92  call    cs:__imp_RegGetValueW
0x1800aed98  mov     edi, eax
0x1800aed9a  test    eax, 0FFFFFFFDh
0x1800aed9f  jnz     loc_1800AEEF6
0x1800aeda5  lea     rax, [rbp+arg_8]
0x1800aeda9  mov     [rbp+arg_8], 4
0x1800aedb0  mov     [rsp+68h+pcbData], rax; pcbData
0x1800aedb5  lea     r8, aRuntimenotific; "RuntimeNotificationInit"
0x1800aedbc  lea     rax, [rbp+var_24]
0x1800aedc0  mov     r9d, 20000010h; dwFlags
0x1800aedc6  mov     [rsp+68h+pvData], rax; pvData
0x1800aedcb  mov     rdx, r12; lpSubKey
0x1800aedce  mov     rcx, r13; hkey
0x1800aedd1  mov     [rsp+68h+pdwType], 0; pdwType
0x1800aedda  call    cs:__imp_RegGetValueW
0x1800aede0  mov     edi, eax
0x1800aede2  test    eax, 0FFFFFFFDh
0x1800aede7  jnz     loc_1800AEEE7
0x1800aeded  xor     edi, edi
0x1800aedef  cmp     [rbp+var_24], edi
0x1800aedf2  jnz     short loc_1800AEE72
0x1800aedf4  cmp     [rbp+arg_10], edi
0x1800aedf7  jz      short loc_1800AEE72
0x1800aedf9  cmp     [rbx+2024h], esi
0x1800aedff  jnz     short loc_1800AEE72
0x1800aee01  lea     rcx, [rbx+1C1Ch]
0x1800aee08  call    SdbTagExeForReinstallUpgrade
0x1800aee0d  mov     ecx, esi
0x1800aee0f  test    eax, eax
0x1800aee11  jnz     short loc_1800AEE22
0x1800aee13  lea     r9, aSdbtagexeforre_0; "SdbTagExeForReinstallUpgrade Failed [%l"...
0x1800aee1a  mov     r8d, 253h
0x1800aee20  jmp     short loc_1800AEE5E
0x1800aee22  mov     r8, r12
0x1800aee25  mov     rdx, r13
0x1800aee28  call    ?WicaPostInstallp_SetInitialized@@YAKW4_NotificationType@@PEAUHKEY__@@PEBG@Z; WicaPostInstallp_SetInitialized(_NotificationType,HKEY__ *,ushort const *)
0x1800aee2d  test    eax, eax
0x1800aee2f  jz      short loc_1800AEE4C
0x1800aee31  lea     r9, aWicapostinstal_13; "WicaPostInstallp_SetInitialized Failed "...
0x1800aee38  mov     dword ptr [rsp+68h+pdwType], eax
0x1800aee3c  mov     r8d, 25Dh
0x1800aee42  mov     rdx, r14
0x1800aee45  mov     ecx, esi
0x1800aee47  call    AslLogCallPrintf
0x1800aee4c  lea     r9, aAdsSetForLsAnd; "ADS set for %ls and initialization bit "...
0x1800aee53  mov     r8d, 265h
0x1800aee59  mov     ecx, 3
0x1800aee5e  lea     rax, [rbx+180Ch]
0x1800aee65  mov     rdx, r14
0x1800aee68  mov     [rsp+68h+pdwType], rax
0x1800aee6d  call    AslLogCallPrintf
0x1800aee72  cmp     [rbx+2028h], edi
0x1800aee78  jnz     short loc_1800AEEAC
0x1800aee7a  cmp     [rbp+arg_0], edi
0x1800aee7d  jnz     short loc_1800AEEA6
0x1800aee7f  mov     rcx, rbx; struct _ExeEntry *
0x1800aee82  call    ?WicaPostInstallp_ShowApphelps@@YAKPEAU_ExeEntry@@@Z; WicaPostInstallp_ShowApphelps(_ExeEntry *)
0x1800aee87  test    eax, eax
0x1800aee89  jz      short loc_1800AEEA6
0x1800aee8b  lea     r9, aWicapostinstal_1; "WicaPostInstallp_ShowApphelps Failed [%"...
0x1800aee92  mov     dword ptr [rsp+68h+pdwType], eax
0x1800aee96  mov     r8d, 276h
0x1800aee9c  mov     rdx, r14
0x1800aee9f  mov     ecx, esi
0x1800aeea1  call    AslLogCallPrintf
0x1800aeea6  cmp     [rbx+2028h], edi
0x1800aeeac  jbe     short loc_1800AEEDF
0x1800aeeae  cmp     [rbp+arg_0], edi
0x1800aeeb1  jnz     short loc_1800AEEDF
0x1800aeeb3  mov     r8, r12
0x1800aeeb6  mov     rdx, r13
0x1800aeeb9  xor     ecx, ecx
0x1800aeebb  call    ?WicaPostInstallp_SetInitialized@@YAKW4_NotificationType@@PEAUHKEY__@@PEBG@Z; WicaPostInstallp_SetInitialized(_NotificationType,HKEY__ *,ushort const *)
0x1800aeec0  test    eax, eax
0x1800aeec2  jz      short loc_1800AEEDF
0x1800aeec4  lea     r9, aWicapostinstal_13; "WicaPostInstallp_SetInitialized Failed "...
0x1800aeecb  mov     dword ptr [rsp+68h+pdwType], eax
0x1800aeecf  mov     r8d, 286h
0x1800aeed5  mov     rdx, r14
0x1800aeed8  mov     ecx, esi
0x1800aeeda  call    AslLogCallPrintf
0x1800aeedf  add     r15, rsi
0x1800aeee2  jmp     loc_1800AEABB
0x1800aeee7  lea     r9, aReggetvaluefai; "RegGetValueFailed [%d]"
0x1800aeeee  mov     r8d, 247h
0x1800aeef4  jmp     short loc_1800AEF03
0x1800aeef6  lea     r9, aReggetvalueFai_0; "RegGetValue Failed [%d]"
0x1800aeefd  mov     r8d, 236h
0x1800aef03  mov     rdx, r14
0x1800aef06  mov     dword ptr [rsp+68h+pdwType], eax
0x1800aef0a  mov     ecx, esi
0x1800aef0c  call    AslLogCallPrintf
0x1800aef11  mov     eax, edi
0x1800aef13  add     rsp, 68h
0x1800aef17  pop     r15
0x1800aef19  pop     r14
0x1800aef1b  pop     r13
0x1800aef1d  pop     r12
0x1800aef1f  pop     rdi
0x1800aef20  pop     rsi
0x1800aef21  pop     rbx
0x1800aef22  pop     rbp
0x1800aef23  retn
```
