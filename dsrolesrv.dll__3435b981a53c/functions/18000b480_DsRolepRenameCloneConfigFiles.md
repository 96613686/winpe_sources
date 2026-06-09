# DsRolepRenameCloneConfigFiles

- ea: `0x18000b480`
- end: `0x18000b624`
- name: `DsRolepRenameCloneConfigFiles`
- size: `420`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b1c8`

## callees

- `0x18000b480`
- `0x18001e204`
- `0x180020dbc`
- `0x18002303c`
- `0x180023428`
- `0x180023468`
- `0x1800236a4`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000b540`
- `ntdll!RtlInitUnicodeString` at `0x18000b550`
- `ntdll!RtlInitUnicodeString` at `0x18000b5b2`
- `ntdll!RtlInitUnicodeString` at `0x18000b540`
- `ntdll!RtlInitUnicodeString` at `0x18000b550`
- `ntdll!RtlInitUnicodeString` at `0x18000b5b2`

## string_xrefs

- `0x18000b4d3`: `DCCloneConfig.xml`
- `0x18000b573`: `vDC Cloning: Renamed vDC clone configuration file.\n`
- `0x18000b5dc`: `vDC Cloning: Renaming vDC clone configuration file %ws failed with error code: %lu\n`

## pseudocode

```c
__int64 DsRolepRenameCloneConfigFiles()
{
  __int64 v0; // rbx
  __int64 v1; // rsi
  unsigned int v2; // r14d
  __int64 v4; // [rsp+20h] [rbp-E0h]
  int v5; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v6; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v8; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SourceString[264]; // [rsp+70h] [rbp-90h] BYREF

  v5 = 0;
  v6 = 0;
  if ( !(unsigned int)InitVdcFileNameList(&v6) )
  {
    GetVdcConfigFiles(&v6, L"DCCloneConfig.xml", 0xFFFFFFFFLL, &v5);
    if ( v5 )
    {
      v0 = 0;
      if ( HIDWORD(v6) )
      {
        v1 = v6;
        do
        {
          memset_0(SourceString, 0, 0x20Au);
          v2 = RenameFileByInsertingCurrentTime(*(LPCWSTR *)(v1 + 8 * v0), SourceString);
          DestinationString = 0;
          if ( v2 )
          {
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v1 + 8 * v0));
            LODWORD(v4) = v2;
            DsRolepEventWrite(DSROLERES_VDC_CLONE_FAILED_RENAME_CONFIG_FILE_EVENT, L"ude", &DestinationString, v2);
            DsRolepLogPrintRoutine(
              1,
              "vDC Cloning: Renaming vDC clone configuration file %ws failed with error code: %lu\n",
              *(_QWORD *)(v1 + 8 * v0),
              v2,
              v4);
          }
          else
          {
            v8 = 0;
            RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v1 + 8 * v0));
            RtlInitUnicodeString(&v8, SourceString);
            DsRolepEventWrite(DSROLERES_VDC_CLONE_RENAMED_CONFIG_FILE_EVENT, L"uu", &DestinationString, &v8);
            DsRolepLogPrintRoutine(4, "vDC Cloning: Renamed vDC clone configuration file.\n");
            DsRolepLogPrintRoutine(4, "vDC Cloning: The old name is: %ws\n", *(_QWORD *)(v1 + 8 * v0));
            DsRolepLogPrintRoutine(4, "vDC Cloning: The new name is: %ws\n", SourceString);
          }
          v0 = (unsigned int)(v0 + 1);
        }
        while ( (unsigned int)v0 < HIDWORD(v6) );
      }
    }
  }
  return UnInitVdcFileNameList(&v6);
}

```

## disassembly

