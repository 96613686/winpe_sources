# ndisReadBindPaths(_NDIS_MINIPORT_BLOCK *,_RTL_QUERY_REGISTRY_TABLE *,void *)

- ea: `0x140099930`
- end: `0x140099d17`
- name: `?ndisReadBindPaths@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_RTL_QUERY_REGISTRY_TABLE@@PEAX@Z`
- size: `999`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _RTL_QUERY_REGISTRY_TABLE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1401434f0`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140060970`
- `0x140088a2c`
- `0x140099930`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140099bd5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140099bd5`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140099a06`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140099a06`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140099bec`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140099bec`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099a72`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099b55`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099a72`
- `ntoskrnl!RtlInitUnicodeString` at `0x140099b55`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099ac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099cc1`
- `ntoskrnl!ExAllocatePool2` at `0x140099ade`
- `ntoskrnl!ExAllocatePool2` at `0x140099ade`

## string_xrefs

- `0x14009999e`: `Linkage`

## pseudocode

```c
__int64 __fastcall ndisReadBindPaths(struct _NDIS_MINIPORT_BLOCK *a1, struct _RTL_QUERY_REGISTRY_TABLE *a2, void *a3)
{
  struct _RTL_QUERY_REGISTRY_TABLE *v4; // rbx
  struct _NDIS_MINIPORT_BLOCK *v5; // rsi
  char v6; // r14
  int v7; // edx
  int v8; // edi
  const WCHAR *v9; // r15
  unsigned int v10; // r12d
  unsigned int v11; // ebx
  unsigned int v12; // r13d
  _NDIS_BIND_PATHS *BindPaths; // rcx
  _NDIS_BIND_PATHS *Pool2; // rax
  const WCHAR *v15; // r15
  char *v16; // r12
  char *v17; // rbx
  int v18; // eax
  UNICODE_STRING v20; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  PCWSTR SourceString; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+58h] BYREF

  SourceString = 0;
  v4 = a2;
  v24 = 0;
  v5 = a1;
  v6 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      13,
      12,
      (struct _GUID *)&WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids,
      (char)a1);
  }
  v24 = 0;
  v4->Name = L"Linkage";
  v4->QueryRoutine = 0;
  v4[1].QueryRoutine = (int (__fastcall *)(wchar_t *, unsigned int, void *, unsigned int, void *, void *))ndisReadParameter;
  v4->Flags = 1;
  v4[1].Name = L"RootDevice";
  v4[1].Flags = 20;
  v4[1].EntryContext = &SourceString;
  v4[1].DefaultType = 0;
  v4[2].QueryRoutine = 0;
  v4[2].Flags = 0;
  v4[2].Name = 0;
  v8 = RtlQueryRegistryValuesEx(0x40000000, a3, v4, &v24, 0);
  if ( v8 == -1073741772 )
  {
    v8 = 0;
  }
  else if ( v8 < 0 || (_DWORD)v24 != 7 )
  {
    if ( SourceString )
      v6 = 1;
    if ( v8 >= 0 )
      v8 = -1073741823;
    goto LABEL_34;
  }
  if ( SourceString )
    v6 = 1;
  else
    SourceString = v5->BaseName.Buffer;
  v9 = SourceString;
  v10 = 24;
  v11 = 0;
  if ( !*SourceString )
    goto LABEL_29;
  do
  {
    v12 = v11;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v9);
    ++v11;
    v10 += DestinationString.Length + ndisDeviceStr.Length + 18;
    v9 += ((unsigned __int64)DestinationString.Length + 2) >> 1;
  }
  while ( *v9 );
  LOBYTE(v5) = (_BYTE)a1;
  if ( v11 )
  {
    BindPaths = a1->BindPaths;
    if ( BindPaths )
      ExFreePoolWithTag(BindPaths, 0);
    Pool2 = (_NDIS_BIND_PATHS *)ExAllocatePool2(64, v10, 1851868238);
    a1->BindPaths = Pool2;
    if ( Pool2 )
    {
      Pool2->Number = v11;
      if ( v11 > 1 )
      {
        a1->PnPFlags |= 0x8000000u;
        a1->InfoFlags |= 0x10000000u;
      }
      v15 = SourceString;
      v16 = (char *)&a1->BindPaths[1] + 16 * v11;
      while ( *v15 )
      {
        v20 = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&v20, v15);
        if ( v20.Length > 0x1000u )
        {
          v8 = -1073741670;
          break;
        }
        v17 = (char *)a1->BindPaths + 16 * v12;
        v15 += ((unsigned __int64)v20.Length + 2) >> 1;
        *((_WORD *)v17 + 4) = 0;
        *((_QWORD *)v17 + 2) = v16;
        *((_WORD *)v17 + 5) = ndisDeviceStr.Length + v20.Length + 2;
        DestinationString.Length = 0;
        DestinationString.Buffer = (wchar_t *)&v16[ndisDeviceStr.Length];
        DestinationString.MaximumLength = v20.Length + 2;
        RtlCopyUnicodeString((PUNICODE_STRING)(v17 + 8), &ndisDeviceStr);
        RtlUpcaseUnicodeString(&DestinationString, &v20, 0);
        --v12;
        *((_WORD *)v17 + 4) += DestinationString.Length;
        v16 += 2 * ((unsigned __int64)*((unsigned __int16 *)v17 + 5) >> 1);
      }
      if ( MINIPORT_TEST_FLAG(a1, 0x80u) )
      {
        v18 = RtlUnicodeStringCopy(a1->BindPaths->Paths, &a1->MiniportName);
        v8 = v18;
        if ( v18 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v7) = 2;
            WPP_RECORDER_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v7,
              13,
              13,
              (struct _GUID *)&WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids,
              (char)a1,
              v18);
          }
        }
      }
    }
    else
    {
      v8 = -1073741670;
    }
  }
  else
  {
LABEL_29:
    v8 = -1073741811;
  }
