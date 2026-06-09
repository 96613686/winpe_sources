# GetNetProviderName(tagICNRLINKW const * const,ushort *)

- ea: `0x1800047fc`
- end: `0x180004837`
- name: `?GetNetProviderName@@YAHQEBUtagICNRLINKW@@PEAG@Z`
- size: `59`
- prototype: `__int64 __fastcall(const struct tagICNRLINKW *const, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800044f0`

## callees

- `0x1800047fc`

## import_xrefs

- `MPR!WNetGetProviderNameW` at `0x18000481a`
- `MPR!WNetGetProviderNameW` at `0x18000481a`

## pseudocode

```c
__int64 __fastcall GetNetProviderName(const struct tagICNRLINKW *const a1, unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  DWORD v3; // ecx
  DWORD BufferSize; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  if ( (*((_BYTE *)a1 + 4) & 2) != 0 )
  {
    v3 = *((_DWORD *)a1 + 4);
    BufferSize = 260;
    return WNetGetProviderNameW(v3, a2, &BufferSize) == 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800047fc  push    rbx
0x1800047fe  sub     rsp, 20h
0x180004802  xor     ebx, ebx
0x180004804  test    byte ptr [rcx+4], 2
0x180004808  jz      short loc_18000482E
0x18000480a  mov     ecx, [rcx+10h]; dwNetType
0x18000480d  lea     r8, [rsp+28h+BufferSize]; lpBufferSize
0x180004812  mov     [rsp+28h+BufferSize], 104h
0x18000481a  call    cs:__imp_WNetGetProviderNameW
0x180004821  nop     dword ptr [rax+rax+00h]
0x180004826  test    eax, eax
0x180004828  lea     ecx, [rbx+1]
0x18000482b  cmovz   ebx, ecx
0x18000482e  mov     eax, ebx
0x180004830  add     rsp, 20h
0x180004834  pop     rbx
0x180004835  retn
```
