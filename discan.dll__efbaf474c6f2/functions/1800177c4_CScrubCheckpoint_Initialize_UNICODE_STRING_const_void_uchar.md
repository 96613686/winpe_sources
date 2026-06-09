# CScrubCheckpoint::Initialize(_UNICODE_STRING const *,void *,uchar)

- ea: `0x1800177c4`
- end: `0x180017a77`
- name: `?Initialize@CScrubCheckpoint@@QEAAJPEBU_UNICODE_STRING@@PEAXE@Z`
- size: `691`
- prototype: `__int64 __fastcall(CScrubCheckpoint *this, struct _UNICODE_STRING *, void *, char)`
- caller_count: `5`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000fa0c`
- `0x18000fbc0`
- `0x18000fd70`
- `0x18000ff90`
- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006470`
- `0x180006498`
- `0x180006688`
- `0x1800129b0`
- `0x180017698`
- `0x1800177c4`
- `0x180018130`
- `0x1800375ee`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800178e0`
- `ntdll!NtOpenFile` at `0x1800178e0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800179e9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800179e9`

## pseudocode

```c
__int64 __fastcall CScrubCheckpoint::Initialize(CScrubCheckpoint *this, struct _UNICODE_STRING *a2, void *a3, char a4)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v9; // r11
  USHORT v10; // dx
  USHORT v11; // ax
  NTSTATUS v12; // eax
  NTSTATUS v13; // edi
  unsigned int v14; // edi
  void *v15; // rax
  int Checkpoint; // eax
  int v17; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-50h] BYREF
  const char *v20; // [rsp+40h] [rbp-40h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp+30h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+40h] BYREF

  FileHandle = a3;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v20 = "CScrubCheckpoint::Initialize";
  v9 = ThreadLocalStoragePointer[tls_index];
  v10 = ++*(_WORD *)(v9 + 8);
  *(_QWORD *)(v9 + 16) = "CScrubCheckpoint::Initialize";
  v11 = Length;
  if ( v10 < Length )
  {
    v11 = v10;
    Length = v10;
  }
  LOWORD(IoStatusBlock.Status) = v11;
  HIDWORD(IoStatusBlock.Pointer) = 0;
  IoStatusBlock.Information = (ULONG_PTR)off_180047060;
  WORD1(IoStatusBlock.Pointer) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubCheckpoint::Initialize");
    a3 = FileHandle;
  }
  *(_QWORD *)this = a2;
  if ( a3 )
  {
    *((_QWORD *)this + 1) = a3;
LABEL_16:
    LOBYTE(SystemTimeAsFileTime.dwLowDateTime) = 0;
    Checkpoint = CScrubCheckpoint::_ReadCheckpoint(this, (unsigned __int8 *)&SystemTimeAsFileTime);
    if ( a4 && LOBYTE(SystemTimeAsFileTime.dwLowDateTime) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids);
      }
      v17 = CScrubCheckpoint::ClearCheckpoint(this, 0);
      v21 = v17;
      v14 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
            (_DWORD)a2,
            v17);
        }
        goto LABEL_35;
      }
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *((struct _FILETIME *)this + 7) = SystemTimeAsFileTime;
    }
    else if ( Checkpoint < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
          (unsigned int)Checkpoint);
      }
      memset_0(*((void **)this + 5), 0, 0x120u);
      **((_DWORD **)this + 5) = 296;
    }
    v21 = 0;
    v14 = 0;
    goto LABEL_35;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = NtOpenFile(&FileHandle, 0x1000A1u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v15 = FileHandle;
    *((_QWORD *)this + 2) = FileHandle;
    *((_QWORD *)this + 1) = v15;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Zd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
      (_DWORD)a2,
      v12);
  }
  v14 = v13 | 0x10000000;
  v21 = v14;
LABEL_35:
  CHResultImp::~CHResultImp((CHResultImp *)&v20);
  return v14;
}

