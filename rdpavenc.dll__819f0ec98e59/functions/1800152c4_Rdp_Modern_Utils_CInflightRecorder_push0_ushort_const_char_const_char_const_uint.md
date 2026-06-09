# Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)

- ea: `0x1800152c4`
- end: `0x1800153f2`
- name: `?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z`
- size: `302`
- prototype: `void __usercall(Rdp::Modern::Utils::CInflightRecorder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const char *@<r8>, const char *@<r9>, unsigned int)`
- caller_count: `20`
- callee_count: `3`
- tags: ``

## callers

- `0x180012950`
- `0x180014230`
- `0x1800153f8`
- `0x18001ad00`
- `0x18001e500`
- `0x18001e620`
- `0x180026410`
- `0x18002cb80`
- `0x1800345b0`
- `0x180038380`
- `0x18003c360`
- `0x18003df00`
- `0x18003e2b0`
- `0x1800409a0`
- `0x18004adb0`
- `0x18004b700`
- `0x18005c770`
- `0x180060bd0`
- `0x180064d90`
- `0x180067c50`

## callees

- `0x18000f9d0`
- `0x1800152c4`
- `0x18001552c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001536c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001536c`

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
0x1800152c4  push    rbp
0x1800152c6  push    rbx
0x1800152c7  push    rsi
0x1800152c8  push    rdi
0x1800152c9  push    r12
0x1800152cb  push    r14
0x1800152cd  push    r15
0x1800152cf  lea     rbp, [rsp-1Fh]
0x1800152d4  sub     rsp, 100h
0x1800152db  mov     r15, r9
0x1800152de  mov     rsi, r8
0x1800152e1  mov     r14, rdx
0x1800152e4  mov     r12, rcx
0x1800152e7  mov     rax, cs:WPP_GLOBAL_Control
0x1800152ee  lea     rcx, WPP_GLOBAL_Control
0x1800152f5  cmp     rax, rcx
0x1800152f8  jz      short loc_18001530A
0x1800152fa  test    byte ptr [rax+1Ch], 2
0x1800152fe  jz      short loc_18001530A
0x180015300  cmp     byte ptr [rax+19h], 4
0x180015304  jb      short loc_18001530A
0x180015306  mov     bl, 1
0x180015308  jmp     short loc_18001530C
0x18001530a  xor     bl, bl
0x18001530c  lea     rax, WPP_RECORDER_INITIALIZED
0x180015313  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001531a  setnz   dil
0x18001531e  test    bl, bl
0x180015320  jnz     short loc_180015327
0x180015322  test    dil, dil
0x180015325  jz      short loc_180015354
0x180015327  call    cs:__imp_GetCurrentThreadId
0x18001532d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015334  mov     r8b, dil
0x180015337  mov     [rsp+130h+var_E0], r14; __int64
0x18001533c  mov     dl, bl
0x18001533e  mov     [rsp+130h+var_E8], rsi; __int64
0x180015343  mov     dword ptr [rsp+130h+var_F0], eax; char
0x180015347  mov     r9, [rcx+28h]
0x18001534b  mov     rcx, [rcx+10h]; LoggerHandle
0x18001534f  call    WPP_RECORDER_AND_TRACE_SF_DsS
0x180015354  xorps   xmm0, xmm0
0x180015357  mov     [rsp+130h+var_D0], 2
0x18001535f  xor     eax, eax
0x180015361  mov     [rbp+4Fh+var_B8], r14
0x180015365  movups  [rbp+4Fh+var_CC], xmm0
0x180015369  mov     [rbp+4Fh+var_BC], eax
0x18001536c  call    cs:__imp_GetCurrentThreadId
0x180015372  xorps   xmm0, xmm0
0x180015375  mov     [rbp+4Fh+var_A0], rsi
0x180015379  mov     [rbp+4Fh+var_B0], eax
0x18001537c  lea     rdx, [rsp+130h+var_D0]; struct wil::FailureInfo *
0x180015381  xor     eax, eax
0x180015383  mov     [rbp+4Fh+var_98], r15
0x180015387  mov     [rbp+4Fh+var_AC], eax
0x18001538a  xorps   xmm1, xmm1
0x18001538d  mov     [rbp+4Fh+var_A8], rax
0x180015391  mov     rcx, r12; this
0x180015394  mov     eax, [rbp+4Fh+arg_20]
0x180015397  mov     [rbp+4Fh+var_90], eax
0x18001539a  mov     [rbp+4Fh+var_8C], 0
0x1800153a1  mov     [rbp+4Fh+var_88], 0
0x1800153a9  mov     [rbp+4Fh+var_80], 0
0x1800153b1  mov     [rbp+4Fh+var_78], 0
0x1800153b9  mov     [rbp+4Fh+var_70], 0
0x1800153c1  mov     [rbp+4Fh+var_68], 0
0x1800153c9  movdqa  [rbp+4Fh+var_60], xmm0
0x1800153ce  movdqa  [rbp+4Fh+var_50], xmm1
0x1800153d3  mov     [rbp+4Fh+var_40], 0
0x1800153db  call    ?pushInternal@CInflightRecorder@Utils@Modern@Rdp@@AEAAXAEBUFailureInfo@wil@@@Z; Rdp::Modern::Utils::CInflightRecorder::pushInternal(wil::FailureInfo const &)
0x1800153e0  add     rsp, 100h
0x1800153e7  pop     r15
0x1800153e9  pop     r14
0x1800153eb  pop     r12
0x1800153ed  pop     rdi
0x1800153ee  pop     rsi
0x1800153ef  pop     rbx
0x1800153f0  pop     rbp
0x1800153f1  retn
```
