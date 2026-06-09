# SIPolicyGetOriginalFilenameAndVersionFromImageBase

- ea: `0x1800a4240`
- end: `0x1800a47e7`
- name: `SIPolicyGetOriginalFilenameAndVersionFromImageBase`
- size: `1447`
- prototype: `__int64 __usercall@<rax>(PVOID BaseAddress@<rcx>, ULONGLONG Size@<rdx>, __int64, __int64, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a358c`
- `0x1800a3eb0`
- `0x1800a4098`
- `0x1800a41d8`

## callees

- `0x18000aa9c`
- `0x18000cbe4`
- `0x18000ed14`
- `0x180015040`
- `0x18002bf20`
- `0x1800a4240`
- `0x1800a47f0`
- `0x1800a4920`
- `0x1800a4a9c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4644`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4730`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a47d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4644`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4730`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a47d6`
- `ntoskrnl!LdrResSearchResource` at `0x1800a4378`
- `ntoskrnl!LdrResSearchResource` at `0x1800a4378`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a4682`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a4682`

## pseudocode

```c
__int64 __fastcall SIPolicyGetOriginalFilenameAndVersionFromImageBase(
        PVOID BaseAddress,
        ULONGLONG Size,
        char a3,
        struct _UNICODE_STRING *a4,
        _QWORD *a5,
        struct _UNICODE_STRING *a6,
        int a7,
        struct _UNICODE_STRING *a8,
        struct _UNICODE_STRING *a9)
{
  ULONGLONG v10; // r15
  size_t v12; // r12
  __int64 i; // rbx
  struct _UNICODE_STRING *v14; // rcx
  NTSTATUS v15; // ebx
  unsigned __int16 *v16; // rdi
  const wchar_t *v17; // rsi
  unsigned __int16 *v18; // r14
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx
  unsigned int v22; // esi
  __int64 v23; // r14
  unsigned int v24; // edi
  struct _UNICODE_STRING *v25; // r15
  WCHAR *v26; // r13
  const wchar_t *v27; // rcx
  int v28; // r15d
  __int64 v30; // [rsp+20h] [rbp-208h]
  char v31; // [rsp+44h] [rbp-1E4h]
  size_t pcbLength; // [rsp+48h] [rbp-1E0h] BYREF
  unsigned __int64 v33; // [rsp+50h] [rbp-1D8h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-1D0h]
  int v35; // [rsp+60h] [rbp-1C8h]
  unsigned int v36; // [rsp+64h] [rbp-1C4h]
  unsigned int v37; // [rsp+68h] [rbp-1C0h]
  unsigned __int16 *v38; // [rsp+70h] [rbp-1B8h] BYREF
  PCWSTR SourceString; // [rsp+78h] [rbp-1B0h] BYREF
  _DWORD v40[4]; // [rsp+80h] [rbp-1A8h]
  const wchar_t *v41; // [rsp+90h] [rbp-198h]
  unsigned __int16 *v42; // [rsp+98h] [rbp-190h]
  UNICODE_STRING String1; // [rsp+A0h] [rbp-188h] BYREF
  char *v44; // [rsp+B0h] [rbp-178h]
  struct _UNICODE_STRING DestinationString; // [rsp+B8h] [rbp-170h] BYREF
  PUNICODE_STRING v46[5]; // [rsp+C8h] [rbp-160h]
  wchar_t pszDest[128]; // [rsp+F0h] [rbp-138h] BYREF

  v10 = (unsigned int)Size;
  v34 = 0;
  v12 = 0;
  pcbLength = 0;
  v38 = 0;
  SourceString = 0;
  v33 = 0;
  v40[0] = 0;
  v40[1] = 1252;
  v40[2] = 1200;
  v31 = 0;
  v46[0] = a4;
  v46[1] = a8;
  v46[2] = a9;
  v46[3] = a6;
  v46[4] = 0;
  if ( a5 )
    *a5 = 0;
  for ( i = 0; i != 5; ++i )
  {
    v14 = v46[i];
    if ( v14 )
      RtlInitUnicodeString(v14, 0);
  }
  if ( (int)SIPolicyCanLoadResources(BaseAddress, v10) < 0 )
    return (unsigned int)-1073741793;
  v33 = v10;
  v15 = LdrResSearchResource(BaseAddress, qword_1800323B0, 3, a3 != 0 ? 0x81210 : 0, &v38, &v33, 0, 0);
  if ( v15 < 0 )
    return (unsigned int)v15;
  if ( v33 < 0x5C )
    return (unsigned int)-1073741275;
  v16 = v38;
  if ( *v38 > v33 || *((_DWORD *)v38 + 10) != -17890115 )
    return (unsigned int)-1073741275;
  if ( a5 )
    *a5 = *((unsigned int *)v38 + 13) + ((unsigned __int64)*((unsigned int *)v38 + 12) << 32);
  v17 = L"\\VarFileInfo\\Translation";
  v41 = L"\\VarFileInfo\\Translation";
  v15 = -1073741275;
  v35 = -1073741275;
  v42 = 0;
  v44 = 0;
  String1 = 0;
  DestinationString = 0;
  if ( v16[2] || (unsigned __int16)(*v16 - 8) > 0x7FF8u || (*v16 & 1) != 0 )
    goto LABEL_54;
LABEL_17:
  while ( *v17 == 92 )
    v41 = ++v17;
  v18 = (unsigned __int16 *)SIPolicyCheckVerBlock(v16, *v16);
  v42 = v18;
  if ( !v18 )
  {
LABEL_54:
    v21 = v34;
    goto LABEL_25;
  }
  if ( *v17 )
  {
    v26 = (WCHAR *)v17;
    while ( 1 )
    {
      v27 = v17;
      if ( !*v17 || *v17 == 92 )
        break;
      ++v17;
      v41 = v27 + 1;
    }
    v28 = (_DWORD)v16 + *v16;
    v44 = (char *)v16 + *v16;
    while ( SIPolicyCheckVerBlock(v18, (unsigned int)(v28 - (_DWORD)v18)) )
    {
      RtlInitUnicodeString(&DestinationString, v18 + 3);
      String1.Length = (_WORD)v17 - (_WORD)v26;
      String1.MaximumLength = (_WORD)v17 - (_WORD)v26;
      String1.Buffer = v26;
      if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
      {
        v16 = v18;
        goto LABEL_17;
      }
      v18 = (unsigned __int16 *)((char *)v18 + ((*v18 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
      v42 = v18;
    }
    goto LABEL_54;
  }
  v12 = v16[1];
  pcbLength = v12;
  v19 = -1;
  do
    ++v19;
  while ( v16[v19 + 3] );
  if ( (_WORD)v12 && (v16[2] || (unsigned __int16)v12 >= 2u) )
    v20 = (2 * (_DWORD)v19 + 11) & 0xFFFFFFFC;
  else
    v20 = 2LL * (unsigned int)v19 + 6;
  v21 = (unsigned __int16 *)((char *)v16 + v20);
  v34 = (unsigned __int16 *)((char *)v16 + v20);
  v15 = 0;
  v35 = 0;
LABEL_25:
  if ( v15 >= 0 )
  {
    if ( v12 < 4 || ((unsigned __int8)v21 & 1) != 0 )
      return (unsigned int)-1073741275;
    v40[0] = v21[1];
    v22 = 0;
    v37 = 0;
    while ( v22 < 3 )
    {
      LODWORD(v30) = v40[v22];
      v15 = RtlStringCbPrintfW(pszDest, 0x100u, L"\\StringFileInfo\\%04x%04x\\", *v21, v30);
      if ( v15 < 0 )
        break;
      v23 = -1;
      do
        ++v23;
      while ( pszDest[v23] );
      v24 = 0;
      v36 = 0;
      while ( v24 < 5 )
      {
        v25 = v46[v24];
        if ( v25 )
        {
          if ( 2 * (unsigned __int64)(unsigned int)v23 >= 0x100 )
            _report_rangecheckfailure();
          pszDest[(unsigned int)v23] = 0;
          v15 = RtlStringCbCatW(pszDest, 0x100u, off_18002F040[v24]);
          if ( v15 < 0 )
            return (unsigned int)v15;
          if ( (int)SIPolicyQuerySubVerBlock(v38, pszDest, &SourceString, &pcbLength) < 0 || pcbLength - 1 > 0xFFFE )
          {
            v15 = 0;
          }
          else
          {
            v31 = 1;
            v15 = RtlStringCbLengthW(SourceString, 2 * pcbLength, &pcbLength);
            if ( v15 >= 0 && pcbLength )
            {
              pcbLength += 2LL;
              RtlInitUnicodeString(v25, SourceString);
            }
            else
            {
              v15 = 0;
            }
          }
        }
        v36 = ++v24;
      }
      if ( v31 )
        break;
      v37 = ++v22;
      v21 = v34;
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800a4240  mov     r11, rsp
0x1800a4243  mov     [r11+18h], rbx
0x1800a4247  mov     [r11+20h], rsi
0x1800a424b  push    rdi
0x1800a424c  push    r12
0x1800a424e  push    r13
0x1800a4250  push    r14
0x1800a4252  push    r15
0x1800a4254  sub     rsp, 200h
0x1800a425b  mov     rax, cs:__security_cookie
0x1800a4262  xor     rax, rsp
0x1800a4265  mov     [rsp+228h+var_38], rax
0x1800a426d  mov     dil, r8b
0x1800a4270  mov     r15d, edx
0x1800a4273  mov     r14, rcx
0x1800a4276  mov     rsi, [rsp+228h+arg_20]
0x1800a427e  xor     r13d, r13d
0x1800a4281  mov     [rsp+228h+var_1D0], r13
0x1800a4286  mov     r12d, r13d
0x1800a4289  mov     [rsp+228h+pcbLength], r13
0x1800a428e  mov     [rsp+228h+var_1B8], r13
0x1800a4293  mov     [rsp+228h+SourceString], r13
0x1800a4298  mov     [rsp+228h+var_1D8], r13
0x1800a429d  mov     [r11-1A8h], r13d
0x1800a42a4  mov     [rsp+228h+var_1A4], 4E4h
0x1800a42af  mov     [rsp+228h+var_1A0], 4B0h
0x1800a42ba  mov     [rsp+228h+var_1E4], r13b
0x1800a42bf  mov     [r11-160h], r9
0x1800a42c6  mov     rax, [rsp+228h+arg_38]
0x1800a42ce  mov     [r11-158h], rax
0x1800a42d5  mov     rax, [rsp+228h+arg_40]
0x1800a42dd  mov     [r11-150h], rax
0x1800a42e4  mov     rax, [rsp+228h+arg_28]
0x1800a42ec  mov     [r11-148h], rax
0x1800a42f3  mov     [r11-140h], r13
0x1800a42fa  test    rsi, rsi
0x1800a42fd  jnz     loc_1800A47CC
0x1800a4303  mov     rbx, r13
0x1800a4306  mov     rcx, [rsp+rbx*8+228h+var_160]; DestinationString
0x1800a430e  test    rcx, rcx
0x1800a4311  jnz     loc_1800A47D4
0x1800a4317  inc     rbx
0x1800a431a  cmp     rbx, 5
0x1800a431e  jnz     short loc_1800A4306
0x1800a4320  mov     r8b, dil
0x1800a4323  mov     rdx, r15; Size
0x1800a4326  mov     rcx, r14; BaseAddress
0x1800a4329  call    SIPolicyCanLoadResources
0x1800a432e  mov     [rsp+228h+var_1E8], eax
0x1800a4332  test    eax, eax
0x1800a4334  js      loc_1800A4701
0x1800a433a  mov     [rsp+228h+var_1D8], r15
0x1800a433f  neg     dil
0x1800a4342  sbb     r9d, r9d
0x1800a4345  and     r9d, 81210h
0x1800a434c  mov     [rsp+228h+var_1F0], r13
0x1800a4351  mov     [rsp+228h+var_1F8], r13
0x1800a4356  lea     rax, [rsp+228h+var_1D8]
0x1800a435b  mov     [rsp+228h+var_200], rax
0x1800a4360  lea     rax, [rsp+228h+var_1B8]
0x1800a4365  mov     [rsp+228h+var_208], rax
0x1800a436a  lea     r8d, [rbx-2]
0x1800a436e  lea     rdx, qword_1800323B0
0x1800a4375  mov     rcx, r14
0x1800a4378  call    cs:__imp_LdrResSearchResource
0x1800a437f  nop     dword ptr [rax+rax+00h]
0x1800a4384  mov     ebx, eax
0x1800a4386  mov     [rsp+228h+var_1E8], eax
0x1800a438a  test    eax, eax
0x1800a438c  js      loc_1800A4794
0x1800a4392  mov     r15d, 5Ch ; '\'
0x1800a4398  cmp     [rsp+228h+var_1D8], r15
0x1800a439d  jb      loc_1800A44BE
0x1800a43a3  mov     rdi, [rsp+228h+var_1B8]
0x1800a43a8  movzx   eax, word ptr [rdi]
0x1800a43ab  cmp     rax, [rsp+228h+var_1D8]
0x1800a43b0  ja      loc_1800A44BE
0x1800a43b6  cmp     dword ptr [rdi+28h], 0FEEF04BDh
0x1800a43bd  jnz     loc_1800A44BE
0x1800a43c3  test    rsi, rsi
0x1800a43c6  jnz     loc_1800A470B
0x1800a43cc  lea     rsi, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x1800a43d3  mov     [rsp+228h+var_198], rsi
0x1800a43db  mov     ebx, 0C0000225h
0x1800a43e0  mov     [rsp+228h+var_1C8], ebx
0x1800a43e4  mov     [rsp+228h+var_190], r13
0x1800a43ec  mov     [rsp+228h+var_178], r13
0x1800a43f4  xorps   xmm0, xmm0
0x1800a43f7  movups  xmmword ptr [rsp+228h+String1.Length], xmm0
0x1800a43ff  xorps   xmm1, xmm1
0x1800a4402  movups  xmmword ptr [rsp+228h+DestinationString.Length], xmm1
0x1800a440a  cmp     [rdi+4], r13w
0x1800a440f  jnz     loc_1800A46CC
0x1800a4415  movzx   ecx, word ptr [rdi]
0x1800a4418  lea     eax, [rcx-8]
0x1800a441b  mov     edx, 7FF8h
0x1800a4420  cmp     ax, dx
0x1800a4423  ja      loc_1800A46CC
0x1800a4429  test    cl, 1
0x1800a442c  jnz     loc_1800A46CC
0x1800a4432  mov     r13d, 2
0x1800a4438  cmp     [rsi], r15w
0x1800a443c  jz      loc_1800A46BC
0x1800a4442  movzx   edx, word ptr [rdi]
0x1800a4445  mov     rcx, rdi
0x1800a4448  call    SIPolicyCheckVerBlock
0x1800a444d  mov     r14, rax
0x1800a4450  mov     [rsp+228h+var_190], rax
0x1800a4458  xor     edx, edx
0x1800a445a  test    rax, rax
0x1800a445d  jz      loc_1800A46D2
0x1800a4463  cmp     [rsi], dx
0x1800a4466  jnz     loc_1800A45F0
0x1800a446c  movzx   r12d, word ptr [rdi+2]
0x1800a4471  mov     [rsp+228h+pcbLength], r12
0x1800a4476  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a447a  inc     rax
0x1800a447d  cmp     [rdi+rax*2+6], dx
0x1800a4482  jnz     short loc_1800A447A
0x1800a4484  test    r12w, r12w
0x1800a4488  jnz     loc_1800A46DC
0x1800a448e  mov     eax, eax
0x1800a4490  lea     rax, ds:6[rax*2]
0x1800a4498  lea     rcx, [rdi+rax]
0x1800a449c  mov     [rsp+228h+var_1D0], rcx
0x1800a44a1  mov     ebx, edx
0x1800a44a3  mov     [rsp+228h+var_1C8], edx
0x1800a44a7  mov     [rsp+228h+var_1E8], ebx
0x1800a44ab  test    ebx, ebx
0x1800a44ad  js      loc_1800A4794
0x1800a44b3  cmp     r12, 4
0x1800a44b7  jb      short loc_1800A44BE
0x1800a44b9  test    cl, 1
0x1800a44bc  jz      short loc_1800A44CC
0x1800a44be  mov     ebx, 0C0000225h
0x1800a44c3  mov     [rsp+228h+var_1E8], ebx
0x1800a44c7  jmp     loc_1800A4794
0x1800a44cc  movzx   eax, word ptr [rcx+2]
0x1800a44d0  mov     [rsp+228h+var_1A8], eax
0x1800a44d7  xor     r12d, r12d
0x1800a44da  mov     esi, r12d
0x1800a44dd  mov     [rsp+228h+var_1C0], r12d
0x1800a44e2  cmp     esi, 3
0x1800a44e5  jnb     loc_1800A4794
0x1800a44eb  mov     eax, esi
0x1800a44ed  movzx   r9d, word ptr [rcx]
0x1800a44f1  mov     eax, [rsp+rax*4+228h+var_1A8]
0x1800a44f8  mov     dword ptr [rsp+228h+var_208], eax
0x1800a44fc  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\"
0x1800a4503  mov     edx, 100h; cbDest
0x1800a4508  lea     rcx, [rsp+228h+pszDest]; pszDest
0x1800a4510  call    RtlStringCbPrintfW
0x1800a4515  mov     ebx, eax
0x1800a4517  mov     [rsp+228h+var_1E8], eax
0x1800a451b  test    eax, eax
0x1800a451d  js      loc_1800A4794
0x1800a4523  lea     rax, [rsp+228h+pszDest]
0x1800a452b  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800a452f  inc     r14
0x1800a4532  cmp     [rax+r14*2], r12w
0x1800a4537  jnz     short loc_1800A452F
0x1800a4539  mov     edi, r12d
0x1800a453c  mov     [rsp+228h+var_1C4], r12d
0x1800a4541  cmp     edi, 5
0x1800a4544  jb      short loc_1800A455E
0x1800a4546  cmp     [rsp+228h+var_1E4], r12b
0x1800a454b  jnz     loc_1800A4794
0x1800a4551  inc     esi
0x1800a4553  mov     [rsp+228h+var_1C0], esi
0x1800a4557  mov     rcx, [rsp+228h+var_1D0]
0x1800a455c  jmp     short loc_1800A44E2
0x1800a455e  mov     r8d, edi
0x1800a4561  mov     r15, [rsp+r8*8+228h+var_160]
0x1800a4569  test    r15, r15
0x1800a456c  jz      loc_1800A473C
0x1800a4572  mov     eax, r14d
0x1800a4575  lea     rcx, [rax+rax]
0x1800a4579  mov     edx, 100h; cbDest
0x1800a457e  cmp     rcx, rdx
0x1800a4581  jnb     loc_1800A478F
0x1800a4587  mov     [rsp+rcx+228h+pszDest], r12w
0x1800a4590  lea     rax, off_18002F040; "OriginalFileName"
0x1800a4597  mov     r8, [rax+r8*8]; pszSrc
0x1800a459b  lea     rcx, [rsp+228h+pszDest]; pszDest
0x1800a45a3  call    RtlStringCbCatW
0x1800a45a8  mov     ebx, eax
0x1800a45aa  mov     [rsp+228h+var_1E8], eax
0x1800a45ae  test    eax, eax
0x1800a45b0  js      loc_1800A4794
0x1800a45b6  lea     r9, [rsp+228h+pcbLength]
0x1800a45bb  lea     r8, [rsp+228h+SourceString]
0x1800a45c0  lea     rdx, [rsp+228h+pszDest]
0x1800a45c8  mov     rcx, [rsp+228h+var_1B8]
0x1800a45cd  call    SIPolicyQuerySubVerBlock
0x1800a45d2  mov     [rsp+228h+var_1E8], eax
0x1800a45d6  test    eax, eax
0x1800a45d8  jns     loc_1800A4741
0x1800a45de  mov     ebx, r12d
0x1800a45e1  mov     [rsp+228h+var_1E8], ebx
0x1800a45e5  inc     edi
0x1800a45e7  mov     [rsp+228h+var_1C4], edi
0x1800a45eb  jmp     loc_1800A4541
0x1800a45f0  mov     r13, rsi
0x1800a45f3  mov     rcx, rsi
0x1800a45f6  movzx   eax, word ptr [rsi]
0x1800a45f9  test    ax, ax
0x1800a45fc  jz      short loc_1800A4612
0x1800a45fe  cmp     ax, r15w
0x1800a4602  jz      short loc_1800A4612
0x1800a4604  lea     rsi, [rcx+2]
0x1800a4608  mov     [rsp+228h+var_198], rsi
0x1800a4610  jmp     short loc_1800A45F3
0x1800a4612  movzx   r15d, word ptr [rdi]
0x1800a4616  add     r15, rdi
0x1800a4619  mov     [rsp+228h+var_178], r15
0x1800a4621  mov     edx, r15d
0x1800a4624  sub     edx, r14d
0x1800a4627  mov     rcx, r14
0x1800a462a  call    SIPolicyCheckVerBlock
0x1800a462f  test    rax, rax
0x1800a4632  jz      loc_1800A46CC
0x1800a4638  lea     rdx, [r14+6]; SourceString
0x1800a463c  lea     rcx, [rsp+228h+DestinationString]; DestinationString
0x1800a4644  call    cs:__imp_RtlInitUnicodeString
0x1800a464b  nop     dword ptr [rax+rax+00h]
0x1800a4650  movzx   eax, si
0x1800a4653  sub     ax, r13w
0x1800a4657  mov     [rsp+228h+String1.Length], ax
0x1800a465f  mov     [rsp+228h+String1.MaximumLength], ax
0x1800a4667  mov     [rsp+228h+String1.Buffer], r13
0x1800a466f  mov     r8b, 1; CaseInSensitive
0x1800a4672  lea     rdx, [rsp+228h+DestinationString]; String2
0x1800a467a  lea     rcx, [rsp+228h+String1]; String1
0x1800a4682  call    cs:__imp_RtlCompareUnicodeString
0x1800a4689  nop     dword ptr [rax+rax+00h]
0x1800a468e  test    eax, eax
0x1800a4690  jz      short loc_1800A46AE
0x1800a4692  movzx   eax, word ptr [r14]
0x1800a4696  add     rax, 3
0x1800a469a  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800a469e  add     r14, rax
0x1800a46a1  mov     [rsp+228h+var_190], r14
0x1800a46a9  jmp     loc_1800A4621
0x1800a46ae  mov     rdi, r14
0x1800a46b1  mov     r15d, 5Ch ; '\'
0x1800a46b7  jmp     loc_1800A4432
0x1800a46bc  add     rsi, r13
0x1800a46bf  mov     [rsp+228h+var_198], rsi
0x1800a46c7  jmp     loc_1800A4438
0x1800a46cc  mov     r13d, 2
0x1800a46d2  mov     rcx, [rsp+228h+var_1D0]
0x1800a46d7  jmp     loc_1800A44A7
0x1800a46dc  cmp     [rdi+4], dx
0x1800a46e0  jz      short loc_1800A46F6
0x1800a46e2  lea     eax, ds:0Bh[rax*2]
0x1800a46e9  mov     ecx, 0FFFFFFFCh
0x1800a46ee  and     rax, rcx
0x1800a46f1  jmp     loc_1800A4498
0x1800a46f6  cmp     r12w, r13w
0x1800a46fa  jnb     short loc_1800A46E2
0x1800a46fc  jmp     loc_1800A448E
0x1800a4701  mov     ebx, 0C000001Fh
0x1800a4706  jmp     loc_1800A44C3
0x1800a470b  mov     ecx, [rdi+30h]
0x1800a470e  shl     rcx, 20h
0x1800a4712  mov     eax, [rdi+34h]
0x1800a4715  add     rcx, rax
0x1800a4718  mov     [rsi], rcx
0x1800a471b  jmp     loc_1800A43CC
0x1800a4720  add     rax, r13
0x1800a4723  mov     [rsp+228h+pcbLength], rax
0x1800a4728  mov     rdx, [rsp+228h+SourceString]; SourceString
0x1800a472d  mov     rcx, r15; DestinationString
0x1800a4730  call    cs:__imp_RtlInitUnicodeString
0x1800a4737  nop     dword ptr [rax+rax+00h]
0x1800a473c  jmp     loc_1800A45E5
0x1800a4741  mov     rdx, [rsp+228h+pcbLength]
0x1800a4746  lea     rax, [rdx-1]
0x1800a474a  cmp     rax, 0FFFEh
0x1800a4750  ja      loc_1800A45DE
0x1800a4756  mov     al, 1
0x1800a4758  mov     [rsp+228h+var_1E4], al
0x1800a475c  mov     [rsp+228h+var_1E3], al
0x1800a4760  add     rdx, rdx; cbMax
0x1800a4763  lea     r8, [rsp+228h+pcbLength]; pcbLength
0x1800a4768  mov     rcx, [rsp+228h+SourceString]; psz
0x1800a476d  call    RtlStringCbLengthW
0x1800a4772  mov     ebx, eax
0x1800a4774  mov     [rsp+228h+var_1E8], eax
0x1800a4778  test    eax, eax
0x1800a477a  js      short loc_1800A4786
0x1800a477c  mov     rax, [rsp+228h+pcbLength]
0x1800a4781  test    rax, rax
0x1800a4784  jnz     short loc_1800A4720
0x1800a4786  mov     ebx, r12d
0x1800a4789  mov     [rsp+228h+var_1E8], ebx
0x1800a478d  jmp     short loc_1800A473C
0x1800a478f  call    __report_rangecheckfailure
0x1800a4794  jmp     short loc_1800A479C
0x1800a4796  mov     ebx, eax
  ... truncated ...
```
