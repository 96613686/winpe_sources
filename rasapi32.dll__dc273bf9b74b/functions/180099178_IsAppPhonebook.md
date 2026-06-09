# IsAppPhonebook

- ea: `0x180099178`
- end: `0x180099390`
- name: `IsAppPhonebook`
- size: `536`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800993e8`

## callees

- `0x18000b0f4`
- `0x180029390`
- `0x18004e580`
- `0x180099178`
- `0x1800ded06`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099233`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099233`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800992cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800992cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099368`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180099368`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800991fc`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800991fc`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800991a2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800991a2`

## string_xrefs

- `0x180099211`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`
- `0x180099202`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters\Config\Phonebooks`

## pseudocode

```c
__int64 __fastcall IsAppPhonebook(PCNZWCH lpString2)
{
  unsigned int v2; // r15d
  HGLOBAL v3; // rsi
  _DWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // ebp
  DWORD v11; // r14d
  unsigned int v12; // eax
  DWORD cchValueName; // [rsp+78h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+18h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = GlobalAlloc(0x40u, 0x7FFFu);
  if ( v3 )
  {
    IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
    v8 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
    if ( !IsStateSeparationEnabled )
      v8 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters\\Config\\Phonebooks";
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0x20019u, &hKey);
    if ( v9 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 1094;
        v6 = v9;
        goto LABEL_6;
      }
    }
    else
    {
      v10 = 0;
      v11 = 0;
      while ( v10 != 259 )
      {
        memset_0(v3, 0, 0x7FFFu);
        cchValueName = 0x3FFF;
        v12 = RegEnumValueW(hKey, v11, (LPWSTR)v3, &cchValueName, 0, 0, 0, 0);
        v10 = v12;
        if ( v12 )
        {
          v4 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 1095, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v12);
            v4 = WPP_GLOBAL_Control;
          }
          if ( v10 != 259 )
          {
            if ( v4 != (_DWORD *)&WPP_GLOBAL_Control && (v4[7] & 0x800) != 0 && *((_BYTE *)v4 + 25) >= 2u )
            {
              v5 = 1096;
              v6 = v10;
              goto LABEL_6;
            }
            break;
          }
        }
        else if ( !(unsigned int)CompareStringWrapW((PCNZWCH)v3, lpString2) )
        {
          v2 = 1;
          break;
        }
        ++v11;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 1093;
      v6 = 8;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, v6);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v3 )
    Free0(v3);
  return v2;
}

```

## disassembly

