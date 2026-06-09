# RtdspGetTriggerEndpoints

- ea: `0x140009410`
- end: `0x14000981d`
- name: `RtdspGetTriggerEndpoints`
- size: `1037`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140009230`

## callees

- `0x140001280`
- `0x140001580`
- `0x140001700`
- `0x140001b40`
- `0x140009410`
- `0x140009830`
- `0x140009890`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400094db`
- `ntoskrnl!ZwClose` at `0x1400094db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009765`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009779`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000980c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009765`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009779`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400097ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000980c`
- `ntoskrnl!ExAllocatePool2` at `0x140009704`
- `ntoskrnl!ExAllocatePool2` at `0x140009728`
- `ntoskrnl!ExAllocatePool2` at `0x140009704`
- `ntoskrnl!ExAllocatePool2` at `0x140009728`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400094ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400094ab`
- `ntoskrnl!ZwOpenKey` at `0x140009591`
- `ntoskrnl!ZwOpenKey` at `0x140009591`
- `ntoskrnl!ZwEnumerateKey` at `0x1400095d2`
- `ntoskrnl!ZwEnumerateKey` at `0x1400095d2`

## pseudocode

```c
__int64 __fastcall RtdspGetTriggerEndpoints(NTSTRSAFE_PCWSTR pszSrc, size_t a2, size_t *a3, const wchar_t *a4)
{
  _WORD *Pool2; // r14
  __int64 v6; // r15
  size_t *v7; // r12
  NTSTATUS v9; // esi
  size_t v10; // rdx
  ULONG v11; // r8d
  unsigned __int64 v13; // rbx
  ULONG v14; // ebx
  NTSTATUS v15; // eax
  size_t v16; // rdx
  ULONG v17; // r8d
  unsigned __int16 v18; // r9
  _WORD *v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // r9
  _WORD *v22; // rdx
  _WORD *v23; // r10
  __int16 v24; // ax
  _WORD *v25; // rcx
  _QWORD *v26; // rcx
  _QWORD *v27; // rax
  size_t Length; // [rsp+20h] [rbp-E0h]
  size_t Lengtha; // [rsp+20h] [rbp-E0h]
  __int128 v30; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  size_t pcchNewDestLength; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-98h] BYREF
  size_t *v36; // [rsp+78h] [rbp-88h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyInformation[12]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v39; // [rsp+BCh] [rbp-44h]
  _BYTE v40[528]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t pszDest[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v36 = a3;
  *((_QWORD *)&v30 + 1) = &v30;
  Pool2 = 0;
  *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
  ResultLength = 0;
  v6 = 0;
  Handle = 0;
  v7 = a3;
  *(_QWORD *)&v30 = &v30;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v9 = RtlStringCopyWorkerW(pszDest, a2, a3, a4, Length);
  if ( v9 )
    goto LABEL_3;
  RtlInitUnicodeString(&DestinationString, pszDest);
  DestinationString.MaximumLength = 514;
  v9 = RtlUnicodeStringValidateWorker(&DestinationString, v10, v11);
  if ( v9 < 0 )
    goto LABEL_3;
  v13 = (unsigned __int64)DestinationString.Length >> 1;
  pcchNewDestLength = 0;
  v9 = RtlWideCharArrayCopyStringWorker(&DestinationString.Buffer[v13], 257 - v13, &pcchNewDestLength, pszSrc, Lengtha);
  DestinationString.Length = 2 * (pcchNewDestLength + v13);
  if ( v9 )
    goto LABEL_3;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes);
  if ( v9 )
    goto LABEL_3;
  v14 = 0;
  while ( 1 )
  {
    if ( !v6 )
    {
LABEL_29:
      Pool2 = (_WORD *)ExAllocatePool2(256, 514, 1935963218);
      if ( !Pool2 )
        goto LABEL_31;
      v6 = ExAllocatePool2(256, 64, 1935963218);
      if ( !v6 )
        goto LABEL_31;
    }
    v15 = ZwEnumerateKey(Handle, v14, KeyBasicInformation, KeyInformation, 0x21Au, &ResultLength);
    v9 = v15;
    if ( v15 == -2147483622 )
      break;
    if ( v15 )
      goto LABEL_3;
    if ( v39 >= 0x21A )
    {
LABEL_31:
      v9 = -1073741801;
      goto LABEL_3;
    }
    SourceString.Length = v39;
    SourceString.Buffer = (PWSTR)v40;
    SourceString.MaximumLength = v39;
    v9 = RtlUnicodeStringValidateWorker(&SourceString, v16, v17);
    if ( v9 < 0 )
    {
      *Pool2 = 0;
      goto LABEL_3;
    }
    v19 = v40;
    v20 = (unsigned __int64)v18 >> 1;
    v21 = 257;
    v22 = Pool2;
    v9 = 0;
    while ( v20 )
    {
      v23 = v22;
      *v22++ = *v19++;
      --v20;
      if ( !--v21 )
      {
        v22 = v23;
        v9 = -2147483643;
        break;
      }
    }
    *v22 = 0;
    if ( v9 )
      goto LABEL_3;
    v24 = *Pool2;
    ++v14;
    if ( *Pool2 )
    {
      v25 = Pool2;
      do
      {
        if ( v24 == 1 )
          *v25 = 92;
        v24 = v25[1];
        ++v25;
      }
      while ( v24 );
      v7 = v36;
    }
    if ( !RtdspFindEndpoint(&v30, Pool2, v19, v21) )
    {
      *(_DWORD *)(v6 + 32) = 0;
      *(_QWORD *)(v6 + 24) = Pool2;
      *(_QWORD *)(v6 + 16) = a2;
      *(_DWORD *)(v6 + 56) = 0;
      v26 = (_QWORD *)*((_QWORD *)&v30 + 1);
      if ( **((__int128 ***)&v30 + 1) != &v30 )
        __fastfail(3u);
      v27 = (_QWORD *)(v6 + 40);
      v6 = 0;
      v27[1] = *((_QWORD *)&v30 + 1);
      *v27 = &v30;
      *v26 = v27;
      *((_QWORD *)&v30 + 1) = v27;
      goto LABEL_29;
    }
  }
  ExFreePoolWithTag(Pool2, 0x73647452u);
  ExFreePoolWithTag((PVOID)v6, 0x73647452u);
  if ( (__int128 *)v30 == &v30 )
  {
    v7[1] = (size_t)v7;
    *v7 = (size_t)v7;
  }
  else
  {
    *(_OWORD *)v7 = v30;
    *(_QWORD *)(*v7 + 8) = v7;
    *(_QWORD *)v7[1] = v7;
  }
  v9 = 0;
  *((_QWORD *)&v30 + 1) = &v30;
  *(_QWORD *)&v30 = &v30;
