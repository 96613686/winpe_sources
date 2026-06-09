# sub_140BAA1CC

- ea: `0x140baa1cc`
- end: `0x140baa7f3`
- name: `sub_140BAA1CC`
- size: `1575`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140744450`
- `0x140747500`
- `0x140b8ed4c`

## callees

- `0x140242868`
- `0x140258260`
- `0x1404564f0`
- `0x14046de40`
- `0x1404796e0`
- `0x14053a530`
- `0x14057fe00`
- `0x140583f08`
- `0x140583fcc`
- `0x1405a3228`
- `0x1405a34f4`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dab70`
- `0x1406dac30`
- `0x1406f4880`
- `0x140baa1cc`
- `0x140c55650`

## string_xrefs

- `0x140baa27f`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET`
- `0x140baa252`: `Services\ACPI\Parameters`

## pseudocode

```c
char __fastcall sub_140BAA1CC(char a1)
{
  unsigned int v1; // edi
  NTSTATUS BusData; // eax
  char v4; // r13
  ULONG v5; // esi
  char v6; // r15
  unsigned int v7; // ebx
  unsigned int v8; // r14d
  int v9; // eax
  __int64 v10; // r8
  ULONG v11; // edx
  unsigned __int16 v12; // r10
  bool v13; // zf
  unsigned int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // rcx
  HANDLE v17; // rcx
  char v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 Buffer; // [rsp+41h] [rbp-BFh] BYREF
  char v21; // [rsp+42h] [rbp-BEh]
  int v22; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  ULONG Disposition; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  ULONG ResultLength; // [rsp+60h] [rbp-A0h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v28[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v29[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v30[2]; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING ValueName; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 v32; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v33; // [rsp+E2h] [rbp-1Eh]
  char v34; // [rsp+E8h] [rbp-18h]
  char v35; // [rsp+EEh] [rbp-12h]
  __int128 KeyValueInformation; // [rsp+120h] [rbp+20h] BYREF
  int v37; // [rsp+130h] [rbp+30h]

  v1 = 0;
  KeyHandle = 0;
  v19 = 0;
  Disposition = 0;
  Buffer = 0;
  v22 = 0;
  Handle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(&v32, 0, 0x40u);
  *(_QWORD *)&ValueName.Length = 2490404;
  ValueName.Buffer = L"EnableBXWorkAround";
  v30[0] = 3276848;
  v30[1] = L"Services\\ACPI\\Parameters";
  v29[0] = 1572886;
  v29[1] = L"Control\\HAL";
  v28[0] = 5636180;
  v28[1] = L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET";
  LOBYTE(BusData) = 0;
  v37 = 0;
  KeyValueInformation = 0;
  if ( a1 )
  {
    BusData = _InterlockedIncrement(&dword_140F867D0);
    if ( BusData != 1 )
      return BusData;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v28;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    BusData = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( BusData < 0 )
      return BusData;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v29;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition) < 0 )
      goto LABEL_77;
  }
  else if ( !byte_140F867CC )
  {
    return BusData;
  }
  v21 = 0;
  LOBYTE(BusData) = -(char)sub_1404796E0(0, 0, 0, &v19);
  v4 = 0;
  v5 = 0;
  v6 = (_BYTE)BusData != 0 ? v19 : 0;
  while ( 1 )
  {
    if ( v5 >= 0x100 )
      goto LABEL_69;
    v7 = 0;
    v8 = 0;
LABEL_10:
    if ( v8 < 0x20 )
      break;
    ++v5;
  }
  while ( 1 )
  {
    if ( v1 >= 8 )
    {
LABEL_62:
      ++v8;
      v1 = 0;
      goto LABEL_10;
    }
    v7 = v8 & 0x1F | v7 & 0xFFFFFF00 | (32 * (v1 & 7));
    BusData = HalGetBusData(4, v5, v7, (int)&v32, 2u);
    if ( !BusData )
      goto LABEL_69;
    LOBYTE(BusData) = v32 - 1;
    if ( (unsigned __int16)(v32 - 1) > 0xFFFDu )
    {
      v13 = v1 == 0;
      goto LABEL_60;
    }
    BusData = HalGetBusData(4, v5, v7, (int)&v32, 0x10u);
    if ( !BusData )
      goto LABEL_61;
    v9 = sub_140242868();
    if ( !a1 )
      break;
    LOBYTE(v10) = v34;
    v11 = 1;
    v12 = v32;
    if ( v9 == 1 && !v5 && !v8 && !v1 && v32 == 4358 && (unsigned __int8)v34 < 0x80u )
      sub_140583FCC(0);
    if ( v12 == 0x8086 && ((v33 - 29072) & 0xFFFD) == 0 && (unsigned __int8)v10 <= 2u )
    {
      v21 = v11;
      HalGetBusDataByOffset(PCIConfiguration, v5, v7, &Buffer, 0x57u, v11);
      LOBYTE(v10) = v34;
      v12 = v32;
      if ( ((Buffer >> 5) & ((Buffer & 0x18) != 0)) != 0 )
        byte_140FB99C9 = 1;
    }
    if ( (int)sub_140C55650(v12, v33, v10, &v22) >= 0 )
    {
      if ( (v22 & 2) != 0 )
        byte_140FB9D08 = 1;
      if ( (v22 & 8) != 0 )
        sub_1405A3228(v5, v7);
    }
    if ( v6 != 2 || v4 )
      break;
    LOBYTE(BusData) = -122;
    if ( v32 == 0x8086 )
    {
      if ( v5 )
        goto LABEL_55;
      LOWORD(BusData) = v33;
      if ( v8 != 17 )
        goto LABEL_46;
      if ( v1 || v33 != 0x98D0 )
      {
        if ( v1 != 1 )
          goto LABEL_56;
        if ( v33 != 0x98D1 )
        {
LABEL_46:
          if ( v8 != 16 )
            goto LABEL_56;
          if ( (v1 != 6 || v33 != 0xA0D0) && (v1 != 7 || v33 != 0xA0D1) )
          {
            if ( v1 != 6 )
              goto LABEL_51;
            if ( v33 != 17360 )
              goto LABEL_56;
            if ( v34 )
            {
LABEL_51:
              if ( v1 != 7 || v33 != 17361 )
                goto LABEL_56;
              if ( v34 )
                goto LABEL_61;
            }
          }
        }
      }
      v4 = 1;
      sub_140583F08(23);
      sub_140583F08(22);
      break;
    }
LABEL_57:
    if ( v1 )
      goto LABEL_61;
    v13 = v35 >= 0;
LABEL_60:
    if ( v13 )
      goto LABEL_62;
LABEL_61:
    ++v1;
  }
  LOBYTE(BusData) = -122;
  if ( v32 != 0x8086 )
    goto LABEL_57;
