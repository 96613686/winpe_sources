# RevertVolumeHelper(void *,ulong)

- ea: `0x18000b1b0`
- end: `0x18000b274`
- name: `?RevertVolumeHelper@@YAJPEAXK@Z`
- size: `196`
- prototype: `__int64 __fastcall(void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005200`

## callees

- `0x1800037a0`
- `0x18000b1b0`

## import_xrefs

- `FVEAPI!FveCloseVolume` at `0x18000b261`
- `FVEAPI!FveCloseVolume` at `0x18000b261`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18000b1da`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18000b1da`
- `FVEAPI!FveRevertVolume` at `0x18000b220`
- `FVEAPI!FveRevertVolume` at `0x18000b220`

## pseudocode

```c
__int64 __fastcall RevertVolumeHelper(void *a1, int a2)
{
  unsigned int v2; // eax
  int v3; // ebx
  unsigned int v4; // eax
  __int64 v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = -1;
  v2 = FveOpenVolumeByHandle(a1, 0, 1, 0xFFFFFFFFLL, a2, &v6);
  v3 = v2;
  if ( !v2 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v2);
  if ( v3 >= 0 )
  {
LABEL_6:
    v4 = FveRevertVolume(v6);
    v3 = v4;
    if ( v4 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v4);
  }
  if ( v6 != -1 )
    FveCloseVolume(v6);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000b1b0  mov     r11, rsp
0x18000b1b3  mov     [r11+8], rbx
0x18000b1b7  push    rdi
0x18000b1b8  sub     rsp, 30h
0x18000b1bc  or      r9d, 0FFFFFFFFh
0x18000b1c0  mov     qword ptr [r11+18h], 0FFFFFFFFFFFFFFFFh
0x18000b1c8  lea     rax, [r11+18h]
0x18000b1cc  mov     [r11-10h], rax
0x18000b1d0  mov     [rsp+38h+var_18], edx
0x18000b1d4  xor     edx, edx
0x18000b1d6  lea     r8d, [r9+2]
0x18000b1da  call    cs:__imp_FveOpenVolumeByHandle
0x18000b1e0  lea     rdi, WPP_GLOBAL_Control
0x18000b1e7  mov     ebx, eax
0x18000b1e9  test    eax, eax
0x18000b1eb  jz      short loc_18000B21B
0x18000b1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1f4  cmp     rcx, rdi
0x18000b1f7  jz      short loc_18000B217
0x18000b1f9  test    byte ptr [rcx+1Ch], 40h
0x18000b1fd  jz      short loc_18000B217
0x18000b1ff  mov     rcx, [rcx+10h]
0x18000b203  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x18000b20a  mov     edx, 51h ; 'Q'
0x18000b20f  mov     r9d, eax
0x18000b212  call    WPP_SF_d
0x18000b217  test    ebx, ebx
0x18000b219  js      short loc_18000B256
0x18000b21b  mov     rcx, [rsp+38h+arg_10]
0x18000b220  call    cs:__imp_FveRevertVolume
0x18000b226  mov     ebx, eax
0x18000b228  test    eax, eax
0x18000b22a  jz      short loc_18000B256
0x18000b22c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b233  cmp     rcx, rdi
0x18000b236  jz      short loc_18000B256
0x18000b238  test    byte ptr [rcx+1Ch], 40h
0x18000b23c  jz      short loc_18000B256
0x18000b23e  mov     rcx, [rcx+10h]
0x18000b242  lea     r8, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x18000b249  mov     edx, 52h ; 'R'
0x18000b24e  mov     r9d, eax
0x18000b251  call    WPP_SF_d
0x18000b256  mov     rcx, [rsp+38h+arg_10]
0x18000b25b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b25f  jz      short loc_18000B267
0x18000b261  call    cs:__imp_FveCloseVolume
0x18000b267  mov     eax, ebx
0x18000b269  mov     rbx, [rsp+38h+arg_0]
0x18000b26e  add     rsp, 30h
0x18000b272  pop     rdi
0x18000b273  retn
```
