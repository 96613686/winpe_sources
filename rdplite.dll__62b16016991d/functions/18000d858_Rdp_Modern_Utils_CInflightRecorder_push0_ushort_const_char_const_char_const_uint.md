# Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)

- ea: `0x18000d858`
- end: `0x18000d986`
- name: `?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z`
- size: `302`
- prototype: `void __usercall(Rdp::Modern::Utils::CInflightRecorder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const char *@<r8>, const char *@<r9>, unsigned int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cbc0`
- `0x18000d98c`
- `0x18001a5f8`
- `0x18001e824`
- `0x18001ec84`
- `0x1800205d4`
- `0x1800224e4`
- `0x1800227a0`

## callees

- `0x180008304`
- `0x18000d858`
- `0x18000dca0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d900`

## pseudocode

```c
void __fastcall Rdp::Modern::Utils::CInflightRecorder::push0(
        Rdp::Modern::Utils::CInflightRecorder *this,
        const unsigned __int16 *a2,
        const char *a3,
        const char *a4,
        unsigned int a5)
{
  bool v9; // bl
  char CurrentThreadId; // al
  int v11; // [rsp+20h] [rbp-C1h]
  int v12; // [rsp+28h] [rbp-B9h]
  int v13; // [rsp+30h] [rbp-B1h]
  int v14; // [rsp+38h] [rbp-A9h]
  int v15; // [rsp+60h] [rbp-81h] BYREF
  __int128 v16; // [rsp+64h] [rbp-7Dh]
  int v17; // [rsp+74h] [rbp-6Dh]
  const unsigned __int16 *v18; // [rsp+78h] [rbp-69h]
  DWORD v19; // [rsp+80h] [rbp-61h]
  int v20; // [rsp+84h] [rbp-5Dh]
  __int64 v21; // [rsp+88h] [rbp-59h]
  const char *v22; // [rsp+90h] [rbp-51h]
  const char *v23; // [rsp+98h] [rbp-49h]
  unsigned int v24; // [rsp+A0h] [rbp-41h]
  int v25; // [rsp+A4h] [rbp-3Dh]
  __int64 v26; // [rsp+A8h] [rbp-39h]
  __int64 v27; // [rsp+B0h] [rbp-31h]
  __int64 v28; // [rsp+B8h] [rbp-29h]
  __int64 v29; // [rsp+C0h] [rbp-21h]
  __int64 v30; // [rsp+C8h] [rbp-19h]
  __int128 v31; // [rsp+D0h] [rbp-11h]
  __int128 v32; // [rsp+E0h] [rbp-1h]
  __int64 v33; // [rsp+F0h] [rbp+Fh]

  v9 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    WPP_RECORDER_AND_TRACE_SF_DsS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v12,
      v13,
      v14,
      CurrentThreadId,
      (__int64)a3,
      (__int64)a2);
  }
  v15 = 2;
  v18 = a2;
  v16 = 0;
  v17 = 0;
  v22 = a3;
  v19 = GetCurrentThreadId();
  v23 = a4;
  v20 = 0;
  v21 = 0;
  v24 = a5;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  Rdp::Modern::Utils::CInflightRecorder::pushInternal(this, (const struct wil::FailureInfo *)&v15);
}

```

## disassembly

