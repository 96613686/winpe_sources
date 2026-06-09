# ApplyLoadedDirectoryPolicy

- ea: `0x18002b688`
- end: `0x18002b86a`
- name: `ApplyLoadedDirectoryPolicy`
- size: `482`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000adac`
- `0x18002c9b0`

## callees

- `0x1800080e0`
- `0x180008f04`
- `0x18000c904`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x18002b688`
- `0x18002da6c`
- `0x180035714`
- `0x180036f00`

## pseudocode

```c
__int64 __fastcall ApplyLoadedDirectoryPolicy(__int64 a1)
{
  __int64 v2; // rdi
  DWORD v3; // eax
  int v4; // r8d
  DWORD dwMessageId; // esi
  _QWORD *v6; // rcx
  int v7; // edx
  int v8; // ecx
  __int64 v10; // rdx
  __int64 v11; // r9
  void *v12; // rcx
  int v13; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  v2 = *(_QWORD *)(a1 + 40);
  v3 = AddPolicyInformation(v2, 3);
  dwMessageId = v3;
  if ( v3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v3);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x10) != 0 )
        WPP_SF_SS(v6[2], 41, v4, *(_QWORD *)(v2 + 48), *(_QWORD *)(a1 + 8));
    }
    SetSpdStateOnError(3, 0, dwMessageId, a1);
    AuditIPSecPolicyErrorEventOld(v8, v7, 1269628930, *(_QWORD *)(v2 + 48), dwMessageId);
    return dwMessageId;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    DeleteRegistryCache();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    CacheDirectorytoRegistry(*(_QWORD *)(a1 + 32));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    SetSpdStateOnError(3, 0, 0, a1);
    v11 = *(unsigned int *)(v2 + 16);
    *(_DWORD *)(a1 + 16) = v11;
    *(_QWORD *)(a1 + 24) = *(unsigned int *)(v2 + 44);
    gCurrentPollingInterval = v11;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v11);
    AuditIPSecPolicyEventOld(v12, v10, 1269628929, *(_QWORD *)(v2 + 48));
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v13, *(_QWORD *)(v2 + 48), *(_QWORD *)(a1 + 8));
    return 0;
  }
}

```

## disassembly

