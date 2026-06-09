# FindServerUsingCLSID

- ea: `0x18000a884`
- end: `0x18000aa48`
- name: `FindServerUsingCLSID`
- size: `452`
- prototype: `__int64 __fastcall(struct _GUID *, BYTE **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a6a4`

## callees

- `0x180003740`
- `0x18000a884`
- `0x18000aea8`
- `0x18000b1c4`
- `0x18000c1a8`
- `0x18000d614`
- `0x180039620`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000a959`
- `ADVAPI32!RegOpenKeyExW` at `0x18000a959`
- `ADVAPI32!RegQueryValueExW` at `0x18000a9a1`
- `ADVAPI32!RegQueryValueExW` at `0x18000a9f7`
- `ADVAPI32!RegQueryValueExW` at `0x18000a9a1`
- `ADVAPI32!RegQueryValueExW` at `0x18000a9f7`

## string_xrefs

- `0x18000a8fa`: `CLSID\`

## pseudocode

```c
__int64 __fastcall FindServerUsingCLSID(struct _GUID *a1, BYTE **a2, unsigned int a3)
{
  struct _GUID v3; // xmm0
  int v5; // ebx
  PHKEY *v6; // rax
  LSTATUS v7; // eax
  unsigned __int128 v8; // rax
  BYTE *v9; // rax
  int v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h]
  struct _GUID v16; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Source[40]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = *a1;
  hKey = 0;
  v15 = 0;
  Type = 0;
  v16 = v3;
  cbData = 0;
  v5 = GuidToLPWSTR(&v16, Source, a3);
  if ( v5 >= 0 )
  {
    wcscpy_s(Destination, 0x80u, L"CLSID\\");
    wcscat_s(Destination, 0x80u, Source);
    wcscat_s(Destination, 0x80u, L"\\Server");
    v6 = (PHKEY *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                    &hKey,
                    &v16);
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, *v6);
    if ( **(_QWORD **)&v16.Data1 )
      *(_DWORD *)(*(_QWORD *)&v16.Data1 + 8LL) = 1;
    if ( v7 )
    {
      v5 = -2147221164;
    }
    else if ( !RegQueryValueExW(hKey, 0, 0, &Type, 0, &cbData) && Type == 1 && cbData )
    {
      v8 = (cbData + 1) * (unsigned __int128)2uLL;
      if ( !is_mul_ok(cbData + 1, 2u) )
        *(_QWORD *)&v8 = -1;
      v9 = (BYTE *)operator new(v8, *((const struct NoThrow **)&v8 + 1));
      *a2 = v9;
      v10 = RegQueryValueExW(hKey, 0, 0, 0, v9, &cbData);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        v5 = v10;
      }
      else
      {
        v5 = 0;
      }
    }
    else
    {
      v5 = -2147221166;
    }
  }
  Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000a884  mov     [rsp-8+arg_0], rbx
