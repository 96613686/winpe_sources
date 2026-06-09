# BasepConstructSxsCreateProcessMessage

- ea: `0x18002ce30`
- end: `0x18002d61e`
- name: `BasepConstructSxsCreateProcessMessage`
- size: `2030`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002bd38`
- `0x18002c180`
- `0x18002c65c`
- `0x18002cba8`
- `0x18002ce30`
- `0x18002d93c`
- `0x180043adc`
- `0x18007a7dd`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002cfc2`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002cfc2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002d0c7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002d124`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002d0c7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002d124`
- `ntdll!NtOpenFile` at `0x18002d18d`
- `ntdll!NtOpenFile` at `0x18002d18d`
- `ntdll!wcslen` at `0x18002cf5f`
- `ntdll!wcslen` at `0x18002cf5f`
- `ntdll!RtlFreeUnicodeString` at `0x18002d5da`
- `ntdll!RtlFreeUnicodeString` at `0x18002d5da`
- `ntdll!NtQueryInformationProcess` at `0x18002cf10`
- `ntdll!NtQueryInformationProcess` at `0x18002cf10`
- `ntdll!RtlInitUnicodeString` at `0x18002d580`
- `ntdll!RtlInitUnicodeString` at `0x18002d580`
- `ntdll!RtlFreeHeap` at `0x18002d5fb`
- `ntdll!RtlFreeHeap` at `0x18002d5fb`
- `ntdll!RtlAllocateHeap` at `0x18002d044`
- `ntdll!RtlAllocateHeap` at `0x18002d37d`
- `ntdll!RtlAllocateHeap` at `0x18002d044`
- `ntdll!RtlAllocateHeap` at `0x18002d37d`

## pseudocode

