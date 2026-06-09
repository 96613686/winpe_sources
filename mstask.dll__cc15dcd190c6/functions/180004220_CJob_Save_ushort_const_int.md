# CJob::Save(ushort const *,int)

- ea: `0x180004220`
- end: `0x18000457c`
- name: `?Save@CJob@@UEAAJPEBGH@Z`
- size: `860`
- prototype: `int(CJob *__hidden this, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180004220`
- `0x180004590`
- `0x1800051d4`
- `0x180009f38`
- `0x18000b920`
- `0x18000ca2c`
- `0x18001aa9a`
- `0x18001aac0`
- `0x18001b010`

## import_xrefs

- `msvcrt!rand` at `0x180004429`
- `msvcrt!rand` at `0x180004429`
- `msvcrt!wcsrchr` at `0x180004335`
- `msvcrt!wcsrchr` at `0x180004335`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001abde`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001abde`
- `RPCRT4!NdrClientCall3` at `0x180004380`
- `RPCRT4!NdrClientCall3` at `0x180004380`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800042e8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800042e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800044ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044ef`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800044ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042fa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004450`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180004450`

## string_xrefs

- `0x1800042e1`: `MPR.DLL`

## pseudocode

```c
__int64 __fastcall CJob::Save(struct _JOB_ACCOUNT_INFO **this, const unsigned __int16 *a2, int a3)
{
  signed int Pointer; // ebx
  int i; // r14d
  _DWORD *v8; // r14
  unsigned int v9; // ebx
  unsigned __int16 *v10; // r12
  HMODULE Library; // rax
  HMODULE v12; // r13
  signed int LastError; // eax
  unsigned int v14; // r8d
  bool v15; // sf
  wchar_t *v16; // rax
  const unsigned __int16 *v17; // r10
  CLIENT_CALL_RETURN v18; // rax
  int v20; // eax
  __int64 v21; // rax
  const unsigned __int16 *v22; // r8
  __int64 v23; // rdx
  unsigned __int16 *v24; // rcx
  unsigned __int16 v25; // r9
  unsigned __int16 *v26; // rax
  FARPROC ProcAddress; // rax
  _WORD *j; // rdx
  unsigned __int16 *Simple; // [rsp+40h] [rbp-488h] BYREF
  char *v30; // [rsp+48h] [rbp-480h] BYREF
  int v31; // [rsp+50h] [rbp-478h]
  CJob *v32; // [rsp+58h] [rbp-470h]
  _BYTE v33[4]; // [rsp+60h] [rbp-468h] BYREF
  _BYTE v34[524]; // [rsp+64h] [rbp-464h] BYREF
  unsigned __int16 v35[264]; // [rsp+270h] [rbp-258h] BYREF

  v32 = (CJob *)this;
  Pointer = 0;
  for ( i = 0; i < 3; ++i )
  {
    Pointer = CJob::SaveP((CJob *)(this - 1), a2, a3, 1u);
    if ( Pointer >= 0 )
    {
      Pointer = 0;
      goto LABEL_5;
    }
    v20 = rand();
    Sleep(v20 % 250 + 250);
  }
  if ( Pointer < 0 )
    return (unsigned int)Pointer;
LABEL_5:
  v8 = this + 10;
  if ( ((_DWORD)this[10] & 0x20000) == 0 )
    return (unsigned int)Pointer;
  v9 = 522;
  memset_0(v33, 0, 0x20Au);
  memset_0(v35, 0, 0x20Au);
  v10 = 0;
  Simple = 0;
  if ( !a2 )
  {
    a2 = (const unsigned __int16 *)this[18];
    if ( !a2 )
      return (unsigned int)-2147467259;
  }
  LODWORD(v30) = 522;
  if ( *a2 == 92 && a2[1] == 92 )
  {
    v21 = 2147483646;
    v22 = a2;
    v23 = 261;
    v24 = (unsigned __int16 *)v33;
    do
    {
      if ( !v21 )
        break;
      v25 = *v22;
      if ( !*v22 )
        break;
      ++v22;
      *v24++ = v25;
      --v21;
      --v23;
    }
    while ( v23 );
    v26 = v24 - 1;
    if ( v23 )
      v26 = v24;
    *v26 = 0;
    goto LABEL_40;
  }
  Library = LoadLibraryExW(L"MPR.DLL", 0, 0);
  v12 = Library;
  if ( !Library )
    goto LABEL_9;
  ProcAddress = GetProcAddress(Library, "WNetGetUniversalNameW");
  if ( !ProcAddress )
  {
    FreeLibrary(v12);
LABEL_9:
    LastError = GetLastError();
    Pointer = LastError;
    if ( LastError <= 0 )
    {
LABEL_12:
      v15 = Pointer < 0;
      goto LABEL_13;
    }
    Pointer = (unsigned __int16)LastError;
LABEL_11:
    Pointer |= 0x80070000;
    goto LABEL_12;
  }
  Pointer = ((__int64 (__fastcall *)(const unsigned __int16 *, __int64, _BYTE *, char **))ProcAddress)(a2, 1, v33, &v30);
  FreeLibrary(v12);
  if ( !Pointer )
  {
    v9 = (unsigned int)v30;
LABEL_40:
    if ( v9 - 7 > 0x203 )
      return (unsigned int)-2147467259;
    v14 = 4;
    for ( j = v34; (unsigned __int64)v14 + 2 <= v9 && *j; ++j )
    {
      if ( *j == 92 )
      {
        *j = 0;
        break;
      }
      v14 += 2;
    }
    v10 = (unsigned __int16 *)v34;
    goto LABEL_49;
  }
  if ( Pointer == 2250 )
  {
LABEL_49:
    Simple = v10;
    Pointer = 0;
    goto LABEL_12;
  }
  v15 = Pointer < 0;
  if ( Pointer > 0 )
  {
    Pointer = (unsigned __int16)Pointer;
    goto LABEL_11;
  }
LABEL_13:
  if ( !v15 )
  {
    if ( v10 )
    {
      Pointer = ResolveTarget((const unsigned __int16 **)&Simple, v35, v14);
      v10 = Simple;
    }
    if ( Pointer >= 0 )
    {
      v30 = (char *)(this + 10);
      v16 = wcsrchr(a2, 0x5Cu);
      v17 = v16 + 1;
      if ( !v16 )
        v17 = a2;
      v18.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                      0,
                      0,
                      v10,
                      v17,
                      *(_QWORD *)this[24],
                      *((_QWORD *)this[24] + 1),
                      *v8,
                      0).Pointer;
      Pointer = (signed int)v18.Pointer;
      Simple = (unsigned __int16 *)v18.Simple;
      v31 = (int)v18.Pointer;
      *v8 &= ~0x20000u;
      ResetAccountInfo(this[24]);
      operator delete(this[24]);
      this[24] = 0;
    }
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180004220  push    rbx
0x180004222  push    rsi
0x180004223  push    rdi
0x180004224  push    r12
0x180004226  push    r13
0x180004228  push    r14
0x18000422a  push    r15
0x18000422c  sub     rsp, 490h
0x180004233  mov     rax, cs:__security_cookie
0x18000423a  xor     rax, rsp
0x18000423d  mov     [rsp+4C8h+var_48], rax
0x180004245  mov     r12d, r8d
0x180004248  mov     r15, rdx
0x18000424b  mov     rdi, rcx
0x18000424e  mov     [rsp+4C8h+var_470], rcx
0x180004253  xor     esi, esi
0x180004255  mov     ebx, esi
0x180004257  mov     r14d, esi
0x18000425a  cmp     r14d, 3
0x18000425e  jge     loc_1800043F8
0x180004264  mov     r9d, 1; unsigned int
0x18000426a  mov     r8d, r12d; int
0x18000426d  mov     rdx, r15; unsigned __int16 *
0x180004270  lea     rcx, [rdi-8]; this
0x180004274  call    ?SaveP@CJob@@QEAAJPEBGHK@Z; CJob::SaveP(ushort const *,int,ulong)
0x180004279  mov     ebx, eax
0x18000427b  test    eax, eax
0x18000427d  js      loc_180004429
0x180004283  mov     ebx, esi
0x180004285  lea     r14, [rdi+50h]
0x180004289  test    dword ptr [r14], 20000h
0x180004290  jz      loc_1800043D3
0x180004296  mov     ebx, 20Ah
0x18000429b  mov     r8d, ebx; Size
0x18000429e  xor     edx, edx; Val
0x1800042a0  lea     rcx, [rsp+4C8h+var_468]; void *
0x1800042a5  call    memset_0
0x1800042aa  mov     r8d, ebx; Size
0x1800042ad  xor     edx, edx; Val
0x1800042af  lea     rcx, [rsp+4C8h+var_258]; void *
0x1800042b7  call    memset_0
0x1800042bc  mov     r12, rsi
0x1800042bf  mov     [rsp+4C8h+var_488], rsi
0x1800042c4  test    r15, r15
0x1800042c7  jz      loc_180004402
0x1800042cd  mov     dword ptr [rsp+4C8h+var_480], ebx
0x1800042d1  cmp     word ptr [r15], 5Ch ; '\'
0x1800042d6  jz      loc_18000445E
0x1800042dc  xor     r8d, r8d; dwFlags
0x1800042df  xor     edx, edx; hFile
0x1800042e1  lea     rcx, LibFileName; "MPR.DLL"
0x1800042e8  call    cs:__imp_LoadLibraryExW
0x1800042ee  mov     r13, rax
0x1800042f1  test    rax, rax
0x1800042f4  jnz     loc_1800044B0
0x1800042fa  call    cs:__imp_GetLastError
0x180004300  mov     ebx, eax
0x180004302  test    eax, eax
0x180004304  jle     short loc_18000430F
0x180004306  movzx   ebx, ax
0x180004309  or      ebx, 80070000h
0x18000430f  test    ebx, ebx
0x180004311  js      loc_1800043D3
0x180004317  test    r12, r12
0x18000431a  jnz     loc_18000455E
0x180004320  test    ebx, ebx
0x180004322  js      loc_1800043D3
0x180004328  mov     [rsp+4C8h+var_480], r14
0x18000432d  mov     edx, 5Ch ; '\'; Ch
0x180004332  mov     rcx, r15; Str
0x180004335  call    cs:__imp_wcsrchr
0x18000433b  nop
0x18000433c  lea     r10, [rax+2]
0x180004340  test    rax, rax
0x180004343  cmovz   r10, r15
0x180004347  mov     r8d, [r14]
0x18000434a  mov     rax, [rdi+0C0h]
0x180004351  mov     rcx, [rax+8]
0x180004355  mov     rdx, [rax]
0x180004358  mov     [rsp+4C8h+var_488], rsi
0x18000435d  mov     [rsp+4C8h+var_490], r8d
0x180004362  mov     [rsp+4C8h+var_498], rcx
0x180004367  mov     [rsp+4C8h+var_4A0], rdx
0x18000436c  mov     [rsp+4C8h+var_4A8], r10
0x180004371  mov     r9, r12
0x180004374  xor     r8d, r8d; pReturnValue
0x180004377  xor     edx, edx; nProcNum
0x180004379  lea     rcx, pProxyInfo; pProxyInfo
0x180004380  call    cs:__imp_NdrClientCall3
0x180004386  mov     rbx, rax
0x180004389  mov     [rsp+4C8h+var_488], rax
0x18000438e  mov     [rsp+4C8h+var_478], eax
0x180004392  jmp     short loc_1800043AD
0x180004394  mov     ecx, eax; unsigned int
0x180004396  call    ?SchedMapRpcError@@YAJK@Z; SchedMapRpcError(ulong)
0x18000439b  mov     ebx, eax
0x18000439d  mov     [rsp+4C8h+var_478], eax
0x1800043a1  xor     esi, esi
0x1800043a3  mov     r14, [rsp+4C8h+var_480]
0x1800043a8  mov     rdi, [rsp+4C8h+var_470]
0x1800043ad  and     dword ptr [r14], 0FFFDFFFFh
0x1800043b4  mov     rcx, [rdi+0C0h]; struct _JOB_ACCOUNT_INFO *
0x1800043bb  call    ?ResetAccountInfo@@YAXPEAU_JOB_ACCOUNT_INFO@@@Z; ResetAccountInfo(_JOB_ACCOUNT_INFO *)
0x1800043c0  mov     rcx, [rdi+0C0h]; Block
0x1800043c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043cc  mov     [rdi+0C0h], rsi
0x1800043d3  mov     eax, ebx
0x1800043d5  mov     rcx, [rsp+4C8h+var_48]
0x1800043dd  xor     rcx, rsp; StackCookie
0x1800043e0  call    __security_check_cookie
0x1800043e5  add     rsp, 490h
0x1800043ec  pop     r15
0x1800043ee  pop     r14
0x1800043f0  pop     r13
0x1800043f2  pop     r12
0x1800043f4  pop     rdi
0x1800043f5  pop     rsi
0x1800043f6  pop     rbx
0x1800043f7  retn
0x1800043f8  test    ebx, ebx
0x1800043fa  jns     loc_180004285
0x180004400  jmp     short loc_1800043D3
0x180004402  mov     r15, [rdi+90h]
0x180004409  test    r15, r15
0x18000440c  jnz     loc_1800042CD
0x180004412  mov     ebx, 80004005h
0x180004417  jmp     short loc_1800043D3
0x180004419  test    ebx, ebx
0x18000441b  jle     loc_180004311
0x180004421  movzx   ebx, bx
0x180004424  jmp     loc_180004309
0x180004429  call    cs:__imp_rand
0x18000442f  mov     ecx, eax
0x180004431  mov     eax, 10624DD3h
0x180004436  imul    ecx
0x180004438  sar     edx, 4
0x18000443b  mov     eax, edx
0x18000443d  shr     eax, 1Fh
0x180004440  add     edx, eax
0x180004442  imul    eax, edx, 0FAh
0x180004448  sub     ecx, eax
0x18000444a  add     ecx, 0FAh; dwMilliseconds
0x180004450  call    cs:__imp_Sleep
0x180004456  inc     r14d
0x180004459  jmp     loc_18000425A
0x18000445e  cmp     word ptr [r15+2], 5Ch ; '\'
0x180004464  jnz     loc_1800042DC
0x18000446a  mov     eax, 7FFFFFFEh
0x18000446f  mov     r8, r15
0x180004472  mov     edx, 105h
0x180004477  lea     rcx, [rsp+4C8h+var_468]
0x18000447c  test    rax, rax
0x18000447f  jz      short loc_1800044A0
0x180004481  movzx   r9d, word ptr [r8]
0x180004485  test    r9w, r9w
0x180004489  jz      short loc_1800044A0
0x18000448b  add     r8, 2
0x18000448f  mov     [rcx], r9w
0x180004493  add     rcx, 2
0x180004497  dec     rax
0x18000449a  sub     rdx, 1
0x18000449e  jnz     short loc_18000447C
0x1800044a0  lea     rax, [rcx-2]
0x1800044a4  test    rdx, rdx
0x1800044a7  cmovnz  rax, rcx
0x1800044ab  mov     [rax], si
0x1800044ae  jmp     short loc_1800044FD
0x1800044b0  lea     rdx, ProcName; "WNetGetUniversalNameW"
0x1800044b7  mov     rcx, r13; hModule
0x1800044ba  call    cs:__imp_GetProcAddress
0x1800044c0  test    rax, rax
0x1800044c3  jnz     short loc_1800044D3
0x1800044c5  mov     rcx, r13; hLibModule
0x1800044c8  call    cs:__imp_FreeLibrary
0x1800044ce  jmp     loc_1800042FA
0x1800044d3  lea     r9, [rsp+4C8h+var_480]
0x1800044d8  lea     r8, [rsp+4C8h+var_468]
0x1800044dd  mov     edx, 1
0x1800044e2  mov     rcx, r15
0x1800044e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ea  mov     ebx, eax
0x1800044ec  mov     rcx, r13; hLibModule
0x1800044ef  call    cs:__imp_FreeLibrary
0x1800044f5  test    ebx, ebx
0x1800044f7  jnz     short loc_180004546
0x1800044f9  mov     ebx, dword ptr [rsp+4C8h+var_480]
0x1800044fd  lea     eax, [rbx-7]
0x180004500  cmp     eax, 203h
0x180004505  ja      loc_180004412
0x18000450b  mov     r8d, 4
0x180004511  lea     rdx, [rsp+4C8h+var_464]
0x180004516  mov     ecx, r8d
0x180004519  add     rcx, 2
0x18000451d  mov     eax, ebx
0x18000451f  cmp     rcx, rax
0x180004522  ja      short loc_18000453F
0x180004524  movzx   eax, word ptr [rdx]
0x180004527  test    ax, ax
0x18000452a  jz      short loc_18000453F
0x18000452c  cmp     ax, 5Ch ; '\'
0x180004530  jz      short loc_18000453C
0x180004532  add     rdx, 2
0x180004536  add     r8d, 2
0x18000453a  jmp     short loc_180004516
0x18000453c  mov     [rdx], si
0x18000453f  lea     r12, [rsp+4C8h+var_464]
0x180004544  jmp     short loc_180004552
0x180004546  cmp     ebx, 8CAh
0x18000454c  jnz     loc_180004419
0x180004552  mov     [rsp+4C8h+var_488], r12
0x180004557  mov     ebx, esi
0x180004559  jmp     loc_18000430F
0x18000455e  lea     rdx, [rsp+4C8h+var_258]; unsigned __int16 *
0x180004566  lea     rcx, [rsp+4C8h+var_488]; unsigned __int16 **
0x18000456b  call    ?ResolveTarget@@YAJPEAPEBGPEAGK@Z; ResolveTarget(ushort const * *,ushort *,ulong)
0x180004570  mov     ebx, eax
0x180004572  mov     r12, [rsp+4C8h+var_488]
0x180004577  jmp     loc_180004320
0x18001abd0  push    rbp
0x18001abd2  sub     rsp, 40h
0x18001abd6  mov     rbp, rdx
0x18001abd9  mov     rcx, [rcx]
0x18001abdc  mov     ecx, [rcx]; ExceptionCode
0x18001abde  call    cs:__imp_I_RpcExceptionFilter
0x18001abe4  nop
0x18001abe5  add     rsp, 40h
0x18001abe9  pop     rbp
0x18001abea  retn
```
