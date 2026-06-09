# CsvIsCsvVolumeByName(_SCRUB_VOLUME_IDENTIFIER const *,_UNICODE_STRING const *)

- ea: `0x180008c9c`
- end: `0x180008e41`
- name: `?CsvIsCsvVolumeByName@@YAJPEBU_SCRUB_VOLUME_IDENTIFIER@@PEBU_UNICODE_STRING@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(const struct _SCRUB_VOLUME_IDENTIFIER *, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ec84`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x180008a6c`
- `0x180008c9c`
- `0x180012048`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180008dab`
- `ntdll!NtOpenFile` at `0x180008dab`

## pseudocode

```c
__int64 __fastcall CsvIsCsvVolumeByName(const struct _SCRUB_VOLUME_IDENTIFIER *a1, struct _UNICODE_STRING *a2)
{
  USHORT Length; // cx
  __int64 v5; // r9
  USHORT v6; // dx
  USHORT v7; // ax
  NTSTATUS v8; // ebx
  unsigned int v9; // ebx
  void *FileHandle; // [rsp+40h] [rbp-39h] BYREF
  int v12; // [rsp+48h] [rbp-31h]
  char v13; // [rsp+4Ch] [rbp-2Dh]
  USHORT v14; // [rsp+50h] [rbp-29h]
  USHORT v15; // [rsp+52h] [rbp-27h]
  int v16; // [rsp+54h] [rbp-25h]
  char *v17; // [rsp+58h] [rbp-21h]
  const char *v18; // [rsp+60h] [rbp-19h] BYREF
  int IsCsvVolume; // [rsp+68h] [rbp-11h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF

  Length = GlobalIndentString.Length;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v18 = "CsvIsCsvVolumeByName";
  v6 = ++*(_WORD *)(v5 + 8);
  *(_QWORD *)(v5 + 16) = "CsvIsCsvVolumeByName";
  v7 = Length;
  if ( v6 < Length )
  {
    v7 = v6;
    Length = v6;
  }
  v14 = v7;
  v16 = 0;
  v17 = off_180047060;
  v15 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CsvIsCsvVolumeByName");
  }
  FileHandle = 0;
  v12 = 0;
  v13 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  v8 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( v8 >= 0 )
  {
    IsCsvVolume = CsvIsCsvVolume(a1, FileHandle);
    v9 = IsCsvVolume;
  }
  else
  {
    v9 = v8 | 0x10000000;
    IsCsvVolume = v9;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(*(_QWORD *)a1 + 36LL),
        *((_QWORD *)a1 + 8),
        (__int64)a2,
        v9);
    }
  }
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CHResultImp::~CHResultImp((CHResultImp *)&v18);
  return v9;
}

```

## disassembly

