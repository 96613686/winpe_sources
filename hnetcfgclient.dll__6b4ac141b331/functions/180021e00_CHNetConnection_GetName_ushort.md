# CHNetConnection::GetName(ushort * *)

- ea: `0x180021e00`
- end: `0x180021ed9`
- name: `?GetName@CHNetConnection@@UEAAJPEAPEAG@Z`
- size: `217`
- prototype: `__int64 __fastcall(CHNetConnection *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001f26`
- `0x18000a45c`
- `0x18000a484`
- `0x180021e00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021e76`

## pseudocode

```c
__int64 __fastcall CHNetConnection::GetName(CHNetConnection *this, unsigned __int16 **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rax
  SIZE_T v7; // rdi
  unsigned __int16 *v8; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(*((_QWORD *)this + 3) + 2 * v6) );
    v7 = (unsigned int)(2 * v6 + 2);
    v8 = (unsigned __int16 *)CoTaskMemAlloc(v7);
    *a2 = v8;
    if ( v8 )
    {
      v5 = 0;
      memcpy_0(v8, *((const void **)this + 3), v7);
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
    WPP_SF_d(v4[2], 13, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180021e00  push    rbx
0x180021e02  push    rbp
0x180021e03  push    rsi
0x180021e04  push    rdi
0x180021e05  push    r14
0x180021e07  sub     rsp, 20h
0x180021e0b  mov     rbx, rdx
0x180021e0e  mov     rsi, rcx
0x180021e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e18  lea     r14, WPP_GLOBAL_Control
0x180021e1f  cmp     rcx, r14
0x180021e22  jz      short loc_180021E4C
0x180021e24  test    byte ptr [rcx+1Ch], 8
0x180021e28  jz      short loc_180021E4C
0x180021e2a  cmp     byte ptr [rcx+19h], 6
0x180021e2e  jb      short loc_180021E4C
0x180021e30  mov     rcx, [rcx+10h]
0x180021e34  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021e3b  mov     edx, 0Ch
0x180021e40  call    WPP_SF_
0x180021e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e4c  xor     ebp, ebp
0x180021e4e  test    rbx, rbx
0x180021e51  jnz     short loc_180021E5A
0x180021e53  mov     ebx, 80070057h
0x180021e58  jmp     short loc_180021EA3
0x180021e5a  mov     rcx, [rsi+18h]
0x180021e5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180021e62  inc     rax
0x180021e65  cmp     [rcx+rax*2], bp
0x180021e69  jnz     short loc_180021E62
0x180021e6b  lea     eax, ds:2[rax*2]
0x180021e72  mov     ecx, eax; cb
0x180021e74  mov     edi, eax
0x180021e76  call    cs:__imp_CoTaskMemAlloc
0x180021e7c  mov     [rbx], rax
0x180021e7f  test    rax, rax
0x180021e82  jnz     short loc_180021E8B
0x180021e84  mov     ebx, 8007000Eh
0x180021e89  jmp     short loc_180021E9C
0x180021e8b  mov     rdx, [rsi+18h]; Src
0x180021e8f  mov     r8, rdi; Size
0x180021e92  mov     rcx, rax; void *
0x180021e95  mov     ebx, ebp
0x180021e97  call    memcpy_0
0x180021e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ea3  cmp     rcx, r14
0x180021ea6  jz      short loc_180021ECC
0x180021ea8  test    byte ptr [rcx+1Ch], 8
0x180021eac  jz      short loc_180021ECC
0x180021eae  cmp     byte ptr [rcx+19h], 6
0x180021eb2  jb      short loc_180021ECC
0x180021eb4  mov     rcx, [rcx+10h]
0x180021eb8  lea     r8, WPP_a20c0b619e453d0f9fdea2b55603e62c_Traceguids
0x180021ebf  mov     edx, 0Dh
0x180021ec4  mov     r9d, ebx
0x180021ec7  call    WPP_SF_d
0x180021ecc  mov     eax, ebx
0x180021ece  add     rsp, 20h
0x180021ed2  pop     r14
0x180021ed4  pop     rdi
0x180021ed5  pop     rsi
0x180021ed6  pop     rbp
0x180021ed7  pop     rbx
0x180021ed8  retn
```
