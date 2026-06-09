# GetRegistryStringValue(HKEY__ *,ushort *,ushort * *)

- ea: `0x180033304`
- end: `0x18003343c`
- name: `?GetRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `312`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE **)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac2c`
- `0x180032a80`
- `0x180032c00`

## callees

- `0x180003070`
- `0x180005468`
- `0x18000b1f0`
- `0x180033304`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180033357`
- `ADVAPI32!RegQueryValueExW` at `0x1800333f3`
- `ADVAPI32!RegQueryValueExW` at `0x180033357`
- `ADVAPI32!RegQueryValueExW` at `0x1800333f3`

## string_xrefs

- `0x180033391`: `Registry value type for %s was not a string!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetRegistryStringValue(HKEY hKey, LPCWSTR lpValueName, BYTE **a3)
{
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  BYTE *lpData; // rbx
  int v9; // eax
  DWORD Type; // [rsp+30h] [rbp-20h] BYREF
  BYTE *v12; // [rsp+38h] [rbp-18h] BYREF
  int v13; // [rsp+40h] [rbp-10h]
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF

  v12 = 0;
  v13 = 0;
  cbData = 0;
  Type = 0;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 == 2 )
    {
      v7 = 1;
    }
    else if ( v6 > 0 )
    {
      v7 = (unsigned __int16)v6 | 0x80070000;
    }
  }
  else if ( Type == 1 )
  {
    lpData = (BYTE *)operator new[](saturated_mul((unsigned __int64)cbData >> 1, 2u));
    v12 = lpData;
    if ( lpData )
    {
      v13 = 1;
      v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
      if ( v9 )
      {
        if ( v9 > 0 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        v7 = v9;
      }
      else
      {
        v13 = 0;
        *a3 = lpData;
        v7 = 0;
      }
    }
    else
    {
      v7 = -2147024882;
    }
  }
  else
  {
    ReportAppCompatError((wchar_t *)L"Registry value type for %s was not a string!", lpValueName);
    v7 = -2147467259;
  }
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v12);
  return v7;
}

```

## disassembly

```asm
0x180033304  mov     r11, rsp
0x180033307  mov     [r11+8], rbx
0x18003330b  mov     [r11+10h], rsi
0x18003330f  push    rbp
0x180033310  push    rdi
0x180033311  push    r14
0x180033313  mov     rbp, rsp
0x180033316  sub     rsp, 50h
0x18003331a  mov     rsi, r8
0x18003331d  mov     rdi, rdx
0x180033320  mov     r14, rcx
0x180033323  mov     [rbp+var_18], 0
0x18003332b  mov     [rbp+var_10], 0
0x180033332  mov     [rbp+cbData], 0
0x180033339  mov     [rbp+Type], 0
0x180033340  lea     rax, [rbp+cbData]
0x180033344  mov     [r11-40h], rax
0x180033348  mov     qword ptr [r11-48h], 0
0x180033350  lea     r9, [rbp+Type]; lpType
0x180033354  xor     r8d, r8d; lpReserved
0x180033357  call    cs:__imp_RegQueryValueExW
0x18003335d  mov     ebx, eax
0x18003335f  test    eax, eax
0x180033361  jz      short loc_180033388
0x180033363  cmp     eax, 2
0x180033366  jz      short loc_18003337E
0x180033368  test    eax, eax
0x18003336a  jle     loc_18003341E
0x180033370  movzx   ebx, ax
0x180033373  or      ebx, 80070000h
0x180033379  jmp     loc_18003341E
0x18003337e  mov     ebx, 1
0x180033383  jmp     loc_18003341E
0x180033388  cmp     [rbp+Type], 1
0x18003338c  jz      short loc_1800333A4
0x18003338e  mov     rdx, rdi
0x180033391  lea     rcx, aRegistryValueT; "Registry value type for %s was not a st"...
0x180033398  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x18003339d  mov     ebx, 80004005h
0x1800333a2  jmp     short loc_18003341E
0x1800333a4  mov     ecx, [rbp+cbData]
0x1800333a7  shr     rcx, 1
0x1800333aa  mov     eax, 2
0x1800333af  mul     rcx
0x1800333b2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800333b9  cmovb   rax, rcx
0x1800333bd  mov     rcx, rax; unsigned __int64
0x1800333c0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800333c5  mov     rbx, rax
0x1800333c8  mov     [rbp+var_18], rax
0x1800333cc  test    rax, rax
0x1800333cf  jz      short loc_180033419
0x1800333d1  mov     [rbp+var_10], 1
0x1800333d8  lea     rax, [rbp+cbData]
0x1800333dc  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1800333e1  mov     [rsp+50h+lpData], rbx; lpData
0x1800333e6  lea     r9, [rbp+Type]; lpType
0x1800333ea  xor     r8d, r8d; lpReserved
0x1800333ed  mov     rdx, rdi; lpValueName
0x1800333f0  mov     rcx, r14; hKey
0x1800333f3  call    cs:__imp_RegQueryValueExW
0x1800333f9  test    eax, eax
0x1800333fb  jz      short loc_18003340B
0x1800333fd  jle     short loc_180033407
0x1800333ff  movzx   eax, ax
0x180033402  or      eax, 80070000h
0x180033407  mov     ebx, eax
0x180033409  jmp     short loc_18003341E
0x18003340b  mov     [rbp+var_10], 0
0x180033412  mov     [rsi], rbx
0x180033415  xor     ebx, ebx
0x180033417  jmp     short loc_18003341E
0x180033419  mov     ebx, 8007000Eh
0x18003341e  lea     rcx, [rbp+var_18]
0x180033422  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180033427  mov     eax, ebx
0x180033429  mov     rbx, [rsp+50h+arg_0]
0x18003342e  mov     rsi, [rsp+50h+arg_8]
0x180033433  add     rsp, 50h
0x180033437  pop     r14
0x180033439  pop     rdi
0x18003343a  pop     rbp
0x18003343b  retn
```
