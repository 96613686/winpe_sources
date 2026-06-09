# SetPnpFailureDescription

- ea: `0x18003a1c0`
- end: `0x18003a57c`
- name: `SetPnpFailureDescription`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180042b00`

## callees

- `0x180009778`
- `0x18000ddc8`
- `0x180020540`
- `0x1800218d0`
- `0x180021ca0`
- `0x18002204c`
- `0x180027ba0`
- `0x18003a1c0`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x18003a550`
- `ntoskrnl!IoSetDevicePropertyData` at `0x18003a550`
- `ntoskrnl!RtlFindMessage` at `0x18003a3b8`
- `ntoskrnl!RtlFindMessage` at `0x18003a3b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003a36d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003a36d`
- `ntoskrnl!ExAllocatePool2` at `0x18003a4bd`
- `ntoskrnl!ExAllocatePool2` at `0x18003a4bd`

## string_xrefs

- `0x18003a1ea`: `@System32\drivers\hidclass.sys`

## pseudocode

```c
void __fastcall SetPnpFailureDescription(_QWORD *a1, ULONG a2, __int64 a3)
{
  wchar_t *Data; // rsi
  char v6; // r15
  _UNKNOWN **v7; // rdx
  struct _DEVICE_OBJECT **v8; // rcx
  struct _DEVICE_OBJECT *v9; // r12
  __int64 v10; // rdx
  int ImageBase; // ebx
  __int64 v12; // r8
  NTSTATUS Message; // eax
  int v14; // edx
  void *v15; // rdx
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  char *v18; // rdi
  wchar_t *Pool2; // rax
  NTSTATUS v20; // eax
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  PMESSAGE_RESOURCE_ENTRY *MessageResourceEntry; // [rsp+20h] [rbp-69h]
  PVOID BaseAddress; // [rsp+50h] [rbp-39h] BYREF
  PMESSAGE_RESOURCE_ENTRY v25; // [rsp+58h] [rbp-31h] BYREF
  _OWORD v26[2]; // [rsp+60h] [rbp-29h] BYREF
  _OWORD v27[2]; // [rsp+80h] [rbp-9h]

  Data = 0;
  v25 = 0;
  BaseAddress = 0;
  v6 = 1;
  v7 = &WPP_RECORDER_INITIALIZED;
  v26[0] = *(_OWORD *)L"@System32\\drivers\\hidclass.sys";
  v26[1] = *(_OWORD *)L"2\\drivers\\hidclass.sys";
  v27[0] = *(_OWORD *)L"s\\hidclass.sys";
  *(_OWORD *)((char *)v27 + 14) = *(_OWORD *)L"ass.sys";
  if ( !a2 )
  {
    LOBYTE(ImageBase) = 0;
LABEL_13:
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = v6;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v7,
        a3,
        a1[84],
        2,
        3,
        50,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a1,
        ImageBase);
    }
LABEL_20:
    if ( !Data )
      return;
    goto LABEL_21;
  }
  v8 = *(struct _DEVICE_OBJECT ***)(*a1 + 64LL);
  v9 = *v8;
  ImageBase = GetImageBase(v8, &BaseAddress, a3, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids);
  if ( ImageBase < 0 )
  {
    LOBYTE(v10) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v10,
        v12,
        a1[84],
        2,
        3,
        48,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a1,
        ImageBase);
    TraceLoggingGetImageBaseFailed((unsigned int)ImageBase, v10, v12);
    goto LABEL_12;
  }
  Message = RtlFindMessage(BaseAddress, 0xBu, 0, a2, &v25);
  LOBYTE(ImageBase) = Message;
  if ( Message < 0 )
  {
    LOBYTE(v14) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        a3,
        a1[84],
        2,
        3,
        49,
        (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
        *a1,
        Message);
    }
    goto LABEL_12;
  }
  v15 = (void *)(v25->Length - 4LL);
  BaseAddress = v15;
  if ( (unsigned __int64)v15 <= 0xFFFFFFFE )
  {
    v16 = RtlUnalignedStringCbLengthW((STRSAFE_PCUNZWCH)v25->Text, (size_t)v15, (size_t *)&BaseAddress);
    LOBYTE(ImageBase) = v16;
    if ( v16 >= 0 )
    {
      v18 = (char *)BaseAddress + 90;
      BaseAddress = (char *)BaseAddress + 90;
      Pool2 = (wchar_t *)ExAllocatePool2(64, BaseAddress, 1130654024);
      Data = Pool2;
      if ( !Pool2 )
        goto LABEL_20;
      LODWORD(MessageResourceEntry) = a2;
      v20 = RtlStringCbPrintfW(Pool2, (size_t)v18, L"%s,#%d;%s", v26, MessageResourceEntry, v25->Text);
      LOBYTE(ImageBase) = v20;
      if ( v20 >= 0 )
      {
        v21 = RtlUnalignedStringCbLengthW(Data, (size_t)v18, (size_t *)&BaseAddress);
        LOBYTE(ImageBase) = v21;
        if ( v21 >= 0 )
        {
          v22 = IoSetDevicePropertyData(
                  v9,
                  &DEVPKEY_Device_DriverProblemDesc,
                  0,
                  0,
                  0x19u,
                  (_DWORD)BaseAddress + 2,
                  Data);
          LOBYTE(ImageBase) = v22;
          if ( v22 >= 0 )
          {
LABEL_21:
            ExFreePoolWithTag(Data, 0);
            return;
          }
          goto LABEL_12;
        }
        v17 = 3926;
      }
      else
      {
        v17 = 3917;
      }
    }
    else
    {
      v17 = 3884;
    }
    TraceLoggingStrSafeOverflow("onecore\\drivers\\input\\hid\\hidcore\\hidclass\\util.c", v17);
LABEL_12:
    v7 = &WPP_RECORDER_INITIALIZED;
    goto LABEL_13;
  }
}

```

