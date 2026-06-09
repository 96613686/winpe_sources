# myLocalGetCertRegValueEx(ushort const *,ushort const *,ushort const *,CSRegPathType,ushort const *,uchar * *,ulong *,ulong *)

- ea: `0x180007f60`
- end: `0x1800083f3`
- name: `?myLocalGetCertRegValueEx@@YAJPEBG00W4CSRegPathType@@0PEAPEAEPEAK3@Z`
- size: `1171`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, DWORD, LPCWSTR lpValueName, BYTE **, DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180006990`

## callees

- `0x180007f60`
- `0x180008400`
- `0x180008420`
- `0x180008610`
- `0x18000a3b0`
- `0x180038262`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008027`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008346`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008027`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008346`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000818a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000818a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800083c9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008141`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008141`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800080b7`

## string_xrefs

- `0x180008050`: `SYSTEM\CurrentControlSet\Services\CertSvc\Configuration`

## pseudocode

```c
__int64 __fastcall myLocalGetCertRegValueEx(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        LPCWSTR lpValueName,
        BYTE **a6,
        DWORD *a7,
        _DWORD *a8)
{
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned __int64 v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // ebx
  unsigned __int16 *v19; // rdi
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rbx
  unsigned __int16 *v23; // rax
  __int64 v24; // rcx
  const WCHAR *v25; // rdx
  unsigned __int64 v26; // r9
  unsigned __int16 *v27; // r8
  unsigned __int16 *v28; // rcx
  LSTATUS v29; // eax
  BYTE **v30; // r14
  BYTE *v31; // rbp
  DWORD *v32; // rsi
  HKEY v33; // r12
  unsigned int v34; // r13d
  _DWORD *v35; // r15
  LSTATUS v36; // eax
  int v37; // ebx
  int v38; // eax
  __int64 v40; // rcx
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  __int64 Type; // [rsp+80h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  cbData = a4;
  hKey = 0;
  if ( !a1 )
  {
    v13 = 0;
LABEL_5:
    v14 = 0;
LABEL_6:
    v15 = 0;
    goto LABEL_7;
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( a1[v12] );
  v13 = v12 + 1;
  if ( !v13 || !a2 )
    goto LABEL_5;
  v40 = -1;
  do
    ++v40;
  while ( a2[v40] );
  v14 = v40 + 1;
  if ( !v14 || !a3 )
    goto LABEL_6;
  do
    ++v11;
  while ( a3[v11] );
  v15 = v11 + 1;
LABEL_7:
  v16 = v13 + 55;
  if ( v16 < 0x37
    || (v20 = v16 + v14, v20 < v16)
    || (v21 = v20 + v15, v20 + v15 < v20)
    || (v22 = v21 + 1, v21 + 1 < v21) )
  {
    v17 = 6095285;
LABEL_9:
    v18 = -2147024362;
LABEL_10:
    v19 = 0;
    CSPrintErrorLineFile(v17, v18);
    CSPrintErrorLineFile(0x1F201B5u, v18);
    goto LABEL_35;
  }
  Type = 0;
  if ( !is_mul_ok(v22, 2u) )
  {
    v17 = 6488501;
    goto LABEL_9;
  }
  v23 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v22);
  v19 = v23;
  if ( !v23 )
  {
    v18 = -2147024882;
    v17 = 7012789;
    goto LABEL_10;
  }
  if ( v22 )
  {
    if ( v22 > 0x7FFFFFFF )
    {
      *v23 = 0;
    }
    else
    {
      v24 = 2147483646;
      v25 = L"SYSTEM\\CurrentControlSet\\Services\\CertSvc\\Configuration";
      v26 = v22;
      v27 = v23;
      do
      {
        if ( !v24 )
          break;
        if ( !*v25 )
          break;
        *v27++ = *v25++;
        --v24;
        --v26;
      }
      while ( v26 );
      v28 = v27 - 1;
      if ( v26 )
        v28 = v27;
      *v28 = 0;
    }
  }
  if ( a1 )
  {
    if ( *v23 )
      StringCchCatW(v23, v22, L"\\");
    StringCchCatW(v19, v22, a1);
    if ( a2 )
    {
      StringCchCatW(v19, v22, L"\\");
      StringCchCatW(v19, v22, a2);
      if ( a3 )
      {
        StringCchCatW(v19, v22, L"\\");
        StringCchCatW(v19, v22, a3);
      }
    }
  }
  v29 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v19, 0, 0x20019u, &hKey);
  v18 = v29;
  if ( v29 )
  {
    CSPrintErrorLineFileData2(0, 0x1FA01B5u, v29, 2);
  }
  else
  {
    v30 = a6;
    v31 = 0;
    v32 = a7;
    v33 = hKey;
    v34 = 0;
    *a6 = 0;
    LODWORD(Type) = 0;
    cbData = 0;
    if ( v32 )
      *v32 = 0;
    v35 = a8;
    if ( a8 )
      *a8 = 0;
    while ( 1 )
    {
      v36 = RegQueryValueExW(v33, lpValueName, 0, (LPDWORD)&Type, v31, &cbData);
      v37 = v36;
      if ( v36 )
      {
        CSPrintErrorLineFileData2(lpValueName, 0x1B101B5u, v36, 2);
        goto LABEL_33;
      }
      if ( v31 )
        break;
      if ( (_DWORD)Type == 7 || (_DWORD)Type == 1 )
      {
        v34 = 4;
        if ( (cbData & 1) != 0 )
          v34 = 5;
      }
      v31 = (BYTE *)LocalAlloc(0, cbData + v34);
      if ( !v31 )
      {
        v37 = -2147024882;
        CSPrintErrorLineFile(0x1CF01B5u, -2147024882);
        goto LABEL_33;
      }
    }
    memset_0(&v31[cbData], 0, v34);
    if ( v35 )
      *v35 = Type;
    if ( v32 )
      *v32 = cbData;
    *v30 = v31;
    v37 = 0;
LABEL_33:
    v38 = myHError(v37);
    v18 = v38;
    if ( v38 )
      CSPrintErrorLineFileData2(lpValueName, 0x20701B5u, v38, -2147024894);
  }
LABEL_35:
  LocalFree(v19);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v18 == 1 )
  {
    CSPrintErrorLineFileData2(L"S_FALSE == hr", 0x65F01CAu, 1, 0);
LABEL_42:
    CSPrintErrorLineFileData2(lpValueName, 0x22C01B5u, v18, 0);
    return v18;
  }
  if ( v18 )
  {
    if ( (v18 & 0x80000000) == 0 )
    {
      v18 = (unsigned __int16)v18 | 0x80070000;
      if ( !(_WORD)v18 )
        v18 = -2147418113;
    }
    goto LABEL_42;
  }
  return v18;
}

```

