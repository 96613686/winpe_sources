# ShareAccessControl::MapShareMode(_DS_SHARE_MODE,ulong *)

- ea: `0x18000fcd4`
- end: `0x18000fd94`
- name: `?MapShareMode@ShareAccessControl@@SAJW4_DS_SHARE_MODE@@PEAK@Z`
- size: `192`
- prototype: `__int64 __fastcall(int, int *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d3e4`
- `0x1800125c4`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000fcd4`

## string_xrefs

- `0x18000fd37`: `ShareAccessControl::MapShareMode`

## pseudocode

```c
__int64 __fastcall ShareAccessControl::MapShareMode(int a1, int *a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // ecx
  int v7; // ebx
  DSLogger *v8; // rax

  v6 = 0;
  if ( a1 )
  {
    switch ( a1 )
    {
      case 1:
        v7 = 1;
        break;
      case 2:
        v7 = 2;
        break;
      case 3:
        v7 = 3;
        break;
      case 4:
        v7 = 4;
        break;
      case 5:
        v7 = 5;
        break;
      case 6:
        v7 = 6;
        break;
      case 7:
        v7 = 7;
        break;
      default:
        v7 = 0;
        v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                           0,
                           a2,
                           (unsigned int)(a1 - 6),
                           a4);
        DSLogger::LogError(v8, L"ShareAccessControl::MapShareMode", 0x124u, L"Invalid share mode %d", a1);
        v6 = -2147024809;
        break;
    }
  }
  else
  {
    v7 = 0;
  }
  *a2 = v7;
  return v6;
}

```

## disassembly

```asm
0x18000fcd4  mov     [rsp+arg_0], rbx
0x18000fcd9  mov     [rsp+arg_8], rsi
0x18000fcde  push    rdi
0x18000fcdf  sub     rsp, 30h
0x18000fce3  mov     edi, ecx
0x18000fce5  mov     rsi, rdx
0x18000fce8  xor     ecx, ecx
0x18000fcea  mov     r8d, edi
0x18000fced  test    edi, edi
0x18000fcef  jz      loc_18000FD7E
0x18000fcf5  sub     r8d, 1
0x18000fcf9  jz      short loc_18000FD77
0x18000fcfb  sub     r8d, 1
0x18000fcff  jz      short loc_18000FD70
0x18000fd01  sub     r8d, 1
0x18000fd05  jz      short loc_18000FD69
0x18000fd07  sub     r8d, 1
0x18000fd0b  jz      short loc_18000FD62
0x18000fd0d  sub     r8d, 1
0x18000fd11  jz      short loc_18000FD5B
0x18000fd13  sub     r8d, 1
0x18000fd17  jz      short loc_18000FD54
0x18000fd19  cmp     r8d, 1
0x18000fd1d  jz      short loc_18000FD4D
0x18000fd1f  xor     ebx, ebx
0x18000fd21  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000fd26  lea     r9, aInvalidShareMo; "Invalid share mode %d"
0x18000fd2d  mov     [rsp+38h+var_18], edi
0x18000fd31  mov     r8d, 124h; unsigned int
0x18000fd37  lea     rdx, aShareaccesscon_0; "ShareAccessControl::MapShareMode"
0x18000fd3e  mov     rcx, rax; this
0x18000fd41  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000fd46  mov     ecx, 80070057h
0x18000fd4b  jmp     short loc_18000FD80
0x18000fd4d  mov     ebx, 7
0x18000fd52  jmp     short loc_18000FD80
0x18000fd54  mov     ebx, 6
0x18000fd59  jmp     short loc_18000FD80
0x18000fd5b  mov     ebx, 5
0x18000fd60  jmp     short loc_18000FD80
0x18000fd62  mov     ebx, 4
0x18000fd67  jmp     short loc_18000FD80
0x18000fd69  mov     ebx, 3
0x18000fd6e  jmp     short loc_18000FD80
0x18000fd70  mov     ebx, 2
0x18000fd75  jmp     short loc_18000FD80
0x18000fd77  mov     ebx, 1
0x18000fd7c  jmp     short loc_18000FD80
0x18000fd7e  xor     ebx, ebx
0x18000fd80  mov     [rsi], ebx
0x18000fd82  mov     eax, ecx
0x18000fd84  mov     rbx, [rsp+38h+arg_0]
0x18000fd89  mov     rsi, [rsp+38h+arg_8]
0x18000fd8e  add     rsp, 30h
0x18000fd92  pop     rdi
0x18000fd93  retn
```
