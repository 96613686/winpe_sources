# RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(eFveVolumeType,_GUID const *,_GUID const *,ushort *,unsigned __int64)

- ea: `0x180016ac8`
- end: `0x180016c6d`
- name: `?GetRegistrySubKeyForProtector@RegistryBasedBackupStatusCache@@AEBAJW4eFveVolumeType@@PEBU_GUID@@1PEAG_K@Z`
- size: `421`
- prototype: `__int64 __fastcall(__int64, int, const GUID *, const GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180016730`
- `0x180022ff0`

## callees

- `0x180002774`
- `0x1800037a0`
- `0x18000b9f8`
- `0x18000ff64`
- `0x180016ac8`
- `0x18002d010`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x180016b0c`
- `ntdll!RtlStringFromGUID` at `0x180016b60`
- `ntdll!RtlStringFromGUID` at `0x180016b0c`
- `ntdll!RtlStringFromGUID` at `0x180016b60`
- `ntdll!RtlFreeUnicodeString` at `0x180016c4e`
- `ntdll!RtlFreeUnicodeString` at `0x180016c59`
- `ntdll!RtlFreeUnicodeString` at `0x180016c4e`
- `ntdll!RtlFreeUnicodeString` at `0x180016c59`

## pseudocode

```c
__int64 __fastcall RegistryBasedBackupStatusCache::GetRegistrySubKeyForProtector(
        __int64 a1,
        int a2,
        const GUID *a3,
        const GUID *a4,
        unsigned __int16 *a5)
{
  NTSTATUS v9; // eax
  unsigned int v10; // eax
  int v11; // ebx
  NTSTATUS v12; // eax
  unsigned int v13; // eax
  int v14; // edi
  const wchar_t *v15; // rbx
  __int64 v16; // rax
  unsigned int v17; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+50h] [rbp-38h] BYREF

  UnicodeString = 0;
  GuidString = 0;
  memset_0(a5, 0, 0x208u);
  v9 = RtlStringFromGUID(a3, &GuidString);
  v10 = FromNtStatus(v9);
  v11 = v10;
  if ( !v10 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v10);
  if ( v11 >= 0 )
  {
LABEL_6:
    v12 = RtlStringFromGUID(a4, &UnicodeString);
    v13 = FromNtStatus(v12);
    v11 = v13;
    if ( !v13 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v13);
    if ( v11 >= 0 )
    {
LABEL_11:
      if ( a2 )
      {
        v14 = a2 - 1;
        if ( v14 )
        {
          if ( v14 == 1 )
            v15 = L"RDV";
          else
            v15 = &qword_1800318B0;
        }
        else
        {
          v15 = L"FDV";
        }
      }
      else
      {
        v15 = L"OSV";
      }
      v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
      v17 = StringCchPrintfW(a5, 0x104u, L"%s\\%s\\%wZ\\%wZ", v16, v15, &GuidString, &UnicodeString);
      v11 = v17;
      if ( v17 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v17);
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&GuidString);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180016ac8  push    rbx
0x180016aca  push    rsi
0x180016acb  push    rdi
0x180016acc  push    r14
0x180016ace  push    r15
0x180016ad0  sub     rsp, 60h
0x180016ad4  mov     rbx, r8
0x180016ad7  mov     edi, edx
0x180016ad9  mov     r14, rcx
0x180016adc  xorps   xmm0, xmm0
0x180016adf  mov     rcx, [rsp+88h+arg_20]; void *
0x180016ae7  xorps   xmm1, xmm1
0x180016aea  xor     edx, edx; Val
0x180016aec  mov     r8d, 208h; Size
0x180016af2  movups  xmmword ptr [rsp+88h+UnicodeString.Length], xmm0
0x180016af7  mov     rsi, r9
0x180016afa  movups  xmmword ptr [rsp+88h+GuidString.Length], xmm1
0x180016aff  call    memset_0
0x180016b04  lea     rdx, [rsp+88h+GuidString]; GuidString
0x180016b09  mov     rcx, rbx; Guid
0x180016b0c  call    cs:__imp_RtlStringFromGUID
0x180016b12  mov     ecx, eax; int
0x180016b14  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180016b19  lea     r15, WPP_GLOBAL_Control
0x180016b20  mov     ebx, eax
0x180016b22  test    eax, eax
0x180016b24  jz      short loc_180016B58
0x180016b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b2d  cmp     rcx, r15
0x180016b30  jz      short loc_180016B50
0x180016b32  test    byte ptr [rcx+1Ch], 40h
0x180016b36  jz      short loc_180016B50
0x180016b38  mov     rcx, [rcx+10h]
0x180016b3c  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016b43  mov     edx, 83h
0x180016b48  mov     r9d, eax
0x180016b4b  call    WPP_SF_d
0x180016b50  test    ebx, ebx
0x180016b52  js      loc_180016C49
0x180016b58  lea     rdx, [rsp+88h+UnicodeString]; GuidString
0x180016b5d  mov     rcx, rsi; Guid
0x180016b60  call    cs:__imp_RtlStringFromGUID
0x180016b66  mov     ecx, eax; int
0x180016b68  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180016b6d  mov     ebx, eax
0x180016b6f  test    eax, eax
0x180016b71  jz      short loc_180016BA5
0x180016b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b7a  cmp     rcx, r15
0x180016b7d  jz      short loc_180016B9D
0x180016b7f  test    byte ptr [rcx+1Ch], 40h
0x180016b83  jz      short loc_180016B9D
0x180016b85  mov     rcx, [rcx+10h]
0x180016b89  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016b90  mov     edx, 84h
0x180016b95  mov     r9d, eax
0x180016b98  call    WPP_SF_d
0x180016b9d  test    ebx, ebx
0x180016b9f  js      loc_180016C49
0x180016ba5  test    edi, edi
0x180016ba7  jz      short loc_180016BCE
0x180016ba9  sub     edi, 1
0x180016bac  jz      short loc_180016BC5
0x180016bae  cmp     edi, 1
0x180016bb1  jz      short loc_180016BBC
0x180016bb3  lea     rbx, qword_1800318B0
0x180016bba  jmp     short loc_180016BD5
0x180016bbc  lea     rbx, aRdv; "RDV"
0x180016bc3  jmp     short loc_180016BD5
0x180016bc5  lea     rbx, aFdv; "FDV"
0x180016bcc  jmp     short loc_180016BD5
0x180016bce  lea     rbx, aOsv; "OSV"
0x180016bd5  mov     rax, [r14]
0x180016bd8  mov     rcx, r14
0x180016bdb  mov     rax, [rax+20h]
0x180016bdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016be4  lea     rcx, [rsp+88h+UnicodeString]
0x180016be9  mov     r9, rax
0x180016bec  mov     [rsp+88h+var_58], rcx
0x180016bf1  lea     r8, aSSWzWz; "%s\\%s\\%wZ\\%wZ"
0x180016bf8  lea     rcx, [rsp+88h+GuidString]
0x180016bfd  mov     edx, 104h; unsigned __int64
0x180016c02  mov     [rsp+88h+var_60], rcx
0x180016c07  mov     rcx, [rsp+88h+arg_20]; unsigned __int16 *
0x180016c0f  mov     [rsp+88h+var_68], rbx
0x180016c14  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180016c19  mov     ebx, eax
0x180016c1b  test    eax, eax
0x180016c1d  jz      short loc_180016C49
0x180016c1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c26  cmp     rcx, r15
0x180016c29  jz      short loc_180016C49
0x180016c2b  test    byte ptr [rcx+1Ch], 40h
0x180016c2f  jz      short loc_180016C49
0x180016c31  mov     rcx, [rcx+10h]
0x180016c35  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180016c3c  mov     edx, 85h
0x180016c41  mov     r9d, eax
0x180016c44  call    WPP_SF_d
0x180016c49  lea     rcx, [rsp+88h+UnicodeString]; UnicodeString
0x180016c4e  call    cs:__imp_RtlFreeUnicodeString
0x180016c54  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x180016c59  call    cs:__imp_RtlFreeUnicodeString
0x180016c5f  mov     eax, ebx
0x180016c61  add     rsp, 60h
0x180016c65  pop     r15
0x180016c67  pop     r14
0x180016c69  pop     rdi
0x180016c6a  pop     rsi
0x180016c6b  pop     rbx
0x180016c6c  retn
```
