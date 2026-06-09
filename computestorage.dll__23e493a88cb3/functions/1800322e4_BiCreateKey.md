# BiCreateKey

- ea: `0x1800322e4`
- end: `0x1800325fd`
- name: `BiCreateKey`
- size: `793`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002c6b4`
- `0x18002d9b0`

## callees

- `0x1800322e4`
- `0x180032604`
- `0x180032bc4`
- `0x180033fec`
- `0x180039298`
- `0x180039320`
- `0x18003b918`

## import_xrefs

- `ntdll!ZwSetSecurityObject` at `0x1800324c6`
- `ntdll!ZwSetSecurityObject` at `0x1800324c6`
- `ntdll!ZwCreateKey` at `0x18003247f`
- `ntdll!ZwCreateKey` at `0x18003247f`
- `ntdll!ZwClose` at `0x18003250c`
- `ntdll!ZwClose` at `0x18003256d`
- `ntdll!ZwClose` at `0x18003250c`
- `ntdll!ZwClose` at `0x18003256d`
- `ntdll!RtlFreeHeap` at `0x180032590`
- `ntdll!RtlFreeHeap` at `0x180032590`
- `ntdll!RtlInitUnicodeString` at `0x18003234b`
- `ntdll!RtlInitUnicodeString` at `0x18003234b`

## pseudocode

```c
__int64 __fastcall BiCreateKey(
        unsigned __int64 a1,
        const WCHAR *a2,
        ACCESS_MASK a3,
        unsigned int a4,
        void **a5,
        bool *a6)
{
  char v6; // r14
  const WCHAR *v8; // rax
  ULONG v10; // edi
  ACCESS_MASK v11; // r15d
  char v12; // r13
  struct _ACL *KeySecurityDescriptor; // r14
  NTSTATUS v14; // edi
  unsigned int v15; // eax
  unsigned int v16; // eax
  NTSTATUS v17; // eax
  __int64 v19; // [rsp+40h] [rbp-A8h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-90h]
  void *v23; // [rsp+60h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-70h] BYREF

  v6 = a4;
  v8 = a2;
  Disposition = 0;
  v23 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v22 = 0;
  while ( 1 )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, v8);
    a1 &= ~2uLL;
    a3 |= 0x40000u;
    v10 = 64;
    v11 = a3;
    v12 = 0;
    if ( (v6 & 1) != 0 )
    {
      v10 = 192;
      if ( (a3 & 0x60019) != a3 )
      {
        v11 = 0x40000;
        v12 = 1;
      }
    }
    KeySecurityDescriptor = BiCreateKeySecurityDescriptor(0xF003Fu);
    if ( KeySecurityDescriptor )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = (HANDLE)a1;
      ObjectAttributes.Attributes = v10;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = KeySecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      v19 = 0;
      if ( (a1 & 1) != 0 )
      {
        v15 = ORCreateKey(
                a1 & 0xFFFFFFFFFFFFFFFEuLL,
                DestinationString.Buffer,
                0,
                (a4 >> 1) & 1,
                KeySecurityDescriptor,
                &v19,
                &Disposition);
        v14 = BiDosErrorToNtStatus(v15);
        if ( v14 >= 0 )
          KeyHandle = (void *)(v19 | 1);
      }
      else
      {
        v14 = ZwCreateKey(&KeyHandle, v11, &ObjectAttributes, 0, 0, (a4 >> 1) & 1, &Disposition);
      }
      LODWORD(v19) = v14;
      if ( v14 < 0 )
        goto LABEL_26;
      if ( v12 )
      {
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          v16 = ORSetKeySecurity((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL, 4, KeySecurityDescriptor);
          v17 = BiDosErrorToNtStatus(v16);
        }
        else
        {
          v17 = ZwSetSecurityObject(KeyHandle, 4u, KeySecurityDescriptor);
        }
        v14 = v17;
        if ( v17 < 0 )
        {
          LODWORD(v19) = v17;
          goto LABEL_25;
        }
        v14 = BiZwOpenKey(&v23);
        LODWORD(v19) = v14;
        if ( v14 < 0 )
          goto LABEL_25;
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
          ORCloseKey((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL);
        else
          ZwClose(KeyHandle);
        KeyHandle = v23;
      }
      if ( a6 )
        *a6 = Disposition == 1;
      *a5 = KeyHandle;
LABEL_25:
      if ( v14 >= 0 )
        goto LABEL_31;
      goto LABEL_26;
    }
    v14 = -1073741703;
    LODWORD(v19) = -1073741703;
