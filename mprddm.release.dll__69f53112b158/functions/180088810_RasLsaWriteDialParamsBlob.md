# RasLsaWriteDialParamsBlob

- ea: `0x180088810`
- end: `0x180088a34`
- name: `RasLsaWriteDialParamsBlob`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180088a3c`

## callees

- `0x180087970`
- `0x18008842c`
- `0x180088810`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800888d3`
- `KERNEL32!LocalFree` at `0x1800889f4`
- `KERNEL32!LocalFree` at `0x1800888d3`
- `KERNEL32!LocalFree` at `0x1800889f4`
- `KERNEL32!GetLastError` at `0x180088878`
- `KERNEL32!GetLastError` at `0x180088878`
- `KERNEL32!LocalAlloc` at `0x180088864`
- `KERNEL32!LocalAlloc` at `0x180088864`
- `ADVAPI32!LsaClose` at `0x180088a04`
- `ADVAPI32!LsaClose` at `0x180088a04`
- `ADVAPI32!LsaStorePrivateData` at `0x180088969`
- `ADVAPI32!LsaStorePrivateData` at `0x1800889bc`
- `ADVAPI32!LsaStorePrivateData` at `0x180088969`
- `ADVAPI32!LsaStorePrivateData` at `0x1800889bc`
- `ADVAPI32!LsaOpenPolicy` at `0x1800888b3`
- `ADVAPI32!LsaOpenPolicy` at `0x1800888b3`
- `ntdll!RtlNtStatusToDosError` at `0x1800888e2`
- `ntdll!RtlNtStatusToDosError` at `0x18008898e`
- `ntdll!RtlNtStatusToDosError` at `0x1800888e2`
- `ntdll!RtlNtStatusToDosError` at `0x18008898e`
- `ntdll!RtlInitUnicodeString` at `0x180088934`
- `ntdll!RtlInitUnicodeString` at `0x1800889a5`
- `ntdll!RtlInitUnicodeString` at `0x180088934`
- `ntdll!RtlInitUnicodeString` at `0x1800889a5`

## pseudocode

```c
ULONG __fastcall RasLsaWriteDialParamsBlob(__int64 a1, __int64 a2, WCHAR *a3, unsigned int a4, int a5)
{
  ULONG v5; // ebx
  unsigned int v8; // edi
  HLOCAL v9; // rsi
  __int64 v11; // r8
  NTSTATUS v12; // r15d
  int v13; // r13d
  __int64 v14; // r9
  unsigned int v15; // r15d
  NTSTATUS v16; // eax
  __int64 v17; // r9
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+B0h] [rbp+30h] BYREF

  v5 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  PolicyHandle = 0;
  v8 = 0;
  DestinationString = 0;
  PrivateData = 0;
  v9 = LocalAlloc(0x40u, 0x80u);
  if ( !v9 )
    return GetLastError();
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v12 )
  {
    memset(v9, 0, 0x80u);
    LocalFree(v9);
    return RtlNtStatusToDosError(v12);
  }
  else
  {
    v13 = a5;
    if ( a3 && !(unsigned int)RasLsaIsPasswordSavingDisabled() && a4 )
    {
      while ( 1 )
      {
        v14 = v8++;
        if ( (unsigned int)FormatKey(v9, 64, v11, v14, v13) )
          break;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v9);
        PrivateData.Buffer = a3;
        v15 = a4;
        if ( a4 > 0xFFFF )
          v15 = 0xFFFF;
        PrivateData.MaximumLength = v15;
        PrivateData.Length = v15;
        v16 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v16 )
        {
          v5 = RtlNtStatusToDosError(v16);
          break;
        }
        a3 = (WCHAR *)((char *)a3 + v15);
        a4 -= v15;
        if ( !a4 )
          goto LABEL_16;
      }
    }
    else
    {
      do
      {
LABEL_16:
        v17 = v8++;
        if ( (unsigned int)FormatKey(v9, 64, v11, v17, v13) )
          break;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v9);
      }
      while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, 0) );
    }
    memset(v9, 0, 0x80u);
    LocalFree(v9);
    LsaClose(PolicyHandle);
    return v5;
  }
}

```

## disassembly

