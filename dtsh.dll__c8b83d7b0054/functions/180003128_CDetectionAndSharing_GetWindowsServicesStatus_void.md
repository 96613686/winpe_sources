# CDetectionAndSharing::GetWindowsServicesStatus(void)

- ea: `0x180003128`
- end: `0x180003207`
- name: `?GetWindowsServicesStatus@CDetectionAndSharing@@AEAAJXZ`
- size: `223`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800025c8`
- `0x180002b64`

## callees

- `0x1800025a0`
- `0x180002fc4`
- `0x180003128`

## pseudocode

```c
__int64 __fastcall CDetectionAndSharing::GetWindowsServicesStatus(CDetectionAndSharing *this)
{
  unsigned int v1; // ebp
  __int64 v3; // rsi
  __int64 v4; // rax
  unsigned int v6; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  if ( *((_QWORD *)this + 11) )
  {
    while ( 1 )
    {
      if ( (unsigned __int64)v1 >= *((_QWORD *)this + 11)
        || (v3 = 32LL * v1,
            *(_DWORD *)(v3 + *((_QWORD *)this + 10) + 20) = 0,
            (unsigned __int64)v1 >= *((_QWORD *)this + 11))
        || (v4 = *((_QWORD *)this + 10),
            v6 = 0,
            v7 = 0,
            *(_DWORD *)(v4 + v3 + 24) = 0,
            (unsigned __int64)v1 >= *((_QWORD *)this + 11)) )
      {
LABEL_14:
        ATL::AtlThrowImpl(-2147024809);
      }
      if ( (int)CDetectionAndSharing::GetServiceInfo(
                  (SC_HANDLE *)this,
                  *(const unsigned __int16 **)(*((_QWORD *)this + 10) + 32LL * v1),
                  &v6,
                  &v7) < 0 )
        goto LABEL_12;
      if ( v6 == 3 )
        break;
      if ( v7 == 4 )
        goto LABEL_10;
LABEL_12:
      if ( (unsigned __int64)++v1 >= *((_QWORD *)this + 11) )
        return 0;
    }
    if ( (unsigned __int64)v1 >= *((_QWORD *)this + 11) )
      goto LABEL_14;
    *(_DWORD *)(*((_QWORD *)this + 10) + v3 + 20) = 1;
LABEL_10:
    if ( (unsigned __int64)v1 >= *((_QWORD *)this + 11) )
      goto LABEL_14;
    *(_DWORD *)(*((_QWORD *)this + 10) + v3 + 24) = 1;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180003128  mov     [rsp+arg_10], rbx
0x18000312d  push    rbp
0x18000312e  push    rsi
0x18000312f  push    rdi
0x180003130  sub     rsp, 20h
0x180003134  xor     ebp, ebp
0x180003136  mov     rbx, rcx
0x180003139  cmp     [rcx+58h], rbp
0x18000313d  jbe     loc_1800031ED
0x180003143  mov     edi, ebp
0x180003145  cmp     rdi, [rbx+58h]
0x180003149  jnb     loc_1800031FC
0x18000314f  mov     rax, [rbx+50h]
0x180003153  mov     esi, edi
0x180003155  shl     rsi, 5
0x180003159  mov     dword ptr [rsi+rax+14h], 0
0x180003161  cmp     rdi, [rbx+58h]
0x180003165  jnb     loc_1800031FC
0x18000316b  mov     rax, [rbx+50h]
0x18000316f  mov     [rsp+38h+arg_0], 0
0x180003177  mov     [rsp+38h+arg_8], 0
0x18000317f  mov     dword ptr [rax+rsi+18h], 0
0x180003187  cmp     rdi, [rbx+58h]
0x18000318b  jnb     short loc_1800031FC
0x18000318d  mov     rdx, [rbx+50h]
0x180003191  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x180003196  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18000319b  mov     rcx, rbx; this
0x18000319e  mov     rdx, [rdx+rsi]; unsigned __int16 *
0x1800031a2  call    ?GetServiceInfo@CDetectionAndSharing@@AEAAJPEBGPEAK1@Z; CDetectionAndSharing::GetServiceInfo(ushort const *,ulong *,ulong *)
0x1800031a7  test    eax, eax
0x1800031a9  js      short loc_1800031DF
0x1800031ab  cmp     [rsp+38h+arg_0], 3
0x1800031b0  jnz     short loc_1800031C6
0x1800031b2  cmp     rdi, [rbx+58h]
0x1800031b6  jnb     short loc_1800031FC
0x1800031b8  mov     rax, [rbx+50h]
0x1800031bc  mov     dword ptr [rax+rsi+14h], 1
0x1800031c4  jmp     short loc_1800031CD
0x1800031c6  cmp     [rsp+38h+arg_8], 4
0x1800031cb  jnz     short loc_1800031DF
0x1800031cd  cmp     rdi, [rbx+58h]
0x1800031d1  jnb     short loc_1800031FC
0x1800031d3  mov     rax, [rbx+50h]
0x1800031d7  mov     dword ptr [rax+rsi+18h], 1
0x1800031df  inc     ebp
0x1800031e1  mov     eax, ebp
0x1800031e3  cmp     rax, [rbx+58h]
0x1800031e7  jb      loc_180003143
0x1800031ed  mov     rbx, [rsp+38h+arg_10]
0x1800031f2  xor     eax, eax
0x1800031f4  add     rsp, 20h
0x1800031f8  pop     rdi
0x1800031f9  pop     rsi
0x1800031fa  pop     rbp
0x1800031fb  retn
0x1800031fc  mov     ecx, 80070057h; int
0x180003201  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
