# BasepLoadLibraryAsDataFileInternal

- ea: `0x180051850`
- end: `0x1800520be`
- name: `BasepLoadLibraryAsDataFileInternal`
- size: `2158`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING Source@<rcx>, PCWSTR SourceString@<rdx>, PCWSTR@<r8>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004cc30`

## callees

- `0x18004b9d0`
- `0x180051850`
- `0x180053330`
- `0x180132244`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180051bdd`
- `ntdll!RtlFreeUnicodeString` at `0x180051d4e`
- `ntdll!RtlFreeUnicodeString` at `0x180051bdd`
- `ntdll!RtlFreeUnicodeString` at `0x180051d4e`
- `ntdll!RtlSetLastWin32Error` at `0x180051dd7`
- `ntdll!RtlSetLastWin32Error` at `0x180051dd7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180052063`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005207b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180052063`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005207b`
- `ntdll!NtCreateSection` at `0x180051aaf`
- `ntdll!NtCreateSection` at `0x180051db6`
- `ntdll!NtCreateSection` at `0x180051aaf`
- `ntdll!NtCreateSection` at `0x180051db6`
- `ntdll!NtMapViewOfSection` at `0x180051b0f`
- `ntdll!NtMapViewOfSection` at `0x180051e37`
- `ntdll!NtMapViewOfSection` at `0x180051b0f`
- `ntdll!NtMapViewOfSection` at `0x180051e37`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800519a0`
- `ntdll!RtlInitUnicodeStringEx` at `0x180051c97`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800519a0`
- `ntdll!RtlInitUnicodeStringEx` at `0x180051c97`
- `ntdll!NtClose` at `0x180051b71`
- `ntdll!NtClose` at `0x180051b80`
- `ntdll!NtClose` at `0x180051d24`
- `ntdll!NtClose` at `0x180051d33`
- `ntdll!NtClose` at `0x180051eaa`
- `ntdll!NtClose` at `0x180051ebb`
- `ntdll!NtClose` at `0x180051b71`
- `ntdll!NtClose` at `0x180051b80`
- `ntdll!NtClose` at `0x180051d24`
- `ntdll!NtClose` at `0x180051d33`
- `ntdll!NtClose` at `0x180051eaa`
- `ntdll!NtClose` at `0x180051ebb`
- `ntdll!NtUnmapViewOfSection` at `0x180051d13`
- `ntdll!NtUnmapViewOfSection` at `0x180051d13`
- `ntdll!RtlFreeHeap` at `0x180051f08`
- `ntdll!RtlFreeHeap` at `0x180051f08`
- `ntdll!RtlDosApplyFileIsolationRedirection_Ustr` at `0x180051911`
- `ntdll!RtlDosApplyFileIsolationRedirection_Ustr` at `0x180051911`
- `ntdll!LdrGetDllHandleByName` at `0x180051a14`
- `ntdll!LdrGetDllHandleByName` at `0x180051c65`
- `ntdll!LdrGetDllHandleByName` at `0x180051ed6`
- `ntdll!LdrGetDllHandleByName` at `0x180051a14`
- `ntdll!LdrGetDllHandleByName` at `0x180051c65`
- `ntdll!LdrGetDllHandleByName` at `0x180051ed6`
- `ntdll!RtlDosSearchPath_Ustr` at `0x1800519ef`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180051ce9`
- `ntdll!RtlDosSearchPath_Ustr` at `0x1800519ef`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180051ce9`
- `ntdll!RtlImageNtHeaderEx` at `0x180051b35`
- `ntdll!RtlImageNtHeaderEx` at `0x180051e5d`
- `ntdll!RtlImageNtHeaderEx` at `0x180051b35`
- `ntdll!RtlImageNtHeaderEx` at `0x180051e5d`
- `ntdll!LdrGetDllHandleByMapping` at `0x180051b53`
- `ntdll!LdrGetDllHandleByMapping` at `0x180051e7b`
- `ntdll!LdrGetDllHandleByMapping` at `0x180051b53`
- `ntdll!LdrGetDllHandleByMapping` at `0x180051e7b`
- `ntdll!RtlGetActiveActivationContext` at `0x180051b9d`
- `ntdll!RtlGetActiveActivationContext` at `0x180051b9d`
- `ntdll!LdrAddLoadAsDataTable` at `0x180051bc6`
- `ntdll!LdrAddLoadAsDataTable` at `0x180051bc6`
- `ntdll!LdrAppxHandleIntegrityFailure` at `0x180052093`
- `ntdll!LdrAppxHandleIntegrityFailure` at `0x180052093`
- `ntdll!RtlAllocateHeap` at `0x180052031`
- `ntdll!RtlAllocateHeap` at `0x180052031`

