# CsrSrvCreateSharedSection

- ea: `0x1800073d0`
- end: `0x180007716`
- name: `CsrSrvCreateSharedSection`
- size: `838`
- prototype: `NTSTATUS __fastcall(const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005180`

## callees

- `0x1800073d0`
- `0x180007720`
- `0x1800084e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800074b1`
- `ntdll!RtlAllocateHeap` at `0x18000768d`
- `ntdll!RtlAllocateHeap` at `0x1800074b1`
- `ntdll!RtlAllocateHeap` at `0x18000768d`
- `ntdll!RtlFreeUnicodeString` at `0x1800075a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800075a2`
- `ntdll!RtlCharToInteger` at `0x18000744b`
- `ntdll!RtlCharToInteger` at `0x18000744b`
- `ntdll!RtlCreateTagHeap` at `0x18000766c`
- `ntdll!RtlCreateTagHeap` at `0x18000766c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800074e0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800074e0`
- `ntdll!NtCreateSection` at `0x18000758a`
- `ntdll!NtCreateSection` at `0x18000758a`
- `ntdll!RtlAppendUnicodeToString` at `0x1800074f7`
- `ntdll!RtlAppendUnicodeToString` at `0x18000750e`
- `ntdll!RtlAppendUnicodeToString` at `0x1800074f7`
- `ntdll!RtlAppendUnicodeToString` at `0x18000750e`
- `ntdll!RtlCreateHeap` at `0x180007640`
- `ntdll!RtlCreateHeap` at `0x180007640`
- `ntdll!NtMapViewOfSection` at `0x180007605`
- `ntdll!NtMapViewOfSection` at `0x180007605`

## pseudocode

