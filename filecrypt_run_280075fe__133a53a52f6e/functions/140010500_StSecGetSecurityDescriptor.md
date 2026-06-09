# StSecGetSecurityDescriptor

- ea: `0x140010500`
- end: `0x140010887`
- name: `StSecGetSecurityDescriptor`
- size: `903`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000f9a0`
- `0x140010250`
- `0x1400103a0`

## callees

- `0x140001010`
- `0x140001340`
- `0x140001560`
- `0x14000dff8`
- `0x140010500`
- `0x140010890`
- `0x140010e20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010664`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010664`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400106a5`
- `ntoskrnl!ExAllocatePool2` at `0x140010626`
- `ntoskrnl!ExAllocatePool2` at `0x140010785`
- `ntoskrnl!ExAllocatePool2` at `0x140010626`
- `ntoskrnl!ExAllocatePool2` at `0x140010785`
- `ntoskrnl!FsRtlDissectName` at `0x14001071b`
- `ntoskrnl!FsRtlDissectName` at `0x14001073a`
- `ntoskrnl!FsRtlDissectName` at `0x1400107de`
- `ntoskrnl!FsRtlDissectName` at `0x1400107ff`
- `ntoskrnl!FsRtlDissectName` at `0x14001071b`
- `ntoskrnl!FsRtlDissectName` at `0x14001073a`
- `ntoskrnl!FsRtlDissectName` at `0x1400107de`
- `ntoskrnl!FsRtlDissectName` at `0x1400107ff`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x14001058a`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x14001058a`

## pseudocode

```c
__int64 __fastcall StSecGetSecurityDescriptor(UNICODE_STRING *a1, __int64 a2, wchar_t **a3, _DWORD *a4)
{
  PVOID v4; // rdi
  int StorageFolderStringSecurityDescriptor; // eax
  NTSTATUS v10; // ebx
  int v11; // r13d
  wchar_t *v12; // r14
  __int64 FolderPropertyPolicyElement; // rax
  __int64 v14; // r9
  __int64 v15; // rbx
  wchar_t *Pool2; // rax
  _WORD *v18; // r10
  _WORD *v19; // rcx
  __int64 v20; // rdx
  wchar_t *v21; // rax
  __int128 v22; // [rsp+28h] [rbp-29h] BYREF
  struct _UNICODE_STRING v23; // [rsp+38h] [rbp-19h] BYREF
  struct _UNICODE_STRING FirstName; // [rsp+48h] [rbp-9h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+58h] [rbp+7h] BYREF
  struct _UNICODE_STRING v26; // [rsp+68h] [rbp+17h] BYREF
  UNICODE_STRING Path; // [rsp+78h] [rbp+27h] BYREF
  PVOID P; // [rsp+B8h] [rbp+67h] BYREF

  v4 = 0;
  P = 0;
  if ( !a1 || !a1->Buffer || !a2 || !a3 || !a4 )
    goto LABEL_20;
  StorageFolderStringSecurityDescriptor = StSecpGetStorageFolderStringSecurityDescriptor(a1, &P);
  v4 = P;
  v10 = StorageFolderStringSecurityDescriptor;
  if ( StorageFolderStringSecurityDescriptor < 0 )
    goto LABEL_17;
  v10 = SeConvertStringSecurityDescriptorToSecurityDescriptor(P, 1, a2, 0);
  if ( v10 < 0 )
    goto LABEL_17;
  v11 = 0;
  v23 = 0;
  v12 = 0;
  v26 = 0;
  FirstName = 0;
  RemainingName = 0;
  FolderPropertyPolicyElement = StSecpFindFolderPropertyPolicyElement(a1);
  *(_QWORD *)&v22 = FolderPropertyPolicyElement;
  if ( !FolderPropertyPolicyElement )
  {
LABEL_9:
    *a4 = v11;
    v10 = 0;
    *a3 = v12;
    goto LABEL_17;
  }
  v18 = *(_WORD **)(FolderPropertyPolicyElement + 40);
  if ( !v18 )
  {
LABEL_20:
    v10 = -1073741811;
    goto LABEL_17;
  }
  v19 = *(_WORD **)(FolderPropertyPolicyElement + 40);
  v20 = 0x7FFFFFFF;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v20;
  }
  while ( v20 );
  v10 = -1073741811;
  if ( v20 )
  {
    v10 = 0;
    v14 = 0x7FFFFFFF - v20;
  }
  else
  {
    v14 = 0;
  }
  P = (PVOID)v14;
  if ( !v20 )
    goto LABEL_17;
  v15 = v14;
  v11 = *(_DWORD *)(FolderPropertyPolicyElement + 32);
  if ( *v18 != 60 || v18[v14 - 1] != 62 )
  {
    Pool2 = (wchar_t *)ExAllocatePool2(256, 2 * v14 + 2, 1884517459);
    v12 = Pool2;
    if ( !Pool2 )
    {
      v10 = -1073741801;
      goto LABEL_17;
    }
    v10 = RtlStringCchCopyW(Pool2, v15 + 1, *(NTSTRSAFE_PCWSTR *)(v22 + 40));
    if ( v10 >= 0 )
      goto LABEL_9;
LABEL_16:
    ExFreePoolWithTag(v12, 0x70537453u);
    goto LABEL_17;
  }
  Path = *(UNICODE_STRING *)(FolderPropertyPolicyElement + 16);
  FsRtlDissectName(&Path, &FirstName, &RemainingName);
  Path = *a1;
  FsRtlDissectName(&Path, &v23, &v26);
  while ( FirstName.Buffer )
  {
    Path = RemainingName;
    FsRtlDissectName(&Path, &FirstName, &RemainingName);
    Path = v26;
    FsRtlDissectName(&Path, &v23, &v26);
  }
  if ( !v23.Buffer )
    goto LABEL_9;
  if ( !wcsicmp(*(const wchar_t **)(v22 + 40), L"<PackageFamilyName>")
    || !wcsicmp(*(const wchar_t **)(v22 + 40), L"<ProductId>") )
  {
    v21 = (wchar_t *)ExAllocatePool2(256, v23.Length + 2LL, 1884517459);
    v12 = v21;
    if ( !v21 )
    {
      v10 = -1073741801;
      goto LABEL_17;
    }
    v10 = RtlStringCbCopyNW(v21, v23.Length + 2LL, v23.Buffer, v23.Length);
    if ( v10 >= 0 )
      goto LABEL_9;
    goto LABEL_16;
  }
  if ( wcsicmp(*(const wchar_t **)(v22 + 40), L"<PackageFullName>") )
  {
    v10 = -1073741823;
  }
  else
  {
    v22 = 0;
    v10 = StSecpPackageFamilyNameFromFullName(&v23, &v22);
    if ( v10 >= 0 )
    {
      v12 = (wchar_t *)*((_QWORD *)&v22 + 1);
      goto LABEL_9;
    }
  }
