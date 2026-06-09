# KbdHidCrashDump

- ea: `0x14001130c`
- end: `0x140011658`
- name: `KbdHidCrashDump`
- size: `844`
- prototype: `__int64 __fastcall(PCWSTR Source)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140011660`

## callees

- `0x140007170`
- `0x14001130c`
- `0x14001187c`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001158f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001158f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011622`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011638`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011622`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011638`
- `ntoskrnl!ExAllocatePool2` at `0x140011448`
- `ntoskrnl!ExAllocatePool2` at `0x140011498`
- `ntoskrnl!ExAllocatePool2` at `0x140011448`
- `ntoskrnl!ExAllocatePool2` at `0x140011498`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400115ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011466`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001157f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140011466`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001157f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400114bb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400114da`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400114bb`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400114da`

## string_xrefs

- `0x14001155b`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall KbdHidCrashDump(PCWSTR Source)
{
  __int64 Pool2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rdx
  PWSTR Buffer; // r8
  PWSTR v6; // rbx
  PVOID SystemRoutineAddress; // rax
  ULONG v8; // ecx
  unsigned int v9; // eax
  _DWORD v10[16]; // [rsp+30h] [rbp-79h]
  __int64 v11; // [rsp+70h] [rbp-39h]
  int v12; // [rsp+78h] [rbp-31h]
  int v13; // [rsp+7Ch] [rbp-2Dh]
  int v14; // [rsp+80h] [rbp-29h]
  int v15; // [rsp+84h] [rbp-25h]
  int v16; // [rsp+88h] [rbp-21h]
  int v17; // [rsp+8Ch] [rbp-1Dh]
  _DWORD v18[4]; // [rsp+90h] [rbp-19h] BYREF
  _WORD v19[8]; // [rsp+A0h] [rbp-9h] BYREF
  int v20; // [rsp+B0h] [rbp+7h]
  __int16 v21; // [rsp+B4h] [rbp+Bh]
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp+17h] BYREF
  ULONG v23; // [rsp+D0h] [rbp+27h] BYREF
  struct _UNICODE_STRING SystemRoutineName; // [rsp+D8h] [rbp+2Fh] BYREF
  int v25; // [rsp+118h] [rbp+6Fh] BYREF
  int v26; // [rsp+120h] [rbp+77h] BYREF
  unsigned int v27; // [rsp+128h] [rbp+7Fh] BYREF

  v10[0] = 50473216;
  v25 = 0;
  DestinationString = 0;
  v23 = 0;
  v26 = 0;
  v27 = 0;
  v10[1] = 117835012;
  v10[2] = 185207048;
  v10[3] = 243076364;
  v10[4] = 303108111;
  v10[5] = 370480147;
  v10[6] = 437852183;
  v10[7] = 507117595;
  v10[8] = 572596255;
  v10[9] = 639968291;
  v10[10] = 472590375;
  v10[11] = 757858346;
  v10[12] = 825241390;
  v10[13] = 892613426;
  v10[14] = 1914483;
  v10[15] = 12073272;
  v11 = 157;
  v12 = -771751936;
  v13 = -889192237;
  v14 = -939470905;
  v15 = 13748688;
  v16 = 1195756800;
  v17 = -1258270901;
  strcpy((char *)v18, "HLPR7IMQSJN");
  v18[3] = 65692;
  strcpy((char *)v19, ";<=>?@ABCDWX");
  HIBYTE(v19[6]) = 70;
  v19[7] = 0;
  v20 = 2063597568;
  v21 = 28793;
  if ( (unsigned __int8)Kbdhid_ShouldEnableDefaultCrashHotkey() )
  {
    v25 = 17;
    v26 = 1;
  }
  DestinationString.Buffer = 0;
  Pool2 = ExAllocatePool2(256, 168, 1214538315);
  if ( Pool2 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    v3 = -1;
    do
      ++v3;
    while ( Source[v3] );
    v4 = (unsigned __int16)(2 * (v3 + 12));
    DestinationString.MaximumLength = v4;
    DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v4, 1214538315);
    Buffer = DestinationString.Buffer;
    if ( !DestinationString.Buffer )
      goto LABEL_15;
    if ( RtlAppendUnicodeToString(&DestinationString, Source) >= 0
      && RtlAppendUnicodeToString(&DestinationString, L"\\Crashdump") >= 0
      && DestinationString.MaximumLength >= (unsigned __int64)DestinationString.Length + 2 )
    {
      SystemRoutineName = 0;
      DestinationString.Buffer[((unsigned __int64)DestinationString.Length >> 1) + 1] = 0;
      *(_DWORD *)(Pool2 + 8) = 288;
      *(_QWORD *)(Pool2 + 16) = L"Dump1Keys";
      *(_QWORD *)(Pool2 + 24) = &v23;
      *(_QWORD *)(Pool2 + 40) = &v25;
      *(_QWORD *)(Pool2 + 72) = L"Dump2Key";
      *(_QWORD *)(Pool2 + 80) = &v27;
      *(_DWORD *)(Pool2 + 32) = 67108868;
      *(_DWORD *)(Pool2 + 64) = 288;
      *(_DWORD *)(Pool2 + 88) = 67108868;
      *(_QWORD *)(Pool2 + 96) = &v26;
      *(_DWORD *)(Pool2 + 48) = 4;
      *(_DWORD *)(Pool2 + 104) = 4;
      v6 = DestinationString.Buffer;
      RtlInitUnicodeString(&SystemRoutineName, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&SystemRoutineName);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      if ( ((int (__fastcall *)(__int64, PWSTR, __int64, _QWORD, _QWORD))SystemRoutineAddress)(
             0x80000000LL,
             v6,
             Pool2,
             0,
             0) >= 0 )
      {
        v8 = v23;
        Buffer = DestinationString.Buffer;
        v9 = v27;
        goto LABEL_16;
      }
    }
  }
  Buffer = DestinationString.Buffer;
LABEL_15:
  v9 = v26;
  v8 = v25;
  v27 = v26;
LABEL_16:
  WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = v8;
  if ( v8 )
  {
    if ( v9 == 124 )
    {
      *((_WORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 2) = 21687;
    }
    else
    {
      if ( v9 > 0x85 )
        *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) = 0;
      else
        *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 4) = *((_BYTE *)v10 + (int)v9);
      *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters + 5) = 0;
    }
  }
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0);
  if ( Pool2 )
    ExFreePoolWithTag((PVOID)Pool2, 0);
}

```