LABEL_55:
  LOWORD(BusData) = v33;
LABEL_56:
  if ( (_WORD)BusData != 28944 )
    goto LABEL_57;
  byte_140F867CC = 1;
  v14 = v7 & 0xFFFFFF1F | 0x60;
  HalGetBusData(4, v5, v14, (int)&v32, 0x40u);
  LOBYTE(v16) = v34;
  byte_140FB99E4 = v34;
  if ( (dword_140FB9A54 & 2) == 0 )
    KeBugCheckEx(0x5Cu, 0x111u, (ULONG_PTR)"minkernel\\hals\\lib\\acpi\\xxacpi.c", 0x663u, 0);
  if ( (unsigned __int8)v34 <= 1u )
  {
    BusNumber = v5;
    SlotNumber = v14;
    HalGetBusDataByOffset(PCIConfiguration, v5, v14, &dword_140FB99DC, 0x58u, 4u);
    dword_140FB99DC |= 0x23u;
    HalSetBusDataByOffset(PCIConfiguration, BusNumber, SlotNumber, &dword_140FB99DC, 0x58u, 4u);
  }
  LOBYTE(v15) = 1;
  LOBYTE(BusData) = sub_1405A34F4(v16, v5, v14 & 0xFFFFFF5F, v15);
LABEL_69:
  if ( a1 )
  {
    v17 = Handle;
    if ( Handle )
    {
      ZwClose(Handle);
      v17 = 0;
      Handle = 0;
    }
    if ( v21 )
    {
      ObjectAttributes.RootDirectory = KeyHandle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)v30;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwCreateKey(&Handle, 0x20019u, &ObjectAttributes, 0, 0, 0, &Disposition) >= 0
        && ZwQueryValueKey(Handle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 0x14u, &ResultLength) >= 0
        && DWORD2(KeyValueInformation) )
      {
        byte_140FB99C9 = BYTE12(KeyValueInformation);
      }
