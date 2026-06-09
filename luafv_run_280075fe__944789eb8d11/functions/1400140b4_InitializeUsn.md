# InitializeUsn

- ea: `0x1400140b4`
- end: `0x1400142a1`
- name: `InitializeUsn`
- size: `493`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001e770`
- `0x140024cfc`

## callees

- `0x140005f30`
- `0x140006380`
- `0x1400140b4`
- `0x140017a58`
- `0x140017afc`
- `0x140017c54`
- `0x14001ea60`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140014148`
- `ntoskrnl!KeClearEvent` at `0x140014148`
- `ntoskrnl!KeReadStateEvent` at `0x140014117`
- `ntoskrnl!KeReadStateEvent` at `0x140014134`
- `ntoskrnl!KeReadStateEvent` at `0x140014117`
- `ntoskrnl!KeReadStateEvent` at `0x140014134`
- `FLTMGR!FltCreateFileEx2` at `0x1400141eb`
- `FLTMGR!FltCreateFileEx2` at `0x1400141eb`

## pseudocode

```c
NTSTATUS __fastcall InitializeUsn(__int64 a1)
{
  NTSTATUS result; // eax
  struct _FLT_INSTANCE *v3; // rdx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v6[8]; // [rsp+C0h] [rbp-40h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(v6, 0, sizeof(v6));
  if ( *(_QWORD *)(a1 + 56) )
  {
LABEL_8:
    do
    {
      result = SynchronousFsControl(a1, 0, 590068, 0, 0, (__int64)v6, 64);
      if ( (unsigned int)(result - 1) <= 1 )
        break;
      if ( result >= 0 )
      {
        *(_QWORD *)(a1 + 248) = v6[0];
        *(_QWORD *)(a1 + 256) = v6[2];
        return 0;
      }
      if ( result == -1073741128 )
      {
        result = CreateUsn(a1);
      }
      else
      {
        if ( result != -1073741129 )
          return result;
        result = WaitForUsnDeletion(a1);
      }
    }
    while ( !result || result >= 3 );
  }
  else if ( KeReadStateEvent((PRKEVENT)(a1 + 112)) )
  {
    return 1;
  }
  else if ( KeReadStateEvent((PRKEVENT)(a1 + 136)) )
  {
    KeClearEvent((PRKEVENT)(a1 + 136));
    AcknowledgePauseRequest(a1);
    return 2;
  }
  else
  {
    v3 = *(struct _FLT_INSTANCE **)(a1 + 16);
    ObjectAttributes.ObjectName = (PUNICODE_STRING)(*(_QWORD *)(a1 + 24) + 56LL);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    result = FltCreateFileEx2(
               LuafvDriverData,
               v3,
               (PHANDLE)(a1 + 56),
               (PFILE_OBJECT *)(a1 + 64),
               3u,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0,
               7u,
               1u,
               0,
               0,
               0,
               0,
               0);
    if ( result >= 0 )
      goto LABEL_8;
    *(_QWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 64) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400140b4  mov     [rsp-8+arg_8], rbx
0x1400140b9  mov     [rsp-8+arg_10], rsi
0x1400140be  push    rbp
0x1400140bf  push    rdi
0x1400140c0  push    r14
0x1400140c2  lea     rbp, [rsp-10h]
0x1400140c7  sub     rsp, 110h
0x1400140ce  mov     rax, cs:__security_cookie
0x1400140d5  xor     rax, rsp
0x1400140d8  mov     [rbp+20h+var_20], rax
0x1400140dc  xorps   xmm0, xmm0
0x1400140df  xor     eax, eax
0x1400140e1  mov     rbx, rcx
0x1400140e4  xor     edx, edx; Val
0x1400140e6  movups  xmmword ptr [rbp+20h+var_A0.ObjectName], xmm0
0x1400140ea  lea     rcx, [rbp+20h+var_60]; void *
0x1400140ee  lea     r8d, [rax+40h]; Size
0x1400140f2  movups  xmmword ptr [rbp+20h+var_A0.Length], xmm0
0x1400140f6  movups  xmmword ptr [rbp+20h+var_A0+1Ch], xmm0
0x1400140fa  movups  xmmword ptr [rbp+20h+var_70], xmm0
0x1400140fe  call    memset
0x140014103  lea     rdi, [rbx+38h]
0x140014107  xor     r14d, r14d
0x14001410a  cmp     [rdi], r14
0x14001410d  jnz     loc_140014204
0x140014113  lea     rcx, [rdi+38h]; Event
0x140014117  call    cs:__imp_KeReadStateEvent
0x14001411e  nop     dword ptr [rax+rax+00h]
0x140014123  test    eax, eax
0x140014125  jz      short loc_140014130
0x140014127  lea     eax, [r14+1]
0x14001412b  jmp     loc_14001427C
0x140014130  lea     rcx, [rdi+50h]; Event
0x140014134  call    cs:__imp_KeReadStateEvent
0x14001413b  nop     dword ptr [rax+rax+00h]
0x140014140  test    eax, eax
0x140014142  jz      short loc_140014166
0x140014144  lea     rcx, [rdi+50h]; Event
0x140014148  call    cs:__imp_KeClearEvent
0x14001414f  nop     dword ptr [rax+rax+00h]
0x140014154  mov     rcx, rbx
0x140014157  call    AcknowledgePauseRequest
0x14001415c  mov     eax, 2
0x140014161  jmp     loc_14001427C
0x140014166  mov     rax, [rbx+18h]
0x14001416a  lea     r9, [rdi+8]; FileObject
0x14001416e  mov     rdx, [rbx+10h]; Instance
0x140014172  add     rax, 38h ; '8'
0x140014176  mov     rcx, cs:LuafvDriverData; Filter
0x14001417d  xorps   xmm0, xmm0
0x140014180  mov     [rsp+120h+DriverContext], r14; DriverContext
0x140014185  mov     r8, rdi; FileHandle
0x140014188  mov     [rsp+120h+Flags], r14d; Flags
0x14001418d  mov     [rsp+120h+EaLength], r14d; EaLength
0x140014192  mov     [rsp+120h+EaBuffer], r14; EaBuffer
0x140014197  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x14001419c  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1400141a4  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x1400141ac  mov     [rsp+120h+FileAttributes], r14d; FileAttributes
0x1400141b1  mov     [rbp+20h+var_A0.ObjectName], rax
0x1400141b5  lea     rax, [rbp+20h+var_70]
0x1400141b9  mov     [rsp+120h+AllocationSize], r14; AllocationSize
0x1400141be  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x1400141c3  lea     rax, [rbp+20h+var_A0]
0x1400141c7  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x1400141cc  mov     [rsp+120h+DesiredAccess], 3; DesiredAccess
0x1400141d4  mov     [rbp+20h+var_A0.Length], 30h ; '0'
0x1400141db  mov     [rbp+20h+var_A0.RootDirectory], r14
0x1400141df  mov     [rbp+20h+var_A0.Attributes], 240h
0x1400141e6  movdqu  xmmword ptr [rbp+20h+var_A0.SecurityDescriptor], xmm0
0x1400141eb  call    cs:__imp_FltCreateFileEx2
0x1400141f2  nop     dword ptr [rax+rax+00h]
0x1400141f7  test    eax, eax
0x1400141f9  jns     short loc_140014204
0x1400141fb  mov     [rdi], r14
0x1400141fe  mov     [rdi+8], r14
0x140014202  jmp     short loc_14001427C
0x140014204  lea     rax, [rbp+20h+var_60]
0x140014208  mov     dword ptr [rsp+120h+IoStatusBlock], 40h ; '@'
0x140014210  mov     [rsp+120h+ObjectAttributes], rax
0x140014215  xor     r9d, r9d
0x140014218  xor     edx, edx
0x14001421a  mov     [rsp+120h+DesiredAccess], r14d
0x14001421f  mov     r8d, 900F4h
0x140014225  mov     rcx, rbx
0x140014228  call    SynchronousFsControl
0x14001422d  lea     ecx, [rax-1]
0x140014230  cmp     ecx, 1
0x140014233  jbe     short loc_14001427C
0x140014235  test    eax, eax
0x140014237  jns     short loc_140014264
0x140014239  cmp     eax, 0C00002B8h
0x14001423e  jnz     short loc_14001424A
0x140014240  mov     rcx, rbx
0x140014243  call    CreateUsn
0x140014248  jmp     short loc_140014259
0x14001424a  cmp     eax, 0C00002B7h
0x14001424f  jnz     short loc_14001427C
0x140014251  mov     rcx, rbx
0x140014254  call    WaitForUsnDeletion
0x140014259  test    eax, eax
0x14001425b  jz      short loc_140014204
0x14001425d  cmp     eax, 3
0x140014260  jge     short loc_140014204
0x140014262  jmp     short loc_14001427C
0x140014264  mov     rax, [rbp+20h+var_60]
0x140014268  mov     [rbx+0F8h], rax
0x14001426f  mov     rax, [rbp+20h+var_50]
0x140014273  mov     [rbx+100h], rax
0x14001427a  xor     eax, eax
0x14001427c  mov     rcx, [rbp+20h+var_20]
0x140014280  xor     rcx, rsp; StackCookie
0x140014283  call    __security_check_cookie
0x140014288  lea     r11, [rsp+120h+var_10]
0x140014290  mov     rbx, [r11+28h]
0x140014294  mov     rsi, [r11+30h]
0x140014298  mov     rsp, r11
0x14001429b  pop     r14
0x14001429d  pop     rdi
0x14001429e  pop     rbp
0x14001429f  retn
```
