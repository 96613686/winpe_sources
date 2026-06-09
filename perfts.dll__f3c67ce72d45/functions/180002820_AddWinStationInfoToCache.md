# AddWinStationInfoToCache

- ea: `0x180002820`
- end: `0x180002892`
- name: `AddWinStationInfoToCache`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002990`

## callees

- `0x180002820`
- `0x180003314`

## pseudocode

```c
void __fastcall AddWinStationInfoToCache(__int64 a1)
{
  char *v1; // r8
  __int64 v2; // rax
  int v3; // eax
  unsigned int v4; // eax
  char v5; // cl

  v1 = (char *)pWinStationHashBuckets + 16 * ((unsigned int)WinStationHashMask & *(_DWORD *)(a1 + 32));
  v2 = *(_QWORD *)v1;
  if ( *(char **)(*(_QWORD *)v1 + 8LL) != v1 )
    __fastfail(3u);
  *(_QWORD *)a1 = v2;
  *(_QWORD *)(a1 + 8) = v1;
  *(_QWORD *)(v2 + 8) = a1;
  v3 = NumCachedWinStations + 1;
  *(_QWORD *)v1 = a1;
  NumCachedWinStations = v3;
  v4 = 4 * v3;
  v5 = 0;
  while ( v4 > 1 )
  {
    v4 >>= 1;
    ++v5;
  }
  if ( NumWinStationHashBuckets < (unsigned int)(1 << v5) )
    CreateNewHashBuckets(1 << v5);
}

```

## disassembly

```asm
0x180002820  sub     rsp, 28h
0x180002824  mov     eax, cs:WinStationHashMask
0x18000282a  mov     r8d, [rcx+20h]
0x18000282e  and     r8, rax
0x180002831  shl     r8, 4
0x180002835  add     r8, cs:pWinStationHashBuckets
0x18000283c  mov     rax, [r8]
0x18000283f  cmp     [rax+8], r8
0x180002843  jz      short loc_18000284C
0x180002845  mov     ecx, 3
0x18000284a  int     29h; Win8: RtlFailFast(ecx)
0x18000284c  mov     [rcx], rax
0x18000284f  mov     edx, 1
0x180002854  mov     [rcx+8], r8
0x180002858  mov     [rax+8], rcx
0x18000285c  mov     eax, cs:NumCachedWinStations
0x180002862  add     eax, edx
0x180002864  mov     [r8], rcx
0x180002867  mov     cs:NumCachedWinStations, eax
0x18000286d  shl     eax, 2
0x180002870  xor     ecx, ecx
0x180002872  jmp     short loc_180002878
0x180002874  shr     eax, 1
0x180002876  add     ecx, edx
0x180002878  cmp     eax, edx
0x18000287a  ja      short loc_180002874
0x18000287c  shl     edx, cl
0x18000287e  cmp     cs:NumWinStationHashBuckets, edx
0x180002884  jnb     short loc_18000288D
0x180002886  mov     ecx, edx
0x180002888  call    CreateNewHashBuckets
0x18000288d  add     rsp, 28h
0x180002891  retn
```
