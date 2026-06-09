# CFileListener::OpenParentKeyAndGetChildKey(ushort *,ulong *,ushort * *)

- ea: `0x18000d194`
- end: `0x18000d36b`
- name: `?OpenParentKeyAndGetChildKey@CFileListener@@AEAAJPEAGPEAKPEAPEAG@Z`
- size: `471`
- prototype: `int(CFileListener *__hidden this, unsigned __int16 *, unsigned int *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000cf68`
- `0x18000d680`

## callees

- `0x180008a08`
- `0x180008a14`
- `0x18000d194`
- `0x18000eb08`
- `0x180031010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18000d212`
- `msvcrt!wcsrchr` at `0x18000d2a3`
- `msvcrt!wcsrchr` at `0x18000d212`
- `msvcrt!wcsrchr` at `0x18000d2a3`
- `IisRTL!PuDbgPrintW` at `0x18000d25b`
- `IisRTL!PuDbgPrintW` at `0x18000d34c`
- `IisRTL!PuDbgPrintW` at `0x18000d25b`
- `IisRTL!PuDbgPrintW` at `0x18000d34c`

## string_xrefs

- `0x18000d22f`: `[CFileListener::OpenParentKeyAndGetChildKey] Unable to find parent key: %s\n`
- `0x18000d243`: `CFileListener::OpenParentKeyAndGetChildKey`
- `0x18000d334`: `CFileListener::OpenParentKeyAndGetChildKey`
- `0x18000d28a`: `[CFileListener::OpenParentKeyAndGetChildKey] Unable to delete/modify the root key: %s\n`
- `0x18000d301`: `[CFileListener::ProcessChanges] Unable to open %s key. IMSAdminBase::OpenKey failed with hr = 0x%x. Assuming %s is deleted.\n`
- `0x18000d31c`: `[CFileListener::ProcessChanges] Unable to open %s key. IMSAdminBase::OpenKey failed with hr = 0x%x. Hence unable to delete %s.\n`

## pseudocode

