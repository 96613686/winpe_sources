# CRasDiagHelper::InitEntryFromGuid(void)

- ea: `0x180006fec`
- end: `0x1800075b0`
- name: `?InitEntryFromGuid@CRasDiagHelper@@AEAAJXZ`
- size: `1476`
- prototype: `__int64 __fastcall(CRasDiagHelper *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007b70`

## callees

- `0x180006fec`
- `0x18000b864`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800070b4`
- `KERNEL32!CloseHandle` at `0x1800070b4`
- `KERNEL32!GetCurrentThread` at `0x180007053`
- `KERNEL32!GetCurrentThread` at `0x180007053`
- `KERNEL32!SetLastError` at `0x18000703e`
- `KERNEL32!SetLastError` at `0x180007172`
- `KERNEL32!SetLastError` at `0x1800073ba`
- `KERNEL32!SetLastError` at `0x180007586`
- `KERNEL32!SetLastError` at `0x18000703e`
- `KERNEL32!SetLastError` at `0x180007172`
- `KERNEL32!SetLastError` at `0x1800073ba`
- `KERNEL32!SetLastError` at `0x180007586`
- `KERNEL32!GetLastError` at `0x18000707e`
- `KERNEL32!GetLastError` at `0x18000707e`
- `ADVAPI32!OpenThreadToken` at `0x18000706e`
- `ADVAPI32!OpenThreadToken` at `0x18000706e`
- `RASAPI32!RasEnumEntriesW` at `0x1800071a2`
- `RASAPI32!RasEnumEntriesW` at `0x1800071f8`
- `RASAPI32!RasEnumEntriesW` at `0x1800071a2`
- `RASAPI32!RasEnumEntriesW` at `0x1800071f8`
- `RASAPI32!RasGetEntryPropertiesW` at `0x1800072d0`
- `RASAPI32!RasGetEntryPropertiesW` at `0x180007330`
- `RASAPI32!RasGetEntryPropertiesW` at `0x1800072d0`
- `RASAPI32!RasGetEntryPropertiesW` at `0x180007330`
- `SHELL32!SHGetFolderPathW` at `0x1800070a1`
- `SHELL32!SHGetFolderPathW` at `0x1800070a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000728a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007027`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007159`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800071c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000728a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800072f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800071ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007247`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800072e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007392`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007426`

## pseudocode

```c
__int64 __fastcall CRasDiagHelper::InitEntryFromGuid(CRasDiagHelper *this)
{
  unsigned int v1; // r15d
  unsigned int v3; // eax
  WCHAR *pszPath; // rsi
  HANDLE CurrentThread; // rax
  int v6; // ebx
  __int64 v7; // rdx
  WCHAR *v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  const wchar_t *v12; // r9
  WCHAR *v13; // rdx
  WCHAR *v14; // rcx
  struct tagRASENTRYNAMEW *v15; // r13
  DWORD v16; // r12d
  struct tagRASENTRYNAMEW *v17; // rax
  struct tagRASENTRYNAMEW *v18; // rdi
  signed int EntryPropertiesW; // ebx
  struct tagRASENTRYNAMEW *v20; // rax
  __int64 v21; // rbx
  const WCHAR *szEntryName; // r12
  struct tagRASENTRYW *v23; // rdi
  const WCHAR *szPhonebookPath; // r13
  struct tagRASENTRYW *v25; // rax
  struct tagRASENTRYW *v26; // rsi
  int v27; // r8d
  _WORD *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  bool v32; // zf
  _WORD *v33; // rcx
  __int64 v34; // rdx
  _WORD *v35; // rax
  __int64 v36; // rcx
  _WORD *v37; // rcx
  DWORD dwType; // eax
  __int64 v39; // [rsp+38h] [rbp-20h]
  struct tagRASENTRYNAMEW *pv; // [rsp+40h] [rbp-18h]
  void *TokenHandle; // [rsp+A0h] [rbp+48h] BYREF
  DWORD v42; // [rsp+A8h] [rbp+50h] BYREF
  DWORD v43; // [rsp+B0h] [rbp+58h]
  unsigned int v44; // [rsp+B8h] [rbp+60h]

  v1 = 0;
  v3 = 0;
  v44 = 0;
  do
  {
    if ( v3 )
    {
      pszPath = 0;
    }
    else
    {
      pszPath = (WCHAR *)CoTaskMemAlloc(0x20Au);
      if ( pszPath )
      {
        TokenHandle = 0;
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
        {
          v6 = (unsigned __int16)SHGetFolderPathW(0, 26, TokenHandle, 0, pszPath);
          CloseHandle(TokenHandle);
          if ( !v6 )
          {
            v7 = 261;
            v8 = pszPath;
            do
            {
              if ( !*v8 )
                break;
              ++v8;
              --v7;
            }
            while ( v7 );
            v9 = (261 - v7) & -(__int64)(v7 != 0);
            if ( v7 )
            {
              v10 = 261 - v9;
              if ( (unsigned __int64)(261 - v9) > 1 )
              {
                v11 = 2147483646;
                v12 = L"\\Microsoft\\Network\\Connections\\Pbk\\rasphone.pbk";
                v13 = &pszPath[v9];
                do
                {
                  if ( !v11 )
                    break;
                  if ( !*v12 )
                    break;
                  *v13++ = *v12++;
                  --v11;
                  --v10;
                }
                while ( v10 );
                v14 = v13 - 1;
                if ( v10 )
                  v14 = v13;
                *v14 = 0;
              }
            }
          }
        }
        else
        {
          GetLastError();
        }
      }
      else
      {
        SetLastError(8u);
      }
    }
    v42 = 0;
    pv = 0;
    v15 = 0;
    v43 = 0;
    v16 = 0;
    LODWORD(TokenHandle) = 1048;
    v17 = (struct tagRASENTRYNAMEW *)CoTaskMemAlloc(0x418u);
    v18 = v17;
    if ( !v17 )
    {
LABEL_22:
      SetLastError(8u);
      EntryPropertiesW = -2147024882;
      goto LABEL_32;
    }
    v17->dwSize = (unsigned int)TokenHandle;
    EntryPropertiesW = RasEnumEntriesW(0, pszPath, v17, (LPDWORD)&TokenHandle, &v42);
    if ( EntryPropertiesW == 603 )
    {
      CoTaskMemFree(v18);
      v20 = (struct tagRASENTRYNAMEW *)CoTaskMemAlloc((unsigned int)TokenHandle);
      v18 = v20;
      if ( !v20 )
        goto LABEL_22;
      v20->dwSize = 1048;
      EntryPropertiesW = RasEnumEntriesW(0, pszPath, v20, (LPDWORD)&TokenHandle, &v42);
    }
    if ( EntryPropertiesW )
    {
      if ( v18 )
        CoTaskMemFree(v18);
      if ( EntryPropertiesW > 0 )
        EntryPropertiesW = (unsigned __int16)EntryPropertiesW | 0x80070000;
    }
    else
    {
      v16 = v42;
      EntryPropertiesW = 0;
      v43 = v42;
      v15 = v18;
      pv = v18;
    }
LABEL_32:
    if ( pszPath )
      CoTaskMemFree(pszPath);
    if ( EntryPropertiesW < 0 )
      break;
    if ( !v16 )
    {
LABEL_54:
      v1 = 0;
      goto LABEL_55;
    }
    while ( 1 )
    {
      v21 = v1;
      szEntryName = v15[v21].szEntryName;
      if ( !szEntryName )
      {
        v27 = -2147024809;
        EntryPropertiesW = -2147024809;
        goto LABEL_53;
      }
      LODWORD(TokenHandle) = 6724;
      v23 = (struct tagRASENTRYW *)CoTaskMemAlloc(0x1A44u);
      if ( !v23 )
        goto LABEL_52;
      szPhonebookPath = v15[v21].szPhonebookPath;
      v23->dwSize = (unsigned int)TokenHandle;
      EntryPropertiesW = RasGetEntryPropertiesW(szPhonebookPath, szEntryName, v23, (LPDWORD)&TokenHandle, 0, 0);
      if ( EntryPropertiesW == 603 )
      {
        CoTaskMemFree(v23);
        v25 = (struct tagRASENTRYW *)CoTaskMemAlloc((unsigned int)TokenHandle);
        v23 = v25;
        if ( v25 )
        {
          v25->dwSize = 6724;
          EntryPropertiesW = RasGetEntryPropertiesW(szPhonebookPath, szEntryName, v25, (LPDWORD)&TokenHandle, 0, 0);
          goto LABEL_41;
        }
LABEL_52:
        SetLastError(8u);
        v27 = -2147024888;
        EntryPropertiesW = -2147024888;
LABEL_53:
        LODWORD(v39) = v27;
        CRasLogger::Log(
          (char *)this + 1208,
          2,
          1,
          L"CRasDiagHelper",
          L"RasGetEntryProperties (%s,%s) failed with error: 0x%x.",
          (char *)this + 650,
          (char *)this + 136,
          v39);
        goto LABEL_54;
      }
LABEL_41:
      if ( EntryPropertiesW )
      {
        v26 = 0;
        CoTaskMemFree(v23);
        if ( EntryPropertiesW > 0 )
          EntryPropertiesW = (unsigned __int16)EntryPropertiesW | 0x80070000;
      }
      else
      {
        v26 = v23;
      }
      v27 = EntryPropertiesW;
      if ( EntryPropertiesW < 0 )
        goto LABEL_53;
      if ( v26 )
        break;
LABEL_50:
      if ( ++v1 >= v43 )
        goto LABEL_54;
      v15 = pv;
    }
    if ( *(_QWORD *)&v26->guidId.Data1 != *((_QWORD *)this + 14)
      || *(_QWORD *)v26->guidId.Data4 != *((_QWORD *)this + 15) )
    {
      CoTaskMemFree(v26);
      goto LABEL_50;
    }
    v1 = 0;
    v29 = (_WORD *)((char *)this + 650);
    v30 = 2147483646;
    v31 = 261;
    do
    {
      if ( !v30 )
        break;
      if ( !*szPhonebookPath )
        break;
      *v29++ = *szPhonebookPath++;
      --v30;
      --v31;
    }
    while ( v31 );
    v32 = v31 == 0;
    v33 = v29 - 1;
    v34 = 257;
    if ( !v32 )
      v33 = v29;
    v35 = (_WORD *)((char *)this + 136);
    *v33 = 0;
    v36 = 2147483646;
    do
    {
      if ( !v36 )
        break;
      if ( !*szEntryName )
        break;
      *v35++ = *szEntryName++;
      --v36;
      --v34;
    }
    while ( v34 );
    v37 = v35 - 1;
    if ( v34 )
      v37 = v35;
    *v37 = 0;
    *((_BYTE *)this + 1176) = v26->szCustomDialDll[0] != 0;
    dwType = v26->dwType;
    switch ( dwType )
    {
      case 2u:
        *((_DWORD *)this + 293) = 0;
        break;
      case 1u:
        *((_DWORD *)this + 293) = 1;
        break;
      case 5u:
        *((_DWORD *)this + 293) = 2;
        break;
    }
    *((_QWORD *)this + 148) = v26;
LABEL_55:
    if ( pv )
      CoTaskMemFree(pv);
    if ( *((_QWORD *)this + 148) )
      return (unsigned int)EntryPropertiesW;
    if ( EntryPropertiesW < 0 )
      goto LABEL_61;
    v3 = v44 + 1;
    v44 = v3;
  }
  while ( v3 < 2 );
  if ( !*((_QWORD *)this + 148) )
  {
LABEL_61:
    EntryPropertiesW = -2147024809;
    CRasLogger::Log(
      (char *)this + 1208,
      2,
      1,
      L"CRasDiagHelper",
      L"Unable to enumerate the entry from the input GUID. Possibly improper GUID passed.");
  }
  return (unsigned int)EntryPropertiesW;
}

