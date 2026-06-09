# CDDPDEV::SyncGPUAccess(uint,int)

- ea: `0x14000e35c`
- end: `0x14000e417`
- name: `?SyncGPUAccess@CDDPDEV@@QEAAJIH@Z`
- size: `187`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, unsigned int, int)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x14000cf80`
- `0x14000e210`
- `0x14000e580`
- `0x14001c630`
- `0x14001ff70`
- `0x14002ee20`
- `0x1400324c0`
- `0x140032640`

## callees

- `0x14000e35c`
- `0x140027b1c`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry3` at `0x14000e3b4`
- `watchdog!WdLogSingleEntry3` at `0x14000e3b4`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000e3cb`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14000e3cb`

## pseudocode

```c
__int64 __fastcall CDDPDEV::SyncGPUAccess(CDDPDEV *this, unsigned int a2, unsigned int a3)
{
  __int64 v3; // rsi
  int v6; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rax

  v3 = a2;
  if ( !a2 )
    return 0;
  v6 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))this + 28))(
         *((_QWORD *)this + 684),
         *((_QWORD *)this + 311),
         a2,
         a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    WdLogSingleEntry3(4, v6, v3, *((_QWORD *)this + 684));
    WdLogGlobalForLineNumber = 418;
    v8 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v8[3] = gCddImageInfo;
    v8[4] = (unsigned int)dword_14003E570;
    v8[5] = 215857758;
    WdLogGlobalForLineNumber = 418;
    CDDPDEV::CheckDeviceRemoved(this, v7);
  }
  return v7;
}

```

## disassembly

```asm
0x14000e35c  mov     [rsp+arg_0], rbx
0x14000e361  mov     [rsp+arg_8], rsi
0x14000e366  push    rdi
0x14000e367  sub     rsp, 30h
0x14000e36b  mov     esi, edx
0x14000e36d  mov     rdi, rcx
0x14000e370  test    edx, edx
0x14000e372  jnz     short loc_14000E37B
0x14000e374  xor     eax, eax
0x14000e376  jmp     loc_14000E406
0x14000e37b  mov     rax, [rcx+0E0h]
0x14000e382  mov     r9d, r8d
0x14000e385  mov     rdx, [rcx+9B8h]
0x14000e38c  mov     r8d, esi
0x14000e38f  mov     rcx, [rcx+1560h]
0x14000e396  call    _guard_dispatch_icall
0x14000e39b  movsxd  rbx, eax
0x14000e39e  test    eax, eax
0x14000e3a0  jns     short loc_14000E404
0x14000e3a2  mov     r9, [rdi+1560h]
0x14000e3a9  mov     r8, rsi
0x14000e3ac  mov     rdx, rbx
0x14000e3af  mov     ecx, 4
0x14000e3b4  call    cs:__imp_WdLogSingleEntry3
0x14000e3bb  nop     dword ptr [rax+rax+00h]
0x14000e3c0  mov     esi, 1A2h
0x14000e3c5  mov     cs:WdLogGlobalForLineNumber, esi
0x14000e3cb  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14000e3d2  nop     dword ptr [rax+rax+00h]
0x14000e3d7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14000e3de  mov     edx, ebx; int
0x14000e3e0  mov     [rax+18h], rcx
0x14000e3e4  mov     ecx, cs:dword_14003E570
0x14000e3ea  mov     [rax+20h], rcx
0x14000e3ee  mov     rcx, rdi; this
0x14000e3f1  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14000e3f9  mov     cs:WdLogGlobalForLineNumber, esi
0x14000e3ff  call    ?CheckDeviceRemoved@CDDPDEV@@QEAAXJ@Z; CDDPDEV::CheckDeviceRemoved(long)
0x14000e404  mov     eax, ebx
0x14000e406  mov     rbx, [rsp+38h+arg_0]
0x14000e40b  mov     rsi, [rsp+38h+arg_8]
0x14000e410  add     rsp, 30h
0x14000e414  pop     rdi
0x14000e415  retn
```
