# SendStatusOnlyResponse

- ea: `0x140005044`
- end: `0x140005083`
- name: `SendStatusOnlyResponse`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000481c`
- `0x1400049c8`
- `0x140004cb0`
- `0x140004d80`

## callees

- `0x140001b90`
- `0x140005044`

## pseudocode

```c
int __fastcall SendStatusOnlyResponse(__int64 *a1, int a2)
{
  __int64 v2; // rax
  __int64 InputBuffer; // [rsp+30h] [rbp-18h] BYREF
  int v5; // [rsp+38h] [rbp-10h]
  int v6; // [rsp+3Ch] [rbp-Ch]

  if ( a1 )
  {
    v2 = *a1;
    if ( *a1 )
    {
      InputBuffer = *a1;
      v5 = a2;
      v6 = 0;
      LODWORD(v2) = LsapCallKsec(0x39006Fu, &InputBuffer, 0x10u, 0, 0);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140005044  sub     rsp, 48h
0x140005048  test    rcx, rcx
0x14000504b  jz      short loc_14000507E
0x14000504d  mov     rax, [rcx]
0x140005050  test    rax, rax
0x140005053  jz      short loc_14000507E
0x140005055  mov     [rsp+48h+InputBuffer], rax
0x14000505a  xor     r9d, r9d; OutputBuffer
0x14000505d  xor     eax, eax
0x14000505f  mov     [rsp+48h+var_10], edx
0x140005063  lea     rdx, [rsp+48h+InputBuffer]; InputBuffer
0x140005068  mov     [rsp+48h+var_C], eax
0x14000506c  mov     ecx, 39006Fh; IoControlCode
0x140005071  mov     [rsp+48h+var_28], eax; ULONG
0x140005075  lea     r8d, [rax+10h]; InputBufferLength
0x140005079  call    LsapCallKsec
0x14000507e  add     rsp, 48h
0x140005082  retn
```