```asm
0x180008c9c  push    rbp
0x180008c9e  push    rbx
0x180008c9f  push    rsi
0x180008ca0  push    rdi
0x180008ca1  push    r15
0x180008ca3  lea     rbp, [rsp-37h]
0x180008ca8  sub     rsp, 0B0h
0x180008caf  mov     r8d, cs:_tls_index
0x180008cb6  mov     rsi, rdx
0x180008cb9  mov     rax, gs:58h
0x180008cc2  mov     rdi, rcx
0x180008cc5  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180008ccc  mov     edx, 8
0x180008cd1  mov     r9, [rax+r8*8]
0x180008cd5  lea     r8, aCsviscsvvolume_0; "CsvIsCsvVolumeByName"
0x180008cdc  mov     eax, 10h
0x180008ce1  mov     [rbp+57h+var_70], r8
0x180008ce5  inc     word ptr [rdx+r9]
0x180008cea  movzx   edx, word ptr [rdx+r9]
0x180008cef  mov     [rax+r9], r8
0x180008cf3  cmp     dx, cx
0x180008cf6  movzx   eax, cx
0x180008cf9  cmovb   ax, dx
0x180008cfd  cmovb   cx, dx
0x180008d01  mov     [rbp+57h+var_80], ax
0x180008d05  xor     eax, eax
0x180008d07  mov     [rbp+57h+var_7C], eax
0x180008d0a  mov     rax, cs:off_180047060; "                                       "...
0x180008d11  mov     [rbp+57h+var_78], rax
0x180008d15  mov     [rbp+57h+var_7E], cx
0x180008d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d20  lea     r15, WPP_GLOBAL_Control
0x180008d27  cmp     rcx, r15
0x180008d2a  jz      short loc_180008D4F
0x180008d2c  test    byte ptr [rcx+1Ch], 1
0x180008d30  jz      short loc_180008D4F
0x180008d32  cmp     byte ptr [rcx+19h], 5
0x180008d36  jb      short loc_180008D4F
0x180008d38  mov     rcx, [rcx+10h]; LoggerHandle
0x180008d3c  lea     r9, [rbp+57h+var_80]
0x180008d40  mov     edx, 0Dh
0x180008d45  mov     qword ptr [rsp+0D0h+ShareAccess], r8; __int64
0x180008d4a  call    WPP_SF_aZs
0x180008d4f  xorps   xmm0, xmm0
0x180008d52  mov     [rsp+0D0h+OpenOptions], 21h ; '!'; OpenOptions
0x180008d5a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180008d5e  mov     [rbp+57h+FileHandle], 0
0x180008d66  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180008d6a  mov     [rbp+57h+var_88], 0
0x180008d71  mov     edx, 100080h; DesiredAccess
0x180008d76  mov     [rbp+57h+var_84], 0
0x180008d7a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180008d7e  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180008d86  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180008d8a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180008d92  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008d97  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180008d9b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180008da3  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180008dab  call    cs:__imp_NtOpenFile
0x180008db1  mov     ebx, eax
0x180008db3  test    eax, eax
0x180008db5  jns     short loc_180008E0E
0x180008db7  bts     ebx, 1Ch
0x180008dbb  mov     [rbp+57h+var_68], ebx
0x180008dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dc5  cmp     rcx, r15
0x180008dc8  jz      short loc_180008E1F
0x180008dca  test    byte ptr [rcx+1Ch], 1
0x180008dce  jz      short loc_180008E1F
0x180008dd0  cmp     byte ptr [rcx+19h], 2
0x180008dd4  jb      short loc_180008E1F
0x180008dd6  mov     r9, [rdi]
0x180008dd9  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x180008de0  mov     rax, [rdi+40h]
0x180008de4  mov     edx, 3Eh ; '>'
0x180008de9  mov     rcx, [rcx+10h]; LoggerHandle
0x180008ded  mov     dword ptr [rsp+0D0h+var_98], ebx; char
0x180008df1  mov     [rsp+0D0h+var_A0], rsi; __int64
0x180008df6  mov     qword ptr [rsp+0D0h+OpenOptions], rax; __int64
0x180008dfb  mov     eax, [r9+24h]
0x180008dff  mov     r9d, [r9+10h]
0x180008e03  mov     [rsp+0D0h+ShareAccess], eax; char
0x180008e07  call    WPP_SF_DDZZd
0x180008e0c  jmp     short loc_180008E1F
0x180008e0e  mov     rdx, [rbp+57h+FileHandle]; void *
0x180008e12  mov     rcx, rdi; struct _SCRUB_VOLUME_IDENTIFIER *
0x180008e15  call    ?CsvIsCsvVolume@@YAJPEBU_SCRUB_VOLUME_IDENTIFIER@@PEAX@Z; CsvIsCsvVolume(_SCRUB_VOLUME_IDENTIFIER const *,void *)
0x180008e1a  mov     [rbp+57h+var_68], eax
0x180008e1d  mov     ebx, eax
0x180008e1f  lea     rcx, [rbp+57h+FileHandle]
0x180008e23  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180008e28  lea     rcx, [rbp+57h+var_70]; this
0x180008e2c  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180008e31  mov     eax, ebx
0x180008e33  add     rsp, 0B0h
0x180008e3a  pop     r15
0x180008e3c  pop     rdi
0x180008e3d  pop     rsi
0x180008e3e  pop     rbx
0x180008e3f  pop     rbp
0x180008e40  retn
```
