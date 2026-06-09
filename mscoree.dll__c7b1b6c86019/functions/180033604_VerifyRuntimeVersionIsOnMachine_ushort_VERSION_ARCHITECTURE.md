# VerifyRuntimeVersionIsOnMachine(ushort *,VERSION_ARCHITECTURE)

- ea: `0x180033604`
- end: `0x180033785`
- name: `?VerifyRuntimeVersionIsOnMachine@@YAJPEAGW4VERSION_ARCHITECTURE@@@Z`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000af8c`

## callees

- `0x180003070`
- `0x180003ed0`
- `0x18000b1f0`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000d838`
- `0x180033604`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetFileAttributesExW` at `0x18003371d`
- `KERNEL32!GetFileAttributesExW` at `0x18003371d`

## string_xrefs

- `0x18003363d`: `InstallRoot`
- `0x18003372c`: `Shim database version %s doesn't have a matching runtime directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VerifyRuntimeVersionIsOnMachine(const wchar_t *a1, int a2)
{
  WCHAR *ConfigString; // rax
  WCHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  __int64 v6; // rbx
  wchar_t *v7; // rax
  unsigned int v8; // ebx
  WCHAR *v10; // [rsp+20h] [rbp-E0h] BYREF
  BOOL v11; // [rsp+28h] [rbp-D8h]
  _OWORD FileInformation[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+50h] [rbp-B0h]
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF

  ConfigString = GetConfigString(L"InstallRoot", 1, a2);
  v4 = ConfigString;
  v10 = ConfigString;
  v11 = ConfigString != 0;
  if ( !ConfigString )
    goto LABEL_14;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( ConfigString[v6] );
  do
    ++v5;
  while ( a1[v5] );
  if ( ~v6 < v5 || v5 + v6 + 1 > 0x104 )
    goto LABEL_14;
  wcscpy_s(Destination, 0x105u, ConfigString);
  if ( v4[v6 - 1] != 92 )
    wcscat_s(Destination, 0x105u, L"\\");
  wcscat_s(Destination, 0x105u, a1);
  v7 = wcsrchr(Destination, 0x2Eu);
  if ( v7 )
  {
    *v7 = 0;
    memset(FileInformation, 0, sizeof(FileInformation));
    v13 = 0;
    if ( GetFileAttributesExW(Destination, GetFileExInfoStandard, FileInformation) )
    {
      v8 = 0;
    }
    else
    {
      ReportAppCompatError(
        (wchar_t *)L"Shim database version %s doesn't have a matching runtime directory",
        Destination);
      v8 = -2147467259;
    }
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v10);
    return v8;
  }
  else
  {
LABEL_14:
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v10);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180033604  mov     [rsp-8+arg_10], rbx
0x180033609  push    rbp
0x18003360a  push    rsi
0x18003360b  push    rdi
0x18003360c  push    r14
0x18003360e  push    r15
0x180033610  lea     rbp, [rsp-180h]
0x180033618  sub     rsp, 280h
0x18003361f  mov     rax, cs:__security_cookie
0x180033626  xor     rax, rsp
0x180033629  mov     [rbp+1A0h+var_30], rax
0x180033630  mov     rsi, rcx
0x180033633  mov     r8d, edx
0x180033636  mov     ebx, 1
0x18003363b  mov     edx, ebx
0x18003363d  lea     rcx, aInstallroot; "InstallRoot"
0x180033644  call    ?GetConfigString@@YAPEAGPEBGHW4VERSION_ARCHITECTURE@@@Z; GetConfigString(ushort const *,int,VERSION_ARCHITECTURE)
0x180033649  mov     rdi, rax
0x18003364c  mov     [rsp+2A0h+var_280], rax
0x180033651  xor     r14d, r14d
0x180033654  mov     ecx, r14d
0x180033657  test    rax, rax
0x18003365a  cmovnz  ecx, ebx
0x18003365d  mov     [rsp+2A0h+var_278], ecx
0x180033661  jz      loc_180033750
0x180033667  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003366b  mov     rbx, rcx
0x18003366e  inc     rbx
0x180033671  cmp     [rax+rbx*2], r14w
0x180033676  jnz     short loc_18003366E
0x180033678  inc     rcx
0x18003367b  cmp     [rsi+rcx*2], r14w
0x180033680  jnz     short loc_180033678
0x180033682  mov     rax, rbx
0x180033685  not     rax
0x180033688  cmp     rax, rcx
0x18003368b  jb      loc_180033750
0x180033691  lea     rax, [rbx+1]
0x180033695  add     rax, rcx
0x180033698  cmp     rax, 104h
0x18003369e  ja      loc_180033750
0x1800336a4  mov     r8, rdi; Source
0x1800336a7  mov     r15d, 105h
0x1800336ad  mov     edx, r15d; SizeInWords
0x1800336b0  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800336b5  call    wcscpy_s
0x1800336ba  cmp     word ptr [rdi+rbx*2-2], 5Ch ; '\'
0x1800336c0  jz      short loc_1800336D6
0x1800336c2  lea     r8, asc_18004C8C0; "\\"
0x1800336c9  mov     edx, r15d; SizeInWords
0x1800336cc  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800336d1  call    wcscat_s
0x1800336d6  mov     r8, rsi; Source
0x1800336d9  mov     rdx, r15; SizeInWords
0x1800336dc  lea     rcx, [rsp+2A0h+Destination]; Destination
0x1800336e1  call    wcscat_s
0x1800336e6  mov     edx, 2Eh ; '.'; Ch
0x1800336eb  lea     rcx, [rsp+2A0h+Destination]; Str
0x1800336f0  call    wcsrchr
0x1800336f5  test    rax, rax
0x1800336f8  jz      short loc_180033750
0x1800336fa  mov     [rax], r14w
0x1800336fe  xorps   xmm0, xmm0
0x180033701  xor     eax, eax
0x180033703  movups  [rsp+2A0h+FileInformation], xmm0
0x180033708  movups  [rsp+2A0h+var_260], xmm0
0x18003370d  mov     [rsp+2A0h+var_250], eax
0x180033711  lea     r8, [rsp+2A0h+FileInformation]; lpFileInformation
0x180033716  xor     edx, edx; fInfoLevelId
0x180033718  lea     rcx, [rsp+2A0h+Destination]; lpFileName
0x18003371d  call    cs:__imp_GetFileAttributesExW
0x180033723  test    eax, eax
0x180033725  jnz     short loc_18003373F
0x180033727  lea     rdx, [rsp+2A0h+Destination]
0x18003372c  lea     rcx, aShimDatabaseVe; "Shim database version %s doesn't have a"...
0x180033733  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180033738  mov     ebx, 80004005h
0x18003373d  jmp     short loc_180033742
0x18003373f  mov     ebx, r14d
0x180033742  lea     rcx, [rsp+2A0h+var_280]
0x180033747  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18003374c  mov     eax, ebx
0x18003374e  jmp     short loc_18003375F
0x180033750  lea     rcx, [rsp+2A0h+var_280]
0x180033755  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18003375a  mov     eax, 80004005h
0x18003375f  mov     rcx, [rbp+1A0h+var_30]
0x180033766  xor     rcx, rsp; StackCookie
0x180033769  call    __security_check_cookie
0x18003376e  mov     rbx, [rsp+2A0h+arg_10]
0x180033776  add     rsp, 280h
0x18003377d  pop     r15
0x18003377f  pop     r14
0x180033781  pop     rdi
0x180033782  pop     rsi
0x180033783  pop     rbp
0x180033784  retn
```
