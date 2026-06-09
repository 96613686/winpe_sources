# PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StartActivity(ushort const *,ushort const *,char const *,uint,unsigned __int64)

- ea: `0x18000e008`
- end: `0x18000e259`
- name: `?StartActivity@NotifySingleSubscriberActivity@PpfTraceLoggingProvider@@QEAAXPEBG0PEBDI_K@Z`
- size: `593`
- prototype: `void __fastcall(PpfTraceLoggingProvider::NotifySingleSubscriberActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const char *, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cfec`

## callees

- `0x180001640`
- `0x180003270`
- `0x1800070e0`
- `0x18000de98`
- `0x18000e008`
- `0x18000e680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e09e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e21c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e09e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e21c`

## pseudocode

```c
void __fastcall PpfTraceLoggingProvider::NotifySingleSubscriberActivity::StartActivity(
        PpfTraceLoggingProvider::NotifySingleSubscriberActivity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const char *a4,
        unsigned int a5,
        unsigned __int64 a6)
{
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // r15
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rax
  int v18; // eax
  int v19; // edx
  __int64 v20; // rax
  int v21; // eax
  _QWORD *v22; // rbx
  _QWORD *Local; // rax
  unsigned int v24; // [rsp+30h] [rbp-A9h] BYREF
  DWORD v25; // [rsp+34h] [rbp-A5h] BYREF
  __int64 v26; // [rsp+38h] [rbp-A1h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp-99h] BYREF
  __int64 v28; // [rsp+48h] [rbp-91h] BYREF
  char v29[32]; // [rsp+50h] [rbp-89h] BYREF
  __int64 *v30; // [rsp+70h] [rbp-69h]
  __int64 v31; // [rsp+78h] [rbp-61h]
  DWORD *v32; // [rsp+80h] [rbp-59h]
  __int64 v33; // [rsp+88h] [rbp-51h]
  const unsigned __int16 *v34; // [rsp+90h] [rbp-49h]
  int v35; // [rsp+98h] [rbp-41h]
  int v36; // [rsp+9Ch] [rbp-3Dh]
  const unsigned __int16 *v37; // [rsp+A0h] [rbp-39h]
  int v38; // [rsp+A8h] [rbp-31h]
  int v39; // [rsp+ACh] [rbp-2Dh]
  const char *v40; // [rsp+B0h] [rbp-29h]
  int v41; // [rsp+B8h] [rbp-21h]
  int v42; // [rsp+BCh] [rbp-1Dh]
  unsigned int *v43; // [rsp+C0h] [rbp-19h]
  __int64 v44; // [rsp+C8h] [rbp-11h]
  unsigned __int64 *v45; // [rsp+D0h] [rbp-9h]
  __int64 v46; // [rsp+D8h] [rbp-1h]
  __int64 *v47; // [rsp+E0h] [rbp+7h]
  __int64 v48; // [rsp+E8h] [rbp+Fh]

  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v10 = PpfTraceLoggingProvider::Provider();
  v12 = v10;
  if ( *(_DWORD *)v10 > 5u )
  {
    v11 = *((_QWORD *)v10 + 2);
    if ( (v11 & 0x400000000000LL) != 0 && (*((_QWORD *)v10 + 3) & 0x400000000000LL) == *((_QWORD *)v10 + 3) )
    {
      v27 = a6;
      v24 = a5;
      v26 = 0x1000000;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v25 = CurrentThreadId;
      v28 = 0x1000000;
      if ( !*(_BYTE *)(v14 + 4)
        || (v15 = v14 + 24, !*(_DWORD *)(v14 + 24))
        && !*(_DWORD *)(v14 + 28)
        && !*(_DWORD *)(v14 + 32)
        && !*(_DWORD *)(v14 + 36) )
      {
        v15 = 0;
      }
      v48 = 8;
      v47 = &v26;
      v16 = -1;
      v46 = 8;
      v45 = &v27;
      v43 = &v24;
      v44 = 4;
      if ( a4 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a4[v17] );
        v18 = v17 + 1;
      }
      else
      {
        a4 = (const char *)&dword_18005C2E4;
        v18 = 1;
      }
      v40 = a4;
      v19 = 2;
      v41 = v18;
      v42 = 0;
      if ( a3 )
      {
        v20 = -1;
        do
          ++v20;
        while ( a3[v20] );
        v21 = 2 * v20 + 2;
      }
      else
      {
        a3 = &Format;
        v21 = 2;
      }
      v37 = a3;
      v38 = v21;
      v39 = 0;
      if ( a2 )
      {
        do
          ++v16;
        while ( a2[v16] );
        v19 = 2 * v16 + 2;
      }
      else
      {
        a2 = &Format;
      }
      v35 = v19;
      v32 = &v25;
      v34 = a2;
      v30 = &v28;
      v36 = 0;
      v33 = 4;
      v31 = 8;
      tlgWriteTransfer_EventWriteTransfer(v12, &byte_180067F3F, v14 + 8, v15, 10, v29);
    }
  }
  if ( !*((_DWORD *)this + 78) )
  {
    v22 = (_QWORD *)((char *)this + 288);
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(
                          v11,
                          1);
      *v22 = Local;
      if ( Local )
      {
        *((_QWORD *)this + 38) = *Local;
        *Local = v22;
        *((_DWORD *)this + 78) = GetCurrentThreadId();
      }
    }
    else
    {
      *v22 = 0;
    }
  }
}

```