## disassembly

```asm
0x14001130c  mov     [rsp-8+arg_0], rbx
0x140011311  push    rbp
0x140011312  push    rsi
0x140011313  push    rdi
0x140011314  lea     rbp, [rsp-47h]
0x140011319  sub     rsp, 0F0h
0x140011320  xor     esi, esi
0x140011322  mov     [rbp+57h+var_D0], 3022900h
0x140011329  xorps   xmm0, xmm0
0x14001132c  mov     [rbp+57h+arg_8], esi
0x14001132f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140011333  mov     [rbp+57h+var_30], esi
0x140011336  mov     rbx, rcx
0x140011339  mov     [rbp+57h+arg_10], esi
0x14001133c  mov     [rbp+57h+arg_18], esi
0x14001133f  mov     [rbp+57h+var_CC], 7060504h
0x140011346  mov     [rbp+57h+var_C8], 0B0A0908h
0x14001134d  mov     [rbp+57h+var_C4], 0E7D0D0Ch
0x140011354  mov     [rbp+57h+var_C0], 1211100Fh
0x14001135b  mov     [rbp+57h+var_BC], 16151413h
0x140011362  mov     [rbp+57h+var_B8], 1A191817h
0x140011369  mov     [rbp+57h+var_B4], 1E3A001Bh
0x140011370  mov     [rbp+57h+var_B0], 2221201Fh
0x140011377  mov     [rbp+57h+var_AC], 26252423h
0x14001137e  mov     [rbp+57h+var_A8], 1C2B2827h
0x140011385  mov     [rbp+57h+var_A4], 2D2C002Ah
0x14001138c  mov     [rbp+57h+var_A0], 31302F2Eh
0x140011393  mov     [rbp+57h+var_9C], 35343332h
0x14001139a  mov     [rbp+57h+var_98], 1D3673h
0x1400113a1  mov     [rbp+57h+var_94], 0B83938h
0x1400113a8  mov     [rbp+57h+var_90], 9Dh
0x1400113b0  mov     [rbp+57h+var_88], 0D2000000h
0x1400113b7  mov     [rbp+57h+var_84], 0CB0000D3h
0x1400113be  mov     [rbp+57h+var_80], 0C800CFC7h
0x1400113c5  mov     [rbp+57h+var_7C], 0D1C9D0h
0x1400113cc  mov     [rbp+57h+var_78], 4745CD00h
0x1400113d3  mov     [rbp+57h+var_74], 0B5004F4Bh
0x1400113da  mov     dword ptr [rbp+57h+var_70], 52504C48h
0x1400113e1  mov     dword ptr [rbp+57h+var_70+4], 514D4937h
0x1400113e8  mov     dword ptr [rbp+57h+var_70+8], 4E4A53h
0x1400113ef  mov     dword ptr [rbp+57h+var_70+0Ch], 1009Ch
0x1400113f6  mov     dword ptr [rbp+57h+var_60], 3E3D3C3Bh
0x1400113fd  mov     dword ptr [rbp+57h+var_60+4], 4241403Fh
0x140011404  mov     dword ptr [rbp+57h+var_60+8], 58574443h
0x14001140b  mov     dword ptr [rbp+57h+var_60+0Ch], 4600h
0x140011412  mov     [rbp+57h+var_50], 7B000000h
0x140011419  mov     [rbp+57h+var_4C], 7079h
0x14001141f  call    Kbdhid_ShouldEnableDefaultCrashHotkey
0x140011424  test    al, al
0x140011426  jz      short loc_140011436
0x140011428  mov     [rbp+57h+arg_8], 11h
0x14001142f  mov     [rbp+57h+arg_10], 1
0x140011436  mov     edx, 0A8h
0x14001143b  mov     [rbp+57h+DestinationString.Buffer], rsi
0x14001143f  mov     r8d, 4864624Bh
0x140011445  lea     ecx, [rdx+58h]
0x140011448  call    cs:__imp_ExAllocatePool2
0x14001144f  nop     dword ptr [rax+rax+00h]
0x140011454  mov     rdi, rax
0x140011457  test    rax, rax
0x14001145a  jz      loc_1400115CE
0x140011460  xor     edx, edx; SourceString
0x140011462  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140011466  call    cs:__imp_RtlInitUnicodeString
0x14001146d  nop     dword ptr [rax+rax+00h]
0x140011472  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140011476  inc     rdx
0x140011479  cmp     [rbx+rdx*2], si
0x14001147d  jnz     short loc_140011476
0x14001147f  add     dx, 0Ch
0x140011483  mov     ecx, 100h
0x140011488  add     dx, dx
0x14001148b  mov     r8d, 4864624Bh
0x140011491  movzx   edx, dx
0x140011494  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140011498  call    cs:__imp_ExAllocatePool2
0x14001149f  nop     dword ptr [rax+rax+00h]
0x1400114a4  mov     [rbp+57h+DestinationString.Buffer], rax
0x1400114a8  mov     r8, rax
0x1400114ab  test    rax, rax
0x1400114ae  jz      loc_1400115D2
0x1400114b4  mov     rdx, rbx; Source
0x1400114b7  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400114bb  call    cs:__imp_RtlAppendUnicodeToString
0x1400114c2  nop     dword ptr [rax+rax+00h]
0x1400114c7  test    eax, eax
0x1400114c9  js      loc_1400115CE
0x1400114cf  lea     rdx, Source; "\\Crashdump"
0x1400114d6  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1400114da  call    cs:__imp_RtlAppendUnicodeToString
0x1400114e1  nop     dword ptr [rax+rax+00h]
0x1400114e6  test    eax, eax
0x1400114e8  js      loc_1400115CE
0x1400114ee  movzx   edx, [rbp+57h+DestinationString.Length]
0x1400114f2  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x1400114f6  lea     rcx, [rdx+2]
0x1400114fa  cmp     rax, rcx
0x1400114fd  jb      loc_1400115CE
0x140011503  mov     rax, [rbp+57h+DestinationString.Buffer]
0x140011507  mov     ecx, 4000004h
0x14001150c  shr     rdx, 1
0x14001150f  xorps   xmm0, xmm0
0x140011512  movups  xmmword ptr [rbp+57h+SystemRoutineName.Length], xmm0
0x140011516  mov     [rax+rdx*2+2], si
0x14001151b  mov     edx, 120h
0x140011520  mov     [rdi+8], edx
0x140011523  lea     rax, aDump1keys; "Dump1Keys"
0x14001152a  mov     [rdi+10h], rax
0x14001152e  lea     rax, [rbp+57h+var_30]
0x140011532  mov     [rdi+18h], rax
0x140011536  lea     rax, [rbp+57h+arg_8]
0x14001153a  mov     [rdi+28h], rax
0x14001153e  lea     rax, aDump2key; "Dump2Key"
0x140011545  mov     [rdi+48h], rax
0x140011549  lea     rax, [rbp+57h+arg_18]
0x14001154d  mov     [rdi+50h], rax
0x140011551  lea     rax, [rbp+57h+arg_10]
0x140011555  mov     [rdi+20h], ecx
0x140011558  mov     [rdi+40h], edx
0x14001155b  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140011562  mov     [rdi+58h], ecx
0x140011565  lea     rcx, [rbp+57h+SystemRoutineName]; DestinationString
0x140011569  mov     [rdi+60h], rax
0x14001156d  mov     dword ptr [rdi+30h], 4
0x140011574  mov     dword ptr [rdi+68h], 4
0x14001157b  mov     rbx, [rbp+57h+DestinationString.Buffer]
0x14001157f  call    cs:__imp_RtlInitUnicodeString
0x140011586  nop     dword ptr [rax+rax+00h]
0x14001158b  lea     rcx, [rbp+57h+SystemRoutineName]; SystemRoutineName
0x14001158f  call    cs:__imp_MmGetSystemRoutineAddress
0x140011596  nop     dword ptr [rax+rax+00h]
0x14001159b  mov     r8, rdi
0x14001159e  mov     [rsp+100h+var_E0], rsi
0x1400115a3  test    rax, rax
0x1400115a6  mov     rdx, rbx
0x1400115a9  mov     ecx, 80000000h
0x1400115ae  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400115b6  xor     r9d, r9d
0x1400115b9  call    _guard_dispatch_icall
0x1400115be  test    eax, eax
0x1400115c0  js      short loc_1400115CE
0x1400115c2  mov     ecx, [rbp+57h+var_30]
0x1400115c5  mov     r8, [rbp+57h+DestinationString.Buffer]
0x1400115c9  mov     eax, [rbp+57h+arg_18]
0x1400115cc  jmp     short loc_1400115DB
0x1400115ce  mov     r8, [rbp+57h+DestinationString.Buffer]
0x1400115d2  mov     eax, [rbp+57h+arg_10]
0x1400115d5  mov     ecx, [rbp+57h+arg_8]
0x1400115d8  mov     [rbp+57h+arg_18], eax
0x1400115db  mov     dword ptr cs:WPP_MAIN_CB.Queue+28h, ecx
0x1400115e1  test    ecx, ecx
0x1400115e3  jz      short loc_140011618
0x1400115e5  cmp     eax, 7Ch ; '|'
0x1400115e8  jnz     short loc_1400115F5
0x1400115ea  mov     word ptr cs:WPP_MAIN_CB.Queue+2Ch, 54B7h
0x1400115f3  jmp     short loc_140011618
0x1400115f5  cmp     eax, 85h
0x1400115fa  ja      short loc_14001160A
0x1400115fc  cdqe
0x1400115fe  mov     cl, byte ptr [rbp+rax+57h+var_D0]
0x140011602  mov     byte ptr cs:WPP_MAIN_CB.Queue+2Ch, cl
0x140011608  jmp     short loc_140011611
0x14001160a  mov     byte ptr cs:WPP_MAIN_CB.Queue+2Ch, sil
0x140011611  mov     byte ptr cs:WPP_MAIN_CB.Queue+2Dh, sil
0x140011618  test    r8, r8
0x14001161b  jz      short loc_14001162E
0x14001161d  xor     edx, edx; Tag
0x14001161f  mov     rcx, r8; P
0x140011622  call    cs:__imp_ExFreePoolWithTag
0x140011629  nop     dword ptr [rax+rax+00h]
0x14001162e  test    rdi, rdi
0x140011631  jz      short loc_140011644
0x140011633  xor     edx, edx; Tag
0x140011635  mov     rcx, rdi; P
0x140011638  call    cs:__imp_ExFreePoolWithTag
0x14001163f  nop     dword ptr [rax+rax+00h]
0x140011644  mov     rbx, [rsp+100h+arg_0]
0x14001164c  add     rsp, 0F0h
0x140011653  pop     rdi
0x140011654  pop     rsi
0x140011655  pop     rbp
0x140011656  retn
```
