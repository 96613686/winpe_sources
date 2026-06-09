# bMakePathNameW

- ea: `0x180044f30`
- end: `0x1800451dd`
- name: `bMakePathNameW`
- size: `685`
- prototype: `__int64 __fastcall(LPWSTR lpBuffer, LPCWSTR lpFileName, LPWSTR *lpFilePart)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180044700`
- `0x180044b8c`
- `0x1800451f0`
- `0x180082770`
- `0x180083060`
- `0x180083320`

## callees

- `0x180044f30`
- `0x1800457e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045022`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045161`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045022`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180045161`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180044fe7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18004509f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800451c0`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180044fe7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18004509f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800451c0`
- `ntdll!RtlEnterCriticalSection` at `0x180044f71`
- `ntdll!RtlEnterCriticalSection` at `0x180044f71`
- `ntdll!RtlLeaveCriticalSection` at `0x180044f99`
- `ntdll!RtlLeaveCriticalSection` at `0x180044f99`

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
0x180044f30  mov     rax, rsp
0x180044f33  push    rbx
0x180044f34  push    rbp
0x180044f35  push    rsi
0x180044f36  push    rdi
0x180044f37  push    r12
0x180044f39  push    r13
0x180044f3b  push    r14
0x180044f3d  push    r15
0x180044f3f  sub     rsp, 38h
0x180044f43  xor     ebp, ebp
0x180044f45  mov     rdi, r9
0x180044f48  mov     [rax+18h], rbp
0x180044f4c  mov     rsi, rdx
0x180044f4f  mov     r12, rcx
0x180044f52  test    r9, r9
0x180044f55  jnz     loc_1800450FB
0x180044f5b  test    r8, r8
0x180044f5e  lea     r13, [rsp+78h+arg_10]
0x180044f66  lea     rcx, semLocal; CriticalSection
0x180044f6d  cmovnz  r13, r8
0x180044f71  call    cs:__imp_RtlEnterCriticalSection
0x180044f78  nop     dword ptr [rax+rax+00h]
0x180044f7d  lea     rdx, gpwcFontsDir
0x180044f84  lea     rcx, gpwcSystemDir
0x180044f8b  call    bInitSystemAndFontsDirectoriesW
0x180044f90  lea     rcx, semLocal; CriticalSection
0x180044f97  mov     ebx, eax
0x180044f99  call    cs:__imp_RtlLeaveCriticalSection
0x180044fa0  nop     dword ptr [rax+rax+00h]
0x180044fa5  test    ebx, ebx
0x180044fa7  jz      short loc_18004500C
0x180044fa9  cmp     word ptr [rsi], 5Ch ; '\'
0x180044fad  mov     r14d, 104h
0x180044fb3  jz      loc_18004508A
0x180044fb9  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180044fbe  jz      loc_1800450EE
0x180044fc4  test    rdi, rdi
0x180044fc7  jnz     loc_180045103
0x180044fcd  mov     rcx, cs:gpwcFontsDir; lpPath
0x180044fd4  mov     r9d, r14d; nBufferLength
0x180044fd7  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x180044fdc  xor     r8d, r8d; lpExtension
0x180044fdf  mov     rdx, rsi; lpFileName
0x180044fe2  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x180044fe7  call    cs:__imp_SearchPathW
0x180044fee  nop     dword ptr [rax+rax+00h]
0x180044ff3  mov     ebx, eax
0x180044ff5  cmp     eax, r14d
0x180044ff8  jnb     short loc_18004500C
0x180044ffa  test    eax, eax
0x180044ffc  jz      loc_18004508A
0x180045002  test    rdi, rdi
0x180045005  jz      short loc_180045071
0x180045007  or      dword ptr [rdi], 1
0x18004500a  jmp     short loc_180045071
0x18004500c  xor     eax, eax
0x18004500e  jmp     short loc_180045078
0x180045010  lea     eax, [rcx+1]
0x180045013  cmp     ebx, eax
0x180045015  jbe     short loc_180045065
0x180045017  mov     ebp, ecx
0x180045019  mov     rdx, r9
0x18004501c  mov     r8d, ecx
0x18004501f  mov     rcx, r12
0x180045022  call    cs:__imp__o__wcsnicmp
0x180045029  nop     dword ptr [rax+rax+00h]
0x18004502e  test    eax, eax
0x180045030  jnz     short loc_18004505C
0x180045032  cmp     word ptr [r12+rbp*2], 5Ch ; '\'
0x180045038  jnz     short loc_18004505C
0x18004503a  mov     eax, ebx
0x18004503c  lea     rcx, [r12+2]
0x180045041  lea     rcx, [rcx+rbp*2]
0x180045045  lea     rdx, [r12+rax*2]
0x180045049  cmp     rcx, rdx
0x18004504c  jb      loc_18004510B
0x180045052  cmp     word ptr [rcx], 5Ch ; '\'
0x180045056  jnz     loc_18004511E
0x18004505c  xor     ebp, ebp
0x18004505e  mov     r9, cs:gpwcSystemDir
0x180045065  mov     ebx, r14d
0x180045068  test    rdi, rdi
0x18004506b  jnz     loc_18004512B
0x180045071  test    ebx, ebx
0x180045073  mov     eax, ebp
0x180045075  setnz   al
0x180045078  add     rsp, 38h
0x18004507c  pop     r15
0x18004507e  pop     r14
0x180045080  pop     r13
0x180045082  pop     r12
0x180045084  pop     rdi
0x180045085  pop     rsi
0x180045086  pop     rbp
0x180045087  pop     rbx
0x180045088  retn
0x18004508a  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x18004508f  mov     r9d, r14d; nBufferLength
0x180045092  xor     r8d, r8d; lpExtension
0x180045095  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x18004509a  mov     rdx, rsi; lpFileName
0x18004509d  xor     ecx, ecx; lpPath
0x18004509f  call    cs:__imp_SearchPathW
0x1800450a6  nop     dword ptr [rax+rax+00h]
0x1800450ab  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800450af  mov     ebx, eax
0x1800450b1  mov     r14d, eax
0x1800450b4  test    eax, eax
0x1800450b6  jz      short loc_18004505E
0x1800450b8  cmp     eax, 104h
0x1800450bd  jnb     loc_18004500C
0x1800450c3  test    rdi, rdi
0x1800450c6  jz      short loc_180045071
0x1800450c8  mov     r9, cs:gpwcSystemDir
0x1800450cf  mov     rcx, r15
0x1800450d2  inc     rcx
0x1800450d5  cmp     [r9+rcx*2], bp
0x1800450da  jnz     short loc_1800450D2
0x1800450dc  mov     rbx, r15
0x1800450df  inc     rbx
0x1800450e2  cmp     [r12+rbx*2], bp
0x1800450e7  jnz     short loc_1800450DF
0x1800450e9  jmp     loc_180045010
0x1800450ee  cmp     word ptr [rsi+4], 5Ch ; '\'
0x1800450f3  jnz     loc_180044FC4
0x1800450f9  jmp     short loc_18004508A
0x1800450fb  mov     [r9], ebp
0x1800450fe  jmp     loc_180044F5B
0x180045103  or      dword ptr [rdi], 4
0x180045106  jmp     loc_180044FCD
0x18004510b  cmp     word ptr [rcx], 5Ch ; '\'
0x18004510f  jz      loc_18004505C
0x180045115  add     rcx, 2
0x180045119  jmp     loc_180045049
0x18004511e  or      dword ptr [rdi], 2
0x180045121  mov     ebx, r14d
0x180045124  xor     ebp, ebp
0x180045126  jmp     loc_180045071
0x18004512b  test    ebx, ebx
0x18004512d  jnz     loc_180045071
0x180045133  mov     rcx, r15
0x180045136  inc     rcx
0x180045139  cmp     [r9+rcx*2], bp
0x18004513e  jnz     short loc_180045136
0x180045140  inc     r15
0x180045143  cmp     [rsi+r15*2], bp
0x180045148  jnz     short loc_180045140
0x18004514a  lea     eax, [r15+1]
0x18004514e  cmp     eax, ecx
0x180045150  jbe     loc_180045071
0x180045156  mov     ebp, ecx
0x180045158  mov     rdx, rsi
0x18004515b  mov     r8d, ecx
0x18004515e  mov     rcx, r9
0x180045161  call    cs:__imp__o__wcsnicmp
0x180045168  nop     dword ptr [rax+rax+00h]
0x18004516d  test    eax, eax
0x18004516f  jnz     short loc_180045124
0x180045171  cmp     word ptr [rsi+rbp*2], 5Ch ; '\'
0x180045176  jnz     short loc_180045124
0x180045178  inc     rbp
0x18004517b  lea     rdx, [rsi+rbp*2]; lpFileName
0x18004517f  xor     ebp, ebp
0x180045181  movzx   ecx, word ptr [rdx]
0x180045184  mov     rax, rdx
0x180045187  jmp     short loc_180045196
0x180045189  cmp     cx, 5Ch ; '\'
0x18004518d  jz      short loc_18004519B
0x18004518f  add     rax, 2
0x180045193  movzx   ecx, word ptr [rax]
0x180045196  test    cx, cx
0x180045199  jnz     short loc_180045189
0x18004519b  cmp     [rax], bp
0x18004519e  jnz     loc_180045071
0x1800451a4  mov     rcx, cs:gpwcFontsDir; lpPath
0x1800451ab  mov     esi, 104h
0x1800451b0  mov     r9d, esi; nBufferLength
0x1800451b3  mov     [rsp+78h+lpFilePart], r13; lpFilePart
0x1800451b8  xor     r8d, r8d; lpExtension
0x1800451bb  mov     [rsp+78h+lpBuffer], r12; lpBuffer
0x1800451c0  call    cs:__imp_SearchPathW
0x1800451c7  nop     dword ptr [rax+rax+00h]
0x1800451cc  mov     ebx, eax
0x1800451ce  cmp     eax, esi
0x1800451d0  jnb     loc_18004500C
0x1800451d6  test    eax, eax
0x1800451d8  jmp     loc_180045005
```
