# NgscbGetWinReConfiguration(bool *,ushort *,ulong)

- ea: `0x1800d6540`
- end: `0x1800d672a`
- name: `?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z`
- size: `490`
- prototype: `__int64 __fastcall(bool *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callees

- `0x1800050c0`
- `0x1800090c0`
- `0x1800450c4`
- `0x18004fddc`
- `0x1800d6540`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d65bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d65bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d661e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d661e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d66fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d66fd`

## string_xrefs

- `0x1800d65ae`: `reinfo.dll`
- `0x1800d6614`: `WinReGetConfig`

## pseudocode

```c
__int64 __fastcall NgscbGetWinReConfiguration(bool *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // rbp
  unsigned int KnownLastErrorHR; // ebx
  HMODULE Library; // rax
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v13; // [rsp+20h] [rbp-ED8h] BYREF
  int v14; // [rsp+28h] [rbp-ED0h]
  unsigned __int16 v15[1556]; // [rsp+298h] [rbp-C60h] BYREF

  v3 = a3;
  memset_0(&v13, 0, 0xEA0u);
  KnownLastErrorHR = 0;
  *a1 = 0;
  if ( a2 )
    memset_0(a2, 0, 2LL * (unsigned int)v3);
  if ( !NgscbGet_TEST_BooleanOverride(L"ReportWinREAvailable", a1) )
  {
    Library = LoadLibraryExW(L"reinfo.dll", 0, 0x800u);
    v8 = Library;
    if ( !Library )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          334,
          &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
          KnownLastErrorHR);
      return KnownLastErrorHR;
    }
    ProcAddress = GetProcAddress(Library, "WinReGetConfig");
    if ( ProcAddress )
    {
      v13 = 3744;
      if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v13) )
      {
        *a1 = v14 != 0;
        if ( !a2 )
          goto LABEL_22;
        KnownLastErrorHR = StringCchCopyW(a2, v3, v15);
        if ( !KnownLastErrorHR )
          goto LABEL_22;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v11 = 337;
      }
      else
      {
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_22;
        v11 = 336;
      }
    }
    else
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_22;
      v11 = 335;
    }
    WPP_SF_d(v10[2], v11, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, KnownLastErrorHR);
LABEL_22:
    FreeLibrary(v8);
  }
  return KnownLastErrorHR;
}

```

## disassembly

