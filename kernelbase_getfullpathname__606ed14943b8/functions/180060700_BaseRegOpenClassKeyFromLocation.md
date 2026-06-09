# BaseRegOpenClassKeyFromLocation

- ea: `0x180060700`
- end: `0x180060d9f`
- name: `BaseRegOpenClassKeyFromLocation`
- size: `1695`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002c150`
- `0x18005cc70`
- `0x18005ebc0`
- `0x180061220`
- `0x180061370`
- `0x180061910`
- `0x180061d14`
- `0x180063f98`
- `0x1800a4bd0`

## callees

- `0x18005f8a0`
- `0x18005fa00`
- `0x180060700`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800608d4`
- `ntdll!RtlFreeUnicodeString` at `0x1800608d4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18006090b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180060ac2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18006090b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180060ac2`
- `ntdll!RtlAppendUnicodeToString` at `0x1800608ec`
- `ntdll!RtlAppendUnicodeToString` at `0x1800608ec`
- `ntdll!RtlCopyUnicodeString` at `0x1800608c3`
- `ntdll!RtlCopyUnicodeString` at `0x180060aac`
- `ntdll!RtlCopyUnicodeString` at `0x1800608c3`
- `ntdll!RtlCopyUnicodeString` at `0x180060aac`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060a5e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180060a5e`
- `ntdll!NtClose` at `0x180060cd5`
- `ntdll!NtClose` at `0x180060d2b`
- `ntdll!NtClose` at `0x180060cd5`
- `ntdll!NtClose` at `0x180060d2b`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800608a3`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800608a3`
- `ntdll!NtQueryKey` at `0x18006080f`
- `ntdll!NtQueryKey` at `0x18006080f`
- `ntdll!RtlFreeHeap` at `0x180060a00`
- `ntdll!RtlFreeHeap` at `0x180060bb2`
- `ntdll!RtlFreeHeap` at `0x180060bff`
- `ntdll!RtlFreeHeap` at `0x180060a00`
- `ntdll!RtlFreeHeap` at `0x180060bb2`
- `ntdll!RtlFreeHeap` at `0x180060bff`
- `ntdll!RtlAllocateHeap` at `0x180060788`
- `ntdll!RtlAllocateHeap` at `0x180060788`
- `ntdll!NtOpenKeyEx` at `0x1800609d6`
- `ntdll!NtOpenKeyEx` at `0x180060b8b`
- `ntdll!NtOpenKeyEx` at `0x1800609d6`
- `ntdll!NtOpenKeyEx` at `0x180060b8b`
- `ntdll!NtSetInformationKey` at `0x180060cba`
- `ntdll!NtSetInformationKey` at `0x180060d10`
- `ntdll!NtSetInformationKey` at `0x180060cba`
- `ntdll!NtSetInformationKey` at `0x180060d10`

## string_xrefs

- `0x180060a47`: `\Registry\Machine\Software\Classes`

## pseudocode

```c
__int64 __fastcall BaseRegOpenClassKeyFromLocation(
        __int64 a1,
        void *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        HANDLE *a7,
        void *a8)
{
  _WORD *v9; // rax
  void *v11; // r10
  USHORT v12; // di
  WCHAR *Heap; // r15
  int v15; // edi
  unsigned int v16; // r14d
  int appended; // ebx
  char v18; // al
  unsigned int v19; // r14d
  __int16 v20; // di
  __int64 v21; // rdx
  _WORD *v22; // r8
  __int16 v23; // cx
  __int64 v24; // r9
  struct _UNICODE_STRING *p_DestinationString; // rax
  __int64 v26; // rcx
  _WORD *v27; // rdx
  __int64 v28; // r8
  struct _UNICODE_STRING *v29; // rax
  int v30; // edi
  _BYTE v31[4]; // [rsp+30h] [rbp-D0h] BYREF
  int KeyInformation; // [rsp+34h] [rbp-CCh] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  __int128 v38; // [rsp+78h] [rbp-88h] BYREF
  __int128 v39; // [rsp+88h] [rbp-78h]
  __int128 v40; // [rsp+98h] [rbp-68h]
  void *v41; // [rsp+A8h] [rbp-58h]
  UNICODE_STRING Source; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-20h]
  __int128 v46; // [rsp+F0h] [rbp-10h]
  _BYTE v47[528]; // [rsp+100h] [rbp+0h] BYREF

  P = a8;
  *(_QWORD *)&SourceString.Length = a3;
  v9 = *(_WORD **)(a1 + 16);
  DestinationString = 0;
  v11 = a2;
  v41 = a2;
  DWORD1(v38) = 0;
  v12 = *v9 + 362;
  HIDWORD(v39) = 0;
  if ( v12 <= 0x208u )
  {
    Heap = (WCHAR *)v47;
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    if ( !Heap )
      return 3221225495LL;
    v11 = v41;
  }
  DestinationString.MaximumLength = v12;
  v15 = a4 & 0x300;
  v16 = a4 & 0xFFFFFCFF;
  appended = -1073741772;
  DestinationString.Buffer = Heap;
  if ( g_Win64Registry )
  {
    if ( !v15 )
    {
      KeyInformation = 0;
      ResultLength = 0;
      if ( NtQueryKey(v11, KeyHandleTagsInformation, &KeyInformation, 4u, &ResultLength) >= 0 )
        v15 = KeyInformation & 0x300;
    }
  }
  v18 = a5;
  v19 = v15 | v16;
  v20 = 1;
  if ( (a5 & 2) != 0 )
  {
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      *((_QWORD *)&v38 + 1) = v41;
      DWORD2(v39) = 32 * (a6 & 8 | 2);
      p_DestinationString = *(struct _UNICODE_STRING **)&SourceString.Length;
    }
    else
    {
      v21 = *(unsigned __int16 *)(a1 + 4);
      v22 = *(_WORD **)(a1 + 16);
      Source = 0;
      if ( v22[v21 + 2] )
      {
        v23 = 1;
        v24 = 1;
      }
      else
      {
        v23 = 0;
        v24 = 0;
      }
      *(_OWORD *)KeyHandle = 0;
      KeyPath = 0;
      Source.Buffer = &v22[v21 - v24 + 2];
      Source.Length = *v22 + 2 * (v23 - v21);
      appended = RtlFormatCurrentUserKeyPath(&KeyPath);
      if ( appended < 0 )
        goto LABEL_41;
      RtlCopyUnicodeString(&DestinationString, &KeyPath);
      RtlFreeUnicodeString(&KeyPath);
      appended = RtlAppendUnicodeToString(&DestinationString, L"_Classes");
      if ( appended < 0 )
        goto LABEL_41;
      appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
      if ( appended < 0 )
        goto LABEL_41;
      *((_QWORD *)&v38 + 1) = 0;
      DWORD2(v39) = 32 * (a6 & 8 | 2);
      p_DestinationString = &DestinationString;
    }
    *(_QWORD *)&v39 = p_DestinationString;
    LODWORD(v38) = 48;
    v40 = 0;
    if ( P )
    {
      appended = Wow64NtOpenKey((_DWORD)a7, v19, (unsigned int)&v38, a6 & 0x1C, (__int64)P);
      goto LABEL_24;
    }
    *(_QWORD *)&Source.Length = 0;
    KeyInformation = 0;
    *(_QWORD *)&KeyPath.Length = 0;
    LOWORD(KeyPath.Buffer) = 0;
    BYTE2(KeyPath.Buffer) = 0;
    KeyHandle[0] = 0;
    v31[0] = 0;
    v44 = v38;
    v45 = v39;
    v46 = 0;
    appended = ConstructKernelKeyPath(
                 v19,
                 (unsigned int)&v44,
                 (unsigned int)&KeyInformation,
                 (unsigned int)&KeyPath,
                 (__int64)v31,
                 (__int64)&Source);
    if ( appended < 0 )
      goto LABEL_24;
    appended = NtOpenKeyEx(KeyHandle, v19, &v44, a6 & 0x1C);
    ResultLength = appended;
    if ( *(_QWORD *)&Source.Length )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&Source.Length);
    if ( appended < 0 )
      goto LABEL_24;
    if ( v31[0] && KeyInformation )
    {
      KeyInformation &= 0xF01u;
      appended = NtSetInformationKey(KeyHandle[0], KeySetHandleTagsInformation, &KeyInformation, 4u);
      if ( appended < 0 )
      {
        NtClose(KeyHandle[0]);
        goto LABEL_24;
      }
      appended = ResultLength;
    }
    *a7 = KeyHandle[0];
