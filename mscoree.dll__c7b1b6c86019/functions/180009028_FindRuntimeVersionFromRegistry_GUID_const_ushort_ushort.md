# FindRuntimeVersionFromRegistry(_GUID const &,ushort * *,ushort * *)

- ea: `0x180009028`
- end: `0x180009327`
- name: `?FindRuntimeVersionFromRegistry@@YAJAEBU_GUID@@PEAPEAG1@Z`
- size: `767`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029774`

## callees

- `0x180003070`
- `0x180003740`
- `0x18000663c`
- `0x180006678`
- `0x180009028`
- `0x180009330`
- `0x180009350`
- `0x1800099b0`
- `0x18000c1a8`
- `0x18000d614`
- `0x180039620`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000918e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000918e`

## string_xrefs

- `0x18000910f`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FindRuntimeVersionFromRegistry(const struct _GUID *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  unsigned __int16 ***v5; // rax
  int HighestVersion; // ebx
  int v7; // eax
  _QWORD *v8; // rax
  const struct NoThrow *v9; // rdx
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rdi
  __int64 v12; // rdi
  __int64 v13; // rcx
  unsigned __int64 v14; // rcx
  unsigned __int128 v15; // rax
  unsigned __int16 *v16; // rsi
  unsigned __int16 *v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+38h] [rbp-C8h]
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  struct _GUID v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  wchar_t Source[64]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Destination[256]; // [rsp+100h] [rbp+0h] BYREF

  phkResult = 0;
  v23 = 0;
  v24 = 0;
  v21 = 0;
  v20 = 0;
  v18 = 0;
  v19 = 0;
  v26 = 0;
  v27 = 0;
  if ( !a2 || (*a2 = 0, v25 = *a1, !(unsigned int)GuidToLPWSTR(&v25, Source, (unsigned int)a3)) )
  {
    HighestVersion = -2147024809;
    goto LABEL_35;
  }
  v5 = (unsigned __int16 ***)BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::operator&(
                               &v23,
                               &v25);
  HighestVersion = FindHighestVersion(a1, 0, 0, *v5, &v21, &v20);
  if ( **(_QWORD **)&v25.Data1 )
    *(_DWORD *)(*(_QWORD *)&v25.Data1 + 8LL) = 1;
  if ( HighestVersion >= 0 )
  {
    if ( v20 )
    {
      v12 = -1;
      v13 = -1;
      do
        ++v13;
      while ( v23[v13] );
      v14 = v13 + 2;
      v15 = v14 * (unsigned __int128)2uLL;
      if ( !is_mul_ok(v14, 2u) )
        *(_QWORD *)&v15 = -1;
      v16 = (unsigned __int16 *)operator new(v15, *((const struct NoThrow **)&v15 + 1));
      if ( v19 )
      {
        FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>::DoRelease(&v18);
        v19 = 0;
      }
      v18 = v16;
      if ( !v16 )
        goto LABEL_22;
      v19 = 1;
      *v16 = 118;
      do
        ++v12;
      while ( v23[v12] );
      wcscpy_s(v18 + 1, v12 + 1, v23);
      goto LABEL_33;
    }
    wcscpy_s(Destination, 0x100u, L"CLSID\\");
    wcscat_s(Destination, 0x100u, Source);
    wcscat_s(Destination, 0x100u, L"\\InprocServer32");
    if ( !v21 )
    {
      wcscat_s(Destination, 0x100u, L"\\");
      wcscat_s(Destination, 0x100u, v23);
    }
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult);
    if ( v7 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      HighestVersion = v7;
      goto LABEL_35;
    }
    v8 = (_QWORD *)BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::operator&(
                     &v18,
                     &v25);
    HighestVersion = ReadRegistryStringValue(&phkResult, L"RuntimeVersion", *v8);
    if ( **(_QWORD **)&v25.Data1 )
      *(_DWORD *)(*(_QWORD *)&v25.Data1 + 8LL) = 1;
    if ( HighestVersion >= 0 )
    {
      if ( HighestVersion == 1 )
      {
        v10 = (wchar_t *)operator new(0x14u, v9);
        v11 = v10;
        if ( v10 )
          wcscpy_s(v10, 0xAu, L"v1.0.3705");
        if ( v19 )
        {
          FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>::DoRelease(&v18);
          v19 = 0;
        }
        v18 = v11;
        if ( !v11 )
        {
LABEL_22:
          HighestVersion = -2147024882;
          goto LABEL_35;
        }
      }
LABEL_33:
      v19 = 0;
      *a2 = v18;
    }
  }