## pseudocode

```c
__int64 __fastcall BasepLoadLibraryAsDataFileInternal(
        struct _UNICODE_STRING *Source,
        PCWSTR SourceString,
        WCHAR *a3,
        char a4,
        unsigned __int64 *a5)
{
  char v5; // di
  NTSTATUS v10; // eax
  int DllHandleByName; // ebx
  __int64 Length; // r9
  char v13; // r8
  PWSTR Buffer; // rdx
  __int16 *v15; // rax
  __int16 v16; // cx
  const WCHAR *v17; // rcx
  HANDLE v18; // rdi
  ULONG v19; // eax
  unsigned __int64 v20; // rsi
  USHORT v22; // cx
  struct _UNICODE_STRING *p_i; // rcx
  HANDLE FileW; // rax
  NTSTATUS v25; // eax
  ULONG v26; // ecx
  unsigned int v27; // ebx
  PVOID BaseAddress; // [rsp+50h] [rbp-B0h] BYREF
  PUNICODE_STRING FullNameOut; // [rsp+58h] [rbp-A8h] BYREF
  ULONG_PTR ViewSize; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE SectionHandle; // [rsp+68h] [rbp-98h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID Context; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING StaticString; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v36; // [rsp+A8h] [rbp-58h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING i; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING PathString; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-18h]
  _BYTE v42[28]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v43; // [rsp+118h] [rbp+18h]
  char v44; // [rsp+130h] [rbp+30h] BYREF

  v5 = 0;
  StaticString.Buffer = (PWSTR)&v44;
  Context = 0;
  FullNameOut = 0;
  NtHeader = 0;
  SectionHandle = 0;
  *(_QWORD *)&StaticString.Length = 0x1000000;
  BaseAddress = 0;
  ViewSize = 0;
  DestinationString = 0;
  PathString = 0;
  *(_OWORD *)P = 0;
  i = 0;
  UnicodeString = 0;
  v10 = RtlDosApplyFileIsolationRedirection_Ustr(
          1u,
          Source,
          (PUNICODE_STRING)&DefaultExtension,
          &StaticString,
          &UnicodeString,
          &FullNameOut,
          0,
          0,
          0);
  DllHandleByName = v10;
  if ( v10 >= 0 )
  {
    DllHandleByName = LdrGetDllHandleByName(0, FullNameOut, a5);
    if ( DllHandleByName != -1073741515 )
      goto LABEL_46;
  }
  else
  {
    if ( v10 != -1072365560 )
      return (unsigned int)DllHandleByName;
    Length = Source->Length;
    v13 = 0;
    Buffer = Source->Buffer;
    v15 = (__int16 *)((char *)Buffer + Length);
    while ( --v15 >= (__int16 *)Buffer )
    {
      v16 = *v15;
      if ( *v15 == 46 )
      {
        v13 = 1;
        while ( 1 )
        {
          if ( --v15 < (__int16 *)Buffer )
            goto LABEL_32;
          if ( *v15 == 47 || *v15 == 92 )
          {
            v5 = 1;
            goto LABEL_14;
          }
        }
      }
      if ( v16 == 92 || v16 == 47 )
      {
        v5 = 1;
        goto LABEL_14;
      }
    }
LABEL_32:
    P[1] = 0;
    if ( v13 )
    {
      v22 = _mm_cvtsi128_si32(*(__m128i *)Source);
      for ( i = *Source; v22 >= 2u; i.Length = v22 )
      {
        if ( i.Buffer[((unsigned __int64)v22 >> 1) - 1] != 46 )
          break;
        v22 -= 2;
      }
      p_i = &i;
    }
    else
    {
      v27 = Length + 10;
      if ( (unsigned int)(Length + 10) > 0xFFFE )
        return (unsigned int)-1073741562;
      P[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
      if ( !P[1] )
        return (unsigned int)-1073741801;
      LOWORD(P[0]) = 0;
      WORD1(P[0]) = v27;
      RtlAppendUnicodeStringToString((PUNICODE_STRING)P, Source);
      RtlAppendUnicodeStringToString((PUNICODE_STRING)P, &DefaultExtension);
      p_i = (struct _UNICODE_STRING *)P;
    }
    FullNameOut = p_i;
    DllHandleByName = LdrGetDllHandleByName(p_i, 0, a5);
    if ( P[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    if ( DllHandleByName != -1073741515 )
      return (unsigned int)DllHandleByName;
LABEL_14:
    if ( !a3 )
      goto LABEL_15;
    DllHandleByName = RtlInitUnicodeStringEx(&PathString, a3);
    if ( DllHandleByName < 0 )
      return (unsigned int)DllHandleByName;
    a3 = 0;
    DllHandleByName = RtlDosSearchPath_Ustr(
                        6u,
                        &PathString,
                        Source,
                        (PUNICODE_STRING)&DefaultExtension,
                        &StaticString,
                        &UnicodeString,
                        &FullNameOut,
                        0,
                        0);
    if ( DllHandleByName == -1073741809 )
    {
LABEL_15:
      DllHandleByName = RtlInitUnicodeStringEx(&DestinationString, SourceString);
      if ( DllHandleByName < 0 )
        return (unsigned int)DllHandleByName;
      DllHandleByName = RtlDosSearchPath_Ustr(
                          6u,
                          &DestinationString,
                          Source,
                          (PUNICODE_STRING)&DefaultExtension,
                          &StaticString,
                          &UnicodeString,
                          &FullNameOut,
                          (PSIZE_T)a3,
                          (PSIZE_T)a3);
    }
    if ( DllHandleByName < 0 )
      return (unsigned int)DllHandleByName;
    if ( v5 )
    {
      DllHandleByName = LdrGetDllHandleByName(0, FullNameOut, a5);
      if ( DllHandleByName != -1073741515 )
        goto LABEL_46;
    }
  }
  v17 = FullNameOut->Buffer;
  if ( (a4 & 0x20) == 0 )
  {
    FileW = CreateFileW(v17, 0x80000000, 5u, 0, 3u, 0, 0);
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_72:
      DllHandleByName = NtCurrentTeb()->LastStatusValue;
      goto LABEL_46;
    }
    memset(v42, 0, sizeof(v42));
    v36 = 0;
    v41 = 0;
    v43 = 0;
    v25 = NtCreateSection(&v36, 0xF0005u, 0, 0, 2u, 0x8000000u, FileW);
    if ( v25 < 0 )
    {
      if ( v25 == -1073740702 || (unsigned int)(v25 + 1073740674) <= 1 )
        v25 = LdrAppxHandleIntegrityFailure((unsigned int)v25);
      BaseSetLastNTError((unsigned int)v25);
      SectionHandle = 0;
    }
    else
    {
      if ( v25 == 0x40000000 )
        v26 = 183;
      else
        v26 = 0;
      RtlSetLastWin32Error(v26);
      SectionHandle = v36;
      if ( v36 )
      {
        BaseAddress = 0;
        ViewSize = 0;
        DllHandleByName = NtMapViewOfSection(
                            v36,
                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                            &BaseAddress,
                            0,
                            0,
                            0,
                            &ViewSize,
                            ViewShare,
                            0,
                            2u);
        if ( DllHandleByName < 0 )
          goto LABEL_44;
        DllHandleByName = RtlImageNtHeaderEx(0, BaseAddress, ViewSize, &NtHeader);
        if ( DllHandleByName >= 0 )
        {
          DllHandleByName = LdrGetDllHandleByMapping(BaseAddress, a5);
          if ( DllHandleByName == -1073741515 )
          {
            v20 = (unsigned __int64)BaseAddress | 1;
            if ( (a4 & 0x40) == 0 )
            {
              NtClose(v18);
LABEL_58:
              NtClose(SectionHandle);
              goto LABEL_28;
            }
            DllHandleByName = BasepTrackDataFileHandle((unsigned __int64)BaseAddress | 1, v18);
            if ( DllHandleByName >= 0 )
              goto LABEL_58;
          }
        }
LABEL_43:
        NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
LABEL_44:
        NtClose(SectionHandle);
LABEL_45:
        NtClose(v18);
        goto LABEL_46;
      }
    }
    DllHandleByName = NtCurrentTeb()->LastStatusValue;
    goto LABEL_45;
  }
  v18 = CreateFileW(v17, 0xA0000000, 5u, 0, 3u, 0, 0);
  if ( v18 != (HANDLE)-1LL )
    goto LABEL_22;
  DllHandleByName = NtCurrentTeb()->LastStatusValue;
  if ( DllHandleByName != -1073741809 )
  {
    v18 = CreateFileW(FullNameOut->Buffer, 0x80000000, 5u, 0, 3u, 0, 0);
    if ( v18 != (HANDLE)-1LL )
    {
LABEL_22:
      v19 = 285212672;
      if ( (NtCurrentPeb()->BitField & 2) != 0 && (a4 & 0x42) == 0 )
        v19 = 0x1000000;
      DllHandleByName = NtCreateSection(&SectionHandle, 5u, 0, 0, 2u, v19, v18);
      if ( DllHandleByName < 0 )
        goto LABEL_45;
      BaseAddress = 0;
      ViewSize = 0;
      DllHandleByName = NtMapViewOfSection(
                          SectionHandle,
                          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                          &BaseAddress,
                          0,
                          0,
                          0,
                          &ViewSize,
                          ViewShare,
                          0x40000u,
                          2u);
      if ( DllHandleByName < 0 )
        goto LABEL_44;
      DllHandleByName = RtlImageNtHeaderEx(0, BaseAddress, ViewSize, &NtHeader);
      if ( DllHandleByName >= 0 )
      {
        DllHandleByName = LdrGetDllHandleByMapping(BaseAddress, a5);
        if ( DllHandleByName == -1073741515 )
        {
          NtClose(SectionHandle);
          NtClose(v18);
          v20 = (unsigned __int64)BaseAddress | 2;
LABEL_28:
          Context = 0;
          RtlGetActiveActivationContext(&Context);
          LdrAddLoadAsDataTable(v20, FullNameOut->Buffer, ViewSize, 0, Context);
          if ( UnicodeString.Buffer )
            RtlFreeUnicodeString(&UnicodeString);
          *a5 = v20;
          return 0;
        }
      }
      goto LABEL_43;
    }
    goto LABEL_72;
  }
LABEL_46:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)DllHandleByName;
}

```

