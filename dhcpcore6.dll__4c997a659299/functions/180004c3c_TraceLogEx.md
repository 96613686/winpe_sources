# TraceLogEx

- ea: `0x180004c3c`
- end: `0x180004cf8`
- name: `TraceLogEx`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18000490c`
- `0x180004b30`
- `0x180004d78`
- `0x180005368`
- `0x180006904`
- `0x180010340`
- `0x1800108f0`
- `0x18001225c`
- `0x180012634`
- `0x18001b314`
- `0x18001e110`
- `0x1800225c8`
- `0x180022b80`
- `0x180023344`
- `0x180023dc0`
- `0x18002458c`
- `0x180025094`

## callees

- `0x180004c3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004ce6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004ce6`

## pseudocode

```c
void __fastcall TraceLogEx(_OWORD *a1)
{
  __int64 v1; // rdx
  __int64 v2; // r9
  __int64 v3; // r8
  _OWORD *v4; // rax
  __int128 v5; // xmm1

  v1 = Dhcpv6GlobalTraceExArray;
  if ( Dhcpv6GlobalTraceExArray )
  {
    v2 = 2;
    v3 = 320LL
       * (((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)Dhcpv6GlobalTraceExArray, 1u) + 1) & 0x7F);
    v4 = (_OWORD *)(v3 + v1 + 8);
    do
    {
      *v4 = *a1;
      v4[1] = a1[1];
      v4[2] = a1[2];
      v4[3] = a1[3];
      v4[4] = a1[4];
      v4[5] = a1[5];
      v4[6] = a1[6];
      v5 = a1[7];
      a1 += 8;
      v4[7] = v5;
      v4 += 8;
      --v2;
    }
    while ( v2 );
    *v4 = *a1;
    v4[1] = a1[1];
    v4[2] = a1[2];
    v4[3] = a1[3];
    GetSystemTimeAsFileTime((LPFILETIME)(v3 + v1 + 12));
  }
}

```

## disassembly

```asm
0x180004c3c  sub     rsp, 28h
0x180004c40  mov     rdx, cs:Dhcpv6GlobalTraceExArray
0x180004c47  test    rdx, rdx
0x180004c4a  jz      loc_180004CF2
0x180004c50  mov     eax, 1
0x180004c55  lock xadd [rdx], eax
0x180004c59  inc     eax
0x180004c5b  mov     r9d, 2
0x180004c61  and     eax, 7Fh
0x180004c64  lea     r10d, [r9+7Eh]
0x180004c68  lea     r8, [rax+rax*4]
0x180004c6c  shl     r8, 6
0x180004c70  lea     rax, [rdx+8]
0x180004c74  add     rax, r8
0x180004c77  movups  xmm0, xmmword ptr [rcx]
0x180004c7a  movups  xmmword ptr [rax], xmm0
0x180004c7d  movups  xmm1, xmmword ptr [rcx+10h]
0x180004c81  movups  xmmword ptr [rax+10h], xmm1
0x180004c85  movups  xmm0, xmmword ptr [rcx+20h]
0x180004c89  movups  xmmword ptr [rax+20h], xmm0
0x180004c8d  movups  xmm1, xmmword ptr [rcx+30h]
0x180004c91  movups  xmmword ptr [rax+30h], xmm1
0x180004c95  movups  xmm0, xmmword ptr [rcx+40h]
0x180004c99  movups  xmmword ptr [rax+40h], xmm0
0x180004c9d  movups  xmm1, xmmword ptr [rcx+50h]
0x180004ca1  movups  xmmword ptr [rax+50h], xmm1
0x180004ca5  movups  xmm0, xmmword ptr [rcx+60h]
0x180004ca9  movups  xmmword ptr [rax+60h], xmm0
0x180004cad  movups  xmm1, xmmword ptr [rcx+70h]
0x180004cb1  add     rcx, r10
0x180004cb4  movups  xmmword ptr [rax+70h], xmm1
0x180004cb8  add     rax, r10
0x180004cbb  sub     r9, 1
0x180004cbf  jnz     short loc_180004C77
0x180004cc1  movups  xmm0, xmmword ptr [rcx]
0x180004cc4  movups  xmmword ptr [rax], xmm0
0x180004cc7  movups  xmm1, xmmword ptr [rcx+10h]
0x180004ccb  movups  xmmword ptr [rax+10h], xmm1
0x180004ccf  movups  xmm0, xmmword ptr [rcx+20h]
0x180004cd3  movups  xmmword ptr [rax+20h], xmm0
0x180004cd7  movups  xmm1, xmmword ptr [rcx+30h]
0x180004cdb  lea     rcx, [rdx+0Ch]
0x180004cdf  add     rcx, r8; lpSystemTimeAsFileTime
0x180004ce2  movups  xmmword ptr [rax+30h], xmm1
0x180004ce6  call    cs:__imp_GetSystemTimeAsFileTime
0x180004ced  nop     dword ptr [rax+rax+00h]
0x180004cf2  add     rsp, 28h
0x180004cf6  retn
```
