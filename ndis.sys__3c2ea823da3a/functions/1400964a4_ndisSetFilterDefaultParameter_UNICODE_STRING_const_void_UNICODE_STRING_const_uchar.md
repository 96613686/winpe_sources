# ndisSetFilterDefaultParameter(_UNICODE_STRING const *,void *,_UNICODE_STRING const *,uchar)

- ea: `0x1400964a4`
- end: `0x140096807`
- name: `?ndisSetFilterDefaultParameter@@YAHPEBU_UNICODE_STRING@@PEAX0E@Z`
- size: `867`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400961c8`

## callees

- `0x14002b980`
- `0x1400472e0`
- `0x140060a10`
- `0x1400964a4`
- `0x1400e6160`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140096600`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140096600`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140096673`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140096673`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009672b`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009672b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400966f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400966f5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400966bb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400966bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096751`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009676e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096785`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096751`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009676e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096785`

## pseudocode

```c
__int64 __fastcall ndisSetFilterDefaultParameter(
        const struct _UNICODE_STRING *a1,
        void *a2,
        const struct _UNICODE_STRING *a3,
        char a4)
{
  void *v6; // r12
  char v8; // di
  int v9; // edx
  int RegistryValues; // ebx
  unsigned int v11; // ebx
  wchar_t *ValueData; // rcx
  unsigned int i; // edi
  const WCHAR *v14; // rdx
  NTSTATUS v15; // eax
  int v16; // ecx
  char v18; // [rsp+30h] [rbp-D0h]
  ULONG Value; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING String; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING String2; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v23[36]; // [rsp+90h] [rbp-70h] BYREF

  *(_QWORD *)&String.Length = 0;
  String.Buffer = 0;
  v6 = a2;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v8 = 1;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  Value = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v18 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      1,
      96,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      v18,
      (char)a3);
  }
  memset(v23, 0, 0x118u);
  v23[2] = a3->Buffer;
  LODWORD(v23[1]) = 1;
  v23[7] = 0;
  LODWORD(v23[11]) = a4 != 0 ? 0x1000000 : 0;
  v23[9] = L"Optional";
  v23[14] = 0;
  LODWORD(v23[18]) = v23[11];
  LODWORD(v23[8]) = a4 != 0 ? 288 : 32;
  v23[10] = &String;
  LODWORD(v23[15]) = v23[8];
  v23[16] = L"Default";
  v23[17] = &DestinationString;
  v23[23] = L"Type";
  LODWORD(v23[22]) = v23[8];
  v23[24] = &String2;
  v23[21] = 0;
  LODWORD(v23[25]) = v23[11];
  v23[30] = 0;
  RegistryValues = RtlQueryRegistryValuesEx(0x40000000, v6, v23, 0, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      1,
      97,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      RegistryValues,
      a4);
  if ( RegistryValues )
  {
    v11 = -1073741823;
  }
  else
  {
    v11 = 0;
    if ( String.Buffer )
      RtlUnicodeStringToInteger(&String, 0xAu, &Value);
    if ( !Value )
    {
      ValueData = DestinationString.Buffer;
      if ( !DestinationString.Buffer )
      {
        if ( String2.Buffer )
        {
          for ( i = 0; i < 6; ++i )
          {
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&qword_1400F3C20[3 * i], &String2, 1u) )
            {
              v14 = (const WCHAR *)&qword_1400F5C08;
              if ( (unsigned int)(LODWORD(qword_1400F3C20[3 * i + 2]) - 4) <= 1 )
                goto LABEL_18;
              break;
            }
          }
        }
        v14 = L"0";
LABEL_18:
        RtlInitUnicodeString(&DestinationString, v14);
        ValueData = DestinationString.Buffer;
        v8 = 0;
      }
      v15 = RtlWriteRegistryValue(1u, a1->Buffer, a3->Buffer, 1u, ValueData, DestinationString.Length + 2);
      v16 = 0;
      if ( v15 )
        v16 = -1073741823;
      v11 = v16;
    }
  }
  if ( String.Buffer )
    ExFreePoolWithTag(String.Buffer, 0);
  if ( DestinationString.Buffer && v8 )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( String2.Buffer )
    ExFreePoolWithTag(String2.Buffer, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v9,
      1,
      98,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      (char)v6,
      (char)a3,
      v11);
  return v11;
}

```

