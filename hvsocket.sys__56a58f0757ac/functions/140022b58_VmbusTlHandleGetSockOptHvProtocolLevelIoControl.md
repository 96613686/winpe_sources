# VmbusTlHandleGetSockOptHvProtocolLevelIoControl

- ea: `0x140022b58`
- end: `0x140022ccf`
- name: `VmbusTlHandleGetSockOptHvProtocolLevelIoControl`
- size: `375`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022cd8`

## callees

- `0x14000975c`
- `0x140022b58`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022c5e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022c5e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022c52`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022c52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022bce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022c1e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022bce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022c1e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022bde`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022c2e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022bde`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022c2e`

## string_xrefs

- `0x140022b96`: `VmbusTlHandleGetSockOptHvProtocolLevelIoControl`

## pseudocode

```c
__int64 __fastcall VmbusTlHandleGetSockOptHvProtocolLevelIoControl(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // edx
  unsigned int v6; // edi
  __int64 v7; // rdx
  const char *v8; // rcx
  bool v9; // zf

  v4 = *(_DWORD *)(a2 + 24) - 1;
  if ( !v4 )
  {
    if ( *(_QWORD *)(a2 + 56) >= 4u )
    {
      v6 = 0;
      **(_DWORD **)(a2 + 48) = *(_QWORD *)(a1 + 176) / -10000LL;
      return v6;
    }
    v6 = -1073741811;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v7 = 139;
      v8 = "VmbusTlHandleGetSockOptConnectTimeout";
      goto LABEL_18;
    }
    return v6;
  }
  v5 = v4 - 3;
  if ( !v5 )
  {
    if ( *(_QWORD *)(a2 + 56) != 4 )
    {
      v6 = -1073741811;
      if ( (unsigned int)dword_140013058 > 2 )
      {
        v7 = 352;
        v8 = "VmbusTlHandleGetSockOptConnectedSuspend";
        goto LABEL_18;
      }
      return v6;
    }
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v6 = 0;
    v9 = *(_BYTE *)(a1 + 185) == 0;
LABEL_14:
    **(_DWORD **)(a2 + 48) = !v9;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    KeLeaveCriticalRegion();
    return v6;
  }
  if ( v5 != 4 )
  {
    v6 = -1073741808;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v7 = 261;
      v8 = "VmbusTlHandleGetSockOptHvProtocolLevelIoControl";
LABEL_18:
      HvsocketTraceEndpointError(v8, v7, v6, a1);
      return v6;
    }
    return v6;
  }
  if ( *(_QWORD *)(a2 + 56) == 4 )
  {
    KeEnterCriticalRegion();
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
    v6 = 0;
    v9 = *(_BYTE *)(a1 + 186) == 0;
    goto LABEL_14;
  }
  v6 = -1073741811;
  if ( (unsigned int)dword_140013058 > 2 )
  {
    v7 = 725;
    v8 = "VmbusTlHandleGetSockOptHighVtl";
    goto LABEL_18;
  }
  return v6;
}

