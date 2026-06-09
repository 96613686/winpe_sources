# GetInfInfo(ushort const *,HICON__ * *)

- ea: `0x180006700`
- end: `0x18000691b`
- name: `?GetInfInfo@@YAPEAGPEBGPEAPEAUHICON__@@@Z`
- size: `539`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, HICON *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007630`

## callees

- `0x180001254`
- `0x180001294`
- `0x180003550`
- `0x180006700`
- `0x18000ccde`
- `0x18000cd10`
- `0x18000cda0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180006870`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180006870`
- `SETUPAPI!SetupFindFirstLineW` at `0x18000677d`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800067a0`
- `SETUPAPI!SetupFindFirstLineW` at `0x180006829`
- `SETUPAPI!SetupFindFirstLineW` at `0x18000677d`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800067a0`
- `SETUPAPI!SetupFindFirstLineW` at `0x180006829`
- `SETUPAPI!SetupOpenInfFileW` at `0x18000673e`
- `SETUPAPI!SetupOpenInfFileW` at `0x18000673e`
- `SETUPAPI!SetupDiLoadClassIcon` at `0x1800068e3`
- `SETUPAPI!SetupDiLoadClassIcon` at `0x1800068e3`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800067ee`
- `SETUPAPI!SetupGetStringFieldW` at `0x180006858`
- `SETUPAPI!SetupGetStringFieldW` at `0x1800067ee`
- `SETUPAPI!SetupGetStringFieldW` at `0x180006858`
- `SETUPAPI!SetupDiGetClassDescriptionExW` at `0x18000689c`
- `SETUPAPI!SetupDiGetClassDescriptionExW` at `0x18000689c`
- `SETUPAPI!SetupCloseInfFile` at `0x1800067ad`
- `SETUPAPI!SetupCloseInfFile` at `0x1800067fb`
- `SETUPAPI!SetupCloseInfFile` at `0x1800068ec`
- `SETUPAPI!SetupCloseInfFile` at `0x1800067ad`
- `SETUPAPI!SetupCloseInfFile` at `0x1800067fb`
- `SETUPAPI!SetupCloseInfFile` at `0x1800068ec`

## pseudocode

```c
unsigned __int16 *__fastcall GetInfInfo(const unsigned __int16 *a1, HICON *a2)
{
  HINF v3; // rbx
  int v5; // r14d
  void *v6; // rdi
  _INFCONTEXT Context; // [rsp+30h] [rbp-D0h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ReturnBuffer[4096]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = SetupOpenInfFileW(a1, 0, 2u, 0);
  if ( v3 == (HINF)-1LL )
    return 0;
  v5 = 1;
  memset(&Context, 0, sizeof(Context));
  if ( !SetupFindFirstLineW(v3, L"Version", L"DriverPackageDisplayName", &Context) )
  {
    v5 = 0;
    if ( !SetupFindFirstLineW(v3, L"Version", L"Provider", &Context) )
    {
      SetupCloseInfFile(v3);
      return 0;
    }
  }
  v6 = operator new(0x2000u);
  memset_0(v6, 0, 0x800u);
  if ( !SetupGetStringFieldW(&Context, 1u, (PWSTR)v6, 0x800u, 0) )
  {
    SetupCloseInfFile(v3);
    operator delete(v6);
    return 0;
  }
  pclsid = 0;
  if ( SetupFindFirstLineW(v3, L"Version", L"ClassGUID", &Context)
    && SetupGetStringFieldW(&Context, 1u, ReturnBuffer, 0x1000u, 0)
    && CLSIDFromString(ReturnBuffer, &pclsid) >= 0
    && SetupDiGetClassDescriptionExW(&pclsid, ReturnBuffer, 0x1000u, 0, 0, 0) )
  {
    if ( !v5 )
    {
      StringCchCatW((unsigned __int16 *)v6, 0x1000u, L" ");
      StringCchCatW((unsigned __int16 *)v6, 0x1000u, ReturnBuffer);
    }
    if ( a2 )
    {
      if ( !*a2 )
        SetupDiLoadClassIcon(&pclsid, a2, 0);
    }
  }
  SetupCloseInfFile(v3);
  return (unsigned __int16 *)v6;
}

