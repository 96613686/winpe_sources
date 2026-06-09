# DaRpcListHostsInLan

- ea: `0x140009180`
- end: `0x140009701`
- name: `DaRpcListHostsInLan`
- size: `1409`
- prototype: `__int64 __fastcall(__int64, int, const wchar_t *, unsigned int, _BYTE *, _DWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task`

## callees

- `0x140002300`
- `0x140002c00`
- `0x140002c40`
- `0x140002fbc`
- `0x140004868`
- `0x140004e64`
- `0x140004f0c`
- `0x140009180`
- `0x140009e0c`
- `0x14000a364`
- `0x14001830e`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140009439`
- `ADVAPI32!RegOpenKeyExW` at `0x140009439`
- `ADVAPI32!RegCloseKey` at `0x1400094cf`
- `ADVAPI32!RegCloseKey` at `0x1400094cf`
- `KERNEL32!EnterCriticalSection` at `0x140009272`
- `KERNEL32!EnterCriticalSection` at `0x1400092f4`
- `KERNEL32!EnterCriticalSection` at `0x140009272`
- `KERNEL32!EnterCriticalSection` at `0x1400092f4`
- `KERNEL32!GlobalFree` at `0x1400094a7`
- `KERNEL32!GlobalFree` at `0x1400094a7`
- `KERNEL32!LeaveCriticalSection` at `0x1400092a7`
- `KERNEL32!LeaveCriticalSection` at `0x1400095e8`
- `KERNEL32!LeaveCriticalSection` at `0x14000966c`
- `KERNEL32!LeaveCriticalSection` at `0x1400092a7`
- `KERNEL32!LeaveCriticalSection` at `0x1400095e8`
- `KERNEL32!LeaveCriticalSection` at `0x14000966c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140009350`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140009350`
- `KERNEL32!GetLastError` at `0x140009445`
- `KERNEL32!GetLastError` at `0x140009445`
- `msvcrt!_snwprintf_s` at `0x140009414`
- `msvcrt!_snwprintf_s` at `0x140009414`
- `msvcrt!_wcsicmp` at `0x14000928d`
- `msvcrt!_wcsicmp` at `0x14000928d`

## string_xrefs

- `0x140009404`: `SYSTEM\CurrentControlSet\Services\NfsClnt\NFS LANS`

## pseudocode

