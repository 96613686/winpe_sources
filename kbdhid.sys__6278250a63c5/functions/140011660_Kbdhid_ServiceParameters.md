# Kbdhid_ServiceParameters

- ea: `0x140011660`
- end: `0x140011876`
- name: `Kbdhid_ServiceParameters`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140011168`

## callees

- `0x140005c9c`
- `0x140007130`
- `0x140007170`
- `0x140007540`
- `0x14001130c`
- `0x140011660`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400117d2`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400117d2`
- `ntoskrnl!ZwClose` at `0x14001184a`
- `ntoskrnl!ZwClose` at `0x14001184a`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400117f3`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400116bc`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400116bc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400117c1`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400117c1`

## string_xrefs

- `0x140011791`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
NTSTATUS __fastcall Kbdhid_ServiceParameters(__int64 a1, const WCHAR *a2)
{
  NTSTATUS result; // eax
  int v4; // edx
  HANDLE v5; // rbx
  PVOID SystemRoutineAddress; // rax
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+3Ch] [rbp-C4h] BYREF
  int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v15[28]; // [rsp+60h] [rbp-A0h] BYREF

  Handle = 0;
  v11 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 1;
  v7 = 1;
  v12 = 0;
  result = IoOpenDriverRegistryKey(a1, 0, 131097, 0);
  if ( result >= 0 )
  {
    memset(v15, 0, sizeof(v15));
    v5 = Handle;
    v15[2] = L"BreakOnSysRq";
    LODWORD(v15[4]) = 67108868;
    LODWORD(v15[6]) = 4;
    LODWORD(v15[11]) = 67108868;
    v15[3] = &v7;
    LODWORD(v15[13]) = 4;
    v15[5] = &v10;
    v15[9] = L"CrashOnCtrlScroll";
    v15[10] = &v8;
    v15[12] = &v11;
    v15[16] = L"DisableAutoRepeat";
    v15[17] = &v9;
    LODWORD(v15[18]) = 67108868;
    LODWORD(v15[20]) = 4;
    v15[19] = &v12;
    LODWORD(v15[1]) = 288;
    LODWORD(v15[8]) = 288;
    LODWORD(v15[15]) = 288;
    v15[21] = 0;
    LODWORD(v15[22]) = 0;
    v15[23] = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    result = ((__int64 (__fastcall *)(__int64, HANDLE, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
               3221225472LL,
               v5,
               v15,
               0,
               0);
    if ( result >= 0 )
    {
      BYTE4(WPP_MAIN_CB.Queue.Wcb.DeviceContext) = v7 != 0;
      if ( v8 )
      {
        WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = 2;
        *((_WORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 2) = 70;
      }
      else
      {
        result = KbdHidCrashDump(a2);
      }
      *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 6) = v9 != 0;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 3;
    result = WPP_RECORDER_SF_d(WPP_GLOBAL_Control->DeviceExtension, v4, 6, 10, (unsigned int)&Handle, result);
  }
  if ( Handle )
    return ZwClose(Handle);
  return result;
}

```

## disassembly