LABEL_24:
    v18 = a5;
  }
  if ( (v18 & 1) == 0 )
  {
    if ( appended < 0 )
      goto LABEL_41;
LABEL_45:
    *a7 = (HANDLE)((unsigned __int64)*a7 | 2);
    goto LABEL_41;
  }
  if ( appended >= 0 )
    goto LABEL_45;
  if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    *((_QWORD *)&v38 + 1) = v41;
    DWORD2(v39) = 32 * (a6 & 8 | 2);
    v29 = *(struct _UNICODE_STRING **)&SourceString.Length;
  }
  else
  {
    SourceString = 0;
    KeyPath = 0;
    RtlInitUnicodeStringEx(&SourceString, L"\\Registry\\Machine\\Software\\Classes");
    v26 = *(unsigned __int16 *)(a1 + 4);
    v27 = *(_WORD **)(a1 + 16);
    if ( v27[v26 + 2] )
    {
      v28 = 1;
    }
    else
    {
      v20 = 0;
      v28 = 0;
    }
    KeyPath.Buffer = &v27[v26 - v28 + 2];
    KeyPath.Length = *v27 + 2 * (v20 - v26);
    RtlCopyUnicodeString(&DestinationString, &SourceString);
    appended = RtlAppendUnicodeStringToString(&DestinationString, &KeyPath);
    if ( appended < 0 )
      goto LABEL_41;
    *((_QWORD *)&v38 + 1) = 0;
    DWORD2(v39) = 32 * (a6 & 8 | 2);
    v29 = &DestinationString;
  }
  *(_QWORD *)&v39 = v29;
  LODWORD(v38) = 48;
  v40 = 0;
  if ( !P )
  {
    *(_QWORD *)&KeyPath.Length = 0;
    LOWORD(KeyPath.Buffer) = 0;
    BYTE2(KeyPath.Buffer) = 0;
    v31[0] = 0;
    P = 0;
    v44 = v38;
    KeyInformation = 0;
    v45 = v39;
    KeyHandle[0] = 0;
    v46 = 0;
    appended = ConstructKernelKeyPath(
                 v19,
                 (unsigned int)&v44,
                 (unsigned int)&KeyInformation,
                 (unsigned int)&KeyPath,
                 (__int64)v31,
                 (__int64)&P);
    if ( appended < 0 )
      goto LABEL_40;
    v30 = NtOpenKeyEx(KeyHandle, v19, &v44, a6 & 0x1C);
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( v30 >= 0 )
    {
      if ( v31[0] )
      {
        if ( KeyInformation )
        {
          KeyInformation &= 0xF01u;
          appended = NtSetInformationKey(KeyHandle[0], KeySetHandleTagsInformation, &KeyInformation, 4u);
          if ( appended < 0 )
          {
            NtClose(KeyHandle[0]);
            goto LABEL_40;
          }
        }
      }
      *a7 = KeyHandle[0];
    }
    appended = v30;
    goto LABEL_40;
  }
  appended = Wow64NtOpenKey((_DWORD)a7, v19, (unsigned int)&v38, a6 & 0x1C, (__int64)P);
