# CCursor::Move(ulong)

- ea: `0x14000ca60`
- end: `0x14000caef`
- name: `?Move@CCursor@@QEAAJK@Z`
- size: `143`
- prototype: `__int64 __fastcall(CCursor *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a220`

## callees

- `0x14000c7b8`
- `0x14000ca40`
- `0x14000ca60`

## pseudocode

```c
__int64 __fastcall CCursor::Move(CCursor *this, int a2)
{
  __int64 result; // rax
  CCursor *v3; // r8
  CCursor *v4; // r8
  int v5; // eax
  unsigned int v6; // ecx
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  if ( !a2 || a2 == 1073742112 || a2 == 0x80000000 )
  {
    if ( CCursor::Current(this) )
    {
      return 0;
    }
    else
    {
      v5 = CCursor::Advance(v4, &v7);
      v6 = 0;
      if ( v5 < 0 )
        return (unsigned int)v5;
      return v6;
    }
  }
  else if ( a2 == -2147483647 )
  {
    if ( CCursor::Current(this) )
    {
      result = CCursor::Advance(v3, &v7);
      if ( (int)result >= 0 )
        return v7 == 0 ? 0x8000001A : 0;
    }
    else
    {
      return 3222143004LL;
    }
  }
  else
  {
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x14000ca60  sub     rsp, 28h
0x14000ca64  mov     [rsp+28h+arg_8], 0
0x14000ca6c  mov     r8, rcx
0x14000ca6f  test    edx, edx
0x14000ca71  jz      short loc_14000CAC5
0x14000ca73  cmp     edx, 40000120h
0x14000ca79  jz      short loc_14000CAC5
0x14000ca7b  cmp     edx, 80000000h
0x14000ca81  jz      short loc_14000CAC5
0x14000ca83  cmp     edx, 80000001h
0x14000ca89  jz      short loc_14000CA92
0x14000ca8b  mov     eax, 0C000000Dh
0x14000ca90  jmp     short loc_14000CAE9
0x14000ca92  call    ?Current@CCursor@@QEAAPEAVCPacket@@XZ; CCursor::Current(void)
0x14000ca97  test    rax, rax
0x14000ca9a  jnz     short loc_14000CAA3
0x14000ca9c  mov     eax, 0C00E001Ch
0x14000caa1  jmp     short loc_14000CAE9
0x14000caa3  lea     rdx, [rsp+28h+arg_8]; int *
0x14000caa8  mov     rcx, r8; this
0x14000caab  call    ?Advance@CCursor@@AEAAJPEAH@Z; CCursor::Advance(int *)
0x14000cab0  test    eax, eax
0x14000cab2  js      short loc_14000CAE9
0x14000cab4  mov     eax, [rsp+28h+arg_8]
0x14000cab8  neg     eax
0x14000caba  sbb     eax, eax
0x14000cabc  not     eax
0x14000cabe  and     eax, 8000001Ah
0x14000cac3  jmp     short loc_14000CAE9
0x14000cac5  call    ?Current@CCursor@@QEAAPEAVCPacket@@XZ; CCursor::Current(void)
0x14000caca  test    rax, rax
0x14000cacd  jnz     short loc_14000CAE7
0x14000cacf  lea     rdx, [rsp+28h+arg_8]; int *
0x14000cad4  mov     rcx, r8; this
0x14000cad7  call    ?Advance@CCursor@@AEAAJPEAH@Z; CCursor::Advance(int *)
0x14000cadc  xor     ecx, ecx
0x14000cade  test    eax, eax
0x14000cae0  cmovs   ecx, eax
0x14000cae3  mov     eax, ecx
0x14000cae5  jmp     short loc_14000CAE9
0x14000cae7  xor     eax, eax
0x14000cae9  add     rsp, 28h
0x14000caed  retn
```
