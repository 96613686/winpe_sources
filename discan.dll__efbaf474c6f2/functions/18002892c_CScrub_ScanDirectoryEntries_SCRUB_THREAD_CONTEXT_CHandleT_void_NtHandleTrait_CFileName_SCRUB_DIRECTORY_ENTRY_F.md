# CScrub::_ScanDirectoryEntries(_SCRUB_THREAD_CONTEXT *,CHandleT<void *,NtHandleTrait> *,CFileName *,_SCRUB_DIRECTORY_ENTRY_FLAGS,_UNICODE_STRING const *)

- ea: `0x18002892c`
- end: `0x180028fde`
- name: `?_ScanDirectoryEntries@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAV?$CHandleT@PEAXUNtHandleTrait@@@@PEAVCFileName@@W4_SCRUB_DIRECTORY_ENTRY_FLAGS@@PEBU_UNICODE_STRING@@@Z`
- size: `1714`
- prototype: `__int64 __fastcall(CScrub *this, struct _SCRUB_THREAD_CONTEXT *, HANDLE *, struct CFileName *, int, const UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024280`
- `0x1800293d4`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x18000ad10`
- `0x180012048`
- `0x180012158`
- `0x18001fde0`
- `0x180027858`
- `0x180027a0c`
- `0x180027b88`
- `0x180028360`
- `0x18002892c`
- `0x180029210`
- `0x18002aeec`
- `0x18002c300`
- `0x18002c7d0`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180028bd8`
- `ntdll!RtlCompareUnicodeString` at `0x180028d1e`
- `ntdll!RtlCompareUnicodeString` at `0x180028bd8`
- `ntdll!RtlCompareUnicodeString` at `0x180028d1e`
- `ntdll!NtQueryDirectoryFile` at `0x180028b2b`
- `ntdll!NtQueryDirectoryFile` at `0x180028b2b`
- `ntdll!RtlEqualUnicodeString` at `0x180028b98`
- `ntdll!RtlEqualUnicodeString` at `0x180028bb4`
- `ntdll!RtlEqualUnicodeString` at `0x180028b98`
- `ntdll!RtlEqualUnicodeString` at `0x180028bb4`

## string_xrefs

- `0x18002897a`: `CScrub::_ScanDirectoryEntries`

## pseudocode

