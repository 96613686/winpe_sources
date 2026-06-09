# CScrub::ScrubVolumeDasd(_UNICODE_STRING const *)

- ea: `0x180026eec`
- end: `0x1800270f7`
- name: `?ScrubVolumeDasd@CScrub@@QEAAJPEBU_UNICODE_STRING@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(CScrub *this, struct _UNICODE_STRING *, __int64, const struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x180012048`
- `0x18002226c`
- `0x180022450`
- `0x180026eec`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180027039`
- `ntdll!NtOpenFile` at `0x180027039`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScrub::ScrubVolumeDasd(
        CScrub *this,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        const struct _UNICODE_STRING *a4)
{
  __int64 v6; // rdx
  USHORT v7; // dx
  USHORT Length; // cx
  USHORT v9; // ax
  struct _UNICODE_STRING *v10; // rcx
  const struct _UNICODE_STRING *v11; // r8
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  int v14; // eax
  void *FileHandle; // [rsp+40h] [rbp-49h] BYREF
  int v17; // [rsp+48h] [rbp-41h]
  char v18; // [rsp+4Ch] [rbp-3Dh]
  const char *v19; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v20; // [rsp+58h] [rbp-31h]
  USHORT v21; // [rsp+60h] [rbp-29h]
  USHORT v22; // [rsp+62h] [rbp-27h]
  int v23; // [rsp+64h] [rbp-25h]
  char *v24; // [rsp+68h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF

  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v6 + 16) = "CScrub::ScrubVolumeDasd";
  v19 = "CScrub::ScrubVolumeDasd";
  v20 = 0;
  v7 = ++*(_WORD *)(v6 + 8);
  Length = GlobalIndentString.Length;
  v9 = GlobalIndentString.Length;
  if ( v7 < GlobalIndentString.Length )
    v9 = v7;
  v21 = v9;
  if ( v7 < GlobalIndentString.Length )
    Length = v7;
  v22 = Length;
  v23 = 0;
  v24 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubVolumeDasd");
  }
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v10 = (struct _UNICODE_STRING *)(*((_QWORD *)this + 177) + 88LL);
  v11 = *(const struct _UNICODE_STRING **)(*(_QWORD *)this + 64LL);
  v10->Length = 0;
  CScrubPath::PushNameEx(v10, &EmptyUnicodeString, v11, a4);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v17 = 0;
  v18 = 0;
  v12 = NtOpenFile(&FileHandle, 0x1000A0u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v12 >= 0 )
  {
    v14 = CScrub::ScrubData((__int64)this, *((struct _SCRUB_THREAD_CONTEXT **)this + 177), FileHandle, 1, 0);
    v20 = v14;
    if ( v14 >= 0 )
    {
      v20 = 0;
      v13 = 0;
    }
    else
    {
      v13 = v14;
    }
  }
  else
  {
    v13 = v12 | 0x10000000;
    v20 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)a2,
        v13);
    }
  }
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v13;
}

```

## disassembly

