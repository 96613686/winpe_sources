# CreateDhcpv6TransactionId

- ea: `0x18000e7dc`
- end: `0x18000e840`
- name: `CreateDhcpv6TransactionId`
- size: `100`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008a70`
- `0x180008f80`
- `0x180014070`
- `0x180014590`
- `0x180016f8c`
- `0x180020d50`
- `0x180021150`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`

## callees

- `0x18000e7dc`

## import_xrefs

- `ntdll!RtlRandomEx` at `0x18000e832`
- `ntdll!RtlRandomEx` at `0x18000e832`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e81d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000e81d`
- `CRYPTBASE!SystemFunction036` at `0x18000e7f7`
- `CRYPTBASE!SystemFunction036` at `0x18000e7f7`

## pseudocode

```c
char __fastcall CreateDhcpv6TransactionId(__int64 a1)
{
  char result; // al
  ULONG RandomBuffer; // [rsp+30h] [rbp+8h] BYREF

  RandomBuffer = 0;
  if ( !SystemFunction036(&RandomBuffer, 4u) )
  {
    RandomBuffer = GetTickCount();
    RtlRandomEx(&RandomBuffer);
  }
  *(_WORD *)a1 = RandomBuffer;
  result = BYTE2(RandomBuffer);
  *(_BYTE *)(a1 + 2) = BYTE2(RandomBuffer);
  return result;
}

```

## disassembly

```asm
0x18000e7dc  push    rbx
0x18000e7de  sub     rsp, 20h
0x18000e7e2  mov     rbx, rcx
0x18000e7e5  mov     [rsp+28h+RandomBuffer], 0
0x18000e7ed  lea     rcx, [rsp+28h+RandomBuffer]; RandomBuffer
0x18000e7f2  mov     edx, 4; RandomBufferLength
0x18000e7f7  call    cs:__imp_SystemFunction036
0x18000e7fe  nop     dword ptr [rax+rax+00h]
0x18000e803  test    al, al
0x18000e805  jz      short loc_18000E81D
0x18000e807  movzx   eax, word ptr [rsp+28h+RandomBuffer]
0x18000e80c  mov     [rbx], ax
0x18000e80f  mov     al, byte ptr [rsp+28h+RandomBuffer+2]
0x18000e813  mov     [rbx+2], al
0x18000e816  add     rsp, 20h
0x18000e81a  pop     rbx
0x18000e81b  retn
0x18000e81d  call    cs:__imp_GetTickCount
0x18000e824  nop     dword ptr [rax+rax+00h]
0x18000e829  lea     rcx, [rsp+28h+RandomBuffer]; Seed
0x18000e82e  mov     [rsp+28h+RandomBuffer], eax
0x18000e832  call    cs:__imp_RtlRandomEx
0x18000e839  nop     dword ptr [rax+rax+00h]
0x18000e83e  jmp     short loc_18000E807
```
