# lldpGetRegistryKeyName

- ea: `0x140012500`
- end: `0x140012562`
- name: `lldpGetRegistryKeyName`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000f3b8`

## callees

- `0x140003cc0`
- `0x140004b00`
- `0x140012500`

## string_xrefs

- `0x140012512`: `Mslldp\Parameters\Agents\%s-%u`

## pseudocode

```c
char __fastcall lldpGetRegistryKeyName(__int64 a1, struct _UNICODE_STRING *a2)
{
  unsigned int v2; // eax

  v2 = RtlUnicodeStringPrintf(
         a2,
         L"Mslldp\\Parameters\\Agents\\%s-%u",
         *(_QWORD *)(a1 + 112),
         *(unsigned int *)(a1 + 132));
  if ( !v2 )
    return 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids, v2);
  return 0;
}

```

## disassembly

```asm
0x140012500  sub     rsp, 28h
0x140012504  mov     r9d, [rcx+84h]
0x14001250b  mov     rax, rdx
0x14001250e  mov     r8, [rcx+70h]
0x140012512  lea     rdx, aMslldpParamete_0; "Mslldp\\Parameters\\Agents\\%s-%u"
0x140012519  mov     rcx, rax; DestinationString
0x14001251c  call    RtlUnicodeStringPrintf
0x140012521  test    eax, eax
0x140012523  jz      short loc_14001255A
0x140012525  mov     rcx, cs:WPP_GLOBAL_Control
0x14001252c  lea     rdx, WPP_GLOBAL_Control
0x140012533  cmp     rcx, rdx
0x140012536  jz      short loc_140012556
0x140012538  cmp     byte ptr [rcx+29h], 2
0x14001253c  jb      short loc_140012556
0x14001253e  mov     rcx, [rcx+18h]
0x140012542  lea     r8, WPP_b3a834d394783de5fb279a081dc3c281_Traceguids
0x140012549  mov     edx, 12h
0x14001254e  mov     r9d, eax
0x140012551  call    WPP_SF_d
0x140012556  xor     al, al
0x140012558  jmp     short loc_14001255C
0x14001255a  mov     al, 1
0x14001255c  add     rsp, 28h
0x140012560  retn
```
