# ScPolicyDeleteSession

- ea: `0x18001b278`
- end: `0x18001b432`
- name: `ScPolicyDeleteSession`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001b490`

## callees

- `0x180004600`
- `0x180018bb4`
- `0x180018d78`
- `0x18001ae78`
- `0x18001b278`
- `0x18001b438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b2fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b34f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b2cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b34f`

## pseudocode

```c
__int64 __fastcall ScPolicyDeleteSession(__int64 a1, int a2)
{
  int v3; // edi
  int v4; // r9d
  __int64 i; // rbx
  __int64 v6; // rcx
  int v7; // r9d
  __int64 j; // rcx
  int v9; // r9d

  v3 = a1;
  WppTraceIndent(a1, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      v4,
      v3);
  }
  EnterCriticalSection(&g_csScPolicyList);
  for ( i = g_pScPolicyList; i; i = *(_QWORD *)i )
  {
    if ( v3 == *(_DWORD *)(i + 52) )
    {
      ScPolicyCancelMonitorThread(i, a2);
      break;
    }
  }
  LeaveCriticalSection(&g_csScPolicyList);
  if ( !i )
  {
    WppTraceIndent(v6, 2);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
        v7,
        v3);
    }
    EnterCriticalSection(&g_csInactiveScPolicyList);
    for ( j = g_pInactiveScPolicyList; ; j = *(_QWORD *)j )
    {
      if ( !j )
      {
        WppTraceIndent(0, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
            v9,
            v3);
        }
        goto LABEL_24;
      }
      if ( v3 == *(_DWORD *)(j + 52) )
        break;
      i = j;
    }
    if ( ((a2 - 2) & 0xFFFFFFFD) != 0 )
    {
      if ( i )
        *(_QWORD *)i = *(_QWORD *)j;
      else
        g_pInactiveScPolicyList = *(_QWORD *)j;
      ScPolicyFreeListNode(j);
    }