```c
__int64 __fastcall CFileListener::OpenParentKeyAndGetChildKey(
        CFileListener *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  __int64 v5; // rax
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  wchar_t *v11; // rdi
  int v12; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  __int64 v15; // rcx

  *a4 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v9 = v5 + 1;
  v10 = (unsigned __int16 *)operator new[](saturated_mul(v5 + 1, 2u));
  v11 = v10;
  if ( v10 )
  {
    v12 = StringCchCopyW(v10, v9, a2);
    if ( v12 >= 0 )
    {
      v13 = wcsrchr(v11, 0x2Fu);
      if ( v13 )
      {
        if ( v11 == v13 )
        {
          if ( !v13[1] )
          {
            v12 = -2147024883;
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrintW(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\listener.cpp",
                2400,
                "CFileListener::OpenParentKeyAndGetChildKey",
                L"[CFileListener::OpenParentKeyAndGetChildKey] Unable to delete/modify the root key: %s\n",
                a2);
            goto LABEL_21;
          }
          v13[1] = 0;
        }
        else
        {
          *v13 = 0;
        }
        v14 = wcsrchr(a2, 0x2Fu);
        v15 = *((_QWORD *)this + 71);
        *a4 = v14 + 1;
        v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, __int64, int, unsigned int *))(*(_QWORD *)v15
                                                                                                  + 280LL))(
                v15,
                0,
                v11,
                2,
                30000,
                a3);
        if ( v12 == -2147024893 )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\listener.cpp",
              2433,
              "CFileListener::OpenParentKeyAndGetChildKey",
              L"[CFileListener::ProcessChanges] Unable to open %s key. IMSAdminBase::OpenKey failed with hr = 0x%x. Assumi"
               "ng %s is deleted.\n",
              v11,
              -2147024893,
              a2);
        }
        else if ( v12 < 0 && (g_dwDebugFlags & 3) != 0 )
        {
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            2441,
            "CFileListener::OpenParentKeyAndGetChildKey",
            L"[CFileListener::ProcessChanges] Unable to open %s key. IMSAdminBase::OpenKey failed with hr = 0x%x. Hence un"
             "able to delete %s.\n",
            v11,
            v12,
            a2);
        }
      }
      else
      {
        v12 = -2147024883;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrintW(
            g_pDebug,
            "inetsrv\\iis\\mb\\metadata\\listener.cpp",
            2383,
            "CFileListener::OpenParentKeyAndGetChildKey",
            L"[CFileListener::OpenParentKeyAndGetChildKey] Unable to find parent key: %s\n",
            a2);
      }
    }
LABEL_21:
    operator delete(v11);
    return (unsigned int)v12;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18000d194  push    rbx
0x18000d196  push    rbp
0x18000d197  push    rsi
0x18000d198  push    rdi
0x18000d199  push    r12
0x18000d19b  push    r14
0x18000d19d  push    r15
0x18000d19f  sub     rsp, 40h
0x18000d1a3  xor     r12d, r12d
0x18000d1a6  mov     r15, rcx
0x18000d1a9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d1ad  mov     [r9], r12
0x18000d1b0  mov     rax, rcx
0x18000d1b3  mov     r14, r9
0x18000d1b6  mov     rbp, r8
0x18000d1b9  mov     rsi, rdx
0x18000d1bc  inc     rax
0x18000d1bf  cmp     [rdx+rax*2], r12w
0x18000d1c4  jnz     short loc_18000D1BC
0x18000d1c6  lea     rbx, [rax+1]
0x18000d1ca  mov     eax, 2
0x18000d1cf  mul     rbx
0x18000d1d2  cmovb   rax, rcx
0x18000d1d6  mov     rcx, rax; unsigned __int64
0x18000d1d9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000d1de  mov     rdi, rax
0x18000d1e1  test    rax, rax
0x18000d1e4  jnz     short loc_18000D1F0
0x18000d1e6  mov     ebx, 8007000Eh
0x18000d1eb  jmp     loc_18000D35A
0x18000d1f0  mov     r8, rsi; unsigned __int16 *
0x18000d1f3  mov     rdx, rbx; unsigned __int64
0x18000d1f6  mov     rcx, rdi; unsigned __int16 *
0x18000d1f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d1fe  mov     ebx, eax
0x18000d200  test    eax, eax
0x18000d202  js      loc_18000D352
0x18000d208  mov     ebx, 2Fh ; '/'
0x18000d20d  mov     rcx, rdi; Str
0x18000d210  mov     edx, ebx; Ch
0x18000d212  call    cs:__imp_wcsrchr
0x18000d218  test    rax, rax
0x18000d21b  jnz     short loc_18000D266
0x18000d21d  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d224  mov     ebx, 8007000Dh
0x18000d229  jz      loc_18000D352
0x18000d22f  lea     rax, aCfilelistenerO_1; "[CFileListener::OpenParentKeyAndGetChil"...
0x18000d236  mov     r8d, 94Fh
0x18000d23c  mov     rcx, cs:g_pDebug
0x18000d243  lea     r9, aCfilelistenerO_6; "CFileListener::OpenParentKeyAndGetChild"...
0x18000d24a  mov     [rsp+78h+var_50], rsi
0x18000d24f  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d256  mov     [rsp+78h+var_58], rax
0x18000d25b  call    cs:__imp_PuDbgPrintW
0x18000d261  jmp     loc_18000D352
0x18000d266  cmp     rdi, rax
0x18000d269  jz      short loc_18000D271
0x18000d26b  mov     [rax], r12w
0x18000d26f  jmp     short loc_18000D29E
0x18000d271  cmp     [rax+2], r12w
0x18000d276  jnz     short loc_18000D299
0x18000d278  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d27f  mov     ebx, 8007000Dh
0x18000d284  jz      loc_18000D352
0x18000d28a  lea     rax, aCfilelistenerO_2; "[CFileListener::OpenParentKeyAndGetChil"...
0x18000d291  mov     r8d, 960h
0x18000d297  jmp     short loc_18000D23C
0x18000d299  mov     [rax+2], r12w
0x18000d29e  mov     edx, ebx; Ch
0x18000d2a0  mov     rcx, rsi; Str
0x18000d2a3  call    cs:__imp_wcsrchr
0x18000d2a9  mov     rcx, [r15+238h]
0x18000d2b0  mov     r9d, 2
0x18000d2b6  add     rax, 2
0x18000d2ba  mov     [rsp+78h+var_50], rbp
0x18000d2bf  mov     [r14], rax
0x18000d2c2  mov     r8, rdi
0x18000d2c5  xor     edx, edx
0x18000d2c7  mov     dword ptr [rsp+78h+var_58], 7530h
0x18000d2cf  mov     rax, [rcx]
0x18000d2d2  mov     rax, [rax+118h]
0x18000d2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2de  mov     ebx, eax
0x18000d2e0  mov     eax, 80070003h
0x18000d2e5  cmp     ebx, eax
0x18000d2e7  jnz     short loc_18000D30A
0x18000d2e9  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d2f0  jz      short loc_18000D352
0x18000d2f2  mov     [rsp+78h+var_40], rsi
0x18000d2f7  mov     r8d, 981h
0x18000d2fd  mov     [rsp+78h+var_48], eax
0x18000d301  lea     rax, aCfilelistenerP_15; "[CFileListener::ProcessChanges] Unable "...
0x18000d308  jmp     short loc_18000D32D
0x18000d30a  test    ebx, ebx
0x18000d30c  jns     short loc_18000D352
0x18000d30e  test    byte ptr cs:g_dwDebugFlags, 3
0x18000d315  jz      short loc_18000D352
0x18000d317  mov     [rsp+78h+var_40], rsi
0x18000d31c  lea     rax, aCfilelistenerP_3; "[CFileListener::ProcessChanges] Unable "...
0x18000d323  mov     [rsp+78h+var_48], ebx
0x18000d327  mov     r8d, 989h
0x18000d32d  mov     rcx, cs:g_pDebug
0x18000d334  lea     r9, aCfilelistenerO_6; "CFileListener::OpenParentKeyAndGetChild"...
0x18000d33b  mov     [rsp+78h+var_50], rdi
0x18000d340  lea     rdx, aInetsrvIisMbMe_5; "inetsrv\\iis\\mb\\metadata\\listener.cp"...
0x18000d347  mov     [rsp+78h+var_58], rax
0x18000d34c  call    cs:__imp_PuDbgPrintW
0x18000d352  mov     rcx, rdi; Block
0x18000d355  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d35a  mov     eax, ebx
0x18000d35c  add     rsp, 40h
0x18000d360  pop     r15
0x18000d362  pop     r14
0x18000d364  pop     r12
0x18000d366  pop     rdi
0x18000d367  pop     rsi
0x18000d368  pop     rbp
0x18000d369  pop     rbx
0x18000d36a  retn
```
