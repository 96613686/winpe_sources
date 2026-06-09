# HsmFltPostQUERY_INFORMATION

- ea: `0x140061c60`
- end: `0x14006204b`
- name: `HsmFltPostQUERY_INFORMATION`
- size: `1003`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, __int64)`
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
- `0x14001e300`
- `0x14001e600`
- `0x140042f18`
- `0x140061c60`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140061dd7`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140061dd7`
- `FLTMGR!FltGetStreamContext` at `0x140061ca6`
- `FLTMGR!FltGetStreamContext` at `0x140061ca6`
- `FLTMGR!FltDeleteContext` at `0x140061ff4`
- `FLTMGR!FltDeleteContext` at `0x140061ff4`
- `FLTMGR!FltGetRequestorProcess` at `0x140061cfa`
- `FLTMGR!FltGetRequestorProcess` at `0x140061e49`
- `FLTMGR!FltGetRequestorProcess` at `0x140061cfa`
- `FLTMGR!FltGetRequestorProcess` at `0x140061e49`
- `FLTMGR!FltReleaseContext` at `0x140061e0c`
- `FLTMGR!FltReleaseContext` at `0x140061e6a`
- `FLTMGR!FltReleaseContext` at `0x140061e0c`
- `FLTMGR!FltReleaseContext` at `0x140061e6a`

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
    PlaceholderCompatMode = HsmOsGetPlaceholderCompatMode(CallbackData);
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
0x140061c60  mov     [rsp+arg_8], rbx
0x140061c65  mov     [rsp+arg_10], rsi
0x140061c6a  mov     [rsp+arg_0], rcx
0x140061c6f  push    rdi
0x140061c70  push    r12
0x140061c72  push    r13
0x140061c74  push    r14
0x140061c76  push    r15
0x140061c78  sub     rsp, 50h
0x140061c7c  mov     rdi, r8
0x140061c7f  mov     rsi, rcx
0x140061c82  mov     eax, [rcx+18h]
0x140061c85  test    eax, eax
0x140061c87  js      loc_140061DF3
0x140061c8d  mov     r14, [rdx+18h]
0x140061c91  mov     [rsp+78h+Context], 0
0x140061c9a  lea     r8, [rsp+78h+Context]; Context
0x140061c9f  mov     rdx, [rdx+20h]; FileObject
0x140061ca3  mov     rcx, r14; Instance
0x140061ca6  call    cs:__imp_FltGetStreamContext
0x140061cad  nop     dword ptr [rax+rax+00h]
0x140061cb2  mov     rbx, [rsp+78h+Context]
0x140061cb7  test    rbx, rbx
0x140061cba  jz      short loc_140061CD0
0x140061cbc  mov     eax, [rbx+1Ch]
0x140061cbf  test    al, 1
0x140061cc1  jz      loc_140061FE8
0x140061cc7  test    rbx, rbx
0x140061cca  jnz     loc_140061E2A
0x140061cd0  mov     qword ptr [rsp+78h+String2.Length], rbx
0x140061cd5  test    rbx, rbx
0x140061cd8  jnz     short loc_140061CF7
0x140061cda  xor     eax, eax
0x140061cdc  lea     r11, [rsp+78h+var_28]
0x140061ce1  mov     rbx, [r11+38h]
0x140061ce5  mov     rsi, [r11+40h]
0x140061ce9  mov     rsp, r11
0x140061cec  pop     r15
0x140061cee  pop     r14
0x140061cf0  pop     r13
0x140061cf2  pop     r12
0x140061cf4  pop     rdi
0x140061cf5  retn
0x140061cf7  mov     rcx, rsi; CallbackData
0x140061cfa  call    cs:__imp_FltGetRequestorProcess
0x140061d01  nop     dword ptr [rax+rax+00h]
0x140061d06  mov     rcx, rax
0x140061d09  call    HsmOsIsPassThroughModeEnabled
0x140061d0e  test    al, al
0x140061d10  jnz     loc_140061E00
0x140061d16  mov     r9b, 1
0x140061d19  xor     r8d, r8d
0x140061d1c  mov     rdx, rdi
0x140061d1f  mov     rcx, rsi
0x140061d22  call    HsmpTracePostCallbackEnter
0x140061d27  mov     rax, [rsi+10h]
0x140061d2b  mov     r14d, [rax+20h]
0x140061d2f  mov     edi, [rbx+1Ch]
0x140061d32  shr     edi, 8
0x140061d35  and     dil, 1
0x140061d39  mov     rcx, rsi
0x140061d3c  call    HsmOsGetPlaceholderCompatMode
0x140061d41  movzx   ecx, al
0x140061d44  movzx   edx, dil
0x140061d48  call    HsmOsDisguisePlaceholder
0x140061d4d  test    al, al
0x140061d4f  jnz     loc_140061E82
0x140061d55  cmp     r14d, 16h
0x140061d59  jnz     loc_140061E00
0x140061d5f  mov     qword ptr [rsp+78h+String1.Length], 540052h
0x140061d68  lea     rax, a3d0ce612Fdee43_1; ":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0"...
0x140061d6f  mov     [rsp+78h+String1.Buffer], rax
0x140061d74  mov     rax, [rsi+10h]
0x140061d78  mov     rax, [rax+28h]
0x140061d7c  mov     [rsp+78h+arg_0], rax
0x140061d84  mov     rdi, rax
0x140061d87  mov     r13d, [rsi+20h]
0x140061d8b  mov     r14d, r13d
0x140061d8e  xor     r12d, r12d
0x140061d91  test    rdi, rdi
0x140061d94  jz      loc_140061F62
0x140061d9a  xorps   xmm0, xmm0
0x140061d9d  movups  xmmword ptr [rsp+78h+String2.Length], xmm0
0x140061da2  mov     eax, [rdi]
0x140061da4  test    eax, eax
0x140061da6  jnz     loc_140061FBF
0x140061dac  xor     r15d, r15d
0x140061daf  lea     rax, [rdi+18h]
0x140061db3  mov     [rsp+78h+String2.Buffer], rax
0x140061db8  movzx   eax, word ptr [rdi+4]
0x140061dbc  mov     [rsp+78h+String2.Length], ax
0x140061dc1  movzx   eax, word ptr [rdi+4]
0x140061dc5  mov     [rsp+78h+String2.MaximumLength], ax
0x140061dca  mov     r8b, 1; CaseInSensitive
0x140061dcd  lea     rdx, [rsp+78h+String2]; String2
0x140061dd2  lea     rcx, [rsp+78h+String1]; String1
0x140061dd7  call    cs:__imp_RtlPrefixUnicodeString
0x140061dde  nop     dword ptr [rax+rax+00h]
0x140061de3  test    al, al
0x140061de5  jnz     loc_140061F90
0x140061deb  mov     r12, rdi
0x140061dee  mov     rdi, r15
0x140061df1  jmp     short loc_140061D91
0x140061df3  xor     ebx, ebx
0x140061df5  cmp     eax, 80000005h
0x140061dfa  jz      loc_140061C8D
0x140061e00  test    rbx, rbx
0x140061e03  jz      loc_140061CDA
0x140061e09  mov     rcx, rbx; Context
0x140061e0c  call    cs:__imp_FltReleaseContext
0x140061e13  nop     dword ptr [rax+rax+00h]
0x140061e18  mov     r9b, 1
0x140061e1b  mov     rdx, rsi
0x140061e1e  xor     ecx, ecx
0x140061e20  call    HsmpTracePostCallbackExit
0x140061e25  jmp     loc_140061CDA
0x140061e2a  mov     rax, [rbx+10h]
0x140061e2e  mov     rcx, [rax+10h]
0x140061e32  cmp     [rcx+20h], r14
0x140061e36  jz      short loc_140061E3D
0x140061e38  mov     rcx, rbx
0x140061e3b  jmp     short loc_140061E6A
0x140061e3d  test    rbx, rbx
0x140061e40  jz      loc_140061CD0
0x140061e46  mov     rcx, rsi; CallbackData
0x140061e49  call    cs:__imp_FltGetRequestorProcess
0x140061e50  nop     dword ptr [rax+rax+00h]
0x140061e55  mov     rcx, rax
0x140061e58  call    HsmOsIsPassThroughModeEnabled
0x140061e5d  test    al, al
0x140061e5f  jz      loc_140062005
0x140061e65  mov     rcx, [rsp+78h+Context]; Context
0x140061e6a  call    cs:__imp_FltReleaseContext
0x140061e71  nop     dword ptr [rax+rax+00h]
0x140061e76  xor     ebx, ebx
0x140061e78  mov     [rsp+78h+Context], rbx
0x140061e7d  jmp     loc_140061CD0
0x140061e82  mov     r9, [rsi+10h]
0x140061e86  mov     r10, [r9+28h]
0x140061e8a  mov     r8d, 0FFFFFFFFh
0x140061e90  cmp     r14d, 12h
0x140061e94  jnz     loc_140061F25
0x140061e9a  mov     edx, 20h ; ' '; jumptable 0000000140061F52 case 4
0x140061e9f  test    edx, edx; jumptable 0000000140061F52 default case, cases 5-33,36-67,69,71-76
0x140061ea1  js      short loc_140061EC4
0x140061ea3  cmp     dword ptr [rsi+18h], 80000005h
0x140061eaa  jz      short loc_140061EDF
0x140061eac  movsxd  rcx, edx
0x140061eaf  mov     eax, [rcx+r10]
0x140061eb3  and     eax, 0FFFFE9FFh
0x140061eb8  mov     edx, 80h
0x140061ebd  cmovz   eax, edx
0x140061ec0  mov     [rcx+r10], eax
0x140061ec4  test    r8d, r8d
0x140061ec7  js      short loc_140061F04
0x140061ec9  cmp     dword ptr [rsi+18h], 80000005h
0x140061ed0  jz      short loc_140061EF1
0x140061ed2  movsxd  rax, r8d
0x140061ed5  mov     dword ptr [rax+r10], 0
0x140061edd  jmp     short loc_140061F04
0x140061edf  mov     ecx, [r9+18h]
0x140061ee3  movsxd  rax, edx
0x140061ee6  add     rax, 4
0x140061eea  cmp     rcx, rax
0x140061eed  jnb     short loc_140061EAC
0x140061eef  jmp     short loc_140061EC4
0x140061ef1  mov     rax, [rsi+10h]
0x140061ef5  mov     ecx, [rax+18h]
0x140061ef8  movsxd  rax, r8d
0x140061efb  add     rax, 4
0x140061eff  cmp     rcx, rax
0x140061f02  jnb     short loc_140061ED2
0x140061f04  jmp     loc_140061D55
0x140061f09  mov     rsi, [rsp+78h+arg_0]
0x140061f11  mov     [rsi+18h], eax
0x140061f14  mov     ecx, eax
0x140061f16  call    HsmDbgBreakOnStatus
0x140061f1b  mov     rbx, qword ptr [rsp+78h+String2.Length]
0x140061f20  jmp     loc_140061E00
0x140061f25  mov     edx, r8d
0x140061f28  lea     eax, [r14-4]; switch 74 cases
0x140061f2c  cmp     eax, 49h
0x140061f2f  ja      def_140061F52; jumptable 0000000140061F52 default case, cases 5-33,36-67,69,71-76
0x140061f35  cdqe
0x140061f37  lea     r11, cs:140000000h
0x140061f3e  movzx   eax, ds:(byte_140021F94 - 140000000h)[r11+rax]
0x140061f47  mov     ecx, ds:(jpt_140061F52 - 140000000h)[r11+rax*4]
0x140061f4f  add     rcx, r11
0x140061f52  jmp     rcx; switch jump
0x140061f58  mov     edx, 30h ; '0'; jumptable 0000000140061F52 case 34
0x140061f5d  jmp     def_140061F52; jumptable 0000000140061F52 default case, cases 5-33,36-67,69,71-76
0x140061f62  mov     rax, [rsp+78h+arg_0]
0x140061f6a  cmp     r14d, r13d
0x140061f6d  jnb     loc_140061E00
0x140061f73  mov     edi, r14d
0x140061f76  sub     r13d, r14d
0x140061f79  mov     r8d, r13d; Size
0x140061f7c  lea     rcx, [rdi+rax]; void *
0x140061f80  xor     edx, edx; Val
0x140061f82  call    memset
0x140061f87  mov     [rsi+20h], rdi
0x140061f8b  jmp     loc_140061E00
0x140061f90  test    r15, r15
0x140061f93  jnz     loc_14006201F
0x140061f99  mov     rax, [rsp+78h+arg_0]
0x140061fa1  test    r12, r12
0x140061fa4  jz      loc_140062040
0x140061faa  mov     [r12], r15d
0x140061fae  mov     r14d, [r12+4]
0x140061fb3  sub     r14d, eax
0x140061fb6  add     r14d, 18h
0x140061fba  add     r14d, r12d
0x140061fbd  jmp     short loc_140061F6A
0x140061fbf  mov     rdx, rax
0x140061fc2  lea     rcx, [rax+20h]
0x140061fc6  mov     eax, r14d
0x140061fc9  cmp     rcx, rax
0x140061fcc  ja      loc_140061DAC
0x140061fd2  lea     r15, [rdx+rdi]
0x140061fd6  jmp     loc_140061DAF
0x140061fdb  xor     edx, edx; jumptable 0000000140061F52 case 35
0x140061fdd  mov     r8d, 4
0x140061fe3  jmp     def_140061F52; jumptable 0000000140061F52 default case, cases 5-33,36-67,69,71-76
0x140061fe8  test    rbx, rbx
0x140061feb  jz      loc_140061CD0
0x140061ff1  mov     rcx, rbx; Context
0x140061ff4  call    cs:__imp_FltDeleteContext
0x140061ffb  nop     dword ptr [rax+rax+00h]
0x140062000  jmp     loc_140061E65
0x140062005  mov     rbx, [rsp+78h+Context]
0x14006200a  jmp     loc_140061CD0
0x14006200f  mov     edx, 38h ; '8'; jumptable 0000000140061F52 cases 68,70,77
0x140062014  mov     r8d, 3Ch ; '<'
0x14006201a  jmp     def_140061F52; jumptable 0000000140061F52 default case, cases 5-33,36-67,69,71-76
0x14006201f  mov     r8d, dword ptr [rsp+78h+arg_0]
0x140062027  sub     r8d, r15d
0x14006202a  add     r8d, r14d; Size
0x14006202d  sub     r14d, [rdi]
0x140062030  mov     rdx, r15; Src
0x140062033  mov     rcx, rdi; void *
0x140062036  call    memmove
0x14006203b  jmp     loc_140061D91
0x140062040  mov     r14d, edi
0x140062043  sub     r14d, eax
0x140062046  jmp     loc_140061F6A
0x1400868a0  push    rbp
0x1400868a2  sub     rsp, 20h
0x1400868a6  mov     rbp, rdx
0x1400868a9  call    HsmUserModeAddressExceptionHandler
0x1400868ae  nop
0x1400868af  add     rsp, 20h
0x1400868b3  pop     rbp
0x1400868b4  retn
```
