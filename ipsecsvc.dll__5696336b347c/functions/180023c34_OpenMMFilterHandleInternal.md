# OpenMMFilterHandleInternal

- ea: `0x180023c34`
- end: `0x180023de8`
- name: `OpenMMFilterHandleInternal`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180014510`
- `0x180014700`

## callees

- `0x18000e510`
- `0x1800175dc`
- `0x1800228fc`
- `0x1800233f8`
- `0x18002344c`
- `0x180023c34`
- `0x180024a8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023cb9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023cb9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023db9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023d74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023db9`

## pseudocode

```c
__int64 __fastcall OpenMMFilterHandleInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
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
  v9 = ValidateMMFilterInternal(a3);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v9);
  }
  else
  {
    EnterCriticalSection(&gcSPDSection);
    for ( i = gpIniMMFilter; ; i = (_QWORD *)i[25] )
    {
      if ( !i )
      {
        v9 = 13007;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, 13007);
        goto LABEL_21;
      }
      if ( (unsigned int)EqualMMFilterPKeys(i, a3) && (unsigned int)EqualMMFilterNonPKeys(i, a3) )
        break;
    }
    v12 = *(_OWORD *)(a3 + 4);
    v9 = CreateMMFilterHandle(i, &v12, &v13);
    if ( !v9 )
    {
      ++*((_DWORD *)i + 31);
      v11 = v13;
      *(_QWORD *)(v13 + 32) = gpMMFilterHandle;
      gpMMFilterHandle = v11;
      *v5 = v11;
      LeaveCriticalSection(&gcSPDSection);
      return v9;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids, v9);
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
0x180023c34  mov     rax, rsp
0x180023c37  mov     [rax+8], rbx
0x180023c3b  mov     [rax+10h], rbp
0x180023c3f  mov     [rax+20h], r9
0x180023c43  push    rsi
0x180023c44  push    rdi
0x180023c45  push    r14
0x180023c47  sub     rsp, 30h
0x180023c4b  mov     r14, [rsp+48h+arg_20]
0x180023c50  xor     esi, esi
0x180023c52  mov     [rax+20h], rsi
0x180023c56  mov     rbp, r8
0x180023c59  test    r14, r14
0x180023c5c  jnz     short loc_180023C66
0x180023c5e  lea     eax, [rsi+57h]
0x180023c61  jmp     loc_180023DD5
0x180023c66  mov     rcx, rbp
0x180023c69  call    ValidateMMFilterInternal
0x180023c6e  mov     edi, eax
0x180023c70  test    eax, eax
0x180023c72  jz      short loc_180023CB2
0x180023c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c7b  lea     rax, WPP_GLOBAL_Control
0x180023c82  cmp     rcx, rax
0x180023c85  jz      loc_180023DCC
0x180023c8b  test    byte ptr [rcx+1Ch], 10h
0x180023c8f  jz      loc_180023DCC
0x180023c95  mov     rcx, [rcx+10h]
0x180023c99  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180023ca0  mov     edx, 66h ; 'f'
0x180023ca5  mov     r9d, edi
0x180023ca8  call    WPP_SF_d
0x180023cad  jmp     loc_180023DCC
0x180023cb2  lea     rcx, gcSPDSection; lpCriticalSection
0x180023cb9  call    cs:__imp_EnterCriticalSection
0x180023cbf  mov     rbx, cs:gpIniMMFilter
0x180023cc6  test    rbx, rbx
0x180023cc9  jz      loc_180023D7C
0x180023ccf  mov     rdx, rbp
0x180023cd2  mov     rcx, rbx
0x180023cd5  call    EqualMMFilterPKeys
0x180023cda  test    eax, eax
0x180023cdc  jz      short loc_180023CED
0x180023cde  mov     rdx, rbp
0x180023ce1  mov     rcx, rbx
0x180023ce4  call    EqualMMFilterNonPKeys
0x180023ce9  test    eax, eax
0x180023ceb  jnz     short loc_180023CF6
0x180023ced  mov     rbx, [rbx+0C8h]
0x180023cf4  jmp     short loc_180023CC6
0x180023cf6  movups  xmm0, xmmword ptr [rbp+4]
0x180023cfa  lea     r8, [rsp+48h+arg_18]
0x180023cff  mov     rcx, rbx
0x180023d02  lea     rdx, [rsp+48h+var_28]
0x180023d07  movdqu  [rsp+48h+var_28], xmm0
0x180023d0d  call    CreateMMFilterHandle
0x180023d12  mov     edi, eax
0x180023d14  test    eax, eax
0x180023d16  jz      short loc_180023D50
0x180023d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d1f  lea     rax, WPP_GLOBAL_Control
0x180023d26  cmp     rcx, rax
0x180023d29  jz      short loc_180023D49
0x180023d2b  test    byte ptr [rcx+1Ch], 10h
0x180023d2f  jz      short loc_180023D49
0x180023d31  mov     rcx, [rcx+10h]
0x180023d35  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180023d3c  mov     edx, 68h ; 'h'
0x180023d41  mov     r9d, edi
0x180023d44  call    WPP_SF_d
0x180023d49  mov     rsi, [rsp+48h+arg_18]
0x180023d4e  jmp     short loc_180023DB2
0x180023d50  inc     dword ptr [rbx+7Ch]
0x180023d53  mov     rcx, [rsp+48h+arg_18]
0x180023d58  mov     rax, cs:gpMMFilterHandle
0x180023d5f  mov     [rcx+20h], rax
0x180023d63  mov     cs:gpMMFilterHandle, rcx
0x180023d6a  mov     [r14], rcx
0x180023d6d  lea     rcx, gcSPDSection; lpCriticalSection
0x180023d74  call    cs:__imp_LeaveCriticalSection
0x180023d7a  jmp     short loc_180023DD3
0x180023d7c  mov     edi, 32CFh
0x180023d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d88  lea     rax, WPP_GLOBAL_Control
0x180023d8f  cmp     rcx, rax
0x180023d92  jz      short loc_180023DB2
0x180023d94  test    byte ptr [rcx+1Ch], 10h
0x180023d98  jz      short loc_180023DB2
0x180023d9a  mov     rcx, [rcx+10h]
0x180023d9e  lea     r8, WPP_7c0a21c92210358d3ee1e33826382c7b_Traceguids
0x180023da5  mov     edx, 67h ; 'g'
0x180023daa  mov     r9d, edi
0x180023dad  call    WPP_SF_d
0x180023db2  lea     rcx, gcSPDSection; lpCriticalSection
0x180023db9  call    cs:__imp_LeaveCriticalSection
0x180023dbf  test    rsi, rsi
0x180023dc2  jz      short loc_180023DCC
0x180023dc4  mov     rcx, rsi
0x180023dc7  call    SPDApiBufferFree
0x180023dcc  mov     qword ptr [r14], 0
0x180023dd3  mov     eax, edi
0x180023dd5  mov     rbx, [rsp+48h+arg_0]
0x180023dda  mov     rbp, [rsp+48h+arg_8]
0x180023ddf  add     rsp, 30h
0x180023de3  pop     r14
0x180023de5  pop     rdi
0x180023de6  pop     rsi
0x180023de7  retn
```
