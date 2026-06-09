# InProc_InitiateQuery

- ea: `0x180092f48`
- end: `0x18009317d`
- name: `InProc_InitiateQuery`
- size: `565`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180013658`
- `0x1800937b0`

## callees

- `0x18002a160`
- `0x1800317e0`
- `0x18004a0b0`
- `0x1800693f4`
- `0x180092f48`
- `0x18009e728`
- `0x1800b6588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092fd3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092fbf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180092fbf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093119`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180093119`

## pseudocode

```c
__int64 __fastcall InProc_InitiateQuery(
        __int64 a1,
        void *a2,
        __int16 a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        int a7,
        int a8,
        int a9,
        __int128 *a10,
        __int64 a11,
        __int64 a12)
{
  __int64 QueryBlob; // rbx
  DWORD LastError; // edi
  HANDLE EventW; // rsi
  __int64 StringCopy_W; // rax
  __int128 v21; // xmm0
  DWORD v22; // eax
  _OWORD v23[4]; // [rsp+20h] [rbp-48h] BYREF

  if ( g_fVelocityInprocDnsCleanup )
    return 120;
  QueryBlob = Query_AllocateQueryBlob(2);
  if ( !QueryBlob )
    goto LABEL_4;
  v23[0] = *a10;
  if ( (unsigned int)Rpc_IsEmptyCallbackInfo(v23) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      goto LABEL_17;
    }
  }
  else
  {
    EventW = 0;
    Query_InProcPrepare(QueryBlob, a1, *((_QWORD *)a10 + 1));
  }
  if ( a2 )
  {
    StringCopy_W = Dns_CreateStringCopy_W(a2);
    *(_QWORD *)(QueryBlob + 224) = StringCopy_W;
    if ( !StringCopy_W )
    {
LABEL_4:
      LastError = 14;
LABEL_21:
      DeRefQueryBlobEx((char *)QueryBlob, (__int64)"InProc_InitiateQuery", 236, 2);
      return LastError;
    }
    *(_QWORD *)(QueryBlob + 232) = StringCopy_W;
    *(_QWORD *)(QueryBlob + 240) = StringCopy_W;
  }
  v21 = *a10;
  *(_WORD *)(QueryBlob + 256) = a3;
  *(_QWORD *)(QueryBlob + 264) = *a4;
  *(_QWORD *)(QueryBlob + 600) = *a4;
  *(_QWORD *)(QueryBlob + 1032) = a5;
  *(_DWORD *)(QueryBlob + 396) = a9;
  *(_DWORD *)(QueryBlob + 404) = a6;
  *(_QWORD *)(QueryBlob + 288) = a11;
  *(_QWORD *)(QueryBlob + 1128) = InProc_ProcessQueryResult;
  *(_QWORD *)(QueryBlob + 368) = a12 + 16;
  *(_DWORD *)(QueryBlob + 408) = a7;
  *(_DWORD *)(QueryBlob + 412) = a8;
  *(_OWORD *)(QueryBlob + 272) = v21;
  *(_QWORD *)(QueryBlob + 296) = a12;
  *(_QWORD *)(QueryBlob + 1168) = EventW;
  *(_QWORD *)(QueryBlob + 352) = a4;
  if ( (*(_DWORD *)a4 & 0x200LL) != 0 )
    *(_QWORD *)(QueryBlob + 376) = a12 + 24;
  v22 = Query_InProcess((LPVOID)QueryBlob);
  LastError = v22;
  if ( v22 != 9506 )
  {
    *(_DWORD *)(a12 + 4) = v22;
    goto LABEL_21;
  }
  v23[0] = *(_OWORD *)(QueryBlob + 272);
  if ( (unsigned int)Rpc_IsEmptyCallbackInfo(v23) )
  {
    WaitForSingleObject(EventW, 0xFFFFFFFF);
    LastError = *(_DWORD *)(QueryBlob + 508);
LABEL_17:
    if ( LastError != 9506 )
      goto LABEL_21;
  }
  v23[0] = *a10;
  if ( (unsigned int)Rpc_IsEmptyCallbackInfo(v23) )
    goto LABEL_21;
  return LastError;
}

```

## disassembly

