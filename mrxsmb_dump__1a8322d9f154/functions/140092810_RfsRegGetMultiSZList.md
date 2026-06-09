# RfsRegGetMultiSZList

- ea: `0x140092810`
- end: `0x14009295b`
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
- `0x140092810`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x1400928f4`
- `ntoskrnl!ZwQueryValueKey` at `0x140096537`
- `ntoskrnl!ZwQueryValueKey` at `0x1400928f4`
- `ntoskrnl!ZwQueryValueKey` at `0x140096537`
- `ntoskrnl!ZwOpenKey` at `0x1400928aa`
- `ntoskrnl!ZwOpenKey` at `0x1400928aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009285c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009286f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009285c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009286f`
- `ntoskrnl!ExAllocatePool2` at `0x140092929`
- `ntoskrnl!ExAllocatePool2` at `0x1400965dc`
- `ntoskrnl!ExAllocatePool2` at `0x140092929`
- `ntoskrnl!ExAllocatePool2` at `0x1400965dc`
- `ntoskrnl!ZwClose` at `0x14009290d`
- `ntoskrnl!ZwClose` at `0x14009294a`
- `ntoskrnl!ZwClose` at `0x140096549`
- `ntoskrnl!ZwClose` at `0x14009290d`
- `ntoskrnl!ZwClose` at `0x14009294a`
- `ntoskrnl!ZwClose` at `0x140096549`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096619`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096695`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096619`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096695`

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
0x140092810  mov     [rsp-8+KeyHandle], r9
0x140092815  push    rbp
0x140092816  push    rbx
0x140092817  push    rsi
0x140092818  push    rdi
0x140092819  push    r12
0x14009281b  push    r13
0x14009281d  push    r14
0x14009281f  push    r15
0x140092821  lea     rbp, [rsp-17h]
0x140092826  sub     rsp, 88h
0x14009282d  xorps   xmm0, xmm0
0x140092830  mov     rdi, rcx
0x140092833  xorps   xmm1, xmm1
0x140092836  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14009283a  xor     esi, esi
0x14009283c  xor     eax, eax
0x14009283e  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x140092842  mov     rbx, r8
0x140092845  mov     [rbp+4Fh+KeyHandle], rsi
0x140092849  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x14009284d  mov     [rbp+4Fh+arg_20], esi
0x140092850  movups  xmmword ptr [rbp+4Fh+ValueName.Length], xmm0
0x140092854  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm1
0x140092858  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x14009285c  call    cs:__imp_RtlInitUnicodeString
0x140092863  nop     dword ptr [rax+rax+00h]
0x140092868  mov     rdx, rbx; SourceString
0x14009286b  lea     rcx, [rbp+4Fh+ValueName]; DestinationString
0x14009286f  call    cs:__imp_RtlInitUnicodeString
0x140092876  nop     dword ptr [rax+rax+00h]
0x14009287b  lea     rax, [rbp+4Fh+DestinationString]
0x14009287f  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x140092886  xorps   xmm0, xmm0
0x140092889  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x14009288d  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140092891  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x140092895  mov     edx, 1; DesiredAccess
0x14009289a  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1400928a1  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1400928a5  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400928aa  call    cs:__imp_ZwOpenKey
0x1400928b1  nop     dword ptr [rax+rax+00h]
0x1400928b6  mov     ebx, eax
0x1400928b8  test    eax, eax
0x1400928ba  jns     short loc_1400928D6
0x1400928bc  mov     [rdi], rsi
0x1400928bf  mov     eax, ebx
0x1400928c1  add     rsp, 88h
0x1400928c8  pop     r15
0x1400928ca  pop     r14
0x1400928cc  pop     r13
0x1400928ce  pop     r12
0x1400928d0  pop     rdi
0x1400928d1  pop     rsi
0x1400928d2  pop     rbx
0x1400928d3  pop     rbp
0x1400928d4  retn
0x1400928d6  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x1400928da  lea     rax, [rbp+4Fh+arg_20]
0x1400928de  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x1400928e3  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x1400928e7  xor     r9d, r9d; KeyValueInformation
0x1400928ea  mov     [rsp+0C0h+Length], esi; Length
0x1400928ee  mov     r8d, 1; KeyValueInformationClass
0x1400928f4  call    cs:__imp_ZwQueryValueKey
0x1400928fb  nop     dword ptr [rax+rax+00h]
0x140092900  mov     ebx, eax
0x140092902  cmp     eax, 0C0000023h
0x140092907  jz      short loc_14009291B
0x140092909  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x14009290d  call    cs:__imp_ZwClose
0x140092914  nop     dword ptr [rax+rax+00h]
0x140092919  jmp     short loc_1400928BC
0x14009291b  mov     edx, [rbp+4Fh+arg_20]
0x14009291e  mov     ecx, 102h
0x140092923  mov     r8d, 52736652h
0x140092929  call    cs:__imp_ExAllocatePool2
0x140092930  nop     dword ptr [rax+rax+00h]
0x140092935  mov     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x140092939  mov     r14, rax
0x14009293c  test    rax, rax
0x14009293f  jnz     loc_14009651A
0x140092945  mov     ebx, 0C000009Ah
0x14009294a  call    cs:__imp_ZwClose
0x140092951  nop     dword ptr [rax+rax+00h]
0x140092956  jmp     loc_1400928BC
0x14009651a  lea     rax, [rbp+4Fh+arg_20]
0x14009651e  mov     r9, r14; KeyValueInformation
0x140096521  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140096526  lea     rdx, [rbp+4Fh+ValueName]; ValueName
0x14009652a  mov     eax, [rbp+4Fh+arg_20]
0x14009652d  mov     r8d, 1; KeyValueInformationClass
0x140096533  mov     [rsp+0C0h+Length], eax; Length
0x140096537  call    cs:__imp_ZwQueryValueKey
0x14009653e  nop     dword ptr [rax+rax+00h]
0x140096543  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x140096547  mov     ebx, eax
0x140096549  call    cs:__imp_ZwClose
0x140096550  nop     dword ptr [rax+rax+00h]
0x140096555  test    ebx, ebx
0x140096557  js      loc_14009668D
0x14009655d  mov     ecx, [r14+0Ch]
0x140096561  mov     [rbp+4Fh+arg_20], ecx
0x140096564  cmp     ecx, 2
0x140096567  jb      loc_14009668D
0x14009656d  mov     r13d, [r14+8]
0x140096571  mov     eax, esi
0x140096573  add     r13, r14
0x140096576  mov     r15d, esi
0x140096579  mov     rdx, r13
0x14009657c  add     eax, 2
0x14009657f  cmp     [rdx], si
0x140096582  jz      short loc_1400965A1
0x140096584  inc     r15d
0x140096587  add     rdx, 2
0x14009658b  cmp     eax, ecx
0x14009658d  jnb     short loc_1400965A9
0x14009658f  cmp     [rdx], si
0x140096592  jz      short loc_1400965A5
0x140096594  add     eax, 2
0x140096597  cmp     eax, ecx
0x140096599  jnb     short loc_1400965A9
0x14009659b  add     rdx, 2
0x14009659f  jmp     short loc_14009658F
0x1400965a1  add     rdx, 2
0x1400965a5  cmp     eax, ecx
0x1400965a7  jb      short loc_14009657C
0x1400965a9  test    r15d, r15d
0x1400965ac  jz      loc_14009668D
0x1400965b2  cmp     r15d, 1000h
0x1400965b9  ja      loc_140096688
0x1400965bf  lea     edx, [rcx+r15*8]
0x1400965c3  lea     eax, [rdx+8]
0x1400965c6  cmp     eax, ecx
0x1400965c8  jb      loc_140096688
0x1400965ce  add     edx, 0Ah
0x1400965d1  mov     ecx, 100h
0x1400965d6  mov     r8d, 52736652h
0x1400965dc  call    cs:__imp_ExAllocatePool2
0x1400965e3  nop     dword ptr [rax+rax+00h]
0x1400965e8  mov     r12, rax
0x1400965eb  test    rax, rax
0x1400965ee  jnz     short loc_1400965FA
0x1400965f0  mov     ebx, 0C000009Ah
0x1400965f5  jmp     loc_14009668D
0x1400965fa  mov     r8d, [rbp+4Fh+arg_20]; Size
0x1400965fe  lea     eax, [r15+1]
0x140096602  lea     rsi, [r12+rax*8]
0x140096606  mov     rdx, r13; Src
0x140096609  mov     rcx, rsi; void *
0x14009660c  call    memmove
0x140096611  mov     edx, 52736652h; Tag
0x140096616  mov     rcx, r14; P
0x140096619  call    cs:__imp_ExFreePoolWithTag
0x140096620  nop     dword ptr [rax+rax+00h]
0x140096625  mov     ecx, [rbp+4Fh+arg_20]
0x140096628  xor     eax, eax
0x14009662a  xor     r9d, r9d
0x14009662d  mov     rdx, r12
0x140096630  mov     [rcx+rsi], ax
0x140096634  mov     ecx, [rbp+4Fh+arg_20]
0x140096637  test    ecx, ecx
0x140096639  jz      short loc_140096679
0x14009663b  cmp     r9d, r15d
0x14009663e  jnb     short loc_140096679
0x140096640  add     eax, 2
0x140096643  cmp     word ptr [rsi], 0
0x140096647  jz      short loc_140096671
0x140096649  mov     [rdx], rsi
0x14009664c  inc     r9d
0x14009664f  mov     ecx, [rbp+4Fh+arg_20]
0x140096652  add     rdx, 8
0x140096656  add     rsi, 2
0x14009665a  cmp     eax, ecx
0x14009665c  jnb     short loc_140096679
0x14009665e  cmp     word ptr [rsi], 0
0x140096662  jz      short loc_140096675
0x140096664  add     eax, 2
0x140096667  cmp     eax, ecx
0x140096669  jnb     short loc_140096679
0x14009666b  add     rsi, 2
0x14009666f  jmp     short loc_14009665E
0x140096671  add     rsi, 2
0x140096675  cmp     eax, ecx
0x140096677  jb      short loc_14009663B
0x140096679  mov     qword ptr [rdx], 0
0x140096680  mov     [rdi], r12
0x140096683  jmp     loc_1400928BF
0x140096688  mov     ebx, 0C0000095h
0x14009668d  mov     edx, 52736652h; Tag
0x140096692  mov     rcx, r14; P
0x140096695  call    cs:__imp_ExFreePoolWithTag
0x14009669c  nop     dword ptr [rax+rax+00h]
0x1400966a1  nop
0x1400966a2  jmp     loc_1400928BC
```
