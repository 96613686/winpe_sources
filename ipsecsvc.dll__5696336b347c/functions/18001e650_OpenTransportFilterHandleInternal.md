# OpenTransportFilterHandleInternal

- ea: `0x18001e650`
- end: `0x18001e807`
- name: `OpenTransportFilterHandleInternal`
- size: `439`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800148a0`
- `0x180014a90`

## callees

- `0x18000bed4`
- `0x18000bf8c`
- `0x18000e510`
- `0x1800175dc`
- `0x18001e024`
- `0x18001e090`
- `0x18001e650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e7d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e7d8`

## pseudocode

```c
__int64 __fastcall OpenTransportFilterHandleInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  __int64 *v5; // r14
  __int64 v6; // rsi
  unsigned int v9; // edi
  _QWORD *i; // rbx
  __int64 v11; // rcx
  __int128 v12; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  v5 = a5;
  v6 = 0;
  v13 = 0;
  if ( !a5 )
    return 87;
  v9 = ValidateTransportFilterInternal(a3);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, v9);
  }
  else
  {
    EnterCriticalSection(&gcSPDSection);
    for ( i = gpIniTxFilter; ; i = (_QWORD *)i[27] )
    {
      if ( !i )
      {
        v9 = 13009;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, 13009);
        goto LABEL_21;
      }
      if ( (unsigned int)EqualTxFilterPKeys(i, a3) && (unsigned int)EqualTxFilterNonPKeys(i, a3) )
        break;
    }
    v12 = *(_OWORD *)(a3 + 4);
    v9 = CreateTxFilterHandle(i, &v12, &v13);
    if ( !v9 )
    {
      ++*((_DWORD *)i + 39);
      v11 = v13;
      *(_QWORD *)(v13 + 32) = gpTxFilterHandle;
      gpTxFilterHandle = v11;
      *v5 = v11;
      LeaveCriticalSection(&gcSPDSection);
      return v9;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids, v9);
    v6 = v13;
LABEL_21:
    LeaveCriticalSection(&gcSPDSection);
    if ( v6 )
      SPDApiBufferFree(v6);
  }
  *v5 = 0;
  return v9;
}

