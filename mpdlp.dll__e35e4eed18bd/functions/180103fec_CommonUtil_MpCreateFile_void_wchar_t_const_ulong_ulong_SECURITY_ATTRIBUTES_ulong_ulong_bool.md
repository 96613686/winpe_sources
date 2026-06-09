# CommonUtil::MpCreateFile(void * *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,bool)

- ea: `0x180103fec`
- end: `0x18010445c`
- name: `?MpCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KK_N@Z`
- size: `1136`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, void **, const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, char, bool)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801760d0`
- `0x180183c68`
- `0x1801b0464`
- `0x1801f7e8c`
- `0x1801f8054`

## callees

- `0x180103fec`
- `0x18010445c`
- `0x18010cb40`
- `0x18010ce3c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18010433e`
- `ntdll!NtCreateFile` at `0x18010433e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180104164`
- `ntdll!RtlInitUnicodeStringEx` at `0x180104164`
- `ntdll!RtlNtStatusToDosError` at `0x1801043b1`
- `ntdll!RtlNtStatusToDosError` at `0x1801043b1`
- `ntdll!NtSetInformationFile` at `0x180104411`
- `ntdll!NtSetInformationFile` at `0x180104411`
- `KERNEL32!Sleep` at `0x180104353`
- `KERNEL32!Sleep` at `0x180104353`
- `KERNEL32!CloseHandle` at `0x1801040cb`
- `KERNEL32!CloseHandle` at `0x180104112`
- `KERNEL32!CloseHandle` at `0x1801042fc`
- `KERNEL32!CloseHandle` at `0x180104381`
- `KERNEL32!CloseHandle` at `0x1801043dc`
- `KERNEL32!CloseHandle` at `0x18010444d`
- `KERNEL32!CloseHandle` at `0x1801040cb`
- `KERNEL32!CloseHandle` at `0x180104112`
- `KERNEL32!CloseHandle` at `0x1801042fc`
- `KERNEL32!CloseHandle` at `0x180104381`
- `KERNEL32!CloseHandle` at `0x1801043dc`
- `KERNEL32!CloseHandle` at `0x18010444d`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpCreateFile(
        CommonUtil *this,
        wchar_t **a2,
        const wchar_t *a3,
        ULONG a4,
        __int64 a5,
        struct _SECURITY_ATTRIBUTES *a6,
        unsigned int a7,
        char a8)
{
  int v8; // r13d
  int v9; // r15d
  __int64 v10; // r9
  wchar_t **v11; // rax
  const struct std::nothrow_t *v12; // rdx
  int NtPathFromWin32; // ebx
  ULONG CreateDisposition; // r14d
  WCHAR *v16; // rcx
  WCHAR *v17; // rbx
  unsigned int v18; // edi
  bool v19; // zf
  ULONG v20; // eax
  unsigned int v21; // ecx
  int v22; // esi
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  int v26; // ecx
  ULONG CreateOptions; // r15d
  ACCESS_MASK v28; // esi
  NTSTATUS v29; // eax
  const struct std::nothrow_t *v30; // rdx
  int v31; // esi
  NTSTATUS v32; // ecx
  signed int v33; // eax
  NTSTATUS v34; // eax
  HANDLE v35; // rcx
  unsigned int v36; // [rsp+60h] [rbp-91h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-81h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-71h] BYREF
  HANDLE hObject; // [rsp+B0h] [rbp-41h] BYREF
  PCWSTR SourceString; // [rsp+B8h] [rbp-39h] BYREF
  ULONG FileInformation[2]; // [rsp+C0h] [rbp-31h] BYREF
  int v43; // [rsp+C8h] [rbp-29h] BYREF
  __int64 v44; // [rsp+CCh] [rbp-25h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-19h] BYREF

  FileInformation[0] = a4;
  v8 = 0;
  hObject = (HANDLE)-1LL;
  v9 = (int)a3;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 )
    return 2147942487LL;
  v10 = 0x7FFFFFFF;
  v11 = a2;
  do
  {
    if ( !*(_WORD *)v11 )
      break;
    v11 = (wchar_t **)((char *)v11 + 2);
    --v10;
  }
  while ( v10 );
  if ( !v10 || ((0x7FFFFFFF - v10) & -(__int64)(v10 != 0)) == 0 )
    return 2147942487LL;
  SourceString = 0;
  NtPathFromWin32 = CommonUtil::MpGetNtPathFromWin32((CommonUtil *)&SourceString, a2, (const wchar_t *)-v10);
  v36 = NtPathFromWin32;
  if ( NtPathFromWin32 < 0 )
  {
    if ( SourceString )
      operator delete((void *)SourceString, v12);
    return (unsigned int)NtPathFromWin32;
  }
  switch ( (_DWORD)a6 )
  {
    case 1:
      CreateDisposition = 2;
      break;
    case 2:
      CreateDisposition = 5;
      break;
    case 3:
      CreateDisposition = 1;
      break;
    case 4:
      CreateDisposition = 3;
      break;
    default:
      if ( (_DWORD)a6 != 5 || (CreateDisposition = 1, (v9 & 0x40000000) == 0) )
      {
        v16 = (WCHAR *)SourceString;
        if ( !SourceString )
          goto LABEL_19;
        goto LABEL_18;
      }
      break;
  }
  v17 = (WCHAR *)SourceString;
  if ( RtlInitUnicodeStringEx(&DestinationString, SourceString) < 0 )
  {
    if ( !v17 )
    {
LABEL_19:
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      return 2147942487LL;
    }
    v16 = v17;
LABEL_18:
    operator delete(v16, v12);
    goto LABEL_19;
  }
  if ( DestinationString.Length <= 1u
    || (v18 = -2147024893, v17[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92) )
  {
    v18 = -2147024891;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityQualityOfService = &v43;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.SecurityDescriptor = 0;
  v44 = 1;
  v43 = 12;
  if ( a5 )
  {
    v19 = *(_DWORD *)(a5 + 16) == 0;
    ObjectAttributes.SecurityDescriptor = *(PVOID *)(a5 + 8);
    v20 = 64;
    if ( !v19 )
      v20 = 66;
    ObjectAttributes.Attributes = v20;
  }
  v21 = ((a7 & 0x2000000) != 0 ? 0x4000 : 0)
      | ((int)a7 >> 31) & 2
      | ~(a7 >> 25) & 0x20
      | ((a7 & 0x800000 | ((a7 & 0x10000000 | ((a7 & 0x8000000 | (a7 >> 1) & 0x10000000) >> 8)) >> 12)) >> 5)
      | 0x10000;
  if ( !a8 )
    v21 = ((a7 & 0x2000000) != 0 ? 0x4000 : 0)
        | ((int)a7 >> 31) & 2
        | ~(a7 >> 25) & 0x20
        | ((a7 & 0x800000 | ((a7 & 0x10000000 | ((a7 & 0x8000000 | (a7 >> 1) & 0x10000000) >> 8)) >> 12)) >> 5);
  v22 = v9 | 0x10000;
  if ( (a7 & 0x4000000) == 0 )
    v22 = v9;
  v23 = v21 | 0x1000;
  if ( (a7 & 0x4000000) == 0 )
    v23 = v21;
  v24 = v23 | 0x200000;
  if ( (a7 & 0x200000) == 0 )
    v24 = v23;
  v25 = v24 | 0x400000;
  if ( (a7 & 0x100000) == 0 )
    v25 = v24;
  if ( (a7 & 0x2000000) != 0 )
  {
    v26 = v25;
    if ( (a7 & 0x1000010) == 0x1000010 && CreateDisposition == 2 )
      v26 = v25 | 1;
  }
  else
  {
    v26 = v25 | 0x40;
  }
  CreateOptions = v26 | 0x100;
  if ( a8 )
    CreateOptions = v26;
  v28 = v22 | 0x100080;
  LODWORD(SourceString) = v28;
  while ( 1 )
  {
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    v29 = NtCreateFile(
            &hObject,
            v28,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            a7 & 0x7FA7,
            FileInformation[0],
            CreateDisposition,
            CreateOptions,
            0,
            0);
    v31 = v29;
    if ( v29 >= 0 )
      break;
    if ( v29 != -1073741670 )
      goto LABEL_67;
    Sleep(0);
    if ( ++v8 >= 16 )
      break;
    v28 = (unsigned int)SourceString;
  }
  if ( v31 == 264 )
  {
    if ( v17 )
      operator delete(v17, v30);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return 2147942432LL;
  }
  if ( v31 < 0 )
  {
LABEL_67:
    _mm_lfence();
    if ( v31 == -1073741771 )
    {
      v18 = -2147024816;
LABEL_73:
      if ( v17 )
        operator delete(v17, v30);
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      return v18;
    }
    if ( v31 == -1073741638 )
      goto LABEL_73;
    v32 = v31;
LABEL_71:
    v33 = RtlNtStatusToDosError(v32);
    v18 = (unsigned __int16)v33 | 0x80070000;
    if ( v33 <= 0 )
      v18 = v33;
    goto LABEL_73;
  }
  if ( (_DWORD)a6 == 5 )
  {
    *(_QWORD *)FileInformation = 0;
    v34 = NtSetInformationFile(hObject, &IoStatusBlock, FileInformation, 8u, FileAllocationInformation);
    if ( v34 < 0 )
    {
      _mm_lfence();
      v32 = v34;
      goto LABEL_71;
    }
  }
  v35 = hObject;
  hObject = (HANDLE)-1LL;
  *(_QWORD *)this = v35;
  if ( v17 )
  {
    operator delete(v17, v30);
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
  }
  return v36;
}

```

