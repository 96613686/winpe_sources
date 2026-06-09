# IASGetAliasMembership

- ea: `0x180027e8c`
- end: `0x18002819a`
- name: `IASGetAliasMembership`
- size: `782`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000d794`
- `0x1800282e4`

## callees

- `0x180027e8c`
- `0x18002a824`
- `0x18002e010`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180027fac`
- `ntdll!RtlLengthSid` at `0x180027fac`
- `ntdll!RtlCopySidAndAttributesArray` at `0x1800280e1`
- `ntdll!RtlCopySidAndAttributesArray` at `0x1800280e1`
- `ntdll!RtlNtStatusToDosError` at `0x180027f51`
- `ntdll!RtlNtStatusToDosError` at `0x180027f85`
- `ntdll!RtlNtStatusToDosError` at `0x180027f51`
- `ntdll!RtlNtStatusToDosError` at `0x180027f85`
- `KERNEL32!LocalAlloc` at `0x180027ef2`
- `KERNEL32!LocalAlloc` at `0x180027ef2`
- `KERNEL32!LocalFree` at `0x180027fe8`
- `KERNEL32!LocalFree` at `0x180027fe8`
- `SAMLIB!SamFreeMemory` at `0x180027fd5`
- `SAMLIB!SamFreeMemory` at `0x180027fdf`
- `SAMLIB!SamFreeMemory` at `0x180027fd5`
- `SAMLIB!SamFreeMemory` at `0x180027fdf`
- `SAMLIB!SamGetAliasMembership` at `0x180027f45`
- `SAMLIB!SamGetAliasMembership` at `0x180027f77`
- `SAMLIB!SamGetAliasMembership` at `0x180027f45`
- `SAMLIB!SamGetAliasMembership` at `0x180027f77`

## pseudocode

