# SslLookupCachedNCryptProv

- ea: `0x1800115b0`
- end: `0x18001161e`
- name: `SslLookupCachedNCryptProv`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180023ac4`

## callees

- `0x1800115b0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001160c`
- `ntdll!RtlReleaseResource` at `0x18001160c`
- `ntdll!RtlAcquireResourceShared` at `0x1800115c7`
- `ntdll!RtlAcquireResourceShared` at `0x1800115c7`

## pseudocode

```c
__int64 __fastcall SslLookupCachedNCryptProv(__int64 a1, unsigned __int16 *a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // r9
  unsigned __int16 *v6; // rax
  int v7; // ecx
  int v8; // edx

  v4 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)(a1 + 24), 1u);
  v5 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    do
    {
      if ( v4 )
        break;
      v6 = a2;
      do
      {
        v7 = *(unsigned __int16 *)((char *)v6 + v5[1] - (_QWORD)a2);
        v8 = *v6 - v7;
        if ( v8 )
          break;
        ++v6;
      }
      while ( v7 );
      if ( !v8 )
        v4 = v5[2];
      v5 = (_QWORD *)*v5;
    }
    while ( v5 );
  }
  RtlReleaseResource((PRTL_RESOURCE)(a1 + 24));
  return v4;
}

```

## disassembly

```asm
0x1800115b0  push    rbx
0x1800115b2  push    rbp
0x1800115b3  push    rsi
0x1800115b4  push    rdi
0x1800115b5  sub     rsp, 28h
0x1800115b9  mov     rsi, rdx
0x1800115bc  mov     rbx, rcx
0x1800115bf  mov     dl, 1; Wait
0x1800115c1  add     rcx, 18h; Resource
0x1800115c5  xor     edi, edi
0x1800115c7  call    cs:__imp_RtlAcquireResourceShared
0x1800115cd  mov     r9, [rbx]
0x1800115d0  test    r9, r9
0x1800115d3  jz      short loc_180011608
0x1800115d5  test    rdi, rdi
0x1800115d8  jnz     short loc_180011608
0x1800115da  mov     r8, [r9+8]
0x1800115de  mov     rax, rsi
0x1800115e1  sub     r8, rsi
0x1800115e4  movzx   edx, word ptr [rax]
0x1800115e7  movzx   ecx, word ptr [rax+r8]
0x1800115ec  sub     edx, ecx
0x1800115ee  jnz     short loc_1800115F8
0x1800115f0  add     rax, 2
0x1800115f4  test    ecx, ecx
0x1800115f6  jnz     short loc_1800115E4
0x1800115f8  test    edx, edx
0x1800115fa  jnz     short loc_180011600
0x1800115fc  mov     rdi, [r9+10h]
0x180011600  mov     r9, [r9]
0x180011603  test    r9, r9
0x180011606  jnz     short loc_1800115D5
0x180011608  lea     rcx, [rbx+18h]; Resource
0x18001160c  call    cs:__imp_RtlReleaseResource
0x180011612  mov     rax, rdi
0x180011615  add     rsp, 28h
0x180011619  pop     rdi
0x18001161a  pop     rsi
0x18001161b  pop     rbp
0x18001161c  pop     rbx
0x18001161d  retn
```
