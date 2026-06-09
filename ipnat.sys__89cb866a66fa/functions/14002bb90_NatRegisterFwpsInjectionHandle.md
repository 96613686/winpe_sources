# NatRegisterFwpsInjectionHandle

- ea: `0x14002bb90`
- end: `0x14002bc75`
- name: `NatRegisterFwpsInjectionHandle`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002adb0`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x14002bb90`

## import_xrefs

- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x14002bbe5`
- `fwpkclnt!FwpsInjectionHandleCreate0` at `0x14002bbe5`

## pseudocode

```c
__int64 NatRegisterFwpsInjectionHandle()
{
  unsigned int v0; // ebx
  HANDLE injectionHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids);
  }
  injectionHandle = (HANDLE)-1LL;
  v0 = FwpsInjectionHandleCreate0(2u, 4u, &injectionHandle);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v0);
  }
  else
  {
    gNetworkInjectionHandle = injectionHandle;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids, v0);
  }
  return v0;
}

```

## disassembly

```asm
0x14002bb90  mov     [rsp+arg_8], rbx
0x14002bb95  push    rsi
0x14002bb96  sub     rsp, 20h
0x14002bb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bba1  lea     rsi, WPP_GLOBAL_Control
0x14002bba8  cmp     rcx, rsi
0x14002bbab  jz      short loc_14002BBCF
0x14002bbad  mov     eax, [rcx+2Ch]
0x14002bbb0  test    al, 2
0x14002bbb2  jz      short loc_14002BBCF
0x14002bbb4  cmp     byte ptr [rcx+29h], 6
0x14002bbb8  jb      short loc_14002BBCF
0x14002bbba  mov     rcx, [rcx+18h]
0x14002bbbe  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002bbc5  mov     edx, 75h ; 'u'
0x14002bbca  call    WPP_SF_
0x14002bbcf  mov     ecx, 2; addressFamily
0x14002bbd4  mov     [rsp+28h+injectionHandle], 0FFFFFFFFFFFFFFFFh
0x14002bbdd  lea     r8, [rsp+28h+injectionHandle]; injectionHandle
0x14002bbe2  lea     edx, [rcx+2]; flags
0x14002bbe5  call    cs:__imp_FwpsInjectionHandleCreate0
0x14002bbec  nop     dword ptr [rax+rax+00h]
0x14002bbf1  mov     ebx, eax
0x14002bbf3  test    eax, eax
0x14002bbf5  jnz     short loc_14002BC05
0x14002bbf7  mov     rcx, [rsp+28h+injectionHandle]
0x14002bbfc  mov     cs:gNetworkInjectionHandle, rcx
0x14002bc03  jmp     short loc_14002BC36
0x14002bc05  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc0c  cmp     rcx, rsi
0x14002bc0f  jz      short loc_14002BC67
0x14002bc11  mov     eax, [rcx+2Ch]
0x14002bc14  test    al, 2
0x14002bc16  jz      short loc_14002BC36
0x14002bc18  cmp     byte ptr [rcx+29h], 2
0x14002bc1c  jb      short loc_14002BC36
0x14002bc1e  mov     rcx, [rcx+18h]
0x14002bc22  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002bc29  mov     edx, 76h ; 'v'
0x14002bc2e  mov     r9d, ebx
0x14002bc31  call    WPP_SF_d
0x14002bc36  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bc3d  cmp     rcx, rsi
0x14002bc40  jz      short loc_14002BC67
0x14002bc42  mov     eax, [rcx+2Ch]
0x14002bc45  test    al, 2
0x14002bc47  jz      short loc_14002BC67
0x14002bc49  cmp     byte ptr [rcx+29h], 6
0x14002bc4d  jb      short loc_14002BC67
0x14002bc4f  mov     rcx, [rcx+18h]
0x14002bc53  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002bc5a  mov     edx, 77h ; 'w'
0x14002bc5f  mov     r9d, ebx
0x14002bc62  call    WPP_SF_d
0x14002bc67  mov     eax, ebx
0x14002bc69  mov     rbx, [rsp+28h+arg_8]
0x14002bc6e  add     rsp, 20h
0x14002bc72  pop     rsi
0x14002bc73  retn
```