```asm
0x180026eec  push    rbp
0x180026eee  push    rbx
0x180026eef  push    rsi
0x180026ef0  push    rdi
0x180026ef1  push    r12
0x180026ef3  push    r15
0x180026ef5  lea     rbp, [rsp-2Fh]
0x180026efa  sub     rsp, 0B8h
0x180026f01  mov     rsi, rdx
0x180026f04  mov     rdi, rcx
0x180026f07  mov     r8d, cs:_tls_index
0x180026f0e  mov     rax, gs:58h
0x180026f17  mov     rdx, [rax+r8*8]
0x180026f1b  mov     eax, 10h
0x180026f20  lea     r8, aCscrubScrubvol_0; "CScrub::ScrubVolumeDasd"
0x180026f27  mov     [rax+rdx], r8
0x180026f2b  mov     [rbp+57h+var_90], r8
0x180026f2f  mov     [rbp+57h+var_88], 0
0x180026f36  mov     eax, 8
0x180026f3b  mov     r15d, 1
0x180026f41  add     [rax+rdx], r15w
0x180026f46  movzx   edx, word ptr [rax+rdx]
0x180026f4a  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180026f51  movzx   eax, cx
0x180026f54  cmp     dx, cx
0x180026f57  cmovb   ax, dx
0x180026f5b  mov     [rbp+57h+var_80], ax
0x180026f5f  cmovb   cx, dx
0x180026f63  mov     [rbp+57h+var_7E], cx
0x180026f67  xor     eax, eax
0x180026f69  mov     [rbp+57h+var_7C], eax
0x180026f6c  mov     rax, cs:off_180047060; "                                       "...
0x180026f73  mov     [rbp+57h+var_78], rax
0x180026f77  lea     r12, WPP_GLOBAL_Control
0x180026f7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026f85  cmp     rcx, r12
0x180026f88  jz      short loc_180026FAD
0x180026f8a  test    [rcx+1Ch], r15b
0x180026f8e  jz      short loc_180026FAD
0x180026f90  cmp     byte ptr [rcx+19h], 5
0x180026f94  jb      short loc_180026FAD
0x180026f96  lea     edx, [r15+0Ch]
0x180026f9a  mov     qword ptr [rsp+0E0h+ShareAccess], r8; __int64
0x180026f9f  lea     r9, [rbp+57h+var_80]
0x180026fa3  mov     rcx, [rcx+10h]; LoggerHandle
0x180026fa7  call    WPP_SF_aZs
0x180026fac  nop
0x180026fad  xorps   xmm0, xmm0
0x180026fb0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180026fb4  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180026fb8  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180026fbc  mov     rcx, [rdi+588h]
0x180026fc3  add     rcx, 58h ; 'X'; this
0x180026fc7  mov     rax, [rdi]
0x180026fca  mov     r8, [rax+40h]; struct _UNICODE_STRING *
0x180026fce  xor     eax, eax
0x180026fd0  mov     [rcx], ax
0x180026fd3  lea     rdx, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180026fda  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180026fdf  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180026fe6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180026fee  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180026ff5  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180026ff9  xorps   xmm0, xmm0
0x180026ffc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180027001  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180027005  mov     [rbp+57h+FileHandle], 0
0x18002700d  mov     [rbp+57h+var_98], 0
0x180027014  mov     [rbp+57h+var_94], 0
0x180027018  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x180027020  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180027028  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002702c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180027030  mov     edx, 1000A0h; DesiredAccess
0x180027035  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180027039  call    cs:__imp_NtOpenFile
0x18002703f  mov     ebx, eax
0x180027041  test    eax, eax
0x180027043  jns     short loc_18002709F
0x180027045  bts     ebx, 1Ch
0x180027049  mov     [rbp+57h+var_88], ebx
0x18002704c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027053  cmp     rcx, r12
0x180027056  jz      short loc_1800270D2
0x180027058  test    [rcx+1Ch], r15b
0x18002705c  jz      short loc_1800270D2
0x18002705e  cmp     byte ptr [rcx+19h], 2
0x180027062  jb      short loc_1800270D2
0x180027064  mov     rax, [rdi]
0x180027067  mov     r9, [rax]
0x18002706a  mov     edx, 66h ; 'f'
0x18002706f  mov     dword ptr [rsp+0E0h+var_A8], ebx; char
0x180027073  mov     [rsp+0E0h+var_B0], rsi; __int64
0x180027078  mov     rax, [rax+40h]
0x18002707c  mov     qword ptr [rsp+0E0h+OpenOptions], rax; __int64
0x180027081  mov     eax, [r9+24h]
0x180027085  mov     [rsp+0E0h+ShareAccess], eax; char
0x180027089  mov     r9d, [r9+10h]
0x18002708d  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180027094  mov     rcx, [rcx+10h]; LoggerHandle
0x180027098  call    WPP_SF_DDZZd
0x18002709d  jmp     short loc_1800270D2
0x18002709f  mov     qword ptr [rsp+0E0h+ShareAccess], 0
0x1800270a8  mov     r9d, r15d
0x1800270ab  mov     r8, [rbp+57h+FileHandle]
0x1800270af  mov     rdx, [rdi+588h]
0x1800270b6  mov     rcx, rdi
0x1800270b9  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x1800270be  mov     [rbp+57h+var_88], eax
0x1800270c1  test    eax, eax
0x1800270c3  jns     short loc_1800270C9
0x1800270c5  mov     ebx, eax
0x1800270c7  jmp     short loc_1800270D2
0x1800270c9  mov     [rbp+57h+var_88], 0
0x1800270d0  xor     ebx, ebx
0x1800270d2  lea     rcx, [rbp+57h+FileHandle]
0x1800270d6  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800270db  nop
0x1800270dc  lea     rcx, [rbp+57h+var_90]; this
0x1800270e0  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800270e5  mov     eax, ebx
0x1800270e7  add     rsp, 0B8h
0x1800270ee  pop     r15
0x1800270f0  pop     r12
0x1800270f2  pop     rdi
0x1800270f3  pop     rsi
0x1800270f4  pop     rbx
0x1800270f5  pop     rbp
0x1800270f6  retn
```
