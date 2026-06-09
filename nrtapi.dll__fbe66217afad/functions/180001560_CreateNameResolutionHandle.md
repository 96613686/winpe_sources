# CreateNameResolutionHandle

- ea: `0x180001560`
- end: `0x180001933`
- name: `CreateNameResolutionHandle`
- size: `979`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001434`
- `0x180001560`
- `0x18000193c`
- `0x1800019b4`
- `0x180001bb4`
- `0x180001d36`

## import_xrefs

- `ntdll!RtlCanonicalizeDomainName` at `0x180001829`
- `ntdll!RtlCanonicalizeDomainName` at `0x180001829`
- `ntdll!wcsnlen` at `0x180001730`
- `ntdll!wcsnlen` at `0x180001730`
- `ntdll!RtlFreeHeap` at `0x1800016ab`
- `ntdll!RtlFreeHeap` at `0x1800016ab`
- `ntdll!wcscpy_s` at `0x180001850`
- `ntdll!wcscpy_s` at `0x180001850`
- `ntdll!RtlInitUnicodeString` at `0x180001812`
- `ntdll!RtlInitUnicodeString` at `0x1800018b0`
- `ntdll!RtlInitUnicodeString` at `0x180001812`
- `ntdll!RtlInitUnicodeString` at `0x1800018b0`
- `ntdll!RtlFreeUnicodeString` at `0x180001688`
- `ntdll!RtlFreeUnicodeString` at `0x180001688`
- `ntdll!RtlAllocateHeap` at `0x1800017ae`
- `ntdll!RtlAllocateHeap` at `0x1800017ae`
- `ntdll!NtCreateFile` at `0x180001918`
- `ntdll!NtCreateFile` at `0x180001918`

## string_xrefs

- `0x1800017ed`: `NrtOpenPacket`

## pseudocode

```c
__int64 __fastcall CreateNameResolutionHandle(void **a1, __int64 a2)
{
  const wchar_t *v3; // rbx
  char *EaBuffer; // rdi
  void *v5; // r13
  __int64 v6; // r15
  NTSTATUS RecordCountAndDnsName; // ebx
  unsigned int v8; // esi
  __int64 v9; // r14
  void **v10; // rsi
  int CanonicalizeProxyNames; // eax
  __int16 v13; // r14
  unsigned __int16 v14; // dx
  size_t v15; // rax
  unsigned int v16; // esi
  char *Heap; // rax
  int v18; // edx
  int v19; // ecx
  ULONG EaLength; // eax
  unsigned int v21; // [rsp+64h] [rbp-75h] BYREF
  int v22; // [rsp+68h] [rbp-71h]
  int v23; // [rsp+6Ch] [rbp-6Dh]
  void *v24; // [rsp+70h] [rbp-69h] BYREF
  const wchar_t *v25; // [rsp+78h] [rbp-61h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-19h] BYREF
  struct _UNICODE_STRING v29; // [rsp+D0h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp+7h] BYREF
  int v32; // [rsp+148h] [rbp+6Fh] BYREF
  unsigned int v33; // [rsp+150h] [rbp+77h] BYREF
  size_t v34; // [rsp+158h] [rbp+7Fh] BYREF

  v21 = 0;
  v24 = 0;
  v23 = 0;
  LOWORD(v33) = 0;
  v22 = 0;
  LOWORD(v34) = 0;
  v3 = 0;
  v25 = 0;
  EaBuffer = 0;
  v5 = 0;
  LOWORD(v32) = 0;
  memset(&ObjectAttributes, 0, 44);
  v29 = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  UnicodeString = 0;
  if ( !a2 || !a1 )
    goto LABEL_12;
  v6 = *(_QWORD *)(a2 + 32);
  if ( v6 )
  {
    if ( *(_WORD *)(a2 + 24) != 1 && *(_WORD *)(a2 + 24) != 28 )
      goto LABEL_12;
    RecordCountAndDnsName = GetRecordCountAndDnsName(*(_QWORD *)(a2 + 32), &v33, &v34, &v25);
    if ( RecordCountAndDnsName < 0 )
    {
LABEL_13:
      v10 = a1;
LABEL_14:
      *v10 = 0;
      goto LABEL_15;
    }
    v23 = (unsigned __int16)v33;
    v22 = (unsigned __int16)v34;
    if ( !((unsigned __int16)v34 + (unsigned __int16)v33) )
      goto LABEL_12;
    v3 = v25;
    v33 = 4 * (unsigned __int16)v33;
    v8 = 16 * (unsigned __int16)v34;
  }
  else
  {
    v33 = 0;
    v6 = 0;
    v8 = 0;
  }
  v9 = *(_QWORD *)(a2 + 40);
  if ( !v9 )
  {
    v13 = 0;
    goto LABEL_23;
  }
  if ( v6 || !*(_WORD *)(v9 + 8) )
  {
LABEL_12:
    RecordCountAndDnsName = -1073741811;
    goto LABEL_13;
  }
  CanonicalizeProxyNames = GetCanonicalizeProxyNames(*(_QWORD *)(a2 + 40), &v24, &v32, &v21);
  v5 = v24;
  RecordCountAndDnsName = CanonicalizeProxyNames;
  if ( CanonicalizeProxyNames < 0 )
    goto LABEL_13;
  v3 = *(const wchar_t **)v9;
  v13 = v32;
LABEL_23:
  if ( v3 )
  {
    v15 = wcsnlen(v3, 0x100u);
    v14 = v15;
    v34 = v15;
  }
  else
  {
    v14 = 0;
    v34 = 0;
  }
  if ( (unsigned __int16)(v14 - 1) > 0xFEu )
    goto LABEL_12;
  if ( v33 > 0xFFFF )
    goto LABEL_12;
  if ( v8 > 0xFFFF )
    goto LABEL_12;
  if ( 2 * (unsigned __int64)v21 > 0xFFFF )
    goto LABEL_12;
  v32 = v14;
  v16 = v33 + v8 + 2 * (v21 + v14) + 40;
  if ( v16 > 0xFFFF )
    goto LABEL_12;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v16 + 25);
  EaBuffer = Heap;
  if ( !Heap )
  {
    RecordCountAndDnsName = -1073741670;
    goto LABEL_13;
  }
  memset_0(Heap, 0, v16 + 25);
  *(_DWORD *)EaBuffer = 0;
  *((_WORD *)EaBuffer + 2) = 3328;
  strcpy(EaBuffer + 8, "NrtOpenPacket");
  *((_WORD *)EaBuffer + 3) = v16;
  RtlInitUnicodeString(&DestinationString, v3);
  RecordCountAndDnsName = RtlCanonicalizeDomainName(&UnicodeString, &DestinationString, 0);
  if ( RecordCountAndDnsName < 0 )
    goto LABEL_13;
  wcscpy_s((wchar_t *)EaBuffer + 28, (unsigned int)(v32 + 1), UnicodeString.Buffer);
  v18 = (unsigned __int16)v22;
  v19 = (unsigned __int16)v23;
  *((_WORD *)EaBuffer + 27) = 2 * v34;
  *((_WORD *)EaBuffer + 14) = v21;
  *(_DWORD *)(EaBuffer + 30) = *(_DWORD *)a2;
  *(_QWORD *)(EaBuffer + 46) = *(_QWORD *)(a2 + 16);
  *(_QWORD *)(EaBuffer + 38) = *(_QWORD *)(a2 + 8);
  CopyNameResolutionInfo(v19, v18, v6, (_DWORD)v5, v13, (__int64)(EaBuffer + 22));
  RtlInitUnicodeString(&v29, L"\\Device\\NameResTrk\\Record");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &v29;
  EaLength = v16 + 25;
  ObjectAttributes.Attributes = 64;
  v10 = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  RecordCountAndDnsName = NtCreateFile(
                            a1,
                            0xC0100000,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            0,
                            3u,
                            3u,
                            0,
                            EaBuffer,
                            EaLength);
  if ( RecordCountAndDnsName < 0 )
    goto LABEL_14;
