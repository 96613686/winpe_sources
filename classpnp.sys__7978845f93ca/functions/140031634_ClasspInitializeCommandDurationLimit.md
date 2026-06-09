# ClasspInitializeCommandDurationLimit

- ea: `0x140031634`
- end: `0x1400316cc`
- name: `ClasspInitializeCommandDurationLimit`
- size: `152`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140033924`
- `0x140033d94`
- `0x1400340b4`
- `0x140034e08`
- `0x140035128`
- `0x140035764`

## callees

- `0x14001fbf4`
- `0x140031634`
- `0x1400316d4`

## pseudocode

```c
__int64 __fastcall ClasspInitializeCommandDurationLimit(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  int v4; // ebx
  PDEVICE_OBJECT v5; // rcx
  __int64 v6; // rdx

  LOBYTE(a2) = -120;
  v4 = ClasspInitializeCommandDurationLimitPerCommand(a1, a2);
  if ( v4 >= 0 )
  {
    LOBYTE(v3) = -118;
    v4 = ClasspInitializeCommandDurationLimitPerCommand(a1, v3);
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v6 = 175;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v6 = 174;
LABEL_11:
      WPP_SF_d(v5->AttachedDevice, v6, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids, (unsigned int)v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140031634  mov     [rsp+arg_0], rbx
0x140031639  push    rdi
0x14003163a  sub     rsp, 20h
0x14003163e  mov     dl, 88h
0x140031640  mov     rdi, rcx
0x140031643  call    ClasspInitializeCommandDurationLimitPerCommand
0x140031648  mov     ebx, eax
0x14003164a  test    eax, eax
0x14003164c  jns     short loc_140031676
0x14003164e  mov     rcx, cs:WPP_GLOBAL_Control
0x140031655  lea     rax, WPP_GLOBAL_Control
0x14003165c  cmp     rcx, rax
0x14003165f  jz      short loc_1400316BE
0x140031661  mov     edx, [rcx+2Ch]
0x140031664  test    dl, 10h
0x140031667  jz      short loc_1400316BE
0x140031669  cmp     byte ptr [rcx+29h], 2
0x14003166d  jb      short loc_1400316BE
0x14003166f  mov     edx, 0AEh
0x140031674  jmp     short loc_1400316AB
0x140031676  mov     dl, 8Ah
0x140031678  mov     rcx, rdi
0x14003167b  call    ClasspInitializeCommandDurationLimitPerCommand
0x140031680  mov     ebx, eax
0x140031682  test    eax, eax
0x140031684  jns     short loc_1400316BE
0x140031686  mov     rcx, cs:WPP_GLOBAL_Control
0x14003168d  lea     rax, WPP_GLOBAL_Control
0x140031694  cmp     rcx, rax
0x140031697  jz      short loc_1400316BE
0x140031699  mov     eax, [rcx+2Ch]
0x14003169c  test    al, 10h
0x14003169e  jz      short loc_1400316BE
0x1400316a0  cmp     byte ptr [rcx+29h], 2
0x1400316a4  jb      short loc_1400316BE
0x1400316a6  mov     edx, 0AFh
0x1400316ab  mov     rcx, [rcx+18h]
0x1400316af  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x1400316b6  mov     r9d, ebx
0x1400316b9  call    WPP_SF_d
0x1400316be  mov     eax, ebx
0x1400316c0  mov     rbx, [rsp+28h+arg_0]
0x1400316c5  add     rsp, 20h
0x1400316c9  pop     rdi
0x1400316ca  retn
```
