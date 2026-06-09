# FatCommonQueryInformation

- ea: `0x140039ad8`
- end: `0x140039e8d`
- name: `FatCommonQueryInformation`
- size: `949`
- prototype: `__int64 __fastcall(PVOID Context1, PVOID Context2)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14003a550`
- `0x1400438e0`

## callees

- `0x140007408`
- `0x140038eb4`
- `0x140039ad8`
- `0x14003a6c8`
- `0x14003a7a4`
- `0x14003a7b8`
- `0x14003a828`
- `0x14003a998`
- `0x14003aaa0`
- `0x14003ab48`
- `0x14003d880`
- `0x1400466c8`
- `0x1400468c4`
- `0x14004a1d4`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140039e43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039e60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e307`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e325`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039e43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140039e60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e307`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e325`

## pseudocode

```c
__int64 __fastcall FatCommonQueryInformation(PVOID Context1, IRP *Context2)
{
  IRP *v2; // r13
  char v4; // r12
  unsigned __int64 Options; // rdi
  struct _IRP *MasterIrp; // r15
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // r8d
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  unsigned int NameInfo; // eax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 p_UserApcContext; // [rsp+20h] [rbp-78h]
  char v28; // [rsp+30h] [rbp-68h]
  __int64 v29; // [rsp+38h] [rbp-60h] BYREF
  struct _ERESOURCE *v30; // [rsp+40h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+48h] [rbp-50h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+50h] [rbp-48h]
  ULONG Length; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+20h] BYREF

  v2 = Context2;
  v30 = 0;
  v34 = 0;
  v29 = 0;
  v28 = 0;
  v4 = 0;
  CurrentStackLocation = Context2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  Length = CurrentStackLocation->Parameters.Read.Length;
  Options = CurrentStackLocation->Parameters.Create.Options;
  MasterIrp = Context2->AssociatedIrp.MasterIrp;
  v7 = 0;
  v8 = FatDecodeFileObject(FileObject, &v30, &v34, &v29) - 2;
  if ( !v8 || (v10 = v8 - 1) == 0 || (v11 = v10 - 1) != 0 && ((v12 = v11 - 2) == 0 || v12 == 3) )
  {
    if ( (unsigned int)Options <= 0x30 )
    {
      v14 = 0x1000000040200LL;
      if ( _bittest64(&v14, Options) )
      {
        if ( !(unsigned __int8)FatAcquireExclusiveVcb_Real(Context1, v30, 0) )
        {
          v7 = FatFsdPostRequest(Context1, v2);
          Context1 = 0;
          v2 = 0;
          v13 = v34;
          goto LABEL_42;
        }
        v4 = 1;
      }
    }
    v13 = v34;
    if ( (*(_DWORD *)(v34 + 192) & 4) == 0 || (*(_DWORD *)(*(_QWORD *)(v34 + 184) + 200LL) & 2) != 0 )
    {
      if ( !(unsigned __int8)FatAcquireSharedFcb(Context1, v34) )
      {
        v7 = FatFsdPostRequest(Context1, v2);
        Context1 = 0;
        v2 = 0;
        goto LABEL_42;
      }
      v28 = 1;
    }
    FatVerifyFcb(Context1, v13);
    if ( (int)Options <= 14 )
    {
      if ( (_DWORD)Options == 14 )
      {
        *(_QWORD *)&MasterIrp->Type = FileObject->CurrentByteOffset.QuadPart;
        Length -= 8;
        goto LABEL_41;
      }
      v18 = Options - 4;
      if ( !v18 )
      {
        FatQueryBasicInfo(v16, v13, v17, (_DWORD)MasterIrp, (__int64)&Length);
        goto LABEL_41;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        FatQueryStandardInfo(Context1, v13, MasterIrp, &Length);
        goto LABEL_41;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        FatQueryInternalInfo(v16, v13, MasterIrp, &Length);
        goto LABEL_41;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        FatQueryEaInfo(v16, v15, MasterIrp, &Length);
        goto LABEL_41;
      }
      if ( v21 == 2 )
      {
        p_UserApcContext = (__int64)MasterIrp;
LABEL_39:
        NameInfo = FatQueryNameInfo((_DWORD)Context1, v13, v29, 0, p_UserApcContext, (__int64)&Length);
        goto LABEL_40;
      }
LABEL_34:
      v7 = -1073741811;
      goto LABEL_41;
    }
    switch ( (_DWORD)Options )
    {
      case 0x12:
        Length -= 12;
        FatQueryBasicInfo(v16, v13, v17, (_DWORD)MasterIrp, (__int64)&Length);
        FatQueryStandardInfo(Context1, v13, &MasterIrp->ThreadListEntry.Blink, &Length);
        FatQueryInternalInfo(v23, v13, &MasterIrp->RequestorMode, &Length);
        FatQueryEaInfo(v25, v24, &MasterIrp->UserIosb, &Length);
        MasterIrp->UserEvent = (PKEVENT)FileObject->CurrentByteOffset.QuadPart;
        Length -= 8;
        p_UserApcContext = (__int64)&MasterIrp->Overlay.AsynchronousParameters.UserApcContext;
        goto LABEL_39;
      case 0x15:
        NameInfo = FatQueryShortNameInfo(v16, v13, MasterIrp, &Length);
        break;
      case 0x22:
        FatQueryNetworkInfo((_DWORD)Context1, v13, v17, (_DWORD)MasterIrp, (__int64)&Length);
        goto LABEL_41;
      case 0x30:
        LOBYTE(v9) = 1;
        NameInfo = FatQueryNameInfo((_DWORD)Context1, v13, v29, v9, (__int64)MasterIrp, (__int64)&Length);
        break;
      default:
        goto LABEL_34;
    }
LABEL_40:
    v7 = NameInfo;
    goto LABEL_41;
  }
  v7 = -1073741811;
  v13 = v34;
LABEL_41:
  v2->IoStatus.Information = CurrentStackLocation->Parameters.Read.Length - Length;
LABEL_42:
  if ( v28 )
    ExReleaseResourceLite(*(PERESOURCE *)(v13 + 8));
  if ( v4 )
    ExReleaseResourceLite(v30 + 5);
  FatCompleteRequest_Real(Context1, v2, v7, v9);
  return v7;
}

```