```asm
0x18000b480  push    rbp
0x18000b482  push    rbx
0x18000b483  push    rsi
0x18000b484  push    r14
0x18000b486  push    r15
0x18000b488  lea     rbp, [rsp-190h]
0x18000b490  sub     rsp, 290h
0x18000b497  mov     rax, cs:__security_cookie
0x18000b49e  xor     rax, rsp
0x18000b4a1  mov     [rbp+1B0h+var_30], rax
0x18000b4a8  xorps   xmm0, xmm0
0x18000b4ab  mov     [rsp+2B0h+var_280], 0
0x18000b4b3  lea     rcx, [rsp+2B0h+var_278]
0x18000b4b8  movups  [rsp+2B0h+var_278], xmm0
0x18000b4bd  call    InitVdcFileNameList
0x18000b4c2  test    eax, eax
0x18000b4c4  jnz     loc_18000B5FC
0x18000b4ca  lea     r9, [rsp+2B0h+var_280]
0x18000b4cf  or      r8d, 0FFFFFFFFh
0x18000b4d3  lea     rdx, aDccloneconfigX; "DCCloneConfig.xml"
0x18000b4da  lea     rcx, [rsp+2B0h+var_278]
0x18000b4df  call    GetVdcConfigFiles
0x18000b4e4  cmp     [rsp+2B0h+var_280], 0
0x18000b4e9  jz      loc_18000B5FC
0x18000b4ef  xor     ebx, ebx
0x18000b4f1  cmp     dword ptr [rsp+2B0h+var_278+0Ch], ebx
0x18000b4f5  jbe     loc_18000B5FC
0x18000b4fb  mov     rsi, qword ptr [rsp+2B0h+var_278]
0x18000b500  xor     edx, edx; Val
0x18000b502  lea     rcx, [rsp+2B0h+SourceString]; void *
0x18000b507  mov     r8d, 20Ah; Size
0x18000b50d  call    memset_0
0x18000b512  mov     rcx, [rsi+rbx*8]; lpExistingFileName
0x18000b516  lea     rdx, [rsp+2B0h+SourceString]; lpNewFileName
0x18000b51b  call    RenameFileByInsertingCurrentTime
0x18000b520  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18000b525  xorps   xmm0, xmm0
0x18000b528  mov     r14d, eax
0x18000b52b  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18000b530  test    eax, eax
0x18000b532  jnz     short loc_18000B5AE
0x18000b534  xorps   xmm1, xmm1
0x18000b537  movups  xmmword ptr [rsp+2B0h+var_258.Length], xmm1
0x18000b53c  mov     rdx, [rsi+rbx*8]; SourceString
0x18000b540  call    cs:__imp_RtlInitUnicodeString
0x18000b546  lea     rdx, [rsp+2B0h+SourceString]; SourceString
0x18000b54b  lea     rcx, [rsp+2B0h+var_258]; DestinationString
0x18000b550  call    cs:__imp_RtlInitUnicodeString
0x18000b556  lea     r9, [rsp+2B0h+var_258]
0x18000b55b  lea     r8, [rsp+2B0h+DestinationString]
0x18000b560  lea     rdx, aUu; "uu"
0x18000b567  lea     rcx, DSROLERES_VDC_CLONE_RENAMED_CONFIG_FILE_EVENT
0x18000b56e  call    DsRolepEventWrite
0x18000b573  lea     rdx, aVdcCloningRena; "vDC Cloning: Renamed vDC clone configur"...
0x18000b57a  lea     ecx, [r14+4]
0x18000b57e  call    DsRolepLogPrintRoutine
0x18000b583  mov     r8, [rsi+rbx*8]
0x18000b587  lea     rdx, aVdcCloningTheO; "vDC Cloning: The old name is: %ws\n"
0x18000b58e  lea     ecx, [r14+4]
0x18000b592  call    DsRolepLogPrintRoutine
0x18000b597  lea     r8, [rsp+2B0h+SourceString]
0x18000b59c  lea     rdx, aVdcCloningTheN; "vDC Cloning: The new name is: %ws\n"
0x18000b5a3  lea     ecx, [r14+4]
0x18000b5a7  call    DsRolepLogPrintRoutine
0x18000b5ac  jmp     short loc_18000B5F0
0x18000b5ae  mov     rdx, [rsi+rbx*8]; SourceString
0x18000b5b2  call    cs:__imp_RtlInitUnicodeString
0x18000b5b8  mov     r9d, r14d
0x18000b5bb  mov     [rsp+2B0h+var_290], r14d
0x18000b5c0  lea     r8, [rsp+2B0h+DestinationString]
0x18000b5c5  lea     rdx, aUde; "ude"
0x18000b5cc  lea     rcx, DSROLERES_VDC_CLONE_FAILED_RENAME_CONFIG_FILE_EVENT
0x18000b5d3  call    DsRolepEventWrite
0x18000b5d8  mov     r8, [rsi+rbx*8]
0x18000b5dc  lea     rdx, aVdcCloningRena_0; "vDC Cloning: Renaming vDC clone configu"...
0x18000b5e3  mov     r9d, r14d
0x18000b5e6  mov     ecx, 1
0x18000b5eb  call    DsRolepLogPrintRoutine
0x18000b5f0  inc     ebx
0x18000b5f2  cmp     ebx, dword ptr [rsp+2B0h+var_278+0Ch]
0x18000b5f6  jb      loc_18000B500
0x18000b5fc  lea     rcx, [rsp+2B0h+var_278]
0x18000b601  call    UnInitVdcFileNameList
0x18000b606  mov     rcx, [rbp+1B0h+var_30]
0x18000b60d  xor     rcx, rsp; StackCookie
0x18000b610  call    __security_check_cookie
0x18000b615  add     rsp, 290h
0x18000b61c  pop     r15
0x18000b61e  pop     r14
0x18000b620  pop     rsi
0x18000b621  pop     rbx
0x18000b622  pop     rbp
0x18000b623  retn
```