```

## disassembly

```asm
0x18001e650  mov     rax, rsp
0x18001e653  mov     [rax+8], rbx
0x18001e657  mov     [rax+10h], rbp
0x18001e65b  mov     [rax+20h], r9
0x18001e65f  push    rsi
0x18001e660  push    rdi
0x18001e661  push    r14
0x18001e663  sub     rsp, 30h
0x18001e667  mov     r14, [rsp+48h+arg_20]
0x18001e66c  xor     esi, esi
0x18001e66e  mov     [rax+20h], rsi
0x18001e672  mov     rbp, r8
0x18001e675  test    r14, r14
0x18001e678  jnz     short loc_18001E682
0x18001e67a  lea     eax, [rsi+57h]
0x18001e67d  jmp     loc_18001E7F4
0x18001e682  mov     rcx, rbp
0x18001e685  call    ValidateTransportFilterInternal
0x18001e68a  mov     edi, eax
0x18001e68c  test    eax, eax
0x18001e68e  jz      short loc_18001E6CE
0x18001e690  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e697  lea     rax, WPP_GLOBAL_Control
0x18001e69e  cmp     rcx, rax
0x18001e6a1  jz      loc_18001E7EB
0x18001e6a7  test    byte ptr [rcx+1Ch], 10h
0x18001e6ab  jz      loc_18001E7EB
0x18001e6b1  mov     rcx, [rcx+10h]
0x18001e6b5  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001e6bc  mov     edx, 6Ah ; 'j'
0x18001e6c1  mov     r9d, edi
0x18001e6c4  call    WPP_SF_d
0x18001e6c9  jmp     loc_18001E7EB
0x18001e6ce  lea     rcx, gcSPDSection; lpCriticalSection
0x18001e6d5  call    cs:__imp_EnterCriticalSection
0x18001e6db  mov     rbx, cs:gpIniTxFilter
0x18001e6e2  test    rbx, rbx
0x18001e6e5  jz      loc_18001E79B
0x18001e6eb  mov     rdx, rbp
0x18001e6ee  mov     rcx, rbx
0x18001e6f1  call    EqualTxFilterPKeys
0x18001e6f6  test    eax, eax
0x18001e6f8  jz      short loc_18001E709
0x18001e6fa  mov     rdx, rbp
0x18001e6fd  mov     rcx, rbx
0x18001e700  call    EqualTxFilterNonPKeys
0x18001e705  test    eax, eax
0x18001e707  jnz     short loc_18001E712
0x18001e709  mov     rbx, [rbx+0D8h]
0x18001e710  jmp     short loc_18001E6E2
0x18001e712  movups  xmm0, xmmword ptr [rbp+4]
0x18001e716  lea     r8, [rsp+48h+arg_18]
0x18001e71b  mov     rcx, rbx
0x18001e71e  lea     rdx, [rsp+48h+var_28]
0x18001e723  movdqu  [rsp+48h+var_28], xmm0
0x18001e729  call    CreateTxFilterHandle
0x18001e72e  mov     edi, eax
0x18001e730  test    eax, eax
0x18001e732  jz      short loc_18001E76C
0x18001e734  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e73b  lea     rax, WPP_GLOBAL_Control
0x18001e742  cmp     rcx, rax
0x18001e745  jz      short loc_18001E765
0x18001e747  test    byte ptr [rcx+1Ch], 10h
0x18001e74b  jz      short loc_18001E765
0x18001e74d  mov     rcx, [rcx+10h]
0x18001e751  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001e758  mov     edx, 6Ch ; 'l'
0x18001e75d  mov     r9d, edi
0x18001e760  call    WPP_SF_d
0x18001e765  mov     rsi, [rsp+48h+arg_18]
0x18001e76a  jmp     short loc_18001E7D1
0x18001e76c  inc     dword ptr [rbx+9Ch]
0x18001e772  mov     rcx, [rsp+48h+arg_18]
0x18001e777  mov     rax, cs:gpTxFilterHandle
0x18001e77e  mov     [rcx+20h], rax
0x18001e782  mov     cs:gpTxFilterHandle, rcx
0x18001e789  mov     [r14], rcx
0x18001e78c  lea     rcx, gcSPDSection; lpCriticalSection
0x18001e793  call    cs:__imp_LeaveCriticalSection
0x18001e799  jmp     short loc_18001E7F2
0x18001e79b  mov     edi, 32D1h
0x18001e7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7a7  lea     rax, WPP_GLOBAL_Control
0x18001e7ae  cmp     rcx, rax
0x18001e7b1  jz      short loc_18001E7D1
0x18001e7b3  test    byte ptr [rcx+1Ch], 10h
0x18001e7b7  jz      short loc_18001E7D1
0x18001e7b9  mov     rcx, [rcx+10h]
0x18001e7bd  lea     r8, WPP_d3e4a8f1960430b115941304a22a5749_Traceguids
0x18001e7c4  mov     edx, 6Bh ; 'k'
0x18001e7c9  mov     r9d, edi
0x18001e7cc  call    WPP_SF_d
0x18001e7d1  lea     rcx, gcSPDSection; lpCriticalSection
0x18001e7d8  call    cs:__imp_LeaveCriticalSection
0x18001e7de  test    rsi, rsi
0x18001e7e1  jz      short loc_18001E7EB
0x18001e7e3  mov     rcx, rsi
0x18001e7e6  call    SPDApiBufferFree
0x18001e7eb  mov     qword ptr [r14], 0
0x18001e7f2  mov     eax, edi
0x18001e7f4  mov     rbx, [rsp+48h+arg_0]
0x18001e7f9  mov     rbp, [rsp+48h+arg_8]
0x18001e7fe  add     rsp, 30h
0x18001e802  pop     r14
0x18001e804  pop     rdi
0x18001e805  pop     rsi
0x18001e806  retn
```
