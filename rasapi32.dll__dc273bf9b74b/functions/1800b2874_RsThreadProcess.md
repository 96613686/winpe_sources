# RsThreadProcess

- ea: `0x1800b2874`
- end: `0x1800b2a25`
- name: `RsThreadProcess`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b2430`

## callees

- `0x1800b2284`
- `0x1800b23c8`
- `0x1800b2874`
- `0x1800b6394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b2970`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b2970`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b28b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b295e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b28b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b295e`
- `rtutils!TracePrintfExA` at `0x1800b28a9`
- `rtutils!TracePrintfExA` at `0x1800b29ba`
- `rtutils!TracePrintfExA` at `0x1800b29d7`
- `rtutils!TracePrintfExA` at `0x1800b2a0b`
- `rtutils!TracePrintfExA` at `0x1800b28a9`
- `rtutils!TracePrintfExA` at `0x1800b29ba`
- `rtutils!TracePrintfExA` at `0x1800b29d7`
- `rtutils!TracePrintfExA` at `0x1800b2a0b`

## string_xrefs

- `0x1800b29cd`: `RsThreadProcess: script completed`
- `0x1800b29b0`: `RsThreadProcess: script waiting for input`
- `0x1800b289f`: `RsThreadProcess`
- `0x1800b2a01`: `RsThreadProcess: Nomore items to execute.`
- `0x1800b2992`: `RsThreadProcess: script paused`

## pseudocode

```c
__int64 __fastcall RsThreadProcess(__int64 a1)
{
  __int64 v1; // rbp
  unsigned int v3; // edi
  int *v4; // r8
  __int64 v5; // r9
  int v6; // eax
  __int64 v7; // rdx
  int v8; // esi
  __int64 v9; // r10
  __int64 v10; // rax
  __int64 v12; // rdx

  v1 = *(_QWORD *)(a1 + 112);
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThreadProcess");
  v3 = 0;
  if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
  {
LABEL_23:
    SetEvent(*(HANDLE *)(a1 + 88));
    return v3;
  }
  while ( 1 )
  {
    v4 = *(int **)(v1 + 1072);
    if ( !v4 )
    {
      if ( g_dwRasscrptTraceId != -1 )
        TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThreadProcess: Nomore items to execute.");
      goto LABEL_37;
    }
    v5 = *((_QWORD *)v4 + 6);
    if ( !v5 || !*((_QWORD *)v4 + 3) )
    {
      v8 = -2147467259;
      goto LABEL_18;
    }
    v6 = *v4;
    if ( (*v4 & 1) != 0 || (v6 & 4) != 0 )
      goto LABEL_16;
    v7 = *((_QWORD *)v4 + 9);
    if ( v7 )
      goto LABEL_14;
    if ( (v6 & 2) == 0 )
    {
      v9 = (unsigned int)v4[14];
      if ( (unsigned int)v9 >= *(_DWORD *)v5 )
      {
        *v4 = v6 | 1;
LABEL_16:
        v8 = 2;
        goto LABEL_18;
      }
      v7 = *(_QWORD *)(*(_QWORD *)(v5 + 8) + 8 * v9);
      v4[14] = v9 + 1;
LABEL_14:
      v8 = Astexec_ProcessStmt(v4, v7);
      goto LABEL_18;
    }
    v8 = 0;
LABEL_18:
    v10 = *(_QWORD *)(v1 + 1072);
    if ( (*(_BYTE *)v10 & 1) != 0 || (*(_BYTE *)v10 & 4) != 0 )
    {
      if ( g_dwRasscrptTraceId != -1 )
        TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThreadProcess: script completed");
      if ( (**(_BYTE **)(v1 + 1072) & 1) == 0 )
      {
        v12 = 6;
        if ( v8 >= 0 )
          v12 = 1;
        goto LABEL_38;
      }
LABEL_37:
      v12 = 0;
LABEL_38:
      RsSignal(a1, v12);
      return 259;
    }
    if ( *(_QWORD *)(v10 + 72) )
      break;
    if ( (*(_BYTE *)v10 & 2) != 0 )
    {
      if ( g_dwRasscrptTraceId != -1 )
        TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThreadProcess: script paused");
      return v3;
    }
    if ( !WaitForSingleObject(*(HANDLE *)(a1 + 88), 0) )
      goto LABEL_23;
  }
  v3 = RsPostReceive(a1);
  if ( g_dwRasscrptTraceId != -1 )
    TracePrintfExA(g_dwRasscrptTraceId, 0xCu, "RsThreadProcess: script waiting for input");
  return v3;
}