```

## disassembly

```asm
0x140022b58  push    rbx
0x140022b5a  push    rbp
0x140022b5b  push    rsi
0x140022b5c  push    rdi
0x140022b5d  sub     rsp, 28h
0x140022b61  mov     rsi, rdx
0x140022b64  mov     rbp, rcx
0x140022b67  mov     edx, [rdx+18h]
0x140022b6a  sub     edx, 1
0x140022b6d  jz      loc_140022C6C
0x140022b73  sub     edx, 3
0x140022b76  jz      short loc_140022BF5
0x140022b78  cmp     edx, 4
0x140022b7b  jz      short loc_140022BA2
0x140022b7d  mov     eax, cs:dword_140013058
0x140022b83  mov     edi, 0C0000010h
0x140022b88  cmp     eax, 2
0x140022b8b  jbe     loc_140022CC3
0x140022b91  mov     edx, 105h
0x140022b96  lea     rcx, aVmbustlhandleg_0; "VmbusTlHandleGetSockOptHvProtocolLevelI"...
0x140022b9d  jmp     loc_140022C8F
0x140022ba2  cmp     qword ptr [rsi+38h], 4
0x140022ba7  jz      short loc_140022BCE
0x140022ba9  mov     eax, cs:dword_140013058
0x140022baf  mov     edi, 0C000000Dh
0x140022bb4  cmp     eax, 2
0x140022bb7  jbe     loc_140022CC3
0x140022bbd  mov     edx, 2D5h
0x140022bc2  lea     rcx, aVmbustlhandleg_4; "VmbusTlHandleGetSockOptHighVtl"
0x140022bc9  jmp     loc_140022C8F
0x140022bce  call    cs:__imp_KeEnterCriticalRegion
0x140022bd5  nop     dword ptr [rax+rax+00h]
0x140022bda  lea     rcx, [rbp+10h]; FastMutex
0x140022bde  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022be5  nop     dword ptr [rax+rax+00h]
0x140022bea  xor     edi, edi
0x140022bec  cmp     [rbp+0BAh], dil
0x140022bf3  jmp     short loc_140022C43
0x140022bf5  cmp     qword ptr [rsi+38h], 4
0x140022bfa  jz      short loc_140022C1E
0x140022bfc  mov     eax, cs:dword_140013058
0x140022c02  mov     edi, 0C000000Dh
0x140022c07  cmp     eax, 2
0x140022c0a  jbe     loc_140022CC3
0x140022c10  mov     edx, 160h
0x140022c15  lea     rcx, aVmbustlhandleg_2; "VmbusTlHandleGetSockOptConnectedSuspend"
0x140022c1c  jmp     short loc_140022C8F
0x140022c1e  call    cs:__imp_KeEnterCriticalRegion
0x140022c25  nop     dword ptr [rax+rax+00h]
0x140022c2a  lea     rcx, [rbp+10h]; FastMutex
0x140022c2e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022c35  nop     dword ptr [rax+rax+00h]
0x140022c3a  xor     edi, edi
0x140022c3c  cmp     [rbp+0B9h], dil
0x140022c43  mov     rax, [rsi+30h]
0x140022c47  lea     rcx, [rbp+10h]; FastMutex
0x140022c4b  mov     edx, edi
0x140022c4d  setnz   dl
0x140022c50  mov     [rax], edx
0x140022c52  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022c59  nop     dword ptr [rax+rax+00h]
0x140022c5e  call    cs:__imp_KeLeaveCriticalRegion
0x140022c65  nop     dword ptr [rax+rax+00h]
0x140022c6a  jmp     short loc_140022CC3
0x140022c6c  cmp     qword ptr [rsi+38h], 4
0x140022c71  jnb     short loc_140022C9C
0x140022c73  mov     eax, cs:dword_140013058
0x140022c79  mov     edi, 0C000000Dh
0x140022c7e  cmp     eax, 2
0x140022c81  jbe     short loc_140022CC3
0x140022c83  mov     edx, 8Bh
0x140022c88  lea     rcx, aVmbustlhandleg_3; "VmbusTlHandleGetSockOptConnectTimeout"
0x140022c8f  mov     r8d, edi
0x140022c92  mov     r9, rbp
0x140022c95  call    HvsocketTraceEndpointError
0x140022c9a  jmp     short loc_140022CC3
0x140022c9c  mov     rax, 0CB923A29C779A6B5h
0x140022ca6  imul    qword ptr [rcx+0B0h]
0x140022cad  sar     rdx, 0Bh
0x140022cb1  mov     rax, rdx
0x140022cb4  shr     rax, 3Fh
0x140022cb8  add     rdx, rax
0x140022cbb  mov     rax, [rsi+30h]
0x140022cbf  xor     edi, edi
0x140022cc1  mov     [rax], edx
0x140022cc3  mov     eax, edi
0x140022cc5  add     rsp, 28h
0x140022cc9  pop     rdi
0x140022cca  pop     rsi
0x140022ccb  pop     rbp
0x140022ccc  pop     rbx
0x140022ccd  retn
```
