# CScrub::ScrubNtfsSystemFileInternal(_SCRUB_THREAD_CONTEXT *,void *,_UNICODE_STRING const *)

- ea: `0x180023ecc`
- end: `0x180024155`
- name: `?ScrubNtfsSystemFileInternal@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_UNICODE_STRING@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CScrub *this, struct _SCRUB_THREAD_CONTEXT *, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002415c`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x180012048`
- `0x18002226c`
- `0x180022450`
- `0x180023ecc`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18002400a`
- `ntdll!NtOpenFile` at `0x18002400a`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubNtfsSystemFileInternal(
        CScrub *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        void *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // edi
  USHORT v10; // dx
  USHORT Length; // cx
  USHORT v12; // ax
  __int16 v13; // r14
  NTSTATUS v14; // esi
  int v15; // esi
  void *FileHandle; // [rsp+40h] [rbp-59h] BYREF
  int v18; // [rsp+48h] [rbp-51h]
  char v19; // [rsp+4Ch] [rbp-4Dh]
  const char *v20; // [rsp+50h] [rbp-49h] BYREF
  int v21; // [rsp+58h] [rbp-41h]
  char *v22; // [rsp+60h] [rbp-39h]
  char *v23; // [rsp+68h] [rbp-31h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF

  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v8 + 16) = "CScrub::ScrubNtfsSystemFileInternal";
  v20 = "CScrub::ScrubNtfsSystemFileInternal";
  v21 = 0;
  v9 = 1;
  v10 = ++*(_WORD *)(v8 + 8);
  Length = GlobalIndentString.Length;
  v12 = GlobalIndentString.Length;
  if ( v10 < GlobalIndentString.Length )
    v12 = v10;
  LOWORD(v22) = v12;
  if ( v10 < GlobalIndentString.Length )
    Length = v10;
  WORD1(v22) = Length;
  HIDWORD(v22) = 0;
  v23 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubNtfsSystemFileInternal");
  }
  v22 = (char *)a2 + 88;
  v13 = CScrubPath::PushNameEx((struct _UNICODE_STRING *)((char *)a2 + 88), &BackslashString, a4, a4);
  LOWORD(v23) = v13;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = a4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v18 = 0;
  v19 = 0;
  v14 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v14 == -1073741772 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)a2 + 88,
        52);
    }
    v21 = 1;
LABEL_15:
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    goto LABEL_24;
  }
  if ( v14 >= 0 )
  {
    v21 = CScrub::ScrubData((__int64)this, a2, FileHandle, 0, 0);
    v9 = -805306102;
    if ( v21 != -805306102 )
    {
      v21 = 0;
      CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
      v9 = 0;
      goto LABEL_24;
    }
    goto LABEL_15;
  }
  v15 = v14 | 0x10000000;
  v21 = v15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DDZZd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL),
      (__int64)a2 + 88,
      v15);
  }
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  v9 = v15;
LABEL_24:
  *((_WORD *)a2 + 44) -= v13;
  CHResultImp::~CHResultImp((CHResultImp *)&v20);
  return v9;
}

