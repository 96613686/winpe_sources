# SecGetProcessPebStartupInfo

- ea: `0x1400421bc`
- end: `0x1400423f7`
- name: `SecGetProcessPebStartupInfo`
- size: `571`
- prototype: `__int64 __usercall@<rax>(PRKPROCESS PROCESS@<rcx>, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002c6b0`

## callees

- `0x140006684`
- `0x140011650`
- `0x1400421bc`
- `0x1400441a0`
- `0x1400441d4`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400422ad`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1400422ad`
- `ntoskrnl!PsGetProcessPeb` at `0x140042258`
- `ntoskrnl!PsGetProcessPeb` at `0x140042258`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x140042273`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x140042273`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400423c5`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400423c5`
- `ntoskrnl!MmUserProbeAddress` at `0x1400422b9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400423b6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400423b6`
- `ntoskrnl!KeStackAttachProcess` at `0x140042294`
- `ntoskrnl!KeStackAttachProcess` at `0x140042294`
- `ntoskrnl!ProbeForRead` at `0x140042335`
- `ntoskrnl!ProbeForRead` at `0x140042335`

## pseudocode

```c
__int64 __fastcall SecGetProcessPebStartupInfo(
        PRKPROCESS PROCESS,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7)
{
  bool v10; // bl
  __int64 result; // rax
  __int64 v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // rdx
  _OWORD *v15; // rdx
  volatile void **v16; // rcx
  char *v17; // rbx
  unsigned int ULongFromUser; // edi
  __int128 v19; // [rsp+20h] [rbp-C8h]
  volatile void *Address[2]; // [rsp+50h] [rbp-98h] BYREF
  __int128 v22; // [rsp+60h] [rbp-88h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+70h] [rbp-78h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  *(_OWORD *)Address = 0;
  v22 = 0;
  v10 = (BYTE8(xmmword_14001B740) & 0x20) != 0;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  result = PsGetProcessPeb(PROCESS);
  v12 = result;
  if ( result )
  {
    result = PsAcquireProcessExitSynchronization(PROCESS);
    v13 = result;
    _mm_lfence();
    if ( (int)result >= 0 )
    {
      KeStackAttachProcess(PROCESS, &ApcState);
      _mm_lfence();
      v14 = *(_QWORD *)(v12 + 32);
      if ( (v14 & 7) != 0 )
        ExRaiseDatatypeMisalignment();
      *a2 = *(_DWORD *)(v14 + 164);
      *a3 = *(_DWORD *)(v14 + 168);
      *a4 = *(_QWORD *)(v14 + 32);
      *a5 = *(_QWORD *)(v14 + 40);
      *a6 = *(_QWORD *)(v14 + 48);
      v15 = (_OWORD *)(v14 + 192);
      if ( v10 )
      {
        *(_OWORD *)Address = *v15;
        ProbeForRead(Address[1], LOWORD(Address[0]), 2u);
        v16 = Address;
      }
      else
      {
        v17 = (char *)v15 + 8;
        ULongFromUser = RtlReadULongFromUser(v15, v15);
        *((_QWORD *)&v19 + 1) = RtlReadULong64FromUser(v17);
        *(_QWORD *)&v19 = ULongFromUser;
        v22 = v19;
        v16 = (volatile void **)&v22;
      }
      SecUnicodeToNullTerminatedUnicode(v16, a7);
      _mm_lfence();
      KeUnstackDetachProcess(&ApcState);
      PsReleaseProcessExitSynchronization(PROCESS);
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400421bc  mov     r11, rsp
0x1400421bf  push    rbx
0x1400421c0  push    rsi
0x1400421c1  push    rdi
0x1400421c2  push    r12
0x1400421c4  push    r13
0x1400421c6  push    r14
0x1400421c8  push    r15
0x1400421ca  sub     rsp, 0B0h
0x1400421d1  mov     rax, cs:__security_cookie
0x1400421d8  xor     rax, rsp
0x1400421db  mov     [rsp+0E8h+var_48], rax
0x1400421e3  mov     [rsp+0E8h+var_B8], r9
0x1400421e8  mov     r13, r8
0x1400421eb  mov     r12, rdx
0x1400421ee  mov     r14, rcx
0x1400421f1  mov     [rsp+0E8h+var_B0], rcx
0x1400421f6  mov     rcx, [rsp+0E8h+arg_20]
0x1400421fe  mov     qword ptr [rsp+0E8h+var_A8], rcx
0x140042203  mov     rdx, [rsp+0E8h+arg_28]
0x14004220b  mov     qword ptr [rsp+0E8h+var_C8], rdx
0x140042210  mov     r15, [rsp+0E8h+arg_30]
0x140042218  xorps   xmm0, xmm0
0x14004221b  movups  xmmword ptr [rsp+0E8h+ApcState.ApcListHead.Flink], xmm0
0x140042220  movups  xmmword ptr [r11-68h], xmm0
0x140042225  movups  xmmword ptr [r11-58h], xmm0
0x14004222a  movups  xmmword ptr [rsp+0E8h+Address], xmm0
0x14004222f  xorps   xmm1, xmm1
0x140042232  movups  [rsp+0E8h+var_88], xmm1
0x140042237  mov     bl, byte ptr cs:xmmword_14001B740+8
0x14004223d  shr     bl, 5
0x140042240  and     bl, 1
0x140042243  xor     esi, esi
0x140042245  mov     [r12], esi
0x140042249  mov     [r8], esi
0x14004224c  mov     [r9], rsi
0x14004224f  mov     [rcx], rsi
0x140042252  mov     [rdx], rsi
0x140042255  mov     rcx, r14
0x140042258  call    cs:__imp_PsGetProcessPeb
0x14004225f  nop     dword ptr [rax+rax+00h]
0x140042264  mov     rdi, rax
0x140042267  test    rax, rax
0x14004226a  jz      loc_1400423D3
0x140042270  mov     rcx, r14
0x140042273  call    cs:__imp_PsAcquireProcessExitSynchronization
0x14004227a  nop     dword ptr [rax+rax+00h]
0x14004227f  mov     esi, eax
0x140042281  lfence
0x140042284  test    eax, eax
0x140042286  js      loc_1400423D3
0x14004228c  lea     rdx, [rsp+0E8h+ApcState]; ApcState
0x140042291  mov     rcx, r14; PROCESS
0x140042294  call    cs:__imp_KeStackAttachProcess
0x14004229b  nop     dword ptr [rax+rax+00h]
0x1400422a0  nop
0x1400422a1  lfence
0x1400422a4  mov     rdx, [rdi+20h]
0x1400422a8  test    dl, 7
0x1400422ab  jz      short loc_1400422B9
0x1400422ad  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1400422b4  nop     dword ptr [rax+rax+00h]
0x1400422b9  mov     rax, cs:MmUserProbeAddress
0x1400422c0  mov     rcx, [rax]
0x1400422c3  mov     rax, rdx
0x1400422c6  cmp     rdx, rcx
0x1400422c9  cmovnb  rax, rcx
0x1400422cd  mov     al, [rax]
0x1400422cf  mov     eax, [rdx+0A4h]
0x1400422d5  mov     [r12], eax
0x1400422d9  mov     eax, [rdx+0A8h]
0x1400422df  mov     [r13+0], eax
0x1400422e3  mov     rax, [rdx+20h]
0x1400422e7  mov     rcx, [rsp+0E8h+var_B8]
0x1400422ec  mov     [rcx], rax
0x1400422ef  mov     rax, [rdx+28h]
0x1400422f3  mov     rcx, qword ptr [rsp+0E8h+var_A8]
0x1400422f8  mov     [rcx], rax
0x1400422fb  mov     rax, [rdx+30h]
0x1400422ff  mov     rcx, qword ptr [rsp+0E8h+var_C8]
0x140042304  mov     [rcx], rax
0x140042307  add     rdx, 0C0h
0x14004230e  test    bl, bl
0x140042310  jz      short loc_14004231B
0x140042312  movups  xmm0, xmmword ptr [rdx]
0x140042315  movdqu  xmmword ptr [rsp+0E8h+Address], xmm0
0x14004231b  xor     ecx, ecx
0x14004231d  test    bl, bl
0x14004231f  cmovz   rcx, rdx
0x140042323  jz      short loc_140042348
0x140042325  movzx   edx, word ptr [rsp+0E8h+Address]; Length
0x14004232a  mov     r8d, 2; Alignment
0x140042330  mov     rcx, [rsp+0E8h+Address+8]; Address
0x140042335  call    cs:__imp_ProbeForRead
0x14004233c  nop     dword ptr [rax+rax+00h]
0x140042341  lea     rcx, [rsp+0E8h+Address]
0x140042346  jmp     short loc_14004239D
0x140042348  lea     rbx, [rcx+8]
0x14004234c  xorps   xmm0, xmm0
0x14004234f  movups  [rsp+0E8h+var_C8], xmm0
0x140042354  call    RtlReadULongFromUser
0x140042359  mov     edi, eax
0x14004235b  mov     dword ptr [rsp+0E8h+var_C8], eax
0x14004235f  mov     rcx, rbx
0x140042362  call    RtlReadULong64FromUser
0x140042367  mov     qword ptr [rsp+0E8h+var_C8+8], rax
0x14004236c  movaps  xmm0, [rsp+0E8h+var_C8]
0x140042371  movdqa  [rsp+0E8h+var_A8], xmm0
0x140042377  mov     dword ptr [rsp+0E8h+var_C8], edi
0x14004237b  movq    rcx, xmm0
0x140042380  shr     rcx, 20h
0x140042384  mov     dword ptr [rsp+0E8h+var_C8+4], ecx
0x140042388  mov     qword ptr [rsp+0E8h+var_C8+8], rax
0x14004238d  movaps  xmm0, [rsp+0E8h+var_C8]
0x140042392  movdqa  [rsp+0E8h+var_88], xmm0
0x140042398  lea     rcx, [rsp+0E8h+var_88]
0x14004239d  mov     rdx, r15
0x1400423a0  call    SecUnicodeToNullTerminatedUnicode
0x1400423a5  jmp     short loc_1400423AE
0x1400423a7  mov     esi, eax
0x1400423a9  mov     r14, [rsp+0E8h+var_B0]
0x1400423ae  lfence
0x1400423b1  lea     rcx, [rsp+0E8h+ApcState]; ApcState
0x1400423b6  call    cs:__imp_KeUnstackDetachProcess
0x1400423bd  nop     dword ptr [rax+rax+00h]
0x1400423c2  mov     rcx, r14
0x1400423c5  call    cs:__imp_PsReleaseProcessExitSynchronization
0x1400423cc  nop     dword ptr [rax+rax+00h]
0x1400423d1  mov     eax, esi
0x1400423d3  mov     rcx, [rsp+0E8h+var_48]
0x1400423db  xor     rcx, rsp; StackCookie
0x1400423de  call    __security_check_cookie
0x1400423e3  add     rsp, 0B0h
0x1400423ea  pop     r15
0x1400423ec  pop     r14
0x1400423ee  pop     r13
0x1400423f0  pop     r12
0x1400423f2  pop     rdi
0x1400423f3  pop     rsi
0x1400423f4  pop     rbx
0x1400423f5  retn
```
