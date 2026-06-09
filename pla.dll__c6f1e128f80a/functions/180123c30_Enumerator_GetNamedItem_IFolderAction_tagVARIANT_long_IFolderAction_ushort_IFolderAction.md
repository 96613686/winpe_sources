# Enumerator::GetNamedItem<IFolderAction>(tagVARIANT,long (IFolderAction::*)(ushort * *),IFolderAction * *)

- ea: `0x180123c30`
- end: `0x180123fde`
- name: `??$GetNamedItem@UIFolderAction@@@Enumerator@@QEAAJUtagVARIANT@@P8IFolderAction@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `942`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800ed8f0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1801237d8`
- `0x180123c30`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123f9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180123f9d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180123d05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180123d05`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180123e17`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180123e17`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180123fac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180123fac`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<IFolderAction>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  IRecordInfo *v8; // xmm1_8
  int v9; // eax
  unsigned int v10; // esi
  __int64 v11; // rax
  SAFEARRAY **v12; // rbx
  HRESULT v13; // eax
  __int64 v14; // rax
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // rcx
  int v16; // eax
  __int64 v17; // rax
  __int64 v19; // [rsp+48h] [rbp-B8h]
  __int64 v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  void *ppvData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v25; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v26[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v27[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v28[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = *(_DWORD *)(a1 + 56);
  v21 = 0;
  ppvData = 0;
  v22 = v4;
  v24 = a1;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "Enumerator::GetNamedItem", 25, &v24, 8, &v22, 4, v19, v20);
  }
  if ( *(_DWORD *)(a1 + 8) )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v8 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v25.vt = *(_OWORD *)a2;
  v25.pRecInfo = v8;
  v9 = Enumerator::GetIndex<IFolderAction>(a1, &v25, a3, (unsigned int *)&v21);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v12 = (SAFEARRAY **)(a1 + 64);
    v13 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 64), &ppvData);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * (unsigned int)v21 + 1);
      v16 = (**v15)(v15, &GUID_03837543_098b_11d8_9414_505054503030, a4);
      v10 = v16;
      if ( v16 >= 0 )
        goto LABEL_29;
      v22 = 0;
      v21 = v16;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v28, 0x4000000000000800uLL);
      v17 = -1;
      do
        ++v17;
      while ( v28[v17] );
    }
    else
    {
      v22 = 0;
      v21 = v13;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_29;
      }
      PlaiWhoAmI(v27, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v27[v14] );
    }
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
    goto LABEL_29;
  }
  v22 = 0;
  v21 = v9;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v11 = -1;
    do
      ++v11;
    while ( v26[v11] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v21,
      4,
      qword_180147320,
      1,
      &v22,
      4,
      "Enumerator::GetNamedItem",
      25);
  }
  v12 = (SAFEARRAY **)(a1 + 64);
LABEL_29:
  if ( *(_DWORD *)(a1 + 8) )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  if ( ppvData )
    SafeArrayUnaccessData(*v12);
  return v10;
}

