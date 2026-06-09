# lldpNmrQueryConfig

- ea: `0x14000f0b0`
- end: `0x14000f117`
- name: `lldpNmrQueryConfig`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140004a60`
- `0x140005084`
- `0x14000e614`
- `0x14000f0b0`

## pseudocode

```c
__int64 __fastcall lldpNmrQueryConfig(_DWORD *a1)
{
  _DWORD *v1; // rax
  __int64 v2; // rdx

  v1 = lldpOpenPortFromHandle(a1);
  if ( !v1 )
    return 3221225480LL;
  if ( *(_DWORD *)v2 == 1 && *(_QWORD *)(v2 + 8) >= 0x2Cu )
  {
    lldpGetPortAdminConfig(*((_QWORD *)v1 + 3), v2);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_7b2e41ea31413e6a6d3bdbc4c714aeb2_Traceguids);
    return 3221225560LL;
  }
}

```

## disassembly

```asm
0x14000f0b0  sub     rsp, 28h
0x14000f0b4  call    lldpOpenPortFromHandle
0x14000f0b9  test    rax, rax
0x14000f0bc  jnz     short loc_14000F0C5
0x14000f0be  mov     eax, 0C0000008h
0x14000f0c3  jmp     short loc_14000F111
0x14000f0c5  cmp     dword ptr [rdx], 1
0x14000f0c8  jnz     short loc_14000F0DE
0x14000f0ca  cmp     qword ptr [rdx+8], 2Ch ; ','
0x14000f0cf  jb      short loc_14000F0DE
0x14000f0d1  mov     rcx, [rax+18h]
0x14000f0d5  call    lldpGetPortAdminConfig
0x14000f0da  xor     eax, eax
0x14000f0dc  jmp     short loc_14000F111
0x14000f0de  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f0e5  lea     rax, WPP_GLOBAL_Control
0x14000f0ec  cmp     rcx, rax
0x14000f0ef  jz      short loc_14000F10C
0x14000f0f1  cmp     byte ptr [rcx+29h], 2
0x14000f0f5  jb      short loc_14000F10C
0x14000f0f7  mov     rcx, [rcx+18h]
0x14000f0fb  lea     r8, WPP_7b2e41ea31413e6a6d3bdbc4c714aeb2_Traceguids
0x14000f102  mov     edx, 0Ah
0x14000f107  call    WPP_SF_
0x14000f10c  mov     eax, 0C0000058h
0x14000f111  add     rsp, 28h
0x14000f115  retn
```
