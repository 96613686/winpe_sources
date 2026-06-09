# PeapQueryCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x1800558a0`
- end: `0x180055b36`
- name: `?PeapQueryCredentialInputFields@@YAKPEAXKPEAEKPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `662`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005a330`

## callees

- `0x180003000`
- `0x1800030d0`
- `0x180003fec`
- `0x180004bd0`
- `0x1800075b0`
- `0x180023064`
- `0x18004acb8`
- `0x1800515ac`
- `0x1800558a0`
- `0x180063f3c`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800559d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055a47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800559d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180055a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800559e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055b14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055b14`

## pseudocode

```c
__int64 __fastcall PeapQueryCredentialInputFields(
        void *a1,
        int a2,
        unsigned __int8 *a3,
        unsigned int a4,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5)
{
  unsigned int InnerConnectionData; // eax
  __int64 v10; // rdx
  const unsigned __int16 *v11; // rcx
  unsigned int v12; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // edi
  DWORD ListNode; // eax
  struct _EAPTLS_CONTROL_BLOCK *v17; // rcx
  __int64 v18; // rdx
  struct _PEAP_EAP_INFO *v19; // rbx
  FARPROC ProcAddress; // r14
  unsigned int (*v21)(unsigned __int8 *); // rsi
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v25; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v26; // [rsp+44h] [rbp-34h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-30h] BYREF
  HLOCAL v28; // [rsp+50h] [rbp-28h] BYREF
  struct _PEAP_EAP_INFO *v29; // [rsp+58h] [rbp-20h] BYREF
  _EAP_CONFIG_INPUT_FIELD_ARRAY v30; // [rsp+60h] [rbp-18h] BYREF

  v28 = 0;
  v29 = 0;
  hMem = 0;
  v26 = 0;
  v25 = 0;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 735, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  InnerConnectionData = GetInnerConnectionData(a2, a4, a3, &v25, (unsigned __int8 **)&hMem, &v26);
  v12 = InnerConnectionData;
  if ( !InnerConnectionData )
  {
    InnerConnectionData = PeapEapInfoGetList(v11, v10, (struct _PEAP_EAP_INFO **)&v28);
    v12 = InnerConnectionData;
    if ( InnerConnectionData )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_31;
      v14 = 737;
      goto LABEL_6;
    }
    v15 = v25;
    ListNode = PeapEapInfoFindListNode(v25, (struct _PEAP_EAP_INFO *)v28, &v29);
    v12 = ListNode;
    if ( ListNode )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_31;
      v18 = 738;
    }
    else
    {
      v19 = v29;
      ProcAddress = GetProcAddress(*((HMODULE *)v29 + 10), "RasEapQueryCredentialInputFields");
      if ( ProcAddress )
      {
        v21 = (unsigned int (*)(unsigned __int8 *))GetProcAddress(*((HMODULE *)v19 + 10), "RasEapFreeMemory");
        if ( v21 )
        {
          v22 = ((__int64 (__fastcall *)(_QWORD, void *, _QWORD, HLOCAL, unsigned int, _EAP_CONFIG_INPUT_FIELD_ARRAY *))ProcAddress)(
                  v15,
                  a1,
                  a2 | 0x10000u,
                  hMem,
                  v26,
                  &v30);
          v12 = v22;
          if ( v22 )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                742,
                &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                v15,
                v22);
          }
          else
          {
            v23 = CopyEAPConfigInputFieldArray(a5, &v30);
            v12 = v23;
            if ( v23 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 743, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v23);
          }
          FreeEAPConfigInputFieldArray(&v30, v21);
          goto LABEL_31;
        }
        ListNode = GetLastError();
        v12 = ListNode;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_31;
        v18 = 741;
      }
      else
      {
        ListNode = GetLastError();
        v12 = ListNode;
        if ( ListNode == 127 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 739, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v15);
          v12 = 50;
          goto LABEL_31;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_31;
        v18 = 740;
      }
    }
    WPP_SF_dd(*((_QWORD *)v17 + 2), v18, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v15, ListNode);
    goto LABEL_31;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v14 = 736;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, InnerConnectionData);
  }
LABEL_31:
  LocalFree(hMem);
  PeapEapInfoFreeList(v28);
  return v12;
}