## disassembly

```asm
0x180051850  mov     [rsp-8+arg_18], rbx
0x180051855  push    rbp
0x180051856  push    rsi
0x180051857  push    rdi
0x180051858  push    r12
0x18005185a  push    r13
0x18005185c  push    r14
0x18005185e  push    r15
0x180051860  lea     rbp, [rsp-140h]
0x180051868  sub     rsp, 240h
0x18005186f  mov     rax, cs:__security_cookie
0x180051876  xor     rax, rsp
0x180051879  mov     [rbp+170h+var_40], rax
0x180051880  mov     r14, [rbp+170h+arg_20]
0x180051887  lea     rax, [rbp+170h+var_140]
0x18005188b  xor     edi, edi
0x18005188d  mov     [rbp+170h+StaticString.Buffer], rax
0x180051891  xorps   xmm0, xmm0
0x180051894  mov     [rsp+270h+RequiredLength], rdi; RequiredLength
0x180051899  mov     [rsp+270h+FileNameSize], rdi; FileNameSize
0x18005189e  lea     rax, [rsp+270h+FullNameOut]
0x1800518a3  mov     [rsp+270h+NewFlags], rdi; NewFlags
0x1800518a8  mov     r12, rdx
0x1800518ab  mov     [rsp+270h+NewName], rax; NewName
0x1800518b0  mov     r13d, r9d
0x1800518b3  lea     rax, [rbp+170h+UnicodeString]
0x1800518b7  mov     [rbp+170h+Context], rdi
0x1800518bb  mov     r15, r8
0x1800518be  mov     [rsp+270h+DynamicString], rax; DynamicString
0x1800518c3  mov     rsi, rcx
0x1800518c6  mov     [rsp+270h+FullNameOut], rdi
0x1800518cb  xorps   xmm1, xmm1
0x1800518ce  mov     [rbp+170h+NtHeader], rdi
0x1800518d2  mov     rdx, rcx; OriginalName
0x1800518d5  mov     [rsp+270h+SectionHandle], rdi
0x1800518da  lea     r9, [rbp+170h+StaticString]; StaticString
0x1800518de  mov     qword ptr [rbp+170h+StaticString.Length], 1000000h
0x1800518e6  lea     r8, DefaultExtension; Extension
0x1800518ed  mov     [rsp+270h+BaseAddress], rdi
0x1800518f2  mov     ecx, 1; Flags
0x1800518f7  mov     [rsp+270h+ViewSize], rdi
0x1800518fc  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x180051900  movups  xmmword ptr [rbp+170h+PathString.Length], xmm1
0x180051904  movups  xmmword ptr [rsp+270h+P], xmm0
0x180051909  movups  [rbp+170h+var_1B8], xmm0
0x18005190d  movups  xmmword ptr [rbp+170h+UnicodeString.Length], xmm0
0x180051911  call    cs:__imp_RtlDosApplyFileIsolationRedirection_Ustr
0x180051918  nop     dword ptr [rax+rax+00h]
0x18005191d  mov     ebx, eax
0x18005191f  test    eax, eax
0x180051921  jns     loc_180051ECC
0x180051927  cmp     eax, 0C0150008h
0x18005192c  jnz     loc_180051BEF
0x180051932  movzx   r9d, word ptr [rsi]
0x180051936  xor     r8b, r8b
0x180051939  mov     rdx, [rsi+8]
0x18005193d  lea     rax, [rdx+r9]
0x180051941  sub     rax, 2
0x180051945  cmp     rax, rdx
0x180051948  jb      loc_180051C1C
0x18005194e  movzx   ecx, word ptr [rax]
0x180051951  cmp     cx, 2Eh ; '.'
0x180051955  jz      short loc_180051968
0x180051957  cmp     cx, 5Ch ; '\'
0x18005195b  jz      short loc_180051963
0x18005195d  cmp     cx, 2Fh ; '/'
0x180051961  jnz     short loc_180051941
0x180051963  mov     dil, 1
0x180051966  jmp     short loc_180051990
0x180051968  mov     r8b, 1
0x18005196b  nop     dword ptr [rax+rax+00h]
0x180051970  sub     rax, 2
0x180051974  cmp     rax, rdx
0x180051977  jb      loc_180051C1C
0x18005197d  movzx   ecx, word ptr [rax]
0x180051980  cmp     cx, 2Fh ; '/'
0x180051984  jz      short loc_18005198C
0x180051986  cmp     cx, 5Ch ; '\'
0x18005198a  jnz     short loc_180051970
0x18005198c  movzx   edi, r8b
0x180051990  test    r15, r15
0x180051993  jnz     loc_180051C90
0x180051999  mov     rdx, r12; SourceString
0x18005199c  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x1800519a0  call    cs:__imp_RtlInitUnicodeStringEx
0x1800519a7  nop     dword ptr [rax+rax+00h]
0x1800519ac  mov     ebx, eax
0x1800519ae  test    eax, eax
0x1800519b0  js      loc_180051BEF
0x1800519b6  mov     [rsp+270h+RequiredLength], r15; LengthNeeded
0x1800519bb  lea     rax, [rsp+270h+FullNameOut]
0x1800519c0  mov     [rsp+270h+FileNameSize], r15; FilePartSize
0x1800519c5  lea     r9, DefaultExtension; ExtensionString
0x1800519cc  mov     [rsp+270h+NewFlags], rax; FullNameOut
0x1800519d1  lea     rdx, [rbp+170h+DestinationString]; PathString
0x1800519d5  lea     rax, [rbp+170h+UnicodeString]
0x1800519d9  mov     r8, rsi; FileNameString
0x1800519dc  mov     [rsp+270h+NewName], rax; DynamicString
0x1800519e1  mov     ecx, 6; Flags
0x1800519e6  lea     rax, [rbp+170h+StaticString]
0x1800519ea  mov     [rsp+270h+DynamicString], rax; CallerBuffer
0x1800519ef  call    cs:__imp_RtlDosSearchPath_Ustr
0x1800519f6  nop     dword ptr [rax+rax+00h]
0x1800519fb  mov     ebx, eax
0x1800519fd  test    ebx, ebx
0x1800519ff  js      loc_180051BEF
0x180051a05  test    dil, dil
0x180051a08  jz      short loc_180051A2D
0x180051a0a  mov     rdx, [rsp+270h+FullNameOut]
0x180051a0f  mov     r8, r14
0x180051a12  xor     ecx, ecx
0x180051a14  call    cs:__imp_LdrGetDllHandleByName
0x180051a1b  nop     dword ptr [rax+rax+00h]
0x180051a20  mov     ebx, eax
0x180051a22  cmp     eax, 0C0000135h
0x180051a27  jnz     loc_180051D3F
0x180051a2d  xor     edi, edi
0x180051a2f  mov     rcx, [rsp+270h+FullNameOut]
0x180051a34  xor     r9d, r9d; lpSecurityAttributes
0x180051a37  mov     [rsp+270h+NewFlags], rdi; hTemplateFile
0x180051a3c  mov     r8d, 5; dwShareMode
0x180051a42  mov     dword ptr [rsp+270h+NewName], edi; dwFlagsAndAttributes
0x180051a46  mov     dword ptr [rsp+270h+DynamicString], 3; dwCreationDisposition
0x180051a4e  mov     rcx, [rcx+8]; lpFileName
0x180051a52  test    r13b, 20h
0x180051a56  jz      loc_180051D5F
0x180051a5c  mov     edx, 0A0000000h; dwDesiredAccess
0x180051a61  call    CreateFileW
0x180051a66  mov     rdi, rax
0x180051a69  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051a6d  jz      loc_180051F82
0x180051a73  xor     r15d, r15d
0x180051a76  mov     rax, gs:60h
0x180051a7f  test    byte ptr [rax+3], 2
0x180051a83  mov     eax, 11000000h
0x180051a88  jnz     loc_180051F53
0x180051a8e  mov     [rsp+270h+NewFlags], rdi; FileHandle
0x180051a93  lea     rcx, [rsp+270h+SectionHandle]; SectionHandle
0x180051a98  mov     dword ptr [rsp+270h+NewName], eax; AllocationAttributes
0x180051a9c  xor     r9d, r9d; MaximumSize
0x180051a9f  xor     r8d, r8d; ObjectAttributes
0x180051aa2  mov     dword ptr [rsp+270h+DynamicString], 2; SectionPageProtection
0x180051aaa  mov     edx, 5; DesiredAccess
0x180051aaf  call    cs:__imp_NtCreateSection
0x180051ab6  nop     dword ptr [rax+rax+00h]
0x180051abb  mov     ebx, eax
0x180051abd  test    eax, eax
0x180051abf  js      loc_180051D30
0x180051ac5  mov     rcx, [rsp+270h+SectionHandle]; SectionHandle
0x180051aca  lea     rax, [rsp+270h+ViewSize]
0x180051acf  mov     [rsp+270h+AccessProtection], 2; AccessProtection
0x180051ad7  lea     r8, [rsp+270h+BaseAddress]; BaseAddress
0x180051adc  mov     dword ptr [rsp+270h+RequiredLength], 40000h; AllocationType
0x180051ae4  xor     r9d, r9d; ZeroBits
0x180051ae7  mov     dword ptr [rsp+270h+FileNameSize], 1; InheritDisposition
0x180051aef  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180051af6  mov     [rsp+270h+NewFlags], rax; ViewSize
0x180051afb  mov     [rsp+270h+NewName], r15; SectionOffset
0x180051b00  mov     [rsp+270h+DynamicString], r15; CommitSize
0x180051b05  mov     [rsp+270h+BaseAddress], r15
0x180051b0a  mov     [rsp+270h+ViewSize], r15
0x180051b0f  call    cs:__imp_NtMapViewOfSection
0x180051b16  nop     dword ptr [rax+rax+00h]
0x180051b1b  mov     ebx, eax
0x180051b1d  test    eax, eax
0x180051b1f  js      loc_180051D1F
0x180051b25  mov     r8, [rsp+270h+ViewSize]; Size
0x180051b2a  lea     r9, [rbp+170h+NtHeader]; NtHeader
0x180051b2e  mov     rdx, [rsp+270h+BaseAddress]; BaseAddress
0x180051b33  xor     ecx, ecx; Flags
0x180051b35  call    cs:__imp_RtlImageNtHeaderEx
0x180051b3c  nop     dword ptr [rax+rax+00h]
0x180051b41  mov     ebx, eax
0x180051b43  test    eax, eax
0x180051b45  js      loc_180051D07
0x180051b4b  mov     rcx, [rsp+270h+BaseAddress]
0x180051b50  mov     rdx, r14
0x180051b53  call    cs:__imp_LdrGetDllHandleByMapping
0x180051b5a  nop     dword ptr [rax+rax+00h]
0x180051b5f  mov     ebx, eax
0x180051b61  cmp     eax, 0C0000135h
0x180051b66  jnz     loc_180051D07
0x180051b6c  mov     rcx, [rsp+270h+SectionHandle]; Handle
0x180051b71  call    cs:__imp_NtClose
0x180051b78  nop     dword ptr [rax+rax+00h]
0x180051b7d  mov     rcx, rdi; Handle
0x180051b80  call    cs:__imp_NtClose
0x180051b87  nop     dword ptr [rax+rax+00h]
0x180051b8c  mov     rsi, [rsp+270h+BaseAddress]
0x180051b91  or      rsi, 2
0x180051b95  lea     rcx, [rbp+170h+Context]; Context
0x180051b99  mov     [rbp+170h+Context], r15
0x180051b9d  call    cs:__imp_RtlGetActiveActivationContext
0x180051ba4  nop     dword ptr [rax+rax+00h]
0x180051ba9  mov     rdx, [rsp+270h+FullNameOut]
0x180051bae  xor     r9d, r9d
0x180051bb1  mov     rax, [rbp+170h+Context]
0x180051bb5  mov     rcx, rsi
0x180051bb8  mov     r8, [rsp+270h+ViewSize]
0x180051bbd  mov     [rsp+270h+DynamicString], rax
0x180051bc2  mov     rdx, [rdx+8]
0x180051bc6  call    cs:__imp_LdrAddLoadAsDataTable
0x180051bcd  nop     dword ptr [rax+rax+00h]
0x180051bd2  cmp     [rbp+170h+UnicodeString.Buffer], 0
0x180051bd7  jz      short loc_180051BE9
0x180051bd9  lea     rcx, [rbp+170h+UnicodeString]; UnicodeString
0x180051bdd  call    cs:__imp_RtlFreeUnicodeString
0x180051be4  nop     dword ptr [rax+rax+00h]
0x180051be9  mov     [r14], rsi
0x180051bec  mov     ebx, r15d
0x180051bef  mov     eax, ebx
0x180051bf1  mov     rcx, [rbp+170h+var_40]
0x180051bf8  xor     rcx, rsp; StackCookie
0x180051bfb  call    __security_check_cookie
0x180051c00  mov     rbx, [rsp+270h+arg_18]
0x180051c08  add     rsp, 240h
0x180051c0f  pop     r15
0x180051c11  pop     r14
0x180051c13  pop     r13
0x180051c15  pop     r12
0x180051c17  pop     rdi
0x180051c18  pop     rsi
0x180051c19  pop     rbp
0x180051c1a  retn
0x180051c1c  mov     [rsp+270h+P+8], rdi
0x180051c21  test    r8b, r8b
0x180051c24  jz      loc_180052006
0x180051c2a  movups  xmm0, xmmword ptr [rsi]
0x180051c2d  movd    ecx, xmm0
0x180051c31  movups  [rbp+170h+var_1B8], xmm0
0x180051c35  cmp     cx, 2
0x180051c39  jb      short loc_180051C57
0x180051c3b  mov     rdx, qword ptr [rbp+170h+var_1B8+8]
0x180051c3f  mov     r8d, 0FFFEh
0x180051c45  movzx   eax, cx
0x180051c48  shr     rax, 1
0x180051c4b  cmp     word ptr [rdx+rax*2-2], 2Eh ; '.'
0x180051c51  jz      loc_180051FEF
0x180051c57  lea     rcx, [rbp+170h+var_1B8]
0x180051c5b  mov     r8, r14
0x180051c5e  mov     [rsp+270h+FullNameOut], rcx
0x180051c63  xor     edx, edx
0x180051c65  call    cs:__imp_LdrGetDllHandleByName
0x180051c6c  nop     dword ptr [rax+rax+00h]
0x180051c71  cmp     [rsp+270h+P+8], 0
0x180051c77  mov     ebx, eax
0x180051c79  jnz     loc_180051EF4
0x180051c7f  cmp     ebx, 0C0000135h
0x180051c85  jz      loc_180051990
0x180051c8b  jmp     loc_180051BEF
0x180051c90  mov     rdx, r15; SourceString
0x180051c93  lea     rcx, [rbp+170h+PathString]; DestinationString
0x180051c97  call    cs:__imp_RtlInitUnicodeStringEx
0x180051c9e  nop     dword ptr [rax+rax+00h]
0x180051ca3  mov     ebx, eax
0x180051ca5  test    eax, eax
0x180051ca7  js      loc_180051BEF
0x180051cad  xor     r15d, r15d
0x180051cb0  lea     rax, [rsp+270h+FullNameOut]
0x180051cb5  mov     [rsp+270h+RequiredLength], r15; LengthNeeded
0x180051cba  lea     r9, DefaultExtension; ExtensionString
0x180051cc1  mov     [rsp+270h+FileNameSize], r15; FilePartSize
0x180051cc6  lea     rdx, [rbp+170h+PathString]; PathString
0x180051cca  mov     [rsp+270h+NewFlags], rax; FullNameOut
0x180051ccf  mov     r8, rsi; FileNameString
0x180051cd2  lea     rax, [rbp+170h+UnicodeString]
0x180051cd6  mov     ecx, 6; Flags
0x180051cdb  mov     [rsp+270h+NewName], rax; DynamicString
0x180051ce0  lea     rax, [rbp+170h+StaticString]
0x180051ce4  mov     [rsp+270h+DynamicString], rax; CallerBuffer
0x180051ce9  call    cs:__imp_RtlDosSearchPath_Ustr
0x180051cf0  nop     dword ptr [rax+rax+00h]
0x180051cf5  mov     ebx, eax
0x180051cf7  cmp     eax, 0C000000Fh
0x180051cfc  jz      loc_180051999
0x180051d02  jmp     loc_1800519FD
0x180051d07  mov     rdx, [rsp+270h+BaseAddress]; BaseAddress
0x180051d0c  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180051d13  call    cs:__imp_NtUnmapViewOfSection
0x180051d1a  nop     dword ptr [rax+rax+00h]
0x180051d1f  mov     rcx, [rsp+270h+SectionHandle]; Handle
0x180051d24  call    cs:__imp_NtClose
0x180051d2b  nop     dword ptr [rax+rax+00h]
0x180051d30  mov     rcx, rdi; Handle
0x180051d33  call    cs:__imp_NtClose
0x180051d3a  nop     dword ptr [rax+rax+00h]
0x180051d3f  cmp     [rbp+170h+UnicodeString.Buffer], 0
0x180051d44  jz      loc_180051BEF
0x180051d4a  lea     rcx, [rbp+170h+UnicodeString]; UnicodeString
0x180051d4e  call    cs:__imp_RtlFreeUnicodeString
0x180051d55  nop     dword ptr [rax+rax+00h]
0x180051d5a  jmp     loc_180051BEF
0x180051d5f  mov     edx, 80000000h; dwDesiredAccess
0x180051d64  call    CreateFileW
0x180051d69  mov     rdi, rax
0x180051d6c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051d70  jz      loc_180051F64
0x180051d76  xorps   xmm0, xmm0
0x180051d79  mov     [rsp+270h+NewFlags], rdi; FileHandle
0x180051d7e  movups  xmmword ptr [rbp+170h+var_178], xmm0
  ... truncated ...
```
