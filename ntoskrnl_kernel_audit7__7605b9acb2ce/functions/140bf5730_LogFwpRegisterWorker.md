# LogFwpRegisterWorker

- ea: `0x140bf5730`
- end: `0x140bf5e62`
- name: `LogFwpRegisterWorker`
- size: `1842`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140403380`
- `0x1406dd5c0`
- `0x1406dd620`
- `0x1406dd780`
- `0x1406ddfe0`
- `0x140bf5730`

## string_xrefs

- `0x140bf5abc`: `ResidentSize`
- `0x140bf574e`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control`
- `0x140bf5e06`: `CompressBitmaps`

## pseudocode

```c
int LogFwpRegisterWorker()
{
  int result; // eax
  NTSTATUS v1; // eax
  HANDLE v2; // rcx
  int v3; // ebx
  HANDLE KeyHandle; // [rsp+40h] [rbp+7h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp+Fh] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+1Fh] BYREF
  int Data; // [rsp+A8h] [rbp+6Fh] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp+77h] BYREF
  HANDLE v9; // [rsp+B8h] [rbp+7Fh] BYREF

  Disposition = 0;
  Data = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v9 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"BGFX");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateKey(&v9, 0x20019u, &ObjectAttributes, 0, 0, 1u, &Disposition);
    v2 = KeyHandle;
    if ( v1 >= 0 )
    {
      v3 = dword_140ED5E10;
      ZwClose(KeyHandle);
      RtlInitUnicodeString(&DestinationString, L"Resume");
      Data = (v3 & 0x100000) != 0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"Width");
      Data = qword_140ED5DF0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"Height");
      Data = HIDWORD(qword_140ED5DF0);
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"BPP");
      Data = dword_140ED5DB8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"LogoSize");
      Data = Size;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressFrames");
      Data = dword_140ED5E0C;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressMemory");
      Data = dword_140EDA2D0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressProlog");
      Data = 1000000 * qword_140ED5DE8 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressLow");
      Data = 1000000 * qword_140E139B0 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressHigh");
      Data = 1000000 * qword_140ED5DC0 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      if ( qword_140EDA2E0 )
      {
        RtlInitUnicodeString(&DestinationString, L"ResidentSize");
        Data = *(_DWORD *)qword_140EDA2E0;
        ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      }
      RtlInitUnicodeString(&DestinationString, L"ProgressTotal");
      Data = 1000000 * qword_140ED5E28 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressManual");
      Data = 1000000 * qword_140ED5E18 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeProlog");
      Data = 1000000 * qword_140ED5E00 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeOverlap");
      Data = dword_140ED5DE0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeIo");
      Data = dword_140ED5E08;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeCpu");
      Data = dword_140ED5DB4;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeFrames");
      Data = dword_140ED5DB0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeMemory");
      Data = dword_140EDA2CC;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeLow");
      Data = 1000000 * qword_140E139B8 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeHigh");
      Data = 1000000 * qword_140ED5DA8 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeTotal");
      Data = 1000000 * qword_140ED5E20 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"AnimationTotal");
      Data = 1000000 * qword_140ED5D98 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"CompressBitmaps");
      Data = 1000000 * qword_140E4B0C8 / qword_140E139A8;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      v2 = v9;
    }
    return ZwClose(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140bf5730  mov     [rsp-8+arg_0], rbx
0x140bf5735  push    rbp
0x140bf5736  lea     rbp, [rsp-57h]
0x140bf573b  sub     rsp, 90h
0x140bf5742  xorps   xmm0, xmm0
0x140bf5745  mov     [rbp+57h+arg_10], 0
0x140bf574c  xor     eax, eax
0x140bf574e  lea     rdx, aRegistryMachin_198; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140bf5755  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140bf5759  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf575d  mov     [rbp+57h+Data], eax
0x140bf5760  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140bf5764  mov     [rbp+57h+KeyHandle], rax
0x140bf5768  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140bf576c  mov     [rbp+57h+arg_18], rax
0x140bf5770  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140bf5774  call    RtlInitUnicodeString
0x140bf5779  lea     rax, [rbp+57h+DestinationString]
0x140bf577d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140bf5785  xorps   xmm0, xmm0
0x140bf5788  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140bf578c  mov     ebx, 30h ; '0'
0x140bf5791  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140bf5798  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140bf579c  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x140bf579f  mov     edx, 20019h; DesiredAccess
0x140bf57a4  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140bf57a8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140bf57ad  call    ZwOpenKey
0x140bf57b2  test    eax, eax
0x140bf57b4  js      short loc_140BF5824
0x140bf57b6  lea     rdx, aBgfx; "BGFX"
0x140bf57bd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf57c1  call    RtlInitUnicodeString
0x140bf57c6  mov     rax, [rbp+57h+KeyHandle]
0x140bf57ca  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140bf57ce  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140bf57d2  lea     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf57d6  lea     rax, [rbp+57h+DestinationString]
0x140bf57da  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x140bf57dd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140bf57e1  xorps   xmm0, xmm0
0x140bf57e4  lea     rax, [rbp+57h+arg_10]
0x140bf57e8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140bf57ef  mov     [rsp+90h+Disposition], rax; Disposition
0x140bf57f4  xor     r9d, r9d; TitleIndex
0x140bf57f7  mov     [rsp+90h+CreateOptions], 1; CreateOptions
0x140bf57ff  mov     edx, 20019h; DesiredAccess
0x140bf5804  mov     [rsp+90h+Class], 0; Class
0x140bf580d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140bf5812  call    ZwCreateKey
0x140bf5817  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140bf581b  test    eax, eax
0x140bf581d  jns     short loc_140BF5836
0x140bf581f  call    ZwClose
0x140bf5824  mov     rbx, [rsp+90h+arg_0]
0x140bf582c  add     rsp, 90h
0x140bf5833  pop     rbp
0x140bf5834  retn
0x140bf5836  mov     ebx, cs:dword_140ED5E10
0x140bf583c  call    ZwClose
0x140bf5841  lea     rdx, aResume; "Resume"
0x140bf5848  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf584c  call    RtlInitUnicodeString
0x140bf5851  mov     [rbp+57h+Data], 0
0x140bf5858  bt      ebx, 14h
0x140bf585c  jb      loc_140BF5E56
0x140bf5862  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5866  lea     rax, [rbp+57h+Data]
0x140bf586a  mov     ebx, 4
0x140bf586f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5873  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5877  mov     r9d, ebx; Type
0x140bf587a  xor     r8d, r8d; TitleIndex
0x140bf587d  mov     [rsp+90h+Class], rax; Data
0x140bf5882  call    ZwSetValueKey
0x140bf5887  lea     rdx, aWidth; "Width"
0x140bf588e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5892  call    RtlInitUnicodeString
0x140bf5897  mov     eax, dword ptr cs:qword_140ED5DF0
0x140bf589d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf58a1  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf58a5  mov     r9d, ebx; Type
0x140bf58a8  mov     [rbp+57h+Data], eax
0x140bf58ab  xor     r8d, r8d; TitleIndex
0x140bf58ae  lea     rax, [rbp+57h+Data]
0x140bf58b2  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf58b6  mov     [rsp+90h+Class], rax; Data
0x140bf58bb  call    ZwSetValueKey
0x140bf58c0  lea     rdx, aHeight; "Height"
0x140bf58c7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf58cb  call    RtlInitUnicodeString
0x140bf58d0  mov     eax, dword ptr cs:qword_140ED5DF0+4
0x140bf58d6  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf58da  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf58de  mov     r9d, ebx; Type
0x140bf58e1  mov     [rbp+57h+Data], eax
0x140bf58e4  xor     r8d, r8d; TitleIndex
0x140bf58e7  lea     rax, [rbp+57h+Data]
0x140bf58eb  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf58ef  mov     [rsp+90h+Class], rax; Data
0x140bf58f4  call    ZwSetValueKey
0x140bf58f9  lea     rdx, aBpp; "BPP"
0x140bf5900  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5904  call    RtlInitUnicodeString
0x140bf5909  mov     eax, cs:dword_140ED5DB8
0x140bf590f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5913  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5917  mov     r9d, ebx; Type
0x140bf591a  mov     [rbp+57h+Data], eax
0x140bf591d  xor     r8d, r8d; TitleIndex
0x140bf5920  lea     rax, [rbp+57h+Data]
0x140bf5924  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5928  mov     [rsp+90h+Class], rax; Data
0x140bf592d  call    ZwSetValueKey
0x140bf5932  lea     rdx, aLogosize; "LogoSize"
0x140bf5939  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf593d  call    RtlInitUnicodeString
0x140bf5942  mov     eax, cs:Size
0x140bf5948  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf594c  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5950  mov     r9d, ebx; Type
0x140bf5953  mov     [rbp+57h+Data], eax
0x140bf5956  xor     r8d, r8d; TitleIndex
0x140bf5959  lea     rax, [rbp+57h+Data]
0x140bf595d  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5961  mov     [rsp+90h+Class], rax; Data
0x140bf5966  call    ZwSetValueKey
0x140bf596b  lea     rdx, aProgressframes; "ProgressFrames"
0x140bf5972  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5976  call    RtlInitUnicodeString
0x140bf597b  mov     eax, cs:dword_140ED5E0C
0x140bf5981  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5985  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5989  mov     r9d, ebx; Type
0x140bf598c  mov     [rbp+57h+Data], eax
0x140bf598f  xor     r8d, r8d; TitleIndex
0x140bf5992  lea     rax, [rbp+57h+Data]
0x140bf5996  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf599a  mov     [rsp+90h+Class], rax; Data
0x140bf599f  call    ZwSetValueKey
0x140bf59a4  lea     rdx, aProgressmemory; "ProgressMemory"
0x140bf59ab  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf59af  call    RtlInitUnicodeString
0x140bf59b4  mov     eax, cs:dword_140EDA2D0
0x140bf59ba  mov     [rbp+57h+Data], eax
0x140bf59bd  lea     rax, [rbp+57h+Data]
0x140bf59c1  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf59c5  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf59c9  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf59cd  mov     r9d, ebx; Type
0x140bf59d0  mov     [rsp+90h+Class], rax; Data
0x140bf59d5  xor     r8d, r8d; TitleIndex
0x140bf59d8  call    ZwSetValueKey
0x140bf59dd  lea     rdx, aProgressprolog_0; "ProgressProlog"
0x140bf59e4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf59e8  call    RtlInitUnicodeString
0x140bf59ed  imul    rax, cs:qword_140ED5DE8, 0F4240h
0x140bf59f8  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf59fc  mov     r9d, ebx; Type
0x140bf59ff  cqo
0x140bf5a01  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5a05  idiv    cs:qword_140E139A8
0x140bf5a0c  xor     r8d, r8d; TitleIndex
0x140bf5a0f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5a13  mov     [rbp+57h+Data], eax
0x140bf5a16  lea     rax, [rbp+57h+Data]
0x140bf5a1a  mov     [rsp+90h+Class], rax; Data
0x140bf5a1f  call    ZwSetValueKey
0x140bf5a24  lea     rdx, aProgresslow; "ProgressLow"
0x140bf5a2b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5a2f  call    RtlInitUnicodeString
0x140bf5a34  imul    rax, cs:qword_140E139B0, 0F4240h
0x140bf5a3f  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5a43  mov     r9d, ebx; Type
0x140bf5a46  cqo
0x140bf5a48  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5a4c  idiv    cs:qword_140E139A8
0x140bf5a53  xor     r8d, r8d; TitleIndex
0x140bf5a56  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5a5a  mov     [rbp+57h+Data], eax
0x140bf5a5d  lea     rax, [rbp+57h+Data]
0x140bf5a61  mov     [rsp+90h+Class], rax; Data
0x140bf5a66  call    ZwSetValueKey
0x140bf5a6b  lea     rdx, aProgresshigh; "ProgressHigh"
0x140bf5a72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5a76  call    RtlInitUnicodeString
0x140bf5a7b  imul    rax, cs:qword_140ED5DC0, 0F4240h
0x140bf5a86  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5a8a  mov     r9d, ebx; Type
0x140bf5a8d  cqo
0x140bf5a8f  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5a93  idiv    cs:qword_140E139A8
0x140bf5a9a  xor     r8d, r8d; TitleIndex
0x140bf5a9d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5aa1  mov     [rbp+57h+Data], eax
0x140bf5aa4  lea     rax, [rbp+57h+Data]
0x140bf5aa8  mov     [rsp+90h+Class], rax; Data
0x140bf5aad  call    ZwSetValueKey
0x140bf5ab2  cmp     cs:qword_140EDA2E0, 0
0x140bf5aba  jz      short loc_140BF5AF8
0x140bf5abc  lea     rdx, aResidentsize; "ResidentSize"
0x140bf5ac3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5ac7  call    RtlInitUnicodeString
0x140bf5acc  mov     rax, cs:qword_140EDA2E0
0x140bf5ad3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5ad7  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5adb  mov     r9d, ebx; Type
0x140bf5ade  xor     r8d, r8d; TitleIndex
0x140bf5ae1  mov     ecx, [rax]
0x140bf5ae3  lea     rax, [rbp+57h+Data]
0x140bf5ae7  mov     [rbp+57h+Data], ecx
0x140bf5aea  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5aee  mov     [rsp+90h+Class], rax; Data
0x140bf5af3  call    ZwSetValueKey
0x140bf5af8  lea     rdx, aProgresstotal; "ProgressTotal"
0x140bf5aff  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5b03  call    RtlInitUnicodeString
0x140bf5b08  imul    rax, cs:qword_140ED5E28, 0F4240h
0x140bf5b13  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5b17  mov     r9d, ebx; Type
0x140bf5b1a  cqo
0x140bf5b1c  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5b20  idiv    cs:qword_140E139A8
0x140bf5b27  xor     r8d, r8d; TitleIndex
0x140bf5b2a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5b2e  mov     [rbp+57h+Data], eax
0x140bf5b31  lea     rax, [rbp+57h+Data]
0x140bf5b35  mov     [rsp+90h+Class], rax; Data
0x140bf5b3a  call    ZwSetValueKey
0x140bf5b3f  lea     rdx, aProgressmanual_0; "ProgressManual"
0x140bf5b46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5b4a  call    RtlInitUnicodeString
0x140bf5b4f  imul    rax, cs:qword_140ED5E18, 0F4240h
0x140bf5b5a  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5b5e  mov     r9d, ebx; Type
0x140bf5b61  cqo
0x140bf5b63  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5b67  idiv    cs:qword_140E139A8
0x140bf5b6e  xor     r8d, r8d; TitleIndex
0x140bf5b71  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5b75  mov     [rbp+57h+Data], eax
0x140bf5b78  lea     rax, [rbp+57h+Data]
0x140bf5b7c  mov     [rsp+90h+Class], rax; Data
0x140bf5b81  call    ZwSetValueKey
0x140bf5b86  lea     rdx, aFadeprolog; "FadeProlog"
0x140bf5b8d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5b91  call    RtlInitUnicodeString
0x140bf5b96  imul    rax, cs:qword_140ED5E00, 0F4240h
0x140bf5ba1  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5ba5  mov     r9d, ebx; Type
0x140bf5ba8  cqo
0x140bf5baa  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5bae  idiv    cs:qword_140E139A8
0x140bf5bb5  xor     r8d, r8d; TitleIndex
0x140bf5bb8  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5bbc  mov     [rbp+57h+Data], eax
0x140bf5bbf  lea     rax, [rbp+57h+Data]
0x140bf5bc3  mov     [rsp+90h+Class], rax; Data
0x140bf5bc8  call    ZwSetValueKey
0x140bf5bcd  lea     rdx, aFadeoverlap; "FadeOverlap"
0x140bf5bd4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5bd8  call    RtlInitUnicodeString
0x140bf5bdd  mov     eax, cs:dword_140ED5DE0
0x140bf5be3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5be7  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5beb  mov     r9d, ebx; Type
0x140bf5bee  mov     [rbp+57h+Data], eax
0x140bf5bf1  xor     r8d, r8d; TitleIndex
0x140bf5bf4  lea     rax, [rbp+57h+Data]
0x140bf5bf8  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5bfc  mov     [rsp+90h+Class], rax; Data
0x140bf5c01  call    ZwSetValueKey
0x140bf5c06  lea     rdx, aFadeio; "FadeIo"
0x140bf5c0d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5c11  call    RtlInitUnicodeString
0x140bf5c16  mov     eax, cs:dword_140ED5E08
0x140bf5c1c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5c20  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5c24  mov     r9d, ebx; Type
0x140bf5c27  mov     [rbp+57h+Data], eax
0x140bf5c2a  xor     r8d, r8d; TitleIndex
0x140bf5c2d  lea     rax, [rbp+57h+Data]
0x140bf5c31  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5c35  mov     [rsp+90h+Class], rax; Data
0x140bf5c3a  call    ZwSetValueKey
0x140bf5c3f  lea     rdx, aFadecpu; "FadeCpu"
0x140bf5c46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf5c4a  call    RtlInitUnicodeString
0x140bf5c4f  mov     eax, cs:dword_140ED5DB4
0x140bf5c55  mov     r9d, ebx; Type
0x140bf5c58  mov     [rbp+57h+Data], eax
0x140bf5c5b  xor     r8d, r8d; TitleIndex
0x140bf5c5e  lea     rax, [rbp+57h+Data]
0x140bf5c62  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf5c66  mov     [rsp+90h+Class], rax; Data
0x140bf5c6b  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf5c6f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf5c73  call    ZwSetValueKey
0x140bf5c78  lea     rdx, aFadeframes; "FadeFrames"
  ... truncated ...
```