LABEL_40:
  if ( appended >= 0 )
    goto LABEL_45;
LABEL_41:
  if ( Heap != (WCHAR *)v47 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180060700  push    rbp
0x180060702  push    rsi
0x180060703  push    rdi
0x180060704  push    r12
0x180060706  push    r14
0x180060708  push    r15
0x18006070a  lea     rbp, [rsp-238h]
0x180060712  sub     rsp, 338h
0x180060719  mov     rax, cs:__security_cookie
0x180060720  xor     rax, rsp
0x180060723  mov     [rbp+260h+var_50], rax
0x18006072a  mov     rax, [rbp+260h+arg_38]
0x180060731  mov     rsi, rcx
0x180060734  mov     r12, [rbp+260h+arg_30]
0x18006073b  xor     ecx, ecx
0x18006073d  mov     [rsp+360h+P], rax
0x180060742  xorps   xmm0, xmm0
0x180060745  mov     edi, 16Ah
0x18006074a  mov     qword ptr [rbp+260h+SourceString.Length], r8
0x18006074e  mov     rax, [rsi+10h]
0x180060752  mov     r14d, r9d
0x180060755  movups  xmmword ptr [rsp+360h+DestinationString.Length], xmm0
0x18006075a  mov     r10, rdx
0x18006075d  mov     [rbp+260h+var_2B8], rdx
0x180060761  mov     dword ptr [rsp+360h+var_2E8+4], ecx
0x180060765  add     di, [rax]
0x180060768  mov     eax, 208h
0x18006076d  mov     dword ptr [rbp+260h+var_2D8+0Ch], ecx
0x180060770  cmp     di, ax
0x180060773  jbe     short loc_1800607AA
0x180060775  mov     rcx, gs:60h
0x18006077e  xor     edx, edx; Flags
0x180060780  movzx   r8d, di; Size
0x180060784  mov     rcx, [rcx+30h]; HeapHandle
0x180060788  call    cs:__imp_RtlAllocateHeap
0x18006078f  nop     dword ptr [rax+rax+00h]
0x180060794  mov     r15, rax
0x180060797  test    rax, rax
0x18006079a  jnz     loc_180060C41
0x1800607a0  mov     eax, 0C0000017h
0x1800607a5  jmp     loc_180060C15
0x1800607aa  lea     r15, [rbp+260h+var_260]
0x1800607ae  mov     [rsp+360h+DestinationString.MaximumLength], di
0x1800607b3  mov     edi, r14d
0x1800607b6  mov     [rsp+360h+var_30], rbx
0x1800607be  and     edi, 300h
0x1800607c4  and     r14d, 0FFFFFCFFh
0x1800607cb  mov     [rsp+360h+var_38], r13
0x1800607d3  cmp     cs:g_Win64Registry, 0
0x1800607da  mov     ebx, 0C0000034h
0x1800607df  mov     [rsp+360h+DestinationString.Buffer], r15
0x1800607e4  jz      short loc_180060829
0x1800607e6  test    edi, edi
0x1800607e8  jnz     short loc_180060829
0x1800607ea  mov     [rsp+360h+KeyInformation], ecx
0x1800607ee  lea     rax, [rsp+360h+var_318]
0x1800607f3  mov     [rsp+360h+var_318], ecx
0x1800607f7  lea     r8, [rsp+360h+KeyInformation]; KeyInformation
0x1800607fc  mov     rcx, r10; KeyHandle
0x1800607ff  mov     [rsp+360h+ResultLength], rax; ResultLength
0x180060804  mov     r9d, 4; Length
0x18006080a  mov     edx, 7; KeyInformationClass
0x18006080f  call    cs:__imp_NtQueryKey
0x180060816  nop     dword ptr [rax+rax+00h]
0x18006081b  test    eax, eax
0x18006081d  js      short loc_180060829
0x18006081f  mov     edi, [rsp+360h+KeyInformation]
0x180060823  and     edi, 300h
0x180060829  mov     eax, dword ptr [rbp+260h+arg_20]
0x18006082f  or      r14d, edi
0x180060832  mov     r13d, dword ptr [rbp+260h+arg_28]
0x180060839  mov     edi, 1
0x18006083e  test    al, 2
0x180060840  jz      loc_180060A2A
0x180060846  test    [rsi], dil
0x180060849  jnz     loc_180060C4C
0x18006084f  movzx   edx, word ptr [rsi+4]
0x180060853  xorps   xmm0, xmm0
0x180060856  mov     r8, [rsi+10h]
0x18006085a  movups  xmmword ptr [rbp+260h+Source.Length], xmm0
0x18006085e  cmp     word ptr [r8+rdx*2+4], 0
0x180060865  jz      loc_180060D82
0x18006086b  movzx   ecx, di
0x18006086e  mov     r9d, edi
0x180060871  sub     cx, dx
0x180060874  mov     rax, rdx
0x180060877  sub     rax, r9
0x18006087a  add     cx, cx
0x18006087d  add     rax, 2
0x180060881  xorps   xmm1, xmm1
0x180060884  movups  xmmword ptr [rsp+360h+KeyHandle], xmm0
0x180060889  movups  xmmword ptr [rsp+360h+KeyPath.Length], xmm1
0x18006088e  lea     rax, [r8+rax*2]
0x180060892  mov     [rbp+260h+Source.Buffer], rax
0x180060896  add     cx, [r8]
0x18006089a  mov     [rbp+260h+Source.Length], cx
0x18006089e  lea     rcx, [rsp+360h+KeyPath]; KeyPath
0x1800608a3  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800608aa  nop     dword ptr [rax+rax+00h]
0x1800608af  mov     ebx, eax
0x1800608b1  test    eax, eax
0x1800608b3  js      loc_180060BDC
0x1800608b9  lea     rdx, [rsp+360h+KeyPath]; SourceString
0x1800608be  lea     rcx, [rsp+360h+DestinationString]; DestinationString
0x1800608c3  call    cs:__imp_RtlCopyUnicodeString
0x1800608ca  nop     dword ptr [rax+rax+00h]
0x1800608cf  lea     rcx, [rsp+360h+KeyPath]; UnicodeString
0x1800608d4  call    cs:__imp_RtlFreeUnicodeString
0x1800608db  nop     dword ptr [rax+rax+00h]
0x1800608e0  lea     rdx, aClasses_0; "_Classes"
0x1800608e7  lea     rcx, [rsp+360h+DestinationString]; Destination
0x1800608ec  call    cs:__imp_RtlAppendUnicodeToString
0x1800608f3  nop     dword ptr [rax+rax+00h]
0x1800608f8  mov     ebx, eax
0x1800608fa  test    eax, eax
0x1800608fc  js      loc_180060BDC
0x180060902  lea     rdx, [rbp+260h+Source]; Source
0x180060906  lea     rcx, [rsp+360h+DestinationString]; Destination
0x18006090b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180060912  nop     dword ptr [rax+rax+00h]
0x180060917  mov     ebx, eax
0x180060919  test    eax, eax
0x18006091b  js      loc_180060BDC
0x180060921  movzx   eax, r13b
0x180060925  and     eax, 8
0x180060928  mov     qword ptr [rbp+260h+var_2E8+8], 0
0x180060930  or      eax, 2
0x180060933  shl     eax, 5
0x180060936  mov     dword ptr [rbp+260h+var_2D8+8], eax
0x180060939  lea     rax, [rsp+360h+DestinationString]
0x18006093e  mov     qword ptr [rbp+260h+var_2D8], rax
0x180060942  xorps   xmm2, xmm2
0x180060945  mov     rax, [rsp+360h+P]
0x18006094a  mov     dword ptr [rsp+360h+var_2E8], 30h ; '0'
0x180060952  movdqu  [rbp+260h+var_2C8], xmm2
0x180060957  test    rax, rax
0x18006095a  jnz     loc_180060D5F
0x180060960  movups  xmm0, [rsp+360h+var_2E8]
0x180060965  mov     qword ptr [rbp+260h+Source.Length], rax
0x180060969  lea     r9, [rsp+360h+KeyPath]
0x18006096e  movups  xmm1, [rbp+260h+var_2D8]
0x180060972  mov     [rsp+360h+KeyInformation], eax
0x180060976  lea     r8, [rsp+360h+KeyInformation]
0x18006097b  mov     qword ptr [rsp+360h+KeyPath.Length], rax
0x180060980  lea     rdx, [rbp+260h+var_290]
0x180060984  mov     word ptr [rsp+360h+KeyPath.Buffer], ax
0x180060989  mov     ecx, r14d
0x18006098c  mov     byte ptr [rsp+360h+KeyPath.Buffer+2], al
0x180060990  mov     [rsp+360h+KeyHandle], rax
0x180060995  mov     [rsp+360h+var_330], al
0x180060999  lea     rax, [rbp+260h+Source]
0x18006099d  mov     [rsp+360h+var_338], rax
0x1800609a2  lea     rax, [rsp+360h+var_330]
0x1800609a7  mov     [rsp+360h+ResultLength], rax
0x1800609ac  movups  [rbp+260h+var_290], xmm0
0x1800609b0  movups  [rbp+260h+var_280], xmm1
0x1800609b4  movups  [rbp+260h+var_270], xmm2
0x1800609b8  call    ConstructKernelKeyPath
0x1800609bd  mov     ebx, eax
0x1800609bf  test    eax, eax
0x1800609c1  js      short loc_180060A24
0x1800609c3  mov     r9d, r13d
0x1800609c6  lea     r8, [rbp+260h+var_290]
0x1800609ca  and     r9d, 1Ch
0x1800609ce  lea     rcx, [rsp+360h+KeyHandle]
0x1800609d3  mov     edx, r14d
0x1800609d6  call    cs:__imp_NtOpenKeyEx
0x1800609dd  nop     dword ptr [rax+rax+00h]
0x1800609e2  mov     r8, qword ptr [rbp+260h+Source.Length]; P
0x1800609e6  mov     ebx, eax
0x1800609e8  mov     [rsp+360h+var_318], eax
0x1800609ec  test    r8, r8
0x1800609ef  jz      short loc_180060A0C
0x1800609f1  mov     rcx, gs:60h
0x1800609fa  xor     edx, edx; Flags
0x1800609fc  mov     rcx, [rcx+30h]; HeapHandle
0x180060a00  call    cs:__imp_RtlFreeHeap
0x180060a07  nop     dword ptr [rax+rax+00h]
0x180060a0c  test    ebx, ebx
0x180060a0e  js      short loc_180060A24
0x180060a10  cmp     [rsp+360h+var_330], 0
0x180060a15  jnz     loc_180060C90
0x180060a1b  mov     rax, [rsp+360h+KeyHandle]
0x180060a20  mov     [r12], rax
0x180060a24  mov     eax, dword ptr [rbp+260h+arg_20]
0x180060a2a  test    dil, al
0x180060a2d  jz      loc_180060C36
0x180060a33  test    ebx, ebx
0x180060a35  jns     loc_180060C3A
0x180060a3b  test    byte ptr [rsi], 2
0x180060a3e  jnz     loc_180060C6D
0x180060a44  xorps   xmm0, xmm0
0x180060a47  lea     rdx, aRegistryMachin_17; "\\Registry\\Machine\\Software\\Classes"
0x180060a4e  xorps   xmm1, xmm1
0x180060a51  lea     rcx, [rbp+260h+SourceString]; DestinationString
0x180060a55  movups  xmmword ptr [rbp+260h+SourceString.Length], xmm0
0x180060a59  movups  xmmword ptr [rsp+360h+KeyPath.Length], xmm1
0x180060a5e  call    cs:__imp_RtlInitUnicodeStringEx
0x180060a65  nop     dword ptr [rax+rax+00h]
0x180060a6a  movzx   ecx, word ptr [rsi+4]
0x180060a6e  mov     rdx, [rsi+10h]
0x180060a72  xor     esi, esi
0x180060a74  cmp     [rdx+rcx*2+4], si
0x180060a79  jz      loc_180060D95
0x180060a7f  mov     r8, rdi
0x180060a82  sub     di, cx
0x180060a85  mov     rax, rcx
0x180060a88  sub     rax, r8
0x180060a8b  lea     rcx, [rsp+360h+DestinationString]; DestinationString
0x180060a90  add     rax, 2
0x180060a94  add     di, di
0x180060a97  lea     rax, [rdx+rax*2]
0x180060a9b  mov     [rsp+360h+KeyPath.Buffer], rax
0x180060aa0  add     di, [rdx]
0x180060aa3  lea     rdx, [rbp+260h+SourceString]; SourceString
0x180060aa7  mov     [rsp+360h+KeyPath.Length], di
0x180060aac  call    cs:__imp_RtlCopyUnicodeString
0x180060ab3  nop     dword ptr [rax+rax+00h]
0x180060ab8  lea     rdx, [rsp+360h+KeyPath]; Source
0x180060abd  lea     rcx, [rsp+360h+DestinationString]; Destination
0x180060ac2  call    cs:__imp_RtlAppendUnicodeStringToString
0x180060ac9  nop     dword ptr [rax+rax+00h]
0x180060ace  mov     ebx, eax
0x180060ad0  test    eax, eax
0x180060ad2  js      loc_180060BDC
0x180060ad8  movzx   eax, r13b
0x180060adc  and     eax, 8
0x180060adf  mov     qword ptr [rbp+260h+var_2E8+8], rsi
0x180060ae3  or      eax, 2
0x180060ae6  shl     eax, 5
0x180060ae9  mov     dword ptr [rbp+260h+var_2D8+8], eax
0x180060aec  lea     rax, [rsp+360h+DestinationString]
0x180060af1  mov     qword ptr [rbp+260h+var_2D8], rax
0x180060af5  xorps   xmm2, xmm2
0x180060af8  mov     rax, [rsp+360h+P]
0x180060afd  mov     dword ptr [rsp+360h+var_2E8], 30h ; '0'
0x180060b05  movdqu  [rbp+260h+var_2C8], xmm2
0x180060b0a  test    rax, rax
0x180060b0d  jnz     loc_180060D3C
0x180060b13  movups  xmm0, [rsp+360h+var_2E8]
0x180060b18  mov     qword ptr [rsp+360h+KeyPath.Length], rax
0x180060b1d  lea     r9, [rsp+360h+KeyPath]
0x180060b22  movups  xmm1, [rbp+260h+var_2D8]
0x180060b26  mov     word ptr [rsp+360h+KeyPath.Buffer], ax
0x180060b2b  lea     r8, [rsp+360h+KeyInformation]
0x180060b30  mov     byte ptr [rsp+360h+KeyPath.Buffer+2], al
0x180060b34  lea     rdx, [rbp+260h+var_290]
0x180060b38  mov     [rsp+360h+var_330], al
0x180060b3c  mov     ecx, r14d
0x180060b3f  lea     rax, [rsp+360h+P]
0x180060b44  mov     [rsp+360h+P], rsi
0x180060b49  mov     [rsp+360h+var_338], rax
0x180060b4e  lea     rax, [rsp+360h+var_330]
0x180060b53  mov     [rsp+360h+ResultLength], rax
0x180060b58  movups  [rbp+260h+var_290], xmm0
0x180060b5c  mov     [rsp+360h+KeyInformation], esi
0x180060b60  movups  [rbp+260h+var_280], xmm1
0x180060b64  mov     [rsp+360h+KeyHandle], rsi
0x180060b69  movups  [rbp+260h+var_270], xmm2
0x180060b6d  call    ConstructKernelKeyPath
0x180060b72  mov     ebx, eax
0x180060b74  test    eax, eax
0x180060b76  js      short loc_180060BD8
0x180060b78  and     r13d, 1Ch
0x180060b7c  lea     r8, [rbp+260h+var_290]
0x180060b80  mov     r9d, r13d
0x180060b83  lea     rcx, [rsp+360h+KeyHandle]
0x180060b88  mov     edx, r14d
0x180060b8b  call    cs:__imp_NtOpenKeyEx
0x180060b92  nop     dword ptr [rax+rax+00h]
0x180060b97  mov     r8, [rsp+360h+P]; P
0x180060b9c  mov     edi, eax
0x180060b9e  test    r8, r8
0x180060ba1  jz      short loc_180060BBE
0x180060ba3  mov     rcx, gs:60h
0x180060bac  xor     edx, edx; Flags
0x180060bae  mov     rcx, [rcx+30h]; HeapHandle
0x180060bb2  call    cs:__imp_RtlFreeHeap
0x180060bb9  nop     dword ptr [rax+rax+00h]
0x180060bbe  test    edi, edi
0x180060bc0  js      short loc_180060BD6
0x180060bc2  cmp     [rsp+360h+var_330], 0
0x180060bc7  jnz     loc_180060CE6
0x180060bcd  mov     rax, [rsp+360h+KeyHandle]
0x180060bd2  mov     [r12], rax
0x180060bd6  mov     ebx, edi
0x180060bd8  test    ebx, ebx
0x180060bda  jns     short loc_180060C3A
0x180060bdc  mov     r13, [rsp+360h+var_38]
0x180060be4  lea     rax, [rbp+260h+var_260]
0x180060be8  cmp     r15, rax
0x180060beb  jz      short loc_180060C0B
0x180060bed  mov     rcx, gs:60h
0x180060bf6  mov     r8, r15; P
0x180060bf9  xor     edx, edx; Flags
0x180060bfb  mov     rcx, [rcx+30h]; HeapHandle
0x180060bff  call    cs:__imp_RtlFreeHeap
0x180060c06  nop     dword ptr [rax+rax+00h]
0x180060c0b  mov     eax, ebx
0x180060c0d  mov     rbx, [rsp+360h+var_30]
  ... truncated ...
```
