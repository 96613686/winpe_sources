# MigrateFromDSToCache

- ea: `0x18002c448`
- end: `0x18002c597`
- name: `MigrateFromDSToCache`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002cf74`

## callees

- `0x180006f60`
- `0x180007160`
- `0x18000c904`
- `0x18000e510`
- `0x18000f638`
- `0x18002ba44`
- `0x18002c448`

## pseudocode

```c
__int64 __fastcall MigrateFromDSToCache(__int64 a1)
{
  unsigned int CachePolicyDN; // eax
  unsigned int v3; // ebx
  void *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  void *v7; // rcx
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  CachePolicyDN = GetCachePolicyDN(&v9);
  v3 = CachePolicyDN;
  if ( CachePolicyDN )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, CachePolicyDN);
  }
  else
  {
    v4 = *(void **)(a1 + 8);
    if ( v4 )
      IpsecFreeMem(v4);
    *(_QWORD *)(a1 + 8) = v9;
    *(_DWORD *)(a1 + 28) = *(_DWORD *)(a1 + 24);
    *(_DWORD *)(a1 + 24) = 0;
    SetSpdStateOnError(4, 0, 0, a1);
    v6 = *(unsigned int *)(a1 + 16);
    gCurrentPollingInterval = *(_DWORD *)(a1 + 16);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v6);
    AuditEventOld((__int64)v7, v5, 0x4BAD000Cu, 0, 0, 1u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  }
  return v3;
}

```

## disassembly

```asm
0x18002c448  mov     [rsp+arg_0], rbx
0x18002c44d  mov     [rsp+arg_10], rdi
0x18002c452  push    r15
0x18002c454  sub     rsp, 40h
0x18002c458  mov     rdi, rcx
0x18002c45b  mov     [rsp+48h+arg_8], 0
0x18002c464  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c46b  lea     r15, WPP_GLOBAL_Control
0x18002c472  cmp     rcx, r15
0x18002c475  jz      short loc_18002C492
0x18002c477  test    byte ptr [rcx+1Ch], 4
0x18002c47b  jz      short loc_18002C492
0x18002c47d  mov     rcx, [rcx+10h]
0x18002c481  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c488  mov     edx, 6Ch ; 'l'
0x18002c48d  call    WPP_SF_
0x18002c492  lea     rcx, [rsp+48h+arg_8]
0x18002c497  call    GetCachePolicyDN
0x18002c49c  mov     ebx, eax
0x18002c49e  test    eax, eax
0x18002c4a0  jz      short loc_18002C4D9
0x18002c4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c4a9  cmp     rcx, r15
0x18002c4ac  jz      loc_18002C584
0x18002c4b2  test    byte ptr [rcx+1Ch], 10h
0x18002c4b6  jz      loc_18002C584
0x18002c4bc  mov     rcx, [rcx+10h]
0x18002c4c0  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c4c7  mov     edx, 6Dh ; 'm'
0x18002c4cc  mov     r9d, eax
0x18002c4cf  call    WPP_SF_d
0x18002c4d4  jmp     loc_18002C584
0x18002c4d9  mov     rcx, [rdi+8]; lpMem
0x18002c4dd  test    rcx, rcx
0x18002c4e0  jz      short loc_18002C4E7
0x18002c4e2  call    IpsecFreeMem
0x18002c4e7  mov     rax, [rsp+48h+arg_8]
0x18002c4ec  xor     edx, edx
0x18002c4ee  mov     [rdi+8], rax
0x18002c4f2  mov     r9, rdi
0x18002c4f5  mov     eax, [rdi+18h]
0x18002c4f8  xor     r8d, r8d
0x18002c4fb  mov     [rdi+1Ch], eax
0x18002c4fe  lea     ecx, [rdx+4]
0x18002c501  mov     dword ptr [rdi+18h], 0
0x18002c508  call    SetSpdStateOnError
0x18002c50d  mov     r9d, [rdi+10h]
0x18002c511  mov     cs:gCurrentPollingInterval, r9d
0x18002c518  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c51f  cmp     rcx, r15
0x18002c522  jz      short loc_18002C53F
0x18002c524  test    byte ptr [rcx+1Ch], 4
0x18002c528  jz      short loc_18002C53F
0x18002c52a  mov     rcx, [rcx+10h]
0x18002c52e  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c535  mov     edx, 6Eh ; 'n'
0x18002c53a  call    WPP_SF_d
0x18002c53f  mov     [rsp+48h+var_20], 1
0x18002c547  xor     r9d, r9d
0x18002c54a  mov     r8d, 4BAD000Ch
0x18002c550  mov     [rsp+48h+var_28], 0
0x18002c558  call    AuditEventOld
0x18002c55d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c564  cmp     rcx, r15
0x18002c567  jz      short loc_18002C584
0x18002c569  test    byte ptr [rcx+1Ch], 4
0x18002c56d  jz      short loc_18002C584
0x18002c56f  mov     rcx, [rcx+10h]
0x18002c573  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c57a  mov     edx, 6Fh ; 'o'
0x18002c57f  call    WPP_SF_
0x18002c584  mov     rdi, [rsp+48h+arg_10]
0x18002c589  mov     eax, ebx
0x18002c58b  mov     rbx, [rsp+48h+arg_0]
0x18002c590  add     rsp, 40h
0x18002c594  pop     r15
0x18002c596  retn
```
