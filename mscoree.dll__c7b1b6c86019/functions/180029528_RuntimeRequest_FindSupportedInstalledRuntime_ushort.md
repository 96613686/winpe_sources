# RuntimeRequest::FindSupportedInstalledRuntime(ushort * *)

- ea: `0x180029528`
- end: `0x18002976c`
- name: `?FindSupportedInstalledRuntime@RuntimeRequest@@QEAAHPEAPEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(RuntimeRequest *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180009af4`

## callees

- `0x180001ff0`
- `0x180003740`
- `0x180003840`
- `0x180003ed0`
- `0x1800088c0`
- `0x18000c1a8`
- `0x18000d164`
- `0x180029528`
- `0x18002bfc0`
- `0x180031008`
- `0x18003145c`

## pseudocode

```c
__int64 __fastcall RuntimeRequest::FindSupportedInstalledRuntime(RuntimeRequest *this, unsigned __int16 **a2)
{
  unsigned int v2; // eax
  __int64 v4; // r12
  WCHAR *ConfigString; // rbx
  unsigned int v6; // r15d
  wchar_t *v8; // rdi
  int StandardVersion; // eax
  void *v10; // r14
  int LatestVersionWithCallback; // eax
  __int64 v12; // rax
  unsigned __int64 v13; // rsi
  unsigned __int128 v14; // rax
  unsigned __int16 *v15; // rax
  int v17; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-1Ch]
  WCHAR *v19; // [rsp+48h] [rbp-18h] BYREF
  void *v20; // [rsp+50h] [rbp-10h] BYREF
  __int16 v21; // [rsp+A0h] [rbp+40h] BYREF
  int v22; // [rsp+B0h] [rbp+50h] BYREF
  unsigned int v23; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *((_DWORD *)this + 26);
  v4 = *((_QWORD *)this + 12);
  v20 = 0;
  ConfigString = 0;
  v19 = 0;
  v6 = 0;
  v18 = v2;
  while ( 1 )
  {
    if ( v6 >= v2 )
      return 0;
    v8 = (wchar_t *)L"v1.0.3705";
    if ( !(unsigned int)ShouldConvertVersionToV1(*(wchar_t **)(v4 + 8LL * v6)) )
      v8 = *(wchar_t **)(v4 + 8LL * v6);
    StandardVersion = FindStandardVersion(*(_QWORD *)(v4 + 8LL * v6), *((unsigned int *)this + 27), &v20);
    v10 = v20;
    if ( StandardVersion >= 0 && v20 )
      v8 = (wchar_t *)v20;
    if ( !(unsigned int)IsRuntimeVersionInstalled(v8, *((_DWORD *)this + 27), *((_DWORD *)this + 18)) )
      goto LABEL_27;
    if ( *((_DWORD *)this + 18) )
    {
      v21 = 0;
      v23 = 0;
      v17 = 0;
      v22 = 0;
      if ( swscanf(v8, L"%c%u.%u%n", &v21, &v23, &v17, &v22) == 3 && !v8[v22] && v23 >= 4 && ((v21 - 86) & 0xFFDF) == 0 )
        break;
    }
LABEL_21:
    if ( v10 )
    {
      operator delete(v10);
      v20 = 0;
    }
    if ( ConfigString )
    {
      operator delete(ConfigString);
      ConfigString = 0;
      v19 = 0;
    }
    v2 = v18;
    ++v6;
  }
  ConfigString = GetConfigString(L"Version", 0, *((_DWORD *)this + 27));
  if ( ConfigString )
  {
    if ( (unsigned int)TwoPartVersionCallback(ConfigString, v8) )
      goto LABEL_19;
    operator delete(ConfigString);
  }
  LatestVersionWithCallback = FindLatestVersionWithCallback(
                                &v19,
                                *((_DWORD *)this + 27),
                                0,
                                (unsigned int (__fastcall *)(void *, __int64))TwoPartVersionCallback,
                                (__int64)v8,
                                0,
                                0);
  ConfigString = v19;
  if ( LatestVersionWithCallback )
    ConfigString = 0;
LABEL_19:
  v19 = ConfigString;
  if ( !ConfigString || (unsigned int)IsRuntimeVersionInstalled(ConfigString, *((_DWORD *)this + 27), 1) )
    goto LABEL_21;
  v8 = ConfigString;
LABEL_27:
  if ( a2 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v8[v12] );
    v13 = v12 + 1;
    if ( v12 == -1 )
      return 0;
    v14 = v13 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v13, 2u) )
      *(_QWORD *)&v14 = -1;
    v15 = (unsigned __int16 *)operator new(v14, *((const struct NoThrow **)&v14 + 1));
    *a2 = v15;
    if ( !v15 )
      return 0;
    wcscpy_s(v15, v13, v8);
  }
  if ( v10 )
    operator delete(v10);
  if ( ConfigString )
    operator delete(ConfigString);
  return 1;
}

```

