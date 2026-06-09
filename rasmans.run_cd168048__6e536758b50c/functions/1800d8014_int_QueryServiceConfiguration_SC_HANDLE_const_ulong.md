# int_QueryServiceConfiguration(SC_HANDLE__ * const,ulong *)

- ea: `0x1800d8014`
- end: `0x1800d81a3`
- name: `?int_QueryServiceConfiguration@@YAHQEAUSC_HANDLE__@@PEAK@Z`
- size: `399`
- prototype: `__int64 __fastcall(SC_HANDLE hService, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2748`

## callees

- `0x180005bfc`
- `0x18007f0b4`
- `0x1800ab634`
- `0x1800d8014`
- `0x1800e3ca0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d80ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d80ed`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d8039`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d80ce`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d8039`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800d80ce`

## pseudocode

```c
__int64 __fastcall int_QueryServiceConfiguration(SC_HANDLE hService, unsigned int *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // edi
  struct _QUERY_SERVICE_CONFIGW *v7; // rax
  struct _QUERY_SERVICE_CONFIGW *v8; // rsi
  unsigned int v9; // edi
  struct _LIST_ENTRY *v10; // rcx
  __int64 v11; // rdx
  DWORD cbBufSize; // [rsp+80h] [rbp+18h] BYREF

  cbBufSize = 0;
  if ( QueryServiceConfigW(hService, 0, 0, &cbBufSize) )
  {
    v5 = 0;
    v9 = 0;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError != 122 )
  {
    v9 = 0;
    if ( !LastError )
      goto LABEL_22;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v9;
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      goto LABEL_23;
    v8 = 0;
    v11 = 969;
    goto LABEL_17;
  }
  v6 = cbBufSize;
  v7 = (struct _QUERY_SERVICE_CONFIGW *)VpnAlloc(cbBufSize);
  v8 = v7;
  if ( v7 )
  {
    if ( QueryServiceConfigW(hService, v7, v6, &cbBufSize) )
    {
      v9 = 1;
      *a2 = v8->dwStartType;
LABEL_18:
      v10 = WPP_GLOBAL_Control;
      goto LABEL_19;
    }
    v9 = 0;
    LastError = GetLastError();
    v5 = LastError;
    if ( !LastError )
      goto LABEL_18;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
LABEL_19:
      if ( v8 )
      {
        MprCommonFree(v8);
        goto LABEL_22;
      }
      goto LABEL_23;
    }
    v11 = 968;
LABEL_17:
    WPP_SF_d(v10[1].Flink, v11, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, LastError);
    goto LABEL_18;
  }
  v9 = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v9;
  v5 = 14;
  if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 967, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, 14);
LABEL_22:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_23:
  if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v10[1].Blink) & 8) != 0 )
    WPP_SF_Dc(v10[1].Flink, 970, &WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids, v5, (_BYTE)v9);
  return v9;
}

```

## disassembly

