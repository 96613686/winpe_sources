# SecMakeSPNEx2

- ea: `0x180022850`
- end: `0x180022b8d`
- name: `SecMakeSPNEx2`
- size: `829`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING InTargetInfo, PUNICODE_STRING Spn, PULONG TotalSize, BOOLEAN Allocate, BOOLEAN IsTargetInfoMarshaled)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180022790`
- `0x1800227f0`

## callees

- `0x1800108a0`
- `0x180010a00`
- `0x180010d00`
- `0x180022850`
- `0x180026800`

## import_xrefs

- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800228f5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800228f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180022b5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180022b5e`
- `ntoskrnl!ExAllocatePool2` at `0x1800229eb`
- `ntoskrnl!ExAllocatePool2` at `0x1800229eb`

## pseudocode

```c
NTSTATUS __stdcall SecMakeSPNEx2(
        PUNICODE_STRING ServiceClass,
        PUNICODE_STRING ServiceName,
        PUNICODE_STRING InstanceName,
        USHORT InstancePort,
        PUNICODE_STRING Referrer,
        PUNICODE_STRING InTargetInfo,
        PUNICODE_STRING Spn,
        PULONG TotalSize,
        BOOLEAN Allocate,
        BOOLEAN IsTargetInfoMarshaled)
{
  unsigned __int64 v12; // rbx
  void *Buffer; // rsi
  __int64 Length; // r12
  int v15; // edi
  wchar_t *v16; // rdi
  int v17; // eax
  wchar_t *v18; // r14
  unsigned __int16 *p_Length; // rbx
  unsigned __int64 v20; // rax
  wchar_t *v21; // rbx
  char *v22; // rbx
  char *v23; // rbx
  char *v24; // rdi
  UNICODE_STRING v25; // xmm0
  unsigned int v28; // [rsp+24h] [rbp-BDh] BYREF
  UNICODE_STRING String; // [rsp+28h] [rbp-B9h] BYREF
  PVOID P; // [rsp+38h] [rbp-A9h] BYREF
  PUNICODE_STRING v31; // [rsp+40h] [rbp-A1h]
  UNICODE_STRING v32; // [rsp+48h] [rbp-99h]
  PULONG v33; // [rsp+58h] [rbp-89h]
  PUNICODE_STRING v34; // [rsp+60h] [rbp-81h]
  _QWORD v35[10]; // [rsp+70h] [rbp-71h] BYREF
  char v36; // [rsp+C0h] [rbp-21h] BYREF

  v34 = ServiceClass;
  v33 = TotalSize;
  v12 = ServiceClass->Length + ServiceName->Length + 4LL;
  v31 = Spn;
  Buffer = 0;
  P = 0;
  LODWORD(Length) = 0;
  v28 = 0;
  String = 0;
  v32 = 0;
  if ( InstancePort )
  {
    String.Buffer = (wchar_t *)&v36;
    *(_DWORD *)&String.Length = 1310720;
    v15 = RtlIntegerToUnicodeString(InstancePort, 0xAu, &String);
    if ( v15 < 0 )
      return v15;
    v12 += String.Length + 4LL;
  }
  if ( InstanceName )
    v12 += ServiceName->Length + InstanceName->Length + 8LL;
  if ( InTargetInfo )
  {
    if ( IsTargetInfoMarshaled )
    {
      Length = InTargetInfo->Length;
      Buffer = InTargetInfo->Buffer;
      v12 += Length + 2;
    }
    else
    {
      v16 = InTargetInfo->Buffer;
      if ( v16 && !v16[((unsigned __int64)InTargetInfo->MaximumLength >> 1) - 1] )
      {
        memset(v35, 0, 0x48u);
        v35[0] = v16;
        LODWORD(v35[7]) = 17;
        v17 = CredMarshalTargetInfo(v35, &P, &v28);
        Buffer = P;
        v15 = v17;
        if ( v17 < 0 )
          goto LABEL_34;
        LODWORD(Length) = v28;
        v12 += v28 + 2LL;
      }
    }
  }
  if ( v12 <= 0xFFFF )
  {
    if ( v33 )
      *v33 = v12;
    if ( Allocate )
    {
      v32.Buffer = (wchar_t *)ExAllocatePool2(256, v12, 1667593035);
      v18 = v32.Buffer;
      if ( !v32.Buffer )
      {
        v15 = -1073741801;
        goto LABEL_34;
      }
      v32.MaximumLength = v12;
    }
    else
    {
      if ( !v31 || v31->MaximumLength < (unsigned __int16)v12 )
      {
        v15 = -2147483643;
        goto LABEL_34;
      }
      v18 = v31->Buffer;
      v32 = *v31;
    }
    p_Length = &v34->Length;
    memmove(v18, v34->Buffer, v34->Length);
    v20 = (unsigned __int64)*p_Length >> 1;
    v18[v20] = 47;
    v21 = &v18[v20 + 1];
    if ( InstanceName )
    {
      memmove(&v18[v20 + 1], InstanceName->Buffer, InstanceName->Length);
      v22 = (char *)&v21[(unsigned __int64)InstanceName->Length >> 1];
      if ( InstancePort )
      {
        *(_WORD *)v22 = 58;
        v23 = v22 + 2;
        memmove(v23, String.Buffer, String.Length);
        v22 = &v23[2 * ((unsigned __int64)String.Length >> 1)];
      }
      *(_WORD *)v22 = 47;
      v21 = (wchar_t *)(v22 + 2);
    }
    memmove(v21, ServiceName->Buffer, ServiceName->Length);
    v24 = (char *)&v21[(unsigned __int64)ServiceName->Length >> 1];
    if ( InstanceName )
    {
      *(_WORD *)v24 = 64;
      memmove(v24 + 2, ServiceName->Buffer, ServiceName->Length);
      v24 += 2 * ((unsigned __int64)ServiceName->Length >> 1) + 2;
    }
    if ( Buffer )
    {
      memmove(v24, Buffer, (unsigned int)Length);
      v24 += 2 * ((unsigned __int64)(unsigned int)Length >> 1);
    }
    v32.Length = 2 * ((v24 - (char *)v18) >> 1);
    v25 = v32;
    *(_WORD *)v24 = 0;
    v15 = 0;
    *v31 = v25;
    goto LABEL_34;
  }
  v15 = -1073741811;
LABEL_34:
  if ( Buffer && !IsTargetInfoMarshaled )
    ExFreePoolWithTag(Buffer, 0);
  return v15;
}

```

