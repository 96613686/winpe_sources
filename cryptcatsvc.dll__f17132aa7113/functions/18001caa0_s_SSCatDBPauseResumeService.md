# s_SSCatDBPauseResumeService

- ea: `0x18001caa0`
- end: `0x18001cb3f`
- name: `s_SSCatDBPauseResumeService`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000a57c`
- `0x18000a59c`
- `0x180019a7c`
- `0x18001c6b4`
- `0x18001caa0`
- `0x18001cf60`
- `0x18001f748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cab6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cad8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cab6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cad8`

## string_xrefs

- `0x18001cb21`: `PauseResumeService():: ERROR_ACCESS_DENIED`

## pseudocode

```c
__int64 __fastcall s_SSCatDBPauseResumeService(void *a1, int a2)
{
  unsigned int v3; // edx
  unsigned __int16 *v4; // rcx
  unsigned int v5; // r8d
  DWORD v6; // eax
  unsigned int Error; // ebx
  int v8; // eax
  int v10; // [rsp+28h] [rbp-10h]

  if ( !a1 )
  {
    SetLastError(0xA0u);
    v5 = 3809;
    goto LABEL_10;
  }
  v6 = _CatDBCanWriteToPathWithImpersonation(a1, g_pwszCatalogFileBaseDirectory);
  Error = v6;
  if ( v6 )
  {
    SetLastError(v6);
    v5 = 3816;
    goto LABEL_10;
  }
  if ( a2 )
    v8 = CatDBThawJet(1);
  else
    v8 = CatDBFreezeJet(1);
  if ( !v8 )
  {
    v5 = 3830;
LABEL_10:
    ErrLog_LogError(v4, v3, v5, 0, 0, v10);
    Error = _CatDBGetNonzeroLastError();
    if ( Error == 5 )
      ErrLog_LogPrintfW(0, 1, L"PauseResumeService():: ERROR_ACCESS_DENIED");
  }
  return Error;
}

```

## disassembly

```asm
0x18001caa0  mov     [rsp+arg_0], rbx
0x18001caa5  push    rdi
0x18001caa6  sub     rsp, 30h
0x18001caaa  mov     edi, edx
0x18001caac  test    rcx, rcx
0x18001caaf  jnz     short loc_18001CAC4
0x18001cab1  mov     ecx, 0A0h; dwErrCode
0x18001cab6  call    cs:__imp_SetLastError
0x18001cabc  mov     r8d, 0EE1h
0x18001cac2  jmp     short loc_18001CB05
0x18001cac4  mov     rdx, cs:?g_pwszCatalogFileBaseDirectory@@3PEAGEA; lpFileName
0x18001cacb  call    ?_CatDBCanWriteToPathWithImpersonation@@YAKPEAXPEBG@Z; _CatDBCanWriteToPathWithImpersonation(void *,ushort const *)
0x18001cad0  mov     ebx, eax
0x18001cad2  test    eax, eax
0x18001cad4  jz      short loc_18001CAE6
0x18001cad6  mov     ecx, eax; dwErrCode
0x18001cad8  call    cs:__imp_SetLastError
0x18001cade  mov     r8d, 0EE8h
0x18001cae4  jmp     short loc_18001CB05
0x18001cae6  mov     ecx, 1; int
0x18001caeb  test    edi, edi
0x18001caed  jz      short loc_18001CAF6
0x18001caef  call    _CatDBThawJet
0x18001caf4  jmp     short loc_18001CAFB
0x18001caf6  call    _CatDBFreezeJet
0x18001cafb  test    eax, eax
0x18001cafd  jnz     short loc_18001CB32
0x18001caff  mov     r8d, 0EF6h; unsigned int
0x18001cb05  xor     r9d, r9d; unsigned int
0x18001cb08  mov     [rsp+38h+var_18], 0; int
0x18001cb10  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001cb15  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18001cb1a  mov     ebx, eax
0x18001cb1c  cmp     eax, 5
0x18001cb1f  jnz     short loc_18001CB32
0x18001cb21  lea     r8, aPauseresumeser; "PauseResumeService():: ERROR_ACCESS_DEN"...
0x18001cb28  xor     ecx, ecx; unsigned __int16 *
0x18001cb2a  lea     edx, [rax-4]; int
0x18001cb2d  call    ?ErrLog_LogPrintfW@@YAXPEAGHPEBGZZ; ErrLog_LogPrintfW(ushort *,int,ushort const *,...)
0x18001cb32  mov     eax, ebx
0x18001cb34  mov     rbx, [rsp+38h+arg_0]
0x18001cb39  add     rsp, 30h
0x18001cb3d  pop     rdi
0x18001cb3e  retn
```
