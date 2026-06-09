# container::DownlevelProvider::GetCiCatalogHint(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180022fd0`
- end: `0x1800232e8`
- name: `?GetCiCatalogHint@DownlevelProvider@container@@YA?AV?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800232f0`

## callees

- `0x180002ad0`
- `0x180002ee4`
- `0x180002f1c`
- `0x18000362c`
- `0x1800051b0`
- `0x18000b4bc`
- `0x18000ca10`
- `0x180022fd0`
- `0x18002c610`
- `0x18002c634`
- `0x18002c800`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002314b`
- `ntdll!RtlFreeHeap` at `0x18002314b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18002304e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18002304e`
- `ntdll!NtClose` at `0x180023128`
- `ntdll!NtClose` at `0x180023128`
- `ntdll!NtCreateFile` at `0x1800230fa`
- `ntdll!NtCreateFile` at `0x1800230fa`
- `ntdll!RtlReleaseRelativeName` at `0x18002315b`
- `ntdll!RtlReleaseRelativeName` at `0x18002315b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall container::DownlevelProvider::GetCiCatalogHint(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rax
  __int64 v4; // rsi
  NTSTATUS CatalogHintByHandle; // ebx
  PVOID v6; // r14
  HANDLE ContainingDirectory; // rax
  int CatalogNameFromHint; // eax
  unsigned __int64 v9; // rbx
  void *v10; // r14
  int v11; // eax
  unsigned __int64 v12; // rdx
  int AllocationSize; // [rsp+20h] [rbp-A9h]
  void *FileHandle; // [rsp+60h] [rbp-69h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v17; // [rsp+78h] [rbp-51h]
  void *v18; // [rsp+80h] [rbp-49h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-39h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-9h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v2 = a2;
  v18 = 0;
  v4 = 0;
  v17 = 0;
  if ( a2[3] > 7u )
    v2 = (_QWORD *)*a2;
  *(_OWORD *)P = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&RelativeName, 0, sizeof(RelativeName));
  CatalogHintByHandle = RtlDosPathNameToRelativeNtPathName_U_WithStatus(v2, P, 0, &RelativeName);
  if ( CatalogHintByHandle >= 0 )
  {
    v6 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    CatalogHintByHandle = NtCreateFile(
                            &FileHandle,
                            0x100008u,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            0x80u,
                            7u,
                            1u,
                            0x4060u,
                            0,
                            0);
    if ( CatalogHintByHandle >= 0 )
    {
      CatalogHintByHandle = CiGetCatalogHintByHandle(FileHandle);
      v4 = v17;
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v6 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
    RtlReleaseRelativeName(&RelativeName);
  }
  if ( CatalogHintByHandle == -1073741275 || CatalogHintByHandle == -1073741772 || CatalogHintByHandle == -1073741766 )
  {
    *(_BYTE *)(a1 + 32) = 0;
    if ( v4 )
      CiFreeCatalogHint(v4);
  }
  else
  {
    if ( CatalogHintByHandle < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\downlevel_provider.cpp",
        (const char *)(unsigned int)CatalogHintByHandle,
        AllocationSize);
    LODWORD(FileHandle) = 0;
    CatalogNameFromHint = CiGetCatalogNameFromHint(v4, 0, &FileHandle);
    if ( CatalogNameFromHint < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\downlevel_provider.cpp",
        (const char *)(unsigned int)CatalogNameFromHint,
        AllocationSize);
    v9 = saturated_mul((unsigned __int64)(unsigned int)FileHandle >> 1, 2u);
    v10 = operator new[](v9);
    memset_0(v10, 0, v9);
    v18 = v10;
    v11 = CiGetCatalogNameFromHint(v4, v10, &FileHandle);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\gendrv\\silos\\container\\downlevel_provider.cpp",
        (const char *)(unsigned int)v11,
        AllocationSize);
    memset(&RelativeName, 0, sizeof(RelativeName));
    std::wstring::_Construct<1,unsigned short const *>(&RelativeName);
    *(_RTL_RELATIVE_NAME_U *)a1 = RelativeName;
    RelativeName.ContainingDirectory = 0;
    RelativeName.CurDirRef = (PRTLP_CURDIR_REF)7;
    RelativeName.RelativeName.Length = 0;
    *(_BYTE *)(a1 + 32) = 1;
    std::wstring::~wstring(&RelativeName);
    if ( v4 )
      CiFreeCatalogHint(v4);
    operator delete(v10, v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180022fd0  mov     [rsp-8+arg_10], rbx
0x180022fd5  push    rbp
0x180022fd6  push    rsi
0x180022fd7  push    rdi
0x180022fd8  push    r14
0x180022fda  push    r15
0x180022fdc  lea     rbp, [rsp-37h]
0x180022fe1  sub     rsp, 100h
0x180022fe8  mov     rax, cs:__security_cookie
0x180022fef  xor     rax, rsp
0x180022ff2  mov     [rbp+57h+var_30], rax
0x180022ff6  mov     rax, rdx
0x180022ff9  mov     rdi, rcx
0x180022ffc  mov     [rbp+57h+var_A0], rcx
0x180023000  xor     r15d, r15d
0x180023003  mov     [rbp+57h+var_A0], r15
0x180023007  mov     esi, r15d
0x18002300a  mov     [rbp+57h+var_A8], r15
0x18002300e  cmp     qword ptr [rdx+18h], 7
0x180023013  jbe     short loc_180023018
0x180023015  mov     rax, [rdx]
0x180023018  xorps   xmm0, xmm0
0x18002301b  movups  xmmword ptr [rbp+57h+P], xmm0
0x18002301f  mov     [rbp+57h+FileHandle], r15
0x180023023  xorps   xmm1, xmm1
0x180023026  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18002302a  xor     ecx, ecx
0x18002302c  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180023030  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180023034  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180023038  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18002303c  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x180023040  lea     r9, [rbp+57h+RelativeName]
0x180023044  xor     r8d, r8d
0x180023047  lea     rdx, [rbp+57h+P]
0x18002304b  mov     rcx, rax
0x18002304e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x180023055  nop     dword ptr [rax+rax+00h]
0x18002305a  mov     ebx, eax
0x18002305c  test    eax, eax
0x18002305e  js      loc_180023167
0x180023064  mov     r14, [rbp+57h+P+8]
0x180023068  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18002306c  test    ax, ax
0x18002306f  jz      short loc_180023091
0x180023071  mov     word ptr [rbp+57h+P], ax
0x180023075  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180023078  mov     dword ptr [rbp+57h+P+2], eax
0x18002307b  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18002307f  mov     word ptr [rbp+57h+P+6], ax
0x180023083  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x180023087  mov     [rbp+57h+P+8], rax
0x18002308b  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18002308f  jmp     short loc_180023098
0x180023091  mov     rax, r15
0x180023094  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180023098  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002309f  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800230a3  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800230aa  lea     rax, [rbp+57h+P]
0x1800230ae  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800230b2  xorps   xmm0, xmm0
0x1800230b5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800230ba  mov     [rsp+120h+EaLength], r15d; EaLength
0x1800230bf  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x1800230c4  mov     [rsp+120h+CreateOptions], 4060h; CreateOptions
0x1800230cc  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1800230d4  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x1800230dc  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x1800230e4  mov     [rsp+120h+AllocationSize], r15; int
0x1800230e9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800230ed  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800230f1  mov     edx, 100008h; DesiredAccess
0x1800230f6  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800230fa  call    cs:__imp_NtCreateFile
0x180023101  nop     dword ptr [rax+rax+00h]
0x180023106  mov     ebx, eax
0x180023108  test    eax, eax
0x18002310a  js      short loc_18002311F
0x18002310c  lea     rdx, [rbp+57h+var_A8]
0x180023110  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180023114  call    CiGetCatalogHintByHandle
0x180023119  mov     ebx, eax
0x18002311b  mov     rsi, [rbp+57h+var_A8]
0x18002311f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180023123  test    rcx, rcx
0x180023126  jz      short loc_180023134
0x180023128  call    cs:__imp_NtClose
0x18002312f  nop     dword ptr [rax+rax+00h]
0x180023134  test    r14, r14
0x180023137  jz      short loc_180023157
0x180023139  mov     rcx, gs:60h
0x180023142  mov     r8, r14; P
0x180023145  xor     edx, edx; Flags
0x180023147  mov     rcx, [rcx+30h]; HeapHandle
0x18002314b  call    cs:__imp_RtlFreeHeap
0x180023152  nop     dword ptr [rax+rax+00h]
0x180023157  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18002315b  call    cs:__imp_RtlReleaseRelativeName
0x180023162  nop     dword ptr [rax+rax+00h]
0x180023167  cmp     ebx, 0C0000225h
0x18002316d  jz      loc_180023270
0x180023173  cmp     ebx, 0C0000034h
0x180023179  jz      loc_180023270
0x18002317f  cmp     ebx, 0C000003Ah
0x180023185  jz      loc_180023270
0x18002318b  mov     rcx, [rbp+5Fh]; this
0x18002318f  test    ebx, ebx
0x180023191  js      loc_1800232BE
0x180023197  mov     dword ptr [rbp+57h+FileHandle], r15d
0x18002319b  lea     r8, [rbp+57h+FileHandle]
0x18002319f  xor     edx, edx
0x1800231a1  mov     rcx, rsi
0x1800231a4  call    CiGetCatalogNameFromHint
0x1800231a9  mov     rcx, [rbp+5Fh]; this
0x1800231ad  test    eax, eax
0x1800231af  js      loc_1800232D3
0x1800231b5  mov     ecx, dword ptr [rbp+57h+FileHandle]
0x1800231b8  shr     rcx, 1
0x1800231bb  mov     eax, 2
0x1800231c0  mul     rcx
0x1800231c3  mov     rbx, rax
0x1800231c6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800231cd  cmovb   rbx, rax
0x1800231d1  mov     rcx, rbx; unsigned __int64
0x1800231d4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800231d9  mov     r14, rax
0x1800231dc  mov     r8, rbx; Size
0x1800231df  xor     edx, edx; Val
0x1800231e1  mov     rcx, rax; void *
0x1800231e4  call    memset_0
0x1800231e9  mov     [rbp+57h+var_A0], r14
0x1800231ed  lea     r8, [rbp+57h+FileHandle]
0x1800231f1  mov     rdx, r14
0x1800231f4  mov     rcx, rsi
0x1800231f7  call    CiGetCatalogNameFromHint
0x1800231fc  mov     rcx, [rbp+5Fh]; this
0x180023200  test    eax, eax
0x180023202  js      loc_1800232A9
0x180023208  xorps   xmm0, xmm0
0x18002320b  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18002320f  mov     [rbp+57h+RelativeName.ContainingDirectory], r15
0x180023213  mov     [rbp+57h+RelativeName.CurDirRef], r15
0x180023217  mov     r8d, dword ptr [rbp+57h+FileHandle]
0x18002321b  shr     r8, 1
0x18002321e  mov     rdx, r14
0x180023221  lea     rcx, [rbp+57h+RelativeName]
0x180023225  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002322a  movups  xmm0, xmmword ptr [rbp+57h+RelativeName.RelativeName.Length]
0x18002322e  movups  xmmword ptr [rdi], xmm0
0x180023231  movups  xmm1, xmmword ptr [rbp+57h+RelativeName.ContainingDirectory]
0x180023235  movups  xmmword ptr [rdi+10h], xmm1
0x180023239  mov     [rbp+57h+RelativeName.ContainingDirectory], r15
0x18002323d  mov     [rbp+57h+RelativeName.CurDirRef], 7
0x180023245  mov     [rbp+57h+RelativeName.RelativeName.Length], r15w
0x18002324a  mov     byte ptr [rdi+20h], 1
0x18002324e  lea     rcx, [rbp+57h+RelativeName]
0x180023252  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023257  nop
0x180023258  test    rsi, rsi
0x18002325b  jz      short loc_180023266
0x18002325d  mov     rcx, rsi
0x180023260  call    CiFreeCatalogHint
0x180023265  nop
0x180023266  mov     rcx, r14; void *
0x180023269  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002326e  jmp     short loc_180023282
0x180023270  mov     [rdi+20h], r15b
0x180023274  test    rsi, rsi
0x180023277  jz      short loc_180023282
0x180023279  mov     rcx, rsi
0x18002327c  call    CiFreeCatalogHint
0x180023281  nop
0x180023282  mov     rax, rdi
0x180023285  mov     rcx, [rbp+57h+var_30]
0x180023289  xor     rcx, rsp; StackCookie
0x18002328c  call    __security_check_cookie
0x180023291  mov     rbx, [rsp+120h+arg_10]
0x180023299  add     rsp, 100h
0x1800232a0  pop     r15
0x1800232a2  pop     r14
0x1800232a4  pop     rdi
0x1800232a5  pop     rsi
0x1800232a6  pop     rbp
0x1800232a7  retn
0x1800232a9  mov     r9d, eax; char *
0x1800232ac  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\container"...
0x1800232b3  mov     edx, 61h ; 'a'; void *
0x1800232b8  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800232be  mov     r9d, ebx; char *
0x1800232c1  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\container"...
0x1800232c8  mov     edx, 4Dh ; 'M'; void *
0x1800232cd  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800232d3  mov     r9d, eax; char *
0x1800232d6  lea     r8, aOnecoreBaseGen_12; "onecore\\base\\gendrv\\silos\\container"...
0x1800232dd  mov     edx, 57h ; 'W'; void *
0x1800232e2  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
