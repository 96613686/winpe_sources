# PersistRegStore::InternalFlushObjectMember(PersistObject *,PersistObject::PERSIST_OBJECT_MEMBER_ID)

- ea: `0x180029550`
- end: `0x1800299fb`
- name: `?InternalFlushObjectMember@PersistRegStore@@MEAAJPEAVPersistObject@@W4PERSIST_OBJECT_MEMBER_ID@2@@Z`
- size: `1195`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180007f48`
- `0x180029550`
- `0x18003b952`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800296ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800297e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800295ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800296ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800297e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800298b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002978d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029901`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800295df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002978d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029901`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002962b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800295f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002962b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800297b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029888`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029988`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800297b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029888`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029988`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002966b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002966b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800296ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800296ab`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180029614`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180029614`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800299cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002982f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002982f`
- `DMCmnUtils!CopyString` at `0x1800298f6`
- `DMCmnUtils!CopyString` at `0x1800298f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PersistRegStore::InternalFlushObjectMember(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // r13
  __int64 v5; // r12
  BYTE *v6; // r15
  int v7; // edi
  const WCHAR *v8; // rsi
  signed int v9; // ebx
  bool v10; // sf
  int v11; // esi
  _QWORD *v12; // r12
  int *v13; // rcx
  int v14; // esi
  int v15; // esi
  _DWORD *v16; // rax
  LSTATUS v17; // eax
  DWORD v18; // esi
  __int64 v19; // rsi
  BYTE *v20; // rax
  LSTATUS v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rdx
  BYTE *v24; // rax
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rcx
  LSTATUS v27; // eax
  int v29; // [rsp+50h] [rbp-59h]
  const WCHAR *v30; // [rsp+58h] [rbp-51h]
  HKEY hKey; // [rsp+78h] [rbp-31h] BYREF
  BYTE Data[4]; // [rsp+80h] [rbp-29h] BYREF
  DWORD dwDisposition; // [rsp+84h] [rbp-25h] BYREF
  BYTE *lpData[2]; // [rsp+88h] [rbp-21h] BYREF
  char v36; // [rsp+98h] [rbp-11h]
  WCHAR ValueName[8]; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v38; // [rsp+B0h] [rbp+7h]

  v3 = a3;
  v5 = a1;
  lpData[0] = 0;
  *(_OWORD *)ValueName = 0;
  v38 = 0;
  v6 = 0;
  hKey = 0;
  *(_DWORD *)Data = 0;
  dwDisposition = 0;
  v7 = 0;
  v29 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a1 + 72LL))(a1) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    v8 = *(const WCHAR **)(a2 + 24);
    v30 = v8;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    if ( !v8 )
    {
      v9 = -2147024809;
LABEL_5:
      v7 = 0;
      goto LABEL_6;
    }
    v9 = StringCchPrintfW(ValueName, 0x10u, L"%d", (unsigned int)v3);
    if ( v9 < 0 )
      goto LABEL_5;
    v9 = RegOpenKeyExW(*(HKEY *)(v5 + 16), v8, 0, 0xF003Fu, &hKey);
    if ( v9 == 2 )
    {
      v9 = RegCreateKeyExW(*(HKEY *)(v5 + 16), v8, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      if ( v9 )
      {
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_15:
        v7 = 0;
        goto LABEL_6;
      }
      v29 = 1;
    }
    else
    {
      v10 = v9 < 0;
      if ( v9 )
      {
        if ( v9 > 0 )
        {
          v9 = (unsigned __int16)v9 | 0x80070000;
          v10 = v9 < 0;
        }
        if ( v10 )
          goto LABEL_15;
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    v11 = 0;
    v12 = (_QWORD *)(a2 + 8);
    if ( (unsigned int)v3 < *(_DWORD *)(a2 + 16) && (_mm_lfence(), (v13 = *(int **)(*v12 + 8 * v3)) != 0) )
    {
      v9 = 0;
      v11 = *v13;
    }
    else
    {
      v9 = -2147023728;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    if ( v9 < 0 )
      goto LABEL_40;
    v14 = v11 - 1;
    if ( !v14 )
    {
      lpData[1] = (BYTE *)(a2 + 32);
      EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
      v36 = 1;
      if ( (unsigned int)v3 < *(_DWORD *)(a2 + 16) && (_mm_lfence(), (v22 = *(_QWORD *)(*v12 + 8 * v3)) != 0) )
      {
        if ( *(_DWORD *)v22 == 1 )
          v9 = CopyString(*(const unsigned __int16 **)(v22 + 16), 0xFFFFFFFF, (unsigned __int16 **)lpData);
        else
          v9 = -2147024883;
      }
      else
      {
        v9 = -2147023728;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
      if ( v9 >= 0 )
      {
        if ( lpData[0] )
        {
          v23 = 0x7FFFFFFF;
          v24 = lpData[0];
          do
          {
            if ( !*(_WORD *)v24 )
              break;
            v24 += 2;
            --v23;
          }
          while ( v23 );
          v9 = v23 == 0 ? 0x80070057 : 0;
          if ( v23 )
          {
            v25 = (2 * (0x7FFFFFFF - v23)) & -(__int64)(v23 != 0);
            v26 = v25 + 2;
            if ( v25 + 2 < v25 || v26 > 0xFFFFFFFF )
            {
              v9 = -2147024362;
            }
            else
            {
              v9 = 0;
              v27 = RegSetValueExW(hKey, ValueName, 0, 1u, lpData[0], v26);
              if ( !v27 )
              {
                v6 = 0;
                goto LABEL_41;
              }
              if ( v27 > 0 )
                v9 = (unsigned __int16)v27 | 0x80070000;
              else
                v9 = v27;
            }
          }
        }
        else
        {
          v9 = -2147024809;
        }
      }
      v6 = 0;
LABEL_41:
      v8 = v30;
      v5 = a1;
      v7 = v29;
      goto LABEL_6;
    }
    v15 = v14 - 2;
    if ( v15 )
    {
      if ( v15 == 1 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
        if ( (unsigned int)v3 < *(_DWORD *)(a2 + 16) && (_mm_lfence(), (v16 = *(_DWORD **)(*v12 + 8 * v3)) != 0) )
        {
          if ( *v16 == 4 )
          {
            v9 = 0;
            *(_DWORD *)Data = v16[1];
          }
          else
          {
            v9 = -2147024883;
          }
        }
        else
        {
          v9 = -2147023728;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
        if ( v9 >= 0 )
        {
          v17 = RegSetValueExW(hKey, ValueName, 0, 4u, Data, 4u);
          if ( v17 )
          {
            if ( v17 > 0 )
              v9 = (unsigned __int16)v17 | 0x80070000;
            else
              v9 = v17;
          }
        }
      }
LABEL_40:
      v6 = 0;
      goto LABEL_41;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
    v18 = 0;
    if ( (unsigned int)v3 < *(_DWORD *)(a2 + 16) )
    {
      _mm_lfence();
      v19 = *(_QWORD *)(*v12 + 8 * v3);
      if ( v19 )
      {
        if ( *(_DWORD *)v19 == 3 )
        {
          v20 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)(v19 + 8));
          v6 = v20;
          if ( v20 )
          {
            v9 = 0;
            memcpy_0(v20, *(const void **)(v19 + 24), *(unsigned int *)(v19 + 8));
            v18 = *(_DWORD *)(v19 + 8);
          }
          else
          {
            v9 = -2147024882;
            v18 = 0;
          }
LABEL_53:
          LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 32));
          if ( v9 >= 0 )
          {
            v21 = RegSetValueExW(hKey, ValueName, 0, 3u, v6, v18);
            if ( v21 )
            {
              if ( v21 > 0 )
                v9 = (unsigned __int16)v21 | 0x80070000;
              else
                v9 = v21;
            }
          }
          goto LABEL_41;
        }
        v9 = -2147024883;
      }
      else
      {
        v9 = -2147023728;
      }
      v18 = 0;
    }
    else
    {
      v9 = -2147023728;
    }
    v6 = 0;
    goto LABEL_53;
  }
  v8 = 0;
  v9 = -2102788096;
LABEL_6:
  RegCloseKey(hKey);
  if ( v9 < 0 && v7 )
  {
    while ( RegDeleteKeyW(*(HKEY *)(v5 + 16), v8) )
    {
      v9 = -2102788091;
      RegCloseKey(hKey);
    }
  }
  LocalFree(lpData[0]);
  LocalFree(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180029550  mov     [rsp-8+arg_18], rbx
0x180029555  push    rbp
0x180029556  push    rsi
0x180029557  push    rdi
0x180029558  push    r12
0x18002955a  push    r13
0x18002955c  push    r14
0x18002955e  push    r15
0x180029560  lea     rbp, [rsp-27h]
0x180029565  sub     rsp, 0D0h
0x18002956c  mov     rax, cs:__security_cookie
0x180029573  xor     rax, rsp
0x180029576  mov     [rbp+57h+var_40], rax
0x18002957a  mov     r13d, r8d
0x18002957d  mov     r14, rdx
0x180029580  mov     r12, rcx
0x180029583  mov     [rbp+57h+var_98], rcx
0x180029587  xor     ebx, ebx
0x180029589  mov     [rbp+57h+lpData], rbx
0x18002958d  xorps   xmm0, xmm0
0x180029590  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180029594  movups  [rbp+57h+var_50], xmm0
0x180029598  mov     r15d, ebx
0x18002959b  mov     [rbp+57h+var_A0], rbx
0x18002959f  mov     [rbp+57h+hKey], rbx
0x1800295a3  mov     dword ptr [rbp+57h+Data], ebx
0x1800295a6  mov     [rbp+57h+dwDisposition], ebx
0x1800295a9  mov     edi, ebx
0x1800295ab  mov     [rbp+57h+var_B0], ebx
0x1800295ae  mov     rax, [rcx]
0x1800295b1  mov     rax, [rax+48h]
0x1800295b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295ba  test    eax, eax
0x1800295bc  jnz     short loc_1800295C7
0x1800295be  mov     esi, ebx
0x1800295c0  mov     ebx, 82AA0000h
0x1800295c5  jmp     short loc_1800295F2
0x1800295c7  lea     rdi, [r14+20h]
0x1800295cb  mov     rcx, rdi; lpCriticalSection
0x1800295ce  call    cs:__imp_EnterCriticalSection
0x1800295d4  mov     rsi, [r14+18h]
0x1800295d8  mov     [rbp+57h+var_A8], rsi
0x1800295dc  mov     rcx, rdi; lpCriticalSection
0x1800295df  call    cs:__imp_LeaveCriticalSection
0x1800295e5  test    rsi, rsi
0x1800295e8  jnz     short loc_180029633
0x1800295ea  mov     ebx, 80070057h
0x1800295ef  mov     edi, r15d
0x1800295f2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800295f6  call    cs:__imp_RegCloseKey
0x1800295fc  test    ebx, ebx
0x1800295fe  jns     loc_1800299BF
0x180029604  test    edi, edi
0x180029606  jz      loc_1800299BF
0x18002960c  mov     rdx, rsi; lpSubKey
0x18002960f  mov     rcx, [r12+10h]; hKey
0x180029614  call    cs:__imp_RegDeleteKeyW
0x18002961a  test    eax, eax
0x18002961c  jz      loc_1800299BF
0x180029622  mov     ebx, 82AA0005h
0x180029627  mov     rcx, [rbp+57h+hKey]; hKey
0x18002962b  call    cs:__imp_RegCloseKey
0x180029631  jmp     short loc_18002960C
0x180029633  mov     r9d, r13d
0x180029636  lea     r8, aD; "%d"
0x18002963d  mov     edx, 10h; unsigned __int64
0x180029642  lea     rcx, [rbp+57h+ValueName]; unsigned __int16 *
0x180029646  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002964b  mov     ebx, eax
0x18002964d  test    eax, eax
0x18002964f  js      short loc_1800295EF
0x180029651  lea     rax, [rbp+57h+hKey]
0x180029655  mov     [rsp+100h+phkResult], rax; phkResult
0x18002965a  mov     r9d, 0F003Fh; samDesired
0x180029660  xor     r8d, r8d; ulOptions
0x180029663  mov     rdx, rsi; lpSubKey
0x180029666  mov     rcx, [r12+10h]; hKey
0x18002966b  call    cs:__imp_RegOpenKeyExW
0x180029671  mov     ebx, eax
0x180029673  cmp     eax, 2
0x180029676  jnz     short loc_1800296D4
0x180029678  lea     rax, [rbp+57h+dwDisposition]
0x18002967c  mov     [rsp+100h+lpdwDisposition], rax; lpdwDisposition
0x180029681  lea     rax, [rbp+57h+hKey]
0x180029685  mov     [rsp+100h+var_C8], rax; phkResult
0x18002968a  xor     eax, eax
0x18002968c  mov     [rsp+100h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180029691  mov     [rsp+100h+samDesired], 2001Fh; samDesired
0x180029699  mov     dword ptr [rsp+100h+phkResult], eax; dwOptions
0x18002969d  xor     r9d, r9d; lpClass
0x1800296a0  xor     r8d, r8d; Reserved
0x1800296a3  mov     rdx, rsi; lpSubKey
0x1800296a6  mov     rcx, [r12+10h]; hKey
0x1800296ab  call    cs:__imp_RegCreateKeyExW
0x1800296b1  mov     ebx, eax
0x1800296b3  xor     eax, eax
0x1800296b5  test    ebx, ebx
0x1800296b7  jz      short loc_1800296CB
0x1800296b9  jle     short loc_1800296C4
0x1800296bb  movzx   ebx, bx
0x1800296be  or      ebx, 80070000h
0x1800296c4  mov     edi, eax
0x1800296c6  jmp     loc_1800295F2
0x1800296cb  mov     [rbp+57h+var_B0], 1
0x1800296d2  jmp     short loc_1800296E9
0x1800296d4  xor     eax, eax
0x1800296d6  test    ebx, ebx
0x1800296d8  jz      short loc_1800296E9
0x1800296da  jle     short loc_1800296E7
0x1800296dc  movzx   ebx, bx
0x1800296df  or      ebx, 80070000h
0x1800296e5  test    ebx, ebx
0x1800296e7  js      short loc_1800296C4
0x1800296e9  mov     rcx, rdi; lpCriticalSection
0x1800296ec  call    cs:__imp_EnterCriticalSection
0x1800296f2  xor     edx, edx
0x1800296f4  mov     esi, edx
0x1800296f6  mov     r8d, 80070490h
0x1800296fc  mov     r15, r13
0x1800296ff  lea     r12, [r14+8]
0x180029703  cmp     r13d, [r14+10h]
0x180029707  jb      short loc_18002970E
0x180029709  mov     ebx, r8d
0x18002970c  jmp     short loc_180029722
0x18002970e  lfence
0x180029711  mov     rax, [r12]
0x180029715  mov     rcx, [rax+r13*8]
0x180029719  test    rcx, rcx
0x18002971c  jz      short loc_180029709
0x18002971e  mov     ebx, edx
0x180029720  mov     esi, [rcx]
0x180029722  mov     rcx, rdi; lpCriticalSection
0x180029725  call    cs:__imp_LeaveCriticalSection
0x18002972b  test    ebx, ebx
0x18002972d  js      loc_1800297CF
0x180029733  sub     esi, 1
0x180029736  jz      loc_1800298AD
0x18002973c  sub     esi, 2
0x18002973f  jz      loc_1800297E3
0x180029745  cmp     esi, 1
0x180029748  jnz     loc_1800297CF
0x18002974e  mov     rcx, rdi; lpCriticalSection
0x180029751  call    cs:__imp_EnterCriticalSection
0x180029757  cmp     r13d, [r14+10h]
0x18002975b  jb      short loc_180029764
0x18002975d  mov     ebx, 80070490h
0x180029762  jmp     short loc_18002978A
0x180029764  lfence
0x180029767  mov     rax, [r12]
0x18002976b  mov     rax, [rax+r15*8]
0x18002976f  xor     esi, esi
0x180029771  test    rax, rax
0x180029774  jz      short loc_18002975D
0x180029776  cmp     dword ptr [rax], 4
0x180029779  jz      short loc_180029782
0x18002977b  mov     ebx, 8007000Dh
0x180029780  jmp     short loc_18002978A
0x180029782  mov     ebx, esi
0x180029784  mov     eax, [rax+4]
0x180029787  mov     dword ptr [rbp+57h+Data], eax
0x18002978a  mov     rcx, rdi; lpCriticalSection
0x18002978d  call    cs:__imp_LeaveCriticalSection
0x180029793  test    ebx, ebx
0x180029795  js      short loc_1800297CF
0x180029797  mov     r9d, 4; dwType
0x18002979d  mov     [rsp+100h+samDesired], r9d; cbData
0x1800297a2  lea     rax, [rbp+57h+Data]
0x1800297a6  mov     [rsp+100h+phkResult], rax; lpData
0x1800297ab  xor     r8d, r8d; Reserved
0x1800297ae  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x1800297b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800297b6  call    cs:__imp_RegSetValueExW
0x1800297bc  test    eax, eax
0x1800297be  jz      short loc_1800297CF
0x1800297c0  jg      short loc_1800297C6
0x1800297c2  mov     ebx, eax
0x1800297c4  jmp     short loc_1800297CF
0x1800297c6  movzx   ebx, ax
0x1800297c9  or      ebx, 80070000h
0x1800297cf  mov     r15, [rbp+57h+var_A0]
0x1800297d3  mov     rsi, [rbp+57h+var_A8]
0x1800297d7  mov     r12, [rbp+57h+var_98]
0x1800297db  mov     edi, [rbp+57h+var_B0]
0x1800297de  jmp     loc_1800295F2
0x1800297e3  mov     rcx, rdi; lpCriticalSection
0x1800297e6  call    cs:__imp_EnterCriticalSection
0x1800297ec  xor     esi, esi
0x1800297ee  cmp     r13d, [r14+10h]
0x1800297f2  jb      short loc_1800297FE
0x1800297f4  mov     ebx, 80070490h
0x1800297f9  mov     r15, rsi
0x1800297fc  jmp     short loc_18002985D
0x1800297fe  lfence
0x180029801  mov     rax, [r12]
0x180029805  mov     rsi, [rax+r15*8]
0x180029809  xor     r12d, r12d
0x18002980c  test    rsi, rsi
0x18002980f  jnz     short loc_18002981B
0x180029811  mov     ebx, 80070490h
0x180029816  mov     esi, r12d
0x180029819  jmp     short loc_1800297F9
0x18002981b  cmp     dword ptr [rsi], 3
0x18002981e  jz      short loc_180029827
0x180029820  mov     ebx, 8007000Dh
0x180029825  jmp     short loc_180029816
0x180029827  mov     edx, [rsi+8]; uBytes
0x18002982a  mov     ecx, 40h ; '@'; uFlags
0x18002982f  call    cs:__imp_LocalAlloc
0x180029835  mov     r15, rax
0x180029838  test    rax, rax
0x18002983b  jnz     short loc_180029847
0x18002983d  mov     ebx, 8007000Eh
0x180029842  mov     esi, r12d
0x180029845  jmp     short loc_18002985D
0x180029847  mov     ebx, r12d
0x18002984a  mov     r8d, [rsi+8]; Size
0x18002984e  mov     rdx, [rsi+18h]; Src
0x180029852  mov     rcx, rax; void *
0x180029855  call    memcpy_0
0x18002985a  mov     esi, [rsi+8]
0x18002985d  mov     rcx, rdi; lpCriticalSection
0x180029860  call    cs:__imp_LeaveCriticalSection
0x180029866  test    ebx, ebx
0x180029868  js      loc_1800297D3
0x18002986e  mov     [rsp+100h+samDesired], esi; cbData
0x180029872  mov     [rsp+100h+phkResult], r15; lpData
0x180029877  mov     r9d, 3; dwType
0x18002987d  xor     r8d, r8d; Reserved
0x180029880  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180029884  mov     rcx, [rbp+57h+hKey]; hKey
0x180029888  call    cs:__imp_RegSetValueExW
0x18002988e  test    eax, eax
0x180029890  jz      loc_1800297D3
0x180029896  jg      short loc_18002989F
0x180029898  mov     ebx, eax
0x18002989a  jmp     loc_1800297D3
0x18002989f  movzx   ebx, ax
0x1800298a2  or      ebx, 80070000h
0x1800298a8  jmp     loc_1800297D3
0x1800298ad  mov     [rbp+57h+var_70], rdi
0x1800298b1  mov     rcx, rdi; lpCriticalSection
0x1800298b4  call    cs:__imp_EnterCriticalSection
0x1800298ba  mov     [rbp+57h+var_68], 1
0x1800298be  mov     esi, 0FFFFFFFFh
0x1800298c3  cmp     r13d, [r14+10h]
0x1800298c7  jb      short loc_1800298D0
0x1800298c9  mov     ebx, 80070490h
0x1800298ce  jmp     short loc_1800298FE
0x1800298d0  lfence
0x1800298d3  mov     rax, [r12]
0x1800298d7  mov     rcx, [rax+r15*8]
0x1800298db  test    rcx, rcx
0x1800298de  jz      short loc_1800298C9
0x1800298e0  cmp     dword ptr [rcx], 1
0x1800298e3  jz      short loc_1800298EC
0x1800298e5  mov     ebx, 8007000Dh
0x1800298ea  jmp     short loc_1800298FE
0x1800298ec  lea     r8, [rbp+57h+lpData]
0x1800298f0  mov     edx, esi
0x1800298f2  mov     rcx, [rcx+10h]
0x1800298f6  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800298fc  mov     ebx, eax
0x1800298fe  mov     rcx, rdi; lpCriticalSection
0x180029901  call    cs:__imp_LeaveCriticalSection
0x180029907  xor     edi, edi
0x180029909  test    ebx, ebx
0x18002990b  js      loc_1800299A8
0x180029911  mov     r10, [rbp+57h+lpData]
0x180029915  test    r10, r10
0x180029918  jz      loc_1800299B0
0x18002991e  mov     r8d, 7FFFFFFFh
0x180029924  mov     edx, r8d
0x180029927  mov     rax, r10
0x18002992a  cmp     [rax], di
0x18002992d  jz      short loc_180029939
0x18002992f  add     rax, 2
0x180029933  sub     rdx, 1
0x180029937  jnz     short loc_18002992A
0x180029939  mov     rax, rdx
0x18002993c  neg     rax
0x18002993f  sbb     ecx, ecx
0x180029941  not     ecx
0x180029943  mov     ebx, 80070057h
0x180029948  and     ebx, ecx
0x18002994a  test    rdx, rdx
0x18002994d  jz      short loc_1800299A8
0x18002994f  sub     r8, rdx
0x180029952  add     r8, r8
0x180029955  neg     rdx
0x180029958  sbb     rax, rax
0x18002995b  and     rax, r8
0x18002995e  lea     rcx, [rax+2]
0x180029962  cmp     rcx, rax
0x180029965  jb      short loc_1800299A3
0x180029967  cmp     rcx, rsi
0x18002996a  ja      short loc_1800299A3
0x18002996c  mov     ebx, edi
0x18002996e  mov     [rsp+100h+samDesired], ecx; cbData
0x180029972  mov     [rsp+100h+phkResult], r10; lpData
0x180029977  mov     r9d, 1; dwType
  ... truncated ...
```