```asm
0x180088810  mov     rax, rsp
0x180088813  mov     [rax+10h], rbx
0x180088817  mov     [rax+18h], rsi
0x18008881b  mov     [rax+20h], rdi
0x18008881f  mov     [rax+8], rcx
0x180088823  push    rbp
0x180088824  push    r12
0x180088826  push    r13
0x180088828  push    r14
0x18008882a  push    r15
0x18008882c  mov     rbp, rsp
0x18008882f  sub     rsp, 80h
0x180088836  xor     ebx, ebx
0x180088838  xorps   xmm0, xmm0
0x18008883b  xorps   xmm1, xmm1
0x18008883e  mov     dword ptr [rbp+ObjectAttributes+4], ebx
0x180088841  mov     r13d, 80h
0x180088847  mov     dword ptr [rbp+ObjectAttributes+1Ch], ebx
0x18008884a  mov     edx, r13d; uBytes
0x18008884d  mov     [rbp+PolicyHandle], rbx
0x180088851  lea     ecx, [rbx+40h]; uFlags
0x180088854  mov     r14d, r9d
0x180088857  mov     r12, r8
0x18008885a  mov     edi, ebx
0x18008885c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180088860  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x180088864  call    cs:__imp_LocalAlloc
0x18008886b  nop     dword ptr [rax+rax+00h]
0x180088870  mov     rsi, rax
0x180088873  test    rax, rax
0x180088876  jnz     short loc_180088889
0x180088878  call    cs:__imp_GetLastError
0x18008887f  nop     dword ptr [rax+rax+00h]
0x180088884  jmp     loc_180088A12
0x180088889  xorps   xmm0, xmm0
0x18008888c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180088893  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180088897  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18008889b  mov     r8d, 207F8h; DesiredAccess
0x1800888a1  mov     [rbp+ObjectAttributes.Attributes], ebx
0x1800888a4  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800888a8  mov     [rbp+ObjectAttributes.ObjectName], rbx
0x1800888ac  xor     ecx, ecx; SystemName
0x1800888ae  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800888b3  call    cs:__imp_LsaOpenPolicy
0x1800888ba  nop     dword ptr [rax+rax+00h]
0x1800888bf  mov     r15d, eax
0x1800888c2  test    eax, eax
0x1800888c4  jz      short loc_1800888F3
0x1800888c6  xor     eax, eax
0x1800888c8  mov     rdi, rsi
0x1800888cb  mov     rcx, r13
0x1800888ce  rep stosb
0x1800888d0  mov     rcx, rsi; hMem
0x1800888d3  call    cs:__imp_LocalFree
0x1800888da  nop     dword ptr [rax+rax+00h]
0x1800888df  mov     ecx, r15d; Status
0x1800888e2  call    cs:__imp_RtlNtStatusToDosError
0x1800888e9  nop     dword ptr [rax+rax+00h]
0x1800888ee  jmp     loc_180088A12
0x1800888f3  mov     r13d, [rbp+arg_20]
0x1800888f7  test    r12, r12
0x1800888fa  jz      loc_180088984
0x180088900  call    RasLsaIsPasswordSavingDisabled
0x180088905  test    eax, eax
0x180088907  jnz     short loc_180088984
0x180088909  test    r14d, r14d
0x18008890c  jz      short loc_180088984
0x18008890e  mov     r9d, edi
0x180088911  mov     [rsp+80h+var_60], r13d
0x180088916  mov     edx, 40h ; '@'
0x18008891b  mov     rcx, rsi
0x18008891e  inc     edi
0x180088920  call    FormatKey
0x180088925  test    eax, eax
0x180088927  jnz     loc_1800889E5
0x18008892d  mov     rdx, rsi; SourceString
0x180088930  lea     rcx, [rbp+DestinationString]; DestinationString
0x180088934  call    cs:__imp_RtlInitUnicodeString
0x18008893b  nop     dword ptr [rax+rax+00h]
0x180088940  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180088944  lea     r8, [rbp+PrivateData]; PrivateData
0x180088948  mov     eax, 0FFFFh
0x18008894d  mov     [rbp+PrivateData.Buffer], r12
0x180088951  cmp     r14d, eax
0x180088954  lea     rdx, [rbp+DestinationString]; KeyName
0x180088958  mov     r15d, r14d
0x18008895b  cmova   r15d, eax
0x18008895f  mov     [rbp+PrivateData.MaximumLength], r15w
0x180088964  mov     [rbp+PrivateData.Length], r15w
0x180088969  call    cs:__imp_LsaStorePrivateData
0x180088970  nop     dword ptr [rax+rax+00h]
0x180088975  test    eax, eax
0x180088977  jnz     short loc_18008898C
0x180088979  mov     eax, r15d
0x18008897c  add     r12, rax
0x18008897f  sub     r14d, r15d
0x180088982  jnz     short loc_18008890E
0x180088984  mov     r14d, 40h ; '@'
0x18008898a  jmp     short loc_1800889CC
0x18008898c  mov     ecx, eax; Status
0x18008898e  call    cs:__imp_RtlNtStatusToDosError
0x180088995  nop     dword ptr [rax+rax+00h]
0x18008899a  mov     ebx, eax
0x18008899c  jmp     short loc_1800889E5
0x18008899e  mov     rdx, rsi; SourceString
0x1800889a1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800889a5  call    cs:__imp_RtlInitUnicodeString
0x1800889ac  nop     dword ptr [rax+rax+00h]
0x1800889b1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800889b5  lea     rdx, [rbp+DestinationString]; KeyName
0x1800889b9  xor     r8d, r8d; PrivateData
0x1800889bc  call    cs:__imp_LsaStorePrivateData
0x1800889c3  nop     dword ptr [rax+rax+00h]
0x1800889c8  test    eax, eax
0x1800889ca  jnz     short loc_1800889E5
0x1800889cc  mov     r9d, edi
0x1800889cf  mov     [rsp+80h+var_60], r13d
0x1800889d4  mov     edx, r14d
0x1800889d7  mov     rcx, rsi
0x1800889da  inc     edi
0x1800889dc  call    FormatKey
0x1800889e1  test    eax, eax
0x1800889e3  jz      short loc_18008899E
0x1800889e5  xor     eax, eax
0x1800889e7  mov     rdi, rsi
0x1800889ea  mov     ecx, 80h
0x1800889ef  rep stosb
0x1800889f1  mov     rcx, rsi; hMem
0x1800889f4  call    cs:__imp_LocalFree
0x1800889fb  nop     dword ptr [rax+rax+00h]
0x180088a00  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180088a04  call    cs:__imp_LsaClose
0x180088a0b  nop     dword ptr [rax+rax+00h]
0x180088a10  mov     eax, ebx
0x180088a12  lea     r11, [rsp+80h+var_s0]
0x180088a1a  mov     rbx, [r11+38h]
0x180088a1e  mov     rsi, [r11+40h]
0x180088a22  mov     rdi, [r11+48h]
0x180088a26  mov     rsp, r11
0x180088a29  pop     r15
0x180088a2b  pop     r14
0x180088a2d  pop     r13
0x180088a2f  pop     r12
0x180088a31  pop     rbp
0x180088a32  retn
```