LABEL_35:
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v26);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v18);
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v23);
  HKEYHolder::~HKEYHolder((HKEYHolder *)&phkResult);
  return (unsigned int)HighestVersion;
}

```

## disassembly

```asm
0x180009028  mov     [rsp-8+arg_10], rbx
0x18000902d  push    rbp
0x18000902e  push    rsi
0x18000902f  push    rdi
0x180009030  push    r14
0x180009032  push    r15
0x180009034  lea     rbp, [rsp-210h]
0x18000903c  sub     rsp, 310h
0x180009043  mov     rax, cs:__security_cookie
0x18000904a  xor     rax, rsp
0x18000904d  mov     [rbp+230h+var_30], rax
0x180009054  mov     r14, rdx
0x180009057  mov     rbx, rcx
0x18000905a  xor     r15d, r15d
0x18000905d  mov     [rsp+330h+var_2E8], r15
0x180009062  mov     [rsp+330h+var_2E0], r15
0x180009067  mov     [rsp+330h+var_2D8], r15d
0x18000906c  mov     [rsp+330h+var_2EC], r15d
0x180009071  mov     [rsp+330h+var_2F0], r15d
0x180009076  mov     [rsp+330h+var_300], r15
0x18000907b  mov     [rsp+330h+var_2F8], r15d
0x180009080  mov     [rsp+330h+var_2C0], r15
0x180009085  mov     [rsp+330h+var_2B8], r15d
0x18000908a  test    rdx, rdx
0x18000908d  jz      loc_1800092CF
0x180009093  mov     [rdx], r15
0x180009096  movups  xmm0, xmmword ptr [rcx]
0x180009099  movdqu  xmmword ptr [rsp+330h+var_2D0.Data1], xmm0
0x18000909f  lea     rdx, [rbp+230h+Source]; unsigned __int16 *
0x1800090a3  lea     rcx, [rsp+330h+var_2D0]; struct _GUID
0x1800090a8  call    ?GuidToLPWSTR@@YAHU_GUID@@PEAGK@Z; GuidToLPWSTR(_GUID,ushort *,ulong)
0x1800090ad  test    eax, eax
0x1800090af  jz      loc_1800092CF
0x1800090b5  lea     rdx, [rsp+330h+var_2D0]
0x1800090ba  lea     rcx, [rsp+330h+var_2E0]
0x1800090bf  call    ??I?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::operator&(void)
0x1800090c4  nop
0x1800090c5  lea     rcx, [rsp+330h+var_2F0]
0x1800090ca  mov     [rsp+330h+var_308], rcx; int *
0x1800090cf  lea     rcx, [rsp+330h+var_2EC]
0x1800090d4  mov     [rsp+330h+phkResult], rcx; int *
0x1800090d9  mov     r9, [rax]; unsigned __int16 **
0x1800090dc  xor     r8d, r8d; struct AssemblyVersion *
0x1800090df  xor     edx, edx; int
0x1800090e1  mov     rcx, rbx; struct _GUID *
0x1800090e4  call    ?FindHighestVersion@@YAJAEBU_GUID@@HPEAVAssemblyVersion@@PEAPEAGPEAH3@Z; FindHighestVersion(_GUID const &,int,AssemblyVersion *,ushort * *,int *,int *)
0x1800090e9  mov     ebx, eax
0x1800090eb  mov     rax, qword ptr [rsp+330h+var_2D0.Data1]
0x1800090f0  cmp     [rax], r15
0x1800090f3  jz      short loc_1800090FC
0x1800090f5  mov     dword ptr [rax+8], 1
0x1800090fc  test    ebx, ebx
0x1800090fe  js      loc_1800092D4
0x180009104  cmp     [rsp+330h+var_2F0], r15d
0x180009109  jnz     loc_180009241
0x18000910f  lea     r8, aClsid; "CLSID\\"
0x180009116  mov     ebx, 100h
0x18000911b  mov     edx, ebx; SizeInWords
0x18000911d  lea     rcx, [rbp+230h+Destination]; Destination
0x180009121  call    wcscpy_s
0x180009126  lea     r8, [rbp+230h+Source]; Source
0x18000912a  mov     edx, ebx; SizeInWords
0x18000912c  lea     rcx, [rbp+230h+Destination]; Destination
0x180009130  call    wcscat_s
0x180009135  lea     r8, aInprocserver32; "\\InprocServer32"
0x18000913c  mov     edx, ebx; SizeInWords
0x18000913e  lea     rcx, [rbp+230h+Destination]; Destination
0x180009142  call    wcscat_s
0x180009147  cmp     [rsp+330h+var_2EC], r15d
0x18000914c  jnz     short loc_180009170
0x18000914e  lea     r8, asc_18004C8C0; "\\"
0x180009155  mov     edx, ebx; SizeInWords
0x180009157  lea     rcx, [rbp+230h+Destination]; Destination
0x18000915b  call    wcscat_s
0x180009160  mov     r8, [rsp+330h+var_2E0]; Source
0x180009165  mov     edx, ebx; SizeInWords
0x180009167  lea     rcx, [rbp+230h+Destination]; Destination
0x18000916b  call    wcscat_s
0x180009170  lea     rax, [rsp+330h+var_2E8]
0x180009175  mov     [rsp+330h+phkResult], rax; phkResult
0x18000917a  mov     r9d, 20019h; samDesired
0x180009180  xor     r8d, r8d; ulOptions
0x180009183  lea     rdx, [rbp+230h+Destination]; lpSubKey
0x180009187  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000918e  call    cs:__imp_RegOpenKeyExW
0x180009194  test    eax, eax
0x180009196  jz      short loc_1800091A9
0x180009198  jle     short loc_1800091A2
0x18000919a  movzx   eax, ax
0x18000919d  or      eax, 80070000h
0x1800091a2  mov     ebx, eax
0x1800091a4  jmp     loc_1800092D4
0x1800091a9  lea     rdx, [rsp+330h+var_2D0]
0x1800091ae  lea     rcx, [rsp+330h+var_300]
0x1800091b3  call    ??I?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ; BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::operator&(void)
0x1800091b8  nop
0x1800091b9  mov     r8, [rax]
0x1800091bc  lea     rdx, aRuntimeversion; "RuntimeVersion"
0x1800091c3  lea     rcx, [rsp+330h+var_2E8]
0x1800091c8  call    ReadRegistryStringValue
0x1800091cd  mov     ebx, eax
0x1800091cf  mov     rax, qword ptr [rsp+330h+var_2D0.Data1]
0x1800091d4  cmp     [rax], r15
0x1800091d7  jz      short loc_1800091E0
0x1800091d9  mov     dword ptr [rax+8], 1
0x1800091e0  test    ebx, ebx
0x1800091e2  js      loc_1800092D4
0x1800091e8  cmp     ebx, 1
0x1800091eb  jnz     loc_1800092C0
0x1800091f1  lea     ecx, [rbx+13h]; unsigned __int64
0x1800091f4  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800091f9  mov     rdi, rax
0x1800091fc  test    rax, rax
0x1800091ff  jz      short loc_180009213
0x180009201  lea     r8, aV103705; "v1.0.3705"
0x180009208  lea     edx, [rbx+9]; SizeInWords
0x18000920b  mov     rcx, rax; Destination
0x18000920e  call    wcscpy_s
0x180009213  cmp     [rsp+330h+var_2F8], r15d
0x180009218  jz      short loc_180009229
0x18000921a  lea     rcx, [rsp+330h+var_300]
0x18000921f  call    ?DoRelease@?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@IEAAXXZ; FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>::DoRelease(void)
0x180009224  mov     [rsp+330h+var_2F8], r15d
0x180009229  mov     [rsp+330h+var_300], rdi
0x18000922e  test    rdi, rdi
0x180009231  jnz     loc_1800092C0
0x180009237  mov     ebx, 8007000Eh
0x18000923c  jmp     loc_1800092D4
0x180009241  mov     rax, [rsp+330h+var_2E0]
0x180009246  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000924a  mov     rcx, rdi
0x18000924d  inc     rcx
0x180009250  cmp     [rax+rcx*2], r15w
0x180009255  jnz     short loc_18000924D
0x180009257  add     rcx, 2
0x18000925b  mov     eax, 2
0x180009260  mul     rcx
0x180009263  cmovb   rax, rdi
0x180009267  mov     rcx, rax; unsigned __int64
0x18000926a  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18000926f  mov     rsi, rax
0x180009272  cmp     [rsp+330h+var_2F8], r15d
0x180009277  jz      short loc_180009288
0x180009279  lea     rcx, [rsp+330h+var_300]
0x18000927e  call    ?DoRelease@?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@IEAAXXZ; FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>::DoRelease(void)
0x180009283  mov     [rsp+330h+var_2F8], r15d
0x180009288  mov     [rsp+330h+var_300], rsi
0x18000928d  test    rsi, rsi
0x180009290  jz      short loc_180009237
0x180009292  mov     [rsp+330h+var_2F8], 1
0x18000929a  mov     word ptr [rsi], 76h ; 'v'
0x18000929f  mov     r8, [rsp+330h+var_2E0]; Source
0x1800092a4  inc     rdi
0x1800092a7  cmp     [r8+rdi*2], r15w
0x1800092ac  jnz     short loc_1800092A4
0x1800092ae  lea     rdx, [rdi+1]; SizeInWords
0x1800092b2  mov     rcx, [rsp+330h+var_300]
0x1800092b7  add     rcx, 2; Destination
0x1800092bb  call    wcscpy_s
0x1800092c0  mov     [rsp+330h+var_2F8], r15d
0x1800092c5  mov     rax, [rsp+330h+var_300]
0x1800092ca  mov     [r14], rax
0x1800092cd  jmp     short loc_1800092D4
0x1800092cf  mov     ebx, 80070057h
0x1800092d4  lea     rcx, [rsp+330h+var_2C0]
0x1800092d9  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x1800092de  nop
0x1800092df  lea     rcx, [rsp+330h+var_300]
0x1800092e4  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x1800092e9  nop
0x1800092ea  lea     rcx, [rsp+330h+var_2E0]
0x1800092ef  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x1800092f4  nop
0x1800092f5  lea     rcx, [rsp+330h+var_2E8]; this
0x1800092fa  call    ??1HKEYHolder@@QEAA@XZ; HKEYHolder::~HKEYHolder(void)
0x1800092ff  mov     eax, ebx
0x180009301  mov     rcx, [rbp+230h+var_30]
0x180009308  xor     rcx, rsp; StackCookie
0x18000930b  call    __security_check_cookie
0x180009310  mov     rbx, [rsp+330h+arg_10]
0x180009318  add     rsp, 310h
0x18000931f  pop     r15
0x180009321  pop     r14
0x180009323  pop     rdi
0x180009324  pop     rsi
0x180009325  pop     rbp
0x180009326  retn
```