LABEL_15:
  RtlFreeUnicodeString(&UnicodeString);
  if ( EaBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
  FreeProxyNameArray(v5);
  return (unsigned int)RecordCountAndDnsName;
}

```

## disassembly

```asm
0x180001560  mov     [rsp-8+FileHandle], rcx
0x180001565  push    rbp
0x180001566  push    rbx
0x180001567  push    rsi
0x180001568  push    rdi
0x180001569  push    r12
0x18000156b  push    r13
0x18000156d  push    r14
0x18000156f  push    r15
0x180001571  lea     rbp, [rsp-1Fh]
0x180001576  sub     rsp, 0F8h
0x18000157d  xor     r8d, r8d
0x180001580  xorps   xmm0, xmm0
0x180001583  mov     r12, rdx
0x180001586  mov     [rbp+57h+var_CC], r8d
0x18000158a  mov     edx, r8d
0x18000158d  mov     [rbp+57h+var_C0], r8
0x180001591  xorps   xmm1, xmm1
0x180001594  mov     [rbp+57h+var_C4], edx
0x180001597  mov     rax, rcx
0x18000159a  mov     word ptr [rbp+57h+arg_10], dx
0x18000159e  xor     ecx, ecx
0x1800015a0  mov     [rbp+57h+var_C8], edx
0x1800015a3  mov     word ptr [rbp+57h+arg_18], dx
0x1800015a7  mov     ebx, r8d
0x1800015aa  mov     [rbp+57h+var_B8], rbx
0x1800015ae  mov     edi, r8d
0x1800015b1  mov     [rbp+57h+var_D0], r8d
0x1800015b5  mov     r13d, r8d
0x1800015b8  mov     word ptr [rbp+57h+arg_8], r8w
0x1800015bd  mov     r14d, r8d
0x1800015c0  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800015c4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800015c8  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800015cc  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x1800015d0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800015d4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800015d8  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x1800015dc  test    r12, r12
0x1800015df  jz      loc_180001674
0x1800015e5  test    rax, rax
0x1800015e8  jz      loc_180001674
0x1800015ee  mov     r15, [r12+20h]
0x1800015f3  test    r15, r15
0x1800015f6  jz      short loc_180001653
0x1800015f8  movzx   ecx, word ptr [r12+18h]
0x1800015fe  sub     ecx, 1
0x180001601  jz      short loc_180001608
0x180001603  cmp     ecx, 1Bh
0x180001606  jnz     short loc_180001674
0x180001608  lea     r9, [rbp+57h+var_B8]
0x18000160c  mov     rcx, r15
0x18000160f  lea     r8, [rbp+57h+arg_18]
0x180001613  lea     rdx, [rbp+57h+arg_10]
0x180001617  call    GetRecordCountAndDnsName
0x18000161c  xor     r8d, r8d
0x18000161f  mov     ebx, eax
0x180001621  test    eax, eax
0x180001623  js      short loc_180001679
0x180001625  movzx   eax, word ptr [rbp+57h+arg_10]
0x180001629  mov     [rbp+57h+var_C4], eax
0x18000162c  movzx   ecx, ax
0x18000162f  movzx   eax, word ptr [rbp+57h+arg_18]
0x180001633  movzx   esi, ax
0x180001636  mov     [rbp+57h+var_C8], eax
0x180001639  lea     eax, [rsi+rcx]
0x18000163c  test    eax, eax
0x18000163e  jz      short loc_180001674
0x180001640  mov     rbx, [rbp+57h+var_B8]
0x180001644  lea     eax, ds:0[rcx*4]
0x18000164b  mov     [rbp+57h+arg_10], eax
0x18000164e  shl     esi, 4
0x180001651  jmp     short loc_18000165D
0x180001653  mov     [rbp+57h+arg_10], r8d
0x180001657  mov     r15, r8
0x18000165a  mov     esi, r8d
0x18000165d  mov     r14, [r12+28h]
0x180001662  test    r14, r14
0x180001665  jz      loc_180001716
0x18000166b  test    r15, r15
0x18000166e  jz      short loc_1800016DA
0x180001670  mov     r14d, [rbp+57h+var_D0]
0x180001674  mov     ebx, 0C000000Dh
0x180001679  mov     rsi, [rbp+57h+FileHandle]
0x18000167d  mov     qword ptr [rsi], 0
0x180001684  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180001688  call    cs:__imp_RtlFreeUnicodeString
0x18000168f  nop     dword ptr [rax+rax+00h]
0x180001694  test    rdi, rdi
0x180001697  jz      short loc_1800016B7
0x180001699  mov     rcx, gs:60h
0x1800016a2  mov     r8, rdi; P
0x1800016a5  xor     edx, edx; Flags
0x1800016a7  mov     rcx, [rcx+30h]; HeapHandle
0x1800016ab  call    cs:__imp_RtlFreeHeap
0x1800016b2  nop     dword ptr [rax+rax+00h]
0x1800016b7  movzx   edx, r14w
0x1800016bb  mov     rcx, r13; P
0x1800016be  call    FreeProxyNameArray
0x1800016c3  mov     eax, ebx
0x1800016c5  add     rsp, 0F8h
0x1800016cc  pop     r15
0x1800016ce  pop     r14
0x1800016d0  pop     r13
0x1800016d2  pop     r12
0x1800016d4  pop     rdi
0x1800016d5  pop     rsi
0x1800016d6  pop     rbx
0x1800016d7  pop     rbp
0x1800016d8  retn
0x1800016da  cmp     [r14+8], r8w
0x1800016df  jz      short loc_180001670
0x1800016e1  lea     r9, [rbp+57h+var_CC]
0x1800016e5  mov     rcx, r14
0x1800016e8  lea     r8, [rbp+57h+arg_8]
0x1800016ec  lea     rdx, [rbp+57h+var_C0]
0x1800016f0  call    GetCanonicalizeProxyNames
0x1800016f5  mov     r13, [rbp+57h+var_C0]
0x1800016f9  xor     r8d, r8d
0x1800016fc  mov     ebx, eax
0x1800016fe  test    eax, eax
0x180001700  js      short loc_18000170C
0x180001702  mov     rbx, [r14]
0x180001705  movzx   r14d, word ptr [rbp+57h+arg_8]
0x18000170a  jmp     short loc_18000171A
0x18000170c  movzx   r14d, word ptr [rbp+57h+arg_8]
0x180001711  jmp     loc_180001679
0x180001716  mov     r14d, [rbp+57h+var_D0]
0x18000171a  test    rbx, rbx
0x18000171d  jnz     short loc_180001728
0x18000171f  mov     rdx, r8
0x180001722  mov     [rbp+57h+arg_18], rdx
0x180001726  jmp     short loc_180001743
0x180001728  mov     edx, 100h; MaxCount
0x18000172d  mov     rcx, rbx; Source
0x180001730  call    cs:__imp_wcsnlen
0x180001737  nop     dword ptr [rax+rax+00h]
0x18000173c  mov     rdx, rax
0x18000173f  mov     [rbp+57h+arg_18], rax
0x180001743  lea     ecx, [rdx-1]
0x180001746  mov     eax, 0FEh
0x18000174b  cmp     cx, ax
0x18000174e  ja      loc_180001674
0x180001754  mov     r8d, [rbp+57h+arg_10]
0x180001758  mov     r9d, 0FFFFh
0x18000175e  cmp     r8d, r9d
0x180001761  ja      loc_180001674
0x180001767  cmp     esi, r9d
0x18000176a  ja      loc_180001674
0x180001770  mov     ecx, [rbp+57h+var_CC]
0x180001773  mov     eax, ecx
0x180001775  add     rax, rax
0x180001778  cmp     rax, r9
0x18000177b  ja      loc_180001674
0x180001781  movzx   eax, dx
0x180001784  mov     [rbp+57h+arg_8], eax
0x180001787  add     eax, ecx
0x180001789  lea     esi, [rsi+rax*2]
0x18000178c  add     esi, 28h ; '('
0x18000178f  add     esi, r8d
0x180001792  cmp     esi, r9d
0x180001795  ja      loc_180001674
0x18000179b  mov     rcx, gs:60h
0x1800017a4  lea     r8d, [rsi+19h]; Size
0x1800017a8  xor     edx, edx; Flags
0x1800017aa  mov     rcx, [rcx+30h]; HeapHandle
0x1800017ae  call    cs:__imp_RtlAllocateHeap
0x1800017b5  nop     dword ptr [rax+rax+00h]
0x1800017ba  mov     rdi, rax
0x1800017bd  test    rax, rax
0x1800017c0  jnz     short loc_1800017CC
0x1800017c2  mov     ebx, 0C000009Ah
0x1800017c7  jmp     loc_180001679
0x1800017cc  lea     r8d, [rsi+19h]; Size
0x1800017d0  xor     edx, edx; Val
0x1800017d2  mov     rcx, rdi; void *
0x1800017d5  call    memset_0
0x1800017da  mov     dword ptr [rdi], 0
0x1800017e0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800017e4  mov     word ptr [rdi+4], 0D00h
0x1800017ea  mov     rdx, rbx; SourceString
0x1800017ed  movsd   xmm0, qword ptr cs:aNrtopenpacket; "NrtOpenPacket"
0x1800017f5  movsd   qword ptr [rdi+8], xmm0
0x1800017fa  mov     eax, dword ptr cs:aNrtopenpacket+8; "acket"
0x180001800  mov     [rdi+10h], eax
0x180001803  movzx   eax, word ptr cs:aNrtopenpacket+0Ch; "t"
0x18000180a  mov     [rdi+14h], ax
0x18000180e  mov     [rdi+6], si
0x180001812  call    cs:__imp_RtlInitUnicodeString
0x180001819  nop     dword ptr [rax+rax+00h]
0x18000181e  xor     r8d, r8d
0x180001821  lea     rdx, [rbp+57h+DestinationString]
0x180001825  lea     rcx, [rbp+57h+UnicodeString]
0x180001829  call    cs:__imp_RtlCanonicalizeDomainName
0x180001830  nop     dword ptr [rax+rax+00h]
0x180001835  mov     ebx, eax
0x180001837  test    eax, eax
0x180001839  js      loc_180001679
0x18000183f  mov     edx, [rbp+57h+arg_8]
0x180001842  lea     rbx, [rdi+16h]
0x180001846  mov     r8, [rbp+57h+UnicodeString.Buffer]; Source
0x18000184a  lea     rcx, [rbx+22h]; Destination
0x18000184e  inc     edx; SizeInWords
0x180001850  call    cs:__imp_wcscpy_s
0x180001857  nop     dword ptr [rax+rax+00h]
0x18000185c  mov     rax, [rbp+57h+arg_18]
0x180001860  mov     r9, r13
0x180001863  movzx   edx, word ptr [rbp+57h+var_C8]
0x180001867  add     ax, ax
0x18000186a  movzx   ecx, word ptr [rbp+57h+var_C4]
0x18000186e  mov     r8, r15
0x180001871  mov     [rbx+20h], ax
0x180001875  mov     eax, [rbp+57h+var_CC]
0x180001878  mov     [rbx+6], ax
0x18000187c  mov     eax, [r12]
0x180001880  mov     [rbx+8], eax
0x180001883  mov     rax, [r12+10h]
0x180001888  mov     [rbx+18h], rax
0x18000188c  mov     rax, [r12+8]
0x180001891  mov     qword ptr [rsp+130h+FileAttributes], rbx
0x180001896  mov     [rbx+10h], rax
0x18000189a  mov     word ptr [rsp+130h+AllocationSize], r14w
0x1800018a0  call    CopyNameResolutionInfo
0x1800018a5  lea     rdx, SourceString; "\\Device\\NameResTrk\\Record"
0x1800018ac  lea     rcx, [rbp+57h+var_60]; DestinationString
0x1800018b0  call    cs:__imp_RtlInitUnicodeString
0x1800018b7  nop     dword ptr [rax+rax+00h]
0x1800018bc  xor     ecx, ecx
0x1800018be  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800018c5  lea     rax, [rbp+57h+var_60]
0x1800018c9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x1800018cd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800018d1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800018d5  lea     eax, [rsi+19h]
0x1800018d8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800018df  mov     rsi, [rbp+57h+FileHandle]
0x1800018e3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800018e7  mov     [rsp+130h+EaLength], eax; EaLength
0x1800018eb  xorps   xmm0, xmm0
0x1800018ee  mov     [rsp+130h+EaBuffer], rdi; EaBuffer
0x1800018f3  lea     eax, [rcx+3]
0x1800018f6  mov     [rsp+130h+CreateOptions], ecx; CreateOptions
0x1800018fa  mov     edx, 0C0100000h; DesiredAccess
0x1800018ff  mov     [rsp+130h+CreateDisposition], eax; CreateDisposition
0x180001903  mov     [rsp+130h+ShareAccess], eax; ShareAccess
0x180001907  mov     [rsp+130h+FileAttributes], ecx; FileAttributes
0x18000190b  mov     [rsp+130h+AllocationSize], rcx; AllocationSize
0x180001910  mov     rcx, rsi; FileHandle
0x180001913  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001918  call    cs:__imp_NtCreateFile
0x18000191f  nop     dword ptr [rax+rax+00h]
0x180001924  mov     ebx, eax
0x180001926  test    eax, eax
0x180001928  jns     loc_180001684
0x18000192e  jmp     loc_18000167D
```
