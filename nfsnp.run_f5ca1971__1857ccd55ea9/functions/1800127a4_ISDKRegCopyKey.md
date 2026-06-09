# ISDKRegCopyKey

- ea: `0x1800127a4`
- end: `0x180012ae1`
- name: `ISDKRegCopyKey`
- size: `829`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000c738`
- `0x1800127a4`

## callees

- `0x180001901`
- `0x180011fec`
- `0x180012240`
- `0x180012688`
- `0x1800127a4`
- `0x180012ae8`
- `0x180012b34`
- `0x180012c34`
- `0x180012cac`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012ab4`
- `KERNEL32!SetLastError` at `0x180012acd`
- `KERNEL32!SetLastError` at `0x180012ab4`
- `KERNEL32!SetLastError` at `0x180012acd`
- `ADVAPI32!RegCreateKeyExW` at `0x180012845`
- `ADVAPI32!RegCreateKeyExW` at `0x180012845`
- `ADVAPI32!RegDeleteKeyW` at `0x180012a9e`
- `ADVAPI32!RegDeleteKeyW` at `0x180012a9e`
- `ADVAPI32!RegCloseKey` at `0x18001285d`
- `ADVAPI32!RegCloseKey` at `0x180012995`
- `ADVAPI32!RegCloseKey` at `0x1800129c5`
- `ADVAPI32!RegCloseKey` at `0x1800129d9`
- `ADVAPI32!RegCloseKey` at `0x18001285d`
- `ADVAPI32!RegCloseKey` at `0x180012995`
- `ADVAPI32!RegCloseKey` at `0x1800129c5`
- `ADVAPI32!RegCloseKey` at `0x1800129d9`

## pseudocode

```c
__int64 ISDKRegCopyKey(HKEY a1, const WCHAR *a2, HKEY a3, const WCHAR *a4, int a5, ...)
{
  unsigned int v6; // esi
  unsigned int v7; // r13d
  unsigned int v9; // ebx
  HKEY v10; // r12
  LSTATUS v11; // eax
  __int64 v12; // r8
  HKEY v13; // rdi
  _QWORD *v14; // rsi
  unsigned int v15; // r14d
  BOOL v16; // r15d
  __int64 v17; // rax
  __int64 v18; // r8
  HKEY *v19; // rsi
  unsigned int v20; // r14d
  HKEY v21; // rax
  HKEY v22; // r12
  LSTATUS v24; // eax
  DWORD dwDisposition; // [rsp+58h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-21h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-19h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-15h] BYREF
  __int64 v29; // [rsp+70h] [rbp-11h] BYREF
  _QWORD *v30; // [rsp+78h] [rbp-9h] BYREF
  HKEY v31; // [rsp+80h] [rbp-1h]
  __int64 v36; // [rsp+100h] [rbp+7Fh] BYREF
  va_list va; // [rsp+100h] [rbp+7Fh]
  va_list va1; // [rsp+108h] [rbp+87h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v36 = va_arg(va1, _QWORD);
  dwDisposition = 0;
  v6 = 0;
  cbData = 0;
  Type = 0;
  v7 = 0;
  v30 = 0;
  v29 = 0;
  v9 = 1;
  v31 = (HKEY)ISDKRegOpenKey(a1, a2, a3, 131097);
  v10 = v31;
  if ( v31 )
  {
    hKey = 0;
    v11 = RegCreateKeyExW(a3, a4, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( v11 )
    {
      v13 = 0;
      SetLastError(v11);
      v9 = 0;
    }
    else
    {
      RegCloseKey(hKey);
      v13 = (HKEY)ISDKRegOpenKey(a3, a4, v12, 131078);
      v9 = v13 != 0;
      if ( v13 )
      {
        LODWORD(v36) = -1;
        v14 = (_QWORD *)ISDKEnumInfoKey(v10, (__int64 *)va);
        v30 = v14;
        if ( v14 && (_DWORD)v36 )
        {
          v15 = 0;
          v16 = v13 != 0;
          while ( 1 )
          {
            v9 = (unsigned int)ISDKRegCopyKey((_DWORD)v10, *v14, (_DWORD)v13, *v14, a5) != 0 && v16;
            if ( !v9 )
              break;
            ++v15;
            v14 += 4;
            v16 = v9;
            if ( v15 >= (unsigned int)v36 )
              goto LABEL_9;
          }
LABEL_16:
          v9 = 0;
        }
        else
        {
LABEL_9:
          LODWORD(hKey) = -1;
          v17 = ISDKEnumInfoValue(v10, &hKey);
          v7 = (unsigned int)hKey;
          v19 = (HKEY *)v17;
          v29 = v17;
          if ( v17 && (_DWORD)hKey )
          {
            v20 = 0;
            while ( 1 )
            {
              dwDisposition = 0;
              if ( (a5 & 4) != 0 )
              {
                Type = 0;
                cbData = 0;
                hKey = *v19;
                v21 = (HKEY)ISDKRegOpenKey(a3, a4, v18, 1);
                v22 = v21;
                if ( v21 && (hKey = (HKEY)ISDKQueryRegValue(v21, (LPCWSTR)hKey, &Type, &cbData), RegCloseKey(v22), hKey) )
                {
                  free_0(hKey);
                  v9 = 1;
                }
                else
                {
                  v9 &= -((unsigned int)ISDKSetRegValue(
                                          a3,
                                          a4,
                                          *v19,
                                          v19[2],
                                          *((_DWORD *)v19 + 2),
                                          *((_DWORD *)v19 + 6)) != 0);
                }
              }
              else if ( !(unsigned int)ISDKSetRegValue(a3, a4, *v19, v19[2], *((_DWORD *)v19 + 2), *((_DWORD *)v19 + 6)) )
              {
                goto LABEL_16;
              }
              if ( !v9 )
                break;
              ++v20;
              v19 += 4;
              if ( v20 >= v7 )
                goto LABEL_25;
            }
          }
          else
          {
LABEL_25:
            if ( (a5 & 1) != 0 )
            {
              v24 = RegDeleteKeyW(a1, a2);
              if ( v24 )
              {
                SetLastError(v24);
                v9 = 0;
              }
            }
          }
        }
        v6 = v36;
      }
    }
    RegCloseKey(v31);
    if ( v13 )
      RegCloseKey(v13);
  }
  ISDKEnumInfoValueFree(&v29, v7);
  ISDKEnumInfoKeyFree(&v30, v6);
  return v9;
}

```

