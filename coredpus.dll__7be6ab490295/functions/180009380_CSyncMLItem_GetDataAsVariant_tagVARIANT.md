# CSyncMLItem::GetDataAsVariant(tagVARIANT *)

- ea: `0x180009380`
- end: `0x18000954b`
- name: `?GetDataAsVariant@CSyncMLItem@@QEBAJPEAUtagVARIANT@@@Z`
- size: `459`
- prototype: `int(CSyncMLItem *__hidden this, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e940`
- `0x18001ef60`
- `0x18001f7a0`

## callees

- `0x180002dd0`
- `0x180009380`
- `0x180014330`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000951f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000951f`
- `OLEAUT32!__imp_VariantClear` at `0x180009429`
- `OLEAUT32!__imp_VariantClear` at `0x180009429`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::GetDataAsVariant(CSyncMLItem *this, struct tagVARIANT *a2)
{
  __int64 v3; // rdx
  __int64 v5; // rax
  __int64 v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  const unsigned __int16 *v10; // rcx
  _DWORD v12[2]; // [rsp+30h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-50h] BYREF
  __int16 *v15; // [rsp+58h] [rbp-40h]
  int v16; // [rsp+60h] [rbp-38h]
  int v17; // [rsp+64h] [rbp-34h]
  _DWORD *v18; // [rsp+68h] [rbp-30h]
  __int64 v19; // [rsp+70h] [rbp-28h]

  v3 = *((_QWORD *)this + 2);
  if ( !v3 )
  {
    v5 = *((_QWORD *)this + 1);
    if ( !v5 )
    {
LABEL_5:
      LODWORD(v6) = 1;
      goto LABEL_6;
    }
    while ( 1 )
    {
      v3 = *(_QWORD *)(v5 + 96);
      if ( v3 )
        break;
      v5 = *(_QWORD *)(v5 + 136);
      if ( !v5 )
        goto LABEL_5;
    }
  }
  v8 = 0;
  while ( *((_DWORD *)&CSyncMLMeta::rgSupportedProps + v8) )
  {
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= 0x10 )
    {
      LODWORD(v8) = -1;
      break;
    }
  }
  v9 = *(_DWORD *)(v3 + 128);
  if ( _bittest(&v9, v8) )
    v6 = *(_QWORD *)(v3 + 8LL * (unsigned int)v8);
  else
    LODWORD(v6) = 1;
LABEL_6:
  if ( a2 )
  {
    v7 = 0;
    VariantClear(a2);
    if ( (unsigned int)(v6 - 8) > 2 )
    {
      v10 = (const unsigned __int16 *)*((_QWORD *)this + 10);
      if ( v10 )
        v7 = ConformDataToVariant(v10, v6, a2);
    }
  }
  else
  {
    v7 = -2147467261;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v12[0] = v7;
    v18 = v12;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v19 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v15 = word_180036442;
    UserData.Reserved = 2;
    v16 = 29;
    v17 = 1;
    v12[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return v7;
}

```

## disassembly