```

## disassembly

```asm
0x180123c30  mov     [rsp-8+arg_10], rbx
0x180123c35  push    rbp
0x180123c36  push    rsi
0x180123c37  push    rdi
0x180123c38  push    r12
0x180123c3a  push    r13
0x180123c3c  push    r14
0x180123c3e  push    r15
0x180123c40  lea     rbp, [rsp-140h]
0x180123c48  sub     rsp, 240h
0x180123c4f  mov     rax, cs:__security_cookie
0x180123c56  xor     rax, rsp
0x180123c59  mov     [rbp+170h+var_40], rax
0x180123c60  mov     eax, [rcx+38h]
0x180123c63  xor     r15d, r15d
0x180123c66  cmp     dword ptr cs:xmmword_180169738, r15d
0x180123c6d  mov     r14, r9
0x180123c70  mov     rbx, rdx
0x180123c73  mov     [rsp+270h+var_200], r15d
0x180123c78  mov     rdi, rcx
0x180123c7b  mov     [rbp+170h+ppvData], r15
0x180123c7f  lea     r12d, [r15+4]
0x180123c83  mov     [rsp+270h+var_1F8], eax
0x180123c87  lea     r13d, [r15+19h]
0x180123c8b  mov     [rbp+170h+var_1E8], rcx
0x180123c8f  jz      short loc_180123CFB
0x180123c91  mov     rdx, 4000000000000400h
0x180123c9b  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123ca2  jz      short loc_180123CFB
0x180123ca4  mov     rax, cs:qword_180169748
0x180123cab  and     rax, rdx
0x180123cae  cmp     cs:qword_180169748, rax
0x180123cb5  jnz     short loc_180123CFB
0x180123cb7  mov     [rsp+270h+var_230], r12
0x180123cbc  lea     rax, [rsp+270h+var_1F8]
0x180123cc1  mov     [rsp+270h+var_238], rax
0x180123cc6  lea     r9, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180123ccd  lea     rax, [rbp+170h+var_1E8]
0x180123cd1  mov     [rsp+270h+var_240], 8
0x180123cda  mov     [rsp+270h+var_248], rax
0x180123cdf  lea     r8d, [r15+3]
0x180123ce3  lea     rdx, PLA_EVENT_METHOD
0x180123cea  mov     [rsp+270h+var_250], r13
0x180123cef  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180123cf6  call    EventingWriteEvent
0x180123cfb  cmp     [rdi+8], r15d
0x180123cff  jz      short loc_180123D0B
0x180123d01  lea     rcx, [rdi+10h]; lpCriticalSection
0x180123d05  call    cs:__imp_EnterCriticalSection
0x180123d0b  movaps  xmm0, xmmword ptr [rbx]
0x180123d0e  lea     r9, [rsp+270h+var_200]
0x180123d13  movsd   xmm1, qword ptr [rbx+10h]
0x180123d18  lea     rdx, [rbp+170h+var_1E0]
0x180123d1c  mov     rcx, rdi
0x180123d1f  movaps  [rbp+170h+var_1E0], xmm0
0x180123d23  movsd   [rbp+170h+var_1D0], xmm1
0x180123d28  call    ??$GetIndex@UIFolderAction@@@Enumerator@@IEAAJUtagVARIANT@@P8IFolderAction@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IFolderAction>(tagVARIANT,long (IFolderAction::*)(ushort * *),ulong *)
0x180123d2d  mov     esi, eax
0x180123d2f  test    eax, eax
0x180123d31  jns     loc_180123E0C
0x180123d37  cmp     dword ptr cs:xmmword_180169738, r15d
0x180123d3e  mov     [rsp+270h+var_1F8], r15d
0x180123d43  mov     [rsp+270h+var_200], eax
0x180123d47  jz      loc_180123E03
0x180123d4d  mov     rdx, 4000000000000800h; unsigned __int64
0x180123d57  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123d5e  jz      loc_180123E03
0x180123d64  mov     rax, cs:qword_180169748
0x180123d6b  and     rax, rdx
0x180123d6e  cmp     cs:qword_180169748, rax
0x180123d75  jnz     loc_180123E03
0x180123d7b  lea     rcx, [rbp+170h+var_1C0]; unsigned __int16 *
0x180123d7f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180123d84  lea     rcx, [rbp+170h+var_1C0]
0x180123d88  or      rax, 0FFFFFFFFFFFFFFFFh
0x180123d8c  inc     rax
0x180123d8f  cmp     [rcx+rax*2], r15w
0x180123d94  jnz     short loc_180123D8C
0x180123d96  lea     ecx, [rax+rax]
0x180123d99  mov     r8d, 5
0x180123d9f  add     rcx, 2
0x180123da3  lea     rax, [rbp+170h+var_1C0]
0x180123da7  mov     [rsp+270h+var_210], rcx
0x180123dac  lea     r9, [rsp+270h+var_200]
0x180123db1  mov     [rsp+270h+var_218], rax
0x180123db6  lea     rdx, PLA_EVENT_ERROR
0x180123dbd  mov     [rsp+270h+var_220], r13
0x180123dc2  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180123dc9  mov     [rsp+270h+var_228], rax
0x180123dce  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180123dd5  mov     [rsp+270h+var_230], r12
0x180123dda  lea     rax, [rsp+270h+var_1F8]
0x180123ddf  mov     [rsp+270h+var_238], rax
0x180123de4  lea     rax, qword_180147320
0x180123deb  mov     [rsp+270h+var_240], 1
0x180123df4  mov     [rsp+270h+var_248], rax
0x180123df9  mov     [rsp+270h+var_250], r12
0x180123dfe  call    EventingWriteEvent
0x180123e03  lea     rbx, [rdi+40h]
0x180123e07  jmp     loc_180123F93
0x180123e0c  lea     rbx, [rdi+40h]
0x180123e10  mov     rcx, [rbx]; psa
0x180123e13  lea     rdx, [rbp+170h+ppvData]; ppvData
0x180123e17  call    cs:__imp_SafeArrayAccessData
0x180123e1d  mov     esi, eax
0x180123e1f  test    eax, eax
0x180123e21  jns     short loc_180123E8E
0x180123e23  cmp     dword ptr cs:xmmword_180169738, r15d
0x180123e2a  mov     [rsp+270h+var_1F8], r15d
0x180123e2f  mov     [rsp+270h+var_200], eax
0x180123e33  jz      loc_180123F93
0x180123e39  mov     rdx, 4000000000000800h; unsigned __int64
0x180123e43  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123e4a  jz      loc_180123F93
0x180123e50  mov     rax, cs:qword_180169748
0x180123e57  and     rax, rdx
0x180123e5a  cmp     cs:qword_180169748, rax
0x180123e61  jnz     loc_180123F93
0x180123e67  lea     rcx, [rbp+170h+var_140]; unsigned __int16 *
0x180123e6b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180123e70  lea     rcx, [rbp+170h+var_140]
0x180123e74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180123e78  inc     rax
0x180123e7b  cmp     [rcx+rax*2], r15w
0x180123e80  jnz     short loc_180123E78
0x180123e82  lea     ecx, [rax+rax]
0x180123e85  lea     rax, [rbp+170h+var_140]
0x180123e89  jmp     loc_180123F2D
0x180123e8e  mov     eax, [rsp+270h+var_200]
0x180123e92  lea     rdx, _GUID_03837543_098b_11d8_9414_505054503030
0x180123e99  mov     r8, r14
0x180123e9c  lea     rcx, [rax+rax*2]
0x180123ea0  mov     rax, [rbp+170h+ppvData]
0x180123ea4  mov     rcx, [rax+rcx*8+8]
0x180123ea9  mov     rax, [rcx]
0x180123eac  mov     rax, [rax]
0x180123eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180123eb4  mov     esi, eax
0x180123eb6  test    eax, eax
0x180123eb8  jns     loc_180123F93
0x180123ebe  cmp     dword ptr cs:xmmword_180169738, r15d
0x180123ec5  mov     [rsp+270h+var_1F8], r15d
0x180123eca  mov     [rsp+270h+var_200], eax
0x180123ece  jz      loc_180123F93
0x180123ed4  mov     rdx, 4000000000000800h; unsigned __int64
0x180123ede  test    qword ptr cs:xmmword_180169738+8, rdx
0x180123ee5  jz      loc_180123F93
0x180123eeb  mov     rax, cs:qword_180169748
0x180123ef2  and     rax, rdx
0x180123ef5  cmp     cs:qword_180169748, rax
0x180123efc  jnz     loc_180123F93
0x180123f02  lea     rcx, [rbp+170h+var_C0]; unsigned __int16 *
0x180123f09  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180123f0e  lea     rcx, [rbp+170h+var_C0]
0x180123f15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180123f19  inc     rax
0x180123f1c  cmp     [rcx+rax*2], r15w
0x180123f21  jnz     short loc_180123F19
0x180123f23  lea     ecx, [rax+rax]
0x180123f26  lea     rax, [rbp+170h+var_C0]
0x180123f2d  add     rcx, 2
0x180123f31  lea     r9, [rsp+270h+var_200]
0x180123f36  mov     [rsp+270h+var_210], rcx
0x180123f3b  lea     rdx, PLA_EVENT_ERROR
0x180123f42  mov     [rsp+270h+var_218], rax
0x180123f47  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180123f4e  mov     [rsp+270h+var_220], r13
0x180123f53  lea     rax, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180123f5a  mov     [rsp+270h+var_228], rax
0x180123f5f  mov     r8d, 5
0x180123f65  mov     [rsp+270h+var_230], r12
0x180123f6a  lea     rax, [rsp+270h+var_1F8]
0x180123f6f  mov     [rsp+270h+var_238], rax
0x180123f74  lea     rax, qword_180147320
0x180123f7b  mov     [rsp+270h+var_240], 1
0x180123f84  mov     [rsp+270h+var_248], rax
0x180123f89  mov     [rsp+270h+var_250], r12
0x180123f8e  call    EventingWriteEvent
0x180123f93  cmp     [rdi+8], r15d
0x180123f97  jz      short loc_180123FA3
0x180123f99  lea     rcx, [rdi+10h]; lpCriticalSection
0x180123f9d  call    cs:__imp_LeaveCriticalSection
0x180123fa3  cmp     [rbp+170h+ppvData], r15
0x180123fa7  jz      short loc_180123FB2
0x180123fa9  mov     rcx, [rbx]; psa
0x180123fac  call    cs:__imp_SafeArrayUnaccessData
0x180123fb2  mov     eax, esi
0x180123fb4  mov     rcx, [rbp+170h+var_40]
0x180123fbb  xor     rcx, rsp; StackCookie
0x180123fbe  call    __security_check_cookie
0x180123fc3  mov     rbx, [rsp+270h+arg_10]
0x180123fcb  add     rsp, 240h
0x180123fd2  pop     r15
0x180123fd4  pop     r14
0x180123fd6  pop     r13
0x180123fd8  pop     r12
0x180123fda  pop     rdi
0x180123fdb  pop     rsi
0x180123fdc  pop     rbp
0x180123fdd  retn
```
