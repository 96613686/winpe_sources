# ClasspInitializeCommandDurationLimitPerCommand

- ea: `0x1400316d4`
- end: `0x1400317ad`
- name: `ClasspInitializeCommandDurationLimitPerCommand`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140031634`

## callees

- `0x14001fbf4`
- `0x140030fac`
- `0x1400316d4`
- `0x140033110`
- `0x140033780`

## pseudocode

```c
__int64 __fastcall ClasspInitializeCommandDurationLimitPerCommand(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  int CommandDurationLimitModePage; // edi
  char v4; // dl
  __int64 v5; // rcx
  __int64 DurationLimitCommandInfo; // rbx
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx

  CommandDurationLimitModePage = 0;
  DurationLimitCommandInfo = ClasspGetDurationLimitCommandInfo(a1, a2);
  if ( (*(_WORD *)DurationLimitCommandInfo & 2) == 0 )
  {
    if ( (*(_WORD *)DurationLimitCommandInfo & 1) != 0
      || (CommandDurationLimitModePage = ClasspQueryCommandDurationLimitSupportAndModePage(v5, v4),
          CommandDurationLimitModePage >= 0) )
    {
      if ( (*(_BYTE *)DurationLimitCommandInfo & 1) != 0 )
      {
        *(_DWORD *)(DurationLimitCommandInfo + 2) = 117901063;
        *(_WORD *)(DurationLimitCommandInfo + 6) = 1799;
        *(_BYTE *)(DurationLimitCommandInfo + 8) = 7;
        CommandDurationLimitModePage = ClasspQueryCommandDurationLimitModePage(a1, (_BYTE *)DurationLimitCommandInfo);
        if ( CommandDurationLimitModePage >= 0 )
        {
          *(_WORD *)DurationLimitCommandInfo |= 2u;
          return (unsigned int)CommandDurationLimitModePage;
        }
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v8 = 173;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v8 = 172;
LABEL_8:
        WPP_SF_d(
          v7->AttachedDevice,
          v8,
          WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids,
          (unsigned int)CommandDurationLimitModePage);
      }
    }
  }
  return (unsigned int)CommandDurationLimitModePage;
}

```

## disassembly

```asm
0x1400316d4  mov     [rsp+arg_0], rbx
0x1400316d9  mov     [rsp+arg_8], rsi
0x1400316de  push    rdi
0x1400316df  sub     rsp, 20h
0x1400316e3  mov     rsi, rcx
0x1400316e6  xor     edi, edi
0x1400316e8  call    ClasspGetDurationLimitCommandInfo
0x1400316ed  mov     rbx, rax
0x1400316f0  movzx   eax, word ptr [rax]
0x1400316f3  test    al, 2
0x1400316f5  jnz     loc_14003179A
0x1400316fb  test    al, 1
0x1400316fd  jnz     short loc_140031745
0x1400316ff  call    ClasspQueryCommandDurationLimitSupportAndModePage
0x140031704  mov     edi, eax
0x140031706  test    eax, eax
0x140031708  jns     short loc_140031745
0x14003170a  mov     rcx, cs:WPP_GLOBAL_Control
0x140031711  lea     rax, WPP_GLOBAL_Control
0x140031718  cmp     rcx, rax
0x14003171b  jz      short loc_14003179A
0x14003171d  mov     edx, [rcx+2Ch]
0x140031720  test    dl, 10h
0x140031723  jz      short loc_14003179A
0x140031725  cmp     byte ptr [rcx+29h], 2
0x140031729  jb      short loc_14003179A
0x14003172b  mov     edx, 0ACh
0x140031730  mov     rcx, [rcx+18h]
0x140031734  lea     r8, WPP_5c962fffc5b3379cf98f2f4c24865c79_Traceguids
0x14003173b  mov     r9d, edi
0x14003173e  call    WPP_SF_d
0x140031743  jmp     short loc_14003179A
0x140031745  test    byte ptr [rbx], 1
0x140031748  jz      short loc_14003179A
0x14003174a  mov     rax, 707070707070707h
0x140031754  mov     rdx, rbx
0x140031757  mov     [rbx+2], eax
0x14003175a  mov     rcx, rsi
0x14003175d  mov     [rbx+6], ax
0x140031761  mov     [rbx+8], al
0x140031764  call    ClasspQueryCommandDurationLimitModePage
0x140031769  mov     edi, eax
0x14003176b  test    eax, eax
0x14003176d  jns     short loc_140031796
0x14003176f  mov     rcx, cs:WPP_GLOBAL_Control
0x140031776  lea     rax, WPP_GLOBAL_Control
0x14003177d  cmp     rcx, rax
0x140031780  jz      short loc_14003179A
0x140031782  mov     eax, [rcx+2Ch]
0x140031785  test    al, 10h
0x140031787  jz      short loc_14003179A
0x140031789  cmp     byte ptr [rcx+29h], 2
0x14003178d  jb      short loc_14003179A
0x14003178f  mov     edx, 0ADh
0x140031794  jmp     short loc_140031730
0x140031796  or      word ptr [rbx], 2
0x14003179a  mov     rbx, [rsp+28h+arg_0]
0x14003179f  mov     eax, edi
0x1400317a1  mov     rsi, [rsp+28h+arg_8]
0x1400317a6  add     rsp, 20h
0x1400317aa  pop     rdi
0x1400317ab  retn
```
