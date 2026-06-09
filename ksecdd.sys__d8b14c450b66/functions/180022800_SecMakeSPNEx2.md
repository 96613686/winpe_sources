# SecMakeSPNEx2

- ea: `0x180022800`
- end: `0x180022b3d`
- name: `SecMakeSPNEx2`
- size: `829`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING ServiceClass, PUNICODE_STRING ServiceName, PUNICODE_STRING InstanceName, USHORT InstancePort, PUNICODE_STRING Referrer, PUNICODE_STRING InTargetInfo, PUNICODE_STRING Spn, PULONG TotalSize, BOOLEAN Allocate, BOOLEAN IsTargetInfoMarshaled)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180022740`
- `0x1800227a0`

## callees

- `0x180010840`
- `0x180010980`
- `0x180010c80`
- `0x180022800`
- `0x1800267b0`

## import_xrefs

- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800228a5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800228a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180022b0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x180022b0e`
- `ntoskrnl!ExAllocatePool2` at `0x18002299b`
- `ntoskrnl!ExAllocatePool2` at `0x18002299b`

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
0x180022800  push    rbp
0x180022802  push    rbx
0x180022803  push    rsi
0x180022804  push    rdi
0x180022805  push    r12
0x180022807  push    r13
0x180022809  push    r14
0x18002280b  push    r15
0x18002280d  lea     rbp, [rsp-7]
0x180022812  sub     rsp, 0E8h
0x180022819  mov     rax, cs:__security_cookie
0x180022820  xor     rax, rsp
0x180022823  mov     [rbp+3Fh+var_48], rax
0x180022827  mov     rax, [rbp+3Fh+Spn]
0x18002282b  xor     edi, edi
0x18002282d  mov     r14, [rbp+3Fh+InTargetInfo]
0x180022831  mov     r15, rdx
0x180022834  mov     rdx, rcx
0x180022837  mov     [rsp+120h+var_C0], rcx
0x18002283c  mov     rcx, [rbp+3Fh+TotalSize]
0x180022843  xorps   xmm0, xmm0
0x180022846  mov     [rsp+120h+var_C8], rcx
0x18002284b  xorps   xmm1, xmm1
0x18002284e  movzx   ebx, word ptr [r15]
0x180022852  mov     r13, r8
0x180022855  movzx   ecx, word ptr [rdx]
0x180022858  add     rbx, 4
0x18002285c  add     rbx, rcx
0x18002285f  mov     [rsp+120h+var_100], r9w
0x180022865  mov     [rsp+120h+var_E0], rax
0x18002286a  mov     esi, edi
0x18002286c  mov     [rsp+120h+P], rdi
0x180022871  mov     r12d, edi
0x180022874  mov     [rsp+120h+var_FC], edi
0x180022878  movups  xmmword ptr [rsp+120h+String.Length], xmm0
0x18002287d  movups  [rsp+120h+var_D8], xmm1
0x180022882  test    r9w, r9w
0x180022886  jz      short loc_1800228C9
0x180022888  lea     rax, [rbp+3Fh+var_60]
0x18002288c  movzx   ecx, r9w; Value
0x180022890  lea     r8, [rsp+120h+String]; String
0x180022895  mov     [rsp+120h+String.Buffer], rax
0x18002289a  lea     edx, [rdi+0Ah]; Base
0x18002289d  mov     dword ptr [rsp+120h+String.Length], 140000h
0x1800228a5  call    cs:__imp_RtlIntegerToUnicodeString
0x1800228ac  nop     dword ptr [rax+rax+00h]
0x1800228b1  mov     edi, eax
0x1800228b3  test    eax, eax
0x1800228b5  js      loc_180022B1A
0x1800228bb  movzx   eax, [rsp+120h+String.Length]
0x1800228c0  add     rax, 4
0x1800228c4  add     rbx, rax
0x1800228c7  xor     edi, edi
0x1800228c9  test    r13, r13
0x1800228cc  jz      short loc_1800228E1
0x1800228ce  movzx   ecx, word ptr [r13+0]
0x1800228d3  movzx   eax, word ptr [r15]
0x1800228d7  add     rax, rbx
0x1800228da  lea     rbx, [rcx+8]
0x1800228de  add     rbx, rax
0x1800228e1  test    r14, r14
0x1800228e4  jz      short loc_180022965
0x1800228e6  cmp     [rbp+3Fh+IsTargetInfoMarshaled], dil
0x1800228ed  jz      short loc_180022900
0x1800228ef  movzx   r12d, word ptr [r14]
0x1800228f3  add     rbx, 2
0x1800228f7  mov     rsi, [r14+8]
0x1800228fb  add     rbx, r12
0x1800228fe  jmp     short loc_180022965
0x180022900  mov     rdi, [r14+8]
0x180022904  xor     eax, eax
0x180022906  test    rdi, rdi
0x180022909  jz      short loc_180022963
0x18002290b  movzx   ecx, word ptr [r14+2]
0x180022910  shr     rcx, 1
0x180022913  cmp     ax, [rdi+rcx*2-2]
0x180022918  jnz     short loc_180022963
0x18002291a  xor     edx, edx; Val
0x18002291c  lea     r8d, [rax+48h]; Size
0x180022920  lea     rcx, [rbp+3Fh+var_B0]; void *
0x180022924  call    memset
0x180022929  lea     r8, [rsp+120h+var_FC]
0x18002292e  mov     [rbp+3Fh+var_B0], rdi
0x180022932  lea     rdx, [rsp+120h+P]
0x180022937  mov     [rbp+3Fh+var_78], 11h
0x18002293e  lea     rcx, [rbp+3Fh+var_B0]
0x180022942  call    CredMarshalTargetInfo
0x180022947  mov     rsi, [rsp+120h+P]
0x18002294c  mov     edi, eax
0x18002294e  test    eax, eax
0x180022950  js      loc_180022AFB
0x180022956  mov     r12d, [rsp+120h+var_FC]
0x18002295b  lea     rax, [r12+2]
0x180022960  add     rbx, rax
0x180022963  xor     edi, edi
0x180022965  cmp     rbx, 0FFFFh
0x18002296c  jbe     short loc_180022978
0x18002296e  mov     edi, 0C000000Dh
0x180022973  jmp     loc_180022AFB
0x180022978  mov     rax, [rsp+120h+var_C8]
0x18002297d  test    rax, rax
0x180022980  jz      short loc_180022984
0x180022982  mov     [rax], ebx
0x180022984  cmp     [rbp+3Fh+Allocate], dil
0x18002298b  jz      short loc_1800229C5
0x18002298d  mov     r8d, 6365734Bh
0x180022993  mov     rdx, rbx
0x180022996  mov     ecx, 100h
0x18002299b  call    cs:__imp_ExAllocatePool2
0x1800229a2  nop     dword ptr [rax+rax+00h]
0x1800229a7  mov     qword ptr [rsp+120h+var_D8+8], rax
0x1800229ac  mov     r14, rax
0x1800229af  test    rax, rax
0x1800229b2  jz      short loc_1800229BB
0x1800229b4  mov     word ptr [rsp+120h+var_D8+2], bx
0x1800229b9  jmp     short loc_1800229E9
0x1800229bb  mov     edi, 0C0000017h
0x1800229c0  jmp     loc_180022AFB
0x1800229c5  mov     rax, [rsp+120h+var_E0]
0x1800229ca  test    rax, rax
0x1800229cd  jz      loc_180022AF6
0x1800229d3  cmp     [rax+2], bx
0x1800229d7  jb      loc_180022AF6
0x1800229dd  movups  xmm0, xmmword ptr [rax]
0x1800229e0  mov     r14, [rax+8]
0x1800229e4  movups  [rsp+120h+var_D8], xmm0
0x1800229e9  mov     rbx, [rsp+120h+var_C0]
0x1800229ee  mov     rcx, r14; void *
0x1800229f1  movzx   r8d, word ptr [rbx]; Size
0x1800229f5  mov     rdx, [rbx+8]; Src
0x1800229f9  call    memmove
0x1800229fe  movzx   eax, word ptr [rbx]
0x180022a01  shr     rax, 1
0x180022a04  mov     word ptr [r14+rax*2], 2Fh ; '/'
0x180022a0b  lea     rbx, [rax+1]
0x180022a0f  lea     rbx, [r14+rbx*2]
0x180022a13  test    r13, r13
0x180022a16  jz      short loc_180022A6D
0x180022a18  movzx   r8d, word ptr [r13+0]; Size
0x180022a1d  mov     rcx, rbx; void *
0x180022a20  mov     rdx, [r13+8]; Src
0x180022a24  call    memmove
0x180022a29  movzx   eax, word ptr [r13+0]
0x180022a2e  shr     rax, 1
0x180022a31  lea     rbx, [rbx+rax*2]
0x180022a35  cmp     [rsp+120h+var_100], di
0x180022a3a  jz      short loc_180022A64
0x180022a3c  mov     word ptr [rbx], 3Ah ; ':'
0x180022a41  add     rbx, 2
0x180022a45  movzx   r8d, [rsp+120h+String.Length]; Size
0x180022a4b  mov     rcx, rbx; void *
0x180022a4e  mov     rdx, [rsp+120h+String.Buffer]; Src
0x180022a53  call    memmove
0x180022a58  movzx   eax, [rsp+120h+String.Length]
0x180022a5d  shr     rax, 1
0x180022a60  lea     rbx, [rbx+rax*2]
0x180022a64  mov     word ptr [rbx], 2Fh ; '/'
0x180022a69  add     rbx, 2
0x180022a6d  movzx   r8d, word ptr [r15]; Size
0x180022a71  mov     rcx, rbx; void *
0x180022a74  mov     rdx, [r15+8]; Src
0x180022a78  call    memmove
0x180022a7d  movzx   eax, word ptr [r15]
0x180022a81  shr     rax, 1
0x180022a84  lea     rdi, [rbx+rax*2]
0x180022a88  test    r13, r13
0x180022a8b  jz      short loc_180022AB1
0x180022a8d  mov     word ptr [rdi], 40h ; '@'
0x180022a92  lea     rbx, [rdi+2]
0x180022a96  movzx   r8d, word ptr [r15]; Size
0x180022a9a  mov     rcx, rbx; void *
0x180022a9d  mov     rdx, [r15+8]; Src
0x180022aa1  call    memmove
0x180022aa6  movzx   eax, word ptr [r15]
0x180022aaa  shr     rax, 1
0x180022aad  lea     rdi, [rbx+rax*2]
0x180022ab1  test    rsi, rsi
0x180022ab4  jz      short loc_180022ACE
0x180022ab6  mov     r8d, r12d; Size
0x180022ab9  mov     rdx, rsi; Src
0x180022abc  mov     rcx, rdi; void *
0x180022abf  mov     ebx, r12d
0x180022ac2  call    memmove
0x180022ac7  shr     rbx, 1
0x180022aca  lea     rdi, [rdi+rbx*2]
0x180022ace  mov     rax, rdi
0x180022ad1  sub     rax, r14
0x180022ad4  sar     rax, 1
0x180022ad7  add     ax, ax
0x180022ada  mov     word ptr [rsp+120h+var_D8], ax
0x180022adf  xor     eax, eax
0x180022ae1  movups  xmm0, [rsp+120h+var_D8]
0x180022ae6  mov     [rdi], ax
0x180022ae9  xor     edi, edi
0x180022aeb  mov     rax, [rsp+120h+var_E0]
0x180022af0  movdqu  xmmword ptr [rax], xmm0
0x180022af4  jmp     short loc_180022AFB
0x180022af6  mov     edi, 80000005h
0x180022afb  test    rsi, rsi
0x180022afe  jz      short loc_180022B1A
0x180022b00  cmp     [rbp+3Fh+IsTargetInfoMarshaled], 0
0x180022b07  jnz     short loc_180022B1A
0x180022b09  xor     edx, edx; Tag
0x180022b0b  mov     rcx, rsi; P
0x180022b0e  call    cs:__imp_ExFreePoolWithTag
0x180022b15  nop     dword ptr [rax+rax+00h]
0x180022b1a  mov     eax, edi
0x180022b1c  mov     rcx, [rbp+3Fh+var_48]
0x180022b20  xor     rcx, rsp; StackCookie
0x180022b23  call    __security_check_cookie
0x180022b28  add     rsp, 0E8h
0x180022b2f  pop     r15
0x180022b31  pop     r14
0x180022b33  pop     r13
0x180022b35  pop     r12
0x180022b37  pop     rdi
0x180022b38  pop     rsi
0x180022b39  pop     rbx
0x180022b3a  pop     rbp
0x180022b3b  retn
```
