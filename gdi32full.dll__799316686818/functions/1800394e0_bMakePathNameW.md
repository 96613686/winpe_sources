# bMakePathNameW

- ea: `0x1800394e0`
- end: `0x180039762`
- name: `bMakePathNameW`
- size: `642`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer, LPCWSTR lpFileName, LPWSTR *lpFilePart)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180038d10`
- `0x180039150`
- `0x180039770`
- `0x18007db20`
- `0x18007e390`
- `0x18007e620`

## callees

- `0x1800394e0`
- `0x180039d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800395c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800396f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800395c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800396f2`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003958b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180039636`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003974b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003958b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180039636`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18003974b`
- `ntdll!RtlEnterCriticalSection` at `0x180039521`
- `ntdll!RtlEnterCriticalSection` at `0x180039521`
- `ntdll!RtlLeaveCriticalSection` at `0x180039543`
- `ntdll!RtlLeaveCriticalSection` at `0x180039543`

## pseudocode

```c
_BOOL8 __fastcall bMakePathNameW(LPWSTR lpBuffer, LPCWSTR lpFileName, LPWSTR *lpFilePart, _DWORD *a4)
{
  LPWSTR *v7; // r13
  int inited; // ebx
  DWORD v9; // eax
  DWORD v10; // ebx
  bool v11; // zf
  __int64 v13; // rbp
  WCHAR *i; // rcx
  __int64 v15; // r9
  DWORD v16; // eax
  __int64 v17; // r15
  DWORD v18; // r14d
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbp
  const WCHAR *v23; // rdx
  WCHAR v24; // cx
  const WCHAR *v25; // rax
  DWORD v26; // eax
  __int64 v27; // [rsp+90h] [rbp+18h] BYREF

  v27 = 0;
  if ( a4 )
    *a4 = 0;
  v7 = (LPWSTR *)&v27;
  if ( lpFilePart )
    v7 = lpFilePart;
  RtlEnterCriticalSection(&semLocal);
  inited = bInitSystemAndFontsDirectoriesW(&gpwcSystemDir, &gpwcFontsDir);
  RtlLeaveCriticalSection(&semLocal);
  if ( !inited )
    return 0;
  if ( *lpFileName != 92 && (lpFileName[1] != 58 || lpFileName[2] != 92) )
  {
    if ( a4 )
      *a4 |= 4u;
    v9 = SearchPathW(gpwcFontsDir, lpFileName, 0, 0x104u, lpBuffer, v7);
    v10 = v9;
    if ( v9 >= 0x104 )
      return 0;
    if ( v9 )
    {
      v11 = a4 == 0;
      goto LABEL_13;
    }
  }
  v16 = SearchPathW(0, lpFileName, 0, 0x104u, lpBuffer, v7);
  v17 = -1;
  v10 = v16;
  v18 = v16;
  if ( !v16 )
    goto LABEL_22;
  if ( v16 >= 0x104 )
    return 0;
  if ( a4 )
  {
    v15 = gpwcSystemDir;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(gpwcSystemDir + 2 * v19) );
    v20 = -1;
    do
      ++v20;
    while ( lpBuffer[v20] );
    if ( (unsigned int)v20 <= (int)v19 + 1 )
      goto LABEL_23;
    v13 = (unsigned int)v19;
    if ( (unsigned int)_o__wcsnicmp(lpBuffer, gpwcSystemDir, (unsigned int)v19) || lpBuffer[v13] != 92 )
      goto LABEL_22;
    for ( i = &lpBuffer[v13 + 1]; i < &lpBuffer[(unsigned int)v20]; ++i )
    {
      if ( *i == 92 )
        goto LABEL_22;
    }
    if ( *i == 92 )
    {
LABEL_22:
      v15 = gpwcSystemDir;
LABEL_23:
      v10 = v18;
      if ( !a4 )
        return v10 != 0;
      if ( v18 )
        return v10 != 0;
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v15 + 2 * v21) );
      do
        ++v17;
      while ( lpFileName[v17] );
      if ( (int)v17 + 1 <= (unsigned int)v21 )
        return v10 != 0;
      v22 = (unsigned int)v21;
      if ( (unsigned int)_o__wcsnicmp(v15, lpFileName, (unsigned int)v21) || lpFileName[v22] != 92 )
        return v10 != 0;
      v23 = &lpFileName[v22 + 1];
      v24 = *v23;
      v25 = v23;
      while ( v24 && v24 != 92 )
        v24 = *++v25;
      if ( *v25 )
        return v10 != 0;
      v26 = SearchPathW(gpwcFontsDir, v23, 0, 0x104u, lpBuffer, v7);
      v10 = v26;
      if ( v26 < 0x104 )
      {
        v11 = v26 == 0;
LABEL_13:
        if ( !v11 )
          *a4 |= 1u;
        return v10 != 0;
      }
      return 0;
    }
    *a4 |= 2u;
    v10 = v18;
  }
  return v10 != 0;
}

```

