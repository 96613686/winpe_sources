# CScrub::ScrubFile(_SCRUB_THREAD_CONTEXT *,void *,_UNICODE_STRING const *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS,_SCRUB_FILE_ENTRY *)

- ea: `0x180023a44`
- end: `0x180023ec5`
- name: `?ScrubFile@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_UNICODE_STRING@@KW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@PEAU_SCRUB_FILE_ENTRY@@@Z`
- size: `1153`
- prototype: `__int64 __fastcall(CScrub *, unsigned __int64, void *, struct _UNICODE_STRING *, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029210`
- `0x18002a2e0`

## callees

- `0x180001bc4`
- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x1800129b0`
- `0x18002226c`
- `0x180022450`
- `0x180023a44`
- `0x180028fe4`
- `0x18002ad9c`
- `0x18002c468`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180023b45`
- `ntdll!RtlCopyUnicodeString` at `0x180023b45`
- `ntdll!NtOpenFile` at `0x180023b9c`
- `ntdll!NtOpenFile` at `0x180023b9c`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubFile(
        CScrub *a1,
        unsigned __int64 a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        char a5,
        __int64 a6,
        __int64 a7)
{
  __int64 v11; // rdx
  const struct _UNICODE_STRING *v12; // r9
  USHORT v13; // dx
  USHORT Length; // cx
  USHORT v15; // ax
  _WORD *v16; // rbx
  __int16 v17; // r15
  NTSTATUS v18; // edi
  unsigned int v19; // edi
  _QWORD *v20; // r8
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  int v23; // edi
  _QWORD *v24; // r8
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // rcx
  _DWORD *v27; // rcx
  void *FileHandle; // [rsp+50h] [rbp-71h] BYREF
  int v30; // [rsp+58h] [rbp-69h]
  char v31; // [rsp+5Ch] [rbp-65h]
  const char *v32; // [rsp+60h] [rbp-61h] BYREF
  int v33; // [rsp+68h] [rbp-59h]
  unsigned __int64 v34; // [rsp+70h] [rbp-51h]
  char *v35; // [rsp+78h] [rbp-49h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-31h] BYREF

  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v12 = (const struct _UNICODE_STRING *)"CScrub::ScrubFile";
  *(_QWORD *)(v11 + 16) = "CScrub::ScrubFile";
  v32 = "CScrub::ScrubFile";
  v33 = 0;
  v13 = ++*(_WORD *)(v11 + 8);
  Length = GlobalIndentString.Length;
  v15 = GlobalIndentString.Length;
  if ( v13 < GlobalIndentString.Length )
    v15 = v13;
  LOWORD(v34) = v15;
  if ( v13 < GlobalIndentString.Length )
    Length = v13;
  WORD1(v34) = Length;
  HIDWORD(v34) = 0;
  v35 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubFile");
  }
  if ( !a2 )
    a2 = *((_QWORD *)a1 + 178);
  v16 = (_WORD *)(a2 + 88);
  v34 = a2 + 88;
  v17 = CScrubPath::PushNameEx((struct _UNICODE_STRING *)(a2 + 88), &BackslashString, a4, v12);
  LOWORD(v35) = v17;
  RtlCopyUnicodeString((PUNICODE_STRING)(a2 + 34496), a4);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = a4;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v30 = 0;
  v31 = 0;
  v18 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x604020u);
  if ( v18 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        117,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        a2 + 88,
        v18);
    }
    v19 = v18 | 0x10000000;
    v33 = v19;
