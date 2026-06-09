# SubstituteParamSet(ushort * *,ushort const *,_DIAG_PARAMSET *)

- ea: `0x140044b20`
- end: `0x140044e63`
- name: `?SubstituteParamSet@@YAJPEAPEAGPEBGPEAU_DIAG_PARAMSET@@@Z`
- size: `835`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *, struct _DIAG_PARAMSET *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140044700`

## callees

- `0x140020420`
- `0x140020b00`
- `0x140022070`
- `0x140044b20`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x140044d79`
- `KERNEL32!HeapAlloc` at `0x140044d79`
- `KERNEL32!HeapFree` at `0x140044e3c`
- `KERNEL32!HeapFree` at `0x140044e3c`
- `KERNEL32!GetProcessHeap` at `0x140044d65`
- `KERNEL32!GetProcessHeap` at `0x140044e28`
- `KERNEL32!GetProcessHeap` at `0x140044d65`
- `KERNEL32!GetProcessHeap` at `0x140044e28`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140044d31`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140044dc7`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140044d31`
- `ntdll!RtlExpandEnvironmentStrings` at `0x140044dc7`
- `ntdll!RtlDestroyEnvironment` at `0x140044e17`
- `ntdll!RtlDestroyEnvironment` at `0x140044e17`
- `ntdll!RtlInitUnicodeStringEx` at `0x140044c17`
- `ntdll!RtlInitUnicodeStringEx` at `0x140044c5a`
- `ntdll!RtlInitUnicodeStringEx` at `0x140044c17`
- `ntdll!RtlInitUnicodeStringEx` at `0x140044c5a`
- `ntdll!RtlCreateEnvironment` at `0x140044ba4`
- `ntdll!RtlCreateEnvironment` at `0x140044ba4`
- `ntdll!RtlNtStatusToDosError` at `0x140044bba`
- `ntdll!RtlNtStatusToDosError` at `0x140044c2d`
- `ntdll!RtlNtStatusToDosError` at `0x140044c70`
- `ntdll!RtlNtStatusToDosError` at `0x140044cae`
- `ntdll!RtlNtStatusToDosError` at `0x140044ddd`
- `ntdll!RtlNtStatusToDosError` at `0x140044bba`
- `ntdll!RtlNtStatusToDosError` at `0x140044c2d`
- `ntdll!RtlNtStatusToDosError` at `0x140044c70`
- `ntdll!RtlNtStatusToDosError` at `0x140044cae`
- `ntdll!RtlNtStatusToDosError` at `0x140044ddd`
- `ntdll!RtlSetEnvironmentVariable` at `0x140044c98`
- `ntdll!RtlSetEnvironmentVariable` at `0x140044c98`

## pseudocode

```c
__int64 __fastcall SubstituteParamSet(unsigned __int16 **a1, const unsigned __int16 *a2, struct _DIAG_PARAMSET *a3)
{
  unsigned __int16 *v5; // r14
  signed int v6; // eax
  unsigned int v7; // esi
  int v8; // r9d
  int v9; // eax
  bool v10; // sf
  unsigned int i; // ebx
  int inited; // eax
  signed int v13; // eax
  bool v14; // sf
  int v15; // eax
  bool v16; // sf
  int v17; // eax
  bool v18; // sf
  NTSTATUS v19; // eax
  SIZE_T v20; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // r8
  bool v24; // sf
  HANDLE v25; // rax
  int v27; // [rsp+20h] [rbp-40h]
  unsigned __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING Value; // [rsp+38h] [rbp-28h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PWSTR Environment; // [rsp+B0h] [rbp+50h] BYREF
  unsigned __int64 v33; // [rsp+B8h] [rbp+58h] BYREF

  v5 = 0;
  Environment = 0;
  DestinationString = 0;
  v28 = 0;
  Value = 0;
  v33 = 0;
  if ( !*(_QWORD *)a3 )
  {
    v6 = DwzStrCpy(a1, a2);
    v7 = v6;
    if ( v6 >= 0 )
      goto LABEL_56;
    v8 = 187;
LABEL_4:
    v27 = v6;
    goto LABEL_5;
  }
  v7 = 0;
  v9 = RtlCreateEnvironment(0, &Environment);
  if ( v9 >= 0 )
  {
    v6 = 0;
LABEL_10:
    v10 = v6 < 0;
    goto LABEL_11;
  }
  v6 = RtlNtStatusToDosError(v9);
  v10 = v6 < 0;
  if ( v6 > 0 )
  {
    v6 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_10;
  }
LABEL_11:
  if ( v10 )
  {
    v8 = 193;
    goto LABEL_4;
  }
  if ( !Environment )
  {
    v7 = -2147418113;
    v8 = 194;
    v27 = -2147418113;
    goto LABEL_5;
  }
  for ( i = 0; i < *((_DWORD *)a3 + 2); ++i )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, *(PCWSTR *)(*(_QWORD *)a3 + 16LL * i));
    if ( inited < 0 )
    {
      v13 = RtlNtStatusToDosError(inited);
      v14 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_22;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v14 = v13 < 0;
LABEL_22:
    if ( v14 )
    {
      v8 = 203;
      goto LABEL_39;
    }
    v15 = RtlInitUnicodeStringEx(&Value, *(PCWSTR *)(*(_QWORD *)a3 + 16LL * i + 8));
    if ( v15 < 0 )
    {
      v13 = RtlNtStatusToDosError(v15);
      v16 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_28;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v16 = v13 < 0;
LABEL_28:
    if ( v16 )
    {
      v8 = 208;
      goto LABEL_39;
    }
    v17 = RtlSetEnvironmentVariable(&Environment, &DestinationString, &Value);
    if ( v17 < 0 )
    {
      v13 = RtlNtStatusToDosError(v17);
      v18 = v13 < 0;
      if ( v13 <= 0 )
        goto LABEL_34;
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v18 = v13 < 0;
LABEL_34:
    if ( v18 )
    {
      v8 = 211;
LABEL_39:
      v27 = v13;
      goto LABEL_5;
    }
  }
  v13 = StringCchLengthW(a2, 0x100000u, &v28);
  v7 = v13;
  if ( v13 < 0 )
  {
    v8 = 215;
    goto LABEL_39;
  }
  v19 = RtlExpandEnvironmentStrings(Environment, a2, v28, 0, 0, &v33);
  if ( v19 != -1073741789 )
  {
LABEL_48:
    if ( v19 < 0 )
    {
      v13 = RtlNtStatusToDosError(v19);
      v24 = v13 < 0;
      if ( v13 <= 0 )
      {
LABEL_53:
        if ( v24 )
        {
          v8 = 246;
          goto LABEL_39;
        }
        *a1 = v5;
        v5 = 0;
        goto LABEL_56;
      }
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v13 = 0;
    }
    v24 = v13 < 0;
    goto LABEL_53;
  }
  if ( v33 > 0x100000 )
  {
    v7 = -2147024785;
    v8 = 231;
    v27 = -2147024785;
    goto LABEL_5;
  }
  v20 = 2 * v33;
  ProcessHeap = GetProcessHeap();
  v22 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, v20);
  v5 = v22;
  if ( v22 )
  {
    v23 = v28;
    *v22 = 0;
    v19 = RtlExpandEnvironmentStrings(Environment, a2, v23, v22, v33, 0);
    goto LABEL_48;
  }
  v7 = -2147024882;
  v8 = 234;
  v27 = -2147024882;
LABEL_5:
  SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SubstituteParamSet", v8, v27);
LABEL_56:
  if ( Environment )
    RtlDestroyEnvironment(Environment);
  if ( v5 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v5);
  }
  return v7;
}

