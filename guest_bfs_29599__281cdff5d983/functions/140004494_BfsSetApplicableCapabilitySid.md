# BfsSetApplicableCapabilitySid

- ea: `0x140004494`
- end: `0x14000460e`
- name: `BfsSetApplicableCapabilitySid`
- size: `378`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x140004494`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x1400045a1`
- `ntoskrnl!RtlDeriveCapabilitySidsFromName` at `0x1400045a1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000458b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000458b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400045e7`
- `ntoskrnl!ExAllocatePool2` at `0x1400044ce`
- `ntoskrnl!ExAllocatePool2` at `0x140004530`
- `ntoskrnl!ExAllocatePool2` at `0x1400044ce`
- `ntoskrnl!ExAllocatePool2` at `0x140004530`

## string_xrefs

- `0x140004580`: `AgenticAppContainer`

## pseudocode

```c
__int64 BfsSetApplicableCapabilitySid()
{
  int v0; // ecx
  void *Pool2; // rsi
  int v2; // r8d
  int v3; // r9d
  unsigned int v4; // edi
  void *v5; // rbx
  int v6; // r8d
  int v7; // r9d
  int v8; // ecx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-29h]
  int v12; // [rsp+30h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+48h] [rbp-1h] BYREF
  int *v15; // [rsp+68h] [rbp+1Fh]
  __int64 v16; // [rsp+70h] [rbp+27h]

  DestinationString = 0;
  Pool2 = (void *)ExAllocatePool2(256, 44, 1400071746);
  if ( !Pool2 )
  {
    v4 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = -1073741801;
      v15 = &v12;
      v16 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v0, (int)&byte_140016D91, v2, v3, v11, &v14);
    }
    return v4;
  }
  v5 = (void *)ExAllocatePool2(256, 48, 1400071746);
  if ( !v5 )
  {
    v8 = dword_140019000;
    v4 = -1073741801;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_12;
    v12 = -1073741801;
    goto LABEL_7;
  }
  RtlInitUnicodeString(&DestinationString, L"AgenticAppContainer");
  v9 = RtlDeriveCapabilitySidsFromName(&DestinationString, Pool2, v5);
  v4 = v9;
  if ( v9 >= 0 )
  {
    gApplicableCapabilitySid = v5;
    v5 = 0;
  }
  else
  {
    v8 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v12 = v9;
LABEL_7:
      v16 = 4;
      v15 = &v12;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v6, v7, v11, &v14);
    }
  }
LABEL_12:
  ExFreePoolWithTag(Pool2, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  return v4;
}

```

## disassembly

```asm
0x140004494  push    rbp
0x140004496  push    rbx
0x140004497  push    rsi
0x140004498  push    rdi
0x140004499  lea     rbp, [rsp-3Fh]
0x14000449e  sub     rsp, 88h
0x1400044a5  mov     rax, cs:__security_cookie
0x1400044ac  xor     rax, rsp
0x1400044af  mov     [rbp+57h+var_28], rax
0x1400044b3  xorps   xmm0, xmm0
0x1400044b6  mov     ebx, 53736642h
0x1400044bb  mov     edi, 100h
0x1400044c0  mov     r8d, ebx
0x1400044c3  mov     ecx, edi
0x1400044c5  mov     edx, 2Ch ; ','
0x1400044ca  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400044ce  call    cs:__imp_ExAllocatePool2
0x1400044d5  nop     dword ptr [rax+rax+00h]
0x1400044da  mov     rsi, rax
0x1400044dd  test    rax, rax
0x1400044e0  jnz     short loc_140004525
0x1400044e2  mov     eax, cs:dword_140019000
0x1400044e8  mov     edx, 0C0000017h
0x1400044ed  mov     edi, edx
0x1400044ef  cmp     eax, 3
0x1400044f2  jbe     loc_1400045F3
0x1400044f8  lea     rax, [rbp+57h+var_70]
0x1400044fc  mov     [rbp+57h+var_70], edx
0x1400044ff  mov     [rbp+57h+var_38], rax
0x140004503  lea     rdx, byte_140016D91; int
0x14000450a  lea     rax, [rbp+57h+var_58]
0x14000450e  mov     [rbp+57h+var_30], 4
0x140004516  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x14000451b  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004520  jmp     loc_1400045F3
0x140004525  mov     r8d, ebx
0x140004528  mov     edx, 30h ; '0'
0x14000452d  mov     rcx, rdi
0x140004530  call    cs:__imp_ExAllocatePool2
0x140004537  nop     dword ptr [rax+rax+00h]
0x14000453c  mov     rbx, rax
0x14000453f  test    rax, rax
0x140004542  jnz     short loc_140004580
0x140004544  mov     ecx, cs:dword_140019000; int
0x14000454a  mov     edx, 0C0000017h
0x14000454f  mov     edi, edx
0x140004551  cmp     ecx, 3
0x140004554  jbe     short loc_1400045CC
0x140004556  mov     [rbp+57h+var_70], edx
0x140004559  lea     rax, [rbp+57h+var_70]
0x14000455d  mov     [rbp+57h+var_30], 4
0x140004565  mov     [rbp+57h+var_38], rax
0x140004569  lea     rdx, byte_140016D91; int
0x140004570  lea     rax, [rbp+57h+var_58]
0x140004574  mov     [rsp+0A0h+var_78], rax; PEVENT_DATA_DESCRIPTOR
0x140004579  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000457e  jmp     short loc_1400045CC
0x140004580  lea     rdx, aAgenticappcont; "AgenticAppContainer"
0x140004587  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000458b  call    cs:__imp_RtlInitUnicodeString
0x140004592  nop     dword ptr [rax+rax+00h]
0x140004597  mov     r8, rbx
0x14000459a  lea     rcx, [rbp+57h+DestinationString]
0x14000459e  mov     rdx, rsi
0x1400045a1  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1400045a8  nop     dword ptr [rax+rax+00h]
0x1400045ad  mov     edi, eax
0x1400045af  test    eax, eax
0x1400045b1  jns     short loc_1400045C3
0x1400045b3  mov     ecx, cs:dword_140019000
0x1400045b9  cmp     ecx, 3
0x1400045bc  jbe     short loc_1400045CC
0x1400045be  mov     [rbp+57h+var_70], eax
0x1400045c1  jmp     short loc_140004559
0x1400045c3  mov     cs:gApplicableCapabilitySid, rbx
0x1400045ca  xor     ebx, ebx
0x1400045cc  xor     edx, edx; Tag
0x1400045ce  mov     rcx, rsi; P
0x1400045d1  call    cs:__imp_ExFreePoolWithTag
0x1400045d8  nop     dword ptr [rax+rax+00h]
0x1400045dd  test    rbx, rbx
0x1400045e0  jz      short loc_1400045F3
0x1400045e2  xor     edx, edx; Tag
0x1400045e4  mov     rcx, rbx; P
0x1400045e7  call    cs:__imp_ExFreePoolWithTag
0x1400045ee  nop     dword ptr [rax+rax+00h]
0x1400045f3  mov     eax, edi
0x1400045f5  mov     rcx, [rbp+57h+var_28]
0x1400045f9  xor     rcx, rsp; StackCookie
0x1400045fc  call    __security_check_cookie
0x140004601  add     rsp, 88h
0x140004608  pop     rdi
0x140004609  pop     rsi
0x14000460a  pop     rbx
0x14000460b  pop     rbp
0x14000460c  retn
```
