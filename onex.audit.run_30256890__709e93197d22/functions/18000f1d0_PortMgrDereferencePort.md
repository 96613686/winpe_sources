# PortMgrDereferencePort

- ea: `0x18000f1d0`
- end: `0x18000f281`
- name: `PortMgrDereferencePort`
- size: `177`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d310`
- `0x18001e824`

## callees

- `0x18000f1d0`
- `0x180023640`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18000f250`
- `MobileNetworking!ReleaseWriteLock` at `0x18000f250`
- `MobileNetworking!AcquireWriteLock` at `0x18000f211`
- `MobileNetworking!AcquireWriteLock` at `0x18000f211`
- `MobileNetworking!FreeMemory` at `0x18000f26f`
- `MobileNetworking!FreeMemory` at `0x18000f26f`

## pseudocode

```c
__int64 __fastcall PortMgrDereferencePort(__int64 a1)
{
  __int64 result; // rax
  __int64 v2; // r9
  _QWORD *v3; // r8
  _QWORD *v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = (_QWORD *)a1;
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    PortMgrDeInitPort(v4);
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 595);
    v2 = *v4;
    if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v3 = (_QWORD *)v4[1], (_QWORD *)*v3 != v4) )
      __fastfail(3u);
    *v3 = v2;
    *(_QWORD *)(v2 + 8) = v3;
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrDereferencePort", 597);
    _InterlockedDecrement((_DWORD *)&qword_18003DD8C + 1);
    return FreeMemory(&v4, "PortMgrDereferencePort", 601);
  }
  return result;
}

```

## disassembly

```asm
0x18000f1d0  mov     [rsp+arg_0], rcx
0x18000f1d5  sub     rsp, 28h
0x18000f1d9  mov     eax, 0FFFFFFFFh
0x18000f1de  lock xadd [rcx+10h], eax
0x18000f1e3  cmp     eax, 1
0x18000f1e6  jnz     loc_18000F275
0x18000f1ec  mov     rcx, [rsp+28h+arg_0]
0x18000f1f1  call    PortMgrDeInitPort
0x18000f1f6  mov     r9d, 253h
0x18000f1fc  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000f203  lea     rdx, qword_18003DD98
0x18000f20a  lea     rcx, g_OneXInfo
0x18000f211  call    cs:__imp_AcquireWriteLock
0x18000f217  mov     rax, [rsp+28h+arg_0]
0x18000f21c  mov     r9, [rax]
0x18000f21f  cmp     [r9+8], rax
0x18000f223  jnz     short loc_18000F27A
0x18000f225  mov     r8, [rax+8]
0x18000f229  cmp     [r8], rax
0x18000f22c  jnz     short loc_18000F27A
0x18000f22e  mov     [r8], r9
0x18000f231  lea     rdx, qword_18003DD98
0x18000f238  mov     [r9+8], r8
0x18000f23c  lea     rcx, g_OneXInfo
0x18000f243  mov     r9d, 255h
0x18000f249  lea     r8, aPortmgrderefer; "PortMgrDereferencePort"
0x18000f250  call    cs:__imp_ReleaseWriteLock
0x18000f256  lock dec dword ptr cs:qword_18003DD8C+4
0x18000f25d  lea     rdx, aPortmgrderefer; "PortMgrDereferencePort"
0x18000f264  mov     r8d, 259h
0x18000f26a  lea     rcx, [rsp+28h+arg_0]
0x18000f26f  call    cs:__imp_FreeMemory
0x18000f275  add     rsp, 28h
0x18000f279  retn
0x18000f27a  mov     ecx, 3
0x18000f27f  int     29h; Win8: RtlFailFast(ecx)
```