## disassembly

```asm
0x180029528  mov     [rsp-38h+arg_8], rbx
0x18002952d  push    rbp
0x18002952e  push    rsi
0x18002952f  push    rdi
0x180029530  push    r12
0x180029532  push    r13
0x180029534  push    r14
0x180029536  push    r15
0x180029538  mov     rbp, rsp
0x18002953b  sub     rsp, 60h
0x18002953f  mov     eax, [rcx+68h]
0x180029542  mov     r13, rdx
0x180029545  mov     r12, [rcx+60h]
0x180029549  xor     edx, edx
0x18002954b  mov     [rbp+var_10], rdx
0x18002954f  mov     ebx, edx
0x180029551  mov     [rbp+var_18], rdx
0x180029555  mov     r15d, edx
0x180029558  mov     rsi, rcx
0x18002955b  mov     [rbp+var_1C], eax
0x18002955e  cmp     r15d, eax
0x180029561  jnb     loc_180029752
0x180029567  mov     r14d, r15d
0x18002956a  mov     rcx, [r12+r14*8]; String1
0x18002956e  call    ShouldConvertVersionToV1
0x180029573  lea     rdi, aV103705; "v1.0.3705"
0x18002957a  test    eax, eax
0x18002957c  jnz     short loc_180029582
0x18002957e  mov     rdi, [r12+r14*8]
0x180029582  mov     edx, [rsi+6Ch]
0x180029585  lea     r8, [rbp+var_10]
0x180029589  mov     rcx, [r12+r14*8]
0x18002958d  call    ?FindStandardVersion@@YAJPEBGW4VERSION_ARCHITECTURE@@PEAPEAG@Z; FindStandardVersion(ushort const *,VERSION_ARCHITECTURE,ushort * *)
0x180029592  mov     r14, [rbp+var_10]
0x180029596  test    eax, eax
0x180029598  js      short loc_1800295A1
0x18002959a  test    r14, r14
0x18002959d  cmovnz  rdi, r14
0x1800295a1  mov     r8d, [rsi+48h]
0x1800295a5  mov     rcx, rdi
0x1800295a8  mov     edx, [rsi+6Ch]
0x1800295ab  call    ?IsRuntimeVersionInstalled@@YAJPEBGW4VERSION_ARCHITECTURE@@H@Z; IsRuntimeVersionInstalled(ushort const *,VERSION_ARCHITECTURE,int)
0x1800295b0  xor     edx, edx
0x1800295b2  test    eax, eax
0x1800295b4  jz      loc_1800296E8
0x1800295ba  cmp     [rsi+48h], edx
0x1800295bd  jz      loc_1800296B4
0x1800295c3  lea     rax, [rbp+arg_10]
0x1800295c7  mov     [rbp+arg_0], dx
0x1800295cb  mov     [rsp+60h+var_38], rax
0x1800295d0  lea     r9, [rbp+arg_18]
0x1800295d4  lea     rax, [rbp+var_20]
0x1800295d8  mov     [rbp+arg_18], edx
0x1800295db  mov     [rbp+var_20], edx
0x1800295de  lea     r8, [rbp+arg_0]
0x1800295e2  mov     [rbp+arg_10], edx
0x1800295e5  mov     rcx, rdi; Buffer
0x1800295e8  lea     rdx, aCUUN; "%c%u.%u%n"
0x1800295ef  mov     [rsp+60h+var_40], rax
0x1800295f4  call    swscanf
0x1800295f9  cmp     eax, 3
0x1800295fc  jnz     loc_1800296B4
0x180029602  mov     eax, [rbp+arg_10]
0x180029605  xor     edx, edx
0x180029607  cmp     [rdi+rax*2], dx
0x18002960b  jnz     loc_1800296B4
0x180029611  cmp     [rbp+arg_18], 4
0x180029615  jb      loc_1800296B4
0x18002961b  movzx   eax, [rbp+arg_0]
0x18002961f  mov     ecx, 0FFDFh
0x180029624  sub     ax, 56h ; 'V'
0x180029628  test    cx, ax
0x18002962b  jnz     loc_1800296B4
0x180029631  mov     r8d, [rsi+6Ch]
0x180029635  lea     rcx, aVersion_1; "Version"
0x18002963c  call    ?GetConfigString@@YAPEAGPEBGHW4VERSION_ARCHITECTURE@@@Z; GetConfigString(ushort const *,int,VERSION_ARCHITECTURE)
0x180029641  mov     rbx, rax
0x180029644  xor     eax, eax
0x180029646  test    rbx, rbx
0x180029649  jz      short loc_180029664
0x18002964b  mov     rdx, rdi; String1
0x18002964e  mov     rcx, rbx; String2
0x180029651  call    TwoPartVersionCallback
0x180029656  test    eax, eax
0x180029658  jnz     short loc_180029694
0x18002965a  mov     rcx, rbx; void *
0x18002965d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029662  xor     eax, eax
0x180029664  mov     edx, [rsi+6Ch]
0x180029667  lea     r9, TwoPartVersionCallback
0x18002966e  mov     [rsp+60h+var_30], rax
0x180029673  lea     rcx, [rbp+var_18]
0x180029677  mov     dword ptr [rsp+60h+var_38], eax
0x18002967b  xor     r8d, r8d
0x18002967e  mov     [rsp+60h+var_40], rdi
0x180029683  call    ?FindLatestVersionWithCallback@@YAJPEAPEAGW4VERSION_ARCHITECTURE@@HP6AHPEAGPEAX@Z3HPEAVShimLog@@@Z; FindLatestVersionWithCallback(ushort * *,VERSION_ARCHITECTURE,int,int (*)(ushort *,void *),void *,int,ShimLog *)
0x180029688  mov     rbx, [rbp+var_18]
0x18002968c  xor     edx, edx
0x18002968e  test    eax, eax
0x180029690  cmovnz  rbx, rdx
0x180029694  mov     [rbp+var_18], rbx
0x180029698  test    rbx, rbx
0x18002969b  jz      short loc_1800296B4
0x18002969d  mov     edx, [rsi+6Ch]
0x1800296a0  mov     r8d, 1
0x1800296a6  mov     rcx, rbx
0x1800296a9  call    ?IsRuntimeVersionInstalled@@YAJPEBGW4VERSION_ARCHITECTURE@@H@Z; IsRuntimeVersionInstalled(ushort const *,VERSION_ARCHITECTURE,int)
0x1800296ae  xor     edx, edx; struct NoThrow *
0x1800296b0  test    eax, eax
0x1800296b2  jz      short loc_1800296E5
0x1800296b4  test    r14, r14
0x1800296b7  jz      short loc_1800296C7
0x1800296b9  mov     rcx, r14; void *
0x1800296bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800296c1  xor     edx, edx
0x1800296c3  mov     [rbp+var_10], rdx
0x1800296c7  test    rbx, rbx
0x1800296ca  jz      short loc_1800296DA
0x1800296cc  mov     rcx, rbx; void *
0x1800296cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800296d4  xor     ebx, ebx
0x1800296d6  mov     [rbp+var_18], rbx
0x1800296da  mov     eax, [rbp+var_1C]
0x1800296dd  inc     r15d
0x1800296e0  jmp     loc_18002955E
0x1800296e5  mov     rdi, rbx
0x1800296e8  test    r13, r13
0x1800296eb  jz      short loc_180029731
0x1800296ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800296f1  mov     rax, rcx
0x1800296f4  inc     rax
0x1800296f7  cmp     [rdi+rax*2], dx
0x1800296fb  jnz     short loc_1800296F4
0x1800296fd  lea     rsi, [rax+1]
0x180029701  test    rsi, rsi
0x180029704  jz      short loc_180029752
0x180029706  mov     eax, 2
0x18002970b  mul     rsi
0x18002970e  cmovb   rax, rcx
0x180029712  mov     rcx, rax; unsigned __int64
0x180029715  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18002971a  mov     [r13+0], rax
0x18002971e  test    rax, rax
0x180029721  jz      short loc_180029752
0x180029723  mov     r8, rdi; Source
0x180029726  mov     rdx, rsi; SizeInWords
0x180029729  mov     rcx, rax; Destination
0x18002972c  call    wcscpy_s
0x180029731  test    r14, r14
0x180029734  jz      short loc_18002973E
0x180029736  mov     rcx, r14; void *
0x180029739  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002973e  test    rbx, rbx
0x180029741  jz      short loc_18002974B
0x180029743  mov     rcx, rbx; void *
0x180029746  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002974b  mov     eax, 1
0x180029750  jmp     short loc_180029754
0x180029752  xor     eax, eax
0x180029754  mov     rbx, [rsp+60h+arg_8]
0x18002975c  add     rsp, 60h
0x180029760  pop     r15
0x180029762  pop     r14
0x180029764  pop     r13
0x180029766  pop     r12
0x180029768  pop     rdi
0x180029769  pop     rsi
0x18002976a  pop     rbp
0x18002976b  retn
```