## disassembly

```asm
0x180007f60  mov     rax, rsp
0x180007f63  mov     [rax+20h], r9d
0x180007f67  push    rbx
0x180007f68  sub     rsp, 70h
0x180007f6c  mov     [rax+10h], rbp
0x180007f70  mov     rbp, rdx
0x180007f73  mov     [rax-10h], rsi
0x180007f77  mov     rsi, rcx
0x180007f7a  mov     [rax-18h], rdi
0x180007f7e  mov     [rax-30h], r14
0x180007f82  mov     r14, r8
0x180007f85  mov     [rax-38h], r15
0x180007f89  xor     r15d, r15d
0x180007f8c  mov     [rax-48h], r15
0x180007f90  test    rcx, rcx
0x180007f93  jz      loc_1800081FF
0x180007f99  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180007fa0  mov     rax, rdx
0x180007fa3  inc     rax
0x180007fa6  cmp     [rcx+rax*2], r15w
0x180007fab  jnz     short loc_180007FA3
0x180007fad  add     rax, 1
0x180007fb1  jnz     loc_180008279
0x180007fb7  mov     rcx, r15
0x180007fba  mov     rdx, r15
0x180007fbd  add     rax, 37h ; '7'
0x180007fc1  cmp     rax, 37h ; '7'
0x180007fc5  jnb     short loc_180007FEC
0x180007fc7  mov     ecx, 5D01B5h; unsigned int
0x180007fcc  mov     ebx, 80070216h
0x180007fd1  mov     edx, ebx; int
0x180007fd3  mov     rdi, r15
0x180007fd6  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180007fdb  mov     edx, ebx; int
0x180007fdd  mov     ecx, 1F201B5h; unsigned int
0x180007fe2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180007fe7  jmp     loc_180008187
0x180007fec  add     rcx, rax
0x180007fef  cmp     rcx, rax
0x180007ff2  jb      short loc_180007FC7
0x180007ff4  lea     rax, [rcx+rdx]
0x180007ff8  cmp     rax, rcx
0x180007ffb  jb      short loc_180007FC7
0x180007ffd  lea     rbx, [rax+1]
0x180008001  cmp     rbx, rax
0x180008004  jb      short loc_180007FC7
0x180008006  mov     eax, 2
0x18000800b  mov     [rsp+78h+Type], r15
0x180008013  mul     rbx
0x180008016  test    rdx, rdx
0x180008019  jnz     loc_180008207
0x18000801f  mov     rdx, rax; uBytes
0x180008022  mov     ecx, 40h ; '@'; uFlags
0x180008027  call    cs:__imp_LocalAlloc
0x18000802d  mov     rdi, rax
0x180008030  test    rax, rax
0x180008033  jz      loc_1800082B5
0x180008039  test    rbx, rbx
0x18000803c  jz      short loc_180008091
0x18000803e  cmp     rbx, 7FFFFFFFh
0x180008045  ja      loc_1800082C4
0x18000804b  mov     ecx, 7FFFFFFEh
0x180008050  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ce"...
0x180008057  mov     r9, rbx
0x18000805a  mov     r8, rax
0x18000805d  nop     dword ptr [rax]
0x180008060  test    rcx, rcx
0x180008063  jz      short loc_180008082
0x180008065  movzx   eax, word ptr [rdx]
0x180008068  test    ax, ax
0x18000806b  jz      short loc_180008082
0x18000806d  mov     [r8], ax
0x180008071  add     rdx, 2
0x180008075  add     r8, 2
0x180008079  dec     rcx
0x18000807c  sub     r9, 1
0x180008080  jnz     short loc_180008060
0x180008082  test    r9, r9
0x180008085  lea     rcx, [r8-2]
0x180008089  cmovnz  rcx, r8
0x18000808d  mov     [rcx], r15w
0x180008091  test    rsi, rsi
0x180008094  jnz     loc_1800082CD
0x18000809a  lea     rax, [rsp+78h+hKey]
0x18000809f  mov     r9d, 20019h; samDesired
0x1800080a5  xor     r8d, r8d; ulOptions
0x1800080a8  mov     [rsp+78h+phkResult], rax; phkResult
0x1800080ad  mov     rdx, rdi; lpSubKey
0x1800080b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800080b7  call    cs:__imp_RegOpenKeyExW
0x1800080bd  mov     ebx, eax
0x1800080bf  test    eax, eax
0x1800080c1  jnz     loc_180008211
0x1800080c7  mov     r14, [rsp+78h+arg_28]
0x1800080cf  mov     rbp, r15
0x1800080d2  mov     rsi, [rsp+78h+arg_30]
0x1800080da  mov     [rsp+78h+var_20], r12
0x1800080df  mov     r12, [rsp+78h+hKey]
0x1800080e4  mov     [rsp+78h+var_28], r13
0x1800080e9  mov     r13d, r15d
0x1800080ec  mov     [r14], r15
0x1800080ef  mov     dword ptr [rsp+78h+Type], r15d
0x1800080f7  mov     [rsp+78h+cbData], r15d
0x1800080ff  test    rsi, rsi
0x180008102  jnz     loc_180008301
0x180008108  mov     r15, [rsp+78h+arg_38]
0x180008110  test    r15, r15
0x180008113  jnz     loc_180008309
0x180008119  mov     rdx, [rsp+78h+lpValueName]; lpValueName
0x180008121  lea     rax, [rsp+78h+cbData]
0x180008129  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000812e  lea     r9, [rsp+78h+Type]; lpType
0x180008136  xor     r8d, r8d; lpReserved
0x180008139  mov     [rsp+78h+phkResult], rbp; lpData
0x18000813e  mov     rcx, r12; hKey
0x180008141  call    cs:__imp_RegQueryValueExW
0x180008147  mov     ebx, eax
0x180008149  test    eax, eax
0x18000814b  jz      loc_180008311
0x180008151  mov     rcx, [rsp+78h+lpValueName]; unsigned __int16 *
0x180008159  mov     r9d, 2; int
0x18000815f  mov     r8d, eax; int
0x180008162  mov     edx, 1B101B5h; unsigned int
0x180008167  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000816c  mov     ecx, ebx; int
0x18000816e  call    ?myHError@@YAJJ@Z; myHError(long)
0x180008173  mov     r13, [rsp+78h+var_28]
0x180008178  mov     ebx, eax
0x18000817a  mov     r12, [rsp+78h+var_20]
0x18000817f  test    eax, eax
0x180008181  jnz     loc_1800083A9
0x180008187  mov     rcx, rdi; hMem
0x18000818a  call    cs:__imp_LocalFree
0x180008190  mov     rcx, [rsp+78h+hKey]; hKey
0x180008195  mov     r15, [rsp+78h+var_38]
0x18000819a  mov     r14, [rsp+78h+var_30]
0x18000819f  mov     rdi, [rsp+78h+var_18]
0x1800081a4  mov     rsi, [rsp+78h+var_10]
0x1800081a9  mov     rbp, [rsp+78h+arg_8]
0x1800081b1  test    rcx, rcx
0x1800081b4  jnz     loc_1800083C9
0x1800081ba  cmp     ebx, 1
0x1800081bd  jz      loc_1800083D4
0x1800081c3  test    ebx, ebx
0x1800081c5  jz      short loc_1800081F7
0x1800081c7  js      short loc_1800081DF
0x1800081c9  jle     short loc_1800081D4
0x1800081cb  movzx   ebx, bx
0x1800081ce  or      ebx, 80070000h
0x1800081d4  test    bx, bx
0x1800081d7  mov     ecx, 8000FFFFh
0x1800081dc  cmovz   ebx, ecx
0x1800081df  mov     rcx, [rsp+78h+lpValueName]; unsigned __int16 *
0x1800081e7  xor     r9d, r9d; int
0x1800081ea  mov     r8d, ebx; int
0x1800081ed  mov     edx, 22C01B5h; unsigned int
0x1800081f2  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800081f7  mov     eax, ebx
0x1800081f9  add     rsp, 70h
0x1800081fd  pop     rbx
0x1800081fe  retn
0x1800081ff  mov     rax, r15
0x180008202  jmp     loc_180007FB7
0x180008207  mov     ecx, 6301B5h
0x18000820c  jmp     loc_180007FCC
0x180008211  mov     r9d, 2; int
0x180008217  mov     r8d, eax; int
0x18000821a  mov     edx, 1FA01B5h; unsigned int
0x18000821f  xor     ecx, ecx; unsigned __int16 *
0x180008221  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180008226  jmp     loc_180008187
0x18000822b  lea     r8, asc_180061BD4; "\\"
0x180008232  mov     rdx, rbx; unsigned __int64
0x180008235  mov     rcx, rdi; unsigned __int16 *
0x180008238  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000823d  mov     r8, rbp; unsigned __int16 *
0x180008240  mov     rdx, rbx; unsigned __int64
0x180008243  mov     rcx, rdi; unsigned __int16 *
0x180008246  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000824b  test    r14, r14
0x18000824e  jz      loc_18000809A
0x180008254  lea     r8, asc_180061BD4; "\\"
0x18000825b  mov     rdx, rbx; unsigned __int64
0x18000825e  mov     rcx, rdi; unsigned __int16 *
0x180008261  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008266  mov     r8, r14; unsigned __int16 *
0x180008269  mov     rdx, rbx; unsigned __int64
0x18000826c  mov     rcx, rdi; unsigned __int16 *
0x18000826f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008274  jmp     loc_18000809A
0x180008279  test    rbp, rbp
0x18000827c  jz      loc_180007FB7
0x180008282  mov     rcx, rdx
0x180008285  inc     rcx
0x180008288  cmp     [rbp+rcx*2+0], r15w
0x18000828e  jnz     short loc_180008285
0x180008290  add     rcx, 1
0x180008294  jz      loc_180007FBA
0x18000829a  test    r14, r14
0x18000829d  jz      loc_180007FBA
0x1800082a3  inc     rdx
0x1800082a6  cmp     [r8+rdx*2], r15w
0x1800082ab  jnz     short loc_1800082A3
0x1800082ad  inc     rdx
0x1800082b0  jmp     loc_180007FBD
0x1800082b5  mov     ebx, 8007000Eh
0x1800082ba  mov     ecx, 6B01B5h
0x1800082bf  jmp     loc_180007FD1
0x1800082c4  mov     [rax], r15w
0x1800082c8  jmp     loc_180008091
0x1800082cd  cmp     r15w, [rdi]
0x1800082d1  jz      short loc_1800082E5
0x1800082d3  lea     r8, asc_180061BD4; "\\"
0x1800082da  mov     rdx, rbx; unsigned __int64
0x1800082dd  mov     rcx, rdi; unsigned __int16 *
0x1800082e0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082e5  mov     r8, rsi; unsigned __int16 *
0x1800082e8  mov     rdx, rbx; unsigned __int64
0x1800082eb  mov     rcx, rdi; unsigned __int16 *
0x1800082ee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800082f3  test    rbp, rbp
0x1800082f6  jz      loc_18000809A
0x1800082fc  jmp     loc_18000822B
0x180008301  mov     [rsi], r15d
0x180008304  jmp     loc_180008108
0x180008309  mov     [r15], ebp
0x18000830c  jmp     loc_180008119
0x180008311  test    rbp, rbp
0x180008314  jnz     short loc_18000836E
0x180008316  mov     eax, dword ptr [rsp+78h+Type]
0x18000831d  mov     ecx, [rsp+78h+cbData]
0x180008324  cmp     eax, 7
0x180008327  jz      short loc_18000832E
0x180008329  cmp     eax, 1
0x18000832c  jnz     short loc_180008340
0x18000832e  test    cl, 1
0x180008331  mov     r13d, 4
0x180008337  mov     eax, 5
0x18000833c  cmovnz  r13d, eax
0x180008340  lea     edx, [rcx+r13]; uBytes
0x180008344  xor     ecx, ecx; uFlags
0x180008346  call    cs:__imp_LocalAlloc
0x18000834c  mov     rbp, rax
0x18000834f  test    rax, rax
0x180008352  jnz     loc_180008119
0x180008358  mov     ebx, 8007000Eh
0x18000835d  mov     ecx, 1CF01B5h; unsigned int
0x180008362  mov     edx, ebx; int
0x180008364  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180008369  jmp     loc_18000816C
0x18000836e  mov     ecx, [rsp+78h+cbData]
0x180008375  xor     edx, edx; Val
0x180008377  add     rcx, rbp; void *
0x18000837a  mov     r8d, r13d; Size
0x18000837d  call    memset_0
0x180008382  test    r15, r15
0x180008385  jz      short loc_180008391
0x180008387  mov     eax, dword ptr [rsp+78h+Type]
0x18000838e  mov     [r15], eax
0x180008391  test    rsi, rsi
0x180008394  jz      short loc_18000839F
0x180008396  mov     eax, [rsp+78h+cbData]
0x18000839d  mov     [rsi], eax
0x18000839f  mov     [r14], rbp
0x1800083a2  xor     ebx, ebx
0x1800083a4  jmp     loc_18000816C
0x1800083a9  mov     rcx, [rsp+78h+lpValueName]; unsigned __int16 *
0x1800083b1  mov     r9d, 80070002h; int
0x1800083b7  mov     r8d, eax; int
0x1800083ba  mov     edx, 20701B5h; unsigned int
0x1800083bf  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800083c4  jmp     loc_180008187
0x1800083c9  call    cs:__imp_RegCloseKey
0x1800083cf  jmp     loc_1800081BA
0x1800083d4  xor     r9d, r9d; int
0x1800083d7  lea     rcx, aSFalseHr; "S_FALSE == hr"
0x1800083de  mov     edx, 65F01CAh; unsigned int
0x1800083e3  mov     r8d, 1; int
0x1800083e9  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800083ee  jmp     loc_1800081DF
```
