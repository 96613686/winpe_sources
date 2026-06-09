# GetConfigFileFromWin32Manifest(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x180040128`
- end: `0x180040376`
- name: `?GetConfigFileFromWin32Manifest@@YAJPEAG_KPEA_K@Z`
- size: `590`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009af4`

## callees

- `0x180006df4`
- `0x180007300`
- `0x180007388`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000d838`
- `0x18000d8f0`
- `0x180040128`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800401a1`
- `KERNEL32!GetLastError` at `0x1800401a1`
- `KERNEL32!QueryActCtxW` at `0x180040193`
- `KERNEL32!QueryActCtxW` at `0x18004020c`
- `KERNEL32!QueryActCtxW` at `0x180040193`
- `KERNEL32!QueryActCtxW` at `0x18004020c`

## string_xrefs

- `0x180040272`: `.config`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetConfigFileFromWin32Manifest(wchar_t *Destination, unsigned __int64 a2, unsigned __int64 *a3)
{
  wchar_t *v4; // r12
  unsigned int v5; // edi
  unsigned __int64 v6; // r15
  __int64 pvBuffer; // rsi
  wchar_t *v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rax
  rsize_t v12; // r12
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  SIZE_T pcbWrittenOrRequired; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *v18; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v19; // [rsp+50h] [rbp-B0h]
  _QWORD v20[68]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v21[68]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t Source[8]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v19 = a2;
  v4 = Destination;
  v18 = Destination;
  v5 = 0;
  pcbWrittenOrRequired = 0;
  v6 = 0;
  if ( !QueryActCtxW(0, 0, 0, 2u, 0, 0, &pcbWrittenOrRequired) && GetLastError() == 122 )
  {
    v20[0] = 0;
    v20[1] = 0;
    v20[2] = 512;
    pvBuffer = CQuickMemoryBase<512,128>::_Alloc<0,0>(v20, pcbWrittenOrRequired);
    if ( !pvBuffer )
    {
      v5 = -2147024882;
LABEL_24:
      CQuickArray<unsigned short>::~CQuickArray<unsigned short>(v20);
      goto LABEL_25;
    }
    if ( !QueryActCtxW(0, 0, 0, 2u, (PVOID)pvBuffer, pcbWrittenOrRequired, &pcbWrittenOrRequired)
      || *(_DWORD *)(pvBuffer + 28) != 2 )
    {
      goto LABEL_24;
    }
    v21[0] = 0;
    v21[1] = 0;
    v21[2] = 512;
    v8 = *(wchar_t **)(pvBuffer + 48);
    v9 = -1;
    if ( !v8 )
    {
      v10 = *(_QWORD *)(pvBuffer + 40);
      if ( !v10 )
        goto LABEL_23;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      if ( !v11 )
        goto LABEL_23;
      wcscpy(Source, L".config");
      v12 = v11 + 8;
      v13 = (wchar_t *)CQuickArrayBase<unsigned short>::AllocNoThrow(v21, v11 + 8);
      v8 = v13;
      if ( !v13 )
      {
        v5 = -2147024882;
LABEL_23:
        CQuickArray<unsigned short>::~CQuickArray<unsigned short>(v21);
        goto LABEL_24;
      }
      wcscpy_s(v13, v12, *(const wchar_t **)(pvBuffer + 40));
      v14 = wcsrchr(v8, 0x2Eu);
      v15 = v14;
      if ( v14 && wcsicmp(v14, L".exe") )
        *v15 = 0;
      wcscat_s(v8, v12, Source);
      v4 = v18;
    }
    do
      ++v9;
    while ( v8[v9] );
    v6 = v9 + 1;
    if ( v4 && v6 <= v19 )
      wcscpy_s(v4, v9 + 1, v8);
    else
      v5 = -2147024774;
    goto LABEL_23;
  }
LABEL_25:
  if ( a3 )
    *a3 = v6;
  return v5;
}

```

## disassembly