```c
__int64 __fastcall CScrub::_ScanDirectoryEntries(
        CScrub *this,
        struct _SCRUB_THREAD_CONTEXT *a2,
        HANDLE *a3,
        struct CFileName *a4,
        int a5,
        const UNICODE_STRING *a6)
{
  HANDLE *v6; // rbx
  struct _SCRUB_THREAD_CONTEXT *v7; // r14
  const UNICODE_STRING *v9; // r15
  __int64 v10; // rdx
  USHORT v11; // dx
  USHORT Length; // cx
  USHORT v13; // ax
  char v14; // cl
  int v15; // edx
  UNICODE_STRING *v16; // r8
  char v17; // al
  unsigned int v18; // r12d
  unsigned int v19; // edi
  unsigned int v20; // eax
  BOOLEAN RestartScan; // al
  const UNICODE_STRING *v22; // r13
  unsigned int *v23; // r15
  NTSTATUS v24; // eax
  struct _SCRUB_THREAD_CONTEXT *v25; // rdx
  int v26; // eax
  int v27; // ebx
  bool v28; // r14
  LONG v29; // ebx
  PVOID *v30; // r10
  PCUNICODE_STRING v31; // rbx
  const struct _UNICODE_STRING *v32; // r8
  const struct _UNICODE_STRING *v33; // r9
  int v34; // eax
  const struct _UNICODE_STRING *FullPathName; // rax
  struct CFileName *IoStatusBlock; // [rsp+20h] [rbp-B9h]
  char FileInformation; // [rsp+28h] [rbp-B1h]
  char v39; // [rsp+60h] [rbp-79h]
  char v40; // [rsp+61h] [rbp-78h]
  bool NextResumeComponent; // [rsp+62h] [rbp-77h]
  int v43; // [rsp+70h] [rbp-69h]
  UNICODE_STRING String2; // [rsp+78h] [rbp-61h] BYREF
  HANDLE *v45; // [rsp+88h] [rbp-51h]
  struct CFileName *v46; // [rsp+90h] [rbp-49h]
  const char *v47; // [rsp+98h] [rbp-41h] BYREF
  int v48; // [rsp+A0h] [rbp-39h]
  PCUNICODE_STRING v49; // [rsp+A8h] [rbp-31h]
  UNICODE_STRING *v50; // [rsp+B0h] [rbp-29h]
  __int64 v51; // [rsp+B8h] [rbp-21h]
  UNICODE_STRING v52; // [rsp+C0h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v53; // [rsp+D0h] [rbp-9h] BYREF

  v46 = a4;
  v6 = a3;
  v45 = a3;
  v7 = a2;
  v9 = a6;
  v51 = (__int64)a6;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v10 + 16) = "CScrub::_ScanDirectoryEntries";
  v47 = "CScrub::_ScanDirectoryEntries";
  v48 = 0;
  v11 = ++*(_WORD *)(v10 + 8);
  Length = GlobalIndentString.Length;
  v13 = GlobalIndentString.Length;
  if ( v11 < GlobalIndentString.Length )
    v13 = v11;
  String2.Length = v13;
  if ( v11 < GlobalIndentString.Length )
    Length = v11;
  String2.MaximumLength = Length;
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Buffer = (PWSTR)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::_ScanDirectoryEntries");
  }
  v53 = 0;
  v52 = 0;
  v14 = 1;
  v39 = 1;
  v15 = *(_DWORD *)(*((_QWORD *)this + 1) + 8LL);
  v43 = v15;
  if ( *((_WORD *)v7 + 17232) )
  {
    NextResumeComponent = CScrub::_GetNextResumeComponent(this, &v52);
    v16 = &v52;
    v50 = &v52;
    v17 = 1;
    v40 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        0);
      v17 = 1;
      v16 = &v52;
    }
    v15 = v43;
    v14 = 1;
  }
  else
  {
    v16 = 0;
    v50 = 0;
    NextResumeComponent = 1;
    v17 = 0;
    v40 = 0;
  }
  v18 = 0;
  v19 = -805306102;
  while ( 2 )
  {
    if ( v17 || v14 || (v20 = 2, v15 != 1) )
      v20 = 1;
    if ( v18 >= v20 )
    {
      v19 = 0;
      goto LABEL_84;
    }
    RestartScan = 1;
    v22 = v16;
    v49 = v9;
LABEL_22:
    v23 = (unsigned int *)((char *)v7 + 1664);
    v24 = NtQueryDirectoryFile(
            *v6,
            *((HANDLE *)v7 + 9),
            0,
            0,
            &v53,
            (char *)v7 + 1664,
            0x8000u,
            FileMaximumInformation|FileBasicInformation,
            0,
            0,
            RestartScan);
    v26 = CScrub::_ScrubWaitIo(this, v25, *v6, &v53, v24, *((HANDLE *)v7 + 9));
    v27 = v26;
    v48 = v26;
    if ( v26 != -805306102 )
    {
      if ( v26 == -1879048186 )
      {
        v48 = 0;
        ++v18;
        v14 = v39;
        v17 = v40;
        v15 = v43;
        v16 = v50;
        v6 = v45;
        v9 = (const UNICODE_STRING *)v51;
        continue;
      }
      if ( v26 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          FullPathName = CScrub::_GetFullPathName(this, v7, v46, 0);
          WPP_SF_DDZZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            (__int64)FullPathName,
            v27);
        }
        break;
      }
      while ( 1 )
      {
        *(_QWORD *)&String2.Length = 0;
        String2.Buffer = (PWSTR)(v23 + 22);
        String2.MaximumLength = *((_WORD *)v23 + 30);
        String2.Length = String2.MaximumLength;
        if ( !RtlEqualUnicodeString(&DotName, &String2, 0) && !RtlEqualUnicodeString(&DotDotName, &String2, 0) )
        {
          v28 = 0;
          if ( v22 )
          {
            v29 = RtlCompareUnicodeString(&String2, v22, 1u);
            if ( v29 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_DDZdZZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                  v18,
                  (__int64)&String2,
                  (__int64)v22);
              }
LABEL_33:
              v7 = a2;
              goto LABEL_34;
            }
            v30 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_DDZddZZ(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                *(_DWORD *)(**(_QWORD **)this + 36LL),
                *(_QWORD *)(*(_QWORD *)this + 64LL),
                v18,
                v29,
                (__int64)&String2,
                (__int64)v22);
              v30 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( !v29 )
              v28 = !NextResumeComponent;
            v22 = 0;
          }
          else
          {
            v31 = v49;
            if ( v49 && (v23[14] & 0x410) != 0x10 )
            {
              if ( RtlCompareUnicodeString(&String2, v49, 1u) < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_DDZdZZ(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    *(_DWORD *)(**(_QWORD **)this + 36LL),
                    *(_QWORD *)(*(_QWORD *)this + 64LL),
                    v18,
                    (__int64)&String2,
                    (__int64)v31);
                }
                goto LABEL_33;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_DDZdZZ(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                  v18,
                  (__int64)&String2,
                  (__int64)v31);
              }
              EventWriteResumeContextFound(
                *((struct _SCRUB_ENVIRONMENT **)this + 1),
                *(const struct _SCRUB_VOLUME_IDENTIFIER **)this,
                v32,
                v33);
              v49 = 0;
            }
            v30 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (v23[14] & 0x410) == 0x10 )
          {
            if ( v18 )
              goto LABEL_33;
            FileInformation = v28;
            v7 = a2;
            v48 = CScrub::_QueueSubDirectoryEntry(
                    (__int64)this,
                    a2,
                    (__int64)v23,
                    v46,
                    (__int64)IoStatusBlock,
                    FileInformation);
            if ( v48 == -805306102 )
              goto LABEL_84;
          }
          else if ( v18 || v43 != 1 )
          {
            if ( v40 )
              goto LABEL_33;
            v7 = a2;
            if ( v43 == 1 )
            {
              v34 = CScrub::_QueueFileEntry((RTL_SRWLOCK *)this, a2, (__int64)v45, (__int64)v23, v46);
            }
            else
            {
              IoStatusBlock = v46;
              v34 = CScrub::_ScrubDirectoryFileEntry(this, a2, *v45, v23);
            }
            v48 = v34;
            if ( v34 == -805306102 )
            {
              v19 = -805306102;
              goto LABEL_84;
            }
          }
          else
          {
            if ( v39 && v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 )
            {
              v7 = a2;
              if ( *((_BYTE *)v30 + 25) >= 4u )
                WPP_SF_DDZd(
                  (unsigned int)v30[2],
                  152,
                  (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                  *(_DWORD *)(**(_QWORD **)this + 16LL),
                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                  ((unsigned __int64)a2 - *((_QWORD *)this + 177)) / 0x88D0);
            }
            else
            {
              v7 = a2;
            }
            v39 = 0;
          }
        }
LABEL_34:
        if ( !*v23 )
        {
          RestartScan = 0;
          v6 = v45;
          goto LABEL_22;
        }
        v23 = (unsigned int *)((char *)v23 + *v23);
      }
    }
    break;
  }
  v19 = v27;
LABEL_84:
  CHResultImp::~CHResultImp((CHResultImp *)&v47);
  return v19;
}

```

