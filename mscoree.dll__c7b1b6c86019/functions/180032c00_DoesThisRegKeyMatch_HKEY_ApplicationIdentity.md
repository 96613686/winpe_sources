# DoesThisRegKeyMatch(HKEY__ *,ApplicationIdentity *)

- ea: `0x180032c00`
- end: `0x18003303a`
- name: `?DoesThisRegKeyMatch@@YAHPEAUHKEY__@@PEAVApplicationIdentity@@@Z`
- size: `1082`
- prototype: `__int64 __fastcall(HKEY hKey, struct ApplicationIdentity *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003070`
- `0x180003840`
- `0x18000abd0`
- `0x18000aea8`
- `0x18000b1c4`
- `0x18000b1f0`
- `0x18000d8f0`
- `0x1800325b8`
- `0x180032c00`
- `0x180033040`
- `0x180033274`
- `0x180033304`
- `0x1800335d8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180032e2f`
- `ADVAPI32!RegQueryValueExW` at `0x180032e2f`

## string_xrefs

- `0x180032cb3`: `Invalid registry presence value for %s - %d`
- `0x180032dfe`: `Invalid registry presence value for %s - %d`
- `0x180032d0f`: `Invalid registry key! - %s`
- `0x180032e97`: `Related registry key for %s does not have a value type entry!`
- `0x180032feb`: `Unknown registry value type - %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_BOOL8 __fastcall DoesThisRegKeyMatch(HKEY hKey, struct ApplicationIdentity *a2)
{
  int RegistryStringValue; // eax
  int v5; // ecx
  BOOL v6; // edi
  int RegistryDWordValue; // eax
  __int64 *v9; // rax
  LSTATUS RegistryKey; // eax
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  unsigned int v14; // edx
  BOOL v15; // ebx
  LSTATUS Value; // eax
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // ecx
  HKEY v23; // rax
  int v24; // ecx
  int v25; // r8d
  unsigned __int16 *p_lpValueName; // [rsp+30h] [rbp-39h] BYREF
  int v27; // [rsp+38h] [rbp-31h]
  LPCWSTR lpValueName; // [rsp+40h] [rbp-29h] BYREF
  int v29; // [rsp+48h] [rbp-21h]
  wchar_t *String2; // [rsp+50h] [rbp-19h] BYREF
  int v31; // [rsp+58h] [rbp-11h]
  HKEY v32; // [rsp+60h] [rbp-9h] BYREF
  int v33; // [rsp+68h] [rbp-1h]
  unsigned int v34; // [rsp+70h] [rbp+7h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp+Fh] BYREF
  wchar_t *v36; // [rsp+80h] [rbp+17h] BYREF
  int v37; // [rsp+88h] [rbp+1Fh]
  HKEY hKeya; // [rsp+90h] [rbp+27h] BYREF
  int v39; // [rsp+98h] [rbp+2Fh]
  void *p_String2; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v41; // [rsp+E8h] [rbp+7Fh] BYREF

  v36 = 0;
  v37 = 0;
  lpValueName = 0;
  v29 = 0;
  String2 = 0;
  v31 = 0;
  hKeya = 0;
  v39 = 0;
  v41 = 999;
  v34 = 999;
  LODWORD(p_String2) = 0;
  p_lpValueName = (unsigned __int16 *)&v36;
  RegistryStringValue = GetRegistryStringValue(hKey, L"Key Name", (BYTE **)&v36);
  v5 = v37;
  v6 = 1;
  if ( v36 )
    v5 = 1;
  v37 = v5;
  if ( RegistryStringValue )
    goto LABEL_51;
  RegistryDWordValue = GetRegistryDWordValue(hKey, L"Key Presence", &v41);
  if ( RegistryDWordValue < 0 )
    goto LABEL_51;
  if ( !RegistryDWordValue && (int)CheckPresenceValue(v41) < 0 )
  {
    ReportAppCompatError((wchar_t *)L"Invalid registry presence value for %s - %d", *((_QWORD *)a2 + 1));
    Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKeya);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&String2);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&lpValueName);
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v36);
    return 0;
  }
  v32 = 0;
  v35 = 0;
  if ( (int)ExtractRegKeyInfo(v36, &v32, &v35) < 0 )
  {
    ReportAppCompatError(L"Invalid registry key! - %s", v36);
    goto LABEL_51;
  }
  v9 = (__int64 *)BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
                    &hKeya,
                    &p_lpValueName);
  RegistryKey = GetRegistryKey(v32, (__int64)v35, *v9, 0);
  if ( *(_QWORD *)p_lpValueName )
    *((_DWORD *)p_lpValueName + 2) = 1;
  if ( RegistryKey < 0 )
    goto LABEL_51;
  if ( (unsigned int)ShouldReturnNowFromKeyExistence(RegistryKey == 0, v41 != 0, (int *)&p_String2) )
    goto LABEL_14;
  p_lpValueName = (unsigned __int16 *)&lpValueName;
  if ( v29 )
  {
    operator delete((void *)lpValueName);
    v29 = 0;
  }
  v11 = GetRegistryStringValue(hKey, L"Value Name", (BYTE **)&lpValueName);
  v12 = v29;
  if ( lpValueName )
    v12 = 1;
  v29 = v12;
  if ( v11 < 0 )
    goto LABEL_51;
  if ( v11 != 1 )
  {
    v13 = GetRegistryDWordValue(hKey, L"Value Presence", &v34);
    if ( v13 < 0 )
      goto LABEL_51;
    v14 = v34;
    if ( !v13 && (int)CheckPresenceValue(v34) < 0 )
    {
      ReportAppCompatError((wchar_t *)L"Invalid registry presence value for %s - %d", *((_QWORD *)a2 + 1), v14);
      goto LABEL_51;
    }
    v15 = v14 != 0;
    Value = RegQueryValueExW(hKeya, lpValueName, 0, 0, 0, 0);
    if ( (unsigned int)ShouldReturnNowFromKeyExistence(Value == 0, v15, (int *)&p_String2) )
    {
LABEL_14:
      v6 = (int)p_String2;
      goto LABEL_52;
    }
    p_String2 = &String2;
    if ( v31 )
    {
      operator delete(String2);
      v31 = 0;
    }
    v17 = GetRegistryStringValue(hKey, L"Value Type", (BYTE **)&String2);
    v18 = v31;
    if ( String2 )
      v18 = 1;
    v31 = v18;
    if ( v17 )
    {
      ReportAppCompatError(L"Related registry key for %s does not have a value type entry!", *((_QWORD *)a2 + 1));
      goto LABEL_51;
    }
    if ( wcsicmp(L"DWORD", String2) )
    {
      if ( wcsicmp(L"String", String2) )
      {
        ReportAppCompatError((wchar_t *)L"Unknown registry value type - %s", String2);
      }
      else
      {
        v32 = 0;
        v33 = 0;
        p_lpValueName = 0;
        v27 = 0;
        p_String2 = &v32;
        v19 = GetRegistryStringValue(hKey, L"Value Value", (BYTE **)&v32);
        v20 = v33;
        if ( v32 )
          v20 = 1;
        v33 = v20;
        if ( !v19 )
        {
          p_String2 = &p_lpValueName;
          if ( v27 )
          {
            operator delete(p_lpValueName);
            v27 = 0;
          }
          v21 = GetRegistryStringValue(hKeya, lpValueName, (BYTE **)&p_lpValueName);
          v22 = v27;
          if ( p_lpValueName )
            v22 = 1;
          v27 = v22;
          if ( !v21 )
          {
            v23 = v32;
            do
            {
              v24 = *(unsigned __int16 *)((char *)v23 + (char *)p_lpValueName - (char *)v32);
              v25 = *(_WORD *)v23 - v24;
              if ( v25 )
                break;
              v23 = (HKEY)((char *)v23 + 2);
            }
            while ( v24 );
            v6 = v25 == 0;
            Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&p_lpValueName);
            Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v32);
            goto LABEL_52;
          }
        }
        Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&p_lpValueName);
        Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v32);
      }
      goto LABEL_51;
    }
    LODWORD(v35) = 0;
    LODWORD(p_String2) = 0;
    if ( (int)GetRegistryDWordValue(hKeya, (unsigned __int16 *)lpValueName, (unsigned int *)&v35) < 0
      || (unsigned int)GetRegistryDWordValue(hKey, L"Value Value", (unsigned int *)&p_String2) )
    {
LABEL_51:
      v6 = 0;
      goto LABEL_52;
    }
    v6 = (_DWORD)v35 == (_DWORD)p_String2;
  }
LABEL_52:
  Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(&hKeya);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&String2);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&lpValueName);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v36);
  return v6;
}

```