```c
NTSTATUS __fastcall CsrSrvCreateSharedSection(const char *a1)
{
  const char *i; // rax
  NTSTATUS result; // eax
  int v3; // eax
  ULONG v4; // ecx
  USHORT v5; // bx
  WCHAR *Heap; // rax
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-29h] BYREF
  __int128 v9; // [rsp+90h] [rbp+7h] BYREF
  _OWORD v10[2]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v11; // [rsp+C0h] [rbp+37h]
  ULONG Value; // [rsp+F8h] [rbp+6Fh] BYREF
  _LARGE_INTEGER MaximumSize; // [rsp+100h] [rbp+77h] BYREF
  ULONG_PTR ViewSize; // [rsp+108h] [rbp+7Fh] BYREF

  MaximumSize.QuadPart = 0;
  ViewSize = 0;
  Value = 0;
  v11 = 0;
  Destination = 0;
  v9 = 0;
  memset(v10, 0, sizeof(v10));
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
    return -1073741811;
  for ( i = a1; ; ++i )
  {
    if ( !*i )
      return -1073741811;
    if ( *i == 44 )
      break;
  }
  *i = 0;
  if ( !i[1] )
    return -1073741811;
  result = RtlCharToInteger(a1, 0, &Value);
  if ( result >= 0 )
  {
    v3 = dword_180010408;
    v4 = Value << 10;
    Value = ~(v3 - 1) & ((Value << 10) + v3 - 1);
    CsrSrvSharedSectionSize = Value;
    MaximumSize.QuadPart = ~(v3 - 1) & (v4 + v3 - 1);
    v5 = CsrDirectoryName.Length + 30;
    Heap = (WCHAR *)RtlAllocateHeap(CsrHeap, CsrBaseTag + 0x40000, (unsigned __int16)(CsrDirectoryName.Length + 30));
    if ( !Heap )
      return -1073741801;
    *(_QWORD *)&Destination.Length = 0;
    Destination.MaximumLength = v5;
    Destination.Buffer = Heap;
    RtlAppendUnicodeStringToString(&Destination, &CsrDirectoryName);
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeToString(&Destination, L"SharedSection");
    result = CsrpGenerateWorldAccessSD(0x2000Du);
    if ( result >= 0 )
    {
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.SecurityDescriptor = v10;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.SecurityQualityOfService = 0;
      result = NtCreateSection(&CsrSrvSharedSection, 0xF001Fu, &ObjectAttributes, &MaximumSize, 4u, 0x4000000u, 0);
      if ( result >= 0 )
      {
        RtlFreeUnicodeString(&Destination);
        CsrpFreeSecurityContext(&v9);
        ViewSize = 0;
        CsrSrvSharedSectionBase = 0;
        result = NtMapViewOfSection(
                   CsrSrvSharedSection,
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   &CsrSrvSharedSectionBase,
                   0,
                   0,
                   0,
                   &ViewSize,
                   ViewUnmap,
                   0x100000u,
                   4u);
        if ( result >= 0 )
        {
          CsrSrvSharedSectionHeap = CsrSrvSharedSectionBase;
          if ( RtlCreateHeap(0x7008u, CsrSrvSharedSectionBase, Value, 0x1000u, 0, 0) )
          {
            CsrSharedBaseTag = RtlCreateTagHeap(CsrSrvSharedSectionHeap, 0, (PWSTR)L"CSRSHR!", (PWSTR)L"!CSRSHR");
            CsrSrvSharedStaticServerData = (__int64)RtlAllocateHeap(CsrSrvSharedSectionHeap, CsrSharedBaseTag, 0x30u);
            if ( CsrSrvSharedStaticServerData )
            {
              *(_QWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 136LL) = CsrSrvSharedSectionBase;
              *(_QWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 152LL) = CsrSrvSharedStaticServerData;
              *(_QWORD *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 896LL) = CsrSrvSharedSectionBase;
              return 0;
            }
          }
          return -1073741801;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800073d0  mov     byte ptr [rsp-8+Value], dl
0x1800073d4  push    rbp
0x1800073d5  push    rdi
0x1800073d6  lea     rbp, [rsp-4Fh]
0x1800073db  sub     rsp, 0D8h
0x1800073e2  xor     edi, edi
0x1800073e4  xorps   xmm0, xmm0
0x1800073e7  xorps   xmm1, xmm1
0x1800073ea  mov     qword ptr [rbp+57h+MaximumSize], rdi
0x1800073ee  xor     eax, eax
0x1800073f0  mov     [rbp+57h+ViewSize], rdi
0x1800073f4  mov     [rbp+57h+Value], edi
0x1800073f7  mov     [rbp+57h+var_20], rax
0x1800073fb  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800073ff  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180007403  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x180007407  movups  [rbp+57h+var_50], xmm1
0x18000740b  movups  [rbp+57h+var_40], xmm1
0x18000740f  movups  [rbp+57h+var_30], xmm1
0x180007413  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180007417  test    rcx, rcx
0x18000741a  jz      loc_180007706
0x180007420  mov     rax, rcx
0x180007423  movzx   edx, byte ptr [rax]
0x180007426  test    dl, dl
0x180007428  jz      loc_180007706
0x18000742e  cmp     dl, 2Ch ; ','
0x180007431  jz      short loc_180007438
0x180007433  inc     rax
0x180007436  jmp     short loc_180007423
0x180007438  mov     [rax], dil
0x18000743b  cmp     [rax+1], dil
0x18000743f  jz      loc_180007706
0x180007445  lea     r8, [rbp+57h+Value]; Value
0x180007449  xor     edx, edx; Base
0x18000744b  call    cs:__imp_RtlCharToInteger
0x180007452  nop     dword ptr [rax+rax+00h]
0x180007457  test    eax, eax
0x180007459  js      loc_1800076F4
0x18000745f  mov     ecx, [rbp+57h+Value]
0x180007462  mov     eax, cs:dword_180010408
0x180007468  shl     ecx, 0Ah
0x18000746b  mov     [rsp+0E0h+var_10], rbx
0x180007473  mov     dword ptr [rbp+57h+MaximumSize+4], edi
0x180007476  lea     edx, [rax-1]
0x180007479  add     edx, ecx
0x18000747b  mov     rcx, cs:CsrHeap; HeapHandle
0x180007482  dec     eax
0x180007484  not     eax
0x180007486  and     edx, eax
0x180007488  movzx   eax, cs:CsrDirectoryName.Length
0x18000748f  mov     [rbp+57h+Value], edx
0x180007492  add     ax, 1Eh
0x180007496  mov     cs:CsrSrvSharedSectionSize, edx
0x18000749c  mov     dword ptr [rbp+57h+MaximumSize], edx
0x18000749f  mov     edx, cs:CsrBaseTag
0x1800074a5  movzx   ebx, ax
0x1800074a8  add     edx, 40000h; Flags
0x1800074ae  mov     r8d, ebx; Size
0x1800074b1  call    cs:__imp_RtlAllocateHeap
0x1800074b8  nop     dword ptr [rax+rax+00h]
0x1800074bd  test    rax, rax
0x1800074c0  jz      loc_1800076FF
0x1800074c6  xorps   xmm0, xmm0
0x1800074c9  lea     rdx, CsrDirectoryName; Source
0x1800074d0  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1800074d4  lea     rcx, [rbp+57h+Destination]; Destination
0x1800074d8  mov     [rbp+57h+Destination.MaximumLength], bx
0x1800074dc  mov     [rbp+57h+Destination.Buffer], rax
0x1800074e0  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800074e7  nop     dword ptr [rax+rax+00h]
0x1800074ec  lea     rdx, Source; "\\"
0x1800074f3  lea     rcx, [rbp+57h+Destination]; Destination
0x1800074f7  call    cs:__imp_RtlAppendUnicodeToString
0x1800074fe  nop     dword ptr [rax+rax+00h]
0x180007503  lea     rdx, aSharedsection; "SharedSection"
0x18000750a  lea     rcx, [rbp+57h+Destination]; Destination
0x18000750e  call    cs:__imp_RtlAppendUnicodeToString
0x180007515  nop     dword ptr [rax+rax+00h]
0x18000751a  lea     r8, [rbp+57h+var_50]
0x18000751e  mov     [rbp+57h+arg_0], 20004h
0x180007525  lea     rdx, [rbp+57h+arg_0]
0x180007529  mov     ecx, 2000Dh; AccessMask
0x18000752e  call    CsrpGenerateWorldAccessSD
0x180007533  test    eax, eax
0x180007535  js      loc_1800076EC
0x18000753b  lea     rax, [rbp+57h+Destination]
0x18000753f  mov     [rsp+0E0h+FileHandle], rdi; FileHandle
0x180007544  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180007548  lea     r9, [rbp+57h+MaximumSize]; MaximumSize
0x18000754c  lea     rax, [rbp+57h+var_40]
0x180007550  mov     [rsp+0E0h+AllocationAttributes], 4000000h; AllocationAttributes
0x180007558  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000755c  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180007560  mov     edx, 0F001Fh; DesiredAccess
0x180007565  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000756c  lea     rcx, CsrSrvSharedSection; SectionHandle
0x180007573  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x180007577  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000757e  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rdi
0x180007582  mov     [rsp+0E0h+SectionPageProtection], 4; SectionPageProtection
0x18000758a  call    cs:__imp_NtCreateSection
0x180007591  nop     dword ptr [rax+rax+00h]
0x180007596  test    eax, eax
0x180007598  js      loc_1800076EC
0x18000759e  lea     rcx, [rbp+57h+Destination]; UnicodeString
0x1800075a2  call    cs:__imp_RtlFreeUnicodeString
0x1800075a9  nop     dword ptr [rax+rax+00h]
0x1800075ae  lea     rcx, [rbp+57h+var_50]
0x1800075b2  call    CsrpFreeSecurityContext
0x1800075b7  mov     rcx, cs:CsrSrvSharedSection; SectionHandle
0x1800075be  lea     rax, [rbp+57h+ViewSize]
0x1800075c2  mov     [rsp+0E0h+AccessProtection], 4; AccessProtection
0x1800075ca  lea     r8, CsrSrvSharedSectionBase; BaseAddress
0x1800075d1  mov     [rsp+0E0h+AllocationType], 100000h; AllocationType
0x1800075d9  xor     r9d, r9d; ZeroBits
0x1800075dc  mov     [rsp+0E0h+InheritDisposition], 2; InheritDisposition
0x1800075e4  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800075eb  mov     [rsp+0E0h+FileHandle], rax; ViewSize
0x1800075f0  mov     qword ptr [rsp+0E0h+AllocationAttributes], rdi; SectionOffset
0x1800075f5  mov     qword ptr [rsp+0E0h+SectionPageProtection], rdi; CommitSize
0x1800075fa  mov     [rbp+57h+ViewSize], rdi
0x1800075fe  mov     cs:CsrSrvSharedSectionBase, rdi
0x180007605  call    cs:__imp_NtMapViewOfSection
0x18000760c  nop     dword ptr [rax+rax+00h]
0x180007611  test    eax, eax
0x180007613  js      loc_1800076EC
0x180007619  mov     rdx, cs:CsrSrvSharedSectionBase; HeapBase
0x180007620  mov     ecx, 7008h; Flags
0x180007625  mov     r8d, [rbp+57h+Value]; ReserveSize
0x180007629  mov     r9d, 1000h; CommitSize
0x18000762f  mov     qword ptr [rsp+0E0h+AllocationAttributes], rdi; Parameters
0x180007634  mov     cs:CsrSrvSharedSectionHeap, rdx
0x18000763b  mov     qword ptr [rsp+0E0h+SectionPageProtection], rdi; Lock
0x180007640  call    cs:__imp_RtlCreateHeap
0x180007647  nop     dword ptr [rax+rax+00h]
0x18000764c  test    rax, rax
0x18000764f  jz      loc_1800076FF
0x180007655  mov     rcx, cs:CsrSrvSharedSectionHeap; HeapHandle
0x18000765c  lea     r9, aCsrshr_0; "!CSRSHR"
0x180007663  lea     r8, aCsrshr; "CSRSHR!"
0x18000766a  xor     edx, edx; Flags
0x18000766c  call    cs:__imp_RtlCreateTagHeap
0x180007673  nop     dword ptr [rax+rax+00h]
0x180007678  mov     rcx, cs:CsrSrvSharedSectionHeap; HeapHandle
0x18000767f  mov     r8d, 30h ; '0'; Size
0x180007685  mov     edx, eax; Flags
0x180007687  mov     cs:CsrSharedBaseTag, eax
0x18000768d  call    cs:__imp_RtlAllocateHeap
0x180007694  nop     dword ptr [rax+rax+00h]
0x180007699  mov     cs:CsrSrvSharedStaticServerData, rax
0x1800076a0  test    rax, rax
0x1800076a3  jz      short loc_1800076FF
0x1800076a5  mov     rcx, gs:60h
0x1800076ae  mov     rax, cs:CsrSrvSharedSectionBase
0x1800076b5  mov     [rcx+88h], rax
0x1800076bc  mov     rcx, gs:60h
0x1800076c5  mov     rax, cs:CsrSrvSharedStaticServerData
0x1800076cc  mov     [rcx+98h], rax
0x1800076d3  mov     rcx, gs:60h
0x1800076dc  mov     rax, cs:CsrSrvSharedSectionBase
0x1800076e3  mov     [rcx+380h], rax
0x1800076ea  xor     eax, eax
0x1800076ec  mov     rbx, [rsp+0E0h+var_10]
0x1800076f4  add     rsp, 0D8h
0x1800076fb  pop     rdi
0x1800076fc  pop     rbp
0x1800076fd  retn
0x1800076ff  mov     eax, 0C0000017h
0x180007704  jmp     short loc_1800076EC
0x180007706  mov     eax, 0C000000Dh
0x18000770b  add     rsp, 0D8h
0x180007712  pop     rdi
0x180007713  pop     rbp
0x180007714  retn
```
