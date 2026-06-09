# MwcGetProtoArray

- ea: `0x180033500`
- end: `0x18003373d`
- name: `MwcGetProtoArray`
- size: `573`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180034098`
- `0x180035bc0`
- `0x180035d84`

## callees

- `0x1800327a8`
- `0x180033500`
- `0x180038104`
- `0x18003aec4`
- `0x180053010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180033673`
- `ntdll!RtlFreeHeap` at `0x180033673`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003358d`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003361a`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003358d`
- `WS2_32!WSCEnumProtocolsEx` at `0x18003361a`

## string_xrefs

- `0x1800336a0`: `MwcGetProtoArray failed because WSCEnumProtocols failed`
- `0x1800336fb`: `MwcGetProtoArray failed because WSCEnumProtocols failed`

## pseudocode

```c
__int64 __fastcall MwcGetProtoArray(char a1, int **a2, _DWORD *a3, _DWORD *a4, __int64 a5)
{
  __int64 v5; // rdi
  int v10; // eax
  __int64 result; // rax
  __int64 v12; // rcx
  int *v13; // rbx
  int v14; // ecx
  unsigned int v15; // ecx
  __int64 v16; // r8
  __int64 v17; // rcx
  const wchar_t *v18; // rdx
  int v19; // [rsp+30h] [rbp-10h] BYREF
  int v20; // [rsp+34h] [rbp-Ch]
  __int64 v21; // [rsp+38h] [rbp-8h]
  unsigned int v22; // [rsp+78h] [rbp+38h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+40h] BYREF

  v5 = a5;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v10 = *(_DWORD *)(v5 + 4) - 2;
  v22 = 0;
  v23 = 0;
  if ( (v10 & 0xFFFFFFFD) != 0 || !a1 )
  {
    result = WSCEnumProtocolsEx(0, 0, &v23, &v22, v5);
  }
  else
  {
    v19 = *(_DWORD *)v5;
    v21 = *(_QWORD *)(v5 + 8);
    v20 = 4;
    result = WSCEnumProtocolsEx(0, 0, &v23, &v22, &v19);
  }
  if ( (_DWORD)result == -1 )
  {
    v12 = v22;
    if ( v22 == 10055 )
    {
      v13 = (int *)((__int64 (__fastcall *)(HANDLE, _QWORD, _QWORD))SockAllocateHeapRoutine)(SockPrivateHeap, 0, v23);
      if ( v13 )
      {
        if ( ((*(_DWORD *)(v5 + 4) - 2) & 0xFFFFFFFD) != 0 || !a1 )
        {
          result = WSCEnumProtocolsEx(0, v13, &v23, &v22, v5);
        }
        else
        {
          v14 = *(_DWORD *)v5;
          v21 = *(_QWORD *)(v5 + 8);
          v19 = v14;
          v20 = 4;
          result = WSCEnumProtocolsEx(0, v13, &v23, &v22, &v19);
        }
        if ( (_DWORD)result != -1 )
        {
          v15 = 0;
          if ( (_DWORD)result )
          {
            v16 = 0;
            do
            {
              if ( v13[157 * v16 + 10] == 1 )
              {
                *(_QWORD *)&v13[157 * v16 + 27] = 0;
              }
              else if ( v13[157 * v16 + 10] > 1 )
              {
                ++*a4;
              }
              ++v15;
              ++v16;
            }
            while ( v15 < (unsigned int)result );
          }
          *a2 = v13;
          *a3 = result;
          return result;
        }
        RtlFreeHeap(SockPrivateHeap, 0, v13);
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_l(v17, 53, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v22);
        v12 = v22;
        v18 = L"MwcGetProtoArray failed because WSCEnumProtocols failed";
      }
      else
      {
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_(1025, 54, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
        v18 = L"Failed to allocate space for info";
        v12 = 8;
      }
    }
    else
    {
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        WPP_SF_l(v22, 56, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v22);
        v12 = v22;
      }
      v18 = L"MwcGetProtoArray failed because WSCEnumProtocols failed";
    }
    return LogError(v12, v18);
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    return WPP_SF_(1025, 55, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180033500  mov     [rsp-28h+arg_0], rbx
0x180033505  mov     [rsp-28h+arg_18], rsi
0x18003350a  push    rbp
0x18003350b  push    rdi
0x18003350c  push    r12
0x18003350e  push    r14
0x180033510  push    r15
0x180033512  mov     rbp, rsp
0x180033515  sub     rsp, 40h
0x180033519  mov     rdi, [rbp+arg_20]
0x18003351d  mov     r14, r9
0x180033520  mov     qword ptr [rdx], 0
0x180033527  mov     r15, r8
0x18003352a  mov     dword ptr [r8], 0
0x180033531  mov     r12, rdx
0x180033534  mov     dword ptr [r9], 0
0x18003353b  mov     sil, cl
0x18003353e  mov     eax, [rdi+4]
0x180033541  sub     eax, 2
0x180033544  mov     [rbp+arg_8], 0
0x18003354b  mov     [rbp+arg_10], 0
0x180033552  test    eax, 0FFFFFFFDh
0x180033557  jnz     short loc_18003357C
0x180033559  test    cl, cl
0x18003355b  jz      short loc_18003357C
0x18003355d  mov     eax, [rdi]
0x18003355f  mov     [rbp+var_10], eax
0x180033562  mov     rax, [rdi+8]
0x180033566  mov     [rbp+var_8], rax
0x18003356a  lea     rax, [rbp+var_10]
0x18003356e  mov     [rsp+40h+var_20], rax
0x180033573  mov     [rbp+var_C], 4
0x18003357a  jmp     short loc_180033581
0x18003357c  mov     [rsp+40h+var_20], rdi
0x180033581  lea     r9, [rbp+arg_8]
0x180033585  xor     edx, edx
0x180033587  lea     r8, [rbp+arg_10]
0x18003358b  xor     ecx, ecx
0x18003358d  call    cs:__imp_WSCEnumProtocolsEx
0x180033594  nop     dword ptr [rax+rax+00h]
0x180033599  cmp     eax, 0FFFFFFFFh
0x18003359c  jnz     loc_180033704
0x1800335a2  mov     ecx, [rbp+arg_8]
0x1800335a5  cmp     ecx, 2747h
0x1800335ab  jnz     loc_1800336DB
0x1800335b1  mov     r8d, [rbp+arg_10]
0x1800335b5  xor     edx, edx
0x1800335b7  mov     rcx, cs:SockPrivateHeap
0x1800335be  mov     rax, cs:SockAllocateHeapRoutine
0x1800335c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800335ca  mov     rbx, rax
0x1800335cd  test    rax, rax
0x1800335d0  jz      loc_1800336A9
0x1800335d6  mov     ecx, [rdi+4]
0x1800335d9  sub     ecx, 2
0x1800335dc  test    ecx, 0FFFFFFFDh
0x1800335e2  jnz     short loc_180033608
0x1800335e4  test    sil, sil
0x1800335e7  jz      short loc_180033608
0x1800335e9  mov     rax, [rdi+8]
0x1800335ed  mov     ecx, [rdi]
0x1800335ef  mov     [rbp+var_8], rax
0x1800335f3  lea     rax, [rbp+var_10]
0x1800335f7  mov     [rsp+40h+var_20], rax
0x1800335fc  mov     [rbp+var_10], ecx
0x1800335ff  mov     [rbp+var_C], 4
0x180033606  jmp     short loc_18003360D
0x180033608  mov     [rsp+40h+var_20], rdi
0x18003360d  lea     r9, [rbp+arg_8]
0x180033611  mov     rdx, rbx
0x180033614  lea     r8, [rbp+arg_10]
0x180033618  xor     ecx, ecx
0x18003361a  call    cs:__imp_WSCEnumProtocolsEx
0x180033621  nop     dword ptr [rax+rax+00h]
0x180033626  cmp     eax, 0FFFFFFFFh
0x180033629  jz      short loc_180033667
0x18003362b  xor     ecx, ecx
0x18003362d  test    eax, eax
0x18003362f  jz      short loc_18003365B
0x180033631  xor     r8d, r8d
0x180033634  imul    rdx, r8, 274h
0x18003363b  cmp     dword ptr [rdx+rbx+28h], 1
0x180033640  jnz     short loc_18003364D
0x180033642  mov     qword ptr [rdx+rbx+6Ch], 0
0x18003364b  jmp     short loc_180033652
0x18003364d  jle     short loc_180033652
0x18003364f  inc     dword ptr [r14]
0x180033652  inc     ecx
0x180033654  inc     r8
0x180033657  cmp     ecx, eax
0x180033659  jb      short loc_180033634
0x18003365b  mov     [r12], rbx
0x18003365f  mov     [r15], eax
0x180033662  jmp     loc_180033723
0x180033667  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18003366e  mov     r8, rbx; P
0x180033671  xor     edx, edx; Flags
0x180033673  call    cs:__imp_RtlFreeHeap
0x18003367a  nop     dword ptr [rax+rax+00h]
0x18003367f  test    byte ptr cs:xmmword_180063D60, 2
0x180033686  jz      short loc_18003369D
0x180033688  mov     r9d, [rbp+arg_8]
0x18003368c  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180033693  mov     edx, 35h ; '5'
0x180033698  call    WPP_SF_l
0x18003369d  mov     ecx, [rbp+arg_8]
0x1800336a0  lea     rdx, aMwcgetprotoarr; "MwcGetProtoArray failed because WSCEnum"...
0x1800336a7  jmp     short loc_1800336D4
0x1800336a9  test    byte ptr cs:xmmword_180063D60, 2
0x1800336b0  jz      short loc_1800336C8
0x1800336b2  mov     edx, 36h ; '6'
0x1800336b7  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800336be  mov     ecx, 401h
0x1800336c3  call    WPP_SF_
0x1800336c8  lea     rdx, aFailedToAlloca_0; "Failed to allocate space for info"
0x1800336cf  mov     ecx, 8
0x1800336d4  call    LogError
0x1800336d9  jmp     short loc_180033723
0x1800336db  test    byte ptr cs:xmmword_180063D60, 2
0x1800336e2  jz      short loc_1800336FB
0x1800336e4  mov     edx, 38h ; '8'
0x1800336e9  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800336f0  mov     r9d, ecx
0x1800336f3  call    WPP_SF_l
0x1800336f8  mov     ecx, [rbp+arg_8]
0x1800336fb  lea     rdx, aMwcgetprotoarr; "MwcGetProtoArray failed because WSCEnum"...
0x180033702  jmp     short loc_1800336D4
0x180033704  test    byte ptr cs:xmmword_180063D60, 2
0x18003370b  jz      short loc_180033723
0x18003370d  mov     edx, 37h ; '7'
0x180033712  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180033719  mov     ecx, 401h
0x18003371e  call    WPP_SF_
0x180033723  lea     r11, [rsp+40h+var_s0]
0x180033728  mov     rbx, [r11+30h]
0x18003372c  mov     rsi, [r11+48h]
0x180033730  mov     rsp, r11
0x180033733  pop     r15
0x180033735  pop     r14
0x180033737  pop     r12
0x180033739  pop     rdi
0x18003373a  pop     rbp
0x18003373b  retn
```
