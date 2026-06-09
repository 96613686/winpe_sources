# CServerVCChannel::static_IssueARead(unsigned __int64)

- ea: `0x180021430`
- end: `0x1800214b5`
- name: `?static_IssueARead@CServerVCChannel@@CAX_K@Z`
- size: `133`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18001d114`
- `0x18001ef44`
- `0x18002081c`
- `0x180021430`
- `0x18002c010`

## string_xrefs

- `0x18002146c`: `pThis->IssueARead FAILED`

## pseudocode

```c
void __fastcall CServerVCChannel::static_IssueARead(CServerVCChannel *a1)
{
  int v2; // edi
  int CurrentThreadActivityIdPrefix; // eax
  int v4; // [rsp+28h] [rbp-10h]

  v2 = CServerVCChannel::IssueARead(a1);
  if ( v2 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = v2;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)&WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"pThis->IssueARead FAILED",
      v4);
  }
  (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)a1 + 5) + 16LL))(*((_QWORD **)a1 + 5));
}

```

## disassembly

```asm
0x180021430  mov     [rsp+arg_0], rbx
0x180021435  push    rdi
0x180021436  sub     rsp, 30h
0x18002143a  mov     rbx, rcx
0x18002143d  call    ?IssueARead@CServerVCChannel@@AEAAJXZ; CServerVCChannel::IssueARead(void)
0x180021442  mov     edi, eax
0x180021444  test    eax, eax
0x180021446  jns     short loc_18002149B
0x180021448  mov     rdx, cs:WPP_GLOBAL_Control
0x18002144f  lea     rax, WPP_GLOBAL_Control
0x180021456  cmp     rdx, rax
0x180021459  jz      short loc_18002149B
0x18002145b  test    byte ptr [rdx+1Ch], 8
0x18002145f  jz      short loc_18002149B
0x180021461  cmp     byte ptr [rdx+19h], 2
0x180021465  jb      short loc_18002149B
0x180021467  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18002146c  lea     rcx, aPthisIssuearea; "pThis->IssueARead FAILED"
0x180021473  mov     [rsp+38h+var_10], edi
0x180021477  mov     [rsp+38h+var_18], rcx
0x18002147c  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x180021483  mov     rcx, cs:WPP_GLOBAL_Control
0x18002148a  mov     edx, 11h
0x18002148f  mov     r9d, eax
0x180021492  mov     rcx, [rcx+10h]
0x180021496  call    WPP_SF_DsD
0x18002149b  mov     rcx, [rbx+28h]
0x18002149f  mov     rax, [rcx]
0x1800214a2  mov     rax, [rax+10h]
0x1800214a6  mov     rbx, [rsp+38h+arg_0]
0x1800214ab  add     rsp, 30h
0x1800214af  pop     rdi
0x1800214b0  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
