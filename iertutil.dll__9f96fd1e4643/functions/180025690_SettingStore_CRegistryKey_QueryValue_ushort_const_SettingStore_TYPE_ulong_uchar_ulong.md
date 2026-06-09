# SettingStore::CRegistryKey::QueryValue(ushort const *,SettingStore::TYPE,ulong,uchar *,ulong)

- ea: `0x180025690`
- end: `0x180025a3a`
- name: `?QueryValue@CRegistryKey@SettingStore@@UEAAJPEBGW4TYPE@2@KPEAEK@Z`
- size: `938`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180025690`
- `0x180025a40`
- `0x180025aec`
- `0x1800580e6`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800258bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800258ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025917`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025940`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800259f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a26`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800258bc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800258ee`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025917`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025940`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800259f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025a26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002570e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002575f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002570e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002575f`

## pseudocode

```c
__int64 __fastcall SettingStore::CRegistryKey::QueryValue(
        __int64 a1,
        const WCHAR *a2,
        unsigned int a3,
        __int16 a4,
        LPBYTE lpData,
        DWORD Size)
{
  HKEY v6; // rcx
  LSTATUS v9; // eax
  signed int v10; // ebx
  LSTATUS v12; // eax
  unsigned int *v13; // r9
  unsigned int v14; // r8d
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rdx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData[3]; // [rsp+34h] [rbp-CCh] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF

  v6 = *(HKEY *)(a1 + 16);
  Type = 0;
  cbData[0] = Size;
  if ( !a3 )
  {
    cbData[0] = 520;
    v9 = RegQueryValueExW(v6, a2, 0, &Type, (LPBYTE)Data, cbData);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v10 < 0 )
      return (unsigned int)v10;
    if ( Type != 1 )
    {
      if ( Type == 4 )
      {
        Type = *(_DWORD *)Data != 0;
LABEL_20:
        memcpy_0(lpData, &Type, Size);
        return (unsigned int)v10;
      }
      return (unsigned int)-2147023267;
    }
    v17 = cbData[0] >> 1;
    if ( !(cbData[0] >> 1) )
    {
      Data[0] = 0;
      goto LABEL_30;
    }
    if ( !Data[(unsigned int)(v17 - 1)] )
      goto LABEL_30;
    if ( (unsigned int)(v17 + 1) <= 0x104 )
    {
      Data[v17] = 0;
LABEL_30:
      v10 = 0;
      if ( CompareStringW(0x7Fu, 1u, L"yes", -1, Data, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"true", -1, Data, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"1", -1, Data, -1) == 2 )
      {
        Type = 1;
        goto LABEL_20;
      }
      if ( CompareStringW(0x7Fu, 1u, L"no", -1, Data, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"false", -1, Data, -1) == 2
        || CompareStringW(0x7Fu, 1u, L"0", -1, Data, -1) == 2 )
      {
        Type = 0;
        goto LABEL_20;
      }
      return (unsigned int)-2147023267;
    }
    return (unsigned int)-2147024662;
  }
  v12 = RegQueryValueExW(v6, a2, 0, &Type, lpData, cbData);
  v10 = v12;
  if ( v12 > 0 )
    v10 = (unsigned __int16)v12 | 0x80070000;
  if ( v10 >= 0 )
  {
    if ( !(unsigned int)SettingStore::IsEqualType(Type, a3) )
    {
      if ( (_DWORD)v13 == 3 && (a3 == 1 || a3 == 8) && cbData[0] == 4 )
        return 0;
      return (unsigned int)-2147023267;
    }
    v10 = 0;
    if ( (unsigned int)((_DWORD)v13 - 1) <= 1 )
    {
      v14 = Size >> 1;
      v15 = cbData[0] >> 1;
      if ( (_DWORD)v15 )
      {
        v16 = (unsigned int)(v15 - 1);
        goto LABEL_13;
      }
LABEL_36:
      if ( !v14 )
        return (unsigned int)-2147024662;
      *(_WORD *)lpData = 0;
      goto LABEL_14;
    }
    if ( (_DWORD)v13 == 7 )
    {
      v14 = Size >> 1;
      v15 = cbData[0] >> 1;
      if ( !(_DWORD)v15 )
        goto LABEL_36;
      if ( *(_WORD *)&lpData[2 * (unsigned int)(v15 - 1)] )
      {
        if ( (int)v15 + 2 > v14 )
          return (unsigned int)-2147024662;
        *(_WORD *)&lpData[2 * (unsigned int)v15] = 0;
        *(_WORD *)&lpData[2 * (unsigned int)(v15 + 1)] = 0;
        goto LABEL_14;
      }
      if ( (unsigned int)v15 >= 2 )
      {
        v16 = (unsigned int)(v15 - 2);
LABEL_13:
        if ( *(_WORD *)&lpData[2 * v16] )
        {
          if ( (int)v15 + 1 > v14 )
            return (unsigned int)-2147024662;
          *(_WORD *)&lpData[2 * v15] = 0;
        }
      }
    }
LABEL_14:
    if ( (unsigned int)((_DWORD)v13 - 1) <= 1 && (a4 & 0x100) != 0 )
      return (unsigned int)SettingStore::ExpandBufferInPlace((SettingStore *)lpData, Size, 0, v13);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180025690  mov     [rsp-8+arg_10], rbx
0x180025695  push    rbp
0x180025696  push    rsi
0x180025697  push    rdi
0x180025698  push    r12
0x18002569a  push    r13
0x18002569c  push    r14
0x18002569e  push    r15
0x1800256a0  lea     rbp, [rsp-160h]
0x1800256a8  sub     rsp, 260h
0x1800256af  mov     rax, cs:__security_cookie
0x1800256b6  xor     rax, rsp
0x1800256b9  mov     [rbp+190h+var_40], rax
0x1800256c0  mov     r15d, dword ptr [rbp+190h+Size]
0x1800256c7  lea     rax, [rsp+290h+cbData]
0x1800256cc  mov     rsi, [rbp+190h+arg_20]
0x1800256d3  xor     r13d, r13d
0x1800256d6  mov     rcx, [rcx+10h]; hKey
0x1800256da  mov     r12d, r9d
0x1800256dd  mov     [rsp+290h+Type], r13d
0x1800256e2  mov     r14d, r8d
0x1800256e5  mov     [rsp+290h+cbData], r15d
0x1800256ea  lea     r9, [rsp+290h+Type]; lpType
0x1800256ef  mov     [rsp+290h+lpcbData], rax; lpcbData
0x1800256f4  test    r8d, r8d
0x1800256f7  jnz     short loc_180025757
0x1800256f9  lea     rax, [rsp+290h+Data]
0x1800256fe  mov     [rsp+290h+cbData], 208h
0x180025706  xor     r8d, r8d; lpReserved
0x180025709  mov     [rsp+290h+lpData], rax; lpData
0x18002570e  call    cs:__imp_RegQueryValueExW
0x180025714  mov     ebx, eax
0x180025716  test    eax, eax
0x180025718  jle     short loc_180025723
0x18002571a  movzx   ebx, ax
0x18002571d  or      ebx, 80070000h
0x180025723  test    ebx, ebx
0x180025725  jns     loc_1800257EC
0x18002572b  mov     eax, ebx
0x18002572d  mov     rcx, [rbp+190h+var_40]
0x180025734  xor     rcx, rsp; StackCookie
0x180025737  call    __security_check_cookie
0x18002573c  mov     rbx, [rsp+290h+arg_10]
0x180025744  add     rsp, 260h
0x18002574b  pop     r15
0x18002574d  pop     r14
0x18002574f  pop     r13
0x180025751  pop     r12
0x180025753  pop     rdi
0x180025754  pop     rsi
0x180025755  pop     rbp
0x180025756  retn
0x180025757  xor     r8d, r8d; lpReserved
0x18002575a  mov     [rsp+290h+lpData], rsi; lpData
0x18002575f  call    cs:__imp_RegQueryValueExW
0x180025765  mov     ebx, eax
0x180025767  test    eax, eax
0x180025769  jle     short loc_180025774
0x18002576b  movzx   ebx, ax
0x18002576e  or      ebx, 80070000h
0x180025774  test    ebx, ebx
0x180025776  js      short loc_18002572B
0x180025778  mov     r9d, [rsp+290h+Type]
0x18002577d  mov     edx, r14d
0x180025780  mov     ecx, r9d
0x180025783  call    ?IsEqualType@SettingStore@@YAHKW4TYPE@1@@Z; SettingStore::IsEqualType(ulong,SettingStore::TYPE)
0x180025788  test    eax, eax
0x18002578a  jz      loc_180025862
0x180025790  mov     edx, [rsp+290h+cbData]
0x180025794  lea     eax, [r9-1]
0x180025798  mov     edi, 1
0x18002579d  mov     ebx, r13d
0x1800257a0  cmp     eax, edi
0x1800257a2  ja      short loc_180025822
0x1800257a4  mov     r8d, r15d
0x1800257a7  shr     r8d, 1
0x1800257aa  shr     edx, 1
0x1800257ac  jz      loc_180025959
0x1800257b2  lea     eax, [rdx-1]
0x1800257b5  cmp     [rsi+rax*2], r13w
0x1800257ba  jnz     loc_1800259B4
0x1800257c0  lea     eax, [r9-1]
0x1800257c4  cmp     eax, edi
0x1800257c6  ja      loc_18002572B
0x1800257cc  bt      r12d, 8
0x1800257d1  jnb     loc_18002572B
0x1800257d7  xor     r8d, r8d; unsigned int *
0x1800257da  mov     edx, r15d; Size
0x1800257dd  mov     rcx, rsi; this
0x1800257e0  call    ?ExpandBufferInPlace@SettingStore@@YAJPEAEKPEAK@Z; SettingStore::ExpandBufferInPlace(uchar *,ulong,ulong *)
0x1800257e5  mov     ebx, eax
0x1800257e7  jmp     loc_18002572B
0x1800257ec  mov     edi, 1
0x1800257f1  cmp     [rsp+290h+Type], edi
0x1800257f5  jz      short loc_180025876
0x1800257f7  cmp     [rsp+290h+Type], 4
0x1800257fc  jnz     short loc_18002586C
0x1800257fe  cmp     dword ptr [rsp+290h+Data], r13d
0x180025803  mov     eax, r13d
0x180025806  setnz   al
0x180025809  mov     [rsp+290h+Type], eax
0x18002580d  mov     r8, r15; Size
0x180025810  lea     rdx, [rsp+290h+Type]; Src
0x180025815  mov     rcx, rsi; void *
0x180025818  call    memcpy_0
0x18002581d  jmp     loc_18002572B
0x180025822  cmp     r9d, 7
0x180025826  jnz     short loc_1800257C0
0x180025828  mov     r8d, r15d
0x18002582b  shr     r8d, 1
0x18002582e  shr     edx, 1
0x180025830  jz      loc_180025959
0x180025836  lea     eax, [rdx-1]
0x180025839  cmp     [rsi+rax*2], r13w
0x18002583e  jz      loc_1800259A3
0x180025844  lea     eax, [rdx+2]
0x180025847  cmp     eax, r8d
0x18002584a  ja      loc_180025967
0x180025850  lea     eax, [rdx+1]
0x180025853  mov     [rsi+rdx*2], r13w
0x180025858  mov     [rsi+rax*2], r13w
0x18002585d  jmp     loc_1800257C0
0x180025862  cmp     r9d, 3
0x180025866  jz      loc_18002597C
0x18002586c  mov     ebx, 8007065Dh
0x180025871  jmp     loc_18002572B
0x180025876  mov     edx, [rsp+290h+cbData]
0x18002587a  shr     edx, 1
0x18002587c  jz      loc_180025971
0x180025882  lea     eax, [rdx-1]
0x180025885  cmp     [rsp+rax*2+290h+Data], r13w
0x18002588b  jnz     loc_1800259C6
0x180025891  or      r14d, 0FFFFFFFFh
0x180025895  lea     rax, [rsp+290h+Data]
0x18002589a  mov     r12d, 7Fh
0x1800258a0  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x1800258a5  mov     r9d, r14d; cchCount1
0x1800258a8  mov     [rsp+290h+lpData], rax; lpString2
0x1800258ad  mov     ecx, r12d; Locale
0x1800258b0  lea     r8, aYes; "yes"
0x1800258b7  mov     edx, edi; dwCmpFlags
0x1800258b9  mov     ebx, r13d
0x1800258bc  call    cs:__imp_CompareStringW
0x1800258c2  cmp     eax, 2
0x1800258c5  jnz     short loc_1800258D0
0x1800258c7  mov     [rsp+290h+Type], edi
0x1800258cb  jmp     loc_18002580D
0x1800258d0  lea     rax, [rsp+290h+Data]
0x1800258d5  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x1800258da  mov     r9d, r14d; cchCount1
0x1800258dd  mov     [rsp+290h+lpData], rax; lpString2
0x1800258e2  lea     r8, aTrue; "true"
0x1800258e9  mov     edx, edi; dwCmpFlags
0x1800258eb  mov     ecx, r12d; Locale
0x1800258ee  call    cs:__imp_CompareStringW
0x1800258f4  cmp     eax, 2
0x1800258f7  jz      short loc_1800258C7
0x1800258f9  lea     rax, [rsp+290h+Data]
0x1800258fe  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x180025903  mov     r9d, r14d; cchCount1
0x180025906  mov     [rsp+290h+lpData], rax; lpString2
0x18002590b  lea     r8, a1; "1"
0x180025912  mov     edx, edi; dwCmpFlags
0x180025914  mov     ecx, r12d; Locale
0x180025917  call    cs:__imp_CompareStringW
0x18002591d  cmp     eax, 2
0x180025920  jz      short loc_1800258C7
0x180025922  lea     rax, [rsp+290h+Data]
0x180025927  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x18002592c  mov     r9d, r14d; cchCount1
0x18002592f  mov     [rsp+290h+lpData], rax; lpString2
0x180025934  lea     r8, aNo_2; "no"
0x18002593b  mov     edx, edi; dwCmpFlags
0x18002593d  mov     ecx, r12d; Locale
0x180025940  call    cs:__imp_CompareStringW
0x180025946  cmp     eax, 2
0x180025949  jnz     loc_1800259DB
0x18002594f  mov     [rsp+290h+Type], r13d
0x180025954  jmp     loc_18002580D
0x180025959  cmp     r8d, edi
0x18002595c  jb      short loc_180025967
0x18002595e  mov     [rsi], r13w
0x180025962  jmp     loc_1800257C0
0x180025967  mov     ebx, 800700EAh
0x18002596c  jmp     loc_18002572B
0x180025971  mov     [rsp+290h+Data], r13w
0x180025977  jmp     loc_180025891
0x18002597c  mov     edi, 1
0x180025981  cmp     r14d, edi
0x180025984  jz      short loc_180025990
0x180025986  cmp     r14d, 8
0x18002598a  jnz     loc_18002586C
0x180025990  cmp     [rsp+290h+cbData], 4
0x180025995  jnz     loc_18002586C
0x18002599b  mov     ebx, r13d
0x18002599e  jmp     loc_18002572B
0x1800259a3  cmp     edx, 2
0x1800259a6  jb      loc_1800257C0
0x1800259ac  lea     eax, [rdx-2]
0x1800259af  jmp     loc_1800257B5
0x1800259b4  lea     eax, [rdx+1]
0x1800259b7  cmp     eax, r8d
0x1800259ba  ja      short loc_180025967
0x1800259bc  mov     [rsi+rdx*2], r13w
0x1800259c1  jmp     loc_1800257C0
0x1800259c6  lea     eax, [rdx+1]
0x1800259c9  cmp     eax, 104h
0x1800259ce  ja      short loc_180025967
0x1800259d0  mov     [rsp+rdx*2+290h+Data], r13w
0x1800259d6  jmp     loc_180025891
0x1800259db  lea     rax, [rsp+290h+Data]
0x1800259e0  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x1800259e5  mov     r9d, r14d; cchCount1
0x1800259e8  mov     [rsp+290h+lpData], rax; lpString2
0x1800259ed  lea     r8, aFalse; "false"
0x1800259f4  mov     edx, edi; dwCmpFlags
0x1800259f6  mov     ecx, r12d; Locale
0x1800259f9  call    cs:__imp_CompareStringW
0x1800259ff  cmp     eax, 2
0x180025a02  jz      loc_18002594F
0x180025a08  lea     rax, [rsp+290h+Data]
0x180025a0d  mov     dword ptr [rsp+290h+lpcbData], r14d; cchCount2
0x180025a12  mov     r9d, r14d; cchCount1
0x180025a15  mov     [rsp+290h+lpData], rax; lpString2
0x180025a1a  lea     r8, a0_0; "0"
0x180025a21  mov     edx, edi; dwCmpFlags
0x180025a23  mov     ecx, r12d; Locale
0x180025a26  call    cs:__imp_CompareStringW
0x180025a2c  cmp     eax, 2
0x180025a2f  jnz     loc_18002586C
0x180025a35  jmp     loc_18002594F
```
