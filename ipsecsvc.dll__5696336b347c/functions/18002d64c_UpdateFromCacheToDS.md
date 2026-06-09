# UpdateFromCacheToDS

- ea: `0x18002d64c`
- end: `0x18002d8be`
- name: `UpdateFromCacheToDS`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update`

## callers

- `0x18002ce78`

## callees

- `0x180006f60`
- `0x180007160`
- `0x180008280`
- `0x18000acb4`
- `0x18000afe8`
- `0x18000c904`
- `0x18000cb1c`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x18002c1ec`
- `0x18002d64c`
- `0x18002d8c4`
- `0x180035714`
- `0x180036f00`
- `0x18003c2d4`
- `0x180042e20`

## pseudocode

```c
__int64 __fastcall UpdateFromCacheToDS(__int64 a1)
{
  LPVOID *v1; // rdi
  _DWORD *v2; // rsi
  unsigned int DirectoryPolicyDN; // eax
  void *v5; // r15
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned __int16 **v10; // rsi
  int updated; // eax
  LPVOID *v12; // rcx
  int v13; // ebx
  _DWORD *v14; // rcx
  void *v15; // rcx
  int v16; // ecx
  unsigned int v17; // edi
  __int64 v18; // rdx
  void *v19; // rcx
  DWORD v20; // ebx
  LPVOID lpMem[2]; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwMessageId; // [rsp+98h] [rbp+48h] BYREF
  LPVOID *v23; // [rsp+A0h] [rbp+50h] BYREF
  _DWORD *v24; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  lpMem[0] = 0;
  v2 = 0;
  v23 = 0;
  v24 = 0;
  dwMessageId = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  DirectoryPolicyDN = GetDirectoryPolicyDN((__int64 *)lpMem);
  v5 = lpMem[0];
  v6 = DirectoryPolicyDN;
  if ( DirectoryPolicyDN )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        115,
        WPP_e815f316f4bb38f383997e5feee741ae_Traceguids,
        DirectoryPolicyDN);
LABEL_18:
    if ( v5 )
      IpsecFreeMem(v5);
    if ( v1 )
      FreeIpsecPolicyObject(v1);
    if ( v2 )
      FreeIpsecPolicyData(v2);
    return v6;
  }
  v7 = LoadDirectoryPolicy((__int64)lpMem[0], &v23);
  v6 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v7);
    v1 = v23;
    goto LABEL_18;
  }
  v1 = v23;
  v8 = ProcessNFAs(v23, 1, &dwMessageId, &v24);
  v6 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v8);
    v2 = v24;
    goto LABEL_18;
  }
  v10 = (unsigned __int16 **)v24;
  updated = UpdatePolicyInformation(*(_QWORD *)(a1 + 40), v24, 3);
  v12 = *(LPVOID **)(a1 + 32);
  v13 = updated;
  if ( v12 )
    FreeIpsecPolicyObject(v12);
  v14 = *(_DWORD **)(a1 + 40);
  if ( v14 )
    FreeIpsecPolicyData(v14);
  v15 = *(void **)(a1 + 8);
  if ( v15 )
    IpsecFreeMem(v15);
  DeleteRegistryCache();
  CacheDirectorytoRegistry((__int64)v1);
  *(_QWORD *)(a1 + 32) = v1;
  *(_QWORD *)(a1 + 40) = v10;
  *(_QWORD *)(a1 + 8) = v5;
  SetSpdStateOnError(3, 0, 0, a1);
  v16 = *((_DWORD *)v10 + 4);
  *(_DWORD *)(a1 + 16) = v16;
  *(_QWORD *)(a1 + 24) = *((unsigned int *)v10 + 11);
  gCurrentPollingInterval = v16;
  if ( v13 || !gbUpdatedAuthMethods )
  {
    NotifyIpsecPolicyChange();
    v20 = dwMessageId;
    v17 = 0;
    if ( dwMessageId )
    {
      AuditIPSecPolicyErrorEventOld((__int64)v19, v18, 0x4BAD0007u, v10[6], dwMessageId);
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v20);
    }
    AuditEventOld((__int64)v19, v18, 0x4BAD000Eu, 0, 0, 1u);
  }
  else
  {
    return (unsigned int)OnPolicyChanged(a1);
  }
  return v17;
}

```

## disassembly

