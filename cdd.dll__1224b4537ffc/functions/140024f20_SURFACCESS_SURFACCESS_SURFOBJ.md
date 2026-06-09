# SURFACCESS::SURFACCESS(_SURFOBJ *)

- ea: `0x140024f20`
- end: `0x14002502a`
- name: `??0SURFACCESS@@QEAA@PEAU_SURFOBJ@@@Z`
- size: `266`
- prototype: `SURFACCESS *__fastcall(SURFACCESS *__hidden this, struct _SURFOBJ *)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x140021660`
- `0x1400217b0`
- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`
- `0x140027370`
- `0x140034a60`
- `0x140034b30`
- `0x1400355b0`
- `0x140035630`
- `0x1400357a0`
- `0x1400358d0`
- `0x1400359f0`
- `0x140035a90`
- `0x1400361e0`
- `0x1400363d0`
- `0x140036510`
- `0x1400365a0`
- `0x140036670`
- `0x140036830`
- `0x1400368b0`

## callees

- `0x140024f20`

## import_xrefs

- `WIN32K!EngIsCddDeviceBitmap` at `0x140024f67`
- `WIN32K!EngIsCddDeviceBitmap` at `0x140024faa`
- `WIN32K!EngIsCddDeviceBitmap` at `0x140024f67`
- `WIN32K!EngIsCddDeviceBitmap` at `0x140024faa`
- `WIN32K!W32GetSessionState` at `0x140024f77`
- `WIN32K!W32GetSessionState` at `0x140024f8d`
- `WIN32K!W32GetSessionState` at `0x140024fc9`
- `WIN32K!W32GetSessionState` at `0x140024fe6`
- `WIN32K!W32GetSessionState` at `0x140024f77`
- `WIN32K!W32GetSessionState` at `0x140024f8d`
- `WIN32K!W32GetSessionState` at `0x140024fc9`
- `WIN32K!W32GetSessionState` at `0x140024fe6`

## pseudocode

```c
SURFACCESS *__fastcall SURFACCESS::SURFACCESS(SURFACCESS *this, struct _SURFOBJ *a2)
{
  DHPDEV dhpdev; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rcx
  int IsCddDeviceBitmap; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx

  *(_QWORD *)this = a2;
  *((_DWORD *)this + 6) = 0;
  if ( a2 )
    dhpdev = a2->dhpdev;
  else
    dhpdev = 0;
  *((_QWORD *)this + 1) = dhpdev;
  if ( dhpdev )
  {
    if ( (a2->fjBitmap & 0x4000) != 0 )
    {
      if ( (unsigned int)EngIsCddDeviceBitmap(a2) )
        v7 = *(_QWORD *)(W32GetSessionState(v6, v5) + 72) + 8LL;
      else
        v7 = *(_QWORD *)(W32GetSessionState(v6, v5) + 72) + 840LL;
      *((_QWORD *)this + 2) = v7;
    }
    else
    {
      IsCddDeviceBitmap = EngIsCddDeviceBitmap(a2);
      v9 = (_QWORD *)*((_QWORD *)this + 1);
      v10 = *(_QWORD *)this;
      if ( IsCddDeviceBitmap )
      {
        *(_QWORD *)(v10 + 16) = v9[1];
        v11 = *(_QWORD *)(W32GetSessionState(v9, v10) + 72) + 8LL;
      }
      else
      {
        *(_QWORD *)(v10 + 16) = *v9;
        v11 = *(_QWORD *)(W32GetSessionState(v9, v10) + 72) + 840LL;
      }
      *((_QWORD *)this + 2) = v11;
      a2->fjBitmap |= 0x4000u;
      *((_DWORD *)this + 6) = 1;
    }
  }
  else
  {
    *((_QWORD *)this + 2) = 0;
  }
  return this;
}

```

## disassembly

```asm
0x140024f20  mov     [rsp+arg_0], rbx
0x140024f25  mov     [rsp+arg_8], rsi
0x140024f2a  push    rdi
0x140024f2b  sub     rsp, 20h
0x140024f2f  mov     [rcx], rdx
0x140024f32  mov     rdi, rdx
0x140024f35  mov     dword ptr [rcx+18h], 0
0x140024f3c  mov     rbx, rcx
0x140024f3f  test    rdx, rdx
0x140024f42  jz      short loc_140024F4A
0x140024f44  mov     rax, [rdx+10h]
0x140024f48  jmp     short loc_140024F4C
0x140024f4a  xor     eax, eax
0x140024f4c  mov     [rcx+8], rax
0x140024f50  test    rax, rax
0x140024f53  jz      loc_14002500E
0x140024f59  mov     esi, 4000h
0x140024f5e  mov     rcx, rdi
0x140024f61  test    [rdx+4Eh], si
0x140024f65  jz      short loc_140024FAA
0x140024f67  call    cs:__imp_EngIsCddDeviceBitmap
0x140024f6e  nop     dword ptr [rax+rax+00h]
0x140024f73  test    eax, eax
0x140024f75  jz      short loc_140024F8D
0x140024f77  call    cs:__imp_W32GetSessionState
0x140024f7e  nop     dword ptr [rax+rax+00h]
0x140024f83  mov     rcx, [rax+48h]
0x140024f87  add     rcx, 8
0x140024f8b  jmp     short loc_140024FA4
0x140024f8d  call    cs:__imp_W32GetSessionState
0x140024f94  nop     dword ptr [rax+rax+00h]
0x140024f99  mov     rcx, [rax+48h]
0x140024f9d  add     rcx, 348h
0x140024fa4  mov     [rbx+10h], rcx
0x140024fa8  jmp     short loc_140025016
0x140024faa  call    cs:__imp_EngIsCddDeviceBitmap
0x140024fb1  nop     dword ptr [rax+rax+00h]
0x140024fb6  mov     rcx, [rbx+8]
0x140024fba  mov     rdx, [rbx]
0x140024fbd  test    eax, eax
0x140024fbf  jz      short loc_140024FDF
0x140024fc1  mov     rax, [rcx+8]
0x140024fc5  mov     [rdx+10h], rax
0x140024fc9  call    cs:__imp_W32GetSessionState
0x140024fd0  nop     dword ptr [rax+rax+00h]
0x140024fd5  mov     rcx, [rax+48h]
0x140024fd9  add     rcx, 8
0x140024fdd  jmp     short loc_140024FFD
0x140024fdf  mov     rax, [rcx]
0x140024fe2  mov     [rdx+10h], rax
0x140024fe6  call    cs:__imp_W32GetSessionState
0x140024fed  nop     dword ptr [rax+rax+00h]
0x140024ff2  mov     rcx, [rax+48h]
0x140024ff6  add     rcx, 348h
0x140024ffd  mov     [rbx+10h], rcx
0x140025001  or      [rdi+4Eh], si
0x140025005  mov     dword ptr [rbx+18h], 1
0x14002500c  jmp     short loc_140025016
0x14002500e  mov     qword ptr [rcx+10h], 0
0x140025016  mov     rsi, [rsp+28h+arg_8]
0x14002501b  mov     rax, rbx
0x14002501e  mov     rbx, [rsp+28h+arg_0]
0x140025023  add     rsp, 20h
0x140025027  pop     rdi
0x140025028  retn
```
