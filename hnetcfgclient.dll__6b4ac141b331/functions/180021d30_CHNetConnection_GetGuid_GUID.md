# CHNetConnection::GetGuid(_GUID * *)

- ea: `0x180021d30`
- end: `0x180021df2`
- name: `?GetGuid@CHNetConnection@@UEAAJPEAPEAU_GUID@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(CHNetConnection *__hidden this, struct _GUID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x180021d30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021d91`

## pseudocode

```c
__int64 __fastcall CHNetConnection::GetGuid(CHNetConnection *this, struct _GUID **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  struct _GUID *v6; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = (struct _GUID *)CoTaskMemAlloc(0x10u);
    *a2 = v6;
    if ( v6 )
    {
      v5 = 0;
      *v6 = *(struct _GUID *)((char *)this + 8);
    }
    else
    {
      v5 = -2147024882;
    }
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 11, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180021d30  mov     [rsp+arg_0], rbx
0x180021d35  mov     [rsp+arg_8], rsi
0x180021d3a  push    rdi
0x180021d3b  sub     rsp, 20h
0x180021d3f  mov     rbx, rdx
0x180021d42  mov     rdi, rcx
0x180021d45  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d4c  lea     rsi, WPP_GLOBAL_Control
0x180021d53  cmp     rcx, rsi
0x180021d56  jz      short loc_180021D80
0x180021d58  test    byte ptr [rcx+1Ch], 8
0x180021d5c  jz      short loc_180021D80
0x180021d5e  cmp     byte ptr [rcx+19h], 6
0x180021d62  jb      short loc_180021D80
0x180021d64  mov     rcx, [rcx+10h]
0x180021d68  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021d6f  mov     edx, 0Ah
0x180021d74  call    WPP_SF_
0x180021d79  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d80  test    rbx, rbx
0x180021d83  jnz     short loc_180021D8C
0x180021d85  mov     ebx, 80070057h
0x180021d8a  jmp     short loc_180021DB7
0x180021d8c  mov     ecx, 10h; cb
0x180021d91  call    cs:__imp_CoTaskMemAlloc
0x180021d97  mov     [rbx], rax
0x180021d9a  test    rax, rax
0x180021d9d  jnz     short loc_180021DA6
0x180021d9f  mov     ebx, 8007000Eh
0x180021da4  jmp     short loc_180021DB0
0x180021da6  movups  xmm0, xmmword ptr [rdi+8]
0x180021daa  xor     ebx, ebx
0x180021dac  movdqu  xmmword ptr [rax], xmm0
0x180021db0  mov     rcx, cs:WPP_GLOBAL_Control
0x180021db7  cmp     rcx, rsi
0x180021dba  jz      short loc_180021DE0
0x180021dbc  test    byte ptr [rcx+1Ch], 8
0x180021dc0  jz      short loc_180021DE0
0x180021dc2  cmp     byte ptr [rcx+19h], 6
0x180021dc6  jb      short loc_180021DE0
0x180021dc8  mov     rcx, [rcx+10h]
0x180021dcc  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021dd3  mov     edx, 0Bh
0x180021dd8  mov     r9d, ebx
0x180021ddb  call    WPP_SF_d
0x180021de0  mov     rsi, [rsp+28h+arg_8]
0x180021de5  mov     eax, ebx
0x180021de7  mov     rbx, [rsp+28h+arg_0]
0x180021dec  add     rsp, 20h
0x180021df0  pop     rdi
0x180021df1  retn
```