```asm
0x18002d64c  push    rbp
0x18002d64e  push    rbx
0x18002d64f  push    rsi
0x18002d650  push    rdi
0x18002d651  push    r13
0x18002d653  push    r14
0x18002d655  push    r15
0x18002d657  mov     rbp, rsp
0x18002d65a  sub     rsp, 50h
0x18002d65e  xor     edi, edi
0x18002d660  mov     [rbp+lpMem], 0
0x18002d668  xor     esi, esi
0x18002d66a  mov     [rbp+arg_10], rdi
0x18002d66e  mov     [rbp+arg_18], rsi
0x18002d672  mov     r14, rcx
0x18002d675  mov     [rbp+arg_8], esi
0x18002d678  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d67f  lea     r13, WPP_GLOBAL_Control
0x18002d686  cmp     rcx, r13
0x18002d689  jz      short loc_18002D6A4
0x18002d68b  test    byte ptr [rcx+1Ch], 4
0x18002d68f  jz      short loc_18002D6A4
0x18002d691  mov     rcx, [rcx+10h]
0x18002d695  lea     edx, [rdi+72h]
0x18002d698  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d69f  call    WPP_SF_
0x18002d6a4  lea     rcx, [rbp+lpMem]
0x18002d6a8  call    GetDirectoryPolicyDN
0x18002d6ad  mov     r15, [rbp+lpMem]
0x18002d6b1  mov     ebx, eax
0x18002d6b3  test    eax, eax
0x18002d6b5  jz      short loc_18002D6EE
0x18002d6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6be  cmp     rcx, r13
0x18002d6c1  jz      loc_18002D77D
0x18002d6c7  test    byte ptr [rcx+1Ch], 10h
0x18002d6cb  jz      loc_18002D77D
0x18002d6d1  mov     rcx, [rcx+10h]
0x18002d6d5  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d6dc  mov     edx, 73h ; 's'
0x18002d6e1  mov     r9d, eax
0x18002d6e4  call    WPP_SF_d
0x18002d6e9  jmp     loc_18002D77D
0x18002d6ee  lea     rdx, [rbp+arg_10]
0x18002d6f2  mov     rcx, r15; int
0x18002d6f5  call    LoadDirectoryPolicy
0x18002d6fa  mov     ebx, eax
0x18002d6fc  test    eax, eax
0x18002d6fe  jz      short loc_18002D730
0x18002d700  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d707  cmp     rcx, r13
0x18002d70a  jz      short loc_18002D72A
0x18002d70c  test    byte ptr [rcx+1Ch], 10h
0x18002d710  jz      short loc_18002D72A
0x18002d712  mov     rcx, [rcx+10h]
0x18002d716  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d71d  mov     edx, 74h ; 't'
0x18002d722  mov     r9d, eax
0x18002d725  call    WPP_SF_d
0x18002d72a  mov     rdi, [rbp+arg_10]
0x18002d72e  jmp     short loc_18002D77D
0x18002d730  mov     rdi, [rbp+arg_10]
0x18002d734  lea     r9, [rbp+arg_18]
0x18002d738  mov     rcx, rdi
0x18002d73b  lea     r8, [rbp+arg_8]
0x18002d73f  mov     edx, 1
0x18002d744  call    ProcessNFAs
0x18002d749  mov     ebx, eax
0x18002d74b  test    eax, eax
0x18002d74d  jz      short loc_18002D7AB
0x18002d74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d756  cmp     rcx, r13
0x18002d759  jz      short loc_18002D779
0x18002d75b  test    byte ptr [rcx+1Ch], 10h
0x18002d75f  jz      short loc_18002D779
0x18002d761  mov     rcx, [rcx+10h]
0x18002d765  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d76c  mov     edx, 75h ; 'u'
0x18002d771  mov     r9d, eax
0x18002d774  call    WPP_SF_d
0x18002d779  mov     rsi, [rbp+arg_18]
0x18002d77d  test    r15, r15
0x18002d780  jz      short loc_18002D78A
0x18002d782  mov     rcx, r15; lpMem
0x18002d785  call    IpsecFreeMem
0x18002d78a  test    rdi, rdi
0x18002d78d  jz      short loc_18002D797
0x18002d78f  mov     rcx, rdi; lpMem
0x18002d792  call    FreeIpsecPolicyObject
0x18002d797  test    rsi, rsi
0x18002d79a  jz      short loc_18002D7A4
0x18002d79c  mov     rcx, rsi; lpMem
0x18002d79f  call    FreeIpsecPolicyData
0x18002d7a4  mov     eax, ebx
0x18002d7a6  jmp     loc_18002D8AF
0x18002d7ab  mov     rsi, [rbp+arg_18]
0x18002d7af  mov     r8d, 3
0x18002d7b5  mov     rcx, [r14+28h]
0x18002d7b9  mov     rdx, rsi
0x18002d7bc  call    UpdatePolicyInformation
0x18002d7c1  mov     rcx, [r14+20h]; lpMem
0x18002d7c5  mov     ebx, eax
0x18002d7c7  test    rcx, rcx
0x18002d7ca  jz      short loc_18002D7D1
0x18002d7cc  call    FreeIpsecPolicyObject
0x18002d7d1  mov     rcx, [r14+28h]; lpMem
0x18002d7d5  test    rcx, rcx
0x18002d7d8  jz      short loc_18002D7DF
0x18002d7da  call    FreeIpsecPolicyData
0x18002d7df  mov     rcx, [r14+8]; lpMem
0x18002d7e3  test    rcx, rcx
0x18002d7e6  jz      short loc_18002D7ED
0x18002d7e8  call    IpsecFreeMem
0x18002d7ed  call    DeleteRegistryCache
0x18002d7f2  mov     rcx, rdi
0x18002d7f5  call    CacheDirectorytoRegistry
0x18002d7fa  xor     edx, edx
0x18002d7fc  mov     [r14+20h], rdi
0x18002d800  mov     r9, r14
0x18002d803  mov     [r14+28h], rsi
0x18002d807  xor     r8d, r8d
0x18002d80a  mov     [r14+8], r15
0x18002d80e  lea     ecx, [rdx+3]
0x18002d811  call    SetSpdStateOnError
0x18002d816  mov     ecx, [rsi+10h]
0x18002d819  mov     [r14+10h], ecx
0x18002d81d  mov     eax, [rsi+2Ch]
0x18002d820  mov     [r14+18h], eax
0x18002d824  mov     dword ptr [r14+1Ch], 0
0x18002d82c  mov     cs:gCurrentPollingInterval, ecx
0x18002d832  test    ebx, ebx
0x18002d834  jnz     short loc_18002D84A
0x18002d836  cmp     cs:gbUpdatedAuthMethods, ebx
0x18002d83c  jz      short loc_18002D84A
0x18002d83e  mov     rcx, r14
0x18002d841  call    OnPolicyChanged
0x18002d846  mov     edi, eax
0x18002d848  jmp     short loc_18002D8AD
0x18002d84a  call    NotifyIpsecPolicyChange
0x18002d84f  mov     ebx, [rbp+arg_8]
0x18002d852  xor     edi, edi
0x18002d854  test    ebx, ebx
0x18002d856  jz      short loc_18002D893
0x18002d858  mov     r9, [rsi+30h]; int
0x18002d85c  mov     r8d, 4BAD0007h; int
0x18002d862  mov     [rsp+50h+dwMessageId], ebx; dwMessageId
0x18002d866  call    AuditIPSecPolicyErrorEventOld
0x18002d86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d872  cmp     rcx, r13
0x18002d875  jz      short loc_18002D893
0x18002d877  test    byte ptr [rcx+1Ch], 8
0x18002d87b  jz      short loc_18002D893
0x18002d87d  mov     rcx, [rcx+10h]
0x18002d881  lea     edx, [rdi+76h]
0x18002d884  mov     r9d, ebx
0x18002d887  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002d88e  call    WPP_SF_d
0x18002d893  mov     [rsp+50h+var_28], 1
0x18002d89b  xor     r9d, r9d
0x18002d89e  mov     r8d, 4BAD000Eh
0x18002d8a4  mov     [rsp+50h+dwMessageId], edi
0x18002d8a8  call    AuditEventOld
0x18002d8ad  mov     eax, edi
0x18002d8af  add     rsp, 50h
0x18002d8b3  pop     r15
0x18002d8b5  pop     r14
0x18002d8b7  pop     r13
0x18002d8b9  pop     rdi
0x18002d8ba  pop     rsi
0x18002d8bb  pop     rbx
0x18002d8bc  pop     rbp
0x18002d8bd  retn
```
