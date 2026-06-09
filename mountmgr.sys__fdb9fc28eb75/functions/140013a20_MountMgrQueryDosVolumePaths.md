# MountMgrQueryDosVolumePaths

- ea: `0x140013a20`
- end: `0x140013e5f`
- name: `MountMgrQueryDosVolumePaths`
- size: `1087`
- prototype: `__int64 __fastcall(struct _KMUTANT *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x140002f80`
- `0x1400119a0`
- `0x140013a20`
- `0x140013e70`
- `0x1400144a0`
- `0x14001a3d0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140013b06`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140013b06`
- `ntoskrnl!KeReleaseMutex` at `0x140013cd4`
- `ntoskrnl!KeReleaseMutex` at `0x140013cd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013bd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013bd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c77`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013cfd`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013cfd`

## pseudocode

```c
__int64 __fastcall MountMgrQueryDosVolumePaths(struct _KMUTANT *a1, _QWORD *a2)
{
  __int64 v2; // r8
  struct _LIST_ENTRY *v3; // r14
  unsigned int v6; // edx
  unsigned __int16 *v7; // r15
  int v8; // ecx
  bool v9; // di
  unsigned int v10; // esi
  unsigned int v11; // ebx
  __int64 v12; // r8
  struct _LIST_ENTRY *Blink; // rbx
  struct _LIST_ENTRY **i; // rdi
  int VolumePaths; // eax
  unsigned int v16; // ecx
  int v17; // eax
  __int64 result; // rax
  bool v19; // zf
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // [rsp+38h] [rbp-29h] BYREF
  __int64 v23; // [rsp+40h] [rbp-21h]
  __int128 v24; // [rsp+48h] [rbp-19h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+58h] [rbp-9h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp+7h] BYREF
  __int128 v27; // [rsp+78h] [rbp+17h] BYREF
  bool v28; // [rsp+D0h] [rbp+6Fh]
  int v29; // [rsp+D8h] [rbp+77h] BYREF
  PVOID P; // [rsp+E0h] [rbp+7Fh] BYREF

  v2 = a2[23];
  v3 = 0;
  v22 = 0;
  P = 0;
  v29 = 0;
  ObjectName = 0;
  v23 = v2;
  v24 = 0;
  v27 = 0;
  v6 = *(_DWORD *)(v2 + 16);
  if ( v6 < 4 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v21 = 313;
    goto LABEL_53;
  }
  v7 = (unsigned __int16 *)a2[3];
  v8 = *v7;
  if ( (v8 & 1) != 0 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v21 = 314;
    goto LABEL_53;
  }
  if ( v6 < v8 + 2 )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v21 = 315;
    goto LABEL_53;
  }
  if ( *(_DWORD *)(v2 + 8) < 4u )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 3221225485LL;
    v21 = 316;
LABEL_53:
    WPP_SF_L(v20->AttachedDevice, v21, v2, 3221225485LL);
    return 3221225485LL;
  }
  v9 = 0;
  v28 = 0;
  v10 = 0;
  ObjectName.Buffer = v7 + 1;
  ObjectName.Length = v8;
  ObjectName.MaximumLength = v8;
  while ( v10 < 0x3E8 )
  {
    String1 = 0;
    v11 = QueryDeviceName(&ObjectName, &String1);
    if ( (v11 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 17, v12, v11);
      }
LABEL_30:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 317, v12, v11);
        return v11;
      }
      return v11;
    }
    Blink = a1->Header.WaitListHead.Blink;
    for ( i = &a1->Header.WaitListHead.Blink; Blink != (struct _LIST_ENTRY *)i; Blink = Blink->Flink )
    {
      v3 = Blink;
      if ( RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)&Blink[5], 1u) )
        break;
    }
    ExFreePoolWithTag(String1.Buffer, 0);
    if ( Blink == (struct _LIST_ENTRY *)i )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 18, v12, 3221225524LL);
      v11 = -1073741772;
      goto LABEL_30;
    }
    v22 = 0;
    *((_QWORD *)&v24 + 1) = &v24;
    *(_QWORD *)&v24 = &v24;
    VolumePaths = MountMgrQueryVolumePaths(
                    (_DWORD)a1,
                    (_DWORD)v3,
                    (unsigned int)&v24,
                    (unsigned int)&P,
                    (__int64)&v29,
                    (__int64)&v22);
    v11 = VolumePaths;
    if ( VolumePaths >= 0 )
    {
      v9 = v28;
      goto LABEL_14;
    }
    if ( VolumePaths != -1073741267 )
      goto LABEL_56;
    if ( v22 )
    {
      v19 = BYTE1(v3[8].Flink) == 0;
      *(_QWORD *)&v27 = a1;
      v9 = v19;
      *((_QWORD *)&v27 + 1) = v22;
      v28 = v19;
      KeReleaseMutex(a1 + 1, 0);
      ReconcileThisDatabaseWithMasterWorker(&v27);
      v3 = 0;
      KeWaitForSingleObject(&a1[1], Executive, 0, 0, 0);
    }
    else
    {
      v9 = v28;
      v3 = 0;
    }
    ++v10;
  }
  if ( v10 == 1000 )
  {
    v11 = -1073741823;
LABEL_56:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 318, v2, v11);
    return v11;
  }