```c
__int64 __fastcall IASGetAliasMembership(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall *a3)(_QWORD),
        __int64 *a4,
        ULONG *a5)
{
  unsigned int v5; // eax
  unsigned int v6; // r14d
  unsigned int v10; // ebx
  ULONG v11; // ebx
  _QWORD *v12; // r12
  unsigned int i; // edx
  __int64 v14; // rax
  __int64 v15; // rcx
  NTSTATUS AliasMembership; // eax
  NTSTATUS v17; // eax
  unsigned int v18; // r15d
  unsigned int v19; // edx
  ULONG v20; // eax
  unsigned int v22; // r9d
  unsigned __int64 v23; // r8
  ULONG v24; // r8d
  unsigned int v25; // r15d
  unsigned __int64 v26; // rdx
  unsigned int v27; // eax
  unsigned __int64 v28; // r14
  __int64 v29; // rax
  ULONG v30; // ecx
  struct _SID_AND_ATTRIBUTES *v31; // r9
  unsigned int v32; // esi
  __int64 v33; // rdi
  char *j; // rcx
  __int64 v35; // rdx
  __int64 k; // rdi
  __int64 v37; // rdx
  unsigned int v38; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-1Ch] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  __int64 v41; // [rsp+50h] [rbp-10h] BYREF
  __int64 v42; // [rsp+58h] [rbp-8h] BYREF
  ULONG SidAreaSize; // [rsp+A8h] [rbp+48h] BYREF
  __int64 (__fastcall *v44)(_QWORD); // [rsp+B0h] [rbp+50h]

  v44 = a3;
  v5 = *(_DWORD *)a2;
  v6 = 0;
  Sid = 0;
  v42 = 0;
  v41 = 0;
  v10 = v5 + 1;
  v38 = 0;
  v39 = 0;
  SidAreaSize = 0;
  if ( v5 + 1 >= v5 && v10 <= 0x1FFFFFFF )
  {
    v12 = LocalAlloc(0x40u, 8LL * v10);
    if ( !v12 )
      return 8;
    for ( i = 0; i < *(_DWORD *)a2; v12[v15] = *(_QWORD *)(a2 + 8 * v14 + 8) )
    {
      v14 = 2LL * i;
      v15 = i++;
    }
    v12[i] = a1;
    AliasMembership = SamGetAliasMembership(theAccountDomainHandle, v10, v12, &v38, &v42);
    if ( AliasMembership < 0 )
    {
      v11 = RtlNtStatusToDosError(AliasMembership);
LABEL_20:
      LocalFree(v12);
      return v11;
    }
    v17 = SamGetAliasMembership(theBuiltinDomainHandle, v10, v12, &v39, &v41);
    v11 = v17;
    if ( v17 < 0 )
    {
      v11 = RtlNtStatusToDosError(v17);
LABEL_19:
      SamFreeMemory(v42);
      goto LABEL_20;
    }
    v18 = *(_DWORD *)a2;
    SidAreaSize = 8;
    v19 = 8;
    while ( v6 < v18 )
    {
      v20 = RtlLengthSid(*(PSID *)(a2 + 16LL * v6 + 8));
      v19 = SidAreaSize + v20;
      if ( SidAreaSize + v20 < SidAreaSize )
        goto LABEL_16;
      SidAreaSize += v20;
      ++v6;
    }
    v22 = v18 + v38;
    if ( v18 + v38 >= v18 )
    {
      v23 = v38 * (unsigned __int64)(unsigned int)theAccountSidLen;
      if ( v23 <= 0xFFFFFFFF )
      {
        v24 = v19 + v23;
        if ( v24 >= v19 )
        {
          SidAreaSize = v24;
          v25 = v22 + v39;
          if ( v22 + v39 < v22 )
            goto LABEL_17;
          v26 = v39 * (unsigned __int64)(unsigned int)theBuiltinSidLen;
          if ( v26 > 0xFFFFFFFF )
            goto LABEL_17;
          v27 = v26 + v24;
          if ( (unsigned int)v26 + v24 >= v24 )
          {
            v28 = 16LL * v25;
            SidAreaSize = v26 + v24;
            if ( v28 > 0xFFFFFFFF )
              goto LABEL_17;
            if ( (unsigned int)v28 + v27 >= v27 )
            {
              SidAreaSize = v28 + v27;
              v29 = v44((unsigned int)v28 + v27);
              *a4 = v29;
              if ( v29 )
              {
                *a5 = SidAreaSize;
                *(_DWORD *)*a4 = v25;
                v30 = *(_DWORD *)a2;
                v31 = (struct _SID_AND_ATTRIBUTES *)(*a4 + 8);
                Sid = &v31[v28 / 0x10];
                RtlCopySidAndAttributesArray(
                  v30,
                  (PSID_AND_ATTRIBUTES)(a2 + 8),
                  SidAreaSize,
                  v31,
                  &v31[v28 / 0x10],
                  &Sid,
                  &SidAreaSize);
                v32 = *(_DWORD *)a2;
                v33 = 0;
                for ( j = (char *)Sid; (unsigned int)v33 < v38; Sid = j )
                {
                  IASInitializeChildSid(j, theAccountDomainSid, *(_DWORD *)(v42 + 4 * v33));
                  v33 = (unsigned int)(v33 + 1);
                  v35 = v32++;
                  v35 *= 2;
                  *(_QWORD *)(*a4 + 8 * v35 + 8) = Sid;
                  *(_DWORD *)(*a4 + 8 * v35 + 16) = 4;
                  j = (char *)Sid + (unsigned int)theAccountSidLen;
                }
                for ( k = 0; (unsigned int)k < v39; Sid = j )
                {
                  IASInitializeChildSid(j, theBuiltinDomainSid, *(_DWORD *)(v41 + 4 * k));
                  k = (unsigned int)(k + 1);
                  v37 = v32++;
                  v37 *= 2;
                  *(_QWORD *)(*a4 + 8 * v37 + 8) = Sid;
                  *(_DWORD *)(*a4 + 8 * v37 + 16) = 4;
                  j = (char *)Sid + (unsigned int)theBuiltinSidLen;
                }
              }
              else
              {
                v11 = 8;
              }
LABEL_18:
              SamFreeMemory(v41);
              goto LABEL_19;
            }
          }
        }
LABEL_16:
        SidAreaSize = -1;
      }
    }
LABEL_17:
    v11 = 534;
    goto LABEL_18;
  }
  return 534;
}

```