## disassembly

```asm
0x18003a1c0  mov     [rsp-8+arg_10], rbx
0x18003a1c5  push    rbp
0x18003a1c6  push    rsi
0x18003a1c7  push    rdi
0x18003a1c8  push    r12
0x18003a1ca  push    r13
0x18003a1cc  push    r14
0x18003a1ce  push    r15
0x18003a1d0  lea     rbp, [rsp-27h]
0x18003a1d5  sub     rsp, 0B0h
0x18003a1dc  mov     rax, cs:__security_cookie
0x18003a1e3  xor     rax, rsp
0x18003a1e6  mov     [rbp+57h+var_40], rax
0x18003a1ea  movups  xmm0, xmmword ptr cs:aSystem32Driver; "@System32\\drivers\\hidclass.sys"
0x18003a1f1  mov     r14d, edx
0x18003a1f4  xor     esi, esi
0x18003a1f6  mov     [rbp+57h+var_88], 0
0x18003a1fe  mov     r13, rcx
0x18003a201  mov     [rbp+57h+BaseAddress], 0
0x18003a209  mov     r15b, 1
0x18003a20c  lea     rdx, WPP_RECORDER_INITIALIZED
0x18003a213  lea     r9, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003a21a  movups  xmm1, xmmword ptr cs:aSystem32Driver+10h; "2\\drivers\\hidclass.sys"
0x18003a221  movups  [rbp+57h+var_80], xmm0
0x18003a225  movups  xmm0, xmmword ptr cs:aSystem32Driver+20h; "s\\hidclass.sys"
0x18003a22c  movups  [rbp+57h+var_70], xmm1
0x18003a230  movups  xmm1, xmmword ptr cs:aSystem32Driver+2Eh; "ass.sys"
0x18003a237  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18003a23b  movups  xmmword ptr [rbp+57h+var_60+0Eh], xmm1
0x18003a23f  test    r14d, r14d
0x18003a242  jz      loc_18003A56B
0x18003a248  mov     rax, [rcx]
0x18003a24b  lea     rdx, [rbp+57h+BaseAddress]
0x18003a24f  mov     rcx, [rax+40h]
0x18003a253  mov     r12, [rcx]
0x18003a256  call    GetImageBase
0x18003a25b  mov     ebx, eax
0x18003a25d  test    eax, eax
0x18003a25f  jns     loc_18003A3A1
0x18003a265  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a26c  lea     rdi, WPP_GLOBAL_Control
0x18003a273  cmp     rcx, rdi
0x18003a276  jz      short loc_18003A28A
0x18003a278  mov     eax, [rcx+2Ch]
0x18003a27b  test    al, 4
0x18003a27d  jz      short loc_18003A28A
0x18003a27f  cmp     byte ptr [rcx+29h], 2
0x18003a283  jb      short loc_18003A28A
0x18003a285  mov     dl, r15b
0x18003a288  jmp     short loc_18003A28C
0x18003a28a  xor     dl, dl
0x18003a28c  lea     rax, WPP_RECORDER_INITIALIZED
0x18003a293  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003a29a  setnz   r8b
0x18003a29e  test    dl, dl
0x18003a2a0  jnz     short loc_18003A2A7
0x18003a2a2  test    r8b, r8b
0x18003a2a5  jz      short loc_18003A2E4
0x18003a2a7  mov     rax, [r13+0]
0x18003a2ab  mov     r9, [r13+2A0h]
0x18003a2b2  mov     rcx, [rcx+18h]
0x18003a2b6  mov     [rsp+0E0h+var_98], ebx
0x18003a2ba  mov     [rsp+0E0h+var_A0], rax
0x18003a2bf  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003a2c6  mov     [rsp+0E0h+var_A8], rax
0x18003a2cb  mov     word ptr [rsp+0E0h+Data], 30h ; '0'
0x18003a2d2  mov     [rsp+0E0h+Size], 3
0x18003a2da  mov     byte ptr [rsp+0E0h+MessageResourceEntry], 2
0x18003a2df  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a2e4  mov     ecx, ebx
0x18003a2e6  call    TraceLoggingGetImageBaseFailed
0x18003a2eb  lea     rdx, WPP_RECORDER_INITIALIZED
0x18003a2f2  lea     r9, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003a2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a300  cmp     rcx, rdi
0x18003a303  jz      short loc_18003A312
0x18003a305  mov     eax, [rcx+2Ch]
0x18003a308  test    al, 4
0x18003a30a  jz      short loc_18003A312
0x18003a30c  cmp     byte ptr [rcx+29h], 2
0x18003a310  jnb     short loc_18003A315
0x18003a312  xor     r15b, r15b
0x18003a315  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18003a31c  setnz   r8b
0x18003a320  test    r15b, r15b
0x18003a323  jnz     short loc_18003A32A
0x18003a325  test    r8b, r8b
0x18003a328  jz      short loc_18003A363
0x18003a32a  mov     rax, [r13+0]
0x18003a32e  mov     dl, r15b
0x18003a331  mov     rcx, [rcx+18h]
0x18003a335  mov     [rsp+0E0h+var_98], ebx
0x18003a339  mov     [rsp+0E0h+var_A0], rax
0x18003a33e  mov     [rsp+0E0h+var_A8], r9
0x18003a343  mov     r9, [r13+2A0h]
0x18003a34a  mov     word ptr [rsp+0E0h+Data], 32h ; '2'
0x18003a351  mov     [rsp+0E0h+Size], 3
0x18003a359  mov     byte ptr [rsp+0E0h+MessageResourceEntry], 2
0x18003a35e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a363  test    rsi, rsi
0x18003a366  jz      short loc_18003A379
0x18003a368  xor     edx, edx; Tag
0x18003a36a  mov     rcx, rsi; P
0x18003a36d  call    cs:__imp_ExFreePoolWithTag
0x18003a374  nop     dword ptr [rax+rax+00h]
0x18003a379  mov     rcx, [rbp+57h+var_40]
0x18003a37d  xor     rcx, rsp; StackCookie
0x18003a380  call    __security_check_cookie
0x18003a385  mov     rbx, [rsp+0E0h+arg_10]
0x18003a38d  add     rsp, 0B0h
0x18003a394  pop     r15
0x18003a396  pop     r14
0x18003a398  pop     r13
0x18003a39a  pop     r12
0x18003a39c  pop     rdi
0x18003a39d  pop     rsi
0x18003a39e  pop     rbp
0x18003a39f  retn
0x18003a3a1  mov     rcx, [rbp+57h+BaseAddress]; BaseAddress
0x18003a3a5  lea     rax, [rbp+57h+var_88]
0x18003a3a9  xor     r8d, r8d; Language
0x18003a3ac  mov     [rsp+0E0h+MessageResourceEntry], rax; MessageResourceEntry
0x18003a3b1  mov     r9d, r14d; MessageId
0x18003a3b4  lea     edx, [r8+0Bh]; Type
0x18003a3b8  call    cs:__imp_RtlFindMessage
0x18003a3bf  nop     dword ptr [rax+rax+00h]
0x18003a3c4  mov     ebx, eax
0x18003a3c6  test    eax, eax
0x18003a3c8  jns     loc_18003A456
0x18003a3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a3d5  lea     rdi, WPP_GLOBAL_Control
0x18003a3dc  cmp     rcx, rdi
0x18003a3df  jz      short loc_18003A3F3
0x18003a3e1  mov     eax, [rcx+2Ch]
0x18003a3e4  test    al, 4
0x18003a3e6  jz      short loc_18003A3F3
0x18003a3e8  cmp     byte ptr [rcx+29h], 2
0x18003a3ec  jb      short loc_18003A3F3
0x18003a3ee  mov     dl, r15b
0x18003a3f1  jmp     short loc_18003A3F5
0x18003a3f3  xor     dl, dl
0x18003a3f5  lea     rax, WPP_RECORDER_INITIALIZED
0x18003a3fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003a403  setnz   r8b
0x18003a407  test    dl, dl
0x18003a409  jnz     short loc_18003A414
0x18003a40b  test    r8b, r8b
0x18003a40e  jz      loc_18003A2EB
0x18003a414  mov     rax, [r13+0]
0x18003a418  mov     r9, [r13+2A0h]
0x18003a41f  mov     rcx, [rcx+18h]
0x18003a423  mov     [rsp+0E0h+var_98], ebx
0x18003a427  mov     [rsp+0E0h+var_A0], rax
0x18003a42c  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x18003a433  mov     [rsp+0E0h+var_A8], rax
0x18003a438  mov     word ptr [rsp+0E0h+Data], 31h ; '1'
0x18003a43f  mov     [rsp+0E0h+Size], 3
0x18003a447  mov     byte ptr [rsp+0E0h+MessageResourceEntry], 2
0x18003a44c  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003a451  jmp     loc_18003A2EB
0x18003a456  mov     rcx, [rbp+57h+var_88]
0x18003a45a  mov     eax, 0FFFFFFFEh
0x18003a45f  movzx   edx, word ptr [rcx]
0x18003a462  add     rdx, 0FFFFFFFFFFFFFFFCh; cbMax
0x18003a466  mov     [rbp+57h+BaseAddress], rdx
0x18003a46a  cmp     rdx, rax
0x18003a46d  ja      loc_18003A379
0x18003a473  add     rcx, 4; psz
0x18003a477  lea     r8, [rbp+57h+BaseAddress]; pcbLength
0x18003a47b  call    RtlUnalignedStringCbLengthW
0x18003a480  mov     ebx, eax
0x18003a482  test    eax, eax
0x18003a484  jns     short loc_18003A4A3
0x18003a486  mov     edx, 0F2Ch
0x18003a48b  lea     rcx, aOnecoreDrivers; "onecore\\drivers\\input\\hid\\hidcore\\"...
0x18003a492  call    TraceLoggingStrSafeOverflow
0x18003a497  lea     rdi, WPP_GLOBAL_Control
0x18003a49e  jmp     loc_18003A2EB
0x18003a4a3  mov     rdi, [rbp+57h+BaseAddress]
0x18003a4a7  mov     r8d, 43646948h
0x18003a4ad  add     rdi, 5Ah ; 'Z'
0x18003a4b1  mov     ecx, 40h ; '@'
0x18003a4b6  mov     rdx, rdi
0x18003a4b9  mov     [rbp+57h+BaseAddress], rdi
0x18003a4bd  call    cs:__imp_ExAllocatePool2
0x18003a4c4  nop     dword ptr [rax+rax+00h]
0x18003a4c9  mov     rsi, rax
0x18003a4cc  test    rax, rax
0x18003a4cf  jz      loc_18003A363
0x18003a4d5  mov     rcx, [rbp+57h+var_88]
0x18003a4d9  lea     r9, [rbp+57h+var_80]
0x18003a4dd  add     rcx, 4
0x18003a4e1  lea     r8, aSDS; "%s,#%d;%s"
0x18003a4e8  mov     qword ptr [rsp+0E0h+Size], rcx
0x18003a4ed  mov     rdx, rdi; cbDest
0x18003a4f0  mov     rcx, rax; pszDest
0x18003a4f3  mov     dword ptr [rsp+0E0h+MessageResourceEntry], r14d
0x18003a4f8  call    RtlStringCbPrintfW
0x18003a4fd  mov     ebx, eax
0x18003a4ff  test    eax, eax
0x18003a501  jns     short loc_18003A50A
0x18003a503  mov     edx, 0F4Dh
0x18003a508  jmp     short loc_18003A48B
0x18003a50a  lea     r8, [rbp+57h+BaseAddress]; pcbLength
0x18003a50e  mov     rdx, rdi; cbMax
0x18003a511  mov     rcx, rsi; psz
0x18003a514  call    RtlUnalignedStringCbLengthW
0x18003a519  mov     ebx, eax
0x18003a51b  test    eax, eax
0x18003a51d  jns     short loc_18003A529
0x18003a51f  mov     edx, 0F56h
0x18003a524  jmp     loc_18003A48B
0x18003a529  mov     eax, dword ptr [rbp+57h+BaseAddress]
0x18003a52c  lea     rdx, DEVPKEY_Device_DriverProblemDesc; PropertyKey
0x18003a533  add     eax, 2
0x18003a536  mov     [rsp+0E0h+Data], rsi; Data
0x18003a53b  mov     [rsp+0E0h+Size], eax; Size
0x18003a53f  xor     r9d, r9d; Flags
0x18003a542  xor     r8d, r8d; Lcid
0x18003a545  mov     dword ptr [rsp+0E0h+MessageResourceEntry], 19h; Type
0x18003a54d  mov     rcx, r12; Pdo
0x18003a550  call    cs:__imp_IoSetDevicePropertyData
0x18003a557  nop     dword ptr [rax+rax+00h]
0x18003a55c  mov     ebx, eax
0x18003a55e  test    eax, eax
0x18003a560  jns     loc_18003A368
0x18003a566  jmp     loc_18003A497
0x18003a56b  mov     ebx, 80000000h
0x18003a570  lea     rdi, WPP_GLOBAL_Control
0x18003a577  jmp     loc_18003A2F9
```
