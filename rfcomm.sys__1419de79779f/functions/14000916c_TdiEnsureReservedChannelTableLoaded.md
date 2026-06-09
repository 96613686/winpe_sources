# TdiEnsureReservedChannelTableLoaded

- ea: `0x14000916c`
- end: `0x140009652`
- name: `TdiEnsureReservedChannelTableLoaded`
- size: `1254`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400035cc`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x140004684`
- `0x140004a68`
- `0x14000916c`
- `0x1400340cc`
- `0x140034118`
- `0x140034168`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400092d6`
- `ntoskrnl!ExAllocatePool2` at `0x140009378`
- `ntoskrnl!ExAllocatePool2` at `0x1400092d6`
- `ntoskrnl!ExAllocatePool2` at `0x140009378`
- `ntoskrnl!ZwClose` at `0x1400094c0`
- `ntoskrnl!ZwClose` at `0x1400095f3`
- `ntoskrnl!ZwClose` at `0x140009608`
- `ntoskrnl!ZwClose` at `0x1400094c0`
- `ntoskrnl!ZwClose` at `0x1400095f3`
- `ntoskrnl!ZwClose` at `0x140009608`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009511`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400094e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009511`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140009256`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140009256`
- `ntoskrnl!ZwQueryKey` at `0x1400092a7`
- `ntoskrnl!ZwQueryKey` at `0x140009300`
- `ntoskrnl!ZwQueryKey` at `0x1400092a7`
- `ntoskrnl!ZwQueryKey` at `0x140009300`
- `ntoskrnl!ZwEnumerateKey` at `0x140009349`
- `ntoskrnl!ZwEnumerateKey` at `0x1400093a9`
- `ntoskrnl!ZwEnumerateKey` at `0x140009349`
- `ntoskrnl!ZwEnumerateKey` at `0x1400093a9`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400093ec`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400093ec`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140009470`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x140009470`

## pseudocode

```c
void __fastcall TdiEnsureReservedChannelTableLoaded(__int64 a1, int a2)
{
  int v3; // edx
  __int64 v4; // rcx
  int v5; // eax
  int v6; // edx
  NTSTATUS v7; // ebx
  int v8; // eax
  _DWORD *Pool2; // rsi
  ULONG v10; // r12d
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rdi
  NTSTATUS v13; // eax
  __int64 v14; // r15
  int v15; // eax
  int KeyValue; // eax
  PSECURITY_DESCRIPTOR v17; // r14
  HANDLE KeyHandle; // [rsp+40h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-28h] BYREF
  HANDLE v21; // [rsp+58h] [rbp-20h] BYREF
  UNICODE_STRING String; // [rsp+60h] [rbp-18h] BYREF
  ULONG Length; // [rsp+C0h] [rbp+48h] BYREF
  ULONG v24; // [rsp+C8h] [rbp+50h] BYREF
  ULONG Value; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+60h] BYREF

  KeyHandle = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      25,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a1);
  if ( *(_BYTE *)(a1 + 129) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        15,
        26,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        a1);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v3,
          15,
          27,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
    }
    return;
  }
  v4 = *(_QWORD *)(a1 + 80);
  *(_BYTE *)(a1 + 129) = 1;
  v21 = 0;
  v5 = IoOpenDriverRegistryKey(*(_QWORD *)(v4 + 40), 0, 131097, 0, &v21);
  LOBYTE(v7) = v5;
  if ( v5 >= 0 )
  {
    v8 = BthOpenKey(v21, L"ReservedChannels", &KeyHandle);
    LOBYTE(v7) = v8;
    if ( v8 >= 0 )
    {
      Length = 0;
      if ( ZwQueryKey(KeyHandle, KeyFullInformation, 0, 0, &Length) == -1073741789 && Length )
      {
        Pool2 = (_DWORD *)ExAllocatePool2(256, Length, 1835230802);
        if ( Pool2 )
          v7 = ZwQueryKey(KeyHandle, KeyFullInformation, Pool2, Length, &Length);
        else
          v7 = -1073741670;
        if ( v7 >= 0 )
        {
          v10 = 0;
          if ( Pool2[5] )
          {
            while ( 1 )
            {
              v24 = 0;
              if ( ZwEnumerateKey(KeyHandle, v10, KeyBasicInformation, 0, 0, &v24) != -1073741789 || !v24 )
                break;
              v11 = (unsigned __int16 *)ExAllocatePool2(256, v24, 1835230802);
              v12 = v11;
              if ( v11 )
                v7 = ZwEnumerateKey(KeyHandle, v10, KeyBasicInformation, v11, v24, &v24);
              else
                v7 = -1073741670;
              if ( v7 < 0 )
                goto LABEL_44;
              *(_DWORD *)(&String.MaximumLength + 1) = 0;
              String.Buffer = v12 + 8;
              String.Length = v12[6];
              String.MaximumLength = String.Length;
              Value = 0;
              v13 = RtlUnicodeStringToInteger(&String, 0, &Value);
              LOBYTE(v7) = v13;
              if ( v13 < 0 || Value - 1 > 0x1D )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_Dd(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v6,
                    1,
                    29,
                    (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                    Value,
                    v13);
              }
              else
              {
                v14 = 2LL * Value;
                if ( *(_BYTE *)(a1 + 16LL * Value + 136) )
                {
                  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    WPP_RECORDER_SF_d(
                      WPP_GLOBAL_Control->DeviceExtension,
                      v6,
                      1,
                      28,
                      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                      Value);
                }
                else
                {
                  Handle = 0;
                  v15 = BthOpenKeyEx(KeyHandle, &String, &Handle);
                  LOBYTE(v7) = v15;
                  if ( v15 >= 0 )
                  {
                    SecurityDescriptor = 0;
                    LODWORD(v26) = 0;
                    KeyValue = BthQueryAllocateKeyValue(Handle, (__int64)&SecurityDescriptor, (__int64)&v26);
                    v17 = SecurityDescriptor;
                    LOBYTE(v7) = KeyValue;
                    if ( KeyValue >= 0 )
                    {
                      if ( RtlValidSecurityDescriptor(SecurityDescriptor) )
                      {
                        *(_QWORD *)(a1 + 8 * v14 + 144) = v17;
                        v17 = 0;
                        *(_BYTE *)(a1 + 8 * v14 + 136) = 1;
                      }
                      else
                      {
                        LOBYTE(v7) = 121;
                      }
                    }
                    if ( v17 )
                      ExFreePoolWithTag(v17, 0x6C687442u);
                  }
                  if ( Handle )
                    ZwClose(Handle);
                }
              }
LABEL_34:
              if ( v12 )
                ExFreePoolWithTag(v12, 0x6D636652u);
              if ( ++v10 >= Pool2[5] )
                goto LABEL_37;
            }
            v12 = 0;
            LOBYTE(v7) = 1;
LABEL_44:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v6,
                1,
                30,
                (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
                v7);
            goto LABEL_34;
          }
        }
LABEL_37:
        if ( Pool2 )
          ExFreePoolWithTag(Pool2, 0x6D636652u);
      }
      else
      {
        LOBYTE(v7) = 1;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( v21 )
    ZwClose(v21);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      15,
      31,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      v7);
}

```

## disassembly

```asm
0x14000916c  push    rbp
0x14000916e  push    rbx
0x14000916f  push    rsi
0x140009170  push    rdi
0x140009171  push    r12
0x140009173  push    r13
0x140009175  push    r14
0x140009177  push    r15
0x140009179  mov     rbp, rsp
0x14000917c  sub     rsp, 78h
0x140009180  xor     r14d, r14d
0x140009183  mov     r13, rcx
0x140009186  mov     [rbp+KeyHandle], r14
0x14000918a  lea     r15, WPP_RECORDER_INITIALIZED
0x140009191  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009198  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000919f  jz      short loc_1400091C3
0x1400091a1  mov     [rsp+78h+var_50], rcx
0x1400091a6  lea     r9d, [r14+19h]
0x1400091aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091b1  lea     r8d, [r14+0Fh]
0x1400091b5  mov     [rsp+78h+ResultLength], rdi
0x1400091ba  mov     rcx, [rcx+40h]
0x1400091be  call    WPP_RECORDER_SF_q
0x1400091c3  cmp     [r13+81h], r14b
0x1400091ca  jz      short loc_14000922E
0x1400091cc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400091d3  jz      loc_140009640
0x1400091d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091e0  mov     r9d, 1Ah
0x1400091e6  mov     [rsp+78h+var_50], r13
0x1400091eb  mov     [rsp+78h+ResultLength], rdi
0x1400091f0  mov     rcx, [rcx+40h]
0x1400091f4  lea     r8d, [r9-0Bh]
0x1400091f8  call    WPP_RECORDER_SF_q
0x1400091fd  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009204  jz      loc_140009640
0x14000920a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009211  mov     r9d, 1Bh
0x140009217  mov     [rsp+78h+ResultLength], rdi
0x14000921c  mov     rcx, [rcx+40h]
0x140009220  lea     r8d, [r9-0Ch]
0x140009224  call    WPP_RECORDER_SF_
0x140009229  jmp     loc_140009640
0x14000922e  mov     rcx, [r13+50h]
0x140009232  lea     rax, [rbp+var_20]
0x140009236  mov     byte ptr [r13+81h], 1
0x14000923e  xor     r9d, r9d
0x140009241  mov     [rbp+var_20], r14
0x140009245  xor     edx, edx
0x140009247  mov     r8d, 20019h
0x14000924d  mov     [rsp+78h+ResultLength], rax
0x140009252  mov     rcx, [rcx+28h]
0x140009256  call    cs:__imp_IoOpenDriverRegistryKey
0x14000925d  nop     dword ptr [rax+rax+00h]
0x140009262  mov     ebx, eax
0x140009264  test    eax, eax
0x140009266  js      loc_1400095EA
0x14000926c  mov     rcx, [rbp+var_20]
0x140009270  lea     r8, [rbp+KeyHandle]
0x140009274  lea     rdx, aReservedchanne; "ReservedChannels"
0x14000927b  call    BthOpenKey
0x140009280  mov     ebx, eax
0x140009282  test    eax, eax
0x140009284  js      loc_1400095EA
0x14000928a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000928e  lea     rax, [rbp+Length]
0x140009292  xor     r9d, r9d; Length
0x140009295  mov     [rbp+Length], r14d
0x140009299  xor     r8d, r8d; KeyInformation
0x14000929c  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1400092a1  lea     ebx, [r9+2]
0x1400092a5  mov     edx, ebx; KeyInformationClass
0x1400092a7  call    cs:__imp_ZwQueryKey
0x1400092ae  nop     dword ptr [rax+rax+00h]
0x1400092b3  cmp     eax, 0C0000023h
0x1400092b8  jnz     loc_1400095E5
0x1400092be  mov     eax, [rbp+Length]
0x1400092c1  test    eax, eax
0x1400092c3  jz      loc_1400095E5
0x1400092c9  mov     edx, eax
0x1400092cb  mov     ecx, 100h
0x1400092d0  mov     r8d, 6D636652h
0x1400092d6  call    cs:__imp_ExAllocatePool2
0x1400092dd  nop     dword ptr [rax+rax+00h]
0x1400092e2  mov     rsi, rax
0x1400092e5  test    rax, rax
0x1400092e8  jz      short loc_140009310
0x1400092ea  mov     r9d, [rbp+Length]; Length
0x1400092ee  lea     rax, [rbp+Length]
0x1400092f2  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400092f6  mov     r8, rsi; KeyInformation
0x1400092f9  mov     edx, ebx; KeyInformationClass
0x1400092fb  mov     [rsp+78h+ResultLength], rax; ResultLength
0x140009300  call    cs:__imp_ZwQueryKey
0x140009307  nop     dword ptr [rax+rax+00h]
0x14000930c  mov     ebx, eax
0x14000930e  jmp     short loc_140009315
0x140009310  mov     ebx, 0C000009Ah
0x140009315  test    ebx, ebx
0x140009317  js      loc_140009500
0x14000931d  mov     r12d, r14d
0x140009320  cmp     [rsi+14h], r14d
0x140009324  jbe     loc_140009500
0x14000932a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14000932e  lea     rax, [rbp+arg_8]
0x140009332  mov     [rsp+78h+var_50], rax; ResultLength
0x140009337  xor     r9d, r9d; KeyInformation
0x14000933a  xor     r8d, r8d; KeyInformationClass
0x14000933d  mov     dword ptr [rsp+78h+ResultLength], r14d; Length
0x140009342  mov     edx, r12d; Index
0x140009345  mov     [rbp+arg_8], r14d
0x140009349  call    cs:__imp_ZwEnumerateKey
0x140009350  nop     dword ptr [rax+rax+00h]
0x140009355  cmp     eax, 0C0000023h
0x14000935a  jnz     loc_1400095A1
0x140009360  mov     eax, [rbp+arg_8]
0x140009363  test    eax, eax
0x140009365  jz      loc_1400095A1
0x14000936b  mov     edx, eax
0x14000936d  mov     ecx, 100h
0x140009372  mov     r8d, 6D636652h
0x140009378  call    cs:__imp_ExAllocatePool2
0x14000937f  nop     dword ptr [rax+rax+00h]
0x140009384  mov     rdi, rax
0x140009387  test    rax, rax
0x14000938a  jz      short loc_1400093B9
0x14000938c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140009390  lea     rax, [rbp+arg_8]
0x140009394  mov     [rsp+78h+var_50], rax; ResultLength
0x140009399  mov     r9, rdi; KeyInformation
0x14000939c  mov     eax, [rbp+arg_8]
0x14000939f  xor     r8d, r8d; KeyInformationClass
0x1400093a2  mov     edx, r12d; Index
0x1400093a5  mov     dword ptr [rsp+78h+ResultLength], eax; Length
0x1400093a9  call    cs:__imp_ZwEnumerateKey
0x1400093b0  nop     dword ptr [rax+rax+00h]
0x1400093b5  mov     ebx, eax
0x1400093b7  jmp     short loc_1400093BE
0x1400093b9  mov     ebx, 0C000009Ah
0x1400093be  test    ebx, ebx
0x1400093c0  js      loc_1400095A9
0x1400093c6  lea     rax, [rdi+10h]
0x1400093ca  mov     dword ptr [rbp+String+4], r14d
0x1400093ce  mov     [rbp+String.Buffer], rax
0x1400093d2  lea     r8, [rbp+Value]; Value
0x1400093d6  movzx   eax, word ptr [rdi+0Ch]
0x1400093da  lea     rcx, [rbp+String]; String
0x1400093de  xor     edx, edx; Base
0x1400093e0  mov     [rbp+String.Length], ax
0x1400093e4  mov     [rbp+String.MaximumLength], ax
0x1400093e8  mov     [rbp+Value], r14d
0x1400093ec  call    cs:__imp_RtlUnicodeStringToInteger
0x1400093f3  nop     dword ptr [rax+rax+00h]
0x1400093f8  mov     ecx, [rbp+Value]
0x1400093fb  mov     ebx, eax
0x1400093fd  test    eax, eax
0x1400093ff  js      loc_140009561
0x140009405  lea     eax, [rcx-1]
0x140009408  cmp     eax, 1Dh
0x14000940b  ja      loc_140009561
0x140009411  mov     r15d, ecx
0x140009414  add     r15, r15
0x140009417  cmp     [r13+r15*8+88h], r14b
0x14000941f  jnz     loc_140009522
0x140009425  mov     rcx, [rbp+KeyHandle]
0x140009429  lea     r8, [rbp+Handle]
0x14000942d  lea     rdx, [rbp+String]
0x140009431  mov     [rbp+Handle], r14
0x140009435  call    BthOpenKeyEx
0x14000943a  mov     ebx, eax
0x14000943c  test    eax, eax
0x14000943e  js      short loc_1400094B7
0x140009440  mov     rcx, [rbp+Handle]; KeyHandle
0x140009444  lea     rax, [rbp+arg_18]
0x140009448  mov     [rsp+78h+var_50], rax; __int64
0x14000944d  lea     rax, [rbp+SecurityDescriptor]
0x140009451  mov     [rsp+78h+ResultLength], rax; __int64
0x140009456  mov     [rbp+SecurityDescriptor], r14
0x14000945a  mov     dword ptr [rbp+arg_18], r14d
0x14000945e  call    BthQueryAllocateKeyValue
0x140009463  mov     r14, [rbp+SecurityDescriptor]
0x140009467  mov     ebx, eax
0x140009469  test    eax, eax
0x14000946b  js      short loc_14000949B
0x14000946d  mov     rcx, r14; SecurityDescriptor
0x140009470  call    cs:__imp_RtlValidSecurityDescriptor
0x140009477  nop     dword ptr [rax+rax+00h]
0x14000947c  test    al, al
0x14000947e  jnz     short loc_140009487
0x140009480  mov     ebx, 0C0000079h
0x140009485  jmp     short loc_14000949B
0x140009487  mov     [r13+r15*8+90h], r14
0x14000948f  xor     r14d, r14d
0x140009492  mov     byte ptr [r13+r15*8+88h], 1
0x14000949b  test    r14, r14
0x14000949e  jz      short loc_1400094B4
0x1400094a0  mov     edx, 6C687442h; Tag
0x1400094a5  mov     rcx, r14; P
0x1400094a8  call    cs:__imp_ExFreePoolWithTag
0x1400094af  nop     dword ptr [rax+rax+00h]
0x1400094b4  xor     r14d, r14d
0x1400094b7  mov     rcx, [rbp+Handle]; Handle
0x1400094bb  test    rcx, rcx
0x1400094be  jz      short loc_1400094CC
0x1400094c0  call    cs:__imp_ZwClose
0x1400094c7  nop     dword ptr [rax+rax+00h]
0x1400094cc  lea     r15, WPP_RECORDER_INITIALIZED
0x1400094d3  test    rdi, rdi
0x1400094d6  jz      short loc_1400094EC
0x1400094d8  mov     edx, 6D636652h; Tag
0x1400094dd  mov     rcx, rdi; P
0x1400094e0  call    cs:__imp_ExFreePoolWithTag
0x1400094e7  nop     dword ptr [rax+rax+00h]
0x1400094ec  inc     r12d
0x1400094ef  cmp     r12d, [rsi+14h]
0x1400094f3  jb      loc_14000932A
0x1400094f9  lea     rdi, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009500  test    rsi, rsi
0x140009503  jz      loc_1400095EA
0x140009509  mov     edx, 6D636652h; Tag
0x14000950e  mov     rcx, rsi; P
0x140009511  call    cs:__imp_ExFreePoolWithTag
0x140009518  nop     dword ptr [rax+rax+00h]
0x14000951d  jmp     loc_1400095EA
0x140009522  lea     r15, WPP_RECORDER_INITIALIZED
0x140009529  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009530  jz      short loc_1400094D3
0x140009532  mov     dword ptr [rsp+78h+var_50], ecx
0x140009536  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000953d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009544  mov     r9d, 1Ch
0x14000954a  mov     [rsp+78h+ResultLength], rax
0x14000954f  mov     rcx, [rcx+40h]
0x140009553  lea     r8d, [r9-1Bh]
0x140009557  call    WPP_RECORDER_SF_d
0x14000955c  jmp     loc_1400094D3
0x140009561  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140009568  jz      loc_1400094D3
0x14000956e  mov     [rsp+78h+var_48], ebx
0x140009572  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140009579  mov     dword ptr [rsp+78h+var_50], ecx
0x14000957d  mov     r9d, 1Dh
0x140009583  mov     rcx, cs:WPP_GLOBAL_Control
0x14000958a  mov     [rsp+78h+ResultLength], rax
0x14000958f  lea     r8d, [r9-1Ch]
0x140009593  mov     rcx, [rcx+40h]
0x140009597  call    WPP_RECORDER_SF_Dd
0x14000959c  jmp     loc_1400094D3
0x1400095a1  mov     rdi, r14
0x1400095a4  mov     ebx, 0C0000001h
0x1400095a9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400095b0  jz      loc_1400094D3
0x1400095b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095bd  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400095c4  mov     r9d, 1Eh
0x1400095ca  mov     dword ptr [rsp+78h+var_50], ebx
0x1400095ce  mov     [rsp+78h+ResultLength], rax
0x1400095d3  mov     rcx, [rcx+40h]
0x1400095d7  lea     r8d, [r9-1Dh]
0x1400095db  call    WPP_RECORDER_SF_d
0x1400095e0  jmp     loc_1400094D3
0x1400095e5  mov     ebx, 0C0000001h
0x1400095ea  mov     rcx, [rbp+KeyHandle]; Handle
0x1400095ee  test    rcx, rcx
0x1400095f1  jz      short loc_1400095FF
0x1400095f3  call    cs:__imp_ZwClose
0x1400095fa  nop     dword ptr [rax+rax+00h]
0x1400095ff  mov     rcx, [rbp+var_20]; Handle
0x140009603  test    rcx, rcx
0x140009606  jz      short loc_140009614
0x140009608  call    cs:__imp_ZwClose
0x14000960f  nop     dword ptr [rax+rax+00h]
0x140009614  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000961b  jz      short loc_140009640
0x14000961d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009624  mov     r9d, 1Fh
0x14000962a  mov     dword ptr [rsp+78h+var_50], ebx
0x14000962e  mov     [rsp+78h+ResultLength], rdi
0x140009633  mov     rcx, [rcx+40h]
0x140009637  lea     r8d, [r9-10h]
0x14000963b  call    WPP_RECORDER_SF_d
0x140009640  add     rsp, 78h
0x140009644  pop     r15
0x140009646  pop     r14
0x140009648  pop     r13
0x14000964a  pop     r12
0x14000964c  pop     rdi
0x14000964d  pop     rsi
0x14000964e  pop     rbx
0x14000964f  pop     rbp
0x140009650  retn
```
