# OpenTraceFile(void)

- ea: `0x1400021cc`
- end: `0x1400022e7`
- name: `?OpenTraceFile@@YAPEAU_iobuf@@XZ`
- size: `283`
- prototype: `struct _iobuf *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1400022f0`
- `0x1400023c4`

## callees

- `0x1400019cf`
- `0x140001c88`
- `0x1400021cc`
- `0x140006f10`

## import_xrefs

- `msvcrt!fopen` at `0x1400022be`
- `msvcrt!fopen` at `0x1400022be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryA` at `0x140002203`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryA` at `0x140002203`

## string_xrefs

- `0x14000226f`: `\DtcInstall.log`

## pseudocode

```c
struct _iobuf *OpenTraceFile(void)
{
  UINT SystemWindowsDirectoryA; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rax
  __int64 v4; // rdx
  CHAR *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  CHAR *v8; // rcx
  const char *v9; // rdx
  __int64 v10; // rbx
  CHAR *v11; // rax
  CHAR Buffer[288]; // [rsp+20h] [rbp-138h] BYREF

  memset_0(Buffer, 0, 0x118u);
  SystemWindowsDirectoryA = GetSystemWindowsDirectoryA(Buffer, 0x104u);
  if ( SystemWindowsDirectoryA - 1 > 0x102 )
    return 0;
  v3 = SystemWindowsDirectoryA - 1;
  if ( Buffer[v3] == 92 )
  {
    if ( (unsigned int)v3 >= 0x118uLL )
      _report_rangecheckfailure((unsigned int)v3, v1, v2, 0);
    Buffer[v3] = 0;
  }
  v4 = 280;
  v5 = Buffer;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = (280 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    return 0;
  v7 = 16;
  v8 = &Buffer[v6];
  v9 = "\\DtcInstall.log";
  v10 = 280 - v6;
  if ( 280 != v6 )
  {
    do
    {
      if ( !v7 )
        break;
      if ( !*v9 )
        break;
      *v8++ = *v9++;
      --v7;
      --v10;
    }
    while ( v10 );
  }
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  if ( !v10 )
    return 0;
  Buffer[279] = 0;
  return fopen(Buffer, "a+");
}

```

## disassembly

```asm
0x1400021cc  push    rbx
0x1400021ce  sub     rsp, 150h
0x1400021d5  mov     rax, cs:__security_cookie
0x1400021dc  xor     rax, rsp
0x1400021df  mov     [rsp+158h+var_18], rax
0x1400021e7  mov     ebx, 118h
0x1400021ec  lea     rcx, [rsp+158h+Buffer]; void *
0x1400021f1  mov     r8d, ebx; Size
0x1400021f4  xor     edx, edx; Val
0x1400021f6  call    memset_0
0x1400021fb  lea     edx, [rbx-14h]; uSize
0x1400021fe  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x140002203  call    cs:__imp_GetSystemWindowsDirectoryA
0x140002209  lea     ecx, [rax-1]
0x14000220c  cmp     ecx, 102h
0x140002212  ja      loc_1400022C6
0x140002218  dec     eax
0x14000221a  xor     r9d, r9d
0x14000221d  mov     ecx, eax
0x14000221f  cmp     [rsp+rax+158h+Buffer], 5Ch ; '\'
0x140002224  jnz     short loc_140002234
0x140002226  cmp     rcx, rbx
0x140002229  jnb     loc_1400022E1
0x14000222f  mov     [rsp+rax+158h+Buffer], r9b
0x140002234  mov     rdx, rbx
0x140002237  lea     rax, [rsp+158h+Buffer]
0x14000223c  cmp     [rax], r9b
0x14000223f  jz      short loc_14000224A
0x140002241  inc     rax
0x140002244  sub     rdx, 1
0x140002248  jnz     short loc_14000223C
0x14000224a  mov     rcx, rbx
0x14000224d  mov     rax, rdx
0x140002250  sub     rcx, rdx
0x140002253  neg     rax
0x140002256  sbb     r8, r8
0x140002259  and     r8, rcx
0x14000225c  test    rdx, rdx
0x14000225f  jz      short loc_1400022C6
0x140002261  lea     rcx, [rsp+158h+Buffer]
0x140002266  mov     eax, 10h
0x14000226b  lea     rcx, [rcx+r8]
0x14000226f  lea     rdx, aDtcinstallLog; "\\DtcInstall.log"
0x140002276  sub     rbx, r8
0x140002279  jz      short loc_14000229A
0x14000227b  test    rax, rax
0x14000227e  jz      short loc_14000229A
0x140002280  mov     r8b, [rdx]
0x140002283  test    r8b, r8b
0x140002286  jz      short loc_14000229A
0x140002288  mov     [rcx], r8b
0x14000228b  inc     rdx
0x14000228e  inc     rcx
0x140002291  dec     rax
0x140002294  sub     rbx, 1
0x140002298  jnz     short loc_14000227B
0x14000229a  test    rbx, rbx
0x14000229d  lea     rax, [rcx-1]
0x1400022a1  cmovnz  rax, rcx
0x1400022a5  mov     [rax], r9b
0x1400022a8  jz      short loc_1400022C6
0x1400022aa  lea     rdx, Mode; "a+"
0x1400022b1  mov     [rsp+158h+var_21], r9b
0x1400022b9  lea     rcx, [rsp+158h+Buffer]; FileName
0x1400022be  call    cs:__imp_fopen
0x1400022c4  jmp     short loc_1400022C8
0x1400022c6  xor     eax, eax
0x1400022c8  mov     rcx, [rsp+158h+var_18]
0x1400022d0  xor     rcx, rsp; StackCookie
0x1400022d3  call    __security_check_cookie
0x1400022d8  add     rsp, 150h
0x1400022df  pop     rbx
0x1400022e0  retn
0x1400022e1  call    __report_rangecheckfailure
```