```asm
0x1800d8014  mov     rax, rsp
0x1800d8017  push    rbx
0x1800d8018  push    rbp
0x1800d8019  push    rsi
0x1800d801a  push    rdi
0x1800d801b  push    r14
0x1800d801d  push    r15
0x1800d801f  sub     rsp, 38h
0x1800d8023  mov     r14, rdx
0x1800d8026  mov     dword ptr [rax+18h], 0
0x1800d802d  xor     edx, edx; lpServiceConfig
0x1800d802f  lea     r9, [rax+18h]; pcbBytesNeeded
0x1800d8033  xor     r8d, r8d; cbBufSize
0x1800d8036  mov     rbp, rcx
0x1800d8039  call    cs:__imp_QueryServiceConfigW
0x1800d8040  nop     dword ptr [rax+rax+00h]
0x1800d8045  lea     r15, WPP_GLOBAL_Control
0x1800d804c  test    eax, eax
0x1800d804e  jnz     loc_1800D8160
0x1800d8054  call    cs:__imp_GetLastError
0x1800d805b  nop     dword ptr [rax+rax+00h]
0x1800d8060  mov     ebx, eax
0x1800d8062  cmp     eax, 7Ah ; 'z'
0x1800d8065  jnz     loc_1800D8118
0x1800d806b  mov     edi, [rsp+68h+cbBufSize]
0x1800d8072  mov     ecx, edi
0x1800d8074  call    VpnAlloc
0x1800d8079  mov     rsi, rax
0x1800d807c  test    rax, rax
0x1800d807f  jnz     short loc_1800D80BD
0x1800d8081  xor     edi, edi
0x1800d8083  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d808a  cmp     rcx, r15
0x1800d808d  jz      loc_1800D8193
0x1800d8093  test    byte ptr [rcx+1Ch], 1
0x1800d8097  lea     ebx, [rax+0Eh]
0x1800d809a  jz      loc_1800D816B
0x1800d80a0  mov     rcx, [rcx+10h]
0x1800d80a4  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d80ab  mov     edx, 3C7h
0x1800d80b0  mov     r9d, ebx
0x1800d80b3  call    WPP_SF_d
0x1800d80b8  jmp     loc_1800D8164
0x1800d80bd  lea     r9, [rsp+68h+cbBufSize]; pcbBytesNeeded
0x1800d80c5  mov     r8d, edi; cbBufSize
0x1800d80c8  mov     rdx, rsi; lpServiceConfig
0x1800d80cb  mov     rcx, rbp; hService
0x1800d80ce  call    cs:__imp_QueryServiceConfigW
0x1800d80d5  nop     dword ptr [rax+rax+00h]
0x1800d80da  test    eax, eax
0x1800d80dc  jz      short loc_1800D80EB
0x1800d80de  mov     eax, [rsi+4]
0x1800d80e1  mov     edi, 1
0x1800d80e6  mov     [r14], eax
0x1800d80e9  jmp     short loc_1800D814A
0x1800d80eb  xor     edi, edi
0x1800d80ed  call    cs:__imp_GetLastError
0x1800d80f4  nop     dword ptr [rax+rax+00h]
0x1800d80f9  mov     ebx, eax
0x1800d80fb  test    eax, eax
0x1800d80fd  jz      short loc_1800D814A
0x1800d80ff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8106  cmp     rcx, r15
0x1800d8109  jz      short loc_1800D8151
0x1800d810b  test    byte ptr [rcx+1Ch], 1
0x1800d810f  jz      short loc_1800D8151
0x1800d8111  mov     edx, 3C8h
0x1800d8116  jmp     short loc_1800D8137
0x1800d8118  xor     edi, edi
0x1800d811a  test    eax, eax
0x1800d811c  jz      short loc_1800D8164
0x1800d811e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8125  cmp     rcx, r15
0x1800d8128  jz      short loc_1800D8193
0x1800d812a  test    byte ptr [rcx+1Ch], 1
0x1800d812e  jz      short loc_1800D816B
0x1800d8130  xor     esi, esi
0x1800d8132  mov     edx, 3C9h
0x1800d8137  mov     rcx, [rcx+10h]
0x1800d813b  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8142  mov     r9d, eax
0x1800d8145  call    WPP_SF_d
0x1800d814a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8151  test    rsi, rsi
0x1800d8154  jz      short loc_1800D816B
0x1800d8156  mov     rcx, rsi; lpMem
0x1800d8159  call    MprCommonFree
0x1800d815e  jmp     short loc_1800D8164
0x1800d8160  xor     ebx, ebx
0x1800d8162  xor     edi, edi
0x1800d8164  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d816b  cmp     rcx, r15
0x1800d816e  jz      short loc_1800D8193
0x1800d8170  test    byte ptr [rcx+1Ch], 8
0x1800d8174  jz      short loc_1800D8193
0x1800d8176  mov     rcx, [rcx+10h]
0x1800d817a  lea     r8, WPP_43961ca848cd3a6dcf2689ed32dcf684_Traceguids
0x1800d8181  mov     edx, 3CAh
0x1800d8186  mov     [rsp+68h+var_48], dil
0x1800d818b  mov     r9d, ebx
0x1800d818e  call    WPP_SF_Dc
0x1800d8193  mov     eax, edi
0x1800d8195  add     rsp, 38h
0x1800d8199  pop     r15
0x1800d819b  pop     r14
0x1800d819d  pop     rdi
0x1800d819e  pop     rsi
0x1800d819f  pop     rbp
0x1800d81a0  pop     rbx
0x1800d81a1  retn
```
