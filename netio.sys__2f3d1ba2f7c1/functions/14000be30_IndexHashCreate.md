# IndexHashCreate

- ea: `0x14000be30`
- end: `0x14000bfbc`
- name: `IndexHashCreate`
- size: `396`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000afa0`
- `0x14000be30`
- `0x14004efd4`
- `0x140050a90`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14000be9b`
- `ntoskrnl!RtlCreateHashTable` at `0x14000be9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bef8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bef8`
- `NDIS!NdisFreeRWLock` at `0x14000bedf`
- `NDIS!NdisFreeRWLock` at `0x14000bedf`

## string_xrefs

- `0x14000bf9b`: `RtlCreateHashTable`
- `0x14000bf2b`: `IndexHashCreate`

## pseudocode

```c
__int64 __fastcall IndexHashCreate(unsigned __int16 *a1, _QWORD *a2)
{
  __int64 v4; // rax
  PVOID v5; // rbx
  __int64 FastRWLock; // rdi
  PVOID v7; // rcx
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  P = 0;
  v4 = WfpPoolAllocNonPaged(32, 1232102999, &P);
  v5 = P;
  FastRWLock = v4;
  if ( !v4 )
  {
    v7 = P;
    *(_OWORD *)P = 0;
    *((_OWORD *)v5 + 1) = 0;
    FastRWLock = WfpCreateFastRWLock(v7);
    if ( !FastRWLock )
    {
      if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)v5 + 2, 0, 0) )
      {
        *((_QWORD *)v5 + 1) = a1;
        *((_QWORD *)v5 + 3) = 32;
        *((_QWORD *)v5 + 3) = 4LL * *a1 + 88;
        *a2 = v5;
        return FastRWLock;
      }
      FastRWLock = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"RtlCreateHashTable",
          1);
      }
      NdisFreeRWLock(*(PNDIS_RW_LOCK_EX *)v5);
      *(_QWORD *)v5 = 0;
    }
  }
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  *a2 = 0;
  if ( FastRWLock
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"IndexHashCreate",
      FastRWLock);
  }
  return FastRWLock;
}

```

## disassembly

```asm
0x14000be30  mov     [rsp+arg_8], rbx
0x14000be35  mov     [rsp+arg_10], rbp
0x14000be3a  push    rsi
0x14000be3b  push    rdi
0x14000be3c  push    r14
0x14000be3e  sub     rsp, 30h
0x14000be42  mov     r14, rdx
0x14000be45  lea     r8, [rsp+48h+P]
0x14000be4a  mov     rsi, rcx
0x14000be4d  xor     ebp, ebp
0x14000be4f  mov     edx, 49706657h
0x14000be54  mov     [rsp+48h+P], rbp
0x14000be59  mov     ecx, 20h ; ' '
0x14000be5e  call    WfpPoolAllocNonPaged
0x14000be63  mov     rbx, [rsp+48h+P]
0x14000be68  mov     rdi, rax
0x14000be6b  test    rax, rax
0x14000be6e  jnz     loc_14000BF8B
0x14000be74  xorps   xmm0, xmm0
0x14000be77  mov     rcx, rbx
0x14000be7a  movups  xmmword ptr [rbx], xmm0
0x14000be7d  movups  xmmword ptr [rbx+10h], xmm0
0x14000be81  call    WfpCreateFastRWLock
0x14000be86  mov     rdi, rax
0x14000be89  test    rax, rax
0x14000be8c  jnz     loc_14000BF8B
0x14000be92  lea     rcx, [rbx+10h]; HashTable
0x14000be96  xor     r8d, r8d; Flags
0x14000be99  xor     edx, edx; Shift
0x14000be9b  call    cs:__imp_RtlCreateHashTable
0x14000bea2  nop     dword ptr [rax+rax+00h]
0x14000bea7  test    al, al
0x14000bea9  jz      loc_14000BF5E
0x14000beaf  mov     [rbx+8], rsi
0x14000beb3  mov     qword ptr [rbx+18h], 20h ; ' '
0x14000bebb  movzx   ecx, word ptr [rsi]
0x14000bebe  lea     rcx, ds:58h[rcx*4]
0x14000bec6  mov     [rbx+18h], rcx
0x14000beca  mov     [r14], rbx
0x14000becd  jmp     short loc_14000BF47
0x14000becf  test    dword ptr [rcx+2Ch], 1000h
0x14000bed6  jnz     loc_14000BF97
0x14000bedc  mov     rcx, [rbx]; Lock
0x14000bedf  call    cs:__imp_NdisFreeRWLock
0x14000bee6  nop     dword ptr [rax+rax+00h]
0x14000beeb  mov     [rbx], rbp
0x14000beee  test    rbx, rbx
0x14000bef1  jz      short loc_14000BF04
0x14000bef3  xor     edx, edx; Tag
0x14000bef5  mov     rcx, rbx; P
0x14000bef8  call    cs:__imp_ExFreePoolWithTag
0x14000beff  nop     dword ptr [rax+rax+00h]
0x14000bf04  mov     [r14], rbp
0x14000bf07  test    rdi, rdi
0x14000bf0a  jz      short loc_14000BF47
0x14000bf0c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf13  cmp     rcx, rsi
0x14000bf16  jz      short loc_14000BF47
0x14000bf18  cmp     byte ptr [rcx+29h], 2
0x14000bf1c  jb      short loc_14000BF47
0x14000bf1e  test    dword ptr [rcx+2Ch], 1000h
0x14000bf25  jz      short loc_14000BF47
0x14000bf27  mov     rcx, [rcx+18h]
0x14000bf2b  lea     r9, aIndexhashcreat; "IndexHashCreate"
0x14000bf32  mov     edx, 0Fh
0x14000bf37  mov     [rsp+48h+var_28], edi
0x14000bf3b  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000bf42  call    WPP_SF_sd
0x14000bf47  mov     rbx, [rsp+48h+arg_8]
0x14000bf4c  mov     rax, rdi
0x14000bf4f  mov     rbp, [rsp+48h+arg_10]
0x14000bf54  add     rsp, 30h
0x14000bf58  pop     r14
0x14000bf5a  pop     rdi
0x14000bf5b  pop     rsi
0x14000bf5c  retn
0x14000bf5e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf65  lea     rsi, WPP_GLOBAL_Control
0x14000bf6c  mov     rdi, 0FFFFFFFFC0000001h
0x14000bf73  cmp     rcx, rsi
0x14000bf76  jz      loc_14000BEDC
0x14000bf7c  cmp     byte ptr [rcx+29h], 2
0x14000bf80  jb      loc_14000BEDC
0x14000bf86  jmp     loc_14000BECF
0x14000bf8b  lea     rsi, WPP_GLOBAL_Control
0x14000bf92  jmp     loc_14000BEEE
0x14000bf97  mov     rcx, [rcx+18h]
0x14000bf9b  lea     r9, aRtlcreatehasht; "RtlCreateHashTable"
0x14000bfa2  mov     edx, 0Ah
0x14000bfa7  mov     [rsp+48h+var_28], edi
0x14000bfab  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000bfb2  call    WPP_SF_sd
0x14000bfb7  jmp     loc_14000BEDC
```