## disassembly

```asm
0x180027e8c  mov     [rsp-38h+arg_0], rbx
0x180027e91  mov     [rsp-38h+arg_10], r8
0x180027e96  push    rbp
0x180027e97  push    rsi
0x180027e98  push    rdi
0x180027e99  push    r12
0x180027e9b  push    r13
0x180027e9d  push    r14
0x180027e9f  push    r15
0x180027ea1  mov     rbp, rsp
0x180027ea4  sub     rsp, 60h
0x180027ea8  mov     eax, [rdx]
0x180027eaa  xor     r14d, r14d
0x180027ead  mov     r13, r9
0x180027eb0  mov     [rbp+Sid], r14
0x180027eb4  mov     rsi, rdx
0x180027eb7  mov     [rbp+var_8], r14
0x180027ebb  mov     rdi, rcx
0x180027ebe  mov     [rbp+var_10], r14
0x180027ec2  lea     ebx, [rax+1]
0x180027ec5  mov     [rbp+var_20], r14d
0x180027ec9  mov     [rbp+var_1C], r14d
0x180027ecd  mov     [rbp+SidAreaSize], r14d
0x180027ed1  cmp     ebx, eax
0x180027ed3  jnb     short loc_180027EDF
0x180027ed5  mov     ebx, 216h
0x180027eda  jmp     loc_180027FEE
0x180027edf  cmp     ebx, 1FFFFFFFh
0x180027ee5  ja      short loc_180027ED5
0x180027ee7  mov     edx, ebx
0x180027ee9  mov     ecx, 40h ; '@'; uFlags
0x180027eee  shl     rdx, 3; uBytes
0x180027ef2  call    cs:__imp_LocalAlloc
0x180027ef8  mov     r12, rax
0x180027efb  test    rax, rax
0x180027efe  jnz     short loc_180027F08
0x180027f00  lea     ebx, [rax+8]
0x180027f03  jmp     loc_180027FEE
0x180027f08  mov     edx, r14d
0x180027f0b  cmp     [rsi], r14d
0x180027f0e  jbe     short loc_180027F26
0x180027f10  mov     eax, edx
0x180027f12  add     rax, rax
0x180027f15  mov     ecx, edx
0x180027f17  inc     edx
0x180027f19  mov     rax, [rsi+rax*8+8]
0x180027f1e  mov     [r12+rcx*8], rax
0x180027f22  cmp     edx, [rsi]
0x180027f24  jb      short loc_180027F10
0x180027f26  mov     eax, edx
0x180027f28  lea     r9, [rbp+var_20]
0x180027f2c  mov     r8, r12
0x180027f2f  mov     edx, ebx
0x180027f31  mov     [r12+rax*8], rdi
0x180027f35  lea     rax, [rbp+var_8]
0x180027f39  mov     rcx, cs:theAccountDomainHandle
0x180027f40  mov     [rsp+60h+SidArea], rax
0x180027f45  call    cs:__imp_SamGetAliasMembership
0x180027f4b  test    eax, eax
0x180027f4d  jns     short loc_180027F5E
0x180027f4f  mov     ecx, eax; Status
0x180027f51  call    cs:__imp_RtlNtStatusToDosError
0x180027f57  mov     ebx, eax
0x180027f59  jmp     loc_180027FE5
0x180027f5e  mov     rcx, cs:theBuiltinDomainHandle
0x180027f65  lea     rax, [rbp+var_10]
0x180027f69  lea     r9, [rbp+var_1C]
0x180027f6d  mov     [rsp+60h+SidArea], rax
0x180027f72  mov     r8, r12
0x180027f75  mov     edx, ebx
0x180027f77  call    cs:__imp_SamGetAliasMembership
0x180027f7d  mov     ebx, eax
0x180027f7f  test    eax, eax
0x180027f81  jns     short loc_180027F8F
0x180027f83  mov     ecx, eax; Status
0x180027f85  call    cs:__imp_RtlNtStatusToDosError
0x180027f8b  mov     ebx, eax
0x180027f8d  jmp     short loc_180027FDB
0x180027f8f  mov     r15d, [rsi]
0x180027f92  mov     edi, 8
0x180027f97  mov     [rbp+SidAreaSize], edi
0x180027f9a  mov     edx, edi
0x180027f9c  cmp     r14d, r15d
0x180027f9f  jnb     short loc_180028008
0x180027fa1  mov     ecx, r14d
0x180027fa4  add     rcx, rcx
0x180027fa7  mov     rcx, [rsi+rcx*8+8]; Sid
0x180027fac  call    cs:__imp_RtlLengthSid
0x180027fb2  mov     ecx, [rbp+SidAreaSize]
0x180027fb5  lea     edx, [rcx+rax]
0x180027fb8  cmp     edx, ecx
0x180027fba  jb      short loc_180027FC4
0x180027fbc  mov     [rbp+SidAreaSize], edx
0x180027fbf  inc     r14d
0x180027fc2  jmp     short loc_180027F9C
0x180027fc4  mov     ecx, 0FFFFFFFFh
0x180027fc9  mov     [rbp+SidAreaSize], ecx
0x180027fcc  mov     ebx, 216h
0x180027fd1  mov     rcx, [rbp+var_10]
0x180027fd5  call    cs:__imp_SamFreeMemory
0x180027fdb  mov     rcx, [rbp+var_8]
0x180027fdf  call    cs:__imp_SamFreeMemory
0x180027fe5  mov     rcx, r12; hMem
0x180027fe8  call    cs:__imp_LocalFree
0x180027fee  mov     eax, ebx
0x180027ff0  mov     rbx, [rsp+60h+arg_0]
0x180027ff8  add     rsp, 60h
0x180027ffc  pop     r15
0x180027ffe  pop     r14
0x180028000  pop     r13
0x180028002  pop     r12
0x180028004  pop     rdi
0x180028005  pop     rsi
0x180028006  pop     rbp
0x180028007  retn
0x180028008  mov     eax, [rbp+var_20]
0x18002800b  lea     r9d, [r15+rax]
0x18002800f  cmp     r9d, r15d
0x180028012  jb      short loc_180027FCC
0x180028014  mov     r8d, cs:theAccountSidLen
0x18002801b  mov     ecx, 0FFFFFFFFh
0x180028020  imul    r8, rax
0x180028024  cmp     r8, rcx
0x180028027  ja      short loc_180027FCC
0x180028029  add     r8d, edx
0x18002802c  cmp     r8d, edx
0x18002802f  jb      short loc_180027FC9
0x180028031  mov     eax, [rbp+var_1C]
0x180028034  mov     [rbp+SidAreaSize], r8d
0x180028038  lea     r15d, [r9+rax]
0x18002803c  cmp     r15d, r9d
0x18002803f  jb      short loc_180027FCC
0x180028041  mov     edx, cs:theBuiltinSidLen
0x180028047  imul    rdx, rax
0x18002804b  cmp     rdx, rcx
0x18002804e  ja      loc_180027FCC
0x180028054  lea     eax, [rdx+r8]
0x180028058  cmp     eax, r8d
0x18002805b  jb      loc_180027FC9
0x180028061  mov     r14d, r15d
0x180028064  shl     r14, 4
0x180028068  mov     [rbp+SidAreaSize], eax
0x18002806b  cmp     r14, rcx
0x18002806e  ja      loc_180027FCC
0x180028074  lea     edx, [r14+rax]
0x180028078  cmp     edx, eax
0x18002807a  jb      loc_180027FC9
0x180028080  mov     rax, [rbp+arg_10]
0x180028084  mov     ecx, edx
0x180028086  mov     [rbp+SidAreaSize], edx
0x180028089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002808e  mov     [r13+0], rax
0x180028092  test    rax, rax
0x180028095  jnz     short loc_18002809E
0x180028097  mov     ebx, edi
0x180028099  jmp     loc_180027FD1
0x18002809e  mov     eax, [rbp+SidAreaSize]
0x1800280a1  lea     rdx, [rsi+8]; Src
0x1800280a5  mov     rcx, [rbp+arg_20]
0x1800280a9  mov     [rcx], eax
0x1800280ab  lea     rcx, [rbp+SidAreaSize]
0x1800280af  mov     rax, [r13+0]
0x1800280b3  mov     [rsp+60h+RemainingSidAreaSize], rcx; RemainingSidAreaSize
0x1800280b8  lea     rcx, [rbp+Sid]
0x1800280bc  mov     [rsp+60h+RemainingSidArea], rcx; RemainingSidArea
0x1800280c1  mov     [rax], r15d
0x1800280c4  mov     r9, [r13+0]
0x1800280c8  mov     r8d, [rbp+SidAreaSize]; SidAreaSize
0x1800280cc  mov     ecx, [rsi]; Count
0x1800280ce  lea     rax, [r9+8]
0x1800280d2  add     r9, rdi; Dest
0x1800280d5  add     rax, r14
0x1800280d8  mov     [rbp+Sid], rax
0x1800280dc  mov     [rsp+60h+SidArea], rax; SidArea
0x1800280e1  call    cs:__imp_RtlCopySidAndAttributesArray
0x1800280e7  mov     esi, [rsi]
0x1800280e9  xor     edi, edi
0x1800280eb  mov     rcx, [rbp+Sid]; Sid
0x1800280ef  lea     r14d, [rdi+4]
0x1800280f3  cmp     [rbp+var_20], edi
0x1800280f6  jbe     short loc_180028141
0x1800280f8  mov     r8, [rbp+var_8]
0x1800280fc  mov     rdx, cs:theAccountDomainSid; SourceSid
0x180028103  mov     r8d, [r8+rdi*4]
0x180028107  call    IASInitializeChildSid
0x18002810c  mov     rax, [rbp+Sid]
0x180028110  inc     edi
0x180028112  mov     rcx, [r13+0]
0x180028116  mov     edx, esi
0x180028118  inc     esi
0x18002811a  add     rdx, rdx
0x18002811d  mov     [rcx+rdx*8+8], rax
0x180028122  mov     rax, [r13+0]
0x180028126  mov     [rax+rdx*8+10h], r14d
0x18002812b  mov     rcx, [rbp+Sid]
0x18002812f  mov     eax, cs:theAccountSidLen
0x180028135  add     rcx, rax; Sid
0x180028138  mov     [rbp+Sid], rcx
0x18002813c  cmp     edi, [rbp+var_20]
0x18002813f  jb      short loc_1800280F8
0x180028141  xor     edi, edi
0x180028143  cmp     [rbp+var_1C], edi
0x180028146  jbe     loc_180027FD1
0x18002814c  mov     r8, [rbp+var_10]
0x180028150  mov     rdx, cs:theBuiltinDomainSid; SourceSid
0x180028157  mov     r8d, [r8+rdi*4]
0x18002815b  call    IASInitializeChildSid
0x180028160  mov     rax, [rbp+Sid]
0x180028164  inc     edi
0x180028166  mov     rcx, [r13+0]
0x18002816a  mov     edx, esi
0x18002816c  inc     esi
0x18002816e  add     rdx, rdx
0x180028171  mov     [rcx+rdx*8+8], rax
0x180028176  mov     rax, [r13+0]
0x18002817a  mov     [rax+rdx*8+10h], r14d
0x18002817f  mov     rcx, [rbp+Sid]
0x180028183  mov     eax, cs:theBuiltinSidLen
0x180028189  add     rcx, rax
0x18002818c  mov     [rbp+Sid], rcx
0x180028190  cmp     edi, [rbp+var_1C]
0x180028193  jb      short loc_18002814C
0x180028195  jmp     loc_180027FD1
```
