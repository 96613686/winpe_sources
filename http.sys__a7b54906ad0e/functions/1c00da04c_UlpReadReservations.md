# UlpReadReservations

- ea: `0x1c00da04c`
- end: `0x1c00da2b0`
- name: `UlpReadReservations`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1c00d95c0`

## callees

- `0x1c00022d0`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c00da04c`
- `0x1c00da2b8`
- `0x1c00da860`
- `0x1c011f308`
- `0x1c0141034`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1c00da11d`
- `ntoskrnl!ZwCreateKey` at `0x1c00da11d`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1c00da163`
- `ntoskrnl!ZwEnumerateValueKey` at `0x1c00da163`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00da237`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00da237`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da1d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da218`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da276`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da1d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da218`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00da276`

## string_xrefs

- `0x1c00da080`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\UrlAclInfo`

## pseudocode

```c
void __fastcall UlpReadReservations(__int64 a1)
{
  int v2; // r12d
  unsigned int *p_KeyValueInformation; // rbx
  NTSTATUS inited; // eax
  int v5; // edx
  HANDLE *v6; // r15
  NTSTATUS v7; // eax
  int v8; // edx
  ULONG v9; // esi
  ULONG v10; // r14d
  __int64 v11; // r9
  int v12; // edi
  ULONG v13; // eax
  unsigned int *PoolWithTagPriority; // rax
  PUNICODE_STRING Class; // [rsp+28h] [rbp-E0h]
  PUNICODE_STRING Classa; // [rsp+28h] [rbp-E0h]
  PVOID P; // [rsp+48h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-B8h] BYREF
  ULONG ResultLength_4; // [rsp+54h] [rbp-B4h] BYREF
  ULONG ResultLength_8[4]; // [rsp+58h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes_8; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v22[144]; // [rsp+98h] [rbp-70h] BYREF
  __int128 KeyValueInformation; // [rsp+128h] [rbp+20h] BYREF
  __int64 v24; // [rsp+138h] [rbp+30h]

  v24 = 0;
  ResultLength_4 = 0;
  ResultLength = 0;
  v2 = 1;
  p_KeyValueInformation = 0;
  KeyValueInformation = 0;
  *(_OWORD *)ResultLength_8 = 0;
  memset(&ObjectAttributes_8, 0, sizeof(ObjectAttributes_8));
  inited = UlInitUnicodeStringEx(
             ResultLength_8,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters\\UrlAclInfo");
  if ( inited < 0 )
  {
LABEL_25:
    LODWORD(P) = inited;
LABEL_26:
    LODWORD(Class) = 4;
    UlWriteEventLogEntry(-1073726815, v5, 0, 0, (size_t)Class, &P);
  }
  else
  {
    ObjectAttributes_8.Length = 48;
    ObjectAttributes_8.ObjectName = (PUNICODE_STRING)ResultLength_8;
    v6 = (HANDLE *)(a1 + 1392);
    ObjectAttributes_8.RootDirectory = 0;
    ObjectAttributes_8.Attributes = 576;
    *(_OWORD *)&ObjectAttributes_8.SecurityDescriptor = 0;
    v7 = ZwCreateKey((PHANDLE)(a1 + 1392), 0x2001Fu, &ObjectAttributes_8, 0, 0, 0, &ResultLength_4);
    if ( v7 < 0 )
    {
      LODWORD(P) = v7;
      LODWORD(Classa) = 4;
      UlWriteEventLogEntry(-1073726815, v8, 0, 0, (size_t)Classa, &P);
      *v6 = 0;
    }
    else if ( ResultLength_4 != 1 )
    {
      p_KeyValueInformation = (unsigned int *)&KeyValueInformation;
      v9 = 0;
      v10 = 24;
      while ( 1 )
      {
        while ( 1 )
        {
          inited = ZwEnumerateValueKey(*v6, v9, KeyValueFullInformation, p_KeyValueInformation, v10, &ResultLength);
          if ( inited )
            break;
          P = 0;
          memset(v22, 0, 0x88u);
          if ( (int)UlpValidateUrlSdPair(a1, p_KeyValueInformation, &P, v22) < 0 )
          {
            v12 = -1073741492;
          }
          else
          {
            v12 = UlpAddReservationEntry(
                    a1,
                    (__int64)v22,
                    (__int64)p_KeyValueInformation + p_KeyValueInformation[2],
                    v11,
                    0,
                    0,
                    0,
                    0);
            ExFreePoolWithTag(P, 0);
          }
          if ( v12 < 0 )
          {
            if ( v2 )
            {
              v2 = 0;
              UlpLogSpecificInitFailure(p_KeyValueInformation, (unsigned int)v12);
            }
          }
          ++v9;
        }
        if ( inited == -2147483622 )
          break;
        if ( inited != -2147483643 )
          goto LABEL_25;
        v13 = ResultLength;
        v10 = ResultLength;
        if ( p_KeyValueInformation != (unsigned int *)&KeyValueInformation )
        {
          ExFreePoolWithTag(p_KeyValueInformation, 0);
          v13 = ResultLength;
        }
        PoolWithTagPriority = (unsigned int *)ExAllocatePoolWithTagPriority(
                                                PagedPool,
                                                v13,
                                                0x44526C55u,
                                                LowPoolPriority);
        p_KeyValueInformation = PoolWithTagPriority;
        if ( !PoolWithTagPriority )
        {
          LODWORD(P) = -1073741670;
          goto LABEL_26;
        }
        memset(PoolWithTagPriority, 0, ResultLength);
      }
    }
  }
  if ( p_KeyValueInformation != (unsigned int *)&KeyValueInformation && p_KeyValueInformation )
    ExFreePoolWithTag(p_KeyValueInformation, 0);
}

```

## disassembly

```asm
0x1c00da04c  mov     rax, rsp
0x1c00da04f  mov     [rax+10h], rbx
0x1c00da053  mov     [rax+18h], rsi
0x1c00da057  mov     [rax+20h], rdi
0x1c00da05b  push    rbp
0x1c00da05c  push    r12
0x1c00da05e  push    r13
0x1c00da060  push    r14
0x1c00da062  push    r15
0x1c00da064  lea     rbp, [rax-68h]
0x1c00da068  sub     rsp, 140h
0x1c00da06f  mov     rax, cs:__security_cookie
0x1c00da076  xor     rax, rsp
0x1c00da079  mov     [rbp+60h+var_28], rax
0x1c00da07d  xorps   xmm1, xmm1
0x1c00da080  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x1c00da087  xor     eax, eax
0x1c00da089  xorps   xmm0, xmm0
0x1c00da08c  xor     edi, edi
0x1c00da08e  mov     [rbp+60h+var_30], rax
0x1c00da092  mov     r13, rcx
0x1c00da095  mov     [rsp+160h+ResultLength+4], edi
0x1c00da099  lea     rcx, [rsp+160h+ResultLength+8]
0x1c00da09e  mov     [rsp+160h+ResultLength], edi
0x1c00da0a2  lea     r12d, [rax+1]
0x1c00da0a6  mov     ebx, edi
0x1c00da0a8  movups  [rbp+60h+KeyValueInformation], xmm0
0x1c00da0ac  movups  xmmword ptr [rsp+160h+ResultLength+8], xmm0
0x1c00da0b1  movups  xmmword ptr [rsp+160h+ObjectAttributes+8], xmm1
0x1c00da0b6  movups  xmmword ptr [rsp+160h+ObjectAttributes+18h], xmm1
0x1c00da0bb  movups  xmmword ptr [rbp+60h+ObjectAttributes+28h], xmm1
0x1c00da0bf  call    UlInitUnicodeStringEx
0x1c00da0c4  test    eax, eax
0x1c00da0c6  js      loc_1C00FE550
0x1c00da0cc  lea     rax, [rsp+160h+ResultLength+8]
0x1c00da0d1  mov     dword ptr [rsp+160h+ObjectAttributes+8], 30h ; '0'
0x1c00da0d9  mov     qword ptr [rsp+160h+ObjectAttributes+18h], rax
0x1c00da0de  lea     r15, [r13+570h]
0x1c00da0e5  lea     rax, [rsp+160h+ResultLength+4]
0x1c00da0ea  mov     qword ptr [rsp+160h+ObjectAttributes+10h], rdi
0x1c00da0ef  mov     [rsp+160h+Disposition], rax; Disposition
0x1c00da0f4  lea     r8, [rsp+160h+ObjectAttributes+8]; ObjectAttributes
0x1c00da0f9  xorps   xmm0, xmm0
0x1c00da0fc  mov     [rsp+160h+CreateOptions], edi; CreateOptions
0x1c00da100  xor     r9d, r9d; TitleIndex
0x1c00da103  mov     [rsp+160h+Class], rdi; Class
0x1c00da108  mov     edx, 2001Fh; DesiredAccess
0x1c00da10d  mov     dword ptr [rsp+160h+ObjectAttributes+20h], 240h
0x1c00da115  mov     rcx, r15; KeyHandle
0x1c00da118  movdqu  xmmword ptr [rbp+60h+ObjectAttributes+28h], xmm0
0x1c00da11d  call    cs:__imp_ZwCreateKey
0x1c00da124  nop     dword ptr [rax+rax+00h]
0x1c00da129  test    eax, eax
0x1c00da12b  js      loc_1C00FE4F2
0x1c00da131  cmp     [rsp+160h+ResultLength+4], r12d
0x1c00da136  jz      loc_1C00DA263
0x1c00da13c  lea     rbx, [rbp+60h+KeyValueInformation]
0x1c00da140  mov     esi, edi
0x1c00da142  lea     r14d, [rdi+18h]
0x1c00da146  mov     rcx, [r15]; KeyHandle
0x1c00da149  lea     rax, [rsp+160h+ResultLength]
0x1c00da14e  mov     qword ptr [rsp+160h+CreateOptions], rax; ResultLength
0x1c00da153  mov     r9, rbx; KeyValueInformation
0x1c00da156  mov     r8d, 1; KeyValueInformationClass
0x1c00da15c  mov     dword ptr [rsp+160h+Class], r14d; Length
0x1c00da161  mov     edx, esi; Index
0x1c00da163  call    cs:__imp_ZwEnumerateValueKey
0x1c00da16a  nop     dword ptr [rax+rax+00h]
0x1c00da16f  test    eax, eax
0x1c00da171  jnz     short loc_1C00DA1F1
0x1c00da173  xor     edx, edx; Val
0x1c00da175  mov     [rsp+160h+P], rdi
0x1c00da17a  mov     r8d, 88h; Size
0x1c00da180  lea     rcx, [rbp+60h+var_D0]; void *
0x1c00da184  call    memset
0x1c00da189  lea     r9, [rbp+60h+var_D0]
0x1c00da18d  mov     rdx, rbx
0x1c00da190  lea     r8, [rsp+160h+P]
0x1c00da195  mov     rcx, r13
0x1c00da198  call    UlpValidateUrlSdPair
0x1c00da19d  test    eax, eax
0x1c00da19f  js      loc_1C00FE520
0x1c00da1a5  mov     r8d, [rbx+8]
0x1c00da1a9  lea     rdx, [rbp+60h+var_D0]
0x1c00da1ad  mov     byte ptr [rsp+160h+var_128], dil
0x1c00da1b2  add     r8, rbx
0x1c00da1b5  mov     byte ptr [rsp+160h+Disposition], dil
0x1c00da1ba  mov     rcx, r13
0x1c00da1bd  mov     [rsp+160h+CreateOptions], edi
0x1c00da1c1  mov     [rsp+160h+Class], rdi
0x1c00da1c6  call    UlpAddReservationEntry
0x1c00da1cb  mov     rcx, [rsp+160h+P]; P
0x1c00da1d0  xor     edx, edx; Tag
0x1c00da1d2  mov     edi, eax
0x1c00da1d4  call    cs:__imp_ExFreePoolWithTag
0x1c00da1db  nop     dword ptr [rax+rax+00h]
0x1c00da1e0  test    edi, edi
0x1c00da1e2  js      loc_1C00FE52A
0x1c00da1e8  inc     esi
0x1c00da1ea  xor     edi, edi
0x1c00da1ec  jmp     loc_1C00DA146
0x1c00da1f1  cmp     eax, 8000001Ah
0x1c00da1f6  jz      short loc_1C00DA263
0x1c00da1f8  cmp     eax, 80000005h
0x1c00da1fd  jnz     loc_1C00FE550
0x1c00da203  mov     eax, [rsp+160h+ResultLength]
0x1c00da207  lea     rcx, [rbp+60h+KeyValueInformation]
0x1c00da20b  mov     r14d, eax
0x1c00da20e  cmp     rbx, rcx
0x1c00da211  jz      short loc_1C00DA228
0x1c00da213  xor     edx, edx; Tag
0x1c00da215  mov     rcx, rbx; P
0x1c00da218  call    cs:__imp_ExFreePoolWithTag
0x1c00da21f  nop     dword ptr [rax+rax+00h]
0x1c00da224  mov     eax, [rsp+160h+ResultLength]
0x1c00da228  xor     r9d, r9d; Priority
0x1c00da22b  mov     edx, eax; NumberOfBytes
0x1c00da22d  mov     r8d, 44526C55h; Tag
0x1c00da233  lea     ecx, [r9+1]; PoolType
0x1c00da237  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00da23e  nop     dword ptr [rax+rax+00h]
0x1c00da243  mov     rbx, rax
0x1c00da246  test    rax, rax
0x1c00da249  jz      loc_1C00FE546
0x1c00da24f  mov     r8d, [rsp+160h+ResultLength]; Size
0x1c00da254  xor     edx, edx; Val
0x1c00da256  mov     rcx, rax; void *
0x1c00da259  call    memset
0x1c00da25e  jmp     loc_1C00DA146
0x1c00da263  lea     rax, [rbp+60h+KeyValueInformation]
0x1c00da267  cmp     rbx, rax
0x1c00da26a  jz      short loc_1C00DA282
0x1c00da26c  test    rbx, rbx
0x1c00da26f  jz      short loc_1C00DA282
0x1c00da271  xor     edx, edx; Tag
0x1c00da273  mov     rcx, rbx; P
0x1c00da276  call    cs:__imp_ExFreePoolWithTag
0x1c00da27d  nop     dword ptr [rax+rax+00h]
0x1c00da282  mov     rcx, [rbp+60h+var_28]
0x1c00da286  xor     rcx, rsp; StackCookie
0x1c00da289  call    __security_check_cookie
0x1c00da28e  lea     r11, [rsp+160h+var_20]
0x1c00da296  mov     rbx, [r11+38h]
0x1c00da29a  mov     rsi, [r11+40h]
0x1c00da29e  mov     rdi, [r11+48h]
0x1c00da2a2  mov     rsp, r11
0x1c00da2a5  pop     r15
0x1c00da2a7  pop     r14
0x1c00da2a9  pop     r13
0x1c00da2ab  pop     r12
0x1c00da2ad  pop     rbp
0x1c00da2ae  retn
0x1c00fe4f2  mov     dword ptr [rsp+160h+P], eax
0x1c00fe4f6  xor     r8d, r8d; int
0x1c00fe4f9  lea     rax, [rsp+160h+P]
0x1c00fe4fe  xor     r9d, r9d; int
0x1c00fe501  mov     qword ptr [rsp+160h+CreateOptions], rax; Src
0x1c00fe506  mov     ecx, 0C0003AA1h; int
0x1c00fe50b  mov     dword ptr [rsp+160h+Class], 4; Size
0x1c00fe513  call    UlWriteEventLogEntry
0x1c00fe518  mov     [r15], rdi
0x1c00fe51b  jmp     loc_1C00DA263
0x1c00fe520  mov     edi, 0C000014Ch
0x1c00fe525  jmp     loc_1C00DA1E0
0x1c00fe52a  test    r12d, r12d
0x1c00fe52d  jz      loc_1C00DA1E8
0x1c00fe533  xor     r12d, r12d
0x1c00fe536  mov     edx, edi
0x1c00fe538  mov     rcx, rbx
0x1c00fe53b  call    UlpLogSpecificInitFailure
0x1c00fe540  nop
0x1c00fe541  jmp     loc_1C00DA1E8
0x1c00fe546  mov     dword ptr [rsp+160h+P], 0C000009Ah
0x1c00fe54e  jmp     short loc_1C00FE554
0x1c00fe550  mov     dword ptr [rsp+160h+P], eax
0x1c00fe554  lea     rax, [rsp+160h+P]
0x1c00fe559  xor     r9d, r9d; int
0x1c00fe55c  mov     qword ptr [rsp+160h+CreateOptions], rax; Src
0x1c00fe561  xor     r8d, r8d; int
0x1c00fe564  mov     ecx, 0C0003AA1h; int
0x1c00fe569  mov     dword ptr [rsp+160h+Class], 4; Size
0x1c00fe571  call    UlWriteEventLogEntry
0x1c00fe576  nop
0x1c00fe577  jmp     loc_1C00DA263
```