## disassembly

```asm
0x140039ad8  mov     r11, rsp
0x140039adb  mov     [r11+10h], rdx
0x140039adf  mov     [r11+8], rcx
0x140039ae3  push    rbx
0x140039ae4  push    rsi
0x140039ae5  push    rdi
0x140039ae6  push    r12
0x140039ae8  push    r13
0x140039aea  push    r14
0x140039aec  push    r15
0x140039aee  sub     rsp, 60h
0x140039af2  mov     r13, rdx
0x140039af5  mov     r14, rcx
0x140039af8  xor     esi, esi
0x140039afa  mov     [r11-58h], rsi
0x140039afe  mov     [r11+20h], rsi
0x140039b02  mov     [r11-60h], rsi
0x140039b06  mov     [rsp+98h+var_68], sil
0x140039b0b  mov     r12b, sil
0x140039b0e  mov     [rsp+98h+var_67], sil
0x140039b13  mov     rdx, [rdx+0B8h]
0x140039b1a  mov     [rsp+98h+var_48], rdx
0x140039b1f  mov     rcx, [rdx+30h]
0x140039b23  mov     [rsp+98h+var_50], rcx
0x140039b28  mov     eax, [rdx+8]
0x140039b2b  mov     [r11+18h], eax
0x140039b2f  mov     edi, [rdx+10h]
0x140039b32  mov     r15, [r13+18h]
0x140039b36  lea     r9, [r11-60h]
0x140039b3a  lea     r8, [r11+20h]
0x140039b3e  lea     rdx, [r11-58h]
0x140039b42  call    FatDecodeFileObject
0x140039b47  mov     ebx, esi
0x140039b49  mov     [rsp+98h+var_64], ebx
0x140039b4d  sub     eax, 2
0x140039b50  jz      short loc_140039B7C
0x140039b52  sub     eax, 1
0x140039b55  jz      short loc_140039B7C
0x140039b57  sub     eax, 1
0x140039b5a  jz      short loc_140039B66
0x140039b5c  sub     eax, 2
0x140039b5f  jz      short loc_140039B7C
0x140039b61  cmp     eax, 3
0x140039b64  jz      short loc_140039B7C
0x140039b66  mov     ebx, 0C000000Dh
0x140039b6b  mov     [rsp+98h+var_64], ebx
0x140039b6f  mov     rsi, [rsp+98h+arg_18]
0x140039b77  jmp     loc_140039E25
0x140039b7c  cmp     edi, 30h ; '0'
0x140039b7f  ja      short loc_140039BE1
0x140039b81  mov     rcx, 1000000040200h
0x140039b8b  bt      rcx, rdi
0x140039b8f  jnb     short loc_140039BE1
0x140039b91  xor     r8d, r8d
0x140039b94  mov     rdx, [rsp+98h+var_58]
0x140039b99  mov     rcx, r14
0x140039b9c  call    FatAcquireExclusiveVcb_Real
0x140039ba1  test    al, al
0x140039ba3  jnz     short loc_140039BD9
0x140039ba5  mov     rdx, r13; Context2
0x140039ba8  mov     rcx, r14; Context1
0x140039bab  call    FatFsdPostRequest
0x140039bb0  mov     ebx, eax
0x140039bb2  mov     [rsp+98h+var_64], eax
0x140039bb6  mov     r14, rsi
0x140039bb9  mov     [rsp+98h+arg_0], rsi
0x140039bc1  mov     r13, rsi
0x140039bc4  mov     [rsp+98h+arg_8], rsi
0x140039bcc  mov     rsi, [rsp+98h+arg_18]
0x140039bd4  jmp     loc_140039E38
0x140039bd9  mov     r12b, 1
0x140039bdc  mov     [rsp+98h+var_67], r12b
0x140039be1  mov     rsi, [rsp+98h+arg_18]
0x140039be9  mov     eax, [rsi+0C0h]
0x140039bef  test    al, 4
0x140039bf1  jz      short loc_140039C05
0x140039bf3  mov     rax, [rsi+0B8h]
0x140039bfa  mov     ecx, [rax+0C8h]
0x140039c00  test    cl, 2
0x140039c03  jz      short loc_140039C45
0x140039c05  mov     rdx, rsi
0x140039c08  mov     rcx, r14
0x140039c0b  call    FatAcquireSharedFcb
0x140039c10  test    al, al
0x140039c12  jnz     short loc_140039C40
0x140039c14  mov     rdx, r13; Context2
0x140039c17  mov     rcx, r14; Context1
0x140039c1a  call    FatFsdPostRequest
0x140039c1f  mov     ebx, eax
0x140039c21  mov     [rsp+98h+var_64], eax
0x140039c25  xor     r14d, r14d
0x140039c28  mov     [rsp+98h+arg_0], r14
0x140039c30  xor     r13d, r13d
0x140039c33  mov     [rsp+98h+arg_8], r13
0x140039c3b  jmp     loc_140039E38
0x140039c40  mov     [rsp+98h+var_68], 1
0x140039c45  mov     rdx, rsi
0x140039c48  mov     rcx, r14
0x140039c4b  call    FatVerifyFcb
0x140039c50  cmp     edi, 0Eh
0x140039c53  jg      loc_140039D11
0x140039c59  jz      loc_140039CF8
0x140039c5f  sub     edi, 4
0x140039c62  jz      short loc_140039CDB
0x140039c64  sub     edi, 1
0x140039c67  jz      short loc_140039CC0
0x140039c69  sub     edi, 1
0x140039c6c  jz      short loc_140039CA8
0x140039c6e  sub     edi, 1
0x140039c71  jz      short loc_140039C93
0x140039c73  cmp     edi, 2
0x140039c76  jnz     loc_140039D25
0x140039c7c  lea     rax, [rsp+98h+arg_10]
0x140039c84  mov     [rsp+98h+var_70], rax
0x140039c89  mov     [rsp+98h+var_78], r15
0x140039c8e  jmp     loc_140039E0C
0x140039c93  lea     r9, [rsp+98h+arg_10]
0x140039c9b  mov     r8, r15
0x140039c9e  call    FatQueryEaInfo
0x140039ca3  jmp     loc_140039E25
0x140039ca8  lea     r9, [rsp+98h+arg_10]
0x140039cb0  mov     r8, r15
0x140039cb3  mov     rdx, rsi
0x140039cb6  call    FatQueryInternalInfo
0x140039cbb  jmp     loc_140039E25
0x140039cc0  lea     r9, [rsp+98h+arg_10]
0x140039cc8  mov     r8, r15
0x140039ccb  mov     rdx, rsi
0x140039cce  mov     rcx, r14
0x140039cd1  call    FatQueryStandardInfo
0x140039cd6  jmp     loc_140039E25
0x140039cdb  lea     rax, [rsp+98h+arg_10]
0x140039ce3  mov     [rsp+98h+var_78], rax
0x140039ce8  mov     r9, r15
0x140039ceb  mov     rdx, rsi
0x140039cee  call    FatQueryBasicInfo
0x140039cf3  jmp     loc_140039E25
0x140039cf8  mov     rcx, [rsp+98h+var_50]
0x140039cfd  mov     rax, [rcx+68h]
0x140039d01  mov     [r15], rax
0x140039d04  add     [rsp+98h+arg_10], 0FFFFFFF8h
0x140039d0c  jmp     loc_140039E25
0x140039d11  cmp     edi, 12h
0x140039d14  jz      short loc_140039D85
0x140039d16  cmp     edi, 15h
0x140039d19  jz      short loc_140039D6D
0x140039d1b  cmp     edi, 22h ; '"'
0x140039d1e  jz      short loc_140039D4D
0x140039d20  cmp     edi, 30h ; '0'
0x140039d23  jz      short loc_140039D33
0x140039d25  mov     ebx, 0C000000Dh
0x140039d2a  mov     [rsp+98h+var_64], ebx
0x140039d2e  jmp     loc_140039E25
0x140039d33  lea     rax, [rsp+98h+arg_10]
0x140039d3b  mov     [rsp+98h+var_70], rax
0x140039d40  mov     [rsp+98h+var_78], r15
0x140039d45  mov     r9b, 1
0x140039d48  jmp     loc_140039E0F
0x140039d4d  lea     rax, [rsp+98h+arg_10]
0x140039d55  mov     [rsp+98h+var_78], rax
0x140039d5a  mov     r9, r15
0x140039d5d  mov     rdx, rsi
0x140039d60  mov     rcx, r14
0x140039d63  call    FatQueryNetworkInfo
0x140039d68  jmp     loc_140039E25
0x140039d6d  lea     r9, [rsp+98h+arg_10]
0x140039d75  mov     r8, r15
0x140039d78  mov     rdx, rsi
0x140039d7b  call    FatQueryShortNameInfo
0x140039d80  jmp     loc_140039E1F
0x140039d85  add     [rsp+98h+arg_10], 0FFFFFFF4h
0x140039d8d  lea     rax, [rsp+98h+arg_10]
0x140039d95  mov     [rsp+98h+var_78], rax
0x140039d9a  mov     r9, r15
0x140039d9d  mov     rdx, rsi
0x140039da0  call    FatQueryBasicInfo
0x140039da5  lea     r8, [r15+28h]
0x140039da9  lea     r9, [rsp+98h+arg_10]
0x140039db1  mov     rdx, rsi
0x140039db4  mov     rcx, r14
0x140039db7  call    FatQueryStandardInfo
0x140039dbc  lea     r8, [r15+40h]
0x140039dc0  lea     r9, [rsp+98h+arg_10]
0x140039dc8  mov     rdx, rsi
0x140039dcb  call    FatQueryInternalInfo
0x140039dd0  lea     r8, [r15+48h]
0x140039dd4  lea     r9, [rsp+98h+arg_10]
0x140039ddc  call    FatQueryEaInfo
0x140039de1  mov     rcx, [rsp+98h+var_50]
0x140039de6  mov     rax, [rcx+68h]
0x140039dea  mov     [r15+50h], rax
0x140039dee  add     [rsp+98h+arg_10], 0FFFFFFF8h
0x140039df6  lea     rax, [r15+60h]
0x140039dfa  lea     rcx, [rsp+98h+arg_10]
0x140039e02  mov     [rsp+98h+var_70], rcx
0x140039e07  mov     [rsp+98h+var_78], rax
0x140039e0c  xor     r9d, r9d
0x140039e0f  mov     r8, [rsp+98h+var_60]
0x140039e14  mov     rdx, rsi
0x140039e17  mov     rcx, r14
0x140039e1a  call    FatQueryNameInfo
0x140039e1f  mov     [rsp+98h+var_64], eax
0x140039e23  mov     ebx, eax
0x140039e25  mov     rax, [rsp+98h+var_48]
0x140039e2a  mov     eax, [rax+8]
0x140039e2d  sub     eax, [rsp+98h+arg_10]
0x140039e34  mov     [r13+38h], rax
0x140039e38  cmp     [rsp+98h+var_68], 0
0x140039e3d  jz      short loc_140039E4F
0x140039e3f  mov     rcx, [rsi+8]; Resource
0x140039e43  call    cs:__imp_ExReleaseResourceLite
0x140039e4a  nop     dword ptr [rax+rax+00h]
0x140039e4f  test    r12b, r12b
0x140039e52  jz      short loc_140039E6C
0x140039e54  mov     rcx, [rsp+98h+var_58]
0x140039e59  add     rcx, 208h; Resource
0x140039e60  call    cs:__imp_ExReleaseResourceLite
0x140039e67  nop     dword ptr [rax+rax+00h]
0x140039e6c  mov     r8d, ebx
0x140039e6f  mov     rdx, r13; Irp
0x140039e72  mov     rcx, r14; Entry
0x140039e75  call    FatCompleteRequest_Real
0x140039e7a  mov     eax, ebx
0x140039e7c  add     rsp, 60h
0x140039e80  pop     r15
0x140039e82  pop     r14
0x140039e84  pop     r13
0x140039e86  pop     r12
0x140039e88  pop     rdi
0x140039e89  pop     rsi
0x140039e8a  pop     rbx
0x140039e8b  retn
0x14005e2e9  push    rbx
0x14005e2eb  push    rbp
0x14005e2ec  sub     rsp, 38h
0x14005e2f0  mov     rbp, rdx
0x14005e2f3  movzx   ebx, cl
0x14005e2f6  cmp     byte ptr [rbp+30h], 0
0x14005e2fa  jz      short loc_14005E314
0x14005e2fc  mov     rcx, [rbp+0B8h]
0x14005e303  mov     rcx, [rcx+8]; Resource
0x14005e307  call    cs:__imp_ExReleaseResourceLite
0x14005e30e  nop     dword ptr [rax+rax+00h]
0x14005e313  nop
0x14005e314  cmp     byte ptr [rbp+31h], 0
0x14005e318  jz      short loc_14005E332
0x14005e31a  mov     rcx, [rbp+40h]
0x14005e31e  add     rcx, 208h; Resource
0x14005e325  call    cs:__imp_ExReleaseResourceLite
0x14005e32c  nop     dword ptr [rax+rax+00h]
0x14005e331  nop
0x14005e332  mov     eax, ebx
0x14005e334  test    bl, bl
0x14005e336  jnz     short loc_14005E350
0x14005e338  mov     r8d, [rbp+34h]
0x14005e33c  mov     rdx, [rbp+0A8h]; Irp
0x14005e343  mov     rcx, [rbp+0A0h]; Entry
0x14005e34a  call    FatCompleteRequest_Real
0x14005e34f  nop
0x14005e350  add     rsp, 38h
0x14005e354  pop     rbp
0x14005e355  pop     rbx
0x14005e356  retn
```
