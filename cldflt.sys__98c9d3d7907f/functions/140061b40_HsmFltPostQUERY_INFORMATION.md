# HsmFltPostQUERY_INFORMATION

- ea: `0x140061b40`
- end: `0x140061f2b`
- name: `HsmFltPostQUERY_INFORMATION`
- size: `1003`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140001590`
- `0x140003c50`
- `0x140006f40`
- `0x140007360`
- `0x140007d94`
- `0x140009364`
- `0x14001e280`
- `0x14001e580`
- `0x140042e28`
- `0x140061b40`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140061cb7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140061cb7`
- `FLTMGR!FltGetStreamContext` at `0x140061b86`
- `FLTMGR!FltGetStreamContext` at `0x140061b86`
- `FLTMGR!FltDeleteContext` at `0x140061ed4`
- `FLTMGR!FltDeleteContext` at `0x140061ed4`
- `FLTMGR!FltGetRequestorProcess` at `0x140061bda`
- `FLTMGR!FltGetRequestorProcess` at `0x140061d29`
- `FLTMGR!FltGetRequestorProcess` at `0x140061bda`
- `FLTMGR!FltGetRequestorProcess` at `0x140061d29`
- `FLTMGR!FltReleaseContext` at `0x140061cec`
- `FLTMGR!FltReleaseContext` at `0x140061d4a`
- `FLTMGR!FltReleaseContext` at `0x140061cec`
- `FLTMGR!FltReleaseContext` at `0x140061d4a`

## pseudocode

