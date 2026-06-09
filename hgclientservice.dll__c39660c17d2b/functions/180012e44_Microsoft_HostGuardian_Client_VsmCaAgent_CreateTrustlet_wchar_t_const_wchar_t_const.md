# Microsoft::HostGuardian::Client::VsmCaAgent::CreateTrustlet(wchar_t const *,wchar_t const *)

- ea: `0x180012e44`
- end: `0x1800131e0`
- name: `?CreateTrustlet@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXPEB_W0@Z`
- size: `924`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012b44`

## callees

- `0x180001770`
- `0x1800021f0`
- `0x1800077a0`
- `0x180012e44`
- `0x180013d08`

## import_xrefs

- `ntdll!NtCreateUserProcess` at `0x180013139`
- `ntdll!NtCreateUserProcess` at `0x180013139`
- `ntdll!NtClose` at `0x18001314e`
- `ntdll!NtClose` at `0x18001314e`
- `ntdll!RtlFreeHeap` at `0x180013182`
- `ntdll!RtlFreeHeap` at `0x180013182`
- `ntdll!RtlDestroyProcessParameters` at `0x180013164`
- `ntdll!RtlDestroyProcessParameters` at `0x180013164`
- `ntdll!RtlInitUnicodeString` at `0x180012f35`
- `ntdll!RtlInitUnicodeString` at `0x180012f35`
- `ntdll!RtlCreateProcessParametersEx` at `0x18001302c`
- `ntdll!RtlCreateProcessParametersEx` at `0x18001302c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180012f5a`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x180012f5a`

## string_xrefs

- `0x180012e8a`: `CreateTrustlet...`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::VsmCaAgent::CreateTrustlet(
        Microsoft::HostGuardian::Client::VsmCaAgent *this,
        const wchar_t *a2,
        const wchar_t *a3)
{
  __int64 v6; // rcx
  int *v7; // rax
  PWSTR Buffer; // rdi
  int v9; // eax
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  __int16 v14; // cx
  struct _RTL_USER_PROCESS_PARAMETERS *v15; // rsi
  struct _RTL_USER_PROCESS_PARAMETERS *v16; // rbx
  int v17; // eax
  unsigned int v18; // r8d
  __int64 v19; // rcx
  _BYTE *v20; // rax
  int v21; // eax
  unsigned int v22; // r8d
  int v23; // [rsp+20h] [rbp-E0h]
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+60h] [rbp-A0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  int v26[4]; // [rsp+78h] [rbp-88h] BYREF
  PWSTR v27; // [rsp+88h] [rbp-78h]
  PRTL_USER_PROCESS_PARAMETERS v28; // [rsp+90h] [rbp-70h]
  int v29; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v30; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp-50h] BYREF
  char v32; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v33[2]; // [rsp+110h] [rbp+10h] BYREF
  char v34; // [rsp+120h] [rbp+20h]
  __int128 v35; // [rsp+170h] [rbp+70h] BYREF
  __int64 v36; // [rsp+180h] [rbp+80h]
  _QWORD v37[14]; // [rsp+190h] [rbp+90h] BYREF
  int v38[4]; // [rsp+200h] [rbp+100h] BYREF
  const wchar_t *v39; // [rsp+210h] [rbp+110h]
  __int64 v40; // [rsp+218h] [rbp+118h]
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v39 = L"CreateTrustlet...";
    v40 = 36;
    McGenEventWrite_EventWriteTransfer(this, ServiceDebugInformational, a3, 2, v38);
  }
  memset_0(v37, 0, 0x68u);
  v35 = 0;
  v36 = 0;
  memset_0(v33, 0, 0x58u);
  *(_OWORD *)v26 = 0;
  DestinationString = 0;
  memset_0(&v29, 0, 0x68u);
  ProcessParameters = 0;
  v6 = 104;
  v7 = &v29;
  do
  {
    *(_BYTE *)v7 = 0;
    v7 = (int *)((char *)v7 + 1);
    --v6;
  }
  while ( v6 );
  v29 = 104;
  RtlInitUnicodeString(&DestinationString, 0);
  Buffer = DestinationString.Buffer;
  v27 = DestinationString.Buffer;
  *(_QWORD *)&v35 = 7;
  v9 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x61, v10, (const char *)(unsigned int)v9, v23);
  v11 = 0;
  *(_OWORD *)v26 = 0;
  if ( a3 )
  {
    v12 = 0x7FFF;
    v13 = a3;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    v11 = v12 == 0 ? (const char *)0xC000000DLL : 0LL;
    if ( v12 )
    {
      v14 = 2 * v12;
      LOWORD(v26[0]) = -2 - v14;
      HIWORD(v26[0]) = -v14;
      *(_QWORD *)&v26[2] = a3;
    }
  }
  if ( (int)v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x63, v10, v11, v23);
  v15 = NtCurrentPeb()->ProcessParameters;
  v16 = ProcessParameters;
  v28 = ProcessParameters;
  v17 = RtlCreateProcessParametersEx(&ProcessParameters, &DestinationString, 0, 0);
  if ( v17 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0x71, v18, (const char *)(unsigned int)v17, (int)v26);
  ProcessParameters[1].Flags = v15[1].Flags;
  v19 = 88;
  v20 = v33;
  do
  {
    *v20++ = 0;
    --v19;
  }
  while ( v19 );
  v33[0] = 88;
  v34 |= 4u;
  v37[1] = 65539;
  v37[2] = 16;
  v37[4] = 0;
  v37[3] = &v32;
  v37[5] = 131077;
  v37[6] = DestinationString.Length;
  v37[8] = 0;
  v37[7] = DestinationString.Buffer;
  v37[9] = 131090;
  v37[10] = 8;
  v37[12] = 0;
  v37[11] = &v35;
  v37[0] = 104;
  v21 = NtCreateUserProcess(&v30, &Handle, 0x2000000, 0x2000000);
  if ( v21 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(retaddr, (void *)0xA4, v22, (const char *)(unsigned int)v21, 0);
  NtClose(Handle);
  *((_QWORD *)this + 4) = v30;
  if ( v16 )
    RtlDestroyProcessParameters(v16);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
}

