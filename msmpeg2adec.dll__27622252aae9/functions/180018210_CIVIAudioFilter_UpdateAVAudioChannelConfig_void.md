# CIVIAudioFilter::UpdateAVAudioChannelConfig(void)

- ea: `0x180018210`
- end: `0x1800183a8`
- name: `?UpdateAVAudioChannelConfig@CIVIAudioFilter@@AEAAXXZ`
- size: `408`
- prototype: `void __fastcall(CIVIAudioFilter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000d580`

## callees

- `0x180018210`

## pseudocode

```c
void __fastcall CIVIAudioFilter::UpdateAVAudioChannelConfig(CIVIAudioFilter *this)
{
  int v1; // eax
  int v2; // eax

  v1 = *((_DWORD *)this + 1613);
  switch ( v1 )
  {
    case 3:
      switch ( *((_DWORD *)this + 1484) )
      {
        case 0:
        case 2:
          goto LABEL_11;
        case 1:
          goto LABEL_3;
        case 3:
          goto LABEL_4;
        case 4:
          goto LABEL_5;
        case 5:
          goto LABEL_6;
        case 6:
          goto LABEL_7;
        case 7:
          goto LABEL_14;
        default:
          goto LABEL_27;
      }
    case 5:
      if ( *((_DWORD *)this + 1620) == 1 )
      {
LABEL_3:
        *((_DWORD *)this + 1637) = 4;
        goto LABEL_29;
      }
      if ( *((_DWORD *)this + 1620) == 2 )
      {
LABEL_11:
        *((_DWORD *)this + 1637) = 3;
        goto LABEL_29;
      }
      goto LABEL_27;
    case 4:
      switch ( *(_DWORD *)(*((_QWORD *)this + 809) + 135620LL) )
      {
        case 0:
          goto LABEL_3;
        case 1:
        case 2:
          goto LABEL_11;
        case 3:
          goto LABEL_5;
        case 4:
          goto LABEL_7;
        case 5:
        case 6:
          goto LABEL_4;
        case 7:
          goto LABEL_6;
        case 8:
          goto LABEL_14;
        default:
          goto LABEL_27;
      }
  }
  if ( v1 != 6 )
  {
    if ( v1 == 9 )
    {
      switch ( *((_DWORD *)this + 1668) )
      {
        case 1:
          v2 = 4 - (*((_DWORD *)this + 1670) != 0);
          break;
        case 2:
        case 0xA:
          v2 = 3;
          break;
        case 3:
          v2 = 7;
          break;
        case 4:
          v2 = 263;
          break;
        case 5:
          v2 = 55;
          break;
        case 6:
          v2 = 63;
          break;
        case 8:
          v2 = 259;
          break;
        case 9:
          v2 = 51;
          break;
        default:
          goto LABEL_27;
      }
      goto LABEL_28;
    }
LABEL_27:
    v2 = 0;
LABEL_28:
    *((_DWORD *)this + 1637) = v2;
    goto LABEL_29;
  }
  switch ( *((_DWORD *)this + 1492) )
  {
    case 0:
      goto LABEL_3;
    case 1:
    case 2:
    case 3:
    case 4:
      goto LABEL_11;
    case 5:
LABEL_4:
      *((_DWORD *)this + 1637) = 7;
      break;
    case 6:
LABEL_5:
      *((_DWORD *)this + 1637) = 259;
      break;
    case 7:
LABEL_6:
      *((_DWORD *)this + 1637) = 263;
      break;
    case 8:
LABEL_7:
      *((_DWORD *)this + 1637) = 1539;
      break;
    case 9:
LABEL_14:
      *((_DWORD *)this + 1637) = 1543;
      break;
    default:
      goto LABEL_27;
  }
LABEL_29:
  if ( *((_DWORD *)this + 1621) )
    *((_DWORD *)this + 1637) |= 8u;
}

```

## disassembly

