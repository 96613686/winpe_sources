# CdVerifyFcbOperation

- ea: `0x14001a2a0`
- end: `0x14001a3fa`
- name: `CdVerifyFcbOperation`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x140011744`
- `0x140012d24`
- `0x140013140`
- `0x140013290`
- `0x140013390`
- `0x1400134c0`
- `0x140014c38`
- `0x1400156c0`
- `0x140015850`
- `0x140015a50`
- `0x140015bf0`
- `0x140015db0`
- `0x140017ab8`
- `0x14001aa78`

## callees

- `0x140001114`
- `0x14001a2a0`

## import_xrefs

- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a37a`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a3a9`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a37a`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001a3a9`

## pseudocode

```c
char __fastcall CdVerifyFcbOperation(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  char *v4; // rcx
  __int64 v5; // rax
  char v6; // al
  __int64 v7; // rcx
  int v8; // r8d
  struct _DEVICE_OBJECT *v9; // rdx

  if ( a1 )
  {
    v3 = *(_QWORD *)(a1 + 8);
    v4 = *(char **)(v3 + 184);
    v5 = *((_QWORD *)v4 + 6);
    if ( v5 )
    {
      if ( (*(_DWORD *)(v5 + 80) & 0x4000) != 0 && (*(_DWORD *)(v3 + 16) & 2) == 0 )
      {
        v6 = *v4;
        if ( *v4 != 2 && v6 != 5 && (v6 != 3 || (v4[1] & 4) == 0) )
          CdRaiseStatusEx(a1, -1073741528, 0, 1769472, 682);
      }
    }
  }
  v7 = *(_QWORD *)(a2 + 120);
  v8 = *(_DWORD *)(v7 + 52);
  if ( (unsigned int)(v8 - 3) <= 1 )
  {
    if ( a1 )
    {
      if ( (*(_DWORD *)(v7 + 48) & 0x800) != 0 )
        CdRaiseStatusEx(a1, -1073741202, 0, 1769472, 699);
      CdRaiseStatusEx(a1, -1073741672, 0, 1769472, 703);
    }
    return 0;
  }
  v9 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v7 + 8) + 16LL);
  if ( (v9->Flags & 2) != 0 )
  {
    if ( a1 )
    {
      IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), v9);
      CdRaiseStatusEx(a1, -2147483626, 0, 1769472, 721);
    }
    return 0;
  }
  if ( (unsigned int)(v8 - 1) <= 1 )
    return 1;
  if ( a1 )
  {
    if ( !v8 )
    {
      IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 8), v9);
      CdRaiseStatusEx(a1, -1073741806, 0, 1769472, 752);
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14001a2a0  push    rbx
0x14001a2a2  sub     rsp, 30h
0x14001a2a6  mov     rbx, rcx
0x14001a2a9  mov     r9b, 2
0x14001a2ac  test    rcx, rcx
0x14001a2af  jz      short loc_14001A2EC
0x14001a2b1  mov     r8, [rcx+8]
0x14001a2b5  mov     rcx, [r8+0B8h]
0x14001a2bc  mov     rax, [rcx+30h]
0x14001a2c0  test    rax, rax
0x14001a2c3  jz      short loc_14001A2EC
0x14001a2c5  test    dword ptr [rax+50h], 4000h
0x14001a2cc  jz      short loc_14001A2EC
0x14001a2ce  mov     eax, [r8+10h]
0x14001a2d2  test    r9b, al
0x14001a2d5  jnz     short loc_14001A2EC
0x14001a2d7  mov     al, [rcx]
0x14001a2d9  cmp     al, r9b
0x14001a2dc  jz      short loc_14001A2EC
0x14001a2de  cmp     al, 5
0x14001a2e0  jz      short loc_14001A2EC
0x14001a2e2  cmp     al, 3
0x14001a2e4  jnz     short loc_14001A357
0x14001a2e6  test    byte ptr [rcx+1], 4
0x14001a2ea  jz      short loc_14001A357
0x14001a2ec  mov     rcx, [rdx+78h]
0x14001a2f0  mov     r8d, [rcx+34h]
0x14001a2f4  lea     eax, [r8-3]
0x14001a2f8  cmp     eax, 1
0x14001a2fb  jbe     short loc_14001A32B
0x14001a2fd  mov     rax, [rcx+8]
0x14001a301  mov     rdx, [rax+10h]; DeviceObject
0x14001a305  mov     eax, [rdx+30h]
0x14001a308  test    r9b, al
0x14001a30b  jz      short loc_14001A314
0x14001a30d  test    rbx, rbx
0x14001a310  jnz     short loc_14001A376
0x14001a312  jmp     short loc_14001A34E
0x14001a314  lea     eax, [r8-1]
0x14001a318  cmp     eax, 1
0x14001a31b  jbe     short loc_14001A327
0x14001a31d  test    rbx, rbx
0x14001a320  jz      short loc_14001A34E
0x14001a322  test    r8d, r8d
0x14001a325  jz      short loc_14001A3A5
0x14001a327  mov     al, 1
0x14001a329  jmp     short loc_14001A350
0x14001a32b  test    rbx, rbx
0x14001a32e  jz      short loc_14001A34E
0x14001a330  xor     r8d, r8d
0x14001a333  mov     r9d, 1B0000h
0x14001a339  test    dword ptr [rcx+30h], 800h
0x14001a340  mov     rcx, rbx
0x14001a343  jz      loc_14001A3E7
0x14001a349  jmp     loc_14001A3D4
0x14001a34e  xor     al, al
0x14001a350  add     rsp, 30h
0x14001a354  pop     rbx
0x14001a355  retn
0x14001a357  mov     r9d, 1B0000h
0x14001a35d  mov     [rsp+38h+var_18], 2AAh
0x14001a365  xor     r8d, r8d
0x14001a368  mov     edx, 0C0000128h
0x14001a36d  mov     rcx, rbx
0x14001a370  call    CdRaiseStatusEx
0x14001a376  mov     rcx, [rbx+8]; Irp
0x14001a37a  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14001a381  nop     dword ptr [rax+rax+00h]
0x14001a386  mov     r9d, 1B0000h
0x14001a38c  mov     [rsp+38h+var_18], 2D1h
0x14001a394  xor     r8d, r8d
0x14001a397  mov     edx, 80000016h
0x14001a39c  mov     rcx, rbx
0x14001a39f  call    CdRaiseStatusEx
0x14001a3a5  mov     rcx, [rbx+8]; Irp
0x14001a3a9  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14001a3b0  nop     dword ptr [rax+rax+00h]
0x14001a3b5  mov     r9d, 1B0000h
0x14001a3bb  mov     [rsp+38h+var_18], 2F0h
0x14001a3c3  xor     r8d, r8d
0x14001a3c6  mov     edx, 0C0000012h
0x14001a3cb  mov     rcx, rbx
0x14001a3ce  call    CdRaiseStatusEx
0x14001a3d4  mov     edx, 0C000026Eh
0x14001a3d9  mov     [rsp+38h+var_18], 2BBh
0x14001a3e1  call    CdRaiseStatusEx
0x14001a3e7  mov     edx, 0C0000098h
0x14001a3ec  mov     [rsp+38h+var_18], 2BFh
0x14001a3f4  call    CdRaiseStatusEx
```
