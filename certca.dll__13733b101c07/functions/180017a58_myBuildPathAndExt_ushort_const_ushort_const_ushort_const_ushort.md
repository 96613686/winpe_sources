# myBuildPathAndExt(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180017a58`
- end: `0x180017b1d`
- name: `?myBuildPathAndExt@@YAJPEBG00PEAPEAG@Z`
- size: `197`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019770`

## callees

- `0x180005f00`
- `0x180008400`
- `0x180008420`
- `0x180017a58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017aa1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017aa1`

## pseudocode

```c
__int64 __fastcall myBuildPathAndExt(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned int v13; // ebx

  v5 = -1;
  *a4 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = v9 + v6 + 2;
  v11 = (unsigned __int16 *)LocalAlloc(0, 2 * v10);
  v12 = v11;
  if ( v11 )
  {
    StringCchCopyW(v11, v10, a1);
    do
      ++v5;
    while ( v12[v5] );
    if ( v12[v5 - 1] != 92 )
      StringCchCatW(v12, v10, L"\\");
    StringCchCatW(v12, v10, a2);
    *a4 = v12;
    return 0;
  }
  else
  {
    v13 = -2147024882;
    CSPrintErrorLineFile(0x10D9019Au, -2147024882);
  }
  return v13;
}

```

## disassembly

```asm
0x180017a58  push    rbx
0x180017a5a  push    rbp
0x180017a5b  push    rsi
0x180017a5c  push    rdi
0x180017a5d  push    r12
0x180017a5f  push    r14
0x180017a61  push    r15
0x180017a63  sub     rsp, 20h
0x180017a67  xor     r12d, r12d
0x180017a6a  mov     r15, r9
0x180017a6d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180017a71  mov     [r9], r12
0x180017a74  mov     r8, rdi
0x180017a77  mov     r14, rdx
0x180017a7a  mov     rbp, rcx
0x180017a7d  inc     r8
0x180017a80  cmp     [rdx+r8*2], r12w
0x180017a85  jnz     short loc_180017A7D
0x180017a87  mov     rax, rdi
0x180017a8a  inc     rax
0x180017a8d  cmp     [rcx+rax*2], r12w
0x180017a92  jnz     short loc_180017A8A
0x180017a94  lea     rsi, [r8+2]
0x180017a98  xor     ecx, ecx; uFlags
0x180017a9a  add     rsi, rax
0x180017a9d  lea     rdx, [rsi+rsi]; uBytes
0x180017aa1  call    cs:__imp_LocalAlloc
0x180017aa7  mov     rbx, rax
0x180017aaa  test    rax, rax
0x180017aad  jnz     short loc_180017AC2
0x180017aaf  mov     ebx, 8007000Eh
0x180017ab4  mov     ecx, 10D9019Ah; unsigned int
0x180017ab9  mov     edx, ebx; int
0x180017abb  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017ac0  jmp     short loc_180017B0C
0x180017ac2  mov     r8, rbp; unsigned __int16 *
0x180017ac5  mov     rdx, rsi; unsigned __int64
0x180017ac8  mov     rcx, rbx; unsigned __int16 *
0x180017acb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017ad0  inc     rdi
0x180017ad3  cmp     [rbx+rdi*2], r12w
0x180017ad8  jnz     short loc_180017AD0
0x180017ada  mov     eax, 5Ch ; '\'
0x180017adf  cmp     ax, [rbx+rdi*2-2]
0x180017ae4  jz      short loc_180017AF8
0x180017ae6  lea     r8, asc_180061BD4; "\\"
0x180017aed  mov     rdx, rsi; unsigned __int64
0x180017af0  mov     rcx, rbx; unsigned __int16 *
0x180017af3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017af8  mov     r8, r14; unsigned __int16 *
0x180017afb  mov     rdx, rsi; unsigned __int64
0x180017afe  mov     rcx, rbx; unsigned __int16 *
0x180017b01  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017b06  mov     [r15], rbx
0x180017b09  mov     ebx, r12d
0x180017b0c  mov     eax, ebx
0x180017b0e  add     rsp, 20h
0x180017b12  pop     r15
0x180017b14  pop     r14
0x180017b16  pop     r12
0x180017b18  pop     rdi
0x180017b19  pop     rsi
0x180017b1a  pop     rbp
0x180017b1b  pop     rbx
0x180017b1c  retn
```
