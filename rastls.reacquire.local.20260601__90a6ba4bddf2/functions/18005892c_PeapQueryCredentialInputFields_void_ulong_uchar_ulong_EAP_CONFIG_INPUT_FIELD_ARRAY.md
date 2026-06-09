# PeapQueryCredentialInputFields(void *,ulong,uchar *,ulong,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x18005892c`
- end: `0x180058be1`
- name: `?PeapQueryCredentialInputFields@@YAKPEAXKPEAEKPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `693`
- prototype: `unsigned int(void *, unsigned int, unsigned __int8 *, unsigned int, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18005d6e0`

## callees

- `0x180003118`
- `0x180003240`
- `0x18000437c`
- `0x180005010`
- `0x180007d00`
- `0x180025b08`
- `0x18004d58c`
- `0x180054344`
- `0x18005892c`
- `0x18006799c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058a5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058adf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058a5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180058adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058af3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058af3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180058bb8`

## pseudocode

```c
__int64 __fastcall PeapQueryCredentialInputFields(
        void *a1,
        unsigned int a2,
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 735, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids);
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
                  a2 | 0x10000,
                  hMem,
                  v26,
                  &v30);
          v12 = v22;
          if ( v22 )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                742,
                &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids,
                v15,
                v22);
          }
          else
          {
            v23 = CopyEAPConfigInputFieldArray(a5, &v30);
            v12 = v23;
            if ( v23 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 743, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v23);
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
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 739, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v15);
          v12 = 50;
          goto LABEL_31;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_31;
        v18 = 740;
      }
    }
    WPP_SF_DD(*((_QWORD *)v17 + 2), v18, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, v15, ListNode);
    goto LABEL_31;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v14 = 736;
LABEL_6:
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids, InnerConnectionData);
  }
LABEL_31:
  LocalFree(hMem);
  PeapEapInfoFreeList(v28);
  return v12;
}