```asm
0x180009380  mov     r11, rsp
0x180009383  sub     rsp, 98h
0x18000938a  mov     rax, cs:__security_cookie
0x180009391  xor     rax, rsp
0x180009394  mov     [rsp+98h+var_20], rax
0x180009399  mov     [r11-8], rbp
0x18000939d  mov     rbp, rdx
0x1800093a0  mov     rdx, [rcx+10h]
0x1800093a4  mov     [r11-10h], rsi
0x1800093a8  mov     rsi, rcx
0x1800093ab  mov     [r11-18h], rdi
0x1800093af  test    rdx, rdx
0x1800093b2  jnz     short loc_1800093EE
0x1800093b4  mov     rax, [rcx+8]
0x1800093b8  test    rax, rax
0x1800093bb  jz      short loc_1800093D5
0x1800093bd  nop     dword ptr [rax]
0x1800093c0  mov     rdx, [rax+60h]
0x1800093c4  test    rdx, rdx
0x1800093c7  jnz     short loc_1800093EE
0x1800093c9  mov     rax, [rax+88h]
0x1800093d0  test    rax, rax
0x1800093d3  jnz     short loc_1800093C0
0x1800093d5  mov     edi, 1
0x1800093da  mov     [rsp+98h+arg_10], rbx
0x1800093e2  test    rbp, rbp
0x1800093e5  jnz     short loc_180009424
0x1800093e7  mov     ebx, 80004003h
0x1800093ec  jmp     short loc_180009452
0x1800093ee  xor     ecx, ecx
0x1800093f0  lea     r8, ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps
0x1800093f7  cmp     dword ptr [r8+rcx*4], 0
0x1800093fc  jz      short loc_18000940A
0x1800093fe  inc     ecx
0x180009400  cmp     ecx, 10h
0x180009403  jb      short loc_1800093F7
0x180009405  mov     ecx, 0FFFFFFFFh
0x18000940a  mov     eax, [rdx+80h]
0x180009410  bt      eax, ecx
0x180009413  jb      short loc_18000941C
0x180009415  mov     edi, 1
0x18000941a  jmp     short loc_1800093DA
0x18000941c  mov     eax, ecx
0x18000941e  mov     rdi, [rdx+rax*8]
0x180009422  jmp     short loc_1800093DA
0x180009424  mov     rcx, rbp; pvarg
0x180009427  xor     ebx, ebx
0x180009429  call    cs:__imp_VariantClear
0x180009430  nop     dword ptr [rax+rax+00h]
0x180009435  lea     eax, [rdi-8]
0x180009438  cmp     eax, 2
0x18000943b  jbe     short loc_180009452
0x18000943d  mov     rcx, [rsi+50h]
0x180009441  test    rcx, rcx
0x180009444  jz      short loc_180009452
0x180009446  mov     r8, rbp
0x180009449  mov     edx, edi
0x18000944b  call    ?ConformDataToVariant@@YAJPEBGW4ConfigDataType@@PEAUtagVARIANT@@@Z; ConformDataToVariant(ushort const *,ConfigDataType,tagVARIANT *)
0x180009450  mov     ebx, eax
0x180009452  mov     ecx, cs:dword_18003E048
0x180009458  mov     rdi, [rsp+98h+var_18]
0x180009460  mov     rsi, [rsp+98h+var_10]
0x180009468  mov     rbp, [rsp+98h+var_8]
0x180009470  cmp     ecx, 5
0x180009473  jbe     loc_18000952B
0x180009479  lea     rax, [rsp+98h+var_68]
0x18000947e  mov     [rsp+98h+var_68], ebx
0x180009482  mov     [rsp+98h+var_30], rax
0x180009487  lea     rcx, _TraceLoggingMetadata
0x18000948e  movzx   eax, cs:word_180036438
0x180009495  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x18000949a  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x18000949e  xor     r9d, r9d; RelatedActivityId
0x1800094a1  mov     rax, cs:off_18003E050
0x1800094a8  xor     r8d, r8d; ActivityId
0x1800094ab  mov     [rsp+98h+var_50.Ptr], rax
0x1800094b0  mov     [rsp+98h+var_28], 4
0x1800094b9  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x1800094c1  mov     [rsp+98h+EventDescriptor.Keyword], 0
0x1800094ca  movzx   eax, word ptr [rax]
0x1800094cd  mov     [rsp+98h+var_50.Size], eax
0x1800094d1  lea     rax, word_180036442
0x1800094d8  mov     [rsp+98h+var_40], rax
0x1800094dd  lea     rax, _TraceLoggingMetadataEnd
0x1800094e4  sub     eax, ecx
0x1800094e6  mov     dword ptr [rsp+98h+var_50.0Ch], 2
0x1800094ee  mov     [rsp+98h+var_38], 1Dh
0x1800094f6  mov     [rsp+98h+var_34], 1
0x1800094fe  mov     [rsp+98h+var_64], eax
0x180009502  mov     eax, [rsp+98h+var_64]
0x180009506  mov     rcx, cs:RegHandle; RegHandle
0x18000950d  lea     rax, [rsp+98h+var_50]
0x180009512  mov     [rsp+98h+UserData], rax; UserData
0x180009517  mov     [rsp+98h+UserDataCount], 3; UserDataCount
0x18000951f  call    cs:__imp_EventWriteTransfer
0x180009526  nop     dword ptr [rax+rax+00h]
0x18000952b  mov     eax, ebx
0x18000952d  mov     rbx, [rsp+98h+arg_10]
0x180009535  mov     rcx, [rsp+98h+var_20]
0x18000953a  xor     rcx, rsp; StackCookie
0x18000953d  call    __security_check_cookie
0x180009542  add     rsp, 98h
0x180009549  retn
```