LABEL_3:
  if ( Handle )
    ZwClose(Handle);
  if ( v9 )
  {
    RtdspFreeEndpointList(&v30);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0x73647452u);
    if ( v6 )
      ExFreePoolWithTag((PVOID)v6, 0x73647452u);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140009410  mov     [rsp-8+arg_8], rbx
0x140009415  push    rbp
0x140009416  push    rsi
0x140009417  push    rdi
0x140009418  push    r12
0x14000941a  push    r13
0x14000941c  push    r14
0x14000941e  push    r15
0x140009420  lea     rbp, [rsp-3F0h]
0x140009428  sub     rsp, 4F0h
0x14000942f  mov     rax, cs:__security_cookie
0x140009436  xor     rax, rsp
0x140009439  mov     [rbp+420h+var_40], rax
0x140009440  xorps   xmm0, xmm0
0x140009443  mov     [rsp+520h+var_4A8], r8
0x140009448  xor     eax, eax
0x14000944a  mov     rdi, rcx
0x14000944d  xor     ecx, ecx
0x14000944f  lea     rax, [rsp+520h+var_4F0]
0x140009454  mov     qword ptr [rsp+520h+var_4F0+8], rax
0x140009459  mov     r14d, ecx
0x14000945c  lea     rax, [rsp+520h+var_4F0]
0x140009461  mov     dword ptr [rsp+520h+SourceString+4], ecx
0x140009465  mov     [rsp+520h+var_4E0], ecx
0x140009469  mov     r15d, ecx
0x14000946c  mov     [rsp+520h+Handle], rcx
0x140009471  mov     r12, r8
0x140009474  movups  xmmword ptr [rbp+420h+ObjectAttributes.ObjectName], xmm0
0x140009478  lea     rcx, [rbp+420h+pszDest]; pszDest
0x14000947f  mov     qword ptr [rsp+520h+var_4F0], rax
0x140009484  mov     r13, rdx
0x140009487  movups  xmmword ptr [rbp+420h+ObjectAttributes.Length], xmm0
0x14000948b  movups  xmmword ptr [rbp+420h+ObjectAttributes+1Ch], xmm0
0x14000948f  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x140009494  call    RtlStringCopyWorkerW
0x140009499  mov     esi, eax
0x14000949b  test    eax, eax
0x14000949d  jnz     short loc_1400094D1
0x14000949f  lea     rdx, [rbp+420h+pszDest]; SourceString
0x1400094a6  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x1400094ab  call    cs:__imp_RtlInitUnicodeString
0x1400094b2  nop     dword ptr [rax+rax+00h]
0x1400094b7  mov     eax, 202h
0x1400094bc  lea     rcx, [rsp+520h+DestinationString]; SourceString
0x1400094c1  mov     [rsp+520h+DestinationString.MaximumLength], ax
0x1400094c6  call    RtlUnicodeStringValidateWorker
0x1400094cb  mov     esi, eax
0x1400094cd  test    eax, eax
0x1400094cf  jns     short loc_14000951C
0x1400094d1  mov     rcx, [rsp+520h+Handle]; Handle
0x1400094d6  test    rcx, rcx
0x1400094d9  jz      short loc_1400094E7
0x1400094db  call    cs:__imp_ZwClose
0x1400094e2  nop     dword ptr [rax+rax+00h]
0x1400094e7  test    esi, esi
0x1400094e9  jnz     loc_1400097D8
0x1400094ef  mov     eax, esi
0x1400094f1  mov     rcx, [rbp+420h+var_40]
0x1400094f8  xor     rcx, rsp; StackCookie
0x1400094fb  call    __security_check_cookie
0x140009500  mov     rbx, [rsp+520h+arg_8]
0x140009508  add     rsp, 4F0h
0x14000950f  pop     r15
0x140009511  pop     r14
0x140009513  pop     r13
0x140009515  pop     r12
0x140009517  pop     rdi
0x140009518  pop     rsi
0x140009519  pop     rbp
0x14000951a  retn
0x14000951c  movzx   ebx, [rsp+520h+DestinationString.Length]
0x140009521  lea     r8, [rsp+520h+pcchNewDestLength]; pcchNewDestLength
0x140009526  mov     rax, [rsp+520h+DestinationString.Buffer]
0x14000952b  mov     edx, 101h
0x140009530  shr     rbx, 1
0x140009533  mov     r9, rdi; pszSrc
0x140009536  sub     rdx, rbx; cchDest
0x140009539  mov     [rsp+520h+pcchNewDestLength], r14
0x14000953e  lea     rcx, [rax+rbx*2]; pszDest
0x140009542  call    RtlWideCharArrayCopyStringWorker
0x140009547  add     bx, word ptr [rsp+520h+pcchNewDestLength]
0x14000954c  mov     esi, eax
0x14000954e  add     bx, bx
0x140009551  mov     [rsp+520h+DestinationString.Length], bx
0x140009556  test    eax, eax
0x140009558  jnz     loc_1400094D1
0x14000955e  lea     rax, [rsp+520h+DestinationString]
0x140009563  mov     [rbp+420h+ObjectAttributes.Length], 30h ; '0'
0x14000956a  xorps   xmm0, xmm0
0x14000956d  mov     [rbp+420h+ObjectAttributes.ObjectName], rax
0x140009571  xor     edi, edi
0x140009573  mov     [rbp+420h+ObjectAttributes.Attributes], 240h
0x14000957a  lea     r8, [rbp+420h+ObjectAttributes]; ObjectAttributes
0x14000957e  mov     [rbp+420h+ObjectAttributes.RootDirectory], rdi
0x140009582  mov     edx, 20019h; DesiredAccess
0x140009587  lea     rcx, [rsp+520h+Handle]; KeyHandle
0x14000958c  movdqu  xmmword ptr [rbp+420h+ObjectAttributes.SecurityDescriptor], xmm0
0x140009591  call    cs:__imp_ZwOpenKey
0x140009598  nop     dword ptr [rax+rax+00h]
0x14000959d  mov     esi, eax
0x14000959f  test    eax, eax
0x1400095a1  jnz     loc_1400094D1
0x1400095a7  mov     ebx, edi
0x1400095a9  test    r15, r15
0x1400095ac  jz      loc_1400096F4
0x1400095b2  mov     rcx, [rsp+520h+Handle]; KeyHandle
0x1400095b7  lea     rax, [rsp+520h+var_4E0]
0x1400095bc  mov     [rsp+520h+ResultLength], rax; ResultLength
0x1400095c1  lea     r9, [rbp+420h+KeyInformation]; KeyInformation
0x1400095c5  xor     r8d, r8d; KeyInformationClass
0x1400095c8  mov     dword ptr [rsp+520h+Length], 21Ah; Length
0x1400095d0  mov     edx, ebx; Index
0x1400095d2  call    cs:__imp_ZwEnumerateKey
0x1400095d9  nop     dword ptr [rax+rax+00h]
0x1400095de  mov     esi, eax
0x1400095e0  cmp     eax, 8000001Ah
0x1400095e5  jz      loc_14000975D
0x1400095eb  test    eax, eax
0x1400095ed  jnz     loc_1400094D1
0x1400095f3  mov     r9d, [rbp+420h+var_464]
0x1400095f7  cmp     r9d, 21Ah
0x1400095fe  jnb     loc_140009740
0x140009604  lea     rax, [rbp+420h+var_460]
0x140009608  mov     [rsp+520h+SourceString.Length], r9w
0x14000960e  lea     rcx, [rsp+520h+SourceString]; SourceString
0x140009613  mov     [rsp+520h+SourceString.Buffer], rax
0x140009618  mov     [rsp+520h+SourceString.MaximumLength], r9w
0x14000961e  call    RtlUnicodeStringValidateWorker
0x140009623  mov     esi, eax
0x140009625  test    eax, eax
0x140009627  js      loc_140009754
0x14000962d  movzx   eax, r9w
0x140009631  lea     r8, [rbp+420h+var_460]
0x140009635  shr     rax, 1
0x140009638  mov     r9d, 101h
0x14000963e  mov     rdx, r14
0x140009641  mov     esi, edi
0x140009643  test    rax, rax
0x140009646  jz      short loc_14000966B
0x140009648  movzx   ecx, word ptr [r8]
0x14000964c  mov     r10, rdx
0x14000964f  mov     [rdx], cx
0x140009652  add     r8, 2
0x140009656  add     rdx, 2
0x14000965a  dec     rax
0x14000965d  sub     r9, 1
0x140009661  jnz     short loc_140009643
0x140009663  mov     rdx, r10
0x140009666  mov     esi, 80000005h
0x14000966b  mov     [rdx], di
0x14000966e  test    esi, esi
0x140009670  jnz     loc_1400094D1
0x140009676  movzx   eax, word ptr [r14]
0x14000967a  inc     ebx
0x14000967c  test    ax, ax
0x14000967f  jz      short loc_1400096A0
0x140009681  mov     rcx, r14
0x140009684  cmp     ax, 1
0x140009688  jz      loc_14000974A
0x14000968e  movzx   eax, word ptr [rcx+2]
0x140009692  add     rcx, 2
0x140009696  test    ax, ax
0x140009699  jnz     short loc_140009684
0x14000969b  mov     r12, [rsp+520h+var_4A8]
0x1400096a0  mov     rdx, r14
0x1400096a3  lea     rcx, [rsp+520h+var_4F0]
0x1400096a8  call    RtdspFindEndpoint
0x1400096ad  test    rax, rax
0x1400096b0  jnz     loc_1400095A9
0x1400096b6  mov     [r15+20h], edi
0x1400096ba  lea     rax, [rsp+520h+var_4F0]
0x1400096bf  mov     [r15+18h], r14
0x1400096c3  mov     [r15+10h], r13
0x1400096c7  mov     [r15+38h], edi
0x1400096cb  mov     rcx, qword ptr [rsp+520h+var_4F0+8]
0x1400096d0  cmp     [rcx], rax
0x1400096d3  jnz     loc_1400097D1
0x1400096d9  lea     rax, [r15+28h]
0x1400096dd  mov     r15, rdi
0x1400096e0  mov     [rax+8], rcx
0x1400096e4  lea     rdx, [rsp+520h+var_4F0]
0x1400096e9  mov     [rax], rdx
0x1400096ec  mov     [rcx], rax
0x1400096ef  mov     qword ptr [rsp+520h+var_4F0+8], rax
0x1400096f4  mov     edx, 202h
0x1400096f9  mov     ecx, 100h
0x1400096fe  mov     r8d, 73647452h
0x140009704  call    cs:__imp_ExAllocatePool2
0x14000970b  nop     dword ptr [rax+rax+00h]
0x140009710  mov     r14, rax
0x140009713  test    rax, rax
0x140009716  jz      short loc_140009740
0x140009718  mov     edx, 40h ; '@'
0x14000971d  mov     ecx, 100h
0x140009722  mov     r8d, 73647452h
0x140009728  call    cs:__imp_ExAllocatePool2
0x14000972f  nop     dword ptr [rax+rax+00h]
0x140009734  mov     r15, rax
0x140009737  test    rax, rax
0x14000973a  jnz     loc_1400095B2
0x140009740  mov     esi, 0C0000017h
0x140009745  jmp     loc_1400094D1
0x14000974a  mov     word ptr [rcx], 5Ch ; '\'
0x14000974f  jmp     loc_14000968E
0x140009754  mov     [r14], di
0x140009758  jmp     loc_1400094D1
0x14000975d  mov     edx, 73647452h; Tag
0x140009762  mov     rcx, r14; P
0x140009765  call    cs:__imp_ExFreePoolWithTag
0x14000976c  nop     dword ptr [rax+rax+00h]
0x140009771  mov     edx, 73647452h; Tag
0x140009776  mov     rcx, r15; P
0x140009779  call    cs:__imp_ExFreePoolWithTag
0x140009780  nop     dword ptr [rax+rax+00h]
0x140009785  lea     rax, [rsp+520h+var_4F0]
0x14000978a  cmp     qword ptr [rsp+520h+var_4F0], rax
0x14000978f  jnz     short loc_1400097B5
0x140009791  mov     [r12+8], r12
0x140009796  mov     [r12], r12
0x14000979a  lea     rax, [rsp+520h+var_4F0]
0x14000979f  mov     esi, edi
0x1400097a1  mov     qword ptr [rsp+520h+var_4F0+8], rax
0x1400097a6  lea     rax, [rsp+520h+var_4F0]
0x1400097ab  mov     qword ptr [rsp+520h+var_4F0], rax
0x1400097b0  jmp     loc_1400094D1
0x1400097b5  movups  xmm0, [rsp+520h+var_4F0]
0x1400097ba  movups  xmmword ptr [r12], xmm0
0x1400097bf  mov     rax, [r12]
0x1400097c3  mov     [rax+8], r12
0x1400097c7  mov     rax, [r12+8]
0x1400097cc  mov     [rax], r12
0x1400097cf  jmp     short loc_14000979A
0x1400097d1  mov     ecx, 3
0x1400097d6  int     29h; Win8: RtlFailFast(ecx)
0x1400097d8  lea     rcx, [rsp+520h+var_4F0]
0x1400097dd  call    RtdspFreeEndpointList
0x1400097e2  test    r14, r14
0x1400097e5  jz      short loc_1400097FB
0x1400097e7  mov     edx, 73647452h; Tag
0x1400097ec  mov     rcx, r14; P
0x1400097ef  call    cs:__imp_ExFreePoolWithTag
0x1400097f6  nop     dword ptr [rax+rax+00h]
0x1400097fb  test    r15, r15
0x1400097fe  jz      loc_1400094EF
0x140009804  mov     edx, 73647452h; Tag
0x140009809  mov     rcx, r15; P
0x14000980c  call    cs:__imp_ExFreePoolWithTag
0x140009813  nop     dword ptr [rax+rax+00h]
0x140009818  jmp     loc_1400094EF
```