LABEL_39:
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    *v16 -= v17;
    goto LABEL_50;
  }
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v21 = *((_QWORD *)a1 + 178);
    if ( v21 > a2 || (v20 = WPP_GLOBAL_Control, a2 > v21 + 35024LL * (*((_DWORD *)a1 + 343) - 1)) )
      LOBYTE(v22) = (a2 - *((_QWORD *)a1 + 177)) / 0x88D0 + 100;
    else
      v22 = (a2 - *((_QWORD *)a1 + 178)) / 0x88D0;
    WPP_SF_DDZdZq(
      v20[2],
      *(_DWORD *)(**(_QWORD **)a1 + 36LL),
      *(_QWORD *)(*(_QWORD *)a1 + 64LL),
      v22,
      a2 + 88,
      (char)FileHandle);
  }
  v23 = CScrub::ScrubData((__int64)a1, (struct _SCRUB_THREAD_CONTEXT *)a2, FileHandle, 0, a7);
  v33 = v23;
  if ( a7 && *(_QWORD *)(a7 + 56) )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v25 = *((_QWORD *)a1 + 178);
      if ( v25 > a2 || (v24 = WPP_GLOBAL_Control, a2 > v25 + 35024LL * (*((_DWORD *)a1 + 343) - 1)) )
        LOBYTE(v26) = (a2 - *((_QWORD *)a1 + 177)) / 0x88D0 + 100;
      else
        v26 = (a2 - *((_QWORD *)a1 + 178)) / 0x88D0;
      WPP_SF_DDZdZq(
        v24[2],
        *(_DWORD *)(**(_QWORD **)a1 + 36LL),
        *(_QWORD *)(*(_QWORD *)a1 + 64LL),
        v26,
        a2 + 88,
        (char)FileHandle);
    }
    if ( v23 == -805306102 )
    {
      _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(a7 + 56) + 8LL), -805306102, 0);
      *(_BYTE *)(*(_QWORD *)(a7 + 56) + 16LL) = 1;
      v19 = -805306102;
    }
    else
    {
      v33 = 0;
      v19 = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)(a7 + 56) + 12LL), 0xFFFFFFFF) != 1 )
      goto LABEL_39;
    v27 = *(_DWORD **)(a7 + 56);
    v23 = v27[2];
    v33 = v23;
    operator delete(v27);
  }
  if ( v23 == -805306102 )
    goto LABEL_42;
  if ( v23 >= 0 )
    ++*(_QWORD *)(a2 + 1504);
  if ( (*((_BYTE *)a1 + 1260) & 8) == 0
    && (v33 = CScrub::_ScrubAlternativeDataStreams((__int64)a1, (struct _SCRUB_THREAD_CONTEXT *)a2, FileHandle),
        v33 == -805306102)
    || (*((_BYTE *)a1 + 1260) & 2) == 0
    && (v33 = CScrub::_ScrubNtfsSystemAttributes(a1, (struct _SCRUB_THREAD_CONTEXT *)a2, FileHandle, a5),
        v33 == -805306102) )
  {
LABEL_42:
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    *v16 -= v17;
    v19 = -805306102;
  }
  else
  {
    v33 = 0;
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    *v16 -= v17;
    v19 = 0;
  }
LABEL_50:
  CHResultImp::~CHResultImp((CHResultImp *)&v32);
  return v19;
}

