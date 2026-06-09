# DiskCreateHandle(_STORAGE_DEVICE_NUMBER_EX const *,void * *,ulong)

- ea: `0x1800090a4`
- end: `0x1800092e5`
- name: `?DiskCreateHandle@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAPEAXK@Z`
- size: `577`
- prototype: `__int64 __fastcall(const struct _STORAGE_DEVICE_NUMBER_EX *, void **, ACCESS_MASK)`
- caller_count: `4`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800148f4`
- `0x1800196e0`
- `0x18001ce8c`
- `0x18001e208`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x18000891c`
- `0x180009088`
- `0x1800090a4`
- `0x18000f6b0`
- `0x180010160`
- `0x180012470`
- `0x180037620`

## import_xrefs

- `ntdll!RtlGetThreadErrorMode` at `0x1800091ea`
- `ntdll!RtlGetThreadErrorMode` at `0x1800091ea`
- `ntdll!NtOpenFile` at `0x180009236`
- `ntdll!NtOpenFile` at `0x180009236`

## string_xrefs

- `0x1800090f3`: `DiskCreateHandle`

## pseudocode

```c
__int64 __fastcall DiskCreateHandle(const struct _STORAGE_DEVICE_NUMBER_EX *a1, void **a2, ACCESS_MASK a3)
{
  USHORT Length; // cx
  __int64 v7; // r9
  USHORT v8; // dx
  USHORT v9; // ax
  __int64 DeviceNumber; // r8
  int v11; // ebx
  unsigned int v12; // ebx
  ULONG ThreadErrorMode; // eax
  NTSTATUS v14; // ebx
  struct _UNICODE_STRING v16; // [rsp+30h] [rbp-D0h] BYREF
  ULONG OldMode; // [rsp+40h] [rbp-C0h] BYREF
  char v18; // [rsp+44h] [rbp-BCh]
  void *FileHandle; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  char v21; // [rsp+54h] [rbp-ACh]
  const char *v22; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v23; // [rsp+60h] [rbp-A0h]
  USHORT v24; // [rsp+68h] [rbp-98h]
  USHORT v25; // [rsp+6Ah] [rbp-96h]
  int v26; // [rsp+6Ch] [rbp-94h]
  char *v27; // [rsp+70h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  char v30; // [rsp+C0h] [rbp-40h] BYREF

  Length = GlobalIndentString.Length;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v22 = "DiskCreateHandle";
  v8 = ++*(_WORD *)(v7 + 8);
  *(_QWORD *)(v7 + 16) = "DiskCreateHandle";
  v9 = Length;
  if ( v8 < Length )
  {
    v9 = v8;
    Length = v8;
  }
  v24 = v9;
  v26 = 0;
  v27 = off_180047060;
  v25 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"DiskCreateHandle");
  }
  *a2 = 0;
  DeviceNumber = a1->DeviceNumber;
  v16.Buffer = (PWSTR)&v30;
  *(_QWORD *)&v16.Length = 0x400000;
  IoStatusBlock = 0;
  v11 = RtlUnicodeStringPrintf(&v16, L"\\??\\PhysicalDrive%u", DeviceNumber);
  if ( v11 >= 0 )
  {
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v16;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 192;
    v18 = 0;
    ThreadErrorMode = RtlGetThreadErrorMode();
    CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
    FileHandle = 0;
    v20 = 0;
    v21 = 0;
    v14 = NtOpenFile(&FileHandle, a3, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    if ( v14 >= 0 )
    {
      *a2 = (void *)CHandleT<void *,NtHandleTrait>::Detach((__int64 *)&FileHandle);
      v12 = 0;
      v23 = 0;
    }
    else
    {
      v12 = v14 | 0x10000000;
      v23 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
          a1->DeviceNumber,
          (__int64)&v16,
          v12);
      }
    }
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    CThreadErrorMode::~CThreadErrorMode(&OldMode);
  }
  else
  {
    v12 = v11 | 0x10000000;
    v23 = v12;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v22);
  return v12;
}

```

## disassembly

