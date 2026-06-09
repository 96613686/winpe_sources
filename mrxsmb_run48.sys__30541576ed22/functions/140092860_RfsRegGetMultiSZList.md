# RfsRegGetMultiSZList

- ea: `0x140092860`
- end: `0x1400929ab`
- name: `RfsRegGetMultiSZList`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140020930`
- `0x140028fec`

## callees

- `0x140059f00`
- `0x140092860`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140092944`
- `ntoskrnl!ZwQueryValueKey` at `0x140096587`
- `ntoskrnl!ZwQueryValueKey` at `0x140092944`
- `ntoskrnl!ZwQueryValueKey` at `0x140096587`
- `ntoskrnl!ZwOpenKey` at `0x1400928fa`
- `ntoskrnl!ZwOpenKey` at `0x1400928fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400928ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400928bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400928ac`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400928bf`
- `ntoskrnl!ExAllocatePool2` at `0x140092979`
- `ntoskrnl!ExAllocatePool2` at `0x14009662c`
- `ntoskrnl!ExAllocatePool2` at `0x140092979`
- `ntoskrnl!ExAllocatePool2` at `0x14009662c`
- `ntoskrnl!ZwClose` at `0x14009295d`
- `ntoskrnl!ZwClose` at `0x14009299a`
- `ntoskrnl!ZwClose` at `0x140096599`
- `ntoskrnl!ZwClose` at `0x14009295d`
- `ntoskrnl!ZwClose` at `0x14009299a`
- `ntoskrnl!ZwClose` at `0x140096599`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096669`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400966e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096669`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400966e5`

## pseudocode

