# GetConfigDWORD(ushort const *,ulong,int,VERSION_ARCHITECTURE)

- ea: `0x180008f00`
- end: `0x180009022`
- name: `?GetConfigDWORD@@YAKPEBGKHW4VERSION_ARCHITECTURE@@@Z`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009af4`

## callees

- `0x180003070`
- `0x180004ed0`
- `0x1800067d0`
- `0x180008f00`
- `0x18000aea8`
- `0x18000b1c4`
- `0x18000d818`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180008fa5`
- `ADVAPI32!RegOpenKeyExW` at `0x180008fa5`
- `ADVAPI32!RegQueryValueExW` at `0x180008fd3`
- `ADVAPI32!RegQueryValueExW` at `0x180008fd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetConfigDWORD(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  const wchar_t *String; // rax
  unsigned int v6; // ebx
  REGSAM RegFlags; // eax
  PHKEY *v8; // r10
  __int64 v10; // [rsp+30h] [rbp-40h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-38h] BYREF
  int v12; // [rsp+40h] [rbp-30h]
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  int v14; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+58h] [rbp-18h] BYREF
  int v16; // [rsp+60h] [rbp-10h]
  DWORD Type; // [rsp+90h] [rbp+20h] BYREF
  int v18; // [rsp+94h] [rbp+24h]
  DWORD cbData; // [rsp+98h] [rbp+28h] BYREF
  unsigned int Data; // [rsp+A0h] [rbp+30h] BYREF

  v18 = HIDWORD(a1);
  v15 = 0;
  v16 = 0;
  hKey = 0;
  v14 = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v12 = 0;
  String = EnvGetString((wchar_t *)L"OnlyUseLatestCLR");
  v11 = String;
  if ( String && (v12 = 1, *String) )
  {
    v6 = wtol(String);
  }
  else
  {
    cbData = 4;
    BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
      &hKey,
      &v10);
    RegFlags = GetRegFlags(a4);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, RegFlags, *v8) )
      RegQueryValueExW(hKey, L"OnlyUseLatestCLR", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( *(_QWORD *)v10 )
      *(_DWORD *)(v10 + 8) = 1;
    v6 = Data;
  }
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v11);
  Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKey);
  Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&v15);
  return v6;
}

```

## disassembly

```asm
0x180008f00  mov     [rsp-18h+Data], r8d
0x180008f05  mov     [rsp-18h+cbData], edx
0x180008f09  mov     qword ptr [rsp-18h+Type], rcx
0x180008f0e  push    rbp
0x180008f0f  push    rbx
0x180008f10  push    rdi
0x180008f11  mov     rbp, rsp
0x180008f14  sub     rsp, 70h
0x180008f18  mov     ebx, r9d
0x180008f1b  xor     edi, edi
0x180008f1d  mov     [rbp+var_18], rdi
0x180008f21  mov     [rbp+var_10], edi
0x180008f24  mov     [rbp+hKey], rdi
0x180008f28  mov     [rbp+var_20], edi
0x180008f2b  mov     [rbp+Type], edi
0x180008f2e  mov     [rbp+cbData], edi
0x180008f31  mov     [rbp+Data], edi
0x180008f34  mov     [rbp+var_38], rdi
0x180008f38  mov     [rbp+var_30], edi
0x180008f3b  lea     rcx, aOnlyuselatestc; "OnlyUseLatestCLR"
0x180008f42  call    ?EnvGetString@@YAPEAGPEBG@Z; EnvGetString(ushort const *)
0x180008f47  mov     [rbp+var_38], rax
0x180008f4b  test    rax, rax
0x180008f4e  jz      short loc_180008F6B
0x180008f50  mov     [rbp+var_30], 1
0x180008f57  cmp     [rax], di
0x180008f5a  jz      short loc_180008F6B
0x180008f5c  mov     rcx, rax; String
0x180008f5f  call    _wtol
0x180008f64  mov     ebx, eax
0x180008f66  jmp     loc_180008FFB
0x180008f6b  mov     [rbp+cbData], 4
0x180008f72  lea     rdx, [rbp+var_40]
0x180008f76  lea     rcx, [rbp+hKey]
0x180008f7a  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x180008f7f  mov     r10, rax
0x180008f82  mov     ecx, ebx
0x180008f84  call    ?GetRegFlags@@YAKW4VERSION_ARCHITECTURE@@@Z; GetRegFlags(VERSION_ARCHITECTURE)
0x180008f89  mov     r9d, eax; samDesired
0x180008f8c  mov     rax, [r10]
0x180008f8f  mov     [rsp+70h+phkResult], rax; phkResult
0x180008f94  xor     r8d, r8d; ulOptions
0x180008f97  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x180008f9e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008fa5  call    cs:__imp_RegOpenKeyExW
0x180008fab  test    eax, eax
0x180008fad  jnz     short loc_180008FE5
0x180008faf  lea     rax, [rbp+cbData]
0x180008fb3  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180008fb8  lea     rax, [rbp+Data]
0x180008fbc  mov     [rsp+70h+phkResult], rax; lpData
0x180008fc1  lea     r9, [rbp+Type]; lpType
0x180008fc5  xor     r8d, r8d; lpReserved
0x180008fc8  lea     rdx, aOnlyuselatestc; "OnlyUseLatestCLR"
0x180008fcf  mov     rcx, [rbp+hKey]; hKey
0x180008fd3  call    cs:__imp_RegQueryValueExW
0x180008fd9  test    eax, eax
0x180008fdb  jnz     short loc_180008FE5
0x180008fdd  cmp     [rbp+Type], 4
0x180008fe1  mov     al, 1
0x180008fe3  jz      short loc_180008FE8
0x180008fe5  mov     al, dil
0x180008fe8  mov     rcx, [rbp+var_40]
0x180008fec  cmp     [rcx], rdi
0x180008fef  jz      short loc_180008FF8
0x180008ff1  mov     dword ptr [rcx+8], 1
0x180008ff8  mov     ebx, [rbp+Data]
0x180008ffb  lea     rcx, [rbp+var_38]
0x180008fff  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180009004  nop
0x180009005  lea     rcx, [rbp+hKey]
0x180009009  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000900e  nop
0x18000900f  lea     rcx, [rbp+var_18]
0x180009013  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x180009018  mov     eax, ebx
0x18000901a  add     rsp, 70h
0x18000901e  pop     rdi
0x18000901f  pop     rbx
0x180009020  pop     rbp
0x180009021  retn
```
