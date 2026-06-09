# NatSplitAndHandlePackets

- ea: `0x14002bc7c`
- end: `0x14002bdfe`
- name: `NatSplitAndHandlePackets`
- size: `386`
- prototype: `__int64 __fastcall(NET_BUFFER_LIST *originalNetBufferList, int, IF_INDEX subInterfaceIndex, int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140029850`
- `0x140029e50`
- `0x14002a440`

## callees

- `0x1400021bc`
- `0x140028ea0`
- `0x14002bc7c`

## import_xrefs

- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14002bdc7`
- `fwpkclnt!FwpsFreeCloneNetBufferList0` at `0x14002bdc7`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x14002bcdd`
- `fwpkclnt!FwpsAllocateCloneNetBufferList0` at `0x14002bcdd`
- `fwpkclnt!FwpsInjectNetworkReceiveAsync0` at `0x14002bd75`
- `fwpkclnt!FwpsInjectNetworkReceiveAsync0` at `0x14002bd75`

## pseudocode

```c
__int64 __fastcall NatSplitAndHandlePackets(
        NET_BUFFER_LIST *originalNetBufferList,
        unsigned int a2,
        IF_INDEX subInterfaceIndex,
        unsigned int a4,
        char a5)
{
  PNET_BUFFER FirstNetBuffer; // rbp
  SLIST_HEADER *v10; // rdi
  SLIST_HEADER *Alignment; // rbx
  NTSTATUS v12; // eax
  __int64 v13; // r8
  HANDLE v14; // rcx
  NTSTATUS v15; // r9d
  NET_BUFFER_LIST *netBufferList; // [rsp+80h] [rbp+8h] BYREF

  FirstNetBuffer = originalNetBufferList->FirstNetBuffer;
  netBufferList = 0;
  v10 = (SLIST_HEADER *)FirstNetBuffer;
  if ( FirstNetBuffer )
  {
    while ( 1 )
    {
      Alignment = (SLIST_HEADER *)v10->Alignment;
      v10->Alignment = 0;
      originalNetBufferList->Link.Region = (ULONGLONG)v10;
      v12 = FwpsAllocateCloneNetBufferList0(originalNetBufferList, 0, 0, 0, &netBufferList);
      v10->Alignment = (ULONGLONG)Alignment;
      originalNetBufferList->Link.Region = (ULONGLONG)FirstNetBuffer;
      if ( v12 < 0 )
        return 1;
      LOBYTE(v13) = a5;
      if ( (unsigned int)NatShimTranslatePacket(a2, a4, v13, (__int64)netBufferList, 0, 0) != 3 )
        goto LABEL_9;
      v14 = gNetworkInjectionHandle;
      netBufferList->Flags |= 0x1000000u;
      v15 = FwpsInjectNetworkReceiveAsync0(
              v14,
              0,
              0,
              DEFAULT_COMPARTMENT_ID,
              a2,
              subInterfaceIndex,
              netBufferList,
              (FWPS_INJECT_COMPLETE0)NatInjectDatagramComplete,
              (HANDLE)1);
      if ( v15 )
        break;
LABEL_10:
      v10 = (SLIST_HEADER *)v10->Alignment;
      if ( !v10 )
        return 1;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        (__int64)WPP_c0a33d2a072834186a96c22b14f343de_Traceguids,
        v15);
    }
LABEL_9:
    FwpsFreeCloneNetBufferList0(netBufferList, 0);
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x14002bc7c  mov     rax, rsp
0x14002bc7f  mov     [rax+10h], rbx
0x14002bc83  mov     [rax+18h], rbp
0x14002bc87  push    rsi
0x14002bc88  push    rdi
0x14002bc89  push    r12
0x14002bc8b  push    r14
0x14002bc8d  push    r15
0x14002bc8f  sub     rsp, 50h
0x14002bc93  mov     rbp, [rcx+8]
0x14002bc97  mov     r15d, r9d
0x14002bc9a  mov     qword ptr [rax+8], 0
0x14002bca2  mov     r12d, r8d
0x14002bca5  mov     r14d, edx
0x14002bca8  mov     rsi, rcx
0x14002bcab  mov     rdi, rbp
0x14002bcae  test    rbp, rbp
0x14002bcb1  jz      loc_14002BDDF
0x14002bcb7  mov     rbx, [rdi]
0x14002bcba  lea     rax, [rsp+78h+arg_0]
0x14002bcc2  mov     qword ptr [rdi], 0
0x14002bcc9  xor     r9d, r9d; allocateCloneFlags
0x14002bccc  xor     r8d, r8d; netBufferPoolHandle
0x14002bccf  mov     [rsi+8], rdi
0x14002bcd3  xor     edx, edx; netBufferListPoolHandle
0x14002bcd5  mov     [rsp+78h+netBufferList], rax; netBufferList
0x14002bcda  mov     rcx, rsi; originalNetBufferList
0x14002bcdd  call    cs:__imp_FwpsAllocateCloneNetBufferList0
0x14002bce4  nop     dword ptr [rax+rax+00h]
0x14002bce9  mov     [rdi], rbx
0x14002bcec  mov     [rsi+8], rbp
0x14002bcf0  test    eax, eax
0x14002bcf2  js      loc_14002BDDF
0x14002bcf8  mov     r9, [rsp+78h+arg_0]; int
0x14002bd00  mov     edx, r15d; int
0x14002bd03  mov     r8b, byte ptr [rsp+78h+arg_20]; int
0x14002bd0b  mov     ecx, r14d; int
0x14002bd0e  mov     byte ptr [rsp+78h+subInterfaceIndex], 0; char
0x14002bd13  mov     dword ptr [rsp+78h+netBufferList], 0; DataOffsetDelta
0x14002bd1b  call    NatShimTranslatePacket
0x14002bd20  cmp     eax, 3
0x14002bd23  jnz     loc_14002BDBD
0x14002bd29  mov     rax, [rsp+78h+arg_0]
0x14002bd31  mov     ecx, 1
0x14002bd36  mov     [rsp+78h+completionContext], rcx; completionContext
0x14002bd3b  mov     r9d, ecx; compartmentId
0x14002bd3e  mov     rcx, cs:gNetworkInjectionHandle; injectionHandle
0x14002bd45  xor     r8d, r8d; flags
0x14002bd48  xor     edx, edx; injectionContext
0x14002bd4a  bts     dword ptr [rax+88h], 18h
0x14002bd52  lea     rax, NatInjectDatagramComplete
0x14002bd59  mov     [rsp+78h+completionFn], rax; completionFn
0x14002bd5e  mov     rax, [rsp+78h+arg_0]
0x14002bd66  mov     [rsp+78h+var_48], rax; netBufferList
0x14002bd6b  mov     [rsp+78h+subInterfaceIndex], r12d; subInterfaceIndex
0x14002bd70  mov     dword ptr [rsp+78h+netBufferList], r14d; interfaceIndex
0x14002bd75  call    cs:__imp_FwpsInjectNetworkReceiveAsync0
0x14002bd7c  nop     dword ptr [rax+rax+00h]
0x14002bd81  mov     r9d, eax
0x14002bd84  test    eax, eax
0x14002bd86  jz      short loc_14002BDD3
0x14002bd88  mov     rcx, cs:WPP_GLOBAL_Control
0x14002bd8f  lea     rax, WPP_GLOBAL_Control
0x14002bd96  cmp     rcx, rax
0x14002bd99  jz      short loc_14002BDBD
0x14002bd9b  mov     eax, [rcx+2Ch]
0x14002bd9e  test    al, 2
0x14002bda0  jz      short loc_14002BDBD
0x14002bda2  cmp     byte ptr [rcx+29h], 2
0x14002bda6  jb      short loc_14002BDBD
0x14002bda8  mov     rcx, [rcx+18h]
0x14002bdac  lea     r8, WPP_c0a33d2a072834186a96c22b14f343de_Traceguids
0x14002bdb3  mov     edx, 0Ah
0x14002bdb8  call    WPP_SF_d
0x14002bdbd  mov     rcx, [rsp+78h+arg_0]; netBufferList
0x14002bdc5  xor     edx, edx; freeCloneFlags
0x14002bdc7  call    cs:__imp_FwpsFreeCloneNetBufferList0
0x14002bdce  nop     dword ptr [rax+rax+00h]
0x14002bdd3  mov     rdi, [rdi]
0x14002bdd6  test    rdi, rdi
0x14002bdd9  jnz     loc_14002BCB7
0x14002bddf  lea     r11, [rsp+78h+var_28]
0x14002bde4  mov     eax, 1
0x14002bde9  mov     rbx, [r11+38h]
0x14002bded  mov     rbp, [r11+40h]
0x14002bdf1  mov     rsp, r11
0x14002bdf4  pop     r15
0x14002bdf6  pop     r14
0x14002bdf8  pop     r12
0x14002bdfa  pop     rdi
0x14002bdfb  pop     rsi
0x14002bdfc  retn
```
