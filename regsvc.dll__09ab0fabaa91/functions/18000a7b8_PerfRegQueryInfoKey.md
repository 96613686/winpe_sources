# PerfRegQueryInfoKey

- ea: `0x18000a7b8`
- end: `0x18000aa98`
- name: `PerfRegQueryInfoKey`
- size: `736`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64, _DWORD *, _DWORD *, _DWORD *, _DWORD *, _DWORD *, unsigned int *, PULONG, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b9c0`

## callees

- `0x180008b58`
- `0x18000a7b8`
- `0x18000aac8`
- `0x18000bef8`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a82d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a82d`
- `ntdll!NtQuerySecurityObject` at `0x18000aa67`
- `ntdll!NtQuerySecurityObject` at `0x18000aa67`
- `ntdll!NtOpenKey` at `0x18000a958`
- `ntdll!NtOpenKey` at `0x18000a973`
- `ntdll!NtOpenKey` at `0x18000a958`
- `ntdll!NtOpenKey` at `0x18000a973`
- `ntdll!RtlInitUnicodeString` at `0x18000a923`
- `ntdll!RtlInitUnicodeString` at `0x18000a923`
- `ntdll!NtClose` at `0x18000aa82`
- `ntdll!NtClose` at `0x18000aa82`

## string_xrefs

- `0x18000a918`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Perflib`

## pseudocode

```c
__int64 __fastcall PerfRegQueryInfoKey(
        HKEY a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        _DWORD *a6,
        _DWORD *a7,
        _DWORD *a8,
        unsigned int *a9,
        PULONG a10,
        _QWORD *a11)
{
  __int64 v14; // r9
  _WORD *v15; // rcx
  _DWORD *v16; // rax
  _DWORD *v17; // r14
  _DWORD *v18; // r15
  unsigned int *v19; // rdi
  _QWORD *v20; // rax
  int v21; // esi
  unsigned int v22; // ebx
  __int64 v23; // r9
  unsigned int v24; // eax
  NTSTATUS v25; // eax
  NTSTATUS SecurityObject; // ebx
  _QWORD *v27; // rcx
  PULONG v29; // rdi
  void *v30; // rcx
  SECURITY_INFORMATION v31; // edx
  ULONG *LengthNeeded; // [rsp+20h] [rbp-99h]
  struct _UNICODE_STRING v33; // [rsp+40h] [rbp-79h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-69h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v36; // [rsp+80h] [rbp-39h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v38; // [rsp+100h] [rbp+47h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+4Fh] BYREF
  unsigned int v40; // [rsp+110h] [rbp+57h] BYREF
  int v41; // [rsp+114h] [rbp+5Bh]

  v41 = HIDWORD(a3);
  v40 = 0;
  v38 = 0;
  KeyHandle = 0;
  v36 = 0;
  v33 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlRunOnceExecuteOnce(qword_18002B570, PerfpInitializeCallback, 0, 0);
  if ( *(_WORD *)(a2 + 2) >= 2u )
  {
    v15 = *(_WORD **)(a2 + 8);
    *(_WORD *)a2 = 0;
    *v15 = 0;
  }
  v16 = a5;
  v17 = a7;
  v18 = a8;
  *a4 = 0;
  v19 = a9;
  *v16 = 0;
  *a6 = 0;
  v20 = a11;
  *v17 = 2;
  *v18 = 30;
  *v19 = 0;
  if ( v20 )
    *v20 = 0;
  v21 = 1;
  if ( ((unsigned __int64)(a1 + 536870892) & 0xFFFFFFFFFFFFFFEFuLL) != 0 )
  {
LABEL_11:
    RtlInitUnicodeString(
      &DestinationString,
      L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib");
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x3000000u, &ObjectAttributes) >= 0
      || (v25 = NtOpenKey(&KeyHandle, 0x2000000u, &ObjectAttributes), SecurityObject = v25, v21 = 0, v25 >= 0) )
    {
      v29 = a10;
      v30 = KeyHandle;
      LengthNeeded = a10;
      *a10 = 0;
      v31 = 7;
      if ( v21 )
        v31 = 15;
      SecurityObject = NtQuerySecurityObject(v30, v31, SecurityDescriptor, 0, LengthNeeded);
      if ( SecurityObject == -1073741789 )
        SecurityObject = 0;
      else
        *v29 = 0;
      NtClose(KeyHandle);
      if ( SecurityObject >= 0 )
        return 0;
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        return PerfpDosError(SecurityObject);
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_17:
        if ( (*((_BYTE *)v27 + 28) & 2) != 0 && *((_BYTE *)v27 + 25) >= 2u )
          WPP_SF_d(v27[2], 47, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)SecurityObject);
        return PerfpDosError(SecurityObject);
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        46,
        WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
        (unsigned int)v25);
    }
    v27 = WPP_GLOBAL_Control;
    goto LABEL_17;
  }
  v33.Buffer = 0;
  *(_DWORD *)&v33.Length = 0;
  v22 = PerfEnumTextValue(a1, 0, &v33, v14, 0, 0, &v38, 0);
  if ( !v22 )
  {
    v22 = PerfEnumTextValue(a1, 1, &v33, v23, 0, 0, &v40, 0);
    if ( !v22 )
    {
      v24 = v38;
      if ( v40 > v38 )
      {
        v24 = v40;
        v38 = v40;
      }
      *v19 = v24;
      goto LABEL_11;
    }
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v22);
  *v17 = 0;
  *v18 = 0;
  return v22;
}

