# CHNetConnection::GetProperties(tagHNET_CONN_PROPERTIES * *)

- ea: `0x180021ee0`
- end: `0x180021f99`
- name: `?GetProperties@CHNetConnection@@UEAAJPEAPEAUtagHNET_CONN_PROPERTIES@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(CHNetConnection *__hidden this, struct tagHNET_CONN_PROPERTIES **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180021ee0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021f3a`

## pseudocode

```c
__int64 __fastcall CHNetConnection::GetProperties(CHNetConnection *this, struct tagHNET_CONN_PROPERTIES **a2)
{
  PVOID *v4; // rcx
  struct tagHNET_CONN_PROPERTIES *v5; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v5 = (struct tagHNET_CONN_PROPERTIES *)CoTaskMemAlloc(0xCu);
    *a2 = v5;
    if ( v5 )
    {
      *(_QWORD *)v5 = *((_QWORD *)this + 4);
      *((_DWORD *)v5 + 2) = *((_DWORD *)this + 10);
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 19, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180021ee0  mov     [rsp+arg_0], rbx
0x180021ee5  mov     [rsp+arg_8], rsi
0x180021eea  push    rdi
0x180021eeb  sub     rsp, 20h
0x180021eef  mov     rbx, rdx
0x180021ef2  mov     rdi, rcx
0x180021ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021efc  lea     rsi, WPP_GLOBAL_Control
0x180021f03  cmp     rcx, rsi
0x180021f06  jz      short loc_180021F30
0x180021f08  test    byte ptr [rcx+1Ch], 8
0x180021f0c  jz      short loc_180021F30
0x180021f0e  cmp     byte ptr [rcx+19h], 6
0x180021f12  jb      short loc_180021F30
0x180021f14  mov     rcx, [rcx+10h]
0x180021f18  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021f1f  mov     edx, 12h
0x180021f24  call    WPP_SF_
0x180021f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f30  test    rbx, rbx
0x180021f33  jz      short loc_180021F5E
0x180021f35  mov     ecx, 0Ch; cb
0x180021f3a  call    cs:__imp_CoTaskMemAlloc
0x180021f40  mov     [rbx], rax
0x180021f43  test    rax, rax
0x180021f46  jz      short loc_180021F57
0x180021f48  movsd   xmm0, qword ptr [rdi+20h]
0x180021f4d  movsd   qword ptr [rax], xmm0
0x180021f51  mov     ecx, [rdi+28h]
0x180021f54  mov     [rax+8], ecx
0x180021f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f5e  cmp     rcx, rsi
0x180021f61  jz      short loc_180021F87
0x180021f63  test    byte ptr [rcx+1Ch], 8
0x180021f67  jz      short loc_180021F87
0x180021f69  cmp     byte ptr [rcx+19h], 6
0x180021f6d  jb      short loc_180021F87
0x180021f6f  mov     rcx, [rcx+10h]
0x180021f73  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021f7a  mov     edx, 13h
0x180021f7f  xor     r9d, r9d
0x180021f82  call    WPP_SF_d
0x180021f87  mov     rbx, [rsp+28h+arg_0]
0x180021f8c  xor     eax, eax
0x180021f8e  mov     rsi, [rsp+28h+arg_8]
0x180021f93  add     rsp, 20h
0x180021f97  pop     rdi
0x180021f98  retn
```
