# NotifyCompletionOnBundledPorts

- ea: `0x180013c48`
- end: `0x180013cec`
- name: `NotifyCompletionOnBundledPorts`
- size: `164`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000e7a4`
- `0x18000ecac`

## callees

- `0x18000f984`
- `0x1800101bc`
- `0x1800139cc`
- `0x180013c48`
- `0x18001427c`

## pseudocode

```c
void __fastcall NotifyCompletionOnBundledPorts(__int64 a1)
{
  unsigned int v1; // r8d
  __int64 i; // rdi
  __int64 *v4; // rbx

  v1 = qword_18004D970;
  for ( i = 0; (unsigned int)i < v1; i = (unsigned int)(i + 1) )
  {
    v4 = (__int64 *)*((_QWORD *)PcbTable + i);
    if ( v4 )
    {
      do
      {
        if ( v4[2] != *(_QWORD *)(a1 + 16) && (v4[7] & 2) != 0 )
        {
          if ( (unsigned int)CanPortsBeBundled(v4, a1, 1) )
          {
            RemoveFromTimerQ(*((_DWORD *)v4 + 16), 0, 0, 0, 3);
            NotifyCallerOfBundledProjection(v4);
            StartAutoDisconnectForPort(v4);
          }
        }
        v4 = (__int64 *)*v4;
      }
      while ( v4 );
      v1 = qword_18004D970;
    }
  }
}

```

## disassembly

```asm
0x180013c48  mov     [rsp+arg_0], rbx
0x180013c4d  mov     [rsp+arg_8], rsi
0x180013c52  push    rdi
0x180013c53  sub     rsp, 30h
0x180013c57  mov     r8d, dword ptr cs:qword_18004D970
0x180013c5e  xor     edi, edi
0x180013c60  mov     rsi, rcx
0x180013c63  test    r8d, r8d
0x180013c66  jz      short loc_180013CDB
0x180013c68  mov     rax, qword ptr cs:PcbTable
0x180013c6f  mov     rbx, [rax+rdi*8]
0x180013c73  test    rbx, rbx
0x180013c76  jz      short loc_180013CD4
0x180013c78  mov     rax, [rsi+10h]
0x180013c7c  cmp     [rbx+10h], rax
0x180013c80  jz      short loc_180013CC5
0x180013c82  test    byte ptr [rbx+38h], 2
0x180013c86  jz      short loc_180013CC5
0x180013c88  mov     r8d, 1
0x180013c8e  mov     rdx, rsi
0x180013c91  mov     rcx, rbx
0x180013c94  call    CanPortsBeBundled
0x180013c99  test    eax, eax
0x180013c9b  jz      short loc_180013CC5
0x180013c9d  mov     ecx, [rbx+40h]
0x180013ca0  xor     r9d, r9d
0x180013ca3  xor     r8d, r8d
0x180013ca6  mov     [rsp+38h+var_18], 3
0x180013cae  xor     edx, edx
0x180013cb0  call    RemoveFromTimerQ
0x180013cb5  mov     rcx, rbx
0x180013cb8  call    NotifyCallerOfBundledProjection
0x180013cbd  mov     rcx, rbx
0x180013cc0  call    StartAutoDisconnectForPort
0x180013cc5  mov     rbx, [rbx]
0x180013cc8  test    rbx, rbx
0x180013ccb  jnz     short loc_180013C78
0x180013ccd  mov     r8d, dword ptr cs:qword_18004D970
0x180013cd4  inc     edi
0x180013cd6  cmp     edi, r8d
0x180013cd9  jb      short loc_180013C68
0x180013cdb  mov     rbx, [rsp+38h+arg_0]
0x180013ce0  mov     rsi, [rsp+38h+arg_8]
0x180013ce5  add     rsp, 30h
0x180013ce9  pop     rdi
0x180013cea  retn
```
