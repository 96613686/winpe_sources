# DfsRootFolder::GetAShortName(void *,uchar *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x14002a848`
- end: `0x14002aa22`
- name: `?GetAShortName@DfsRootFolder@@QEAAJPEAXPEAEPEAU_UNICODE_STRING@@2@Z`
- size: `474`
- prototype: `int(DfsRootFolder *__hidden this, void *, unsigned __int8 *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14002a25c`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005a94`
- `0x1400178d8`
- `0x140028ff8`
- `0x14002a848`

## import_xrefs

- `ntdll!NtQueryDirectoryFile` at `0x14002a8ed`
- `ntdll!NtQueryDirectoryFile` at `0x14002a8ed`
- `ntdll!RtlCompareUnicodeString` at `0x14002a968`
- `ntdll!RtlCompareUnicodeString` at `0x14002a968`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::GetAShortName(
        DfsRootFolder *this,
        void *a2,
        unsigned __int8 *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5)
{
  USHORT *FileInformation; // rax
  USHORT *v9; // rsi
  unsigned int v10; // ebx
  DfsRootFolder *v11; // rcx
  struct _UNICODE_STRING *p_String1; // rdx
  DfsRootFolder *v13; // rcx
  UNICODE_STRING String1; // [rsp+68h] [rbp+Fh] BYREF
  struct _UNICODE_STRING v16; // [rsp+78h] [rbp+1Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp+2Fh] BYREF

  *(_DWORD *)(&v16.MaximumLength + 1) = 0;
  v16.Buffer = (PWSTR)L"\\";
  *a3 = 0;
  *(_DWORD *)&v16.Length = 131074;
  IoStatusBlock = 0;
  String1 = 0;
  FileInformation = (USHORT *)operator new(0x410u);
  v9 = FileInformation;
  if ( FileInformation )
  {
    v10 = NtQueryDirectoryFile(a2, 0, 0, 0, &IoStatusBlock, FileInformation, 0x410u, FileNamesInformation, 1u, a4, 1u);
    if ( !v10 )
    {
      String1.Buffer = v9 + 6;
      String1.MaximumLength = v9[4];
      String1.Length = String1.MaximumLength;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && pWppControl
        && (pWppControl[7] & 0x80000020) != 0
        && *((_BYTE *)pWppControl + 25) >= 3u )
      {
        WPP_SF_ZZD(
          *((_QWORD *)pWppControl + 2),
          80,
          (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
          (_DWORD)a4,
          (__int64)&String1,
          0);
      }
      if ( RtlCompareUnicodeString(&String1, a4, 1u) )
      {
        *a3 = 1;
        p_String1 = &String1;
      }
      else
      {
        *a3 = 0;
        p_String1 = a4;
      }
      v10 = DfsRootFolder::CopyShortName(v11, p_String1, a5);
      if ( !v10 )
        v10 = DfsRootFolder::CopyShortName(v13, &v16, a5);
    }
    operator delete(v9);
  }
  else
  {
    v10 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (v10 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_D(*((_QWORD *)pWppControl + 2), 81, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x14002a848  mov     rax, rsp
0x14002a84b  mov     [rax+8], rbx
0x14002a84f  mov     [rax+10h], rsi
0x14002a853  mov     [rax+18h], rdi
0x14002a857  push    rbp
0x14002a858  push    r12
0x14002a85a  push    r14
0x14002a85c  lea     rbp, [rax-57h]
0x14002a860  sub     rsp, 90h
0x14002a867  and     dword ptr [rbp+4Fh+var_30+4], 0
0x14002a86b  lea     rax, asc_14006334C; "\\"
0x14002a872  xorps   xmm0, xmm0
0x14002a875  mov     [rbp+4Fh+var_30.Buffer], rax
0x14002a879  xorps   xmm1, xmm1
0x14002a87c  mov     byte ptr [r8], 0
0x14002a880  mov     ecx, 410h; Size
0x14002a885  mov     dword ptr [rbp+4Fh+var_30.Length], 20002h
0x14002a88c  movups  xmmword ptr [rbp+4Fh+var_20], xmm0
0x14002a890  mov     r14, r9
0x14002a893  mov     rdi, r8
0x14002a896  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm1
0x14002a89a  mov     rbx, rdx
0x14002a89d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002a8a2  lea     r12, WPP_GLOBAL_Control
0x14002a8a9  mov     rsi, rax
0x14002a8ac  test    rax, rax
0x14002a8af  jz      loc_14002A9B1
0x14002a8b5  mov     [rsp+0A0h+RestartScan], 1; RestartScan
0x14002a8ba  xor     r9d, r9d; ApcContext
0x14002a8bd  mov     [rsp+0A0h+FileName], r14; FileName
0x14002a8c2  xor     r8d, r8d; ApcRoutine
0x14002a8c5  mov     [rsp+0A0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14002a8ca  xor     edx, edx; Event
0x14002a8cc  mov     [rsp+0A0h+FileInformationClass], 0Ch; FileInformationClass
0x14002a8d4  mov     rcx, rbx; FileHandle
0x14002a8d7  mov     [rsp+0A0h+Length], 410h; Length
0x14002a8df  mov     [rsp+0A0h+FileInformation], rax; FileInformation
0x14002a8e4  lea     rax, [rbp+4Fh+var_20]
0x14002a8e8  mov     [rsp+0A0h+IoStatusBlock], rax; IoStatusBlock
0x14002a8ed  call    cs:__imp_NtQueryDirectoryFile
0x14002a8f4  nop     dword ptr [rax+rax+00h]
0x14002a8f9  mov     ebx, eax
0x14002a8fb  test    eax, eax
0x14002a8fd  jnz     loc_14002A9A7
0x14002a903  lea     rax, [rsi+0Ch]
0x14002a907  mov     [rbp+4Fh+String1.Buffer], rax
0x14002a90b  movzx   eax, word ptr [rsi+8]
0x14002a90f  mov     [rbp+4Fh+String1.MaximumLength], ax
0x14002a913  mov     [rbp+4Fh+String1.Length], ax
0x14002a917  cmp     cs:WPP_GLOBAL_Control, r12
0x14002a91e  jz      short loc_14002A95E
0x14002a920  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002a927  test    rcx, rcx
0x14002a92a  jz      short loc_14002A95E
0x14002a92c  test    dword ptr [rcx+1Ch], 80000020h
0x14002a933  jz      short loc_14002A95E
0x14002a935  cmp     byte ptr [rcx+19h], 3
0x14002a939  jb      short loc_14002A95E
0x14002a93b  and     dword ptr [rsp+0A0h+FileInformation], ebx
0x14002a93f  lea     rax, [rbp+4Fh+String1]
0x14002a943  mov     rcx, [rcx+10h]
0x14002a947  lea     edx, [rbx+50h]
0x14002a94a  mov     r9, r14
0x14002a94d  mov     [rsp+0A0h+IoStatusBlock], rax
0x14002a952  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002a959  call    WPP_SF_ZZD
0x14002a95e  mov     r8b, 1; CaseInsensitive
0x14002a961  lea     rcx, [rbp+4Fh+String1]; String1
0x14002a965  mov     rdx, r14; String2
0x14002a968  call    cs:__imp_RtlCompareUnicodeString
0x14002a96f  nop     dword ptr [rax+rax+00h]
0x14002a974  test    eax, eax
0x14002a976  jz      short loc_14002A981
0x14002a978  mov     byte ptr [rdi], 1
0x14002a97b  lea     rdx, [rbp+4Fh+String1]
0x14002a97f  jmp     short loc_14002A987
0x14002a981  mov     byte ptr [rdi], 0
0x14002a984  mov     rdx, r14; struct _UNICODE_STRING *
0x14002a987  mov     rdi, [rbp+4Fh+arg_20]
0x14002a98b  mov     r8, rdi; struct _UNICODE_STRING *
0x14002a98e  call    ?CopyShortName@DfsRootFolder@@QEAAJPEAU_UNICODE_STRING@@0@Z; DfsRootFolder::CopyShortName(_UNICODE_STRING *,_UNICODE_STRING *)
0x14002a993  mov     ebx, eax
0x14002a995  test    eax, eax
0x14002a997  jnz     short loc_14002A9A7
0x14002a999  mov     r8, rdi; struct _UNICODE_STRING *
0x14002a99c  lea     rdx, [rbp+4Fh+var_30]; struct _UNICODE_STRING *
0x14002a9a0  call    ?CopyShortName@DfsRootFolder@@QEAAJPEAU_UNICODE_STRING@@0@Z; DfsRootFolder::CopyShortName(_UNICODE_STRING *,_UNICODE_STRING *)
0x14002a9a5  mov     ebx, eax
0x14002a9a7  mov     rcx, rsi; Block
0x14002a9aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002a9af  jmp     short loc_14002A9B6
0x14002a9b1  mov     ebx, 0C000009Ah
0x14002a9b6  cmp     cs:WPP_GLOBAL_Control, r12
0x14002a9bd  jz      short loc_14002AA02
0x14002a9bf  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002a9c6  test    rcx, rcx
0x14002a9c9  jz      short loc_14002AA02
0x14002a9cb  mov     eax, ebx
0x14002a9cd  neg     eax
0x14002a9cf  mov     eax, 20h ; ' '
0x14002a9d4  sbb     edx, edx
0x14002a9d6  and     edx, 0FFFFFFECh
0x14002a9d9  add     edx, 1Fh
0x14002a9dc  bts     eax, edx
0x14002a9df  test    [rcx+1Ch], eax
0x14002a9e2  jz      short loc_14002AA02
0x14002a9e4  cmp     byte ptr [rcx+19h], 3
0x14002a9e8  jb      short loc_14002AA02
0x14002a9ea  mov     rcx, [rcx+10h]
0x14002a9ee  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002a9f5  mov     edx, 51h ; 'Q'
0x14002a9fa  mov     r9d, ebx
0x14002a9fd  call    WPP_SF_D
0x14002aa02  lea     r11, [rsp+0A0h+var_10]
0x14002aa0a  mov     eax, ebx
0x14002aa0c  mov     rbx, [r11+20h]
0x14002aa10  mov     rsi, [r11+28h]
0x14002aa14  mov     rdi, [r11+30h]
0x14002aa18  mov     rsp, r11
0x14002aa1b  pop     r14
0x14002aa1d  pop     r12
0x14002aa1f  pop     rbp
0x14002aa20  retn
```
