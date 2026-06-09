# RmtDeleteDeviceBitmapExSurf(_SURFOBJ *)

- ea: `0x140034e90`
- end: `0x140034ee8`
- name: `?RmtDeleteDeviceBitmapExSurf@@YAXPEAU_SURFOBJ@@@Z`
- size: `88`
- prototype: `void __fastcall(struct _SURFOBJ *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140034e90`
- `0x1400372d0`

## import_xrefs

- `WIN32K!EngIsCddDeviceBitmap` at `0x140034e99`
- `WIN32K!EngIsCddDeviceBitmap` at `0x140034e99`
- `WIN32K!W32GetSessionState` at `0x140034ea9`
- `WIN32K!W32GetSessionState` at `0x140034ec2`
- `WIN32K!W32GetSessionState` at `0x140034ea9`
- `WIN32K!W32GetSessionState` at `0x140034ec2`

## pseudocode

```c
void __fastcall RmtDeleteDeviceBitmapExSurf(struct _SURFOBJ *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  void (__fastcall *v4)(DHSURF); // rax

  if ( (unsigned int)EngIsCddDeviceBitmap(a1) )
    v4 = *(void (__fastcall **)(DHSURF))(*(_QWORD *)(W32GetSessionState(v3, v2) + 72) + 768LL);
  else
    v4 = *(void (__fastcall **)(DHSURF))(*(_QWORD *)(W32GetSessionState(v3, v2) + 72) + 1600LL);
  v4(a1->dhsurf);
}

```

## disassembly

```asm
0x140034e90  push    rbx
0x140034e92  sub     rsp, 20h
0x140034e96  mov     rbx, rcx
0x140034e99  call    cs:__imp_EngIsCddDeviceBitmap
0x140034ea0  nop     dword ptr [rax+rax+00h]
0x140034ea5  test    eax, eax
0x140034ea7  jz      short loc_140034EC2
0x140034ea9  call    cs:__imp_W32GetSessionState
0x140034eb0  nop     dword ptr [rax+rax+00h]
0x140034eb5  mov     rdx, [rax+48h]
0x140034eb9  mov     rax, [rdx+300h]
0x140034ec0  jmp     short loc_140034ED9
0x140034ec2  call    cs:__imp_W32GetSessionState
0x140034ec9  nop     dword ptr [rax+rax+00h]
0x140034ece  mov     rcx, [rax+48h]
0x140034ed2  mov     rax, [rcx+640h]
0x140034ed9  mov     rcx, [rbx]
0x140034edc  call    _guard_dispatch_icall
0x140034ee1  add     rsp, 20h
0x140034ee5  pop     rbx
0x140034ee6  retn
```
