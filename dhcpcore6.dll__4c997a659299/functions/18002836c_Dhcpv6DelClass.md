# Dhcpv6DelClass

- ea: `0x18002836c`
- end: `0x18002840a`
- name: `Dhcpv6DelClass`
- size: `158`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x180005bcc`
- `0x180005e8c`
- `0x18000bb2c`
- `0x18000bc88`
- `0x18000c264`
- `0x180018864`
- `0x1800192e4`
- `0x180027c3c`
- `0x180029818`
- `0x180029fe4`

## callees

- `0x18000c740`
- `0x18002836c`
- `0x180028698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028383`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028383`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800283f0`

## pseudocode

```c
__int64 __fastcall Dhcpv6DelClass(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v5; // rcx
  _DWORD *Class; // rax
  _DWORD *v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // rax
  _QWORD *v11; // rdx
  LPVOID v13; // [rsp+48h] [rbp+20h] BYREF

  EnterCriticalSection(&Dhcpv6GlobalOptionsListCritSect);
  if ( a3 && a2 && (Class = (_DWORD *)Dhcpv6FindClass(v5, a2, a3), v13 = Class, (v7 = Class) != 0) )
  {
    v8 = 0;
    if ( Class[7]-- == 1 )
    {
      v10 = *(_QWORD *)Class;
      if ( *(_DWORD **)(v10 + 8) != v7 || (v11 = (_QWORD *)*((_QWORD *)v7 + 1), (_DWORD *)*v11 != v7) )
        __fastfail(3u);
      *v11 = v10;
      *(_QWORD *)(v10 + 8) = v11;
      DhcpFree(&v13);
    }
  }
  else
  {
    v8 = 87;
  }
  LeaveCriticalSection(&Dhcpv6GlobalOptionsListCritSect);
  return v8;
}

```

## disassembly

```asm
0x18002836c  mov     [rsp+arg_8], rbx
0x180028371  push    rdi
0x180028372  sub     rsp, 20h
0x180028376  lea     rcx, Dhcpv6GlobalOptionsListCritSect; lpCriticalSection
0x18002837d  mov     edi, r8d
0x180028380  mov     rbx, rdx
0x180028383  call    cs:__imp_EnterCriticalSection
0x18002838a  nop     dword ptr [rax+rax+00h]
0x18002838f  test    edi, edi
0x180028391  jz      short loc_1800283E4
0x180028393  test    rbx, rbx
0x180028396  jz      short loc_1800283E4
0x180028398  mov     r8d, edi
0x18002839b  mov     rdx, rbx
0x18002839e  call    Dhcpv6FindClass
0x1800283a3  mov     [rsp+28h+arg_18], rax
0x1800283a8  mov     rcx, rax
0x1800283ab  test    rax, rax
0x1800283ae  jz      short loc_1800283E4
0x1800283b0  xor     ebx, ebx
0x1800283b2  add     dword ptr [rax+1Ch], 0FFFFFFFFh
0x1800283b6  jnz     short loc_1800283E9
0x1800283b8  mov     rax, [rax]
0x1800283bb  cmp     [rax+8], rcx
0x1800283bf  jnz     short loc_1800283DD
0x1800283c1  mov     rdx, [rcx+8]
0x1800283c5  cmp     [rdx], rcx
0x1800283c8  jnz     short loc_1800283DD
0x1800283ca  mov     [rdx], rax
0x1800283cd  lea     rcx, [rsp+28h+arg_18]
0x1800283d2  mov     [rax+8], rdx
0x1800283d6  call    DhcpFree
0x1800283db  jmp     short loc_1800283E9
0x1800283dd  mov     ecx, 3
0x1800283e2  int     29h; Win8: RtlFailFast(ecx)
0x1800283e4  mov     ebx, 57h ; 'W'
0x1800283e9  lea     rcx, Dhcpv6GlobalOptionsListCritSect; lpCriticalSection
0x1800283f0  call    cs:__imp_LeaveCriticalSection
0x1800283f7  nop     dword ptr [rax+rax+00h]
0x1800283fc  mov     eax, ebx
0x1800283fe  mov     rbx, [rsp+28h+arg_8]
0x180028403  add     rsp, 20h
0x180028407  pop     rdi
0x180028408  retn
```