```c
__int64 __fastcall HsmFltPostQUERY_INFORMATION(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3)
{
  NTSTATUS Status; // eax
  struct _FLT_INSTANCE *v6; // r14
  _DWORD *v7; // rbx
  PEPROCESS v9; // rax
  __int64 v10; // r9
  ULONG Options; // r14d
  unsigned __int8 v12; // di
  unsigned __int8 PlaceholderCompatMode; // al
  unsigned int *QuadPart; // rdi
  DWORD Information; // r13d
  DWORD v16; // r14d
  _DWORD *v17; // r12
  __int64 v18; // rax
  unsigned int *v19; // r15
  __int64 v20; // r9
  __int64 v21; // r8
  PFLT_CONTEXT v22; // rcx
  PEPROCESS RequestorProcess; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // r9
  LARGE_INTEGER ByteOffset; // r10
  int v26; // r8d
  int v27; // edx
  unsigned int v28; // eax
  LARGE_INTEGER v29; // rax
  size_t v30; // r8
  PFLT_CONTEXT Context; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING String2; // [rsp+28h] [rbp-50h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-40h] BYREF
  LARGE_INTEGER v34; // [rsp+80h] [rbp+8h]

  Status = CallbackData->IoStatus.Status;
  if ( Status < 0 )
  {
    v7 = 0;
    if ( Status != -2147483643 )
      goto LABEL_17;
  }
  v6 = *(struct _FLT_INSTANCE **)(a2 + 24);
  Context = 0;
  FltGetStreamContext(v6, *(PFILE_OBJECT *)(a2 + 32), &Context);
  v7 = Context;
  if ( Context )
  {
    if ( (*((_DWORD *)Context + 7) & 1) != 0 )
    {
      if ( *(struct _FLT_INSTANCE **)(*(_QWORD *)(*((_QWORD *)Context + 2) + 16LL) + 32LL) != v6 )
      {
        v22 = Context;
LABEL_23:
        FltReleaseContext(v22);
        v7 = 0;
        Context = 0;
        goto LABEL_5;
      }
      RequestorProcess = FltGetRequestorProcess(CallbackData);
      if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(RequestorProcess) )
      {
        v7 = Context;
        goto LABEL_5;
      }
    }
    else
    {
      FltDeleteContext(Context);
    }
    v22 = Context;
    goto LABEL_23;
  }
LABEL_5:
  *(_QWORD *)&String2.Length = v7;
  if ( !v7 )
    return 0;
  v9 = FltGetRequestorProcess(CallbackData);
  if ( !(unsigned __int8)HsmOsIsPassThroughModeEnabled(v9) )
  {
    LOBYTE(v10) = 1;
    HsmpTracePostCallbackEnter(CallbackData, a3, 0, v10);
    Options = CallbackData->Iopb->Parameters.Create.Options;
    v12 = BYTE1(v7[7]) & 1;
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode((__int64)CallbackData);
    if ( (unsigned __int8)HsmOsDisguisePlaceholder(PlaceholderCompatMode, v12) )
    {
      Iopb = CallbackData->Iopb;
      ByteOffset = Iopb->Parameters.Read.ByteOffset;
      v26 = -1;
      if ( Options == 18 )
      {
LABEL_25:
        v27 = 32;
      }
      else
      {
        v27 = -1;
        switch ( Options )
        {
          case 4u:
            goto LABEL_25;
          case 0x22u:
            v27 = 48;
            break;
          case 0x23u:
            v27 = 0;
            v26 = 4;
            break;
          case 0x44u:
          case 0x46u:
          case 0x4Du:
            v27 = 56;
            v26 = 60;
            break;
          default:
            break;
        }
      }
      if ( v27 >= 0
        && (CallbackData->IoStatus.Status != -2147483643 || Iopb->Parameters.Read.Length >= (unsigned __int64)(v27 + 4LL)) )
      {
        v28 = *(_DWORD *)(v27 + ByteOffset.QuadPart) & 0xFFFFE9FF;
        if ( !v28 )
          v28 = 128;
        *(_DWORD *)(v27 + ByteOffset.QuadPart) = v28;
      }
      if ( v26 >= 0
        && (CallbackData->IoStatus.Status != -2147483643
         || CallbackData->Iopb->Parameters.Read.Length >= (unsigned __int64)(v26 + 4LL)) )
      {
        *(_DWORD *)(v26 + ByteOffset.QuadPart) = 0;
      }
    }
    if ( Options == 22 )
    {
      *(_QWORD *)&String1.Length = 5505106;
      String1.Buffer = L":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0}.";
      v34 = CallbackData->Iopb->Parameters.Read.ByteOffset;
      QuadPart = (unsigned int *)v34.QuadPart;
      Information = CallbackData->IoStatus.Information;
      v16 = Information;
      v17 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( !QuadPart )
          {
            v29 = v34;
            goto LABEL_41;
          }
          String2 = 0;
          v18 = *QuadPart;
          if ( (_DWORD)v18 && v18 + 32 <= (unsigned __int64)v16 )
            v19 = (unsigned int *)((char *)QuadPart + *QuadPart);
          else
            v19 = 0;
          String2.Buffer = (PWSTR)(QuadPart + 6);
          String2.Length = *((_WORD *)QuadPart + 2);
          String2.MaximumLength = *((_WORD *)QuadPart + 2);
          if ( RtlPrefixUnicodeString(&String1, &String2, 1u) )
            break;
          v17 = QuadPart;
          QuadPart = v19;
        }
        if ( !v19 )
          break;
        v30 = v16 + v34.LowPart - (_DWORD)v19;
        v16 -= *QuadPart;
        memmove(QuadPart, v19, v30);
      }
      v29 = v34;
      if ( v17 )
      {
        *v17 = 0;
        v16 = (_DWORD)v17 + v17[1] - v34.LowPart + 24;
      }
      else
      {
        v16 = (_DWORD)QuadPart - v34.LowPart;
      }
LABEL_41:
      if ( v16 < Information )
      {
        memset((void *)(v16 + v29.QuadPart), 0, Information - v16);
        CallbackData->IoStatus.Information = v16;
      }
    }
  }
LABEL_17:
  if ( v7 )
  {
    FltReleaseContext(v7);
    LOBYTE(v20) = 1;
    HsmpTracePostCallbackExit(0, CallbackData, v21, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x140061b40  mov     [rsp+arg_8], rbx
0x140061b45  mov     [rsp+arg_10], rsi
0x140061b4a  mov     [rsp+arg_0], rcx
0x140061b4f  push    rdi
0x140061b50  push    r12
0x140061b52  push    r13
0x140061b54  push    r14
0x140061b56  push    r15
0x140061b58  sub     rsp, 50h
0x140061b5c  mov     rdi, r8
0x140061b5f  mov     rsi, rcx
0x140061b62  mov     eax, [rcx+18h]
0x140061b65  test    eax, eax
0x140061b67  js      loc_140061CD3
0x140061b6d  mov     r14, [rdx+18h]
0x140061b71  mov     [rsp+78h+Context], 0
0x140061b7a  lea     r8, [rsp+78h+Context]; Context
0x140061b7f  mov     rdx, [rdx+20h]; FileObject
0x140061b83  mov     rcx, r14; Instance
0x140061b86  call    cs:__imp_FltGetStreamContext
0x140061b8d  nop     dword ptr [rax+rax+00h]
0x140061b92  mov     rbx, [rsp+78h+Context]
0x140061b97  test    rbx, rbx
0x140061b9a  jz      short loc_140061BB0
0x140061b9c  mov     eax, [rbx+1Ch]
0x140061b9f  test    al, 1
0x140061ba1  jz      loc_140061EC8
0x140061ba7  test    rbx, rbx
0x140061baa  jnz     loc_140061D0A
0x140061bb0  mov     qword ptr [rsp+78h+String2.Length], rbx
0x140061bb5  test    rbx, rbx
0x140061bb8  jnz     short loc_140061BD7
0x140061bba  xor     eax, eax
0x140061bbc  lea     r11, [rsp+78h+var_28]
0x140061bc1  mov     rbx, [r11+38h]
0x140061bc5  mov     rsi, [r11+40h]
0x140061bc9  mov     rsp, r11
0x140061bcc  pop     r15
0x140061bce  pop     r14
0x140061bd0  pop     r13
0x140061bd2  pop     r12
0x140061bd4  pop     rdi
0x140061bd5  retn
0x140061bd7  mov     rcx, rsi; CallbackData
0x140061bda  call    cs:__imp_FltGetRequestorProcess
0x140061be1  nop     dword ptr [rax+rax+00h]
0x140061be6  mov     rcx, rax
0x140061be9  call    HsmOsIsPassThroughModeEnabled
0x140061bee  test    al, al
0x140061bf0  jnz     loc_140061CE0
0x140061bf6  mov     r9b, 1
0x140061bf9  xor     r8d, r8d
0x140061bfc  mov     rdx, rdi
0x140061bff  mov     rcx, rsi
0x140061c02  call    HsmpTracePostCallbackEnter
0x140061c07  mov     rax, [rsi+10h]
0x140061c0b  mov     r14d, [rax+20h]
0x140061c0f  mov     edi, [rbx+1Ch]
0x140061c12  shr     edi, 8
0x140061c15  and     dil, 1
0x140061c19  mov     rcx, rsi
0x140061c1c  call    HsmOsGetPlaceholderCompatMode
0x140061c21  movzx   ecx, al
0x140061c24  movzx   edx, dil
0x140061c28  call    HsmOsDisguisePlaceholder
0x140061c2d  test    al, al
0x140061c2f  jnz     loc_140061D62
0x140061c35  cmp     r14d, 16h
0x140061c39  jnz     loc_140061CE0
0x140061c3f  mov     qword ptr [rsp+78h+String1.Length], 540052h
0x140061c48  lea     rax, a3d0ce612Fdee43_1; ":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0"...
0x140061c4f  mov     [rsp+78h+String1.Buffer], rax
0x140061c54  mov     rax, [rsi+10h]
0x140061c58  mov     rax, [rax+28h]
0x140061c5c  mov     [rsp+78h+arg_0], rax
0x140061c64  mov     rdi, rax
0x140061c67  mov     r13d, [rsi+20h]
0x140061c6b  mov     r14d, r13d
0x140061c6e  xor     r12d, r12d
0x140061c71  test    rdi, rdi
0x140061c74  jz      loc_140061E42
0x140061c7a  xorps   xmm0, xmm0
0x140061c7d  movups  xmmword ptr [rsp+78h+String2.Length], xmm0
0x140061c82  mov     eax, [rdi]
0x140061c84  test    eax, eax
0x140061c86  jnz     loc_140061E9F
0x140061c8c  xor     r15d, r15d
0x140061c8f  lea     rax, [rdi+18h]
0x140061c93  mov     [rsp+78h+String2.Buffer], rax
0x140061c98  movzx   eax, word ptr [rdi+4]
0x140061c9c  mov     [rsp+78h+String2.Length], ax
0x140061ca1  movzx   eax, word ptr [rdi+4]
0x140061ca5  mov     [rsp+78h+String2.MaximumLength], ax
0x140061caa  mov     r8b, 1; CaseInSensitive
0x140061cad  lea     rdx, [rsp+78h+String2]; String2
0x140061cb2  lea     rcx, [rsp+78h+String1]; String1
0x140061cb7  call    cs:__imp_RtlPrefixUnicodeString
0x140061cbe  nop     dword ptr [rax+rax+00h]
0x140061cc3  test    al, al
0x140061cc5  jnz     loc_140061E70
0x140061ccb  mov     r12, rdi
0x140061cce  mov     rdi, r15
0x140061cd1  jmp     short loc_140061C71
0x140061cd3  xor     ebx, ebx
0x140061cd5  cmp     eax, 80000005h
0x140061cda  jz      loc_140061B6D
0x140061ce0  test    rbx, rbx
0x140061ce3  jz      loc_140061BBA
0x140061ce9  mov     rcx, rbx; Context
0x140061cec  call    cs:__imp_FltReleaseContext
0x140061cf3  nop     dword ptr [rax+rax+00h]
0x140061cf8  mov     r9b, 1
0x140061cfb  mov     rdx, rsi
0x140061cfe  xor     ecx, ecx
0x140061d00  call    HsmpTracePostCallbackExit
0x140061d05  jmp     loc_140061BBA
0x140061d0a  mov     rax, [rbx+10h]
0x140061d0e  mov     rcx, [rax+10h]
0x140061d12  cmp     [rcx+20h], r14
0x140061d16  jz      short loc_140061D1D
0x140061d18  mov     rcx, rbx
0x140061d1b  jmp     short loc_140061D4A
0x140061d1d  test    rbx, rbx
0x140061d20  jz      loc_140061BB0
0x140061d26  mov     rcx, rsi; CallbackData
0x140061d29  call    cs:__imp_FltGetRequestorProcess
0x140061d30  nop     dword ptr [rax+rax+00h]
0x140061d35  mov     rcx, rax
0x140061d38  call    HsmOsIsPassThroughModeEnabled
0x140061d3d  test    al, al
0x140061d3f  jz      loc_140061EE5
0x140061d45  mov     rcx, [rsp+78h+Context]; Context
0x140061d4a  call    cs:__imp_FltReleaseContext
0x140061d51  nop     dword ptr [rax+rax+00h]
0x140061d56  xor     ebx, ebx
0x140061d58  mov     [rsp+78h+Context], rbx
0x140061d5d  jmp     loc_140061BB0
0x140061d62  mov     r9, [rsi+10h]
0x140061d66  mov     r10, [r9+28h]
0x140061d6a  mov     r8d, 0FFFFFFFFh
0x140061d70  cmp     r14d, 12h
0x140061d74  jnz     loc_140061E05
0x140061d7a  mov     edx, 20h ; ' '; jumptable 0000000140061E32 case 4
0x140061d7f  test    edx, edx; jumptable 0000000140061E32 default case, cases 5-33,36-67,69,71-76
0x140061d81  js      short loc_140061DA4
0x140061d83  cmp     dword ptr [rsi+18h], 80000005h
0x140061d8a  jz      short loc_140061DBF
0x140061d8c  movsxd  rcx, edx
0x140061d8f  mov     eax, [rcx+r10]
0x140061d93  and     eax, 0FFFFE9FFh
0x140061d98  mov     edx, 80h
0x140061d9d  cmovz   eax, edx
0x140061da0  mov     [rcx+r10], eax
0x140061da4  test    r8d, r8d
0x140061da7  js      short loc_140061DE4
0x140061da9  cmp     dword ptr [rsi+18h], 80000005h
0x140061db0  jz      short loc_140061DD1
0x140061db2  movsxd  rax, r8d
0x140061db5  mov     dword ptr [rax+r10], 0
0x140061dbd  jmp     short loc_140061DE4
0x140061dbf  mov     ecx, [r9+18h]
0x140061dc3  movsxd  rax, edx
0x140061dc6  add     rax, 4
0x140061dca  cmp     rcx, rax
0x140061dcd  jnb     short loc_140061D8C
0x140061dcf  jmp     short loc_140061DA4
0x140061dd1  mov     rax, [rsi+10h]
0x140061dd5  mov     ecx, [rax+18h]
0x140061dd8  movsxd  rax, r8d
0x140061ddb  add     rax, 4
0x140061ddf  cmp     rcx, rax
0x140061de2  jnb     short loc_140061DB2
0x140061de4  jmp     loc_140061C35
0x140061de9  mov     rsi, [rsp+78h+arg_0]
0x140061df1  mov     [rsi+18h], eax
0x140061df4  mov     ecx, eax
0x140061df6  call    HsmDbgBreakOnStatus
0x140061dfb  mov     rbx, qword ptr [rsp+78h+String2.Length]
0x140061e00  jmp     loc_140061CE0
0x140061e05  mov     edx, r8d
0x140061e08  lea     eax, [r14-4]; switch 74 cases
0x140061e0c  cmp     eax, 49h
0x140061e0f  ja      def_140061E32; jumptable 0000000140061E32 default case, cases 5-33,36-67,69,71-76
0x140061e15  cdqe
0x140061e17  lea     r11, cs:140000000h
0x140061e1e  movzx   eax, ds:(byte_140021F94 - 140000000h)[r11+rax]
0x140061e27  mov     ecx, ds:(jpt_140061E32 - 140000000h)[r11+rax*4]
0x140061e2f  add     rcx, r11
0x140061e32  jmp     rcx; switch jump
0x140061e38  mov     edx, 30h ; '0'; jumptable 0000000140061E32 case 34
0x140061e3d  jmp     def_140061E32; jumptable 0000000140061E32 default case, cases 5-33,36-67,69,71-76
0x140061e42  mov     rax, [rsp+78h+arg_0]
0x140061e4a  cmp     r14d, r13d
0x140061e4d  jnb     loc_140061CE0
0x140061e53  mov     edi, r14d
0x140061e56  sub     r13d, r14d
0x140061e59  mov     r8d, r13d; Size
0x140061e5c  lea     rcx, [rdi+rax]; void *
0x140061e60  xor     edx, edx; Val
0x140061e62  call    memset
0x140061e67  mov     [rsi+20h], rdi
0x140061e6b  jmp     loc_140061CE0
0x140061e70  test    r15, r15
0x140061e73  jnz     loc_140061EFF
0x140061e79  mov     rax, [rsp+78h+arg_0]
0x140061e81  test    r12, r12
0x140061e84  jz      loc_140061F20
0x140061e8a  mov     [r12], r15d
0x140061e8e  mov     r14d, [r12+4]
0x140061e93  sub     r14d, eax
0x140061e96  add     r14d, 18h
0x140061e9a  add     r14d, r12d
0x140061e9d  jmp     short loc_140061E4A
0x140061e9f  mov     rdx, rax
0x140061ea2  lea     rcx, [rax+20h]
0x140061ea6  mov     eax, r14d
0x140061ea9  cmp     rcx, rax
0x140061eac  ja      loc_140061C8C
0x140061eb2  lea     r15, [rdx+rdi]
0x140061eb6  jmp     loc_140061C8F
0x140061ebb  xor     edx, edx; jumptable 0000000140061E32 case 35
0x140061ebd  mov     r8d, 4
0x140061ec3  jmp     def_140061E32; jumptable 0000000140061E32 default case, cases 5-33,36-67,69,71-76
0x140061ec8  test    rbx, rbx
0x140061ecb  jz      loc_140061BB0
0x140061ed1  mov     rcx, rbx; Context
0x140061ed4  call    cs:__imp_FltDeleteContext
0x140061edb  nop     dword ptr [rax+rax+00h]
0x140061ee0  jmp     loc_140061D45
0x140061ee5  mov     rbx, [rsp+78h+Context]
0x140061eea  jmp     loc_140061BB0
0x140061eef  mov     edx, 38h ; '8'; jumptable 0000000140061E32 cases 68,70,77
0x140061ef4  mov     r8d, 3Ch ; '<'
0x140061efa  jmp     def_140061E32; jumptable 0000000140061E32 default case, cases 5-33,36-67,69,71-76
0x140061eff  mov     r8d, dword ptr [rsp+78h+arg_0]
0x140061f07  sub     r8d, r15d
0x140061f0a  add     r8d, r14d; Size
0x140061f0d  sub     r14d, [rdi]
0x140061f10  mov     rdx, r15; Src
0x140061f13  mov     rcx, rdi; void *
0x140061f16  call    memmove
0x140061f1b  jmp     loc_140061C71
0x140061f20  mov     r14d, edi
0x140061f23  sub     r14d, eax
0x140061f26  jmp     loc_140061E4A
0x1400866e0  push    rbp
0x1400866e2  sub     rsp, 20h
0x1400866e6  mov     rbp, rdx
0x1400866e9  call    HsmUserModeAddressExceptionHandler
0x1400866ee  nop
0x1400866ef  add     rsp, 20h
0x1400866f3  pop     rbp
0x1400866f4  retn
```
