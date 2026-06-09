# _RegRtlCreateTreeTransacted

- ea: `0x180001620`
- end: `0x1800018f6`
- name: `_RegRtlCreateTreeTransacted`
- size: `726`
- prototype: `__int64 __fastcall(HANDLE Handle, PCWSTR SourceString, ULONG CreateOptions, ACCESS_MASK DesiredAccess, __int64, int, PHANDLE KeyHandle, PULONG, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001304`
- `0x180066dbc`

## callees

- `0x180001490`
- `0x180001620`
- `0x180001900`
- `0x1800049f0`
- `0x18001d760`
- `0x18001df70`
- `0x18003c748`
- `0x18007d328`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001810`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180001810`
- `ntdll!NtCreateKey` at `0x180001733`
- `ntdll!NtCreateKey` at `0x180001733`
- `ntdll!NtClose` at `0x180001744`
- `ntdll!NtClose` at `0x1800018a5`
- `ntdll!NtClose` at `0x180001744`
- `ntdll!NtClose` at `0x1800018a5`
- `ntdll!RtlFreeHeap` at `0x1800018da`
- `ntdll!RtlFreeHeap` at `0x1800018da`
- `ntdll!RtlAllocateHeap` at `0x18000178e`
- `ntdll!RtlAllocateHeap` at `0x18000178e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001690`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001690`

## string_xrefs

- `0x1800017e5`: `\REGISTRY\MACHINE\`

## pseudocode

```c
__int64 __fastcall RegRtlCreateTreeTransacted(
        HANDLE Handle,
        PCWSTR SourceString,
        ULONG CreateOptions,
        ACCESS_MASK DesiredAccess,
        void *a5,
        int a6,
        PHANDLE KeyHandle,
        PULONG Disposition,
        __int64 a9)
{
  __int64 v13; // rcx
  int inited; // ebx
  int v15; // r9d
  HANDLE v16; // rcx
  int v17; // ebx
  wchar_t *Heap; // rax
  wchar_t *v19; // rsi
  unsigned __int64 v20; // rdi
  __int64 v21; // r14
  unsigned __int64 v22; // rbx
  __int64 v23; // r9
  void *v24; // r10
  __int64 v25; // r8
  HANDLE Handlea; // [rsp+50h] [rbp-61h] BYREF
  void *v28; // [rsp+58h] [rbp-59h]
  __int64 v29; // [rsp+60h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-39h] BYREF

  v29 = 0;
  v28 = 0;
  Handlea = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !(unsigned __int8)RegRtlIsPredefinedKey(Handle) || (inited = RegRtlOpenPredefinedKey(v13, &Handlea), inited >= 0) )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
    if ( inited >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.SecurityQualityOfService = 0;
      v16 = Handle;
      ObjectAttributes.Attributes = 32 * (CreateOptions & 8 | 6);
      if ( Handlea )
        v16 = Handlea;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = v16;
      ObjectAttributes.SecurityDescriptor = a5;
      if ( a9 )
      {
        inited = NtCreateKeyTransacted_Stub((_DWORD)KeyHandle, DesiredAccess, (unsigned int)&ObjectAttributes, v15);
        if ( inited == -1073741702 )
          inited = -1072103420;
      }
      else
      {
        inited = NtCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, CreateOptions, Disposition);
      }
    }
  }
  if ( Handlea )
    NtClose(Handlea);
  if ( inited == -1073741772 )
  {
    inited = RtlUnalignedStringCchLengthW(SourceString, 0x7FFF, &v29);
    if ( inited >= 0 )
    {
      v17 = v29 + 1;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * (v29 + 1));
      v19 = Heap;
      if ( Heap )
      {
        inited = RtlStringCchCopyExW((_DWORD)Heap, v17, (_DWORD)SourceString, 0, 0, 256);
        if ( !inited )
        {
          v20 = (unsigned __int64)v19;
          v21 = (__int64)Handle;
          if ( !Handle && !wcsnicmp(v19, L"\\REGISTRY\\MACHINE\\", 0x12u) )
          {
            v21 = 2147483650LL;
            v20 = (unsigned __int64)(v19 + 18);
          }
          while ( 1 )
          {
            v22 = v20;
            v20 = (unsigned __int64)wcschr((const wchar_t *)v20, 0x5Cu);
            if ( v20 )
            {
              *(_WORD *)v20 = 0;
              do
                v20 += 2LL;
              while ( *(_WORD *)v20 == 92 );
              v20 &= -(__int64)(*(_WORD *)v20 != 0);
            }
            v23 = DesiredAccess;
            v24 = a5;
            v25 = CreateOptions;
            if ( v20 )
            {
              v24 = 0;
              v25 = CreateOptions & 0xFFFFFFFC;
              v23 = 4;
            }
            inited = RegRtlCreateKeyTransacted(v21, v22, v25, v23, v24);
            if ( (HANDLE)v21 != Handle && v21 != 2147483650LL )
              NtClose((HANDLE)v21);
            if ( inited )
              break;
            if ( !v20 )
            {
              *KeyHandle = v28;
              break;
            }
            v21 = (__int64)v28;
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
      }
      else
      {
        return (unsigned int)-1073741801;
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180001620  mov     [rsp-8+arg_18], r9d
0x180001625  push    rbp
0x180001626  push    rbx
0x180001627  push    rsi
0x180001628  push    rdi
0x180001629  push    r12
0x18000162b  push    r13
0x18000162d  push    r14
0x18000162f  push    r15
0x180001631  lea     rbp, [rsp-7]
0x180001636  sub     rsp, 0B8h
0x18000163d  xorps   xmm0, xmm0
0x180001640  xor     r13d, r13d
0x180001643  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x180001647  xor     eax, eax
0x180001649  mov     [rbp+3Fh+var_90], r13
0x18000164d  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x180001651  mov     esi, r9d
0x180001654  mov     [rbp+3Fh+var_98], r13
0x180001658  mov     r12d, r8d
0x18000165b  mov     [rbp+3Fh+Handle], r13
0x18000165f  mov     rdi, rdx
0x180001662  mov     r15, rcx
0x180001665  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x180001669  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18000166d  call    _RegRtlIsPredefinedKey
0x180001672  test    al, al
0x180001674  jz      short loc_180001689
0x180001676  lea     rdx, [rbp+3Fh+Handle]
0x18000167a  call    _RegRtlOpenPredefinedKey
0x18000167f  mov     ebx, eax
0x180001681  test    eax, eax
0x180001683  js      loc_18000173B
0x180001689  mov     rdx, rdi; SourceString
0x18000168c  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180001690  call    cs:__imp_RtlInitUnicodeStringEx
0x180001696  mov     ebx, eax
0x180001698  test    eax, eax
0x18000169a  js      loc_18000173B
0x1800016a0  mov     rax, [rbp+3Fh+Handle]
0x1800016a4  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1800016a8  mov     edx, r12d
0x1800016ab  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1800016b2  and     edx, 8
0x1800016b5  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], r13
0x1800016b9  or      edx, 6
0x1800016bc  mov     rcx, r15
0x1800016bf  shl     edx, 5
0x1800016c2  test    rax, rax
0x1800016c5  mov     [rbp+3Fh+ObjectAttributes.Attributes], edx
0x1800016c8  mov     edx, esi; DesiredAccess
0x1800016ca  cmovnz  rcx, rax
0x1800016ce  lea     rax, [rbp+3Fh+DestinationString]
0x1800016d2  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rax
0x1800016d6  mov     rax, [rbp+3Fh+arg_20]
0x1800016da  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rcx
0x1800016de  mov     rcx, [rbp+3Fh+arg_40]
0x1800016e5  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], rax
0x1800016e9  mov     rax, [rbp+3Fh+arg_38]
0x1800016f0  test    rcx, rcx
0x1800016f3  jz      short loc_18000171D
0x1800016f5  mov     [rsp+0F0h+var_B8], rax
0x1800016fa  mov     [rsp+0F0h+Disposition], rcx
0x1800016ff  mov     rcx, [rbp+3Fh+KeyHandle]
0x180001703  mov     [rsp+0F0h+CreateOptions], r12d
0x180001708  call    NtCreateKeyTransacted_Stub
0x18000170d  mov     ebx, eax
0x18000170f  cmp     eax, 0C000007Ah
0x180001714  jnz     short loc_18000173B
0x180001716  mov     ebx, 0C0190004h
0x18000171b  jmp     short loc_18000173B
0x18000171d  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x180001721  xor     r9d, r9d; TitleIndex
0x180001724  mov     [rsp+0F0h+Disposition], rax; Disposition
0x180001729  mov     [rsp+0F0h+CreateOptions], r12d; CreateOptions
0x18000172e  mov     [rsp+0F0h+Class], r13; Class
0x180001733  call    cs:__imp_NtCreateKey
0x180001739  mov     ebx, eax
0x18000173b  mov     rcx, [rbp+3Fh+Handle]; Handle
0x18000173f  test    rcx, rcx
0x180001742  jz      short loc_18000174A
0x180001744  call    cs:__imp_NtClose
0x18000174a  cmp     ebx, 0C0000034h
0x180001750  jnz     loc_1800018E0
0x180001756  lea     r8, [rbp+3Fh+var_90]
0x18000175a  mov     edx, 7FFFh
0x18000175f  mov     rcx, rdi
0x180001762  call    RtlUnalignedStringCchLengthW
0x180001767  mov     ebx, eax
0x180001769  test    eax, eax
0x18000176b  js      loc_1800018E0
0x180001771  mov     rcx, gs:60h
0x18000177a  mov     edx, 8; Flags
0x18000177f  mov     rbx, [rbp+3Fh+var_90]
0x180001783  inc     rbx
0x180001786  mov     rcx, [rcx+30h]; HeapHandle
0x18000178a  lea     r8, [rbx+rbx]; Size
0x18000178e  call    cs:__imp_RtlAllocateHeap
0x180001794  mov     rsi, rax
0x180001797  test    rax, rax
0x18000179a  jnz     short loc_1800017A6
0x18000179c  mov     ebx, 0C0000017h
0x1800017a1  jmp     loc_1800018E0
0x1800017a6  mov     [rsp+0F0h+CreateOptions], 100h
0x1800017ae  xor     r9d, r9d
0x1800017b1  mov     r8, rdi
0x1800017b4  mov     [rsp+0F0h+Class], r13
0x1800017b9  mov     rdx, rbx
0x1800017bc  mov     rcx, rsi
0x1800017bf  call    RtlStringCchCopyExW
0x1800017c4  mov     ebx, eax
0x1800017c6  test    eax, eax
0x1800017c8  jnz     loc_1800018C8
0x1800017ce  mov     rdi, rsi
0x1800017d1  mov     r14, r15
0x1800017d4  mov     ebx, 80000002h
0x1800017d9  test    r15, r15
0x1800017dc  jnz     short loc_1800017FC
0x1800017de  lea     r8d, [rax+12h]; MaxCount
0x1800017e2  mov     rcx, rsi; String1
0x1800017e5  lea     rdx, aRegistryMachin_3; "\\REGISTRY\\MACHINE\\"
0x1800017ec  call    _wcsnicmp
0x1800017f1  test    eax, eax
0x1800017f3  jnz     short loc_1800017FC
0x1800017f5  mov     r14d, ebx
0x1800017f8  lea     rdi, [rsi+24h]
0x1800017fc  mov     r13d, r12d
0x1800017ff  and     r13d, 0FFFFFFFCh
0x180001803  mov     eax, 5Ch ; '\'
0x180001808  mov     rcx, rdi; Str
0x18000180b  mov     edx, eax; Ch
0x18000180d  mov     rbx, rdi
0x180001810  call    cs:__imp_wcschr
0x180001816  mov     rdi, rax
0x180001819  test    rax, rax
0x18000181c  jz      short loc_18000183B
0x18000181e  xor     eax, eax
0x180001820  mov     [rdi], ax
0x180001823  lea     ecx, [rax+5Ch]
0x180001826  add     rdi, 2
0x18000182a  movzx   eax, word ptr [rdi]
0x18000182d  cmp     ax, cx
0x180001830  jz      short loc_180001826
0x180001832  neg     ax
0x180001835  sbb     rax, rax
0x180001838  and     rdi, rax
0x18000183b  mov     r9d, [rbp+3Fh+arg_18]
0x18000183f  xor     eax, eax
0x180001841  mov     rcx, [rbp+3Fh+arg_38]
0x180001848  test    rdi, rdi
0x18000184b  mov     r10, [rbp+3Fh+arg_20]
0x18000184f  mov     r8d, r12d
0x180001852  cmovnz  rcx, rax
0x180001856  cmovnz  r10, rax
0x18000185a  mov     eax, 4
0x18000185f  cmovnz  r8d, r13d
0x180001863  cmovnz  r9d, eax
0x180001867  mov     rdx, rbx
0x18000186a  mov     rax, [rbp+3Fh+arg_40]
0x180001871  mov     [rsp+0F0h+var_B0], rax
0x180001876  lea     rax, [rbp+3Fh+var_98]
0x18000187a  mov     [rsp+0F0h+var_B8], rcx
0x18000187f  mov     rcx, r14
0x180001882  mov     [rsp+0F0h+Disposition], rax
0x180001887  mov     [rsp+0F0h+Class], r10
0x18000188c  call    _RegRtlCreateKeyTransacted
0x180001891  mov     ebx, eax
0x180001893  cmp     r14, r15
0x180001896  jz      short loc_1800018AB
0x180001898  mov     eax, 80000002h
0x18000189d  cmp     r14, rax
0x1800018a0  jz      short loc_1800018AB
0x1800018a2  mov     rcx, r14; Handle
0x1800018a5  call    cs:__imp_NtClose
0x1800018ab  test    ebx, ebx
0x1800018ad  jnz     short loc_1800018C8
0x1800018af  test    rdi, rdi
0x1800018b2  jz      short loc_1800018BD
0x1800018b4  mov     r14, [rbp+3Fh+var_98]
0x1800018b8  jmp     loc_180001803
0x1800018bd  mov     rcx, [rbp+3Fh+KeyHandle]
0x1800018c1  mov     rax, [rbp+3Fh+var_98]
0x1800018c5  mov     [rcx], rax
0x1800018c8  mov     rcx, gs:60h
0x1800018d1  mov     r8, rsi; P
0x1800018d4  xor     edx, edx; Flags
0x1800018d6  mov     rcx, [rcx+30h]; HeapHandle
0x1800018da  call    cs:__imp_RtlFreeHeap
0x1800018e0  mov     eax, ebx
0x1800018e2  add     rsp, 0B8h
0x1800018e9  pop     r15
0x1800018eb  pop     r14
0x1800018ed  pop     r13
0x1800018ef  pop     r12
0x1800018f1  pop     rdi
0x1800018f2  pop     rsi
0x1800018f3  pop     rbx
0x1800018f4  pop     rbp
0x1800018f5  retn
```