```c
__int64 __fastcall DaRpcListHostsInLan(
        __int64 a1,
        int a2,
        const wchar_t *a3,
        unsigned int a4,
        _BYTE *a5,
        _DWORD *a6,
        unsigned int *a7)
{
  unsigned int *v7; // r15
  __int64 v10; // r12
  _QWORD *v11; // rcx
  __int64 *i; // rdi
  const wchar_t *v13; // rcx
  DWORD LastError; // ebx
  struct _RTL_CRITICAL_SECTION *v15; // r13
  __int64 v16; // rax
  _QWORD *v17; // rcx
  int v18; // edx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  _QWORD *v21; // rax
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rdi
  __int64 v25; // rcx
  unsigned int v26; // esi
  _QWORD *j; // rbx
  __int64 v28; // r8
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v31; // [rsp+38h] [rbp-C8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  char v33[24]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = a7;
  strcpy(v33, "DaRpcListHostsInLan");
  v10 = a4;
  v31 = a7;
  SystemTimeAsFileTime = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v33);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a2 && (_DWORD)v10 && a3 && a5 && a6 && a7 )
  {
    *a6 = 0;
    *a5 = 0;
    EnterCriticalSection(&LanListCS);
    for ( i = (__int64 *)pLanHead; i; i = (__int64 *)i[6] )
    {
      v13 = (const wchar_t *)i[1];
      if ( v13 )
      {
        if ( !_wcsicmp(v13, a3) )
          break;
      }
    }
    LeaveCriticalSection(&LanListCS);
    if ( !i )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v33);
      LastError = 87;
      goto LABEL_69;
    }
    v15 = (struct _RTL_CRITICAL_SECTION *)(i + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(i + 8));
    v16 = i[3];
    if ( !v16 || *(_DWORD *)(v16 + 20) != 2 )
    {
LABEL_34:
      if ( *((_DWORD *)i + 4) == 1 )
      {
        hKey = 0;
        memset_0(Buffer, 0, 0x208u);
        _snwprintf_s(Buffer, 0x104u, 0x103u, L"%s\\%s", L"SYSTEM\\CurrentControlSet\\Services\\NfsClnt\\NFS LANS", i[1]);
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              75,
              (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
              (unsigned int)v33,
              i[1],
              LastError);
LABEL_68:
          LeaveCriticalSection(v15);
LABEL_69:
          *v7 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              80,
              &WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
              LastError);
          return LastError;
        }
        v19 = (_QWORD *)i[4];
        if ( v19 )
        {
          do
          {
            v20 = (_QWORD *)v19[2];
            GlobalFree(v19);
            v19 = v20;
          }
          while ( v20 );
        }
        i[4] = 0;
        LastError = ReadHostsList(i, hKey);
        RegCloseKey(hKey);
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              76,
              (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids,
              (unsigned int)v33,
              LastError);
          goto LABEL_68;
        }
      }
      v21 = (_QWORD *)i[4];
      v22 = 0;
      while ( v21 )
      {
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(*v21 + 2 * v23) );
        v21 = (_QWORD *)v21[2];
        v22 = (unsigned int)(v22 + 2 * v23 + 18);
      }
      *a6 = v22;
      if ( (unsigned int)v22 <= (unsigned int)v10 )
      {
        v24 = i[4];
        v25 = (__int64)&a5[v10];
        v26 = 0;
        for ( j = a5; ; j += 2 )
        {
          if ( !v24 )
          {
            LeaveCriticalSection(v15);
            *v31 = v26;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v26);
            return 0;
          }
          hKey = *(HKEY *)v24;
          v25 = PackString(&hKey, j, &NameStrings, v25);
          if ( j < (_QWORD *)a5 || j > (_QWORD *)&a5[v10 - 16] )
            break;
          ++v26;
          *j = v25 - (_QWORD)a5;
          v24 = *(_QWORD *)(v24 + 16);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_qqD(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, v28, j, a5, v10);
        v7 = v31;
        LastError = 59;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v22);
        LastError = 234;
      }
      goto LABEL_68;
    }
    if ( i[4] )
    {
      hKey = (HKEY)i[5];
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( (unsigned int)((*(_QWORD *)&SystemTimeAsFileTime - (_QWORD)hKey) / 0x2710uLL) <= *(_DWORD *)(i[3] + 12) )
        goto LABEL_32;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_31:
        *(_DWORD *)i |= 1u;
LABEL_32:
        if ( (*(_BYTE *)i & 1) != 0 )
          RPCBroadcast(i);
        goto LABEL_34;
      }
      v18 = 74;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_31;
      v18 = 73;
    }
    WPP_SF_sS(v17[2], v18, (unsigned int)&WPP_4b94345935ba3175354bb878a9e98408_Traceguids, (unsigned int)v33, i[1]);
    goto LABEL_31;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
    WPP_SF_s(v11[2], 71, &WPP_4b94345935ba3175354bb878a9e98408_Traceguids, v33);
  return 87;
}

```

## disassembly