```asm
0x180040128  mov     [rsp-8+arg_8], rbx
0x18004012d  push    rbp
0x18004012e  push    rsi
0x18004012f  push    rdi
0x180040130  push    r12
0x180040132  push    r13
0x180040134  push    r14
0x180040136  push    r15
0x180040138  lea     rbp, [rsp-3C0h]
0x180040140  sub     rsp, 4C0h
0x180040147  mov     rax, cs:__security_cookie
0x18004014e  xor     rax, rsp
0x180040151  mov     [rbp+3F0h+var_40], rax
0x180040158  mov     r13, r8
0x18004015b  mov     [rsp+4F0h+var_4A0], rdx
0x180040160  mov     r12, rcx
0x180040163  mov     [rsp+4F0h+var_4A8], rcx
0x180040168  xor     ebx, ebx
0x18004016a  mov     edi, ebx
0x18004016c  mov     [rsp+4F0h+var_4B0], rbx
0x180040171  mov     r15d, ebx
0x180040174  lea     rax, [rsp+4F0h+var_4B0]
0x180040179  mov     [rsp+4F0h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x18004017e  mov     [rsp+4F0h+cbBuffer], rbx; cbBuffer
0x180040183  mov     [rsp+4F0h+pvBuffer], rbx; pvBuffer
0x180040188  lea     r9d, [rbx+2]; ulInfoClass
0x18004018c  xor     r8d, r8d; pvSubInstance
0x18004018f  xor     edx, edx; hActCtx
0x180040191  xor     ecx, ecx; dwFlags
0x180040193  call    cs:__imp_QueryActCtxW
0x180040199  test    eax, eax
0x18004019b  jnz     loc_180040341
0x1800401a1  call    cs:__imp_GetLastError
0x1800401a7  cmp     eax, 7Ah ; 'z'
0x1800401aa  jnz     loc_180040341
0x1800401b0  mov     [rsp+4F0h+var_490], rbx
0x1800401b5  mov     [rsp+4F0h+var_488], rbx
0x1800401ba  mov     r14d, 200h
0x1800401c0  mov     [rsp+4F0h+var_480], r14
0x1800401c5  mov     rdx, [rsp+4F0h+var_4B0]
0x1800401ca  lea     rcx, [rsp+4F0h+var_490]
0x1800401cf  call    ??$_Alloc@$0A@$0A@@?$CQuickMemoryBase@$0CAA@$0IA@@@IEAAPEAX_K@Z; CQuickMemoryBase<512,128>::_Alloc<0,0>(unsigned __int64)
0x1800401d4  mov     rsi, rax
0x1800401d7  test    rax, rax
0x1800401da  jnz     short loc_1800401E6
0x1800401dc  mov     edi, 8007000Eh
0x1800401e1  jmp     loc_180040337
0x1800401e6  lea     rax, [rsp+4F0h+var_4B0]
0x1800401eb  mov     [rsp+4F0h+pcbWrittenOrRequired], rax; pcbWrittenOrRequired
0x1800401f0  mov     rax, [rsp+4F0h+var_4B0]
0x1800401f5  mov     [rsp+4F0h+cbBuffer], rax; cbBuffer
0x1800401fa  mov     [rsp+4F0h+pvBuffer], rsi; pvBuffer
0x1800401ff  mov     r9d, 2; ulInfoClass
0x180040205  xor     r8d, r8d; pvSubInstance
0x180040208  xor     edx, edx; hActCtx
0x18004020a  xor     ecx, ecx; dwFlags
0x18004020c  call    cs:__imp_QueryActCtxW
0x180040212  test    eax, eax
0x180040214  jz      loc_180040337
0x18004021a  cmp     dword ptr [rsi+1Ch], 2
0x18004021e  jnz     loc_180040337
0x180040224  mov     [rbp+3F0h+var_270], rbx
0x18004022b  mov     [rbp+3F0h+var_268], rbx
0x180040232  mov     [rbp+3F0h+var_260], r14
0x180040239  mov     rbx, [rsi+30h]
0x18004023d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180040241  test    rbx, rbx
0x180040244  jz      short loc_18004024E
0x180040246  xor     r15d, r15d
0x180040249  jmp     loc_1800402FB
0x18004024e  mov     rcx, [rsi+28h]
0x180040252  xor     ebx, ebx
0x180040254  test    rcx, rcx
0x180040257  jz      loc_18004032A
0x18004025d  mov     rax, r14
0x180040260  inc     rax
0x180040263  cmp     [rcx+rax*2], bx
0x180040267  jnz     short loc_180040260
0x180040269  test    rax, rax
0x18004026c  jz      loc_18004032A
0x180040272  movups  xmm0, xmmword ptr cs:aConfig; ".config"
0x180040279  movdqu  xmmword ptr [rbp+3F0h+Source], xmm0
0x180040281  lea     r12, [rax+8]
0x180040285  mov     rdx, r12
0x180040288  lea     rcx, [rbp+3F0h+var_270]
0x18004028f  call    ?AllocNoThrow@?$CQuickArrayBase@G@@QEAAPEAG_K@Z; CQuickArrayBase<ushort>::AllocNoThrow(unsigned __int64)
0x180040294  mov     rbx, rax
0x180040297  test    rax, rax
0x18004029a  jnz     short loc_1800402A6
0x18004029c  mov     edi, 8007000Eh
0x1800402a1  jmp     loc_18004032A
0x1800402a6  mov     r8, [rsi+28h]; Source
0x1800402aa  mov     rdx, r12; SizeInWords
0x1800402ad  mov     rcx, rbx; Destination
0x1800402b0  call    wcscpy_s
0x1800402b5  mov     edx, 2Eh ; '.'; Ch
0x1800402ba  mov     rcx, rbx; Str
0x1800402bd  call    wcsrchr
0x1800402c2  mov     rsi, rax
0x1800402c5  xor     r15d, r15d
0x1800402c8  test    rax, rax
0x1800402cb  jz      short loc_1800402E4
0x1800402cd  lea     rdx, aExe; ".exe"
0x1800402d4  mov     rcx, rax; String1
0x1800402d7  call    _wcsicmp
0x1800402dc  test    eax, eax
0x1800402de  jz      short loc_1800402E4
0x1800402e0  mov     [rsi], r15w
0x1800402e4  lea     r8, [rbp+3F0h+Source]; Source
0x1800402eb  mov     rdx, r12; SizeInWords
0x1800402ee  mov     rcx, rbx; Destination
0x1800402f1  call    wcscat_s
0x1800402f6  mov     r12, [rsp+4F0h+var_4A8]
0x1800402fb  inc     r14
0x1800402fe  cmp     [rbx+r14*2], r15w
0x180040303  jnz     short loc_1800402FB
0x180040305  lea     r15, [r14+1]
0x180040309  test    r12, r12
0x18004030c  jz      short loc_180040325
0x18004030e  cmp     r15, [rsp+4F0h+var_4A0]
0x180040313  ja      short loc_180040325
0x180040315  mov     r8, rbx; Source
0x180040318  mov     rdx, r15; SizeInWords
0x18004031b  mov     rcx, r12; Destination
0x18004031e  call    wcscpy_s
0x180040323  jmp     short loc_18004032A
0x180040325  mov     edi, 8007007Ah
0x18004032a  lea     rcx, [rbp+3F0h+var_270]
0x180040331  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180040336  nop
0x180040337  lea     rcx, [rsp+4F0h+var_490]
0x18004033c  call    ??1?$CQuickArray@G@@QEAA@XZ; CQuickArray<ushort>::~CQuickArray<ushort>(void)
0x180040341  test    r13, r13
0x180040344  jz      short loc_18004034A
0x180040346  mov     [r13+0], r15
0x18004034a  mov     eax, edi
0x18004034c  mov     rcx, [rbp+3F0h+var_40]
0x180040353  xor     rcx, rsp; StackCookie
0x180040356  call    __security_check_cookie
0x18004035b  mov     rbx, [rsp+4F0h+arg_8]
0x180040363  add     rsp, 4C0h
0x18004036a  pop     r15
0x18004036c  pop     r14
0x18004036e  pop     r13
0x180040370  pop     r12
0x180040372  pop     rdi
0x180040373  pop     rsi
0x180040374  pop     rbp
0x180040375  retn
```