```asm
0x18002b688  push    rbx
0x18002b68a  push    rbp
0x18002b68b  push    rsi
0x18002b68c  push    rdi
0x18002b68d  push    r15
0x18002b68f  sub     rsp, 40h
0x18002b693  mov     rbx, rcx
0x18002b696  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b69d  lea     rbp, WPP_GLOBAL_Control
0x18002b6a4  lea     r15, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002b6ab  cmp     rcx, rbp
0x18002b6ae  jz      short loc_18002B6C7
0x18002b6b0  test    byte ptr [rcx+1Ch], 4
0x18002b6b4  jz      short loc_18002B6C7
0x18002b6b6  mov     rcx, [rcx+10h]
0x18002b6ba  mov     edx, 22h ; '"'
0x18002b6bf  mov     r8, r15
0x18002b6c2  call    WPP_SF_
0x18002b6c7  mov     rdi, [rbx+28h]
0x18002b6cb  mov     edx, 3
0x18002b6d0  mov     rcx, rdi
0x18002b6d3  call    AddPolicyInformation
0x18002b6d8  mov     esi, eax
0x18002b6da  test    eax, eax
0x18002b6dc  jz      short loc_18002B75B
0x18002b6de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6e5  cmp     rcx, rbp
0x18002b6e8  jz      short loc_18002B731
0x18002b6ea  test    byte ptr [rcx+1Ch], 10h
0x18002b6ee  jz      short loc_18002B70B
0x18002b6f0  mov     rcx, [rcx+10h]
0x18002b6f4  mov     edx, 23h ; '#'
0x18002b6f9  mov     r9d, eax
0x18002b6fc  mov     r8, r15
0x18002b6ff  call    WPP_SF_d
0x18002b704  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b70b  cmp     rcx, rbp
0x18002b70e  jz      short loc_18002B731
0x18002b710  test    byte ptr [rcx+1Ch], 10h
0x18002b714  jz      short loc_18002B731
0x18002b716  mov     rax, [rbx+8]
0x18002b71a  mov     edx, 29h ; ')'
0x18002b71f  mov     r9, [rdi+30h]
0x18002b723  mov     rcx, [rcx+10h]
0x18002b727  mov     qword ptr [rsp+68h+dwMessageId], rax
0x18002b72c  call    WPP_SF_SS
0x18002b731  xor     edx, edx
0x18002b733  mov     r9, rbx
0x18002b736  mov     r8d, esi
0x18002b739  lea     ecx, [rdx+3]
0x18002b73c  call    SetSpdStateOnError
0x18002b741  mov     r9, [rdi+30h]; int
0x18002b745  mov     r8d, 4BAD0002h; int
0x18002b74b  mov     [rsp+68h+dwMessageId], esi; dwMessageId
0x18002b74f  call    AuditIPSecPolicyErrorEventOld
0x18002b754  mov     eax, esi
0x18002b756  jmp     loc_18002B85F
0x18002b75b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b762  cmp     rcx, rbp
0x18002b765  jz      short loc_18002B77E
0x18002b767  test    byte ptr [rcx+1Ch], 4
0x18002b76b  jz      short loc_18002B77E
0x18002b76d  mov     rcx, [rcx+10h]
0x18002b771  mov     edx, 24h ; '$'
0x18002b776  mov     r8, r15
0x18002b779  call    WPP_SF_
0x18002b77e  call    DeleteRegistryCache
0x18002b783  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b78a  cmp     rcx, rbp
0x18002b78d  jz      short loc_18002B7A6
0x18002b78f  test    byte ptr [rcx+1Ch], 4
0x18002b793  jz      short loc_18002B7A6
0x18002b795  mov     rcx, [rcx+10h]
0x18002b799  mov     edx, 25h ; '%'
0x18002b79e  mov     r8, r15
0x18002b7a1  call    WPP_SF_
0x18002b7a6  mov     rcx, [rbx+20h]
0x18002b7aa  call    CacheDirectorytoRegistry
0x18002b7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7b6  cmp     rcx, rbp
0x18002b7b9  jz      short loc_18002B7D2
0x18002b7bb  test    byte ptr [rcx+1Ch], 4
0x18002b7bf  jz      short loc_18002B7D2
0x18002b7c1  mov     rcx, [rcx+10h]
0x18002b7c5  mov     edx, 26h ; '&'
0x18002b7ca  mov     r8, r15
0x18002b7cd  call    WPP_SF_
0x18002b7d2  xor     edx, edx
0x18002b7d4  mov     r9, rbx
0x18002b7d7  xor     r8d, r8d
0x18002b7da  lea     ecx, [rdx+3]
0x18002b7dd  call    SetSpdStateOnError
0x18002b7e2  mov     r9d, [rdi+10h]
0x18002b7e6  mov     [rbx+10h], r9d
0x18002b7ea  mov     eax, [rdi+2Ch]
0x18002b7ed  mov     [rbx+18h], eax
0x18002b7f0  mov     dword ptr [rbx+1Ch], 0
0x18002b7f7  mov     cs:gCurrentPollingInterval, r9d
0x18002b7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b805  cmp     rcx, rbp
0x18002b808  jz      short loc_18002B821
0x18002b80a  test    byte ptr [rcx+1Ch], 4
0x18002b80e  jz      short loc_18002B821
0x18002b810  mov     rcx, [rcx+10h]
0x18002b814  mov     edx, 27h ; '''
0x18002b819  mov     r8, r15
0x18002b81c  call    WPP_SF_d
0x18002b821  mov     r9, [rdi+30h]
0x18002b825  mov     r8d, 4BAD0001h
0x18002b82b  call    AuditIPSecPolicyEventOld
0x18002b830  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b837  cmp     rcx, rbp
0x18002b83a  jz      short loc_18002B85D
0x18002b83c  test    byte ptr [rcx+1Ch], 4
0x18002b840  jz      short loc_18002B85D
0x18002b842  mov     rax, [rbx+8]
0x18002b846  mov     edx, 28h ; '('
0x18002b84b  mov     r9, [rdi+30h]
0x18002b84f  mov     rcx, [rcx+10h]
0x18002b853  mov     qword ptr [rsp+68h+dwMessageId], rax
0x18002b858  call    WPP_SF_SS
0x18002b85d  xor     eax, eax
0x18002b85f  add     rsp, 40h
0x18002b863  pop     r15
0x18002b865  pop     rdi
0x18002b866  pop     rsi
0x18002b867  pop     rbp
0x18002b868  pop     rbx
0x18002b869  retn
```