## disassembly

```asm
0x18000e008  mov     [rsp-8+arg_8], rbx
0x18000e00d  mov     [rsp-8+arg_10], rsi
0x18000e012  push    rbp
0x18000e013  push    rdi
0x18000e014  push    r13
0x18000e016  push    r14
0x18000e018  push    r15
0x18000e01a  lea     rbp, [rsp-27h]
0x18000e01f  sub     rsp, 100h
0x18000e026  mov     rax, cs:__security_cookie
0x18000e02d  xor     rax, rsp
0x18000e030  mov     [rbp+47h+var_30], rax
0x18000e034  mov     rbx, r9
0x18000e037  mov     rsi, r8
0x18000e03a  mov     r14, rdx
0x18000e03d  mov     rdi, rcx
0x18000e040  call    ?zInternalStart@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18000e045  call    ?Provider@PpfTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; PpfTraceLoggingProvider::Provider(void)
0x18000e04a  xor     r13d, r13d
0x18000e04d  mov     r15, rax
0x18000e050  mov     edx, [rax]
0x18000e052  cmp     edx, 5
0x18000e055  jbe     loc_18000E1EA
0x18000e05b  mov     rdx, [rax+18h]
0x18000e05f  mov     r8, 400000000000h
0x18000e069  mov     rcx, [rax+10h]
0x18000e06d  test    r8, rcx
0x18000e070  jz      loc_18000E1EA
0x18000e076  mov     rax, rdx
0x18000e079  and     rax, r8
0x18000e07c  cmp     rax, rdx
0x18000e07f  jnz     loc_18000E1EA
0x18000e085  mov     rax, [rbp+47h+arg_28]
0x18000e089  mov     [rsp+120h+var_E0], rax
0x18000e08e  mov     eax, [rbp+47h+arg_20]
0x18000e091  mov     [rsp+120h+var_F0], eax
0x18000e095  mov     [rsp+120h+var_E8], 1000000h
0x18000e09e  call    cs:__imp_GetCurrentThreadId
0x18000e0a5  nop     dword ptr [rax+rax+00h]
0x18000e0aa  mov     r8, [rdi+110h]
0x18000e0b1  mov     [rsp+120h+var_EC], eax
0x18000e0b5  mov     [rsp+120h+var_D8], 1000000h
0x18000e0be  cmp     [r8+4], r13b
0x18000e0c2  jz      short loc_18000E0DF
0x18000e0c4  lea     r9, [r8+18h]
0x18000e0c8  cmp     [r9], r13d
0x18000e0cb  jnz     short loc_18000E0E2
0x18000e0cd  cmp     [r9+4], r13d
0x18000e0d1  jnz     short loc_18000E0E2
0x18000e0d3  cmp     [r9+8], r13d
0x18000e0d7  jnz     short loc_18000E0E2
0x18000e0d9  cmp     [r9+0Ch], r13d
0x18000e0dd  jnz     short loc_18000E0E2
0x18000e0df  mov     r9, r13
0x18000e0e2  lea     rax, [rsp+120h+var_E8]
0x18000e0e7  mov     [rbp+47h+var_38], 8
0x18000e0ef  mov     [rbp+47h+var_40], rax
0x18000e0f3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000e0f7  mov     [rbp+47h+var_48], 8
0x18000e0ff  lea     rax, [rsp+120h+var_E0]
0x18000e104  mov     [rbp+47h+var_50], rax
0x18000e108  lea     rax, [rsp+120h+var_F0]
0x18000e10d  mov     [rbp+47h+var_60], rax
0x18000e111  mov     [rbp+47h+var_58], 4
0x18000e119  test    rbx, rbx
0x18000e11c  jz      short loc_18000E12E
0x18000e11e  mov     rax, rcx
0x18000e121  inc     rax
0x18000e124  cmp     [rbx+rax], r13b
0x18000e128  jnz     short loc_18000E121
0x18000e12a  inc     eax
0x18000e12c  jmp     short loc_18000E13A
0x18000e12e  lea     rbx, dword_18005C2E4
0x18000e135  mov     eax, 1
0x18000e13a  mov     [rbp+47h+var_70], rbx
0x18000e13e  mov     edx, 2
0x18000e143  mov     [rbp+47h+var_68], eax
0x18000e146  mov     [rbp+47h+var_64], r13d
0x18000e14a  test    rsi, rsi
0x18000e14d  jz      short loc_18000E165
0x18000e14f  mov     rax, rcx
0x18000e152  inc     rax
0x18000e155  cmp     [rsi+rax*2], r13w
0x18000e15a  jnz     short loc_18000E152
0x18000e15c  lea     eax, ds:2[rax*2]
0x18000e163  jmp     short loc_18000E16E
0x18000e165  lea     rsi, Format
0x18000e16c  mov     eax, edx
0x18000e16e  mov     [rbp+47h+var_80], rsi
0x18000e172  mov     [rbp+47h+var_78], eax
0x18000e175  mov     [rbp+47h+var_74], r13d
0x18000e179  test    r14, r14
0x18000e17c  jz      short loc_18000E191
0x18000e17e  inc     rcx
0x18000e181  cmp     [r14+rcx*2], r13w
0x18000e186  jnz     short loc_18000E17E
0x18000e188  lea     edx, ds:2[rcx*2]
0x18000e18f  jmp     short loc_18000E198
0x18000e191  lea     r14, Format
0x18000e198  lea     rax, [rsp+120h+var_EC]
0x18000e19d  mov     [rbp+47h+var_88], edx
0x18000e1a0  mov     [rbp+47h+var_A0], rax
0x18000e1a4  lea     rdx, byte_180067F3F
0x18000e1ab  lea     rax, [rsp+120h+var_D8]
0x18000e1b0  mov     [rbp+47h+var_90], r14
0x18000e1b4  mov     [rbp+47h+var_B0], rax
0x18000e1b8  add     r8, 8
0x18000e1bc  lea     rax, [rsp+120h+var_D0]
0x18000e1c1  mov     [rbp+47h+var_84], r13d
0x18000e1c5  mov     [rsp+120h+var_F8], rax
0x18000e1ca  mov     rcx, r15
0x18000e1cd  mov     [rsp+120h+var_100], 0Ah
0x18000e1d5  mov     [rbp+47h+var_98], 4
0x18000e1dd  mov     [rbp+47h+var_A8], 8
0x18000e1e5  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e1ea  cmp     [rdi+138h], r13d
0x18000e1f1  jnz     short loc_18000E230
0x18000e1f3  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, r13; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000e1fa  lea     rbx, [rdi+120h]
0x18000e201  jz      short loc_18000E22D
0x18000e203  mov     dl, 1
0x18000e205  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x18000e20a  mov     [rbx], rax
0x18000e20d  test    rax, rax
0x18000e210  jz      short loc_18000E230
0x18000e212  mov     rcx, [rax]
0x18000e215  mov     [rbx+10h], rcx
0x18000e219  mov     [rax], rbx
0x18000e21c  call    cs:__imp_GetCurrentThreadId
0x18000e223  nop     dword ptr [rax+rax+00h]
0x18000e228  mov     [rbx+18h], eax
0x18000e22b  jmp     short loc_18000E230
0x18000e22d  mov     [rbx], r13
0x18000e230  mov     rcx, [rbp+47h+var_30]
0x18000e234  xor     rcx, rsp; StackCookie
0x18000e237  call    __security_check_cookie
0x18000e23c  lea     r11, [rsp+120h+var_20]
0x18000e244  mov     rbx, [r11+38h]
0x18000e248  mov     rsi, [r11+40h]
0x18000e24c  mov     rsp, r11
0x18000e24f  pop     r15
0x18000e251  pop     r14
0x18000e253  pop     r13
0x18000e255  pop     rdi
0x18000e256  pop     rbp
0x18000e257  retn
```