## disassembly

```asm
0x180032c00  mov     [rsp-8+arg_0], rbx
0x180032c05  push    rbp
0x180032c06  push    rsi
0x180032c07  push    rdi
0x180032c08  push    r14
0x180032c0a  push    r15
0x180032c0c  lea     rbp, [rsp-37h]
0x180032c11  sub     rsp, 0A0h
0x180032c18  mov     r14, rdx
0x180032c1b  mov     rsi, rcx
0x180032c1e  xor     r15d, r15d
0x180032c21  mov     [rbp+57h+var_40], r15
0x180032c25  mov     [rbp+57h+var_38], r15d
0x180032c29  mov     [rbp+57h+lpValueName], r15
0x180032c2d  mov     [rbp+57h+var_78], r15d
0x180032c31  mov     [rbp+57h+String2], r15
0x180032c35  mov     [rbp+57h+var_68], r15d
0x180032c39  mov     [rbp+57h+hKey], r15
0x180032c3d  mov     [rbp+57h+var_28], r15d
0x180032c41  mov     eax, 3E7h
0x180032c46  mov     [rbp+57h+arg_18], eax
0x180032c49  mov     [rbp+57h+var_50], eax
0x180032c4c  mov     dword ptr [rbp+57h+arg_10], r15d
0x180032c50  lea     rax, [rbp+57h+var_40]
0x180032c54  mov     [rbp+57h+var_90], rax
0x180032c58  lea     r8, [rbp+57h+var_40]; unsigned __int16 **
0x180032c5c  lea     rdx, aKeyName; "Key Name"
0x180032c63  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032c68  nop
0x180032c69  mov     ecx, [rbp+57h+var_38]
0x180032c6c  lea     edi, [r15+1]
0x180032c70  cmp     [rbp+57h+var_40], r15
0x180032c74  cmovnz  ecx, edi
0x180032c77  mov     [rbp+57h+var_38], ecx
0x180032c7a  test    eax, eax
0x180032c7c  jnz     loc_180032FF7
0x180032c82  lea     r8, [rbp+57h+arg_18]; unsigned int *
0x180032c86  lea     rdx, aKeyPresence; "Key Presence"
0x180032c8d  mov     rcx, rsi; HKEY
0x180032c90  call    ?GetRegistryDWordValue@@YAJPEAUHKEY__@@PEAGPEAK@Z; GetRegistryDWordValue(HKEY__ *,ushort *,ulong *)
0x180032c95  test    eax, eax
0x180032c97  js      loc_180032FF7
0x180032c9d  jnz     short loc_180032CEE
0x180032c9f  mov     r8d, [rbp+57h+arg_18]
0x180032ca3  mov     ecx, r8d; unsigned int
0x180032ca6  call    ?CheckPresenceValue@@YAJK@Z; CheckPresenceValue(ulong)
0x180032cab  test    eax, eax
0x180032cad  jns     short loc_180032CEE
0x180032caf  mov     rdx, [r14+8]
0x180032cb3  lea     rcx, aInvalidRegistr; "Invalid registry presence value for %s "...
0x180032cba  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180032cbf  nop
0x180032cc0  lea     rcx, [rbp+57h+hKey]
0x180032cc4  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x180032cc9  nop
0x180032cca  lea     rcx, [rbp+57h+String2]
0x180032cce  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032cd3  nop
0x180032cd4  lea     rcx, [rbp+57h+lpValueName]
0x180032cd8  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032cdd  nop
0x180032cde  lea     rcx, [rbp+57h+var_40]
0x180032ce2  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032ce7  xor     eax, eax
0x180032ce9  jmp     loc_180033023
0x180032cee  mov     [rbp+57h+var_60], r15
0x180032cf2  mov     [rbp+57h+var_48], r15
0x180032cf6  lea     r8, [rbp+57h+var_48]; unsigned __int16 **
0x180032cfa  lea     rdx, [rbp+57h+var_60]; HKEY *
0x180032cfe  mov     rcx, [rbp+57h+var_40]; String2
0x180032d02  call    ?ExtractRegKeyInfo@@YAJPEAGPEAPEAUHKEY__@@PEAPEAG@Z; ExtractRegKeyInfo(ushort *,HKEY__ * *,ushort * *)
0x180032d07  test    eax, eax
0x180032d09  jns     short loc_180032D1B
0x180032d0b  mov     rdx, [rbp+57h+var_40]
0x180032d0f  lea     rcx, aInvalidRegistr_0; "Invalid registry key! - %s"
0x180032d16  jmp     loc_180032FF2
0x180032d1b  lea     rdx, [rbp+57h+var_90]
0x180032d1f  lea     rcx, [rbp+57h+hKey]
0x180032d23  call    ??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)
0x180032d28  xor     r9d, r9d
0x180032d2b  mov     r8, [rax]
0x180032d2e  mov     rdx, [rbp+57h+var_48]
0x180032d32  mov     rcx, [rbp+57h+var_60]
0x180032d36  call    ?GetRegistryKey@@YAJPEAUHKEY__@@PEAGPEAPEAU1@W4VERSION_ARCHITECTURE@@@Z; GetRegistryKey(HKEY__ *,ushort *,HKEY__ * *,VERSION_ARCHITECTURE)
0x180032d3b  mov     ecx, eax
0x180032d3d  shr     ecx, 1Fh
0x180032d40  mov     rdx, [rbp+57h+var_90]
0x180032d44  cmp     [rdx], r15
0x180032d47  jz      short loc_180032D4C
0x180032d49  mov     [rdx+8], edi
0x180032d4c  test    cl, cl
0x180032d4e  jnz     loc_180032FF7
0x180032d54  mov     edx, r15d
0x180032d57  cmp     [rbp+57h+arg_18], r15d
0x180032d5b  setnz   dl; int
0x180032d5e  mov     ecx, r15d
0x180032d61  test    eax, eax
0x180032d63  setz    cl; int
0x180032d66  lea     r8, [rbp+57h+arg_10]; int *
0x180032d6a  call    ?ShouldReturnNowFromKeyExistence@@YAHHHPEAH@Z; ShouldReturnNowFromKeyExistence(int,int,int *)
0x180032d6f  test    eax, eax
0x180032d71  jz      short loc_180032D7B
0x180032d73  mov     edi, dword ptr [rbp+57h+arg_10]
0x180032d76  jmp     loc_180032FFA
0x180032d7b  lea     rax, [rbp+57h+lpValueName]
0x180032d7f  mov     [rbp+57h+var_90], rax
0x180032d83  cmp     [rbp+57h+var_78], r15d
0x180032d87  jz      short loc_180032D96
0x180032d89  mov     rcx, [rbp+57h+lpValueName]; void *
0x180032d8d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032d92  mov     [rbp+57h+var_78], r15d
0x180032d96  lea     r8, [rbp+57h+lpValueName]; unsigned __int16 **
0x180032d9a  lea     rdx, aValueName; "Value Name"
0x180032da1  mov     rcx, rsi; hKey
0x180032da4  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032da9  nop
0x180032daa  mov     edx, eax
0x180032dac  shr     edx, 1Fh
0x180032daf  mov     ecx, [rbp+57h+var_78]
0x180032db2  cmp     [rbp+57h+lpValueName], r15
0x180032db6  cmovnz  ecx, edi
0x180032db9  mov     [rbp+57h+var_78], ecx
0x180032dbc  test    dl, dl
0x180032dbe  jnz     loc_180032FF7
0x180032dc4  cmp     eax, edi
0x180032dc6  jz      loc_180032FFA
0x180032dcc  lea     r8, [rbp+57h+var_50]; unsigned int *
0x180032dd0  lea     rdx, aValuePresence; "Value Presence"
0x180032dd7  mov     rcx, rsi; HKEY
0x180032dda  call    ?GetRegistryDWordValue@@YAJPEAUHKEY__@@PEAGPEAK@Z; GetRegistryDWordValue(HKEY__ *,ushort *,ulong *)
0x180032ddf  test    eax, eax
0x180032de1  js      loc_180032FF7
0x180032de7  mov     edx, [rbp+57h+var_50]
0x180032dea  jnz     short loc_180032E0F
0x180032dec  mov     ecx, edx; unsigned int
0x180032dee  call    ?CheckPresenceValue@@YAJK@Z; CheckPresenceValue(ulong)
0x180032df3  test    eax, eax
0x180032df5  jns     short loc_180032E0F
0x180032df7  mov     r8d, edx
0x180032dfa  mov     rdx, [r14+8]
0x180032dfe  lea     rcx, aInvalidRegistr; "Invalid registry presence value for %s "...
0x180032e05  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180032e0a  jmp     loc_180032FF7
0x180032e0f  mov     ebx, r15d
0x180032e12  test    edx, edx
0x180032e14  setnz   bl
0x180032e17  mov     [rsp+0C0h+lpcbData], r15; lpcbData
0x180032e1c  mov     [rsp+0C0h+lpData], r15; lpData
0x180032e21  xor     r9d, r9d; lpType
0x180032e24  xor     r8d, r8d; lpReserved
0x180032e27  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x180032e2b  mov     rcx, [rbp+57h+hKey]; hKey
0x180032e2f  call    cs:__imp_RegQueryValueExW
0x180032e35  mov     ecx, r15d
0x180032e38  test    eax, eax
0x180032e3a  setz    cl; int
0x180032e3d  lea     r8, [rbp+57h+arg_10]; int *
0x180032e41  mov     edx, ebx; int
0x180032e43  call    ?ShouldReturnNowFromKeyExistence@@YAHHHPEAH@Z; ShouldReturnNowFromKeyExistence(int,int,int *)
0x180032e48  test    eax, eax
0x180032e4a  jnz     loc_180032D73
0x180032e50  lea     rax, [rbp+57h+String2]
0x180032e54  mov     [rbp+57h+arg_10], rax
0x180032e58  cmp     [rbp+57h+var_68], r15d
0x180032e5c  jz      short loc_180032E6B
0x180032e5e  mov     rcx, [rbp+57h+String2]; void *
0x180032e62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032e67  mov     [rbp+57h+var_68], r15d
0x180032e6b  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x180032e6f  lea     rdx, aValueType; "Value Type"
0x180032e76  mov     rcx, rsi; hKey
0x180032e79  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032e7e  nop
0x180032e7f  mov     ecx, [rbp+57h+var_68]
0x180032e82  mov     rdx, [rbp+57h+String2]; String2
0x180032e86  test    rdx, rdx
0x180032e89  cmovnz  ecx, edi
0x180032e8c  mov     [rbp+57h+var_68], ecx
0x180032e8f  test    eax, eax
0x180032e91  jz      short loc_180032EA3
0x180032e93  mov     rdx, [r14+8]
0x180032e97  lea     rcx, aRelatedRegistr; "Related registry key for %s does not ha"...
0x180032e9e  jmp     loc_180032FF2
0x180032ea3  lea     rcx, aDword; "DWORD"
0x180032eaa  call    _wcsicmp
0x180032eaf  test    eax, eax
0x180032eb1  jnz     short loc_180032F01
0x180032eb3  mov     dword ptr [rbp+57h+var_48], r15d
0x180032eb7  mov     dword ptr [rbp+57h+arg_10], r15d
0x180032ebb  lea     r8, [rbp+57h+var_48]; unsigned int *
0x180032ebf  mov     rdx, [rbp+57h+lpValueName]; unsigned __int16 *
0x180032ec3  mov     rcx, [rbp+57h+hKey]; HKEY
0x180032ec7  call    ?GetRegistryDWordValue@@YAJPEAUHKEY__@@PEAGPEAK@Z; GetRegistryDWordValue(HKEY__ *,ushort *,ulong *)
0x180032ecc  test    eax, eax
0x180032ece  js      loc_180032FF7
0x180032ed4  lea     r8, [rbp+57h+arg_10]; unsigned int *
0x180032ed8  lea     rdx, aValueValue; "Value Value"
0x180032edf  mov     rcx, rsi; HKEY
0x180032ee2  call    ?GetRegistryDWordValue@@YAJPEAUHKEY__@@PEAGPEAK@Z; GetRegistryDWordValue(HKEY__ *,ushort *,ulong *)
0x180032ee7  test    eax, eax
0x180032ee9  jnz     loc_180032FF7
0x180032eef  mov     edi, r15d
0x180032ef2  mov     eax, dword ptr [rbp+57h+arg_10]
0x180032ef5  cmp     dword ptr [rbp+57h+var_48], eax
0x180032ef8  setz    dil
0x180032efc  jmp     loc_180032FFA
0x180032f01  mov     rdx, [rbp+57h+String2]; String2
0x180032f05  lea     rcx, aString; "String"
0x180032f0c  call    _wcsicmp
0x180032f11  test    eax, eax
0x180032f13  jnz     loc_180032FE7
0x180032f19  mov     [rbp+57h+var_60], r15
0x180032f1d  mov     [rbp+57h+var_58], r15d
0x180032f21  mov     [rbp+57h+var_90], r15
0x180032f25  mov     [rbp+57h+var_88], r15d
0x180032f29  lea     rax, [rbp+57h+var_60]
0x180032f2d  mov     [rbp+57h+arg_10], rax
0x180032f31  lea     r8, [rbp+57h+var_60]; unsigned __int16 **
0x180032f35  lea     rdx, aValueValue; "Value Value"
0x180032f3c  mov     rcx, rsi; hKey
0x180032f3f  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032f44  nop
0x180032f45  mov     ecx, [rbp+57h+var_58]
0x180032f48  cmp     [rbp+57h+var_60], r15
0x180032f4c  cmovnz  ecx, edi
0x180032f4f  mov     [rbp+57h+var_58], ecx
0x180032f52  test    eax, eax
0x180032f54  jnz     short loc_180032FD2
0x180032f56  lea     rax, [rbp+57h+var_90]
0x180032f5a  mov     [rbp+57h+arg_10], rax
0x180032f5e  cmp     [rbp+57h+var_88], r15d
0x180032f62  jz      short loc_180032F71
0x180032f64  mov     rcx, [rbp+57h+var_90]; void *
0x180032f68  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180032f6d  mov     [rbp+57h+var_88], r15d
0x180032f71  lea     r8, [rbp+57h+var_90]; unsigned __int16 **
0x180032f75  mov     rdx, [rbp+57h+lpValueName]; lpValueName
0x180032f79  mov     rcx, [rbp+57h+hKey]; hKey
0x180032f7d  call    ?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z; GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)
0x180032f82  nop
0x180032f83  mov     ecx, [rbp+57h+var_88]
0x180032f86  mov     rdx, [rbp+57h+var_90]
0x180032f8a  test    rdx, rdx
0x180032f8d  cmovnz  ecx, edi
0x180032f90  mov     [rbp+57h+var_88], ecx
0x180032f93  test    eax, eax
0x180032f95  jnz     short loc_180032FD2
0x180032f97  mov     rax, [rbp+57h+var_60]
0x180032f9b  sub     rdx, rax
0x180032f9e  movzx   r8d, word ptr [rax]
0x180032fa2  movzx   ecx, word ptr [rax+rdx]
0x180032fa6  sub     r8d, ecx
0x180032fa9  jnz     short loc_180032FB3
0x180032fab  add     rax, 2
0x180032faf  test    ecx, ecx
0x180032fb1  jnz     short loc_180032F9E
0x180032fb3  mov     edi, r15d
0x180032fb6  test    r8d, r8d
0x180032fb9  setz    dil
0x180032fbd  lea     rcx, [rbp+57h+var_90]
0x180032fc1  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032fc6  nop
0x180032fc7  lea     rcx, [rbp+57h+var_60]
0x180032fcb  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032fd0  jmp     short loc_180032FFA
0x180032fd2  lea     rcx, [rbp+57h+var_90]
0x180032fd6  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032fdb  nop
0x180032fdc  lea     rcx, [rbp+57h+var_60]
0x180032fe0  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032fe5  jmp     short loc_180032FF7
0x180032fe7  mov     rdx, [rbp+57h+String2]
0x180032feb  lea     rcx, aUnknownRegistr; "Unknown registry value type - %s"
0x180032ff2  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180032ff7  mov     edi, r15d
0x180032ffa  lea     rcx, [rbp+57h+hKey]
0x180032ffe  call    ??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)
0x180033003  nop
0x180033004  lea     rcx, [rbp+57h+String2]
0x180033008  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x18003300d  nop
0x18003300e  lea     rcx, [rbp+57h+lpValueName]
0x180033012  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180033017  nop
0x180033018  lea     rcx, [rbp+57h+var_40]
0x18003301c  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180033021  mov     eax, edi
0x180033023  mov     rbx, [rsp+0C0h+arg_0]
0x18003302b  add     rsp, 0A0h
0x180033032  pop     r15
0x180033034  pop     r14
0x180033036  pop     rdi
0x180033037  pop     rsi
0x180033038  pop     rbp
0x180033039  retn
```