0x18000a889  mov     [rsp-8+arg_10], rdi
0x18000a88e  push    rbp
0x18000a88f  lea     rbp, [rsp-0C0h]
0x18000a897  sub     rsp, 1C0h
0x18000a89e  mov     rax, cs:__security_cookie
0x18000a8a5  xor     rax, rsp
0x18000a8a8  mov     [rbp+0C0h+var_10], rax
0x18000a8af  movups  xmm0, xmmword ptr [rcx]
0x18000a8b2  mov     rdi, rdx
0x18000a8b5  mov     [rsp+1C0h+hKey], 0
0x18000a8be  lea     rdx, [rsp+1C0h+Source]; unsigned __int16 *
0x18000a8c3  mov     [rsp+1C0h+var_180], 0
0x18000a8cb  lea     rcx, [rsp+1C0h+var_170]; struct _GUID
0x18000a8d0  mov     [rsp+1C0h+Type], 0
0x18000a8d8  movdqu  xmmword ptr [rsp+1C0h+var_170.Data1], xmm0
0x18000a8de  mov     [rsp+1C0h+cbData], 0
0x18000a8e6  call    ?GuidToLPWSTR@@YAHU_GUID@@PEAGK@Z; GuidToLPWSTR(_GUID,ushort *,ulong)
0x18000a8eb  mov     ebx, eax
0x18000a8ed  test    eax, eax
0x18000a8ef  js      loc_18000AA18
0x18000a8f5  mov     ebx, 80h
0x18000a8fa  lea     r8, aClsid; "CLSID\\"
0x18000a901  mov     edx, ebx; SizeInWords
0x18000a903  lea     rcx, [rbp+0C0h+Destination]; Destination
0x18000a907  call    wcscpy_s
0x18000a90c  lea     r8, [rsp+1C0h+Source]; Source
0x18000a911  mov     edx, ebx; SizeInWords
0x18000a913  lea     rcx, [rbp+0C0h+Destination]; Destination
0x18000a917  call    wcscat_s
0x18000a91c  lea     r8, aServer; "\\Server"
0x18000a923  mov     edx, ebx; SizeInWords
0x18000a925  lea     rcx, [rbp+0C0h+Destination]; Destination
0x18000a929  call    wcscat_s
0x18000a92e  lea     rdx, [rsp+1C0h+var_170]
0x18000a933  lea     rcx, [rsp+1C0h+hKey]
0x18000a938  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x18000a93d  mov     r9d, 20019h; samDesired
0x18000a943  lea     rdx, [rbp+0C0h+Destination]; lpSubKey
0x18000a947  xor     r8d, r8d; ulOptions
0x18000a94a  mov     rcx, [rax]
0x18000a94d  mov     [rsp+1C0h+phkResult], rcx; phkResult
0x18000a952  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000a959  call    cs:__imp_RegOpenKeyExW
0x18000a95f  mov     rcx, qword ptr [rsp+1C0h+var_170.Data1]
0x18000a964  cmp     qword ptr [rcx], 0
0x18000a968  jz      short loc_18000A971
0x18000a96a  mov     dword ptr [rcx+8], 1
0x18000a971  test    eax, eax
0x18000a973  jz      short loc_18000A97F
0x18000a975  mov     ebx, 80040154h
0x18000a97a  jmp     loc_18000AA18
0x18000a97f  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000a984  lea     rax, [rsp+1C0h+cbData]
0x18000a989  mov     [rsp+1C0h+lpcbData], rax; lpcbData
0x18000a98e  lea     r9, [rsp+1C0h+Type]; lpType
0x18000a993  xor     r8d, r8d; lpReserved
0x18000a996  mov     [rsp+1C0h+phkResult], 0; lpData
0x18000a99f  xor     edx, edx; lpValueName
0x18000a9a1  call    cs:__imp_RegQueryValueExW
0x18000a9a7  test    eax, eax
0x18000a9a9  jnz     short loc_18000AA13
0x18000a9ab  cmp     [rsp+1C0h+Type], 1
0x18000a9b0  jnz     short loc_18000AA13
0x18000a9b2  mov     eax, [rsp+1C0h+cbData]
0x18000a9b6  test    eax, eax
0x18000a9b8  jz      short loc_18000AA13
0x18000a9ba  lea     ecx, [rax+1]
0x18000a9bd  mov     eax, 2
0x18000a9c2  mul     rcx
0x18000a9c5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a9cc  cmovb   rax, rcx
0x18000a9d0  mov     rcx, rax; unsigned __int64
0x18000a9d3  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18000a9d8  lea     rcx, [rsp+1C0h+cbData]
0x18000a9dd  mov     [rdi], rax
0x18000a9e0  mov     [rsp+1C0h+lpcbData], rcx; lpcbData
0x18000a9e5  xor     r9d, r9d; lpType
0x18000a9e8  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000a9ed  xor     r8d, r8d; lpReserved
0x18000a9f0  xor     edx, edx; lpValueName
0x18000a9f2  mov     [rsp+1C0h+phkResult], rax; lpData
0x18000a9f7  call    cs:__imp_RegQueryValueExW
0x18000a9fd  test    eax, eax
0x18000a9ff  jz      short loc_18000AA0F
0x18000aa01  jle     short loc_18000AA0B
0x18000aa03  movzx   eax, ax
0x18000aa06  or      eax, 80070000h
0x18000aa0b  mov     ebx, eax
0x18000aa0d  jmp     short loc_18000AA18
0x18000aa0f  xor     ebx, ebx
0x18000aa11  jmp     short loc_18000AA18
0x18000aa13  mov     ebx, 80040152h
0x18000aa18  lea     rcx, [rsp+1C0h+hKey]
0x18000aa1d  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x18000aa22  mov     eax, ebx
0x18000aa24  mov     rcx, [rbp+0C0h+var_10]
0x18000aa2b  xor     rcx, rsp; StackCookie
0x18000aa2e  call    __security_check_cookie
0x18000aa33  lea     r11, [rsp+1C0h+var_s0]
0x18000aa3b  mov     rbx, [r11+10h]
0x18000aa3f  mov     rdi, [r11+20h]
0x18000aa43  mov     rsp, r11
0x18000aa46  pop     rbp
0x18000aa47  retn
```