```c
__int64 __fastcall RfsRegGetMultiSZList(__int64 *a1, const WCHAR *a2, const WCHAR *a3, __int64 a4, ULONG ResultLength)
{
  NTSTATUS v7; // ebx
  unsigned int *Pool2; // rax
  unsigned int *v10; // r14
  ULONG v11; // ecx
  ULONG v12; // eax
  _WORD *v13; // r13
  unsigned int v14; // r15d
  _WORD *v15; // rdx
  ULONG v16; // edx
  __int64 v17; // r12
  _WORD *v18; // rsi
  ULONG v19; // eax
  unsigned int v20; // r9d
  _QWORD *v21; // rdx
  ULONG v22; // ecx
  UNICODE_STRING ValueName; // [rsp+30h] [rbp-41h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-21h] BYREF
  void *KeyHandle; // [rsp+E8h] [rbp+77h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  ValueName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, a2);
  RtlInitUnicodeString(&ValueName, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( v7 < 0 )
    goto LABEL_2;
  v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v7 != -1073741789 )
  {
    ZwClose(KeyHandle);
LABEL_2:
    *a1 = 0;
    return (unsigned int)v7;
  }
  Pool2 = (unsigned int *)ExAllocatePool2(258, ResultLength, 1383294546);
  v10 = Pool2;
  if ( !Pool2 )
  {
    v7 = -1073741670;
    ZwClose(KeyHandle);
    goto LABEL_2;
  }
  v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, Pool2, ResultLength, &ResultLength);
  ZwClose(KeyHandle);
  if ( v7 < 0 )
    goto LABEL_34;
  v11 = v10[3];
  ResultLength = v11;
  if ( v11 < 2 )
    goto LABEL_34;
  v12 = 0;
  v13 = (_WORD *)((char *)v10 + v10[2]);
  v14 = 0;
  v15 = v13;
  do
  {
    v12 += 2;
    if ( *v15 )
    {
      ++v14;
      ++v15;
      if ( v12 >= v11 )
        break;
      while ( *v15 )
      {
        v12 += 2;
        if ( v12 >= v11 )
          goto LABEL_18;
        ++v15;
      }
    }
    else
    {
      ++v15;
    }
  }
  while ( v12 < v11 );
LABEL_18:
  if ( !v14 )
  {
LABEL_34:
    ExFreePoolWithTag(v10, 0x52736652u);
    goto LABEL_2;
  }
  if ( v14 > 0x1000 || (v16 = v11 + 8 * v14, v16 + 8 < v11) )
  {
    v7 = -1073741675;
    goto LABEL_34;
  }
  v17 = ExAllocatePool2(256, v16 + 10, 1383294546);
  if ( !v17 )
  {
    v7 = -1073741670;
    goto LABEL_34;
  }
  v18 = (_WORD *)(v17 + 8LL * (v14 + 1));
  memmove(v18, v13, ResultLength);
  ExFreePoolWithTag(v10, 0x52736652u);
  v19 = 0;
  v20 = 0;
  v21 = (_QWORD *)v17;
  *(_WORD *)((char *)v18 + ResultLength) = 0;
  v22 = ResultLength;
  while ( v19 < v22 )
  {
    if ( v20 >= v14 )
      break;
    v19 += 2;
    if ( *v18 )
    {
      *v21 = v18;
      ++v20;
      v22 = ResultLength;
      ++v21;
      ++v18;
      if ( v19 >= ResultLength )
        break;
      while ( *v18 )
      {
        v19 += 2;
        if ( v19 >= ResultLength )
          goto LABEL_32;
        ++v18;
      }
    }
    else
    {
      ++v18;
    }
  }
LABEL_32:
  *v21 = 0;
  *a1 = v17;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140092860  mov     [rsp-8+KeyHandle], r9
0x140092865  push    rbp
0x140092866  push    rbx
0x140092867  push    rsi
0x140092868  push    rdi
0x140092869  push    r12
0x14009286b  push    r13
0x14009286d  push    r14
0x14009286f  push    r15
0x140092871  lea     rbp, [rsp-17h]
0x140092876  sub     rsp, 88h
0x14009287d  xorps   xmm0, xmm0
0x140092880  mov     rdi, rcx
0x140092883  xorps   xmm1, xmm1
0x140092886  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14009288a  xor     esi, esi
0x14009288c  xor     eax, eax
0x14009288e  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x140092892  mov     rbx, r8
0x140092895  mov     [rbp+4Fh+KeyHandle], rsi
0x140092899  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14009289d  mov     [rbp+4Fh+arg_20], esi
0x1400928a0  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x1400928a4  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x1400928a8  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400928ac  call    cs:__imp_RtlInitUnicodeString
0x1400928b3  nop     dword ptr [rax+rax+00h]
0x1400928b8  mov     rdx, rbx; SourceString
0x1400928bb  lea     rcx, [rbp+4Fh+ValueName]; DestinationString
0x1400928bf  call    cs:__imp_RtlInitUnicodeString
0x1400928c6  nop     dword ptr [rax+rax+00h]
0x1400928cb  lea     rax, [rbp+4Fh+DestinationString]
0x1400928cf  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400928d6  xorps   xmm0, xmm0
0x1400928d9  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400928dd  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400928e1  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x1400928e5  mov     edx, 1; DesiredAccess
0x1400928ea  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1400928f1  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1400928f5  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400928fa  call    cs:__imp_ZwOpenKey
0x140092901  nop     dword ptr [rax+rax+00h]
0x140092906  mov     ebx, eax
0x140092908  test    eax, eax
0x14009290a  jns     short loc_140092926
0x14009290c  mov     [rdi], rsi
0x14009290f  mov     eax, ebx
0x140092911  add     rsp, 88h
0x140092918  pop     r15
0x14009291a  pop     r14
0x14009291c  pop     r13
0x14009291e  pop     r12
0x140092920  pop     rdi
0x140092921  pop     rsi
0x140092922  pop     rbx
0x140092923  pop     rbp
0x140092924  retn
0x140092926  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14009292a  lea     rax, [rbp+4Fh+arg_20]
0x14009292e  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140092933  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x140092937  xor     r9d, r9d; KeyValueInformation
0x14009293a  mov     [rsp+0C0h+Length], esi; Length
0x14009293e  mov     r8d, 1; KeyValueInformationClass
0x140092944  call    cs:__imp_ZwQueryValueKey
0x14009294b  nop     dword ptr [rax+rax+00h]
0x140092950  mov     ebx, eax
0x140092952  cmp     eax, 0C0000023h
0x140092957  jz      short loc_14009296B
0x140092959  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14009295d  call    cs:__imp_ZwClose
0x140092964  nop     dword ptr [rax+rax+00h]
0x140092969  jmp     short loc_14009290C
0x14009296b  mov     edx, [rbp+4Fh+arg_20]
0x14009296e  mov     ecx, 102h
0x140092973  mov     r8d, 52736652h
0x140092979  call    cs:__imp_ExAllocatePool2
0x140092980  nop     dword ptr [rax+rax+00h]
0x140092985  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x140092989  mov     r14, rax
0x14009298c  test    rax, rax
0x14009298f  jnz     loc_14009656A
0x140092995  mov     ebx, 0C000009Ah
0x14009299a  call    cs:__imp_ZwClose
0x1400929a1  nop     dword ptr [rax+rax+00h]
0x1400929a6  jmp     loc_14009290C
0x14009656a  lea     rax, [rbp+4Fh+arg_20]
0x14009656e  mov     r9, r14; KeyValueInformation
0x140096571  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140096576  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14009657a  mov     eax, [rbp+4Fh+arg_20]
0x14009657d  mov     r8d, 1; KeyValueInformationClass
0x140096583  mov     [rsp+0C0h+Length], eax; Length
0x140096587  call    cs:__imp_ZwQueryValueKey
0x14009658e  nop     dword ptr [rax+rax+00h]
0x140096593  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x140096597  mov     ebx, eax
0x140096599  call    cs:__imp_ZwClose
0x1400965a0  nop     dword ptr [rax+rax+00h]
0x1400965a5  test    ebx, ebx
0x1400965a7  js      loc_1400966DD
0x1400965ad  mov     ecx, [r14+0Ch]
0x1400965b1  mov     [rbp+4Fh+arg_20], ecx
0x1400965b4  cmp     ecx, 2
0x1400965b7  jb      loc_1400966DD
0x1400965bd  mov     r13d, [r14+8]
0x1400965c1  mov     eax, esi
0x1400965c3  add     r13, r14
0x1400965c6  mov     r15d, esi
0x1400965c9  mov     rdx, r13
0x1400965cc  add     eax, 2
0x1400965cf  cmp     [rdx], si
0x1400965d2  jz      short loc_1400965F1
0x1400965d4  inc     r15d
0x1400965d7  add     rdx, 2
0x1400965db  cmp     eax, ecx
0x1400965dd  jnb     short loc_1400965F9
0x1400965df  cmp     [rdx], si
0x1400965e2  jz      short loc_1400965F5
0x1400965e4  add     eax, 2
0x1400965e7  cmp     eax, ecx
0x1400965e9  jnb     short loc_1400965F9
0x1400965eb  add     rdx, 2
0x1400965ef  jmp     short loc_1400965DF
0x1400965f1  add     rdx, 2
0x1400965f5  cmp     eax, ecx
0x1400965f7  jb      short loc_1400965CC
0x1400965f9  test    r15d, r15d
0x1400965fc  jz      loc_1400966DD
0x140096602  cmp     r15d, 1000h
0x140096609  ja      loc_1400966D8
0x14009660f  lea     edx, [rcx+r15*8]
0x140096613  lea     eax, [rdx+8]
0x140096616  cmp     eax, ecx
0x140096618  jb      loc_1400966D8
0x14009661e  add     edx, 0Ah
0x140096621  mov     ecx, 100h
0x140096626  mov     r8d, 52736652h
0x14009662c  call    cs:__imp_ExAllocatePool2
0x140096633  nop     dword ptr [rax+rax+00h]
0x140096638  mov     r12, rax
0x14009663b  test    rax, rax
0x14009663e  jnz     short loc_14009664A
0x140096640  mov     ebx, 0C000009Ah
0x140096645  jmp     loc_1400966DD
0x14009664a  mov     r8d, [rbp+4Fh+arg_20]; Size
0x14009664e  lea     eax, [r15+1]
0x140096652  lea     rsi, [r12+rax*8]
0x140096656  mov     rdx, r13; Src
0x140096659  mov     rcx, rsi; void *
0x14009665c  call    memmove
0x140096661  mov     edx, 52736652h; Tag
0x140096666  mov     rcx, r14; P
0x140096669  call    cs:__imp_ExFreePoolWithTag
0x140096670  nop     dword ptr [rax+rax+00h]
0x140096675  mov     ecx, [rbp+4Fh+arg_20]
0x140096678  xor     eax, eax
0x14009667a  xor     r9d, r9d
0x14009667d  mov     rdx, r12
0x140096680  mov     [rcx+rsi], ax
0x140096684  mov     ecx, [rbp+4Fh+arg_20]
0x140096687  test    ecx, ecx
0x140096689  jz      short loc_1400966C9
0x14009668b  cmp     r9d, r15d
0x14009668e  jnb     short loc_1400966C9
0x140096690  add     eax, 2
0x140096693  cmp     word ptr [rsi], 0
0x140096697  jz      short loc_1400966C1
0x140096699  mov     [rdx], rsi
0x14009669c  inc     r9d
0x14009669f  mov     ecx, [rbp+4Fh+arg_20]
0x1400966a2  add     rdx, 8
0x1400966a6  add     rsi, 2
0x1400966aa  cmp     eax, ecx
0x1400966ac  jnb     short loc_1400966C9
0x1400966ae  cmp     word ptr [rsi], 0
0x1400966b2  jz      short loc_1400966C5
0x1400966b4  add     eax, 2
0x1400966b7  cmp     eax, ecx
0x1400966b9  jnb     short loc_1400966C9
0x1400966bb  add     rsi, 2
0x1400966bf  jmp     short loc_1400966AE
0x1400966c1  add     rsi, 2
0x1400966c5  cmp     eax, ecx
0x1400966c7  jb      short loc_14009668B
0x1400966c9  mov     qword ptr [rdx], 0
0x1400966d0  mov     [rdi], r12
0x1400966d3  jmp     loc_14009290F
0x1400966d8  mov     ebx, 0C0000095h
0x1400966dd  mov     edx, 52736652h; Tag
0x1400966e2  mov     rcx, r14; P
0x1400966e5  call    cs:__imp_ExFreePoolWithTag
0x1400966ec  nop     dword ptr [rax+rax+00h]
0x1400966f1  nop
0x1400966f2  jmp     loc_14009290C
```