```c
__int64 __fastcall BasepConstructSxsCreateProcessMessage(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *p_Destination,
        __int64 a3,
        void *a4,
        __int64 a5,
        HANDLE TokenHandle,
        int a7,
        char a8,
        __int64 a9,
        unsigned int a10,
        int a11,
        wchar_t *String,
        __int64 a13,
        __int64 a14,
        int a15,
        _DWORD *a16,
        _DWORD *a17,
        PVOID *a18)
{
  bool v20; // r12
  int v23; // eax
  __int16 v24; // si
  int appended; // ebx
  __int64 v26; // rdx
  USHORT v27; // si
  SIZE_T v28; // r8
  SIZE_T v29; // rax
  PVOID Heap; // rax
  __int64 i; // rcx
  __int64 v32; // r8
  PVOID v33; // rdx
  __int64 v34; // rsi
  __int64 v35; // rsi
  struct _UNICODE_STRING *v36; // r15
  bool v37; // r12
  USHORT Length; // dx
  USHORT v39; // dx
  SIZE_T v40; // r8
  __int64 j; // rdx
  SIZE_T v42; // rax
  PVOID v43; // rax
  __int64 k; // rcx
  __int64 v45; // r8
  PVOID v46; // rdx
  struct _UNICODE_STRING v47; // xmm0
  struct _UNICODE_STRING *v48; // rcx
  __int128 v49; // xmm0
  struct _UNICODE_STRING v50; // xmm1
  __int64 v51; // rax
  int v52; // eax
  char v54; // [rsp+78h] [rbp-90h] BYREF
  int v55; // [rsp+7Ch] [rbp-8Ch] BYREF
  _DWORD v56[2]; // [rsp+80h] [rbp-88h] BYREF
  struct _UNICODE_STRING v57; // [rsp+88h] [rbp-80h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+98h] [rbp-70h] BYREF
  struct _UNICODE_STRING v59; // [rsp+A8h] [rbp-60h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-50h] BYREF
  int v61[2]; // [rsp+C8h] [rbp-40h]
  struct _UNICODE_STRING v62[2]; // [rsp+D0h] [rbp-38h] BYREF
  PVOID P; // [rsp+F0h] [rbp-18h]
  __int16 v64; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v65[6]; // [rsp+FAh] [rbp-Eh]
  __int64 v66; // [rsp+100h] [rbp-8h]
  __int16 v67; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v68[6]; // [rsp+10Ah] [rbp+2h]
  __int64 v69; // [rsp+110h] [rbp+8h]
  _WORD v70[2]; // [rsp+118h] [rbp+10h] BYREF
  int v71; // [rsp+11Ch] [rbp+14h]
  __int64 v72; // [rsp+120h] [rbp+18h]
  _WORD v73[2]; // [rsp+128h] [rbp+20h] BYREF
  int v74; // [rsp+12Ch] [rbp+24h]
  __int64 v75; // [rsp+130h] [rbp+28h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+138h] [rbp+30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+168h] [rbp+60h] BYREF
  __int64 v78[2]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v79; // [rsp+188h] [rbp+80h] BYREF
  struct _UNICODE_STRING v80; // [rsp+198h] [rbp+90h] BYREF
  __int128 v81; // [rsp+1A8h] [rbp+A0h]
  __int64 v82[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v83; // [rsp+1C8h] [rbp+C0h]
  _QWORD ProcessInformation[7]; // [rsp+1D8h] [rbp+D0h] BYREF
  char v85; // [rsp+210h] [rbp+108h]
  int Stringa; // [rsp+2B0h] [rbp+1A8h]
  bool v90; // [rsp+2D8h] [rbp+1D0h]

  v55 = 0;
  v56[0] = 0;
  v20 = 0;
  memset_0(ProcessInformation, 0, 0x40u);
  v54 = 0;
  P = 0;
  *(_OWORD *)v82 = 0;
  v83 = 0;
  v80 = 0;
  v81 = 0;
  UnicodeString = 0;
  Destination = 0;
  v59 = 0;
  v79 = 0;
  memset_0(a17, 0, 0x1C8u);
  memset_0(a18, 0, 0x58u);
  a17[39] = 0;
  ProcessInformation[0] = 64;
  if ( NtQueryInformationProcess(a4, ProcessBasicInformation, ProcessInformation, 0x40u, 0) >= 0 )
    v20 = (v85 & 1) != 0;
  if ( String )
  {
    *(_QWORD *)&v57.Length = &Destination;
    v57.Buffer = (PWSTR)&v59;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    v23 = wcslen(String);
    v24 = v23;
    if ( String[v23 - 1] == 92 )
    {
      appended = -1073741811;
      goto LABEL_85;
    }
    *a17 |= 0x400u;
    appended = IsFullTrustIntegrityToken(TokenHandle, &v54);
    if ( appended < 0 )
      goto LABEL_85;
    if ( v54 )
      *a17 |= 0x800u;
    v90 = a7 == 0;
    appended = RtlDosPathNameToNtPathName_U_WithStatus(String, &UnicodeString, 0, 0);
    if ( appended < 0 )
      goto LABEL_85;
    v26 = 0;
    v27 = 2 * v24;
    Destination.Length = 0;
    *(&Destination.MaximumLength + 2) = 0;
    Destination.Buffer = 0;
    v59.Length = 0;
    *(&v59.MaximumLength + 2) = 0;
    *(_DWORD *)&Destination.MaximumLength = (unsigned __int16)(v27 + 26);
    v59.Buffer = 0;
    *(_DWORD *)&v59.MaximumLength = (unsigned __int16)(UnicodeString.Length + 26);
    v28 = 0;
    while ( v26 != 2 )
    {
      v29 = v28 + *(unsigned __int16 *)(*((_QWORD *)&v57.Length + v26) + 2LL);
      if ( v29 < v28 )
      {
LABEL_14:
        appended = -1073741675;
        goto LABEL_85;
      }
      ++v26;
      v28 = v29;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v28);
    a18[8] = Heap;
    if ( !Heap )
      goto LABEL_16;
    for ( i = 0; i != 2; ++i )
    {
      v32 = *((_QWORD *)&v57.Length + i);
      *(_WORD *)v32 = 0;
      if ( i )
        v33 = (PVOID)(*(_QWORD *)(*(_QWORD *)&v56[2 * i] + 8LL) + *(unsigned __int16 *)(*(_QWORD *)&v56[2 * i] + 2LL));
      else
        v33 = a18[8];
      *(_QWORD *)(v32 + 8) = v33;
    }
    v62[0].MaximumLength = v27;
    v62[0].Length = v27;
    v34 = 0;
    v62[1] = *(struct _UNICODE_STRING *)ModernFakeExePathSuffix;
    v62[0].Buffer = String;
    while ( v34 != 2 )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, &v62[v34]);
      if ( appended < 0 )
        goto LABEL_85;
      ++v34;
    }
    v35 = 0;
    Destination.Buffer[(unsigned __int64)Destination.Length >> 1] = 0;
    v62[0] = UnicodeString;
    while ( v35 != 2 )
    {
      appended = RtlAppendUnicodeStringToString(&v59, &v62[v35]);
      if ( appended < 0 )
        goto LABEL_85;
      ++v35;
    }
    v59.Buffer[(unsigned __int64)v59.Length >> 1] = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &UnicodeString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    appended = NtOpenFile(a18 + 10, 0x120089u, &ObjectAttributes, &IoStatusBlock, 5u, 0x21u);
    if ( appended < 0 )
      goto LABEL_85;
    a3 = (__int64)a18[10];
    p_Destination = &Destination;
    a1 = &v59;
    *(_QWORD *)v61 = 0;
    Stringa = 0;
  }
  else
  {
    v90 = 0;
    appended = BasepGetPreferExternalManifestConfig(&v55);
    if ( appended < 0 )
      goto LABEL_85;
    Stringa = a15;
    *(_QWORD *)v61 = a14;
  }
  if ( a11 )
  {
    *a17 |= 0x20u;
    v36 = a1;
    v37 = v90;
    goto LABEL_76;
  }
  if ( v20 || !v55 && !a7 && !(unsigned int)BasepIsRemovableMedia(a3) && !MEMORY[0x7FFE02EC] )
  {
    if ( a9 )
    {
      *((_QWORD *)a17 + 6) = a9;
      *((_QWORD *)a17 + 7) = a10;
    }
    v36 = a1;
    v37 = v90;
    *((struct _UNICODE_STRING *)a17 + 2) = *a1;
    v50 = *p_Destination;
    v51 = *(_QWORD *)v61;
    *a17 |= 0x40u;
    *((_QWORD *)a17 + 10) = v51;
    a17[22] = Stringa;
    *((_QWORD *)a17 + 1) = a3;
    *((struct _UNICODE_STRING *)a17 + 1) = v50;
    if ( v90 )
      *a17 |= 0x200u;
    goto LABEL_59;
  }
  *(_DWORD *)&v65[2] = 0;
  *(_DWORD *)&v68[2] = 0;
  v64 = 0;
  Length = p_Destination->Length;
  v66 = 0;
  v67 = 0;
  v69 = 0;
  *(_DWORD *)v65 = (unsigned __int16)(Length + 20);
  *(_DWORD *)v68 = (unsigned __int16)(Length + 16);
  v57.MaximumLength = Length + 2;
  v39 = a1->Length;
  v57.Length = 0;
  *(_DWORD *)(&v57.MaximumLength + 1) = 0;
  v57.Buffer = 0;
  v70[0] = 0;
  v70[1] = v39 + 20;
  v71 = 0;
  IoStatusBlock.Pointer = &v64;
  IoStatusBlock.Information = (ULONG_PTR)v70;
  v78[0] = (__int64)&v67;
  v78[1] = (__int64)v73;
  *(_QWORD *)&ObjectAttributes.Length = &v57;
  ObjectAttributes.RootDirectory = &v64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v67;
  *(_QWORD *)&ObjectAttributes.Attributes = v70;
  ObjectAttributes.SecurityDescriptor = v73;
  v72 = 0;
  v73[0] = 0;
  v73[1] = v39 + 16;
  v74 = 0;
  v75 = 0;
  *(_QWORD *)&v62[0].Length = p_Destination;
  v62[0].Buffer = &a1->Length;
  if ( a18[8] )
  {
    P = a18[8];
    a18[8] = 0;
  }
  v40 = 0;
  for ( j = 0; j != 5; ++j )
  {
    v42 = v40 + *(unsigned __int16 *)(*((_QWORD *)&ObjectAttributes.Length + j) + 2LL);
    if ( v42 < v40 )
      goto LABEL_14;
    v40 = v42;
  }
  v43 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v40);
  a18[8] = v43;
  if ( !v43 )
  {
LABEL_16:
    appended = -1073741801;
    goto LABEL_85;
  }
  for ( k = 0; k != 5; ++k )
  {
    v45 = *((_QWORD *)&ObjectAttributes.Length + k);
    *(_WORD *)v45 = 0;
    if ( k )
      v46 = (PVOID)(*(_QWORD *)(*(&v75 + k) + 8) + *(unsigned __int16 *)(*(&v75 + k) + 2));
    else
      v46 = a18[8];
    *(_QWORD *)(v45 + 8) = v46;
  }
  v82[1] = (__int64)a4;
  *(_QWORD *)&v83 = a5;
  v82[0] = a3;
  if ( a9 )
  {
    v47 = *p_Destination;
    *(_QWORD *)&v81 = a9;
    v80 = v47;
    *((_QWORD *)&v81 + 1) = a10;
  }
  v48 = &v80;
  if ( !a9 )
    LODWORD(v48) = 0;
  appended = BasepSxsCreateProcessCsrMessage(
               (int)v48,
               (int)a18 + 32,
               v61[0],
               Stringa,
               (__int64)&IoStatusBlock,
               (__int64)a18,
               (__int64)v62,
               (__int64)v82,
               (__int64)v78,
               (__int64)(a18 + 4),
               &v57,
               a13,
               a17);
  if ( appended >= 0 )
  {
    v36 = a1;
    v37 = v90;
LABEL_59:
    if ( !String || v54 )
    {
      appended = BasepSxsGetCreateProcessLanguageFallbacksCached(&v79);
      if ( appended < 0 )
        goto LABEL_85;
      v49 = v79;
    }
    else
    {
      v49 = *(_OWORD *)g_DoubleNulString;
    }
    *(_OWORD *)(a17 + 34) = v49;
    if ( a7 )
      *a17 |= 0x80u;
    v52 = *a17;
    if ( (*a17 & 1) != 0 )
    {
      *a16 |= 0x2000u;
      v52 = *a17;
    }
    if ( (a8 & 1) != 0 )
    {
      v52 |= 0x10u;
      *a17 = v52;
    }
    if ( (v52 & 0x41) != 0 )
      RtlInitUnicodeString((PUNICODE_STRING)(a17 + 42), L"-----------------------------------------------------------");
LABEL_76:
    if ( a7 )
    {
      *a16 |= 0x8000u;
    }
    else if ( (*(_BYTE *)a17 & 0x41) != 0 || String )
    {
LABEL_84:
      a17[1] = *a16;
      goto LABEL_85;
    }
    if ( !v37 )
    {
      appended = BasepCheckDotLocalExists(v36, String != 0, v56);
      if ( appended < 0 )
        goto LABEL_85;
      if ( v56[0] )
        *a16 |= 0x1000u;
    }
    goto LABEL_84;
  }
LABEL_85:
  RtlFreeUnicodeString(&UnicodeString);
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18002ce30  mov     rax, rsp
0x18002ce33  mov     [rax+18h], rbx
0x18002ce37  mov     [rax+20h], r9
0x18002ce3b  mov     [rax+10h], rdx
0x18002ce3f  mov     [rax+8], rcx
0x18002ce43  push    rbp
0x18002ce44  push    rsi
0x18002ce45  push    rdi
0x18002ce46  push    r12
0x18002ce48  push    r13
0x18002ce4a  push    r14
0x18002ce4c  push    r15
0x18002ce4e  lea     rbp, [rax-148h]
0x18002ce55  sub     rsp, 210h
0x18002ce5c  xor     esi, esi
0x18002ce5e  lea     rcx, [rbp+140h+ProcessInformation]; void *
0x18002ce65  mov     r13, r8
0x18002ce68  mov     dword ptr [rsp+240h+var_1D0+4], esi
0x18002ce6c  xor     edx, edx; Val
0x18002ce6e  mov     [rsp+240h+var_1C8], esi
0x18002ce72  mov     rbx, r9
0x18002ce75  movzx   r12d, sil
0x18002ce79  lea     r14d, [rsi+40h]
0x18002ce7d  mov     r8d, r14d; Size
0x18002ce80  call    memset_0
0x18002ce85  mov     rdi, [rbp+140h+arg_80]
0x18002ce8c  xorps   xmm0, xmm0
0x18002ce8f  xorps   xmm1, xmm1
0x18002ce92  mov     byte ptr [rsp+240h+var_1D0], sil
0x18002ce97  mov     rcx, rdi; void *
0x18002ce9a  mov     [rbp+140h+P], rsi
0x18002ce9e  xor     edx, edx; Val
0x18002cea0  mov     r8d, 1C8h; Size
0x18002cea6  movups  xmmword ptr [rbp+140h+var_90], xmm0
0x18002cead  movups  [rbp+140h+var_80], xmm0
0x18002ceb4  movups  [rbp+140h+var_B0], xmm1
0x18002cebb  movups  [rbp+140h+var_A0], xmm1
0x18002cec2  movups  xmmword ptr [rbp+140h+UnicodeString.Length], xmm0
0x18002cec6  movups  xmmword ptr [rbp+140h+Destination.Length], xmm1
0x18002ceca  movups  xmmword ptr [rbp+140h+var_1A0.Length], xmm0
0x18002cece  movups  [rbp+140h+var_C0], xmm1
0x18002ced5  call    memset_0
0x18002ceda  mov     r15, [rbp+140h+arg_88]
0x18002cee1  lea     r8d, [rsi+58h]; Size
0x18002cee5  mov     rcx, r15; void *
0x18002cee8  xor     edx, edx; Val
0x18002ceea  call    memset_0
0x18002ceef  mov     r9d, r14d; ProcessInformationLength
0x18002cef2  mov     [rdi+9Ch], esi
0x18002cef8  lea     r8, [rbp+140h+ProcessInformation]; ProcessInformation
0x18002ceff  mov     [rbp+140h+ProcessInformation], r14
0x18002cf06  xor     edx, edx; ProcessInformationClass
0x18002cf08  mov     [rsp+240h+ReturnLength], rsi; ReturnLength
0x18002cf0d  mov     rcx, rbx; ProcessHandle
0x18002cf10  call    cs:__imp_NtQueryInformationProcess
0x18002cf16  lea     ecx, [rsi+1]
0x18002cf19  test    eax, eax
0x18002cf1b  js      short loc_18002CF27
0x18002cf1d  test    [rbp+140h+var_38], cl
0x18002cf23  cmovnz  r12d, ecx
0x18002cf27  mov     r14, [rbp+140h+String]
0x18002cf2e  test    r14, r14
0x18002cf31  jz      loc_18002D1C7
0x18002cf37  xorps   xmm0, xmm0
0x18002cf3a  xor     eax, eax
0x18002cf3c  lea     rax, [rbp+140h+Destination]
0x18002cf40  mov     rcx, r14; String
0x18002cf43  mov     qword ptr [rbp+140h+var_1C0.Length], rax
0x18002cf47  lea     rax, [rbp+140h+var_1A0]
0x18002cf4b  movups  xmmword ptr [rbp+140h+ObjectAttributes.ObjectName], xmm0
0x18002cf4f  mov     [rbp+140h+var_1C0.Buffer], rax
0x18002cf53  movups  xmmword ptr [rbp+140h+ObjectAttributes.Length], xmm0
0x18002cf57  movups  xmmword ptr [rbp+140h+ObjectAttributes+1Ch], xmm0
0x18002cf5b  movups  xmmword ptr [rbp+140h+IoStatusBlock], xmm0
0x18002cf5f  call    cs:__imp_wcslen
0x18002cf65  mov     rsi, rax
0x18002cf68  lea     ecx, [rax-1]
0x18002cf6b  cmp     word ptr [r14+rcx*2], 5Ch ; '\'
0x18002cf71  jnz     short loc_18002CF7D
0x18002cf73  mov     ebx, 0C000000Dh
0x18002cf78  jmp     loc_18002D5D6
0x18002cf7d  mov     rcx, [rbp+140h+TokenHandle]; TokenHandle
0x18002cf84  lea     rdx, [rsp+240h+var_1D0]
0x18002cf89  bts     dword ptr [rdi], 0Ah
0x18002cf8d  call    IsFullTrustIntegrityToken
0x18002cf92  mov     ebx, eax
0x18002cf94  test    eax, eax
0x18002cf96  js      loc_18002D5D6
0x18002cf9c  cmp     byte ptr [rsp+240h+var_1D0], 0
0x18002cfa1  jz      short loc_18002CFA7
0x18002cfa3  bts     dword ptr [rdi], 0Bh
0x18002cfa7  cmp     [rbp+140h+arg_30], 0
0x18002cfae  lea     rdx, [rbp+140h+UnicodeString]
0x18002cfb2  mov     rcx, r14
0x18002cfb5  setz    byte ptr [rbp+140h+arg_80]
0x18002cfbc  xor     r9d, r9d
0x18002cfbf  xor     r8d, r8d
0x18002cfc2  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002cfc8  mov     ebx, eax
0x18002cfca  test    eax, eax
0x18002cfcc  js      loc_18002D5D6
0x18002cfd2  xor     ecx, ecx
0x18002cfd4  xor     edx, edx
0x18002cfd6  add     si, si
0x18002cfd9  mov     [rbp+140h+Destination.Length], cx
0x18002cfdd  xor     ebx, ebx
0x18002cfdf  mov     dword ptr [rbp+140h+Destination+4], edx
0x18002cfe2  mov     [rbp+140h+Destination.Buffer], rcx
0x18002cfe6  mov     [rbp+140h+var_1A0.Length], cx
0x18002cfea  lea     r13d, [rcx+2]
0x18002cfee  lea     eax, [rsi+1Ah]
0x18002cff1  mov     dword ptr [rbp+140h+var_1A0+4], edx
0x18002cff4  mov     [rbp+140h+Destination.MaximumLength], ax
0x18002cff8  movzx   eax, [rbp+140h+UnicodeString.Length]
0x18002cffc  add     ax, 1Ah
0x18002d000  mov     [rbp+140h+var_1A0.Buffer], rcx
0x18002d004  mov     [rbp+140h+var_1A0.MaximumLength], ax
0x18002d008  xor     r8d, r8d; Size
0x18002d00b  cmp     rdx, r13
0x18002d00e  jz      short loc_18002D035
0x18002d010  mov     rax, qword ptr [rbp+rdx*8+140h+var_1C0.Length]
0x18002d015  movzx   eax, word ptr [rax+2]
0x18002d019  add     rax, r8
0x18002d01c  cmp     rax, r8
0x18002d01f  jb      short loc_18002D02B
0x18002d021  inc     rdx
0x18002d024  mov     r8, rax
0x18002d027  xor     ebx, ebx
0x18002d029  jmp     short loc_18002D00B
0x18002d02b  mov     ebx, 0C0000095h
0x18002d030  jmp     loc_18002D5D6
0x18002d035  mov     rcx, gs:60h
0x18002d03e  xor     edx, edx; Flags
0x18002d040  mov     rcx, [rcx+30h]; HeapHandle
0x18002d044  call    cs:__imp_RtlAllocateHeap
0x18002d04a  mov     [r15+40h], rax
0x18002d04e  test    rax, rax
0x18002d051  jnz     short loc_18002D05D
0x18002d053  mov     ebx, 0C0000017h
0x18002d058  jmp     loc_18002D5D6
0x18002d05d  xor     ecx, ecx
0x18002d05f  mov     r8, qword ptr [rbp+rcx*8+140h+var_1C0.Length]
0x18002d064  xor     eax, eax
0x18002d066  mov     [r8], ax
0x18002d06a  test    rcx, rcx
0x18002d06d  jz      short loc_18002D07E
0x18002d06f  mov     rax, qword ptr [rsp+rcx*8+240h+var_1C8]
0x18002d074  movzx   edx, word ptr [rax+2]
0x18002d078  add     rdx, [rax+8]
0x18002d07c  jmp     short loc_18002D082
0x18002d07e  mov     rdx, [r15+40h]
0x18002d082  inc     rcx
0x18002d085  mov     [r8+8], rdx
0x18002d089  cmp     rcx, r13
0x18002d08c  jnz     short loc_18002D05F
0x18002d08e  test    ebx, ebx
0x18002d090  js      loc_18002D5D6
0x18002d096  movups  xmm0, xmmword ptr cs:ModernFakeExePathSuffix
0x18002d09d  mov     word ptr [rbp+140h+var_178+2], si
0x18002d0a1  mov     word ptr [rbp+140h+var_178], si
0x18002d0a5  xor     esi, esi
0x18002d0a7  movdqu  [rbp+140h+var_168], xmm0
0x18002d0ac  mov     [rbp+140h+var_170], r14
0x18002d0b0  cmp     rsi, r13
0x18002d0b3  jz      short loc_18002D0DC
0x18002d0b5  mov     rax, rsi
0x18002d0b8  lea     rdx, [rbp+140h+var_178]
0x18002d0bc  shl     rax, 4
0x18002d0c0  lea     rcx, [rbp+140h+Destination]; Destination
0x18002d0c4  add     rdx, rax; Source
0x18002d0c7  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002d0cd  mov     ebx, eax
0x18002d0cf  test    eax, eax
0x18002d0d1  js      loc_18002D5D6
0x18002d0d7  inc     rsi
0x18002d0da  jmp     short loc_18002D0B0
0x18002d0dc  mov     rax, [rbp+140h+Destination.Buffer]
0x18002d0e0  xor     ecx, ecx
0x18002d0e2  movzx   edx, [rbp+140h+Destination.Length]
0x18002d0e6  shr     rdx, 1
0x18002d0e9  xor     esi, esi
0x18002d0eb  mov     [rax+rdx*2], cx
0x18002d0ef  movzx   eax, [rbp+140h+UnicodeString.Length]
0x18002d0f3  mov     word ptr [rbp+140h+var_178], ax
0x18002d0f7  movzx   eax, [rbp+140h+UnicodeString.MaximumLength]
0x18002d0fb  mov     word ptr [rbp+140h+var_178+2], ax
0x18002d0ff  mov     eax, dword ptr [rbp+140h+UnicodeString+4]
0x18002d102  mov     dword ptr [rbp+140h+var_178+4], eax
0x18002d105  mov     rax, [rbp+140h+UnicodeString.Buffer]
0x18002d109  mov     [rbp+140h+var_170], rax
0x18002d10d  cmp     rsi, r13
0x18002d110  jz      short loc_18002D139
0x18002d112  mov     rax, rsi
0x18002d115  lea     rdx, [rbp+140h+var_178]
0x18002d119  shl     rax, 4
0x18002d11d  lea     rcx, [rbp+140h+var_1A0]; Destination
0x18002d121  add     rdx, rax; Source
0x18002d124  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002d12a  mov     ebx, eax
0x18002d12c  test    eax, eax
0x18002d12e  js      loc_18002D5D6
0x18002d134  inc     rsi
0x18002d137  jmp     short loc_18002D10D
0x18002d139  movzx   edx, [rbp+140h+var_1A0.Length]
0x18002d13d  lea     r9, [rbp+140h+IoStatusBlock]; IoStatusBlock
0x18002d141  mov     rax, [rbp+140h+var_1A0.Buffer]
0x18002d145  lea     r8, [rbp+140h+ObjectAttributes]; ObjectAttributes
0x18002d149  xor     ecx, ecx
0x18002d14b  shr     rdx, 1
0x18002d14e  xorps   xmm0, xmm0
0x18002d151  mov     [rsp+240h+OpenOptions], 21h ; '!'; OpenOptions
0x18002d159  mov     dword ptr [rsp+240h+ReturnLength], 5; ShareAccess
0x18002d161  mov     [rax+rdx*2], cx
0x18002d165  lea     rax, [rbp+140h+UnicodeString]
0x18002d169  mov     [rbp+140h+ObjectAttributes.RootDirectory], rcx
0x18002d16d  mov     edx, 120089h; DesiredAccess
0x18002d172  lea     rcx, [r15+50h]; FileHandle
0x18002d176  mov     [rbp+140h+ObjectAttributes.ObjectName], rax
0x18002d17a  mov     [rbp+140h+ObjectAttributes.Length], 30h ; '0'
0x18002d181  mov     [rbp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x18002d188  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002d18d  call    cs:__imp_NtOpenFile
0x18002d193  xor     r10d, r10d
0x18002d196  mov     ebx, eax
0x18002d198  test    eax, eax
0x18002d19a  js      loc_18002D5D6
0x18002d1a0  mov     r13, [r15+50h]
0x18002d1a4  lea     rax, [rbp+140h+Destination]
0x18002d1a8  mov     [rbp+140h+arg_8], rax
0x18002d1af  lea     rax, [rbp+140h+var_1A0]
0x18002d1b3  mov     [rbp+140h+arg_0], rax
0x18002d1ba  mov     qword ptr [rbp+140h+var_180], r10
0x18002d1be  mov     dword ptr [rbp+140h+String], r10d
0x18002d1c5  jmp     short loc_18002D1FC
0x18002d1c7  lea     rcx, [rsp+240h+var_1D0+4]
0x18002d1cc  mov     byte ptr [rbp+140h+arg_80], sil
0x18002d1d3  call    BasepGetPreferExternalManifestConfig
0x18002d1d8  xor     r10d, r10d
0x18002d1db  mov     ebx, eax
0x18002d1dd  test    eax, eax
0x18002d1df  js      loc_18002D5D6
0x18002d1e5  mov     eax, [rbp+140h+arg_70]
0x18002d1eb  mov     dword ptr [rbp+140h+String], eax
0x18002d1f1  mov     rax, [rbp+140h+arg_68]
0x18002d1f8  mov     qword ptr [rbp+140h+var_180], rax
0x18002d1fc  mov     rsi, [rbp+140h+arg_78]
0x18002d203  cmp     [rbp+140h+arg_50], r10d
0x18002d20a  jz      short loc_18002D222
0x18002d20c  or      dword ptr [rdi], 20h
0x18002d20f  mov     r15, [rbp+140h+arg_0]
0x18002d216  mov     r12b, byte ptr [rbp+140h+arg_80]
0x18002d21d  jmp     loc_18002D589
0x18002d222  test    r12b, r12b
0x18002d225  jnz     loc_18002D4BC
0x18002d22b  cmp     dword ptr [rsp+240h+var_1D0+4], r10d
0x18002d230  jnz     short loc_18002D258
0x18002d232  cmp     [rbp+140h+arg_30], r10d
0x18002d239  jnz     short loc_18002D258
0x18002d23b  mov     rcx, r13
0x18002d23e  call    BasepIsRemovableMedia
0x18002d243  xor     r10d, r10d
0x18002d246  test    eax, eax
0x18002d248  jnz     short loc_18002D258
0x18002d24a  cmp     ds:7FFE02ECh, r10b
0x18002d252  jz      loc_18002D4BC
0x18002d258  mov     r12, [rbp+140h+arg_8]
0x18002d25f  xor     r8d, r8d
0x18002d262  xor     ecx, ecx
0x18002d264  mov     [rbp+140h+var_14C], r8d
0x18002d268  mov     [rbp+140h+var_13C], r8d
0x18002d26c  xor     r9d, r9d
0x18002d26f  mov     [rbp+140h+var_150], r10w
0x18002d274  movzx   edx, word ptr [r12]
0x18002d279  lea     r11d, [r8+10h]
0x18002d27d  mov     r8, [rbp+140h+arg_0]
0x18002d284  mov     [rbp+140h+var_148], r10
0x18002d288  mov     [rbp+140h+var_140], r10w
0x18002d28d  lea     eax, [rdx+14h]
0x18002d290  mov     [rbp+140h+var_138], r10
0x18002d294  mov     [rbp+140h+var_14E], ax
0x18002d298  lea     eax, [r11+rdx]
0x18002d29c  mov     [rbp+140h+var_13E], ax
0x18002d2a0  add     dx, 2
0x18002d2a4  mov     [rbp+140h+var_1C0.MaximumLength], dx
0x18002d2a8  movzx   edx, word ptr [r8]
0x18002d2ac  mov     [rbp+140h+var_1C0.Length], r10w
0x18002d2b1  mov     dword ptr [rbp+140h+var_1C0+4], ecx
0x18002d2b4  mov     [rbp+140h+var_1C0.Buffer], r10
0x18002d2b8  lea     eax, [rdx+14h]
0x18002d2bb  mov     [rbp+140h+var_130], r10w
0x18002d2c0  mov     [rbp+140h+var_12E], ax
0x18002d2c4  add     dx, r11w
0x18002d2c8  lea     rax, [rbp+140h+var_150]
0x18002d2cc  mov     [rbp+140h+var_12C], r9d
0x18002d2d0  mov     qword ptr [rbp+140h+IoStatusBlock], rax
0x18002d2d4  lea     rax, [rbp+140h+var_130]
0x18002d2d8  mov     [rbp+140h+IoStatusBlock.Information], rax
0x18002d2dc  lea     rax, [rbp+140h+var_140]
0x18002d2e0  mov     [rbp+140h+var_D0], rax
0x18002d2e4  lea     rax, [rbp+140h+var_120]
  ... truncated ...
```