## disassembly

```asm
0x1800127a4  mov     rax, rsp
0x1800127a7  mov     [rax+20h], r9
0x1800127ab  mov     [rax+18h], r8
0x1800127af  mov     [rax+10h], rdx
0x1800127b3  mov     [rax+8], rcx
0x1800127b7  push    rbp
0x1800127b8  push    rbx
0x1800127b9  push    rsi
0x1800127ba  push    rdi
0x1800127bb  push    r12
0x1800127bd  push    r13
0x1800127bf  push    r14
0x1800127c1  push    r15
0x1800127c3  lea     rbp, [rax-4Fh]
0x1800127c7  sub     rsp, 88h
0x1800127ce  xor     r15d, r15d
0x1800127d1  mov     rdi, r9
0x1800127d4  mov     r9d, 20019h
0x1800127da  mov     [rbp+47h+dwDisposition], r15d
0x1800127de  mov     esi, r15d
0x1800127e1  mov     [rbp+47h+cbData], r15d
0x1800127e5  mov     [rbp+47h+Type], r15d
0x1800127e9  mov     r13d, r15d
0x1800127ec  mov     [rbp+47h+var_50], r15
0x1800127f0  mov     r14, r8
0x1800127f3  mov     [rbp+47h+var_58], r15
0x1800127f7  mov     ebx, 1
0x1800127fc  call    ISDKRegOpenKey
0x180012801  mov     [rbp+47h+var_48], rax
0x180012805  mov     r12, rax
0x180012808  test    rax, rax
0x18001280b  jz      loc_1800129E5
0x180012811  lea     rax, [rbp+47h+dwDisposition]
0x180012815  mov     [rbp+47h+hKey], r15
0x180012819  mov     [rsp+40h], rax; lpdwDisposition
0x18001281e  xor     r9d, r9d; lpClass
0x180012821  lea     rax, [rbp+47h+hKey]
0x180012825  xor     r8d, r8d; Reserved
0x180012828  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001282d  mov     rdx, rdi; lpSubKey
0x180012830  mov     [rsp+0C0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180012835  mov     rcx, r14; hKey
0x180012838  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x180012840  mov     [rsp+0C0h+dwOptions], r15d; dwOptions
0x180012845  call    cs:__imp_RegCreateKeyExW
0x18001284c  nop     dword ptr [rax+rax+00h]
0x180012851  test    eax, eax
0x180012853  jnz     loc_180012AC8
0x180012859  mov     rcx, [rbp+47h+hKey]; hKey
0x18001285d  call    cs:__imp_RegCloseKey
0x180012864  nop     dword ptr [rax+rax+00h]
0x180012869  mov     r9d, 20006h
0x18001286f  mov     rdx, rdi
0x180012872  mov     rcx, r14
0x180012875  call    ISDKRegOpenKey
0x18001287a  test    rax, rax
0x18001287d  mov     ebx, r15d
0x180012880  mov     rdi, rax
0x180012883  setnz   bl
0x180012886  test    rax, rax
0x180012889  jz      loc_1800129C1
0x18001288f  lea     rdx, [rbp+47h+arg_28]
0x180012893  mov     dword ptr [rbp+47h+arg_28], 0FFFFFFFFh
0x18001289a  mov     rcx, r12
0x18001289d  call    ISDKEnumInfoKey
0x1800128a2  mov     rsi, rax
0x1800128a5  mov     [rbp+47h+var_50], rax
0x1800128a9  mov     eax, dword ptr [rbp+47h+arg_28]
0x1800128ac  mov     dword ptr [rbp+47h+arg_28], eax
0x1800128af  test    rsi, rsi
0x1800128b2  jz      short loc_1800128FB
0x1800128b4  test    eax, eax
0x1800128b6  jz      short loc_1800128FB
0x1800128b8  mov     r14d, r15d
0x1800128bb  mov     r15d, ebx
0x1800128be  mov     r9, [rsi]
0x1800128c1  mov     r8, rdi
0x1800128c4  mov     eax, [rbp+47h+arg_20]
0x1800128c7  mov     rdx, r9
0x1800128ca  mov     [rsp+0C0h+samDesired], r13d
0x1800128cf  mov     rcx, r12
0x1800128d2  mov     [rsp+0C0h+dwOptions], eax
0x1800128d6  call    ISDKRegCopyKey
0x1800128db  neg     eax
0x1800128dd  sbb     ebx, ebx
0x1800128df  and     ebx, r15d
0x1800128e2  jz      loc_1800129BC
0x1800128e8  inc     r14d
0x1800128eb  add     rsi, 20h ; ' '
0x1800128ef  mov     r15d, ebx
0x1800128f2  cmp     r14d, dword ptr [rbp+47h+arg_28]
0x1800128f6  jb      short loc_1800128BE
0x1800128f8  xor     r15d, r15d
0x1800128fb  lea     rdx, [rbp+47h+hKey]
0x1800128ff  mov     dword ptr [rbp+47h+hKey], 0FFFFFFFFh
0x180012906  mov     rcx, r12
0x180012909  call    ISDKEnumInfoValue
0x18001290e  mov     r13d, dword ptr [rbp+47h+hKey]
0x180012912  mov     rsi, rax
0x180012915  mov     [rbp+47h+var_58], rax
0x180012919  test    rax, rax
0x18001291c  jz      loc_180012A8C
0x180012922  test    r13d, r13d
0x180012925  jz      loc_180012A8C
0x18001292b  mov     r14d, r15d
0x18001292e  mov     r15d, [rbp+47h+arg_20]
0x180012932  and     r15d, 4
0x180012936  mov     rdx, [rbp+47h+arg_18]
0x18001293a  mov     rcx, [rbp+47h+arg_10]
0x18001293e  mov     [rbp+47h+dwDisposition], 0
0x180012945  test    r15d, r15d
0x180012948  jz      loc_180012A46
0x18001294e  mov     [rbp+47h+Type], 0
0x180012955  mov     r9d, 1
0x18001295b  mov     [rbp+47h+cbData], 0
0x180012962  mov     rax, [rsi]
0x180012965  mov     [rbp+47h+hKey], rax
0x180012969  call    ISDKRegOpenKey
0x18001296e  mov     r12, rax
0x180012971  test    rax, rax
0x180012974  jz      loc_180012A13
0x18001297a  mov     rdx, [rbp+47h+hKey]; lpValueName
0x18001297e  lea     r9, [rbp+47h+cbData]; lpcbData
0x180012982  lea     r8, [rbp+47h+Type]; lpType
0x180012986  mov     rcx, rax; hKey
0x180012989  call    ISDKQueryRegValue
0x18001298e  mov     rcx, r12; hKey
0x180012991  mov     [rbp+47h+hKey], rax
0x180012995  call    cs:__imp_RegCloseKey
0x18001299c  nop     dword ptr [rax+rax+00h]
0x1800129a1  mov     rax, [rbp+47h+hKey]
0x1800129a5  test    rax, rax
0x1800129a8  jz      short loc_180012A13
0x1800129aa  mov     rcx, rax; Block
0x1800129ad  call    free_0
0x1800129b2  mov     ebx, 1
0x1800129b7  jmp     loc_180012A71
0x1800129bc  xor     ebx, ebx
0x1800129be  mov     esi, dword ptr [rbp+47h+arg_28]
0x1800129c1  mov     rcx, [rbp+47h+var_48]; hKey
0x1800129c5  call    cs:__imp_RegCloseKey
0x1800129cc  nop     dword ptr [rax+rax+00h]
0x1800129d1  test    rdi, rdi
0x1800129d4  jz      short loc_1800129E5
0x1800129d6  mov     rcx, rdi; hKey
0x1800129d9  call    cs:__imp_RegCloseKey
0x1800129e0  nop     dword ptr [rax+rax+00h]
0x1800129e5  mov     edx, r13d
0x1800129e8  lea     rcx, [rbp+47h+var_58]
0x1800129ec  call    ISDKEnumInfoValueFree
0x1800129f1  mov     edx, esi
0x1800129f3  lea     rcx, [rbp+47h+var_50]
0x1800129f7  call    ISDKEnumInfoKeyFree
0x1800129fc  mov     eax, ebx
0x1800129fe  add     rsp, 88h
0x180012a05  pop     r15
0x180012a07  pop     r14
0x180012a09  pop     r13
0x180012a0b  pop     r12
0x180012a0d  pop     rdi
0x180012a0e  pop     rsi
0x180012a0f  pop     rbx
0x180012a10  pop     rbp
0x180012a11  retn
0x180012a13  mov     r9, [rsi+10h]
0x180012a17  lea     rax, [rbp+47h+dwDisposition]
0x180012a1b  mov     r8, [rsi]
0x180012a1e  mov     rdx, [rbp+47h+arg_18]
0x180012a22  mov     rcx, [rbp+47h+arg_10]
0x180012a26  mov     [rsp+40h], rax
0x180012a2b  mov     eax, [rsi+18h]
0x180012a2e  mov     [rsp+0C0h+samDesired], eax
0x180012a32  mov     eax, [rsi+8]
0x180012a35  mov     [rsp+0C0h+dwOptions], eax
0x180012a39  call    ISDKSetRegValue
0x180012a3e  neg     eax
0x180012a40  sbb     ecx, ecx
0x180012a42  and     ebx, ecx
0x180012a44  jmp     short loc_180012A71
0x180012a46  mov     r9, [rsi+10h]
0x180012a4a  lea     rax, [rbp+47h+dwDisposition]
0x180012a4e  mov     r8, [rsi]
0x180012a51  mov     [rsp+40h], rax
0x180012a56  mov     eax, [rsi+18h]
0x180012a59  mov     [rsp+0C0h+samDesired], eax
0x180012a5d  mov     eax, [rsi+8]
0x180012a60  mov     [rsp+0C0h+dwOptions], eax
0x180012a64  call    ISDKSetRegValue
0x180012a69  test    eax, eax
0x180012a6b  jz      loc_1800129BC
0x180012a71  test    ebx, ebx
0x180012a73  jz      loc_1800129BE
0x180012a79  inc     r14d
0x180012a7c  add     rsi, 20h ; ' '
0x180012a80  cmp     r14d, r13d
0x180012a83  jb      loc_180012936
0x180012a89  xor     r15d, r15d
0x180012a8c  test    byte ptr [rbp+47h+arg_20], 1
0x180012a90  jz      loc_1800129BE
0x180012a96  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x180012a9a  mov     rcx, [rbp+47h+arg_0]; hKey
0x180012a9e  call    cs:__imp_RegDeleteKeyW
0x180012aa5  nop     dword ptr [rax+rax+00h]
0x180012aaa  test    eax, eax
0x180012aac  jz      loc_1800129BE
0x180012ab2  mov     ecx, eax; dwErrCode
0x180012ab4  call    cs:__imp_SetLastError
0x180012abb  nop     dword ptr [rax+rax+00h]
0x180012ac0  mov     ebx, r15d
0x180012ac3  jmp     loc_1800129BE
0x180012ac8  mov     ecx, eax; dwErrCode
0x180012aca  mov     rdi, r15
0x180012acd  call    cs:__imp_SetLastError
0x180012ad4  nop     dword ptr [rax+rax+00h]
0x180012ad9  mov     ebx, r15d
0x180012adc  jmp     loc_1800129C1
```
