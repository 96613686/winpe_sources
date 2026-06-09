# OncRpcCopyAddress

- ea: `0x14000bab0`
- end: `0x14000bae2`
- name: `OncRpcCopyAddress`
- size: `50`
- prototype: `__int64 __fastcall(_OWORD *, _OWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140009f60`
- `0x14000adb0`

## callees

- `0x14000bab0`

## pseudocode

```c
__int64 __fastcall OncRpcCopyAddress(_OWORD *a1, _OWORD *a2)
{
  __int64 result; // rax

  result = *(unsigned __int16 *)a2;
  if ( (_WORD)result == 2 )
  {
    *a1 = *a2;
  }
  else if ( (_WORD)result == 23 )
  {
    *a1 = *a2;
    *(_OWORD *)((char *)a1 + 12) = *(_OWORD *)((char *)a2 + 12);
  }
  else
  {
    *a1 = 0;
    *(_OWORD *)((char *)a1 + 12) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000bab0  movzx   eax, word ptr [rdx]
0x14000bab3  cmp     ax, 2
0x14000bab7  jz      short loc_14000BADB
0x14000bab9  cmp     ax, 17h
0x14000babd  jz      short loc_14000BACB
0x14000babf  xorps   xmm0, xmm0
0x14000bac2  movups  xmmword ptr [rcx], xmm0
0x14000bac5  movups  xmmword ptr [rcx+0Ch], xmm0
0x14000bac9  retn
0x14000bacb  movups  xmm0, xmmword ptr [rdx]
0x14000bace  movups  xmmword ptr [rcx], xmm0
0x14000bad1  movups  xmm1, xmmword ptr [rdx+0Ch]
0x14000bad5  movups  xmmword ptr [rcx+0Ch], xmm1
0x14000bad9  retn
0x14000badb  movups  xmm0, xmmword ptr [rdx]
0x14000bade  movups  xmmword ptr [rcx], xmm0
0x14000bae1  retn
```
