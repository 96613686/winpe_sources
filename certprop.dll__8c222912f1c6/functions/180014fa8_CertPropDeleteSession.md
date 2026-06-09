# CertPropDeleteSession

- ea: `0x180014fa8`
- end: `0x18001509f`
- name: `CertPropDeleteSession`
- size: `247`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800061c0`
- `0x18000fe80`

## callees

- `0x1800010c4`
- `0x180004600`
- `0x180014fa8`
- `0x180018bb4`
- `0x180018d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001503a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ffb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014ffb`

## pseudocode

```c
__int64 __fastcall CertPropDeleteSession(__int64 a1)
{
  _QWORD *v1; // rdi
  int v2; // esi
  int v3; // r9d
  _DWORD *v4; // rbx
  LPVOID v5; // rax
  __int64 v6; // rcx

  v1 = 0;
  v2 = a1;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      v3,
      v2);
  }
  EnterCriticalSection(&g_csSessionList);
  v4 = g_pSessionList;
  if ( g_pSessionList )
  {
    while ( 1 )
    {
      v5 = *(LPVOID *)v4;
      if ( v2 == v4[2] )
        break;
      v1 = v4;
      v4 = *(_DWORD **)v4;
      if ( !v5 )
        goto LABEL_12;
    }
    if ( v1 )
      *v1 = v5;
    else
      g_pSessionList = *(LPVOID *)v4;
  }
LABEL_12:
  LeaveCriticalSection(&g_csSessionList);
  if ( v4 )
    CertPropFreeListNode(v4);
  WppTraceIndent(v6, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180014fa8  push    rbx
0x180014faa  push    rsi
0x180014fab  push    rdi
0x180014fac  push    r14
0x180014fae  sub     rsp, 38h
0x180014fb2  xor     edi, edi
0x180014fb4  mov     esi, ecx
0x180014fb6  lea     edx, [rdi+2]
0x180014fb9  call    WppTraceIndent
0x180014fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fc5  lea     r14, WPP_GLOBAL_Control
0x180014fcc  cmp     rcx, r14
0x180014fcf  jz      short loc_180014FF4
0x180014fd1  test    byte ptr [rcx+1Ch], 1
0x180014fd5  jz      short loc_180014FF4
0x180014fd7  cmp     byte ptr [rcx+19h], 4
0x180014fdb  jb      short loc_180014FF4
0x180014fdd  mov     rcx, [rcx+10h]
0x180014fe1  lea     edx, [rdi+13h]
0x180014fe4  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x180014feb  mov     [rsp+58h+var_38], esi
0x180014fef  call    WPP_SF_sd
0x180014ff4  lea     rcx, g_csSessionList; lpCriticalSection
0x180014ffb  call    cs:__imp_EnterCriticalSection
0x180015001  mov     rbx, cs:g_pSessionList
0x180015008  test    rbx, rbx
0x18001500b  jz      short loc_180015033
0x18001500d  mov     rax, [rbx]
0x180015010  cmp     esi, [rbx+8]
0x180015013  jz      short loc_180015022
0x180015015  mov     rdi, rbx
0x180015018  mov     rbx, rax
0x18001501b  test    rax, rax
0x18001501e  jnz     short loc_18001500D
0x180015020  jmp     short loc_180015033
0x180015022  test    rdi, rdi
0x180015025  jnz     short loc_180015030
0x180015027  mov     cs:g_pSessionList, rax
0x18001502e  jmp     short loc_180015033
0x180015030  mov     [rdi], rax
0x180015033  lea     rcx, g_csSessionList; lpCriticalSection
0x18001503a  call    cs:__imp_LeaveCriticalSection
0x180015040  test    rbx, rbx
0x180015043  jz      short loc_18001504D
0x180015045  mov     rcx, rbx; lpMem
0x180015048  call    CertPropFreeListNode
0x18001504d  mov     edx, 2
0x180015052  call    WppTraceIndent
0x180015057  mov     rcx, cs:WPP_GLOBAL_Control
0x18001505e  cmp     rcx, r14
0x180015061  jz      short loc_180015093
0x180015063  test    byte ptr [rcx+1Ch], 1
0x180015067  jz      short loc_180015093
0x180015069  cmp     byte ptr [rcx+19h], 4
0x18001506d  jb      short loc_180015093
0x18001506f  mov     r9, cs:WPP_pszIndent
0x180015076  lea     r8, WPP_4521d3af5b983da37950f871b0dc8b30_Traceguids
0x18001507d  mov     rcx, [rcx+10h]
0x180015081  mov     edx, 14h
0x180015086  mov     [rsp+58h+var_38], 0
0x18001508e  call    WPP_SF_sD
0x180015093  xor     eax, eax
0x180015095  add     rsp, 38h
0x180015099  pop     r14
0x18001509b  pop     rdi
0x18001509c  pop     rsi
0x18001509d  pop     rbx
0x18001509e  retn
```