```asm
0x140011660  mov     [rsp-8+arg_10], rbx
0x140011665  push    rbp
0x140011666  push    rsi
0x140011667  push    rdi
0x140011668  lea     rbp, [rsp-50h]
0x14001166d  sub     rsp, 150h
0x140011674  mov     rax, cs:__security_cookie
0x14001167b  xor     rax, rsp
0x14001167e  mov     [rbp+60h+var_20], rax
0x140011682  xor     esi, esi
0x140011684  mov     rdi, rdx
0x140011687  xor     r9d, r9d
0x14001168a  mov     [rsp+160h+Handle], rsi
0x14001168f  xor     edx, edx
0x140011691  mov     [rsp+160h+var_120], esi
0x140011695  mov     r8d, 20019h
0x14001169b  mov     [rsp+160h+var_12C], esi
0x14001169f  lea     eax, [rsi+1]
0x1400116a2  mov     [rsp+160h+var_128], esi
0x1400116a6  mov     [rsp+160h+var_124], eax
0x1400116aa  mov     [rsp+160h+var_130], eax
0x1400116ae  lea     rax, [rsp+160h+Handle]
0x1400116b3  mov     [rsp+160h+var_140], rax
0x1400116b8  mov     [rsp+160h+var_11C], esi
0x1400116bc  call    cs:__imp_IoOpenDriverRegistryKey
0x1400116c3  nop     dword ptr [rax+rax+00h]
0x1400116c8  test    eax, eax
0x1400116ca  jns     short loc_140011703
0x1400116cc  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400116d3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400116da  jz      loc_140011840
0x1400116e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400116e7  lea     r9d, [rsi+0Ah]
0x1400116eb  lea     r8d, [rsi+6]
0x1400116ef  mov     [rsp+160h+var_138], eax
0x1400116f3  mov     dl, 3
0x1400116f5  mov     rcx, [rcx+40h]
0x1400116f9  call    WPP_RECORDER_SF_d
0x1400116fe  jmp     loc_140011840
0x140011703  xor     edx, edx; Val
0x140011705  lea     rcx, [rsp+160h+var_100]; void *
0x14001170a  mov     r8d, 0E0h; Size
0x140011710  call    memset
0x140011715  mov     rbx, [rsp+160h+Handle]
0x14001171a  lea     rax, aBreakonsysrq; "BreakOnSysRq"
0x140011721  mov     [rsp+160h+var_F0], rax
0x140011726  mov     edx, 4000004h
0x14001172b  mov     ecx, 4
0x140011730  mov     [rbp+60h+var_E0], edx
0x140011733  mov     r8d, 120h
0x140011739  mov     [rbp+60h+var_D0], ecx
0x14001173c  lea     rax, [rsp+160h+var_130]
0x140011741  mov     [rbp+60h+var_A8], edx
0x140011744  mov     [rsp+160h+var_E8], rax
0x140011749  xorps   xmm0, xmm0
0x14001174c  lea     rax, [rsp+160h+var_124]
0x140011751  mov     [rbp+60h+var_98], ecx
0x140011754  mov     [rbp+60h+var_D8], rax
0x140011758  lea     rax, aCrashonctrlscr; "CrashOnCtrlScroll"
0x14001175f  mov     [rbp+60h+var_B8], rax
0x140011763  lea     rax, [rsp+160h+var_12C]
0x140011768  mov     [rbp+60h+var_B0], rax
0x14001176c  lea     rax, [rsp+160h+var_120]
0x140011771  mov     [rbp+60h+var_A0], rax
0x140011775  lea     rax, aDisableautorep; "DisableAutoRepeat"
0x14001177c  mov     [rbp+60h+var_80], rax
0x140011780  lea     rax, [rsp+160h+var_128]
0x140011785  mov     [rbp+60h+var_78], rax
0x140011789  lea     rax, [rsp+160h+var_11C]
0x14001178e  mov     [rbp+60h+var_70], edx
0x140011791  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140011798  mov     [rbp+60h+var_60], ecx
0x14001179b  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x1400117a0  mov     [rbp+60h+var_68], rax
0x1400117a4  mov     [rsp+160h+var_F8], r8d
0x1400117a9  mov     [rbp+60h+var_C0], r8d
0x1400117ad  mov     [rbp+60h+var_88], r8d
0x1400117b1  mov     [rbp+60h+var_58], rsi
0x1400117b5  mov     [rbp+60h+var_50], esi
0x1400117b8  mov     [rbp+60h+var_48], rsi
0x1400117bc  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x1400117c1  call    cs:__imp_RtlInitUnicodeString
0x1400117c8  nop     dword ptr [rax+rax+00h]
0x1400117cd  lea     rcx, [rsp+160h+DestinationString]; SystemRoutineName
0x1400117d2  call    cs:__imp_MmGetSystemRoutineAddress
0x1400117d9  nop     dword ptr [rax+rax+00h]
0x1400117de  lea     r8, [rsp+160h+var_100]
0x1400117e3  mov     [rsp+160h+var_140], rsi
0x1400117e8  test    rax, rax
0x1400117eb  mov     rdx, rbx
0x1400117ee  mov     ecx, 0C0000000h
0x1400117f3  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400117fb  xor     r9d, r9d
0x1400117fe  call    _guard_dispatch_icall
0x140011803  test    eax, eax
0x140011805  js      short loc_140011840
0x140011807  cmp     [rsp+160h+var_130], esi
0x14001180b  setnz   byte ptr cs:WPP_MAIN_CB.Queue+24h
0x140011812  cmp     [rsp+160h+var_12C], esi
0x140011816  jz      short loc_14001182D
0x140011818  mov     dword ptr cs:WPP_MAIN_CB.Queue+28h, 2
0x140011822  mov     word ptr cs:WPP_MAIN_CB.Queue+2Ch, 46h ; 'F'
0x14001182b  jmp     short loc_140011835
0x14001182d  mov     rcx, rdi; Source
0x140011830  call    KbdHidCrashDump
0x140011835  cmp     [rsp+160h+var_128], esi
0x140011839  setnz   byte ptr cs:WPP_MAIN_CB.Queue+2Eh
0x140011840  mov     rcx, [rsp+160h+Handle]; Handle
0x140011845  test    rcx, rcx
0x140011848  jz      short loc_140011856
0x14001184a  call    cs:__imp_ZwClose
0x140011851  nop     dword ptr [rax+rax+00h]
0x140011856  mov     rcx, [rbp+60h+var_20]
0x14001185a  xor     rcx, rsp; StackCookie
0x14001185d  call    __security_check_cookie
0x140011862  mov     rbx, [rsp+160h+arg_10]
0x14001186a  add     rsp, 150h
0x140011871  pop     rdi
0x140011872  pop     rsi
0x140011873  pop     rbp
0x140011874  retn
```