## disassembly

```asm
0x1800394e0  mov     rax, rsp
0x1800394e3  push    rbx
0x1800394e4  push    rbp
0x1800394e5  push    rsi
0x1800394e6  push    rdi
0x1800394e7  push    r12
0x1800394e9  push    r13
0x1800394eb  push    r14
0x1800394ed  push    r15
0x1800394ef  sub     rsp, 38h
0x1800394f3  xor     ebp, ebp
0x1800394f5  mov     rdi, r9
0x1800394f8  mov     [rax+18h], rbp
0x1800394fc  mov     rsi, rdx
0x1800394ff  mov     r12, rcx
0x180039502  test    r9, r9
0x180039505  jnz     loc_18003968C
0x18003950b  test    r8, r8
0x18003950e  lea     r13, [rsp+78h+arg_10]
0x180039516  lea     rcx, semLocal; CriticalSection
0x18003951d  cmovnz  r13, r8
0x180039521  call    cs:__imp_RtlEnterCriticalSection
0x180039527  lea     rdx, gpwcFontsDir
0x18003952e  lea     rcx, gpwcSystemDir
0x180039535  call    bInitSystemAndFontsDirectoriesW
0x18003953a  lea     rcx, semLocal; CriticalSection
0x180039541  mov     ebx, eax
0x180039543  call    cs:__imp_RtlLeaveCriticalSection
0x180039549  test    ebx, ebx
0x18003954b  jz      short loc_1800395AA
0x18003954d  cmp     word ptr [rsi], 5Ch ; '\'
0x180039551  mov     r14d, 104h
0x180039557  jz      loc_180039621
0x18003955d  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180039562  jz      loc_18003967F
0x180039568  test    rdi, rdi
0x18003956b  jnz     loc_180039694
0x180039571  mov     rcx, cs:gpwcFontsDir; lpPath
0x180039578  mov     r9d, r14d; nBufferLength
0x18003957b  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x180039580  xor     r8d, r8d; lpExtension
0x180039583  mov     rdx, rsi; lpFileName
0x180039586  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x18003958b  call    cs:__imp_SearchPathW
0x180039591  mov     ebx, eax
0x180039593  cmp     eax, r14d
0x180039596  jnb     short loc_1800395AA
0x180039598  test    eax, eax
0x18003959a  jz      loc_180039621
0x1800395a0  test    rdi, rdi
0x1800395a3  jz      short loc_180039609
0x1800395a5  or      dword ptr [rdi], 1
0x1800395a8  jmp     short loc_180039609
0x1800395aa  xor     eax, eax
0x1800395ac  jmp     short loc_180039610
0x1800395ae  lea     eax, [rcx+1]
0x1800395b1  cmp     ebx, eax
0x1800395b3  jbe     short loc_1800395FD
0x1800395b5  mov     ebp, ecx
0x1800395b7  mov     rdx, r9
0x1800395ba  mov     r8d, ecx
0x1800395bd  mov     rcx, r12
0x1800395c0  call    cs:__imp__o__wcsnicmp
0x1800395c6  test    eax, eax
0x1800395c8  jnz     short loc_1800395F4
0x1800395ca  cmp     word ptr [r12+rbp*2], 5Ch ; '\'
0x1800395d0  jnz     short loc_1800395F4
0x1800395d2  mov     eax, ebx
0x1800395d4  lea     rcx, [r12+2]
0x1800395d9  lea     rcx, [rcx+rbp*2]
0x1800395dd  lea     rdx, [r12+rax*2]
0x1800395e1  cmp     rcx, rdx
0x1800395e4  jb      loc_18003969C
0x1800395ea  cmp     word ptr [rcx], 5Ch ; '\'
0x1800395ee  jnz     loc_1800396AF
0x1800395f4  xor     ebp, ebp
0x1800395f6  mov     r9, cs:gpwcSystemDir
0x1800395fd  mov     ebx, r14d
0x180039600  test    rdi, rdi
0x180039603  jnz     loc_1800396BC
0x180039609  test    ebx, ebx
0x18003960b  mov     eax, ebp
0x18003960d  setnz   al
0x180039610  add     rsp, 38h
0x180039614  pop     r15
0x180039616  pop     r14
0x180039618  pop     r13
0x18003961a  pop     r12
0x18003961c  pop     rdi
0x18003961d  pop     rsi
0x18003961e  pop     rbp
0x18003961f  pop     rbx
0x180039620  retn
0x180039621  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x180039626  mov     r9d, r14d; nBufferLength
0x180039629  xor     r8d, r8d; lpExtension
0x18003962c  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x180039631  mov     rdx, rsi; lpFileName
0x180039634  xor     ecx, ecx; lpPath
0x180039636  call    cs:__imp_SearchPathW
0x18003963c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180039640  mov     ebx, eax
0x180039642  mov     r14d, eax
0x180039645  test    eax, eax
0x180039647  jz      short loc_1800395F6
0x180039649  cmp     eax, 104h
0x18003964e  jnb     loc_1800395AA
0x180039654  test    rdi, rdi
0x180039657  jz      short loc_180039609
0x180039659  mov     r9, cs:gpwcSystemDir
0x180039660  mov     rcx, r15
0x180039663  inc     rcx
0x180039666  cmp     [r9+rcx*2], bp
0x18003966b  jnz     short loc_180039663
0x18003966d  mov     rbx, r15
0x180039670  inc     rbx
0x180039673  cmp     [r12+rbx*2], bp
0x180039678  jnz     short loc_180039670
0x18003967a  jmp     loc_1800395AE
0x18003967f  cmp     word ptr [rsi+4], 5Ch ; '\'
0x180039684  jnz     loc_180039568
0x18003968a  jmp     short loc_180039621
0x18003968c  mov     [r9], ebp
0x18003968f  jmp     loc_18003950B
0x180039694  or      dword ptr [rdi], 4
0x180039697  jmp     loc_180039571
0x18003969c  cmp     word ptr [rcx], 5Ch ; '\'
0x1800396a0  jz      loc_1800395F4
0x1800396a6  add     rcx, 2
0x1800396aa  jmp     loc_1800395E1
0x1800396af  or      dword ptr [rdi], 2
0x1800396b2  mov     ebx, r14d
0x1800396b5  xor     ebp, ebp
0x1800396b7  jmp     loc_180039609
0x1800396bc  test    ebx, ebx
0x1800396be  jnz     loc_180039609
0x1800396c4  mov     rcx, r15
0x1800396c7  inc     rcx
0x1800396ca  cmp     [r9+rcx*2], bp
0x1800396cf  jnz     short loc_1800396C7
0x1800396d1  inc     r15
0x1800396d4  cmp     [rsi+r15*2], bp
0x1800396d9  jnz     short loc_1800396D1
0x1800396db  lea     eax, [r15+1]
0x1800396df  cmp     eax, ecx
0x1800396e1  jbe     loc_180039609
0x1800396e7  mov     ebp, ecx
0x1800396e9  mov     rdx, rsi
0x1800396ec  mov     r8d, ecx
0x1800396ef  mov     rcx, r9
0x1800396f2  call    cs:__imp__o__wcsnicmp
0x1800396f8  test    eax, eax
0x1800396fa  jnz     short loc_1800396B5
0x1800396fc  cmp     word ptr [rsi+rbp*2], 5Ch ; '\'
0x180039701  jnz     short loc_1800396B5
0x180039703  inc     rbp
0x180039706  lea     rdx, [rsi+rbp*2]; lpFileName
0x18003970a  xor     ebp, ebp
0x18003970c  movzx   ecx, word ptr [rdx]
0x18003970f  mov     rax, rdx
0x180039712  jmp     short loc_180039721
0x180039714  cmp     cx, 5Ch ; '\'
0x180039718  jz      short loc_180039726
0x18003971a  add     rax, 2
0x18003971e  movzx   ecx, word ptr [rax]
0x180039721  test    cx, cx
0x180039724  jnz     short loc_180039714
0x180039726  cmp     [rax], bp
0x180039729  jnz     loc_180039609
0x18003972f  mov     rcx, cs:gpwcFontsDir; lpPath
0x180039736  mov     esi, 104h
0x18003973b  mov     r9d, esi; nBufferLength
0x18003973e  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x180039743  xor     r8d, r8d; lpExtension
0x180039746  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x18003974b  call    cs:__imp_SearchPathW
0x180039751  mov     ebx, eax
0x180039753  cmp     eax, esi
0x180039755  jnb     loc_1800395AA
0x18003975b  test    eax, eax
0x18003975d  jmp     loc_1800395A3
```
