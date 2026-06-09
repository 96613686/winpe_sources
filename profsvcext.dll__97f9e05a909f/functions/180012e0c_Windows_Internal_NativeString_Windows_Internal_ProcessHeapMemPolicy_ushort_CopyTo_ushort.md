# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)

- ea: `0x180012e0c`
- end: `0x180012e9c`
- name: `?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z`
- size: `144`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001375c`
- `0x180013938`

## callees

- `0x180005424`
- `0x180012e0c`
- `0x1800167e0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  int v5; // ebx
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+28h] [rbp-20h]
  __int64 v9; // [rsp+30h] [rbp-18h]

  *a2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    v4 = -1;
    v7 = 0;
    v8 = 0;
    v9 = 0;
    if ( a1[1] == -1 )
    {
      do
        ++v4;
      while ( *(_WORD *)(v3 + 2 * v4) );
    }
    else
    {
      v4 = a1[1];
    }
    v5 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
           &v7,
           v3,
           v4);
    if ( v5 >= 0 )
    {
      *a2 = v7;
      v7 = 0;
      v9 = 0;
      v8 = 0;
    }
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v7);
  }
  else
  {
    return (unsigned int)-2147023728;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012e0c  mov     rax, rsp
0x180012e0f  mov     [rax+8], rbx
0x180012e13  mov     [rax+10h], rsi
0x180012e17  push    rdi
0x180012e18  sub     rsp, 40h
0x180012e1c  xor     esi, esi
0x180012e1e  mov     rdi, rdx
0x180012e21  mov     [rdx], rsi
0x180012e24  mov     rdx, [rcx]
0x180012e27  test    rdx, rdx
0x180012e2a  jz      short loc_180012E85
0x180012e2c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012e30  mov     [rax-28h], rsi
0x180012e34  mov     [rax-20h], rsi
0x180012e38  mov     [rax-18h], rsi
0x180012e3c  cmp     [rcx+8], r8
0x180012e40  jnz     short loc_180012E4E
0x180012e42  inc     r8
0x180012e45  cmp     [rdx+r8*2], si
0x180012e4a  jnz     short loc_180012E42
0x180012e4c  jmp     short loc_180012E52
0x180012e4e  mov     r8, [rcx+8]
0x180012e52  lea     rcx, [rsp+48h+var_28]
0x180012e57  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180012e5c  mov     ebx, eax
0x180012e5e  test    eax, eax
0x180012e60  js      short loc_180012E79
0x180012e62  mov     rcx, [rsp+48h+var_28]
0x180012e67  mov     [rdi], rcx
0x180012e6a  mov     [rsp+48h+var_28], rsi
0x180012e6f  mov     [rsp+48h+var_18], rsi
0x180012e74  mov     [rsp+48h+var_20], rsi
0x180012e79  lea     rcx, [rsp+48h+var_28]
0x180012e7e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180012e83  jmp     short loc_180012E8A
0x180012e85  mov     ebx, 80070490h
0x180012e8a  mov     rsi, [rsp+48h+arg_8]
0x180012e8f  mov     eax, ebx
0x180012e91  mov     rbx, [rsp+48h+arg_0]
0x180012e96  add     rsp, 40h
0x180012e9a  pop     rdi
0x180012e9b  retn
```