LABEL_77:
      v17 = Handle;
    }
    if ( v17 )
      ZwClose(v17);
    if ( KeyHandle )
      ZwClose(KeyHandle);
    LOBYTE(BusData) = KeSetEvent(&stru_140F867E0, 0, 0);
  }
  return BusData;
}

```

## disassembly

```asm
0x140baa1cc  push    rbp
0x140baa1ce  push    rbx
0x140baa1cf  push    rsi
0x140baa1d0  push    rdi
0x140baa1d1  push    r12
0x140baa1d3  push    r13
0x140baa1d5  push    r14
0x140baa1d7  push    r15
0x140baa1d9  lea     rbp, [rsp-48h]
0x140baa1de  sub     rsp, 148h
0x140baa1e5  mov     rax, cs:__security_cookie
0x140baa1ec  xor     rax, rsp
0x140baa1ef  mov     [rbp+80h+var_48], rax
0x140baa1f3  xor     edi, edi
0x140baa1f5  xorps   xmm0, xmm0
0x140baa1f8  mov     r12b, cl
0x140baa1fb  mov     [rsp+180h+KeyHandle], rdi
0x140baa200  movups  xmmword ptr [rsp+180h+ObjectAttributes.ObjectName], xmm0
0x140baa205  xor     eax, eax
0x140baa207  mov     [rsp+180h+var_140], dil
0x140baa20c  lea     ebx, [rdi+40h]
0x140baa20f  mov     [rsp+180h+var_130], edi
0x140baa213  mov     r8d, ebx; Size
0x140baa216  mov     [rsp+180h+Buffer], dil
0x140baa21b  xor     edx, edx; Val
0x140baa21d  mov     [rsp+180h+var_13C], edi
0x140baa221  lea     rcx, [rbp+80h+var_A0]; void *
0x140baa225  mov     [rsp+180h+Handle], rdi
0x140baa22a  mov     [rsp+180h+ResultLength], edi
0x140baa22e  movups  xmmword ptr [rsp+180h+ObjectAttributes.Length], xmm0
0x140baa233  movups  xmmword ptr [rbp+80h+ObjectAttributes+1Ch], xmm0
0x140baa237  call    memset_0
0x140baa23c  lea     rax, aEnablebxworkar; "EnableBXWorkAround"
0x140baa243  mov     qword ptr [rbp+80h+ValueName.Length], 260024h
0x140baa24b  mov     [rbp+80h+ValueName.Buffer], rax
0x140baa24f  lea     esi, [rdi+30h]
0x140baa252  lea     rax, aServicesAcpiPa; "Services\\ACPI\\Parameters"
0x140baa259  mov     [rbp+80h+var_C8], 320030h
0x140baa261  mov     [rbp+80h+var_C0], rax
0x140baa265  lea     r14d, [rdi+1]
0x140baa269  lea     rax, aControlHal; "Control\\HAL"
0x140baa270  mov     [rbp+80h+var_D8], 180016h
0x140baa278  mov     [rbp+80h+var_D0], rax
0x140baa27c  xorps   xmm0, xmm0
0x140baa27f  lea     rax, aRegistryMachin_146; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140baa286  mov     [rbp+80h+var_E8], 560054h
0x140baa28e  mov     [rbp+80h+var_E0], rax
0x140baa292  mov     r15d, 20019h
0x140baa298  xor     eax, eax
0x140baa29a  mov     [rbp+80h+var_50], eax
0x140baa29d  movups  [rbp+80h+KeyValueInformation], xmm0
0x140baa2a1  test    r12b, r12b
0x140baa2a4  jnz     short loc_140BAA2B8
0x140baa2a6  cmp     cs:byte_140F867CC, dil
0x140baa2ad  jnz     loc_140BAA355
0x140baa2b3  jmp     loc_140BAA7D2
0x140baa2b8  mov     eax, r14d
0x140baa2bb  lock xadd cs:dword_140F867D0, eax
0x140baa2c3  add     eax, r14d
0x140baa2c6  cmp     eax, r14d
0x140baa2c9  jnz     loc_140BAA7D2
0x140baa2cf  lea     rax, [rbp+80h+var_E8]
0x140baa2d3  mov     [rsp+180h+ObjectAttributes.Length], esi
0x140baa2d7  lea     r8, [rsp+180h+ObjectAttributes]; ObjectAttributes
0x140baa2dc  mov     [rsp+180h+ObjectAttributes.ObjectName], rax
0x140baa2e1  mov     edx, r15d; DesiredAccess
0x140baa2e4  mov     [rsp+180h+ObjectAttributes.RootDirectory], rdi
0x140baa2e9  lea     rcx, [rsp+180h+KeyHandle]; KeyHandle
0x140baa2ee  mov     [rbp+80h+ObjectAttributes.Attributes], ebx
0x140baa2f1  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x140baa2f6  call    ZwOpenKey
0x140baa2fb  test    eax, eax
0x140baa2fd  js      loc_140BAA7D2
0x140baa303  mov     rax, [rsp+180h+KeyHandle]
0x140baa308  lea     r8, [rsp+180h+ObjectAttributes]; ObjectAttributes
0x140baa30d  mov     [rsp+180h+ObjectAttributes.RootDirectory], rax
0x140baa312  lea     rcx, [rsp+180h+Handle]; KeyHandle
0x140baa317  lea     rax, [rbp+80h+var_D8]
0x140baa31b  mov     [rsp+180h+ObjectAttributes.Length], esi
0x140baa31f  mov     [rsp+180h+ObjectAttributes.ObjectName], rax
0x140baa324  xorps   xmm0, xmm0
0x140baa327  lea     rax, [rsp+180h+var_130]
0x140baa32c  mov     [rbp+80h+ObjectAttributes.Attributes], ebx
0x140baa32f  mov     [rsp+180h+Disposition], rax; Disposition
0x140baa334  xor     r9d, r9d; TitleIndex
0x140baa337  mov     [rsp+180h+CreateOptions], edi; CreateOptions
0x140baa33b  mov     edx, r15d; DesiredAccess
0x140baa33e  mov     [rsp+180h+Class], rdi; Class
0x140baa343  movdqu  xmmword ptr [rbp+80h+ObjectAttributes.SecurityDescriptor], xmm0
0x140baa348  call    ZwCreateKey
0x140baa34d  test    eax, eax
0x140baa34f  js      loc_140BAA7A3
0x140baa355  lea     r9, [rsp+180h+var_140]
0x140baa35a  mov     [rsp+180h+var_13E], dil
0x140baa35f  xor     r8d, r8d
0x140baa362  xor     edx, edx
0x140baa364  xor     ecx, ecx
0x140baa366  call    sub_1404796E0
0x140baa36b  neg     al
0x140baa36d  mov     r13b, dil
0x140baa370  mov     esi, edi
0x140baa372  sbb     r15b, r15b
0x140baa375  and     r15b, [rsp+180h+var_140]
0x140baa37a  cmp     esi, 100h
0x140baa380  jnb     loc_140BAA6E3
0x140baa386  mov     ebx, edi
0x140baa388  mov     r14d, edi
0x140baa38b  cmp     r14d, 20h ; ' '
0x140baa38f  jnb     loc_140BAA5F0
0x140baa395  cmp     edi, 8
0x140baa398  jnb     loc_140BAA5E6
0x140baa39e  mov     eax, ebx
0x140baa3a0  mov     dword ptr [rsp+180h+Class], 2; ULONG
0x140baa3a8  and     eax, 0FFFFFF00h
0x140baa3ad  lea     r9, [rbp+80h+var_A0]; int
0x140baa3b1  mov     ecx, edi
0x140baa3b3  mov     edx, esi; int
0x140baa3b5  and     ecx, 7
0x140baa3b8  shl     ecx, 5
0x140baa3bb  mov     ebx, ecx
0x140baa3bd  mov     ecx, 4; int
0x140baa3c2  or      ebx, eax
0x140baa3c4  mov     eax, r14d
0x140baa3c7  and     eax, 1Fh
0x140baa3ca  or      ebx, eax
0x140baa3cc  mov     r8d, ebx; int
0x140baa3cf  call    HalGetBusData
0x140baa3d4  test    eax, eax
0x140baa3d6  jz      loc_140BAA6DB
0x140baa3dc  movzx   eax, [rbp+80h+var_A0]
0x140baa3e0  mov     ecx, 0FFFDh
0x140baa3e5  dec     ax
0x140baa3e8  cmp     ax, cx
0x140baa3eb  ja      loc_140BAA5DB
0x140baa3f1  lea     r9, [rbp+80h+var_A0]; int
0x140baa3f5  mov     dword ptr [rsp+180h+Class], 10h; ULONG
0x140baa3fd  mov     r8d, ebx; int
0x140baa400  mov     edx, esi; int
0x140baa402  mov     ecx, 4; int
0x140baa407  call    HalGetBusData
0x140baa40c  test    eax, eax
0x140baa40e  jz      loc_140BAA5DF
0x140baa414  call    sub_140242868
0x140baa419  test    r12b, r12b
0x140baa41c  jz      loc_140BAA5B8
0x140baa422  mov     r8b, [rbp+80h+var_98]
0x140baa426  mov     edx, 1
0x140baa42b  movzx   r10d, [rbp+80h+var_A0]
0x140baa430  cmp     eax, edx
0x140baa432  jnz     short loc_140BAA459
0x140baa434  test    esi, esi
0x140baa436  jnz     short loc_140BAA459
0x140baa438  test    r14d, r14d
0x140baa43b  jnz     short loc_140BAA459
0x140baa43d  test    edi, edi
0x140baa43f  jnz     short loc_140BAA459
0x140baa441  mov     eax, 1106h
0x140baa446  cmp     r10w, ax
0x140baa44a  jnz     short loc_140BAA459
0x140baa44c  cmp     r8b, 80h
0x140baa450  jnb     short loc_140BAA459
0x140baa452  xor     ecx, ecx
0x140baa454  call    sub_140583FCC
0x140baa459  mov     eax, 8086h
0x140baa45e  cmp     r10w, ax
0x140baa462  jnz     short loc_140BAA4CB
0x140baa464  movzx   eax, [rbp+80h+var_A0+2]
0x140baa468  mov     ecx, 7190h
0x140baa46d  sub     ax, cx
0x140baa470  mov     ecx, 0FFFDh
0x140baa475  test    cx, ax
0x140baa478  jnz     short loc_140BAA4CB
0x140baa47a  cmp     r8b, 2
0x140baa47e  ja      short loc_140BAA4CB
0x140baa480  mov     [rsp+180h+CreateOptions], edx; Length
0x140baa484  lea     r9, [rsp+180h+Buffer]; Buffer
0x140baa489  mov     [rsp+180h+var_13E], dl
0x140baa48d  mov     r8d, ebx; SlotNumber
0x140baa490  mov     edx, esi; BusNumber
0x140baa492  mov     dword ptr [rsp+180h+Class], 57h ; 'W'; Offset
0x140baa49a  mov     ecx, 4; BusDataType
0x140baa49f  call    HalGetBusDataByOffset
0x140baa4a4  mov     cl, [rsp+180h+Buffer]
0x140baa4a8  mov     r8b, [rbp+80h+var_98]
0x140baa4ac  test    cl, 18h
0x140baa4af  movzx   r10d, [rbp+80h+var_A0]
0x140baa4b4  setnz   al
0x140baa4b7  shr     cl, 5
0x140baa4ba  and     al, cl
0x140baa4bc  mov     ecx, 1
0x140baa4c1  test    cl, al
0x140baa4c3  jz      short loc_140BAA4CB
0x140baa4c5  mov     cs:byte_140FB99C9, cl
0x140baa4cb  movzx   edx, [rbp+80h+var_A0+2]
0x140baa4cf  lea     r9, [rsp+180h+var_13C]
0x140baa4d4  movzx   ecx, r10w
0x140baa4d8  call    sub_140C55650
0x140baa4dd  test    eax, eax
0x140baa4df  js      short loc_140BAA4FF
0x140baa4e1  test    byte ptr [rsp+180h+var_13C], 2
0x140baa4e6  jz      short loc_140BAA4EF
0x140baa4e8  mov     cs:byte_140FB9D08, 1
0x140baa4ef  test    byte ptr [rsp+180h+var_13C], 8
0x140baa4f4  jz      short loc_140BAA4FF
0x140baa4f6  mov     edx, ebx; SlotNumber
0x140baa4f8  mov     ecx, esi; BusNumber
0x140baa4fa  call    sub_1405A3228
0x140baa4ff  cmp     r15b, 2
0x140baa503  jnz     loc_140BAA5B8
0x140baa509  test    r13b, r13b
0x140baa50c  jnz     loc_140BAA5B8
0x140baa512  mov     eax, 8086h
0x140baa517  cmp     [rbp+80h+var_A0], ax
0x140baa51b  jnz     loc_140BAA5D1
0x140baa521  test    esi, esi
0x140baa523  jnz     loc_140BAA5C3
0x140baa529  movzx   eax, [rbp+80h+var_A0+2]
0x140baa52d  cmp     r14d, 11h
0x140baa531  jnz     short loc_140BAA554
0x140baa533  test    edi, edi
0x140baa535  jnz     short loc_140BAA541
0x140baa537  mov     ecx, 98D0h
0x140baa53c  cmp     ax, cx
0x140baa53f  jz      short loc_140BAA5A1
0x140baa541  mov     ecx, 1
0x140baa546  cmp     edi, ecx
0x140baa548  jnz     short loc_140BAA5C7
0x140baa54a  mov     ecx, 98D1h
0x140baa54f  cmp     ax, cx
0x140baa552  jz      short loc_140BAA5A1
0x140baa554  cmp     r14d, 10h
0x140baa558  jnz     short loc_140BAA5C7
0x140baa55a  cmp     edi, 6
0x140baa55d  jnz     short loc_140BAA569
0x140baa55f  mov     ecx, 0A0D0h
0x140baa564  cmp     ax, cx
0x140baa567  jz      short loc_140BAA5A1
0x140baa569  cmp     edi, 7
0x140baa56c  jnz     short loc_140BAA578
0x140baa56e  mov     ecx, 0A0D1h
0x140baa573  cmp     ax, cx
0x140baa576  jz      short loc_140BAA5A1
0x140baa578  mov     cl, [rbp+80h+var_98]
0x140baa57b  cmp     edi, 6
0x140baa57e  jnz     short loc_140BAA58E
0x140baa580  mov     edx, 43D0h
0x140baa585  cmp     ax, dx
0x140baa588  jnz     short loc_140BAA5C7
0x140baa58a  test    cl, cl
0x140baa58c  jz      short loc_140BAA5A1
0x140baa58e  cmp     edi, 7
0x140baa591  jnz     short loc_140BAA5C7
0x140baa593  mov     edx, 43D1h
0x140baa598  cmp     ax, dx
0x140baa59b  jnz     short loc_140BAA5C7
0x140baa59d  test    cl, cl
0x140baa59f  jnz     short loc_140BAA5DF
0x140baa5a1  mov     ecx, 17h
0x140baa5a6  mov     r13b, 1
0x140baa5a9  call    sub_140583F08
0x140baa5ae  mov     ecx, 16h
0x140baa5b3  call    sub_140583F08
0x140baa5b8  mov     eax, 8086h
0x140baa5bd  cmp     [rbp+80h+var_A0], ax
0x140baa5c1  jnz     short loc_140BAA5D1
0x140baa5c3  movzx   eax, [rbp+80h+var_A0+2]
0x140baa5c7  mov     ecx, 7110h
0x140baa5cc  cmp     ax, cx
0x140baa5cf  jz      short loc_140BAA5FE
0x140baa5d1  test    edi, edi
0x140baa5d3  jnz     short loc_140BAA5DF
0x140baa5d5  test    [rbp+80h+var_92], 80h
0x140baa5d9  jmp     short loc_140BAA5DD
0x140baa5db  test    edi, edi
0x140baa5dd  jz      short loc_140BAA5E6
0x140baa5df  inc     edi
0x140baa5e1  jmp     loc_140BAA395
0x140baa5e6  inc     r14d
0x140baa5e9  xor     edi, edi
0x140baa5eb  jmp     loc_140BAA38B
0x140baa5f0  mov     r14d, 1
0x140baa5f6  add     esi, r14d
0x140baa5f9  jmp     loc_140BAA37A
0x140baa5fe  mov     r14d, 1
0x140baa604  mov     dword ptr [rsp+180h+Class], 40h ; '@'; ULONG
0x140baa60c  btr     ebx, 7
0x140baa610  mov     cs:byte_140F867CC, r14b
0x140baa617  or      ebx, 60h
0x140baa61a  lea     r9, [rbp+80h+var_A0]; int
0x140baa61e  mov     r8d, ebx; int
0x140baa621  mov     edx, esi; int
0x140baa623  lea     r15d, [r14+3]
0x140baa627  mov     ecx, r15d; int
0x140baa62a  call    HalGetBusData
0x140baa62f  mov     cl, [rbp+80h+var_98]
0x140baa632  mov     eax, cs:dword_140FB9A54
0x140baa638  mov     cs:byte_140FB99E4, cl
0x140baa63e  test    al, 2
0x140baa640  jnz     short loc_140BAA667
0x140baa642  mov     r9d, 663h; BugCheckParameter3
  ... truncated ...
```
