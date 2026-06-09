# AddInterfaceToInterfaceStateNameList(_WNF_STATE_NAME,_GUID,_WNF_STATE_NAME *)

- ea: `0x180039818`
- end: `0x1800399f4`
- name: `?AddInterfaceToInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@PEAU1@@Z`
- size: `476`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, struct _GUID *__struct_ptr, struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000f4a0`

## callees

- `0x1800025f0`
- `0x180039818`
- `0x1800399fc`
- `0x180039c3c`
- `0x180039d4c`
- `0x18003a028`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x1800399c9`
- `ntdll!NtDeleteWnfStateName` at `0x1800399c9`
- `ntdll!NtQueryWnfStateNameInformation` at `0x1800398bc`
- `ntdll!NtQueryWnfStateNameInformation` at `0x1800398bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003995f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003995f`

## pseudocode

```c
__int64 __fastcall AddInterfaceToInterfaceStateNameList(
        struct _WNF_STATE_NAME a1,
        struct _GUID *a2,
        struct _WNF_STATE_NAME *a3)
{
  int InterfaceStateEntryFromInterfaceGuid; // eax
  struct _GUID *v7; // rcx
  int v8; // esi
  struct _WNF_STATE_NAME v9; // rbx
  int v10; // esi
  _WNF_STATE_NAME v11; // xmm0_8
  unsigned int v12; // r8d
  int v13; // eax
  unsigned int v14; // eax
  int v16; // [rsp+30h] [rbp-39h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-35h] BYREF
  _QWORD v18[4]; // [rsp+38h] [rbp-31h] BYREF
  _WNF_STATE_NAME v19; // [rsp+58h] [rbp-11h] BYREF
  struct _GUID v20; // [rsp+60h] [rbp-9h] BYREF
  _WNF_STATE_NAME v21[4]; // [rsp+70h] [rbp+7h] BYREF

  memset((char *)v18 + 4, 0, 28);
  memset(v21, 0, sizeof(v21));
  v19 = 0;
  v17 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v20 = *a2;
      InterfaceStateEntryFromInterfaceGuid = GetInterfaceStateEntryFromInterfaceGuid(
                                               a1,
                                               &v20,
                                               (struct InterfaceStateEntry *)v18,
                                               &v17);
      v8 = InterfaceStateEntryFromInterfaceGuid;
      if ( InterfaceStateEntryFromInterfaceGuid == -2147023728 )
        goto LABEL_13;
      if ( InterfaceStateEntryFromInterfaceGuid < 0 )
        goto LABEL_21;
      v9 = (struct _WNF_STATE_NAME)v18[2];
      *(_QWORD *)&v20.Data1 = v18[2];
      v16 = 0;
      v10 = NtQueryWnfStateNameInformation(&v20, 0, 0, &v16, 4);
      if ( v10 < 0 || v16 )
        break;
      v20 = *a2;
      v8 = RemoveInterfaceFromInterfaceStateNameList(a1, &v20);
      if ( v8 < 0 )
        goto LABEL_21;
    }
    v7 = (struct _GUID *)(unsigned int)v10;
    v8 = v10 | 0x10000000;
    if ( (int)v7 >= 0 )
      v8 = 0;
    if ( v8 < 0 )
      goto LABEL_21;
    if ( !v8 )
    {
      v8 = -2147024713;
      if ( a3 )
        *a3 = v9;
LABEL_21:
      v14 = NullWnfStateName;
      goto LABEL_25;
    }
LABEL_13:
    if ( v19 == NullWnfStateName )
    {
      v8 = CreateInterfaceStateName(v7, &v19);
      if ( v8 < 0 )
        goto LABEL_21;
      v11 = *(_WNF_STATE_NAME *)&a2->Data2;
      v21[0].Data[0] = a2->Data1;
      v21[1].Data[1] = *(_DWORD *)&a2->Data4[4];
      v21[2] = v19;
      *(_WNF_STATE_NAME *)((char *)v21 + 4) = v11;
    }
    GetSystemTimeAsFileTime((LPFILETIME)&v21[3]);
    v13 = AddToInterfaceStateNameList(a1, (struct InterfaceStateEntry *)v21, v12, &v17);
    v8 = v13;
    if ( v13 >= 0 )
      break;
    if ( v13 != -805306367 )
      goto LABEL_21;
  }
  if ( a3 )
    *a3 = v19;
  v14 = NullWnfStateName;
  v19 = (_WNF_STATE_NAME)NullWnfStateName;
LABEL_25:
  if ( v19 != __PAIR64__(HIDWORD(NullWnfStateName), v14) )
    NtDeleteWnfStateName(&v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039818  mov     [rsp-8+arg_18], rbx
0x18003981d  push    rbp
0x18003981e  push    rsi
0x18003981f  push    rdi
0x180039820  push    r14
0x180039822  push    r15
0x180039824  lea     rbp, [rsp-37h]
0x180039829  sub     rsp, 0A0h
0x180039830  mov     rax, cs:__security_cookie
0x180039837  xor     rax, rsp
0x18003983a  mov     [rbp+57h+var_30], rax
0x18003983e  xorps   xmm0, xmm0
0x180039841  xor     eax, eax
0x180039843  movups  xmmword ptr [rbp+57h+var_84], xmm0
0x180039847  mov     r14, r8
0x18003984a  mov     r15, rdx
0x18003984d  movups  [rbp+57h+var_4C], xmm0
0x180039851  mov     rdi, rcx
0x180039854  mov     [rbp+57h+var_50], eax
0x180039857  movups  xmmword ptr [rbp+57h+var_84+0Ch], xmm0
0x18003985b  mov     qword ptr [rbp+57h+var_68.Data], rax
0x18003985f  movups  [rbp+57h+var_4C+0Ch], xmm0
0x180039863  mov     [rbp+57h+var_8C], eax
0x180039866  movaps  xmm0, xmmword ptr [r15]
0x18003986a  lea     r9, [rbp+57h+var_8C]; unsigned int *
0x18003986e  lea     r8, [rbp+57h+var_88]; struct InterfaceStateEntry *
0x180039872  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180039877  lea     rdx, [rbp+57h+var_60]; struct _GUID
0x18003987b  mov     rcx, rdi; struct _WNF_STATE_NAME
0x18003987e  call    ?GetInterfaceStateEntryFromInterfaceGuid@@YAJU_WNF_STATE_NAME@@U_GUID@@PEAUInterfaceStateEntry@@PEAK@Z; GetInterfaceStateEntryFromInterfaceGuid(_WNF_STATE_NAME,_GUID,InterfaceStateEntry *,ulong *)
0x180039883  mov     esi, eax
0x180039885  cmp     eax, 80070490h
0x18003988a  jz      loc_180039912
0x180039890  test    eax, eax
0x180039892  js      loc_180039995
0x180039898  mov     rbx, qword ptr [rbp+57h+var_84+0Ch]
0x18003989c  lea     r9, [rbp+57h+var_90]
0x1800398a0  xor     r8d, r8d
0x1800398a3  mov     qword ptr [rbp+57h+var_60.Data1], rbx
0x1800398a7  xor     edx, edx
0x1800398a9  mov     [rbp+57h+var_90], 0
0x1800398b0  lea     rcx, [rbp+57h+var_60]
0x1800398b4  mov     [rsp+0C0h+var_A0], 4
0x1800398bc  call    cs:__imp_NtQueryWnfStateNameInformation
0x1800398c2  mov     esi, eax
0x1800398c4  test    eax, eax
0x1800398c6  js      short loc_1800398CE
0x1800398c8  cmp     [rbp+57h+var_90], 0
0x1800398cc  jz      short loc_1800398EE
0x1800398ce  mov     ecx, esi
0x1800398d0  xor     eax, eax
0x1800398d2  bts     esi, 1Ch
0x1800398d6  test    ecx, ecx
0x1800398d8  cmovns  esi, eax
0x1800398db  test    esi, esi
0x1800398dd  js      loc_180039995
0x1800398e3  jz      loc_180039988
0x1800398e9  cmp     esi, 1
0x1800398ec  jnz     short loc_180039912
0x1800398ee  movaps  xmm0, xmmword ptr [r15]
0x1800398f2  lea     rdx, [rbp+57h+var_60]; struct _GUID
0x1800398f6  mov     rcx, rdi; struct _WNF_STATE_NAME
0x1800398f9  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800398fe  call    ?RemoveInterfaceFromInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@U_GUID@@@Z; RemoveInterfaceFromInterfaceStateNameList(_WNF_STATE_NAME,_GUID)
0x180039903  mov     esi, eax
0x180039905  test    eax, eax
0x180039907  jns     loc_180039866
0x18003990d  jmp     loc_180039995
0x180039912  mov     eax, [rbp+57h+var_68.Data]
0x180039915  cmp     eax, dword ptr cs:NullWnfStateName
0x18003991b  jnz     short loc_18003995B
0x18003991d  mov     eax, dword ptr cs:NullWnfStateName+4
0x180039923  cmp     [rbp+57h+var_68.Data+4], eax
0x180039926  jnz     short loc_18003995B
0x180039928  lea     rdx, [rbp+57h+var_68]; struct _WNF_STATE_NAME *
0x18003992c  call    ?CreateInterfaceStateName@@YAJU_GUID@@PEAU_WNF_STATE_NAME@@@Z; CreateInterfaceStateName(_GUID,_WNF_STATE_NAME *)
0x180039931  mov     esi, eax
0x180039933  test    eax, eax
0x180039935  js      short loc_180039995
0x180039937  mov     eax, [r15]
0x18003993a  movsd   xmm0, qword ptr [r15+4]
0x180039940  mov     [rbp+57h+var_50], eax
0x180039943  mov     eax, [r15+0Ch]
0x180039947  mov     dword ptr [rbp+57h+var_4C+8], eax
0x18003994a  mov     eax, [rbp+57h+var_68.Data]
0x18003994d  mov     dword ptr [rbp+57h+var_4C+0Ch], eax
0x180039950  mov     eax, [rbp+57h+var_68.Data+4]
0x180039953  mov     [rbp+57h+var_3C], eax
0x180039956  movsd   qword ptr [rbp+57h+var_4C], xmm0
0x18003995b  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003995f  call    cs:__imp_GetSystemTimeAsFileTime
0x180039965  lea     r9, [rbp+57h+var_8C]; unsigned int *
0x180039969  mov     rcx, rdi; struct _WNF_STATE_NAME
0x18003996c  lea     rdx, [rbp+57h+var_50]; struct InterfaceStateEntry *
0x180039970  call    ?AddToInterfaceStateNameList@@YAJU_WNF_STATE_NAME@@PEAUInterfaceStateEntry@@KPEAK@Z; AddToInterfaceStateNameList(_WNF_STATE_NAME,InterfaceStateEntry *,ulong,ulong *)
0x180039975  mov     esi, eax
0x180039977  test    eax, eax
0x180039979  jns     short loc_18003999E
0x18003997b  cmp     eax, 0D0000001h
0x180039980  jz      loc_180039866
0x180039986  jmp     short loc_180039995
0x180039988  mov     esi, 800700B7h
0x18003998d  test    r14, r14
0x180039990  jz      short loc_180039995
0x180039992  mov     [r14], rbx
0x180039995  mov     rax, cs:NullWnfStateName
0x18003999c  jmp     short loc_1800399B5
0x18003999e  test    r14, r14
0x1800399a1  jz      short loc_1800399AA
0x1800399a3  mov     rax, qword ptr [rbp+57h+var_68.Data]
0x1800399a7  mov     [r14], rax
0x1800399aa  mov     rax, cs:NullWnfStateName
0x1800399b1  mov     qword ptr [rbp+57h+var_68.Data], rax
0x1800399b5  cmp     [rbp+57h+var_68.Data], eax
0x1800399b8  jnz     short loc_1800399C5
0x1800399ba  mov     eax, dword ptr cs:NullWnfStateName+4
0x1800399c0  cmp     [rbp+57h+var_68.Data+4], eax
0x1800399c3  jz      short loc_1800399CF
0x1800399c5  lea     rcx, [rbp+57h+var_68]
0x1800399c9  call    cs:__imp_NtDeleteWnfStateName
0x1800399cf  mov     eax, esi
0x1800399d1  mov     rcx, [rbp+57h+var_30]
0x1800399d5  xor     rcx, rsp; StackCookie
0x1800399d8  call    __security_check_cookie
0x1800399dd  mov     rbx, [rsp+0C0h+arg_18]
0x1800399e5  add     rsp, 0A0h
0x1800399ec  pop     r15
0x1800399ee  pop     r14
0x1800399f0  pop     rdi
0x1800399f1  pop     rsi
0x1800399f2  pop     rbp
0x1800399f3  retn
```
