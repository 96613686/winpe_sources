# SetTimer

- ea: `0x140015e58`
- end: `0x140015f00`
- name: `SetTimer`
- size: `168`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140005504`
- `0x140005720`
- `0x140015f08`

## callees

- `0x14000113c`
- `0x140015e58`

## import_xrefs

- `NDIS!NdisSetTimer` at `0x140015eb3`
- `NDIS!NdisSetTimer` at `0x140015eb3`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall SetTimer(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT *result; // rax
  __int64 v4; // rcx
  UINT v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rdx

  result = (PDEVICE_OBJECT *)(a1 + 8);
  v4 = *(_QWORD *)(a1 + 8);
  if ( (PDEVICE_OBJECT *)v4 != result )
  {
    if ( !a2 )
      a2 = MEMORY[0xFFFFF78000000014];
    v5 = 0;
    v6 = (unsigned __int128)((*(_QWORD *)(v4 + 16) - a2) * (__int128)0x346DC5D63886594BLL) >> 64;
    v7 = ((unsigned __int64)v6 >> 63) + (v6 >> 11);
    if ( v7 > 0 )
      v5 = v7;
    NdisSetTimer((PNDIS_TIMER)(a1 + 64), v5);
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      return (PDEVICE_OBJECT *)WPP_SF_d(
                                 (__int64)WPP_GLOBAL_Control->AttachedDevice,
                                 0x11u,
                                 (__int64)WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids,
                                 v5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140015e58  push    rbx
0x140015e5a  sub     rsp, 20h
0x140015e5e  lea     rax, [rcx+8]
0x140015e62  mov     r8, rcx
0x140015e65  mov     rcx, [rax]
0x140015e68  cmp     rcx, rax
0x140015e6b  jz      loc_140015EF9
0x140015e71  test    rdx, rdx
0x140015e74  jnz     short loc_140015E83
0x140015e76  mov     rdx, 0FFFFF78000000014h
0x140015e80  mov     rdx, [rdx]
0x140015e83  mov     rcx, [rcx+10h]
0x140015e87  xor     ebx, ebx
0x140015e89  sub     rcx, rdx
0x140015e8c  mov     rax, 346DC5D63886594Bh
0x140015e96  imul    rcx
0x140015e99  lea     rcx, [r8+40h]; Timer
0x140015e9d  sar     rdx, 0Bh
0x140015ea1  mov     rax, rdx
0x140015ea4  shr     rax, 3Fh
0x140015ea8  add     rdx, rax
0x140015eab  test    rdx, rdx
0x140015eae  cmovg   ebx, edx
0x140015eb1  mov     edx, ebx; MillisecondsToDelay
0x140015eb3  call    cs:__imp_NdisSetTimer
0x140015eba  nop     dword ptr [rax+rax+00h]
0x140015ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ec6  lea     rax, WPP_GLOBAL_Control
0x140015ecd  cmp     rcx, rax
0x140015ed0  jz      short loc_140015EF9
0x140015ed2  test    dword ptr [rcx+2Ch], 400h
0x140015ed9  jz      short loc_140015EF9
0x140015edb  cmp     byte ptr [rcx+29h], 3
0x140015edf  jb      short loc_140015EF9
0x140015ee1  mov     rcx, [rcx+18h]
0x140015ee5  lea     r8, WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids
0x140015eec  mov     edx, 11h
0x140015ef1  mov     r9d, ebx
0x140015ef4  call    WPP_SF_d
0x140015ef9  add     rsp, 20h
0x140015efd  pop     rbx
0x140015efe  retn
```