```

## disassembly

```asm
0x18005892c  push    rbp
0x18005892e  push    rbx
0x18005892f  push    rsi
0x180058930  push    rdi
0x180058931  push    r12
0x180058933  push    r13
0x180058935  push    r14
0x180058937  push    r15
0x180058939  mov     rbp, rsp
0x18005893c  sub     rsp, 78h
0x180058940  xor     esi, esi
0x180058942  xorps   xmm0, xmm0
0x180058945  mov     [rbp+var_28], rsi
0x180058949  mov     ebx, r9d
0x18005894c  mov     [rbp+var_20], rsi
0x180058950  mov     rdi, r8
0x180058953  mov     [rbp+hMem], rsi
0x180058957  mov     r15d, edx
0x18005895a  mov     [rbp+var_34], esi
0x18005895d  mov     r12, rcx
0x180058960  mov     [rbp+var_38], esi
0x180058963  movups  xmmword ptr [rbp+var_18.dwVersion], xmm0
0x180058967  mov     rcx, cs:WPP_GLOBAL_Control
0x18005896e  lea     r13, WPP_GLOBAL_Control
0x180058975  lea     r14, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x18005897c  cmp     rcx, r13
0x18005897f  jz      short loc_180058992
0x180058981  mov     rcx, [rcx+10h]
0x180058985  mov     edx, 2DFh
0x18005898a  mov     r8, r14
0x18005898d  call    WPP_SF_
0x180058992  lea     rax, [rbp+var_34]
0x180058996  mov     r8, rdi; unsigned __int8 *
0x180058999  mov     [rsp+78h+var_50], rax; unsigned int *
0x18005899e  lea     r9, [rbp+var_38]; unsigned int *
0x1800589a2  lea     rax, [rbp+hMem]
0x1800589a6  mov     edx, ebx; unsigned int
0x1800589a8  mov     ecx, r15d; unsigned int
0x1800589ab  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x1800589b0  call    ?GetInnerConnectionData@@YAKKKPEAEPEAKPEAPEAE1@Z; GetInnerConnectionData(ulong,ulong,uchar *,ulong *,uchar * *,ulong *)
0x1800589b5  mov     ebx, eax
0x1800589b7  test    eax, eax
0x1800589b9  jz      short loc_1800589E4
0x1800589bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800589c2  cmp     rcx, r13
0x1800589c5  jz      loc_180058BB4
0x1800589cb  mov     edx, 2E0h
0x1800589d0  mov     rcx, [rcx+10h]
0x1800589d4  mov     r9d, eax
0x1800589d7  mov     r8, r14
0x1800589da  call    WPP_SF_d
0x1800589df  jmp     loc_180058BB4
0x1800589e4  lea     r8, [rbp+var_28]; struct _PEAP_EAP_INFO **
0x1800589e8  call    ?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)
0x1800589ed  mov     ebx, eax
0x1800589ef  test    eax, eax
0x1800589f1  jz      short loc_180058A0A
0x1800589f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800589fa  cmp     rcx, r13
0x1800589fd  jz      loc_180058BB4
0x180058a03  mov     edx, 2E1h
0x180058a08  jmp     short loc_1800589D0
0x180058a0a  mov     edi, [rbp+var_38]
0x180058a0d  lea     r8, [rbp+var_20]; struct _PEAP_EAP_INFO **
0x180058a11  mov     rdx, [rbp+var_28]; struct _PEAP_EAP_INFO *
0x180058a15  mov     ecx, edi; unsigned int
0x180058a17  call    ?PeapEapInfoFindListNode@@YAKKPEAU_PEAP_EAP_INFO@@PEAPEAU1@@Z; PeapEapInfoFindListNode(ulong,_PEAP_EAP_INFO *,_PEAP_EAP_INFO * *)
0x180058a1c  mov     ebx, eax
0x180058a1e  test    eax, eax
0x180058a20  jz      short loc_180058A4F
0x180058a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180058a29  cmp     rcx, r13
0x180058a2c  jz      loc_180058BB4
0x180058a32  mov     edx, 2E2h
0x180058a37  mov     r8, r14
0x180058a3a  mov     rcx, [rcx+10h]
0x180058a3e  mov     r9d, edi
0x180058a41  mov     dword ptr [rsp+78h+var_58], eax
0x180058a45  call    WPP_SF_DD
0x180058a4a  jmp     loc_180058BB4
0x180058a4f  mov     rbx, [rbp+var_20]
0x180058a53  lea     rdx, aRaseapquerycre_0; "RasEapQueryCredentialInputFields"
0x180058a5a  mov     rcx, [rbx+50h]; hModule
0x180058a5e  call    cs:__imp_GetProcAddress
0x180058a65  nop     dword ptr [rax+rax+00h]
0x180058a6a  mov     r14, rax
0x180058a6d  test    rax, rax
0x180058a70  jnz     short loc_180058AD4
0x180058a72  call    cs:__imp_GetLastError
0x180058a79  nop     dword ptr [rax+rax+00h]
0x180058a7e  mov     ebx, eax
0x180058a80  cmp     eax, 7Fh
0x180058a83  jnz     short loc_180058AB3
0x180058a85  mov     rcx, cs:WPP_GLOBAL_Control
0x180058a8c  cmp     rcx, r13
0x180058a8f  jz      short loc_180058AA9
0x180058a91  mov     rcx, [rcx+10h]
0x180058a95  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180058a9c  mov     edx, 2E3h
0x180058aa1  mov     r9d, edi
0x180058aa4  call    WPP_SF_d
0x180058aa9  mov     ebx, 32h ; '2'
0x180058aae  jmp     loc_180058BB4
0x180058ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180058aba  cmp     rcx, r13
0x180058abd  jz      loc_180058BB4
0x180058ac3  mov     edx, 2E4h
0x180058ac8  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180058acf  jmp     loc_180058A3A
0x180058ad4  mov     rcx, [rbx+50h]; hModule
0x180058ad8  lea     rdx, ProcName; "RasEapFreeMemory"
0x180058adf  call    cs:__imp_GetProcAddress
0x180058ae6  nop     dword ptr [rax+rax+00h]
0x180058aeb  mov     rsi, rax
0x180058aee  test    rax, rax
0x180058af1  jnz     short loc_180058B18
0x180058af3  call    cs:__imp_GetLastError
0x180058afa  nop     dword ptr [rax+rax+00h]
0x180058aff  mov     ebx, eax
0x180058b01  mov     rcx, cs:WPP_GLOBAL_Control
0x180058b08  cmp     rcx, r13
0x180058b0b  jz      loc_180058BB4
0x180058b11  mov     edx, 2E5h
0x180058b16  jmp     short loc_180058AC8
0x180058b18  mov     r9, [rbp+hMem]
0x180058b1c  lea     rax, [rbp+var_18]
0x180058b20  mov     [rsp+78h+var_50], rax
0x180058b25  bts     r15d, 10h
0x180058b2a  mov     eax, [rbp+var_34]
0x180058b2d  mov     r8d, r15d
0x180058b30  mov     dword ptr [rsp+78h+var_58], eax
0x180058b34  mov     rdx, r12
0x180058b37  mov     rax, r14
0x180058b3a  mov     ecx, edi
0x180058b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b41  mov     ebx, eax
0x180058b43  test    eax, eax
0x180058b45  jz      short loc_180058B71
0x180058b47  mov     rcx, cs:WPP_GLOBAL_Control
0x180058b4e  cmp     rcx, r13
0x180058b51  jz      short loc_180058BA8
0x180058b53  mov     rcx, [rcx+10h]
0x180058b57  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180058b5e  mov     edx, 2E6h
0x180058b63  mov     dword ptr [rsp+78h+var_58], eax
0x180058b67  mov     r9d, edi
0x180058b6a  call    WPP_SF_DD
0x180058b6f  jmp     short loc_180058BA8
0x180058b71  mov     rcx, [rbp+arg_20]
0x180058b75  lea     rdx, [rbp+var_18]
0x180058b79  call    CopyEAPConfigInputFieldArray
0x180058b7e  mov     ebx, eax
0x180058b80  test    eax, eax
0x180058b82  jz      short loc_180058BA8
0x180058b84  mov     rcx, cs:WPP_GLOBAL_Control
0x180058b8b  cmp     rcx, r13
0x180058b8e  jz      short loc_180058BA8
0x180058b90  mov     rcx, [rcx+10h]
0x180058b94  lea     r8, WPP_eb8ccc023461353daee6fb3f53c7a16f_Traceguids
0x180058b9b  mov     edx, 2E7h
0x180058ba0  mov     r9d, eax
0x180058ba3  call    WPP_SF_d
0x180058ba8  mov     rdx, rsi; unsigned int (*)(unsigned __int8 *)
0x180058bab  lea     rcx, [rbp+var_18]; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x180058baf  call    ?FreeEAPConfigInputFieldArray@@YAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x180058bb4  mov     rcx, [rbp+hMem]; hMem
0x180058bb8  call    cs:__imp_LocalFree
0x180058bbf  nop     dword ptr [rax+rax+00h]
0x180058bc4  mov     rcx, [rbp+var_28]; hMem
0x180058bc8  call    ?PeapEapInfoFreeList@@YAXPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoFreeList(_PEAP_EAP_INFO *)
0x180058bcd  mov     eax, ebx
0x180058bcf  add     rsp, 78h
0x180058bd3  pop     r15
0x180058bd5  pop     r14
0x180058bd7  pop     r13
0x180058bd9  pop     r12
0x180058bdb  pop     rdi
0x180058bdc  pop     rsi
0x180058bdd  pop     rbx
0x180058bde  pop     rbp
0x180058bdf  retn
```