## disassembly

```asm
0x180022850  push    rbp
0x180022852  push    rbx
0x180022853  push    rsi
0x180022854  push    rdi
0x180022855  push    r12
0x180022857  push    r13
0x180022859  push    r14
0x18002285b  push    r15
0x18002285d  lea     rbp, [rsp-7]
0x180022862  sub     rsp, 0E8h
0x180022869  mov     rax, cs:__security_cookie
0x180022870  xor     rax, rsp
0x180022873  mov     [rbp+3Fh+var_48], rax
0x180022877  mov     rax, [rbp+3Fh+Spn]
0x18002287b  xor     edi, edi
0x18002287d  mov     r14, [rbp+3Fh+InTargetInfo]
0x180022881  mov     r15, rdx
0x180022884  mov     rdx, rcx
0x180022887  mov     [rsp+120h+var_C0], rcx
0x18002288c  mov     rcx, [rbp+3Fh+TotalSize]
0x180022893  xorps   xmm0, xmm0
0x180022896  mov     [rsp+120h+var_C8], rcx
0x18002289b  xorps   xmm1, xmm1
0x18002289e  movzx   ebx, word ptr [r15]
0x1800228a2  mov     r13, r8
0x1800228a5  movzx   ecx, word ptr [rdx]
0x1800228a8  add     rbx, 4
0x1800228ac  add     rbx, rcx
0x1800228af  mov     [rsp+120h+var_100], r9w
0x1800228b5  mov     [rsp+120h+var_E0], rax
0x1800228ba  mov     esi, edi
0x1800228bc  mov     [rsp+120h+P], rdi
0x1800228c1  mov     r12d, edi
0x1800228c4  mov     [rsp+120h+var_FC], edi
0x1800228c8  movups  xmmword ptr [rsp+120h+String.Length], xmm0
0x1800228cd  movups  [rsp+120h+var_D8], xmm1
0x1800228d2  test    r9w, r9w
0x1800228d6  jz      short loc_180022919
0x1800228d8  lea     rax, [rbp+3Fh+var_60]
0x1800228dc  movzx   ecx, r9w; Value
0x1800228e0  lea     r8, [rsp+120h+String]; String
0x1800228e5  mov     [rsp+120h+String.Buffer], rax
0x1800228ea  lea     edx, [rdi+0Ah]; Base
0x1800228ed  mov     dword ptr [rsp+120h+String.Length], 140000h
0x1800228f5  call    cs:__imp_RtlIntegerToUnicodeString
0x1800228fc  nop     dword ptr [rax+rax+00h]
0x180022901  mov     edi, eax
0x180022903  test    eax, eax
0x180022905  js      loc_180022B6A
0x18002290b  movzx   eax, [rsp+120h+String.Length]
0x180022910  add     rax, 4
0x180022914  add     rbx, rax
0x180022917  xor     edi, edi
0x180022919  test    r13, r13
0x18002291c  jz      short loc_180022931
0x18002291e  movzx   ecx, word ptr [r13+0]
0x180022923  movzx   eax, word ptr [r15]
0x180022927  add     rax, rbx
0x18002292a  lea     rbx, [rcx+8]
0x18002292e  add     rbx, rax
0x180022931  test    r14, r14
0x180022934  jz      short loc_1800229B5
0x180022936  cmp     [rbp+3Fh+IsTargetInfoMarshaled], dil
0x18002293d  jz      short loc_180022950
0x18002293f  movzx   r12d, word ptr [r14]
0x180022943  add     rbx, 2
0x180022947  mov     rsi, [r14+8]
0x18002294b  add     rbx, r12
0x18002294e  jmp     short loc_1800229B5
0x180022950  mov     rdi, [r14+8]
0x180022954  xor     eax, eax
0x180022956  test    rdi, rdi
0x180022959  jz      short loc_1800229B3
0x18002295b  movzx   ecx, word ptr [r14+2]
0x180022960  shr     rcx, 1
0x180022963  cmp     ax, [rdi+rcx*2-2]
0x180022968  jnz     short loc_1800229B3
0x18002296a  xor     edx, edx; Val
0x18002296c  lea     r8d, [rax+48h]; Size
0x180022970  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180022974  call    memset
0x180022979  lea     r8, [rsp+120h+var_FC]
0x18002297e  mov     [rbp+3Fh+var_B0], rdi
0x180022982  lea     rdx, [rsp+120h+P]
0x180022987  mov     [rbp+3Fh+var_78], 11h
0x18002298e  lea     rcx, [rbp+3Fh+var_B0]
0x180022992  call    CredMarshalTargetInfo
0x180022997  mov     rsi, [rsp+120h+P]
0x18002299c  mov     edi, eax
0x18002299e  test    eax, eax
0x1800229a0  js      loc_180022B4B
0x1800229a6  mov     r12d, [rsp+120h+var_FC]
0x1800229ab  lea     rax, [r12+2]
0x1800229b0  add     rbx, rax
0x1800229b3  xor     edi, edi
0x1800229b5  cmp     rbx, 0FFFFh
0x1800229bc  jbe     short loc_1800229C8
0x1800229be  mov     edi, 0C000000Dh
0x1800229c3  jmp     loc_180022B4B
0x1800229c8  mov     rax, [rsp+120h+var_C8]
0x1800229cd  test    rax, rax
0x1800229d0  jz      short loc_1800229D4
0x1800229d2  mov     [rax], ebx
0x1800229d4  cmp     [rbp+3Fh+Allocate], dil
0x1800229db  jz      short loc_180022A15
0x1800229dd  mov     r8d, 6365734Bh
0x1800229e3  mov     rdx, rbx
0x1800229e6  mov     ecx, 100h
0x1800229eb  call    cs:__imp_ExAllocatePool2
0x1800229f2  nop     dword ptr [rax+rax+00h]
0x1800229f7  mov     qword ptr [rsp+120h+var_D8+8], rax
0x1800229fc  mov     r14, rax
0x1800229ff  test    rax, rax
0x180022a02  jz      short loc_180022A0B
0x180022a04  mov     word ptr [rsp+120h+var_D8+2], bx
0x180022a09  jmp     short loc_180022A39
0x180022a0b  mov     edi, 0C0000017h
0x180022a10  jmp     loc_180022B4B
0x180022a15  mov     rax, [rsp+120h+var_E0]
0x180022a1a  test    rax, rax
0x180022a1d  jz      loc_180022B46
0x180022a23  cmp     [rax+2], bx
0x180022a27  jb      loc_180022B46
0x180022a2d  movups  xmm0, xmmword ptr [rax]
0x180022a30  mov     r14, [rax+8]
0x180022a34  movups  [rsp+120h+var_D8], xmm0
0x180022a39  mov     rbx, [rsp+120h+var_C0]
0x180022a3e  mov     rcx, r14; void *
0x180022a41  movzx   r8d, word ptr [rbx]; Size
0x180022a45  mov     rdx, [rbx+8]; Src
0x180022a49  call    memmove
0x180022a4e  movzx   eax, word ptr [rbx]
0x180022a51  shr     rax, 1
0x180022a54  mov     word ptr [r14+rax*2], 2Fh ; '/'
0x180022a5b  lea     rbx, [rax+1]
0x180022a5f  lea     rbx, [r14+rbx*2]
0x180022a63  test    r13, r13
0x180022a66  jz      short loc_180022ABD
0x180022a68  movzx   r8d, word ptr [r13+0]; Size
0x180022a6d  mov     rcx, rbx; void *
0x180022a70  mov     rdx, [r13+8]; Src
0x180022a74  call    memmove
0x180022a79  movzx   eax, word ptr [r13+0]
0x180022a7e  shr     rax, 1
0x180022a81  lea     rbx, [rbx+rax*2]
0x180022a85  cmp     [rsp+120h+var_100], di
0x180022a8a  jz      short loc_180022AB4
0x180022a8c  mov     word ptr [rbx], 3Ah ; ':'
0x180022a91  add     rbx, 2
0x180022a95  movzx   r8d, [rsp+120h+String.Length]; Size
0x180022a9b  mov     rcx, rbx; void *
0x180022a9e  mov     rdx, [rsp+120h+String.Buffer]; Src
0x180022aa3  call    memmove
0x180022aa8  movzx   eax, [rsp+120h+String.Length]
0x180022aad  shr     rax, 1
0x180022ab0  lea     rbx, [rbx+rax*2]
0x180022ab4  mov     word ptr [rbx], 2Fh ; '/'
0x180022ab9  add     rbx, 2
0x180022abd  movzx   r8d, word ptr [r15]; Size
0x180022ac1  mov     rcx, rbx; void *
0x180022ac4  mov     rdx, [r15+8]; Src
0x180022ac8  call    memmove
0x180022acd  movzx   eax, word ptr [r15]
0x180022ad1  shr     rax, 1
0x180022ad4  lea     rdi, [rbx+rax*2]
0x180022ad8  test    r13, r13
0x180022adb  jz      short loc_180022B01
0x180022add  mov     word ptr [rdi], 40h ; '@'
0x180022ae2  lea     rbx, [rdi+2]
0x180022ae6  movzx   r8d, word ptr [r15]; Size
0x180022aea  mov     rcx, rbx; void *
0x180022aed  mov     rdx, [r15+8]; Src
0x180022af1  call    memmove
0x180022af6  movzx   eax, word ptr [r15]
0x180022afa  shr     rax, 1
0x180022afd  lea     rdi, [rbx+rax*2]
0x180022b01  test    rsi, rsi
0x180022b04  jz      short loc_180022B1E
0x180022b06  mov     r8d, r12d; Size
0x180022b09  mov     rdx, rsi; Src
0x180022b0c  mov     rcx, rdi; void *
0x180022b0f  mov     ebx, r12d
0x180022b12  call    memmove
0x180022b17  shr     rbx, 1
0x180022b1a  lea     rdi, [rdi+rbx*2]
0x180022b1e  mov     rax, rdi
0x180022b21  sub     rax, r14
0x180022b24  sar     rax, 1
0x180022b27  add     ax, ax
0x180022b2a  mov     word ptr [rsp+120h+var_D8], ax
0x180022b2f  xor     eax, eax
0x180022b31  movups  xmm0, [rsp+120h+var_D8]
0x180022b36  mov     [rdi], ax
0x180022b39  xor     edi, edi
0x180022b3b  mov     rax, [rsp+120h+var_E0]
0x180022b40  movdqu  xmmword ptr [rax], xmm0
0x180022b44  jmp     short loc_180022B4B
0x180022b46  mov     edi, 80000005h
0x180022b4b  test    rsi, rsi
0x180022b4e  jz      short loc_180022B6A
0x180022b50  cmp     [rbp+3Fh+IsTargetInfoMarshaled], 0
0x180022b57  jnz     short loc_180022B6A
0x180022b59  xor     edx, edx; Tag
0x180022b5b  mov     rcx, rsi; P
0x180022b5e  call    cs:__imp_ExFreePoolWithTag
0x180022b65  nop     dword ptr [rax+rax+00h]
0x180022b6a  mov     eax, edi
0x180022b6c  mov     rcx, [rbp+3Fh+var_48]
0x180022b70  xor     rcx, rsp; StackCookie
0x180022b73  call    __security_check_cookie
0x180022b78  add     rsp, 0E8h
0x180022b7f  pop     r15
0x180022b81  pop     r14
0x180022b83  pop     r13
0x180022b85  pop     r12
0x180022b87  pop     rdi
0x180022b88  pop     rsi
0x180022b89  pop     rbx
0x180022b8a  pop     rbp
0x180022b8b  retn
```
