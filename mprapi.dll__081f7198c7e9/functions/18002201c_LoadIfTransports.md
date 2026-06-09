# LoadIfTransports

- ea: `0x18002201c`
- end: `0x18002231b`
- name: `LoadIfTransports`
- size: `767`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800255a0`
- `0x180025880`
- `0x180025ac0`
- `0x1800274d0`

## callees

- `0x180018470`
- `0x18002201c`
- `0x1800291b4`
- `0x18002998c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800220df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800221f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002223d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800222a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800220df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800221f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002223d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800222a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800220ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022204`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800220ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022204`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002224b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800222af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002224b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800222af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800221db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002228a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800221db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002228a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800220a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800220a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002213c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002213c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022165`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022165`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800221a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800221a0`

## string_xrefs

- `0x180022199`: `ProtocolId`

## pseudocode

```c
LSTATUS __fastcall LoadIfTransports(__int64 a1)
{
  _QWORD *v1; // rsi
  _QWORD *v2; // rax
  LSTATUS result; // eax
  LSTATUS v5; // edi
  DWORD v6; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // r12
  DWORD v9; // r15d
  HKEY v10; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  unsigned int v13; // eax
  bool v14; // zf
  HKEY v15; // rcx
  HANDLE v16; // rax
  _OWORD *v17; // rax
  _QWORD *v18; // rdi
  PWSTR v19; // rax
  HANDLE v20; // rax
  _QWORD *v21; // rcx
  HANDLE v22; // rax
  _QWORD *i; // rbx
  _QWORD *v24; // rcx
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  DWORD Type; // [rsp+60h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+C0h] [rbp+48h] BYREF
  unsigned int Data; // [rsp+C8h] [rbp+50h] BYREF
  DWORD cSubKeys; // [rsp+D0h] [rbp+58h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D8h] [rbp+60h] BYREF

  v1 = (_QWORD *)(a1 + 80);
  v2 = *(_QWORD **)(a1 + 80);
  phkResult = 0;
  Data = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  Type = 0;
  cchName = 0;
  while ( v2 != v1 )
  {
    *((_DWORD *)v2 - 2) = 1;
    v2 = (_QWORD *)*v2;
  }
  result = RegQueryInfoKeyW(*(HKEY *)(a1 + 40), 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v5 = result;
  if ( !result && cSubKeys )
  {
    if ( cbMaxSubKeyLen + 1 < cbMaxSubKeyLen || 2 * (unsigned __int64)(cbMaxSubKeyLen + 1) > 0xFFFFFFFF )
    {
      return 534;
    }
    else
    {
      v6 = 2 * (cbMaxSubKeyLen + 1);
      ProcessHeap = GetProcessHeap();
      v8 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v6);
      if ( !v8 )
        return 8;
      v9 = 0;
      if ( cSubKeys )
      {
        while ( 1 )
        {
          v10 = *(HKEY *)(a1 + 40);
          cchName = cbMaxSubKeyLen + 1;
          v5 = RegEnumKeyExW(v10, v9, v8, &cchName, 0, 0, 0, 0);
          if ( v5 )
            goto LABEL_33;
          v5 = RegOpenKeyExW(*(HKEY *)(a1 + 40), v8, 0, 0x3001Fu, &phkResult);
          if ( !v5 )
            break;
LABEL_32:
          if ( ++v9 >= cSubKeys )
            goto LABEL_33;
        }
        cchName = 4;
        if ( !RegQueryValueExW(phkResult, L"ProtocolId", 0, &Type, (LPBYTE)&Data, &cchName) )
        {
          v11 = (_QWORD *)*v1;
          if ( (_QWORD *)*v1 != v1 )
          {
            while ( 1 )
            {
              v12 = v11 - 4;
              v13 = *((_DWORD *)v11 - 8);
              v14 = v13 == Data;
              if ( v13 >= Data )
                break;
              v11 = (_QWORD *)*v11;
              if ( v11 == v1 )
              {
                v14 = v13 == Data;
                break;
              }
            }
            if ( v14 )
            {
              v15 = (HKEY)v12[2];
              *((_DWORD *)v12 + 6) = 0;
              if ( v15 )
                RegCloseKey(v15);
              v12[2] = phkResult;
              v5 = 0;
              phkResult = 0;
              goto LABEL_32;
            }
          }
          v16 = GetProcessHeap();
          v17 = HeapAlloc(v16, 0, 0x30u);
          v18 = v17;
          if ( !v17 )
            goto LABEL_23;
          *v17 = 0;
          v17[1] = 0;
          v17[2] = 0;
          *(_DWORD *)v17 = Data;
          v19 = StrDupW(v8);
          v18[1] = v19;
          if ( !v19 )
          {
            v20 = GetProcessHeap();
            HeapFree(v20, 0, v18);
LABEL_23:
            v5 = 8;
            goto LABEL_29;
          }
          v18[2] = phkResult;
          phkResult = 0;
          v21 = (_QWORD *)v11[1];
          if ( (_QWORD *)*v21 != v11 )
LABEL_41:
            __fastfail(3u);
          v18[4] = v11;
          v18[5] = v21;
          *v21 = v18 + 4;
          v11[1] = v18 + 4;
        }
        v5 = 0;
LABEL_29:
        if ( phkResult )
          RegCloseKey(phkResult);
        if ( v5 )
          goto LABEL_33;
        goto LABEL_32;
      }
LABEL_33:
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v8);
      for ( i = (_QWORD *)*v1; i != v1; i = (_QWORD *)*i )
      {
        v24 = i - 4;
        if ( *((_DWORD *)i - 2) )
        {
          v25 = (_QWORD *)*i;
          if ( *(_QWORD **)(*i + 8LL) != i )
            goto LABEL_41;
          v26 = (_QWORD *)i[1];
          if ( (_QWORD *)*v26 != i )
            goto LABEL_41;
          *v26 = v25;
          i = v26;
          v25[1] = v26;
          FreeTransport(v24);
        }
      }
      UpdateTimeStamp(*(HKEY *)(a1 + 40), (PFILETIME)(a1 + 48));
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002201c  push    rbp
0x18002201e  push    rbx
0x18002201f  push    rsi
0x180022020  push    rdi
0x180022021  push    r12
0x180022023  push    r13
0x180022025  push    r14
0x180022027  push    r15
0x180022029  mov     rbp, rsp
0x18002202c  sub     rsp, 78h
0x180022030  xor     r13d, r13d
0x180022033  lea     rsi, [rcx+50h]
0x180022037  mov     rax, [rsi]
0x18002203a  mov     r14, rcx
0x18002203d  mov     [rbp+phkResult], r13
0x180022041  mov     [rbp+Data], r13d
0x180022045  mov     [rbp+cSubKeys], r13d
0x180022049  mov     [rbp+cbMaxSubKeyLen], r13d
0x18002204d  mov     [rbp+Type], r13d
0x180022051  mov     [rbp+cchName], r13d
0x180022055  jmp     short loc_180022061
0x180022057  mov     dword ptr [rax-8], 1
0x18002205e  mov     rax, [rax]
0x180022061  cmp     rax, rsi
0x180022064  jnz     short loc_180022057
0x180022066  mov     rcx, [rcx+28h]; hKey
0x18002206a  lea     rax, [rbp+cbMaxSubKeyLen]
0x18002206e  mov     [rsp+78h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180022073  xor     r9d, r9d; lpReserved
0x180022076  mov     [rsp+78h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002207b  xor     r8d, r8d; lpcchClass
0x18002207e  mov     [rsp+78h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180022083  xor     edx, edx; lpClass
0x180022085  mov     [rsp+78h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18002208a  mov     [rsp+78h+lpcValues], r13; lpcValues
0x18002208f  mov     [rsp+78h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180022094  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180022099  lea     rax, [rbp+cSubKeys]
0x18002209d  mov     [rsp+78h+lpcSubKeys], rax; lpcSubKeys
0x1800220a2  call    cs:__imp_RegQueryInfoKeyW
0x1800220a8  mov     edi, eax
0x1800220aa  test    eax, eax
0x1800220ac  jnz     loc_18002230A
0x1800220b2  cmp     [rbp+cSubKeys], r13d
0x1800220b6  jz      loc_18002230A
0x1800220bc  mov     eax, [rbp+cbMaxSubKeyLen]
0x1800220bf  lea     ecx, [rax+1]
0x1800220c2  cmp     ecx, eax
0x1800220c4  jb      loc_180022305
0x1800220ca  mov     eax, ecx
0x1800220cc  mov     ecx, 0FFFFFFFFh
0x1800220d1  add     rax, rax
0x1800220d4  cmp     rax, rcx
0x1800220d7  ja      loc_180022305
0x1800220dd  mov     ebx, eax
0x1800220df  call    cs:__imp_GetProcessHeap
0x1800220e5  mov     r8d, ebx; dwBytes
0x1800220e8  xor     edx, edx; dwFlags
0x1800220ea  mov     rcx, rax; hHeap
0x1800220ed  call    cs:__imp_HeapAlloc
0x1800220f3  mov     r12, rax
0x1800220f6  test    rax, rax
0x1800220f9  jnz     short loc_180022105
0x1800220fb  lea     eax, [r12+8]
0x180022100  jmp     loc_18002230A
0x180022105  mov     r15d, r13d
0x180022108  cmp     [rbp+cSubKeys], r13d
0x18002210c  jbe     loc_1800222A1
0x180022112  mov     eax, [rbp+cbMaxSubKeyLen]
0x180022115  lea     r9, [rbp+cchName]; lpcchName
0x180022119  mov     rcx, [r14+28h]; hKey
0x18002211d  inc     eax
0x18002211f  mov     [rsp+78h+lpcValues], r13; lpftLastWriteTime
0x180022124  mov     r8, r12; lpName
0x180022127  mov     [rsp+78h+lpcbMaxClassLen], r13; lpcchClass
0x18002212c  mov     edx, r15d; dwIndex
0x18002212f  mov     [rsp+78h+lpcbMaxSubKeyLen], r13; lpClass
0x180022134  mov     [rbp+cchName], eax
0x180022137  mov     [rsp+78h+lpcSubKeys], r13; lpReserved
0x18002213c  call    cs:__imp_RegEnumKeyExW
0x180022142  mov     edi, eax
0x180022144  test    eax, eax
0x180022146  jnz     loc_1800222A1
0x18002214c  mov     rcx, [r14+28h]; hKey
0x180022150  lea     rax, [rbp+phkResult]
0x180022154  mov     r9d, 3001Fh; samDesired
0x18002215a  mov     [rsp+78h+lpcSubKeys], rax; phkResult
0x18002215f  xor     r8d, r8d; ulOptions
0x180022162  mov     rdx, r12; lpSubKey
0x180022165  call    cs:__imp_RegOpenKeyExW
0x18002216b  mov     edi, eax
0x18002216d  test    eax, eax
0x18002216f  jnz     loc_180022294
0x180022175  mov     rcx, [rbp+phkResult]; hKey
0x180022179  lea     rax, [rbp+cchName]
0x18002217d  mov     [rsp+78h+lpcbMaxSubKeyLen], rax; lpcbData
0x180022182  lea     r9, [rbp+Type]; lpType
0x180022186  lea     rax, [rbp+Data]
0x18002218a  mov     [rbp+cchName], 4
0x180022191  xor     r8d, r8d; lpReserved
0x180022194  mov     [rsp+78h+lpcSubKeys], rax; lpData
0x180022199  lea     rdx, c_szProtocolId; "ProtocolId"
0x1800221a0  call    cs:__imp_RegQueryValueExW
0x1800221a6  test    eax, eax
0x1800221a8  jnz     loc_18002227E
0x1800221ae  mov     rbx, [rsi]
0x1800221b1  cmp     rbx, rsi
0x1800221b4  jz      short loc_1800221F5
0x1800221b6  lea     rdi, [rbx-20h]
0x1800221ba  mov     eax, [rdi]
0x1800221bc  cmp     eax, [rbp+Data]
0x1800221bf  jnb     short loc_1800221CC
0x1800221c1  mov     rbx, [rbx]
0x1800221c4  cmp     rbx, rsi
0x1800221c7  jnz     short loc_1800221B6
0x1800221c9  cmp     eax, [rbp+Data]
0x1800221cc  jnz     short loc_1800221F5
0x1800221ce  mov     rcx, [rdi+10h]; hKey
0x1800221d2  mov     [rdi+18h], r13d
0x1800221d6  test    rcx, rcx
0x1800221d9  jz      short loc_1800221E1
0x1800221db  call    cs:__imp_RegCloseKey
0x1800221e1  mov     rax, [rbp+phkResult]
0x1800221e5  mov     [rdi+10h], rax
0x1800221e9  mov     edi, r13d
0x1800221ec  mov     [rbp+phkResult], r13
0x1800221f0  jmp     loc_180022294
0x1800221f5  call    cs:__imp_GetProcessHeap
0x1800221fb  xor     edx, edx; dwFlags
0x1800221fd  mov     rcx, rax; hHeap
0x180022200  lea     r8d, [rdx+30h]; dwBytes
0x180022204  call    cs:__imp_HeapAlloc
0x18002220a  mov     rdi, rax
0x18002220d  test    rax, rax
0x180022210  jnz     short loc_180022219
0x180022212  mov     edi, 8
0x180022217  jmp     short loc_180022281
0x180022219  xorps   xmm0, xmm0
0x18002221c  mov     rcx, r12; pszSrch
0x18002221f  movups  xmmword ptr [rax], xmm0
0x180022222  movups  xmmword ptr [rax+10h], xmm0
0x180022226  movups  xmmword ptr [rax+20h], xmm0
0x18002222a  mov     eax, [rbp+Data]
0x18002222d  mov     [rdi], eax
0x18002222f  call    StrDupW
0x180022234  mov     [rdi+8], rax
0x180022238  test    rax, rax
0x18002223b  jnz     short loc_180022253
0x18002223d  call    cs:__imp_GetProcessHeap
0x180022243  mov     r8, rdi; lpMem
0x180022246  xor     edx, edx; dwFlags
0x180022248  mov     rcx, rax; hHeap
0x18002224b  call    cs:__imp_HeapFree
0x180022251  jmp     short loc_180022212
0x180022253  mov     rax, [rbp+phkResult]
0x180022257  mov     [rdi+10h], rax
0x18002225b  mov     [rbp+phkResult], r13
0x18002225f  mov     rcx, [rbx+8]
0x180022263  cmp     [rcx], rbx
0x180022266  jnz     loc_1800222FE
0x18002226c  lea     rax, [rdi+20h]
0x180022270  mov     [rax], rbx
0x180022273  mov     [rax+8], rcx
0x180022277  mov     [rcx], rax
0x18002227a  mov     [rbx+8], rax
0x18002227e  mov     edi, r13d
0x180022281  mov     rcx, [rbp+phkResult]; hKey
0x180022285  test    rcx, rcx
0x180022288  jz      short loc_180022290
0x18002228a  call    cs:__imp_RegCloseKey
0x180022290  test    edi, edi
0x180022292  jnz     short loc_1800222A1
0x180022294  inc     r15d
0x180022297  cmp     r15d, [rbp+cSubKeys]
0x18002229b  jb      loc_180022112
0x1800222a1  call    cs:__imp_GetProcessHeap
0x1800222a7  mov     r8, r12; lpMem
0x1800222aa  xor     edx, edx; dwFlags
0x1800222ac  mov     rcx, rax; hHeap
0x1800222af  call    cs:__imp_HeapFree
0x1800222b5  mov     rbx, [rsi]
0x1800222b8  jmp     short loc_1800222E8
0x1800222ba  lea     rcx, [rbx-20h]
0x1800222be  cmp     [rcx+18h], r13d
0x1800222c2  jz      short loc_1800222E5
0x1800222c4  mov     rdx, [rbx]
0x1800222c7  cmp     [rdx+8], rbx
0x1800222cb  jnz     short loc_1800222FE
0x1800222cd  mov     rax, [rbx+8]
0x1800222d1  cmp     [rax], rbx
0x1800222d4  jnz     short loc_1800222FE
0x1800222d6  mov     [rax], rdx
0x1800222d9  mov     rbx, rax
0x1800222dc  mov     [rdx+8], rax
0x1800222e0  call    FreeTransport
0x1800222e5  mov     rbx, [rbx]
0x1800222e8  cmp     rbx, rsi
0x1800222eb  jnz     short loc_1800222BA
0x1800222ed  mov     rcx, [r14+28h]; hKey
0x1800222f1  lea     rdx, [r14+30h]; lpftLastWriteTime
0x1800222f5  call    UpdateTimeStamp
0x1800222fa  mov     eax, edi
0x1800222fc  jmp     short loc_18002230A
0x1800222fe  mov     ecx, 3
0x180022303  int     29h; Win8: RtlFailFast(ecx)
0x180022305  mov     eax, 216h
0x18002230a  add     rsp, 78h
0x18002230e  pop     r15
0x180022310  pop     r14
0x180022312  pop     r13
0x180022314  pop     r12
0x180022316  pop     rdi
0x180022317  pop     rsi
0x180022318  pop     rbx
0x180022319  pop     rbp
0x18002231a  retn
```