## disassembly

```asm
0x1400964a4  mov     [rsp-8+arg_18], rbx
0x1400964a9  push    rbp
0x1400964aa  push    rsi
0x1400964ab  push    rdi
0x1400964ac  push    r12
0x1400964ae  push    r13
0x1400964b0  push    r14
0x1400964b2  push    r15
0x1400964b4  lea     rbp, [rsp-0C0h]
0x1400964bc  sub     rsp, 1C0h
0x1400964c3  mov     rax, cs:__security_cookie
0x1400964ca  xor     rax, rsp
0x1400964cd  mov     [rbp+0F0h+var_40], rax
0x1400964d4  xor     r13d, r13d
0x1400964d7  movzx   esi, r9b
0x1400964db  mov     qword ptr [rsp+1F0h+String.Length], r13
0x1400964e0  mov     r14, r8
0x1400964e3  mov     [rsp+1F0h+String.Buffer], r13
0x1400964e8  mov     r12, rdx
0x1400964eb  mov     qword ptr [rsp+1F0h+DestinationString.Length], r13
0x1400964f0  mov     r15, rcx
0x1400964f3  mov     [rsp+1F0h+DestinationString.Buffer], r13
0x1400964f8  mov     dil, 1
0x1400964fb  mov     qword ptr [rsp+1F0h+String2.Length], r13
0x140096500  mov     [rbp+0F0h+String2.Buffer], r13
0x140096504  mov     [rsp+1F0h+Value], r13d
0x140096509  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140096510  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140096517  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009651e  jz      short loc_14009654E
0x140096520  mov     rcx, cs:WPP_GLOBAL_Control
0x140096527  lea     r9d, [r13+60h]; int
0x14009652b  mov     qword ptr [rsp+1F0h+var_1B8], r8; char
0x140096530  lea     r8d, [r13+1]; int
0x140096534  mov     qword ptr [rsp+1F0h+var_1C0], rdx; char
0x140096539  mov     dl, 4; int
0x14009653b  mov     qword ptr [rsp+1F0h+ValueLength], r15; char
0x140096540  mov     rcx, [rcx+40h]; int
0x140096544  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x140096549  call    WPP_RECORDER_SF_qqq
0x14009654e  mov     al, sil
0x140096551  lea     rcx, [rbp+0F0h+var_160]; void *
0x140096555  neg     al
0x140096557  mov     r8d, 118h; Size
0x14009655d  sbb     ebx, ebx
0x14009655f  xor     edx, edx; Val
0x140096561  and     ebx, 1000000h
0x140096567  call    memset
0x14009656c  mov     rax, [r14+8]
0x140096570  lea     r8, [rbp+0F0h+var_160]
0x140096574  mov     [rbp+0F0h+var_150], rax
0x140096578  mov     rdx, r12
0x14009657b  mov     al, sil
0x14009657e  mov     [rbp+0F0h+var_158], 1
0x140096585  neg     al
0x140096587  mov     [rbp+0F0h+var_128], r13
0x14009658b  lea     rax, aOptional; "Optional"
0x140096592  mov     [rbp+0F0h+var_108], ebx
0x140096595  mov     [rbp+0F0h+var_118], rax
0x140096599  sbb     ecx, ecx
0x14009659b  and     ecx, 100h
0x1400965a1  mov     [rbp+0F0h+var_F0], r13
0x1400965a5  add     ecx, 20h ; ' '
0x1400965a8  mov     [rbp+0F0h+var_D0], ebx
0x1400965ab  lea     rax, [rsp+1F0h+String]
0x1400965b0  mov     [rbp+0F0h+var_120], ecx
0x1400965b3  mov     [rbp+0F0h+var_110], rax
0x1400965b7  xor     r9d, r9d
0x1400965ba  lea     rax, aDefault; "Default"
0x1400965c1  mov     [rbp+0F0h+var_E8], ecx
0x1400965c4  mov     [rbp+0F0h+var_E0], rax
0x1400965c8  lea     rax, [rsp+1F0h+DestinationString]
0x1400965cd  mov     [rbp+0F0h+var_D8], rax
0x1400965d1  lea     rax, aType; "Type"
0x1400965d8  mov     [rbp+0F0h+var_A8], rax
0x1400965dc  lea     rax, [rsp+1F0h+String2]
0x1400965e1  mov     [rbp+0F0h+var_B0], ecx
0x1400965e4  mov     ecx, 40000000h
0x1400965e9  mov     [rbp+0F0h+var_A0], rax
0x1400965ed  mov     [rbp+0F0h+var_B8], r13
0x1400965f1  mov     [rbp+0F0h+var_98], ebx
0x1400965f4  mov     [rbp+0F0h+var_70], r13
0x1400965fb  mov     [rsp+1F0h+ValueData], r13
0x140096600  call    cs:__imp_RtlQueryRegistryValuesEx
0x140096607  nop     dword ptr [rax+rax+00h]
0x14009660c  mov     ebx, eax
0x14009660e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140096615  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009661c  jz      short loc_14009664C
0x14009661e  mov     rcx, cs:WPP_GLOBAL_Control
0x140096625  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009662c  mov     r9d, 61h ; 'a'; int
0x140096632  mov     dword ptr [rsp+1F0h+var_1C0], esi; char
0x140096636  mov     [rsp+1F0h+ValueLength], ebx; char
0x14009663a  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x14009663f  mov     rcx, [rcx+40h]; int
0x140096643  lea     r8d, [r9-60h]; int
0x140096647  call    WPP_RECORDER_SF_dd
0x14009664c  test    ebx, ebx
0x14009664e  jz      short loc_14009665A
0x140096650  mov     ebx, 0C0000001h
0x140096655  jmp     loc_140096745
0x14009665a  mov     ebx, r13d
0x14009665d  cmp     [rsp+1F0h+String.Buffer], r13
0x140096662  jz      short loc_14009667F
0x140096664  lea     r8, [rsp+1F0h+Value]; Value
0x140096669  mov     edx, 0Ah; Base
0x14009666e  lea     rcx, [rsp+1F0h+String]; String
0x140096673  call    cs:__imp_RtlUnicodeStringToInteger
0x14009667a  nop     dword ptr [rax+rax+00h]
0x14009667f  cmp     [rsp+1F0h+Value], r13d
0x140096684  jnz     loc_140096745
0x14009668a  mov     rcx, [rsp+1F0h+DestinationString.Buffer]
0x14009668f  test    rcx, rcx
0x140096692  jnz     short loc_140096709
0x140096694  cmp     [rbp+0F0h+String2.Buffer], r13
0x140096698  jz      short loc_1400966E9
0x14009669a  mov     edi, r13d
0x14009669d  lea     rcx, qword_1400F3C20
0x1400966a4  cmp     edi, 6
0x1400966a7  jnb     short loc_1400966E9
0x1400966a9  mov     eax, edi
0x1400966ab  lea     rdx, [rsp+1F0h+String2]; String2
0x1400966b0  mov     r8b, 1; CaseInSensitive
0x1400966b3  lea     rsi, [rax+rax*2]
0x1400966b7  lea     rcx, [rcx+rsi*8]; String1
0x1400966bb  call    cs:__imp_RtlCompareUnicodeString
0x1400966c2  nop     dword ptr [rax+rax+00h]
0x1400966c7  test    eax, eax
0x1400966c9  jz      short loc_1400966CF
0x1400966cb  inc     edi
0x1400966cd  jmp     short loc_14009669D
0x1400966cf  lea     rax, qword_1400F3C20
0x1400966d6  mov     eax, [rax+rsi*8+10h]
0x1400966da  lea     rdx, qword_1400F5C08
0x1400966e1  sub     eax, 4
0x1400966e4  cmp     eax, 1
0x1400966e7  jbe     short loc_1400966F0
0x1400966e9  lea     rdx, a0; "0"
0x1400966f0  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x1400966f5  call    cs:__imp_RtlInitUnicodeString
0x1400966fc  nop     dword ptr [rax+rax+00h]
0x140096701  mov     rcx, [rsp+1F0h+DestinationString.Buffer]
0x140096706  mov     dil, r13b
0x140096709  movzx   eax, [rsp+1F0h+DestinationString.Length]
0x14009670e  mov     r9d, 1; ValueType
0x140096714  mov     r8, [r14+8]; ValueName
0x140096718  add     eax, 2
0x14009671b  mov     rdx, [r15+8]; Path
0x14009671f  mov     [rsp+1F0h+ValueLength], eax; ValueLength
0x140096723  mov     [rsp+1F0h+ValueData], rcx; ValueData
0x140096728  mov     ecx, r9d; RelativeTo
0x14009672b  call    cs:__imp_RtlWriteRegistryValue
0x140096732  nop     dword ptr [rax+rax+00h]
0x140096737  mov     ecx, ebx
0x140096739  mov     ebx, 0C0000001h
0x14009673e  test    eax, eax
0x140096740  cmovnz  ecx, ebx
0x140096743  mov     ebx, ecx
0x140096745  mov     rcx, [rsp+1F0h+String.Buffer]; P
0x14009674a  test    rcx, rcx
0x14009674d  jz      short loc_14009675D
0x14009674f  xor     edx, edx; Tag
0x140096751  call    cs:__imp_ExFreePoolWithTag
0x140096758  nop     dword ptr [rax+rax+00h]
0x14009675d  mov     rcx, [rsp+1F0h+DestinationString.Buffer]; P
0x140096762  test    rcx, rcx
0x140096765  jz      short loc_14009677A
0x140096767  test    dil, dil
0x14009676a  jz      short loc_14009677A
0x14009676c  xor     edx, edx; Tag
0x14009676e  call    cs:__imp_ExFreePoolWithTag
0x140096775  nop     dword ptr [rax+rax+00h]
0x14009677a  mov     rcx, [rbp+0F0h+String2.Buffer]; P
0x14009677e  test    rcx, rcx
0x140096781  jz      short loc_140096791
0x140096783  xor     edx, edx; Tag
0x140096785  call    cs:__imp_ExFreePoolWithTag
0x14009678c  nop     dword ptr [rax+rax+00h]
0x140096791  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140096798  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009679f  jz      short loc_1400967DA
0x1400967a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400967a8  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x1400967af  mov     dword ptr [rsp+1F0h+var_1B0], ebx; char
0x1400967b3  mov     r9d, 62h ; 'b'; int
0x1400967b9  mov     qword ptr [rsp+1F0h+var_1B8], r14; char
0x1400967be  mov     qword ptr [rsp+1F0h+var_1C0], r12; char
0x1400967c3  mov     rcx, [rcx+40h]; int
0x1400967c7  lea     r8d, [r9-61h]; int
0x1400967cb  mov     qword ptr [rsp+1F0h+ValueLength], r15; char
0x1400967d0  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x1400967d5  call    WPP_RECORDER_SF_qqqL
0x1400967da  mov     eax, ebx
0x1400967dc  mov     rcx, [rbp+0F0h+var_40]
0x1400967e3  xor     rcx, rsp; StackCookie
0x1400967e6  call    __security_check_cookie
0x1400967eb  mov     rbx, [rsp+1F0h+arg_18]
0x1400967f3  add     rsp, 1C0h
0x1400967fa  pop     r15
0x1400967fc  pop     r14
0x1400967fe  pop     r13
0x140096800  pop     r12
0x140096802  pop     rdi
0x140096803  pop     rsi
0x140096804  pop     rbp
0x140096805  retn
```