```

## disassembly

```asm
0x180012e44  push    rbp
0x180012e46  push    rbx
0x180012e47  push    rsi
0x180012e48  push    rdi
0x180012e49  push    r12
0x180012e4b  push    r13
0x180012e4d  push    r14
0x180012e4f  push    r15
0x180012e51  lea     rbp, [rsp-138h]
0x180012e59  sub     rsp, 238h
0x180012e60  mov     rax, cs:__security_cookie
0x180012e67  xor     rax, rsp
0x180012e6a  mov     [rbp+170h+var_50], rax
0x180012e71  mov     rbx, r8
0x180012e74  mov     rsi, rdx
0x180012e77  mov     r14, rcx
0x180012e7a  xor     r15d, r15d
0x180012e7d  lea     r12d, [r15+2]
0x180012e81  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r12b
0x180012e88  jz      short loc_180012EBE
0x180012e8a  lea     rax, aCreatetrustlet; "CreateTrustlet..."
0x180012e91  mov     [rbp+170h+var_60], rax
0x180012e98  mov     [rbp+170h+var_58], 24h ; '$'
0x180012ea3  lea     rax, [rbp+170h+var_70]
0x180012eaa  mov     qword ptr [rsp+270h+var_250], rax; int
0x180012eaf  mov     r9d, r12d
0x180012eb2  lea     rdx, ServiceDebugInformational
0x180012eb9  call    McGenEventWrite_EventWriteTransfer
0x180012ebe  mov     r13d, 68h ; 'h'
0x180012ec4  mov     r8d, r13d; Size
0x180012ec7  xor     edx, edx; Val
0x180012ec9  lea     rcx, [rbp+170h+var_E0]; void *
0x180012ed0  call    memset_0
0x180012ed5  xorps   xmm0, xmm0
0x180012ed8  xor     eax, eax
0x180012eda  movups  [rbp+170h+var_100], xmm0
0x180012ede  mov     [rbp+170h+var_F0], rax
0x180012ee5  xor     edx, edx; Val
0x180012ee7  lea     r8d, [r13-10h]; Size
0x180012eeb  lea     rcx, [rbp+170h+var_160]; void *
0x180012eef  call    memset_0
0x180012ef4  xorps   xmm0, xmm0
0x180012ef7  movups  xmmword ptr [rsp+270h+var_1F8], xmm0
0x180012efc  xorps   xmm1, xmm1
0x180012eff  movups  xmmword ptr [rsp+270h+DestinationString.Length], xmm1
0x180012f04  mov     r8d, r13d; Size
0x180012f07  xor     edx, edx; Val
0x180012f09  lea     rcx, [rbp+170h+var_1D0]; void *
0x180012f0d  call    memset_0
0x180012f12  mov     [rsp+270h+ProcessParameters], r15
0x180012f17  mov     ecx, r13d
0x180012f1a  lea     rax, [rbp+170h+var_1D0]
0x180012f1e  mov     [rax], r15b
0x180012f21  inc     rax
0x180012f24  sub     rcx, 1
0x180012f28  jnz     short loc_180012F1E
0x180012f2a  mov     [rbp+170h+var_1D0], r13d
0x180012f2e  xor     edx, edx; SourceString
0x180012f30  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x180012f35  call    cs:__imp_RtlInitUnicodeString
0x180012f3b  mov     rdi, [rsp+270h+DestinationString.Buffer]
0x180012f40  mov     [rbp+170h+var_1E8], rdi
0x180012f44  mov     qword ptr [rbp+170h+var_100], 7
0x180012f4c  xor     r9d, r9d
0x180012f4f  xor     r8d, r8d
0x180012f52  lea     rdx, [rsp+270h+DestinationString]
0x180012f57  mov     rcx, rsi
0x180012f5a  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180012f60  mov     rcx, [rbp+178h]; this
0x180012f67  test    eax, eax
0x180012f69  js      loc_1800131B9
0x180012f6f  mov     r9d, r15d
0x180012f72  xorps   xmm0, xmm0
0x180012f75  movups  xmmword ptr [rsp+270h+var_1F8], xmm0
0x180012f7a  test    rbx, rbx
0x180012f7d  jz      short loc_180012FCB
0x180012f7f  mov     ecx, 7FFFh
0x180012f84  mov     rax, rbx
0x180012f87  cmp     [rax], r15w
0x180012f8b  jz      short loc_180012F96
0x180012f8d  add     rax, r12
0x180012f90  sub     rcx, 1
0x180012f94  jnz     short loc_180012F87
0x180012f96  mov     rax, rcx
0x180012f99  neg     rax
0x180012f9c  sbb     r9d, r9d
0x180012f9f  not     r9d
0x180012fa2  and     r9d, 0C000000Dh; char *
0x180012fa9  test    rcx, rcx
0x180012fac  jz      short loc_180012FCB
0x180012fae  add     cx, cx
0x180012fb1  mov     eax, 0FFFEh
0x180012fb6  sub     ax, cx
0x180012fb9  mov     word ptr [rsp+270h+var_1F8], ax
0x180012fbe  add     ax, r12w
0x180012fc2  mov     word ptr [rsp+270h+var_1F8+2], ax
0x180012fc7  mov     qword ptr [rbp+170h+var_1F8+8], rbx
0x180012fcb  mov     rcx, [rbp+178h]; this
0x180012fd2  test    r9d, r9d
0x180012fd5  js      loc_1800131C7
0x180012fdb  mov     rax, gs:60h
0x180012fe4  mov     rsi, [rax+20h]
0x180012fe8  mov     rbx, [rsp+270h+ProcessParameters]
0x180012fed  mov     [rbp+170h+var_1E0], rbx
0x180012ff1  mov     dword ptr [rsp+270h+var_220], 1
0x180012ff9  mov     [rsp+270h+var_228], r15
0x180012ffe  mov     [rsp+270h+var_230], r15
0x180013003  mov     [rsp+270h+var_238], r15
0x180013008  mov     [rsp+270h+var_240], r15
0x18001300d  mov     [rsp+270h+var_248], r15
0x180013012  lea     rax, [rsp+270h+var_1F8]
0x180013017  mov     qword ptr [rsp+270h+var_250], rax; int
0x18001301c  xor     r9d, r9d
0x18001301f  xor     r8d, r8d
0x180013022  lea     rdx, [rsp+270h+DestinationString]
0x180013027  lea     rcx, [rsp+270h+ProcessParameters]
0x18001302c  call    cs:__imp_RtlCreateProcessParametersEx
0x180013032  mov     rcx, [rbp+178h]; this
0x180013039  test    eax, eax
0x18001303b  js      loc_1800131D2
0x180013041  mov     ecx, [rsi+408h]
0x180013047  mov     rax, [rsp+270h+ProcessParameters]
0x18001304c  mov     [rax+408h], ecx
0x180013052  mov     edx, 58h ; 'X'
0x180013057  mov     ecx, edx
0x180013059  lea     rax, [rbp+170h+var_160]
0x18001305d  mov     [rax], r15b
0x180013060  inc     rax
0x180013063  sub     rcx, 1
0x180013067  jnz     short loc_18001305D
0x180013069  mov     [rbp+170h+var_160], rdx
0x18001306d  or      [rbp+170h+var_150], 4
0x180013071  mov     [rbp+170h+var_D8], 10003h
0x18001307c  mov     [rbp+170h+var_D0], 10h
0x180013087  mov     [rbp+170h+var_C0], r15
0x18001308e  lea     rax, [rbp+170h+var_1B8]
0x180013092  mov     [rbp+170h+var_C8], rax
0x180013099  mov     [rbp+170h+var_B8], 20005h
0x1800130a4  movzx   eax, [rsp+270h+DestinationString.Length]
0x1800130a9  mov     [rbp+170h+var_B0], rax
0x1800130b0  mov     [rbp+170h+var_A0], r15
0x1800130b7  mov     rax, [rsp+270h+DestinationString.Buffer]
0x1800130bc  mov     [rbp+170h+var_A8], rax
0x1800130c3  mov     [rbp+170h+var_98], 20012h
0x1800130ce  mov     [rbp+170h+var_90], 8
0x1800130d9  mov     [rbp+170h+var_80], r15
0x1800130e0  lea     rax, [rbp+170h+var_100]
0x1800130e4  mov     [rbp+170h+var_88], rax
0x1800130eb  mov     [rbp+170h+var_E0], r13
0x1800130f2  lea     rax, [rbp+170h+var_E0]
0x1800130f9  mov     [rsp+270h+var_220], rax
0x1800130fe  lea     rax, [rbp+170h+var_160]
0x180013102  mov     [rsp+270h+var_228], rax
0x180013107  mov     rax, [rsp+270h+ProcessParameters]
0x18001310c  mov     [rsp+270h+var_230], rax
0x180013111  mov     dword ptr [rsp+270h+var_238], r15d
0x180013116  mov     dword ptr [rsp+270h+var_240], 100h
0x18001311e  mov     [rsp+270h+var_248], r15
0x180013123  mov     qword ptr [rsp+270h+var_250], r15; int
0x180013128  mov     r8d, 2000000h
0x18001312e  mov     r9d, r8d
0x180013131  lea     rdx, [rbp+170h+Handle]
0x180013135  lea     rcx, [rbp+170h+var_1C8]
0x180013139  call    cs:__imp_NtCreateUserProcess
0x18001313f  mov     rcx, [rbp+178h]; this
0x180013146  test    eax, eax
0x180013148  js      short loc_1800131AB
0x18001314a  mov     rcx, [rbp+170h+Handle]; Handle
0x18001314e  call    cs:__imp_NtClose
0x180013154  mov     rax, [rbp+170h+var_1C8]
0x180013158  mov     [r14+20h], rax
0x18001315c  test    rbx, rbx
0x18001315f  jz      short loc_18001316B
0x180013161  mov     rcx, rbx; ProcessParameters
0x180013164  call    cs:__imp_RtlDestroyProcessParameters
0x18001316a  nop
0x18001316b  test    rdi, rdi
0x18001316e  jz      short loc_180013188
0x180013170  mov     rcx, gs:60h
0x180013179  mov     r8, rdi; P
0x18001317c  xor     edx, edx; Flags
0x18001317e  mov     rcx, [rcx+30h]; HeapHandle
0x180013182  call    cs:__imp_RtlFreeHeap
0x180013188  mov     rcx, [rbp+170h+var_50]
0x18001318f  xor     rcx, rsp; StackCookie
0x180013192  call    __security_check_cookie
0x180013197  add     rsp, 238h
0x18001319e  pop     r15
0x1800131a0  pop     r14
0x1800131a2  pop     r13
0x1800131a4  pop     r12
0x1800131a6  pop     rdi
0x1800131a7  pop     rsi
0x1800131a8  pop     rbx
0x1800131a9  pop     rbp
0x1800131aa  retn
0x1800131ab  mov     r9d, eax; char *
0x1800131ae  mov     edx, 0A4h; void *
0x1800131b3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800131b9  mov     r9d, eax; char *
0x1800131bc  mov     edx, 61h ; 'a'; void *
0x1800131c1  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800131c7  mov     edx, 63h ; 'c'; void *
0x1800131cc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800131d2  mov     r9d, eax; char *
0x1800131d5  mov     edx, 71h ; 'q'; void *
0x1800131da  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
