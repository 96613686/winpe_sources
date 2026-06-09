# CPortClient::SendComplexSyncRequest(ulong,void const *,short,CAlpcView const *,void *,short,long *)

- ea: `0x18000b05c`
- end: `0x18000b255`
- name: `?SendComplexSyncRequest@CPortClient@@QEAAJKPEBXFPEBVCAlpcView@@PEAXFPEAJ@Z`
- size: `505`
- prototype: `__int64 __fastcall(CPortClient *this, int, const void *, __int16, const struct CAlpcView *, void *, __int16, int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001a10`
- `0x1800035f0`
- `0x180005060`
- `0x18000af44`

## callees

- `0x18000352c`
- `0x18000b05c`
- `0x18000b25c`
- `0x18000ddac`
- `0x180015514`

## import_xrefs

- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000b189`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18000b189`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b22f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b0a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b22f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b0b8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b0b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b23d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b23d`

## pseudocode

```c
__int64 __fastcall CPortClient::SendComplexSyncRequest(
        CPortClient *this,
        int a2,
        const void *a3,
        __int16 a4,
        const struct CAlpcView *a5,
        void *a6,
        __int16 a7,
        int *a8)
{
  size_t v8; // rbx
  __int16 v10; // ax
  __int64 v13; // r13
  HANDLE ProcessHeap; // rax
  int *v15; // rax
  void *v16; // rdx
  unsigned int v17; // r8d
  int *v18; // rdi
  unsigned int v19; // ebx
  __int128 v20; // xmm0
  __int64 v21; // xmm1_8
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // r9d
  HANDLE v25; // rax
  int v27; // [rsp+20h] [rbp-50h]
  void *v28; // [rsp+28h] [rbp-48h]
  __int64 v29; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v30[5]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v8 = a4;
  HIDWORD(v30[4]) = 0;
  v10 = a4;
  LODWORD(v30[0]) = 0;
  if ( a4 <= a7 )
    v10 = a7;
  v13 = (unsigned __int16)(v10 + 48);
  memset((char *)v30 + 4, 0, 32);
  ProcessHeap = GetProcessHeap();
  v15 = (int *)HeapAlloc(ProcessHeap, 8u, (unsigned int)v13);
  v18 = v15;
  if ( v15 )
  {
    v15[10] = a2;
    *(_WORD *)v15 = v8 + 8;
    *((_WORD *)v15 + 1) = v8 + 48;
    if ( (__int16)(v8 + 48) > 512 )
      wil::details::in1diag3::Log_Hr(retaddr, v16, v17, (const char *)0x8007029CLL, v27);
    memcpy_0(v18 + 12, a3, v8);
    LODWORD(v30[0]) = 0x40000000;
    if ( a5 )
    {
      v20 = *(_OWORD *)((char *)a5 + 8);
      HIDWORD(v30[0]) = 0x40000000;
      v21 = *((_QWORD *)a5 + 3);
      v22 = *((_QWORD *)a5 + 5);
      *(_OWORD *)&v30[1] = v20;
      v30[4] = v22;
      v30[3] = v21;
    }
    v23 = *((_QWORD *)this + 2);
    v29 = v13;
    v19 = NtAlpcSendWaitReceivePort(v23, 0x20000, v18, v30, v18) | 0x10000000;
    CPortClient::CheckHRESULT(this, v19);
    if ( v24 >= 0 )
    {
      v19 = 0;
      if ( v18[11] >= 0 && a6 && a7 )
      {
        if ( *(_WORD *)v18 == a7 + 8 )
        {
          memcpy_0(a6, v18 + 12, a7);
        }
        else
        {
          v19 = -2147024872;
          MilInstrumentationCheckHR_MaybeFailFast(
            4u,
            &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
            9u,
            -2147024872,
            0x206u,
            &v29);
        }
      }
      *a8 = v18[11];
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(4u, &CPortClient::MILINSTRUMENTATIONHRESULTLIST, 9u, v19, 0x1FEu, &v29);
    }
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v18);
  }
  else
  {
    v19 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(
      4u,
      &CPortClient::MILINSTRUMENTATIONHRESULTLIST,
      9u,
      -2147024882,
      0x1E4u,
      v28);
  }
  return v19;
}

