# CscEnpFindChild

- ea: `0x14000aaf0`
- end: `0x14000b0d4`
- name: `CscEnpFindChild`
- size: `1508`
- prototype: `__int64 __fastcall(unsigned __int64, const UNICODE_STRING *, char *, const UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14006a8d0`

## callees

- `0x14000aaf0`
- `0x14000b5a0`
- `0x14000c5f8`
- `0x140010e20`
- `0x140012d20`
- `0x1400169d4`
- `0x140018930`
- `0x14001ef50`
- `0x14002f010`
- `0x14002f0f0`
- `0x14002f440`
- `0x1400683ac`
- `0x14006d870`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000aee4`
- `ntoskrnl!KeInitializeEvent` at `0x14000aee4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000aca9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14000aca9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000adc7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b022`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000adc7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000b022`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000ac92`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x14000ac92`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000af27`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000af52`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000af27`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x14000af52`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000ad8a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14000ad8a`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000b071`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14000b071`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000afd5`
- `ntoskrnl!SeCreateClientSecurity` at `0x14000afd5`
- `ntoskrnl!IoGetStackLimits` at `0x14000ad4f`
- `ntoskrnl!IoGetStackLimits` at `0x14000ad4f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ab67`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ab81`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ab67`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ab81`

## pseudocode

```c
__int64 __fastcall CscEnpFindChild(unsigned __int64 a1, const UNICODE_STRING *a2, char *a3, const UNICODE_STRING **a4)
{
  int v4; // eax
  const UNICODE_STRING *v8; // rdi
  const UNICODE_STRING *v9; // r12
  const UNICODE_STRING *v10; // r14
  const UNICODE_STRING *v11; // rbx
  char v12; // al
  const UNICODE_STRING **v13; // r14
  __int64 result; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r12
  NTSTATUS v20; // eax
  int Blink; // ebx
  int v22; // ecx
  unsigned int v23; // ecx
  __int64 v24; // rcx
  NTSTATUS v25; // eax
  char v26; // [rsp+38h] [rbp-D0h]
  BOOLEAN v27; // [rsp+38h] [rbp-D0h]
  char v28; // [rsp+38h] [rbp-D0h]
  BOOLEAN v29; // [rsp+39h] [rbp-CFh]
  HANDLE Handle; // [rsp+40h] [rbp-C8h] BYREF
  struct _UNICODE_STRING *v31; // [rsp+48h] [rbp-C0h] BYREF
  const UNICODE_STRING **LowLimit; // [rsp+50h] [rbp-B8h] BYREF
  struct _KEVENT LowLimit_8; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 HighLimit[3]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v35; // [rsp+88h] [rbp-80h]
  __int128 v36; // [rsp+98h] [rbp-70h]
  __int64 v37; // [rsp+A8h] [rbp-60h]
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+B0h] [rbp-58h] BYREF
  _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+C8h] [rbp-40h] BYREF

  v4 = *(_DWORD *)(a1 + 336);
  LowLimit = a4;
  if ( (v4 & 0x10) == 0 )
    return 3221225530LL;
  v8 = *(const UNICODE_STRING **)(a1 + 80);
  v9 = 0;
  v10 = (const UNICODE_STRING *)(a1 + 80);
  v26 = 0;
  while ( 1 )
  {
    if ( v8 == v10 )
    {
      v12 = 0;
      goto LABEL_13;
    }
    v11 = v8 - 6;
    if ( RtlEqualUnicodeString(v8 - 3, a2, 1u) )
    {
      v12 = 0;
      goto LABEL_8;
    }
    if ( RtlEqualUnicodeString(v11 + 4, a2, 1u) )
      break;
    v8 = *(const UNICODE_STRING **)&v8->Length;
  }
  v12 = 1;
  v26 = 1;
LABEL_8:
  if ( v8 == (const UNICODE_STRING *)96 )
  {
    v9 = 0;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(&v11->MaximumLength + 1));
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      v9 = v8 - 6;
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        WPP_SF_qdq(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v11);
      v12 = v26;
      v9 = v8 - 6;
    }
  }
