# CDirectMusicSynthPort7::CacheSinkUsesDSound(void)

- ea: `0x180016500`
- end: `0x18001658c`
- name: `?CacheSinkUsesDSound@CDirectMusicSynthPort7@@AEAAXXZ`
- size: `140`
- prototype: `void __fastcall(CDirectMusicSynthPort7 *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800166f4`
- `0x1800168a0`

## callees

- `0x180016500`
- `0x180022010`

## pseudocode

```c
void __fastcall CDirectMusicSynthPort7::CacheSinkUsesDSound(CDirectMusicSynthPort7 *this)
{
  __int64 v2; // rcx
  GUID v3; // [rsp+40h] [rbp-28h] BYREF
  int v4; // [rsp+50h] [rbp-18h]
  int v5; // [rsp+54h] [rbp-14h]
  int v6; // [rsp+70h] [rbp+8h] BYREF
  int v7; // [rsp+78h] [rbp+10h] BYREF

  *((_BYTE *)this + 792) = 0;
  v2 = *((_QWORD *)this + 55);
  if ( v2 )
  {
    v6 = 0;
    v7 = 0;
    v3 = GUID_DMUS_PROP_SinkUsesDSound;
    v4 = 0;
    v5 = 1;
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64, int *, int, int *))(*(_QWORD *)v2 + 24LL))(
           v2,
           &v3,
           24,
           &v6,
           4,
           &v7) >= 0 )
    {
      if ( v6 )
        *((_BYTE *)this + 792) = 1;
    }
  }
}

```

## disassembly

```asm
0x180016500  mov     rax, rsp
0x180016503  push    rbx
0x180016504  sub     rsp, 60h
0x180016508  mov     rbx, rcx
0x18001650b  mov     byte ptr [rcx+318h], 0
0x180016512  mov     rcx, [rcx+1B8h]
0x180016519  test    rcx, rcx
0x18001651c  jz      short loc_180016586
0x18001651e  movups  xmm0, xmmword ptr cs:GUID_DMUS_PROP_SinkUsesDSound.Data1
0x180016525  mov     dword ptr [rax+8], 0
0x18001652c  lea     rdx, [rsp+68h+arg_8]
0x180016531  mov     dword ptr [rax+10h], 0
0x180016538  lea     r9, [rsp+68h+arg_0]
0x18001653d  movdqu  xmmword ptr [rax-28h], xmm0
0x180016542  mov     dword ptr [rax-18h], 0
0x180016549  mov     r8d, 18h
0x18001654f  mov     dword ptr [rax-14h], 1
0x180016556  mov     rax, [rcx]
0x180016559  mov     [rsp+68h+var_40], rdx
0x18001655e  lea     rdx, [rsp+68h+var_28]
0x180016563  mov     [rsp+68h+var_48], 4
0x18001656b  mov     rax, [rax+18h]
0x18001656f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016574  test    eax, eax
0x180016576  js      short loc_180016586
0x180016578  cmp     [rsp+68h+arg_0], 0
0x18001657d  jz      short loc_180016586
0x18001657f  mov     byte ptr [rbx+318h], 1
0x180016586  add     rsp, 60h
0x18001658a  pop     rbx
0x18001658b  retn
```