LABEL_34:
  if ( v6 )
    ExFreePoolWithTag((PVOID)SourceString, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v7,
      13,
      14,
      (struct _GUID *)&WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids,
      (char)v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140099930  mov     r11, rsp
0x140099933  mov     [r11+18h], rbx
0x140099937  mov     [r11+8], rcx
0x14009993b  push    rbp
0x14009993c  push    rsi
0x14009993d  push    rdi
0x14009993e  push    r12
0x140099940  push    r13
0x140099942  push    r14
0x140099944  push    r15
0x140099946  mov     rbp, rsp
0x140099949  sub     rsp, 60h
0x14009994d  xor     r13d, r13d
0x140099950  mov     rdi, r8
0x140099953  mov     [rbp+SourceString], r13
0x140099957  mov     rbx, rdx
0x14009995a  mov     [rbp+arg_18], r13
0x14009995e  mov     rsi, rcx
0x140099961  movzx   r14d, r13b
0x140099965  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009996c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140099973  lea     rax, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x14009997a  jz      short loc_14009999E
0x14009997c  mov     [r11-70h], rcx
0x140099980  lea     r9d, [r13+0Ch]; int
0x140099984  mov     rcx, cs:WPP_GLOBAL_Control
0x14009998b  lea     r8d, [r13+0Dh]; int
0x14009998f  mov     dl, 4; int
0x140099991  mov     [r11-78h], rax
0x140099995  mov     rcx, [rcx+40h]; int
0x140099999  call    WPP_RECORDER_SF_q
0x14009999e  lea     rax, aLinkage; "Linkage"
0x1400999a5  mov     [rbp+arg_18], r13
0x1400999a9  mov     [rbx+10h], rax
0x1400999ad  lea     r9, [rbp+arg_18]
0x1400999b1  lea     rax, ?ndisReadParameter@@YAJPEA_WKPEAXK11@Z; ndisReadParameter(wchar_t *,ulong,void *,ulong,void *,void *)
0x1400999b8  mov     [rbx], r13
0x1400999bb  mov     [rbx+38h], rax
0x1400999bf  mov     r15d, 1
0x1400999c5  lea     rax, aRootdevice; "RootDevice"
0x1400999cc  mov     [rbx+8], r15d
0x1400999d0  mov     [rbx+48h], rax
0x1400999d4  mov     r8, rbx
0x1400999d7  lea     rax, [rbp+SourceString]
0x1400999db  mov     dword ptr [rbx+40h], 14h
0x1400999e2  mov     rdx, rdi
0x1400999e5  mov     [rbx+50h], rax
0x1400999e9  mov     ecx, 40000000h
0x1400999ee  mov     [rbx+58h], r13d
0x1400999f2  mov     [rbx+70h], r13
0x1400999f6  mov     [rbx+78h], r13d
0x1400999fa  mov     [rbx+80h], r13
0x140099a01  mov     [rsp+60h+var_40], r13
0x140099a06  call    cs:__imp_RtlQueryRegistryValuesEx
0x140099a0d  nop     dword ptr [rax+rax+00h]
0x140099a12  mov     edi, eax
0x140099a14  cmp     eax, 0C0000034h
0x140099a19  jnz     short loc_140099A20
0x140099a1b  mov     edi, r13d
0x140099a1e  jmp     short loc_140099A32
0x140099a20  test    edi, edi
0x140099a22  js      loc_140099C9D
0x140099a28  cmp     dword ptr [rbp+arg_18], 7
0x140099a2c  jnz     loc_140099C9D
0x140099a32  cmp     [rbp+SourceString], r13
0x140099a36  jnz     short loc_140099A45
0x140099a38  mov     rax, [rsi+0ED8h]
0x140099a3f  mov     [rbp+SourceString], rax
0x140099a43  jmp     short loc_140099A48
0x140099a45  mov     r14b, r15b
0x140099a48  mov     r15, [rbp+SourceString]
0x140099a4c  mov     r12d, 18h
0x140099a52  mov     ebx, r13d
0x140099a55  cmp     [r15], r13w
0x140099a59  jz      loc_140099C93
0x140099a5f  xor     esi, esi
0x140099a61  xorps   xmm0, xmm0
0x140099a64  lea     rcx, [rbp+DestinationString]; DestinationString
0x140099a68  mov     rdx, r15; SourceString
0x140099a6b  mov     r13d, ebx
0x140099a6e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140099a72  call    cs:__imp_RtlInitUnicodeString
0x140099a79  nop     dword ptr [rax+rax+00h]
0x140099a7e  movzx   eax, [rbp+DestinationString.Length]
0x140099a82  inc     ebx
0x140099a84  movzx   ecx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140099a8b  add     eax, r12d
0x140099a8e  lea     r12d, [rcx+12h]
0x140099a92  add     r12d, eax
0x140099a95  movzx   eax, [rbp+DestinationString.Length]
0x140099a99  add     rax, 2
0x140099a9d  shr     rax, 1
0x140099aa0  lea     r15, [r15+rax*2]
0x140099aa4  cmp     [r15], si
0x140099aa8  jnz     short loc_140099A61
0x140099aaa  mov     rsi, [rbp+arg_0]
0x140099aae  test    ebx, ebx
0x140099ab0  jz      loc_140099C93
0x140099ab6  mov     rcx, [rsi+0EB8h]; P
0x140099abd  test    rcx, rcx
0x140099ac0  jz      short loc_140099AD0
0x140099ac2  xor     edx, edx; Tag
0x140099ac4  call    cs:__imp_ExFreePoolWithTag
0x140099acb  nop     dword ptr [rax+rax+00h]
0x140099ad0  mov     edx, r12d
0x140099ad3  mov     ecx, 40h ; '@'
0x140099ad8  mov     r8d, 6E61444Eh
0x140099ade  call    cs:__imp_ExAllocatePool2
0x140099ae5  nop     dword ptr [rax+rax+00h]
0x140099aea  xor     r8d, r8d
0x140099aed  mov     [rsi+0EB8h], rax
0x140099af4  test    rax, rax
0x140099af7  jnz     short loc_140099B0A
0x140099af9  mov     edi, 0C000009Ah
0x140099afe  lea     r12, WPP_RECORDER_INITIALIZED
0x140099b05  jmp     loc_140099CAF
0x140099b0a  mov     [rax], ebx
0x140099b0c  cmp     ebx, 1
0x140099b0f  jbe     short loc_140099B1E
0x140099b11  bts     dword ptr [rsi+7Ch], 1Bh
0x140099b16  bts     dword ptr [rsi+750h], 1Ch
0x140099b1e  mov     r12, [rsi+0EB8h]
0x140099b25  mov     r15, [rbp+SourceString]
0x140099b29  add     r12, 18h
0x140099b2d  mov     ecx, ebx
0x140099b2f  shl     rcx, 4
0x140099b33  add     r12, rcx
0x140099b36  cmp     [r15], r8w
0x140099b3a  jz      loc_140099C1B
0x140099b40  xorps   xmm0, xmm0
0x140099b43  lea     rcx, [rbp+var_20]; DestinationString
0x140099b47  xorps   xmm1, xmm1
0x140099b4a  mov     rdx, r15; SourceString
0x140099b4d  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140099b51  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140099b55  call    cs:__imp_RtlInitUnicodeString
0x140099b5c  nop     dword ptr [rax+rax+00h]
0x140099b61  mov     eax, 1000h
0x140099b66  cmp     [rbp+var_20.Length], ax
0x140099b6a  ja      loc_140099C16
0x140099b70  movzx   eax, [rbp+var_20.Length]
0x140099b74  mov     edx, 2
0x140099b79  add     rax, rdx
0x140099b7c  mov     ebx, r13d
0x140099b7f  shr     rax, 1
0x140099b82  xor     ecx, ecx
0x140099b84  shl     rbx, 4
0x140099b88  add     rbx, [rsi+0EB8h]
0x140099b8f  lea     r15, [r15+rax*2]
0x140099b93  mov     [rbx+8], cx
0x140099b97  mov     [rbx+10h], r12
0x140099b9b  movzx   eax, [rbp+var_20.Length]
0x140099b9f  add     ax, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140099ba6  add     ax, dx
0x140099ba9  mov     [rbx+0Ah], ax
0x140099bad  movzx   eax, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140099bb4  add     rax, r12
0x140099bb7  mov     [rbp+DestinationString.Length], cx
0x140099bbb  mov     [rbp+DestinationString.Buffer], rax
0x140099bbf  lea     rcx, [rbx+8]; DestinationString
0x140099bc3  movzx   eax, [rbp+var_20.Length]
0x140099bc7  add     ax, dx
0x140099bca  lea     rdx, ?ndisDeviceStr@@3U_UNICODE_STRING@@A; SourceString
0x140099bd1  mov     [rbp+DestinationString.MaximumLength], ax
0x140099bd5  call    cs:__imp_RtlCopyUnicodeString
0x140099bdc  nop     dword ptr [rax+rax+00h]
0x140099be1  xor     r8d, r8d; AllocateDestinationString
0x140099be4  lea     rdx, [rbp+var_20]; SourceString
0x140099be8  lea     rcx, [rbp+DestinationString]; DestinationString
0x140099bec  call    cs:__imp_RtlUpcaseUnicodeString
0x140099bf3  nop     dword ptr [rax+rax+00h]
0x140099bf8  movzx   eax, [rbp+DestinationString.Length]
0x140099bfc  dec     r13d
0x140099bff  add     [rbx+8], ax
0x140099c03  movzx   eax, word ptr [rbx+0Ah]
0x140099c07  shr     rax, 1
0x140099c0a  xor     r8d, r8d
0x140099c0d  lea     r12, [r12+rax*2]
0x140099c11  jmp     loc_140099B36
0x140099c16  mov     edi, 0C000009Ah
0x140099c1b  mov     edx, 80h; unsigned int
0x140099c20  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x140099c23  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x140099c28  test    al, al
0x140099c2a  jz      loc_140099AFE
0x140099c30  mov     rcx, [rsi+0EB8h]
0x140099c37  lea     rdx, [rsi+0EE0h]; struct _UNICODE_STRING *
0x140099c3e  add     rcx, 8; struct _UNICODE_STRING *
0x140099c42  call    ?RtlUnicodeStringCopy@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCopy(_UNICODE_STRING *,_UNICODE_STRING const *)
0x140099c47  mov     edi, eax
0x140099c49  test    eax, eax
0x140099c4b  jz      loc_140099AFE
0x140099c51  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140099c58  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140099c5f  jz      short loc_140099CAF
0x140099c61  mov     rcx, cs:WPP_GLOBAL_Control
0x140099c68  lea     rbx, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x140099c6f  mov     dword ptr [rsp+60h+var_30], eax; char
0x140099c73  mov     r9d, 0Dh; int
0x140099c79  mov     qword ptr [rsp+60h+var_38], rsi; char
0x140099c7e  mov     r8d, r9d; int
0x140099c81  mov     dl, 2; int
0x140099c83  mov     [rsp+60h+var_40], rbx; struct _GUID *
0x140099c88  mov     rcx, [rcx+40h]; int
0x140099c8c  call    WPP_RECORDER_SF_qD
0x140099c91  jmp     short loc_140099CB6
0x140099c93  mov     edi, 0C000000Dh
0x140099c98  jmp     loc_140099AFE
0x140099c9d  cmp     [rbp+SourceString], r13
0x140099ca1  mov     eax, 0C0000001h
0x140099ca6  cmovnz  r14d, r15d
0x140099caa  test    edi, edi
0x140099cac  cmovns  edi, eax
0x140099caf  lea     rbx, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x140099cb6  test    r14b, r14b
0x140099cb9  jz      short loc_140099CCD
0x140099cbb  mov     rcx, [rbp+SourceString]; P
0x140099cbf  xor     edx, edx; Tag
0x140099cc1  call    cs:__imp_ExFreePoolWithTag
0x140099cc8  nop     dword ptr [rax+rax+00h]
0x140099ccd  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140099cd4  jz      short loc_140099CFC
0x140099cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140099cdd  mov     r9d, 0Eh; int
0x140099ce3  mov     qword ptr [rsp+60h+var_38], rsi; char
0x140099ce8  mov     dl, 4; int
0x140099cea  mov     [rsp+60h+var_40], rbx; struct _GUID *
0x140099cef  mov     rcx, [rcx+40h]; int
0x140099cf3  lea     r8d, [r9-1]; int
0x140099cf7  call    WPP_RECORDER_SF_q
0x140099cfc  mov     rbx, [rsp+60h+arg_10]
0x140099d04  mov     eax, edi
0x140099d06  add     rsp, 60h
0x140099d0a  pop     r15
0x140099d0c  pop     r14
0x140099d0e  pop     r13
0x140099d10  pop     r12
0x140099d12  pop     rdi
0x140099d13  pop     rsi
0x140099d14  pop     rbp
0x140099d15  retn
```
