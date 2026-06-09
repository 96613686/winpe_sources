# FIPreCreateCallback

- ea: `0x140016dc0`
- end: `0x140016e96`
- name: `FIPreCreateCallback`
- size: `214`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140010cd0`
- `0x140014bf0`
- `0x140016dc0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140016e40`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140016e40`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140016e30`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x140016e30`

## pseudocode

```c
__int64 __fastcall FIPreCreateCallback(struct _FLT_CALLBACK_DATA *a1, _QWORD *a2, __int64 *a3)
{
  __int64 v3; // rsi
  int v7; // ebx
  _QWORD v9[9]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v10; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v10 = 0;
  if ( *(_QWORD *)(qword_140009A00 + 16) )
    FIETWLogFileCreate(a1, (__int64)a2, 0x402u, 1088);
  if ( (*(_DWORD *)(a2[4] + 80LL) & 0x400000) != 0
    && ((a1->Iopb->Parameters.Create.ShareAccess & 6) == 0 || (*(_DWORD *)(a2[4] + 80LL) & 0x800) != 0) )
  {
    v7 = 1;
    _InterlockedAdd(&dword_1400099F8, 1u);
  }
  else
  {
    v7 = 0;
  }
  if ( !PsIsCurrentThreadPrefetching() && !IoGetTopLevelIrp() && v7 )
  {
    v9[0] = a2[2];
    v9[1] = a2[3];
    v9[2] = a2[4];
    FIPfVolumeFSOpPreventConflicts((__int64)v9, 0, &v10);
    v3 = v10;
  }
  *a3 = v3;
  return 0;
}

```

## disassembly

```asm
0x140016dc0  push    rbx
0x140016dc2  push    rsi
0x140016dc3  push    rdi
0x140016dc4  push    r14
0x140016dc6  sub     rsp, 48h
0x140016dca  mov     rax, cs:qword_140009A00
0x140016dd1  xor     esi, esi
0x140016dd3  mov     r14, r8
0x140016dd6  mov     [rsp+68h+arg_0], rsi
0x140016ddb  mov     rdi, rdx
0x140016dde  mov     rbx, rcx
0x140016de1  mov     r9, [rax+10h]
0x140016de5  test    r9, r9
0x140016de8  jz      short loc_140016DF9
0x140016dea  mov     r9d, 440h
0x140016df0  lea     r8d, [r9-3Eh]
0x140016df4  call    FIETWLogFileCreate
0x140016df9  mov     rax, [rbx+10h]
0x140016dfd  movzx   edx, word ptr [rax+2Ah]
0x140016e01  mov     rax, [rdi+20h]
0x140016e05  mov     ecx, [rax+50h]
0x140016e08  bt      ecx, 16h
0x140016e0c  jnb     short loc_140016E2E
0x140016e0e  test    dl, 6
0x140016e11  jz      short loc_140016E20
0x140016e13  mov     rax, [rdi+20h]
0x140016e17  mov     ecx, [rax+50h]
0x140016e1a  bt      ecx, 0Bh
0x140016e1e  jnb     short loc_140016E2E
0x140016e20  mov     ebx, 1
0x140016e25  lock add cs:dword_1400099F8, ebx
0x140016e2c  jmp     short loc_140016E30
0x140016e2e  xor     ebx, ebx
0x140016e30  call    cs:__imp_PsIsCurrentThreadPrefetching
0x140016e37  nop     dword ptr [rax+rax+00h]
0x140016e3c  test    al, al
0x140016e3e  jnz     short loc_140016E86
0x140016e40  call    cs:__imp_IoGetTopLevelIrp
0x140016e47  nop     dword ptr [rax+rax+00h]
0x140016e4c  test    rax, rax
0x140016e4f  jnz     short loc_140016E86
0x140016e51  test    ebx, ebx
0x140016e53  jz      short loc_140016E86
0x140016e55  mov     rax, [rdi+10h]
0x140016e59  lea     r8, [rsp+68h+arg_0]
0x140016e5e  mov     [rsp+68h+var_48], rax
0x140016e63  lea     rcx, [rsp+68h+var_48]
0x140016e68  mov     rax, [rdi+18h]
0x140016e6c  xor     edx, edx
0x140016e6e  mov     [rsp+68h+var_40], rax
0x140016e73  mov     rax, [rdi+20h]
0x140016e77  mov     [rsp+68h+var_38], rax
0x140016e7c  call    FIPfVolumeFSOpPreventConflicts
0x140016e81  mov     rsi, [rsp+68h+arg_0]
0x140016e86  mov     [r14], rsi
0x140016e89  xor     eax, eax
0x140016e8b  add     rsp, 48h
0x140016e8f  pop     r14
0x140016e91  pop     rdi
0x140016e92  pop     rsi
0x140016e93  pop     rbx
0x140016e94  retn
```
