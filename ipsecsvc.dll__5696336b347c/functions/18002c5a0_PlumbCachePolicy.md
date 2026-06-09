# PlumbCachePolicy

- ea: `0x18002c5a0`
- end: `0x18002c9a9`
- name: `PlumbCachePolicy`
- size: `1033`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x180001590`

## callees

- `0x180006f60`
- `0x1800080e0`
- `0x180008280`
- `0x180008f04`
- `0x18000b29c`
- `0x18000c904`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x18002ba44`
- `0x18002c0b4`
- `0x18002c5a0`
- `0x18002da6c`
- `0x18003c2d4`
- `0x180042e20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002c5ee`
- `ntdll!EtwEventWrite` at `0x18002c851`
- `ntdll!EtwEventWrite` at `0x18002c989`
- `ntdll!EtwEventWrite` at `0x18002c5ee`
- `ntdll!EtwEventWrite` at `0x18002c851`
- `ntdll!EtwEventWrite` at `0x18002c989`

## pseudocode

```c
__int64 __fastcall PlumbCachePolicy(__int64 a1)
{
  LPVOID *v1; // rsi
  __int64 v2; // rbx
  unsigned int v4; // r12d
  DWORD CachePolicyDN; // eax
  unsigned __int16 *v6; // r14
  DWORD dwMessageId; // edi
  int v8; // r13d
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  DWORD v11; // eax
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  LPVOID *v16; // rcx
  _DWORD *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  void *v21; // rcx
  DWORD v22; // edi
  int v23; // r8d
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD v25; // [rsp+98h] [rbp+48h] BYREF
  LPVOID *v26; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v27; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  lpMem[0] = 0;
  v2 = 0;
  v26 = 0;
  v27 = 0;
  v25 = 0;
  v4 = 1;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyCachePolicy_Begin, 0, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  CachePolicyDN = GetCachePolicyDN(lpMem);
  v6 = (unsigned __int16 *)lpMem[0];
  dwMessageId = CachePolicyDN;
  if ( CachePolicyDN )
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_34;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_31;
    v10 = 43;
    goto LABEL_29;
  }
  v8 = 1;
  v11 = LoadCachePolicy((int)lpMem[0], &v26);
  dwMessageId = v11;
  if ( v11 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v1 = v26;
      goto LABEL_34;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v11);
      v1 = v26;
LABEL_30:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    v1 = v26;
    goto LABEL_31;
  }
  v1 = v26;
  v12 = ProcessNFAs(v26, 0, &v25, &v27);
  dwMessageId = v12;
  if ( v12 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v2 = v27;
      goto LABEL_34;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v12);
      v2 = v27;
      goto LABEL_30;
    }
    v2 = v27;
LABEL_31:
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x10) != 0 )
      WPP_SF_(v9[2], 51, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    goto LABEL_34;
  }
  v2 = v27;
  dwMessageId = AddPolicyInformation(v27, 4);
  if ( dwMessageId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    DeletePolicyInformation(v2);
    v4 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_34:
      SetSpdStateOnError(4, v4, dwMessageId, a1);
      if ( v8 )
      {
        if ( !v6 )
        {
LABEL_39:
          if ( v1 )
            FreeIpsecPolicyObject(v1);
          if ( v2 )
            FreeIpsecPolicyData((_DWORD *)v2);
          if ( g_Provider )
            EtwEventWrite(g_Provider, IPSEC_SVC_ApplyCachePolicy_End, 0, 0);
          return dwMessageId;
        }
        AuditIPSecPolicyErrorEventOld(v14, v13, 0x4BAD0004u, v6, dwMessageId);
      }
      if ( v6 )
        IpsecFreeMem(v6);
      goto LABEL_39;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 47;
LABEL_29:
      WPP_SF_d(v9[2], v10, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  v16 = *(LPVOID **)(a1 + 32);
  if ( v16 )
    FreeIpsecPolicyObject(v16);
  v17 = *(_DWORD **)(a1 + 40);
  if ( v17 )
    FreeIpsecPolicyData(v17);
  v18 = *(void **)(a1 + 8);
  if ( v18 )
    IpsecFreeMem(v18);
  *(_QWORD *)(a1 + 32) = v1;
  *(_QWORD *)(a1 + 40) = v2;
  *(_QWORD *)(a1 + 8) = v6;
  SetSpdStateOnError(4, 0, 0, a1);
  v20 = *(unsigned int *)(v2 + 16);
  *(_DWORD *)(a1 + 16) = v20;
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 28) = *(_DWORD *)(v2 + 44);
  gCurrentPollingInterval = v20;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v20);
  v22 = v25;
  if ( v25 )
  {
    AuditIPSecPolicyErrorEventOld((__int64)v21, v19, 0x4BAD0007u, *(unsigned __int16 **)(v2 + 48), v25);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v22);
  }
  AuditIPSecPolicyEventOld(v21, v19, 1269628931, *(_QWORD *)(v2 + 48));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v23, *(_QWORD *)(v2 + 48), *(_QWORD *)(a1 + 8));
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyCachePolicy_End, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18002c5a0  mov     [rsp-38h+arg_0], rbx
0x18002c5a5  push    rbp
0x18002c5a6  push    rsi
0x18002c5a7  push    rdi
0x18002c5a8  push    r12
0x18002c5aa  push    r13
0x18002c5ac  push    r14
0x18002c5ae  push    r15
0x18002c5b0  mov     rbp, rsp
0x18002c5b3  sub     rsp, 50h
0x18002c5b7  xor     esi, esi
0x18002c5b9  mov     [rbp+lpMem], 0
0x18002c5c1  xor     ebx, ebx
0x18002c5c3  mov     [rbp+arg_10], rsi
0x18002c5c7  mov     r15, rcx
0x18002c5ca  mov     [rbp+arg_18], rbx
0x18002c5ce  mov     rcx, cs:g_Provider
0x18002c5d5  mov     [rbp+arg_8], ebx
0x18002c5d8  lea     r12d, [rsi+1]
0x18002c5dc  test    rcx, rcx
0x18002c5df  jz      short loc_18002C5F4
0x18002c5e1  xor     r9d, r9d
0x18002c5e4  lea     rdx, IPSEC_SVC_ApplyCachePolicy_Begin
0x18002c5eb  xor     r8d, r8d
0x18002c5ee  call    cs:__imp_EtwEventWrite
0x18002c5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5fb  lea     rax, WPP_GLOBAL_Control
0x18002c602  cmp     rcx, rax
0x18002c605  jz      short loc_18002C622
0x18002c607  test    byte ptr [rcx+1Ch], 4
0x18002c60b  jz      short loc_18002C622
0x18002c60d  mov     rcx, [rcx+10h]
0x18002c611  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c618  mov     edx, 2Ah ; '*'
0x18002c61d  call    WPP_SF_
0x18002c622  lea     rcx, [rbp+lpMem]
0x18002c626  call    GetCachePolicyDN
0x18002c62b  mov     r14, [rbp+lpMem]
0x18002c62f  mov     edi, eax
0x18002c631  test    eax, eax
0x18002c633  jz      short loc_18002C662
0x18002c635  xor     r13d, r13d
0x18002c638  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c63f  lea     rax, WPP_GLOBAL_Control
0x18002c646  cmp     rcx, rax
0x18002c649  jz      loc_18002C7E2
0x18002c64f  test    byte ptr [rcx+1Ch], 10h
0x18002c653  jz      loc_18002C7C2
0x18002c659  lea     edx, [r13+2Bh]
0x18002c65d  jmp     loc_18002C7A1
0x18002c662  lea     rdx, [rbp+arg_10]
0x18002c666  mov     rcx, r14
0x18002c669  mov     r13d, r12d
0x18002c66c  call    LoadCachePolicy
0x18002c671  mov     edi, eax
0x18002c673  test    eax, eax
0x18002c675  jz      short loc_18002C6C3
0x18002c677  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c67e  lea     rsi, WPP_GLOBAL_Control
0x18002c685  cmp     rcx, rsi
0x18002c688  jz      short loc_18002C6BA
0x18002c68a  test    byte ptr [rcx+1Ch], 10h
0x18002c68e  jz      short loc_18002C6B1
0x18002c690  mov     rcx, [rcx+10h]
0x18002c694  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c69b  mov     edx, 2Ch ; ','
0x18002c6a0  mov     r9d, eax
0x18002c6a3  call    WPP_SF_d
0x18002c6a8  mov     rsi, [rbp+arg_10]
0x18002c6ac  jmp     loc_18002C7B4
0x18002c6b1  mov     rsi, [rbp+arg_10]
0x18002c6b5  jmp     loc_18002C7BB
0x18002c6ba  mov     rsi, [rbp+arg_10]
0x18002c6be  jmp     loc_18002C7E2
0x18002c6c3  mov     rsi, [rbp+arg_10]
0x18002c6c7  lea     r9, [rbp+arg_18]
0x18002c6cb  mov     rcx, rsi
0x18002c6ce  lea     r8, [rbp+arg_8]
0x18002c6d2  xor     edx, edx
0x18002c6d4  call    ProcessNFAs
0x18002c6d9  mov     edi, eax
0x18002c6db  test    eax, eax
0x18002c6dd  jz      short loc_18002C72B
0x18002c6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c6e6  lea     rbx, WPP_GLOBAL_Control
0x18002c6ed  cmp     rcx, rbx
0x18002c6f0  jz      short loc_18002C722
0x18002c6f2  test    byte ptr [rcx+1Ch], 10h
0x18002c6f6  jz      short loc_18002C719
0x18002c6f8  mov     rcx, [rcx+10h]
0x18002c6fc  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c703  mov     edx, 2Dh ; '-'
0x18002c708  mov     r9d, eax
0x18002c70b  call    WPP_SF_d
0x18002c710  mov     rbx, [rbp+arg_18]
0x18002c714  jmp     loc_18002C7B4
0x18002c719  mov     rbx, [rbp+arg_18]
0x18002c71d  jmp     loc_18002C7BB
0x18002c722  mov     rbx, [rbp+arg_18]
0x18002c726  jmp     loc_18002C7E2
0x18002c72b  mov     rbx, [rbp+arg_18]
0x18002c72f  mov     r12d, 4
0x18002c735  mov     edx, r12d
0x18002c738  mov     rcx, rbx
0x18002c73b  call    AddPolicyInformation
0x18002c740  mov     edi, eax
0x18002c742  test    eax, eax
0x18002c744  jz      loc_18002C85E
0x18002c74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c751  lea     rax, WPP_GLOBAL_Control
0x18002c758  cmp     rcx, rax
0x18002c75b  jz      short loc_18002C778
0x18002c75d  test    [rcx+1Ch], r12b
0x18002c761  jz      short loc_18002C778
0x18002c763  mov     rcx, [rcx+10h]
0x18002c767  lea     edx, [r12+2Ah]
0x18002c76c  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c773  call    WPP_SF_
0x18002c778  mov     rcx, rbx
0x18002c77b  call    DeletePolicyInformation
0x18002c780  xor     r12d, r12d
0x18002c783  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c78a  lea     rax, WPP_GLOBAL_Control
0x18002c791  cmp     rcx, rax
0x18002c794  jz      short loc_18002C7E2
0x18002c796  test    byte ptr [rcx+1Ch], 10h
0x18002c79a  jz      short loc_18002C7C2
0x18002c79c  lea     edx, [r12+2Fh]
0x18002c7a1  mov     rcx, [rcx+10h]
0x18002c7a5  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c7ac  mov     r9d, edi
0x18002c7af  call    WPP_SF_d
0x18002c7b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c7bb  lea     rax, WPP_GLOBAL_Control
0x18002c7c2  cmp     rcx, rax
0x18002c7c5  jz      short loc_18002C7E2
0x18002c7c7  test    byte ptr [rcx+1Ch], 10h
0x18002c7cb  jz      short loc_18002C7E2
0x18002c7cd  mov     rcx, [rcx+10h]
0x18002c7d1  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c7d8  mov     edx, 33h ; '3'
0x18002c7dd  call    WPP_SF_
0x18002c7e2  mov     r9, r15
0x18002c7e5  mov     r8d, edi
0x18002c7e8  mov     edx, r12d
0x18002c7eb  mov     ecx, 4
0x18002c7f0  call    SetSpdStateOnError
0x18002c7f5  test    r13d, r13d
0x18002c7f8  jz      short loc_18002C811
0x18002c7fa  test    r14, r14
0x18002c7fd  jz      short loc_18002C81E
0x18002c7ff  mov     r9, r14; int
0x18002c802  mov     [rsp+50h+dwMessageId], edi; dwMessageId
0x18002c806  mov     r8d, 4BAD0004h; int
0x18002c80c  call    AuditIPSecPolicyErrorEventOld
0x18002c811  test    r14, r14
0x18002c814  jz      short loc_18002C81E
0x18002c816  mov     rcx, r14; lpMem
0x18002c819  call    IpsecFreeMem
0x18002c81e  test    rsi, rsi
0x18002c821  jz      short loc_18002C82B
0x18002c823  mov     rcx, rsi; lpMem
0x18002c826  call    FreeIpsecPolicyObject
0x18002c82b  test    rbx, rbx
0x18002c82e  jz      short loc_18002C838
0x18002c830  mov     rcx, rbx; lpMem
0x18002c833  call    FreeIpsecPolicyData
0x18002c838  mov     rcx, cs:g_Provider
0x18002c83f  test    rcx, rcx
0x18002c842  jz      short loc_18002C857
0x18002c844  xor     r9d, r9d
0x18002c847  lea     rdx, IPSEC_SVC_ApplyCachePolicy_End
0x18002c84e  xor     r8d, r8d
0x18002c851  call    cs:__imp_EtwEventWrite
0x18002c857  mov     eax, edi
0x18002c859  jmp     loc_18002C991
0x18002c85e  mov     rcx, [r15+20h]; lpMem
0x18002c862  test    rcx, rcx
0x18002c865  jz      short loc_18002C86C
0x18002c867  call    FreeIpsecPolicyObject
0x18002c86c  mov     rcx, [r15+28h]; lpMem
0x18002c870  test    rcx, rcx
0x18002c873  jz      short loc_18002C87A
0x18002c875  call    FreeIpsecPolicyData
0x18002c87a  mov     rcx, [r15+8]; lpMem
0x18002c87e  test    rcx, rcx
0x18002c881  jz      short loc_18002C888
0x18002c883  call    IpsecFreeMem
0x18002c888  mov     r9, r15
0x18002c88b  mov     [r15+20h], rsi
0x18002c88f  xor     r8d, r8d
0x18002c892  mov     [r15+28h], rbx
0x18002c896  xor     edx, edx
0x18002c898  mov     [r15+8], r14
0x18002c89c  mov     ecx, r12d
0x18002c89f  call    SetSpdStateOnError
0x18002c8a4  mov     r9d, [rbx+10h]
0x18002c8a8  mov     [r15+10h], r9d
0x18002c8ac  mov     dword ptr [r15+18h], 0
0x18002c8b4  mov     eax, [rbx+2Ch]
0x18002c8b7  mov     [r15+1Ch], eax
0x18002c8bb  mov     cs:gCurrentPollingInterval, r9d
0x18002c8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8c9  lea     rsi, WPP_GLOBAL_Control
0x18002c8d0  cmp     rcx, rsi
0x18002c8d3  jz      short loc_18002C8F0
0x18002c8d5  test    [rcx+1Ch], r12b
0x18002c8d9  jz      short loc_18002C8F0
0x18002c8db  mov     rcx, [rcx+10h]
0x18002c8df  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c8e6  mov     edx, 30h ; '0'
0x18002c8eb  call    WPP_SF_d
0x18002c8f0  mov     edi, [rbp+arg_8]
0x18002c8f3  test    edi, edi
0x18002c8f5  jz      short loc_18002C934
0x18002c8f7  mov     r9, [rbx+30h]; int
0x18002c8fb  mov     r8d, 4BAD0007h; int
0x18002c901  mov     [rsp+50h+dwMessageId], edi; dwMessageId
0x18002c905  call    AuditIPSecPolicyErrorEventOld
0x18002c90a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c911  cmp     rcx, rsi
0x18002c914  jz      short loc_18002C934
0x18002c916  test    byte ptr [rcx+1Ch], 8
0x18002c91a  jz      short loc_18002C934
0x18002c91c  mov     rcx, [rcx+10h]
0x18002c920  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c927  mov     edx, 31h ; '1'
0x18002c92c  mov     r9d, edi
0x18002c92f  call    WPP_SF_d
0x18002c934  mov     r9, [rbx+30h]
0x18002c938  mov     r8d, 4BAD0003h
0x18002c93e  call    AuditIPSecPolicyEventOld
0x18002c943  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c94a  cmp     rcx, rsi
0x18002c94d  jz      short loc_18002C970
0x18002c94f  test    [rcx+1Ch], r12b
0x18002c953  jz      short loc_18002C970
0x18002c955  mov     rax, [r15+8]
0x18002c959  mov     edx, 32h ; '2'
0x18002c95e  mov     r9, [rbx+30h]
0x18002c962  mov     rcx, [rcx+10h]
0x18002c966  mov     qword ptr [rsp+50h+dwMessageId], rax
0x18002c96b  call    WPP_SF_SS
0x18002c970  mov     rcx, cs:g_Provider
0x18002c977  test    rcx, rcx
0x18002c97a  jz      short loc_18002C98F
0x18002c97c  xor     r9d, r9d
0x18002c97f  lea     rdx, IPSEC_SVC_ApplyCachePolicy_End
0x18002c986  xor     r8d, r8d
0x18002c989  call    cs:__imp_EtwEventWrite
0x18002c98f  xor     eax, eax
0x18002c991  mov     rbx, [rsp+50h+arg_0]
0x18002c999  add     rsp, 50h
0x18002c99d  pop     r15
0x18002c99f  pop     r14
0x18002c9a1  pop     r13
0x18002c9a3  pop     r12
0x18002c9a5  pop     rdi
0x18002c9a6  pop     rsi
0x18002c9a7  pop     rbp
0x18002c9a8  retn
```