```

## disassembly

```asm
0x18000b05c  push    rbp
0x18000b05e  push    rbx
0x18000b05f  push    rdi
0x18000b060  push    r12
0x18000b062  push    r13
0x18000b064  push    r14
0x18000b066  push    r15
0x18000b068  mov     rbp, rsp
0x18000b06b  sub     rsp, 70h
0x18000b06f  xor     eax, eax
0x18000b071  movsx   rbx, r9w
0x18000b075  cmp     bx, [rbp+arg_30]
0x18000b079  xorps   xmm0, xmm0
0x18000b07c  mov     [rbp+var_4], eax
0x18000b07f  mov     r12, r8
0x18000b082  movzx   eax, bx
0x18000b085  mov     [rbp+var_28], 0
0x18000b08c  cmovle  ax, [rbp+arg_30]
0x18000b091  mov     r14d, edx
0x18000b094  add     ax, 30h ; '0'
0x18000b098  mov     r15, rcx
0x18000b09b  movzx   r13d, ax
0x18000b09f  movups  [rbp+var_24], xmm0
0x18000b0a3  movups  [rbp+var_14], xmm0
0x18000b0a7  call    cs:__imp_GetProcessHeap
0x18000b0ad  mov     r8d, r13d; dwBytes
0x18000b0b0  mov     edx, 8; dwFlags
0x18000b0b5  mov     rcx, rax; hHeap
0x18000b0b8  call    cs:__imp_HeapAlloc
0x18000b0be  mov     rdi, rax
0x18000b0c1  test    rax, rax
0x18000b0c4  jnz     short loc_18000B0EE
0x18000b0c6  mov     ebx, 8007000Eh
0x18000b0cb  mov     [rsp+70h+var_50], 1E4h; unsigned int
0x18000b0d3  mov     r9d, ebx; int
0x18000b0d6  lea     r8d, [rax+9]; unsigned int
0x18000b0da  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x18000b0e1  lea     ecx, [rax+4]; unsigned int
0x18000b0e4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000b0e9  jmp     loc_18000B243
0x18000b0ee  mov     [rax+28h], r14d
0x18000b0f2  mov     ecx, 200h
0x18000b0f7  mov     eax, 8
0x18000b0fc  add     eax, ebx
0x18000b0fe  mov     [rdi], ax
0x18000b101  add     ax, 28h ; '('
0x18000b105  mov     [rdi+2], ax
0x18000b109  cmp     ax, cx
0x18000b10c  jle     short loc_18000B11D
0x18000b10e  mov     rcx, [rbp+38h]; this
0x18000b112  mov     r9d, 8007029Ch; char *
0x18000b118  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000b11d  mov     r8, rbx; Size
0x18000b120  lea     rcx, [rdi+30h]; void *
0x18000b124  mov     rdx, r12; Src
0x18000b127  call    memcpy_0
0x18000b12c  mov     rax, [rbp+arg_20]
0x18000b130  xor     r12d, r12d
0x18000b133  mov     ecx, 40000000h
0x18000b138  mov     [rbp+var_28], ecx
0x18000b13b  test    rax, rax
0x18000b13e  jz      short loc_18000B15D
0x18000b140  movups  xmm0, xmmword ptr [rax+8]
0x18000b144  mov     dword ptr [rbp+var_24], ecx
0x18000b147  movsd   xmm1, qword ptr [rax+18h]
0x18000b14c  mov     rax, [rax+28h]
0x18000b150  movups  [rbp+var_24+4], xmm0
0x18000b154  mov     qword ptr [rbp+var_14+0Ch], rax
0x18000b158  movsd   qword ptr [rbp+var_14+4], xmm1
0x18000b15d  mov     rcx, [r15+10h]
0x18000b161  lea     rax, [rbp+var_30]
0x18000b165  mov     [rsp+70h+var_38], r12
0x18000b16a  lea     r9, [rbp+var_28]
0x18000b16e  mov     [rsp+70h+var_40], r12
0x18000b173  mov     r8, rdi
0x18000b176  mov     [rsp+70h+var_48], rax; void *
0x18000b17b  mov     edx, 20000h
0x18000b180  mov     qword ptr [rsp+70h+var_50], rdi
0x18000b185  mov     [rbp+var_30], r13
0x18000b189  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18000b18f  mov     ebx, eax
0x18000b191  mov     rcx, r15; this
0x18000b194  bts     ebx, 1Ch
0x18000b198  mov     r9d, eax
0x18000b19b  mov     edx, ebx; int
0x18000b19d  call    ?CheckHRESULT@CPortClient@@AEAAJJ@Z; CPortClient::CheckHRESULT(long)
0x18000b1a2  test    r9d, r9d
0x18000b1a5  jns     short loc_18000B1CA
0x18000b1a7  mov     r8d, 9; unsigned int
0x18000b1ad  mov     [rsp+70h+var_50], 1FEh; unsigned int
0x18000b1b5  mov     r9d, ebx; int
0x18000b1b8  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x18000b1bf  lea     ecx, [r8-5]; unsigned int
0x18000b1c3  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000b1c8  jmp     short loc_18000B22F
0x18000b1ca  mov     ebx, r12d
0x18000b1cd  cmp     [rdi+2Ch], r12d
0x18000b1d1  jl      short loc_18000B226
0x18000b1d3  mov     rcx, [rbp+arg_28]; void *
0x18000b1d7  test    rcx, rcx
0x18000b1da  jz      short loc_18000B226
0x18000b1dc  cmp     [rbp+arg_30], r12w
0x18000b1e1  jz      short loc_18000B226
0x18000b1e3  movzx   eax, [rbp+arg_30]
0x18000b1e7  add     ax, 8
0x18000b1eb  cmp     [rdi], ax
0x18000b1ee  jz      short loc_18000B218
0x18000b1f0  mov     r8d, 9; unsigned int
0x18000b1f6  mov     [rsp+70h+var_50], 206h; unsigned int
0x18000b1fe  mov     ebx, 80070018h
0x18000b203  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CPortClient@@2QBJB; int *
0x18000b20a  mov     r9d, ebx; int
0x18000b20d  lea     ecx, [r8-5]; unsigned int
0x18000b211  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000b216  jmp     short loc_18000B226
0x18000b218  movsx   r8, [rbp+arg_30]; Size
0x18000b21d  lea     rdx, [rdi+30h]; Src
0x18000b221  call    memcpy_0
0x18000b226  mov     rcx, [rbp+arg_38]
0x18000b22a  mov     edx, [rdi+2Ch]
0x18000b22d  mov     [rcx], edx
0x18000b22f  call    cs:__imp_GetProcessHeap
0x18000b235  mov     r8, rdi; lpMem
0x18000b238  xor     edx, edx; dwFlags
0x18000b23a  mov     rcx, rax; hHeap
0x18000b23d  call    cs:__imp_HeapFree
0x18000b243  mov     eax, ebx
0x18000b245  add     rsp, 70h
0x18000b249  pop     r15
0x18000b24b  pop     r14
0x18000b24d  pop     r13
0x18000b24f  pop     r12
0x18000b251  pop     rdi
0x18000b252  pop     rbx
0x18000b253  pop     rbp
0x18000b254  retn
```
