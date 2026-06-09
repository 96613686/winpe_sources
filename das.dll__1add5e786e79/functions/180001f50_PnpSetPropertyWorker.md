# _PnpSetPropertyWorker

- ea: `0x180001f50`
- end: `0x1800026a3`
- name: `_PnpSetPropertyWorker`
- size: `1875`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, ULONG)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001ab0`

## callees

- `0x180001900`
- `0x180001f50`
- `0x1800026b0`
- `0x1800037f0`
- `0x180003bf0`
- `0x1800049f0`
- `0x18001df70`
- `0x18003bc80`
- `0x18003c858`
- `0x180065744`
- `0x18007d328`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180002320`
- `ntdll!NtCreateKey` at `0x1800023d7`
- `ntdll!NtCreateKey` at `0x1800024ae`
- `ntdll!NtCreateKey` at `0x180002320`
- `ntdll!NtCreateKey` at `0x1800023d7`
- `ntdll!NtCreateKey` at `0x1800024ae`
- `ntdll!NtClose` at `0x180002208`
- `ntdll!NtClose` at `0x18000222f`
- `ntdll!NtClose` at `0x180002246`
- `ntdll!NtClose` at `0x180002335`
- `ntdll!NtClose` at `0x1800023ec`
- `ntdll!NtClose` at `0x1800024bf`
- `ntdll!NtClose` at `0x180002208`
- `ntdll!NtClose` at `0x18000222f`
- `ntdll!NtClose` at `0x180002246`
- `ntdll!NtClose` at `0x180002335`
- `ntdll!NtClose` at `0x1800023ec`
- `ntdll!NtClose` at `0x1800024bf`
- `ntdll!NtSetValueKey` at `0x1800021e8`
- `ntdll!NtSetValueKey` at `0x1800021e8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800021b8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800022b7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002372`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002452`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002502`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800021b8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800022b7`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002372`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002452`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002502`

## pseudocode

