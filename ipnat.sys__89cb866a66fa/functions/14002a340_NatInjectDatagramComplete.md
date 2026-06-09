# NatInjectDatagramComplete

- ea: `0x14002a340`
- end: `0x14002a42c`
- name: `NatInjectDatagramComplete`
- size: `236`
- prototype: `void __stdcall(void *context, NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14002a340`

## import_xrefs

- `fwpkclnt!FwpsFreeNetBufferList0` at `0x14002a3e1`
- `fwpkclnt!FwpsFreeNetBufferList0` at `0x14002a3e1`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14002a3d3`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14002a3d3`

## pseudocode

```c
void __fastcall NatInjectDatagramComplete(void *context, NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)
{
  char v4; // di
  __int64 NdisReserved2; // r9

  v4 = (char)context;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
  }
  if ( netBufferList )
  {
    NdisReserved2 = netBufferList->NdisReserved2;
    if ( (_DWORD)NdisReserved2
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, NdisReserved2);
    }
    if ( v4 )
      FwpsFreeCloneNetBufferList0(netBufferList, 0);
    else
      FwpsFreeNetBufferList0(netBufferList);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
  }
}

```

## disassembly

```asm
0x14002a340  mov     [rsp+arg_0], rbx
0x14002a345  mov     [rsp+arg_8], rbp
0x14002a34a  push    rdi
0x14002a34b  sub     rsp, 20h
0x14002a34f  mov     rbx, rdx
0x14002a352  mov     rdi, rcx
0x14002a355  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a35c  lea     rbp, WPP_GLOBAL_Control
0x14002a363  cmp     rcx, rbp
0x14002a366  jz      short loc_14002A38A
0x14002a368  mov     eax, [rcx+2Ch]
0x14002a36b  test    al, 2
0x14002a36d  jz      short loc_14002A38A
0x14002a36f  cmp     byte ptr [rcx+29h], 6
0x14002a373  jb      short loc_14002A38A
0x14002a375  mov     rcx, [rcx+18h]
0x14002a379  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002a380  mov     edx, 7Ah ; 'z'
0x14002a385  call    WPP_SF_
0x14002a38a  test    rbx, rbx
0x14002a38d  jz      short loc_14002A3ED
0x14002a38f  mov     r9d, [rbx+8Ch]
0x14002a396  test    r9d, r9d
0x14002a399  jz      short loc_14002A3C9
0x14002a39b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a3a2  cmp     rcx, rbp
0x14002a3a5  jz      short loc_14002A3C9
0x14002a3a7  mov     eax, [rcx+2Ch]
0x14002a3aa  test    al, 2
0x14002a3ac  jz      short loc_14002A3C9
0x14002a3ae  cmp     byte ptr [rcx+29h], 2
0x14002a3b2  jb      short loc_14002A3C9
0x14002a3b4  mov     rcx, [rcx+18h]
0x14002a3b8  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002a3bf  mov     edx, 7Bh ; '{'
0x14002a3c4  call    WPP_SF_d
0x14002a3c9  mov     rcx, rbx; netBufferList
0x14002a3cc  test    dil, dil
0x14002a3cf  jz      short loc_14002A3E1
0x14002a3d1  xor     edx, edx; freeCloneFlags
0x14002a3d3  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x14002a3da  nop     dword ptr [rax+rax+00h]
0x14002a3df  jmp     short loc_14002A3ED
0x14002a3e1  call    cs:__imp_FwpsFreeNetBufferList0
0x14002a3e8  nop     dword ptr [rax+rax+00h]
0x14002a3ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a3f4  cmp     rcx, rbp
0x14002a3f7  jz      short loc_14002A41B
0x14002a3f9  mov     eax, [rcx+2Ch]
0x14002a3fc  test    al, 1
0x14002a3fe  jz      short loc_14002A41B
0x14002a400  cmp     byte ptr [rcx+29h], 6
0x14002a404  jb      short loc_14002A41B
0x14002a406  mov     rcx, [rcx+18h]
0x14002a40a  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002a411  mov     edx, 7Ch ; '|'
0x14002a416  call    WPP_SF_
0x14002a41b  mov     rbx, [rsp+28h+arg_0]
0x14002a420  mov     rbp, [rsp+28h+arg_8]
0x14002a425  add     rsp, 20h
0x14002a429  pop     rdi
0x14002a42a  retn
```