```

## disassembly

```asm
0x1800177c4  mov     [rsp-28h+arg_8], rbx
0x1800177c9  mov     [rsp-28h+FileHandle], r8
0x1800177ce  push    rbp
0x1800177cf  push    rsi
0x1800177d0  push    rdi
0x1800177d1  push    r13
0x1800177d3  push    r14
0x1800177d5  mov     rbp, rsp
0x1800177d8  sub     rsp, 80h
0x1800177df  mov     rax, gs:58h
0x1800177e8  mov     rsi, rdx
0x1800177eb  mov     r10d, cs:_tls_index
0x1800177f2  mov     rbx, rcx
0x1800177f5  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800177fc  mov     r14b, r9b
0x1800177ff  mov     edx, 8
0x180017804  lea     r9, aCscrubcheckpoi; "CScrubCheckpoint::Initialize"
0x18001780b  mov     [rbp+var_40], r9
0x18001780f  mov     r11, [rax+r10*8]
0x180017813  mov     eax, 10h
0x180017818  inc     word ptr [rdx+r11]
0x18001781d  movzx   edx, word ptr [rdx+r11]
0x180017822  mov     [rax+r11], r9
0x180017826  cmp     dx, cx
0x180017829  movzx   eax, cx
0x18001782c  cmovb   ax, dx
0x180017830  cmovb   cx, dx
0x180017834  mov     word ptr [rbp+IoStatusBlock], ax
0x180017838  xor     eax, eax
0x18001783a  mov     dword ptr [rbp+IoStatusBlock+4], eax
0x18001783d  mov     rax, cs:off_180047060; "                                       "...
0x180017844  mov     [rbp+IoStatusBlock.Information], rax
0x180017848  mov     word ptr [rbp+IoStatusBlock+2], cx
0x18001784c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017853  lea     r13, WPP_GLOBAL_Control
0x18001785a  cmp     rcx, r13
0x18001785d  jz      short loc_180017886
0x18001785f  test    byte ptr [rcx+1Ch], 1
0x180017863  jz      short loc_180017886
0x180017865  cmp     byte ptr [rcx+19h], 5
0x180017869  jb      short loc_180017886
0x18001786b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001786f  mov     edx, 0Dh
0x180017874  mov     qword ptr [rsp+80h+ShareAccess], r9; __int64
0x180017879  lea     r9, [rbp+IoStatusBlock]
0x18001787d  call    WPP_SF_aZs
0x180017882  mov     r8, [rbp+FileHandle]
0x180017886  mov     [rbx], rsi
0x180017889  test    r8, r8
0x18001788c  jz      short loc_180017897
0x18001788e  mov     [rbx+8], r8
0x180017892  jmp     loc_180017938
0x180017897  xorps   xmm0, xmm0
0x18001789a  mov     [rsp+80h+OpenOptions], 0; OpenOptions
0x1800178a2  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1800178a6  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800178ae  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800178b2  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800178ba  mov     edx, 1000A1h; DesiredAccess
0x1800178bf  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x1800178c3  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800178c7  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800178cf  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800178d3  mov     [rsp+80h+ShareAccess], 7; ShareAccess
0x1800178db  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800178e0  call    cs:__imp_NtOpenFile
0x1800178e6  mov     edi, eax
0x1800178e8  test    eax, eax
0x1800178ea  jns     short loc_18001792C
0x1800178ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800178f3  cmp     rcx, r13
0x1800178f6  jz      short loc_180017920
0x1800178f8  test    byte ptr [rcx+1Ch], 1
0x1800178fc  jz      short loc_180017920
0x1800178fe  cmp     byte ptr [rcx+19h], 2
0x180017902  jb      short loc_180017920
0x180017904  mov     rcx, [rcx+10h]
0x180017908  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x18001790f  mov     edx, 0Ah
0x180017914  mov     [rsp+80h+ShareAccess], eax
0x180017918  mov     r9, rsi
0x18001791b  call    WPP_SF_Zd
0x180017920  bts     edi, 1Ch
0x180017924  mov     [rbp+var_38], edi
0x180017927  jmp     loc_180017A55
0x18001792c  mov     rax, [rbp+FileHandle]
0x180017930  mov     [rbx+10h], rax
0x180017934  mov     [rbx+8], rax
0x180017938  lea     rdx, [rbp+SystemTimeAsFileTime]; unsigned __int8 *
0x18001793c  mov     byte ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180017940  mov     rcx, rbx; this
0x180017943  call    ?_ReadCheckpoint@CScrubCheckpoint@@AEAAJPEAE@Z; CScrubCheckpoint::_ReadCheckpoint(uchar *)
0x180017948  test    r14b, r14b
0x18001794b  jz      loc_1800179FD
0x180017951  cmp     byte ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180017955  jz      loc_1800179FD
0x18001795b  mov     rcx, cs:WPP_GLOBAL_Control
0x180017962  cmp     rcx, r13
0x180017965  jz      short loc_180017988
0x180017967  test    byte ptr [rcx+1Ch], 1
0x18001796b  jz      short loc_180017988
0x18001796d  cmp     byte ptr [rcx+19h], 4
0x180017971  jb      short loc_180017988
0x180017973  mov     rcx, [rcx+10h]
0x180017977  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x18001797e  mov     edx, 0Bh
0x180017983  call    WPP_SF_
0x180017988  xor     edx, edx; unsigned int
0x18001798a  mov     rcx, rbx; this
0x18001798d  call    ?ClearCheckpoint@CScrubCheckpoint@@QEAAJK@Z; CScrubCheckpoint::ClearCheckpoint(ulong)
0x180017992  mov     [rbp+var_38], eax
0x180017995  mov     edi, eax
0x180017997  test    eax, eax
0x180017999  jns     short loc_1800179DD
0x18001799b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800179a2  cmp     rcx, r13
0x1800179a5  jz      loc_180017A55
0x1800179ab  test    byte ptr [rcx+1Ch], 1
0x1800179af  jz      loc_180017A55
0x1800179b5  cmp     byte ptr [rcx+19h], 2
0x1800179b9  jb      loc_180017A55
0x1800179bf  mov     rcx, [rcx+10h]
0x1800179c3  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x1800179ca  mov     edx, 0Ch
0x1800179cf  mov     [rsp+80h+ShareAccess], eax
0x1800179d3  mov     r9, rsi
0x1800179d6  call    WPP_SF_Zd
0x1800179db  jmp     short loc_180017A55
0x1800179dd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800179e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800179e9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800179ef  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800179f2  mov     [rbx+38h], eax
0x1800179f5  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800179f8  mov     [rbx+3Ch], eax
0x1800179fb  jmp     short loc_180017A4C
0x1800179fd  test    eax, eax
0x1800179ff  jns     short loc_180017A4C
0x180017a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a08  cmp     rcx, r13
0x180017a0b  jz      short loc_180017A31
0x180017a0d  test    byte ptr [rcx+1Ch], 1
0x180017a11  jz      short loc_180017A31
0x180017a13  cmp     byte ptr [rcx+19h], 2
0x180017a17  jb      short loc_180017A31
0x180017a19  mov     rcx, [rcx+10h]
0x180017a1d  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180017a24  mov     edx, 0Dh
0x180017a29  mov     r9d, eax
0x180017a2c  call    WPP_SF_d
0x180017a31  mov     rcx, [rbx+28h]; void *
0x180017a35  xor     edx, edx; Val
0x180017a37  mov     r8d, 120h; Size
0x180017a3d  call    memset_0
0x180017a42  mov     rax, [rbx+28h]
0x180017a46  mov     dword ptr [rax], 128h
0x180017a4c  mov     [rbp+var_38], 0
0x180017a53  xor     edi, edi
0x180017a55  lea     rcx, [rbp+var_40]; this
0x180017a59  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180017a5e  mov     rbx, [rsp+80h+arg_8]
0x180017a66  mov     eax, edi
0x180017a68  add     rsp, 80h
0x180017a6f  pop     r14
0x180017a71  pop     r13
0x180017a73  pop     rdi
0x180017a74  pop     rsi
0x180017a75  pop     rbp
0x180017a76  retn
```
