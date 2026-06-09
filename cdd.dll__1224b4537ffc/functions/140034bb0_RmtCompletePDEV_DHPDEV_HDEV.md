# RmtCompletePDEV(DHPDEV__ *,HDEV__ *)

- ea: `0x140034bb0`
- end: `0x140034c19`
- name: `?RmtCompletePDEV@@YAXPEAUDHPDEV__@@PEAUHDEV__@@@Z`
- size: `105`
- prototype: `void __fastcall(struct DHPDEV__ *, HDEV)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140034bb0`
- `0x1400372d0`

## import_xrefs

- `WIN32K!W32GetSessionState` at `0x140034bc0`
- `WIN32K!W32GetSessionState` at `0x140034be9`
- `WIN32K!W32GetSessionState` at `0x140034bc0`
- `WIN32K!W32GetSessionState` at `0x140034be9`

## pseudocode

```c
void __fastcall RmtCompletePDEV(struct DHPDEV__ *a1, HDEV a2)
{
  __int64 SessionState; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax

  SessionState = W32GetSessionState(a1, a2);
  (*(void (__fastcall **)(_QWORD, HDEV))(*(_QWORD *)(SessionState + 72) + 848LL))(*(_QWORD *)a1, a2);
  if ( *((_QWORD *)a1 + 1) )
  {
    v7 = W32GetSessionState(v6, v5);
    (*(void (__fastcall **)(_QWORD, HDEV))(*(_QWORD *)(v7 + 72) + 16LL))(*((_QWORD *)a1 + 1), a2);
  }
  *((_QWORD *)a1 + 2) = a2;
}

```

## disassembly

```asm
0x140034bb0  mov     [rsp+arg_0], rbx
0x140034bb5  push    rdi
0x140034bb6  sub     rsp, 20h
0x140034bba  mov     rdi, rdx
0x140034bbd  mov     rbx, rcx
0x140034bc0  call    cs:__imp_W32GetSessionState
0x140034bc7  nop     dword ptr [rax+rax+00h]
0x140034bcc  mov     rcx, [rbx]
0x140034bcf  mov     rdx, rdi
0x140034bd2  mov     r8, [rax+48h]
0x140034bd6  mov     rax, [r8+350h]
0x140034bdd  call    _guard_dispatch_icall
0x140034be2  cmp     qword ptr [rbx+8], 0
0x140034be7  jz      short loc_140034C09
0x140034be9  call    cs:__imp_W32GetSessionState
0x140034bf0  nop     dword ptr [rax+rax+00h]
0x140034bf5  mov     rdx, rdi
0x140034bf8  mov     rcx, [rax+48h]
0x140034bfc  mov     rax, [rcx+10h]
0x140034c00  mov     rcx, [rbx+8]
0x140034c04  call    _guard_dispatch_icall
0x140034c09  mov     [rbx+10h], rdi
0x140034c0d  mov     rbx, [rsp+28h+arg_0]
0x140034c12  add     rsp, 20h
0x140034c16  pop     rdi
0x140034c17  retn
```
