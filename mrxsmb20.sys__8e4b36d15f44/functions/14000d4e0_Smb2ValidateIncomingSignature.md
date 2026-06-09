# Smb2ValidateIncomingSignature

- ea: `0x14000d4e0`
- end: `0x14000d5c3`
- name: `Smb2ValidateIncomingSignature`
- size: `227`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000cfa0`
- `0x14000d140`
- `0x140053130`

## callees

- `0x14000d4e0`
- `0x14002a1dc`
- `0x1400330a4`
- `0x140037120`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000d579`
- `ntoskrnl!RtlCompareMemory` at `0x14000d579`
- `ksecdd!BCryptFinishHash` at `0x14000d538`
- `ksecdd!BCryptFinishHash` at `0x14000d538`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x14000d549`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x14000d549`

## pseudocode

```c
__int64 __fastcall Smb2ValidateIncomingSignature(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  _QWORD *v4; // rbp
  ULONG v7; // r8d
  void *v10; // rcx
  NTSTATUS v11; // edi
  __int64 v13; // rcx
  char v14; // r13
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // r9d
  __int64 v18; // r10
  __int64 v19; // r11
  UCHAR Source1[32]; // [rsp+90h] [rbp-68h] BYREF

  v4 = *(_QWORD **)(a1 + 56);
  v7 = *(_DWORD *)(a1 + 800);
  v10 = *(void **)(a1 + 792);
  memset(Source1, 0, sizeof(Source1));
  v11 = BCryptFinishHash(v10, Source1, v7, 0);
  SmbCseDestroyHashHandle(a1);
  if ( v11 >= 0 )
  {
    if ( *(_DWORD *)(a1 + 48) == -1073741309 || RtlCompareMemory(Source1, (const void *)(a1 + 820), 0x10u) == 16 )
      return (unsigned int)v11;
    v11 = -1073700864;
  }
  v13 = v4[12];
  v14 = 0;
  if ( *(_DWORD *)(a1 + 736) != *(_DWORD *)(a1 + 740) )
    v14 = *(_DWORD *)(a1 + 740);
  if ( !v13 )
    v13 = a2;
  if ( (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 2) != 0 )
  {
    v15 = v4[11];
    if ( v13 )
    {
      v16 = *(_QWORD *)(v13 + 392);
      v17 = 28;
      v18 = v16 + 400;
      v19 = v16 + 428;
      if ( !*(_BYTE *)(v16 + 325) )
        v17 = 16;
    }
    else
    {
      v18 = 0;
      v19 = 0;
      v17 = 0;
    }
    if ( a3 >= DefaultPacketFragmentSize )
      a3 = DefaultPacketFragmentSize;
    if ( v15 )
      LODWORD(v15) = *(_DWORD *)(v15 + 436);
    McTemplateK0hxxqhzr4qqqqbr9qbr11qbr13_EtwWriteTransfer(
      *(_WORD *)(v4[9] + 80LL) >> 1,
      v4[10],
      v15,
      *(unsigned __int16 *)(a1 + 2),
      *(_QWORD *)(a1 + 40),
      *(_QWORD *)(v4[10] + 440LL),
      v15,
      *(_WORD *)(v4[9] + 80LL) >> 1,
      *(_QWORD *)(v4[9] + 88LL),
      *(_DWORD *)(a1 + 48),
      *(_DWORD *)(a1 + 736),
      v14,
      a3,
      a4,
      v17,
      v19,
      v17,
      v18);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_60db1590be613abca80435fd5891bee8_Traceguids,
      *(_QWORD *)(a1 + 56),
      a1);
  }
  if ( dbgSmb2BreakOnSignatureMismatch )
    __debugbreak();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000d4e0  mov     r11, rsp
0x14000d4e3  push    rbx
0x14000d4e4  push    rbp
0x14000d4e5  push    rsi
0x14000d4e6  push    rdi
0x14000d4e7  push    r12
0x14000d4e9  push    r14
0x14000d4eb  push    r15
0x14000d4ed  sub     rsp, 0C0h
0x14000d4f4  mov     rax, cs:__security_cookie
0x14000d4fb  xor     rax, rsp
0x14000d4fe  mov     [rsp+0F8h+var_48], rax
0x14000d506  mov     rbp, [rcx+38h]
0x14000d50a  xorps   xmm0, xmm0
0x14000d50d  mov     r14d, r8d
0x14000d510  mov     r12, r9
0x14000d513  mov     r8d, [rcx+320h]; cbOutput
0x14000d51a  mov     r15, rdx
0x14000d51d  mov     rbx, rcx
0x14000d520  lea     rdx, [r11-68h]; pbOutput
0x14000d524  mov     rcx, [rcx+318h]; hHash
0x14000d52b  xor     r9d, r9d; dwFlags
0x14000d52e  movups  xmmword ptr [r11-68h], xmm0
0x14000d533  movups  xmmword ptr [r11-58h], xmm0
0x14000d538  call    cs:__imp_BCryptFinishHash
0x14000d53f  nop     dword ptr [rax+rax+00h]
0x14000d544  mov     rcx, rbx
0x14000d547  mov     edi, eax
0x14000d549  call    cs:__imp_SmbCseDestroyHashHandle
0x14000d550  nop     dword ptr [rax+rax+00h]
0x14000d555  test    edi, edi
0x14000d557  js      short loc_14000D5AF
0x14000d559  cmp     dword ptr [rbx+30h], 0C0000203h
0x14000d560  jz      short loc_14000D58A
0x14000d562  mov     esi, 10h
0x14000d567  lea     rdx, [rbx+334h]; Source2
0x14000d56e  mov     r8d, esi; Length
0x14000d571  lea     rcx, [rsp+0F8h+Source1]; Source1
0x14000d579  call    cs:__imp_RtlCompareMemory
0x14000d580  nop     dword ptr [rax+rax+00h]
0x14000d585  cmp     rax, rsi
0x14000d588  jnz     short loc_14000D5B9
0x14000d58a  mov     eax, edi
0x14000d58c  mov     rcx, [rsp+0F8h+var_48]
0x14000d594  xor     rcx, rsp; StackCookie
0x14000d597  call    __security_check_cookie
0x14000d59c  add     rsp, 0C0h
0x14000d5a3  pop     r15
0x14000d5a5  pop     r14
0x14000d5a7  pop     r12
0x14000d5a9  pop     rdi
0x14000d5aa  pop     rsi
0x14000d5ab  pop     rbp
0x14000d5ac  pop     rbx
0x14000d5ad  retn
0x14000d5af  mov     esi, 10h
0x14000d5b4  jmp     loc_140039A2A
0x14000d5b9  mov     edi, 0C000A000h
0x14000d5be  jmp     loc_140039A2A
0x140039a2a  mov     eax, [rbx+2E4h]
0x140039a30  mov     rcx, [rbp+60h]
0x140039a34  mov     [rsp+0F8h+arg_10], r13
0x140039a3c  xor     r13d, r13d
0x140039a3f  cmp     [rbx+2E0h], eax
0x140039a45  cmovnz  r13d, eax
0x140039a49  test    rcx, rcx
0x140039a4c  cmovz   rcx, r15
0x140039a50  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 2
0x140039a57  jz      loc_140039B31
0x140039a5d  mov     r15, [rbp+48h]
0x140039a61  mov     r8, [rbp+58h]
0x140039a65  test    rcx, rcx
0x140039a68  jz      short loc_140039A92
0x140039a6a  mov     rax, [rcx+188h]
0x140039a71  mov     r9d, 1Ch
0x140039a77  cmp     byte ptr [rax+145h], 0
0x140039a7e  lea     r10, [rax+190h]
0x140039a85  lea     r11, [rax+1ACh]
0x140039a8c  cmovz   r9, rsi
0x140039a90  jmp     short loc_140039A9B
0x140039a92  xor     r10d, r10d
0x140039a95  xor     r11d, r11d
0x140039a98  xor     r9d, r9d
0x140039a9b  mov     eax, cs:DefaultPacketFragmentSize
0x140039aa1  cmp     r14d, eax
0x140039aa4  jb      short loc_140039AAD
0x140039aa6  mov     r14d, cs:DefaultPacketFragmentSize
0x140039aad  test    r8, r8
0x140039ab0  jz      short loc_140039AB9
0x140039ab2  mov     r8d, [r8+1B4h]
0x140039ab9  mov     eax, [rbx+2E0h]
0x140039abf  mov     rdx, [rbp+50h]
0x140039ac3  movzx   ecx, word ptr [r15+50h]
0x140039ac8  mov     [rsp+0F8h+var_70], r10
0x140039ad0  mov     [rsp+0F8h+var_78], r9d
0x140039ad8  mov     [rsp+0F8h+var_80], r11
0x140039add  mov     [rsp+0F8h+var_88], r9d
0x140039ae2  movzx   r9d, word ptr [rbx+2]
0x140039ae7  mov     [rsp+0F8h+var_90], r12
0x140039aec  mov     [rsp+0F8h+var_98], r14d
0x140039af1  mov     [rsp+0F8h+var_A0], r13d
0x140039af6  mov     [rsp+0F8h+var_A8], eax
0x140039afa  mov     eax, [rbx+30h]
0x140039afd  mov     [rsp+0F8h+var_B0], eax
0x140039b01  mov     rax, [r15+58h]
0x140039b05  mov     [rsp+0F8h+var_B8], rax
0x140039b0a  mov     rax, [rdx+1B8h]
0x140039b11  shr     cx, 1
0x140039b14  mov     [rsp+0F8h+var_C0], cx
0x140039b19  mov     [rsp+0F8h+var_C8], r8d
0x140039b1e  mov     [rsp+0F8h+var_D0], rax
0x140039b23  mov     rax, [rbx+28h]
0x140039b27  mov     [rsp+0F8h+var_D8], rax
0x140039b2c  call    McTemplateK0hxxqhzr4qqqqbr9qbr11qbr13_EtwWriteTransfer
0x140039b31  mov     rcx, cs:WPP_GLOBAL_Control
0x140039b38  lea     rax, WPP_GLOBAL_Control
0x140039b3f  mov     r13, [rsp+0F8h+arg_10]
0x140039b47  cmp     rcx, rax
0x140039b4a  jz      short loc_140039B77
0x140039b4c  mov     eax, [rcx+2Ch]
0x140039b4f  test    al, 1
0x140039b51  jz      short loc_140039B77
0x140039b53  cmp     byte ptr [rcx+29h], 1
0x140039b57  jb      short loc_140039B77
0x140039b59  mov     r9, [rbx+38h]
0x140039b5d  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x140039b64  mov     rcx, [rcx+18h]
0x140039b68  mov     edx, 22h ; '"'
0x140039b6d  mov     [rsp+0F8h+var_D8], rbx
0x140039b72  call    WPP_SF_qq
0x140039b77  movzx   eax, cs:dbgSmb2BreakOnSignatureMismatch
0x140039b7e  test    al, al
0x140039b80  jz      loc_14000D58A
0x140039b86  int     3; Trap to Debugger
0x140039b87  jmp     loc_14000D58A
```
