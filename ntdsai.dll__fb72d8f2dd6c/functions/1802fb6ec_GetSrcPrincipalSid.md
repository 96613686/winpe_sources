# GetSrcPrincipalSid

- ea: `0x1802fb6ec`
- end: `0x1802fb8ec`
- name: `GetSrcPrincipalSid`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1802fb900`

## callees

- `0x180161d38`
- `0x1802fb6ec`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1802fb74e`
- `ntdll!RtlInitUnicodeString` at `0x1802fb74e`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb779`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb87b`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb891`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb8bf`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb779`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb87b`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb891`
- `ntdll!RtlNtStatusToDosError` at `0x1802fb8bf`
- `SAMLIB!SamCloseHandle` at `0x1802fb7ed`
- `SAMLIB!SamCloseHandle` at `0x1802fb887`
- `SAMLIB!SamCloseHandle` at `0x1802fb7ed`
- `SAMLIB!SamCloseHandle` at `0x1802fb887`
- `SAMLIB!SamOpenAlias` at `0x1802fb7db`
- `SAMLIB!SamOpenAlias` at `0x1802fb7db`
- `SAMLIB!SamOpenGroup` at `0x1802fb80b`
- `SAMLIB!SamOpenGroup` at `0x1802fb80b`
- `SAMLIB!SamLookupNamesInDomain` at `0x1802fb76d`
- `SAMLIB!SamLookupNamesInDomain` at `0x1802fb76d`
- `SAMLIB!SamQueryInformationUser` at `0x1802fb83d`
- `SAMLIB!SamQueryInformationUser` at `0x1802fb83d`
- `SAMLIB!SamFreeMemory` at `0x1802fb861`
- `SAMLIB!SamFreeMemory` at `0x1802fb8cb`
- `SAMLIB!SamFreeMemory` at `0x1802fb8d5`
- `SAMLIB!SamFreeMemory` at `0x1802fb861`
- `SAMLIB!SamFreeMemory` at `0x1802fb8cb`
- `SAMLIB!SamFreeMemory` at `0x1802fb8d5`
- `SAMLIB!SamOpenUser` at `0x1802fb826`
- `SAMLIB!SamOpenUser` at `0x1802fb826`
- `SAMSRV!SampAccountControlToFlags` at `0x1802fb84d`
- `SAMSRV!SampAccountControlToFlags` at `0x1802fb84d`

## pseudocode

```c
__int64 __fastcall GetSrcPrincipalSid(__int64 a1, const WCHAR *a2, void *a3, _OWORD *a4, _DWORD *a5, int *a6)
{
  NTSTATUS v9; // eax
  ULONG v10; // ebx
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  __int16 v13; // ax
  unsigned int *v14; // rcx
  int v15; // ebx
  NTSTATUS v16; // eax
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  ULONG *v19; // [rsp+38h] [rbp-28h] BYREF
  _DWORD *v20; // [rsp+40h] [rbp-20h] BYREF
  unsigned int *v21; // [rsp+48h] [rbp-18h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF

  *a4 = 0;
  *(_OWORD *)((char *)a4 + 12) = 0;
  *a5 = 8;
  *a6 = 0;
  DestinationString = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v21 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  v9 = SamLookupNamesInDomain(a1, 1, &DestinationString, &v19, &v20);
  if ( v9 >= 0 )
  {
    if ( !v20 )
      return 8538;
    v10 = 0;
    if ( *v20 == 1 )
    {
      v11 = SamOpenUser(a1, 0x2000000, *v19, &v18);
      if ( v11 >= 0 )
      {
        v12 = SamQueryInformationUser(v18, 16, &v21);
        if ( v12 < 0 )
        {
          v10 = RtlNtStatusToDosError(v12);
        }
        else
        {
          v13 = SampAccountControlToFlags(*v21);
          v14 = v21;
          v15 = v13 & 0x3B00;
          *a6 = v15;
          SamFreeMemory(v14);
          v10 = (v15 & 0xFFFFCDFF) != 0 ? 0x2035 : 0;
        }
        SamCloseHandle(v18);
LABEL_19:
        if ( v10 )
          goto LABEL_23;
LABEL_20:
        v16 = SampBuildNT4FullSid(a3, *v19, a4);
        if ( v16 < 0 )
          v10 = RtlNtStatusToDosError(v16);
        else
          *a5 = *v20;
        goto LABEL_23;
      }
    }
    else
    {
      if ( *v20 == 2 )
      {
        v11 = SamOpenGroup(a1, 0x2000000, *v19, &v18);
      }
      else
      {
        if ( *v20 != 4 )
        {
          v10 = 8538;
LABEL_23:
          SamFreeMemory(v19);
          SamFreeMemory(v20);
          return v10;
        }
        v11 = SamOpenAlias(a1, 0x2000000, *v19, &v18);
      }
      if ( v11 >= 0 )
      {
        SamCloseHandle(v18);
        goto LABEL_20;
      }
    }
    v10 = RtlNtStatusToDosError(v11);
    goto LABEL_19;
  }
  return RtlNtStatusToDosError(v9);
}

