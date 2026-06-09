# MRxDAVHandleCreateSrvCallCancellation

- ea: `0x140004dac`
- end: `0x140004e8f`
- name: `MRxDAVHandleCreateSrvCallCancellation`
- size: `227`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400044b0`

## callees

- `0x140001b64`
- `0x140004dac`
- `0x140006880`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140004de2`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140004de2`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140004e33`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140004e33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004e48`

## pseudocode

```c
__int64 __fastcall MRxDAVHandleCreateSrvCallCancellation(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v5; // rbx
  __int64 v6; // rsi
  void (__fastcall *v7)(__int64); // rax

  v1 = *(_QWORD *)(a1 + 80);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v3 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qqq(v3, 29, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids, CurrentThreadId, a1, v1);
  }
  v5 = *(_QWORD *)(v1 + 216);
  v6 = *(_QWORD *)(v5 + 264);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 32);
  if ( *(_BYTE *)(v6 + 4) )
  {
    SeDeleteClientSecurity(*(_QWORD *)(v1 + 224));
    ExFreePoolWithTag(*(PVOID *)(v1 + 224), 0);
    *(_QWORD *)(v1 + 224) = 0;
    *(_BYTE *)(v6 + 4) = 0;
  }
  v7 = *(void (__fastcall **)(__int64))(v5 + 272);
  *(_DWORD *)(v5 + 280) = -1073741634;
  v7(v5);
  return 0;
}

```

## disassembly

```asm
0x140004dac  mov     [rsp+arg_0], rbx
0x140004db1  mov     [rsp+arg_8], rsi
0x140004db6  push    rdi
0x140004db7  sub     rsp, 30h
0x140004dbb  mov     rdi, [rcx+50h]
0x140004dbf  mov     rsi, rcx
0x140004dc2  mov     rbx, cs:WPP_GLOBAL_Control
0x140004dc9  lea     rax, WPP_GLOBAL_Control
0x140004dd0  cmp     rbx, rax
0x140004dd3  jz      short loc_140004E0F
0x140004dd5  test    dword ptr [rbx+2Ch], 2000h
0x140004ddc  jz      short loc_140004E0F
0x140004dde  mov     rbx, [rbx+18h]
0x140004de2  call    cs:__imp_PsGetCurrentThreadId
0x140004de9  nop     dword ptr [rax+rax+00h]
0x140004dee  mov     edx, 1Dh
0x140004df3  mov     [rsp+38h+var_10], rdi
0x140004df8  mov     r9, rax
0x140004dfb  mov     [rsp+38h+var_18], rsi
0x140004e00  lea     r8, WPP_ac0b5044678f3066f3e1489d74d9001d_Traceguids
0x140004e07  mov     rcx, rbx
0x140004e0a  call    WPP_SF_qqq
0x140004e0f  mov     rbx, [rdi+0D8h]
0x140004e16  mov     rsi, [rbx+108h]
0x140004e1d  test    rsi, rsi
0x140004e20  jz      short loc_140004E26
0x140004e22  mov     rsi, [rsi+20h]
0x140004e26  cmp     byte ptr [rsi+4], 0
0x140004e2a  jz      short loc_140004E63
0x140004e2c  mov     rcx, [rdi+0E0h]
0x140004e33  call    cs:__imp_SeDeleteClientSecurity
0x140004e3a  nop     dword ptr [rax+rax+00h]
0x140004e3f  mov     rcx, [rdi+0E0h]; P
0x140004e46  xor     edx, edx; Tag
0x140004e48  call    cs:__imp_ExFreePoolWithTag
0x140004e4f  nop     dword ptr [rax+rax+00h]
0x140004e54  mov     qword ptr [rdi+0E0h], 0
0x140004e5f  mov     byte ptr [rsi+4], 0
0x140004e63  mov     rax, [rbx+110h]
0x140004e6a  mov     rcx, rbx
0x140004e6d  mov     dword ptr [rbx+118h], 0C00000BEh
0x140004e77  call    _guard_dispatch_icall
0x140004e7c  mov     rbx, [rsp+38h+arg_0]
0x140004e81  xor     eax, eax
0x140004e83  mov     rsi, [rsp+38h+arg_8]
0x140004e88  add     rsp, 30h
0x140004e8c  pop     rdi
0x140004e8d  retn
```