```

## disassembly

```asm
0x18000a7b8  mov     [rsp-8+arg_18], rbx
0x18000a7bd  mov     qword ptr [rsp-8+arg_10], r8
0x18000a7c2  push    rbp
0x18000a7c3  push    rsi
0x18000a7c4  push    rdi
0x18000a7c5  push    r12
0x18000a7c7  push    r13
0x18000a7c9  push    r14
0x18000a7cb  push    r15
0x18000a7cd  lea     rbp, [rsp-7]
0x18000a7d2  sub     rsp, 0C0h
0x18000a7d9  xorps   xmm0, xmm0
0x18000a7dc  xor     r12d, r12d
0x18000a7df  xorps   xmm1, xmm1
0x18000a7e2  mov     [rbp+37h+arg_10], r12d
0x18000a7e6  mov     rdi, r9
0x18000a7e9  mov     [rbp+37h+arg_0], r12d
0x18000a7ed  mov     rbx, rdx
0x18000a7f0  mov     [rbp+37h+KeyHandle], r12
0x18000a7f4  mov     r13, rcx
0x18000a7f7  lea     rdx, PerfpInitializeCallback
0x18000a7fe  xor     eax, eax
0x18000a800  lea     rcx, qword_18002B570
0x18000a807  xor     r9d, r9d
0x18000a80a  mov     [rbp+37h+var_70], rax
0x18000a80e  xor     r8d, r8d
0x18000a811  movups  [rbp+37h+var_B0], xmm0
0x18000a815  movups  [rbp+37h+SecurityDescriptor], xmm1
0x18000a819  movups  [rbp+37h+var_80], xmm1
0x18000a81d  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x18000a821  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x18000a825  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a829  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x18000a82d  call    cs:__imp_RtlRunOnceExecuteOnce
0x18000a833  lea     edx, [r12+2]
0x18000a838  cmp     [rbx+2], dx
0x18000a83c  jb      short loc_18000A84A
0x18000a83e  mov     rcx, [rbx+8]
0x18000a842  mov     [rbx], r12w
0x18000a846  mov     [rcx], r12w
0x18000a84a  mov     rax, [rbp+37h+arg_20]
0x18000a84e  mov     r14, [rbp+37h+arg_30]
0x18000a852  mov     r15, [rbp+37h+arg_38]
0x18000a856  mov     [rdi], r12d
0x18000a859  mov     rdi, [rbp+37h+arg_40]
0x18000a860  mov     [rax], r12d
0x18000a863  mov     rax, [rbp+37h+arg_28]
0x18000a867  mov     [rax], r12d
0x18000a86a  mov     rax, [rbp+37h+arg_50]
0x18000a871  mov     [r14], edx
0x18000a874  mov     dword ptr [r15], 1Eh
0x18000a87b  mov     [rdi], r12d
0x18000a87e  test    rax, rax
0x18000a881  jz      short loc_18000A886
0x18000a883  mov     [rax], r12
0x18000a886  lea     rax, [r13+7FFFFFB0h]
0x18000a88d  mov     esi, 1
0x18000a892  test    rax, 0FFFFFFFFFFFFFFEFh
0x18000a898  jnz     short loc_18000A912
0x18000a89a  mov     [rsp+0F0h+var_B8], r12; unsigned int *
0x18000a89f  lea     rax, [rbp+37h+arg_0]
0x18000a8a3  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x18000a8a8  lea     r8, [rbp+37h+var_B0]
0x18000a8ac  mov     [rsp+0F0h+var_C8], r12; unsigned __int8 *
0x18000a8b1  xor     edx, edx
0x18000a8b3  mov     rcx, r13; HKEY
0x18000a8b6  mov     [rsp+0F0h+LengthNeeded], r12; unsigned int *
0x18000a8bb  mov     qword ptr [rbp+37h+var_B0+8], r12
0x18000a8bf  mov     dword ptr [rbp+37h+var_B0], r12d
0x18000a8c3  call    PerfEnumTextValue
0x18000a8c8  mov     ebx, eax
0x18000a8ca  test    eax, eax
0x18000a8cc  jnz     loc_18000AA02
0x18000a8d2  mov     [rsp+0F0h+var_B8], r12; unsigned int *
0x18000a8d7  lea     rax, [rbp+37h+arg_10]
0x18000a8db  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x18000a8e0  lea     r8, [rbp+37h+var_B0]
0x18000a8e4  mov     [rsp+0F0h+var_C8], r12; unsigned __int8 *
0x18000a8e9  mov     edx, esi
0x18000a8eb  mov     rcx, r13; HKEY
0x18000a8ee  mov     [rsp+0F0h+LengthNeeded], r12; unsigned int *
0x18000a8f3  call    PerfEnumTextValue
0x18000a8f8  mov     ebx, eax
0x18000a8fa  test    eax, eax
0x18000a8fc  jnz     loc_18000AA02
0x18000a902  mov     eax, [rbp+37h+arg_0]
0x18000a905  cmp     [rbp+37h+arg_10], eax
0x18000a908  jbe     short loc_18000A910
0x18000a90a  mov     eax, [rbp+37h+arg_10]
0x18000a90d  mov     [rbp+37h+arg_0], eax
0x18000a910  mov     [rdi], eax
0x18000a912  mov     r13d, 2
0x18000a918  lea     rdx, ?PerflibKey@@3QBGB; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x18000a91f  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x18000a923  call    cs:__imp_RtlInitUnicodeString
0x18000a929  lea     rax, [rbp+37h+DestinationString]
0x18000a92d  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x18000a934  xorps   xmm0, xmm0
0x18000a937  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x18000a93b  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18000a93f  mov     [rbp+37h+ObjectAttributes.RootDirectory], r12
0x18000a943  mov     edx, 3000000h; DesiredAccess
0x18000a948  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x18000a94f  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18000a953  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a958  call    cs:__imp_NtOpenKey
0x18000a95e  test    eax, eax
0x18000a960  jns     loc_18000AA41
0x18000a966  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x18000a96a  mov     edx, 2000000h; DesiredAccess
0x18000a96f  lea     rcx, [rbp+37h+KeyHandle]; KeyHandle
0x18000a973  call    cs:__imp_NtOpenKey
0x18000a979  mov     ebx, eax
0x18000a97b  mov     esi, r12d
0x18000a97e  test    eax, eax
0x18000a980  jns     loc_18000AA41
0x18000a986  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a98d  test    [rcx+1Ch], r13b
0x18000a991  jz      short loc_18000A9DC
0x18000a993  cmp     [rcx+19h], r13b
0x18000a997  jb      short loc_18000A9B8
0x18000a999  mov     rcx, [rcx+10h]
0x18000a99d  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000a9a4  mov     edx, 2Eh ; '.'
0x18000a9a9  mov     r9d, eax
0x18000a9ac  call    WPP_SF_d
0x18000a9b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9b8  test    [rcx+1Ch], r13b
0x18000a9bc  jz      short loc_18000A9DC
0x18000a9be  cmp     [rcx+19h], r13b
0x18000a9c2  jb      short loc_18000A9DC
0x18000a9c4  mov     rcx, [rcx+10h]
0x18000a9c8  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000a9cf  mov     edx, 2Fh ; '/'
0x18000a9d4  mov     r9d, ebx
0x18000a9d7  call    WPP_SF_d
0x18000a9dc  mov     ecx, ebx; int
0x18000a9de  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x18000a9e3  mov     ebx, eax
0x18000a9e5  mov     eax, ebx
0x18000a9e7  mov     rbx, [rsp+0F0h+arg_18]
0x18000a9ef  add     rsp, 0C0h
0x18000a9f6  pop     r15
0x18000a9f8  pop     r14
0x18000a9fa  pop     r13
0x18000a9fc  pop     r12
0x18000a9fe  pop     rdi
0x18000a9ff  pop     rsi
0x18000aa00  pop     rbp
0x18000aa01  retn
0x18000aa02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa09  mov     r13d, 2
0x18000aa0f  test    [rcx+1Ch], r13b
0x18000aa13  jz      short loc_18000AA32
0x18000aa15  cmp     [rcx+19h], r13b
0x18000aa19  jb      short loc_18000AA32
0x18000aa1b  mov     rcx, [rcx+10h]
0x18000aa1f  lea     edx, [r13+2Bh]
0x18000aa23  mov     r9d, ebx
0x18000aa26  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000aa2d  call    WPP_SF_d
0x18000aa32  mov     [r14], r12d
0x18000aa35  mov     [r15], r12d
0x18000aa38  test    ebx, ebx
0x18000aa3a  jnz     short loc_18000A9E5
0x18000aa3c  jmp     loc_18000A918
0x18000aa41  mov     rdi, [rbp+37h+arg_48]
0x18000aa48  lea     r8, [rbp+37h+SecurityDescriptor]; SecurityDescriptor
0x18000aa4c  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18000aa50  xor     r9d, r9d; Length
0x18000aa53  mov     [rsp+0F0h+LengthNeeded], rdi; LengthNeeded
0x18000aa58  mov     [rdi], r12d
0x18000aa5b  lea     edx, [r9+7]
0x18000aa5f  test    esi, esi
0x18000aa61  jz      short loc_18000AA67
0x18000aa63  lea     edx, [r9+0Fh]; SecurityInformation
0x18000aa67  call    cs:__imp_NtQuerySecurityObject
0x18000aa6d  mov     ebx, eax
0x18000aa6f  cmp     eax, 0C0000023h
0x18000aa74  jz      short loc_18000AA7B
0x18000aa76  mov     [rdi], r12d
0x18000aa79  jmp     short loc_18000AA7E
0x18000aa7b  mov     ebx, r12d
0x18000aa7e  mov     rcx, [rbp+37h+KeyHandle]; Handle
0x18000aa82  call    cs:__imp_NtClose
0x18000aa88  test    ebx, ebx
0x18000aa8a  js      loc_18000A9B1
0x18000aa90  mov     ebx, r12d
0x18000aa93  jmp     loc_18000A9E5
```