```c
__int64 __fastcall PnpSetPropertyWorker(__int64 a1, int a2, const WCHAR *a3, _DWORD *a4, int a5, void *a6, ULONG a7)
{
  PCWSTR v8; // rax
  int v11; // ebx
  int v12; // r8d
  HANDLE v13; // rsi
  __int64 *v14; // r14
  __int64 v15; // rax
  __int64 v16; // r12
  int inited; // edi
  int v18; // r8d
  HANDLE v19; // rsi
  __int64 v20; // rax
  __int64 v21; // r14
  int KeyTransacted_Stub; // edi
  HANDLE v23; // rdi
  NTSTATUS v24; // eax
  __int64 result; // rax
  int v26; // r9d
  int v27; // r9d
  __int64 v28; // rcx
  __int64 v29; // rcx
  int DataSize; // [rsp+28h] [rbp-E8h]
  unsigned __int8 DataSizea; // [rsp+28h] [rbp-E8h]
  HANDLE v32; // [rsp+90h] [rbp-80h] BYREF
  ULONG v33; // [rsp+98h] [rbp-78h] BYREF
  ULONG Disposition; // [rsp+9Ch] [rbp-74h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-70h] BYREF
  HANDLE KeyHandle; // [rsp+A8h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-50h] BYREF
  HANDLE v39; // [rsp+F0h] [rbp-20h] BYREF
  PCWSTR SourceString; // [rsp+F8h] [rbp-18h]
  PVOID Data; // [rsp+100h] [rbp-10h]
  wchar_t Buffer[12]; // [rsp+108h] [rbp-8h] BYREF
  WCHAR v43[40]; // [rsp+120h] [rbp+10h] BYREF

  v8 = a3;
  Data = a6;
  SourceString = a3;
  Disposition = 0;
  v33 = 0;
  v39 = 0;
  Handle = 0;
  KeyHandle = 0;
  if ( a7 > 0x7FFFFFFF )
    return 3221225485LL;
  if ( a3 )
  {
    result = RtlUnalignedStringCchLengthW(a3, 85, &v32);
    if ( (int)result < 0 )
      return result;
    v8 = SourceString;
  }
  if ( a5 == 25 && v8 && *v8 )
    return 3221225485LL;
  if ( (int)RtlStringCchPrintfExW(
              (int)v43,
              39,
              0,
              0,
              2048,
              (__int64)L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
              *a4) < 0 )
  {
    v11 = -1073741595;
    goto LABEL_23;
  }
  swprintf_s(Buffer, 9u, L"%04lX", (unsigned int)a4[4]);
  v11 = PnpOpenPropertiesKey(a1, a2, 0, 4, 1, DataSize, (__int64)&v39);
  if ( v11 < 0 )
  {
    v39 = 0;
    goto LABEL_23;
  }
  v13 = v39;
  if ( a1 && (v14 = (__int64 *)(a1 + 224), (v15 = *(_QWORD *)(a1 + 224)) != 0) )
  {
    v16 = *(_QWORD *)(v15 + 8);
    if ( *(_BYTE *)(v15 + 16) )
    {
      inited = RegRtlCreateProtectedKeyTransacted(
                 (__int64)v39,
                 v43,
                 v12,
                 4u,
                 0,
                 DataSizea,
                 &Handle,
                 &Disposition,
                 *(_QWORD *)(v15 + 8));
    }
    else
    {
      v32 = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      if ( (char *)v39 + 0x80000000 > (char *)7 || (inited = RegRtlOpenPredefinedKey(v39, &v32), inited >= 0) )
      {
        inited = RtlInitUnicodeStringEx(&DestinationString, v43);
        if ( inited >= 0 )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.Attributes = 192;
          if ( v32 )
            v13 = v32;
          ObjectAttributes.RootDirectory = v13;
          ObjectAttributes.ObjectName = &DestinationString;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( v16 )
          {
            DataSizea = 0;
            inited = NtCreateKeyTransacted_Stub((unsigned int)&Handle, 4, (unsigned int)&ObjectAttributes, v26);
            if ( inited == -1073741702 )
              inited = -1072103420;
          }
          else
          {
            inited = NtCreateKey(&Handle, 4u, &ObjectAttributes, 0, 0, 0, &Disposition);
          }
        }
      }
      if ( v32 )
        NtClose(v32);
    }
  }
  else
  {
    v32 = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    if ( !(unsigned __int8)RegRtlIsPredefinedKey(v39) || (inited = RegRtlOpenPredefinedKey(v28, &v32), inited >= 0) )
    {
      inited = RtlInitUnicodeStringEx(&DestinationString, v43);
      if ( inited >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 192;
        if ( v32 )
          v13 = v32;
        ObjectAttributes.RootDirectory = v13;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        inited = NtCreateKey(&Handle, 4u, &ObjectAttributes, 0, 0, 0, &Disposition);
      }
    }
    if ( v32 )
      NtClose(v32);
    v14 = (__int64 *)(a1 + 224);
  }
  if ( inited == -1073741444 )
  {
    v11 = -1073741595;
    goto LABEL_23;
  }
  if ( inited < 0 )
  {
    Handle = 0;
    v11 = inited;
LABEL_23:
    if ( KeyHandle )
    {
      NtClose(KeyHandle);
      if ( v11 < 0 && v33 == 1 )
        PnpCtxRegDeleteTree(a1, Handle, Buffer);
    }
    goto LABEL_25;
  }
  v19 = Handle;
  if ( a1 && (v20 = *v14) != 0 )
  {
    v21 = *(_QWORD *)(v20 + 8);
    if ( *(_BYTE *)(v20 + 16) )
    {
      KeyTransacted_Stub = RegRtlCreateProtectedKeyTransacted(
                             (__int64)Handle,
                             Buffer,
                             v18,
                             0x10006u,
                             0,
                             DataSizea,
                             &KeyHandle,
                             &v33,
                             *(_QWORD *)(v20 + 8));
      goto LABEL_16;
    }
    v32 = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    if ( (char *)Handle + 0x80000000 > (char *)7
      || (KeyTransacted_Stub = RegRtlOpenPredefinedKey(Handle, &v32), KeyTransacted_Stub >= 0) )
    {
      KeyTransacted_Stub = RtlInitUnicodeStringEx(&DestinationString, Buffer);
      if ( KeyTransacted_Stub >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 192;
        if ( v32 )
          v19 = v32;
        ObjectAttributes.RootDirectory = v19;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        if ( v21 )
        {
          KeyTransacted_Stub = NtCreateKeyTransacted_Stub(
                                 (unsigned int)&KeyHandle,
                                 65542,
                                 (unsigned int)&ObjectAttributes,
                                 v27);
          if ( KeyTransacted_Stub == -1073741702 )
            KeyTransacted_Stub = -1072103420;
          goto LABEL_46;
        }
        goto LABEL_45;
      }
    }
  }
  else
  {
    v32 = 0;
    memset(&ObjectAttributes, 0, 44);
    DestinationString = 0;
    if ( !(unsigned __int8)RegRtlIsPredefinedKey(Handle)
      || (KeyTransacted_Stub = RegRtlOpenPredefinedKey(v29, &v32), KeyTransacted_Stub >= 0) )
    {
      KeyTransacted_Stub = RtlInitUnicodeStringEx(&DestinationString, Buffer);
      if ( KeyTransacted_Stub >= 0 )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.Attributes = 192;
        if ( v32 )
          v19 = v32;
        ObjectAttributes.RootDirectory = v19;
        ObjectAttributes.ObjectName = &DestinationString;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
LABEL_45:
        KeyTransacted_Stub = NtCreateKey(&KeyHandle, 0x10006u, &ObjectAttributes, 0, 0, 0, &v33);
      }
    }
  }
LABEL_46:
  if ( v32 )
    NtClose(v32);
LABEL_16:
  if ( KeyTransacted_Stub == -1073741444 )
  {
    v11 = -1073741595;
    goto LABEL_23;
  }
  if ( KeyTransacted_Stub >= 0 )
  {
    v23 = KeyHandle;
    DestinationString = 0;
    v24 = RtlInitUnicodeStringEx(&DestinationString, SourceString);
    if ( v24 >= 0 )
      v24 = NtSetValueKey(v23, &DestinationString, 0, a5 | 0xFFFF0000, Data, a7);
    if ( v24 == -1073741444 )
    {
      v11 = -1073741595;
    }
    else if ( v24 < 0 )
    {
      v11 = v24;
    }
    goto LABEL_23;
  }
  KeyHandle = 0;
  v11 = KeyTransacted_Stub;
LABEL_25:
  if ( Handle )
  {
    NtClose(Handle);
    if ( v11 < 0 && Disposition == 1 )
      PnpCtxRegDeleteTree(a1, v39, v43);
  }
  if ( v39 )
    NtClose(v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180001f50  push    rbp
0x180001f52  push    r12
0x180001f54  push    r13
0x180001f56  push    r14
0x180001f58  push    r15
0x180001f5a  lea     rbp, [rsp-90h]
0x180001f62  sub     rsp, 1A0h
0x180001f69  mov     rax, cs:__security_cookie
0x180001f70  xor     rax, rsp
0x180001f73  mov     [rbp+0B0h+var_50], rax
0x180001f77  mov     r15d, [rbp+0B0h+arg_30]
0x180001f7e  mov     r13, rcx
0x180001f81  mov     rcx, [rbp+0B0h+arg_28]
0x180001f88  mov     rax, r8
0x180001f8b  mov     [rbp+0B0h+var_C0], rcx
0x180001f8f  mov     r14, r9
0x180001f92  xor     ecx, ecx
0x180001f94  mov     [rbp+0B0h+SourceString], rax
0x180001f98  mov     [rbp+0B0h+var_124], ecx
0x180001f9b  mov     r12, rdx
0x180001f9e  mov     [rbp+0B0h+var_128], ecx
0x180001fa1  mov     [rbp+0B0h+var_D0], rcx
0x180001fa5  mov     [rbp+0B0h+Handle], rcx
0x180001fa9  mov     [rbp+0B0h+KeyHandle], rcx
0x180001fad  cmp     r15d, 7FFFFFFFh
0x180001fb4  ja      loc_180002409
0x180001fba  test    rax, rax
0x180001fbd  jnz     loc_180002555
0x180001fc3  cmp     [rbp+0B0h+arg_20], 19h
0x180001fca  jz      loc_1800023F7
0x180001fd0  movzx   eax, byte ptr [r9+0Fh]
0x180001fd5  movzx   ecx, byte ptr [r9+0Eh]
0x180001fda  movzx   edx, byte ptr [r9+0Dh]
0x180001fdf  movzx   r8d, byte ptr [r9+0Ch]
0x180001fe4  movzx   r9d, byte ptr [r9+0Bh]
0x180001fe9  movzx   r10d, byte ptr [r14+0Ah]
0x180001fee  movzx   r11d, byte ptr [r14+9]
0x180001ff3  mov     [rsp+1C0h+var_140], eax
0x180001ffa  mov     eax, [r14]
0x180001ffd  mov     [rsp+1C0h+var_148], ecx
0x180002001  lea     rcx, [rbp+0B0h+var_A0]; int
0x180002005  mov     [rsp+1C0h+var_150], edx
0x180002009  mov     edx, 27h ; '''; int
0x18000200e  mov     [rsp+1C0h+var_158], r8d
0x180002013  xor     r8d, r8d; int
0x180002016  mov     [rsp+1C0h+var_160], r9d
0x18000201b  xor     r9d, r9d; int
0x18000201e  mov     [rsp+1C0h+var_168], r10d
0x180002023  mov     [rsp+1C0h+var_170], r11d
0x180002028  mov     [rsp+1C0h+var_28], rbx
0x180002030  movzx   ebx, byte ptr [r14+8]
0x180002035  mov     [rsp+1C0h+var_178], ebx
0x180002039  mov     [rsp+1C0h+var_30], rsi
0x180002041  movzx   esi, word ptr [r14+4]
0x180002046  mov     [rsp+1C0h+var_38], rdi
0x18000204e  movzx   edi, word ptr [r14+6]
0x180002053  mov     dword ptr [rsp+1C0h+var_180], edi
0x180002057  mov     dword ptr [rsp+1C0h+var_188], esi
0x18000205b  mov     dword ptr [rsp+1C0h+Disposition], eax; Args
0x18000205f  lea     rax, a08lx04x04x02x0_0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180002066  mov     qword ptr [rsp+1C0h+DataSize], rax; __int64
0x18000206b  mov     dword ptr [rsp+1C0h+Data], 800h; int
0x180002073  call    RtlStringCchPrintfExW
0x180002078  test    eax, eax
0x18000207a  js      loc_180002579
0x180002080  mov     r9d, [r14+10h]
0x180002084  lea     r8, a04lx; "%04lX"
0x18000208b  mov     edx, 9; BufferCount
0x180002090  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x180002094  call    swprintf_s
0x180002099  lea     rax, [rbp+0B0h+var_D0]
0x18000209d  mov     r9d, 4
0x1800020a3  mov     [rsp+1C0h+Disposition], rax
0x1800020a8  xor     r8d, r8d
0x1800020ab  mov     rdx, r12
0x1800020ae  mov     byte ptr [rsp+1C0h+Data], 1
0x1800020b3  mov     rcx, r13
0x1800020b6  call    _PnpOpenPropertiesKey
0x1800020bb  mov     ebx, eax
0x1800020bd  test    eax, eax
0x1800020bf  js      loc_180002583
0x1800020c5  mov     rsi, [rbp+0B0h+var_D0]
0x1800020c9  test    r13, r13
0x1800020cc  jz      loc_18000241E
0x1800020d2  lea     r14, [r13+0E0h]
0x1800020d9  mov     rax, [r14]
0x1800020dc  test    rax, rax
0x1800020df  jz      loc_18000241E
0x1800020e5  cmp     byte ptr [rax+10h], 0
0x1800020e9  mov     r12, [rax+8]
0x1800020ed  jz      loc_180002273
0x1800020f3  mov     [rsp+1C0h+var_180], r12
0x1800020f8  lea     rax, [rbp+0B0h+var_124]
0x1800020fc  mov     [rsp+1C0h+var_188], rax
0x180002101  lea     rdx, [rbp+0B0h+var_A0]
0x180002105  lea     rax, [rbp+0B0h+Handle]
0x180002109  xor     r12d, r12d
0x18000210c  mov     [rsp+1C0h+Disposition], rax
0x180002111  mov     r9d, 4
0x180002117  mov     rcx, rsi
0x18000211a  mov     [rsp+1C0h+Data], r12
0x18000211f  call    _RegRtlCreateProtectedKeyTransacted
0x180002124  mov     edi, eax
0x180002126  cmp     edi, 0C000017Ch
0x18000212c  jz      loc_1800025DE
0x180002132  test    edi, edi
0x180002134  js      loc_180002413
0x18000213a  mov     rsi, [rbp+0B0h+Handle]
0x18000213e  test    r13, r13
0x180002141  jz      loc_1800024D1
0x180002147  mov     rax, [r14]
0x18000214a  test    rax, rax
0x18000214d  jz      loc_1800024D1
0x180002153  cmp     byte ptr [rax+10h], 0
0x180002157  mov     r14, [rax+8]
0x18000215b  jz      loc_180002340
0x180002161  mov     [rsp+1C0h+var_180], r14
0x180002166  lea     rax, [rbp+0B0h+var_128]
0x18000216a  mov     [rsp+1C0h+var_188], rax
0x18000216f  lea     rdx, [rbp+0B0h+Buffer]
0x180002173  lea     rax, [rbp+0B0h+KeyHandle]
0x180002177  mov     r9d, 10006h
0x18000217d  mov     [rsp+1C0h+Disposition], rax
0x180002182  mov     rcx, rsi
0x180002185  mov     [rsp+1C0h+Data], r12
0x18000218a  call    _RegRtlCreateProtectedKeyTransacted
0x18000218f  mov     edi, eax
0x180002191  cmp     edi, 0C000017Ch
0x180002197  jz      loc_180002646
0x18000219d  test    edi, edi
0x18000219f  js      loc_180002650
0x1800021a5  mov     rdx, [rbp+0B0h+SourceString]; SourceString
0x1800021a9  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x1800021ad  mov     rdi, [rbp+0B0h+KeyHandle]
0x1800021b1  xorps   xmm0, xmm0
0x1800021b4  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x1800021b8  call    cs:__imp_RtlInitUnicodeStringEx
0x1800021be  test    eax, eax
0x1800021c0  js      short loc_1800021EE
0x1800021c2  mov     rcx, [rbp+0B0h+var_C0]
0x1800021c6  lea     rdx, [rbp+0B0h+DestinationString]; ValueName
0x1800021ca  mov     r9d, [rbp+0B0h+arg_20]
0x1800021d1  xor     r8d, r8d; TitleIndex
0x1800021d4  mov     [rsp+1C0h+DataSize], r15d; DataSize
0x1800021d9  or      r9d, 0FFFF0000h; Type
0x1800021e0  mov     [rsp+1C0h+Data], rcx; Data
0x1800021e5  mov     rcx, rdi; KeyHandle
0x1800021e8  call    cs:__imp_NtSetValueKey
0x1800021ee  cmp     eax, 0C000017Ch
0x1800021f3  jz      loc_18000265B
0x1800021f9  test    eax, eax
0x1800021fb  jns     short loc_1800021FF
0x1800021fd  mov     ebx, eax
0x1800021ff  mov     rcx, [rbp+0B0h+KeyHandle]; Handle
0x180002203  test    rcx, rcx
0x180002206  jz      short loc_180002216
0x180002208  call    cs:__imp_NtClose
0x18000220e  test    ebx, ebx
0x180002210  js      loc_180002665
0x180002216  mov     rcx, [rbp+0B0h+Handle]; Handle
0x18000221a  mov     rdi, [rsp+1C0h+var_38]
0x180002222  mov     rsi, [rsp+1C0h+var_30]
0x18000222a  test    rcx, rcx
0x18000222d  jz      short loc_18000223D
0x18000222f  call    cs:__imp_NtClose
0x180002235  test    ebx, ebx
0x180002237  js      loc_180002684
0x18000223d  mov     rcx, [rbp+0B0h+var_D0]; Handle
0x180002241  test    rcx, rcx
0x180002244  jz      short loc_18000224C
0x180002246  call    cs:__imp_NtClose
0x18000224c  mov     eax, ebx
0x18000224e  mov     rbx, [rsp+1C0h+var_28]
0x180002256  mov     rcx, [rbp+0B0h+var_50]
0x18000225a  xor     rcx, rsp; StackCookie
0x18000225d  call    __security_check_cookie
0x180002262  add     rsp, 1A0h
0x180002269  pop     r15
0x18000226b  pop     r14
0x18000226d  pop     r13
0x18000226f  pop     r12
0x180002271  pop     rbp
0x180002272  retn
0x180002273  xorps   xmm0, xmm0
0x180002276  xor     eax, eax
0x180002278  mov     [rbp+0B0h+var_130], rax
0x18000227c  lea     rax, [rsi-80000000h]
0x180002283  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x180002287  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x18000228b  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x18000228f  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180002293  cmp     rax, 7
0x180002297  ja      short loc_1800022AF
0x180002299  lea     rdx, [rbp+0B0h+var_130]
0x18000229d  mov     rcx, rsi
0x1800022a0  call    _RegRtlOpenPredefinedKey
0x1800022a5  mov     edi, eax
0x1800022a7  test    eax, eax
0x1800022a9  js      loc_1800025BE
0x1800022af  lea     rdx, [rbp+0B0h+var_A0]; SourceString
0x1800022b3  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x1800022b7  call    cs:__imp_RtlInitUnicodeStringEx
0x1800022bd  mov     edi, eax
0x1800022bf  test    eax, eax
0x1800022c1  js      loc_1800025BE
0x1800022c7  mov     rax, [rbp+0B0h+var_130]
0x1800022cb  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1800022cf  test    rax, rax
0x1800022d2  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x1800022d9  xorps   xmm0, xmm0
0x1800022dc  mov     [rbp+0B0h+ObjectAttributes.Attributes], 0C0h
0x1800022e3  cmovnz  rsi, rax
0x1800022e7  lea     rcx, [rbp+0B0h+Handle]; KeyHandle
0x1800022eb  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rsi
0x1800022ef  lea     rax, [rbp+0B0h+DestinationString]
0x1800022f3  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x1800022f7  lea     rax, [rbp+0B0h+var_124]
0x1800022fb  mov     edx, 4; DesiredAccess
0x180002300  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002305  test    r12, r12
0x180002308  jnz     loc_180002590
0x18000230e  mov     [rsp+1C0h+Disposition], rax; Disposition
0x180002313  xor     r9d, r9d; TitleIndex
0x180002316  mov     [rsp+1C0h+DataSize], r12d; CreateOptions
0x18000231b  mov     [rsp+1C0h+Data], r12; Class
0x180002320  call    cs:__imp_NtCreateKey
0x180002326  mov     edi, eax
0x180002328  mov     rcx, [rbp+0B0h+var_130]; Handle
0x18000232c  test    rcx, rcx
0x18000232f  jz      loc_180002126
0x180002335  call    cs:__imp_NtClose
0x18000233b  jmp     loc_180002126
0x180002340  xorps   xmm0, xmm0
0x180002343  mov     [rbp+0B0h+var_130], r12
0x180002347  xor     eax, eax
0x180002349  lea     rax, [rsi-80000000h]
0x180002350  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x180002354  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x180002358  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x18000235c  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180002360  cmp     rax, 7
0x180002364  jbe     loc_1800025E8
0x18000236a  lea     rdx, [rbp+0B0h+Buffer]; SourceString
0x18000236e  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180002372  call    cs:__imp_RtlInitUnicodeStringEx
0x180002378  mov     edi, eax
0x18000237a  test    eax, eax
0x18000237c  js      short loc_1800023DF
0x18000237e  mov     rax, [rbp+0B0h+var_130]
0x180002382  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x180002386  test    rax, rax
0x180002389  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x180002390  xorps   xmm0, xmm0
0x180002393  mov     [rbp+0B0h+ObjectAttributes.Attributes], 0C0h
0x18000239a  cmovnz  rsi, rax
0x18000239e  lea     rcx, [rbp+0B0h+KeyHandle]; KeyHandle
0x1800023a2  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rsi
0x1800023a6  lea     rax, [rbp+0B0h+DestinationString]
0x1800023aa  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x1800023ae  lea     rax, [rbp+0B0h+var_128]
0x1800023b2  mov     edx, 10006h; DesiredAccess
0x1800023b7  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800023bc  test    r14, r14
0x1800023bf  jnz     loc_180002603
0x1800023c5  mov     [rsp+1C0h+Disposition], rax; Disposition
0x1800023ca  xor     r9d, r9d; TitleIndex
0x1800023cd  mov     [rsp+1C0h+DataSize], r12d; CreateOptions
0x1800023d2  mov     [rsp+1C0h+Data], r12; Class
0x1800023d7  call    cs:__imp_NtCreateKey
0x1800023dd  mov     edi, eax
0x1800023df  mov     rcx, [rbp+0B0h+var_130]; Handle
0x1800023e3  test    rcx, rcx
0x1800023e6  jz      loc_180002191
0x1800023ec  call    cs:__imp_NtClose
0x1800023f2  jmp     loc_180002191
0x1800023f7  test    rax, rax
0x1800023fa  jz      loc_180001FD0
0x180002400  cmp     [rax], cx
0x180002403  jz      loc_180001FD0
0x180002409  mov     eax, 0C000000Dh
0x18000240e  jmp     loc_180002256
0x180002413  mov     [rbp+0B0h+Handle], r12
0x180002417  mov     ebx, edi
0x180002419  jmp     loc_1800021FF
0x18000241e  xorps   xmm0, xmm0
0x180002421  xor     r12d, r12d
0x180002424  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x180002428  xor     eax, eax
0x18000242a  mov     [rbp+0B0h+var_130], r12
0x18000242e  mov     rcx, rsi
0x180002431  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x180002435  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x180002439  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x18000243d  call    _RegRtlIsPredefinedKey
0x180002442  test    al, al
0x180002444  jnz     loc_1800025C6
0x18000244a  lea     rdx, [rbp+0B0h+var_A0]; SourceString
0x18000244e  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180002452  call    cs:__imp_RtlInitUnicodeStringEx
0x180002458  mov     edi, eax
  ... truncated ...
```
