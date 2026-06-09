# PublicNetworkListManager::ClearIpHlpEventQueueNoLock(void)

- ea: `0x180020048`
- end: `0x18002010b`
- name: `?ClearIpHlpEventQueueNoLock@PublicNetworkListManager@@QEAAXXZ`
- size: `195`
- prototype: `void __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a294`

## callees

- `0x180006770`
- `0x18000c650`
- `0x180020048`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800200cc`

## pseudocode

```c
void __fastcall PublicNetworkListManager::ClearIpHlpEventQueueNoLock(PublicNetworkListManager *this)
{
  __int64 v2; // r8
  __int64 *v3; // rcx
  __int64 v4; // rdx
  void *v5; // rbx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  while ( 1 )
  {
    v2 = *((_QWORD *)this + 95);
    if ( !v2 )
      break;
    v3 = (__int64 *)**((_QWORD **)this + 94);
    v4 = *v3;
    v5 = (void *)v3[2];
    *((_QWORD *)this + 95) = v2 - 1;
    *(_QWORD *)v3[1] = v4;
    *(_QWORD *)(v4 + 8) = v3[1];
    std::_Deallocate<16>(v3, 0x18u);
    CoTaskMemFree(v5);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
}

```

## disassembly

```asm
0x180020048  mov     [rsp+arg_8], rbx
0x18002004d  mov     [rsp+arg_10], rsi
0x180020052  push    rdi
0x180020053  sub     rsp, 20h
0x180020057  mov     rdi, rcx
0x18002005a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020061  lea     rsi, WPP_GLOBAL_Control
0x180020068  cmp     rcx, rsi
0x18002006b  jz      short loc_180020088
0x18002006d  test    byte ptr [rcx+1Ch], 8
0x180020071  jz      short loc_180020088
0x180020073  mov     rcx, [rcx+10h]
0x180020077  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x18002007e  mov     edx, 0DCh
0x180020083  call    WPP_SF_
0x180020088  mov     r8, [rdi+2F8h]
0x18002008f  test    r8, r8
0x180020092  jz      short loc_1800200D4
0x180020094  mov     rax, [rdi+2F0h]
0x18002009b  mov     rcx, [rax]
0x18002009e  lea     rax, [r8-1]
0x1800200a2  mov     rdx, [rcx]
0x1800200a5  mov     rbx, [rcx+10h]
0x1800200a9  mov     [rdi+2F8h], rax
0x1800200b0  mov     rax, [rcx+8]
0x1800200b4  mov     [rax], rdx
0x1800200b7  mov     rax, [rcx+8]
0x1800200bb  mov     [rdx+8], rax
0x1800200bf  mov     edx, 18h
0x1800200c4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800200c9  mov     rcx, rbx; pv
0x1800200cc  call    cs:__imp_CoTaskMemFree
0x1800200d2  jmp     short loc_180020088
0x1800200d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200db  cmp     rcx, rsi
0x1800200de  jz      short loc_1800200FB
0x1800200e0  test    byte ptr [rcx+1Ch], 8
0x1800200e4  jz      short loc_1800200FB
0x1800200e6  mov     rcx, [rcx+10h]
0x1800200ea  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800200f1  mov     edx, 0DDh
0x1800200f6  call    WPP_SF_
0x1800200fb  mov     rbx, [rsp+28h+arg_8]
0x180020100  mov     rsi, [rsp+28h+arg_10]
0x180020105  add     rsp, 20h
0x180020109  pop     rdi
0x18002010a  retn
```