```

## disassembly

```asm
0x180006fec  push    rbp
0x180006fee  push    rbx
0x180006fef  push    rsi
0x180006ff0  push    rdi
0x180006ff1  push    r12
0x180006ff3  push    r13
0x180006ff5  push    r14
0x180006ff7  push    r15
0x180006ff9  mov     rbp, rsp
0x180006ffc  sub     rsp, 58h
0x180007000  xor     r15d, r15d
0x180007003  mov     r14, rcx
0x180007006  mov     eax, r15d
0x180007009  mov     r12d, 105h
0x18000700f  mov     [rbp+arg_18], eax
0x180007012  lea     edi, [r15+1]
0x180007016  test    eax, eax
0x180007018  jz      short loc_180007022
0x18000701a  mov     rsi, r15
0x18000701d  jmp     loc_18000713D
0x180007022  mov     ecx, 20Ah; cb
0x180007027  call    cs:__imp_CoTaskMemAlloc
0x18000702e  nop     dword ptr [rax+rax+00h]
0x180007033  mov     rsi, rax
0x180007036  test    rax, rax
0x180007039  jnz     short loc_18000704F
0x18000703b  lea     ecx, [rax+8]; dwErrCode
0x18000703e  call    cs:__imp_SetLastError
0x180007045  nop     dword ptr [rax+rax+00h]
0x18000704a  jmp     loc_18000713D
0x18000704f  mov     [rbp+TokenHandle], r15
0x180007053  call    cs:__imp_GetCurrentThread
0x18000705a  nop     dword ptr [rax+rax+00h]
0x18000705f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180007063  xor     r8d, r8d; OpenAsSelf
0x180007066  mov     rcx, rax; ThreadHandle
0x180007069  mov     edx, 20008h; DesiredAccess
0x18000706e  call    cs:__imp_OpenThreadToken
0x180007075  nop     dword ptr [rax+rax+00h]
0x18000707a  test    eax, eax
0x18000707c  jnz     short loc_18000708F
0x18000707e  call    cs:__imp_GetLastError
0x180007085  nop     dword ptr [rax+rax+00h]
0x18000708a  jmp     loc_18000713D
0x18000708f  mov     r8, [rbp+TokenHandle]; hToken
0x180007093  xor     r9d, r9d; dwFlags
0x180007096  xor     ecx, ecx; hwnd
0x180007098  mov     [rsp+58h+pszPath], rsi; pszPath
0x18000709d  lea     edx, [r9+1Ah]; csidl
0x1800070a1  call    cs:__imp_SHGetFolderPathW
0x1800070a8  nop     dword ptr [rax+rax+00h]
0x1800070ad  mov     rcx, [rbp+TokenHandle]; hObject
0x1800070b1  movzx   ebx, ax
0x1800070b4  call    cs:__imp_CloseHandle
0x1800070bb  nop     dword ptr [rax+rax+00h]
0x1800070c0  test    ebx, ebx
0x1800070c2  jnz     short loc_18000713D
0x1800070c4  mov     rdx, r12
0x1800070c7  mov     rax, rsi
0x1800070ca  cmp     [rax], r15w
0x1800070ce  jz      short loc_1800070D9
0x1800070d0  add     rax, 2
0x1800070d4  sub     rdx, rdi
0x1800070d7  jnz     short loc_1800070CA
0x1800070d9  mov     rcx, r12
0x1800070dc  mov     rax, rdx
0x1800070df  sub     rcx, rdx
0x1800070e2  neg     rax
0x1800070e5  sbb     r8, r8
0x1800070e8  and     r8, rcx
0x1800070eb  test    rdx, rdx
0x1800070ee  jz      short loc_18000713D
0x1800070f0  mov     rax, r12
0x1800070f3  sub     rax, r8
0x1800070f6  cmp     rax, rdi
0x1800070f9  jbe     short loc_18000713D
0x1800070fb  mov     ecx, 7FFFFFFEh
0x180007100  lea     r9, aMicrosoftNetwo; "\\Microsoft\\Network\\Connections\\Pbk"...
0x180007107  lea     rdx, [rsi+r8*2]
0x18000710b  test    rcx, rcx
0x18000710e  jz      short loc_18000712E
0x180007110  movzx   r8d, word ptr [r9]
0x180007114  test    r8w, r8w
0x180007118  jz      short loc_18000712E
0x18000711a  mov     [rdx], r8w
0x18000711e  add     r9, 2
0x180007122  add     rdx, 2
0x180007126  sub     rcx, rdi
0x180007129  sub     rax, rdi
0x18000712c  jnz     short loc_18000710B
0x18000712e  test    rax, rax
0x180007131  lea     rcx, [rdx-2]
0x180007135  cmovnz  rcx, rdx
0x180007139  mov     [rcx], r15w
0x18000713d  mov     eax, 418h
0x180007142  mov     [rbp+arg_8], r15d
0x180007146  mov     ecx, eax; cb
0x180007148  mov     [rbp+pv], r15
0x18000714c  mov     r13, r15
0x18000714f  mov     [rbp+arg_10], r15d
0x180007153  mov     r12d, r15d
0x180007156  mov     dword ptr [rbp+TokenHandle], eax
0x180007159  call    cs:__imp_CoTaskMemAlloc
0x180007160  nop     dword ptr [rax+rax+00h]
0x180007165  mov     rdi, rax
0x180007168  test    rax, rax
0x18000716b  jnz     short loc_180007188
0x18000716d  mov     ecx, 8; dwErrCode
0x180007172  call    cs:__imp_SetLastError
0x180007179  nop     dword ptr [rax+rax+00h]
0x18000717e  mov     ebx, 8007000Eh
0x180007183  jmp     loc_18000723F
0x180007188  mov     eax, dword ptr [rbp+TokenHandle]
0x18000718b  lea     r9, [rbp+TokenHandle]; LPDWORD
0x18000718f  mov     [rdi], eax
0x180007191  mov     r8, rdi; struct tagRASENTRYNAMEW *
0x180007194  lea     rax, [rbp+arg_8]
0x180007198  mov     rdx, rsi; LPCWSTR
0x18000719b  xor     ecx, ecx; LPCWSTR
0x18000719d  mov     [rsp+58h+pszPath], rax; LPDWORD
0x1800071a2  call    cs:__imp_RasEnumEntriesW
0x1800071a9  nop     dword ptr [rax+rax+00h]
0x1800071ae  mov     ebx, eax
0x1800071b0  cmp     eax, 25Bh
0x1800071b5  jnz     short loc_180007206
0x1800071b7  mov     rcx, rdi; pv
0x1800071ba  call    cs:__imp_CoTaskMemFree
0x1800071c1  nop     dword ptr [rax+rax+00h]
0x1800071c6  mov     ecx, dword ptr [rbp+TokenHandle]; cb
0x1800071c9  call    cs:__imp_CoTaskMemAlloc
0x1800071d0  nop     dword ptr [rax+rax+00h]
0x1800071d5  mov     rdi, rax
0x1800071d8  test    rax, rax
0x1800071db  jz      short loc_18000716D
0x1800071dd  mov     dword ptr [rax], 418h
0x1800071e3  lea     r9, [rbp+TokenHandle]; LPDWORD
0x1800071e7  lea     rax, [rbp+arg_8]
0x1800071eb  mov     r8, rdi; struct tagRASENTRYNAMEW *
0x1800071ee  mov     rdx, rsi; LPCWSTR
0x1800071f1  mov     [rsp+58h+pszPath], rax; LPDWORD
0x1800071f6  xor     ecx, ecx; LPCWSTR
0x1800071f8  call    cs:__imp_RasEnumEntriesW
0x1800071ff  nop     dword ptr [rax+rax+00h]
0x180007204  mov     ebx, eax
0x180007206  test    ebx, ebx
0x180007208  jz      short loc_18000722D
0x18000720a  test    rdi, rdi
0x18000720d  jz      short loc_18000721E
0x18000720f  mov     rcx, rdi; pv
0x180007212  call    cs:__imp_CoTaskMemFree
0x180007219  nop     dword ptr [rax+rax+00h]
0x18000721e  test    ebx, ebx
0x180007220  jle     short loc_18000723F
0x180007222  movzx   ebx, bx
0x180007225  or      ebx, 80070000h
0x18000722b  jmp     short loc_18000723F
0x18000722d  mov     r12d, [rbp+arg_8]
0x180007231  mov     ebx, r15d
0x180007234  mov     [rbp+arg_10], r12d
0x180007238  mov     r13, rdi
0x18000723b  mov     [rbp+pv], rdi
0x18000723f  test    rsi, rsi
0x180007242  jz      short loc_180007253
0x180007244  mov     rcx, rsi; pv
0x180007247  call    cs:__imp_CoTaskMemFree
0x18000724e  nop     dword ptr [rax+rax+00h]
0x180007253  test    ebx, ebx
0x180007255  js      loc_180007456
0x18000725b  mov     edi, 1
0x180007260  test    r12d, r12d
0x180007263  jz      loc_18000741A
0x180007269  mov     eax, r15d
0x18000726c  lea     r12, [r13+4]
0x180007270  imul    rbx, rax, 418h
0x180007277  add     r12, rbx
0x18000727a  jz      loc_1800075A1
0x180007280  mov     esi, 1A44h
0x180007285  mov     ecx, esi; cb
0x180007287  mov     dword ptr [rbp+TokenHandle], esi
0x18000728a  call    cs:__imp_CoTaskMemAlloc
0x180007291  nop     dword ptr [rax+rax+00h]
0x180007296  mov     rdi, rax
0x180007299  test    rax, rax
0x18000729c  jz      loc_180007581
0x1800072a2  mov     eax, dword ptr [rbp+TokenHandle]
0x1800072a5  lea     r9, [rbp+TokenHandle]; LPDWORD
0x1800072a9  add     r13, 20Ch
0x1800072b0  mov     [rsp+58h+var_30], 0; LPDWORD
0x1800072b9  add     r13, rbx
0x1800072bc  mov     [rdi], eax
0x1800072be  mov     rcx, r13; LPCWSTR
0x1800072c1  mov     [rsp+58h+pszPath], 0; LPBYTE
0x1800072ca  mov     r8, rdi; struct tagRASENTRYW *
0x1800072cd  mov     rdx, r12; LPCWSTR
0x1800072d0  call    cs:__imp_RasGetEntryPropertiesW
0x1800072d7  nop     dword ptr [rax+rax+00h]
0x1800072dc  mov     ebx, eax
0x1800072de  cmp     eax, 25Bh
0x1800072e3  jnz     short loc_18000733E
0x1800072e5  mov     rcx, rdi; pv
0x1800072e8  call    cs:__imp_CoTaskMemFree
0x1800072ef  nop     dword ptr [rax+rax+00h]
0x1800072f4  mov     ecx, dword ptr [rbp+TokenHandle]; cb
0x1800072f7  call    cs:__imp_CoTaskMemAlloc
0x1800072fe  nop     dword ptr [rax+rax+00h]
0x180007303  mov     rdi, rax
0x180007306  test    rax, rax
0x180007309  jz      loc_1800073B5
0x18000730f  mov     [rsp+58h+var_30], 0; LPDWORD
0x180007318  lea     r9, [rbp+TokenHandle]; LPDWORD
0x18000731c  mov     r8, rax; struct tagRASENTRYW *
0x18000731f  mov     [rsp+58h+pszPath], 0; LPBYTE
0x180007328  mov     rdx, r12; LPCWSTR
0x18000732b  mov     [rax], esi
0x18000732d  mov     rcx, r13; LPCWSTR
0x180007330  call    cs:__imp_RasGetEntryPropertiesW
0x180007337  nop     dword ptr [rax+rax+00h]
0x18000733c  mov     ebx, eax
0x18000733e  test    ebx, ebx
0x180007340  jnz     short loc_180007347
0x180007342  mov     rsi, rdi
0x180007345  jmp     short loc_180007365
0x180007347  mov     rcx, rdi; pv
0x18000734a  xor     esi, esi
0x18000734c  call    cs:__imp_CoTaskMemFree
0x180007353  nop     dword ptr [rax+rax+00h]
0x180007358  test    ebx, ebx
0x18000735a  jle     short loc_180007365
0x18000735c  movzx   ebx, bx
0x18000735f  or      ebx, 80070000h
0x180007365  mov     r8d, ebx
0x180007368  test    ebx, ebx
0x18000736a  js      short loc_1800073D0
0x18000736c  test    rsi, rsi
0x18000736f  jz      short loc_18000739E
0x180007371  mov     rax, [rsi+0DB4h]
0x180007378  cmp     rax, [r14+70h]
0x18000737c  jnz     short loc_18000738F
0x18000737e  mov     rax, [rsi+0DBCh]
0x180007385  cmp     rax, [r14+78h]
0x180007389  jz      loc_1800074A3
0x18000738f  mov     rcx, rsi; pv
0x180007392  call    cs:__imp_CoTaskMemFree
0x180007399  nop     dword ptr [rax+rax+00h]
0x18000739e  mov     edi, 1
0x1800073a3  add     r15d, edi
0x1800073a6  cmp     r15d, [rbp+arg_10]
0x1800073aa  jnb     short loc_18000741A
0x1800073ac  mov     r13, [rbp+pv]
0x1800073b0  jmp     loc_180007269
0x1800073b5  mov     ecx, 8; dwErrCode
0x1800073ba  call    cs:__imp_SetLastError
0x1800073c1  nop     dword ptr [rax+rax+00h]
0x1800073c6  mov     esi, 80070008h
0x1800073cb  mov     r8d, esi
0x1800073ce  mov     ebx, esi
0x1800073d0  mov     edi, 1
0x1800073d5  mov     dword ptr [rsp+58h+var_20], r8d
0x1800073da  lea     rdx, [r14+28Ah]
0x1800073e1  lea     rax, [r14+88h]
0x1800073e8  movsx   r8d, di
0x1800073ec  mov     [rsp+58h+var_28], rax
0x1800073f1  lea     rcx, [r14+4B8h]
0x1800073f8  mov     [rsp+58h+var_30], rdx
0x1800073fd  lea     rax, aRasgetentrypro; "RasGetEntryProperties (%s,%s) failed wi"...
0x180007404  mov     edx, 2
0x180007409  mov     [rsp+58h+pszPath], rax
0x18000740e  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x180007415  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000741a  xor     r15d, r15d
0x18000741d  mov     rcx, [rbp+pv]; pv
0x180007421  test    rcx, rcx
0x180007424  jz      short loc_180007432
0x180007426  call    cs:__imp_CoTaskMemFree
0x18000742d  nop     dword ptr [rax+rax+00h]
0x180007432  cmp     [r14+4A0h], r15
0x180007439  jnz     short loc_18000748F
0x18000743b  test    ebx, ebx
0x18000743d  js      short loc_18000745F
0x18000743f  mov     eax, [rbp+arg_18]
0x180007442  mov     r12d, 105h
0x180007448  add     eax, edi
0x18000744a  mov     [rbp+arg_18], eax
0x18000744d  cmp     eax, 2
0x180007450  jb      loc_180007016
0x180007456  cmp     [r14+4A0h], r15
0x18000745d  jnz     short loc_18000748F
0x18000745f  lea     rax, aUnableToEnumer; "Unable to enumerate the entry from the "...
0x180007466  mov     ebx, 80070057h
0x18000746b  mov     [rsp+58h+pszPath], rax
0x180007470  lea     rcx, [r14+4B8h]
0x180007477  mov     eax, 1
0x18000747c  lea     r9, aCrasdiaghelper; "CRasDiagHelper"
0x180007483  movsx   r8d, ax
0x180007487  lea     edx, [rax+1]
0x18000748a  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000748f  mov     eax, ebx
0x180007491  add     rsp, 58h
0x180007495  pop     r15
0x180007497  pop     r14
  ... truncated ...
```