```

## disassembly

```asm
0x180023a44  push    rbp
0x180023a46  push    rbx
0x180023a47  push    rsi
0x180023a48  push    rdi
0x180023a49  push    r12
0x180023a4b  push    r13
0x180023a4d  push    r14
0x180023a4f  push    r15
0x180023a51  lea     rbp, [rsp-7]
0x180023a56  sub     rsp, 0C8h
0x180023a5d  mov     rdi, r9
0x180023a60  mov     r12, r8
0x180023a63  mov     rsi, rdx
0x180023a66  mov     r14, rcx
0x180023a69  mov     r10d, cs:_tls_index
0x180023a70  mov     rax, gs:58h
0x180023a79  mov     rdx, [rax+r10*8]
0x180023a7d  mov     eax, 10h
0x180023a82  lea     r9, aCscrubScrubfil_0; "CScrub::ScrubFile"
0x180023a89  mov     [rax+rdx], r9
0x180023a8d  mov     [rbp+3Fh+var_A0], r9
0x180023a91  xor     r13d, r13d
0x180023a94  mov     [rbp+3Fh+var_98], r13d
0x180023a98  mov     eax, 8
0x180023a9d  lea     r8d, [r13+1]
0x180023aa1  add     [rax+rdx], r8w
0x180023aa6  movzx   edx, word ptr [rax+rdx]
0x180023aaa  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180023ab1  movzx   eax, cx
0x180023ab4  cmp     dx, cx
0x180023ab7  cmovb   ax, dx
0x180023abb  mov     word ptr [rbp+3Fh+var_90], ax
0x180023abf  cmovb   cx, dx
0x180023ac3  mov     word ptr [rbp+3Fh+var_90+2], cx
0x180023ac7  xor     eax, eax
0x180023ac9  mov     dword ptr [rbp+3Fh+var_90+4], eax
0x180023acc  mov     rax, cs:off_180047060; "                                       "...
0x180023ad3  mov     [rbp+3Fh+var_88], rax
0x180023ad7  lea     rax, WPP_GLOBAL_Control
0x180023ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ae5  cmp     rcx, rax
0x180023ae8  jz      short loc_180023B0D
0x180023aea  test    [rcx+1Ch], r8b
0x180023aee  jz      short loc_180023B0D
0x180023af0  cmp     byte ptr [rcx+19h], 5
0x180023af4  jb      short loc_180023B0D
0x180023af6  lea     edx, [r13+0Dh]
0x180023afa  mov     qword ptr [rsp+100h+ShareAccess], r9; __int64
0x180023aff  lea     r9, [rbp+3Fh+var_90]
0x180023b03  mov     rcx, [rcx+10h]; LoggerHandle
0x180023b07  call    WPP_SF_aZs
0x180023b0c  nop
0x180023b0d  test    rsi, rsi
0x180023b10  jnz     short loc_180023B19
0x180023b12  mov     rsi, [r14+590h]
0x180023b19  lea     rbx, [rsi+58h]
0x180023b1d  mov     [rbp+3Fh+var_90], rbx
0x180023b21  mov     r8, rdi; struct _UNICODE_STRING *
0x180023b24  lea     rdx, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180023b2b  mov     rcx, rbx; this
0x180023b2e  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180023b33  movzx   r15d, ax
0x180023b37  mov     word ptr [rbp+3Fh+var_88], ax
0x180023b3b  lea     rcx, [rsi+86C0h]; DestinationString
0x180023b42  mov     rdx, rdi; SourceString
0x180023b45  call    cs:__imp_RtlCopyUnicodeString
0x180023b4b  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x180023b53  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], 40h ; '@'
0x180023b5b  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r12
0x180023b5f  mov     [rbp+3Fh+ObjectAttributes.ObjectName], rdi
0x180023b63  xorps   xmm0, xmm0
0x180023b66  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180023b6b  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x180023b6f  mov     [rbp+3Fh+FileHandle], r13
0x180023b73  mov     [rbp+3Fh+var_A8], r13d
0x180023b77  mov     [rbp+3Fh+var_A4], r13b
0x180023b7b  mov     [rsp+100h+OpenOptions], 604020h; OpenOptions
0x180023b83  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x180023b8b  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x180023b8f  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x180023b93  mov     edx, 100080h; DesiredAccess
0x180023b98  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x180023b9c  call    cs:__imp_NtOpenFile
0x180023ba2  mov     edi, eax
0x180023ba4  test    eax, eax
0x180023ba6  jns     short loc_180023BEF
0x180023ba8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023baf  lea     rax, WPP_GLOBAL_Control
0x180023bb6  cmp     rcx, rax
0x180023bb9  jz      short loc_180023BE3
0x180023bbb  test    byte ptr [rcx+1Ch], 1
0x180023bbf  jz      short loc_180023BE3
0x180023bc1  cmp     byte ptr [rcx+19h], 2
0x180023bc5  jb      short loc_180023BE3
0x180023bc7  mov     edx, 75h ; 'u'
0x180023bcc  mov     [rsp+100h+ShareAccess], edi
0x180023bd0  mov     r9, rbx
0x180023bd3  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180023bda  mov     rcx, [rcx+10h]
0x180023bde  call    WPP_SF_Zd
0x180023be3  bts     edi, 1Ch
0x180023be7  mov     [rbp+3Fh+var_98], edi
0x180023bea  jmp     loc_180023E04
0x180023bef  mov     r9, 77C150CFB348283Bh
0x180023bf9  mov     r8, cs:WPP_GLOBAL_Control
0x180023c00  lea     rax, WPP_GLOBAL_Control
0x180023c07  cmp     r8, rax
0x180023c0a  jz      loc_180023CBE
0x180023c10  test    byte ptr [r8+1Ch], 1
0x180023c15  jz      loc_180023CBE
0x180023c1b  cmp     byte ptr [r8+19h], 4
0x180023c20  jb      loc_180023CBE
0x180023c26  mov     r10, [rbp+3Fh+FileHandle]
0x180023c2a  mov     rdx, [r14+590h]
0x180023c31  cmp     rdx, rsi
0x180023c34  ja      short loc_180023C70
0x180023c36  mov     eax, [r14+55Ch]
0x180023c3d  dec     eax
0x180023c3f  cdqe
0x180023c41  imul    rcx, rax, 88D0h
0x180023c48  add     rcx, rdx
0x180023c4b  mov     r8, cs:WPP_GLOBAL_Control
0x180023c52  cmp     rsi, rcx
0x180023c55  ja      short loc_180023C70
0x180023c57  mov     rcx, rsi
0x180023c5a  sub     rcx, [r14+590h]
0x180023c61  mov     rax, r9
0x180023c64  mul     rcx
0x180023c67  mov     rcx, rdx
0x180023c6a  shr     rcx, 0Eh
0x180023c6e  jmp     short loc_180023C87
0x180023c70  mov     rcx, rsi
0x180023c73  sub     rcx, [r14+588h]
0x180023c7a  mov     rax, r9
0x180023c7d  mul     rcx
0x180023c80  shr     rdx, 0Eh
0x180023c84  lea     ecx, [rdx+64h]
0x180023c87  mov     rax, [r14]
0x180023c8a  mov     r9, [rax]
0x180023c8d  mov     edx, 76h ; 'v'
0x180023c92  mov     qword ptr [rsp+100h+var_C0], r10; char
0x180023c97  mov     [rsp+100h+var_C8], rbx; __int64
0x180023c9c  mov     dword ptr [rsp+100h+var_D0], ecx; char
0x180023ca0  mov     rax, [rax+40h]
0x180023ca4  mov     qword ptr [rsp+100h+OpenOptions], rax; __int64
0x180023ca9  mov     eax, [r9+24h]
0x180023cad  mov     [rsp+100h+ShareAccess], eax; char
0x180023cb1  mov     r9d, [r9+10h]
0x180023cb5  mov     rcx, [r8+10h]; LoggerHandle
0x180023cb9  call    WPP_SF_DDZdZq
0x180023cbe  mov     r13, [rbp+3Fh+arg_30]
0x180023cc2  mov     qword ptr [rsp+100h+ShareAccess], r13
0x180023cc7  xor     r9d, r9d
0x180023cca  mov     r8, [rbp+3Fh+FileHandle]
0x180023cce  mov     rdx, rsi
0x180023cd1  mov     rcx, r14
0x180023cd4  call    ?ScrubData@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXW4_SCRUB_DATA_TYPE@@PEAU_SCRUB_FILE_ENTRY@@@Z; CScrub::ScrubData(_SCRUB_THREAD_CONTEXT *,void *,_SCRUB_DATA_TYPE,_SCRUB_FILE_ENTRY *)
0x180023cd9  mov     edi, eax
0x180023cdb  mov     [rbp+3Fh+var_98], eax
0x180023cde  mov     r12d, 0D000010Ah
0x180023ce4  test    r13, r13
0x180023ce7  jz      loc_180023E26
0x180023ced  cmp     qword ptr [r13+38h], 0
0x180023cf2  jz      loc_180023E26
0x180023cf8  mov     r8, cs:WPP_GLOBAL_Control
0x180023cff  lea     rax, WPP_GLOBAL_Control
0x180023d06  cmp     r8, rax
0x180023d09  jz      loc_180023DCC
0x180023d0f  test    byte ptr [r8+1Ch], 1
0x180023d14  jz      loc_180023DCC
0x180023d1a  cmp     byte ptr [r8+19h], 4
0x180023d1f  jb      loc_180023DCC
0x180023d25  mov     r10, [rbp+3Fh+FileHandle]
0x180023d29  mov     r9, [r14+590h]
0x180023d30  cmp     r9, rsi
0x180023d33  ja      short loc_180023D77
0x180023d35  mov     ecx, [r14+55Ch]
0x180023d3c  dec     ecx
0x180023d3e  movsxd  rcx, ecx
0x180023d41  imul    rdx, rcx, 88D0h
0x180023d48  add     rdx, r9
0x180023d4b  mov     r8, cs:WPP_GLOBAL_Control
0x180023d52  cmp     rsi, rdx
0x180023d55  ja      short loc_180023D77
0x180023d57  mov     rcx, rsi
0x180023d5a  sub     rcx, [r14+590h]
0x180023d61  mov     rax, 77C150CFB348283Bh
0x180023d6b  mul     rcx
0x180023d6e  mov     rcx, rdx
0x180023d71  shr     rcx, 0Eh
0x180023d75  jmp     short loc_180023D95
0x180023d77  mov     rcx, rsi
0x180023d7a  sub     rcx, [r14+588h]
0x180023d81  mov     rax, 77C150CFB348283Bh
0x180023d8b  mul     rcx
0x180023d8e  shr     rdx, 0Eh
0x180023d92  lea     ecx, [rdx+64h]
0x180023d95  mov     rax, [r14]
0x180023d98  mov     r9, [rax]
0x180023d9b  mov     edx, 77h ; 'w'
0x180023da0  mov     qword ptr [rsp+100h+var_C0], r10; char
0x180023da5  mov     [rsp+100h+var_C8], rbx; __int64
0x180023daa  mov     dword ptr [rsp+100h+var_D0], ecx; char
0x180023dae  mov     rax, [rax+40h]
0x180023db2  mov     qword ptr [rsp+100h+OpenOptions], rax; __int64
0x180023db7  mov     eax, [r9+24h]
0x180023dbb  mov     [rsp+100h+ShareAccess], eax; char
0x180023dbf  mov     r9d, [r9+10h]
0x180023dc3  mov     rcx, [r8+10h]; LoggerHandle
0x180023dc7  call    WPP_SF_DDZdZq
0x180023dcc  cmp     edi, r12d
0x180023dcf  jnz     short loc_180023DEA
0x180023dd1  mov     rcx, [r13+38h]
0x180023dd5  xor     eax, eax
0x180023dd7  lock cmpxchg [rcx+8], r12d
0x180023ddd  mov     rcx, [r13+38h]
0x180023de1  mov     byte ptr [rcx+10h], 1
0x180023de5  mov     edi, r12d
0x180023de8  jmp     short loc_180023DF3
0x180023dea  mov     [rbp+3Fh+var_98], 0
0x180023df1  xor     edi, edi
0x180023df3  mov     rcx, [r13+38h]
0x180023df7  or      eax, 0FFFFFFFFh
0x180023dfa  lock xadd [rcx+0Ch], eax
0x180023dff  cmp     eax, 1
0x180023e02  jz      short loc_180023E17
0x180023e04  lea     rcx, [rbp+3Fh+FileHandle]
0x180023e08  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180023e0d  nop
0x180023e0e  sub     [rbx], r15w
0x180023e12  jmp     loc_180023EA6
0x180023e17  mov     rcx, [r13+38h]; Block
0x180023e1b  mov     edi, [rcx+8]
0x180023e1e  mov     [rbp+3Fh+var_98], edi
0x180023e21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023e26  cmp     edi, r12d
0x180023e29  jnz     short loc_180023E3E
0x180023e2b  lea     rcx, [rbp+3Fh+FileHandle]
0x180023e2f  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180023e34  nop
0x180023e35  sub     [rbx], r15w
0x180023e39  mov     edi, r12d
0x180023e3c  jmp     short loc_180023EA6
0x180023e3e  test    edi, edi
0x180023e40  js      short loc_180023E49
0x180023e42  inc     qword ptr [rsi+5E0h]
0x180023e49  test    byte ptr [r14+4ECh], 8
0x180023e51  jnz     short loc_180023E6A
0x180023e53  mov     r8, [rbp+3Fh+FileHandle]
0x180023e57  mov     rdx, rsi
0x180023e5a  mov     rcx, r14
0x180023e5d  call    ?_ScrubAlternativeDataStreams@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXKW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z; CScrub::_ScrubAlternativeDataStreams(_SCRUB_THREAD_CONTEXT *,void *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS)
0x180023e62  mov     [rbp+3Fh+var_98], eax
0x180023e65  cmp     eax, r12d
0x180023e68  jz      short loc_180023E2B
0x180023e6a  test    byte ptr [r14+4ECh], 2
0x180023e72  jnz     short loc_180023E8F
0x180023e74  mov     r9d, dword ptr [rbp+3Fh+arg_20]; unsigned int
0x180023e78  mov     r8, [rbp+3Fh+FileHandle]; void *
0x180023e7c  mov     rdx, rsi; struct _SCRUB_THREAD_CONTEXT *
0x180023e7f  mov     rcx, r14; this
0x180023e82  call    ?_ScrubNtfsSystemAttributes@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXK@Z; CScrub::_ScrubNtfsSystemAttributes(_SCRUB_THREAD_CONTEXT *,void *,ulong)
0x180023e87  mov     [rbp+3Fh+var_98], eax
0x180023e8a  cmp     eax, r12d
0x180023e8d  jz      short loc_180023E2B
0x180023e8f  mov     [rbp+3Fh+var_98], 0
0x180023e96  lea     rcx, [rbp+3Fh+FileHandle]
0x180023e9a  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180023e9f  nop
0x180023ea0  sub     [rbx], r15w
0x180023ea4  xor     edi, edi
0x180023ea6  lea     rcx, [rbp+3Fh+var_A0]; this
0x180023eaa  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x180023eaf  mov     eax, edi
0x180023eb1  add     rsp, 0C8h
0x180023eb8  pop     r15
0x180023eba  pop     r14
0x180023ebc  pop     r13
0x180023ebe  pop     r12
0x180023ec0  pop     rdi
0x180023ec1  pop     rsi
0x180023ec2  pop     rbx
0x180023ec3  pop     rbp
0x180023ec4  retn
```