```

## disassembly

```asm
0x1802fb6ec  push    rbp
0x1802fb6ee  push    rbx
0x1802fb6ef  push    rsi
0x1802fb6f0  push    rdi
0x1802fb6f1  push    r12
0x1802fb6f3  push    r14
0x1802fb6f5  push    r15
0x1802fb6f7  mov     rbp, rsp
0x1802fb6fa  sub     rsp, 60h
0x1802fb6fe  mov     r14, [rbp+arg_20]
0x1802fb702  xorps   xmm0, xmm0
0x1802fb705  mov     rsi, [rbp+arg_28]
0x1802fb709  mov     rdi, rcx
0x1802fb70c  movups  xmmword ptr [r9], xmm0
0x1802fb710  xor     eax, eax
0x1802fb712  lea     rcx, [rbp+DestinationString]; DestinationString
0x1802fb716  movups  xmmword ptr [r9+0Ch], xmm0
0x1802fb71b  mov     dword ptr [r14], 8
0x1802fb722  mov     r15, r9
0x1802fb725  mov     [rsi], eax
0x1802fb727  mov     r12, r8
0x1802fb72a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1802fb72e  mov     [rbp+var_20], 0
0x1802fb736  mov     [rbp+var_28], 0
0x1802fb73e  mov     [rbp+var_30], 0
0x1802fb746  mov     [rbp+var_18], 0
0x1802fb74e  call    cs:__imp_RtlInitUnicodeString
0x1802fb754  lea     rax, [rbp+var_20]
0x1802fb758  mov     edx, 1
0x1802fb75d  lea     r9, [rbp+var_28]
0x1802fb761  mov     [rsp+60h+var_40], rax
0x1802fb766  lea     r8, [rbp+DestinationString]
0x1802fb76a  mov     rcx, rdi
0x1802fb76d  call    cs:__imp_SamLookupNamesInDomain
0x1802fb773  test    eax, eax
0x1802fb775  jns     short loc_1802FB786
0x1802fb777  mov     ecx, eax; Status
0x1802fb779  call    cs:__imp_RtlNtStatusToDosError
0x1802fb77f  mov     ebx, eax
0x1802fb781  jmp     loc_1802FB8DB
0x1802fb786  mov     rcx, [rbp+var_20]
0x1802fb78a  test    rcx, rcx
0x1802fb78d  jnz     short loc_1802FB799
0x1802fb78f  mov     ebx, 215Ah
0x1802fb794  jmp     loc_1802FB8DB
0x1802fb799  mov     ecx, [rcx]
0x1802fb79b  xor     ebx, ebx
0x1802fb79d  sub     ecx, 1
0x1802fb7a0  jz      short loc_1802FB813
0x1802fb7a2  sub     ecx, 1
0x1802fb7a5  jz      short loc_1802FB7F8
0x1802fb7a7  sub     ecx, 1
0x1802fb7aa  jz      short loc_1802FB7BE
0x1802fb7ac  sub     ecx, 1
0x1802fb7af  jz      short loc_1802FB7C8
0x1802fb7b1  sub     ecx, 1
0x1802fb7b4  jz      short loc_1802FB7BE
0x1802fb7b6  sub     ecx, 1
0x1802fb7b9  jz      short loc_1802FB7BE
0x1802fb7bb  sub     ecx, 1
0x1802fb7be  mov     ebx, 215Ah
0x1802fb7c3  jmp     loc_1802FB8C7
0x1802fb7c8  mov     r8, [rbp+var_28]
0x1802fb7cc  lea     r9, [rbp+var_30]
0x1802fb7d0  mov     edx, 2000000h
0x1802fb7d5  mov     rcx, rdi
0x1802fb7d8  mov     r8d, [r8]
0x1802fb7db  call    cs:__imp_SamOpenAlias
0x1802fb7e1  test    eax, eax
0x1802fb7e3  js      loc_1802FB88F
0x1802fb7e9  mov     rcx, [rbp+var_30]
0x1802fb7ed  call    cs:__imp_SamCloseHandle
0x1802fb7f3  jmp     loc_1802FB89D
0x1802fb7f8  mov     r8, [rbp+var_28]
0x1802fb7fc  lea     r9, [rbp+var_30]
0x1802fb800  mov     edx, 2000000h
0x1802fb805  mov     rcx, rdi
0x1802fb808  mov     r8d, [r8]
0x1802fb80b  call    cs:__imp_SamOpenGroup
0x1802fb811  jmp     short loc_1802FB7E1
0x1802fb813  mov     r8, [rbp+var_28]
0x1802fb817  lea     r9, [rbp+var_30]
0x1802fb81b  mov     edx, 2000000h
0x1802fb820  mov     rcx, rdi
0x1802fb823  mov     r8d, [r8]
0x1802fb826  call    cs:__imp_SamOpenUser
0x1802fb82c  test    eax, eax
0x1802fb82e  js      short loc_1802FB88F
0x1802fb830  mov     rcx, [rbp+var_30]
0x1802fb834  lea     r8, [rbp+var_18]
0x1802fb838  mov     edx, 10h
0x1802fb83d  call    cs:__imp_SamQueryInformationUser
0x1802fb843  test    eax, eax
0x1802fb845  js      short loc_1802FB879
0x1802fb847  mov     rcx, [rbp+var_18]
0x1802fb84b  mov     ecx, [rcx]
0x1802fb84d  call    cs:__imp_SampAccountControlToFlags
0x1802fb853  mov     rcx, [rbp+var_18]
0x1802fb857  mov     ebx, eax
0x1802fb859  and     ebx, 3B00h
0x1802fb85f  mov     [rsi], ebx
0x1802fb861  call    cs:__imp_SamFreeMemory
0x1802fb867  and     ebx, 0FFFFCDFFh
0x1802fb86d  neg     ebx
0x1802fb86f  sbb     ebx, ebx
0x1802fb871  and     ebx, 2035h
0x1802fb877  jmp     short loc_1802FB883
0x1802fb879  mov     ecx, eax; Status
0x1802fb87b  call    cs:__imp_RtlNtStatusToDosError
0x1802fb881  mov     ebx, eax
0x1802fb883  mov     rcx, [rbp+var_30]
0x1802fb887  call    cs:__imp_SamCloseHandle
0x1802fb88d  jmp     short loc_1802FB899
0x1802fb88f  mov     ecx, eax; Status
0x1802fb891  call    cs:__imp_RtlNtStatusToDosError
0x1802fb897  mov     ebx, eax
0x1802fb899  test    ebx, ebx
0x1802fb89b  jnz     short loc_1802FB8C7
0x1802fb89d  mov     rdx, [rbp+var_28]
0x1802fb8a1  mov     r8, r15
0x1802fb8a4  mov     rcx, r12; Src
0x1802fb8a7  mov     edx, [rdx]
0x1802fb8a9  call    SampBuildNT4FullSid
0x1802fb8ae  test    eax, eax
0x1802fb8b0  js      short loc_1802FB8BD
0x1802fb8b2  mov     rax, [rbp+var_20]
0x1802fb8b6  mov     ecx, [rax]
0x1802fb8b8  mov     [r14], ecx
0x1802fb8bb  jmp     short loc_1802FB8C7
0x1802fb8bd  mov     ecx, eax; Status
0x1802fb8bf  call    cs:__imp_RtlNtStatusToDosError
0x1802fb8c5  mov     ebx, eax
0x1802fb8c7  mov     rcx, [rbp+var_28]
0x1802fb8cb  call    cs:__imp_SamFreeMemory
0x1802fb8d1  mov     rcx, [rbp+var_20]
0x1802fb8d5  call    cs:__imp_SamFreeMemory
0x1802fb8db  mov     eax, ebx
0x1802fb8dd  add     rsp, 60h
0x1802fb8e1  pop     r15
0x1802fb8e3  pop     r14
0x1802fb8e5  pop     r12
0x1802fb8e7  pop     rdi
0x1802fb8e8  pop     rsi
0x1802fb8e9  pop     rbx
0x1802fb8ea  pop     rbp
0x1802fb8eb  retn
```