## disassembly

```asm
0x180103fec  push    rbp
0x180103fee  push    rbx
0x180103fef  push    rsi
0x180103ff0  push    rdi
0x180103ff1  push    r12
0x180103ff3  push    r13
0x180103ff5  push    r14
0x180103ff7  push    r15
0x180103ff9  lea     rbp, [rsp-7]
0x180103ffe  sub     rsp, 0F8h
0x180104005  mov     rax, cs:__security_cookie
0x18010400c  xor     rax, rsp
0x18010400f  mov     [rbp+3Fh+var_48], rax
0x180104013  mov     rsi, [rbp+3Fh+arg_20]
0x180104017  xorps   xmm0, xmm0
0x18010401a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010401e  mov     [rbp+3Fh+FileInformation], r9d
0x180104022  xor     r13d, r13d
0x180104025  mov     [rsp+130h+var_C8], rcx
0x18010402a  mov     [rbp+3Fh+hObject], rdi
0x18010402e  xorps   xmm1, xmm1
0x180104031  mov     r15d, r8d
0x180104034  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180104038  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x18010403c  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180104040  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180104045  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm1
0x180104049  test    rdx, rdx
0x18010404c  jz      loc_180104118
0x180104052  mov     r10d, 7FFFFFFFh
0x180104058  lea     r12d, [rdi+2]
0x18010405c  mov     r9d, r10d
0x18010405f  mov     rax, rdx
0x180104062  cmp     [rax], r13w
0x180104066  jz      short loc_180104071
0x180104068  add     rax, 2
0x18010406c  sub     r9, r12
0x18010406f  jnz     short loc_180104062
0x180104071  sub     r10, r9
0x180104074  mov     rax, r9
0x180104077  neg     rax
0x18010407a  mov     r8, r9
0x18010407d  sbb     rcx, rcx
0x180104080  and     rcx, r10
0x180104083  neg     r8; wchar_t *
0x180104086  sbb     rax, rax
0x180104089  and     rax, rcx
0x18010408c  test    r9, r9
0x18010408f  jz      loc_180104118
0x180104095  test    rax, rax
0x180104098  jz      short loc_180104118
0x18010409a  lea     rcx, [rbp+3Fh+SourceString]; this
0x18010409e  mov     [rbp+3Fh+SourceString], r13
0x1801040a2  call    ?MpGetNtPathFromWin32@CommonUtil@@YAJPEAPEA_WPEB_W@Z; CommonUtil::MpGetNtPathFromWin32(wchar_t * *,wchar_t const *)
0x1801040a7  mov     ebx, eax
0x1801040a9  mov     [rsp+130h+var_D0], eax
0x1801040ad  shr     eax, 1Fh
0x1801040b0  test    al, al
0x1801040b2  jz      short loc_1801040D5
0x1801040b4  mov     rcx, [rbp+3Fh+SourceString]; void *
0x1801040b8  test    rcx, rcx
0x1801040bb  jz      short loc_1801040C2
0x1801040bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801040c2  mov     rcx, [rbp+3Fh+hObject]; hObject
0x1801040c6  cmp     rcx, rdi
0x1801040c9  jz      short loc_1801040D1
0x1801040cb  call    cs:__imp_CloseHandle
0x1801040d1  mov     eax, ebx
0x1801040d3  jmp     short loc_18010411D
0x1801040d5  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x1801040d8  sub     eax, r12d
0x1801040db  jz      short loc_180104152
0x1801040dd  sub     eax, r12d
0x1801040e0  jz      short loc_18010414A
0x1801040e2  sub     eax, r12d
0x1801040e5  jz      short loc_180104145
0x1801040e7  sub     eax, r12d
0x1801040ea  jz      short loc_18010413D
0x1801040ec  cmp     eax, r12d
0x1801040ef  jnz     short loc_1801040FB
0x1801040f1  mov     r14d, r12d
0x1801040f4  bt      r15d, 1Eh
0x1801040f9  jb      short loc_180104158
0x1801040fb  mov     rcx, [rbp+3Fh+SourceString]; void *
0x1801040ff  test    rcx, rcx
0x180104102  jz      short loc_180104109
0x180104104  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180104109  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18010410d  cmp     rcx, rdi
0x180104110  jz      short loc_180104118
0x180104112  call    cs:__imp_CloseHandle
0x180104118  mov     eax, 80070057h
0x18010411d  mov     rcx, [rbp+3Fh+var_48]
0x180104121  xor     rcx, rsp; StackCookie
0x180104124  call    __security_check_cookie
0x180104129  add     rsp, 0F8h
0x180104130  pop     r15
0x180104132  pop     r14
0x180104134  pop     r13
0x180104136  pop     r12
0x180104138  pop     rdi
0x180104139  pop     rsi
0x18010413a  pop     rbx
0x18010413b  pop     rbp
0x18010413c  retn
0x18010413d  mov     r14d, 3
0x180104143  jmp     short loc_180104158
0x180104145  mov     r14d, r12d
0x180104148  jmp     short loc_180104158
0x18010414a  mov     r14d, 5
0x180104150  jmp     short loc_180104158
0x180104152  mov     r14d, 2
0x180104158  mov     rbx, [rbp+3Fh+SourceString]
0x18010415c  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180104161  mov     rdx, rbx; SourceString
0x180104164  call    cs:__imp_RtlInitUnicodeStringEx
0x18010416a  test    eax, eax
0x18010416c  jns     short loc_180104178
0x18010416e  test    rbx, rbx
0x180104171  jz      short loc_180104109
0x180104173  mov     rcx, rbx
0x180104176  jmp     short loc_180104104
0x180104178  cmp     [rsp+130h+DestinationString.Length], r12w
0x18010417e  jbe     short loc_180104195
0x180104180  movzx   eax, [rsp+130h+DestinationString.Length]
0x180104185  mov     edi, 80070003h
0x18010418a  shr     rax, 1
0x18010418d  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x180104193  jz      short loc_18010419A
0x180104195  mov     edi, 80070005h
0x18010419a  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1801041a1  lea     rax, [rsp+130h+DestinationString]
0x1801041a6  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x1801041aa  lea     rax, [rbp+3Fh+var_68]
0x1801041ae  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], rax
0x1801041b2  mov     r11d, 40h ; '@'
0x1801041b8  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r13
0x1801041bc  mov     [rbp+3Fh+ObjectAttributes.Attributes], r11d
0x1801041c0  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], r13
0x1801041c4  mov     [rbp+3Fh+var_64], r12
0x1801041c8  mov     [rbp+3Fh+var_68], 0Ch
0x1801041cf  test    rsi, rsi
0x1801041d2  jz      short loc_1801041ED
0x1801041d4  mov     rax, [rsi+8]
0x1801041d8  lea     ecx, [r11+2]
0x1801041dc  cmp     [rsi+10h], r13d
0x1801041e0  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x1801041e4  mov     eax, r11d
0x1801041e7  cmovnz  eax, ecx
0x1801041ea  mov     [rbp+3Fh+ObjectAttributes.Attributes], eax
0x1801041ed  mov     r12d, [rbp+3Fh+arg_30]
0x1801041f1  mov     ecx, 10000000h
0x1801041f6  mov     r9b, [rbp+3Fh+arg_38]
0x1801041fd  mov     r10d, 10000h
0x180104203  mov     edx, r12d
0x180104206  mov     eax, r12d
0x180104209  shr     edx, 1
0x18010420b  and     eax, 8000000h
0x180104210  and     edx, ecx
0x180104212  mov     r8d, r12d
0x180104215  or      edx, eax
0x180104217  and     r8d, 2000000h
0x18010421e  shr     edx, 8
0x180104221  mov     eax, r12d
0x180104224  and     eax, ecx
0x180104226  mov     esi, r15d
0x180104229  or      edx, eax
0x18010422b  mov     eax, r12d
0x18010422e  shr     edx, 0Ch
0x180104231  and     eax, 800000h
0x180104236  or      edx, eax
0x180104238  mov     eax, r12d
0x18010423b  shr     edx, 5
0x18010423e  shr     eax, 19h
0x180104241  not     eax
0x180104243  and     eax, 20h
0x180104246  or      edx, eax
0x180104248  mov     eax, r12d
0x18010424b  sar     eax, 1Fh
0x18010424e  and     eax, 2
0x180104251  or      edx, eax
0x180104253  mov     eax, r8d
0x180104256  neg     eax
0x180104258  sbb     ecx, ecx
0x18010425a  and     ecx, 4000h
0x180104260  or      edx, ecx
0x180104262  mov     ecx, edx
0x180104264  or      ecx, r10d
0x180104267  test    r9b, r9b
0x18010426a  cmovz   ecx, edx
0x18010426d  or      esi, r10d
0x180104270  bt      r12d, 1Ah
0x180104275  mov     edx, ecx
0x180104277  mov     r10d, 200000h
0x18010427d  cmovnb  esi, r15d
0x180104281  bts     edx, 0Ch
0x180104285  bt      r12d, 1Ah
0x18010428a  cmovnb  edx, ecx
0x18010428d  mov     ecx, edx
0x18010428f  or      ecx, r10d
0x180104292  test    r10d, r12d
0x180104295  cmovz   ecx, edx
0x180104298  mov     edx, ecx
0x18010429a  bts     edx, 16h
0x18010429e  bt      r12d, 14h
0x1801042a3  cmovnb  edx, ecx
0x1801042a6  test    r8d, r8d
0x1801042a9  jnz     short loc_1801042B2
0x1801042ab  or      edx, r11d
0x1801042ae  mov     ecx, edx
0x1801042b0  jmp     short loc_1801042CE
0x1801042b2  mov     r8d, 1000010h
0x1801042b8  mov     eax, r12d
0x1801042bb  and     eax, r8d
0x1801042be  mov     ecx, edx
0x1801042c0  cmp     eax, r8d
0x1801042c3  jnz     short loc_1801042CE
0x1801042c5  cmp     r14d, 2
0x1801042c9  jnz     short loc_1801042CE
0x1801042cb  or      ecx, 1
0x1801042ce  mov     r15d, ecx
0x1801042d1  bts     r15d, 8
0x1801042d6  test    r9b, r9b
0x1801042d9  cmovnz  r15d, ecx
0x1801042dd  and     r12d, 7FA7h
0x1801042e4  or      esi, 100080h
0x1801042ea  mov     dword ptr [rbp+3Fh+SourceString], esi
0x1801042ed  jmp     short loc_1801042F2
0x1801042ef  mov     esi, dword ptr [rbp+3Fh+SourceString]
0x1801042f2  mov     rcx, [rbp+3Fh+hObject]; hObject
0x1801042f6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801042fa  jz      short loc_18010430A
0x1801042fc  call    cs:__imp_CloseHandle
0x180104302  mov     [rbp+3Fh+hObject], 0FFFFFFFFFFFFFFFFh
0x18010430a  mov     eax, [rbp+3Fh+FileInformation]
0x18010430d  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180104311  xor     ecx, ecx
0x180104313  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180104317  mov     [rsp+130h+EaLength], ecx; EaLength
0x18010431b  mov     edx, esi; DesiredAccess
0x18010431d  mov     [rsp+130h+EaBuffer], rcx; EaBuffer
0x180104322  mov     [rsp+130h+CreateOptions], r15d; CreateOptions
0x180104327  mov     [rsp+130h+CreateDisposition], r14d; CreateDisposition
0x18010432c  mov     [rsp+130h+ShareAccess], eax; ShareAccess
0x180104330  mov     [rsp+130h+FileAttributes], r12d; FileAttributes
0x180104335  mov     [rsp+130h+AllocationSize], rcx; AllocationSize
0x18010433a  lea     rcx, [rbp+3Fh+hObject]; FileHandle
0x18010433e  call    cs:__imp_NtCreateFile
0x180104344  mov     esi, eax
0x180104346  test    eax, eax
0x180104348  jns     short loc_180104362
0x18010434a  cmp     eax, 0C000009Ah
0x18010434f  jnz     short loc_180104395
0x180104351  xor     ecx, ecx; dwMilliseconds
0x180104353  call    cs:__imp_Sleep
0x180104359  inc     r13d
0x18010435c  cmp     r13d, 10h
0x180104360  jl      short loc_1801042EF
0x180104362  cmp     esi, 108h
0x180104368  jnz     short loc_180104391
0x18010436a  test    rbx, rbx
0x18010436d  jz      short loc_180104377
0x18010436f  mov     rcx, rbx; void *
0x180104372  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180104377  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18010437b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18010437f  jz      short loc_180104387
0x180104381  call    cs:__imp_CloseHandle
0x180104387  mov     eax, 80070020h
0x18010438c  jmp     loc_18010411D
0x180104391  test    esi, esi
0x180104393  jns     short loc_1801043E9
0x180104395  lfence
0x180104398  cmp     esi, 0C0000035h
0x18010439e  jnz     short loc_1801043A7
0x1801043a0  mov     edi, 80070050h
0x1801043a5  jmp     short loc_1801043C5
0x1801043a7  cmp     esi, 0C00000BAh
0x1801043ad  jz      short loc_1801043C5
0x1801043af  mov     ecx, esi; Status
0x1801043b1  call    cs:__imp_RtlNtStatusToDosError
0x1801043b7  movzx   edi, ax
0x1801043ba  or      edi, 80070000h
0x1801043c0  test    eax, eax
0x1801043c2  cmovle  edi, eax
0x1801043c5  test    rbx, rbx
0x1801043c8  jz      short loc_1801043D2
0x1801043ca  mov     rcx, rbx; void *
0x1801043cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801043d2  mov     rcx, [rbp+3Fh+hObject]; hObject
0x1801043d6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801043da  jz      short loc_1801043E2
0x1801043dc  call    cs:__imp_CloseHandle
0x1801043e2  mov     eax, edi
0x1801043e4  jmp     loc_18010411D
0x1801043e9  cmp     dword ptr [rbp+3Fh+arg_28], 5
0x1801043ed  jnz     short loc_180104422
0x1801043ef  mov     rcx, [rbp+3Fh+hObject]; FileHandle
0x1801043f3  lea     r8, [rbp+3Fh+FileInformation]; FileInformation
0x1801043f7  mov     r9d, 8; Length
  ... truncated ...
```