```asm
0x180092f48  push    rbx
0x180092f4a  push    rbp
0x180092f4b  push    rsi
0x180092f4c  push    rdi
0x180092f4d  push    r12
0x180092f4f  push    r14
0x180092f51  push    r15
0x180092f53  sub     rsp, 30h
0x180092f57  cmp     cs:g_fVelocityInprocDnsCleanup, 0
0x180092f5e  mov     r15, r9
0x180092f61  movzx   r12d, r8w
0x180092f65  mov     rdi, rdx
0x180092f68  mov     rbp, rcx
0x180092f6b  jz      short loc_180092F77
0x180092f6d  mov     eax, 78h ; 'x'
0x180092f72  jmp     loc_18009316D
0x180092f77  mov     ecx, 2
0x180092f7c  call    Query_AllocateQueryBlob
0x180092f81  mov     rbx, rax
0x180092f84  test    rax, rax
0x180092f87  jnz     short loc_180092F93
0x180092f89  mov     edi, 0Eh
0x180092f8e  jmp     loc_180093150
0x180092f93  mov     r14, [rsp+68h+arg_48]
0x180092f9b  lea     rcx, [rsp+68h+var_48]
0x180092fa0  movaps  xmm0, xmmword ptr [r14]
0x180092fa4  movdqa  [rsp+68h+var_48], xmm0
0x180092faa  call    Rpc_IsEmptyCallbackInfo
0x180092faf  test    eax, eax
0x180092fb1  jz      short loc_180092FE6
0x180092fb3  xor     r9d, r9d; lpName
0x180092fb6  xor     r8d, r8d; bInitialState
0x180092fb9  xor     ecx, ecx; lpEventAttributes
0x180092fbb  lea     edx, [r9+1]; bManualReset
0x180092fbf  call    cs:__imp_CreateEventW
0x180092fc6  nop     dword ptr [rax+rax+00h]
0x180092fcb  mov     rsi, rax
0x180092fce  test    rax, rax
0x180092fd1  jnz     short loc_180092FF7
0x180092fd3  call    cs:__imp_GetLastError
0x180092fda  nop     dword ptr [rax+rax+00h]
0x180092fdf  mov     edi, eax
0x180092fe1  jmp     loc_18009312B
0x180092fe6  mov     r8, [r14+8]
0x180092fea  xor     esi, esi
0x180092fec  mov     rdx, rbp
0x180092fef  mov     rcx, rbx
0x180092ff2  call    Query_InProcPrepare
0x180092ff7  test    rdi, rdi
0x180092ffa  jz      short loc_180093022
0x180092ffc  mov     rcx, rdi; Src
0x180092fff  call    Dns_CreateStringCopy_W
0x180093004  mov     [rbx+0E0h], rax
0x18009300b  test    rax, rax
0x18009300e  jz      loc_180092F89
0x180093014  mov     [rbx+0E8h], rax
0x18009301b  mov     [rbx+0F0h], rax
0x180093022  mov     rbp, [rsp+68h+arg_58]
0x18009302a  movaps  xmm0, xmmword ptr [r14]
0x18009302e  mov     [rbx+100h], r12w
0x180093036  mov     rax, [r15]
0x180093039  mov     [rbx+108h], rax
0x180093040  mov     rax, [r15]
0x180093043  mov     [rbx+258h], rax
0x18009304a  mov     rax, [rsp+68h+arg_20]
0x180093052  mov     [rbx+408h], rax
0x180093059  mov     eax, [rsp+68h+arg_40]
0x180093060  mov     [rbx+18Ch], eax
0x180093066  mov     eax, [rsp+68h+arg_28]
0x18009306d  mov     [rbx+194h], eax
0x180093073  mov     rax, [rsp+68h+arg_50]
0x18009307b  mov     [rbx+120h], rax
0x180093082  lea     rax, InProc_ProcessQueryResult
0x180093089  mov     [rbx+468h], rax
0x180093090  lea     rax, [rbp+10h]
0x180093094  mov     [rbx+170h], rax
0x18009309b  mov     eax, [rsp+68h+arg_30]
0x1800930a2  mov     [rbx+198h], eax
0x1800930a8  mov     eax, [rsp+68h+arg_38]
0x1800930af  mov     [rbx+19Ch], eax
0x1800930b5  movdqu  xmmword ptr [rbx+110h], xmm0
0x1800930bd  mov     [rbx+128h], rbp
0x1800930c4  mov     [rbx+490h], rsi
0x1800930cb  mov     [rbx+160h], r15
0x1800930d2  mov     eax, [r15]
0x1800930d5  bt      rax, 9
0x1800930da  jnb     short loc_1800930E7
0x1800930dc  lea     rax, [rbp+18h]
0x1800930e0  mov     [rbx+178h], rax
0x1800930e7  mov     rcx, rbx; lpMem
0x1800930ea  call    Query_InProcess
0x1800930ef  mov     edi, eax
0x1800930f1  cmp     eax, 2522h
0x1800930f6  jnz     short loc_18009314D
0x1800930f8  movups  xmm0, xmmword ptr [rbx+110h]
0x1800930ff  lea     rcx, [rsp+68h+var_48]
0x180093104  movdqu  [rsp+68h+var_48], xmm0
0x18009310a  call    Rpc_IsEmptyCallbackInfo
0x18009310f  test    eax, eax
0x180093111  jz      short loc_180093133
0x180093113  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180093116  mov     rcx, rsi; hHandle
0x180093119  call    cs:__imp_WaitForSingleObject
0x180093120  nop     dword ptr [rax+rax+00h]
0x180093125  mov     edi, [rbx+1FCh]
0x18009312b  cmp     edi, 2522h
0x180093131  jnz     short loc_180093150
0x180093133  movaps  xmm0, xmmword ptr [r14]
0x180093137  lea     rcx, [rsp+68h+var_48]
0x18009313c  movdqa  [rsp+68h+var_48], xmm0
0x180093142  call    Rpc_IsEmptyCallbackInfo
0x180093147  test    eax, eax
0x180093149  jz      short loc_18009316B
0x18009314b  jmp     short loc_180093150
0x18009314d  mov     [rbp+4], eax
0x180093150  mov     r9d, 2
0x180093156  lea     rdx, aInprocInitiate; "InProc_InitiateQuery"
0x18009315d  mov     r8d, 6ECh
0x180093163  mov     rcx, rbx; lpMem
0x180093166  call    DeRefQueryBlobEx
0x18009316b  mov     eax, edi
0x18009316d  add     rsp, 30h
0x180093171  pop     r15
0x180093173  pop     r14
0x180093175  pop     r12
0x180093177  pop     rdi
0x180093178  pop     rsi
0x180093179  pop     rbp
0x18009317a  pop     rbx
0x18009317b  retn
```