```asm
0x180018210  mov     eax, [rcx+1934h]
0x180018216  cmp     eax, 3
0x180018219  jnz     short loc_18001828D
0x18001821b  movsxd  rax, dword ptr [rcx+1730h]
0x180018222  cmp     eax, 7; switch 8 cases
0x180018225  ja      def_18001823C; jumptable 000000018001823C default case
0x18001822b  lea     rdx, __ImageBase
0x180018232  mov     eax, ds:(jpt_18001823C - 180000000h)[rdx+rax*4]
0x180018239  add     rax, rdx
0x18001823c  jmp     rax; switch jump
0x180018242  mov     dword ptr [rcx+1994h], 4; jumptable 000000018001823C case 1
0x18001824c  jmp     loc_180018397
0x180018251  mov     dword ptr [rcx+1994h], 7; jumptable 000000018001823C case 3
0x18001825b  jmp     loc_180018397
0x180018260  mov     dword ptr [rcx+1994h], 103h; jumptable 000000018001823C case 4
0x18001826a  jmp     loc_180018397
0x18001826f  mov     dword ptr [rcx+1994h], 107h; jumptable 000000018001823C case 5
0x180018279  jmp     loc_180018397
0x18001827e  mov     dword ptr [rcx+1994h], 603h; jumptable 000000018001823C case 6
0x180018288  jmp     loc_180018397
0x18001828d  cmp     eax, 5
0x180018290  jnz     short loc_1800182B5
0x180018292  mov     edx, [rcx+1950h]
0x180018298  sub     edx, 1
0x18001829b  jz      short loc_180018242; jumptable 000000018001823C case 1
0x18001829d  cmp     edx, 1
0x1800182a0  jnz     def_18001823C; jumptable 000000018001823C default case
0x1800182a6  mov     dword ptr [rcx+1994h], 3; jumptable 000000018001823C cases 0,2
0x1800182b0  jmp     loc_180018397
0x1800182b5  cmp     eax, 4
0x1800182b8  jnz     short loc_1800182FA
0x1800182ba  mov     rax, [rcx+1948h]
0x1800182c1  movsxd  rdx, dword ptr [rax+211C4h]
0x1800182c8  cmp     edx, 8; switch 9 cases
0x1800182cb  ja      def_18001823C; jumptable 000000018001823C default case
0x1800182d1  mov     rax, rdx
0x1800182d4  lea     rdx, __ImageBase
0x1800182db  mov     eax, ds:(jpt_1800182E5 - 180000000h)[rdx+rax*4]
0x1800182e2  add     rax, rdx
0x1800182e5  jmp     rax; switch jump
0x1800182eb  mov     dword ptr [rcx+1994h], 607h; jumptable 000000018001823C case 7
0x1800182f5  jmp     loc_180018397
0x1800182fa  cmp     eax, 6
0x1800182fd  jnz     short loc_180018326
0x1800182ff  movsxd  rax, dword ptr [rcx+1750h]
0x180018306  cmp     eax, 9; switch 10 cases
0x180018309  ja      def_18001823C; jumptable 000000018001823C default case
0x18001830f  lea     rdx, __ImageBase
0x180018316  mov     eax, ds:(jpt_180018320 - 180000000h)[rdx+rax*4]
0x18001831d  add     rax, rdx
0x180018320  jmp     rax; switch jump
0x180018326  cmp     eax, 9
0x180018329  jnz     short def_18001823C; jumptable 000000018001823C default case
0x18001832b  mov     eax, [rcx+1A10h]
0x180018331  dec     eax; switch 10 cases
0x180018333  cmp     eax, 9
0x180018336  ja      short def_18001823C; jumptable 000000018001823C default case
0x180018338  lea     rdx, __ImageBase
0x18001833f  mov     eax, ds:(jpt_180018349 - 180000000h)[rdx+rax*4]
0x180018346  add     rax, rdx
0x180018349  jmp     rax; switch jump
0x18001834f  mov     eax, [rcx+1A18h]; jumptable 0000000180018349 case 1
0x180018355  neg     eax
0x180018357  sbb     eax, eax
0x180018359  add     eax, 4
0x18001835c  jmp     short loc_180018391
0x18001835e  mov     eax, 3; jumptable 0000000180018349 cases 2,10
0x180018363  jmp     short loc_180018391
0x180018365  mov     eax, 7; jumptable 0000000180018349 case 3
0x18001836a  jmp     short loc_180018391
0x18001836c  mov     eax, 107h; jumptable 0000000180018349 case 4
0x180018371  jmp     short loc_180018391
0x180018373  mov     eax, 37h ; '7'; jumptable 0000000180018349 case 5
0x180018378  jmp     short loc_180018391
0x18001837a  mov     eax, 3Fh ; '?'; jumptable 0000000180018349 case 6
0x18001837f  jmp     short loc_180018391
0x180018381  mov     eax, 103h; jumptable 0000000180018349 case 8
0x180018386  jmp     short loc_180018391
0x180018388  mov     eax, 33h ; '3'; jumptable 0000000180018349 case 9
0x18001838d  jmp     short loc_180018391
0x18001838f  xor     eax, eax; jumptable 000000018001823C default case
0x180018391  mov     [rcx+1994h], eax
0x180018397  cmp     dword ptr [rcx+1954h], 0
0x18001839e  jz      short locret_1800183A7
0x1800183a0  or      dword ptr [rcx+1994h], 8
0x1800183a7  retn
```
