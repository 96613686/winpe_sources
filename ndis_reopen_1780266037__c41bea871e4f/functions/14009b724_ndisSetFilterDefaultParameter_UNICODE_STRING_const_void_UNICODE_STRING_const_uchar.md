# ndisSetFilterDefaultParameter(_UNICODE_STRING const *,void *,_UNICODE_STRING const *,uchar)

- ea: `0x14009b724`
- end: `0x14009ba87`
- name: `?ndisSetFilterDefaultParameter@@YAHPEBU_UNICODE_STRING@@PEAX0E@Z`
- size: `867`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14009b448`

## callees

- `0x14001fa30`
- `0x14004bc60`
- `0x140065890`
- `0x14009b724`
- `0x1400eb380`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14009b880`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14009b880`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14009b8f3`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14009b8f3`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b9ab`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14009b9ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b975`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b975`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14009b93b`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14009b93b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b9d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b9ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009ba05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b9d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b9ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009ba05`

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
            if ( !RtlCompareUnicodeString((PCUNICODE_STRING)&qword_1400F8C40[3 * i], &String2, 1u) )
            {
              v14 = (const WCHAR *)&qword_1400FAC18;
              if ( (unsigned int)(LODWORD(qword_1400F8C40[3 * i + 2]) - 4) <= 1 )
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
0x14009b724  mov     [rsp-8+arg_18], rbx
0x14009b729  push    rbp
0x14009b72a  push    rsi
0x14009b72b  push    rdi
0x14009b72c  push    r12
0x14009b72e  push    r13
0x14009b730  push    r14
0x14009b732  push    r15
0x14009b734  lea     rbp, [rsp-0C0h]
0x14009b73c  sub     rsp, 1C0h
0x14009b743  mov     rax, cs:__security_cookie
0x14009b74a  xor     rax, rsp
0x14009b74d  mov     [rbp+0F0h+var_40], rax
0x14009b754  xor     r13d, r13d
0x14009b757  movzx   esi, r9b
0x14009b75b  mov     qword ptr [rsp+1F0h+String.Length], r13
0x14009b760  mov     r14, r8
0x14009b763  mov     [rsp+1F0h+String.Buffer], r13
0x14009b768  mov     r12, rdx
0x14009b76b  mov     qword ptr [rsp+1F0h+DestinationString.Length], r13
0x14009b770  mov     r15, rcx
0x14009b773  mov     [rsp+1F0h+DestinationString.Buffer], r13
0x14009b778  mov     dil, 1
0x14009b77b  mov     qword ptr [rsp+1F0h+String2.Length], r13
0x14009b780  mov     [rbp+0F0h+String2.Buffer], r13
0x14009b784  mov     [rsp+1F0h+Value], r13d
0x14009b789  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009b790  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14009b797  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009b79e  jz      short loc_14009B7CE
0x14009b7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b7a7  lea     r9d, [r13+60h]; int
0x14009b7ab  mov     qword ptr [rsp+1F0h+var_1B8], r8; char
0x14009b7b0  lea     r8d, [r13+1]; int
0x14009b7b4  mov     qword ptr [rsp+1F0h+var_1C0], rdx; char
0x14009b7b9  mov     dl, 4; int
0x14009b7bb  mov     qword ptr [rsp+1F0h+ValueLength], r15; char
0x14009b7c0  mov     rcx, [rcx+40h]; int
0x14009b7c4  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x14009b7c9  call    WPP_RECORDER_SF_qqq
0x14009b7ce  mov     al, sil
0x14009b7d1  lea     rcx, [rbp+0F0h+var_160]; void *
0x14009b7d5  neg     al
0x14009b7d7  mov     r8d, 118h; Size
0x14009b7dd  sbb     ebx, ebx
0x14009b7df  xor     edx, edx; Val
0x14009b7e1  and     ebx, 1000000h
0x14009b7e7  call    memset
0x14009b7ec  mov     rax, [r14+8]
0x14009b7f0  lea     r8, [rbp+0F0h+var_160]
0x14009b7f4  mov     [rbp+0F0h+var_150], rax
0x14009b7f8  mov     rdx, r12
0x14009b7fb  mov     al, sil
0x14009b7fe  mov     [rbp+0F0h+var_158], 1
0x14009b805  neg     al
0x14009b807  mov     [rbp+0F0h+var_128], r13
0x14009b80b  lea     rax, aOptional; "Optional"
0x14009b812  mov     [rbp+0F0h+var_108], ebx
0x14009b815  mov     [rbp+0F0h+var_118], rax
0x14009b819  sbb     ecx, ecx
0x14009b81b  and     ecx, 100h
0x14009b821  mov     [rbp+0F0h+var_F0], r13
0x14009b825  add     ecx, 20h ; ' '
0x14009b828  mov     [rbp+0F0h+var_D0], ebx
0x14009b82b  lea     rax, [rsp+1F0h+String]
0x14009b830  mov     [rbp+0F0h+var_120], ecx
0x14009b833  mov     [rbp+0F0h+var_110], rax
0x14009b837  xor     r9d, r9d
0x14009b83a  lea     rax, aDefault; "Default"
0x14009b841  mov     [rbp+0F0h+var_E8], ecx
0x14009b844  mov     [rbp+0F0h+var_E0], rax
0x14009b848  lea     rax, [rsp+1F0h+DestinationString]
0x14009b84d  mov     [rbp+0F0h+var_D8], rax
0x14009b851  lea     rax, aType; "Type"
0x14009b858  mov     [rbp+0F0h+var_A8], rax
0x14009b85c  lea     rax, [rsp+1F0h+String2]
0x14009b861  mov     [rbp+0F0h+var_B0], ecx
0x14009b864  mov     ecx, 40000000h
0x14009b869  mov     [rbp+0F0h+var_A0], rax
0x14009b86d  mov     [rbp+0F0h+var_B8], r13
0x14009b871  mov     [rbp+0F0h+var_98], ebx
0x14009b874  mov     [rbp+0F0h+var_70], r13
0x14009b87b  mov     [rsp+1F0h+ValueData], r13
0x14009b880  call    cs:__imp_RtlQueryRegistryValuesEx
0x14009b887  nop     dword ptr [rax+rax+00h]
0x14009b88c  mov     ebx, eax
0x14009b88e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009b895  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009b89c  jz      short loc_14009B8CC
0x14009b89e  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b8a5  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009b8ac  mov     r9d, 61h ; 'a'; int
0x14009b8b2  mov     dword ptr [rsp+1F0h+var_1C0], esi; char
0x14009b8b6  mov     [rsp+1F0h+ValueLength], ebx; char
0x14009b8ba  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x14009b8bf  mov     rcx, [rcx+40h]; int
0x14009b8c3  lea     r8d, [r9-60h]; int
0x14009b8c7  call    WPP_RECORDER_SF_dd
0x14009b8cc  test    ebx, ebx
0x14009b8ce  jz      short loc_14009B8DA
0x14009b8d0  mov     ebx, 0C0000001h
0x14009b8d5  jmp     loc_14009B9C5
0x14009b8da  mov     ebx, r13d
0x14009b8dd  cmp     [rsp+1F0h+String.Buffer], r13
0x14009b8e2  jz      short loc_14009B8FF
0x14009b8e4  lea     r8, [rsp+1F0h+Value]; Value
0x14009b8e9  mov     edx, 0Ah; Base
0x14009b8ee  lea     rcx, [rsp+1F0h+String]; String
0x14009b8f3  call    cs:__imp_RtlUnicodeStringToInteger
0x14009b8fa  nop     dword ptr [rax+rax+00h]
0x14009b8ff  cmp     [rsp+1F0h+Value], r13d
0x14009b904  jnz     loc_14009B9C5
0x14009b90a  mov     rcx, [rsp+1F0h+DestinationString.Buffer]
0x14009b90f  test    rcx, rcx
0x14009b912  jnz     short loc_14009B989
0x14009b914  cmp     [rbp+0F0h+String2.Buffer], r13
0x14009b918  jz      short loc_14009B969
0x14009b91a  mov     edi, r13d
0x14009b91d  lea     rcx, qword_1400F8C40
0x14009b924  cmp     edi, 6
0x14009b927  jnb     short loc_14009B969
0x14009b929  mov     eax, edi
0x14009b92b  lea     rdx, [rsp+1F0h+String2]; String2
0x14009b930  mov     r8b, 1; CaseInSensitive
0x14009b933  lea     rsi, [rax+rax*2]
0x14009b937  lea     rcx, [rcx+rsi*8]; String1
0x14009b93b  call    cs:__imp_RtlCompareUnicodeString
0x14009b942  nop     dword ptr [rax+rax+00h]
0x14009b947  test    eax, eax
0x14009b949  jz      short loc_14009B94F
0x14009b94b  inc     edi
0x14009b94d  jmp     short loc_14009B91D
0x14009b94f  lea     rax, qword_1400F8C40
0x14009b956  mov     eax, [rax+rsi*8+10h]
0x14009b95a  lea     rdx, qword_1400FAC18
0x14009b961  sub     eax, 4
0x14009b964  cmp     eax, 1
0x14009b967  jbe     short loc_14009B970
0x14009b969  lea     rdx, a0; "0"
0x14009b970  lea     rcx, [rsp+1F0h+DestinationString]; DestinationString
0x14009b975  call    cs:__imp_RtlInitUnicodeString
0x14009b97c  nop     dword ptr [rax+rax+00h]
0x14009b981  mov     rcx, [rsp+1F0h+DestinationString.Buffer]
0x14009b986  mov     dil, r13b
0x14009b989  movzx   eax, [rsp+1F0h+DestinationString.Length]
0x14009b98e  mov     r9d, 1; ValueType
0x14009b994  mov     r8, [r14+8]; ValueName
0x14009b998  add     eax, 2
0x14009b99b  mov     rdx, [r15+8]; Path
0x14009b99f  mov     [rsp+1F0h+ValueLength], eax; ValueLength
0x14009b9a3  mov     [rsp+1F0h+ValueData], rcx; ValueData
0x14009b9a8  mov     ecx, r9d; RelativeTo
0x14009b9ab  call    cs:__imp_RtlWriteRegistryValue
0x14009b9b2  nop     dword ptr [rax+rax+00h]
0x14009b9b7  mov     ecx, ebx
0x14009b9b9  mov     ebx, 0C0000001h
0x14009b9be  test    eax, eax
0x14009b9c0  cmovnz  ecx, ebx
0x14009b9c3  mov     ebx, ecx
0x14009b9c5  mov     rcx, [rsp+1F0h+String.Buffer]; P
0x14009b9ca  test    rcx, rcx
0x14009b9cd  jz      short loc_14009B9DD
0x14009b9cf  xor     edx, edx; Tag
0x14009b9d1  call    cs:__imp_ExFreePoolWithTag
0x14009b9d8  nop     dword ptr [rax+rax+00h]
0x14009b9dd  mov     rcx, [rsp+1F0h+DestinationString.Buffer]; P
0x14009b9e2  test    rcx, rcx
0x14009b9e5  jz      short loc_14009B9FA
0x14009b9e7  test    dil, dil
0x14009b9ea  jz      short loc_14009B9FA
0x14009b9ec  xor     edx, edx; Tag
0x14009b9ee  call    cs:__imp_ExFreePoolWithTag
0x14009b9f5  nop     dword ptr [rax+rax+00h]
0x14009b9fa  mov     rcx, [rbp+0F0h+String2.Buffer]; P
0x14009b9fe  test    rcx, rcx
0x14009ba01  jz      short loc_14009BA11
0x14009ba03  xor     edx, edx; Tag
0x14009ba05  call    cs:__imp_ExFreePoolWithTag
0x14009ba0c  nop     dword ptr [rax+rax+00h]
0x14009ba11  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009ba18  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009ba1f  jz      short loc_14009BA5A
0x14009ba21  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ba28  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009ba2f  mov     dword ptr [rsp+1F0h+var_1B0], ebx; char
0x14009ba33  mov     r9d, 62h ; 'b'; int
0x14009ba39  mov     qword ptr [rsp+1F0h+var_1B8], r14; char
0x14009ba3e  mov     qword ptr [rsp+1F0h+var_1C0], r12; char
0x14009ba43  mov     rcx, [rcx+40h]; int
0x14009ba47  lea     r8d, [r9-61h]; int
0x14009ba4b  mov     qword ptr [rsp+1F0h+ValueLength], r15; char
0x14009ba50  mov     [rsp+1F0h+ValueData], rax; struct _GUID *
0x14009ba55  call    WPP_RECORDER_SF_qqqL
0x14009ba5a  mov     eax, ebx
0x14009ba5c  mov     rcx, [rbp+0F0h+var_40]
0x14009ba63  xor     rcx, rsp; StackCookie
0x14009ba66  call    __security_check_cookie
0x14009ba6b  mov     rbx, [rsp+1F0h+arg_18]
0x14009ba73  add     rsp, 1C0h
0x14009ba7a  pop     r15
0x14009ba7c  pop     r14
0x14009ba7e  pop     r13
0x14009ba80  pop     r12
0x14009ba82  pop     rdi
0x14009ba83  pop     rsi
0x14009ba84  pop     rbp
0x14009ba85  retn
```
