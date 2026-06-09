# IsRetriableSession(ushort const *,ushort const *,ulong,int *,long *)

- ea: `0x140010bb8`
- end: `0x140010cff`
- name: `?IsRetriableSession@@YAJPEBG0KPEAHPEAJ@Z`
- size: `327`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, int *@<r9>, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fff0`

## callees

- `0x14000b708`
- `0x14000c084`
- `0x140010bb8`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010c1f`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010c1f`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140010c77`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140010c77`

## string_xrefs

- `0x140010c44`: `OmaDmRegistryGetDWORD`
- `0x140010c9e`: `IsNonAutoDeleteSession`

## pseudocode

```c
__int64 __fastcall IsRetriableSession(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3, int *a4, int *a5)
{
  int *v9; // r15
  int DWORD; // eax
  unsigned int v11; // ebx
  COmaDmPrcLogger *v12; // rax
  const unsigned __int16 *v13; // rcx
  int v14; // edx
  unsigned int v15; // eax
  COmaDmPrcLogger *Logger; // rax
  unsigned int v18; // [rsp+70h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 || !a2 || !a4 || (v9 = a5) == 0 )
  {
    Logger = COmaDmPrcLogger::GetLogger();
    v11 = -2147024809;
    COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(
      Logger,
      a1,
      a2,
      L"IsRetriableSession",
      L"IsRetriableSession",
      -2147024809);
    return v11;
  }
  *a4 = 0;
  DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, a2, L"SessionHRESULT", &v18);
  v11 = DWORD;
  if ( DWORD < 0 )
  {
    if ( DWORD == -2147024894 )
      return 0;
    v12 = COmaDmPrcLogger::GetLogger();
    v13 = L"OmaDmRegistryGetDWORD";
LABEL_17:
    COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(v12, a1, a2, L"IsRetriableSession", v13, v11);
    return v11;
  }
  if ( v18 + 2147012894 <= 0x1E && (v14 = 1476427821, _bittest(&v14, v18 + 2147012894))
    || v18 == -2147012816
    || v18 == -2102657013 )
  {
    if ( IsWvdFeatureAllowed(a1) )
    {
      v12 = COmaDmPrcLogger::GetLogger();
      v13 = L"IsWvdFeatureAllowed";
    }
    else
    {
      if ( a3 )
      {
        v15 = v18;
        *a4 = 1;
        *v9 = v15;
        return v11;
      }
      v12 = COmaDmPrcLogger::GetLogger();
      v13 = L"IsNonAutoDeleteSession";
    }
    goto LABEL_17;
  }
  return v11;
}

```

## disassembly

```asm
0x140010bb8  push    rbx
0x140010bba  push    rbp
0x140010bbb  push    rsi
0x140010bbc  push    rdi
0x140010bbd  push    r14
0x140010bbf  push    r15
0x140010bc1  sub     rsp, 38h
0x140010bc5  mov     [rsp+68h+arg_0], 0
0x140010bcd  mov     r14, r9
0x140010bd0  mov     ebp, r8d
0x140010bd3  mov     rdi, rdx
0x140010bd6  mov     rsi, rcx
0x140010bd9  test    rcx, rcx
0x140010bdc  jz      loc_140010CC7
0x140010be2  test    rdx, rdx
0x140010be5  jz      loc_140010CC7
0x140010beb  test    r9, r9
0x140010bee  jz      loc_140010CC7
0x140010bf4  mov     r15, [rsp+68h+arg_20]
0x140010bfc  test    r15, r15
0x140010bff  jz      loc_140010CC7
0x140010c05  mov     dword ptr [r9], 0
0x140010c0c  lea     r8, aSessionhresult; "SessionHRESULT"
0x140010c13  lea     r9, [rsp+68h+arg_0]
0x140010c18  mov     rcx, 0FFFFFFFF80000002h
0x140010c1f  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140010c26  nop     dword ptr [rax+rax+00h]
0x140010c2b  mov     ebx, eax
0x140010c2d  test    eax, eax
0x140010c2f  jns     short loc_140010C4D
0x140010c31  cmp     eax, 80070002h
0x140010c36  jnz     short loc_140010C3F
0x140010c38  xor     ebx, ebx
0x140010c3a  jmp     loc_140010CEF
0x140010c3f  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010c44  lea     rcx, aOmadmregistryg; "OmaDmRegistryGetDWORD"
0x140010c4b  jmp     short loc_140010CA5
0x140010c4d  mov     eax, [rsp+68h+arg_0]
0x140010c51  lea     ecx, [rax+7FF8D11Eh]
0x140010c57  cmp     ecx, 1Eh
0x140010c5a  ja      short loc_140010C66
0x140010c5c  mov     edx, 5800802Dh
0x140010c61  bt      edx, ecx
0x140010c64  jb      short loc_140010C74
0x140010c66  cmp     eax, 80072F30h
0x140010c6b  jz      short loc_140010C74
0x140010c6d  cmp     eax, 82AC000Bh
0x140010c72  jnz     short loc_140010CEF
0x140010c74  mov     rcx, rsi
0x140010c77  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x140010c7e  nop     dword ptr [rax+rax+00h]
0x140010c83  test    eax, eax
0x140010c85  jz      short loc_140010C95
0x140010c87  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010c8c  lea     rcx, aIswvdfeatureal; "IsWvdFeatureAllowed"
0x140010c93  jmp     short loc_140010CA5
0x140010c95  test    ebp, ebp
0x140010c97  jnz     short loc_140010CB7
0x140010c99  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010c9e  lea     rcx, aIsnonautodelet; "IsNonAutoDeleteSession"
0x140010ca5  mov     [rsp+68h+var_40], ebx
0x140010ca9  lea     r9, aIsretriableses; "IsRetriableSession"
0x140010cb0  mov     [rsp+68h+var_48], rcx
0x140010cb5  jmp     short loc_140010CE1
0x140010cb7  mov     eax, [rsp+68h+arg_0]
0x140010cbb  mov     dword ptr [r14], 1
0x140010cc2  mov     [r15], eax
0x140010cc5  jmp     short loc_140010CEF
0x140010cc7  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010ccc  mov     ebx, 80070057h
0x140010cd1  lea     r9, aIsretriableses; "IsRetriableSession"
0x140010cd8  mov     [rsp+68h+var_40], ebx; int
0x140010cdc  mov     [rsp+68h+var_48], r9; unsigned __int16 *
0x140010ce1  mov     r8, rdi; unsigned __int16 *
0x140010ce4  mov     rdx, rsi; unsigned __int16 *
0x140010ce7  mov     rcx, rax; this
0x140010cea  call    ?LogOmaDmPrcScheduleRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x140010cef  mov     eax, ebx
0x140010cf1  add     rsp, 38h
0x140010cf5  pop     r15
0x140010cf7  pop     r14
0x140010cf9  pop     rdi
0x140010cfa  pop     rsi
0x140010cfb  pop     rbp
0x140010cfc  pop     rbx
0x140010cfd  retn
```