```

## disassembly

```asm
0x1800558a0  push    rbp
0x1800558a2  push    rbx
0x1800558a3  push    rsi
0x1800558a4  push    rdi
0x1800558a5  push    r12
0x1800558a7  push    r13
0x1800558a9  push    r14
0x1800558ab  push    r15
0x1800558ad  mov     rbp, rsp
0x1800558b0  sub     rsp, 78h
0x1800558b4  xor     esi, esi
0x1800558b6  xorps   xmm0, xmm0
0x1800558b9  mov     [rbp+var_28], rsi
0x1800558bd  mov     ebx, r9d
0x1800558c0  mov     [rbp+var_20], rsi
0x1800558c4  mov     rdi, r8
0x1800558c7  mov     [rbp+hMem], rsi
0x1800558cb  mov     r15d, edx
0x1800558ce  mov     [rbp+var_34], esi
0x1800558d1  mov     r12, rcx
0x1800558d4  mov     [rbp+var_38], esi
0x1800558d7  movups  xmmword ptr [rbp+var_18.dwVersion], xmm0
0x1800558db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800558e2  lea     r13, WPP_GLOBAL_Control
0x1800558e9  lea     r14, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x1800558f0  cmp     rcx, r13
0x1800558f3  jz      short loc_180055906
0x1800558f5  mov     rcx, [rcx+10h]
0x1800558f9  mov     edx, 2DFh
0x1800558fe  mov     r8, r14
0x180055901  call    WPP_SF_
0x180055906  lea     rax, [rbp+var_34]
0x18005590a  mov     r8, rdi; unsigned __int8 *
0x18005590d  mov     [rsp+78h+var_50], rax; unsigned int *
0x180055912  lea     r9, [rbp+var_38]; unsigned int *
0x180055916  lea     rax, [rbp+hMem]
0x18005591a  mov     edx, ebx; unsigned int
0x18005591c  mov     ecx, r15d; unsigned int
0x18005591f  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x180055924  call    ?GetInnerConnectionData@@YAKKKPEAEPEAKPEAPEAE1@Z; GetInnerConnectionData(ulong,ulong,uchar *,ulong *,uchar * *,ulong *)
0x180055929  mov     ebx, eax
0x18005592b  test    eax, eax
0x18005592d  jz      short loc_180055958
0x18005592f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055936  cmp     rcx, r13
0x180055939  jz      loc_180055B10
0x18005593f  mov     edx, 2E0h
0x180055944  mov     rcx, [rcx+10h]
0x180055948  mov     r9d, eax
0x18005594b  mov     r8, r14
0x18005594e  call    WPP_SF_d
0x180055953  jmp     loc_180055B10
0x180055958  lea     r8, [rbp+var_28]; struct _PEAP_EAP_INFO **
0x18005595c  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x180055961  mov     ebx, eax
0x180055963  test    eax, eax
0x180055965  jz      short loc_18005597E
0x180055967  mov     rcx, cs:WPP_GLOBAL_Control
0x18005596e  cmp     rcx, r13
0x180055971  jz      loc_180055B10
0x180055977  mov     edx, 2E1h
0x18005597c  jmp     short loc_180055944
0x18005597e  mov     edi, [rbp+var_38]
0x180055981  lea     r8, [rbp+var_20]; struct _PEAP_EAP_INFO **
0x180055985  mov     rdx, [rbp+var_28]; struct _PEAP_EAP_INFO *
0x180055989  mov     ecx, edi; unsigned int
0x18005598b  call    ?PeapEapInfoFindListNode@@YAKKPEAU_PEAP_EAP_INFO@@PEAPEAU1@@Z; PeapEapInfoFindListNode(ulong,_PEAP_EAP_INFO *,_PEAP_EAP_INFO * *)
0x180055990  mov     ebx, eax
0x180055992  test    eax, eax
0x180055994  jz      short loc_1800559C3
0x180055996  mov     rcx, cs:WPP_GLOBAL_Control
0x18005599d  cmp     rcx, r13
0x1800559a0  jz      loc_180055B10
0x1800559a6  mov     edx, 2E2h
0x1800559ab  mov     r8, r14
0x1800559ae  mov     rcx, [rcx+10h]
0x1800559b2  mov     r9d, edi
0x1800559b5  mov     dword ptr [rsp+78h+var_58], eax
0x1800559b9  call    WPP_SF_dd
0x1800559be  jmp     loc_180055B10
0x1800559c3  mov     rbx, [rbp+var_20]
0x1800559c7  lea     rdx, aRaseapquerycre_0; "RasEapQueryCredentialInputFields"
0x1800559ce  mov     rcx, [rbx+50h]; hModule
0x1800559d2  call    cs:__imp_GetProcAddress
0x1800559d8  mov     r14, rax
0x1800559db  test    rax, rax
0x1800559de  jnz     short loc_180055A3C
0x1800559e0  call    cs:__imp_GetLastError
0x1800559e6  mov     ebx, eax
0x1800559e8  cmp     eax, 7Fh
0x1800559eb  jnz     short loc_180055A1B
0x1800559ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800559f4  cmp     rcx, r13
0x1800559f7  jz      short loc_180055A11
0x1800559f9  mov     rcx, [rcx+10h]
0x1800559fd  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180055a04  mov     edx, 2E3h
0x180055a09  mov     r9d, edi
0x180055a0c  call    WPP_SF_d
0x180055a11  mov     ebx, 32h ; '2'
0x180055a16  jmp     loc_180055B10
0x180055a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a22  cmp     rcx, r13
0x180055a25  jz      loc_180055B10
0x180055a2b  mov     edx, 2E4h
0x180055a30  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180055a37  jmp     loc_1800559AE
0x180055a3c  mov     rcx, [rbx+50h]; hModule
0x180055a40  lea     rdx, ProcName; "RasEapFreeMemory"
0x180055a47  call    cs:__imp_GetProcAddress
0x180055a4d  mov     rsi, rax
0x180055a50  test    rax, rax
0x180055a53  jnz     short loc_180055A74
0x180055a55  call    cs:__imp_GetLastError
0x180055a5b  mov     ebx, eax
0x180055a5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a64  cmp     rcx, r13
0x180055a67  jz      loc_180055B10
0x180055a6d  mov     edx, 2E5h
0x180055a72  jmp     short loc_180055A30
0x180055a74  mov     r9, [rbp+hMem]
0x180055a78  lea     rax, [rbp+var_18]
0x180055a7c  mov     [rsp+78h+var_50], rax
0x180055a81  bts     r15d, 10h
0x180055a86  mov     eax, [rbp+var_34]
0x180055a89  mov     r8d, r15d
0x180055a8c  mov     dword ptr [rsp+78h+var_58], eax
0x180055a90  mov     rdx, r12
0x180055a93  mov     rax, r14
0x180055a96  mov     ecx, edi
0x180055a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a9d  mov     ebx, eax
0x180055a9f  test    eax, eax
0x180055aa1  jz      short loc_180055ACD
0x180055aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180055aaa  cmp     rcx, r13
0x180055aad  jz      short loc_180055B04
0x180055aaf  mov     rcx, [rcx+10h]
0x180055ab3  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180055aba  mov     edx, 2E6h
0x180055abf  mov     dword ptr [rsp+78h+var_58], eax
0x180055ac3  mov     r9d, edi
0x180055ac6  call    WPP_SF_dd
0x180055acb  jmp     short loc_180055B04
0x180055acd  mov     rcx, [rbp+arg_20]
0x180055ad1  lea     rdx, [rbp+var_18]
0x180055ad5  call    CopyEAPConfigInputFieldArray
0x180055ada  mov     ebx, eax
0x180055adc  test    eax, eax
0x180055ade  jz      short loc_180055B04
0x180055ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ae7  cmp     rcx, r13
0x180055aea  jz      short loc_180055B04
0x180055aec  mov     rcx, [rcx+10h]
0x180055af0  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180055af7  mov     edx, 2E7h
0x180055afc  mov     r9d, eax
0x180055aff  call    WPP_SF_d
0x180055b04  mov     rdx, rsi; unsigned int (*)(unsigned __int8 *)
0x180055b07  lea     rcx, [rbp+var_18]; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x180055b0b  call    ?FreeEAPConfigInputFieldArray@@YAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x180055b10  mov     rcx, [rbp+hMem]; hMem
0x180055b14  call    cs:__imp_LocalFree
0x180055b1a  mov     rcx, [rbp+var_28]; hMem
0x180055b1e  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x180055b23  mov     eax, ebx
0x180055b25  add     rsp, 78h
0x180055b29  pop     r15
0x180055b2b  pop     r14
0x180055b2d  pop     r13
0x180055b2f  pop     r12
0x180055b31  pop     rdi
0x180055b32  pop     rsi
0x180055b33  pop     rbx
0x180055b34  pop     rbp
0x180055b35  retn
```