LABEL_13:
  if ( a3 )
    *a3 = v12;
  v13 = LowLimit;
  *LowLimit = v9;
  if ( v9 )
    return 0;
  Handle = 0;
  v31 = 0;
  v37 = 0;
  v15 = *(_QWORD *)(a1 + 8);
  *(_OWORD *)&HighLimit[1] = 0;
  v35 = 0;
  v36 = 0;
  v16 = *(_QWORD *)(v15 + 24);
  LowLimit = *(const UNICODE_STRING ***)(a1 + 144);
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&ClientContext, 0, sizeof(ClientContext));
  v27 = KeAreAllApcsDisabled();
  v17 = ExAllocateFromPagedLookasideList(&Lookaside);
  v19 = v17;
  if ( !v17 )
  {
    Blink = -1073741670;
    goto LABEL_29;
  }
  memset(v17, 0, 0x90u);
  v19[5] = &Handle;
  v19[7] = LowLimit;
  v19[8] = a2;
  *((_DWORD *)v19 + 18) = 1245592;
  *((_DWORD *)v19 + 23) = 7;
  *((_DWORD *)v19 + 24) = 1;
  *((_DWORD *)v19 + 25) = 32;
  v19[15] = v16;
  if ( v27 )
  {
    ClientSecurityQos.Length = 12;
    ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
    *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 257;
    v25 = SeCreateClientSecurity(KeGetCurrentThread(), &ClientSecurityQos, 0, &ClientContext);
    Blink = v25;
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v25);
      }
      ExFreeToPagedLookasideList(&Lookaside, v19);
      goto LABEL_29;
    }
    v28 = 1;
    v19[17] = &ClientContext;
    memset(&LowLimit_8, 0, sizeof(LowLimit_8));
    KeInitializeEvent(&LowLimit_8, NotificationEvent, 0);
    *v19 = KeGetCurrentThread();
    v19[2] = CscStorepLowIoCreateFilePostedRoutine;
    v19[4] = &LowLimit_8;
    v19[1] = 0;
    *((_DWORD *)v19 + 6) = -1;
    v29 = KeSetKernelStackSwapEnable(0);
    Blink = CscStorepLowIoPostWorkItemAndWait(v24, v19, &LowLimit_8);
    if ( v29 )
      KeSetKernelStackSwapEnable(v29);
    if ( Blink >= 0 )
      Blink = *((_DWORD *)v19 + 6);
  }
  else
  {
    v28 = 0;
    LowLimit_8.Header.WaitListHead.Blink = 0;
    *(_QWORD *)&LowLimit_8.Header.Lock = CscStorepLowIoCreateFilePostedRoutine;
    HighLimit[0] = 0;
    LowLimit = 0;
    LowLimit_8.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v19;
    IoGetStackLimits((PULONG_PTR)&LowLimit, HighLimit);
    if ( (char *)HighLimit - (char *)LowLimit < (unsigned __int64)(unsigned int)dword_14003BD20 )
    {
      v20 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &LowLimit_8, 0x6000u, 0, 0);
      if ( v20 >= 0 )
      {
        Blink = (int)LowLimit_8.Header.WaitListHead.Blink;
        goto LABEL_26;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
          (unsigned int)v20);
      }
    }
    Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&LowLimit_8.Header.Lock)(LowLimit_8.Header.WaitListHead.Flink);
  }
LABEL_26:
  ExFreeToPagedLookasideList(&Lookaside, v19);
  if ( v28 )
    SeDeleteClientSecurity(&ClientContext);
  if ( Blink < 0 )
    goto LABEL_29;
  Blink = CscStorepLowIoDisableImplicitTimeUpdates(Handle);
  if ( Blink < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
    }
    goto LABEL_29;
  }
  *(_QWORD *)&v35 = Handle;
  v37 = 0;
  *(_OWORD *)&HighLimit[1] = a1;
  v36 = 0;
  *((_QWORD *)&v35 + 1) = a2;
  Blink = CscEnpCreateEntry(&v31, a3, (PWSTR *)&HighLimit[1]);
  if ( Blink < 0
    || ((Handle = 0, v22 = *(_DWORD *)&v31[12].Length, (v22 & 0x100000) != 0) || (*(_DWORD *)(a1 + 192) & 0x20000) != 0
      ? (v23 = v22 | 0x20000)
      : (v23 = v22 & 0xFFFDFFFF),
        *(_DWORD *)&v31[12].Length = v23,
        Blink = CscEnpQuotaRecoverEntry(v31),
        Blink < 0) )
  {
LABEL_29:
    if ( Handle )
      CscStorepLowIoClose(Handle);
    if ( Blink < 0 )
    {
      if ( v31 )
      {
        LOBYTE(v18) = 1;
        CscEnpDereferenceEntryEx((__int64)&v31, v18);
      }
    }
  }
  result = (unsigned int)Blink;
  *v13 = v31;
  return result;
}