LABEL_17:
  if ( v4 )
    ExFreePoolWithTag(v4, 0x70537453u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140010500  mov     rax, rsp
0x140010503  push    rbp
0x140010504  push    rbx
0x140010505  push    rdi
0x140010506  lea     rbp, [rax-5Fh]
0x14001050a  sub     rsp, 90h
0x140010511  mov     [rax+10h], rsi
0x140010515  xor     edi, edi
0x140010517  mov     [rax+18h], r12
0x14001051b  mov     r12, r8
0x14001051e  mov     [rax+20h], r13
0x140010522  mov     rsi, rcx
0x140010525  mov     [rax-20h], r14
0x140010529  mov     r14, rdx
0x14001052c  mov     [rax-28h], r15
0x140010530  mov     r15, r9
0x140010533  mov     [rbp+57h+P], rdi
0x140010537  test    rcx, rcx
0x14001053a  jz      loc_1400106BF
0x140010540  cmp     [rcx+8], rdi
0x140010544  jz      loc_1400106BF
0x14001054a  test    rdx, rdx
0x14001054d  jz      loc_1400106BF
0x140010553  test    r8, r8
0x140010556  jz      loc_1400106BF
0x14001055c  test    r9, r9
0x14001055f  jz      loc_1400106BF
0x140010565  lea     rdx, [rbp+57h+P]
0x140010569  call    StSecpGetStorageFolderStringSecurityDescriptor
0x14001056e  mov     rdi, [rbp+57h+P]
0x140010572  mov     ebx, eax
0x140010574  test    eax, eax
0x140010576  js      loc_140010670
0x14001057c  xor     r9d, r9d
0x14001057f  mov     r8, r14
0x140010582  mov     edx, 1
0x140010587  mov     rcx, rdi
0x14001058a  call    cs:__imp_SeConvertStringSecurityDescriptorToSecurityDescriptor
0x140010591  nop     dword ptr [rax+rax+00h]
0x140010596  mov     ebx, eax
0x140010598  test    eax, eax
0x14001059a  js      loc_140010670
0x1400105a0  xorps   xmm0, xmm0
0x1400105a3  xorps   xmm1, xmm1
0x1400105a6  mov     rcx, rsi
0x1400105a9  xor     r13d, r13d
0x1400105ac  movups  xmmword ptr [rbp+57h+var_70.Length], xmm0
0x1400105b0  xor     r14d, r14d
0x1400105b3  movups  xmmword ptr [rbp+57h+var_40.Length], xmm1
0x1400105b7  movups  xmmword ptr [rbp+57h+FirstName.Length], xmm0
0x1400105bb  movups  xmmword ptr [rbp+57h+RemainingName.Length], xmm1
0x1400105bf  call    StSecpFindFolderPropertyPolicyElement
0x1400105c4  mov     qword ptr [rbp+57h+var_80], rax
0x1400105c8  mov     r8, rax
0x1400105cb  test    rax, rax
0x1400105ce  jnz     loc_1400106C6
0x1400105d4  mov     [r15], r13d
0x1400105d7  xor     ebx, ebx
0x1400105d9  mov     [r12], r14
0x1400105dd  jmp     loc_140010670
0x1400105e2  xor     eax, eax
0x1400105e4  mov     ebx, 0C000000Dh
0x1400105e9  test    rdx, rdx
0x1400105ec  cmovnz  ebx, eax
0x1400105ef  jz      loc_1400107C1
0x1400105f5  sub     r9, rdx
0x1400105f8  mov     [rbp+57h+P], r9
0x1400105fc  test    rdx, rdx
0x1400105ff  jz      short loc_140010670
0x140010601  cmp     word ptr [r10], 3Ch ; '<'
0x140010606  mov     rbx, r9
0x140010609  mov     r13d, [r8+20h]
0x14001060d  jz      loc_1400106F9
0x140010613  lea     rdx, ds:2[rbx*2]
0x14001061b  mov     ecx, 100h
0x140010620  mov     r8d, 70537453h
0x140010626  call    cs:__imp_ExAllocatePool2
0x14001062d  nop     dword ptr [rax+rax+00h]
0x140010632  mov     r14, rax
0x140010635  test    rax, rax
0x140010638  jz      loc_14001087D
0x14001063e  lea     rdx, [rbx+1]; cchDest
0x140010642  mov     rcx, rax; pszDest
0x140010645  mov     rbx, qword ptr [rbp+57h+var_80]
0x140010649  mov     r8, [rbx+28h]; pszSrc
0x14001064d  call    RtlStringCchCopyW
0x140010652  mov     ebx, eax
0x140010654  test    eax, eax
0x140010656  jns     loc_1400105D4
0x14001065c  mov     edx, 70537453h; Tag
0x140010661  mov     rcx, r14; P
0x140010664  call    cs:__imp_ExFreePoolWithTag
0x14001066b  nop     dword ptr [rax+rax+00h]
0x140010670  mov     r15, [rsp+0A0h+var_20]
0x140010678  mov     r14, [rsp+88h]
0x140010680  mov     r13, [rsp+0A0h+arg_18]
0x140010688  mov     r12, [rsp+0A0h+arg_10]
0x140010690  mov     rsi, [rsp+0A0h+arg_8]
0x140010698  test    rdi, rdi
0x14001069b  jz      short loc_1400106B1
0x14001069d  mov     edx, 70537453h; Tag
0x1400106a2  mov     rcx, rdi; P
0x1400106a5  call    cs:__imp_ExFreePoolWithTag
0x1400106ac  nop     dword ptr [rax+rax+00h]
0x1400106b1  mov     eax, ebx
0x1400106b3  add     rsp, 90h
0x1400106ba  pop     rdi
0x1400106bb  pop     rbx
0x1400106bc  pop     rbp
0x1400106bd  retn
0x1400106bf  mov     ebx, 0C000000Dh
0x1400106c4  jmp     short loc_140010670
0x1400106c6  mov     r10, [rax+28h]
0x1400106ca  test    r10, r10
0x1400106cd  jz      short loc_1400106BF
0x1400106cf  mov     r9d, 7FFFFFFFh
0x1400106d5  mov     rcx, r10
0x1400106d8  mov     edx, r9d
0x1400106db  nop     dword ptr [rax+rax+00h]
0x1400106e0  cmp     [rcx], r13w
0x1400106e4  jz      loc_1400105E2
0x1400106ea  add     rcx, 2
0x1400106ee  sub     rdx, 1
0x1400106f2  jnz     short loc_1400106E0
0x1400106f4  jmp     loc_1400105E2
0x1400106f9  cmp     word ptr [r10+rbx*2-2], 3Eh ; '>'
0x140010700  jnz     loc_140010613
0x140010706  movups  xmm0, xmmword ptr [r8+10h]
0x14001070b  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x14001070f  lea     rdx, [rbp+57h+FirstName]; FirstName
0x140010713  lea     rcx, [rbp+57h+Path]; Path
0x140010717  movaps  xmmword ptr [rbp+57h+Path.Length], xmm0
0x14001071b  call    cs:__imp_FsRtlDissectName
0x140010722  nop     dword ptr [rax+rax+00h]
0x140010727  movups  xmm0, xmmword ptr [rsi]
0x14001072a  lea     r8, [rbp+57h+var_40]; RemainingName
0x14001072e  lea     rdx, [rbp+57h+var_70]; FirstName
0x140010732  lea     rcx, [rbp+57h+Path]; Path
0x140010736  movaps  xmmword ptr [rbp+57h+Path.Length], xmm0
0x14001073a  call    cs:__imp_FsRtlDissectName
0x140010741  nop     dword ptr [rax+rax+00h]
0x140010746  cmp     [rbp+57h+FirstName.Buffer], r14
0x14001074a  jnz     short loc_1400107C9
0x14001074c  cmp     [rbp+57h+var_70.Buffer], r14
0x140010750  jz      loc_1400105D4
0x140010756  mov     rbx, qword ptr [rbp+57h+var_80]
0x14001075a  lea     rdx, aPackagefamilyn; "<PackageFamilyName>"
0x140010761  mov     rcx, [rbx+28h]; Str1
0x140010765  call    _wcsicmp
0x14001076a  test    eax, eax
0x14001076c  jnz     loc_140010816
0x140010772  movzx   edx, [rbp+57h+var_70.Length]
0x140010776  mov     ecx, 100h
0x14001077b  add     rdx, 2
0x14001077f  mov     r8d, 70537453h
0x140010785  call    cs:__imp_ExAllocatePool2
0x14001078c  nop     dword ptr [rax+rax+00h]
0x140010791  mov     r14, rax
0x140010794  test    rax, rax
0x140010797  jz      loc_140010873
0x14001079d  movzx   r9d, [rbp+57h+var_70.Length]; cbToCopy
0x1400107a2  mov     rcx, rax; pszDest
0x1400107a5  mov     r8, [rbp+57h+var_70.Buffer]; pszSrc
0x1400107a9  lea     rdx, [r9+2]; cbDest
0x1400107ad  call    RtlStringCbCopyNW
0x1400107b2  mov     ebx, eax
0x1400107b4  test    eax, eax
0x1400107b6  js      loc_14001065C
0x1400107bc  jmp     loc_1400105D4
0x1400107c1  xor     r9d, r9d
0x1400107c4  jmp     loc_1400105F8
0x1400107c9  movaps  xmm0, xmmword ptr [rbp+57h+RemainingName.Length]
0x1400107cd  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x1400107d1  lea     rdx, [rbp+57h+FirstName]; FirstName
0x1400107d5  movdqa  xmmword ptr [rbp+57h+Path.Length], xmm0
0x1400107da  lea     rcx, [rbp+57h+Path]; Path
0x1400107de  call    cs:__imp_FsRtlDissectName
0x1400107e5  nop     dword ptr [rax+rax+00h]
0x1400107ea  movaps  xmm0, xmmword ptr [rbp+57h+var_40.Length]
0x1400107ee  lea     r8, [rbp+57h+var_40]; RemainingName
0x1400107f2  lea     rdx, [rbp+57h+var_70]; FirstName
0x1400107f6  movdqa  xmmword ptr [rbp+57h+Path.Length], xmm0
0x1400107fb  lea     rcx, [rbp+57h+Path]; Path
0x1400107ff  call    cs:__imp_FsRtlDissectName
0x140010806  nop     dword ptr [rax+rax+00h]
0x14001080b  cmp     [rbp+57h+FirstName.Buffer], r14
0x14001080f  jnz     short loc_1400107C9
0x140010811  jmp     loc_14001074C
0x140010816  mov     rcx, [rbx+28h]; Str1
0x14001081a  lea     rdx, aProductid; "<ProductId>"
0x140010821  call    _wcsicmp
0x140010826  test    eax, eax
0x140010828  jz      loc_140010772
0x14001082e  mov     rcx, [rbx+28h]; Str1
0x140010832  lea     rdx, aPackagefullnam_0; "<PackageFullName>"
0x140010839  call    _wcsicmp
0x14001083e  test    eax, eax
0x140010840  jnz     short loc_140010869
0x140010842  xorps   xmm0, xmm0
0x140010845  lea     rdx, [rbp+57h+var_80]
0x140010849  lea     rcx, [rbp+57h+var_70]
0x14001084d  movups  [rbp+57h+var_80], xmm0
0x140010851  call    StSecpPackageFamilyNameFromFullName
0x140010856  mov     ebx, eax
0x140010858  test    eax, eax
0x14001085a  js      loc_140010670
0x140010860  mov     r14, qword ptr [rbp+57h+var_80+8]
0x140010864  jmp     loc_1400105D4
0x140010869  mov     ebx, 0C0000001h
0x14001086e  jmp     loc_140010670
0x140010873  mov     ebx, 0C0000017h
0x140010878  jmp     loc_140010670
0x14001087d  mov     ebx, 0C0000017h
0x140010882  jmp     loc_140010670
```
