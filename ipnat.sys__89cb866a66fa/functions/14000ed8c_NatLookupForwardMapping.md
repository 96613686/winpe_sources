# NatLookupForwardMapping

- ea: `0x14000ed8c`
- end: `0x14000ef59`
- name: `NatLookupForwardMapping`
- size: `461`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140009488`
- `0x14000d8b0`
- `0x14000e988`
- `0x14000f2a4`
- `0x14000f6cc`
- `0x140022320`

## callees

- `0x14000218c`
- `0x14000ed8c`
- `0x14000fe48`

## pseudocode

```c
__int64 __fastcall NatLookupForwardMapping(unsigned __int64 a1, unsigned __int64 a2, __int64 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  PDEVICE_OBJECT v8; // rcx
  unsigned __int16 v9; // dx
  _QWORD *v11; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_ii(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x37u,
      (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids,
      a1,
      a2);
  }
  v6 = a1 & 0x3FF;
  if ( (_DWORD)a1 == LODWORD(MappingCache[3 * v6]) )
  {
    ++LODWORD(MappingCache[3 * v6 + 2]);
    v7 = MappingCache[3 * v6 + 1];
    if ( v7 && *(_QWORD *)(v7 + 64) == a1 && *(_QWORD *)(v7 + 80) == a2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x38u,
            (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v9 = 57;
          goto LABEL_17;
        }
      }
      return v7;
    }
  }
  else
  {
    ++HIDWORD(MappingCache[3 * v6 + 2]);
  }
  v7 = 0;
  v11 = (_QWORD *)((MappingTree + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)MappingTree >> 64));
  if ( !v11 )
  {
LABEL_28:
    if ( a3 )
      *a3 = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x3Bu,
        (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    return 0;
  }
  while ( 1 )
  {
    v7 = (__int64)(v11 - 2);
    if ( a1 >= v11[6] )
    {
      if ( a1 > *(_QWORD *)(v7 + 64) )
        goto LABEL_26;
      if ( a2 >= *(_QWORD *)(v7 + 80) )
        break;
    }
    v11 = (_QWORD *)v11[1];
LABEL_27:
    if ( !v11 )
      goto LABEL_28;
  }
  if ( a2 > *(_QWORD *)(v7 + 80) )
  {
LABEL_26:
    v11 = (_QWORD *)v11[2];
    goto LABEL_27;
  }
  if ( (_DWORD)a1 != LODWORD(MappingCache[3 * v6])
    && SLODWORD(MappingCache[3 * v6 + 2]) < HIDWORD(MappingCache[3 * v6 + 2])
                                          - (SHIDWORD(MappingCache[3 * v6 + 2]) >> 2) )
  {
    LODWORD(MappingCache[3 * v6]) = a1;
    MappingCache[3 * v6 + 1] = v7;
    MappingCache[3 * v6 + 2] = 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v9 = 58;
LABEL_17:
    WPP_SF_((__int64)v8->AttachedDevice, v9, (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x14000ed8c  push    rbx
0x14000ed8e  push    rsi
0x14000ed8f  push    rdi
0x14000ed90  push    r12
0x14000ed92  push    r14
0x14000ed94  push    r15
0x14000ed96  sub     rsp, 38h
0x14000ed9a  mov     r14, r8
0x14000ed9d  mov     rsi, rdx
0x14000eda0  mov     rdi, rcx
0x14000eda3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edaa  lea     r15, WPP_GLOBAL_Control
0x14000edb1  lea     r12, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000edb8  cmp     rcx, r15
0x14000edbb  jz      short loc_14000EDE3
0x14000edbd  mov     eax, [rcx+2Ch]
0x14000edc0  test    al, 1
0x14000edc2  jz      short loc_14000EDE3
0x14000edc4  cmp     byte ptr [rcx+29h], 6
0x14000edc8  jb      short loc_14000EDE3
0x14000edca  mov     rcx, [rcx+18h]
0x14000edce  mov     edx, 37h ; '7'
0x14000edd3  mov     r9, rdi
0x14000edd6  mov     [rsp+68h+var_48], rsi
0x14000eddb  mov     r8, r12
0x14000edde  call    WPP_SF_ii
0x14000ede3  mov     rcx, cs:off_14002F070
0x14000edea  mov     eax, edi
0x14000edec  and     eax, 3FFh
0x14000edf1  lea     r8, [rax+rax*2]
0x14000edf5  cmp     edi, [rcx+r8*8]
0x14000edf9  jnz     short loc_14000EE70
0x14000edfb  inc     dword ptr [rcx+r8*8+10h]
0x14000ee00  mov     rbx, [rcx+r8*8+8]
0x14000ee05  test    rbx, rbx
0x14000ee08  jz      short loc_14000EE75
0x14000ee0a  cmp     [rbx+40h], rdi
0x14000ee0e  jnz     short loc_14000EE75
0x14000ee10  cmp     [rbx+50h], rsi
0x14000ee14  jnz     short loc_14000EE75
0x14000ee16  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee1d  cmp     rcx, r15
0x14000ee20  jz      short loc_14000EE6B
0x14000ee22  mov     eax, [rcx+2Ch]
0x14000ee25  test    al, 1
0x14000ee27  jz      short loc_14000EE40
0x14000ee29  cmp     byte ptr [rcx+29h], 5
0x14000ee2d  jb      short loc_14000EE40
0x14000ee2f  mov     rcx, [rcx+18h]
0x14000ee33  mov     edx, 38h ; '8'
0x14000ee38  mov     r8, r12
0x14000ee3b  call    WPP_SF_
0x14000ee40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee47  cmp     rcx, r15
0x14000ee4a  jz      short loc_14000EE6B
0x14000ee4c  mov     edx, [rcx+2Ch]
0x14000ee4f  test    dl, 1
0x14000ee52  jz      short loc_14000EE6B
0x14000ee54  cmp     byte ptr [rcx+29h], 6
0x14000ee58  jb      short loc_14000EE6B
0x14000ee5a  mov     edx, 39h ; '9'
0x14000ee5f  mov     rcx, [rcx+18h]
0x14000ee63  mov     r8, r12
0x14000ee66  call    WPP_SF_
0x14000ee6b  mov     rax, rbx
0x14000ee6e  jmp     short loc_14000EEE8
0x14000ee70  inc     dword ptr [rcx+r8*8+14h]
0x14000ee75  mov     rax, qword ptr cs:MappingTree
0x14000ee7c  xor     ebx, ebx
0x14000ee7e  lea     rcx, [rax+10h]
0x14000ee82  neg     rax
0x14000ee85  sbb     rdx, rdx
0x14000ee88  and     rdx, rcx
0x14000ee8b  jz      short loc_14000EEB4
0x14000ee8d  lea     rbx, [rdx-10h]
0x14000ee91  cmp     rdi, [rdx+30h]
0x14000ee95  jnb     short loc_14000EE9D
0x14000ee97  mov     rdx, [rdx+8]
0x14000ee9b  jmp     short loc_14000EEAF
0x14000ee9d  cmp     rdi, [rbx+40h]
0x14000eea1  ja      short loc_14000EEAB
0x14000eea3  cmp     rsi, [rbx+50h]
0x14000eea7  jb      short loc_14000EE97
0x14000eea9  jbe     short loc_14000EEF7
0x14000eeab  mov     rdx, [rdx+10h]
0x14000eeaf  test    rdx, rdx
0x14000eeb2  jnz     short loc_14000EE8D
0x14000eeb4  test    r14, r14
0x14000eeb7  jz      short loc_14000EEBC
0x14000eeb9  mov     [r14], rbx
0x14000eebc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eec3  cmp     rcx, r15
0x14000eec6  jz      short loc_14000EEE6
0x14000eec8  mov     eax, [rcx+2Ch]
0x14000eecb  test    al, 1
0x14000eecd  jz      short loc_14000EEE6
0x14000eecf  cmp     byte ptr [rcx+29h], 6
0x14000eed3  jb      short loc_14000EEE6
0x14000eed5  mov     rcx, [rcx+18h]
0x14000eed9  mov     edx, 3Bh ; ';'
0x14000eede  mov     r8, r12
0x14000eee1  call    WPP_SF_
0x14000eee6  xor     eax, eax
0x14000eee8  add     rsp, 38h
0x14000eeec  pop     r15
0x14000eeee  pop     r14
0x14000eef0  pop     r12
0x14000eef2  pop     rdi
0x14000eef3  pop     rsi
0x14000eef4  pop     rbx
0x14000eef5  retn
0x14000eef7  mov     rdx, cs:off_14002F070
0x14000eefe  cmp     edi, [rdx+r8*8]
0x14000ef02  jz      short loc_14000EF29
0x14000ef04  mov     ecx, [rdx+r8*8+14h]
0x14000ef09  mov     eax, ecx
0x14000ef0b  sar     eax, 2
0x14000ef0e  sub     ecx, eax
0x14000ef10  cmp     [rdx+r8*8+10h], ecx
0x14000ef15  jge     short loc_14000EF29
0x14000ef17  mov     [rdx+r8*8], edi
0x14000ef1b  mov     [rdx+r8*8+8], rbx
0x14000ef20  mov     qword ptr [rdx+r8*8+10h], 0
0x14000ef29  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef30  cmp     rcx, r15
0x14000ef33  jz      loc_14000EE6B
0x14000ef39  mov     edx, [rcx+2Ch]
0x14000ef3c  test    dl, 1
0x14000ef3f  jz      loc_14000EE6B
0x14000ef45  cmp     byte ptr [rcx+29h], 6
0x14000ef49  jb      loc_14000EE6B
0x14000ef4f  mov     edx, 3Ah ; ':'
0x14000ef54  jmp     loc_14000EE5F
```
