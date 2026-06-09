# ndisReadBindPaths(_NDIS_MINIPORT_BLOCK *,_RTL_QUERY_REGISTRY_TABLE *,void *)

- ea: `0x1400946b0`
- end: `0x140094a97`
- name: `?ndisReadBindPaths@@YAJPEAU_NDIS_MINIPORT_BLOCK@@PEAU_RTL_QUERY_REGISTRY_TABLE@@PEAX@Z`
- size: `999`
- prototype: `__int64 __fastcall(struct _NDIS_MINIPORT_BLOCK *, struct _RTL_QUERY_REGISTRY_TABLE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14013c550`

## callees

- `0x14001cf50`
- `0x14001d030`
- `0x14005c380`
- `0x1400837ac`
- `0x1400946b0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140094955`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140094955`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140094786`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140094786`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14009496c`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14009496c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400947f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400948d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400947f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400948d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094844`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094a41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094844`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094a41`
- `ntoskrnl!ExAllocatePool2` at `0x14009485e`
- `ntoskrnl!ExAllocatePool2` at `0x14009485e`

## string_xrefs

- `0x14009471e`: `Linkage`

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
0x1400946b0  mov     r11, rsp
0x1400946b3  mov     [r11+18h], rbx
0x1400946b7  mov     [r11+8], rcx
0x1400946bb  push    rbp
0x1400946bc  push    rsi
0x1400946bd  push    rdi
0x1400946be  push    r12
0x1400946c0  push    r13
0x1400946c2  push    r14
0x1400946c4  push    r15
0x1400946c6  mov     rbp, rsp
0x1400946c9  sub     rsp, 60h
0x1400946cd  xor     r13d, r13d
0x1400946d0  mov     rdi, r8
0x1400946d3  mov     [rbp+SourceString], r13
0x1400946d7  mov     rbx, rdx
0x1400946da  mov     [rbp+arg_18], r13
0x1400946de  mov     rsi, rcx
0x1400946e1  movzx   r14d, r13b
0x1400946e5  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400946ec  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400946f3  lea     rax, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x1400946fa  jz      short loc_14009471E
0x1400946fc  mov     [r11-70h], rcx
0x140094700  lea     r9d, [r13+0Ch]; int
0x140094704  mov     rcx, cs:WPP_GLOBAL_Control
0x14009470b  lea     r8d, [r13+0Dh]; int
0x14009470f  mov     dl, 4; int
0x140094711  mov     [r11-78h], rax
0x140094715  mov     rcx, [rcx+40h]; int
0x140094719  call    WPP_RECORDER_SF_q
0x14009471e  lea     rax, aLinkage; "Linkage"
0x140094725  mov     [rbp+arg_18], r13
0x140094729  mov     [rbx+10h], rax
0x14009472d  lea     r9, [rbp+arg_18]
0x140094731  lea     rax, ?ndisReadParameter@@YAJPEA_WKPEAXK11@Z; ndisReadParameter(wchar_t *,ulong,void *,ulong,void *,void *)
0x140094738  mov     [rbx], r13
0x14009473b  mov     [rbx+38h], rax
0x14009473f  mov     r15d, 1
0x140094745  lea     rax, aRootdevice; "RootDevice"
0x14009474c  mov     [rbx+8], r15d
0x140094750  mov     [rbx+48h], rax
0x140094754  mov     r8, rbx
0x140094757  lea     rax, [rbp+SourceString]
0x14009475b  mov     dword ptr [rbx+40h], 14h
0x140094762  mov     rdx, rdi
0x140094765  mov     [rbx+50h], rax
0x140094769  mov     ecx, 40000000h
0x14009476e  mov     [rbx+58h], r13d
0x140094772  mov     [rbx+70h], r13
0x140094776  mov     [rbx+78h], r13d
0x14009477a  mov     [rbx+80h], r13
0x140094781  mov     [rsp+60h+var_40], r13
0x140094786  call    cs:__imp_RtlQueryRegistryValuesEx
0x14009478d  nop     dword ptr [rax+rax+00h]
0x140094792  mov     edi, eax
0x140094794  cmp     eax, 0C0000034h
0x140094799  jnz     short loc_1400947A0
0x14009479b  mov     edi, r13d
0x14009479e  jmp     short loc_1400947B2
0x1400947a0  test    edi, edi
0x1400947a2  js      loc_140094A1D
0x1400947a8  cmp     dword ptr [rbp+arg_18], 7
0x1400947ac  jnz     loc_140094A1D
0x1400947b2  cmp     [rbp+SourceString], r13
0x1400947b6  jnz     short loc_1400947C5
0x1400947b8  mov     rax, [rsi+0ED8h]
0x1400947bf  mov     [rbp+SourceString], rax
0x1400947c3  jmp     short loc_1400947C8
0x1400947c5  mov     r14b, r15b
0x1400947c8  mov     r15, [rbp+SourceString]
0x1400947cc  mov     r12d, 18h
0x1400947d2  mov     ebx, r13d
0x1400947d5  cmp     [r15], r13w
0x1400947d9  jz      loc_140094A13
0x1400947df  xor     esi, esi
0x1400947e1  xorps   xmm0, xmm0
0x1400947e4  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400947e8  mov     rdx, r15; SourceString
0x1400947eb  mov     r13d, ebx
0x1400947ee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400947f2  call    cs:__imp_RtlInitUnicodeString
0x1400947f9  nop     dword ptr [rax+rax+00h]
0x1400947fe  movzx   eax, [rbp+DestinationString.Length]
0x140094802  inc     ebx
0x140094804  movzx   ecx, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x14009480b  add     eax, r12d
0x14009480e  lea     r12d, [rcx+12h]
0x140094812  add     r12d, eax
0x140094815  movzx   eax, [rbp+DestinationString.Length]
0x140094819  add     rax, 2
0x14009481d  shr     rax, 1
0x140094820  lea     r15, [r15+rax*2]
0x140094824  cmp     [r15], si
0x140094828  jnz     short loc_1400947E1
0x14009482a  mov     rsi, [rbp+arg_0]
0x14009482e  test    ebx, ebx
0x140094830  jz      loc_140094A13
0x140094836  mov     rcx, [rsi+0EB8h]; P
0x14009483d  test    rcx, rcx
0x140094840  jz      short loc_140094850
0x140094842  xor     edx, edx; Tag
0x140094844  call    cs:__imp_ExFreePoolWithTag
0x14009484b  nop     dword ptr [rax+rax+00h]
0x140094850  mov     edx, r12d
0x140094853  mov     ecx, 40h ; '@'
0x140094858  mov     r8d, 6E61444Eh
0x14009485e  call    cs:__imp_ExAllocatePool2
0x140094865  nop     dword ptr [rax+rax+00h]
0x14009486a  xor     r8d, r8d
0x14009486d  mov     [rsi+0EB8h], rax
0x140094874  test    rax, rax
0x140094877  jnz     short loc_14009488A
0x140094879  mov     edi, 0C000009Ah
0x14009487e  lea     r12, WPP_RECORDER_INITIALIZED
0x140094885  jmp     loc_140094A2F
0x14009488a  mov     [rax], ebx
0x14009488c  cmp     ebx, 1
0x14009488f  jbe     short loc_14009489E
0x140094891  bts     dword ptr [rsi+7Ch], 1Bh
0x140094896  bts     dword ptr [rsi+750h], 1Ch
0x14009489e  mov     r12, [rsi+0EB8h]
0x1400948a5  mov     r15, [rbp+SourceString]
0x1400948a9  add     r12, 18h
0x1400948ad  mov     ecx, ebx
0x1400948af  shl     rcx, 4
0x1400948b3  add     r12, rcx
0x1400948b6  cmp     [r15], r8w
0x1400948ba  jz      loc_14009499B
0x1400948c0  xorps   xmm0, xmm0
0x1400948c3  lea     rcx, [rbp+var_20]; DestinationString
0x1400948c7  xorps   xmm1, xmm1
0x1400948ca  mov     rdx, r15; SourceString
0x1400948cd  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x1400948d1  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400948d5  call    cs:__imp_RtlInitUnicodeString
0x1400948dc  nop     dword ptr [rax+rax+00h]
0x1400948e1  mov     eax, 1000h
0x1400948e6  cmp     [rbp+var_20.Length], ax
0x1400948ea  ja      loc_140094996
0x1400948f0  movzx   eax, [rbp+var_20.Length]
0x1400948f4  mov     edx, 2
0x1400948f9  add     rax, rdx
0x1400948fc  mov     ebx, r13d
0x1400948ff  shr     rax, 1
0x140094902  xor     ecx, ecx
0x140094904  shl     rbx, 4
0x140094908  add     rbx, [rsi+0EB8h]
0x14009490f  lea     r15, [r15+rax*2]
0x140094913  mov     [rbx+8], cx
0x140094917  mov     [rbx+10h], r12
0x14009491b  movzx   eax, [rbp+var_20.Length]
0x14009491f  add     ax, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140094926  add     ax, dx
0x140094929  mov     [rbx+0Ah], ax
0x14009492d  movzx   eax, cs:?ndisDeviceStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisDeviceStr ...
0x140094934  add     rax, r12
0x140094937  mov     [rbp+DestinationString.Length], cx
0x14009493b  mov     [rbp+DestinationString.Buffer], rax
0x14009493f  lea     rcx, [rbx+8]; DestinationString
0x140094943  movzx   eax, [rbp+var_20.Length]
0x140094947  add     ax, dx
0x14009494a  lea     rdx, ?ndisDeviceStr@@3U_UNICODE_STRING@@A; SourceString
0x140094951  mov     [rbp+DestinationString.MaximumLength], ax
0x140094955  call    cs:__imp_RtlCopyUnicodeString
0x14009495c  nop     dword ptr [rax+rax+00h]
0x140094961  xor     r8d, r8d; AllocateDestinationString
0x140094964  lea     rdx, [rbp+var_20]; SourceString
0x140094968  lea     rcx, [rbp+DestinationString]; DestinationString
0x14009496c  call    cs:__imp_RtlUpcaseUnicodeString
0x140094973  nop     dword ptr [rax+rax+00h]
0x140094978  movzx   eax, [rbp+DestinationString.Length]
0x14009497c  dec     r13d
0x14009497f  add     [rbx+8], ax
0x140094983  movzx   eax, word ptr [rbx+0Ah]
0x140094987  shr     rax, 1
0x14009498a  xor     r8d, r8d
0x14009498d  lea     r12, [r12+rax*2]
0x140094991  jmp     loc_1400948B6
0x140094996  mov     edi, 0C000009Ah
0x14009499b  mov     edx, 80h; unsigned int
0x1400949a0  mov     rcx, rsi; struct _NDIS_MINIPORT_BLOCK *
0x1400949a3  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400949a8  test    al, al
0x1400949aa  jz      loc_14009487E
0x1400949b0  mov     rcx, [rsi+0EB8h]
0x1400949b7  lea     rdx, [rsi+0EE0h]; struct _UNICODE_STRING *
0x1400949be  add     rcx, 8; struct _UNICODE_STRING *
0x1400949c2  call    ?RtlUnicodeStringCopy@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCopy(_UNICODE_STRING *,_UNICODE_STRING const *)
0x1400949c7  mov     edi, eax
0x1400949c9  test    eax, eax
0x1400949cb  jz      loc_14009487E
0x1400949d1  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400949d8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400949df  jz      short loc_140094A2F
0x1400949e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400949e8  lea     rbx, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x1400949ef  mov     dword ptr [rsp+60h+var_30], eax; char
0x1400949f3  mov     r9d, 0Dh; int
0x1400949f9  mov     qword ptr [rsp+60h+var_38], rsi; char
0x1400949fe  mov     r8d, r9d; int
0x140094a01  mov     dl, 2; int
0x140094a03  mov     [rsp+60h+var_40], rbx; struct _GUID *
0x140094a08  mov     rcx, [rcx+40h]; int
0x140094a0c  call    WPP_RECORDER_SF_qD
0x140094a11  jmp     short loc_140094A36
0x140094a13  mov     edi, 0C000000Dh
0x140094a18  jmp     loc_14009487E
0x140094a1d  cmp     [rbp+SourceString], r13
0x140094a21  mov     eax, 0C0000001h
0x140094a26  cmovnz  r14d, r15d
0x140094a2a  test    edi, edi
0x140094a2c  cmovns  edi, eax
0x140094a2f  lea     rbx, WPP_901e3e1acd0b36a9ab86c452924f7c21_Traceguids
0x140094a36  test    r14b, r14b
0x140094a39  jz      short loc_140094A4D
0x140094a3b  mov     rcx, [rbp+SourceString]; P
0x140094a3f  xor     edx, edx; Tag
0x140094a41  call    cs:__imp_ExFreePoolWithTag
0x140094a48  nop     dword ptr [rax+rax+00h]
0x140094a4d  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140094a54  jz      short loc_140094A7C
0x140094a56  mov     rcx, cs:WPP_GLOBAL_Control
0x140094a5d  mov     r9d, 0Eh; int
0x140094a63  mov     qword ptr [rsp+60h+var_38], rsi; char
0x140094a68  mov     dl, 4; int
0x140094a6a  mov     [rsp+60h+var_40], rbx; struct _GUID *
0x140094a6f  mov     rcx, [rcx+40h]; int
0x140094a73  lea     r8d, [r9-1]; int
0x140094a77  call    WPP_RECORDER_SF_q
0x140094a7c  mov     rbx, [rsp+60h+arg_10]
0x140094a84  mov     eax, edi
0x140094a86  add     rsp, 60h
0x140094a8a  pop     r15
0x140094a8c  pop     r14
0x140094a8e  pop     r13
0x140094a90  pop     r12
0x140094a92  pop     rdi
0x140094a93  pop     rsi
0x140094a94  pop     rbp
0x140094a95  retn
```
