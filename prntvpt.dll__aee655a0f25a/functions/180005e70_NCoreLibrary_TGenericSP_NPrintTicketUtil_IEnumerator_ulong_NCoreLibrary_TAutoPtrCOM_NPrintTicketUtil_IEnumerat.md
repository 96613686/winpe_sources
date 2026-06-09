# NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<ulong>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<ulong>>,NPrintTicketUtil::IEnumerator<ulong> *,0,NPrintTicketUtil::IEnumerator<ulong> const *>::Reset(void)

- ea: `0x180005e70`
- end: `0x180005e9a`
- name: `?Reset@?$TGenericSP@V?$IEnumerator@K@NPrintTicketUtil@@V?$TAutoPtrCOM@V?$IEnumerator@K@NPrintTicketUtil@@@NCoreLibrary@@PEAV12@$0A@PEBV12@@NCoreLibrary@@QEAAXXZ`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `94`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002c80`
- `0x1800034a4`
- `0x180005d78`
- `0x180005ea0`
- `0x180006130`
- `0x1800064a0`
- `0x180006b10`
- `0x1800077f0`
- `0x180007b9c`
- `0x180008848`
- `0x180009410`
- `0x180009da8`
- `0x18000a2e0`
- `0x18000b5a0`
- `0x18000ca58`
- `0x18000e03c`
- `0x18000e084`
- `0x18000e608`
- `0x18000ece0`
- `0x18000f13c`
- `0x1800121d0`
- `0x180013380`
- `0x180013420`
- `0x1800141b0`
- `0x180019050`
- `0x1800191a0`
- `0x180019300`
- `0x1800194e0`
- `0x180019b60`
- `0x180019c60`
- `0x180019db0`
- `0x180019eb0`
- `0x180019ff0`
- `0x18001a150`
- `0x18001a254`
- `0x18001a390`
- `0x18001a4cc`
- `0x18001a60c`
- `0x18001a73c`
- `0x18001b204`
- `0x18001b4b0`
- `0x18001b590`
- `0x18001b6f0`
- `0x18001b7b0`
- `0x18001b9f0`
- `0x18001bae0`
- `0x18001bbac`
- `0x18001beb8`
- `0x18001c060`
- `0x18001c2b0`

## callees

- `0x180005e70`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall NCoreLibrary::TGenericSP<NPrintTicketUtil::IEnumerator<unsigned long>,NCoreLibrary::TAutoPtrCOM<NPrintTicketUtil::IEnumerator<unsigned long>>,NPrintTicketUtil::IEnumerator<unsigned long> *,0,NPrintTicketUtil::IEnumerator<unsigned long> const *>::Reset(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005e70  push    rbx
0x180005e72  sub     rsp, 20h
0x180005e76  mov     rbx, rcx
0x180005e79  mov     rcx, [rcx]
0x180005e7c  test    rcx, rcx
0x180005e7f  jz      short loc_180005E94
0x180005e81  mov     rax, [rcx]
0x180005e84  mov     rax, [rax+10h]
0x180005e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e8d  mov     qword ptr [rbx], 0
0x180005e94  add     rsp, 20h
0x180005e98  pop     rbx
0x180005e99  retn
```