```asm
0x1800090a4  mov     [rsp-8+arg_18], rbx
0x1800090a9  push    rbp
0x1800090aa  push    rsi
0x1800090ab  push    rdi
0x1800090ac  push    r12
0x1800090ae  push    r14
0x1800090b0  lea     rbp, [rsp-10h]
0x1800090b5  sub     rsp, 110h
0x1800090bc  mov     rax, cs:__security_cookie
0x1800090c3  xor     rax, rsp
0x1800090c6  mov     [rbp+30h+var_30], rax
0x1800090ca  mov     rax, gs:58h
0x1800090d3  mov     r14d, r8d
0x1800090d6  mov     r8d, cs:_tls_index
0x1800090dd  mov     rdi, rdx
0x1800090e0  mov     edx, 8
0x1800090e5  mov     rsi, rcx
0x1800090e8  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800090ef  mov     r9, [rax+r8*8]
0x1800090f3  lea     r8, aDiskcreatehand; "DiskCreateHandle"
0x1800090fa  mov     eax, 10h
0x1800090ff  mov     [rsp+130h+var_D8], r8
0x180009104  inc     word ptr [rdx+r9]
0x180009109  movzx   edx, word ptr [rdx+r9]
0x18000910e  mov     [rax+r9], r8
0x180009112  cmp     dx, cx
0x180009115  movzx   eax, cx
0x180009118  cmovb   ax, dx
0x18000911c  cmovb   cx, dx
0x180009120  mov     [rsp+130h+var_C8], ax
0x180009125  xor     eax, eax
0x180009127  mov     [rsp+130h+var_C4], eax
0x18000912b  mov     rax, cs:off_180047060; "                                       "...
0x180009132  mov     [rsp+130h+var_C0], rax
0x180009137  mov     [rsp+130h+var_C6], cx
0x18000913c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009143  lea     r12, WPP_GLOBAL_Control
0x18000914a  cmp     rcx, r12
0x18000914d  jz      short loc_180009173
0x18000914f  test    byte ptr [rcx+1Ch], 1
0x180009153  jz      short loc_180009173
0x180009155  cmp     byte ptr [rcx+19h], 5
0x180009159  jb      short loc_180009173
0x18000915b  mov     rcx, [rcx+10h]; LoggerHandle
0x18000915f  lea     r9, [rsp+130h+var_C8]
0x180009164  mov     edx, 0Dh
0x180009169  mov     qword ptr [rsp+130h+ShareAccess], r8; __int64
0x18000916e  call    WPP_SF_aZs
0x180009173  xorps   xmm0, xmm0
0x180009176  mov     qword ptr [rdi], 0
0x18000917d  mov     r8d, [rsi+10h]
0x180009181  lea     rax, [rbp+30h+var_70]
0x180009185  lea     rdx, aPhysicaldriveU; "\\??\\PhysicalDrive%u"
0x18000918c  mov     [rsp+130h+var_100.Buffer], rax
0x180009191  lea     rcx, [rsp+130h+var_100]; struct _UNICODE_STRING *
0x180009196  mov     qword ptr [rsp+130h+var_100.Length], 400000h
0x18000919f  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x1800091a3  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x1800091a8  mov     ebx, eax
0x1800091aa  test    eax, eax
0x1800091ac  jns     short loc_1800091BB
0x1800091ae  bts     ebx, 1Ch
0x1800091b2  mov     [rsp+130h+var_D0], ebx
0x1800091b6  jmp     loc_1800092B6
0x1800091bb  lea     rax, [rsp+130h+var_100]
0x1800091c0  mov     qword ptr [rsp+130h+ObjectAttributes.Length], 30h ; '0'
0x1800091c9  xorps   xmm0, xmm0
0x1800091cc  mov     [rbp+30h+ObjectAttributes.ObjectName], rax
0x1800091d0  movdqu  xmmword ptr [rbp+30h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800091d5  mov     [rbp+30h+ObjectAttributes.RootDirectory], 0
0x1800091dd  mov     qword ptr [rbp+30h+ObjectAttributes.Attributes], 0C0h
0x1800091e5  mov     [rsp+130h+var_EC], 0
0x1800091ea  call    cs:__imp_RtlGetThreadErrorMode
0x1800091f0  or      eax, 10h
0x1800091f3  lea     rcx, [rsp+130h+OldMode]; OldMode
0x1800091f8  mov     edx, eax; NewMode
0x1800091fa  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x1800091ff  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x180009203  mov     [rsp+130h+OpenOptions], 60h ; '`'; OpenOptions
0x18000920b  lea     r8, [rsp+130h+ObjectAttributes]; ObjectAttributes
0x180009210  mov     [rsp+130h+FileHandle], 0
0x180009219  mov     edx, r14d; DesiredAccess
0x18000921c  mov     [rsp+130h+var_E0], 0
0x180009224  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x180009229  mov     [rsp+130h+var_DC], 0
0x18000922e  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x180009236  call    cs:__imp_NtOpenFile
0x18000923c  mov     ebx, eax
0x18000923e  test    eax, eax
0x180009240  jns     short loc_18000928B
0x180009242  bts     ebx, 1Ch
0x180009246  mov     [rsp+130h+var_D0], ebx
0x18000924a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009251  cmp     rcx, r12
0x180009254  jz      short loc_1800092A2
0x180009256  test    byte ptr [rcx+1Ch], 1
0x18000925a  jz      short loc_1800092A2
0x18000925c  cmp     byte ptr [rcx+19h], 2
0x180009260  jb      short loc_1800092A2
0x180009262  mov     r9d, [rsi+10h]
0x180009266  lea     rax, [rsp+130h+var_100]
0x18000926b  mov     rcx, [rcx+10h]
0x18000926f  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x180009276  mov     edx, 72h ; 'r'
0x18000927b  mov     [rsp+130h+OpenOptions], ebx
0x18000927f  mov     qword ptr [rsp+130h+ShareAccess], rax
0x180009284  call    WPP_SF_DZd
0x180009289  jmp     short loc_1800092A2
0x18000928b  lea     rcx, [rsp+130h+FileHandle]
0x180009290  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x180009295  mov     [rdi], rax
0x180009298  xor     ebx, ebx
0x18000929a  mov     [rsp+130h+var_D0], 0
0x1800092a2  lea     rcx, [rsp+130h+FileHandle]
0x1800092a7  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800092ac  lea     rcx, [rsp+130h+OldMode]; this
0x1800092b1  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x1800092b6  lea     rcx, [rsp+130h+var_D8]; this
0x1800092bb  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800092c0  mov     eax, ebx
0x1800092c2  mov     rcx, [rbp+30h+var_30]
0x1800092c6  xor     rcx, rsp; StackCookie
0x1800092c9  call    __security_check_cookie
0x1800092ce  mov     rbx, [rsp+130h+arg_18]
0x1800092d6  add     rsp, 110h
0x1800092dd  pop     r14
0x1800092df  pop     r12
0x1800092e1  pop     rdi
0x1800092e2  pop     rsi
0x1800092e3  pop     rbp
0x1800092e4  retn
```
