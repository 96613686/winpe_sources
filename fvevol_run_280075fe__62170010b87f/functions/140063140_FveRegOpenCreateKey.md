# FveRegOpenCreateKey

- ea: `0x140063140`
- end: `0x1400632fe`
- name: `FveRegOpenCreateKey`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140063a40`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14005cf34`
- `0x140063140`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400631d7`
- `ntoskrnl!ZwOpenKey` at `0x1400631d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400632a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400632a2`
- `ntoskrnl!ZwCreateKey` at `0x140063287`
- `ntoskrnl!ZwCreateKey` at `0x140063287`

## pseudocode

```c
__int64 __fastcall FveRegOpenCreateKey(struct _UNICODE_STRING *a1, __int64 a2, void **a3)
{
  unsigned int v5; // ebx
  int SecurityDescriptor; // eax
  PVOID v7; // rdi
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  PVOID P; // [rsp+90h] [rbp+20h] BYREF

  memset(&ObjectAttributes, 0, 44);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
  }
  P = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = a1;
  v5 = ZwOpenKey(a3, 0x20006u, &ObjectAttributes);
  if ( v5 == -1073741772 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids);
    }
    SecurityDescriptor = FvepCreateSecurityDescriptor((struct _ACL **)&P);
    v7 = P;
    v5 = SecurityDescriptor;
    if ( SecurityDescriptor >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = a1;
      ObjectAttributes.SecurityDescriptor = P;
      ObjectAttributes.SecurityQualityOfService = 0;
      v5 = ZwCreateKey(a3, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0x30455646u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140063140  mov     [rsp-18h+arg_8], rbx
0x140063145  mov     [rsp-18h+arg_10], rsi
0x14006314a  push    rbp
0x14006314b  push    rdi
0x14006314c  push    r14
0x14006314e  mov     rbp, rsp
0x140063151  sub     rsp, 70h
0x140063155  xorps   xmm0, xmm0
0x140063158  mov     rsi, r8
0x14006315b  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14006315f  mov     r14, rcx
0x140063162  xor     eax, eax
0x140063164  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140063168  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14006316c  mov     rcx, cs:WPP_GLOBAL_Control
0x140063173  lea     rax, WPP_GLOBAL_Control
0x14006317a  cmp     rcx, rax
0x14006317d  jz      short loc_1400631A1
0x14006317f  mov     eax, [rcx+2Ch]
0x140063182  test    al, 8
0x140063184  jz      short loc_1400631A1
0x140063186  cmp     byte ptr [rcx+29h], 5
0x14006318a  jb      short loc_1400631A1
0x14006318c  mov     rcx, [rcx+18h]
0x140063190  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140063197  mov     edx, 36h ; '6'
0x14006319c  call    WPP_SF_
0x1400631a1  xorps   xmm0, xmm0
0x1400631a4  mov     [rbp+P], 0
0x1400631ac  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400631b0  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400631b7  mov     edx, 20006h; DesiredAccess
0x1400631bc  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400631c4  mov     rcx, rsi; KeyHandle
0x1400631c7  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400631ce  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400631d3  mov     [rbp+ObjectAttributes.ObjectName], r14
0x1400631d7  call    cs:__imp_ZwOpenKey
0x1400631de  nop     dword ptr [rax+rax+00h]
0x1400631e3  mov     ebx, eax
0x1400631e5  cmp     eax, 0C0000034h
0x1400631ea  jnz     loc_1400632AE
0x1400631f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400631f7  lea     rax, WPP_GLOBAL_Control
0x1400631fe  cmp     rcx, rax
0x140063201  jz      short loc_140063225
0x140063203  mov     eax, [rcx+2Ch]
0x140063206  test    al, 8
0x140063208  jz      short loc_140063225
0x14006320a  cmp     byte ptr [rcx+29h], 5
0x14006320e  jb      short loc_140063225
0x140063210  mov     rcx, [rcx+18h]
0x140063214  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14006321b  mov     edx, 37h ; '7'
0x140063220  call    WPP_SF_
0x140063225  lea     rcx, [rbp+P]
0x140063229  call    FvepCreateSecurityDescriptor
0x14006322e  mov     rdi, [rbp+P]
0x140063232  mov     ebx, eax
0x140063234  test    eax, eax
0x140063236  js      short loc_140063295
0x140063238  mov     [rsp+70h+Disposition], 0; Disposition
0x140063241  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140063245  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x14006324d  xor     r9d, r9d; TitleIndex
0x140063250  mov     edx, 20006h; DesiredAccess
0x140063255  mov     [rsp+70h+Class], 0; Class
0x14006325e  mov     rcx, rsi; KeyHandle
0x140063261  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140063268  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140063270  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140063277  mov     [rbp+ObjectAttributes.ObjectName], r14
0x14006327b  mov     [rbp+ObjectAttributes.SecurityDescriptor], rdi
0x14006327f  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140063287  call    cs:__imp_ZwCreateKey
0x14006328e  nop     dword ptr [rax+rax+00h]
0x140063293  mov     ebx, eax
0x140063295  test    rdi, rdi
0x140063298  jz      short loc_1400632AE
0x14006329a  mov     edx, 30455646h; Tag
0x14006329f  mov     rcx, rdi; P
0x1400632a2  call    cs:__imp_ExFreePoolWithTag
0x1400632a9  nop     dword ptr [rax+rax+00h]
0x1400632ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400632b5  lea     rax, WPP_GLOBAL_Control
0x1400632bc  cmp     rcx, rax
0x1400632bf  jz      short loc_1400632E6
0x1400632c1  mov     eax, [rcx+2Ch]
0x1400632c4  test    al, 8
0x1400632c6  jz      short loc_1400632E6
0x1400632c8  cmp     byte ptr [rcx+29h], 5
0x1400632cc  jb      short loc_1400632E6
0x1400632ce  mov     rcx, [rcx+18h]
0x1400632d2  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400632d9  mov     edx, 38h ; '8'
0x1400632de  mov     r9d, ebx
0x1400632e1  call    WPP_SF_d
0x1400632e6  lea     r11, [rsp+70h+var_s0]
0x1400632eb  mov     eax, ebx
0x1400632ed  mov     rbx, [r11+28h]
0x1400632f1  mov     rsi, [r11+30h]
0x1400632f5  mov     rsp, r11
0x1400632f8  pop     r14
0x1400632fa  pop     rdi
0x1400632fb  pop     rbp
0x1400632fc  retn
```
