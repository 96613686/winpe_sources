# PrjfFilterCommandReplyStatus

- ea: `0x14002fda4`
- end: `0x14002fe58`
- name: `PrjfFilterCommandReplyStatus`
- size: `180`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140033de8`

## callees

- `0x140010594`
- `0x14002fda4`

## pseudocode

```c
__int64 __fastcall PrjfFilterCommandReplyStatus(__int64 a1, int a2)
{
  int v2; // r8d

  if ( *(_DWORD *)(a1 + 4) != 7 )
    return (unsigned int)a2;
  v2 = *(_DWORD *)(a1 + 324) - 2;
  if ( *(_DWORD *)(a1 + 324) != 2 )
  {
    v2 = *(_DWORD *)(a1 + 324) - 4;
    if ( *(_DWORD *)(a1 + 324) != 4 )
    {
      v2 = *(_DWORD *)(a1 + 324) - 8;
      if ( *(_DWORD *)(a1 + 324) != 8 )
      {
        v2 = *(_DWORD *)(a1 + 324) - 128;
        if ( *(_DWORD *)(a1 + 324) != 128 )
        {
          v2 = *(_DWORD *)(a1 + 324) - 256;
          if ( *(_DWORD *)(a1 + 324) != 256 )
          {
            v2 = *(_DWORD *)(a1 + 324) - 512;
            if ( *(_DWORD *)(a1 + 324) != 512 )
            {
              v2 = *(_DWORD *)(a1 + 324) - 1024;
              if ( *(_DWORD *)(a1 + 324) != 1024 && *(_DWORD *)(a1 + 324) != 2048 )
                return (unsigned int)a2;
            }
          }
        }
      }
    }
  }
  if ( a2 < 0
    && ((BYTE9(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
  {
    LOBYTE(a2) = BYTE9(xmmword_14001A3D0) & 0x40;
    LOBYTE(a1) = BYTE9(xmmword_14001A3D0) & 0x40;
    LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDdLLl(a1, a2, v2, *((_QWORD *)WPP_GLOBAL_Control + 8));
  }
  return 0;
}

```

## disassembly

```asm
0x14002fda4  sub     rsp, 78h
0x14002fda8  cmp     dword ptr [rcx+4], 7
0x14002fdac  mov     r9, rcx
0x14002fdaf  jnz     loc_14002FE50
0x14002fdb5  mov     r10d, [rcx+144h]
0x14002fdbc  mov     r8d, r10d
0x14002fdbf  sub     r8d, 2
0x14002fdc3  jz      short loc_14002FDFB
0x14002fdc5  sub     r8d, 2
0x14002fdc9  jz      short loc_14002FDFB
0x14002fdcb  sub     r8d, 4
0x14002fdcf  jz      short loc_14002FDFB
0x14002fdd1  sub     r8d, 78h ; 'x'
0x14002fdd5  jz      short loc_14002FDFB
0x14002fdd7  sub     r8d, 80h
0x14002fdde  jz      short loc_14002FDFB
0x14002fde0  sub     r8d, 100h
0x14002fde7  jz      short loc_14002FDFB
0x14002fde9  sub     r8d, 200h
0x14002fdf0  jz      short loc_14002FDFB
0x14002fdf2  cmp     r8d, 400h
0x14002fdf9  jnz     short loc_14002FE50
0x14002fdfb  test    edx, edx
0x14002fdfd  jns     short loc_14002FE4C
0x14002fdff  mov     cl, byte ptr cs:xmmword_14001A3D0+9
0x14002fe05  lea     rax, WPP_RECORDER_INITIALIZED
0x14002fe0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002fe13  setnz   r8b
0x14002fe17  and     cl, 40h
0x14002fe1a  jnz     short loc_14002FE21
0x14002fe1c  test    r8b, r8b
0x14002fe1f  jz      short loc_14002FE4C
0x14002fe21  mov     eax, [r9+18h]
0x14002fe25  mov     r9, cs:WPP_GLOBAL_Control
0x14002fe2c  mov     [rsp+78h+var_10], eax
0x14002fe30  mov     [rsp+78h+var_18], r10d
0x14002fe35  mov     [rsp+78h+var_20], 7
0x14002fe3d  mov     r9, [r9+40h]
0x14002fe41  mov     [rsp+78h+var_28], edx
0x14002fe45  mov     dl, cl
0x14002fe47  call    WPP_RECORDER_AND_TRACE_SF_sDdLLl
0x14002fe4c  xor     eax, eax
0x14002fe4e  jmp     short loc_14002FE52
0x14002fe50  mov     eax, edx
0x14002fe52  add     rsp, 78h
0x14002fe56  retn
```