```

## disassembly

```asm
0x180006700  mov     [rsp-8+arg_10], rbx
0x180006705  push    rbp
0x180006706  push    rsi
0x180006707  push    rdi
0x180006708  push    r14
0x18000670a  push    r15
0x18000670c  lea     rbp, [rsp-1F70h]
0x180006714  mov     eax, 2070h
0x180006719  call    _alloca_probe
0x18000671e  sub     rsp, rax
0x180006721  mov     rax, cs:__security_cookie
0x180006728  xor     rax, rsp
0x18000672b  mov     [rbp+1F90h+var_30], rax
0x180006732  xor     r9d, r9d; ErrorLine
0x180006735  mov     rsi, rdx
0x180006738  xor     edx, edx; InfClass
0x18000673a  lea     r8d, [r9+2]; InfStyle
0x18000673e  call    cs:__imp_SetupOpenInfFileW
0x180006744  mov     rbx, rax
0x180006747  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000674b  jnz     short loc_180006754
0x18000674d  xor     eax, eax
0x18000674f  jmp     loc_1800068F5
0x180006754  xor     eax, eax
0x180006756  lea     r9, [rsp+2090h+Context]; Context
0x18000675b  xorps   xmm0, xmm0
0x18000675e  mov     qword ptr [rsp+2090h+Context.Section], rax
0x180006763  lea     r8, Key; "DriverPackageDisplayName"
0x18000676a  mov     rcx, rbx; InfHandle
0x18000676d  lea     rdx, Section; "Version"
0x180006774  lea     r14d, [rax+1]
0x180006778  movups  xmmword ptr [rsp+2090h+Context.Inf], xmm0
0x18000677d  call    cs:__imp_SetupFindFirstLineW
0x180006783  test    eax, eax
0x180006785  jnz     short loc_1800067B5
0x180006787  lea     r9, [rsp+2090h+Context]; Context
0x18000678c  mov     rcx, rbx; InfHandle
0x18000678f  lea     r8, aProvider; "Provider"
0x180006796  xor     r14d, r14d
0x180006799  lea     rdx, Section; "Version"
0x1800067a0  call    cs:__imp_SetupFindFirstLineW
0x1800067a6  test    eax, eax
0x1800067a8  jnz     short loc_1800067B5
0x1800067aa  mov     rcx, rbx; InfHandle
0x1800067ad  call    cs:__imp_SetupCloseInfFile
0x1800067b3  jmp     short loc_18000674D
0x1800067b5  mov     ecx, 2000h; Size
0x1800067ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800067bf  mov     r15d, 800h
0x1800067c5  xor     edx, edx; Val
0x1800067c7  mov     r8d, r15d; Size
0x1800067ca  mov     rcx, rax; void *
0x1800067cd  mov     rdi, rax
0x1800067d0  call    memset_0
0x1800067d5  mov     r9d, r15d; ReturnBufferSize
0x1800067d8  mov     [rsp+2090h+RequiredSize], 0; RequiredSize
0x1800067e1  mov     r8, rdi; ReturnBuffer
0x1800067e4  lea     rcx, [rsp+2090h+Context]; Context
0x1800067e9  mov     edx, 1; FieldIndex
0x1800067ee  call    cs:__imp_SetupGetStringFieldW
0x1800067f4  mov     rcx, rbx; InfHandle
0x1800067f7  test    eax, eax
0x1800067f9  jnz     short loc_18000680E
0x1800067fb  call    cs:__imp_SetupCloseInfFile
0x180006801  mov     rcx, rdi; Block
0x180006804  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006809  jmp     loc_18000674D
0x18000680e  xorps   xmm0, xmm0
0x180006811  lea     r9, [rsp+2090h+Context]; Context
0x180006816  lea     r8, aClassguid; "ClassGUID"
0x18000681d  lea     rdx, Section; "Version"
0x180006824  movups  xmmword ptr [rsp+2090h+pclsid.Data1], xmm0
0x180006829  call    cs:__imp_SetupFindFirstLineW
0x18000682f  test    eax, eax
0x180006831  jz      loc_1800068E9
0x180006837  mov     r15d, 1000h
0x18000683d  mov     [rsp+2090h+RequiredSize], 0; RequiredSize
0x180006846  mov     r9d, r15d; ReturnBufferSize
0x180006849  lea     r8, [rsp+2090h+ReturnBuffer]; ReturnBuffer
0x18000684e  mov     edx, 1; FieldIndex
0x180006853  lea     rcx, [rsp+2090h+Context]; Context
0x180006858  call    cs:__imp_SetupGetStringFieldW
0x18000685e  test    eax, eax
0x180006860  jz      loc_1800068E9
0x180006866  lea     rdx, [rsp+2090h+pclsid]; pclsid
0x18000686b  lea     rcx, [rsp+2090h+ReturnBuffer]; lpsz
0x180006870  call    cs:__imp_CLSIDFromString
0x180006876  test    eax, eax
0x180006878  js      short loc_1800068E9
0x18000687a  mov     [rsp+2090h+Reserved], 0; Reserved
0x180006883  lea     rdx, [rsp+2090h+ReturnBuffer]; ClassDescription
0x180006888  xor     r9d, r9d; RequiredSize
0x18000688b  mov     [rsp+2090h+RequiredSize], 0; MachineName
0x180006894  mov     r8d, r15d; ClassDescriptionSize
0x180006897  lea     rcx, [rsp+2090h+pclsid]; ClassGuid
0x18000689c  call    cs:__imp_SetupDiGetClassDescriptionExW
0x1800068a2  test    eax, eax
0x1800068a4  jz      short loc_1800068E9
0x1800068a6  test    r14d, r14d
0x1800068a9  jnz     short loc_1800068CD
0x1800068ab  lea     r8, asc_180010214; " "
0x1800068b2  mov     edx, r15d; unsigned __int64
0x1800068b5  mov     rcx, rdi; unsigned __int16 *
0x1800068b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068bd  lea     r8, [rsp+2090h+ReturnBuffer]; unsigned __int16 *
0x1800068c2  mov     edx, r15d; unsigned __int64
0x1800068c5  mov     rcx, rdi; unsigned __int16 *
0x1800068c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800068cd  test    rsi, rsi
0x1800068d0  jz      short loc_1800068E9
0x1800068d2  cmp     qword ptr [rsi], 0
0x1800068d6  jnz     short loc_1800068E9
0x1800068d8  xor     r8d, r8d; MiniIconIndex
0x1800068db  lea     rcx, [rsp+2090h+pclsid]; ClassGuid
0x1800068e0  mov     rdx, rsi; LargeIcon
0x1800068e3  call    cs:__imp_SetupDiLoadClassIcon
0x1800068e9  mov     rcx, rbx; InfHandle
0x1800068ec  call    cs:__imp_SetupCloseInfFile
0x1800068f2  mov     rax, rdi
0x1800068f5  mov     rcx, [rbp+1F90h+var_30]
0x1800068fc  xor     rcx, rsp; StackCookie
0x1800068ff  call    __security_check_cookie
0x180006904  mov     rbx, [rsp+2090h+arg_10]
0x18000690c  add     rsp, 2070h
0x180006913  pop     r15
0x180006915  pop     r14
0x180006917  pop     rdi
0x180006918  pop     rsi
0x180006919  pop     rbp
0x18000691a  retn
```