```

## disassembly

```asm
0x1800b2874  push    rbx
0x1800b2876  push    rbp
0x1800b2877  push    rsi
0x1800b2878  push    rdi
0x1800b2879  push    r12
0x1800b287b  push    r14
0x1800b287d  push    r15
0x1800b287f  sub     rsp, 20h
0x1800b2883  mov     rbp, [rcx+70h]
0x1800b2887  mov     rbx, rcx
0x1800b288a  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b2890  or      r14d, 0FFFFFFFFh
0x1800b2894  mov     r15d, 0Ch
0x1800b289a  cmp     ecx, r14d
0x1800b289d  jz      short loc_1800B28AF
0x1800b289f  lea     r8, aRsthreadproces_3; "RsThreadProcess"
0x1800b28a6  mov     edx, r15d; dwFlags
0x1800b28a9  call    cs:__imp_TracePrintfExA
0x1800b28af  mov     rcx, [rbx+58h]; hHandle
0x1800b28b3  xor     edx, edx; dwMilliseconds
0x1800b28b5  xor     edi, edi
0x1800b28b7  call    cs:__imp_WaitForSingleObject
0x1800b28bd  test    eax, eax
0x1800b28bf  jz      loc_1800B296C
0x1800b28c5  lea     r12d, [rdi+1]
0x1800b28c9  mov     r8, [rbp+430h]
0x1800b28d0  test    r8, r8
0x1800b28d3  jz      loc_1800B29F6
0x1800b28d9  mov     r9, [r8+30h]
0x1800b28dd  test    r9, r9
0x1800b28e0  jz      short loc_1800B2937
0x1800b28e2  cmp     [r8+18h], rdi
0x1800b28e6  jz      short loc_1800B2937
0x1800b28e8  mov     eax, [r8]
0x1800b28eb  test    r12b, al
0x1800b28ee  jnz     short loc_1800B2930
0x1800b28f0  test    al, 4
0x1800b28f2  jnz     short loc_1800B2930
0x1800b28f4  mov     rdx, [r8+48h]
0x1800b28f8  test    rdx, rdx
0x1800b28fb  jnz     short loc_1800B291E
0x1800b28fd  test    al, 2
0x1800b28ff  jz      short loc_1800B2905
0x1800b2901  xor     esi, esi
0x1800b2903  jmp     short loc_1800B293C
0x1800b2905  mov     r10d, [r8+38h]
0x1800b2909  cmp     r10d, [r9]
0x1800b290c  jnb     short loc_1800B292A
0x1800b290e  mov     rax, [r9+8]
0x1800b2912  mov     rdx, [rax+r10*8]
0x1800b2916  lea     eax, [r10+1]
0x1800b291a  mov     [r8+38h], eax
0x1800b291e  mov     rcx, r8
0x1800b2921  call    Astexec_ProcessStmt
0x1800b2926  mov     esi, eax
0x1800b2928  jmp     short loc_1800B293C
0x1800b292a  or      eax, r12d
0x1800b292d  mov     [r8], eax
0x1800b2930  mov     esi, 2
0x1800b2935  jmp     short loc_1800B293C
0x1800b2937  mov     esi, 80004005h
0x1800b293c  mov     rax, [rbp+430h]
0x1800b2943  test    [rax], r12b
0x1800b2946  jnz     short loc_1800B29C2
0x1800b2948  test    byte ptr [rax], 4
0x1800b294b  jnz     short loc_1800B29C2
0x1800b294d  cmp     [rax+48h], rdi
0x1800b2951  jnz     short loc_1800B299B
0x1800b2953  test    byte ptr [rax], 2
0x1800b2956  jnz     short loc_1800B2987
0x1800b2958  mov     rcx, [rbx+58h]; hHandle
0x1800b295c  xor     edx, edx; dwMilliseconds
0x1800b295e  call    cs:__imp_WaitForSingleObject
0x1800b2964  test    eax, eax
0x1800b2966  jnz     loc_1800B28C9
0x1800b296c  mov     rcx, [rbx+58h]; hEvent
0x1800b2970  call    cs:__imp_SetEvent
0x1800b2976  mov     eax, edi
0x1800b2978  add     rsp, 20h
0x1800b297c  pop     r15
0x1800b297e  pop     r14
0x1800b2980  pop     r12
0x1800b2982  pop     rdi
0x1800b2983  pop     rsi
0x1800b2984  pop     rbp
0x1800b2985  pop     rbx
0x1800b2986  retn
0x1800b2987  mov     ecx, cs:g_dwRasscrptTraceId
0x1800b298d  cmp     ecx, r14d
0x1800b2990  jz      short loc_1800B2976
0x1800b2992  lea     r8, aRsthreadproces_2; "RsThreadProcess: script paused"
0x1800b2999  jmp     short loc_1800B29B7
0x1800b299b  mov     rcx, rbx
0x1800b299e  call    RsPostReceive
0x1800b29a3  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b29a9  mov     edi, eax
0x1800b29ab  cmp     ecx, r14d
0x1800b29ae  jz      short loc_1800B2976
0x1800b29b0  lea     r8, aRsthreadproces_0; "RsThreadProcess: script waiting for inp"...
0x1800b29b7  mov     edx, r15d; dwFlags
0x1800b29ba  call    cs:__imp_TracePrintfExA
0x1800b29c0  jmp     short loc_1800B2976
0x1800b29c2  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b29c8  cmp     ecx, r14d
0x1800b29cb  jz      short loc_1800B29DD
0x1800b29cd  lea     r8, aRsthreadproces; "RsThreadProcess: script completed"
0x1800b29d4  mov     edx, r15d; dwFlags
0x1800b29d7  call    cs:__imp_TracePrintfExA
0x1800b29dd  mov     rax, [rbp+430h]
0x1800b29e4  test    [rax], r12b
0x1800b29e7  jnz     short loc_1800B2A11
0x1800b29e9  test    esi, esi
0x1800b29eb  mov     edx, 6
0x1800b29f0  cmovns  edx, r12d
0x1800b29f4  jmp     short loc_1800B2A13
0x1800b29f6  mov     ecx, cs:g_dwRasscrptTraceId; dwTraceID
0x1800b29fc  cmp     ecx, r14d
0x1800b29ff  jz      short loc_1800B2A11
0x1800b2a01  lea     r8, aRsthreadproces_1; "RsThreadProcess: Nomore items to execut"...
0x1800b2a08  mov     edx, r15d; dwFlags
0x1800b2a0b  call    cs:__imp_TracePrintfExA
0x1800b2a11  xor     edx, edx
0x1800b2a13  mov     rcx, rbx
0x1800b2a16  call    RsSignal
0x1800b2a1b  mov     edi, 103h
0x1800b2a20  jmp     loc_1800B2976
```