```

## disassembly

```asm
0x14000aaf0  mov     r11, rsp
0x14000aaf3  push    rbp
0x14000aaf4  push    rsi
0x14000aaf5  push    r13
0x14000aaf7  push    r15
0x14000aaf9  lea     rbp, [r11-68h]
0x14000aafd  sub     rsp, 148h
0x14000ab04  mov     rax, cs:__security_cookie
0x14000ab0b  xor     rax, rsp
0x14000ab0e  mov     [rbp+60h+var_50], rax
0x14000ab12  mov     eax, [rcx+150h]
0x14000ab18  mov     r15, r8
0x14000ab1b  mov     [rsp+160h+LowLimit], r9
0x14000ab20  mov     rsi, rdx
0x14000ab23  mov     r13, rcx
0x14000ab26  test    al, 10h
0x14000ab28  jz      loc_14000AC32
0x14000ab2e  mov     [r11-30h], rdi
0x14000ab32  mov     rdi, [rcx+50h]
0x14000ab36  mov     [r11-38h], r12
0x14000ab3a  xor     r12d, r12d
0x14000ab3d  mov     [r11-40h], r14
0x14000ab41  lea     r14, [rcx+50h]
0x14000ab45  mov     byte ptr [rsp+160h+var_130], r12b
0x14000ab4a  mov     [r11-28h], rbx
0x14000ab4e  xchg    ax, ax
0x14000ab50  cmp     rdi, r14
0x14000ab53  jz      loc_14000AE99
0x14000ab59  lea     rbx, [rdi-60h]
0x14000ab5d  mov     r8b, 1; CaseInSensitive
0x14000ab60  lea     rcx, [rbx+30h]; String1
0x14000ab64  mov     rdx, rsi; String2
0x14000ab67  call    cs:__imp_RtlEqualUnicodeString
0x14000ab6e  nop     dword ptr [rax+rax+00h]
0x14000ab73  test    al, al
0x14000ab75  jnz     short loc_14000AB9A
0x14000ab77  lea     rcx, [rbx+40h]; String1
0x14000ab7b  mov     r8b, 1; CaseInSensitive
0x14000ab7e  mov     rdx, rsi; String2
0x14000ab81  call    cs:__imp_RtlEqualUnicodeString
0x14000ab88  nop     dword ptr [rax+rax+00h]
0x14000ab8d  test    al, al
0x14000ab8f  jnz     loc_14000AC39
0x14000ab95  mov     rdi, [rdi]
0x14000ab98  jmp     short loc_14000AB50
0x14000ab9a  xor     al, al
0x14000ab9c  test    rbx, rbx
0x14000ab9f  jz      loc_14000AF9B
0x14000aba5  mov     r8d, 1
0x14000abab  lock xadd [rbx+4], r8d
0x14000abb1  inc     r8d
0x14000abb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000abbb  lea     rdi, WPP_GLOBAL_Control
0x14000abc2  cmp     rcx, rdi
0x14000abc5  jz      loc_14000ADA4
0x14000abcb  test    dword ptr [rcx+2Ch], 40000h
0x14000abd2  jnz     loc_14000AF70
0x14000abd8  movzx   eax, byte ptr [rsp+160h+var_130]
0x14000abdd  mov     r12, rbx
0x14000abe0  test    r15, r15
0x14000abe3  jz      short loc_14000ABE8
0x14000abe5  mov     [r15], al
0x14000abe8  mov     r14, [rsp+160h+LowLimit]
0x14000abed  mov     [r14], r12
0x14000abf0  test    r12, r12
0x14000abf3  jz      short loc_14000AC44
0x14000abf5  xor     eax, eax
0x14000abf7  mov     rbx, [rsp+140h]
0x14000abff  mov     rdi, [rsp+160h+var_28]
0x14000ac07  mov     r12, [rsp+160h+var_30]
0x14000ac0f  mov     r14, [rsp+160h+var_38]
0x14000ac17  mov     rcx, [rbp+60h+var_50]
0x14000ac1b  xor     rcx, rsp; StackCookie
0x14000ac1e  call    __security_check_cookie
0x14000ac23  add     rsp, 148h
0x14000ac2a  pop     r15
0x14000ac2c  pop     r13
0x14000ac2e  pop     rsi
0x14000ac2f  pop     rbp
0x14000ac30  retn
0x14000ac32  mov     eax, 0C000003Ah
0x14000ac37  jmp     short loc_14000AC17
0x14000ac39  mov     al, 1
0x14000ac3b  mov     byte ptr [rsp+160h+var_130], al
0x14000ac3f  jmp     loc_14000AB9C
0x14000ac44  xor     eax, eax
0x14000ac46  lea     rcx, [rbp+60h+ClientContext]; void *
0x14000ac4a  mov     [rsp+160h+Handle], rax
0x14000ac4f  xorps   xmm0, xmm0
0x14000ac52  mov     [rsp+160h+var_120], rax
0x14000ac57  xor     edx, edx; Val
0x14000ac59  mov     [rbp+60h+var_C0], rax
0x14000ac5d  mov     r8d, 48h ; 'H'; Size
0x14000ac63  mov     rax, [r13+8]
0x14000ac67  movups  xmmword ptr [rsp+160h+HighLimit+8], xmm0
0x14000ac6c  movups  [rbp+60h+var_E0], xmm0
0x14000ac70  movups  [rbp+60h+var_D0], xmm0
0x14000ac74  mov     rbx, [rax+18h]
0x14000ac78  mov     rax, [r13+90h]
0x14000ac7f  mov     [rsp+160h+LowLimit], rax
0x14000ac84  xor     eax, eax
0x14000ac86  mov     qword ptr [rbp+60h+ClientSecurityQos.Length], rax
0x14000ac8a  mov     dword ptr [rbp+60h+ClientSecurityQos.ContextTrackingMode], eax
0x14000ac8d  call    memset
0x14000ac92  call    cs:__imp_KeAreAllApcsDisabled
0x14000ac99  nop     dword ptr [rax+rax+00h]
0x14000ac9e  lea     rcx, Lookaside; Lookaside
0x14000aca5  mov     byte ptr [rsp+160h+var_130], al
0x14000aca9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14000acb0  nop     dword ptr [rax+rax+00h]
0x14000acb5  mov     r12, rax
0x14000acb8  test    rax, rax
0x14000acbb  jz      loc_14000AFA3
0x14000acc1  xor     edx, edx; Val
0x14000acc3  mov     r8d, 90h; Size
0x14000acc9  mov     rcx, rax; void *
0x14000accc  call    memset
0x14000acd1  cmp     byte ptr [rsp+160h+var_130], 0
0x14000acd6  lea     rax, [rsp+160h+Handle]
0x14000acdb  mov     [r12+28h], rax
0x14000ace0  mov     rax, [rsp+160h+LowLimit]
0x14000ace5  mov     [r12+38h], rax
0x14000acea  mov     [r12+40h], rsi
0x14000acef  mov     dword ptr [r12+48h], 130198h
0x14000acf8  mov     dword ptr [r12+5Ch], 7
0x14000ad01  mov     dword ptr [r12+60h], 1
0x14000ad0a  mov     dword ptr [r12+64h], 20h ; ' '
0x14000ad13  mov     [r12+78h], rbx
0x14000ad18  jnz     loc_14000AFAD
0x14000ad1e  xor     ebx, ebx
0x14000ad20  mov     byte ptr [rsp+160h+var_130], 0
0x14000ad25  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000ad2c  mov     [rsp+160h+var_100], rbx
0x14000ad31  lea     rdx, [rsp+160h+HighLimit]; HighLimit
0x14000ad36  mov     [rsp+160h+LowLimit+8], rax
0x14000ad3b  lea     rcx, [rsp+160h+LowLimit]; LowLimit
0x14000ad40  mov     qword ptr [rsp+160h+HighLimit], rbx
0x14000ad45  mov     [rsp+160h+LowLimit], rbx
0x14000ad4a  mov     [rsp+160h+var_108], r12
0x14000ad4f  call    cs:__imp_IoGetStackLimits
0x14000ad56  nop     dword ptr [rax+rax+00h]
0x14000ad5b  mov     eax, cs:dword_14003BD20
0x14000ad61  lea     rcx, [rsp+160h+HighLimit]
0x14000ad66  sub     rcx, [rsp+160h+LowLimit]
0x14000ad6b  cmp     rcx, rax
0x14000ad6e  jnb     short loc_14000ADAC
0x14000ad70  xor     r9d, r9d; Wait
0x14000ad73  mov     [rsp+160h+Context], rbx; Context
0x14000ad78  mov     r8d, 6000h; Size
0x14000ad7e  lea     rdx, [rsp+160h+LowLimit+8]; Parameter
0x14000ad83  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x14000ad8a  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14000ad91  nop     dword ptr [rax+rax+00h]
0x14000ad96  test    eax, eax
0x14000ad98  js      loc_14000B033
0x14000ad9e  mov     ebx, dword ptr [rsp+160h+var_100]
0x14000ada2  jmp     short loc_14000ADBD
0x14000ada4  mov     r12, rbx
0x14000ada7  jmp     loc_14000ABE0
0x14000adac  mov     rcx, [rsp+160h+var_108]
0x14000adb1  mov     rax, [rsp+160h+LowLimit+8]
0x14000adb6  call    _guard_dispatch_icall
0x14000adbb  mov     ebx, eax
0x14000adbd  mov     rdx, r12; Entry
0x14000adc0  lea     rcx, Lookaside; Lookaside
0x14000adc7  call    cs:__imp_ExFreeToPagedLookasideList
0x14000adce  nop     dword ptr [rax+rax+00h]
0x14000add3  cmp     byte ptr [rsp+160h+var_130], 0
0x14000add8  jnz     loc_14000B06D
0x14000adde  test    ebx, ebx
0x14000ade0  jns     short loc_14000AE0F
0x14000ade2  mov     rcx, [rsp+160h+Handle]; Handle
0x14000ade7  test    rcx, rcx
0x14000adea  jnz     loc_14000B0B9
0x14000adf0  test    ebx, ebx
0x14000adf2  jns     short loc_14000AE00
0x14000adf4  cmp     [rsp+160h+var_120], 0
0x14000adfa  jnz     loc_14000B0C3
0x14000ae00  mov     rcx, [rsp+160h+var_120]
0x14000ae05  mov     eax, ebx
0x14000ae07  mov     [r14], rcx
0x14000ae0a  jmp     loc_14000ABF7
0x14000ae0f  mov     rcx, [rsp+160h+Handle]
0x14000ae14  call    CscStorepLowIoDisableImplicitTimeUpdates
0x14000ae19  mov     ebx, eax
0x14000ae1b  test    eax, eax
0x14000ae1d  js      loc_14000B082
0x14000ae23  mov     rax, [rsp+160h+Handle]
0x14000ae28  lea     r8, [rsp+160h+HighLimit+8]
0x14000ae2d  xor     edi, edi
0x14000ae2f  mov     qword ptr [rbp+60h+var_E0], rax
0x14000ae33  xorps   xmm0, xmm0
0x14000ae36  mov     qword ptr [rsp+160h+HighLimit+10h], rdi
0x14000ae3b  mov     rdx, r15
0x14000ae3e  mov     [rbp+60h+var_C0], rdi
0x14000ae42  lea     rcx, [rsp+160h+var_120]
0x14000ae47  mov     qword ptr [rsp+160h+HighLimit+8], r13
0x14000ae4c  movdqu  [rbp+60h+var_D0], xmm0
0x14000ae51  mov     qword ptr [rbp+60h+var_E0+8], rsi
0x14000ae55  call    CscEnpCreateEntry
0x14000ae5a  mov     ebx, eax
0x14000ae5c  test    eax, eax
0x14000ae5e  js      short loc_14000ADE2
0x14000ae60  mov     rdx, [rsp+160h+var_120]
0x14000ae65  mov     [rsp+160h+Handle], rdi
0x14000ae6a  mov     ecx, [rdx+0C0h]
0x14000ae70  bt      ecx, 14h
0x14000ae74  jnb     short loc_14000AEA7
0x14000ae76  bts     ecx, 11h
0x14000ae7a  mov     [rdx+0C0h], ecx
0x14000ae80  mov     rcx, [rsp+160h+var_120]
0x14000ae85  call    CscEnpQuotaRecoverEntry
0x14000ae8a  mov     ebx, eax
0x14000ae8c  test    eax, eax
0x14000ae8e  js      loc_14000ADE2
0x14000ae94  jmp     loc_14000AE00
0x14000ae99  xor     al, al
0x14000ae9b  lea     rdi, WPP_GLOBAL_Control
0x14000aea2  jmp     loc_14000ABE0
0x14000aea7  test    dword ptr [r13+0C0h], 20000h
0x14000aeb2  jnz     short loc_14000AE76
0x14000aeb4  btr     ecx, 11h
0x14000aeb8  jmp     short loc_14000AE7A
0x14000aeba  lea     rax, [rbp+60h+ClientContext]
0x14000aebe  mov     byte ptr [rsp+160h+var_130], 1
0x14000aec3  mov     [r12+88h], rax
0x14000aecb  lea     rcx, [rsp+160h+LowLimit+8]; Event
0x14000aed0  xor     eax, eax
0x14000aed2  xorps   xmm0, xmm0
0x14000aed5  xor     r8d, r8d; State
0x14000aed8  mov     [rsp+160h+var_100], rax
0x14000aedd  xor     edx, edx; Type
0x14000aedf  movups  xmmword ptr [rsp+160h+LowLimit+8], xmm0
0x14000aee4  call    cs:__imp_KeInitializeEvent
0x14000aeeb  nop     dword ptr [rax+rax+00h]
0x14000aef0  mov     rax, gs:188h
0x14000aef9  xor     ecx, ecx; Enable
0x14000aefb  mov     [r12], rax
0x14000aeff  lea     rax, CscStorepLowIoCreateFilePostedRoutine
0x14000af06  mov     [r12+10h], rax
0x14000af0b  lea     rax, [rsp+160h+LowLimit+8]
0x14000af10  mov     [r12+20h], rax
0x14000af15  mov     qword ptr [r12+8], 0
0x14000af1e  mov     dword ptr [r12+18h], 0FFFFFFFFh
0x14000af27  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000af2e  nop     dword ptr [rax+rax+00h]
0x14000af33  lea     r8, [rsp+160h+LowLimit+8]
0x14000af38  mov     rdx, r12
0x14000af3b  mov     byte ptr [rsp+160h+var_130+1], al
0x14000af3f  call    CscStorepLowIoPostWorkItemAndWait
0x14000af44  mov     ebx, eax
0x14000af46  movzx   eax, byte ptr [rsp+160h+var_130+1]
0x14000af4b  test    al, al
0x14000af4d  jz      short loc_14000AF5E
0x14000af4f  movzx   ecx, al; Enable
0x14000af52  call    cs:__imp_KeSetKernelStackSwapEnable
0x14000af59  nop     dword ptr [rax+rax+00h]
0x14000af5e  test    ebx, ebx
0x14000af60  js      loc_14000ADBD
0x14000af66  mov     ebx, [r12+18h]
0x14000af6b  jmp     loc_14000ADBD
0x14000af70  mov     rax, [rbp+68h]
0x14000af74  mov     edx, 21h ; '!'
0x14000af79  mov     rcx, [rcx+18h]
0x14000af7d  mov     r9, rbx
0x14000af80  mov     qword ptr [rsp+160h+var_138], rax
0x14000af85  mov     dword ptr [rsp+160h+Context], r8d
0x14000af8a  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000af91  call    WPP_SF_qdq
0x14000af96  jmp     loc_14000ABD8
0x14000af9b  mov     r12, rbx
0x14000af9e  jmp     loc_14000AE9B
0x14000afa3  mov     ebx, 0C000009Ah
0x14000afa8  jmp     loc_14000ADE2
0x14000afad  mov     [rbp+60h+ClientSecurityQos.Length], 0Ch
0x14000afb4  lea     r9, [rbp+60h+ClientContext]; ClientContext
0x14000afb8  mov     [rbp+60h+ClientSecurityQos.ImpersonationLevel], 2
0x14000afbf  lea     rdx, [rbp+60h+ClientSecurityQos]; ClientSecurityQos
0x14000afc3  mov     word ptr [rbp+60h+ClientSecurityQos.ContextTrackingMode], 101h
0x14000afc9  xor     r8d, r8d; RemoteSession
0x14000afcc  mov     rcx, gs:188h; ClientThread
0x14000afd5  call    cs:__imp_SeCreateClientSecurity
0x14000afdc  nop     dword ptr [rax+rax+00h]
0x14000afe1  mov     ebx, eax
0x14000afe3  test    eax, eax
0x14000afe5  jns     loc_14000AEBA
0x14000afeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aff2  cmp     rcx, rdi
0x14000aff5  jz      short loc_14000B018
0x14000aff7  test    dword ptr [rcx+2Ch], 20000h
0x14000affe  jz      short loc_14000B018
0x14000b000  mov     rcx, [rcx+18h]
0x14000b004  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000b00b  mov     edx, 11h
0x14000b010  mov     r9d, eax
0x14000b013  call    WPP_SF_d
0x14000b018  mov     rdx, r12; Entry
0x14000b01b  lea     rcx, Lookaside; Lookaside
0x14000b022  call    cs:__imp_ExFreeToPagedLookasideList
0x14000b029  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