LABEL_14:
  if ( v9 )
    MountMgrNotifyNameChange(a1, &ObjectName, 0);
  v16 = *(_DWORD *)P;
  v17 = -5;
  *(_DWORD *)v7 = *(_DWORD *)P;
  if ( v16 > 0xFFFFFFFB )
    *(_DWORD *)v7 = -5;
  else
    v17 = v16;
  a2[7] = (unsigned int)(v17 + 4);
  if ( (unsigned int)(v17 + 4) > *(_DWORD *)(v23 + 8) )
  {
    ExFreePoolWithTag(P, 0);
    result = 2147483653LL;
    a2[7] = 4;
  }
  else
  {
    memmove(v7 + 2, (char *)P + 4, *(unsigned int *)v7);
    ExFreePoolWithTag(P, 0);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140013a20  mov     r11, rsp
0x140013a23  push    rbp
0x140013a24  push    rdi
0x140013a25  push    r12
0x140013a27  push    r13
0x140013a29  push    r14
0x140013a2b  push    r15
0x140013a2d  lea     rbp, [r11-5Fh]
0x140013a31  sub     rsp, 88h
0x140013a38  mov     r8, [rdx+0B8h]
0x140013a3f  xor     r14d, r14d
0x140013a42  xorps   xmm0, xmm0
0x140013a45  mov     [rbp+57h+var_80], r14
0x140013a49  xorps   xmm1, xmm1
0x140013a4c  mov     [rbp+57h+P], r14
0x140013a50  mov     r12, rdx
0x140013a53  mov     [rbp+57h+arg_10], r14d
0x140013a57  movups  xmmword ptr [rbp+57h+ObjectName.Length], xmm0
0x140013a5b  mov     r13, rcx
0x140013a5e  mov     [rbp+57h+var_78], r8
0x140013a62  movups  [rbp+57h+var_70], xmm1
0x140013a66  movups  xmmword ptr [rbp+17h], xmm0
0x140013a6a  mov     edx, [r8+10h]
0x140013a6e  cmp     edx, 4
0x140013a71  jb      loc_140013D6B
0x140013a77  mov     r15, [r12+18h]
0x140013a7c  movzx   ecx, word ptr [r15]
0x140013a80  test    cl, 1
0x140013a83  jnz     loc_140013D8C
0x140013a89  lea     eax, [rcx+2]
0x140013a8c  cmp     edx, eax
0x140013a8e  jb      loc_140013DAD
0x140013a94  cmp     dword ptr [r8+8], 4
0x140013a99  jb      loc_140013DCE
0x140013a9f  mov     [r11+8], rbx
0x140013aa3  lea     rax, [r15+2]
0x140013aa7  xor     dil, dil
0x140013aaa  mov     [r11-38h], rsi
0x140013aae  mov     [rbp+57h+arg_8], dil
0x140013ab2  mov     esi, r14d
0x140013ab5  mov     [rbp+57h+ObjectName.Buffer], rax
0x140013ab9  mov     [rbp+57h+ObjectName.Length], cx
0x140013abd  mov     [rbp+57h+ObjectName.MaximumLength], cx
0x140013ac1  cmp     esi, 3E8h
0x140013ac7  jnb     loc_140013B7E
0x140013acd  xorps   xmm0, xmm0
0x140013ad0  lea     rdx, [rbp+57h+String1]; StringOut
0x140013ad4  lea     rcx, [rbp+57h+ObjectName]; ObjectName
0x140013ad8  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140013adc  call    QueryDeviceName
0x140013ae1  mov     ebx, eax
0x140013ae3  test    eax, eax
0x140013ae5  js      loc_140013D10
0x140013aeb  mov     rbx, [r13+10h]
0x140013aef  lea     rdi, [r13+10h]
0x140013af3  cmp     rbx, rdi
0x140013af6  jz      short loc_140013B1A
0x140013af8  lea     rdx, [rbx+50h]; String2
0x140013afc  mov     r8b, 1; CaseInSensitive
0x140013aff  lea     rcx, [rbp+57h+String1]; String1
0x140013b03  mov     r14, rbx
0x140013b06  call    cs:__imp_RtlEqualUnicodeString
0x140013b0d  nop     dword ptr [rax+rax+00h]
0x140013b12  test    al, al
0x140013b14  jz      loc_140013BE6
0x140013b1a  mov     rcx, [rbp+57h+String1.Buffer]; P
0x140013b1e  xor     edx, edx; Tag
0x140013b20  call    cs:__imp_ExFreePoolWithTag
0x140013b27  nop     dword ptr [rax+rax+00h]
0x140013b2c  cmp     rbx, rdi
0x140013b2f  jz      loc_140013C1D
0x140013b35  lea     rax, [rbp+57h+var_70]
0x140013b39  mov     [rbp+57h+var_80], 0
0x140013b41  mov     qword ptr [rbp+57h+var_70+8], rax
0x140013b45  lea     r9, [rbp+57h+P]
0x140013b49  lea     rax, [rbp+57h+var_70]
0x140013b4d  mov     rdx, r14
0x140013b50  mov     qword ptr [rbp+57h+var_70], rax
0x140013b54  lea     r8, [rbp+57h+var_70]
0x140013b58  lea     rax, [rbp+57h+var_80]
0x140013b5c  mov     rcx, r13
0x140013b5f  mov     [rsp+28h], rax
0x140013b64  lea     rax, [rbp+57h+arg_10]
0x140013b68  mov     [rsp+0B0h+Timeout], rax
0x140013b6d  call    MountMgrQueryVolumePaths
0x140013b72  mov     ebx, eax
0x140013b74  test    eax, eax
0x140013b76  js      short loc_140013BF7
0x140013b78  movzx   edi, [rbp+57h+arg_8]
0x140013b7c  jmp     short loc_140013B84
0x140013b7e  jz      loc_140013E06
0x140013b84  test    dil, dil
0x140013b87  jnz     loc_140013E43
0x140013b8d  mov     rax, [rbp+57h+P]
0x140013b91  mov     ecx, [rax]
0x140013b93  mov     eax, 0FFFFFFFBh
0x140013b98  mov     [r15], ecx
0x140013b9b  cmp     ecx, eax
0x140013b9d  ja      loc_140013E57
0x140013ba3  mov     eax, ecx
0x140013ba5  lea     ecx, [rax+4]
0x140013ba8  mov     eax, ecx
0x140013baa  mov     [r12+38h], rax
0x140013baf  mov     rax, [rbp+57h+var_78]
0x140013bb3  cmp     ecx, [rax+8]
0x140013bb6  ja      loc_140013C71
0x140013bbc  mov     rdx, [rbp+57h+P]
0x140013bc0  lea     rcx, [r15+4]; void *
0x140013bc4  mov     r8d, [r15]; Size
0x140013bc7  add     rdx, 4; Src
0x140013bcb  call    memmove
0x140013bd0  mov     rcx, [rbp+57h+P]; P
0x140013bd4  xor     edx, edx; Tag
0x140013bd6  call    cs:__imp_ExFreePoolWithTag
0x140013bdd  nop     dword ptr [rax+rax+00h]
0x140013be2  xor     eax, eax
0x140013be4  jmp     short loc_140013C4E
0x140013be6  mov     rbx, [rbx]
0x140013be9  cmp     rbx, rdi
0x140013bec  jz      loc_140013B1A
0x140013bf2  jmp     loc_140013AF8
0x140013bf7  cmp     eax, 0C000022Dh
0x140013bfc  jnz     loc_140013E0B
0x140013c02  mov     rax, [rbp+57h+var_80]
0x140013c06  test    rax, rax
0x140013c09  jnz     loc_140013CB6
0x140013c0f  movzx   edi, [rbp+57h+arg_8]
0x140013c13  xor     r14d, r14d
0x140013c16  inc     esi
0x140013c18  jmp     loc_140013AC1
0x140013c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c24  lea     rdi, WPP_GLOBAL_Control
0x140013c2b  cmp     rcx, rdi
0x140013c2e  jz      short loc_140013C3B
0x140013c30  mov     eax, [rcx+2Ch]
0x140013c33  test    al, 1
0x140013c35  jnz     loc_140013D52
0x140013c3b  mov     ebx, 0C0000034h
0x140013c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c47  cmp     rcx, rdi
0x140013c4a  jnz     short loc_140013C93
0x140013c4c  mov     eax, ebx
0x140013c4e  mov     rbx, [rsp+0B0h+arg_0]
0x140013c56  mov     rsi, [rsp+80h]
0x140013c5e  add     rsp, 88h
0x140013c65  pop     r15
0x140013c67  pop     r14
0x140013c69  pop     r13
0x140013c6b  pop     r12
0x140013c6d  pop     rdi
0x140013c6e  pop     rbp
0x140013c6f  retn
0x140013c71  mov     rcx, [rbp+57h+P]; P
0x140013c75  xor     edx, edx; Tag
0x140013c77  call    cs:__imp_ExFreePoolWithTag
0x140013c7e  nop     dword ptr [rax+rax+00h]
0x140013c83  mov     eax, 80000005h
0x140013c88  mov     qword ptr [r12+38h], 4
0x140013c91  jmp     short loc_140013C4E
0x140013c93  mov     edx, [rcx+2Ch]
0x140013c96  test    dl, 1
0x140013c99  jz      short loc_140013C4C
0x140013c9b  cmp     byte ptr [rcx+29h], 1
0x140013c9f  jb      short loc_140013C4C
0x140013ca1  mov     rcx, [rcx+18h]
0x140013ca5  mov     edx, 13Dh
0x140013caa  mov     r9d, ebx
0x140013cad  call    WPP_SF_L
0x140013cb2  mov     eax, ebx
0x140013cb4  jmp     short loc_140013C4E
0x140013cb6  cmp     byte ptr [r14+81h], 0
0x140013cbe  lea     rcx, [r13+38h]; Mutex
0x140013cc2  mov     [rbp+57h+var_40], r13
0x140013cc6  setz    dil
0x140013cca  mov     [rbp+57h+var_38], rax
0x140013cce  xor     edx, edx; Wait
0x140013cd0  mov     [rbp+57h+arg_8], dil
0x140013cd4  call    cs:__imp_KeReleaseMutex
0x140013cdb  nop     dword ptr [rax+rax+00h]
0x140013ce0  lea     rcx, [rbp+57h+var_40]
0x140013ce4  call    ReconcileThisDatabaseWithMasterWorker
0x140013ce9  xor     r14d, r14d
0x140013cec  lea     rcx, [r13+38h]; Object
0x140013cf0  xor     r9d, r9d; Alertable
0x140013cf3  mov     [rsp+0B0h+Timeout], r14; Timeout
0x140013cf8  xor     r8d, r8d; WaitMode
0x140013cfb  xor     edx, edx; WaitReason
0x140013cfd  call    cs:__imp_KeWaitForSingleObject
0x140013d04  nop     dword ptr [rax+rax+00h]
0x140013d09  inc     esi
0x140013d0b  jmp     loc_140013AC1
0x140013d10  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d17  lea     rdi, WPP_GLOBAL_Control
0x140013d1e  cmp     rcx, rdi
0x140013d21  jz      loc_140013C40
0x140013d27  mov     eax, [rcx+2Ch]
0x140013d2a  test    al, 1
0x140013d2c  jz      loc_140013C40
0x140013d32  cmp     byte ptr [rcx+29h], 1
0x140013d36  jb      loc_140013C40
0x140013d3c  mov     rcx, [rcx+18h]
0x140013d40  mov     edx, 11h
0x140013d45  mov     r9d, ebx
0x140013d48  call    WPP_SF_L
0x140013d4d  jmp     loc_140013C40
0x140013d52  mov     rcx, [rcx+18h]
0x140013d56  mov     edx, 12h
0x140013d5b  mov     r9d, 0C0000034h
0x140013d61  call    WPP_SF_L
0x140013d66  jmp     loc_140013C3B
0x140013d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d72  lea     rdi, WPP_GLOBAL_Control
0x140013d79  cmp     rcx, rdi
0x140013d7c  jz      short loc_140013DFC
0x140013d7e  mov     eax, [rcx+2Ch]
0x140013d81  test    al, 1
0x140013d83  jz      short loc_140013DFC
0x140013d85  mov     edx, 139h
0x140013d8a  jmp     short loc_140013DED
0x140013d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d93  lea     rdi, WPP_GLOBAL_Control
0x140013d9a  cmp     rcx, rdi
0x140013d9d  jz      short loc_140013DFC
0x140013d9f  mov     eax, [rcx+2Ch]
0x140013da2  test    al, 1
0x140013da4  jz      short loc_140013DFC
0x140013da6  mov     edx, 13Ah
0x140013dab  jmp     short loc_140013DED
0x140013dad  mov     rcx, cs:WPP_GLOBAL_Control
0x140013db4  lea     rdi, WPP_GLOBAL_Control
0x140013dbb  cmp     rcx, rdi
0x140013dbe  jz      short loc_140013DFC
0x140013dc0  mov     eax, [rcx+2Ch]
0x140013dc3  test    al, 1
0x140013dc5  jz      short loc_140013DFC
0x140013dc7  mov     edx, 13Bh
0x140013dcc  jmp     short loc_140013DED
0x140013dce  mov     rcx, cs:WPP_GLOBAL_Control
0x140013dd5  lea     rdi, WPP_GLOBAL_Control
0x140013ddc  cmp     rcx, rdi
0x140013ddf  jz      short loc_140013DFC
0x140013de1  mov     eax, [rcx+2Ch]
0x140013de4  test    al, 1
0x140013de6  jz      short loc_140013DFC
0x140013de8  mov     edx, 13Ch
0x140013ded  mov     rcx, [rcx+18h]
0x140013df1  mov     r9d, 0C000000Dh
0x140013df7  call    WPP_SF_L
0x140013dfc  mov     eax, 0C000000Dh
0x140013e01  jmp     loc_140013C5E
0x140013e06  mov     ebx, 0C0000001h
0x140013e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013e12  lea     rdi, WPP_GLOBAL_Control
0x140013e19  cmp     rcx, rdi
0x140013e1c  jz      loc_140013C4C
0x140013e22  mov     eax, [rcx+2Ch]
0x140013e25  test    al, 1
0x140013e27  jz      loc_140013C4C
0x140013e2d  mov     rcx, [rcx+18h]
0x140013e31  mov     edx, 13Eh
0x140013e36  mov     r9d, ebx
0x140013e39  call    WPP_SF_L
0x140013e3e  jmp     loc_140013C4C
0x140013e43  xor     r8d, r8d
0x140013e46  lea     rdx, [rbp+57h+ObjectName]
0x140013e4a  mov     rcx, r13
0x140013e4d  call    MountMgrNotifyNameChange
0x140013e52  jmp     loc_140013B8D
0x140013e57  mov     [r15], eax
0x140013e5a  jmp     loc_140013BA5
```