```

## disassembly

```asm
0x180023ecc  push    rbp
0x180023ece  push    rbx
0x180023ecf  push    rsi
0x180023ed0  push    rdi
0x180023ed1  push    r12
0x180023ed3  push    r13
0x180023ed5  push    r14
0x180023ed7  push    r15
0x180023ed9  lea     rbp, [rsp-1Fh]
0x180023ede  sub     rsp, 0B8h
0x180023ee5  mov     rsi, r9
0x180023ee8  mov     r12, r8
0x180023eeb  mov     r13, rdx
0x180023eee  mov     r15, rcx
0x180023ef1  mov     r10d, cs:_tls_index
0x180023ef8  mov     rax, gs:58h
0x180023f01  mov     rdx, [rax+r10*8]
0x180023f05  mov     eax, 10h
0x180023f0a  lea     r8, aCscrubScrubntf_0; "CScrub::ScrubNtfsSystemFileInternal"
0x180023f11  mov     [rax+rdx], r8
0x180023f15  mov     [rbp+57h+var_A0], r8
0x180023f19  mov     [rbp+57h+var_98], 0
0x180023f20  mov     eax, 8
0x180023f25  mov     edi, 1
0x180023f2a  add     [rax+rdx], di
0x180023f2e  movzx   edx, word ptr [rax+rdx]
0x180023f32  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180023f39  movzx   eax, cx
0x180023f3c  cmp     dx, cx
0x180023f3f  cmovb   ax, dx
0x180023f43  mov     word ptr [rbp+57h+var_90], ax
0x180023f47  cmovb   cx, dx
0x180023f4b  mov     word ptr [rbp+57h+var_90+2], cx
0x180023f4f  xor     eax, eax
0x180023f51  mov     dword ptr [rbp+57h+var_90+4], eax
0x180023f54  mov     rax, cs:off_180047060; "                                       "...
0x180023f5b  mov     [rbp+57h+var_88], rax
0x180023f5f  lea     rax, WPP_GLOBAL_Control
0x180023f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f6d  cmp     rcx, rax
0x180023f70  jz      short loc_180023F94
0x180023f72  test    [rcx+1Ch], dil
0x180023f76  jz      short loc_180023F94
0x180023f78  cmp     byte ptr [rcx+19h], 5
0x180023f7c  jb      short loc_180023F94
0x180023f7e  lea     edx, [rdi+0Ch]
0x180023f81  mov     qword ptr [rsp+0F0h+ShareAccess], r8; __int64
0x180023f86  lea     r9, [rbp+57h+var_90]
0x180023f8a  mov     rcx, [rcx+10h]; LoggerHandle
0x180023f8e  call    WPP_SF_aZs
0x180023f93  nop
0x180023f94  lea     rbx, [r13+58h]
0x180023f98  mov     [rbp+57h+var_90], rbx
0x180023f9c  mov     r8, rsi; struct _UNICODE_STRING *
0x180023f9f  lea     rdx, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180023fa6  mov     rcx, rbx; this
0x180023fa9  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180023fae  movzx   r14d, ax
0x180023fb2  mov     word ptr [rbp+57h+var_88], ax
0x180023fb6  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180023fbe  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180023fc6  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180023fca  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x180023fce  xorps   xmm0, xmm0
0x180023fd1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180023fd6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180023fda  xor     r12d, r12d
0x180023fdd  mov     [rbp+57h+FileHandle], r12
0x180023fe1  mov     [rbp+57h+var_A8], r12d
0x180023fe5  mov     [rbp+57h+var_A4], r12b
0x180023fe9  mov     [rsp+0F0h+OpenOptions], 60h ; '`'; OpenOptions
0x180023ff1  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x180023ff9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180023ffd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180024001  mov     edx, 100080h; DesiredAccess
0x180024006  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002400a  call    cs:__imp_NtOpenFile
0x180024010  mov     esi, eax
0x180024012  mov     r8d, 0C0000034h
0x180024018  cmp     eax, r8d
0x18002401b  jnz     short loc_180024088
0x18002401d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024024  lea     rax, WPP_GLOBAL_Control
0x18002402b  cmp     rcx, rax
0x18002402e  jz      short loc_180024076
0x180024030  test    [rcx+1Ch], dil
0x180024034  jz      short loc_180024076
0x180024036  cmp     byte ptr [rcx+19h], 5
0x18002403a  jb      short loc_180024076
0x18002403c  mov     rax, [r15]
0x18002403f  mov     r9, [rax]
0x180024042  lea     edx, [r12+7Dh]
0x180024047  mov     dword ptr [rsp+0F0h+var_B8], r8d; char
0x18002404c  mov     [rsp+0F0h+var_C0], rbx; __int64
0x180024051  mov     rax, [rax+40h]
0x180024055  mov     qword ptr [rsp+0F0h+OpenOptions], rax; __int64
0x18002405a  mov     eax, [r9+24h]
0x18002405e  mov     [rsp+0F0h+ShareAccess], eax; char
0x180024062  mov     r9d, [r9+10h]
0x180024066  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002406d  mov     rcx, [rcx+10h]; LoggerHandle
0x180024071  call    WPP_SF_DDZZd
0x180024076  mov     [rbp+57h+var_98], edi
0x180024079  lea     rcx, [rbp+57h+FileHandle]
0x18002407d  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180024082  nop
0x180024083  jmp     loc_180024132
0x180024088  test    esi, esi
0x18002408a  jns     short loc_1800240FA
0x18002408c  bts     esi, 1Ch
0x180024090  mov     [rbp+57h+var_98], esi
0x180024093  mov     rcx, cs:WPP_GLOBAL_Control
0x18002409a  lea     rax, WPP_GLOBAL_Control
0x1800240a1  cmp     rcx, rax
0x1800240a4  jz      short loc_1800240EC
0x1800240a6  test    [rcx+1Ch], dil
0x1800240aa  jz      short loc_1800240EC
0x1800240ac  cmp     byte ptr [rcx+19h], 2
0x1800240b0  jb      short loc_1800240EC
0x1800240b2  mov     rax, [r15]
0x1800240b5  mov     r9, [rax]
0x1800240b8  mov     edx, 7Eh ; '~'
0x1800240bd  mov     dword ptr [rsp+0F0h+var_B8], esi; char
0x1800240c1  mov     [rsp+0F0h+var_C0], rbx; __int64
0x1800240c6  mov     rax, [rax+40h]
0x1800240ca  mov     qword ptr [rsp+0F0h+OpenOptions], rax; __int64
0x1800240cf  mov     eax, [r9+24h]
0x1800240d3  mov     [rsp+0F0h+ShareAccess], eax; char
0x1800240d7  mov     r9d, [r9+10h]
0x1800240db  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x1800240e2  mov     rcx, [rcx+10h]; LoggerHandle
0x1800240e6  call    WPP_SF_DDZZd
0x1800240eb  nop
0x1800240ec  lea     rcx, [rbp+57h+FileHandle]
0x1800240f0  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800240f5  nop
0x1800240f6  mov     edi, esi
0x1800240f8  jmp     short loc_180024132
0x1800240fa  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x1800240ff  xor     r9d, r9d
0x180024102  mov     r8, [rbp+57h+FileHandle]
0x180024106  mov     rdx, r13
0x180024109  mov     rcx, r15
0x18002410c  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x180024111  mov     [rbp+57h+var_98], eax
0x180024114  mov     edi, 0D000010Ah
0x180024119  cmp     eax, edi
0x18002411b  jz      loc_180024079
0x180024121  mov     [rbp+57h+var_98], r12d
0x180024125  lea     rcx, [rbp+57h+FileHandle]
0x180024129  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18002412e  nop
0x18002412f  mov     edi, r12d
0x180024132  sub     [rbx], r14w
0x180024136  lea     rcx, [rbp+57h+var_A0]; this
0x18002413a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002413f  mov     eax, edi
0x180024141  add     rsp, 0B8h
0x180024148  pop     r15
0x18002414a  pop     r14
0x18002414c  pop     r13
0x18002414e  pop     r12
0x180024150  pop     rdi
0x180024151  pop     rsi
0x180024152  pop     rbx
0x180024153  pop     rbp
0x180024154  retn
```
