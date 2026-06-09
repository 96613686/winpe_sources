# GetTempBuffer

- ea: `0x14000cf88`
- end: `0x14000d009`
- name: `GetTempBuffer`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000c6d0`
- `0x14000d4cc`
- `0x14000d5c4`

## callees

- `0x14000caa8`
- `0x14000cf88`
- `0x14000e838`
- `0x14000e87c`
- `0x14000e8c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000cfe3`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000cfe3`

## pseudocode

```c
__int64 __fastcall GetTempBuffer(__int64 a1, WCHAR *a2, unsigned int a3, int a4)
{
  unsigned int Count2; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // r11d
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // r11d
  __int64 v11; // rax
  __int64 v12; // rbx

  if ( a2 || a3 || a4 )
    return GetInternalTemporaryBuffer(a1, a2, a3, a4);
  if ( g_bInitialized )
  {
    Count2 = DynArrayGetCount2(a1, 3);
    if ( Count2 > v7 )
    {
      if ( (unsigned int)DynArrayGetItemType2(v6, v5, v7) )
      {
        v11 = DynArrayItem2(v9, v8, v10);
        v12 = v11;
        if ( v11 )
        {
          if ( !(unsigned int)_o__memicmp(v11, "BUFFER", 7) )
            return *(_QWORD *)(v12 + 16);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000cf88  push    rbx
0x14000cf8a  sub     rsp, 20h
0x14000cf8e  mov     r11d, ecx
0x14000cf91  test    rdx, rdx
0x14000cf94  jnz     short loc_14000CFFF
0x14000cf96  test    r8d, r8d
0x14000cf99  jnz     short loc_14000CFFF
0x14000cf9b  test    r9d, r9d
0x14000cf9e  jnz     short loc_14000CFFF
0x14000cfa0  cmp     cs:g_bInitialized, r9d
0x14000cfa7  jz      short loc_14000CFF7
0x14000cfa9  lea     edx, [r8+3]
0x14000cfad  call    DynArrayGetCount2
0x14000cfb2  cmp     eax, r11d
0x14000cfb5  jbe     short loc_14000CFF7
0x14000cfb7  mov     r8d, r11d
0x14000cfba  call    DynArrayGetItemType2
0x14000cfbf  test    eax, eax
0x14000cfc1  jz      short loc_14000CFF7
0x14000cfc3  mov     r8d, r11d
0x14000cfc6  call    DynArrayItem2
0x14000cfcb  mov     rbx, rax
0x14000cfce  test    rax, rax
0x14000cfd1  jz      short loc_14000CFF7
0x14000cfd3  mov     r8d, 7
0x14000cfd9  lea     rdx, cszSignature; "BUFFER"
0x14000cfe0  mov     rcx, rax
0x14000cfe3  call    cs:__imp__o__memicmp
0x14000cfe9  test    eax, eax
0x14000cfeb  jnz     short loc_14000CFF7
0x14000cfed  mov     rax, [rbx+10h]
0x14000cff1  add     rsp, 20h
0x14000cff5  pop     rbx
0x14000cff6  retn
0x14000cff7  xor     eax, eax
0x14000cff9  add     rsp, 20h
0x14000cffd  pop     rbx
0x14000cffe  retn
0x14000cfff  add     rsp, 20h
0x14000d003  pop     rbx
0x14000d004  jmp     GetInternalTemporaryBuffer
```
