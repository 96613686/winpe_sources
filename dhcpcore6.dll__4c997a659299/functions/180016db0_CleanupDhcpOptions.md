# CleanupDhcpOptions

- ea: `0x180016db0`
- end: `0x180016e99`
- name: `CleanupDhcpOptions`
- size: `233`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x1800034c8`
- `0x180003cc0`
- `0x180008a70`
- `0x180008f80`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x180021b58`
- `0x1800225c8`

## callees

- `0x18000c740`
- `0x180016db0`
- `0x180016ea0`
- `0x180016ed0`
- `0x180016f14`
- `0x180016f48`

## pseudocode

```c
__int64 __fastcall CleanupDhcpOptions(__int64 a1)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax

  if ( g_fVelocityDhcpv6ParserFreeCleanup )
  {
    FreeOptionIana();
    FreeOptionIata(a1);
    FreeOptionIapd(a1);
    *(_DWORD *)(a1 + 144) = 0;
    DhcpFree(a1 + 152);
    return FreeOptionVendorOpts(a1);
  }
  else
  {
    *(_DWORD *)(a1 + 48) = 0;
    v3 = *(_QWORD *)(a1 + 80);
    if ( v3 )
      DhcpFree(v3);
    DhcpFree(a1 + 80);
    v4 = *(_QWORD *)(a1 + 88);
    *(_DWORD *)(a1 + 52) = 0;
    if ( v4 )
      DhcpFree(v4);
    DhcpFree(a1 + 88);
    v5 = *(_QWORD *)(a1 + 96);
    if ( v5 )
    {
      *(_DWORD *)(v5 + 4) = 0;
      DhcpFree(*(_QWORD *)(a1 + 96) + 24LL);
    }
    DhcpFree(a1 + 96);
    *(_DWORD *)(a1 + 144) = 0;
    DhcpFree(a1 + 152);
    *(_DWORD *)(a1 + 180) = 0;
    return DhcpFree(a1 + 184);
  }
}

```

## disassembly

```asm
0x180016db0  mov     [rsp+arg_0], rbx
0x180016db5  push    rdi
0x180016db6  sub     rsp, 20h
0x180016dba  cmp     cs:g_fVelocityDhcpv6ParserFreeCleanup, 0
0x180016dc1  mov     rbx, rcx
0x180016dc4  jz      short loc_180016DFE
0x180016dc6  call    FreeOptionIana
0x180016dcb  mov     rcx, rbx
0x180016dce  call    FreeOptionIata
0x180016dd3  mov     rcx, rbx
0x180016dd6  call    FreeOptionIapd
0x180016ddb  lea     rcx, [rbx+98h]
0x180016de2  mov     dword ptr [rbx+90h], 0
0x180016dec  call    DhcpFree
0x180016df1  mov     rcx, rbx
0x180016df4  call    FreeOptionVendorOpts
0x180016df9  jmp     loc_180016E8D
0x180016dfe  mov     dword ptr [rcx+30h], 0
0x180016e05  mov     rcx, [rcx+50h]
0x180016e09  test    rcx, rcx
0x180016e0c  jz      short loc_180016E13
0x180016e0e  call    DhcpFree
0x180016e13  lea     rcx, [rbx+50h]
0x180016e17  call    DhcpFree
0x180016e1c  mov     rcx, [rbx+58h]
0x180016e20  mov     dword ptr [rbx+34h], 0
0x180016e27  test    rcx, rcx
0x180016e2a  jz      short loc_180016E31
0x180016e2c  call    DhcpFree
0x180016e31  lea     rcx, [rbx+58h]
0x180016e35  call    DhcpFree
0x180016e3a  lea     rdi, [rbx+60h]
0x180016e3e  mov     rax, [rdi]
0x180016e41  test    rax, rax
0x180016e44  jz      short loc_180016E59
0x180016e46  mov     dword ptr [rax+4], 0
0x180016e4d  mov     rcx, [rdi]
0x180016e50  add     rcx, 18h
0x180016e54  call    DhcpFree
0x180016e59  mov     rcx, rdi
0x180016e5c  call    DhcpFree
0x180016e61  lea     rcx, [rbx+98h]
0x180016e68  mov     dword ptr [rbx+90h], 0
0x180016e72  call    DhcpFree
0x180016e77  lea     rcx, [rbx+0B8h]
0x180016e7e  mov     dword ptr [rbx+0B4h], 0
0x180016e88  call    DhcpFree
0x180016e8d  mov     rbx, [rsp+28h+arg_0]
0x180016e92  add     rsp, 20h
0x180016e96  pop     rdi
0x180016e97  retn
```