## disassembly

```asm
0x18002892c  push    rbp
0x18002892e  push    rbx
0x18002892f  push    rsi
0x180028930  push    rdi
0x180028931  push    r12
0x180028933  push    r13
0x180028935  push    r14
0x180028937  push    r15
0x180028939  lea     rbp, [rsp-0Fh]
0x18002893e  sub     rsp, 0E8h
0x180028945  mov     [rbp+47h+var_90], r9
0x180028949  mov     rbx, r8
0x18002894c  mov     [rbp+47h+var_98], rbx
0x180028950  mov     r14, rdx
0x180028953  mov     [rbp+47h+var_B8], rdx
0x180028957  mov     rsi, rcx
0x18002895a  mov     r15, [rbp+47h+arg_28]
0x18002895e  mov     [rbp+47h+var_68], r15
0x180028962  mov     ecx, cs:_tls_index
0x180028968  mov     rax, gs:58h
0x180028971  mov     rdx, [rax+rcx*8]
0x180028975  mov     eax, 10h
0x18002897a  lea     r8, aCscrubScandire; "CScrub::_ScanDirectoryEntries"
0x180028981  mov     [rax+rdx], r8
0x180028985  mov     [rbp+47h+var_88], r8
0x180028989  xor     r13d, r13d
0x18002898c  mov     [rbp+47h+var_80], r13d
0x180028990  mov     eax, 8
0x180028995  lea     r9d, [r13+1]
0x180028999  add     [rax+rdx], r9w
0x18002899e  movzx   edx, word ptr [rax+rdx]
0x1800289a2  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x1800289a9  movzx   eax, cx
0x1800289ac  cmp     dx, cx
0x1800289af  cmovb   ax, dx
0x1800289b3  mov     [rbp+47h+String2.Length], ax
0x1800289b7  cmovb   cx, dx
0x1800289bb  mov     [rbp+47h+String2.MaximumLength], cx
0x1800289bf  xor     eax, eax
0x1800289c1  mov     dword ptr [rbp+47h+String2+4], eax
0x1800289c4  mov     rax, cs:off_180047060; "                                       "...
0x1800289cb  mov     [rbp+47h+String2.Buffer], rax
0x1800289cf  lea     rdi, WPP_GLOBAL_Control
0x1800289d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289dd  cmp     rcx, rdi
0x1800289e0  jz      short loc_180028A08
0x1800289e2  test    [rcx+1Ch], r9b
0x1800289e6  jz      short loc_180028A08
0x1800289e8  cmp     byte ptr [rcx+19h], 5
0x1800289ec  jb      short loc_180028A08
0x1800289ee  lea     edx, [r13+0Dh]
0x1800289f2  mov     [rsp+120h+IoStatusBlock], r8; __int64
0x1800289f7  lea     r9, [rbp+47h+String2]
0x1800289fb  mov     rcx, [rcx+10h]; LoggerHandle
0x1800289ff  call    WPP_SF_aZs
0x180028a04  lea     r9d, [r13+1]
0x180028a08  xorps   xmm0, xmm0
0x180028a0b  movups  xmmword ptr [rbp+47h+var_50], xmm0
0x180028a0f  xorps   xmm1, xmm1
0x180028a12  movups  xmmword ptr [rbp+47h+var_60.Length], xmm1
0x180028a16  mov     cl, r9b
0x180028a19  mov     [rbp+47h+var_C0], cl
0x180028a1c  mov     rax, [rsi+8]
0x180028a20  mov     edx, [rax+8]
0x180028a23  mov     [rbp+47h+var_B0], edx
0x180028a26  cmp     [r14+86A0h], r13w
0x180028a2e  jbe     loc_180028C5C
0x180028a34  lea     rdx, [rbp+47h+var_60]; struct _UNICODE_STRING *
0x180028a38  mov     rcx, rsi; this
0x180028a3b  call    ?_GetNextResumeComponent@CScrub@@AEAA_NPEAU_UNICODE_STRING@@@Z; CScrub::_GetNextResumeComponent(_UNICODE_STRING *)
0x180028a40  mov     [rbp+47h+var_BE], al
0x180028a43  lea     r8, [rbp+47h+var_60]
0x180028a47  mov     [rbp+47h+var_70], r8
0x180028a4b  mov     r9d, 1
0x180028a51  mov     al, r9b
0x180028a54  mov     [rbp+47h+var_BF], al
0x180028a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a5e  cmp     rcx, rdi
0x180028a61  jz      short loc_180028AB1
0x180028a63  test    [rcx+1Ch], r9b
0x180028a67  jz      short loc_180028AB1
0x180028a69  cmp     byte ptr [rcx+19h], 4
0x180028a6d  jb      short loc_180028AB1
0x180028a6f  mov     rax, [rsi]
0x180028a72  mov     r9, [rax]
0x180028a75  mov     edx, 92h
0x180028a7a  mov     qword ptr [rsp+120h+Length], r13; __int64
0x180028a7f  mov     rax, [rax+40h]
0x180028a83  mov     [rsp+120h+FileInformation], rax; __int64
0x180028a88  mov     eax, [r9+24h]
0x180028a8c  mov     dword ptr [rsp+120h+IoStatusBlock], eax; char
0x180028a90  mov     r9d, [r9+10h]
0x180028a94  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180028a9b  mov     rcx, [rcx+10h]; LoggerHandle
0x180028a9f  call    WPP_SF_DDZZ
0x180028aa4  mov     al, [rbp+47h+var_BF]
0x180028aa7  lea     r8, [rbp+47h+var_60]
0x180028aab  mov     r9d, 1
0x180028ab1  mov     edx, [rbp+47h+var_B0]
0x180028ab4  mov     cl, [rbp+47h+var_C0]
0x180028ab7  mov     r12d, r13d
0x180028aba  mov     edi, 0D000010Ah
0x180028abf  test    al, al
0x180028ac1  jnz     short loc_180028AD1
0x180028ac3  test    cl, cl
0x180028ac5  jnz     short loc_180028AD1
0x180028ac7  cmp     edx, r9d
0x180028aca  mov     eax, 2
0x180028acf  jz      short loc_180028AD4
0x180028ad1  mov     eax, r9d
0x180028ad4  cmp     r12d, eax
0x180028ad7  jnb     loc_180028FBC
0x180028add  mov     al, r9b
0x180028ae0  mov     r13, r8
0x180028ae3  mov     [rbp+47h+var_78], r15
0x180028ae7  lea     r15, [r14+680h]
0x180028aee  mov     [rsp+120h+RestartScan], al; RestartScan
0x180028af2  mov     [rsp+120h+FileName], 0; FileName
0x180028afb  mov     [rsp+120h+ReturnSingleEntry], 0; ReturnSingleEntry
0x180028b00  mov     [rsp+120h+FileInformationClass], 3Ch ; '<'; FileInformationClass
0x180028b08  mov     [rsp+120h+Length], 8000h; Length
0x180028b10  mov     [rsp+120h+FileInformation], r15; FileInformation
0x180028b15  lea     rax, [rbp+47h+var_50]
0x180028b19  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x180028b1e  xor     r9d, r9d; ApcContext
0x180028b21  xor     r8d, r8d; ApcRoutine
0x180028b24  mov     rdx, [r14+48h]; Event
0x180028b28  mov     rcx, [rbx]; FileHandle
0x180028b2b  call    cs:__imp_NtQueryDirectoryFile
0x180028b31  mov     rcx, [r14+48h]
0x180028b35  mov     [rsp+120h+FileInformation], rcx; Handle
0x180028b3a  mov     dword ptr [rsp+120h+IoStatusBlock], eax; struct _UNICODE_STRING *
0x180028b3e  lea     r9, [rbp+47h+var_50]; struct _IO_STATUS_BLOCK *
0x180028b42  mov     r8, [rbx]; void *
0x180028b45  mov     rcx, rsi; this
0x180028b48  call    ?_ScrubWaitIo@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEAU_IO_STATUS_BLOCK@@J1@Z; CScrub::_ScrubWaitIo(_SCRUB_THREAD_CONTEXT *,void *,_IO_STATUS_BLOCK *,long,void *)
0x180028b4d  mov     ebx, eax
0x180028b4f  mov     [rbp+47h+var_80], eax
0x180028b52  cmp     eax, edi
0x180028b54  jz      loc_180028FB8
0x180028b5a  cmp     eax, 90000006h
0x180028b5f  jz      loc_180028F1F
0x180028b65  test    eax, eax
0x180028b67  js      loc_180028F47
0x180028b6d  mov     qword ptr [rbp+47h+String2.Length], 0
0x180028b75  lea     rax, [r15+58h]
0x180028b79  mov     [rbp+47h+String2.Buffer], rax
0x180028b7d  movzx   eax, word ptr [r15+3Ch]
0x180028b82  mov     [rbp+47h+String2.MaximumLength], ax
0x180028b86  mov     [rbp+47h+String2.Length], ax
0x180028b8a  xor     r8d, r8d; CaseInsensitive
0x180028b8d  lea     rdx, [rbp+47h+String2]; String2
0x180028b91  lea     rcx, ?DotName@@3U_UNICODE_STRING@@B; String1
0x180028b98  call    cs:__imp_RtlEqualUnicodeString
0x180028b9e  test    al, al
0x180028ba0  jnz     loc_180028C47
0x180028ba6  xor     r8d, r8d; CaseInsensitive
0x180028ba9  lea     rdx, [rbp+47h+String2]; String2
0x180028bad  lea     rcx, ?DotDotName@@3U_UNICODE_STRING@@B; String1
0x180028bb4  call    cs:__imp_RtlEqualUnicodeString
0x180028bba  test    al, al
0x180028bbc  jnz     loc_180028C47
0x180028bc2  xor     r14b, r14b
0x180028bc5  test    r13, r13
0x180028bc8  jz      loc_180028CF5
0x180028bce  mov     r8b, 1; CaseInsensitive
0x180028bd1  mov     rdx, r13; String2
0x180028bd4  lea     rcx, [rbp+47h+String2]; String1
0x180028bd8  call    cs:__imp_RtlCompareUnicodeString
0x180028bde  mov     ebx, eax
0x180028be0  test    eax, eax
0x180028be2  jns     loc_180028C72
0x180028be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bef  lea     rax, WPP_GLOBAL_Control
0x180028bf6  cmp     rcx, rax
0x180028bf9  jz      short loc_180028C43
0x180028bfb  test    byte ptr [rcx+1Ch], 1
0x180028bff  jz      short loc_180028C43
0x180028c01  cmp     byte ptr [rcx+19h], 4
0x180028c05  jb      short loc_180028C43
0x180028c07  mov     edx, 94h
0x180028c0c  mov     qword ptr [rsp+120h+ReturnSingleEntry], r13; __int64
0x180028c11  mov     rax, [rsi]
0x180028c14  mov     r9, [rax]
0x180028c17  lea     r8, [rbp+47h+String2]
0x180028c1b  mov     qword ptr [rsp+120h+FileInformationClass], r8; __int64
0x180028c20  mov     [rsp+120h+Length], r12d; char
0x180028c25  mov     rax, [rax+40h]
0x180028c29  mov     [rsp+120h+FileInformation], rax; __int64
0x180028c2e  mov     eax, [r9+24h]
0x180028c32  mov     dword ptr [rsp+120h+IoStatusBlock], eax; char
0x180028c36  mov     r9d, [r9+10h]
0x180028c3a  mov     rcx, [rcx+10h]; LoggerHandle
0x180028c3e  call    WPP_SF_DDZdZZ
0x180028c43  mov     r14, [rbp+47h+var_B8]
0x180028c47  cmp     dword ptr [r15], 0
0x180028c4b  jz      loc_180028F14
0x180028c51  mov     eax, [r15]
0x180028c54  add     r15, rax
0x180028c57  jmp     loc_180028B6D
0x180028c5c  mov     r8, r13
0x180028c5f  mov     [rbp+47h+var_70], r13
0x180028c63  mov     [rbp+47h+var_BE], r9b
0x180028c67  mov     al, r13b
0x180028c6a  mov     [rbp+47h+var_BF], al
0x180028c6d  jmp     loc_180028AB7
0x180028c72  mov     r10, cs:WPP_GLOBAL_Control
0x180028c79  lea     rax, WPP_GLOBAL_Control
0x180028c80  cmp     r10, rax
0x180028c83  mov     eax, 1
0x180028c88  jz      short loc_180028CDE
0x180028c8a  test    [r10+1Ch], al
0x180028c8e  jz      short loc_180028CDE
0x180028c90  cmp     byte ptr [r10+19h], 4
0x180028c95  jb      short loc_180028CDE
0x180028c97  mov     rax, [rsi]
0x180028c9a  mov     r9, [rax]
0x180028c9d  mov     [rsp+120h+FileName], r13; __int64
0x180028ca2  lea     rcx, [rbp+47h+String2]
0x180028ca6  mov     qword ptr [rsp+120h+ReturnSingleEntry], rcx; __int64
0x180028cab  mov     [rsp+120h+FileInformationClass], ebx; char
0x180028caf  mov     [rsp+120h+Length], r12d; char
0x180028cb4  mov     rax, [rax+40h]
0x180028cb8  mov     [rsp+120h+FileInformation], rax; __int64
0x180028cbd  mov     eax, [r9+24h]
0x180028cc1  mov     dword ptr [rsp+120h+IoStatusBlock], eax; char
0x180028cc5  mov     r9d, [r9+10h]
0x180028cc9  mov     rcx, [r10+10h]; LoggerHandle
0x180028ccd  call    WPP_SF_DDZddZZ
0x180028cd2  mov     r10, cs:WPP_GLOBAL_Control
0x180028cd9  mov     eax, 1
0x180028cde  test    ebx, ebx
0x180028ce0  jnz     short loc_180028CED
0x180028ce2  movzx   r14d, r14b
0x180028ce6  cmp     [rbp+47h+var_BE], bl
0x180028ce9  cmovz   r14d, eax
0x180028ced  xor     r13d, r13d
0x180028cf0  jmp     loc_180028DD6
0x180028cf5  mov     rbx, [rbp+47h+var_78]
0x180028cf9  test    rbx, rbx
0x180028cfc  jz      loc_180028DCF
0x180028d02  mov     eax, [r15+38h]
0x180028d06  and     eax, 410h
0x180028d0b  cmp     eax, 10h
0x180028d0e  jz      loc_180028DCF
0x180028d14  mov     r8b, 1; CaseInsensitive
0x180028d17  mov     rdx, rbx; String2
0x180028d1a  lea     rcx, [rbp+47h+String2]; String1
0x180028d1e  call    cs:__imp_RtlCompareUnicodeString
0x180028d24  test    eax, eax
0x180028d26  jns     short loc_180028D62
0x180028d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d2f  lea     rax, WPP_GLOBAL_Control
0x180028d36  cmp     rcx, rax
0x180028d39  jz      loc_180028C43
0x180028d3f  test    byte ptr [rcx+1Ch], 1
0x180028d43  jz      loc_180028C43
0x180028d49  cmp     byte ptr [rcx+19h], 4
0x180028d4d  jb      loc_180028C43
0x180028d53  mov     edx, 96h
0x180028d58  mov     qword ptr [rsp+120h+ReturnSingleEntry], rbx
0x180028d5d  jmp     loc_180028C11
0x180028d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180028d69  lea     rax, WPP_GLOBAL_Control
0x180028d70  cmp     rcx, rax
0x180028d73  jz      short loc_180028DBD
0x180028d75  test    byte ptr [rcx+1Ch], 1
0x180028d79  jz      short loc_180028DBD
0x180028d7b  cmp     byte ptr [rcx+19h], 4
0x180028d7f  jb      short loc_180028DBD
0x180028d81  mov     rax, [rsi]
0x180028d84  mov     r9, [rax]
0x180028d87  mov     edx, 97h
0x180028d8c  mov     qword ptr [rsp+120h+ReturnSingleEntry], rbx; __int64
0x180028d91  lea     r8, [rbp+47h+String2]
0x180028d95  mov     qword ptr [rsp+120h+FileInformationClass], r8; __int64
0x180028d9a  mov     [rsp+120h+Length], r12d; char
0x180028d9f  mov     rax, [rax+40h]
0x180028da3  mov     [rsp+120h+FileInformation], rax; __int64
0x180028da8  mov     eax, [r9+24h]
0x180028dac  mov     dword ptr [rsp+120h+IoStatusBlock], eax; char
0x180028db0  mov     r9d, [r9+10h]
0x180028db4  mov     rcx, [rcx+10h]; LoggerHandle
0x180028db8  call    WPP_SF_DDZdZZ
0x180028dbd  mov     rdx, [rsi]; struct _SCRUB_VOLUME_IDENTIFIER *
0x180028dc0  mov     rcx, [rsi+8]; struct _SCRUB_ENVIRONMENT *
0x180028dc4  call    ?EventWriteResumeContextFound@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@PEBU_UNICODE_STRING@@2@Z; EventWriteResumeContextFound(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180028dc9  xor     ecx, ecx
0x180028dcb  mov     [rbp+47h+var_78], rcx
0x180028dcf  mov     r10, cs:WPP_GLOBAL_Control
0x180028dd6  mov     eax, [r15+38h]
0x180028dda  and     eax, 410h
0x180028ddf  cmp     eax, 10h
0x180028de2  jnz     short loc_180028E18
0x180028de4  test    r12d, r12d
0x180028de7  jnz     loc_180028C43
0x180028ded  mov     byte ptr [rsp+120h+FileInformation], r14b
0x180028df2  mov     r9, [rbp+47h+var_90]
0x180028df6  mov     r8, r15
0x180028df9  mov     r14, [rbp+47h+var_B8]
  ... truncated ...
```