LABEL_24:
    LeaveCriticalSection(&g_csInactiveScPolicyList);
  }
  WppTraceIndent(v6, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b278  push    rbx
0x18001b27a  push    rsi
0x18001b27b  push    rdi
0x18001b27c  push    r12
0x18001b27e  sub     rsp, 38h
0x18001b282  mov     esi, edx
0x18001b284  mov     edi, ecx
0x18001b286  mov     edx, 2
0x18001b28b  call    WppTraceIndent
0x18001b290  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b297  lea     r12, WPP_GLOBAL_Control
0x18001b29e  cmp     rcx, r12
0x18001b2a1  jz      short loc_18001B2C8
0x18001b2a3  test    byte ptr [rcx+1Ch], 1
0x18001b2a7  jz      short loc_18001B2C8
0x18001b2a9  cmp     byte ptr [rcx+19h], 4
0x18001b2ad  jb      short loc_18001B2C8
0x18001b2af  mov     rcx, [rcx+10h]
0x18001b2b3  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b2ba  mov     edx, 10h
0x18001b2bf  mov     [rsp+58h+var_38], edi
0x18001b2c3  call    WPP_SF_sd
0x18001b2c8  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b2cf  call    cs:__imp_EnterCriticalSection
0x18001b2d5  mov     rbx, cs:g_pScPolicyList
0x18001b2dc  jmp     short loc_18001B2E6
0x18001b2de  cmp     edi, [rbx+34h]
0x18001b2e1  jz      short loc_18001B2ED
0x18001b2e3  mov     rbx, [rbx]
0x18001b2e6  test    rbx, rbx
0x18001b2e9  jnz     short loc_18001B2DE
0x18001b2eb  jmp     short loc_18001B2F7
0x18001b2ed  mov     edx, esi
0x18001b2ef  mov     rcx, rbx
0x18001b2f2  call    ScPolicyCancelMonitorThread
0x18001b2f7  lea     rcx, g_csScPolicyList; lpCriticalSection
0x18001b2fe  call    cs:__imp_LeaveCriticalSection
0x18001b304  test    rbx, rbx
0x18001b307  jnz     loc_18001B3B8
0x18001b30d  mov     edx, 2
0x18001b312  call    WppTraceIndent
0x18001b317  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b31e  cmp     rcx, r12
0x18001b321  jz      short loc_18001B348
0x18001b323  test    byte ptr [rcx+1Ch], 1
0x18001b327  jz      short loc_18001B348
0x18001b329  cmp     byte ptr [rcx+19h], 3
0x18001b32d  jb      short loc_18001B348
0x18001b32f  mov     rcx, [rcx+10h]
0x18001b333  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b33a  mov     edx, 11h
0x18001b33f  mov     [rsp+58h+var_38], edi
0x18001b343  call    WPP_SF_sd
0x18001b348  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b34f  call    cs:__imp_EnterCriticalSection
0x18001b355  mov     rcx, cs:g_pInactiveScPolicyList
0x18001b35c  jmp     short loc_18001B36D
0x18001b35e  cmp     edi, [rcx+34h]
0x18001b361  jz      loc_18001B40A
0x18001b367  mov     rbx, rcx
0x18001b36a  mov     rcx, [rcx]
0x18001b36d  test    rcx, rcx
0x18001b370  jnz     short loc_18001B35E
0x18001b372  lea     edx, [rcx+2]
0x18001b375  call    WppTraceIndent
0x18001b37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b381  cmp     rcx, r12
0x18001b384  jz      short loc_18001B3AB
0x18001b386  test    byte ptr [rcx+1Ch], 1
0x18001b38a  jz      short loc_18001B3AB
0x18001b38c  cmp     byte ptr [rcx+19h], 2
0x18001b390  jb      short loc_18001B3AB
0x18001b392  mov     rcx, [rcx+10h]
0x18001b396  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b39d  mov     edx, 12h
0x18001b3a2  mov     [rsp+58h+var_38], edi
0x18001b3a6  call    WPP_SF_sd
0x18001b3ab  lea     rcx, g_csInactiveScPolicyList; lpCriticalSection
0x18001b3b2  call    cs:__imp_LeaveCriticalSection
0x18001b3b8  mov     edx, 2
0x18001b3bd  call    WppTraceIndent
0x18001b3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3c9  cmp     rcx, r12
0x18001b3cc  jz      short loc_18001B3FE
0x18001b3ce  test    byte ptr [rcx+1Ch], 1
0x18001b3d2  jz      short loc_18001B3FE
0x18001b3d4  cmp     byte ptr [rcx+19h], 4
0x18001b3d8  jb      short loc_18001B3FE
0x18001b3da  mov     r9, cs:WPP_pszIndent
0x18001b3e1  lea     r8, WPP_d7eb28ff47173aa5291fb72972aa2797_Traceguids
0x18001b3e8  mov     rcx, [rcx+10h]
0x18001b3ec  mov     edx, 13h
0x18001b3f1  mov     [rsp+58h+var_38], 0
0x18001b3f9  call    WPP_SF_sD
0x18001b3fe  xor     eax, eax
0x18001b400  add     rsp, 38h
0x18001b404  pop     r12
0x18001b406  pop     rdi
0x18001b407  pop     rsi
0x18001b408  pop     rbx
0x18001b409  retn
0x18001b40a  lea     eax, [rsi-2]
0x18001b40d  test    eax, 0FFFFFFFDh
0x18001b412  jz      short loc_18001B3AB
0x18001b414  mov     rax, [rcx]
0x18001b417  test    rbx, rbx
0x18001b41a  jnz     short loc_18001B425
0x18001b41c  mov     cs:g_pInactiveScPolicyList, rax
0x18001b423  jmp     short loc_18001B428
0x18001b425  mov     [rbx], rax
0x18001b428  call    ScPolicyFreeListNode
0x18001b42d  jmp     loc_18001B3AB
```