```

## disassembly

```asm
0x140044b20  mov     [rsp-38h+arg_8], rbx
0x140044b25  mov     [rsp-38h+arg_0], rcx
0x140044b2a  push    rbp
0x140044b2b  push    rsi
0x140044b2c  push    rdi
0x140044b2d  push    r12
0x140044b2f  push    r13
0x140044b31  push    r14
0x140044b33  push    r15
0x140044b35  mov     rbp, rsp
0x140044b38  sub     rsp, 60h
0x140044b3c  xor     eax, eax
0x140044b3e  xorps   xmm0, xmm0
0x140044b41  xorps   xmm1, xmm1
0x140044b44  mov     r12, r8
0x140044b47  mov     r13, rdx
0x140044b4a  mov     r14d, eax
0x140044b4d  mov     [rbp+Environment], rax
0x140044b51  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140044b55  mov     [rbp+var_30], rax
0x140044b59  movups  xmmword ptr [rbp+Value.Length], xmm1
0x140044b5d  mov     [rbp+arg_18], rax
0x140044b61  cmp     [r8], rax
0x140044b64  jnz     short loc_140044B9C
0x140044b66  call    ?DwzStrCpy@@YAJPEAPEAGPEBG@Z; DwzStrCpy(ushort * *,ushort const *)
0x140044b6b  mov     esi, eax
0x140044b6d  test    eax, eax
0x140044b6f  jns     loc_140044E0E
0x140044b75  mov     r9d, 0BBh
0x140044b7b  mov     dword ptr [rsp+60h+var_40], eax
0x140044b7f  mov     ecx, 1; Level
0x140044b84  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140044b8b  lea     r8, aSubstitutepara; "SubstituteParamSet"
0x140044b92  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140044b97  jmp     loc_140044E0E
0x140044b9c  lea     rdx, [rbp+Environment]; Environment
0x140044ba0  xor     ecx, ecx; Inherit
0x140044ba2  xor     esi, esi
0x140044ba4  call    cs:__imp_RtlCreateEnvironment
0x140044bab  nop     dword ptr [rax+rax+00h]
0x140044bb0  test    eax, eax
0x140044bb2  js      short loc_140044BB8
0x140044bb4  xor     eax, eax
0x140044bb6  jmp     short loc_140044BD2
0x140044bb8  mov     ecx, eax; Status
0x140044bba  call    cs:__imp_RtlNtStatusToDosError
0x140044bc1  nop     dword ptr [rax+rax+00h]
0x140044bc6  test    eax, eax
0x140044bc8  jle     short loc_140044BD4
0x140044bca  movzx   eax, ax
0x140044bcd  or      eax, 80070000h
0x140044bd2  test    eax, eax
0x140044bd4  jns     short loc_140044BDE
0x140044bd6  mov     r9d, 0C1h
0x140044bdc  jmp     short loc_140044B7B
0x140044bde  cmp     [rbp+Environment], rsi
0x140044be2  jnz     short loc_140044BF5
0x140044be4  mov     esi, 8000FFFFh
0x140044be9  mov     r9d, 0C2h
0x140044bef  mov     dword ptr [rsp+60h+var_40], esi
0x140044bf3  jmp     short loc_140044B7F
0x140044bf5  xor     ebx, ebx
0x140044bf7  lea     edi, [rbx+1]
0x140044bfa  cmp     ebx, [r12+8]
0x140044bff  jnb     loc_140044CF2
0x140044c05  mov     rdx, [r12]
0x140044c09  lea     rcx, [rbp+DestinationString]; DestinationString
0x140044c0d  mov     r15d, ebx
0x140044c10  add     r15, r15
0x140044c13  mov     rdx, [rdx+r15*8]; SourceString
0x140044c17  call    cs:__imp_RtlInitUnicodeStringEx
0x140044c1e  nop     dword ptr [rax+rax+00h]
0x140044c23  test    eax, eax
0x140044c25  js      short loc_140044C2B
0x140044c27  xor     eax, eax
0x140044c29  jmp     short loc_140044C45
0x140044c2b  mov     ecx, eax; Status
0x140044c2d  call    cs:__imp_RtlNtStatusToDosError
0x140044c34  nop     dword ptr [rax+rax+00h]
0x140044c39  test    eax, eax
0x140044c3b  jle     short loc_140044C47
0x140044c3d  movzx   eax, ax
0x140044c40  or      eax, 80070000h
0x140044c45  test    eax, eax
0x140044c47  js      loc_140044CE1
0x140044c4d  mov     rdx, [r12]
0x140044c51  lea     rcx, [rbp+Value]; DestinationString
0x140044c55  mov     rdx, [rdx+r15*8+8]; SourceString
0x140044c5a  call    cs:__imp_RtlInitUnicodeStringEx
0x140044c61  nop     dword ptr [rax+rax+00h]
0x140044c66  test    eax, eax
0x140044c68  js      short loc_140044C6E
0x140044c6a  xor     eax, eax
0x140044c6c  jmp     short loc_140044C88
0x140044c6e  mov     ecx, eax; Status
0x140044c70  call    cs:__imp_RtlNtStatusToDosError
0x140044c77  nop     dword ptr [rax+rax+00h]
0x140044c7c  test    eax, eax
0x140044c7e  jle     short loc_140044C8A
0x140044c80  movzx   eax, ax
0x140044c83  or      eax, 80070000h
0x140044c88  test    eax, eax
0x140044c8a  js      short loc_140044CD9
0x140044c8c  lea     r8, [rbp+Value]; Value
0x140044c90  lea     rdx, [rbp+DestinationString]; Name
0x140044c94  lea     rcx, [rbp+Environment]; Environment
0x140044c98  call    cs:__imp_RtlSetEnvironmentVariable
0x140044c9f  nop     dword ptr [rax+rax+00h]
0x140044ca4  test    eax, eax
0x140044ca6  js      short loc_140044CAC
0x140044ca8  xor     eax, eax
0x140044caa  jmp     short loc_140044CC6
0x140044cac  mov     ecx, eax; Status
0x140044cae  call    cs:__imp_RtlNtStatusToDosError
0x140044cb5  nop     dword ptr [rax+rax+00h]
0x140044cba  test    eax, eax
0x140044cbc  jle     short loc_140044CC8
0x140044cbe  movzx   eax, ax
0x140044cc1  or      eax, 80070000h
0x140044cc6  test    eax, eax
0x140044cc8  js      short loc_140044CD1
0x140044cca  add     ebx, edi
0x140044ccc  jmp     loc_140044BFA
0x140044cd1  mov     r9d, 0D3h
0x140044cd7  jmp     short loc_140044CE7
0x140044cd9  mov     r9d, 0D0h
0x140044cdf  jmp     short loc_140044CE7
0x140044ce1  mov     r9d, 0CBh
0x140044ce7  mov     dword ptr [rsp+60h+var_40], eax
0x140044ceb  mov     ecx, edi
0x140044ced  jmp     loc_140044B84
0x140044cf2  mov     r15d, 100000h
0x140044cf8  lea     r8, [rbp+var_30]; unsigned __int64 *
0x140044cfc  mov     edx, r15d; unsigned __int64
0x140044cff  mov     rcx, r13; unsigned __int16 *
0x140044d02  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140044d07  mov     esi, eax
0x140044d09  test    eax, eax
0x140044d0b  jns     short loc_140044D15
0x140044d0d  mov     r9d, 0D7h
0x140044d13  jmp     short loc_140044CE7
0x140044d15  mov     r8, [rbp+var_30]
0x140044d19  lea     rax, [rbp+arg_18]
0x140044d1d  mov     rcx, [rbp+Environment]
0x140044d21  xor     r9d, r9d
0x140044d24  mov     [rsp+60h+var_38], rax
0x140044d29  mov     rdx, r13
0x140044d2c  mov     [rsp+60h+var_40], r14
0x140044d31  call    cs:__imp_RtlExpandEnvironmentStrings
0x140044d38  nop     dword ptr [rax+rax+00h]
0x140044d3d  cmp     eax, 0C0000023h
0x140044d42  jnz     loc_140044DD3
0x140044d48  mov     rbx, [rbp+arg_18]
0x140044d4c  cmp     rbx, r15
0x140044d4f  jbe     short loc_140044D62
0x140044d51  mov     esi, 8007006Fh
0x140044d56  mov     r9d, 0E7h
0x140044d5c  mov     dword ptr [rsp+60h+var_40], esi
0x140044d60  jmp     short loc_140044CEB
0x140044d62  add     rbx, rbx
0x140044d65  call    cs:__imp_GetProcessHeap
0x140044d6c  nop     dword ptr [rax+rax+00h]
0x140044d71  mov     r8, rbx; dwBytes
0x140044d74  xor     edx, edx; dwFlags
0x140044d76  mov     rcx, rax; hHeap
0x140044d79  call    cs:__imp_HeapAlloc
0x140044d80  nop     dword ptr [rax+rax+00h]
0x140044d85  mov     r14, rax
0x140044d88  test    rax, rax
0x140044d8b  jnz     short loc_140044DA1
0x140044d8d  mov     esi, 8007000Eh
0x140044d92  mov     r9d, 0EAh
0x140044d98  mov     dword ptr [rsp+60h+var_40], esi
0x140044d9c  jmp     loc_140044CEB
0x140044da1  mov     r8, [rbp+var_30]
0x140044da5  xor     eax, eax
0x140044da7  mov     [r14], ax
0x140044dab  mov     r9, r14
0x140044dae  mov     rax, [rbp+arg_18]
0x140044db2  mov     rdx, r13
0x140044db5  mov     rcx, [rbp+Environment]
0x140044db9  mov     [rsp+60h+var_38], 0
0x140044dc2  mov     [rsp+60h+var_40], rax
0x140044dc7  call    cs:__imp_RtlExpandEnvironmentStrings
0x140044dce  nop     dword ptr [rax+rax+00h]
0x140044dd3  test    eax, eax
0x140044dd5  js      short loc_140044DDB
0x140044dd7  xor     eax, eax
0x140044dd9  jmp     short loc_140044DF5
0x140044ddb  mov     ecx, eax; Status
0x140044ddd  call    cs:__imp_RtlNtStatusToDosError
0x140044de4  nop     dword ptr [rax+rax+00h]
0x140044de9  test    eax, eax
0x140044deb  jle     short loc_140044DF7
0x140044ded  movzx   eax, ax
0x140044df0  or      eax, 80070000h
0x140044df5  test    eax, eax
0x140044df7  jns     short loc_140044E04
0x140044df9  mov     r9d, 0F6h
0x140044dff  jmp     loc_140044CE7
0x140044e04  mov     rax, [rbp+arg_0]
0x140044e08  mov     [rax], r14
0x140044e0b  xor     r14d, r14d
0x140044e0e  mov     rcx, [rbp+Environment]; Environment
0x140044e12  test    rcx, rcx
0x140044e15  jz      short loc_140044E23
0x140044e17  call    cs:__imp_RtlDestroyEnvironment
0x140044e1e  nop     dword ptr [rax+rax+00h]
0x140044e23  test    r14, r14
0x140044e26  jz      short loc_140044E48
0x140044e28  call    cs:__imp_GetProcessHeap
0x140044e2f  nop     dword ptr [rax+rax+00h]
0x140044e34  mov     r8, r14; lpMem
0x140044e37  xor     edx, edx; dwFlags
0x140044e39  mov     rcx, rax; hHeap
0x140044e3c  call    cs:__imp_HeapFree
0x140044e43  nop     dword ptr [rax+rax+00h]
0x140044e48  mov     rbx, [rsp+60h+arg_8]
0x140044e50  mov     eax, esi
0x140044e52  add     rsp, 60h
0x140044e56  pop     r15
0x140044e58  pop     r14
0x140044e5a  pop     r13
0x140044e5c  pop     r12
0x140044e5e  pop     rdi
0x140044e5f  pop     rsi
0x140044e60  pop     rbp
0x140044e61  retn
```
