# ProfileIsActive

- ea: `0x1800694fc`
- end: `0x1800696d6`
- name: `ProfileIsActive`
- size: `474`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18006ddcc`

## callees

- `0x1800694fc`
- `0x180069cc0`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800695a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800695a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800696aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800696aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800695ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069643`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800695ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180069643`

## string_xrefs

- `0x18006957a`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18006958c`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18006963c`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall ProfileIsActive(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  const WCHAR *v6; // rdx
  BYTE *v7; // rax
  __int64 v8; // rsi
  int v9; // edx
  int v10; // ecx
  BYTE *v11; // rax
  __int64 v12; // rdi
  int v13; // ecx
  int v14; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[528]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v20[528]; // [rsp+250h] [rbp+150h] BYREF

  cbData = 0;
  Type = 0;
  hKey = 0;
  v4 = 0;
  memset_0(Data, 0, 0x105u);
  memset_0(v20, 0, 0x105u);
  if ( a2 )
  {
    v5 = StateSepEnabled();
    v6 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v5 )
      v6 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
    {
      cbData = 520;
      if ( !RegQueryValueExW(hKey, L"AutoTriggerProfileEntryName", 0, &Type, Data, &cbData) && Type - 1 <= 1 )
      {
        cbData = 520;
        if ( !RegQueryValueExW(hKey, L"AutoTriggerProfilePhonebookPath", 0, &Type, v20, &cbData) && Type - 1 <= 1 )
        {
          v7 = Data;
          v8 = a1 - (_QWORD)Data;
          do
          {
            v9 = *(unsigned __int16 *)&v7[v8];
            v10 = *(unsigned __int16 *)v7 - v9;
            if ( v10 )
              break;
            v7 += 2;
          }
          while ( v9 );
          if ( !v10 )
          {
            v11 = v20;
            v12 = a2 - (_QWORD)v20;
            do
            {
              v13 = *(unsigned __int16 *)&v11[v12];
              v14 = *(unsigned __int16 *)v11 - v13;
              if ( v14 )
                break;
              v11 += 2;
            }
            while ( v13 );
            if ( !v14 )
              v4 = 1;
          }
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x1800694fc  push    rbp
0x1800694fe  push    rbx
0x1800694ff  push    rsi
0x180069500  push    rdi
0x180069501  push    r14
0x180069503  lea     rbp, [rsp-370h]
0x18006950b  sub     rsp, 470h
0x180069512  mov     rax, cs:__security_cookie
0x180069519  xor     rax, rsp
0x18006951c  mov     [rbp+390h+var_30], rax
0x180069523  mov     rdi, rdx
0x180069526  mov     [rsp+490h+cbData], 0
0x18006952e  mov     rsi, rcx
0x180069531  mov     [rsp+490h+Type], 0
0x180069539  mov     r14d, 105h
0x18006953f  mov     [rsp+490h+hKey], 0
0x180069548  mov     r8d, r14d; Size
0x18006954b  lea     rcx, [rsp+490h+Data]; void *
0x180069550  xor     edx, edx; Val
0x180069552  xor     ebx, ebx
0x180069554  call    memset_0
0x180069559  mov     r8d, r14d; Size
0x18006955c  lea     rcx, [rbp+390h+var_240]; void *
0x180069563  xor     edx, edx; Val
0x180069565  call    memset_0
0x18006956a  test    rdi, rdi
0x18006956d  jz      loc_1800696B6
0x180069573  call    StateSepEnabled
0x180069578  test    eax, eax
0x18006957a  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180069581  lea     rax, [rsp+490h+hKey]
0x180069586  mov     r9d, 20019h; samDesired
0x18006958c  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180069593  mov     [rsp+490h+phkResult], rax; phkResult
0x180069598  cmovz   rdx, rcx; lpSubKey
0x18006959c  xor     r8d, r8d; ulOptions
0x18006959f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800695a6  call    cs:__imp_RegOpenKeyExW
0x1800695ad  nop     dword ptr [rax+rax+00h]
0x1800695b2  test    eax, eax
0x1800695b4  jnz     loc_1800696A0
0x1800695ba  mov     rcx, [rsp+490h+hKey]; hKey
0x1800695bf  lea     rax, [rsp+490h+cbData]
0x1800695c4  mov     [rsp+490h+lpcbData], rax; lpcbData
0x1800695c9  lea     r9, [rsp+490h+Type]; lpType
0x1800695ce  lea     rax, [rsp+490h+Data]
0x1800695d3  mov     [rsp+490h+cbData], 208h
0x1800695db  xor     r8d, r8d; lpReserved
0x1800695de  mov     [rsp+490h+phkResult], rax; lpData
0x1800695e3  lea     rdx, aAutotriggerpro; "AutoTriggerProfileEntryName"
0x1800695ea  call    cs:__imp_RegQueryValueExW
0x1800695f1  nop     dword ptr [rax+rax+00h]
0x1800695f6  test    eax, eax
0x1800695f8  jnz     loc_1800696A0
0x1800695fe  mov     eax, [rsp+490h+Type]
0x180069602  lea     r14d, [rbx+1]
0x180069606  dec     eax
0x180069608  cmp     eax, r14d
0x18006960b  ja      loc_1800696A0
0x180069611  mov     rcx, [rsp+490h+hKey]; hKey
0x180069616  lea     rax, [rsp+490h+cbData]
0x18006961b  mov     [rsp+490h+lpcbData], rax; lpcbData
0x180069620  lea     r9, [rsp+490h+Type]; lpType
0x180069625  lea     rax, [rbp+390h+var_240]
0x18006962c  mov     [rsp+490h+cbData], 208h
0x180069634  xor     r8d, r8d; lpReserved
0x180069637  mov     [rsp+490h+phkResult], rax; lpData
0x18006963c  lea     rdx, aAutotriggerpro_1; "AutoTriggerProfilePhonebookPath"
0x180069643  call    cs:__imp_RegQueryValueExW
0x18006964a  nop     dword ptr [rax+rax+00h]
0x18006964f  test    eax, eax
0x180069651  jnz     short loc_1800696A0
0x180069653  mov     eax, [rsp+490h+Type]
0x180069657  dec     eax
0x180069659  cmp     eax, r14d
0x18006965c  ja      short loc_1800696A0
0x18006965e  lea     rax, [rsp+490h+Data]
0x180069663  sub     rsi, rax
0x180069666  movzx   ecx, word ptr [rax]
0x180069669  movzx   edx, word ptr [rax+rsi]
0x18006966d  sub     ecx, edx
0x18006966f  jnz     short loc_180069679
0x180069671  add     rax, 2
0x180069675  test    edx, edx
0x180069677  jnz     short loc_180069666
0x180069679  test    ecx, ecx
0x18006967b  jnz     short loc_1800696A0
0x18006967d  lea     rax, [rbp+390h+var_240]
0x180069684  sub     rdi, rax
0x180069687  movzx   edx, word ptr [rax]
0x18006968a  movzx   ecx, word ptr [rax+rdi]
0x18006968e  sub     edx, ecx
0x180069690  jnz     short loc_18006969A
0x180069692  add     rax, 2
0x180069696  test    ecx, ecx
0x180069698  jnz     short loc_180069687
0x18006969a  test    edx, edx
0x18006969c  cmovz   ebx, r14d
0x1800696a0  mov     rcx, [rsp+490h+hKey]; hKey
0x1800696a5  test    rcx, rcx
0x1800696a8  jz      short loc_1800696B6
0x1800696aa  call    cs:__imp_RegCloseKey
0x1800696b1  nop     dword ptr [rax+rax+00h]
0x1800696b6  mov     eax, ebx
0x1800696b8  mov     rcx, [rbp+390h+var_30]
0x1800696bf  xor     rcx, rsp; StackCookie
0x1800696c2  call    __security_check_cookie
0x1800696c7  add     rsp, 470h
0x1800696ce  pop     r14
0x1800696d0  pop     rdi
0x1800696d1  pop     rsi
0x1800696d2  pop     rbx
0x1800696d3  pop     rbp
0x1800696d4  retn
```
