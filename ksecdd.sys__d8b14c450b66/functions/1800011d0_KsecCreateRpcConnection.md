# KsecCreateRpcConnection

- ea: `0x1800011d0`
- end: `0x180001228`
- name: `KsecCreateRpcConnection`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006bf4`

## callees

- `0x1800011d0`
- `0x180001230`
- `0x18001f310`
- `0x180020e20`

## pseudocode

```c
__int64 __fastcall KsecCreateRpcConnection(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  int v5; // ebx
  void *v6; // [rsp+30h] [rbp-18h] BYREF

  v6 = 0;
  result = CreateRpcConnection(a1, 1, (__int64)&v6, a3, a4);
  if ( (int)result >= 0 )
  {
    v5 = KsecpAddRpcConnection(v6);
    if ( v5 < 0 )
    {
      DisconnectRpcConnection(v6);
      if ( v5 == -1073741771 )
        return 0;
    }
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800011d0  push    rbx
0x1800011d2  sub     rsp, 40h
0x1800011d6  mov     [rsp+48h+var_28], r9
0x1800011db  mov     edx, 1
0x1800011e0  mov     r9, r8
0x1800011e3  mov     [rsp+48h+var_18], 0
0x1800011ec  lea     r8, [rsp+48h+var_18]
0x1800011f1  call    CreateRpcConnection
0x1800011f6  test    eax, eax
0x1800011f8  js      short loc_180001221
0x1800011fa  mov     rcx, [rsp+48h+var_18]; void *
0x1800011ff  call    ?KsecpAddRpcConnection@@YAJPEAX@Z; KsecpAddRpcConnection(void *)
0x180001204  mov     ebx, eax
0x180001206  test    eax, eax
0x180001208  jns     short loc_18000121F
0x18000120a  mov     rcx, [rsp+48h+var_18]
0x18000120f  call    DisconnectRpcConnection
0x180001214  xor     ecx, ecx
0x180001216  cmp     ebx, 0C0000035h
0x18000121c  cmovz   ebx, ecx
0x18000121f  mov     eax, ebx
0x180001221  add     rsp, 40h
0x180001225  pop     rbx
0x180001226  retn
```