```asm
0x18000d858  push    rbp
0x18000d85a  push    rbx
0x18000d85b  push    rsi
0x18000d85c  push    rdi
0x18000d85d  push    r12
0x18000d85f  push    r14
0x18000d861  push    r15
0x18000d863  lea     rbp, [rsp-1Fh]
0x18000d868  sub     rsp, 100h
0x18000d86f  mov     r15, r9
0x18000d872  mov     rsi, r8
0x18000d875  mov     r14, rdx
0x18000d878  mov     r12, rcx
0x18000d87b  mov     rax, cs:WPP_GLOBAL_Control
0x18000d882  lea     rcx, WPP_GLOBAL_Control
0x18000d889  cmp     rax, rcx
0x18000d88c  jz      short loc_18000D89E
0x18000d88e  test    byte ptr [rax+1Ch], 2
0x18000d892  jz      short loc_18000D89E
0x18000d894  cmp     byte ptr [rax+19h], 4
0x18000d898  jb      short loc_18000D89E
0x18000d89a  mov     bl, 1
0x18000d89c  jmp     short loc_18000D8A0
0x18000d89e  xor     bl, bl
0x18000d8a0  lea     rax, WPP_RECORDER_INITIALIZED
0x18000d8a7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000d8ae  setnz   dil
0x18000d8b2  test    bl, bl
0x18000d8b4  jnz     short loc_18000D8BB
0x18000d8b6  test    dil, dil
0x18000d8b9  jz      short loc_18000D8E8
0x18000d8bb  call    cs:__imp_GetCurrentThreadId
0x18000d8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8c8  mov     r8b, dil
0x18000d8cb  mov     [rsp+130h+var_E0], r14; __int64
0x18000d8d0  mov     dl, bl
0x18000d8d2  mov     [rsp+130h+var_E8], rsi; __int64
0x18000d8d7  mov     dword ptr [rsp+130h+var_F0], eax; char
0x18000d8db  mov     r9, [rcx+28h]
0x18000d8df  mov     rcx, [rcx+10h]; LoggerHandle
0x18000d8e3  call    WPP_RECORDER_AND_TRACE_SF_DsS
0x18000d8e8  xorps   xmm0, xmm0
0x18000d8eb  mov     [rsp+130h+var_D0], 2
0x18000d8f3  xor     eax, eax
0x18000d8f5  mov     [rbp+4Fh+var_B8], r14
0x18000d8f9  movups  [rbp+4Fh+var_CC], xmm0
0x18000d8fd  mov     [rbp+4Fh+var_BC], eax
0x18000d900  call    cs:__imp_GetCurrentThreadId
0x18000d906  xorps   xmm0, xmm0
0x18000d909  mov     [rbp+4Fh+var_A0], rsi
0x18000d90d  mov     [rbp+4Fh+var_B0], eax
0x18000d910  lea     rdx, [rsp+130h+var_D0]; struct wil::FailureInfo *
0x18000d915  xor     eax, eax
0x18000d917  mov     [rbp+4Fh+var_98], r15
0x18000d91b  mov     [rbp+4Fh+var_AC], eax
0x18000d91e  xorps   xmm1, xmm1
0x18000d921  mov     [rbp+4Fh+var_A8], rax
0x18000d925  mov     rcx, r12; this
0x18000d928  mov     eax, [rbp+4Fh+arg_20]
0x18000d92b  mov     [rbp+4Fh+var_90], eax
0x18000d92e  mov     [rbp+4Fh+var_8C], 0
0x18000d935  mov     [rbp+4Fh+var_88], 0
0x18000d93d  mov     [rbp+4Fh+var_80], 0
0x18000d945  mov     [rbp+4Fh+var_78], 0
0x18000d94d  mov     [rbp+4Fh+var_70], 0
0x18000d955  mov     [rbp+4Fh+var_68], 0
0x18000d95d  movdqa  [rbp+4Fh+var_60], xmm0
0x18000d962  movdqa  [rbp+4Fh+var_50], xmm1
0x18000d967  mov     [rbp+4Fh+var_40], 0
0x18000d96f  call    ?pushInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAAXAEBUFailureInfo@wil@@@Z; Rdp::Modern::Utils::CInflightRecorder::pushInternal(wil::FailureInfo const &)
0x18000d974  add     rsp, 100h
0x18000d97b  pop     r15
0x18000d97d  pop     r14
0x18000d97f  pop     r12
0x18000d981  pop     rdi
0x18000d982  pop     rsi
0x18000d983  pop     rbx
0x18000d984  pop     rbp
0x18000d985  retn
```
