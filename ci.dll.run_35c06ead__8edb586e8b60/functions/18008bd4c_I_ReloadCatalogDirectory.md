# I_ReloadCatalogDirectory

- ea: `0x18008bd4c`
- end: `0x18008c19a`
- name: `I_ReloadCatalogDirectory`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061ae8`

## callees

- `0x18000c53c`
- `0x18008bd4c`
- `0x18008c1a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18008be96`
- `ntoskrnl!RtlInitUnicodeString` at `0x18008be96`
- `ntoskrnl!ExAllocatePool2` at `0x18008be5b`
- `ntoskrnl!ExAllocatePool2` at `0x18008be5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008c189`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008c189`
- `ntoskrnl!ZwOpenFile` at `0x18008be04`
- `ntoskrnl!ZwOpenFile` at `0x18008be04`
- `ntoskrnl!ZwClose` at `0x18008be1f`
- `ntoskrnl!ZwClose` at `0x18008be1f`
- `ntoskrnl!qsort` at `0x18008bf7e`
- `ntoskrnl!qsort` at `0x18008bf7e`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x18008beeb`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x18008beeb`

## pseudocode

```c
__int64 __fastcall I_ReloadCatalogDirectory(
        int a1,
        char a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        UNICODE_STRING *a7,
        _DWORD *a8)
{
  unsigned int *v8; // rdi
  UNICODE_STRING *v9; // r14
  NTSTATUS v10; // esi
  __int64 Pool2; // rax
  _QWORD *v13; // r12
  unsigned int *v14; // r15
  BOOLEAN RestartScan; // bl
  FILE_INFORMATION_CLASS FileInformationClass; // ecx
  NTSTATUS v17; // eax
  unsigned int *i; // rbx
  __int64 v19; // r14
  unsigned int v20; // eax
  _WORD *j; // rcx
  __int64 v22; // rax
  __int64 k; // r12
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  __int64 v29; // [rsp+68h] [rbp-81h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-71h] BYREF
  PCUNICODE_STRING v32; // [rsp+88h] [rbp-61h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-19h] BYREF
  int v38; // [rsp+148h] [rbp+5Fh]
  FILE_INFORMATION_CLASS v40; // [rsp+168h] [rbp+7Fh]

  FileHandle = 0;
  LODWORD(v29) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v8 = 0;
  memset(&ObjectAttributes.Length + 1, 0, 20);
  IoStatusBlock = 0;
  DestinationString = 0;
  SourceString = 0;
  CiGetCurrentSiloState();
  v9 = (UNICODE_STRING *)&stru_18002E470;
  ObjectAttributes.Length = 48;
  *a8 = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a7 )
    v9 = a7;
  v32 = v9;
  ObjectAttributes.ObjectName = v9;
  v10 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v10 >= 0 )
  {
    Pool2 = ExAllocatePool2(258, 155648, 1919109443);
    v8 = (unsigned int *)Pool2;
    if ( Pool2 )
    {
      v10 = 0;
      v13 = (_QWORD *)(Pool2 + 153600);
      v14 = 0;
      v38 = 0;
      RestartScan = 1;
      _InterlockedIncrement(&g_ReloadInProgressCount);
      RtlInitUnicodeString(&DestinationString, L"*.cat");
      FileInformationClass = FileIdFullDirectoryInformation;
LABEL_11:
      while ( 1 )
      {
        v40 = FileInformationClass;
        while ( 1 )
        {
          v17 = ZwQueryDirectoryFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  v8,
                  0x25800u,
                  FileInformationClass,
                  v14 != 0,
                  &DestinationString,
                  RestartScan);
          if ( v17 < 0 )
            break;
          if ( v14 )
          {
            SourceString.Buffer = (PWSTR)(v14 + 16);
            SourceString.MaximumLength = *((_WORD *)v14 + 30);
            SourceString.Length = SourceString.MaximumLength;
            v27 = I_ReloadCatalog(
                    a1,
                    0,
                    a4,
                    a5,
                    a6,
                    &SourceString,
                    v32,
                    0,
                    0,
                    (__int64)(v14 + 6),
                    (__int64)(v14 + 8),
                    (__int64)&v29);
            if ( v27 < 0 )
            {
              if ( v27 == -1073741801 || v27 == -1073741670 )
                v10 = v27;
            }
            else
            {
              v28 = v29;
              *a8 |= v29;
              if ( v28 )
                ++v38;
            }
          }
          else
          {
            for ( i = v8; ; i = (unsigned int *)((char *)i + v26) )
            {
              v19 = 0;
              while ( 1 )
              {
                if ( a2 )
                {
                  v20 = i[15] >> 1;
                  if ( v20 >= 0xB )
                  {
                    for ( j = i + 20; j < (_WORD *)i + v20 + 30; ++j )
                    {
                      if ( *j == 126 && j[3] == 45 && j[6] == 126 )
                        goto LABEL_26;
                    }
                  }
                }
                v13[v19] = i;
                v19 = (unsigned int)(v19 + 1);
LABEL_26:
                v22 = *i;
                if ( !(_DWORD)v22 || (_DWORD)v19 == 256 )
                  break;
                i = (unsigned int *)((char *)i + v22);
              }
              qsort(v13, (unsigned int)v19, 8u, I_SortDirectoryInfoByFileId);
              for ( k = 0; (unsigned int)k < (unsigned int)v19; k = (unsigned int)(k + 1) )
              {
                SourceString.Buffer = (PWSTR)(*(_QWORD *)&v8[2 * k + 38400] + 80LL);
                SourceString.MaximumLength = *(_WORD *)(*(_QWORD *)&v8[2 * k + 38400] + 60LL);
                SourceString.Length = SourceString.MaximumLength;
                v24 = I_ReloadCatalog(
                        a1,
                        0,
                        a4,
                        a5,
                        a6,
                        &SourceString,
                        v32,
                        (int)FileHandle,
                        (unsigned int)*(_QWORD *)&v8[2 * k + 38400] + 72,
                        *(_QWORD *)&v8[2 * k + 38400] + 24LL,
                        *(_QWORD *)&v8[2 * k + 38400] + 32LL,
                        (__int64)&v29);
                if ( v24 < 0 )
                {
                  if ( !v38 )
                  {
                    FileInformationClass = FileDirectoryInformation;
                    v13 = v8 + 38400;
                    RestartScan = 1;
                    v14 = v8;
                    goto LABEL_11;
                  }
                  if ( v24 == -1073741670 || v24 == -1073741801 )
                    v10 = v24;
                }
                else
                {
                  v25 = v29;
                  *a8 |= v29;
                  if ( v25 )
                    ++v38;
                }
              }
              v26 = *i;
              v13 = v8 + 38400;
              if ( !(_DWORD)v26 )
                break;
            }
          }
          FileInformationClass = v40;
          RestartScan = 0;
        }
        if ( !RestartScan || v14 )
          break;
        v14 = v8;
        FileInformationClass = FileDirectoryInformation;
      }
      if ( v10 >= 0 && (v17 == -1073741801 || v17 == -1073741670) )
        v10 = v17;
      _InterlockedDecrement(&g_ReloadInProgressCount);
    }
    else
    {
      v10 = -1073741801;
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x72634943u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008bd4c  mov     rax, rsp
0x18008bd4f  mov     [rax+20h], r9d
0x18008bd53  mov     [rax+18h], r8b
0x18008bd57  mov     [rax+10h], dl
0x18008bd5a  mov     [rax+8], rcx
0x18008bd5e  push    rbp
0x18008bd5f  push    rbx
0x18008bd60  push    rsi
0x18008bd61  push    rdi
0x18008bd62  push    r12
0x18008bd64  push    r13
0x18008bd66  push    r14
0x18008bd68  push    r15
0x18008bd6a  lea     rbp, [rax-47h]
0x18008bd6e  sub     rsp, 0E8h
0x18008bd75  xorps   xmm0, xmm0
0x18008bd78  xor     ebx, ebx
0x18008bd7a  xorps   xmm1, xmm1
0x18008bd7d  mov     [rbp+3Fh+FileHandle], rbx
0x18008bd81  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x18008bd85  xor     eax, eax
0x18008bd87  mov     dword ptr [rsp+120h+var_C0], ebx
0x18008bd8b  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x18008bd8f  mov     edi, ebx
0x18008bd91  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x18008bd95  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x18008bd99  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x18008bd9d  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x18008bda1  call    CiGetCurrentSiloState
0x18008bda6  mov     rax, [rbp+3Fh+arg_38]
0x18008bdad  lea     r14, stru_18002E470
0x18008bdb4  xorps   xmm0, xmm0
0x18008bdb7  mov     [rsp+120h+OpenOptions], 4021h; OpenOptions
0x18008bdbf  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x18008bdc3  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18008bdca  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x18008bdce  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x18008bdd2  mov     [rax], ebx
0x18008bdd4  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x18008bdd8  mov     rax, [rbp+3Fh+arg_30]
0x18008bddc  mov     edx, 100001h; DesiredAccess
0x18008bde1  test    rax, rax
0x18008bde4  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x18008bdeb  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18008bdf0  cmovnz  r14, rax
0x18008bdf4  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x18008bdfc  mov     [rbp+3Fh+var_A0], r14
0x18008be00  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x18008be04  call    cs:__imp_ZwOpenFile
0x18008be0b  nop     dword ptr [rax+rax+00h]
0x18008be10  mov     esi, eax
0x18008be12  test    eax, eax
0x18008be14  jns     short loc_18008BE4B
0x18008be16  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x18008be1a  test    rcx, rcx
0x18008be1d  jz      short loc_18008BE2B
0x18008be1f  call    cs:__imp_ZwClose
0x18008be26  nop     dword ptr [rax+rax+00h]
0x18008be2b  test    rdi, rdi
0x18008be2e  jnz     loc_18008C181
0x18008be34  mov     eax, esi
0x18008be36  add     rsp, 0E8h
0x18008be3d  pop     r15
0x18008be3f  pop     r14
0x18008be41  pop     r13
0x18008be43  pop     r12
0x18008be45  pop     rdi
0x18008be46  pop     rsi
0x18008be47  pop     rbx
0x18008be48  pop     rbp
0x18008be49  retn
0x18008be4b  mov     edx, 26000h
0x18008be50  mov     ecx, 102h
0x18008be55  mov     r8d, 72634943h
0x18008be5b  call    cs:__imp_ExAllocatePool2
0x18008be62  nop     dword ptr [rax+rax+00h]
0x18008be67  mov     rdi, rax
0x18008be6a  test    rax, rax
0x18008be6d  jz      loc_18008C13C
0x18008be73  xor     esi, esi
0x18008be75  lea     r12, [rax+25800h]
0x18008be7c  xor     r15d, r15d
0x18008be7f  mov     [rbp+3Fh+arg_10], esi
0x18008be82  mov     bl, 1
0x18008be84  lock inc cs:g_ReloadInProgressCount
0x18008be8b  lea     rdx, aCat; "*.cat"
0x18008be92  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18008be96  call    cs:__imp_RtlInitUnicodeString
0x18008be9d  nop     dword ptr [rax+rax+00h]
0x18008bea2  lea     ecx, [rsi+26h]
0x18008bea5  mov     r13d, 0C0000017h
0x18008beab  mov     dword ptr [rbp+3Fh+arg_30], ecx
0x18008beae  mov     [rsp+120h+RestartScan], bl; RestartScan
0x18008beb2  lea     rdx, [rbp+3Fh+DestinationString]
0x18008beb6  mov     [rsp+120h+FileName], rdx; FileName
0x18008bebb  test    r15, r15
0x18008bebe  setnz   al
0x18008bec1  xor     r9d, r9d; ApcContext
0x18008bec4  mov     [rsp+120h+ReturnSingleEntry], al; ReturnSingleEntry
0x18008bec8  xor     r8d, r8d; ApcRoutine
0x18008becb  mov     [rsp+120h+FileInformationClass], ecx; FileInformationClass
0x18008becf  lea     rax, [rbp+3Fh+IoStatusBlock]
0x18008bed3  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x18008bed7  xor     edx, edx; Event
0x18008bed9  mov     [rsp+120h+Length], 25800h; Length
0x18008bee1  mov     qword ptr [rsp+120h+OpenOptions], rdi; FileInformation
0x18008bee6  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x18008beeb  call    cs:__imp_ZwQueryDirectoryFile
0x18008bef2  nop     dword ptr [rax+rax+00h]
0x18008bef7  test    eax, eax
0x18008bef9  js      loc_18008C114
0x18008beff  test    r15, r15
0x18008bf02  jnz     loc_18008C083
0x18008bf08  mov     rbx, rdi
0x18008bf0b  mov     r13b, [rbp+3Fh+arg_8]
0x18008bf0f  xor     r14d, r14d
0x18008bf12  test    r13b, r13b
0x18008bf15  jz      short loc_18008BF50
0x18008bf17  mov     eax, [rbx+3Ch]
0x18008bf1a  shr     eax, 1
0x18008bf1c  cmp     eax, 0Bh
0x18008bf1f  jb      short loc_18008BF50
0x18008bf21  mov     edx, eax
0x18008bf23  lea     rcx, [rbx+50h]
0x18008bf27  add     rdx, 0FFFFFFFFFFFFFFF6h
0x18008bf2b  lea     rdx, [rcx+rdx*2]
0x18008bf2f  cmp     rcx, rdx
0x18008bf32  jnb     short loc_18008BF50
0x18008bf34  cmp     word ptr [rcx], 7Eh ; '~'
0x18008bf38  jz      short loc_18008BF40
0x18008bf3a  add     rcx, 2
0x18008bf3e  jmp     short loc_18008BF2F
0x18008bf40  cmp     word ptr [rcx+6], 2Dh ; '-'
0x18008bf45  jnz     short loc_18008BF3A
0x18008bf47  cmp     word ptr [rcx+0Ch], 7Eh ; '~'
0x18008bf4c  jnz     short loc_18008BF3A
0x18008bf4e  jmp     short loc_18008BF57
0x18008bf50  mov     [r12+r14*8], rbx
0x18008bf54  inc     r14d
0x18008bf57  mov     eax, [rbx]
0x18008bf59  test    eax, eax
0x18008bf5b  jz      short loc_18008BF6B
0x18008bf5d  cmp     r14d, 100h
0x18008bf64  jz      short loc_18008BF6B
0x18008bf66  add     rbx, rax
0x18008bf69  jmp     short loc_18008BF12
0x18008bf6b  mov     edx, r14d; NumOfElements
0x18008bf6e  lea     r9, I_SortDirectoryInfoByFileId; PtFuncCompare
0x18008bf75  mov     r8d, 8; SizeOfElements
0x18008bf7b  mov     rcx, r12; Base
0x18008bf7e  call    cs:__imp_qsort
0x18008bf85  nop     dword ptr [rax+rax+00h]
0x18008bf8a  xor     r12d, r12d
0x18008bf8d  mov     r13d, 0C0000017h
0x18008bf93  cmp     r12d, r14d
0x18008bf96  jnb     loc_18008C068
0x18008bf9c  mov     r9d, [rbp+3Fh+arg_20]; int
0x18008bfa0  lea     r8, [rdi+25800h]
0x18008bfa7  mov     rax, [r8+r12*8]
0x18008bfab  add     rax, 50h ; 'P'
0x18008bfaf  mov     [rbp+3Fh+SourceString.Buffer], rax
0x18008bfb3  mov     rax, [r8+r12*8]
0x18008bfb7  movzx   ecx, word ptr [rax+3Ch]
0x18008bfbb  mov     [rbp+3Fh+SourceString.MaximumLength], cx
0x18008bfbf  mov     [rbp+3Fh+SourceString.Length], cx
0x18008bfc3  mov     rax, [r8+r12*8]
0x18008bfc7  lea     r8, [rsp+120h+var_C0]
0x18008bfcc  mov     [rsp+120h+var_C8], r8; __int64
0x18008bfd1  mov     r8d, [rbp+3Fh+arg_18]; int
0x18008bfd5  lea     rcx, [rax+20h]
0x18008bfd9  lea     rdx, [rax+18h]
0x18008bfdd  mov     qword ptr [rsp+120h+RestartScan], rcx; __int64
0x18008bfe2  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x18008bfe6  add     rax, 48h ; 'H'
0x18008bfea  mov     [rsp+120h+FileName], rdx; __int64
0x18008bfef  xor     edx, edx; int
0x18008bff1  mov     qword ptr [rsp+120h+ReturnSingleEntry], rax; int
0x18008bff6  mov     rax, [rbp+3Fh+FileHandle]
0x18008bffa  mov     qword ptr [rsp+120h+FileInformationClass], rax; int
0x18008bfff  mov     rax, [rbp+3Fh+var_A0]
0x18008c003  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x18008c008  lea     rax, [rbp+3Fh+SourceString]
0x18008c00c  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x18008c011  mov     eax, [rbp+3Fh+arg_28]
0x18008c014  mov     [rsp+120h+ShareAccess], eax; int
0x18008c018  call    I_ReloadCatalog
0x18008c01d  test    eax, eax
0x18008c01f  js      short loc_18008C03D
0x18008c021  mov     eax, dword ptr [rsp+120h+var_C0]
0x18008c025  mov     rcx, [rbp+3Fh+arg_38]
0x18008c02c  or      [rcx], eax
0x18008c02e  test    eax, eax
0x18008c030  jz      short loc_18008C035
0x18008c032  inc     [rbp+3Fh+arg_10]
0x18008c035  inc     r12d
0x18008c038  jmp     loc_18008BF93
0x18008c03d  cmp     [rbp+3Fh+arg_10], 0
0x18008c041  jnz     short loc_18008C059
0x18008c043  mov     ecx, 1
0x18008c048  lea     r12, [rdi+25800h]
0x18008c04f  mov     bl, cl
0x18008c051  mov     r15, rdi
0x18008c054  jmp     loc_18008BEAB
0x18008c059  cmp     eax, 0C000009Ah
0x18008c05e  jnz     loc_18008C146
0x18008c064  mov     esi, eax
0x18008c066  jmp     short loc_18008C035
0x18008c068  mov     eax, [rbx]
0x18008c06a  lea     r12, [rdi+25800h]
0x18008c071  test    eax, eax
0x18008c073  jnz     loc_18008C134
0x18008c079  mov     ecx, dword ptr [rbp+3Fh+arg_30]
0x18008c07c  xor     bl, bl
0x18008c07e  jmp     loc_18008BEAE
0x18008c083  mov     r9d, [rbp+3Fh+arg_20]; int
0x18008c087  lea     rax, [r15+40h]
0x18008c08b  mov     r8d, [rbp+3Fh+arg_18]; int
0x18008c08f  lea     rdx, [rsp+120h+var_C0]
0x18008c094  mov     [rsp+120h+var_C8], rdx; __int64
0x18008c099  lea     rcx, [r15+18h]
0x18008c09d  mov     [rbp+3Fh+SourceString.Buffer], rax
0x18008c0a1  xor     edx, edx; int
0x18008c0a3  movzx   eax, word ptr [r15+3Ch]
0x18008c0a8  mov     [rbp+3Fh+SourceString.MaximumLength], ax
0x18008c0ac  mov     [rbp+3Fh+SourceString.Length], ax
0x18008c0b0  lea     rax, [r15+20h]
0x18008c0b4  mov     qword ptr [rsp+120h+RestartScan], rax; __int64
0x18008c0b9  mov     rax, [rbp+3Fh+var_A0]
0x18008c0bd  mov     [rsp+120h+FileName], rcx; __int64
0x18008c0c2  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x18008c0c6  mov     qword ptr [rsp+120h+ReturnSingleEntry], 0; int
0x18008c0cf  mov     qword ptr [rsp+120h+FileInformationClass], 0; int
0x18008c0d8  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x18008c0dd  lea     rax, [rbp+3Fh+SourceString]
0x18008c0e1  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x18008c0e6  mov     eax, [rbp+3Fh+arg_28]
0x18008c0e9  mov     [rsp+120h+ShareAccess], eax; int
0x18008c0ed  call    I_ReloadCatalog
0x18008c0f2  test    eax, eax
0x18008c0f4  js      short loc_18008C154
0x18008c0f6  mov     eax, dword ptr [rsp+120h+var_C0]
0x18008c0fa  mov     r14, [rbp+3Fh+arg_38]
0x18008c101  or      [r14], eax
0x18008c104  test    eax, eax
0x18008c106  jz      loc_18008C079
0x18008c10c  inc     [rbp+3Fh+arg_10]
0x18008c10f  jmp     loc_18008C079
0x18008c114  test    bl, bl
0x18008c116  jnz     short loc_18008C16B
0x18008c118  test    esi, esi
0x18008c11a  js      short loc_18008C128
0x18008c11c  cmp     eax, r13d
0x18008c11f  jz      short loc_18008C17D
0x18008c121  cmp     eax, 0C000009Ah
0x18008c126  jz      short loc_18008C17D
0x18008c128  lock dec cs:g_ReloadInProgressCount
0x18008c12f  jmp     loc_18008BE16
0x18008c134  add     rbx, rax
0x18008c137  jmp     loc_18008BF0B
0x18008c13c  mov     esi, 0C0000017h
0x18008c141  jmp     loc_18008BE16
0x18008c146  cmp     eax, r13d
0x18008c149  jz      loc_18008C064
0x18008c14f  jmp     loc_18008C035
0x18008c154  cmp     eax, r13d
0x18008c157  jz      short loc_18008C164
0x18008c159  cmp     eax, 0C000009Ah
0x18008c15e  jnz     loc_18008C079
0x18008c164  mov     esi, eax
0x18008c166  jmp     loc_18008C079
0x18008c16b  test    r15, r15
0x18008c16e  jnz     short loc_18008C118
0x18008c170  mov     r15, rdi
0x18008c173  mov     ecx, 1
0x18008c178  jmp     loc_18008BEAB
0x18008c17d  mov     esi, eax
0x18008c17f  jmp     short loc_18008C128
0x18008c181  mov     edx, 72634943h; Tag
0x18008c186  mov     rcx, rdi; P
0x18008c189  call    cs:__imp_ExFreePoolWithTag
0x18008c190  nop     dword ptr [rax+rax+00h]
0x18008c195  jmp     loc_18008BE34
```
