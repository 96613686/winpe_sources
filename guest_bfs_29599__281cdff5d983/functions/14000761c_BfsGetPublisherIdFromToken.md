# BfsGetPublisherIdFromToken

- ea: `0x14000761c`
- end: `0x14000779e`
- name: `BfsGetPublisherIdFromToken`
- size: `386`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400067c0`

## callees

- `0x140001008`
- `0x14000761c`
- `0x140013860`
- `0x140013c80`
- `0x14001ed28`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400076d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400076d8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000776c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000776c`
- `ntoskrnl!ExAllocatePool2` at `0x140007704`
- `ntoskrnl!ExAllocatePool2` at `0x140007704`
- `ntoskrnl!RtlQueryPackageIdentityEx` at `0x1400076a8`
- `ntoskrnl!RtlQueryPackageIdentityEx` at `0x1400076a8`

## pseudocode

```c
__int64 __fastcall BfsGetPublisherIdFromToken(__int64 a1, struct _UNICODE_STRING *a2)
{
  int v4; // eax
  int v5; // r8d
  int v6; // r9d
  int v7; // ebx
  int v8; // ecx
  __int64 v9; // rdx
  __int64 Pool2; // rax
  __int64 v11; // rdx
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+68h] [rbp-98h] BYREF
  int *v18; // [rsp+88h] [rbp-78h]
  __int64 v19; // [rsp+90h] [rbp-70h]
  WCHAR SourceString[128]; // [rsp+A0h] [rbp-60h] BYREF

  v14 = 0;
  DestinationString = 0;
  memset(SourceString, 0, sizeof(SourceString));
  v15 = 256;
  *(_DWORD *)&a2->Length = 0;
  a2->Buffer = 0;
  v4 = RtlQueryPackageIdentityEx(a1, SourceString, &v15, 0);
  v7 = v4;
  if ( v4 < 0 )
  {
    v8 = dword_140019000;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v13 = v4;
LABEL_10:
      v19 = 4;
      v18 = &v13;
      tlgWriteTransfer_EtwWriteTransfer(v8, (int)&byte_140016D91, v5, v6, 0, &v17);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v7 = KappxParsePackageFullNameFromToken(&DestinationString, v9, a2);
  if ( v7 < 0 )
    goto LABEL_8;
  Pool2 = ExAllocatePool2(256, a2->MaximumLength, 1316185666);
  a2->Buffer = (PWSTR)Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741801;
    goto LABEL_8;
  }
  v7 = KappxParsePackageFullNameFromToken(&DestinationString, v11, a2);
  if ( v7 < 0 )
  {
LABEL_8:
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v13 = v7;
      goto LABEL_10;
    }
LABEL_11:
    RtlFreeUnicodeString(a2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000761c  mov     [rsp-8+arg_10], rbx
0x140007621  push    rbp
0x140007622  push    rdi
0x140007623  push    r14
0x140007625  lea     rbp, [rsp-0B0h]
0x14000762d  sub     rsp, 1B0h
0x140007634  mov     rax, cs:__security_cookie
0x14000763b  xor     rax, rsp
0x14000763e  mov     [rbp+0C0h+var_20], rax
0x140007645  mov     rdi, rdx
0x140007648  mov     [rsp+1C0h+var_178], 0
0x140007651  mov     rbx, rcx
0x140007654  xorps   xmm0, xmm0
0x140007657  mov     r14d, 100h
0x14000765d  lea     rcx, [rbp+0C0h+SourceString]; void *
0x140007661  mov     r8d, r14d; Size
0x140007664  xor     edx, edx; Val
0x140007666  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x14000766b  call    memset
0x140007670  xor     eax, eax
0x140007672  mov     [rsp+1C0h+var_170], r14
0x140007677  mov     [rdi], eax
0x140007679  lea     r8, [rsp+1C0h+var_170]
0x14000767e  mov     [rdi+8], rax
0x140007682  lea     rdx, [rbp+0C0h+SourceString]
0x140007686  lea     rax, [rsp+1C0h+var_178]
0x14000768b  xor     r9d, r9d
0x14000768e  mov     [rsp+1C0h+var_190], rax
0x140007693  mov     rcx, rbx
0x140007696  mov     [rsp+1C0h+var_198], 0
0x14000769f  mov     qword ptr [rsp+1C0h+var_1A0], 0; int
0x1400076a8  call    cs:__imp_RtlQueryPackageIdentityEx
0x1400076af  nop     dword ptr [rax+rax+00h]
0x1400076b4  mov     ebx, eax
0x1400076b6  test    eax, eax
0x1400076b8  jns     short loc_1400076CF
0x1400076ba  mov     ecx, cs:dword_140019000
0x1400076c0  cmp     ecx, 3
0x1400076c3  jbe     loc_140007769
0x1400076c9  mov     [rsp+1C0h+var_180], eax
0x1400076cd  jmp     short loc_140007742
0x1400076cf  lea     rdx, [rbp+0C0h+SourceString]; SourceString
0x1400076d3  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x1400076d8  call    cs:__imp_RtlInitUnicodeString
0x1400076df  nop     dword ptr [rax+rax+00h]
0x1400076e4  mov     r8, rdi
0x1400076e7  lea     rcx, [rsp+1C0h+DestinationString]
0x1400076ec  call    KappxParsePackageFullNameFromToken
0x1400076f1  mov     ebx, eax
0x1400076f3  test    eax, eax
0x1400076f5  js      short loc_140007733
0x1400076f7  movzx   edx, word ptr [rdi+2]
0x1400076fb  mov     r8d, 4E736642h
0x140007701  mov     rcx, r14
0x140007704  call    cs:__imp_ExAllocatePool2
0x14000770b  nop     dword ptr [rax+rax+00h]
0x140007710  mov     [rdi+8], rax
0x140007714  test    rax, rax
0x140007717  jnz     short loc_140007720
0x140007719  mov     ebx, 0C0000017h
0x14000771e  jmp     short loc_140007733
0x140007720  mov     r8, rdi
0x140007723  lea     rcx, [rsp+1C0h+DestinationString]
0x140007728  call    KappxParsePackageFullNameFromToken
0x14000772d  mov     ebx, eax
0x14000772f  test    eax, eax
0x140007731  jns     short loc_140007778
0x140007733  mov     eax, cs:dword_140019000
0x140007739  cmp     eax, 3
0x14000773c  jbe     short loc_140007769
0x14000773e  mov     [rsp+1C0h+var_180], ebx
0x140007742  lea     rax, [rsp+1C0h+var_180]
0x140007747  mov     [rbp+0C0h+var_130], 4
0x14000774f  mov     [rbp+0C0h+var_138], rax
0x140007753  lea     rdx, byte_140016D91; int
0x14000775a  lea     rax, [rsp+1C0h+var_158]
0x14000775f  mov     [rsp+1C0h+var_198], rax; PEVENT_DATA_DESCRIPTOR
0x140007764  call    _tlgWriteTransfer_EtwWriteTransfer
0x140007769  mov     rcx, rdi; UnicodeString
0x14000776c  call    cs:__imp_RtlFreeUnicodeString
0x140007773  nop     dword ptr [rax+rax+00h]
0x140007778  mov     eax, ebx
0x14000777a  mov     rcx, [rbp+0C0h+var_20]
0x140007781  xor     rcx, rsp; StackCookie
0x140007784  call    __security_check_cookie
0x140007789  mov     rbx, [rsp+1C0h+arg_10]
0x140007791  add     rsp, 1B0h
0x140007798  pop     r14
0x14000779a  pop     rdi
0x14000779b  pop     rbp
0x14000779c  retn
```
