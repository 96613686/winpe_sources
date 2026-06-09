# FveRegOpenCreateKey

- ea: `0x1400651c0`
- end: `0x14006537e`
- name: `FveRegOpenCreateKey`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140065ac0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14005efb4`
- `0x1400651c0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x140065257`
- `ntoskrnl!ZwOpenKey` at `0x140065257`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065322`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065322`
- `ntoskrnl!ZwCreateKey` at `0x140065307`
- `ntoskrnl!ZwCreateKey` at `0x140065307`

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
0x1400651c0  mov     [rsp-18h+arg_8], rbx
0x1400651c5  mov     [rsp-18h+arg_10], rsi
0x1400651ca  push    rbp
0x1400651cb  push    rdi
0x1400651cc  push    r14
0x1400651ce  mov     rbp, rsp
0x1400651d1  sub     rsp, 70h
0x1400651d5  xorps   xmm0, xmm0
0x1400651d8  mov     rsi, r8
0x1400651db  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400651df  mov     r14, rcx
0x1400651e2  xor     eax, eax
0x1400651e4  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400651e8  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400651ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400651f3  lea     rax, WPP_GLOBAL_Control
0x1400651fa  cmp     rcx, rax
0x1400651fd  jz      short loc_140065221
0x1400651ff  mov     eax, [rcx+2Ch]
0x140065202  test    al, 8
0x140065204  jz      short loc_140065221
0x140065206  cmp     byte ptr [rcx+29h], 5
0x14006520a  jb      short loc_140065221
0x14006520c  mov     rcx, [rcx+18h]
0x140065210  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140065217  mov     edx, 36h ; '6'
0x14006521c  call    WPP_SF_
0x140065221  xorps   xmm0, xmm0
0x140065224  mov     [rbp+P], 0
0x14006522c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140065230  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140065237  mov     edx, 20006h; DesiredAccess
0x14006523c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140065244  mov     rcx, rsi; KeyHandle
0x140065247  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14006524e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140065253  mov     [rbp+ObjectAttributes.ObjectName], r14
0x140065257  call    cs:__imp_ZwOpenKey
0x14006525e  nop     dword ptr [rax+rax+00h]
0x140065263  mov     ebx, eax
0x140065265  cmp     eax, 0C0000034h
0x14006526a  jnz     loc_14006532E
0x140065270  mov     rcx, cs:WPP_GLOBAL_Control
0x140065277  lea     rax, WPP_GLOBAL_Control
0x14006527e  cmp     rcx, rax
0x140065281  jz      short loc_1400652A5
0x140065283  mov     eax, [rcx+2Ch]
0x140065286  test    al, 8
0x140065288  jz      short loc_1400652A5
0x14006528a  cmp     byte ptr [rcx+29h], 5
0x14006528e  jb      short loc_1400652A5
0x140065290  mov     rcx, [rcx+18h]
0x140065294  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x14006529b  mov     edx, 37h ; '7'
0x1400652a0  call    WPP_SF_
0x1400652a5  lea     rcx, [rbp+P]
0x1400652a9  call    FvepCreateSecurityDescriptor
0x1400652ae  mov     rdi, [rbp+P]
0x1400652b2  mov     ebx, eax
0x1400652b4  test    eax, eax
0x1400652b6  js      short loc_140065315
0x1400652b8  mov     [rsp+70h+Disposition], 0; Disposition
0x1400652c1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400652c5  mov     [rsp+70h+CreateOptions], 0; CreateOptions
0x1400652cd  xor     r9d, r9d; TitleIndex
0x1400652d0  mov     edx, 20006h; DesiredAccess
0x1400652d5  mov     [rsp+70h+Class], 0; Class
0x1400652de  mov     rcx, rsi; KeyHandle
0x1400652e1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400652e8  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400652f0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400652f7  mov     [rbp+ObjectAttributes.ObjectName], r14
0x1400652fb  mov     [rbp+ObjectAttributes.SecurityDescriptor], rdi
0x1400652ff  mov     [rbp+ObjectAttributes.SecurityQualityOfService], 0
0x140065307  call    cs:__imp_ZwCreateKey
0x14006530e  nop     dword ptr [rax+rax+00h]
0x140065313  mov     ebx, eax
0x140065315  test    rdi, rdi
0x140065318  jz      short loc_14006532E
0x14006531a  mov     edx, 30455646h; Tag
0x14006531f  mov     rcx, rdi; P
0x140065322  call    cs:__imp_ExFreePoolWithTag
0x140065329  nop     dword ptr [rax+rax+00h]
0x14006532e  mov     rcx, cs:WPP_GLOBAL_Control
0x140065335  lea     rax, WPP_GLOBAL_Control
0x14006533c  cmp     rcx, rax
0x14006533f  jz      short loc_140065366
0x140065341  mov     eax, [rcx+2Ch]
0x140065344  test    al, 8
0x140065346  jz      short loc_140065366
0x140065348  cmp     byte ptr [rcx+29h], 5
0x14006534c  jb      short loc_140065366
0x14006534e  mov     rcx, [rcx+18h]
0x140065352  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x140065359  mov     edx, 38h ; '8'
0x14006535e  mov     r9d, ebx
0x140065361  call    WPP_SF_d
0x140065366  lea     r11, [rsp+70h+var_s0]
0x14006536b  mov     eax, ebx
0x14006536d  mov     rbx, [r11+28h]
0x140065371  mov     rsi, [r11+30h]
0x140065375  mov     rsp, r11
0x140065378  pop     r14
0x14006537a  pop     rdi
0x14006537b  pop     rbp
0x14006537c  retn
```