```asm
0x140009180  mov     [rsp-8+arg_0], rbx
0x140009185  push    rbp
0x140009186  push    rsi
0x140009187  push    rdi
0x140009188  push    r12
0x14000918a  push    r13
0x14000918c  push    r14
0x14000918e  push    r15
0x140009190  lea     rbp, [rsp-180h]
0x140009198  sub     rsp, 280h
0x14000919f  mov     rax, cs:__security_cookie
0x1400091a6  xor     rax, rsp
0x1400091a9  mov     [rbp+1B0h+var_40], rax
0x1400091b0  movups  xmm0, xmmword ptr cs:aDarpclisthosts; "DaRpcListHostsInLan"
0x1400091b7  mov     r15, [rbp+1B0h+arg_30]
0x1400091be  xor     r13d, r13d
0x1400091c1  mov     eax, dword ptr cs:aDarpclisthosts+10h; "Lan"
0x1400091c7  mov     rbx, r8
0x1400091ca  mov     r14, [rbp+1B0h+arg_20]
0x1400091d1  mov     edi, edx
0x1400091d3  mov     rsi, [rbp+1B0h+arg_28]
0x1400091da  movups  xmmword ptr [rsp+2B0h+var_268], xmm0
0x1400091df  mov     r12d, r9d
0x1400091e2  mov     [rsp+2B0h+var_278], r15
0x1400091e7  mov     dword ptr [rsp+2B0h+var_268+10h], eax
0x1400091eb  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1400091f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091f7  lea     rax, WPP_GLOBAL_Control
0x1400091fe  cmp     rcx, rax
0x140009201  jz      short loc_140009230
0x140009203  test    byte ptr [rcx+1Ch], 1
0x140009207  jz      short loc_140009230
0x140009209  mov     rcx, [rcx+10h]
0x14000920d  lea     edx, [r13+46h]
0x140009211  lea     r9, [rsp+2B0h+var_268]
0x140009216  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000921d  call    WPP_SF_s
0x140009222  mov     rcx, cs:WPP_GLOBAL_Control
0x140009229  lea     rax, WPP_GLOBAL_Control
0x140009230  test    edi, edi
0x140009232  jz      loc_1400096AD
0x140009238  test    r12d, r12d
0x14000923b  jz      loc_1400096AD
0x140009241  test    rbx, rbx
0x140009244  jz      loc_1400096AD
0x14000924a  test    r14, r14
0x14000924d  jz      loc_1400096AD
0x140009253  test    rsi, rsi
0x140009256  jz      loc_1400096AD
0x14000925c  test    r15, r15
0x14000925f  jz      loc_1400096AD
0x140009265  mov     [rsi], r13d
0x140009268  lea     rcx, LanListCS; lpCriticalSection
0x14000926f  mov     [r14], r13b
0x140009272  call    cs:__imp_EnterCriticalSection
0x140009278  mov     rdi, cs:pLanHead
0x14000927f  jmp     short loc_14000929B
0x140009281  mov     rcx, [rdi+8]; String1
0x140009285  test    rcx, rcx
0x140009288  jz      short loc_140009297
0x14000928a  mov     rdx, rbx; String2
0x14000928d  call    cs:__imp__wcsicmp
0x140009293  test    eax, eax
0x140009295  jz      short loc_1400092A0
0x140009297  mov     rdi, [rdi+30h]
0x14000929b  test    rdi, rdi
0x14000929e  jnz     short loc_140009281
0x1400092a0  lea     rcx, LanListCS; lpCriticalSection
0x1400092a7  call    cs:__imp_LeaveCriticalSection
0x1400092ad  test    rdi, rdi
0x1400092b0  jnz     short loc_1400092ED
0x1400092b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092b9  lea     rax, WPP_GLOBAL_Control
0x1400092c0  cmp     rcx, rax
0x1400092c3  jz      short loc_1400092E3
0x1400092c5  test    byte ptr [rcx+1Ch], 2
0x1400092c9  jz      short loc_1400092E3
0x1400092cb  mov     rcx, [rcx+10h]
0x1400092cf  lea     edx, [rdi+48h]
0x1400092d2  lea     r9, [rsp+2B0h+var_268]
0x1400092d7  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x1400092de  call    WPP_SF_s
0x1400092e3  mov     ebx, 57h ; 'W'
0x1400092e8  jmp     loc_140009675
0x1400092ed  lea     r13, [rdi+40h]
0x1400092f1  mov     rcx, r13; lpCriticalSection
0x1400092f4  call    cs:__imp_EnterCriticalSection
0x1400092fa  mov     rax, [rdi+18h]
0x1400092fe  xor     r8d, r8d
0x140009301  test    rax, rax
0x140009304  jz      loc_1400093C9
0x14000930a  cmp     dword ptr [rax+14h], 2
0x14000930e  jnz     loc_1400093C9
0x140009314  cmp     [rdi+20h], r8
0x140009318  jnz     short loc_14000933D
0x14000931a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009321  lea     rax, WPP_GLOBAL_Control
0x140009328  cmp     rcx, rax
0x14000932b  jz      loc_1400093B6
0x140009331  test    byte ptr [rcx+1Ch], 10h
0x140009335  jz      short loc_1400093B6
0x140009337  lea     edx, [r8+49h]
0x14000933b  jmp     short loc_140009398
0x14000933d  mov     eax, [rdi+28h]
0x140009340  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140009345  mov     dword ptr [rsp+2B0h+hKey], eax
0x140009349  mov     eax, [rdi+2Ch]
0x14000934c  mov     dword ptr [rsp+2B0h+hKey+4], eax
0x140009350  call    cs:__imp_GetSystemTimeAsFileTime
0x140009356  mov     rcx, qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime]
0x14000935b  mov     rax, 346DC5D63886594Bh
0x140009365  sub     rcx, [rsp+2B0h+hKey]
0x14000936a  mul     rcx
0x14000936d  mov     rax, [rdi+18h]
0x140009371  shr     rdx, 0Bh
0x140009375  cmp     edx, [rax+0Ch]
0x140009378  jbe     short loc_1400093B9
0x14000937a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009381  lea     rax, WPP_GLOBAL_Control
0x140009388  cmp     rcx, rax
0x14000938b  jz      short loc_1400093B6
0x14000938d  test    byte ptr [rcx+1Ch], 10h
0x140009391  jz      short loc_1400093B6
0x140009393  mov     edx, 4Ah ; 'J'
0x140009398  mov     rax, [rdi+8]
0x14000939c  lea     r9, [rsp+2B0h+var_268]
0x1400093a1  mov     rcx, [rcx+10h]
0x1400093a5  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x1400093ac  mov     [rsp+2B0h+phkResult], rax
0x1400093b1  call    WPP_SF_sS
0x1400093b6  or      dword ptr [rdi], 1
0x1400093b9  test    byte ptr [rdi], 1
0x1400093bc  jz      short loc_1400093C6
0x1400093be  mov     rcx, rdi; void *
0x1400093c1  call    RPCBroadcast
0x1400093c6  xor     r8d, r8d
0x1400093c9  cmp     dword ptr [rdi+10h], 1
0x1400093cd  jnz     loc_14000951F
0x1400093d3  mov     [rsp+2B0h+hKey], r8
0x1400093d8  lea     rcx, [rsp+2B0h+Buffer]; void *
0x1400093dd  mov     r8d, 208h; Size
0x1400093e3  xor     edx, edx; Val
0x1400093e5  call    memset_0
0x1400093ea  mov     rax, [rdi+8]
0x1400093ee  lea     r9, aSS; "%s\\%s"
0x1400093f5  mov     [rsp+2B0h+var_288], rax
0x1400093fa  lea     rcx, [rsp+2B0h+Buffer]; Buffer
0x1400093ff  mov     edx, 104h; BufferCount
0x140009404  lea     rax, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Nf"...
0x14000940b  mov     [rsp+2B0h+phkResult], rax
0x140009410  lea     r8d, [rdx-1]; MaxCount
0x140009414  call    cs:__imp__snwprintf_s
0x14000941a  lea     rax, [rsp+2B0h+hKey]
0x14000941f  mov     r9d, 20019h; samDesired
0x140009425  xor     r8d, r8d; ulOptions
0x140009428  mov     [rsp+2B0h+phkResult], rax; phkResult
0x14000942d  lea     rdx, [rsp+2B0h+Buffer]; lpSubKey
0x140009432  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009439  call    cs:__imp_RegOpenKeyExW
0x14000943f  xor     edx, edx
0x140009441  test    eax, eax
0x140009443  jz      short loc_14000949A
0x140009445  call    cs:__imp_GetLastError
0x14000944b  mov     ebx, eax
0x14000944d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009454  lea     rax, WPP_GLOBAL_Control
0x14000945b  cmp     rcx, rax
0x14000945e  jz      loc_140009669
0x140009464  test    byte ptr [rcx+1Ch], 2
0x140009468  jz      loc_140009669
0x14000946e  mov     r8, [rdi+8]
0x140009472  lea     r9, [rsp+2B0h+var_268]
0x140009477  mov     rcx, [rcx+10h]
0x14000947b  mov     edx, 4Bh ; 'K'
0x140009480  mov     dword ptr [rsp+2B0h+var_288], ebx
0x140009484  mov     [rsp+2B0h+phkResult], r8
0x140009489  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140009490  call    WPP_SF_sSd
0x140009495  jmp     loc_140009669
0x14000949a  mov     rcx, [rdi+20h]; hMem
0x14000949e  test    rcx, rcx
0x1400094a1  jz      short loc_1400094B7
0x1400094a3  mov     rbx, [rcx+10h]
0x1400094a7  call    cs:__imp_GlobalFree
0x1400094ad  mov     rcx, rbx
0x1400094b0  test    rbx, rbx
0x1400094b3  jnz     short loc_1400094A3
0x1400094b5  xor     edx, edx
0x1400094b7  mov     [rdi+20h], rdx
0x1400094bb  mov     rcx, rdi
0x1400094be  mov     rdx, [rsp+2B0h+hKey]
0x1400094c3  call    ReadHostsList
0x1400094c8  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400094cd  mov     ebx, eax
0x1400094cf  call    cs:__imp_RegCloseKey
0x1400094d5  xor     r8d, r8d
0x1400094d8  test    ebx, ebx
0x1400094da  jz      short loc_14000951F
0x1400094dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400094e3  lea     rax, WPP_GLOBAL_Control
0x1400094ea  cmp     rcx, rax
0x1400094ed  jz      loc_140009669
0x1400094f3  test    byte ptr [rcx+1Ch], 2
0x1400094f7  jz      loc_140009669
0x1400094fd  mov     rcx, [rcx+10h]
0x140009501  lea     edx, [r8+4Ch]
0x140009505  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000950c  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x140009510  lea     r9, [rsp+2B0h+var_268]
0x140009515  call    WPP_SF_sd
0x14000951a  jmp     loc_140009669
0x14000951f  mov     rax, [rdi+20h]
0x140009523  mov     r9d, r8d
0x140009526  jmp     short loc_140009545
0x140009528  mov     rdx, [rax]
0x14000952b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14000952f  inc     rcx
0x140009532  cmp     [rdx+rcx*2], r8w
0x140009537  jnz     short loc_14000952F
0x140009539  mov     rax, [rax+10h]
0x14000953d  lea     r9d, [r9+rcx*2]
0x140009541  add     r9d, 12h
0x140009545  test    rax, rax
0x140009548  jnz     short loc_140009528
0x14000954a  mov     [rsi], r9d
0x14000954d  cmp     r9d, r12d
0x140009550  jbe     short loc_14000958A
0x140009552  mov     rcx, cs:WPP_GLOBAL_Control
0x140009559  lea     rax, WPP_GLOBAL_Control
0x140009560  cmp     rcx, rax
0x140009563  jz      short loc_140009580
0x140009565  test    byte ptr [rcx+1Ch], 2
0x140009569  jz      short loc_140009580
0x14000956b  mov     rcx, [rcx+10h]
0x14000956f  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x140009576  mov     edx, 4Dh ; 'M'
0x14000957b  call    WPP_SF_d
0x140009580  mov     ebx, 0EAh
0x140009585  jmp     loc_140009669
0x14000958a  mov     rdi, [rdi+20h]
0x14000958e  lea     r15, [r14+r12]
0x140009592  mov     rcx, r15
0x140009595  mov     esi, r8d
0x140009598  mov     rbx, r14
0x14000959b  jmp     short loc_1400095E0
0x14000959d  mov     rax, [rdi]
0x1400095a0  lea     r8, NameStrings
0x1400095a7  mov     r9, rcx
0x1400095aa  mov     [rsp+2B0h+hKey], rax
0x1400095af  lea     rcx, [rsp+2B0h+hKey]
0x1400095b4  mov     rdx, rbx
0x1400095b7  call    PackString
0x1400095bc  mov     rcx, rax
0x1400095bf  cmp     rbx, r14
0x1400095c2  jb      short loc_14000962B
0x1400095c4  lea     rax, [r15-10h]
0x1400095c8  cmp     rbx, rax
0x1400095cb  ja      short loc_14000962B
0x1400095cd  mov     rax, rcx
0x1400095d0  inc     esi
0x1400095d2  sub     rax, r14
0x1400095d5  mov     [rbx], rax
0x1400095d8  add     rbx, 10h
0x1400095dc  mov     rdi, [rdi+10h]
0x1400095e0  test    rdi, rdi
0x1400095e3  jnz     short loc_14000959D
0x1400095e5  mov     rcx, r13; lpCriticalSection
0x1400095e8  call    cs:__imp_LeaveCriticalSection
0x1400095ee  mov     rax, [rsp+2B0h+var_278]
0x1400095f3  mov     [rax], esi
0x1400095f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095fc  lea     rax, WPP_GLOBAL_Control
0x140009603  cmp     rcx, rax
0x140009606  jz      short loc_140009624
0x140009608  test    byte ptr [rcx+1Ch], 1
0x14000960c  jz      short loc_140009624
0x14000960e  mov     rcx, [rcx+10h]
0x140009612  lea     edx, [rdi+4Fh]
0x140009615  mov     r9d, esi
0x140009618  lea     r8, WPP_4b94345935ba3175354bb878a9e98408_Traceguids
0x14000961f  call    WPP_SF_d
0x140009624  xor     eax, eax
0x140009626  jmp     loc_1400096D7
0x14000962b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009632  lea     rax, WPP_GLOBAL_Control
0x140009639  cmp     rcx, rax
0x14000963c  jz      short loc_14000965F
0x14000963e  test    byte ptr [rcx+1Ch], 2
0x140009642  jz      short loc_14000965F
0x140009644  mov     rcx, [rcx+10h]
0x140009648  mov     edx, 4Eh ; 'N'
0x14000964d  mov     dword ptr [rsp+2B0h+var_288], r12d
0x140009652  mov     r9, rbx
0x140009655  mov     [rsp+2B0h+phkResult], r14
0x14000965a  call    WPP_SF_qqD
0x14000965f  mov     r15, [rsp+2B0h+var_278]
0x140009664  mov     ebx, 3Bh ; ';'
0x140009669  mov     rcx, r13; lpCriticalSection
0x14000966c  call    cs:__imp_LeaveCriticalSection
0x140009672  xor     r13d, r13d
  ... truncated ...
```