LABEL_26:
    if ( KeyHandle )
    {
      if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        ORCloseKey((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL);
      else
        ZwClose(KeyHandle);
    }
LABEL_31:
    if ( KeySecurityDescriptor )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, KeySecurityDescriptor);
    if ( v14 != -1073741443 )
      break;
    __debugbreak();
    if ( v22 >= 5 )
      break;
    ++v22;
    v6 = a4;
    v8 = a2;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800322e4  mov     r11, rsp
0x1800322e7  mov     [r11+20h], r9d
0x1800322eb  mov     [r11+10h], rdx
0x1800322ef  push    rsi
0x1800322f0  push    rdi
0x1800322f1  push    r12
0x1800322f3  push    r13
0x1800322f5  push    r14
0x1800322f7  push    r15
0x1800322f9  sub     rsp, 0B8h
0x180032300  mov     r14d, r9d
0x180032303  mov     esi, r8d
0x180032306  mov     rax, rdx
0x180032309  mov     r12, rcx
0x18003230c  mov     [rsp+0E8h+var_A0], 0
0x180032314  mov     [rsp+0E8h+var_88], 0
0x18003231d  xorps   xmm0, xmm0
0x180032320  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x180032325  xor     ecx, ecx
0x180032327  movups  xmmword ptr [rsp+0E8h+ObjectAttributes.Length], xmm0
0x18003232c  movups  xmmword ptr [r11-60h], xmm0
0x180032331  movups  xmmword ptr [r11-54h], xmm0
0x180032336  mov     [rsp+0E8h+var_90], ecx
0x18003233a  mov     [rsp+0E8h+KeyHandle], 0
0x180032343  mov     rdx, rax; SourceString
0x180032346  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x18003234b  call    cs:__imp_RtlInitUnicodeString
0x180032352  nop     dword ptr [rax+rax+00h]
0x180032357  and     r12, 0FFFFFFFFFFFFFFFDh
0x18003235b  mov     [rsp+0E8h+arg_0], r12
0x180032363  bts     esi, 12h
0x180032367  mov     [rsp+0E8h+arg_10], esi
0x18003236e  mov     edi, 40h ; '@'
0x180032373  mov     r15d, esi
0x180032376  xor     r13b, r13b
0x180032379  test    r14b, 1
0x18003237d  jz      short loc_180032398
0x18003237f  mov     edi, 0C0h
0x180032384  mov     eax, esi
0x180032386  and     eax, 60019h
0x18003238b  cmp     eax, esi
0x18003238d  jz      short loc_180032398
0x18003238f  mov     r15d, 40000h
0x180032395  mov     r13b, 1
0x180032398  mov     ecx, 0F003Fh; AccessMask
0x18003239d  call    BiCreateKeySecurityDescriptor
0x1800323a2  mov     r14, rax
0x1800323a5  test    rax, rax
0x1800323a8  jnz     short loc_1800323B8
0x1800323aa  mov     edi, 0C0000079h
0x1800323af  mov     dword ptr [rsp+0E8h+var_A8], edi
0x1800323b3  jmp     loc_18003254D
0x1800323b8  mov     eax, [rsp+0E8h+arg_18]
0x1800323bf  shr     eax, 1
0x1800323c1  and     eax, 1
0x1800323c4  mov     [rsp+0E8h+ObjectAttributes.Length], 30h ; '0'
0x1800323cc  mov     [rsp+0E8h+ObjectAttributes.RootDirectory], r12
0x1800323d4  mov     [rsp+0E8h+ObjectAttributes.Attributes], edi
0x1800323db  lea     rcx, [rsp+0E8h+DestinationString]
0x1800323e0  mov     [rsp+0E8h+ObjectAttributes.ObjectName], rcx
0x1800323e8  mov     [rsp+0E8h+ObjectAttributes.SecurityDescriptor], r14
0x1800323f0  mov     [rsp+0E8h+ObjectAttributes.SecurityQualityOfService], 0
0x1800323fc  mov     [rsp+0E8h+var_A8], 0
0x180032405  test    r12b, 1
0x180032409  jz      short loc_180032458
0x18003240b  mov     rcx, r12
0x18003240e  and     rcx, 0FFFFFFFFFFFFFFFEh; int
0x180032412  lea     rdx, [rsp+0E8h+var_A0]
0x180032417  mov     [rsp+0E8h+Disposition], rdx; __int64
0x18003241c  lea     rdx, [rsp+0E8h+var_A8]
0x180032421  mov     qword ptr [rsp+0E8h+CreateOptions], rdx; __int64
0x180032426  mov     [rsp+0E8h+Class], r14; pSecurityDescriptor
0x18003242b  mov     r9d, eax; int
0x18003242e  xor     r8d, r8d; int
0x180032431  mov     rdx, [rsp+0E8h+DestinationString.Buffer]; int
0x180032436  call    ORCreateKey
0x18003243b  mov     ecx, eax
0x18003243d  call    BiDosErrorToNtStatus
0x180032442  mov     edi, eax
0x180032444  test    eax, eax
0x180032446  js      short loc_18003248D
0x180032448  mov     rax, [rsp+0E8h+var_A8]
0x18003244d  or      rax, 1
0x180032451  mov     [rsp+0E8h+KeyHandle], rax
0x180032456  jmp     short loc_18003248D
0x180032458  lea     rcx, [rsp+0E8h+var_A0]
0x18003245d  mov     [rsp+0E8h+Disposition], rcx; Disposition
0x180032462  mov     [rsp+0E8h+CreateOptions], eax; CreateOptions
0x180032466  mov     [rsp+0E8h+Class], 0; Class
0x18003246f  xor     r9d, r9d; TitleIndex
0x180032472  lea     r8, [rsp+0E8h+ObjectAttributes]; ObjectAttributes
0x180032477  mov     edx, r15d; DesiredAccess
0x18003247a  lea     rcx, [rsp+0E8h+KeyHandle]; KeyHandle
0x18003247f  call    cs:__imp_ZwCreateKey
0x180032486  nop     dword ptr [rax+rax+00h]
0x18003248b  mov     edi, eax
0x18003248d  mov     dword ptr [rsp+0E8h+var_A8], edi
0x180032491  test    edi, edi
0x180032493  js      loc_18003254D
0x180032499  test    r13b, r13b
0x18003249c  jz      loc_180032522
0x1800324a2  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x1800324a7  mov     r8, r14; SecurityDescriptor
0x1800324aa  mov     edx, 4; SecurityInformation
0x1800324af  test    cl, 1
0x1800324b2  jz      short loc_1800324C6
0x1800324b4  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800324b8  call    ORSetKeySecurity
0x1800324bd  mov     ecx, eax
0x1800324bf  call    BiDosErrorToNtStatus
0x1800324c4  jmp     short loc_1800324D2
0x1800324c6  call    cs:__imp_ZwSetSecurityObject
0x1800324cd  nop     dword ptr [rax+rax+00h]
0x1800324d2  mov     edi, eax
0x1800324d4  test    eax, eax
0x1800324d6  js      loc_180032567
0x1800324dc  lea     r8, [rsp+0E8h+ObjectAttributes]
0x1800324e1  mov     edx, esi
0x1800324e3  lea     rcx, [rsp+0E8h+var_88]; KeyHandle
0x1800324e8  call    BiZwOpenKey
0x1800324ed  mov     edi, eax
0x1800324ef  mov     dword ptr [rsp+0E8h+var_A8], eax
0x1800324f3  test    eax, eax
0x1800324f5  js      short loc_180032549
0x1800324f7  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x1800324fc  test    cl, 1
0x1800324ff  jz      short loc_18003250C
0x180032501  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180032505  call    ORCloseKey
0x18003250a  jmp     short loc_180032518
0x18003250c  call    cs:__imp_ZwClose
0x180032513  nop     dword ptr [rax+rax+00h]
0x180032518  mov     rax, [rsp+0E8h+var_88]
0x18003251d  mov     [rsp+0E8h+KeyHandle], rax
0x180032522  mov     rcx, [rsp+0E8h+arg_28]
0x18003252a  test    rcx, rcx
0x18003252d  jz      short loc_180032539
0x18003252f  cmp     [rsp+0E8h+var_A0], 1
0x180032534  setz    al
0x180032537  mov     [rcx], al
0x180032539  mov     rcx, [rsp+0E8h+arg_20]
0x180032541  mov     rax, [rsp+0E8h+KeyHandle]
0x180032546  mov     [rcx], rax
0x180032549  test    edi, edi
0x18003254b  jns     short loc_180032579
0x18003254d  mov     rcx, [rsp+0E8h+KeyHandle]; Handle
0x180032552  test    rcx, rcx
0x180032555  jz      short loc_180032579
0x180032557  test    cl, 1
0x18003255a  jz      short loc_18003256D
0x18003255c  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180032560  call    ORCloseKey
0x180032565  jmp     short loc_180032579
0x180032567  mov     dword ptr [rsp+0E8h+var_A8], edi
0x18003256b  jmp     short loc_180032549
0x18003256d  call    cs:__imp_ZwClose
0x180032574  nop     dword ptr [rax+rax+00h]
0x180032579  test    r14, r14
0x18003257c  jz      short loc_18003259C
0x18003257e  mov     rcx, gs:60h
0x180032587  mov     r8, r14; P
0x18003258a  xor     edx, edx; Flags
0x18003258c  mov     rcx, [rcx+30h]; HeapHandle
0x180032590  call    cs:__imp_RtlFreeHeap
0x180032597  nop     dword ptr [rax+rax+00h]
0x18003259c  cmp     edi, 0C000017Dh
0x1800325a2  jnz     short loc_1800325E8
0x1800325a4  int     3; Trap to Debugger
0x1800325a5  mov     r14d, [rsp+0E8h+var_90]
0x1800325aa  jmp     short loc_1800325C5
0x1800325ac  mov     r14d, 5
0x1800325b2  mov     esi, [rsp+0E8h+arg_10]
0x1800325b9  mov     r12, [rsp+0E8h+arg_0]
0x1800325c1  mov     edi, dword ptr [rsp+0E8h+var_A8]
0x1800325c5  cmp     r14d, 5
0x1800325c9  jnb     short loc_1800325E8
0x1800325cb  inc     r14d
0x1800325ce  mov     [rsp+0E8h+var_90], r14d
0x1800325d3  mov     r14d, [rsp+0E8h+arg_18]
0x1800325db  mov     rax, [rsp+0E8h+arg_8]
0x1800325e3  jmp     loc_18003233A
0x1800325e8  mov     eax, edi
0x1800325ea  add     rsp, 0B8h
0x1800325f1  pop     r15
0x1800325f3  pop     r14
0x1800325f5  pop     r13
0x1800325f7  pop     r12
0x1800325f9  pop     rdi
0x1800325fa  pop     rsi
0x1800325fb  retn
```