```asm
0x180099178  mov     rax, rsp
0x18009917b  mov     [rax+8], rbx
0x18009917f  push    rbp
0x180099180  push    rsi
0x180099181  push    r12
0x180099183  push    r14
0x180099185  push    r15
0x180099187  sub     rsp, 40h
0x18009918b  mov     r12, rcx
0x18009918e  mov     qword ptr [rax+18h], 0
0x180099196  xor     r15d, r15d
0x180099199  mov     edx, 7FFFh; dwBytes
0x18009919e  lea     ecx, [r15+40h]; uFlags
0x1800991a2  call    cs:__imp_GlobalAlloc
0x1800991a8  mov     rsi, rax
0x1800991ab  test    rax, rax
0x1800991ae  jnz     short loc_1800991FC
0x1800991b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800991b7  lea     rbx, WPP_GLOBAL_Control
0x1800991be  cmp     rcx, rbx
0x1800991c1  jz      loc_18009935B
0x1800991c7  test    dword ptr [rcx+1Ch], 800h
0x1800991ce  jz      loc_18009935B
0x1800991d4  cmp     byte ptr [rcx+19h], 2
0x1800991d8  jb      loc_18009935B
0x1800991de  mov     edx, 445h
0x1800991e3  lea     r9d, [r15+8]
0x1800991e7  mov     rcx, [rcx+10h]
0x1800991eb  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x1800991f2  call    WPP_SF_d
0x1800991f7  jmp     loc_18009935B
0x1800991fc  call    cs:__imp_RtlIsStateSeparationEnabled
0x180099202  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180099209  mov     r9d, 20019h; samDesired
0x18009920f  test    al, al
0x180099211  lea     rdx, aOsdataSystemCu; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180099218  lea     rax, [rsp+68h+hKey]
0x180099220  cmovz   rdx, rcx; lpSubKey
0x180099224  mov     [rsp+68h+phkResult], rax; phkResult
0x180099229  xor     r8d, r8d; ulOptions
0x18009922c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099233  call    cs:__imp_RegOpenKeyExW
0x180099239  test    eax, eax
0x18009923b  jz      short loc_180099278
0x18009923d  mov     rcx, cs:WPP_GLOBAL_Control
0x180099244  lea     rbx, WPP_GLOBAL_Control
0x18009924b  cmp     rcx, rbx
0x18009924e  jz      loc_18009935B
0x180099254  test    dword ptr [rcx+1Ch], 800h
0x18009925b  jz      loc_18009935B
0x180099261  cmp     byte ptr [rcx+19h], 2
0x180099265  jb      loc_18009935B
0x18009926b  mov     edx, 446h
0x180099270  mov     r9d, eax
0x180099273  jmp     loc_1800991E7
0x180099278  xor     ebp, ebp
0x18009927a  lea     rbx, WPP_GLOBAL_Control
0x180099281  xor     r14d, r14d
0x180099284  cmp     ebp, 103h
0x18009928a  jz      loc_18009935B
0x180099290  xor     edx, edx; Val
0x180099292  mov     r8d, 7FFFh; Size
0x180099298  mov     rcx, rsi; void *
0x18009929b  call    memset_0
0x1800992a0  mov     rcx, [rsp+68h+hKey]; hKey
0x1800992a8  lea     r9, [rsp+68h+cchValueName]; lpcchValueName
0x1800992ad  mov     [rsp+68h+lpcbData], r15; lpcbData
0x1800992b2  mov     r8, rsi; lpValueName
0x1800992b5  mov     [rsp+68h+lpData], r15; lpData
0x1800992ba  mov     edx, r14d; dwIndex
0x1800992bd  mov     [rsp+68h+lpType], r15; lpType
0x1800992c2  mov     [rsp+68h+phkResult], r15; lpReserved
0x1800992c7  mov     [rsp+68h+cchValueName], 3FFFh
0x1800992cf  call    cs:__imp_RegEnumValueW
0x1800992d5  mov     ebp, eax
0x1800992d7  test    eax, eax
0x1800992d9  jz      short loc_18009933E
0x1800992db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800992e2  cmp     rcx, rbx
0x1800992e5  jz      short loc_180099315
0x1800992e7  test    dword ptr [rcx+1Ch], 800h
0x1800992ee  jz      short loc_180099315
0x1800992f0  cmp     byte ptr [rcx+19h], 2
0x1800992f4  jb      short loc_180099315
0x1800992f6  mov     rcx, [rcx+10h]
0x1800992fa  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099301  mov     edx, 447h
0x180099306  mov     r9d, eax
0x180099309  call    WPP_SF_d
0x18009930e  mov     rcx, cs:WPP_GLOBAL_Control
0x180099315  cmp     ebp, 103h
0x18009931b  jz      short loc_18009934D
0x18009931d  cmp     rcx, rbx
0x180099320  jz      short loc_18009935B
0x180099322  test    dword ptr [rcx+1Ch], 800h
0x180099329  jz      short loc_18009935B
0x18009932b  cmp     byte ptr [rcx+19h], 2
0x18009932f  jb      short loc_18009935B
0x180099331  mov     edx, 448h
0x180099336  mov     r9d, ebp
0x180099339  jmp     loc_1800991E7
0x18009933e  mov     rdx, r12; lpString2
0x180099341  mov     rcx, rsi; lpString1
0x180099344  call    CompareStringWrapW
0x180099349  test    eax, eax
0x18009934b  jz      short loc_180099355
0x18009934d  inc     r14d
0x180099350  jmp     loc_180099284
0x180099355  mov     r15d, 1
0x18009935b  mov     rcx, [rsp+68h+hKey]; hKey
0x180099363  test    rcx, rcx
0x180099366  jz      short loc_18009936E
0x180099368  call    cs:__imp_RegCloseKey
0x18009936e  test    rsi, rsi
0x180099371  jz      short loc_18009937B
0x180099373  mov     rcx, rsi
0x180099376  call    Free0
0x18009937b  mov     rbx, [rsp+68h+arg_0]
0x180099380  mov     eax, r15d
0x180099383  add     rsp, 40h
0x180099387  pop     r15
0x180099389  pop     r14
0x18009938b  pop     r12
0x18009938d  pop     rsi
0x18009938e  pop     rbp
0x18009938f  retn
```
