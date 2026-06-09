# CScrub::ScrubStream(_SCRUB_THREAD_CONTEXT *,void *,_UNICODE_STRING const *,ulong)

- ea: `0x1800247c4`
- end: `0x180024b1d`
- name: `?ScrubStream@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_UNICODE_STRING@@K@Z`
- size: `857`
- prototype: `__int64 __fastcall(CScrub *this, struct _SCRUB_THREAD_CONTEXT *, void *, struct _UNICODE_STRING *, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180028fe4`
- `0x18002ad9c`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x180012048`
- `0x1800129b0`
- `0x18002226c`
- `0x180022450`
- `0x1800247c4`
- `0x18002d7b0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18002495f`
- `ntdll!RtlEqualUnicodeString` at `0x18002495f`
- `ntdll!NtOpenFile` at `0x180024931`
- `ntdll!NtOpenFile` at `0x180024931`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubStream(
        CScrub *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        char a5)
{
  __int64 v9; // rdx
  USHORT v10; // dx
  USHORT Length; // cx
  USHORT v12; // ax
  _WORD *v13; // rdi
  int v14; // edx
  __int16 v15; // si
  int v16; // r8d
  NTSTATUS v17; // eax
  NTSTATUS v18; // ebx
  _QWORD *v19; // rcx
  int v20; // edx
  int v21; // ebx
  void *FileHandle; // [rsp+40h] [rbp-61h] BYREF
  int v24; // [rsp+48h] [rbp-59h]
  char v25; // [rsp+4Ch] [rbp-55h]
  const char *v26; // [rsp+50h] [rbp-51h] BYREF
  int v27; // [rsp+58h] [rbp-49h]
  char *v28; // [rsp+60h] [rbp-41h]
  char *v29; // [rsp+68h] [rbp-39h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-21h] BYREF

  v9 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v9 + 16) = "CScrub::ScrubStream";
  v26 = "CScrub::ScrubStream";
  v27 = 0;
  v10 = ++*(_WORD *)(v9 + 8);
  Length = GlobalIndentString.Length;
  v12 = GlobalIndentString.Length;
  if ( v10 < GlobalIndentString.Length )
    v12 = v10;
  LOWORD(v28) = v12;
  if ( v10 < GlobalIndentString.Length )
    Length = v10;
  WORD1(v28) = Length;
  HIDWORD(v28) = 0;
  v29 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubStream");
  }
  v13 = (_WORD *)((char *)a2 + 88);
  v28 = (char *)a2 + 88;
  v15 = CScrubPath::PushNameEx((struct _UNICODE_STRING *)((char *)a2 + 88), &EmptyUnicodeString, a4, a4);
  LOWORD(v29) = v15;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_ZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v16, (_DWORD)a2 + 88, (__int64)a4);
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = a4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v24 = 0;
  v25 = 0;
  v17 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x604020u);
  v18 = v17;
  if ( v17 < 0 )
  {
    if ( (a5 & 2) != 0 )
    {
      if ( v17 == -1073741790 && RtlEqualUnicodeString(&NtfsAttributeNameSecurityDescriptor, a4, 1u)
        || (unsigned int)(v18 + 1073741773) <= 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_Zd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            121,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            (_DWORD)a2 + 88,
            v18);
        }
        v27 = 1;
        v21 = 1;
        goto LABEL_40;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_32:
        v21 = v18 | 0x10000000;
        v27 = v21;
LABEL_40:
        CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
        *v13 -= v15;
        goto LABEL_42;
      }
      v20 = 122;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_32;
      }
      v20 = 123;
    }
    WPP_SF_Zd(v19[2], v20, (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids, (_DWORD)a2 + 88, v18);
    goto LABEL_32;
  }
  v21 = CScrub::ScrubData((__int64)this, a2, FileHandle, 0, 0);
  v27 = v21;
  if ( v21 != -805306102 )
  {
    if ( v21 >= 0 )
    {
      ++*((_QWORD *)a2 + 190);
      v27 = 0;
      CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
      *v13 -= v15;
      v21 = 0;
      goto LABEL_42;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)a2 + 88,
        v21);
    }
    goto LABEL_40;
  }
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  *v13 -= v15;
  v21 = -805306102;
LABEL_42:
  CHResultImp::~CHResultImp((CHResultImp *)&v26);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800247c4  push    rbp
0x1800247c6  push    rbx
0x1800247c7  push    rsi
0x1800247c8  push    rdi
0x1800247c9  push    r12
0x1800247cb  push    r13
0x1800247cd  push    r14
0x1800247cf  push    r15
0x1800247d1  lea     rbp, [rsp-17h]
0x1800247d6  sub     rsp, 0B8h
0x1800247dd  mov     r15, r9
0x1800247e0  mov     rbx, r8
0x1800247e3  mov     r14, rdx
0x1800247e6  mov     r12, rcx
0x1800247e9  mov     r10d, cs:_tls_index
0x1800247f0  mov     rax, gs:58h
0x1800247f9  mov     rdx, [rax+r10*8]
0x1800247fd  mov     eax, 10h
0x180024802  lea     r8, aCscrubScrubstr; "CScrub::ScrubStream"
0x180024809  mov     [rax+rdx], r8
0x18002480d  mov     [rbp+4Fh+var_A0], r8
0x180024811  mov     [rbp+4Fh+var_98], 0
0x180024818  mov     eax, 8
0x18002481d  mov     r13d, 1
0x180024823  add     [rax+rdx], r13w
0x180024828  movzx   edx, word ptr [rax+rdx]
0x18002482c  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180024833  movzx   eax, cx
0x180024836  cmp     dx, cx
0x180024839  cmovb   ax, dx
0x18002483d  mov     word ptr [rbp+4Fh+var_90], ax
0x180024841  cmovb   cx, dx
0x180024845  mov     word ptr [rbp+4Fh+var_90+2], cx
0x180024849  xor     eax, eax
0x18002484b  mov     dword ptr [rbp+4Fh+var_90+4], eax
0x18002484e  mov     rax, cs:off_180047060; "                                       "...
0x180024855  mov     [rbp+4Fh+var_88], rax
0x180024859  lea     rax, WPP_GLOBAL_Control
0x180024860  mov     rcx, cs:WPP_GLOBAL_Control
0x180024867  cmp     rcx, rax
0x18002486a  jz      short loc_18002488F
0x18002486c  test    [rcx+1Ch], r13b
0x180024870  jz      short loc_18002488F
0x180024872  cmp     byte ptr [rcx+19h], 5
0x180024876  jb      short loc_18002488F
0x180024878  lea     edx, [r13+0Ch]
0x18002487c  mov     qword ptr [rsp+0F0h+ShareAccess], r8; __int64
0x180024881  lea     r9, [rbp+4Fh+var_90]
0x180024885  mov     rcx, [rcx+10h]; LoggerHandle
0x180024889  call    WPP_SF_aZs
0x18002488e  nop
0x18002488f  lea     rdi, [r14+58h]
0x180024893  mov     [rbp+4Fh+var_90], rdi
0x180024897  mov     r8, r15; struct _UNICODE_STRING *
0x18002489a  lea     rdx, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800248a1  mov     rcx, rdi; this
0x1800248a4  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x1800248a9  movzx   esi, ax
0x1800248ac  mov     word ptr [rbp+4Fh+var_88], ax
0x1800248b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800248b7  lea     rax, WPP_GLOBAL_Control
0x1800248be  cmp     rcx, rax
0x1800248c1  jz      short loc_1800248E0
0x1800248c3  test    [rcx+1Ch], r13b
0x1800248c7  jz      short loc_1800248E0
0x1800248c9  cmp     byte ptr [rcx+19h], 5
0x1800248cd  jb      short loc_1800248E0
0x1800248cf  mov     qword ptr [rsp+0F0h+ShareAccess], r15
0x1800248d4  mov     r9, rdi
0x1800248d7  mov     rcx, [rcx+10h]
0x1800248db  call    WPP_SF_ZZ
0x1800248e0  xor     eax, eax
0x1800248e2  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800248ea  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800248f2  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x1800248f6  mov     [rbp+4Fh+ObjectAttributes.ObjectName], r15
0x1800248fa  xorps   xmm0, xmm0
0x1800248fd  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180024902  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm0
0x180024906  mov     [rbp+4Fh+FileHandle], rax
0x18002490a  mov     [rbp+4Fh+var_A8], eax
0x18002490d  mov     [rbp+4Fh+var_A4], al
0x180024910  mov     [rsp+0F0h+OpenOptions], 604020h; OpenOptions
0x180024918  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x180024920  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x180024924  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180024928  mov     edx, 100080h; DesiredAccess
0x18002492d  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x180024931  call    cs:__imp_NtOpenFile
0x180024937  mov     ebx, eax
0x180024939  test    eax, eax
0x18002493b  jns     loc_180024A34
0x180024941  test    byte ptr [rbp+4Fh+arg_20], 2
0x180024945  jz      loc_1800249ED
0x18002494b  cmp     eax, 0C0000022h
0x180024950  jnz     short loc_180024969
0x180024952  mov     r8b, r13b; CaseInsensitive
0x180024955  mov     rdx, r15; String2
0x180024958  lea     rcx, ?NtfsAttributeNameSecurityDescriptor@@3U_UNICODE_STRING@@A; String1
0x18002495f  call    cs:__imp_RtlEqualUnicodeString
0x180024965  test    al, al
0x180024967  jnz     short loc_1800249A6
0x180024969  lea     eax, [rbx+3FFFFFCDh]
0x18002496f  cmp     eax, r13d
0x180024972  jbe     short loc_1800249A6
0x180024974  mov     rcx, cs:WPP_GLOBAL_Control
0x18002497b  lea     rax, WPP_GLOBAL_Control
0x180024982  cmp     rcx, rax
0x180024985  jz      loc_180024A28
0x18002498b  test    [rcx+1Ch], r13b
0x18002498f  jz      loc_180024A28
0x180024995  cmp     byte ptr [rcx+19h], 2
0x180024999  jb      loc_180024A28
0x18002499f  mov     edx, 7Ah ; 'z'
0x1800249a4  jmp     short loc_180024A11
0x1800249a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249ad  lea     rax, WPP_GLOBAL_Control
0x1800249b4  cmp     rcx, rax
0x1800249b7  jz      short loc_1800249E1
0x1800249b9  test    [rcx+1Ch], r13b
0x1800249bd  jz      short loc_1800249E1
0x1800249bf  cmp     byte ptr [rcx+19h], 5
0x1800249c3  jb      short loc_1800249E1
0x1800249c5  mov     edx, 79h ; 'y'
0x1800249ca  mov     [rsp+0F0h+ShareAccess], ebx
0x1800249ce  mov     r9, rdi
0x1800249d1  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x1800249d8  mov     rcx, [rcx+10h]
0x1800249dc  call    WPP_SF_Zd
0x1800249e1  mov     [rbp+4Fh+var_98], r13d
0x1800249e5  mov     ebx, r13d
0x1800249e8  jmp     loc_180024AD2
0x1800249ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249f4  lea     rax, WPP_GLOBAL_Control
0x1800249fb  cmp     rcx, rax
0x1800249fe  jz      short loc_180024A28
0x180024a00  test    [rcx+1Ch], r13b
0x180024a04  jz      short loc_180024A28
0x180024a06  cmp     byte ptr [rcx+19h], 2
0x180024a0a  jb      short loc_180024A28
0x180024a0c  mov     edx, 7Bh ; '{'
0x180024a11  mov     [rsp+0F0h+ShareAccess], ebx
0x180024a15  mov     r9, rdi
0x180024a18  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024a1f  mov     rcx, [rcx+10h]
0x180024a23  call    WPP_SF_Zd
0x180024a28  bts     ebx, 1Ch
0x180024a2c  mov     [rbp+4Fh+var_98], ebx
0x180024a2f  jmp     loc_180024AD2
0x180024a34  mov     qword ptr [rsp+0F0h+ShareAccess], 0
0x180024a3d  xor     r9d, r9d
0x180024a40  mov     r8, [rbp+4Fh+FileHandle]
0x180024a44  mov     rdx, r14
0x180024a47  mov     rcx, r12
0x180024a4a  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x180024a4f  mov     ebx, eax
0x180024a51  mov     [rbp+4Fh+var_98], eax
0x180024a54  mov     r15d, 0D000010Ah
0x180024a5a  cmp     eax, r15d
0x180024a5d  jnz     short loc_180024A74
0x180024a5f  lea     rcx, [rbp+4Fh+FileHandle]
0x180024a63  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180024a68  nop
0x180024a69  sub     [rdi], si
0x180024a6c  mov     ebx, r15d
0x180024a6f  jmp     loc_180024AFE
0x180024a74  test    ebx, ebx
0x180024a76  jns     short loc_180024AE1
0x180024a78  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a7f  lea     rax, WPP_GLOBAL_Control
0x180024a86  cmp     rcx, rax
0x180024a89  jz      short loc_180024AD2
0x180024a8b  test    [rcx+1Ch], r13b
0x180024a8f  jz      short loc_180024AD2
0x180024a91  cmp     byte ptr [rcx+19h], 2
0x180024a95  jb      short loc_180024AD2
0x180024a97  mov     rax, [r12]
0x180024a9b  mov     r9, [rax]
0x180024a9e  mov     edx, 7Ch ; '|'
0x180024aa3  mov     dword ptr [rsp+0F0h+var_B8], ebx; char
0x180024aa7  mov     [rsp+0F0h+var_C0], rdi; __int64
0x180024aac  mov     rax, [rax+40h]
0x180024ab0  mov     qword ptr [rsp+0F0h+OpenOptions], rax; __int64
0x180024ab5  mov     eax, [r9+24h]
0x180024ab9  mov     [rsp+0F0h+ShareAccess], eax; char
0x180024abd  mov     r9d, [r9+10h]
0x180024ac1  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024ac8  mov     rcx, [rcx+10h]; LoggerHandle
0x180024acc  call    WPP_SF_DDZZd
0x180024ad1  nop
0x180024ad2  lea     rcx, [rbp+4Fh+FileHandle]
0x180024ad6  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180024adb  nop
0x180024adc  sub     [rdi], si
0x180024adf  jmp     short loc_180024AFE
0x180024ae1  add     [r14+5F0h], r13
0x180024ae8  mov     [rbp+4Fh+var_98], 0
0x180024aef  lea     rcx, [rbp+4Fh+FileHandle]
0x180024af3  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180024af8  nop
0x180024af9  sub     [rdi], si
0x180024afc  xor     ebx, ebx
0x180024afe  lea     rcx, [rbp+4Fh+var_A0]; this
0x180024b02  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180024b07  mov     eax, ebx
0x180024b09  add     rsp, 0B8h
0x180024b10  pop     r15
0x180024b12  pop     r14
0x180024b14  pop     r13
0x180024b16  pop     r12
0x180024b18  pop     rdi
0x180024b19  pop     rsi
0x180024b1a  pop     rbx
0x180024b1b  pop     rbp
0x180024b1c  retn
```
