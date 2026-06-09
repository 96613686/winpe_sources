# BasepConstructSxsCreateProcessMessage

- ea: `0x18002e8e0`
- end: `0x18002f111`
- name: `BasepConstructSxsCreateProcessMessage`
- size: `2097`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002d730`
- `0x18002dbac`
- `0x18002e0cc`
- `0x18002e644`
- `0x18002e8e0`
- `0x18002f43c`
- `0x180048084`
- `0x18008275d`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002ea7e`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18002ea7e`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002eb8f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ebf2`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002eb8f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18002ebf2`
- `ntdll!NtOpenFile` at `0x18002ec61`
- `ntdll!NtOpenFile` at `0x18002ec61`
- `ntdll!wcslen` at `0x18002ea15`
- `ntdll!wcslen` at `0x18002ea15`
- `ntdll!RtlFreeUnicodeString` at `0x18002f0c0`
- `ntdll!RtlFreeUnicodeString` at `0x18002f0c0`
- `ntdll!NtQueryInformationProcess` at `0x18002e9c0`
- `ntdll!NtQueryInformationProcess` at `0x18002e9c0`
- `ntdll!RtlInitUnicodeString` at `0x18002f060`
- `ntdll!RtlInitUnicodeString` at `0x18002f060`
- `ntdll!RtlFreeHeap` at `0x18002f0e7`
- `ntdll!RtlFreeHeap` at `0x18002f0e7`
- `ntdll!RtlAllocateHeap` at `0x18002eb06`
- `ntdll!RtlAllocateHeap` at `0x18002ee57`
- `ntdll!RtlAllocateHeap` at `0x18002eb06`
- `ntdll!RtlAllocateHeap` at `0x18002ee57`

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
0x18002e8e0  mov     rax, rsp
0x18002e8e3  mov     [rax+18h], rbx
0x18002e8e7  mov     [rax+20h], r9
0x18002e8eb  mov     [rax+10h], rdx
0x18002e8ef  mov     [rax+8], rcx
0x18002e8f3  push    rbp
0x18002e8f4  push    rsi
0x18002e8f5  push    rdi
0x18002e8f6  push    r12
0x18002e8f8  push    r13
0x18002e8fa  push    r14
0x18002e8fc  push    r15
0x18002e8fe  lea     rbp, [rax-148h]
0x18002e905  sub     rsp, 210h
0x18002e90c  xor     esi, esi
0x18002e90e  lea     rcx, [rbp+140h+ProcessInformation]; void *
0x18002e915  mov     r13, r8
0x18002e918  mov     dword ptr [rsp+240h+var_1D0+4], esi
0x18002e91c  xor     edx, edx; Val
0x18002e91e  mov     [rsp+240h+var_1C8], esi
0x18002e922  mov     rbx, r9
0x18002e925  movzx   r12d, sil
0x18002e929  lea     r14d, [rsi+40h]
0x18002e92d  mov     r8d, r14d; Size
0x18002e930  call    memset_0
0x18002e935  mov     rdi, [rbp+140h+arg_80]
0x18002e93c  xorps   xmm0, xmm0
0x18002e93f  xorps   xmm1, xmm1
0x18002e942  mov     byte ptr [rsp+240h+var_1D0], sil
0x18002e947  mov     rcx, rdi; void *
0x18002e94a  mov     [rbp+140h+P], rsi
0x18002e94e  xor     edx, edx; Val
0x18002e950  mov     r8d, 1C8h; Size
0x18002e956  movups  xmmword ptr [rbp+140h+var_90], xmm0
0x18002e95d  movups  [rbp+140h+var_80], xmm0
0x18002e964  movups  [rbp+140h+var_B0], xmm1
0x18002e96b  movups  [rbp+140h+var_A0], xmm1
0x18002e972  movups  xmmword ptr [rbp+140h+UnicodeString.Length], xmm0
0x18002e976  movups  xmmword ptr [rbp+140h+Destination.Length], xmm1
0x18002e97a  movups  xmmword ptr [rbp+140h+var_1A0.Length], xmm0
0x18002e97e  movups  [rbp+140h+var_C0], xmm1
0x18002e985  call    memset_0
0x18002e98a  mov     r15, [rbp+140h+arg_88]
0x18002e991  lea     r8d, [rsi+58h]; Size
0x18002e995  mov     rcx, r15; void *
0x18002e998  xor     edx, edx; Val
0x18002e99a  call    memset_0
0x18002e99f  mov     r9d, r14d; ProcessInformationLength
0x18002e9a2  mov     [rdi+9Ch], esi
0x18002e9a8  lea     r8, [rbp+140h+ProcessInformation]; ProcessInformation
0x18002e9af  mov     [rbp+140h+ProcessInformation], r14
0x18002e9b6  xor     edx, edx; ProcessInformationClass
0x18002e9b8  mov     [rsp+240h+ReturnLength], rsi; ReturnLength
0x18002e9bd  mov     rcx, rbx; ProcessHandle
0x18002e9c0  call    cs:__imp_NtQueryInformationProcess
0x18002e9c7  nop     dword ptr [rax+rax+00h]
0x18002e9cc  lea     ecx, [rsi+1]
0x18002e9cf  test    eax, eax
0x18002e9d1  js      short loc_18002E9DD
0x18002e9d3  test    [rbp+140h+var_38], cl
0x18002e9d9  cmovnz  r12d, ecx
0x18002e9dd  mov     r14, [rbp+140h+String]
0x18002e9e4  test    r14, r14
0x18002e9e7  jz      loc_18002ECA1
0x18002e9ed  xorps   xmm0, xmm0
0x18002e9f0  xor     eax, eax
0x18002e9f2  lea     rax, [rbp+140h+Destination]
0x18002e9f6  mov     rcx, r14; String
0x18002e9f9  mov     qword ptr [rbp+140h+var_1C0.Length], rax
0x18002e9fd  lea     rax, [rbp+140h+var_1A0]
0x18002ea01  movups  xmmword ptr [rbp+140h+ObjectAttributes.ObjectName], xmm0
0x18002ea05  mov     [rbp+140h+var_1C0.Buffer], rax
0x18002ea09  movups  xmmword ptr [rbp+140h+ObjectAttributes.Length], xmm0
0x18002ea0d  movups  xmmword ptr [rbp+140h+ObjectAttributes+1Ch], xmm0
0x18002ea11  movups  xmmword ptr [rbp+140h+IoStatusBlock], xmm0
0x18002ea15  call    cs:__imp_wcslen
0x18002ea1c  nop     dword ptr [rax+rax+00h]
0x18002ea21  mov     rsi, rax
0x18002ea24  lea     ecx, [rax-1]
0x18002ea27  cmp     word ptr [r14+rcx*2], 5Ch ; '\'
0x18002ea2d  jnz     short loc_18002EA39
0x18002ea2f  mov     ebx, 0C000000Dh
0x18002ea34  jmp     loc_18002F0BC
0x18002ea39  mov     rcx, [rbp+140h+TokenHandle]; TokenHandle
0x18002ea40  lea     rdx, [rsp+240h+var_1D0]
0x18002ea45  bts     dword ptr [rdi], 0Ah
0x18002ea49  call    IsFullTrustIntegrityToken
0x18002ea4e  mov     ebx, eax
0x18002ea50  test    eax, eax
0x18002ea52  js      loc_18002F0BC
0x18002ea58  cmp     byte ptr [rsp+240h+var_1D0], 0
0x18002ea5d  jz      short loc_18002EA63
0x18002ea5f  bts     dword ptr [rdi], 0Bh
0x18002ea63  cmp     [rbp+140h+arg_30], 0
0x18002ea6a  lea     rdx, [rbp+140h+UnicodeString]
0x18002ea6e  mov     rcx, r14
0x18002ea71  setz    byte ptr [rbp+140h+arg_80]
0x18002ea78  xor     r9d, r9d
0x18002ea7b  xor     r8d, r8d
0x18002ea7e  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x18002ea85  nop     dword ptr [rax+rax+00h]
0x18002ea8a  mov     ebx, eax
0x18002ea8c  test    eax, eax
0x18002ea8e  js      loc_18002F0BC
0x18002ea94  xor     ecx, ecx
0x18002ea96  xor     edx, edx
0x18002ea98  add     si, si
0x18002ea9b  mov     [rbp+140h+Destination.Length], cx
0x18002ea9f  xor     ebx, ebx
0x18002eaa1  mov     dword ptr [rbp+140h+Destination+4], edx
0x18002eaa4  mov     [rbp+140h+Destination.Buffer], rcx
0x18002eaa8  mov     [rbp+140h+var_1A0.Length], cx
0x18002eaac  lea     r13d, [rcx+2]
0x18002eab0  lea     eax, [rsi+1Ah]
0x18002eab3  mov     dword ptr [rbp+140h+var_1A0+4], edx
0x18002eab6  mov     [rbp+140h+Destination.MaximumLength], ax
0x18002eaba  movzx   eax, [rbp+140h+UnicodeString.Length]
0x18002eabe  add     ax, 1Ah
0x18002eac2  mov     [rbp+140h+var_1A0.Buffer], rcx
0x18002eac6  mov     [rbp+140h+var_1A0.MaximumLength], ax
0x18002eaca  xor     r8d, r8d; Size
0x18002eacd  cmp     rdx, r13
0x18002ead0  jz      short loc_18002EAF7
0x18002ead2  mov     rax, qword ptr [rbp+rdx*8+140h+var_1C0.Length]
0x18002ead7  movzx   eax, word ptr [rax+2]
0x18002eadb  add     rax, r8
0x18002eade  cmp     rax, r8
0x18002eae1  jb      short loc_18002EAED
0x18002eae3  inc     rdx
0x18002eae6  mov     r8, rax
0x18002eae9  xor     ebx, ebx
0x18002eaeb  jmp     short loc_18002EACD
0x18002eaed  mov     ebx, 0C0000095h
0x18002eaf2  jmp     loc_18002F0BC
0x18002eaf7  mov     rcx, gs:60h
0x18002eb00  xor     edx, edx; Flags
0x18002eb02  mov     rcx, [rcx+30h]; HeapHandle
0x18002eb06  call    cs:__imp_RtlAllocateHeap
0x18002eb0d  nop     dword ptr [rax+rax+00h]
0x18002eb12  mov     [r15+40h], rax
0x18002eb16  test    rax, rax
0x18002eb19  jnz     short loc_18002EB25
0x18002eb1b  mov     ebx, 0C0000017h
0x18002eb20  jmp     loc_18002F0BC
0x18002eb25  xor     ecx, ecx
0x18002eb27  mov     r8, qword ptr [rbp+rcx*8+140h+var_1C0.Length]
0x18002eb2c  xor     eax, eax
0x18002eb2e  mov     [r8], ax
0x18002eb32  test    rcx, rcx
0x18002eb35  jz      short loc_18002EB46
0x18002eb37  mov     rax, qword ptr [rsp+rcx*8+240h+var_1C8]
0x18002eb3c  movzx   edx, word ptr [rax+2]
0x18002eb40  add     rdx, [rax+8]
0x18002eb44  jmp     short loc_18002EB4A
0x18002eb46  mov     rdx, [r15+40h]
0x18002eb4a  inc     rcx
0x18002eb4d  mov     [r8+8], rdx
0x18002eb51  cmp     rcx, r13
0x18002eb54  jnz     short loc_18002EB27
0x18002eb56  test    ebx, ebx
0x18002eb58  js      loc_18002F0BC
0x18002eb5e  movups  xmm0, xmmword ptr cs:ModernFakeExePathSuffix
0x18002eb65  mov     word ptr [rbp+140h+var_178+2], si
0x18002eb69  mov     word ptr [rbp+140h+var_178], si
0x18002eb6d  xor     esi, esi
0x18002eb6f  movdqu  [rbp+140h+var_168], xmm0
0x18002eb74  mov     [rbp+140h+var_170], r14
0x18002eb78  cmp     rsi, r13
0x18002eb7b  jz      short loc_18002EBAA
0x18002eb7d  mov     rax, rsi
0x18002eb80  lea     rdx, [rbp+140h+var_178]
0x18002eb84  shl     rax, 4
0x18002eb88  lea     rcx, [rbp+140h+Destination]; Destination
0x18002eb8c  add     rdx, rax; Source
0x18002eb8f  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002eb96  nop     dword ptr [rax+rax+00h]
0x18002eb9b  mov     ebx, eax
0x18002eb9d  test    eax, eax
0x18002eb9f  js      loc_18002F0BC
0x18002eba5  inc     rsi
0x18002eba8  jmp     short loc_18002EB78
0x18002ebaa  mov     rax, [rbp+140h+Destination.Buffer]
0x18002ebae  xor     ecx, ecx
0x18002ebb0  movzx   edx, [rbp+140h+Destination.Length]
0x18002ebb4  shr     rdx, 1
0x18002ebb7  xor     esi, esi
0x18002ebb9  mov     [rax+rdx*2], cx
0x18002ebbd  movzx   eax, [rbp+140h+UnicodeString.Length]
0x18002ebc1  mov     word ptr [rbp+140h+var_178], ax
0x18002ebc5  movzx   eax, [rbp+140h+UnicodeString.MaximumLength]
0x18002ebc9  mov     word ptr [rbp+140h+var_178+2], ax
0x18002ebcd  mov     eax, dword ptr [rbp+140h+UnicodeString+4]
0x18002ebd0  mov     dword ptr [rbp+140h+var_178+4], eax
0x18002ebd3  mov     rax, [rbp+140h+UnicodeString.Buffer]
0x18002ebd7  mov     [rbp+140h+var_170], rax
0x18002ebdb  cmp     rsi, r13
0x18002ebde  jz      short loc_18002EC0D
0x18002ebe0  mov     rax, rsi
0x18002ebe3  lea     rdx, [rbp+140h+var_178]
0x18002ebe7  shl     rax, 4
0x18002ebeb  lea     rcx, [rbp+140h+var_1A0]; Destination
0x18002ebef  add     rdx, rax; Source
0x18002ebf2  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002ebf9  nop     dword ptr [rax+rax+00h]
0x18002ebfe  mov     ebx, eax
0x18002ec00  test    eax, eax
0x18002ec02  js      loc_18002F0BC
0x18002ec08  inc     rsi
0x18002ec0b  jmp     short loc_18002EBDB
0x18002ec0d  movzx   edx, [rbp+140h+var_1A0.Length]
0x18002ec11  lea     r9, [rbp+140h+IoStatusBlock]; IoStatusBlock
0x18002ec15  mov     rax, [rbp+140h+var_1A0.Buffer]
0x18002ec19  lea     r8, [rbp+140h+ObjectAttributes]; ObjectAttributes
0x18002ec1d  xor     ecx, ecx
0x18002ec1f  shr     rdx, 1
0x18002ec22  xorps   xmm0, xmm0
0x18002ec25  mov     [rsp+240h+OpenOptions], 21h ; '!'; OpenOptions
0x18002ec2d  mov     dword ptr [rsp+240h+ReturnLength], 5; ShareAccess
0x18002ec35  mov     [rax+rdx*2], cx
0x18002ec39  lea     rax, [rbp+140h+UnicodeString]
0x18002ec3d  mov     [rbp+140h+ObjectAttributes.RootDirectory], rcx
0x18002ec41  mov     edx, 120089h; DesiredAccess
0x18002ec46  lea     rcx, [r15+50h]; FileHandle
0x18002ec4a  mov     [rbp+140h+ObjectAttributes.ObjectName], rax
0x18002ec4e  mov     [rbp+140h+ObjectAttributes.Length], 30h ; '0'
0x18002ec55  mov     [rbp+140h+ObjectAttributes.Attributes], 40h ; '@'
0x18002ec5c  movdqu  xmmword ptr [rbp+140h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002ec61  call    cs:__imp_NtOpenFile
0x18002ec68  nop     dword ptr [rax+rax+00h]
0x18002ec6d  xor     r10d, r10d
0x18002ec70  mov     ebx, eax
0x18002ec72  test    eax, eax
0x18002ec74  js      loc_18002F0BC
0x18002ec7a  mov     r13, [r15+50h]
0x18002ec7e  lea     rax, [rbp+140h+Destination]
0x18002ec82  mov     [rbp+140h+arg_8], rax
0x18002ec89  lea     rax, [rbp+140h+var_1A0]
0x18002ec8d  mov     [rbp+140h+arg_0], rax
0x18002ec94  mov     qword ptr [rbp+140h+var_180], r10
0x18002ec98  mov     dword ptr [rbp+140h+String], r10d
0x18002ec9f  jmp     short loc_18002ECD6
0x18002eca1  lea     rcx, [rsp+240h+var_1D0+4]
0x18002eca6  mov     byte ptr [rbp+140h+arg_80], sil
0x18002ecad  call    BasepGetPreferExternalManifestConfig
0x18002ecb2  xor     r10d, r10d
0x18002ecb5  mov     ebx, eax
0x18002ecb7  test    eax, eax
0x18002ecb9  js      loc_18002F0BC
0x18002ecbf  mov     eax, [rbp+140h+arg_70]
0x18002ecc5  mov     dword ptr [rbp+140h+String], eax
0x18002eccb  mov     rax, [rbp+140h+arg_68]
0x18002ecd2  mov     qword ptr [rbp+140h+var_180], rax
0x18002ecd6  mov     rsi, [rbp+140h+arg_78]
0x18002ecdd  cmp     [rbp+140h+arg_50], r10d
0x18002ece4  jz      short loc_18002ECFC
0x18002ece6  or      dword ptr [rdi], 20h
0x18002ece9  mov     r15, [rbp+140h+arg_0]
0x18002ecf0  mov     r12b, byte ptr [rbp+140h+arg_80]
0x18002ecf7  jmp     loc_18002F06F
0x18002ecfc  test    r12b, r12b
0x18002ecff  jnz     loc_18002EF9C
0x18002ed05  cmp     dword ptr [rsp+240h+var_1D0+4], r10d
0x18002ed0a  jnz     short loc_18002ED32
0x18002ed0c  cmp     [rbp+140h+arg_30], r10d
0x18002ed13  jnz     short loc_18002ED32
0x18002ed15  mov     rcx, r13
0x18002ed18  call    BasepIsRemovableMedia
0x18002ed1d  xor     r10d, r10d
0x18002ed20  test    eax, eax
0x18002ed22  jnz     short loc_18002ED32
0x18002ed24  cmp     ds:7FFE02ECh, r10b
0x18002ed2c  jz      loc_18002EF9C
0x18002ed32  mov     r12, [rbp+140h+arg_8]
0x18002ed39  xor     r8d, r8d
0x18002ed3c  xor     ecx, ecx
0x18002ed3e  mov     [rbp+140h+var_14C], r8d
0x18002ed42  mov     [rbp+140h+var_13C], r8d
0x18002ed46  xor     r9d, r9d
0x18002ed49  mov     [rbp+140h+var_150], r10w
0x18002ed4e  movzx   edx, word ptr [r12]
0x18002ed53  lea     r11d, [r8+10h]
0x18002ed57  mov     r8, [rbp+140h+arg_0]
0x18002ed5e  mov     [rbp+140h+var_148], r10
0x18002ed62  mov     [rbp+140h+var_140], r10w
0x18002ed67  lea     eax, [rdx+14h]
0x18002ed6a  mov     [rbp+140h+var_138], r10
0x18002ed6e  mov     [rbp+140h+var_14E], ax
0x18002ed72  lea     eax, [r11+rdx]
0x18002ed76  mov     [rbp+140h+var_13E], ax
0x18002ed7a  add     dx, 2
0x18002ed7e  mov     [rbp+140h+var_1C0.MaximumLength], dx
0x18002ed82  movzx   edx, word ptr [r8]
0x18002ed86  mov     [rbp+140h+var_1C0.Length], r10w
0x18002ed8b  mov     dword ptr [rbp+140h+var_1C0+4], ecx
0x18002ed8e  mov     [rbp+140h+var_1C0.Buffer], r10
0x18002ed92  lea     eax, [rdx+14h]
0x18002ed95  mov     [rbp+140h+var_130], r10w
0x18002ed9a  mov     [rbp+140h+var_12E], ax
0x18002ed9e  add     dx, r11w
0x18002eda2  lea     rax, [rbp+140h+var_150]
  ... truncated ...
```