```asm
0x1800d6540  push    rbx
0x1800d6542  push    rbp
0x1800d6543  push    rsi
0x1800d6544  push    rdi
0x1800d6545  push    r14
0x1800d6547  sub     rsp, 0ED0h
0x1800d654e  mov     rax, cs:__security_cookie
0x1800d6555  xor     rax, rsp
0x1800d6558  mov     [rsp+0EF8h+var_38], rax
0x1800d6560  mov     ebp, r8d
0x1800d6563  mov     rdi, rdx
0x1800d6566  mov     r14, rcx
0x1800d6569  xor     edx, edx; Val
0x1800d656b  mov     r8d, 0EA0h; Size
0x1800d6571  lea     rcx, [rsp+0EF8h+var_ED8]; void *
0x1800d6576  call    memset_0
0x1800d657b  xor     ebx, ebx
0x1800d657d  mov     [r14], bl
0x1800d6580  test    rdi, rdi
0x1800d6583  jz      short loc_1800D6595
0x1800d6585  mov     r8d, ebp
0x1800d6588  xor     edx, edx; Val
0x1800d658a  add     r8, r8; Size
0x1800d658d  mov     rcx, rdi; void *
0x1800d6590  call    memset_0
0x1800d6595  mov     rdx, r14; bool *
0x1800d6598  lea     rcx, aReportwinreava; "ReportWinREAvailable"
0x1800d659f  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x1800d65a4  test    al, al
0x1800d65a6  jnz     loc_1800D6709
0x1800d65ac  xor     edx, edx; hFile
0x1800d65ae  lea     rcx, aReinfoDll; "reinfo.dll"
0x1800d65b5  mov     r8d, 800h; dwFlags
0x1800d65bb  call    cs:__imp_LoadLibraryExW
0x1800d65c2  nop     dword ptr [rax+rax+00h]
0x1800d65c7  mov     rsi, rax
0x1800d65ca  test    rax, rax
0x1800d65cd  jnz     short loc_1800D6614
0x1800d65cf  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800d65d4  mov     ebx, eax
0x1800d65d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d65dd  lea     rax, WPP_GLOBAL_Control
0x1800d65e4  cmp     rcx, rax
0x1800d65e7  jz      loc_1800D6709
0x1800d65ed  test    byte ptr [rcx+1Ch], 40h
0x1800d65f1  jz      loc_1800D6709
0x1800d65f7  mov     rcx, [rcx+10h]
0x1800d65fb  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d6602  mov     edx, 14Eh
0x1800d6607  mov     r9d, ebx
0x1800d660a  call    WPP_SF_d
0x1800d660f  jmp     loc_1800D6709
0x1800d6614  lea     rdx, aWinregetconfig_0; "WinReGetConfig"
0x1800d661b  mov     rcx, rsi; hModule
0x1800d661e  call    cs:__imp_GetProcAddress
0x1800d6625  nop     dword ptr [rax+rax+00h]
0x1800d662a  test    rax, rax
0x1800d662d  jnz     short loc_1800D6661
0x1800d662f  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800d6634  mov     ebx, eax
0x1800d6636  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d663d  lea     rax, WPP_GLOBAL_Control
0x1800d6644  cmp     rcx, rax
0x1800d6647  jz      loc_1800D66FA
0x1800d664d  test    byte ptr [rcx+1Ch], 40h
0x1800d6651  jz      loc_1800D66FA
0x1800d6657  mov     edx, 14Fh
0x1800d665c  jmp     loc_1800D66E7
0x1800d6661  lea     rdx, [rsp+0EF8h+var_ED8]
0x1800d6666  mov     [rsp+0EF8h+var_ED8], 0EA0h
0x1800d666f  xor     ecx, ecx
0x1800d6671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6676  test    eax, eax
0x1800d6678  jnz     short loc_1800D66A1
0x1800d667a  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800d667f  mov     ebx, eax
0x1800d6681  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6688  lea     rax, WPP_GLOBAL_Control
0x1800d668f  cmp     rcx, rax
0x1800d6692  jz      short loc_1800D66FA
0x1800d6694  test    byte ptr [rcx+1Ch], 40h
0x1800d6698  jz      short loc_1800D66FA
0x1800d669a  mov     edx, 150h
0x1800d669f  jmp     short loc_1800D66E7
0x1800d66a1  cmp     [rsp+0EF8h+var_ED0], ebx
0x1800d66a5  setnz   al
0x1800d66a8  mov     [r14], al
0x1800d66ab  test    rdi, rdi
0x1800d66ae  jz      short loc_1800D66FA
0x1800d66b0  mov     rdx, rbp; unsigned __int64
0x1800d66b3  lea     r8, [rsp+0EF8h+var_C60]; unsigned __int16 *
0x1800d66bb  mov     rcx, rdi; unsigned __int16 *
0x1800d66be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d66c3  mov     ebx, eax
0x1800d66c5  test    eax, eax
0x1800d66c7  jz      short loc_1800D66FA
0x1800d66c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d66d0  lea     rax, WPP_GLOBAL_Control
0x1800d66d7  cmp     rcx, rax
0x1800d66da  jz      short loc_1800D66FA
0x1800d66dc  test    byte ptr [rcx+1Ch], 40h
0x1800d66e0  jz      short loc_1800D66FA
0x1800d66e2  mov     edx, 151h
0x1800d66e7  mov     rcx, [rcx+10h]
0x1800d66eb  lea     r8, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d66f2  mov     r9d, ebx
0x1800d66f5  call    WPP_SF_d
0x1800d66fa  mov     rcx, rsi; hLibModule
0x1800d66fd  call    cs:__imp_FreeLibrary
0x1800d6704  nop     dword ptr [rax+rax+00h]
0x1800d6709  mov     eax, ebx
0x1800d670b  mov     rcx, [rsp+0EF8h+var_38]
0x1800d6713  xor     rcx, rsp; StackCookie
0x1800d6716  call    __security_check_cookie
0x1800d671b  add     rsp, 0ED0h
0x1800d6722  pop     r14
0x1800d6724  pop     rdi
0x1800d6725  pop     rsi
0x1800d6726  pop     rbp
0x1800d6727  pop     rbx
0x1800d6728  retn
```
